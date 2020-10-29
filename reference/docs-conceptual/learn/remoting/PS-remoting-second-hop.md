---
ms.date: 05/14/2020
keywords: powershell,コマンドレット
title: PowerShell リモート処理での次ホップの実行
description: この記事では、セキュリティへの影響や推奨事項など、PowerShell のリモート処理のために次ホップ認証を構成するさまざまな方法について説明します。
ms.openlocfilehash: 905b27b4e6c612249c945a741bbe0d2ba9ae28aa
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501373"
---
# <a name="making-the-second-hop-in-powershell-remoting"></a><span data-ttu-id="9ff7a-104">PowerShell リモート処理での次ホップの実行</span><span class="sxs-lookup"><span data-stu-id="9ff7a-104">Making the second hop in PowerShell Remoting</span></span>

<span data-ttu-id="9ff7a-105">"次ホップの問題" とは次のような状況のことです。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-105">The "second hop problem" refers to a situation like the following:</span></span>

1. <span data-ttu-id="9ff7a-106">_ServerA_ にログインしています。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-106">You are logged in to _ServerA_ .</span></span>
2. <span data-ttu-id="9ff7a-107">_ServerA_ からリモート PowerShell セッションを開始して _ServerB_ に接続します。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-107">From _ServerA_ , you start a remote PowerShell session to connect to _ServerB_ .</span></span>
3. <span data-ttu-id="9ff7a-108">PowerShell リモート処理セッションを介して _ServerB_ で実行するコマンドは、 _ServerC_ 上のリソースにアクセスを試みます。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-108">A command you run on _ServerB_ via your PowerShell Remoting session attempts to access a resource on _ServerC_ .</span></span>
4. <span data-ttu-id="9ff7a-109">PowerShell リモート処理セッションの作成に使った資格情報は _ServerB_ から _ServerC_ に渡されないため、 _ServerC_ 上のリソースへのアクセスは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-109">Access to the resource on _ServerC_ is denied, because the credentials you used to create the PowerShell Remoting session are not passed from _ServerB_ to _ServerC_ .</span></span>

<span data-ttu-id="9ff7a-110">この問題に対処する方法はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-110">There are several ways to address this problem.</span></span> <span data-ttu-id="9ff7a-111">次の表に、優先順位順に方法の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-111">The following table lists the methods in order of preference.</span></span>

|                      <span data-ttu-id="9ff7a-112">構成</span><span class="sxs-lookup"><span data-stu-id="9ff7a-112">Configuration</span></span>                       |                                  <span data-ttu-id="9ff7a-113">Note</span><span class="sxs-lookup"><span data-stu-id="9ff7a-113">Note</span></span>                                  |
| -------------------------------------------------------- | ---------------------------------------------------------------------- |
| <span data-ttu-id="9ff7a-114">CredSSP</span><span class="sxs-lookup"><span data-stu-id="9ff7a-114">CredSSP</span></span>                                                  | <span data-ttu-id="9ff7a-115">使いやすさとセキュリティのバランスが取れている</span><span class="sxs-lookup"><span data-stu-id="9ff7a-115">Balances ease of use and security</span></span>                                      |
| <span data-ttu-id="9ff7a-116">リソースに基づく Kerberos の制約付き委任</span><span class="sxs-lookup"><span data-stu-id="9ff7a-116">Resource-based Kerberos constrained delegation</span></span>           | <span data-ttu-id="9ff7a-117">単純な構成で高いセキュリティ</span><span class="sxs-lookup"><span data-stu-id="9ff7a-117">Higher security with simpler configuration</span></span>                             |
| <span data-ttu-id="9ff7a-118">Kerberos の制約付き委任</span><span class="sxs-lookup"><span data-stu-id="9ff7a-118">Kerberos constrained delegation</span></span>                          | <span data-ttu-id="9ff7a-119">セキュリティは高いが、ドメイン管理者が必要</span><span class="sxs-lookup"><span data-stu-id="9ff7a-119">High security but requires Domain Administrator</span></span>                         |
| <span data-ttu-id="9ff7a-120">Kerberos の委任 (無制限)</span><span class="sxs-lookup"><span data-stu-id="9ff7a-120">Kerberos delegation (unconstrained)</span></span>                      | <span data-ttu-id="9ff7a-121">推奨されません</span><span class="sxs-lookup"><span data-stu-id="9ff7a-121">Not recommended</span></span>                                                        |
| <span data-ttu-id="9ff7a-122">Just Enough Administration (JEA)</span><span class="sxs-lookup"><span data-stu-id="9ff7a-122">Just Enough Administration (JEA)</span></span>                         | <span data-ttu-id="9ff7a-123">セキュリティは最も高いが、より詳細な構成が必要</span><span class="sxs-lookup"><span data-stu-id="9ff7a-123">Can provide the best security but requires more detailed configuration</span></span> |
| <span data-ttu-id="9ff7a-124">RunAs を使用する PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="9ff7a-124">PSSessionConfiguration using RunAs</span></span>                       | <span data-ttu-id="9ff7a-125">簡単に構成できるが、資格情報の管理が必要</span><span class="sxs-lookup"><span data-stu-id="9ff7a-125">Simpler to configure but requires credential management</span></span>                |
| <span data-ttu-id="9ff7a-126">`Invoke-Command` スクリプト ブロックの内部で資格情報を渡す</span><span class="sxs-lookup"><span data-stu-id="9ff7a-126">Pass credentials inside an `Invoke-Command` script block</span></span> | <span data-ttu-id="9ff7a-127">最も簡単に使用できるが、資格情報を指定する必要がある</span><span class="sxs-lookup"><span data-stu-id="9ff7a-127">Simplest to use but you must provide credentials</span></span>                       |

