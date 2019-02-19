---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成データでの資格情報オプション
ms.openlocfilehash: 2a326e45bbbad7bd2362b66b88bf61b98df7b02e
ms.sourcegitcommit: 6ae5b50a4b3ffcd649de1525c3ce6f15d3669082
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2019
ms.locfileid: "55681231"
---
# <a name="credentials-options-in-configuration-data"></a><span data-ttu-id="78635-103">構成データでの資格情報オプション</span><span class="sxs-lookup"><span data-stu-id="78635-103">Credentials Options in Configuration Data</span></span>

><span data-ttu-id="78635-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="78635-104">Applies To: Windows PowerShell 5.0</span></span>

## <a name="plain-text-passwords-and-domain-users"></a><span data-ttu-id="78635-105">プレーンテキスト パスワードとドメイン ユーザー</span><span class="sxs-lookup"><span data-stu-id="78635-105">Plain Text Passwords and Domain Users</span></span>

<span data-ttu-id="78635-106">暗号化されていない資格情報を含む DSC 構成では、プレーンテキスト パスワードについてのエラー メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="78635-106">DSC configurations containing a credential without encryption will generate an error message about plain text passwords.</span></span>
<span data-ttu-id="78635-107">また、DSC では、ドメイン資格情報を使用すると警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="78635-107">Also, DSC will generate a warning when using domain credentials.</span></span>
<span data-ttu-id="78635-108">これらのエラーや警告メッセージが表示されないようにするには、次の DSC 構成データ キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="78635-108">To suppress these error and warning messages use the DSC configuration data keywords:</span></span>

- <span data-ttu-id="78635-109">**PsDscAllowPlainTextPassword**</span><span class="sxs-lookup"><span data-stu-id="78635-109">**PsDscAllowPlainTextPassword**</span></span>
- <span data-ttu-id="78635-110">**PsDscAllowDomainUser**</span><span class="sxs-lookup"><span data-stu-id="78635-110">**PsDscAllowDomainUser**</span></span>

