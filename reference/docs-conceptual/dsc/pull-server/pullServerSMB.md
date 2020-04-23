---
ms.date: 04/11/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC SMB プル サーバーのセットアップ
ms.openlocfilehash: be41f7a708f1a129919fae8300fc4307441097f7
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "80500703"
---
# <a name="setting-up-a-dsc-smb-pull-server"></a><span data-ttu-id="3459a-103">DSC SMB プル サーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="3459a-103">Setting up a DSC SMB pull server</span></span>

<span data-ttu-id="3459a-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="3459a-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3459a-105">プル サーバー (Windows Feature *DSC-Service*) は、Windows Server のサポート対象のコンポーネントですが、新機能がオファーされる予定はありません。</span><span class="sxs-lookup"><span data-stu-id="3459a-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="3459a-106">管理対象のクライアントは、(Windows Server のプル サーバー以降の機能が含まれる) [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) または、[こちら](pullserver.md#community-solutions-for-pull-service)に列挙されているコミュニティ ソリューションのいずれかに切り替えを開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3459a-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="3459a-107">DSC [SMB](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831795(v=ws.11)) プル サーバーは、DSC 構成ファイルと DSC リソースを必要なときにターゲット ノードに提供する SMB ファイル共有をホストするコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="3459a-107">A DSC [SMB](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831795(v=ws.11)) pull server is a computer hosting SMB file shares that make DSC configuration files and DSC resources available to target nodes when those nodes ask for them.</span></span>

<span data-ttu-id="3459a-108">DSC の SMB プル サーバーを使うには、次のことが必要です。</span><span class="sxs-lookup"><span data-stu-id="3459a-108">To use an SMB pull server for DSC, you have to:</span></span>

- <span data-ttu-id="3459a-109">PowerShell 4.0 以降を実行しているサーバーに SMB ファイル共有をセットアップする</span><span class="sxs-lookup"><span data-stu-id="3459a-109">Set up an SMB file share on a server running PowerShell 4.0 or higher</span></span>
- <span data-ttu-id="3459a-110">SMB 共有からプルするための、PowerShell 4.0 以降を実行しているクライアントを構成する</span><span class="sxs-lookup"><span data-stu-id="3459a-110">Configure a client running PowerShell 4.0 or higher to pull from that SMB share</span></span>

## <a name="using-the-xsmbshare-resource-to-create-an-smb-file-share"></a><span data-ttu-id="3459a-111">xSmbShare リソースを使用して SMB ファイル共有を作成する</span><span class="sxs-lookup"><span data-stu-id="3459a-111">Using the xSmbShare resource to create an SMB file share</span></span>

<span data-ttu-id="3459a-112">SMB ファイル共有を設定する方法はいくつかありますが、ここでは DSC を使って設定する方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="3459a-112">There are a number of ways to set up an SMB file share, but let's look at how you can do this by using DSC.</span></span>

### <a name="install-the-xsmbshare-resource"></a><span data-ttu-id="3459a-113">xSmbShare リソースをインストールする</span><span class="sxs-lookup"><span data-stu-id="3459a-113">Install the xSmbShare resource</span></span>

<span data-ttu-id="3459a-114">[Install-Module](/powershell/module/PowershellGet/Install-Module) コマンドレットを呼び出して **xSmbShare** モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3459a-114">Call the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet to install the **xSmbShare** module.</span></span>

> [!NOTE]
> <span data-ttu-id="3459a-115">`Install-Module` は、PowerShell 5.0 に含まれている **PowerShellGet** モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="3459a-115">`Install-Module` is included in the **PowerShellGet** module, which is included in PowerShell 5.0.</span></span>
> <span data-ttu-id="3459a-116">**xSmbShare** に含まれる DSC リソース **xSmbShare** を使うと、SMB ファイル共有を作成できます。</span><span class="sxs-lookup"><span data-stu-id="3459a-116">The **xSmbShare** contains the DSC resource **xSmbShare**, which can be used to create an SMB file share.</span></span>

### <a name="create-the-directory-and-file-share"></a><span data-ttu-id="3459a-117">ディレクトリとファイル共有を作成する</span><span class="sxs-lookup"><span data-stu-id="3459a-117">Create the directory and file share</span></span>

<span data-ttu-id="3459a-118">次の構成では、**File** リソースを使って共有するディレクトリを作成し、**xSmbShare** リソースを使って SMB 共有をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="3459a-118">The following configuration uses the **File** resource to create the directory for the share and the **xSmbShare** resource to set up the SMB share:</span></span>

```powershell
Configuration SmbShare
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Import-DscResource -ModuleName xSmbShare

    Node localhost
    {

        File CreateFolder
        {
            DestinationPath = 'C:\DscSmbShare'
            Type = 'Directory'
            Ensure = 'Present'
        }

        xSMBShare CreateShare
        {
            Name = 'DscSmbShare'
            Path = 'C:\DscSmbShare'
            FullAccess = 'administrator'
            ReadAccess = 'myDomain\Contoso-Server$'
            FolderEnumerationMode = 'AccessBased'
            Ensure = 'Present'
            DependsOn = '[File]CreateFolder'
        }
    }
}
```

<span data-ttu-id="3459a-119">ディレクトリ `C:\DscSmbShare` がまだ存在しない場合は、構成によって作成され、そのディレクトリが SMB ファイル共有として使用されます。</span><span class="sxs-lookup"><span data-stu-id="3459a-119">The configuration creates the directory `C:\DscSmbShare`, if it doesn't already exist, and then uses that directory as an SMB file share.</span></span> <span data-ttu-id="3459a-120">**FullAccess** は、ファイル共有に書き込む必要があるか、ファイル共有から削除する必要があるあらゆるアカウントに付与してください。</span><span class="sxs-lookup"><span data-stu-id="3459a-120">**FullAccess** should be given to any account that needs to write to or delete from the file share.</span></span> <span data-ttu-id="3459a-121">**ReadAccess** は、共有から構成または DSC リソースを取得するあらゆるクライアント ノードに付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3459a-121">**ReadAccess** must be given to any client nodes that get configurations and/or DSC resources from the share.</span></span>

> [!NOTE]
> <span data-ttu-id="3459a-122">DSC は既定ではシステム アカウントとして実行されるので、コンピューター自体も共有にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3459a-122">DSC runs as the system account by default, so the computer itself must have access to the share.</span></span>

### <a name="give-file-system-access-to-the-pull-client"></a><span data-ttu-id="3459a-123">ファイル システムにプル クライアントへのアクセス権限を付与する</span><span class="sxs-lookup"><span data-stu-id="3459a-123">Give file system access to the pull client</span></span>

<span data-ttu-id="3459a-124">クライアント ノードに **ReadAccess** を与えると、そのノードは SMB 共有にアクセスできるようになりますが、その共有内のファイルやフォルダーにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="3459a-124">Giving **ReadAccess** to a client node allows that node to access the SMB share, but not to files or folders within that share.</span></span> <span data-ttu-id="3459a-125">クライアント ノードに、SMB 共有のフォルダーやサブフォルダーに対するアクセス権限を明示的に許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3459a-125">You have to explicitly grant client nodes access to the SMB share folder and subfolders.</span></span> <span data-ttu-id="3459a-126">DSC でこれを行うには、**cNtfsAccessControl** モジュールに含まれている [cNtfsPermissionEntry](https://www.powershellgallery.com/packages/cNtfsAccessControl/1.2.0) リソースを使用して追加します。</span><span class="sxs-lookup"><span data-stu-id="3459a-126">We can do this with DSC by adding using the **cNtfsPermissionEntry** resource, which is contained in the [CNtfsAccessControl](https://www.powershellgallery.com/packages/cNtfsAccessControl/1.2.0) module.</span></span>
<span data-ttu-id="3459a-127">次の構成では、プル クライアントに ReadAndExecute アクセスを付与する **cNtfsPermissionEntry** ブロックを追加します。</span><span class="sxs-lookup"><span data-stu-id="3459a-127">The following configuration adds a **cNtfsPermissionEntry** block that grants ReadAndExecute access to the pull client:</span></span>

```powershell
Configuration DSCSMB
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Import-DscResource -ModuleName xSmbShare
    Import-DscResource -ModuleName cNtfsAccessControl

    Node localhost
    {

        File CreateFolder
        {
            DestinationPath = 'C:\DscSmbShare'
            Type = 'Directory'
            Ensure = 'Present'
        }

        xSMBShare CreateShare
        {
            Name = 'DscSmbShare'
            Path = 'C:\DscSmbShare'
            FullAccess = 'administrator'
            ReadAccess = 'myDomain\Contoso-Server$'
            FolderEnumerationMode = 'AccessBased'
            Ensure = 'Present'
            DependsOn = '[File]CreateFolder'
        }

        cNtfsPermissionEntry PermissionSet1
        {
            Ensure = 'Present'
            Path = 'C:\DscSmbShare'
            Principal = 'myDomain\Contoso-Server$'
            AccessControlInformation = @(
                cNtfsAccessControlInformation
                {
                    AccessControlType = 'Allow'
                    FileSystemRights = 'ReadAndExecute'
                    Inheritance = 'ThisFolderSubfoldersAndFiles'
                    NoPropagateInherit = $false
                }
            )
            DependsOn = '[File]CreateFolder'
        }
    }
}
```

## <a name="placing-configurations-and-resources"></a><span data-ttu-id="3459a-128">構成とリソースの配置</span><span class="sxs-lookup"><span data-stu-id="3459a-128">Placing configurations and resources</span></span>

<span data-ttu-id="3459a-129">クライアント ノードがプルする必要のある構成 MOF ファイルや DSC リソースを SMB 共有フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="3459a-129">Save any configuration MOF files and/or DSC resources that you want client nodes to pull in the SMB share folder.</span></span>

<span data-ttu-id="3459a-130">すべての構成 MOF ファイルは、*ConfigurationID*.mof という名前である必要があります。ここで、*ConfigurationID* はターゲット ノードの LCM の **ConfigurationID** プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="3459a-130">Any configuration MOF file must be named *ConfigurationID*.mof, where *ConfigurationID* is the value of the **ConfigurationID** property of the target node's LCM.</span></span> <span data-ttu-id="3459a-131">プル クライアントの設定の詳細については、「[構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3459a-131">For more information about setting up pull clients, see [Setting up a pull client using configuration ID](pullClientConfigID.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3459a-132">SMB プル サーバーを使っている場合は、構成 ID を使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3459a-132">You must use configuration IDs if you are using an SMB pull server.</span></span> <span data-ttu-id="3459a-133">構成名は、SMB ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="3459a-133">Configuration names are not supported for SMB.</span></span>

<span data-ttu-id="3459a-134">各リソース モジュールは、圧縮し、`{Module Name}_{Module Version}.zip` というパターンで名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="3459a-134">Each resource module needs to be zipped and named according to the following pattern `{Module Name}_{Module Version}.zip`.</span></span> <span data-ttu-id="3459a-135">たとえば、モジュール名が xWebAdminstration で、バージョンが 3.1.2.0 のモジュールでは、'xWebAdministration_3.2.1.0.zip' という名前になります。</span><span class="sxs-lookup"><span data-stu-id="3459a-135">For example, a module named xWebAdminstration with a module version of 3.1.2.0 would be named 'xWebAdministration_3.2.1.0.zip'.</span></span> <span data-ttu-id="3459a-136">各バージョンのモジュールを 1 つの zip ファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="3459a-136">Each version of a module must be contained in a single zip file.</span></span> <span data-ttu-id="3459a-137">zip ファイル内のモジュールの個別のバージョンはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3459a-137">Separate versions of a module in a zip file are not supported.</span></span>
<span data-ttu-id="3459a-138">プル サーバーで使うための DSC リソース モジュールをパッケージ化する前に、ディレクトリ構造に少しの変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="3459a-138">Before packaging up DSC resource modules for use with pull server, you need to make a small change to the directory structure.</span></span>

<span data-ttu-id="3459a-139">WMF 5.0 の DSC リソースを含むモジュールの既定の形式は、`{Module Folder}\{Module Version}\DscResources\{DSC Resource Folder}\` です。</span><span class="sxs-lookup"><span data-stu-id="3459a-139">The default format of modules containing DSC resource in WMF 5.0 is `{Module Folder}\{Module Version}\DscResources\{DSC Resource Folder}\`.</span></span>

<span data-ttu-id="3459a-140">プル サーバー用にパッケージ化する前に、パスが `{Module version}` になるように単純に `{Module Folder}\DscResources\{DSC Resource Folder}\` フォルダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="3459a-140">Before packaging up for the pull server simply remove the `{Module version}` folder so the path becomes `{Module Folder}\DscResources\{DSC Resource Folder}\`.</span></span> <span data-ttu-id="3459a-141">この変更を加えた後、上で説明したようにフォルダーを zip 圧縮し、これらの zip ファイルを SMB 共有フォルダーに置きます。</span><span class="sxs-lookup"><span data-stu-id="3459a-141">With this change, zip the folder as described above and place these zip files in the SMB share folder.</span></span>

## <a name="creating-the-mof-checksum"></a><span data-ttu-id="3459a-142">MOF チェックサムの作成</span><span class="sxs-lookup"><span data-stu-id="3459a-142">Creating the MOF checksum</span></span>

<span data-ttu-id="3459a-143">ターゲット ノード上の LCM が構成を検証できるように、構成 MOF ファイルはチェックサム ファイルと組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3459a-143">A configuration MOF file needs to be paired with a checksum file so that an LCM on a target node can validate the configuration.</span></span> <span data-ttu-id="3459a-144">チェックサムを作成するには、[New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3459a-144">To create a checksum, call the [New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) cmdlet.</span></span> <span data-ttu-id="3459a-145">このコマンドレットは、構成 MOF が存在するフォルダーが指定された `Path` パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3459a-145">The cmdlet takes a `Path` parameter that specifies the folder where the configuration MOF is located.</span></span> <span data-ttu-id="3459a-146">このコマンドレットは、`ConfigurationMOFName.mof.checksum` という名前でチェックサム ファイルを作成します。ここで、`ConfigurationMOFName` は構成 MOF ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="3459a-146">The cmdlet creates a checksum file named `ConfigurationMOFName.mof.checksum`, where `ConfigurationMOFName` is the name of the configuration mof file.</span></span> <span data-ttu-id="3459a-147">指定のフォルダーに複数の構成 MOF ファイルがある場合は、そのフォルダー内の構成ごとにチェックサムが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3459a-147">If there are more than one configuration MOF files in the specified folder, a checksum is created for each configuration in the folder.</span></span>

<span data-ttu-id="3459a-148">チェックサム ファイルは、構成 MOF ファイルと同じディレクトリ (既定では `$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration`) に存在し、拡張子として `.checksum` が付けられた同じ名前である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3459a-148">The checksum file must be present in the same directory as the configuration MOF file (`$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration` by default), and have the same name with the `.checksum` extension appended.</span></span>

> [!NOTE]
> <span data-ttu-id="3459a-149">何らかの方法で構成 MOF ファイルを変更した場合は、チェックサム ファイルも作成し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3459a-149">If you change the configuration MOF file in any way, you must also recreate the checksum file.</span></span>

## <a name="setting-up-a-pull-client-for-smb"></a><span data-ttu-id="3459a-150">SMB のプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="3459a-150">Setting up a pull client for SMB</span></span>

<span data-ttu-id="3459a-151">SMB 共有から構成とリソースの両方または一方をプルするクライアントを設定するには、構成と DSC リソースのプル元の共有を指定する **ConfigurationRepositoryShare** ブロックと **ResourceRepositoryShare** ブロックでクライアントのローカル構成マネージャー (LCM) を構成します。</span><span class="sxs-lookup"><span data-stu-id="3459a-151">To set up a client that pulls configurations and/or resources from an SMB share, you configure the client's Local Configuration Manager (LCM) with **ConfigurationRepositoryShare** and **ResourceRepositoryShare** blocks that specify the share from which to pull configurations and DSC resources.</span></span>

<span data-ttu-id="3459a-152">LCM 構成の詳細については、「[構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3459a-152">For more information about configuring the LCM, see [Setting up a pull client using configuration ID](pullClientConfigID.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3459a-153">わかりやすくする目的で、この例では **PSDscAllowPlainTextPassword** を使用し、**Credential** パラメーターにプレーンテキスト パスワードを渡すようにしています。</span><span class="sxs-lookup"><span data-stu-id="3459a-153">For simplicity, this example uses the **PSDscAllowPlainTextPassword** to allow passing a plaintext password to the **Credential** parameter.</span></span> <span data-ttu-id="3459a-154">資格情報をより安全に渡す方法については、「[構成データでの資格情報オプション](../configurations/configDataCredentials.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3459a-154">For information about passing credentials more securely, see [Credentials Options in Configuration Data](../configurations/configDataCredentials.md).</span></span> <span data-ttu-id="3459a-155">リソースをプルするだけであっても、SMB プル サーバーのメタ構成の**設定**ブロックに **ConfigurationID** を指定する**必要があります**。</span><span class="sxs-lookup"><span data-stu-id="3459a-155">You **MUST** specify a **ConfigurationID** in the **Settings** block of a metaconfiguration for an SMB pull server, even if you are only pulling resources.</span></span>

```powershell
$secpasswd = ConvertTo-SecureString "Pass1Word" -AsPlainText -Force
$mycreds = New-Object System.Management.Automation.PSCredential ("TestUser", $secpasswd)

[DSCLocalConfigurationManager()]
configuration SmbCredTest
{
    Node $AllNodes.NodeName
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
            ConfigurationID    = '16db7357-9083-4806-a80c-ebbaf4acd6c1'
        }

         ConfigurationRepositoryShare SmbConfigShare
        {
            SourcePath = '\\WIN-E0TRU6U11B1\DscSmbShare'
            Credential = $mycreds
        }

        ResourceRepositoryShare SmbResourceShare
        {
            SourcePath = '\\WIN-E0TRU6U11B1\DscSmbShare'
            Credential = $mycreds

        }
    }
}

