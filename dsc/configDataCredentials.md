---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "構成データでの資格情報オプション"
ms.openlocfilehash: 94ff541fc517254ef2876c424307513eaf1d362a
ms.sourcegitcommit: 28e71b0ae868014523631fec3f5417de751944f3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2017
---
# <a name="credentials-options-in-configuration-data"></a><span data-ttu-id="6ba37-103">構成データでの資格情報オプション</span><span class="sxs-lookup"><span data-stu-id="6ba37-103">Credentials Options in Configuration Data</span></span>
><span data-ttu-id="6ba37-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="6ba37-104">Applies To: Windows PowerShell 5.0</span></span>

## <a name="plain-text-passwords-and-domain-users"></a><span data-ttu-id="6ba37-105">プレーンテキスト パスワードとドメイン ユーザー</span><span class="sxs-lookup"><span data-stu-id="6ba37-105">Plain Text Passwords and Domain Users</span></span>

<span data-ttu-id="6ba37-106">暗号化されていない資格情報を含む DSC 構成では、プレーンテキスト パスワードについてのエラー メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6ba37-106">DSC configurations containing a credential without encryption will generate an error message about plain text passwords.</span></span>
<span data-ttu-id="6ba37-107">また、DSC では、ドメイン資格情報を使用すると警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="6ba37-107">Also, DSC will generate a warning when using domain credentials.</span></span>
<span data-ttu-id="6ba37-108">これらのエラーや警告メッセージが表示されないようにするには、次の DSC 構成データ キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ba37-108">To suppress these error and warning messages use the DSC configuration data keywords:</span></span>
* <span data-ttu-id="6ba37-109">**PsDscAllowPlainTextPassword**</span><span class="sxs-lookup"><span data-stu-id="6ba37-109">**PsDscAllowPlainTextPassword**</span></span>
* <span data-ttu-id="6ba37-110">**PsDscAllowDomainUser**</span><span class="sxs-lookup"><span data-stu-id="6ba37-110">**PsDscAllowDomainUser**</span></span>