## <a name="credssp"></a><span data-ttu-id="9ff7a-128">CredSSP</span><span class="sxs-lookup"><span data-stu-id="9ff7a-128">CredSSP</span></span>

<span data-ttu-id="9ff7a-129">認証に[資格情報のセキュリティ サポート プロバイダー (CredSSP)][credssp] を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-129">You can use the [Credential Security Support Provider (CredSSP)][credssp] for authentication.</span></span>
<span data-ttu-id="9ff7a-130">CredSSP はリモート サーバー ( _ServerB_ ) に資格情報をキャッシュするため、これを使用すると資格情報の盗難攻撃にさらされます。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-130">CredSSP caches credentials on the remote server ( _ServerB_ ), so using it opens you up to credential theft attacks.</span></span> <span data-ttu-id="9ff7a-131">リモート コンピューターが侵害されると、攻撃者はユーザーの資格情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-131">If the remote computer is compromised, the attacker has access to the user's credentials.</span></span> <span data-ttu-id="9ff7a-132">CredSSP は、既定では、クライアント コンピューターとサーバー コンピューターの両方で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-132">CredSSP is disabled by default on both client and server computers.</span></span> <span data-ttu-id="9ff7a-133">CredSSP は、最も信頼性の高い環境でのみ有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-133">You should enable CredSSP only in the most trusted environments.</span></span> <span data-ttu-id="9ff7a-134">たとえば、ドメイン コントローラーは信頼性が高いため、ドメイン コントローラーに接続しているドメイン管理者が有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-134">For example, a domain administrator connecting to a domain controller because the domain controller is highly trusted.</span></span>

<span data-ttu-id="9ff7a-135">PowerShell リモート処理で CredSSP を使用する場合のセキュリティに関する注意事項の詳細については、「[Accidental Sabotage: Beware of CredSSP (予想外の妨害行為: CredSSP に関する注意事項)][beware]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-135">For more information about security concerns when using CredSSP for PowerShell Remoting, see [Accidental Sabotage: Beware of CredSSP][beware].</span></span>

<span data-ttu-id="9ff7a-136">資格情報の盗難攻撃の詳細については、「[Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft (Pass-the-Hash (PtH) 攻撃とその他の資格情報の盗難の抑制)][pth]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-136">For more information about credential theft attacks, see [Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft][pth].</span></span>

<span data-ttu-id="9ff7a-137">PowerShell リモート処理用に CredSSP を有効にして使用する方法の例については、「[CredSSP を使用して PowerShell "次ホップ" 機能を有効にする][credssp-psblog]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-137">For an example of how to enable and use CredSSP for PowerShell remoting, see [Enable PowerShell "Second-Hop" Functionality with CredSSP][credssp-psblog].</span></span>

