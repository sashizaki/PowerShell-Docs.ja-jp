---
ms.date: 05/14/2020
keywords: powershell,コマンドレット
title: PowerShell リモート処理での次ホップの実行
ms.openlocfilehash: 3a9db11726d4c02dc69e52c45da304f7422def39
ms.sourcegitcommit: 843756c8277e7afb874867703963248abc8a6c91
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "83439378"
---
# <a name="making-the-second-hop-in-powershell-remoting"></a><span data-ttu-id="4bba7-103">PowerShell リモート処理での次ホップの実行</span><span class="sxs-lookup"><span data-stu-id="4bba7-103">Making the second hop in PowerShell Remoting</span></span>

<span data-ttu-id="4bba7-104">"次ホップの問題" とは次のような状況のことです。</span><span class="sxs-lookup"><span data-stu-id="4bba7-104">The "second hop problem" refers to a situation like the following:</span></span>

1. <span data-ttu-id="4bba7-105">_ServerA_ にログインしています。</span><span class="sxs-lookup"><span data-stu-id="4bba7-105">You are logged in to _ServerA_.</span></span>
2. <span data-ttu-id="4bba7-106">_ServerA_ からリモート PowerShell セッションを開始して _ServerB_ に接続します。</span><span class="sxs-lookup"><span data-stu-id="4bba7-106">From _ServerA_, you start a remote PowerShell session to connect to _ServerB_.</span></span>
3. <span data-ttu-id="4bba7-107">PowerShell リモート処理セッションを介して _ServerB_ で実行するコマンドは、_ServerC_ 上のリソースにアクセスを試みます。</span><span class="sxs-lookup"><span data-stu-id="4bba7-107">A command you run on _ServerB_ via your PowerShell Remoting session attempts to access a resource on _ServerC_.</span></span>
4. <span data-ttu-id="4bba7-108">PowerShell リモート処理セッションの作成に使った資格情報は _ServerB_ から _ServerC_ に渡されないため、_ServerC_ 上のリソースへのアクセスは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="4bba7-108">Access to the resource on _ServerC_ is denied, because the credentials you used to create the PowerShell Remoting session are not passed from _ServerB_ to _ServerC_.</span></span>

<span data-ttu-id="4bba7-109">この問題に対処する方法はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="4bba7-109">There are several ways to address this problem.</span></span> <span data-ttu-id="4bba7-110">次の表に、優先順位順に方法の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="4bba7-110">The following table lists the methods in order of preference.</span></span>

|                      <span data-ttu-id="4bba7-111">構成</span><span class="sxs-lookup"><span data-stu-id="4bba7-111">Configuration</span></span>                       |                                  <span data-ttu-id="4bba7-112">Note</span><span class="sxs-lookup"><span data-stu-id="4bba7-112">Note</span></span>                                  |
| -------------------------------------------------------- | ---------------------------------------------------------------------- |
| <span data-ttu-id="4bba7-113">CredSSP</span><span class="sxs-lookup"><span data-stu-id="4bba7-113">CredSSP</span></span>                                                  | <span data-ttu-id="4bba7-114">使いやすさとセキュリティのバランスが取れている</span><span class="sxs-lookup"><span data-stu-id="4bba7-114">Balances ease of use and security</span></span>                                      |
| <span data-ttu-id="4bba7-115">リソースに基づく Kerberos の制約付き委任</span><span class="sxs-lookup"><span data-stu-id="4bba7-115">Resource-based Kerberos constrained delegation</span></span>           | <span data-ttu-id="4bba7-116">単純な構成で高いセキュリティ</span><span class="sxs-lookup"><span data-stu-id="4bba7-116">Higher security with simpler configuration</span></span>                             |
| <span data-ttu-id="4bba7-117">Kerberos の制約付き委任</span><span class="sxs-lookup"><span data-stu-id="4bba7-117">Kerberos constrained delegation</span></span>                          | <span data-ttu-id="4bba7-118">セキュリティは高いが、ドメイン管理者が必要</span><span class="sxs-lookup"><span data-stu-id="4bba7-118">High security but requires Domain Administrator</span></span>                         |
| <span data-ttu-id="4bba7-119">Kerberos の委任 (無制限)</span><span class="sxs-lookup"><span data-stu-id="4bba7-119">Kerberos delegation (unconstrained)</span></span>                      | <span data-ttu-id="4bba7-120">推奨されません</span><span class="sxs-lookup"><span data-stu-id="4bba7-120">Not recommended</span></span>                                                        |
| <span data-ttu-id="4bba7-121">Just Enough Administration (JEA)</span><span class="sxs-lookup"><span data-stu-id="4bba7-121">Just Enough Administration (JEA)</span></span>                         | <span data-ttu-id="4bba7-122">セキュリティは最も高いが、より詳細な構成が必要</span><span class="sxs-lookup"><span data-stu-id="4bba7-122">Can provide the best security but requires more detailed configuration</span></span> |
| <span data-ttu-id="4bba7-123">RunAs を使用する PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4bba7-123">PSSessionConfiguration using RunAs</span></span>                       | <span data-ttu-id="4bba7-124">簡単に構成できるが、資格情報の管理が必要</span><span class="sxs-lookup"><span data-stu-id="4bba7-124">Simpler to configure but requires credential management</span></span>                |
| <span data-ttu-id="4bba7-125">`Invoke-Command` スクリプト ブロックの内部で資格情報を渡す</span><span class="sxs-lookup"><span data-stu-id="4bba7-125">Pass credentials inside an `Invoke-Command` script block</span></span> | <span data-ttu-id="4bba7-126">最も簡単に使用できるが、資格情報を指定する必要がある</span><span class="sxs-lookup"><span data-stu-id="4bba7-126">Simplest to use but you must provide credentials</span></span>                       |