><span data-ttu-id="6ba37-111">**注**:</span><span class="sxs-lookup"><span data-stu-id="6ba37-111">**Notes:**</span></span> <p><span data-ttu-id="6ba37-112">暗号化されていないプレーンテキスト パスワードを格納/送信するのは一般的には安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="6ba37-112">Storing/transmitting plaintext passwords unencrypted is generally not secure.</span></span> <span data-ttu-id="6ba37-113">このトピックで後述する手法を使って資格情報をセキュリティ保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6ba37-113">Securing credentials by using the techniques covered later in this topic is recommended.</span></span></p> <p><span data-ttu-id="6ba37-114">Azure Automation DSC サービスでは、構成でコンパイルされ、安全に格納される資格情報を一元的に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="6ba37-114">The Azure Automation DSC service allows you to centrally manage credentials to be compiled in configurations and stored securely.</span></span>  <span data-ttu-id="6ba37-115">詳細について、「[DSC 構成のコンパイル/資格情報資産](https://docs.microsoft.com/en-in/azure/automation/automation-dsc-compile#credential-assets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba37-115">For information, see: [Compiling DSC Configurations / Credential Assets](https://docs.microsoft.com/en-in/azure/automation/automation-dsc-compile#credential-assets)</span></span></p>

<span data-ttu-id="6ba37-116">プレーンテキストの資格情報を渡す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6ba37-116">The following is an example of passing plain text credentials:</span></span>

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

## <a name="handling-credentials-in-dsc"></a><span data-ttu-id="6ba37-117">DSC での資格情報の処理</span><span class="sxs-lookup"><span data-stu-id="6ba37-117">Handling Credentials in DSC</span></span>

<span data-ttu-id="6ba37-118">DSC 構成リソースは、既定で `Local System` として実行されます。</span><span class="sxs-lookup"><span data-stu-id="6ba37-118">DSC configuration resources run as `Local System` by default.</span></span>
<span data-ttu-id="6ba37-119">ただし、`Package` リソースでソフトウェアを特定のユーザー アカウントでインストールする必要がある場合など、リソースによっては資格情報が必要となることがあります。</span><span class="sxs-lookup"><span data-stu-id="6ba37-119">However, some resources need a credential, for example when the `Package` resource needs to install software under a specific user account.</span></span>

<span data-ttu-id="6ba37-120">以前のリソースでは、ハード コードされた `Credential` プロパティ名使用してこのことに対処していました。</span><span class="sxs-lookup"><span data-stu-id="6ba37-120">Earlier resources used a hard-coded `Credential` property name to handle this.</span></span>
<span data-ttu-id="6ba37-121">WMF 5.0 では、すべてのリソースに対して自動 `PsDscRunAsCredential` プロパティが追加されました。</span><span class="sxs-lookup"><span data-stu-id="6ba37-121">WMF 5.0 added an automatic `PsDscRunAsCredential` property for all resources.</span></span>
<span data-ttu-id="6ba37-122">`PsDscRunAsCredential` の使用の詳細については、「[ユーザーの資格情報を指定して DSC を実行する](runAsUser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba37-122">For information about using `PsDscRunAsCredential`, see [Running DSC with user credentials](runAsUser.md).</span></span>
<span data-ttu-id="6ba37-123">新しいリソースおよびカスタム リソースでは、資格情報の独自のプロパティを作成する代わりに、この自動プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ba37-123">Newer resources and custom resources can use this automatic property instead of creating their own property for credentials.</span></span>

><span data-ttu-id="6ba37-124">**注**: 一部のリソースは特定の理由のために複数の資格情報を使用するように設計されており、それらのリソースには独自の資格情報プロパティがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6ba37-124">**Note:** the design of some resources are to use multiple credentials for a specific reason, and they will have their own credential properties.</span></span>

<span data-ttu-id="6ba37-125">リソースの使用可能な資格情報プロパティを検索するには、ISE で `Get-DscResource -Name ResourceName -Syntax` または Intellisense を使用します (`CTRL+SPACE`)。</span><span class="sxs-lookup"><span data-stu-id="6ba37-125">To find the available credential properties on a resource use either `Get-DscResource -Name ResourceName -Syntax` or the Intellisense in the ISE (`CTRL+SPACE`).</span></span>

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

<span data-ttu-id="6ba37-126">この例では、`PSDesiredStateConfiguration` 組み込み DSC リソース モジュールの [Group](https://msdn.microsoft.com/en-us/powershell/dsc/groupresource) リソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ba37-126">This example uses a [Group](https://msdn.microsoft.com/en-us/powershell/dsc/groupresource) resource from the `PSDesiredStateConfiguration` built-in DSC resource module.</span></span>
<span data-ttu-id="6ba37-127">ローカル グループを作成し、メンバーを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="6ba37-127">It can create local groups and add or remove members.</span></span>
<span data-ttu-id="6ba37-128">`Credential` プロパティと、自動 `PsDscRunAsCredential` プロパティの両方を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6ba37-128">It accepts both the `Credential` property and the automatic `PsDscRunAsCredential` property.</span></span>
<span data-ttu-id="6ba37-129">ただし、リソースでは `Credential` プロパティのみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ba37-129">However, the resource only uses the `Credential` property.</span></span>

<span data-ttu-id="6ba37-130">`PsDscRunAsCredential`プロパティの詳細については、「[ユーザーの資格情報を指定して DSC を実行する](runAsUser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba37-130">For more information about the `PsDscRunAsCredential` property, see [Running DSC with user credentials](runAsUser.md).</span></span>

## <a name="example-the-group-resource-credential-property"></a><span data-ttu-id="6ba37-131">例: Group リソース資格情報プロパティ</span><span class="sxs-lookup"><span data-stu-id="6ba37-131">Example: The Group resource Credential property</span></span>

<span data-ttu-id="6ba37-132">DSC は `Local System` で実行されるため、ローカル ユーザーおよびグループを変更するためのアクセス許可が既にあります。</span><span class="sxs-lookup"><span data-stu-id="6ba37-132">DSC runs under `Local System`, so it already has permissions to change local users and groups.</span></span>
<span data-ttu-id="6ba37-133">追加されたメンバーがローカル アカウントの場合、資格情報は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6ba37-133">If the member added is a local account, then no credential is necessary.</span></span>
<span data-ttu-id="6ba37-134">`Group` リソースがローカル グループにドメイン アカウントを追加する場合、資格情報が必要となります。</span><span class="sxs-lookup"><span data-stu-id="6ba37-134">If the `Group` resource adds a domain account to the local group, then a credential is necessary.</span></span>

<span data-ttu-id="6ba37-135">Active Directory への匿名クエリは許可されません。</span><span class="sxs-lookup"><span data-stu-id="6ba37-135">Anonymous queries to Active Directory are not allowed.</span></span>
<span data-ttu-id="6ba37-136">`Group` リソースの `Credential` プロパティは、Active Directory のクエリに使用されるドメイン アカウントです。</span><span class="sxs-lookup"><span data-stu-id="6ba37-136">The `Credential` property of the `Group` resource is the domain account used to query Active Directory.</span></span>
<span data-ttu-id="6ba37-137">既定では、ユーザーは Active Directory 内の大部分のオブジェクトを*読み取る*ことができるため、ほとんどの場合これは汎用ユーザー アカウントです。</span><span class="sxs-lookup"><span data-stu-id="6ba37-137">For most purposes this could be a generic user account, because by default users can *read* most of the objects in Active Directory.</span></span>

## <a name="example-configuration"></a><span data-ttu-id="6ba37-138">構成の例</span><span class="sxs-lookup"><span data-stu-id="6ba37-138">Example Configuration</span></span>

<span data-ttu-id="6ba37-139">次のコード例では、DSC を使用してローカル グループにドメイン ユーザーを設定します。</span><span class="sxs-lookup"><span data-stu-id="6ba37-139">The following example code uses DSC to populate a local group with a domain user:</span></span>

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

<span data-ttu-id="6ba37-140">このコードでは、エラーと警告メッセージの両方が生成されます。</span><span class="sxs-lookup"><span data-stu-id="6ba37-140">This code generates both an error and warning message:</span></span>

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

<span data-ttu-id="6ba37-141">この例には、次の 2 つの問題があります。</span><span class="sxs-lookup"><span data-stu-id="6ba37-141">This example has two issues:</span></span>
1.  <span data-ttu-id="6ba37-142">プレーンテキスト パスワードが推奨されないことを説明するエラー。</span><span class="sxs-lookup"><span data-stu-id="6ba37-142">An error explains that plain text passwords are not recommended</span></span>
2.  <span data-ttu-id="6ba37-143">ドメイン資格情報を使用しないよう勧める警告。</span><span class="sxs-lookup"><span data-stu-id="6ba37-143">A warning advises against using a domain credential</span></span>

## <a name="psdscallowplaintextpassword"></a><span data-ttu-id="6ba37-144">PsDscAllowPlainTextPassword</span><span class="sxs-lookup"><span data-stu-id="6ba37-144">PsDscAllowPlainTextPassword</span></span>

<span data-ttu-id="6ba37-145">最初のエラー メッセージには、ドキュメントの URL があります。</span><span class="sxs-lookup"><span data-stu-id="6ba37-145">The first error message has a URL with documentation.</span></span>
<span data-ttu-id="6ba37-146">このリンクでは、[ConfigurationData](https://msdn.microsoft.com/en-us/powershell/dsc/configdata) 構造と証明書を使用してパスワードを暗号化する方法を説明しています。</span><span class="sxs-lookup"><span data-stu-id="6ba37-146">This link explains how to encrypt passwords using a [ConfigurationData](https://msdn.microsoft.com/en-us/powershell/dsc/configdata) structure and a certificate.</span></span>
<span data-ttu-id="6ba37-147">証明書と DSC の詳細については、[この投稿をご覧ください](http://aka.ms/certs4dsc)。</span><span class="sxs-lookup"><span data-stu-id="6ba37-147">For more information on certificates and DSC [read this post](http://aka.ms/certs4dsc).</span></span>

<span data-ttu-id="6ba37-148">プレーンテキスト パスワードを強制的に使用するには、次のようにリソースの構成データ セクションに `PsDscAllowPlainTextPassword` キーワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="6ba37-148">To force a plain text password, the resource requires the `PsDscAllowPlainTextPassword` keyword in the configuration data section as follows:</span></span>

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

><span data-ttu-id="6ba37-149">**注**: `NodeName`にアスタリスクは指定できません。特定のノード名が必須です。</span><span class="sxs-lookup"><span data-stu-id="6ba37-149">**Note:** `NodeName` cannot equal asterisk, a specific node name is mandatory.</span></span>

<span data-ttu-id="6ba37-150">**Microsoft では、重大なセキュリティ リスクのため、プレーンテキスト パスワードを使用しないことをお勧めします。**</span><span class="sxs-lookup"><span data-stu-id="6ba37-150">**Microsoft advises to avoid plain text passwords due to the significant security risk.**</span></span>
<span data-ttu-id="6ba37-151">例外は Azure Automation DSC サービスを使用するときで、データが常に暗号化されて格納されるためです (送信中、サービスの一時停止中、ノードの一時停止中)。</span><span class="sxs-lookup"><span data-stu-id="6ba37-151">An exception would be when using the Azure Automation DSC service, only because the data is always stored encrypted (in transit, at rest in the service, and at rest on the node).</span></span>

## <a name="domain-credentials"></a><span data-ttu-id="6ba37-152">ドメイン資格情報</span><span class="sxs-lookup"><span data-stu-id="6ba37-152">Domain Credentials</span></span>

<span data-ttu-id="6ba37-153">構成スクリプト例を (暗号化して、またはしないで) もう一度実行しても、資格情報のドメイン アカウントを使用することは推奨されないという警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="6ba37-153">Running the example configuration script again (with or without encryption), still generates the warning that using a domain account for a credential is not recommended.</span></span>
<span data-ttu-id="6ba37-154">ローカル アカウントを使用すると、他のサーバーで使用可能なドメイン資格情報が漏えいする可能性がなくなります。</span><span class="sxs-lookup"><span data-stu-id="6ba37-154">Using a local account eliminates potential exposure of domain credentials that could be used on other servers.</span></span>

<span data-ttu-id="6ba37-155">**DSC リソースで資格情報を使用する場合、可能な場合は、ドメイン アカウントではなくローカル アカウントを選択します。**</span><span class="sxs-lookup"><span data-stu-id="6ba37-155">**When using credentials with DSC resources, prefer a local account over a domain account when possible.**</span></span>

<span data-ttu-id="6ba37-156">資格情報の `Username` プロパティに \' または '@' がある場合、DSC ではその資格情報はドメイン アカウントとして処理されます。</span><span class="sxs-lookup"><span data-stu-id="6ba37-156">If there is a '\' or '@' in the `Username` property of the credential, then DSC will treat it as a domain account.</span></span>
<span data-ttu-id="6ba37-157">ユーザー名のドメイン部分には、"localhost"、"127.0.0.1"、および "::1" の例外があります。</span><span class="sxs-lookup"><span data-stu-id="6ba37-157">There is an exception for "localhost", "127.0.0.1", and "::1" in the domain portion of the user name.</span></span>

## <a name="psdscallowdomainuser"></a><span data-ttu-id="6ba37-158">PSDscAllowDomainUser</span><span class="sxs-lookup"><span data-stu-id="6ba37-158">PSDscAllowDomainUser</span></span>

<span data-ttu-id="6ba37-159">上記の DSC `Group` リソースの例では、Active Directory ドメインのクエリを実行するにはドメイン アカウントが*必要です*。</span><span class="sxs-lookup"><span data-stu-id="6ba37-159">In the DSC `Group` resource example above, querying an Active Directory domain *requires* a domain account.</span></span>
<span data-ttu-id="6ba37-160">この場合は、次のように `ConfigurationData` ブロックに `PSDscAllowDomainUser` プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="6ba37-160">In this case add the `PSDscAllowDomainUser` property to the `ConfigurationData` block as follows:</span></span>

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

<span data-ttu-id="6ba37-161">これで、構成スクリプトによってエラーや警告なしで MOF ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6ba37-161">Now the configuration script will generate the MOF file with no errors or warnings.</span></span>