<span data-ttu-id="9ff7a-138">**長所**</span><span class="sxs-lookup"><span data-stu-id="9ff7a-138">**Pros**</span></span>

- <span data-ttu-id="9ff7a-139">Windows Server 2008 以降のすべてのサーバーで機能します。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-139">It works for all servers with Windows Server 2008 or later.</span></span>

<span data-ttu-id="9ff7a-140">**短所**</span><span class="sxs-lookup"><span data-stu-id="9ff7a-140">**Cons**</span></span>

- <span data-ttu-id="9ff7a-141">セキュリティの脆弱性があります。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-141">Has security vulnerabilities.</span></span>
- <span data-ttu-id="9ff7a-142">クライアント ロールとサーバー ロールの両方の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-142">Requires configuration of both client and server roles.</span></span>
- <span data-ttu-id="9ff7a-143">Protected Users グループでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-143">Does not work with the Protected Users group.</span></span> <span data-ttu-id="9ff7a-144">詳細については、「[Protected Users セキュリティ グループ][protected-users]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-144">For more information, see [Protected Users Security Group][protected-users].</span></span>

## <a name="kerberos-constrained-delegation"></a><span data-ttu-id="9ff7a-145">Kerberos の制約付き委任</span><span class="sxs-lookup"><span data-stu-id="9ff7a-145">Kerberos constrained delegation</span></span>

<span data-ttu-id="9ff7a-146">従来の (リソースに基づかない) 制約付き委任を使って、次ホップを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-146">You can use legacy constrained delegation (not resource-based) to make the second hop.</span></span> <span data-ttu-id="9ff7a-147">プロトコル遷移を許可するには、[任意の認証プロトコルを使う] オプションを使用して Kerberos の制約付き委任を構成します。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-147">Configure Kerberos constrained delegation with the option "Use any authentication protocol" to allow protocol transition.</span></span>

<span data-ttu-id="9ff7a-148">**長所**</span><span class="sxs-lookup"><span data-stu-id="9ff7a-148">**Pros**</span></span>

- <span data-ttu-id="9ff7a-149">特別なコーディングが必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-149">Requires no special coding</span></span>
- <span data-ttu-id="9ff7a-150">資格情報が保存されません。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-150">Credentials are not stored.</span></span>

<span data-ttu-id="9ff7a-151">**短所**</span><span class="sxs-lookup"><span data-stu-id="9ff7a-151">**Cons**</span></span>

- <span data-ttu-id="9ff7a-152">WinRM の次ホップはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-152">Does not support the second hop for WinRM.</span></span>
- <span data-ttu-id="9ff7a-153">構成には、ドメイン管理者のアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-153">Requires Domain Administrator access to configure.</span></span>
- <span data-ttu-id="9ff7a-154">リモート サーバー ( _ServerB_ ) の Active Directory オブジェクトで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-154">Must be configured on the Active Directory object of the remote server ( _ServerB_ ).</span></span>
- <span data-ttu-id="9ff7a-155">1 つのドメインに制限されます。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-155">Limited to one domain.</span></span> <span data-ttu-id="9ff7a-156">複数のドメインまたはフォレストにまたがることはできません。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-156">Cannot cross domains or forests.</span></span>
- <span data-ttu-id="9ff7a-157">オブジェクトとサービス プリンシパル名 (SPN) を更新する権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-157">Requires rights to update objects and Service Principal Names (SPNs).</span></span>
- <span data-ttu-id="9ff7a-158">_ServerB_ は、ユーザーの介入なしに、ユーザーに代わって _ServerC_ への Kerberos チケットを取得できます。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-158">_ServerB_ can acquire a Kerberos ticket to _ServerC_ on behalf of the user without user intervention.</span></span>

> [!NOTE]
> <span data-ttu-id="9ff7a-159">**[アカウントは重要なので委任できない]** プロパティが設定されている Active Directory アカウントは委任できません。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-159">Active Directory accounts that have the **Account is sensitive and cannot be delegated** property set cannot be delegated.</span></span> <span data-ttu-id="9ff7a-160">詳しくは、「[Security Focus: セキュリティ フォーカス: 特権アカウントに対する "アカウントは重要なので委任できない" の分析][blog]」および「[Kerberos 認証のツールと設定][ktools]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-160">For more information, see [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] and [Kerberos Authentication Tools and Settings][ktools].</span></span>