## <a name="credssp"></a><span data-ttu-id="4bba7-127">CredSSP</span><span class="sxs-lookup"><span data-stu-id="4bba7-127">CredSSP</span></span>

<span data-ttu-id="4bba7-128">認証に[資格情報のセキュリティ サポート プロバイダー (CredSSP)][credssp] を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4bba7-128">You can use the [Credential Security Support Provider (CredSSP)][credssp] for authentication.</span></span>
<span data-ttu-id="4bba7-129">CredSSP はリモート サーバー (_ServerB_) に資格情報をキャッシュするため、これを使用すると資格情報の盗難攻撃にさらされます。</span><span class="sxs-lookup"><span data-stu-id="4bba7-129">CredSSP caches credentials on the remote server (_ServerB_), so using it opens you up to credential theft attacks.</span></span> <span data-ttu-id="4bba7-130">リモート コンピューターが侵害されると、攻撃者はユーザーの資格情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4bba7-130">If the remote computer is compromised, the attacker has access to the user's credentials.</span></span> <span data-ttu-id="4bba7-131">CredSSP は、既定では、クライアント コンピューターとサーバー コンピューターの両方で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="4bba7-131">CredSSP is disabled by default on both client and server computers.</span></span> <span data-ttu-id="4bba7-132">CredSSP は、最も信頼性の高い環境でのみ有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="4bba7-132">You should enable CredSSP only in the most trusted environments.</span></span> <span data-ttu-id="4bba7-133">たとえば、ドメイン コントローラーは信頼性が高いため、ドメイン コントローラーに接続しているドメイン管理者が有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4bba7-133">For example, a domain administrator connecting to a domain controller because the domain controller is highly trusted.</span></span>

<span data-ttu-id="4bba7-134">PowerShell リモート処理で CredSSP を使用する場合のセキュリティに関する注意事項の詳細については、「[Accidental Sabotage: Beware of CredSSP (予想外の妨害行為: CredSSP に関する注意事項)][beware]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bba7-134">For more information about security concerns when using CredSSP for PowerShell Remoting, see [Accidental Sabotage: Beware of CredSSP][beware].</span></span>

<span data-ttu-id="4bba7-135">資格情報の盗難攻撃の詳細については、「[Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft (Pass-the-Hash (PtH) 攻撃とその他の資格情報の盗難の抑制)][pth]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bba7-135">For more information about credential theft attacks, see [Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft][pth].</span></span>

<span data-ttu-id="4bba7-136">PowerShell リモート処理用に CredSSP を有効にして使用する方法の例については、「[CredSSP を使用して PowerShell "次ホップ" 機能を有効にする][credssp-psblog]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4bba7-136">For an example of how to enable and use CredSSP for PowerShell remoting, see [Enable PowerShell "Second-Hop" Functionality with CredSSP][credssp-psblog].</span></span>

<span data-ttu-id="4bba7-137">**長所**</span><span class="sxs-lookup"><span data-stu-id="4bba7-137">**Pros**</span></span>

- <span data-ttu-id="4bba7-138">Windows Server 2008 以降のすべてのサーバーで機能します。</span><span class="sxs-lookup"><span data-stu-id="4bba7-138">It works for all servers with Windows Server 2008 or later.</span></span>

<span data-ttu-id="4bba7-139">**短所**</span><span class="sxs-lookup"><span data-stu-id="4bba7-139">**Cons**</span></span>

- <span data-ttu-id="4bba7-140">セキュリティの脆弱性があります。</span><span class="sxs-lookup"><span data-stu-id="4bba7-140">Has security vulnerabilities.</span></span>
- <span data-ttu-id="4bba7-141">クライアント ロールとサーバー ロールの両方の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="4bba7-141">Requires configuration of both client and server roles.</span></span>
- <span data-ttu-id="4bba7-142">Protected Users グループでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="4bba7-142">Does not work with the Protected Users group.</span></span> <span data-ttu-id="4bba7-143">詳細については、「[Protected Users セキュリティ グループ][protected-users]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4bba7-143">For more information, see [Protected Users Security Group][protected-users].</span></span>