> [!NOTE]
> <span data-ttu-id="78635-111">暗号化されていないプレーンテキスト パスワードを格納/送信するのは一般的には安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="78635-111">Storing/transmitting plaintext passwords unencrypted is generally not secure.</span></span> <span data-ttu-id="78635-112">このトピックで後述する手法を使って資格情報をセキュリティ保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="78635-112">Securing credentials by using the techniques covered later in this topic is recommended.</span></span>
> <span data-ttu-id="78635-113">Azure Automation DSC サービスでは、構成でコンパイルされ、安全に格納される資格情報を一元的に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="78635-113">The Azure Automation DSC service allows you to centrally manage credentials to be compiled in configurations and stored securely.</span></span>
> <span data-ttu-id="78635-114">詳細について、「[DSC 構成のコンパイル/資格情報資産](/azure/automation/automation-dsc-compile#credential-assets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78635-114">For information, see: [Compiling DSC Configurations / Credential Assets](/azure/automation/automation-dsc-compile#credential-assets)</span></span>

## <a name="handling-credentials-in-dsc"></a><span data-ttu-id="78635-115">DSC での資格情報の処理</span><span class="sxs-lookup"><span data-stu-id="78635-115">Handling Credentials in DSC</span></span>

<span data-ttu-id="78635-116">DSC 構成リソースは、既定で `Local System` として実行されます。</span><span class="sxs-lookup"><span data-stu-id="78635-116">DSC configuration resources run as `Local System` by default.</span></span>
<span data-ttu-id="78635-117">ただし、`Package` リソースでソフトウェアを特定のユーザー アカウントでインストールする必要がある場合など、リソースによっては資格情報が必要となることがあります。</span><span class="sxs-lookup"><span data-stu-id="78635-117">However, some resources need a credential, for example when the `Package` resource needs to install software under a specific user account.</span></span>

<span data-ttu-id="78635-118">以前のリソースでは、ハード コードされた `Credential` プロパティ名使用してこのことに対処していました。</span><span class="sxs-lookup"><span data-stu-id="78635-118">Earlier resources used a hard-coded `Credential` property name to handle this.</span></span>
<span data-ttu-id="78635-119">WMF 5.0 では、すべてのリソースに対して自動 `PsDscRunAsCredential` プロパティが追加されました。</span><span class="sxs-lookup"><span data-stu-id="78635-119">WMF 5.0 added an automatic `PsDscRunAsCredential` property for all resources.</span></span>
<span data-ttu-id="78635-120">`PsDscRunAsCredential` の使用の詳細については、「[ユーザーの資格情報を指定して DSC を実行する](runAsUser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78635-120">For information about using `PsDscRunAsCredential`, see [Running DSC with user credentials](runAsUser.md).</span></span>
<span data-ttu-id="78635-121">新しいリソースおよびカスタム リソースでは、資格情報の独自のプロパティを作成する代わりに、この自動プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="78635-121">Newer resources and custom resources can use this automatic property instead of creating their own property for credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="78635-122">一部のリソースは特定の理由のために複数の資格情報を使用するように設計されており、それらのリソースには独自の資格情報プロパティがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="78635-122">The design of some resources are to use multiple credentials for a specific reason, and they will have their own credential properties.</span></span>

<span data-ttu-id="78635-123">リソースの使用可能な資格情報プロパティを検索するには、ISE で `Get-DscResource -Name ResourceName -Syntax` または Intellisense を使用します (`CTRL+SPACE`)。</span><span class="sxs-lookup"><span data-stu-id="78635-123">To find the available credential properties on a resource use either `Get-DscResource -Name ResourceName -Syntax` or the Intellisense in the ISE (`CTRL+SPACE`).</span></span>

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

<span data-ttu-id="78635-124">この例では、`PSDesiredStateConfiguration` 組み込み DSC リソース モジュールの [Group](../resources/resources.md) リソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="78635-124">This example uses a [Group](../resources/resources.md) resource from the `PSDesiredStateConfiguration` built-in DSC resource module.</span></span>
<span data-ttu-id="78635-125">ローカル グループを作成し、メンバーを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="78635-125">It can create local groups and add or remove members.</span></span>
<span data-ttu-id="78635-126">`Credential` プロパティと、自動 `PsDscRunAsCredential` プロパティの両方を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="78635-126">It accepts both the `Credential` property and the automatic `PsDscRunAsCredential` property.</span></span>
<span data-ttu-id="78635-127">ただし、リソースでは `Credential` プロパティのみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="78635-127">However, the resource only uses the `Credential` property.</span></span>

<span data-ttu-id="78635-128">`PsDscRunAsCredential`プロパティの詳細については、「[ユーザーの資格情報を指定して DSC を実行する](runAsUser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78635-128">For more information about the `PsDscRunAsCredential` property, see [Running DSC with user credentials](runAsUser.md).</span></span>

## <a name="example-the-group-resource-credential-property"></a><span data-ttu-id="78635-129">例: Group リソース資格情報プロパティ</span><span class="sxs-lookup"><span data-stu-id="78635-129">Example: The Group resource Credential property</span></span>

<span data-ttu-id="78635-130">DSC は `Local System` で実行されるため、ローカル ユーザーおよびグループを変更するためのアクセス許可が既にあります。</span><span class="sxs-lookup"><span data-stu-id="78635-130">DSC runs under `Local System`, so it already has permissions to change local users and groups.</span></span>
<span data-ttu-id="78635-131">追加されたメンバーがローカル アカウントの場合、資格情報は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="78635-131">If the member added is a local account, then no credential is necessary.</span></span>
<span data-ttu-id="78635-132">`Group` リソースがローカル グループにドメイン アカウントを追加する場合、資格情報が必要となります。</span><span class="sxs-lookup"><span data-stu-id="78635-132">If the `Group` resource adds a domain account to the local group, then a credential is necessary.</span></span>

<span data-ttu-id="78635-133">Active Directory への匿名クエリは許可されません。</span><span class="sxs-lookup"><span data-stu-id="78635-133">Anonymous queries to Active Directory are not allowed.</span></span>
<span data-ttu-id="78635-134">`Group` リソースの `Credential` プロパティは、Active Directory のクエリに使用されるドメイン アカウントです。</span><span class="sxs-lookup"><span data-stu-id="78635-134">The `Credential` property of the `Group` resource is the domain account used to query Active Directory.</span></span>
<span data-ttu-id="78635-135">既定では、ユーザーは Active Directory 内の大部分のオブジェクトを*読み取る*ことができるため、ほとんどの場合これは汎用ユーザー アカウントです。</span><span class="sxs-lookup"><span data-stu-id="78635-135">For most purposes this could be a generic user account, because by default users can *read* most of the objects in Active Directory.</span></span>

## <a name="example-configuration"></a><span data-ttu-id="78635-136">構成の例</span><span class="sxs-lookup"><span data-stu-id="78635-136">Example Configuration</span></span>

<span data-ttu-id="78635-137">次のコード例では、DSC を使用してローカル グループにドメイン ユーザーを設定します。</span><span class="sxs-lookup"><span data-stu-id="78635-137">The following example code uses DSC to populate a local group with a domain user:</span></span>

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

<span data-ttu-id="78635-138">このコードでは、エラーと警告メッセージの両方が生成されます。</span><span class="sxs-lookup"><span data-stu-id="78635-138">This code generates both an error and warning message:</span></span>

```
ConvertTo-MOFInstance : System.InvalidOperationException error processing property 'Credential' OF
TYPE 'Group': Converting and storing encrypted passwords as plain text is not recommended.
For more information on securing credentials in MOF file, please refer to MSDN blog:
https://go.microsoft.com/fwlink/?LinkId=393729

At line:11 char:9
+   Group
At line:341 char:16
+     $aliasId = ConvertTo-MOFInstance $keywordName $canonicalizedValue
+                ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Write-Error], InvalidOperationException
    + FullyQualifiedErrorId : FailToProcessProperty,ConvertTo-MOFInstance
WARNING: It is not recommended to use domain credential for node 'localhost'. In order to suppress
the warning, you can add a property named 'PSDscAllowDomainUser' with a value of $true to your DSC
configuration data for node 'localhost'.

Compilation errors occurred while processing configuration
'DomainCredentialExample'. Please review the errors reported in error stream and modify your
configuration code appropriately.
At C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\PSDesiredStateConfiguration\PSDesiredStateConfiguration.psm1:3917 char:5
+     throw $ErrorRecord
+     ~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (DomainCredentialExample:String) [], InvalidOperationException
    + FullyQualifiedErrorId : FailToProcessConfiguration
```

<span data-ttu-id="78635-139">この例には、次の 2 つの問題があります。</span><span class="sxs-lookup"><span data-stu-id="78635-139">This example has two issues:</span></span>

1. <span data-ttu-id="78635-140">プレーンテキスト パスワードが推奨されないことを説明するエラー。</span><span class="sxs-lookup"><span data-stu-id="78635-140">An error explains that plain text passwords are not recommended</span></span>
2. <span data-ttu-id="78635-141">ドメイン資格情報を使用しないよう勧める警告。</span><span class="sxs-lookup"><span data-stu-id="78635-141">A warning advises against using a domain credential</span></span>

<span data-ttu-id="78635-142">フラグ**PSDSCAllowPlainTextPassword**と**PSDSCAllowDomainUser**エラーと関連するリスクのユーザーに通知する警告を抑制します。</span><span class="sxs-lookup"><span data-stu-id="78635-142">The flags **PSDSCAllowPlainTextPassword** and **PSDSCAllowDomainUser** suppress the error and warning informing the user of the risk involved.</span></span>

## <a name="psdscallowplaintextpassword"></a><span data-ttu-id="78635-143">PSDSCAllowPlainTextPassword</span><span class="sxs-lookup"><span data-stu-id="78635-143">PSDSCAllowPlainTextPassword</span></span>

<span data-ttu-id="78635-144">最初のエラー メッセージには、ドキュメントの URL があります。</span><span class="sxs-lookup"><span data-stu-id="78635-144">The first error message has a URL with documentation.</span></span>
<span data-ttu-id="78635-145">このリンクでは、[ConfigurationData](./configData.md) 構造と証明書を使用してパスワードを暗号化する方法を説明しています。</span><span class="sxs-lookup"><span data-stu-id="78635-145">This link explains how to encrypt passwords using a [ConfigurationData](./configData.md) structure and a certificate.</span></span>
<span data-ttu-id="78635-146">証明書と DSC の詳細については、[この投稿をご覧ください](http://aka.ms/certs4dsc)。</span><span class="sxs-lookup"><span data-stu-id="78635-146">For more information on certificates and DSC [read this post](http://aka.ms/certs4dsc).</span></span>

<span data-ttu-id="78635-147">プレーンテキスト パスワードを強制的に使用するには、次のようにリソースの構成データ セクションに `PsDscAllowPlainTextPassword` キーワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="78635-147">To force a plain text password, the resource requires the `PsDscAllowPlainTextPassword` keyword in the configuration data section as follows:</span></span>

```powershell
$password = "ThisIsAPlaintextPassword" | ConvertTo-SecureString -asPlainText -Force
$username = "contoso\Administrator"
[PSCredential] $credential = New-Object System.Management.Automation.PSCredential($username,$password)

Configuration DomainCredentialExample
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    node localhost
    {
        Group DomainUserToLocalGroup
        {
            GroupName        = 'ApplicationAdmins'
            MembersToInclude = 'contoso\alice'
            Credential       = $credential
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

DomainCredentialExample -ConfigurationData $cd
```

### <a name="localhostmof"></a><span data-ttu-id="78635-148">localhost.mof</span><span class="sxs-lookup"><span data-stu-id="78635-148">localhost.mof</span></span>

<span data-ttu-id="78635-149">**PSDSCAllowPlainTextPassword**フラグは、ユーザーが MOF ファイルにプレーン テキスト パスワードを格納するリスクを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78635-149">The **PSDSCAllowPlainTextPassword** flag requires that the user acknowledge the risk of storing plain text passwords in a MOF file.</span></span> <span data-ttu-id="78635-150">生成された MOF ファイルの場合でも、 **PSCredential**オブジェクトを含む、 **SecureString**が使用すると、パスワードがプレーン テキストとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="78635-150">In the generated MOF file, even though a **PSCredential** object containing a **SecureString** was used, the passwords still appear as plain text.</span></span> <span data-ttu-id="78635-151">これは、資格情報が公開されているときだけです。</span><span class="sxs-lookup"><span data-stu-id="78635-151">This is the only time the credentials are exposed.</span></span> <span data-ttu-id="78635-152">この MOF ファイルは、すべてのユーザーの管理者アカウントにアクセスするには、アクセス キーを押します。</span><span class="sxs-lookup"><span data-stu-id="78635-152">Gaining access to this MOF file gives anyone access to the Administrator account.</span></span>

```
/*
@TargetNode='localhost'
@GeneratedBy=Administrator
@GenerationDate=01/31/2019 06:43:13
@GenerationHost=Server01
*/

instance of MSFT_Credential as $MSFT_Credential1ref
{
Password = "ThisIsAPlaintextPassword";
 UserName = "Administrator";

};

instance of MSFT_GroupResource as $MSFT_GroupResource1ref
{
ResourceID = "[Group]DomainUserToLocalGroup";
 MembersToInclude = {
    "contoso\\alice"
};
 Credential = $MSFT_Credential1ref;
 SourceInfo = "::11::9::Group";
 GroupName = "ApplicationAdmins";
 ModuleName = "PSDesiredStateConfiguration";

ModuleVersion = "1.0";

 ConfigurationName = "DomainCredentialExample";

};
```

### <a name="credentials-in-transit-and-at-rest"></a><span data-ttu-id="78635-153">送信および保存時の資格情報</span><span class="sxs-lookup"><span data-stu-id="78635-153">Credentials in transit and at rest</span></span>

- <span data-ttu-id="78635-154">**PSDscAllowPlainTextPassword**フラグがクリア テキストでパスワードを含む MOF ファイルのコンパイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="78635-154">The **PSDscAllowPlainTextPassword** flag allows the compilation of MOF files that contain passwords in clear text.</span></span>
  <span data-ttu-id="78635-155">クリア テキスト パスワードを含む MOF ファイルを格納する場合は注意してください。</span><span class="sxs-lookup"><span data-stu-id="78635-155">Take precautions when storing MOF files containing clear text passwords.</span></span>
- <span data-ttu-id="78635-156">内のノードに、MOF ファイルを配信するタイミング**プッシュ**モードでは、WinRM がで既定値を上書きしない限り、クリア テキスト パスワードを保護する通信を暗号化する、 **AllowUnencrypted**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="78635-156">When the MOF file is delivered to a Node in **Push** mode, WinRM encrypts the communication to protect the clear text password unless you override the default with the **AllowUnencrypted** parameter.</span></span>
  - <span data-ttu-id="78635-157">証明書で MOF の暗号化では、ノードに適用する前に残りの部分で MOF ファイルを保護します。</span><span class="sxs-lookup"><span data-stu-id="78635-157">Encrypting the MOF with a certificate protects the MOF file at rest before it has been applied to a node.</span></span>
- <span data-ttu-id="78635-158">**プル**モードでは、インターネット インフォメーション サーバーで指定されたプロトコルを使用してトラフィックを暗号化する HTTPS を使用する Windows のプル サーバーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="78635-158">In **Pull** mode, you can configure Windows pull server to use HTTPS to encrypt traffic using the protocol specified in Internet Information Server.</span></span> <span data-ttu-id="78635-159">詳細については、記事をご覧ください。 [DSC プル クライアントのセットアップ](../pull-server/pullclient.md)と[セキュリティで保護する MOF ファイルに証明書](../pull-server/secureMOF.md)します。</span><span class="sxs-lookup"><span data-stu-id="78635-159">For more information, see the articles [Setting up a DSC pull client](../pull-server/pullclient.md) and [Securing MOF files with Certificates](../pull-server/secureMOF.md).</span></span>
  - <span data-ttu-id="78635-160">[Azure Automation State Configuration](https://docs.microsoft.com/en-us/azure/automation/automation-dsc-overview)サービス、トラフィックの暗号化は常にプルします。</span><span class="sxs-lookup"><span data-stu-id="78635-160">In the [Azure Automation State Configuration](https://docs.microsoft.com/en-us/azure/automation/automation-dsc-overview) service, Pull traffic is always encrypted.</span></span>
- <span data-ttu-id="78635-161">MOF ファイルが保存時暗号化ノードで、PowerShell 5.0 以降します。</span><span class="sxs-lookup"><span data-stu-id="78635-161">On the Node, MOF files are encrypted at rest Beginning in PowerShell 5.0.</span></span>
  - <span data-ttu-id="78635-162">PowerShell 4.0 の MOF のプッシュまたはプル ノードにある証明書で暗号化されていないファイルは保存時暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="78635-162">In PowerShell 4.0 MOF files are unencrypted at rest unless they are encrypted with a certificate when they pushed or pulled to the Node.</span></span>

<span data-ttu-id="78635-163">**Microsoft では、重大なセキュリティ リスクのため、プレーンテキスト パスワードを使用しないことをお勧めします。**</span><span class="sxs-lookup"><span data-stu-id="78635-163">**Microsoft advises to avoid plain text passwords due to the significant security risk.**</span></span>

## <a name="domain-credentials"></a><span data-ttu-id="78635-164">ドメイン資格情報</span><span class="sxs-lookup"><span data-stu-id="78635-164">Domain Credentials</span></span>

<span data-ttu-id="78635-165">構成スクリプト例を (暗号化して、またはしないで) もう一度実行しても、資格情報のドメイン アカウントを使用することは推奨されないという警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="78635-165">Running the example configuration script again (with or without encryption), still generates the warning that using a domain account for a credential is not recommended.</span></span>
<span data-ttu-id="78635-166">ローカル アカウントを使用すると、他のサーバーで使用可能なドメイン資格情報が漏えいする可能性がなくなります。</span><span class="sxs-lookup"><span data-stu-id="78635-166">Using a local account eliminates potential exposure of domain credentials that could be used on other servers.</span></span>

<span data-ttu-id="78635-167">**DSC リソースで資格情報を使用する場合、可能な場合は、ドメイン アカウントではなくローカル アカウントを選択します。**</span><span class="sxs-lookup"><span data-stu-id="78635-167">**When using credentials with DSC resources, prefer a local account over a domain account when possible.**</span></span>

<span data-ttu-id="78635-168">資格情報の `Username` プロパティに '\\' または '\@' が含まれていた場合、DSC はそれをドメイン アカウントとして処理します。</span><span class="sxs-lookup"><span data-stu-id="78635-168">If there is a '\\' or '\@' in the `Username` property of the credential, then DSC will treat it as a domain account.</span></span>
<span data-ttu-id="78635-169">ユーザー名のドメイン部分には、"localhost"、"127.0.0.1"、および "::1" の例外があります。</span><span class="sxs-lookup"><span data-stu-id="78635-169">There is an exception for "localhost", "127.0.0.1", and "::1" in the domain portion of the user name.</span></span>

## <a name="psdscallowdomainuser"></a><span data-ttu-id="78635-170">PSDscAllowDomainUser</span><span class="sxs-lookup"><span data-stu-id="78635-170">PSDscAllowDomainUser</span></span>

<span data-ttu-id="78635-171">上記の DSC `Group` リソースの例では、Active Directory ドメインのクエリを実行するにはドメイン アカウントが*必要です*。</span><span class="sxs-lookup"><span data-stu-id="78635-171">In the DSC `Group` resource example above, querying an Active Directory domain *requires* a domain account.</span></span>
<span data-ttu-id="78635-172">この場合は、次のように `ConfigurationData` ブロックに `PSDscAllowDomainUser` プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="78635-172">In this case add the `PSDscAllowDomainUser` property to the `ConfigurationData` block as follows:</span></span>

```powershell
$password = "ThisIsAPlaintextPassword" | ConvertTo-SecureString -asPlainText -Force
$username = "contoso\Administrator"
[PSCredential] $credential = New-Object System.Management.Automation.PSCredential($username,$password)

Configuration DomainCredentialExample
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    node localhost
    {
        Group DomainUserToLocalGroup
        {
            GroupName        = 'ApplicationAdmins'
            MembersToInclude = 'contoso\alice'
            Credential       = $credential
        }
    }
}

$cd = @{
    AllNodes = @(
        @{
            NodeName = 'localhost'
            PSDscAllowDomainUser = $true
            PSDscAllowPlainTextPassword = $true
        }
    )
}

DomainCredentialExample -ConfigurationData $cd
```

<span data-ttu-id="78635-173">これで、構成スクリプトによってエラーや警告なしで MOF ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="78635-173">Now the configuration script will generate the MOF file with no errors or warnings.</span></span>