## <a name="resource-based-kerberos-constrained-delegation"></a><span data-ttu-id="9ff7a-161">リソースに基づく Kerberos の制約付き委任</span><span class="sxs-lookup"><span data-stu-id="9ff7a-161">Resource-based Kerberos constrained delegation</span></span>

<span data-ttu-id="9ff7a-162">リソースに基づく Kerberos の制約付き委任 (Windows Server 2012 で導入) を使って、リソースが存在するサーバー オブジェクトでの資格情報の委任を構成します。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-162">Using resource-based Kerberos constrained delegation (introduced in Windows Server 2012), you configure credential delegation on the server object where resources reside.</span></span> <span data-ttu-id="9ff7a-163">上で説明した次ホップのシナリオでは、 _ServerC_ を構成して、どこから委任された資格情報の受け入れるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-163">In the second hop scenario described above, you configure _ServerC_ to specify from where it accepts delegated credentials.</span></span>

<span data-ttu-id="9ff7a-164">**長所**</span><span class="sxs-lookup"><span data-stu-id="9ff7a-164">**Pros**</span></span>

- <span data-ttu-id="9ff7a-165">資格情報が保存されません。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-165">Credentials are not stored.</span></span>
- <span data-ttu-id="9ff7a-166">PowerShell コマンドレットを使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-166">Configured using PowerShell cmdlets.</span></span> <span data-ttu-id="9ff7a-167">特別にコードを記述する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-167">No special coding required.</span></span>
- <span data-ttu-id="9ff7a-168">構成に、ドメイン管理者のアクセス権は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-168">Does not require Domain Administrator access to configure.</span></span>
- <span data-ttu-id="9ff7a-169">複数のドメインおよびフォレストをまたいで動作します。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-169">Works across domains and forests.</span></span>

<span data-ttu-id="9ff7a-170">**短所**</span><span class="sxs-lookup"><span data-stu-id="9ff7a-170">**Cons**</span></span>

- <span data-ttu-id="9ff7a-171">Windows Server 2012 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-171">Requires Windows Server 2012 or later.</span></span>
- <span data-ttu-id="9ff7a-172">WinRM の次ホップはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-172">Does not support the second hop for WinRM.</span></span>
- <span data-ttu-id="9ff7a-173">オブジェクトとサービス プリンシパル名 (SPN) を更新する権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-173">Requires rights to update objects and Service Principal Names (SPNs).</span></span>

> [!NOTE]
> <span data-ttu-id="9ff7a-174">**[アカウントは重要なので委任できない]** プロパティが設定されている Active Directory アカウントは委任できません。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-174">Active Directory accounts that have the **Account is sensitive and cannot be delegated** property set cannot be delegated.</span></span> <span data-ttu-id="9ff7a-175">詳しくは、「[Security Focus: セキュリティ フォーカス: 特権アカウントに対する "アカウントは重要なので委任できない" の分析][blog]」および「[Kerberos 認証のツールと設定][ktools]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-175">For more information, see [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] and [Kerberos Authentication Tools and Settings][ktools].</span></span>

### <a name="example"></a><span data-ttu-id="9ff7a-176">例</span><span class="sxs-lookup"><span data-stu-id="9ff7a-176">Example</span></span>

<span data-ttu-id="9ff7a-177">_ServerB_ からの委任された資格情報を許可するように _ServerC_ でリソースに基づく制約付き委任を構成する PowerShell の例を示します。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-177">Let's look at a PowerShell example that configures resource-based constrained delegation on _ServerC_ to allow delegated credentials from a _ServerB_ .</span></span> <span data-ttu-id="9ff7a-178">この例では、すべてのサーバーが Windows Server 2012 以降を実行しており、いずれかのサーバーが属している各ドメインに少なくとも 1 つの Windows Server 2012 ドメイン コントローラーがあるものとします。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-178">This example assumes that all servers are running Windows Server 2012 or later, and that there is at least one Windows Server 2012 domain controller each domain to which any of the servers belong.</span></span>