$ConfigurationData = @{
    AllNodes = @(
        @{
            #the "*" means "all nodes named in ConfigData" so we don't have to repeat ourselves
            NodeName="localhost"
            PSDscAllowPlainTextPassword = $true
        })
}
```

## <a name="acknowledgements"></a><span data-ttu-id="3459a-156">謝辞</span><span class="sxs-lookup"><span data-stu-id="3459a-156">Acknowledgements</span></span>

<span data-ttu-id="3459a-157">次の方々に感謝します。</span><span class="sxs-lookup"><span data-stu-id="3459a-157">Special thanks to the following individuals:</span></span>

- <span data-ttu-id="3459a-158">DSC で SMB を使用することに関する Mike F. Robbins 氏の投稿を、このトピックの内容として参考にしました。</span><span class="sxs-lookup"><span data-stu-id="3459a-158">Mike F. Robbins, whose posts on using SMB for DSC helped inform the content in this topic.</span></span> <span data-ttu-id="3459a-159">彼のブログは [Mike F Robbins](http://mikefrobbins.com/) にあります。</span><span class="sxs-lookup"><span data-stu-id="3459a-159">His blog is at [Mike F Robbins](http://mikefrobbins.com/).</span></span>
- <span data-ttu-id="3459a-160">**cNtfsAccessControl** モジュールを作成した Serge Nikalaichyk 氏。</span><span class="sxs-lookup"><span data-stu-id="3459a-160">Serge Nikalaichyk, who authored the **cNtfsAccessControl** module.</span></span> <span data-ttu-id="3459a-161">このモジュールのソースは [cNtfsAccessControl](https://github.com/SNikalaichyk/cNtfsAccessControl) にあります。</span><span class="sxs-lookup"><span data-stu-id="3459a-161">The source for this module is at [cNtfsAccessControl](https://github.com/SNikalaichyk/cNtfsAccessControl).</span></span>

## <a name="see-also"></a><span data-ttu-id="3459a-162">参照</span><span class="sxs-lookup"><span data-stu-id="3459a-162">See also</span></span>

[<span data-ttu-id="3459a-163">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="3459a-163">Windows PowerShell Desired State Configuration Overview</span></span>](../overview/overview.md)

[<span data-ttu-id="3459a-164">構成の適用</span><span class="sxs-lookup"><span data-stu-id="3459a-164">Enacting configurations</span></span>](enactingConfigurations.md)

[<span data-ttu-id="3459a-165">構成 ID を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="3459a-165">Setting up a pull client using configuration ID</span></span>](pullClientConfigID.md)