## <a name="kerberos-constrained-delegation"></a><span data-ttu-id="4bba7-144">Kerberos の制約付き委任</span><span class="sxs-lookup"><span data-stu-id="4bba7-144">Kerberos constrained delegation</span></span>

<span data-ttu-id="4bba7-145">従来の (リソースに基づかない) 制約付き委任を使って、次ホップを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4bba7-145">You can use legacy constrained delegation (not resource-based) to make the second hop.</span></span> <span data-ttu-id="4bba7-146">プロトコル遷移を許可するには、[任意の認証プロトコルを使う] オプションを使用して Kerberos の制約付き委任を構成します。</span><span class="sxs-lookup"><span data-stu-id="4bba7-146">Configure Kerberos constrained delegation with the option "Use any authentication protocol" to allow protocol transition.</span></span>

<span data-ttu-id="4bba7-147">**長所**</span><span class="sxs-lookup"><span data-stu-id="4bba7-147">**Pros**</span></span>

- <span data-ttu-id="4bba7-148">特別なコーディングが必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4bba7-148">Requires no special coding</span></span>
- <span data-ttu-id="4bba7-149">資格情報が保存されません。</span><span class="sxs-lookup"><span data-stu-id="4bba7-149">Credentials are not stored.</span></span>

<span data-ttu-id="4bba7-150">**短所**</span><span class="sxs-lookup"><span data-stu-id="4bba7-150">**Cons**</span></span>

- <span data-ttu-id="4bba7-151">WinRM の次ホップはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="4bba7-151">Does not support the second hop for WinRM.</span></span>
- <span data-ttu-id="4bba7-152">構成には、ドメイン管理者のアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="4bba7-152">Requires Domain Administrator access to configure.</span></span>
- <span data-ttu-id="4bba7-153">リモート サーバー (_ServerB_) の Active Directory オブジェクトで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bba7-153">Must be configured on the Active Directory object of the remote server (_ServerB_).</span></span>
- <span data-ttu-id="4bba7-154">1 つのドメインに制限されます。</span><span class="sxs-lookup"><span data-stu-id="4bba7-154">Limited to one domain.</span></span> <span data-ttu-id="4bba7-155">複数のドメインまたはフォレストにまたがることはできません。</span><span class="sxs-lookup"><span data-stu-id="4bba7-155">Cannot cross domains or forests.</span></span>
- <span data-ttu-id="4bba7-156">オブジェクトとサービス プリンシパル名 (SPN) を更新する権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="4bba7-156">Requires rights to update objects and Service Principal Names (SPNs).</span></span>
- <span data-ttu-id="4bba7-157">_ServerB_ は、ユーザーの介入なしに、ユーザーに代わって _ServerC_ への Kerberos チケットを取得できます。</span><span class="sxs-lookup"><span data-stu-id="4bba7-157">_ServerB_ can acquire a Kerberos ticket to _ServerC_ on behalf of the user without user intervention.</span></span>

> [!NOTE]
> <span data-ttu-id="4bba7-158">**[アカウントは重要なので委任できない]** プロパティが設定されている Active Directory アカウントは委任できません。</span><span class="sxs-lookup"><span data-stu-id="4bba7-158">Active Directory accounts that have the **Account is sensitive and cannot be delegated** property set cannot be delegated.</span></span> <span data-ttu-id="4bba7-159">詳しくは、「[Security Focus: セキュリティ フォーカス: 特権アカウントに対する "アカウントは重要なので委任できない" の分析][blog]」および「[Kerberos 認証のツールと設定][ktools]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4bba7-159">For more information, see [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] and [Kerberos Authentication Tools and Settings][ktools].</span></span>

## <a name="resource-based-kerberos-constrained-delegation"></a><span data-ttu-id="4bba7-160">リソースに基づく Kerberos の制約付き委任</span><span class="sxs-lookup"><span data-stu-id="4bba7-160">Resource-based Kerberos constrained delegation</span></span>

<span data-ttu-id="4bba7-161">リソースに基づく Kerberos の制約付き委任 (Windows Server 2012 で導入) を使って、リソースが存在するサーバー オブジェクトでの資格情報の委任を構成します。</span><span class="sxs-lookup"><span data-stu-id="4bba7-161">Using resource-based Kerberos constrained delegation (introduced in Windows Server 2012), you configure credential delegation on the server object where resources reside.</span></span> <span data-ttu-id="4bba7-162">上で説明した次ホップのシナリオでは、_ServerC_ を構成して、どこから委任された資格情報の受け入れるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4bba7-162">In the second hop scenario described above, you configure _ServerC_ to specify from where it accepts delegated credentials.</span></span>