<span data-ttu-id="9ff7a-179">制約付き委任を構成する前に、`RSAT-AD-PowerShell` 機能を追加して Active Directory PowerShell モジュールをインストールした後、そのモジュールをセッションにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-179">Before you can configure constrained delegation, you must add the `RSAT-AD-PowerShell` feature to install the Active Directory PowerShell module, and then import that module into your session:</span></span>

```powershell
Add-WindowsFeature RSAT-AD-PowerShell
Import-Module ActiveDirectory
Get-Command -ParameterName PrincipalsAllowedToDelegateToAccount
```

<span data-ttu-id="9ff7a-180">使用できる複数のコマンドレットに、 **PrincipalsAllowedToDelegateToAccount** パラメーターが追加されています。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-180">Several available cmdlets now have a **PrincipalsAllowedToDelegateToAccount** parameter:</span></span>

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

<span data-ttu-id="9ff7a-181">**PrincipalsAllowedToDelegateToAccount** パラメーターは、Active Directory オブジェクトの **msDS-AllowedToActOnBehalfOfOtherIdentity** 属性を設定します。この属性には、関連付けられたアカウント (この例では、 _Server_ のコンピューター アカウント) に資格情報を委任する権限を持つアカウントを指定するアクセス制御リスト (ACL) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-181">The **PrincipalsAllowedToDelegateToAccount** parameter sets the Active Directory object attribute **msDS-AllowedToActOnBehalfOfOtherIdentity** , which contains an access control list (ACL) that specifies which accounts have permission to delegate credentials to the associated account (in our example, it will be the machine account for _ServerA_ ).</span></span>

<span data-ttu-id="9ff7a-182">サーバーを表すために使用する変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-182">Now let's set up the variables we'll use to represent the servers:</span></span>

```powershell
# Set up variables for reuse
$ServerA = $env:COMPUTERNAME
$ServerB = Get-ADComputer -Identity ServerB
$ServerC = Get-ADComputer -Identity ServerC
```

<span data-ttu-id="9ff7a-183">WinRM (したがって PowerShell リモート処理) は、既定でコンピューター アカウントとして実行します。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-183">WinRM (and therefore PowerShell remoting) runs as the computer account by default.</span></span> <span data-ttu-id="9ff7a-184">これは、`winrm` サービスの **StartName** プロパティを見て確認できます。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-184">You can see this by looking at the **StartName** property of the `winrm` service:</span></span>

```powershell
Get-CimInstance Win32_Service -Filter 'Name="winrm"' | Select-Object StartName
```

```Output
StartName
---------
NT AUTHORITY\NetworkService
```

<span data-ttu-id="9ff7a-185">_ServerC_ で _ServerB_ の PowerShell リモート処理セッションからの委任を許可するため、 _ServerC_ の **PrincipalsAllowedToDelegateToAccount** パラメーターを _ServerB_ のコンピューター オブジェクトに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-185">For _ServerC_ to allow delegation from a PowerShell remoting session on _ServerB_ , we must set the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to the computer object of _ServerB_ :</span></span>

```powershell
# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB

# Check the value of the attribute directly
$x = Get-ADComputer -Identity $ServerC -Properties msDS-AllowedToActOnBehalfOfOtherIdentity
$x.'msDS-AllowedToActOnBehalfOfOtherIdentity'.Access

# Check the value of the attribute indirectly
Get-ADComputer -Identity $ServerC -Properties PrincipalsAllowedToDelegateToAccount
```

