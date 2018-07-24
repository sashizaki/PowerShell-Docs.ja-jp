---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成データでの資格情報オプション
ms.openlocfilehash: 12bb8d8ce5fc4685e583e74d411b098320ac4fd4
ms.sourcegitcommit: 77f62a55cac8c13d69d51eef5fade18f71d66955
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2018
ms.locfileid: "39093679"
---
# <a name="credentials-options-in-configuration-data"></a><span data-ttu-id="3d909-103">構成データでの資格情報オプション</span><span class="sxs-lookup"><span data-stu-id="3d909-103">Credentials Options in Configuration Data</span></span>
><span data-ttu-id="3d909-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="3d909-104">Applies To: Windows PowerShell 5.0</span></span>

## <a name="plain-text-passwords-and-domain-users"></a><span data-ttu-id="3d909-105">プレーンテキスト パスワードとドメイン ユーザー</span><span class="sxs-lookup"><span data-stu-id="3d909-105">Plain Text Passwords and Domain Users</span></span>

<span data-ttu-id="3d909-106">暗号化されていない資格情報を含む DSC 構成では、プレーンテキスト パスワードについてのエラー メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="3d909-106">DSC configurations containing a credential without encryption will generate an error message about plain text passwords.</span></span>
<span data-ttu-id="3d909-107">また、DSC では、ドメイン資格情報を使用すると警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3d909-107">Also, DSC will generate a warning when using domain credentials.</span></span>
<span data-ttu-id="3d909-108">これらのエラーや警告メッセージが表示されないようにするには、次の DSC 構成データ キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d909-108">To suppress these error and warning messages use the DSC configuration data keywords:</span></span>
* <span data-ttu-id="3d909-109">**PsDscAllowPlainTextPassword**</span><span class="sxs-lookup"><span data-stu-id="3d909-109">**PsDscAllowPlainTextPassword**</span></span>
* <span data-ttu-id="3d909-110">**PsDscAllowDomainUser**</span><span class="sxs-lookup"><span data-stu-id="3d909-110">**PsDscAllowDomainUser**</span></span>