<span data-ttu-id="4bba7-163">**長所**</span><span class="sxs-lookup"><span data-stu-id="4bba7-163">**Pros**</span></span>

- <span data-ttu-id="4bba7-164">資格情報が保存されません。</span><span class="sxs-lookup"><span data-stu-id="4bba7-164">Credentials are not stored.</span></span>
- <span data-ttu-id="4bba7-165">PowerShell コマンドレットを使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="4bba7-165">Configured using PowerShell cmdlets.</span></span> <span data-ttu-id="4bba7-166">特別にコードを記述する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="4bba7-166">No special coding required.</span></span>
- <span data-ttu-id="4bba7-167">構成に、ドメイン管理者のアクセス権は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4bba7-167">Does not require Domain Administrator access to configure.</span></span>
- <span data-ttu-id="4bba7-168">複数のドメインおよびフォレストをまたいで動作します。</span><span class="sxs-lookup"><span data-stu-id="4bba7-168">Works across domains and forests.</span></span>

<span data-ttu-id="4bba7-169">**短所**</span><span class="sxs-lookup"><span data-stu-id="4bba7-169">**Cons**</span></span>

- <span data-ttu-id="4bba7-170">Windows Server 2012 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="4bba7-170">Requires Windows Server 2012 or later.</span></span>
- <span data-ttu-id="4bba7-171">WinRM の次ホップはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="4bba7-171">Does not support the second hop for WinRM.</span></span>
- <span data-ttu-id="4bba7-172">オブジェクトとサービス プリンシパル名 (SPN) を更新する権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="4bba7-172">Requires rights to update objects and Service Principal Names (SPNs).</span></span>

> [!NOTE]
> <span data-ttu-id="4bba7-173">**[アカウントは重要なので委任できない]** プロパティが設定されている Active Directory アカウントは委任できません。</span><span class="sxs-lookup"><span data-stu-id="4bba7-173">Active Directory accounts that have the **Account is sensitive and cannot be delegated** property set cannot be delegated.</span></span> <span data-ttu-id="4bba7-174">詳しくは、「[Security Focus: セキュリティ フォーカス: 特権アカウントに対する "アカウントは重要なので委任できない" の分析][blog]」および「[Kerberos 認証のツールと設定][ktools]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4bba7-174">For more information, see [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] and [Kerberos Authentication Tools and Settings][ktools].</span></span>

### <a name="example"></a><span data-ttu-id="4bba7-175">例</span><span class="sxs-lookup"><span data-stu-id="4bba7-175">Example</span></span>

<span data-ttu-id="4bba7-176">_ServerB_ からの委任された資格情報を許可するように _ServerC_ でリソースに基づく制約付き委任を構成する PowerShell の例を示します。</span><span class="sxs-lookup"><span data-stu-id="4bba7-176">Let's look at a PowerShell example that configures resource-based constrained delegation on _ServerC_ to allow delegated credentials from a _ServerB_.</span></span> <span data-ttu-id="4bba7-177">この例では、すべてのサーバーが Windows Server 2012 以降を実行しており、いずれかのサーバーが属している各ドメインに少なくとも 1 つの Windows Server 2012 ドメイン コントローラーがあるものとします。</span><span class="sxs-lookup"><span data-stu-id="4bba7-177">This example assumes that all servers are running Windows Server 2012 or later, and that there is at least one Windows Server 2012 domain controller each domain to which any of the servers belong.</span></span>

<span data-ttu-id="4bba7-178">制約付き委任を構成する前に、`RSAT-AD-PowerShell` 機能を追加して Active Directory PowerShell モジュールをインストールした後、そのモジュールをセッションにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bba7-178">Before you can configure constrained delegation, you must add the `RSAT-AD-PowerShell` feature to install the Active Directory PowerShell module, and then import that module into your session:</span></span>

```powershell
Add-WindowsFeature RSAT-AD-PowerShell
Import-Module ActiveDirectory
Get-Command -ParameterName PrincipalsAllowedToDelegateToAccount
```

<span data-ttu-id="4bba7-179">使用できる複数のコマンドレットに、**PrincipalsAllowedToDelegateToAccount** パラメーターが追加されています。</span><span class="sxs-lookup"><span data-stu-id="4bba7-179">Several available cmdlets now have a **PrincipalsAllowedToDelegateToAccount** parameter:</span></span>

```Output
CommandType Name                 ModuleName
----------- ----                 ----------
Cmdlet      New-ADComputer       ActiveDirectory
Cmdlet      New-ADServiceAccount ActiveDirectory
Cmdlet      New-ADUser           ActiveDirectory
Cmdlet      Set-ADComputer       ActiveDirectory
Cmdlet      Set-ADServiceAccount ActiveDirectory
Cmdlet      Set-ADUser           ActiveDirectory
```

