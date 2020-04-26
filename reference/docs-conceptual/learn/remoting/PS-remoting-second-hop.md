---
ms.date: 04/15/2020
keywords: powershell,コマンドレット
title: PowerShell リモート処理での次ホップの実行
ms.openlocfilehash: 7819058bd8118ba44e66ec658017f536076609b5
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81527624"
---
# <a name="making-the-second-hop-in-powershell-remoting"></a><span data-ttu-id="bb5fa-103">PowerShell リモート処理での次ホップの実行</span><span class="sxs-lookup"><span data-stu-id="bb5fa-103">Making the second hop in PowerShell Remoting</span></span>

<span data-ttu-id="bb5fa-104">"次ホップの問題" とは次のような状況のことです。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-104">The "second hop problem" refers to a situation like the following:</span></span>

1. <span data-ttu-id="bb5fa-105">_ServerA_ にログインしています。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-105">You are logged in to _ServerA_.</span></span>
2. <span data-ttu-id="bb5fa-106">_ServerA_ からリモート PowerShell セッションを開始して _ServerB_ に接続します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-106">From _ServerA_, you start a remote PowerShell session to connect to _ServerB_.</span></span>
3. <span data-ttu-id="bb5fa-107">PowerShell リモート処理セッションを介して _ServerB_ で実行するコマンドは、_ServerC_ 上のリソースにアクセスを試みます。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-107">A command you run on _ServerB_ via your PowerShell Remoting session attempts to access a resource on _ServerC_.</span></span>
4. <span data-ttu-id="bb5fa-108">PowerShell リモート処理セッションの作成に使った資格情報は _ServerB_ から _ServerC_ に渡されないため、_ServerC_ 上のリソースへのアクセスは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-108">Access to the resource on _ServerC_ is denied, because the credentials you used to create the PowerShell Remoting session are not passed from _ServerB_ to _ServerC_.</span></span>

<span data-ttu-id="bb5fa-109">この問題に対処する方法はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-109">There are several ways to address this problem.</span></span> <span data-ttu-id="bb5fa-110">このトピックでは、次ホップの問題に対する最も一般的な解決方法をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-110">In this topic, we'll look at several of the most popular solutions to the second hop problem.</span></span>

## <a name="credssp"></a><span data-ttu-id="bb5fa-111">CredSSP</span><span class="sxs-lookup"><span data-stu-id="bb5fa-111">CredSSP</span></span>

<span data-ttu-id="bb5fa-112">認証に[資格情報のセキュリティ サポート プロバイダー (CredSSP)](/windows/win32/secauthn/credential-security-support-provider) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-112">You can use the [Credential Security Support Provider (CredSSP)](/windows/win32/secauthn/credential-security-support-provider) for authentication.</span></span> <span data-ttu-id="bb5fa-113">CredSSP はリモート サーバー (_ServerB_) に資格情報をキャッシュするため、これを使用すると資格情報の盗難攻撃にさらされます。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-113">CredSSP caches credentials on the remote server (_ServerB_), so using it opens you up to credential theft attacks.</span></span> <span data-ttu-id="bb5fa-114">リモート コンピューターが侵害されると、攻撃者はユーザーの資格情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-114">If the remote computer is compromised, the attacker has access to the user's credentials.</span></span> <span data-ttu-id="bb5fa-115">CredSSP は、既定では、クライアント コンピューターとサーバー コンピューターの両方で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-115">CredSSP is disabled by default on both client and server computers.</span></span> <span data-ttu-id="bb5fa-116">CredSSP は、最も信頼性の高い環境でのみ有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-116">You should enable CredSSP only in the most trusted environments.</span></span> <span data-ttu-id="bb5fa-117">たとえば、ドメイン コントローラーは信頼性が高いため、ドメイン コントローラーに接続しているドメイン管理者が有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-117">For example, a domain administrator connecting to a domain controller because the domain controller is highly trusted.</span></span>