<span data-ttu-id="9ff7a-186">Kerberos の[キー配布センター (KDC)](/windows/win32/secauthn/key-distribution-center) は、拒否されたアクセス試行を 15 分間キャッシュします (ネガティブ キャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-186">The Kerberos [Key Distribution Center (KDC)](/windows/win32/secauthn/key-distribution-center) caches denied-access attempts (negative cache) for 15 minutes.</span></span> <span data-ttu-id="9ff7a-187">_ServerB_ が以前に _ServerC_ にアクセスしようとした場合、次のコマンドを呼び出すことによって _ServerB_ 上のキャッシュをクリアする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-187">If _ServerB_ has previously attempted to access _ServerC_ , you will need to clear the cache on _ServerB_ by invoking the following command:</span></span>

```powershell
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    klist purge -li 0x3e7
}
```

<span data-ttu-id="9ff7a-188">キャッシュを消去するには、コンピューターを再起動するか、15 分以上待つのでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-188">You could also restart the computer, or wait at least 15 minutes to clear the cache.</span></span>

<span data-ttu-id="9ff7a-189">キャッシュをクリアした後は、 _ServerA_ から _ServerB_ を経由して _ServerC_ にコードを正常に実行できます。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-189">After clearing the cache, you can successfully run code from _ServerA_ through _ServerB_ to _ServerC_ :</span></span>

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

<span data-ttu-id="9ff7a-190">この例では、 _ServerB_ が `$ServerC` 変数を認識できるようにするため、`$using` 変数を使用しています。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-190">In this example, the `$using` variable is used to make the `$ServerC` variable visible to _ServerB_ .</span></span>
<span data-ttu-id="9ff7a-191">`$using` 変数については、「[About Remote Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Remote_Variables)」 (リモート変数について) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-191">For more information about the `$using` variable, see [about_Remote_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Remote_Variables).</span></span>

<span data-ttu-id="9ff7a-192">複数のサーバーが _ServerC_ に資格情報を委任できるようにするには、 _ServerC_ で **PrincipalsAllowedToDelegateToAccount** パラメーターの値に配列を設定します。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-192">To allow multiple servers to delegate credentials to _ServerC_ , set the value of the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to an array:</span></span>

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

<span data-ttu-id="9ff7a-193">ドメインをまたいで次ホップを実行する場合は、 _ServerB_ が属するドメインのドメイン コントローラーの完全修飾ドメイン名 (FQDN) を追加します。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-193">If you want to make the second hop across domains, add fully-qualified domain name (FQDN) of the domain controller of the domain to which _ServerB_ belongs:</span></span>

```powershell
# For ServerC in Contoso domain and ServerB in other domain
$ServerB = Get-ADComputer -Identity ServerB -Server dc1.alpineskihouse.com
$ServerC = Get-ADComputer -Identity ServerC
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB
```

<span data-ttu-id="9ff7a-194">ServerC に資格情報を委任する機能を削除するには、 _ServerC_ の **PrincipalsAllowedToDelegateToAccount** パラメーターの値に `$null` を設定します。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-194">To remove the ability to delegate credentials to ServerC, set the value of the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to `$null`:</span></span>

```powershell
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $null
```

### <a name="information-on-resource-based-kerberos-constrained-delegation"></a><span data-ttu-id="9ff7a-195">リソースに基づく Kerberos の制約付き委任についての情報</span><span class="sxs-lookup"><span data-stu-id="9ff7a-195">Information on resource-based Kerberos constrained delegation</span></span>

- <span data-ttu-id="9ff7a-196">[Kerberos 認証の新機能][whats-new]</span><span class="sxs-lookup"><span data-stu-id="9ff7a-196">[What's New in Kerberos Authentication][whats-new]</span></span>
- <span data-ttu-id="9ff7a-197">[Windows Server 2012 による Kerberos の制約付き委任の処理方法、第 1 部][kcd2012-1]</span><span class="sxs-lookup"><span data-stu-id="9ff7a-197">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 1][kcd2012-1]</span></span>
- <span data-ttu-id="9ff7a-198">[Windows Server 2012 による Kerberos の制約付き委任の処理方法、第 2 部][kcd2012-2]</span><span class="sxs-lookup"><span data-stu-id="9ff7a-198">[How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 2][kcd2012-2]</span></span>
- <span data-ttu-id="9ff7a-199">[統合 Windows 認証での Azure Active Directory アプリケーション プロキシ展開に対する Kerberos の制約付き委任の概要][kcdpaper]</span><span class="sxs-lookup"><span data-stu-id="9ff7a-199">[Understanding Kerberos Constrained Delegation for Azure Active Directory Application Proxy Deployments with Integrated Windows Authentication][kcdpaper]</span></span>
- <span data-ttu-id="9ff7a-200">[[MS-ADA2] Active Directory スキーマ属性 M2.210 属性 msDS-AllowedToActOnBehalfOfOtherIdentity][MS-ADA2]</span><span class="sxs-lookup"><span data-stu-id="9ff7a-200">[[MS-ADA2] Active Directory Schema Attributes M2.210 Attribute msDS-AllowedToActOnBehalfOfOtherIdentity][MS-ADA2]</span></span>
- <span data-ttu-id="9ff7a-201">[[MS-SFU] Kerberos プロトコル拡張:Service for User および制約付き委任プロトコルの 1.3.2 S4U2proxy][MS-SFU]</span><span class="sxs-lookup"><span data-stu-id="9ff7a-201">[[MS-SFU] Kerberos Protocol Extensions: Service for User and Constrained Delegation Protocol 1.3.2 S4U2proxy][MS-SFU]</span></span>
- <span data-ttu-id="9ff7a-202">[PrincipalsAllowedToDelegateToAccount を使用した制約付き委任を使用しないリモート管理][remote-admin]</span><span class="sxs-lookup"><span data-stu-id="9ff7a-202">[Remote Administration Without Constrained Delegation Using PrincipalsAllowedToDelegateToAccount][remote-admin]</span></span>

## <a name="kerberos-delegation-unconstrained"></a><span data-ttu-id="9ff7a-203">Kerberos の委任 (無制限)</span><span class="sxs-lookup"><span data-stu-id="9ff7a-203">Kerberos delegation (unconstrained)</span></span>

<span data-ttu-id="9ff7a-204">Kerberos の無制限の委任を使って、次ホップを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-204">You can also used Kerberos unconstrained delegation to make the second hop.</span></span> <span data-ttu-id="9ff7a-205">すべての Kerberos のシナリオと同様に、資格情報は保存されません。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-205">Like all Kerberos scenarios, credentials are not stored.</span></span> <span data-ttu-id="9ff7a-206">この方法では、WinRM の次ホップはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-206">This method does not support the second hop for WinRM.</span></span>

> [!WARNING]
> <span data-ttu-id="9ff7a-207">この方法では、委任された資格情報がどこで使われるかは制御されません。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-207">This method provides no control of where delegated credentials are used.</span></span> <span data-ttu-id="9ff7a-208">CredSSP よりもセキュリティが低いです。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-208">It is less secure than CredSSP.</span></span> <span data-ttu-id="9ff7a-209">このメソッドは、テスト シナリオにのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-209">This method should only be used for testing scenarios.</span></span>

## <a name="just-enough-administration-jea"></a><span data-ttu-id="9ff7a-210">Just Enough Administration (JEA)</span><span class="sxs-lookup"><span data-stu-id="9ff7a-210">Just Enough Administration (JEA)</span></span>

<span data-ttu-id="9ff7a-211">JEA では、PowerShell セッションの間に管理者が実行できるコマンドを制限できます。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-211">JEA allows you to restrict what commands an administrator can run during a PowerShell session.</span></span> <span data-ttu-id="9ff7a-212">これを使って、次ホップの問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-212">It can be used to solve the second hop problem.</span></span>

<span data-ttu-id="9ff7a-213">JEA については、「[Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-213">For information about JEA, see [Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview).</span></span>

<span data-ttu-id="9ff7a-214">**長所**</span><span class="sxs-lookup"><span data-stu-id="9ff7a-214">**Pros**</span></span>

- <span data-ttu-id="9ff7a-215">仮想アカウントを使う場合にパスワードの管理が不要です。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-215">No password maintenance when using a virtual account.</span></span>

<span data-ttu-id="9ff7a-216">**短所**</span><span class="sxs-lookup"><span data-stu-id="9ff7a-216">**Cons**</span></span>

- <span data-ttu-id="9ff7a-217">WMF 5.0 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-217">Requires WMF 5.0 or later.</span></span>
- <span data-ttu-id="9ff7a-218">すべての中間サーバー ( _ServerB_ ) の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-218">Requires configuration on every intermediate server ( _ServerB_ ).</span></span>

## <a name="pssessionconfiguration-using-runas"></a><span data-ttu-id="9ff7a-219">RunAs を使用する PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="9ff7a-219">PSSessionConfiguration using RunAs</span></span>

<span data-ttu-id="9ff7a-220">_ServerB_ にセッション構成を作成し、その **RunAsCredential** パラメーターを設定できます。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-220">You can create a session configuration on _ServerB_ and set its **RunAsCredential** parameter.</span></span>

<span data-ttu-id="9ff7a-221">**PSSessionConfiguration** と **RunAs** を使って次ホップの問題を解決する方法については、 [PowerShell をリモートから使用する場合のマルチホップの別の解決策][pssessionconfig]に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-221">For information about using **PSSessionConfiguration** and **RunAs** to solve the second hop problem, see [Another solution to multi-hop PowerShell remoting][pssessionconfig].</span></span>

<span data-ttu-id="9ff7a-222">**長所**</span><span class="sxs-lookup"><span data-stu-id="9ff7a-222">**Pros**</span></span>

- <span data-ttu-id="9ff7a-223">WMF 3.0 以降のすべてのサーバーで機能します。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-223">Works with any server with WMF 3.0 or later.</span></span>

<span data-ttu-id="9ff7a-224">**短所**</span><span class="sxs-lookup"><span data-stu-id="9ff7a-224">**Cons**</span></span>

- <span data-ttu-id="9ff7a-225">すべての中間サーバー ( _ServerB_ ) で **PSSessionConfiguration** と **RunAs** を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-225">Requires configuration of **PSSessionConfiguration** and **RunAs** on every intermediate server ( _ServerB_ ).</span></span>
- <span data-ttu-id="9ff7a-226">ドメインの **RunAs** アカウントを使うときは、パスワードの管理が必要です。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-226">Requires password maintenance when using a domain **RunAs** account</span></span>

## <a name="pass-credentials-inside-an-invoke-command-script-block"></a><span data-ttu-id="9ff7a-227">Invoke-Command スクリプト ブロックの内部で資格情報を渡す</span><span class="sxs-lookup"><span data-stu-id="9ff7a-227">Pass credentials inside an Invoke-Command script block</span></span>

<span data-ttu-id="9ff7a-228">[Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) コマンドレットを呼び出すときに **ScriptBlock** パラメーターの内部で資格情報を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-228">You can pass credentials inside the **ScriptBlock** parameter of a call to the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet.</span></span>

<span data-ttu-id="9ff7a-229">**長所**</span><span class="sxs-lookup"><span data-stu-id="9ff7a-229">**Pros**</span></span>

- <span data-ttu-id="9ff7a-230">特別なサーバー構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-230">Does not require special server configuration.</span></span>
- <span data-ttu-id="9ff7a-231">WMF 2.0 以降を実行する任意のサーバーで動作します。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-231">Works on any server running WMF 2.0 or later.</span></span>

<span data-ttu-id="9ff7a-232">**短所**</span><span class="sxs-lookup"><span data-stu-id="9ff7a-232">**Cons**</span></span>

- <span data-ttu-id="9ff7a-233">面倒なコード技法が必要です。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-233">Requires an awkward code technique.</span></span>
- <span data-ttu-id="9ff7a-234">WMF 2.0 を実行している場合は、リモート セッションに引数を渡すために異なる構文が必要です。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-234">If running WMF 2.0, requires different syntax for passing arguments to a remote session.</span></span>

### <a name="example"></a><span data-ttu-id="9ff7a-235">例</span><span class="sxs-lookup"><span data-stu-id="9ff7a-235">Example</span></span>

<span data-ttu-id="9ff7a-236">**Invoke-Command** スクリプト ブロックで資格情報を渡す方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9ff7a-236">The following example shows how to pass credentials in an **Invoke-Command** script block:</span></span>

```powershell
# This works without delegation, passing fresh creds
# Note $Using:Cred in nested request
$cred = Get-Credential Contoso\Administrator
Invoke-Command -ComputerName ServerB -Credential $cred -ScriptBlock {
    hostname
    Invoke-Command -ComputerName ServerC -Credential $Using:cred -ScriptBlock {hostname}
}
```

## <a name="see-also"></a><span data-ttu-id="9ff7a-237">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ff7a-237">See also</span></span>

[<span data-ttu-id="9ff7a-238">PowerShell リモート処理のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="9ff7a-238">PowerShell Remoting Security Considerations</span></span>](WinRMSecurity.md)

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