<span data-ttu-id="4bba7-180">**PrincipalsAllowedToDelegateToAccount** パラメーターは、Active Directory オブジェクトの **msDS-AllowedToActOnBehalfOfOtherIdentity** 属性を設定します。この属性には、関連付けられたアカウント (この例では、_Server_ のコンピューター アカウント) に資格情報を委任する権限を持つアカウントを指定するアクセス制御リスト (ACL) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4bba7-180">The **PrincipalsAllowedToDelegateToAccount** parameter sets the Active Directory object attribute **msDS-AllowedToActOnBehalfOfOtherIdentity**, which contains an access control list (ACL) that specifies which accounts have permission to delegate credentials to the associated account (in our example, it will be the machine account for _ServerA_).</span></span>

<span data-ttu-id="4bba7-181">サーバーを表すために使用する変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="4bba7-181">Now let's set up the variables we'll use to represent the servers:</span></span>

```powershell
# Set up variables for reuse
$ServerA = $env:COMPUTERNAME
$ServerB = Get-ADComputer -Identity ServerB
$ServerC = Get-ADComputer -Identity ServerC
```

<span data-ttu-id="4bba7-182">WinRM (したがって PowerShell リモート処理) は、既定でコンピューター アカウントとして実行します。</span><span class="sxs-lookup"><span data-stu-id="4bba7-182">WinRM (and therefore PowerShell remoting) runs as the computer account by default.</span></span> <span data-ttu-id="4bba7-183">これは、`winrm` サービスの **StartName** プロパティを見て確認できます。</span><span class="sxs-lookup"><span data-stu-id="4bba7-183">You can see this by looking at the **StartName** property of the `winrm` service:</span></span>

```powershell
Get-CimInstance Win32_Service -Filter 'Name="winrm"' | Select-Object StartName
```

```Output
StartName
---------
NT AUTHORITY\NetworkService
```

<span data-ttu-id="4bba7-184">_ServerC_ で _ServerB_ の PowerShell リモート処理セッションからの委任を許可するため、_ServerC_ の **PrincipalsAllowedToDelegateToAccount** パラメーターを _ServerB_ のコンピューター オブジェクトに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bba7-184">For _ServerC_ to allow delegation from a PowerShell remoting session on _ServerB_, we must set the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to the computer object of _ServerB_:</span></span>

```powershell
# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB

# Check the value of the attribute directly
$x = Get-ADComputer -Identity $ServerC -Properties msDS-AllowedToActOnBehalfOfOtherIdentity
$x.'msDS-AllowedToActOnBehalfOfOtherIdentity'.Access

# Check the value of the attribute indirectly
Get-ADComputer -Identity $ServerC -Properties PrincipalsAllowedToDelegateToAccount
```