<span data-ttu-id="bb5fa-118">PowerShell リモート処理で CredSSP を使用する場合のセキュリティに関する注意事項の詳細については、「[Accidental Sabotage: Beware of CredSSP (予想外の妨害行為: CredSSP に関する注意事項)](https://www.powershellmagazine.com/2014/03/06/accidental-sabotage-beware-of-credssp)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-118">For more information about security concerns when using CredSSP for PowerShell Remoting, see [Accidental Sabotage: Beware of CredSSP](https://www.powershellmagazine.com/2014/03/06/accidental-sabotage-beware-of-credssp).</span></span>

<span data-ttu-id="bb5fa-119">資格情報の盗難攻撃の詳細については、「[Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft (Pass-the-Hash (PtH) 攻撃とその他の資格情報の盗難の抑制)](https://www.microsoft.com/en-us/download/details.aspx?id=36036)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-119">For more information about credential theft attacks, see [Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft](https://www.microsoft.com/en-us/download/details.aspx?id=36036).</span></span>

<span data-ttu-id="bb5fa-120">PowerShell リモート処理用に CredSSP を有効にして使用する方法の例については、「[CredSSP を使用して PowerShell "次ホップ" 機能を有効にする](https://devblogs.microsoft.com/scripting/enable-powershell-second-hop-functionality-with-credssp/)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-120">For an example of how to enable and use CredSSP for PowerShell remoting, see [Enable PowerShell "Second-Hop" Functionality with CredSSP](https://devblogs.microsoft.com/scripting/enable-powershell-second-hop-functionality-with-credssp/).</span></span>

### <a name="pros"></a><span data-ttu-id="bb5fa-121">長所</span><span class="sxs-lookup"><span data-stu-id="bb5fa-121">Pros</span></span>

- <span data-ttu-id="bb5fa-122">Windows Server 2008 以降のすべてのサーバーで機能します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-122">It works for all servers with Windows Server 2008 or later.</span></span>

### <a name="cons"></a><span data-ttu-id="bb5fa-123">短所</span><span class="sxs-lookup"><span data-stu-id="bb5fa-123">Cons</span></span>

- <span data-ttu-id="bb5fa-124">セキュリティの脆弱性があります。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-124">Has security vulnerabilities.</span></span>
- <span data-ttu-id="bb5fa-125">クライアント ロールとサーバー ロールの両方の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-125">Requires configuration of both client and server roles.</span></span>

## <a name="kerberos-delegation-unconstrained"></a><span data-ttu-id="bb5fa-126">Kerberos の委任 (無制限)</span><span class="sxs-lookup"><span data-stu-id="bb5fa-126">Kerberos delegation (unconstrained)</span></span>

<span data-ttu-id="bb5fa-127">Kerberos の無制限の委任を使って、次ホップを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-127">You can also used Kerberos unconstrained delegation to make the second hop.</span></span> <span data-ttu-id="bb5fa-128">ただし、この方法では、委任された資格情報が使われる場所を制御することはできません。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-128">However, this method provides no control of where delegated credentials are used.</span></span>

> [!NOTE]
> <span data-ttu-id="bb5fa-129">**[アカウントは重要なので委任できない]** プロパティが設定されている Active Directory アカウントは委任できません。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-129">Active Directory accounts that have the **Account is sensitive and cannot be delegated** property set cannot be delegated.</span></span> <span data-ttu-id="bb5fa-130">詳しくは、「[Security Focus: セキュリティ フォーカス: 特権アカウントに対する "アカウントは重要なので委任できない" の分析](/archive/blogs/poshchap/security-focus-analysing-account-is-sensitive-and-cannot-be-delegated-for-privileged-accounts)」および「[Kerberos 認証のツールと設定](https://technet.microsoft.com/library/cc738673(v=ws.10).aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-130">For more information, see [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts](/archive/blogs/poshchap/security-focus-analysing-account-is-sensitive-and-cannot-be-delegated-for-privileged-accounts) and [Kerberos Authentication Tools and Settings](https://technet.microsoft.com/library/cc738673(v=ws.10).aspx).</span></span>

### <a name="pros"></a><span data-ttu-id="bb5fa-131">長所</span><span class="sxs-lookup"><span data-stu-id="bb5fa-131">Pros</span></span>

- <span data-ttu-id="bb5fa-132">特別なコーディングが必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-132">Requires no special coding.</span></span>

### <a name="cons"></a><span data-ttu-id="bb5fa-133">短所</span><span class="sxs-lookup"><span data-stu-id="bb5fa-133">Cons</span></span>

- <span data-ttu-id="bb5fa-134">WinRM の次ホップはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-134">Does not support the second hop for WinRM.</span></span>
- <span data-ttu-id="bb5fa-135">資格情報が使われる場所を制御できず、セキュリティの脆弱性が発生します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-135">Provides no control over where credentials are used, creating a security vulnerability.</span></span>

## <a name="kerberos-constrained-delegation"></a><span data-ttu-id="bb5fa-136">Kerberos の制約付き委任</span><span class="sxs-lookup"><span data-stu-id="bb5fa-136">Kerberos constrained delegation</span></span>

<span data-ttu-id="bb5fa-137">従来の (リソースに基づかない) 制約付き委任を使って、次ホップを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-137">You can use legacy constrained delegation (not resource-based) to make the second hop.</span></span> <span data-ttu-id="bb5fa-138">プロトコル遷移を許可するには、[任意の認証プロトコルを使う] オプションを使用して Kerberos の制約付き委任を構成します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-138">Configure Kerberos constrained delegation with the option "Use any authentication protocol" to allow protocol transition.</span></span>

> [!NOTE]
> <span data-ttu-id="bb5fa-139">**[アカウントは重要なので委任できない]** プロパティが設定されている Active Directory アカウントは委任できません。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-139">Active Directory accounts that have the **Account is sensitive and cannot be delegated** property set cannot be delegated.</span></span> <span data-ttu-id="bb5fa-140">詳しくは、「[Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts (セキュリティ フォーカス: 特権アカウントに対する "アカウントは重要なので委任できない" の分析)](/archive/blogs/poshchap/security-focus-analysing-account-is-sensitive-and-cannot-be-delegated-for-privileged-accounts)」および「[Kerberos Authentication Tools and Settings (Kerberos 認証のツールと設定)](https://technet.microsoft.com/library/cc738673(v=ws.10).aspx)」をご覧ください</span><span class="sxs-lookup"><span data-stu-id="bb5fa-140">For more information, see [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts](/archive/blogs/poshchap/security-focus-analysing-account-is-sensitive-and-cannot-be-delegated-for-privileged-accounts) and [Kerberos Authentication Tools and Settings](https://technet.microsoft.com/library/cc738673(v=ws.10).aspx)</span></span>

### <a name="pros"></a><span data-ttu-id="bb5fa-141">長所</span><span class="sxs-lookup"><span data-stu-id="bb5fa-141">Pros</span></span>

- <span data-ttu-id="bb5fa-142">特別なコーディングが必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-142">Requires no special coding</span></span>

### <a name="cons"></a><span data-ttu-id="bb5fa-143">短所</span><span class="sxs-lookup"><span data-stu-id="bb5fa-143">Cons</span></span>

- <span data-ttu-id="bb5fa-144">WinRM の次ホップはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-144">Does not support the second hop for WinRM.</span></span>
- <span data-ttu-id="bb5fa-145">リモート サーバー (_ServerB_) の Active Directory オブジェクトで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-145">Must be configured on the Active Directory object of the remote server (_ServerB_).</span></span>
- <span data-ttu-id="bb5fa-146">1 つのドメインに制限されます。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-146">Limited to one domain.</span></span> <span data-ttu-id="bb5fa-147">複数のドメインまたはフォレストにまたがることはできません。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-147">Cannot cross domains or forests.</span></span>
- <span data-ttu-id="bb5fa-148">オブジェクトとサービス プリンシパル名 (SPN) を更新する権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-148">Requires rights to update objects and Service Principal Names (SPNs).</span></span>

## <a name="resource-based-kerberos-constrained-delegation"></a><span data-ttu-id="bb5fa-149">リソースに基づく Kerberos の制約付き委任</span><span class="sxs-lookup"><span data-stu-id="bb5fa-149">Resource-based Kerberos constrained delegation</span></span>

<span data-ttu-id="bb5fa-150">リソースに基づく Kerberos の制約付き委任 (Windows Server 2012 で導入) を使って、リソースが存在するサーバー オブジェクトでの資格情報の委任を構成します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-150">Using resource-based Kerberos constrained delegation (introduced in Windows Server 2012), you configure credential delegation on the server object where resources reside.</span></span> <span data-ttu-id="bb5fa-151">上で説明した次ホップのシナリオでは、_ServerC_ を構成して、受け入れる委任された資格情報の委任元を指定します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-151">In the second hop scenario described above, you configure _ServerC_ to specify from where it will accept delegated credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="bb5fa-152">**[アカウントは重要なので委任できない]** プロパティが設定されている Active Directory アカウントは委任できません。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-152">Active Directory accounts that have the **Account is sensitive and cannot be delegated** property set cannot be delegated.</span></span> <span data-ttu-id="bb5fa-153">詳しくは、「[Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts (セキュリティ フォーカス: 特権アカウントに対する "アカウントは重要なので委任できない" の分析)](/archive/blogs/poshchap/security-focus-analysing-account-is-sensitive-and-cannot-be-delegated-for-privileged-accounts)」および「[Kerberos Authentication Tools and Settings (Kerberos 認証のツールと設定)](https://technet.microsoft.com/library/cc738673(v=ws.10).aspx)」をご覧ください</span><span class="sxs-lookup"><span data-stu-id="bb5fa-153">For more information, see [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts](/archive/blogs/poshchap/security-focus-analysing-account-is-sensitive-and-cannot-be-delegated-for-privileged-accounts) and [Kerberos Authentication Tools and Settings](https://technet.microsoft.com/library/cc738673(v=ws.10).aspx)</span></span>

### <a name="pros"></a><span data-ttu-id="bb5fa-154">長所</span><span class="sxs-lookup"><span data-stu-id="bb5fa-154">Pros</span></span>

- <span data-ttu-id="bb5fa-155">資格情報が保存されません。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-155">Credentials are not stored.</span></span>
- <span data-ttu-id="bb5fa-156">PowerShell コマンドレットを使った構成が比較的簡単です。特別なコーディングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-156">Relatively easy to configure by using PowerShell cmdlets--no special coding required.</span></span>
- <span data-ttu-id="bb5fa-157">特別なドメイン アクセスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-157">No special domain access is required.</span></span>
- <span data-ttu-id="bb5fa-158">複数のドメインおよびフォレストをまたいで動作します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-158">Works across domains and forests.</span></span>
- <span data-ttu-id="bb5fa-159">PowerShell のコード。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-159">PowerShell code.</span></span>

### <a name="cons"></a><span data-ttu-id="bb5fa-160">短所</span><span class="sxs-lookup"><span data-stu-id="bb5fa-160">Cons</span></span>

- <span data-ttu-id="bb5fa-161">Windows Server 2012 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-161">Requires Windows Server 2012 or later.</span></span>
- <span data-ttu-id="bb5fa-162">WinRM の次ホップはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-162">Does not support the second hop for WinRM.</span></span>
- <span data-ttu-id="bb5fa-163">オブジェクトとサービス プリンシパル名 (SPN) を更新する権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-163">Requires rights to update objects and Service Principal Names (SPNs).</span></span>

### <a name="example"></a><span data-ttu-id="bb5fa-164">例</span><span class="sxs-lookup"><span data-stu-id="bb5fa-164">Example</span></span>

<span data-ttu-id="bb5fa-165">_ServerB_ からの委任された資格情報を許可するように _ServerC_ でリソースに基づく制約付き委任を構成する PowerShell の例を示します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-165">Let's look at a PowerShell example that configures resource based constrained delegation on _ServerC_ to allow delegated credentials from a _ServerB_.</span></span> <span data-ttu-id="bb5fa-166">この例では、すべてのサーバーが Windows Server 2012 以降を実行しており、いずれかのサーバーが属している各ドメインに少なくとも 1 つの Windows Server 2012 ドメイン コントローラーがあるものとします。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-166">This example assumes that all servers are running Windows Server 2012 or later, and that there is at least one Windows Server 2012 domain controller each domain to which any of the servers belong.</span></span>

<span data-ttu-id="bb5fa-167">制約付き委任を構成する前に、`RSAT-AD-PowerShell` 機能を追加して Active Directory PowerShell モジュールをインストールした後、そのモジュールをセッションにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-167">Before you can configure constrained delegation, you must add the `RSAT-AD-PowerShell` feature to install the Active Directory PowerShell module, and then import that module into your session:</span></span>

```powershell
PS C:\> Add-WindowsFeature RSAT-AD-PowerShell
PS C:\> Import-Module ActiveDirectory
```

<span data-ttu-id="bb5fa-168">使用できる複数のコマンドレットに、**PrincipalsAllowedToDelegateToAccount** パラメーターが追加されています。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-168">Several available cmdlets now have a **PrincipalsAllowedToDelegateToAccount** parameter:</span></span>

```powershell
PS C:\> Get-Command -ParameterName PrincipalsAllowedToDelegateToAccount

CommandType Name                 ModuleName
----------- ----                 ----------
Cmdlet      New-ADComputer       ActiveDirectory
Cmdlet      New-ADServiceAccount ActiveDirectory
Cmdlet      New-ADUser           ActiveDirectory
Cmdlet      Set-ADComputer       ActiveDirectory
Cmdlet      Set-ADServiceAccount ActiveDirectory
Cmdlet      Set-ADUser           ActiveDirectory
```

<span data-ttu-id="bb5fa-169">**PrincipalsAllowedToDelegateToAccount** パラメーターは、Active Directory オブジェクトの **msDS-AllowedToActOnBehalfOfOtherIdentity** 属性を設定します。この属性には、関連付けられたアカウント (この例では、_Server_ のコンピューター アカウント) に資格情報を委任する権限を持つアカウントを指定するアクセス制御リスト (ACL) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-169">The **PrincipalsAllowedToDelegateToAccount** parameter sets the Active Directory object attribute **msDS-AllowedToActOnBehalfOfOtherIdentity**, which contains an access control list (ACL) that specifies which accounts have permission to delegate credentials to the associated account (in our example, it will be the machine account for _Server_).</span></span>

<span data-ttu-id="bb5fa-170">サーバーを表すために使用する変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-170">Now let's set up the variables we'll use to represent the servers:</span></span>

```powershell
# Set up variables for reuse
$ServerA = $env:COMPUTERNAME
$ServerB = Get-ADComputer -Identity ServerB
$ServerC = Get-ADComputer -Identity ServerC
```

<span data-ttu-id="bb5fa-171">WinRM (したがって PowerShell リモート処理) は、既定でコンピューター アカウントとして実行します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-171">WinRM (and therefore PowerShell remoting) runs as the computer account by default.</span></span> <span data-ttu-id="bb5fa-172">これは、`winrm` サービスの **StartName** プロパティを見て確認できます。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-172">You can see this by looking at the **StartName** property of the `winrm` service:</span></span>

```powershell
PS C:\> Get-WmiObject win32_service -filter 'name="winrm"' | Format-List StartName

StartName : NT AUTHORITY\NetworkService
```

<span data-ttu-id="bb5fa-173">_ServerC_ で _ServerB_ の PowerShell リモート処理セッションからの委任を許可するため、_ServerC_ の **PrincipalsAllowedToDelegateToAccount** パラメーターを _ServerB_ のコンピューター オブジェクトに設定することによって、アクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-173">For _ServerC_ to allow delegation from a PowerShell remoting session on _ServerB_, we will grant access by setting the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to the computer object of _ServerB_:</span></span>

```powershell
# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB

# Check the value of the attribute directly
$x = Get-ADComputer -Identity $ServerC -Properties msDS-AllowedToActOnBehalfOfOtherIdentity
$x.'msDS-AllowedToActOnBehalfOfOtherIdentity'.Access

# Check the value of the attribute indirectly
Get-ADComputer -Identity $ServerC -Properties PrincipalsAllowedToDelegateToAccount
```

<span data-ttu-id="bb5fa-174">Kerberos の[キー配布センター (KDC)](/windows/win32/secauthn/key-distribution-center) は、拒否されたアクセス試行を 15 分間キャッシュします (ネガティブ キャッシュ)。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-174">The Kerberos [Key Distribution Center (KDC)](/windows/win32/secauthn/key-distribution-center) caches denied access attempts (negative cache) for 15 minutes.</span></span> <span data-ttu-id="bb5fa-175">_ServerB_ が以前に _ServerC_ にアクセスしようとした場合、次のコマンドを呼び出すことによって _ServerB_ 上のキャッシュをクリアする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-175">If _ServerB_ has previously attempted to access _ServerC_, you will need to clear the cache on _ServerB_ by invoking the following command:</span></span>

```powershell
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    klist purge -li 0x3e7
}
```

<span data-ttu-id="bb5fa-176">キャッシュを消去するには、コンピューターを再起動するか、15 分以上待つのでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-176">You could also restart the computer, or wait at least 15 minutes to clear the cache.</span></span>

<span data-ttu-id="bb5fa-177">キャッシュをクリアした後は、_ServerA_ から _ServerB_ を経由して _ServerC_ にコードを正常に実行できます。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-177">After clearing the cache, you can successfully run code from _ServerA_ through _ServerB_ to _ServerC_:</span></span>

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

<span data-ttu-id="bb5fa-178">この例では、_ServerB_ が `$ServerC` 変数を認識できるようにするため、`$using` 変数を使用しています。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-178">In this example, the `$using` variable is used to make the `$ServerC` variable visible to _ServerB_.</span></span>
<span data-ttu-id="bb5fa-179">`$using` 変数については、「[About Remote Variables](https://technet.microsoft.com/library/jj149005.aspx)」 (リモート変数について) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-179">For more information about the `$using` variable, see [about_Remote_Variables](https://technet.microsoft.com/library/jj149005.aspx).</span></span>

<span data-ttu-id="bb5fa-180">複数のサーバーが _ServerC_ に資格情報を委任できるようにするには、_ServerC_ で **PrincipalsAllowedToDelegateToAccount** パラメーターの値に配列を設定します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-180">To allow multiple servers to delegate credentials to _ServerC_, set the value of the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to an array:</span></span>

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

<span data-ttu-id="bb5fa-181">ドメインをまたいで次ホップを実行する場合は、_ServerB_ が属するドメインのドメイン コントローラーの完全修飾ドメイン名 (FQDN) を追加します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-181">If you want to make the second hop across domains, add fully-qualified domain name (FQDN) of the domain controller of the domain to which _ServerB_ belongs:</span></span>

```powershell
# For ServerC in Contoso domain and ServerB in other domain
$ServerB = Get-ADComputer -Identity ServerB -Server dc1.alpineskihouse.com
$ServerC = Get-ADComputer -Identity ServerC
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB
```

<span data-ttu-id="bb5fa-182">ServerC に資格情報を委任する機能を削除するには、_ServerC_ の **PrincipalsAllowedToDelegateToAccount** パラメーターの値に `$null` を設定します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-182">To remove the ability to delegate credentials to ServerC, set the value of the **PrincipalsAllowedToDelegateToAccount** parameter on _ServerC_ to `$null`:</span></span>

```powershell
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $null
```

### <a name="information-on-resource-based-kerberos-constrained-delegation"></a><span data-ttu-id="bb5fa-183">リソースに基づく Kerberos の制約付き委任についての情報</span><span class="sxs-lookup"><span data-stu-id="bb5fa-183">Information on resource-based Kerberos constrained delegation</span></span>

- <span data-ttu-id="bb5fa-184">[Kerberos 認証の新機能](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831747(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="bb5fa-184">[What's New in Kerberos Authentication](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831747(v=ws.11))</span></span>
- [<span data-ttu-id="bb5fa-185">Windows Server 2012 による Kerberos の制約付き委任の処理方法、第 1 部</span><span class="sxs-lookup"><span data-stu-id="bb5fa-185">How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 1</span></span>](https://www.itprotoday.com/windows-server/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-1)
- [<span data-ttu-id="bb5fa-186">Windows Server 2012 による Kerberos の制約付き委任の処理方法、第 2 部</span><span class="sxs-lookup"><span data-stu-id="bb5fa-186">How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 2</span></span>](https://www.itprotoday.com/windows-server/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-2)
- [<span data-ttu-id="bb5fa-187">統合 Windows 認証での Azure Active Directory アプリケーション プロキシ展開に対する Kerberos の制約付き委任の概要</span><span class="sxs-lookup"><span data-stu-id="bb5fa-187">Understanding Kerberos Constrained Delegation for Azure Active Directory Application Proxy Deployments with Integrated Windows Authentication</span></span>](https://aka.ms/kcdpaper)
- <span data-ttu-id="bb5fa-188">[[MS-ADA2]: Active Directory スキーマ属性 M2.210 Attribute msDS-AllowedToActOnBehalfOfOtherIdentity](/openspecs/windows_protocols/ms-ada2/cea4ac11-a4b2-4f2d-84cc-aebb4a4ad405)</span><span class="sxs-lookup"><span data-stu-id="bb5fa-188">[[MS-ADA2]: Active Directory Schema Attributes M2.210 Attribute msDS-AllowedToActOnBehalfOfOtherIdentity](/openspecs/windows_protocols/ms-ada2/cea4ac11-a4b2-4f2d-84cc-aebb4a4ad405)</span></span>
- <span data-ttu-id="bb5fa-189">[[MS-SFU]: Kerberos プロトコル拡張: Service for User および制約付き委任プロトコルの 1.3.2 S4U2proxy](/openspecs/windows_protocols/ms-sfu/bde93b0e-f3c9-4ddf-9f44-e1453be7af5a)</span><span class="sxs-lookup"><span data-stu-id="bb5fa-189">[[MS-SFU]: Kerberos Protocol Extensions: Service for User and Constrained Delegation Protocol 1.3.2 S4U2proxy](/openspecs/windows_protocols/ms-sfu/bde93b0e-f3c9-4ddf-9f44-e1453be7af5a)</span></span>
- [<span data-ttu-id="bb5fa-190">PrincipalsAllowedToDelegateToAccount を使用した制約付き委任を使用しないリモート管理</span><span class="sxs-lookup"><span data-stu-id="bb5fa-190">Remote Administration Without Constrained Delegation Using PrincipalsAllowedToDelegateToAccount</span></span>](/archive/blogs/taylorb/remote-administration-without-constrained-delegation-using-principalsallowedtodelegatetoaccount)

## <a name="pssessionconfiguration-using-runas"></a><span data-ttu-id="bb5fa-191">RunAs を使用する PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="bb5fa-191">PSSessionConfiguration using RunAs</span></span>

<span data-ttu-id="bb5fa-192">_ServerB_ にセッション構成を作成し、その **RunAsCredential** パラメーターを設定できます。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-192">You can create a session configuration on _ServerB_ and set its **RunAsCredential** parameter.</span></span>

<span data-ttu-id="bb5fa-193">PSSessionConfiguration と RunAs を使って次ホップの問題を解決する方法については、「[Another solution to multi-hop PowerShell remoting](/archive/blogs/sergey_babkins_blog/another-solution-to-multi-hop-powershell-remoting)」 (マルチホップ PowerShell リモート処理に対する別の解決策) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-193">For information about using PSSessionConfiguration and RunAs to solve the second hop problem, see [Another solution to multi-hop PowerShell remoting](/archive/blogs/sergey_babkins_blog/another-solution-to-multi-hop-powershell-remoting).</span></span>

### <a name="pros"></a><span data-ttu-id="bb5fa-194">長所</span><span class="sxs-lookup"><span data-stu-id="bb5fa-194">Pros</span></span>

- <span data-ttu-id="bb5fa-195">WMF 3.0 以降のすべてのサーバーで機能します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-195">Works with any server with WMF 3.0 or later.</span></span>

### <a name="cons"></a><span data-ttu-id="bb5fa-196">短所</span><span class="sxs-lookup"><span data-stu-id="bb5fa-196">Cons</span></span>

- <span data-ttu-id="bb5fa-197">すべての中間サーバー (_ServerB_) で **PSSessionConfiguration** と **RunAs** を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-197">Requires configuration of **PSSessionConfiguration** and **RunAs** on every intermediate server (_ServerB_).</span></span>
- <span data-ttu-id="bb5fa-198">ドメインの **RunAs** アカウントを使うときは、パスワードの管理が必要です。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-198">Requires password maintenance when using a domain **RunAs** account</span></span>

## <a name="just-enough-administration-jea"></a><span data-ttu-id="bb5fa-199">Just Enough Administration (JEA)</span><span class="sxs-lookup"><span data-stu-id="bb5fa-199">Just Enough Administration (JEA)</span></span>

<span data-ttu-id="bb5fa-200">JEA では、PowerShell セッションの間に管理者が実行できるコマンドを制限できます。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-200">JEA allows you to restrict what commands an administrator can run during a PowerShell session.</span></span> <span data-ttu-id="bb5fa-201">これを使って、次ホップの問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-201">It can be used to solve the second hop problem.</span></span>

<span data-ttu-id="bb5fa-202">JEA については、「[Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-202">For information about JEA, see [Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview).</span></span>

### <a name="pros"></a><span data-ttu-id="bb5fa-203">長所</span><span class="sxs-lookup"><span data-stu-id="bb5fa-203">Pros</span></span>

- <span data-ttu-id="bb5fa-204">仮想アカウントを使う場合にパスワードの管理が不要です。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-204">No password maintenance when using a virtual account.</span></span>

### <a name="cons"></a><span data-ttu-id="bb5fa-205">短所</span><span class="sxs-lookup"><span data-stu-id="bb5fa-205">Cons</span></span>

- <span data-ttu-id="bb5fa-206">WMF 5.0 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-206">Requires WMF 5.0 or later.</span></span>
- <span data-ttu-id="bb5fa-207">すべての中間サーバー (_ServerB_) の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-207">Requires configuration on every intermediate server (_ServerB_).</span></span>

## <a name="pass-credentials-inside-an-invoke-command-script-block"></a><span data-ttu-id="bb5fa-208">Invoke-Command スクリプト ブロックの内部で資格情報を渡す</span><span class="sxs-lookup"><span data-stu-id="bb5fa-208">Pass credentials inside an Invoke-Command script block</span></span>

<span data-ttu-id="bb5fa-209">[Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) コマンドレットを呼び出すときに **ScriptBlock** パラメーターの内部で資格情報を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-209">You can pass credentials inside the **ScriptBlock** parameter of a call to the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet.</span></span>

### <a name="pros"></a><span data-ttu-id="bb5fa-210">長所</span><span class="sxs-lookup"><span data-stu-id="bb5fa-210">Pros</span></span>

- <span data-ttu-id="bb5fa-211">特別なサーバー構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-211">Does not require special server configuration.</span></span>
- <span data-ttu-id="bb5fa-212">WMF 2.0 以降を実行する任意のサーバーで動作します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-212">Works on any server running WMF 2.0 or later.</span></span>

### <a name="cons"></a><span data-ttu-id="bb5fa-213">短所</span><span class="sxs-lookup"><span data-stu-id="bb5fa-213">Cons</span></span>

- <span data-ttu-id="bb5fa-214">面倒なコード技法が必要です。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-214">Requires an awkward code technique.</span></span>
- <span data-ttu-id="bb5fa-215">WMF 2.0 を実行している場合は、リモート セッションに引数を渡すために異なる構文が必要です。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-215">If running WMF 2.0, requires different syntax for passing arguments to a remote session.</span></span>

### <a name="example"></a><span data-ttu-id="bb5fa-216">例</span><span class="sxs-lookup"><span data-stu-id="bb5fa-216">Example</span></span>

<span data-ttu-id="bb5fa-217">**Invoke-Command** スクリプト ブロックで資格情報を渡す方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bb5fa-217">The following example shows how to pass credentials in an **Invoke-Command** script block:</span></span>

```powershell
# This works without delegation, passing fresh creds
# Note $Using:Cred in nested request
$cred = Get-Credential Contoso\Administrator
Invoke-Command -ComputerName ServerB -Credential $cred -ScriptBlock {
    hostname
    Invoke-Command -ComputerName ServerC -Credential $Using:cred -ScriptBlock {hostname}
}
```

## <a name="see-also"></a><span data-ttu-id="bb5fa-218">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb5fa-218">See also</span></span>

[<span data-ttu-id="bb5fa-219">PowerShell リモート処理のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="bb5fa-219">PowerShell Remoting Security Considerations</span></span>](WinRMSecurity.md)