> [!NOTE]
> <span data-ttu-id="3d909-111">暗号化されていないプレーンテキスト パスワードを格納/送信するのは一般的には安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="3d909-111">Storing/transmitting plaintext passwords unencrypted is generally not secure.</span></span> <span data-ttu-id="3d909-112">このトピックで後述する手法を使って資格情報をセキュリティ保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3d909-112">Securing credentials by using the techniques covered later in this topic is recommended.</span></span>
> <span data-ttu-id="3d909-113">Azure Automation DSC サービスでは、構成でコンパイルされ、安全に格納される資格情報を一元的に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="3d909-113">The Azure Automation DSC service allows you to centrally manage credentials to be compiled in configurations and stored securely.</span></span>
> <span data-ttu-id="3d909-114">詳細について、「[DSC 構成のコンパイル/資格情報資産](/azure/automation/automation-dsc-compile#credential-assets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d909-114">For information, see: [Compiling DSC Configurations / Credential Assets](/azure/automation/automation-dsc-compile#credential-assets)</span></span>

<span data-ttu-id="3d909-115">プレーンテキストの資格情報を渡す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3d909-115">The following is an example of passing plain text credentials:</span></span>

```powershell
#Prompt user for their credentials
#credentials will be unencrypted in the MOF
$promptedCreds = get-credential -Message "Please enter your credentials to generate a DSC MOF:"

# Store passwords in plaintext, in the document itself
# will also be stored in plaintext in the mof
$password = "ThisIsAPlaintextPassword" | ConvertTo-SecureString -asPlainText -Force
$username = "User1"
[PSCredential] $credential = New-Object System.Management.Automation.PSCredential($username,$password)

# DSC requires explicit confirmation before storing passwords insecurely
$ConfigurationData = @{
    AllNodes = @(
        @{
            # The "*" means "all nodes named in ConfigData" so we don't have to repeat ourselves
            NodeName="*"
            PSDscAllowPlainTextPassword = $true
        },
        #however, each node still needs to be explicitly defined for "*" to have meaning
        @{
            NodeName = "TestMachine1"
        },
        #we can also use a property to define node-specific passwords, although this is no more secure
        @{
            NodeName = "TestMachine2";
            UserName = "User2"
            LocalPassword = "ThisIsYetAnotherPlaintextPassword"
        }
        )
}
configuration unencryptedPasswordDemo
{
    Node "TestMachine1"
    {
        # We use the plaintext password to generate a new account
        User User1
        {
            UserName = $username
            Password = $credential
            Description = "local account"
            Ensure = "Present"
            Disabled = $false
            PasswordNeverExpires = $true
            PasswordChangeRequired = $false
        }
        # We use the prompted password to add this account to the local admins group
        Group addToAdmin
        {
            # Ensure the user exists before we add the user to a group
            DependsOn = "[User]User1"
            Credential = $promptedCreds
            GroupName = "Administrators"
            Ensure = "Present"
            MembersToInclude = "User1"
        }
    }

    Node "TestMachine2"
    {
        # Now we'll use a node-specific password to this machine
        $password = $Node.LocalPass | ConvertTo-SecureString -asPlainText -Force
        $username = $node.UserName
        [PSCredential] $nodeCred = New-Object System.Management.Automation.PSCredential($username,$password)

        User User2
        {
            UserName = $username
            Password = $nodeCred
            Description = "local account"
            Ensure = "Present"
            Disabled = $false
            PasswordNeverExpires = $true
            PasswordChangeRequired = $false
        }

        Group addToAdmin
        {
            Credential = $domain
            GroupName = "Administrators"
            DependsOn = "[User]User2"
            Ensure = "Present"
            MembersToInclude = "User2"
        }
    }

}
# We declared the ConfigurationData in a local variable, but we need to pass it in to our configuration function
# We need to invoke the configuration function we created to generate a MOF
unencryptedPasswordDemo -ConfigurationData $ConfigurationData
# We need to pass the MOF to the machines we named.
#-wait: doesn't use jobs so we get blocked at the prompt until the configuration is done
#-verbose: so we can see what's going on and catch any errors
#-force: for testing purposes, I run start-dscconfiguration frequently + want to make sure i'm
#        not blocked by previous configurations that are still running
Start-DscConfiguration ./unencryptedPasswordDemo -verbose -wait -force
```

## <a name="handling-credentials-in-dsc"></a><span data-ttu-id="3d909-116">DSC での資格情報の処理</span><span class="sxs-lookup"><span data-stu-id="3d909-116">Handling Credentials in DSC</span></span>

<span data-ttu-id="3d909-117">DSC 構成リソースは、既定で `Local System` として実行されます。</span><span class="sxs-lookup"><span data-stu-id="3d909-117">DSC configuration resources run as `Local System` by default.</span></span>
<span data-ttu-id="3d909-118">ただし、`Package` リソースでソフトウェアを特定のユーザー アカウントでインストールする必要がある場合など、リソースによっては資格情報が必要となることがあります。</span><span class="sxs-lookup"><span data-stu-id="3d909-118">However, some resources need a credential, for example when the `Package` resource needs to install software under a specific user account.</span></span>

<span data-ttu-id="3d909-119">以前のリソースでは、ハード コードされた `Credential` プロパティ名使用してこのことに対処していました。</span><span class="sxs-lookup"><span data-stu-id="3d909-119">Earlier resources used a hard-coded `Credential` property name to handle this.</span></span>
<span data-ttu-id="3d909-120">WMF 5.0 では、すべてのリソースに対して自動 `PsDscRunAsCredential` プロパティが追加されました。</span><span class="sxs-lookup"><span data-stu-id="3d909-120">WMF 5.0 added an automatic `PsDscRunAsCredential` property for all resources.</span></span>
<span data-ttu-id="3d909-121">`PsDscRunAsCredential` の使用の詳細については、「[ユーザーの資格情報を指定して DSC を実行する](runAsUser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d909-121">For information about using `PsDscRunAsCredential`, see [Running DSC with user credentials](runAsUser.md).</span></span>
<span data-ttu-id="3d909-122">新しいリソースおよびカスタム リソースでは、資格情報の独自のプロパティを作成する代わりに、この自動プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3d909-122">Newer resources and custom resources can use this automatic property instead of creating their own property for credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="3d909-123">一部のリソースは特定の理由のために複数の資格情報を使用するように設計されており、それらのリソースには独自の資格情報プロパティがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3d909-123">The design of some resources are to use multiple credentials for a specific reason, and they will have their own credential properties.</span></span>

<span data-ttu-id="3d909-124">リソースの使用可能な資格情報プロパティを検索するには、ISE で `Get-DscResource -Name ResourceName -Syntax` または Intellisense を使用します (`CTRL+SPACE`)。</span><span class="sxs-lookup"><span data-stu-id="3d909-124">To find the available credential properties on a resource use either `Get-DscResource -Name ResourceName -Syntax` or the Intellisense in the ISE (`CTRL+SPACE`).</span></span>

```powershell
PS C:\> Get-DscResource -Name Group -Syntax
Group [String] #ResourceName
{
    GroupName = [string]
    [Credential = [PSCredential]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Members = [string[]]]
    [MembersToExclude = [string[]]]
    [MembersToInclude = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
}
```

<span data-ttu-id="3d909-125">この例では、`PSDesiredStateConfiguration` 組み込み DSC リソース モジュールの [Group](https://msdn.microsoft.com/powershell/dsc/groupresource) リソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d909-125">This example uses a [Group](https://msdn.microsoft.com/powershell/dsc/groupresource) resource from the `PSDesiredStateConfiguration` built-in DSC resource module.</span></span>
<span data-ttu-id="3d909-126">ローカル グループを作成し、メンバーを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="3d909-126">It can create local groups and add or remove members.</span></span>
<span data-ttu-id="3d909-127">`Credential` プロパティと、自動 `PsDscRunAsCredential` プロパティの両方を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3d909-127">It accepts both the `Credential` property and the automatic `PsDscRunAsCredential` property.</span></span>
<span data-ttu-id="3d909-128">ただし、リソースでは `Credential` プロパティのみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3d909-128">However, the resource only uses the `Credential` property.</span></span>

<span data-ttu-id="3d909-129">`PsDscRunAsCredential`プロパティの詳細については、「[ユーザーの資格情報を指定して DSC を実行する](runAsUser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d909-129">For more information about the `PsDscRunAsCredential` property, see [Running DSC with user credentials](runAsUser.md).</span></span>

## <a name="example-the-group-resource-credential-property"></a><span data-ttu-id="3d909-130">例: Group リソース資格情報プロパティ</span><span class="sxs-lookup"><span data-stu-id="3d909-130">Example: The Group resource Credential property</span></span>

<span data-ttu-id="3d909-131">DSC は `Local System` で実行されるため、ローカル ユーザーおよびグループを変更するためのアクセス許可が既にあります。</span><span class="sxs-lookup"><span data-stu-id="3d909-131">DSC runs under `Local System`, so it already has permissions to change local users and groups.</span></span>
<span data-ttu-id="3d909-132">追加されたメンバーがローカル アカウントの場合、資格情報は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3d909-132">If the member added is a local account, then no credential is necessary.</span></span>
<span data-ttu-id="3d909-133">`Group` リソースがローカル グループにドメイン アカウントを追加する場合、資格情報が必要となります。</span><span class="sxs-lookup"><span data-stu-id="3d909-133">If the `Group` resource adds a domain account to the local group, then a credential is necessary.</span></span>

<span data-ttu-id="3d909-134">Active Directory への匿名クエリは許可されません。</span><span class="sxs-lookup"><span data-stu-id="3d909-134">Anonymous queries to Active Directory are not allowed.</span></span>
<span data-ttu-id="3d909-135">`Group` リソースの `Credential` プロパティは、Active Directory のクエリに使用されるドメイン アカウントです。</span><span class="sxs-lookup"><span data-stu-id="3d909-135">The `Credential` property of the `Group` resource is the domain account used to query Active Directory.</span></span>
<span data-ttu-id="3d909-136">既定では、ユーザーは Active Directory 内の大部分のオブジェクトを*読み取る*ことができるため、ほとんどの場合これは汎用ユーザー アカウントです。</span><span class="sxs-lookup"><span data-stu-id="3d909-136">For most purposes this could be a generic user account, because by default users can *read* most of the objects in Active Directory.</span></span>

## <a name="example-configuration"></a><span data-ttu-id="3d909-137">構成の例</span><span class="sxs-lookup"><span data-stu-id="3d909-137">Example Configuration</span></span>

<span data-ttu-id="3d909-138">次のコード例では、DSC を使用してローカル グループにドメイン ユーザーを設定します。</span><span class="sxs-lookup"><span data-stu-id="3d909-138">The following example code uses DSC to populate a local group with a domain user:</span></span>

```powershell
Configuration DomainCredentialExample
{
    param
    (
        [PSCredential] $DomainCredential
    )
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    node localhost
    {
        Group DomainUserToLocalGroup
        {
            GroupName        = 'ApplicationAdmins'
            MembersToInclude = 'contoso\alice'
            Credential       = $DomainCredential
        }
    }
}

$cred = Get-Credential -UserName contoso\genericuser -Message "Password please"
DomainCredentialExample -DomainCredential $cred
```

<span data-ttu-id="3d909-139">このコードでは、エラーと警告メッセージの両方が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3d909-139">This code generates both an error and warning message:</span></span>

```
ConvertTo-MOFInstance : System.InvalidOperationException error processing
property 'Credential' OF TYPE 'Group': Converting and storing encrypted
passwords as plain text is not recommended. For more information on securing
credentials in MOF file, please refer to MSDN blog:
http://go.microsoft.com/fwlink/?LinkId=393729

At line:11 char:9
+   Group
At line:297 char:16
+     $aliasId = ConvertTo-MOFInstance $keywordName $canonicalizedValue
+                ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Write-Error], InvalidOperationException
    + FullyQualifiedErrorId : FailToProcessProperty,ConvertTo-MOFInstance

WARNING: It is not recommended to use domain credential for node 'localhost'.
In order to suppress the warning, you can add a property named
'PSDscAllowDomainUser' with a value of $true to your DSC configuration data
for node 'localhost'.
```

<span data-ttu-id="3d909-140">この例には、次の 2 つの問題があります。</span><span class="sxs-lookup"><span data-stu-id="3d909-140">This example has two issues:</span></span>
1. <span data-ttu-id="3d909-141">プレーンテキスト パスワードが推奨されないことを説明するエラー。</span><span class="sxs-lookup"><span data-stu-id="3d909-141">An error explains that plain text passwords are not recommended</span></span>
2. <span data-ttu-id="3d909-142">ドメイン資格情報を使用しないよう勧める警告。</span><span class="sxs-lookup"><span data-stu-id="3d909-142">A warning advises against using a domain credential</span></span>

## <a name="psdscallowplaintextpassword"></a><span data-ttu-id="3d909-143">PsDscAllowPlainTextPassword</span><span class="sxs-lookup"><span data-stu-id="3d909-143">PsDscAllowPlainTextPassword</span></span>

<span data-ttu-id="3d909-144">最初のエラー メッセージには、ドキュメントの URL があります。</span><span class="sxs-lookup"><span data-stu-id="3d909-144">The first error message has a URL with documentation.</span></span>
<span data-ttu-id="3d909-145">このリンクでは、[ConfigurationData](https://msdn.microsoft.com/powershell/dsc/configdata) 構造と証明書を使用してパスワードを暗号化する方法を説明しています。</span><span class="sxs-lookup"><span data-stu-id="3d909-145">This link explains how to encrypt passwords using a [ConfigurationData](https://msdn.microsoft.com/powershell/dsc/configdata) structure and a certificate.</span></span>
<span data-ttu-id="3d909-146">証明書と DSC の詳細については、[この投稿をご覧ください](http://aka.ms/certs4dsc)。</span><span class="sxs-lookup"><span data-stu-id="3d909-146">For more information on certificates and DSC [read this post](http://aka.ms/certs4dsc).</span></span>

<span data-ttu-id="3d909-147">プレーンテキスト パスワードを強制的に使用するには、次のようにリソースの構成データ セクションに `PsDscAllowPlainTextPassword` キーワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="3d909-147">To force a plain text password, the resource requires the `PsDscAllowPlainTextPassword` keyword in the configuration data section as follows:</span></span>

```powershell
Configuration DomainCredentialExample
{
    param
    (
        [PSCredential] $DomainCredential
    )
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    node localhost
    {
        Group DomainUserToLocalGroup
        {
            GroupName        = 'ApplicationAdmins'
            MembersToInclude = 'contoso\alice'
            Credential       = $DomainCredential
        }
    }
}

$cd = @{
    AllNodes = @(
        @{
            NodeName = 'localhost'
            PSDscAllowPlainTextPassword = $true
        }
    )
}

$cred = Get-Credential -UserName contoso\genericuser -Message "Password please"
DomainCredentialExample -DomainCredential $cred -ConfigurationData $cd
```

> [!NOTE]
> <span data-ttu-id="3d909-148">`NodeName` にアスタリスクは指定できません。特定のノード名が必須です。</span><span class="sxs-lookup"><span data-stu-id="3d909-148">`NodeName` cannot equal asterisk, a specific node name is mandatory.</span></span>

<span data-ttu-id="3d909-149">**Microsoft では、重大なセキュリティ リスクのため、プレーンテキスト パスワードを使用しないことをお勧めします。**</span><span class="sxs-lookup"><span data-stu-id="3d909-149">**Microsoft advises to avoid plain text passwords due to the significant security risk.**</span></span>

## <a name="domain-credentials"></a><span data-ttu-id="3d909-150">ドメイン資格情報</span><span class="sxs-lookup"><span data-stu-id="3d909-150">Domain Credentials</span></span>

<span data-ttu-id="3d909-151">構成スクリプト例を (暗号化して、またはしないで) もう一度実行しても、資格情報のドメイン アカウントを使用することは推奨されないという警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3d909-151">Running the example configuration script again (with or without encryption), still generates the warning that using a domain account for a credential is not recommended.</span></span>
<span data-ttu-id="3d909-152">ローカル アカウントを使用すると、他のサーバーで使用可能なドメイン資格情報が漏えいする可能性がなくなります。</span><span class="sxs-lookup"><span data-stu-id="3d909-152">Using a local account eliminates potential exposure of domain credentials that could be used on other servers.</span></span>

<span data-ttu-id="3d909-153">**DSC リソースで資格情報を使用する場合、可能な場合は、ドメイン アカウントではなくローカル アカウントを選択します。**</span><span class="sxs-lookup"><span data-stu-id="3d909-153">**When using credentials with DSC resources, prefer a local account over a domain account when possible.**</span></span>

<span data-ttu-id="3d909-154">資格情報の `Username` プロパティに \' または '@' がある場合、DSC ではその資格情報はドメイン アカウントとして処理されます。</span><span class="sxs-lookup"><span data-stu-id="3d909-154">If there is a '\' or '@' in the `Username` property of the credential, then DSC will treat it as a domain account.</span></span>
<span data-ttu-id="3d909-155">ユーザー名のドメイン部分には、"localhost"、"127.0.0.1"、および "::1" の例外があります。</span><span class="sxs-lookup"><span data-stu-id="3d909-155">There is an exception for "localhost", "127.0.0.1", and "::1" in the domain portion of the user name.</span></span>

## <a name="psdscallowdomainuser"></a><span data-ttu-id="3d909-156">PSDscAllowDomainUser</span><span class="sxs-lookup"><span data-stu-id="3d909-156">PSDscAllowDomainUser</span></span>

<span data-ttu-id="3d909-157">上記の DSC `Group` リソースの例では、Active Directory ドメインのクエリを実行するにはドメイン アカウントが*必要です*。</span><span class="sxs-lookup"><span data-stu-id="3d909-157">In the DSC `Group` resource example above, querying an Active Directory domain *requires* a domain account.</span></span>
<span data-ttu-id="3d909-158">この場合は、次のように `ConfigurationData` ブロックに `PSDscAllowDomainUser` プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="3d909-158">In this case add the `PSDscAllowDomainUser` property to the `ConfigurationData` block as follows:</span></span>

```powershell
$cd = @{
    AllNodes = @(
        @{
            NodeName = 'localhost'
            PSDscAllowDomainUser = $true
            # PSDscAllowPlainTextPassword = $true
            CertificateFile = "C:\PublicKeys\server1.cer"
        }
    )
}
```

<span data-ttu-id="3d909-159">これで、構成スクリプトによってエラーや警告なしで MOF ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="3d909-159">Now the configuration script will generate the MOF file with no errors or warnings.</span></span>