<span data-ttu-id="4bba7-185">Kerberos の[キー配布センター (KDC)](/windows/win32/secauthn/key-distribution-center) は、拒否されたアクセス試行を 15 分間キャッシュします (ネガティブ キャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="4bba7-185">The Kerberos [Key Distribution Center (KDC)](/windows/win32/secauthn/key-distribution-center) caches denied-access attempts (negative cache) for 15 minutes.</span></span> <span data-ttu-id="4bba7-186">_ServerB_ が以前に _ServerC_ にアクセスしようとした場合、次のコマンドを呼び出すことによって _ServerB_ 上のキャッシュをクリアする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bba7-186">If _ServerB_ has previously attempted to access _ServerC_, you will need to clear the cache on _ServerB_ by invoking the following command:</span></span>

```powershell
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    klist purge -li 0x3e7
}
```

<span data-ttu-id="4bba7-187">キャッシュを消去するには、コンピューターを再起動するか、15 分以上待つのでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="4bba7-187">You could also restart the computer, or wait at least 15 minutes to clear the cache.</span></span>

<span data-ttu-id="4bba7-188">キャッシュをクリアした後は、_ServerA_ から _ServerB_ を経由して _ServerC_ にコードを正常に実行できます。</span><span class="sxs-lookup"><span data-stu-id="4bba7-188">After clearing the cache, you can successfully run code from _ServerA_ through _ServerB_ to _ServerC_:</span></span>

```powershell
# Capture a credential
$cred = Get-Credential Contoso\Alice

# Test kerberos double hop
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    Test-Path \\$($using:ServerC.Name)\C$
    Get-Process lsass -ComputerName $($using:ServerC.Name)
    Get-EventLog -LogName System -Newest 3 -ComputerName $($using:ServerC.Name)
}
```

<span data-ttu-id="4bba7-189">この例では、_ServerB_ が `$ServerC` 変数を認識できるようにするため、`$using` 変数を使用しています。</span><span class="sxs-lookup"><span data-stu-id="4bba7-189">In this example, the `$using` variable is used to make the `$ServerC` variable visible to _ServerB_.</span></span>
<span data-ttu-id="4bba7-190">`$using` 変数については、「[About Remote Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Remote_Variables)」 (リモート変数について) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bba7-190">For more information about the `$using` variable, see [about_Remote_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Remote_Variables).</span></span>

<span data-ttu-id="4bba7-191">複数のサーバーが _ServerC_ に資格情報を委任できるようにするには、_ServerC_ で **PrincipalsAllowedToDelegateToAccount** パラメーターの値に配列を設定します。</span><span class="sxs-lookup"><span data-stu-id="4bba7-191">To allow multiple servers to delegate credentials to _ServerC_, set the value of the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to an array:</span></span>

```powershell
# Set up variables for each server
$ServerB1 = Get-ADComputer -Identity ServerB1
$ServerB2 = Get-ADComputer -Identity ServerB2
$ServerB3 = Get-ADComputer -Identity ServerB3
$ServerC  = Get-ADComputer -Identity ServerC

# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC `
    -PrincipalsAllowedToDelegateToAccount @($ServerB1,$ServerB2,$ServerB3)
```

<span data-ttu-id="4bba7-192">ドメインをまたいで次ホップを実行する場合は、_ServerB_ が属するドメインのドメイン コントローラーの完全修飾ドメイン名 (FQDN) を追加します。</span><span class="sxs-lookup"><span data-stu-id="4bba7-192">If you want to make the second hop across domains, add fully-qualified domain name (FQDN) of the domain controller of the domain to which _ServerB_ belongs:</span></span>

```powershell
# For ServerC in Contoso domain and ServerB in other domain
$ServerB = Get-ADComputer -Identity ServerB -Server dc1.alpineskihouse.com
$ServerC = Get-ADComputer -Identity ServerC
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB
```

<span data-ttu-id="4bba7-193">ServerC に資格情報を委任する機能を削除するには、_ServerC_ の **PrincipalsAllowedToDelegateToAccount** パラメーターの値に `$null` を設定します。</span><span class="sxs-lookup"><span data-stu-id="4bba7-193">To remove the ability to delegate credentials to ServerC, set the value of the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to `$null`:</span></span>

```powershell
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $null
```

### <a name="information-on-resource-based-kerberos-constrained-delegation"></a><span data-ttu-id="4bba7-194">リソースに基づく Kerberos の制約付き委任についての情報</span><span class="sxs-lookup"><span data-stu-id="4bba7-194">Information on resource-based Kerberos constrained delegation</span></span>

- <span data-ttu-id="4bba7-195">[Kerberos 認証の新機能][whats-new]</span><span class="sxs-lookup"><span data-stu-id="4bba7-195">[What's New in Kerberos Authentication][whats-new]</span></span>
- <span data-ttu-id="4bba7-196">[Windows Server 2012 による Kerberos の制約付き委任の処理方法、第 1 部][kcd2012-1]</span><span class="sxs-lookup"><span data-stu-id="4bba7-196">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 1][kcd2012-1]</span></span>
- <span data-ttu-id="4bba7-197">[Windows Server 2012 による Kerberos の制約付き委任の処理方法、第 2 部][kcd2012-2]</span><span class="sxs-lookup"><span data-stu-id="4bba7-197">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 2][kcd2012-2]</span></span>
- <span data-ttu-id="4bba7-198">[統合 Windows 認証での Azure Active Directory アプリケーション プロキシ展開に対する Kerberos の制約付き委任の概要][kcdpaper]</span><span class="sxs-lookup"><span data-stu-id="4bba7-198">[Understanding Kerberos Constrained Delegation for Azure Active Directory Application Proxy Deployments with Integrated Windows Authentication][kcdpaper]</span></span>
- <span data-ttu-id="4bba7-199">[[MS-ADA2] Active Directory スキーマ属性 M2.210 属性 msDS-AllowedToActOnBehalfOfOtherIdentity][MS-ADA2]</span><span class="sxs-lookup"><span data-stu-id="4bba7-199">[[MS-ADA2] Active Directory Schema Attributes M2.210 Attribute msDS-AllowedToActOnBehalfOfOtherIdentity][MS-ADA2]</span></span>
- <span data-ttu-id="4bba7-200">[[MS-SFU] Kerberos プロトコル拡張:Service for User および制約付き委任プロトコルの 1.3.2 S4U2proxy][MS-SFU]</span><span class="sxs-lookup"><span data-stu-id="4bba7-200">[[MS-SFU] Kerberos Protocol Extensions: Service for User and Constrained Delegation Protocol 1.3.2 S4U2proxy][MS-SFU]</span></span>
- <span data-ttu-id="4bba7-201">[PrincipalsAllowedToDelegateToAccount を使用した制約付き委任を使用しないリモート管理][remote-admin]</span><span class="sxs-lookup"><span data-stu-id="4bba7-201">[Remote Administration Without Constrained Delegation Using PrincipalsAllowedToDelegateToAccount][remote-admin]</span></span>

## <a name="kerberos-delegation-unconstrained"></a><span data-ttu-id="4bba7-202">Kerberos の委任 (無制限)</span><span class="sxs-lookup"><span data-stu-id="4bba7-202">Kerberos delegation (unconstrained)</span></span>

<span data-ttu-id="4bba7-203">Kerberos の無制限の委任を使って、次ホップを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="4bba7-203">You can also used Kerberos unconstrained delegation to make the second hop.</span></span> <span data-ttu-id="4bba7-204">すべての Kerberos のシナリオと同様に、資格情報は保存されません。</span><span class="sxs-lookup"><span data-stu-id="4bba7-204">Like all Kerberos scenarios, credentials are not stored.</span></span> <span data-ttu-id="4bba7-205">この方法では、WinRM の次ホップはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="4bba7-205">This method does not support the second hop for WinRM.</span></span>

> [!WARNING]
> <span data-ttu-id="4bba7-206">この方法では、委任された資格情報がどこで使われるかは制御されません。</span><span class="sxs-lookup"><span data-stu-id="4bba7-206">This method provides no control of where delegated credentials are used.</span></span> <span data-ttu-id="4bba7-207">CredSSP よりもセキュリティが低いです。</span><span class="sxs-lookup"><span data-stu-id="4bba7-207">It is less secure than CredSSP.</span></span> <span data-ttu-id="4bba7-208">このメソッドは、テスト シナリオにのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="4bba7-208">This method should only be used for testing scenarios.</span></span>

## <a name="just-enough-administration-jea"></a><span data-ttu-id="4bba7-209">Just Enough Administration (JEA)</span><span class="sxs-lookup"><span data-stu-id="4bba7-209">Just Enough Administration (JEA)</span></span>

<span data-ttu-id="4bba7-210">JEA では、PowerShell セッションの間に管理者が実行できるコマンドを制限できます。</span><span class="sxs-lookup"><span data-stu-id="4bba7-210">JEA allows you to restrict what commands an administrator can run during a PowerShell session.</span></span> <span data-ttu-id="4bba7-211">これを使って、次ホップの問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="4bba7-211">It can be used to solve the second hop problem.</span></span>

<span data-ttu-id="4bba7-212">JEA については、「[Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4bba7-212">For information about JEA, see [Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview).</span></span>

<span data-ttu-id="4bba7-213">**長所**</span><span class="sxs-lookup"><span data-stu-id="4bba7-213">**Pros**</span></span>

- <span data-ttu-id="4bba7-214">仮想アカウントを使う場合にパスワードの管理が不要です。</span><span class="sxs-lookup"><span data-stu-id="4bba7-214">No password maintenance when using a virtual account.</span></span>

<span data-ttu-id="4bba7-215">**短所**</span><span class="sxs-lookup"><span data-stu-id="4bba7-215">**Cons**</span></span>

- <span data-ttu-id="4bba7-216">WMF 5.0 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="4bba7-216">Requires WMF 5.0 or later.</span></span>
- <span data-ttu-id="4bba7-217">すべての中間サーバー (_ServerB_) の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="4bba7-217">Requires configuration on every intermediate server (_ServerB_).</span></span>

## <a name="pssessionconfiguration-using-runas"></a><span data-ttu-id="4bba7-218">RunAs を使用する PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4bba7-218">PSSessionConfiguration using RunAs</span></span>

<span data-ttu-id="4bba7-219">_ServerB_ にセッション構成を作成し、その **RunAsCredential** パラメーターを設定できます。</span><span class="sxs-lookup"><span data-stu-id="4bba7-219">You can create a session configuration on _ServerB_ and set its **RunAsCredential** parameter.</span></span>

<span data-ttu-id="4bba7-220">**PSSessionConfiguration** と **RunAs** を使って次ホップの問題を解決する方法については、[PowerShell をリモートから使用する場合のマルチホップの別の解決策][pssessionconfig]に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4bba7-220">For information about using **PSSessionConfiguration** and **RunAs** to solve the second hop problem, see [Another solution to multi-hop PowerShell remoting][pssessionconfig].</span></span>

<span data-ttu-id="4bba7-221">**長所**</span><span class="sxs-lookup"><span data-stu-id="4bba7-221">**Pros**</span></span>

- <span data-ttu-id="4bba7-222">WMF 3.0 以降のすべてのサーバーで機能します。</span><span class="sxs-lookup"><span data-stu-id="4bba7-222">Works with any server with WMF 3.0 or later.</span></span>

<span data-ttu-id="4bba7-223">**短所**</span><span class="sxs-lookup"><span data-stu-id="4bba7-223">**Cons**</span></span>

- <span data-ttu-id="4bba7-224">すべての中間サーバー (_ServerB_) で **PSSessionConfiguration** と **RunAs** を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bba7-224">Requires configuration of **PSSessionConfiguration** and **RunAs** on every intermediate server (_ServerB_).</span></span>
- <span data-ttu-id="4bba7-225">ドメインの **RunAs** アカウントを使うときは、パスワードの管理が必要です。</span><span class="sxs-lookup"><span data-stu-id="4bba7-225">Requires password maintenance when using a domain **RunAs** account</span></span>

## <a name="pass-credentials-inside-an-invoke-command-script-block"></a><span data-ttu-id="4bba7-226">Invoke-Command スクリプト ブロックの内部で資格情報を渡す</span><span class="sxs-lookup"><span data-stu-id="4bba7-226">Pass credentials inside an Invoke-Command script block</span></span>

<span data-ttu-id="4bba7-227">[Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) コマンドレットを呼び出すときに **ScriptBlock** パラメーターの内部で資格情報を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="4bba7-227">You can pass credentials inside the **ScriptBlock** parameter of a call to the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet.</span></span>

<span data-ttu-id="4bba7-228">**長所**</span><span class="sxs-lookup"><span data-stu-id="4bba7-228">**Pros**</span></span>

- <span data-ttu-id="4bba7-229">特別なサーバー構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4bba7-229">Does not require special server configuration.</span></span>
- <span data-ttu-id="4bba7-230">WMF 2.0 以降を実行する任意のサーバーで動作します。</span><span class="sxs-lookup"><span data-stu-id="4bba7-230">Works on any server running WMF 2.0 or later.</span></span>

<span data-ttu-id="4bba7-231">**短所**</span><span class="sxs-lookup"><span data-stu-id="4bba7-231">**Cons**</span></span>

- <span data-ttu-id="4bba7-232">面倒なコード技法が必要です。</span><span class="sxs-lookup"><span data-stu-id="4bba7-232">Requires an awkward code technique.</span></span>
- <span data-ttu-id="4bba7-233">WMF 2.0 を実行している場合は、リモート セッションに引数を渡すために異なる構文が必要です。</span><span class="sxs-lookup"><span data-stu-id="4bba7-233">If running WMF 2.0, requires different syntax for passing arguments to a remote session.</span></span>

### <a name="example"></a><span data-ttu-id="4bba7-234">例</span><span class="sxs-lookup"><span data-stu-id="4bba7-234">Example</span></span>

<span data-ttu-id="4bba7-235">**Invoke-Command** スクリプト ブロックで資格情報を渡す方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4bba7-235">The following example shows how to pass credentials in an **Invoke-Command** script block:</span></span>

```powershell
# This works without delegation, passing fresh creds
# Note $Using:Cred in nested request
$cred = Get-Credential Contoso\Administrator
Invoke-Command -ComputerName ServerB -Credential $cred -ScriptBlock {
    hostname
    Invoke-Command -ComputerName ServerC -Credential $Using:cred -ScriptBlock {hostname}
}
```

## <a name="see-also"></a><span data-ttu-id="4bba7-236">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bba7-236">See also</span></span>

[<span data-ttu-id="4bba7-237">PowerShell リモート処理のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="4bba7-237">PowerShell Remoting Security Considerations</span></span>](WinRMSecurity.md)

<!-- link references -->
[blog]: /archive/blogs/poshchap/security-focus-analysing-account-is-sensitive-and-cannot-be-delegated-for-privileged-accounts
[ktools]: /previous-versions/windows/it-pro/windows-server-2003/cc738673(v=ws.10)
[credssp]: /windows/win32/secauthn/credential-security-support-provider
[beware]: https://www.powershellmagazine.com/2014/03/06/accidental-sabotage-beware-of-credssp
[pth]: https://www.microsoft.com/download/details.aspx?id=36036
[credssp-psblog]: https://devblogs.microsoft.com/scripting/enable-powershell-second-hop-functionality-with-credssp/
[whats-new]: /previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831747(v=ws.11)
[kcd2012-1]: https://www.itprotoday.com/windows-server/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-1
[kcd2012-2]: https://www.itprotoday.com/windows-server/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-2
[kcdpaper]: https://aka.ms/kcdpaper
[MS-ADA2]: /openspecs/windows_protocols/ms-ada2/cea4ac11-a4b2-4f2d-84cc-aebb4a4ad405
[MS-SFU]: /openspecs/windows_protocols/ms-sfu/bde93b0e-f3c9-4ddf-9f44-e1453be7af5a
[remote-admin]: /archive/blogs/taylorb/remote-administration-without-constrained-delegation-using-principalsallowedtodelegatetoaccount
[pssessionconfig]: /archive/blogs/sergey_babkins_blog/another-solution-to-multi-hop-powershell-remoting
[protected-users]: /windows-server/security/credentials-protection-and-management/protected-users-security-group
