---
ms.date: 04/11/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC SMB プル サーバーのセットアップ
description: DSC SMB プル サーバーは、DSC 構成ファイルと DSC リソースを必要なときにターゲット ノードに提供する SMB ファイル共有をホストするコンピューターです。
ms.openlocfilehash: 4ac1b0db719fa124d6fa9a654acb64ec24d9ea41
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658434"
---
# <a name="setting-up-a-dsc-smb-pull-server"></a><span data-ttu-id="2e9c6-104">DSC SMB プル サーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="2e9c6-104">Setting up a DSC SMB pull server</span></span>

<span data-ttu-id="2e9c6-105">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="2e9c6-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e9c6-106">プル サーバー (Windows Feature *DSC-Service* ) は、Windows Server のサポート対象のコンポーネントですが、新機能がオファーされる予定はありません。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-106">The Pull Server (Windows Feature *DSC-Service* ) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="2e9c6-107">管理対象のクライアントは、(Windows Server のプル サーバー以降の機能が含まれる) [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) または、[こちら](pullserver.md#community-solutions-for-pull-service)に列挙されているコミュニティ ソリューションのいずれかに切り替えを開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-107">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="2e9c6-108">DSC [SMB](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831795(v=ws.11)) プル サーバーは、DSC 構成ファイルと DSC リソースを必要なときにターゲット ノードに提供する SMB ファイル共有をホストするコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-108">A DSC [SMB](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831795(v=ws.11)) pull server is a computer hosting SMB file shares that make DSC configuration files and DSC resources available to target nodes when those nodes ask for them.</span></span>

<span data-ttu-id="2e9c6-109">DSC の SMB プル サーバーを使うには、次のことが必要です。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-109">To use an SMB pull server for DSC, you have to:</span></span>

- <span data-ttu-id="2e9c6-110">PowerShell 4.0 以降を実行しているサーバーに SMB ファイル共有をセットアップする</span><span class="sxs-lookup"><span data-stu-id="2e9c6-110">Set up an SMB file share on a server running PowerShell 4.0 or higher</span></span>
- <span data-ttu-id="2e9c6-111">SMB 共有からプルするための、PowerShell 4.0 以降を実行しているクライアントを構成する</span><span class="sxs-lookup"><span data-stu-id="2e9c6-111">Configure a client running PowerShell 4.0 or higher to pull from that SMB share</span></span>

## <a name="using-the-xsmbshare-resource-to-create-an-smb-file-share"></a><span data-ttu-id="2e9c6-112">xSmbShare リソースを使用して SMB ファイル共有を作成する</span><span class="sxs-lookup"><span data-stu-id="2e9c6-112">Using the xSmbShare resource to create an SMB file share</span></span>

<span data-ttu-id="2e9c6-113">SMB ファイル共有を設定する方法はいくつかありますが、ここでは DSC を使って設定する方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-113">There are a number of ways to set up an SMB file share, but let's look at how you can do this by using DSC.</span></span>

### <a name="install-the-xsmbshare-resource"></a><span data-ttu-id="2e9c6-114">xSmbShare リソースをインストールする</span><span class="sxs-lookup"><span data-stu-id="2e9c6-114">Install the xSmbShare resource</span></span>

<span data-ttu-id="2e9c6-115">[Install-Module](/powershell/module/PowershellGet/Install-Module) コマンドレットを呼び出して **xSmbShare** モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-115">Call the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet to install the **xSmbShare** module.</span></span>

> [!NOTE]
> <span data-ttu-id="2e9c6-116">`Install-Module` は、PowerShell 5.0 に含まれている **PowerShellGet** モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-116">`Install-Module` is included in the **PowerShellGet** module, which is included in PowerShell 5.0.</span></span>
> <span data-ttu-id="2e9c6-117">**xSmbShare** に含まれる DSC リソース **xSmbShare** を使うと、SMB ファイル共有を作成できます。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-117">The **xSmbShare** contains the DSC resource **xSmbShare** , which can be used to create an SMB file share.</span></span>

### <a name="create-the-directory-and-file-share"></a><span data-ttu-id="2e9c6-118">ディレクトリとファイル共有を作成する</span><span class="sxs-lookup"><span data-stu-id="2e9c6-118">Create the directory and file share</span></span>

<span data-ttu-id="2e9c6-119">次の構成では、 **File** リソースを使って共有するディレクトリを作成し、 **xSmbShare** リソースを使って SMB 共有をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-119">The following configuration uses the **File** resource to create the directory for the share and the **xSmbShare** resource to set up the SMB share:</span></span>

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

<span data-ttu-id="2e9c6-120">ディレクトリ `C:\DscSmbShare` がまだ存在しない場合は、構成によって作成され、そのディレクトリが SMB ファイル共有として使用されます。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-120">The configuration creates the directory `C:\DscSmbShare`, if it doesn't already exist, and then uses that directory as an SMB file share.</span></span> <span data-ttu-id="2e9c6-121">**FullAccess** は、ファイル共有に書き込む必要があるか、ファイル共有から削除する必要があるあらゆるアカウントに付与してください。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-121">**FullAccess** should be given to any account that needs to write to or delete from the file share.</span></span> <span data-ttu-id="2e9c6-122">**ReadAccess** は、共有から構成または DSC リソースを取得するあらゆるクライアント ノードに付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-122">**ReadAccess** must be given to any client nodes that get configurations and/or DSC resources from the share.</span></span>

> [!NOTE]
> <span data-ttu-id="2e9c6-123">DSC は既定ではシステム アカウントとして実行されるので、コンピューター自体も共有にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-123">DSC runs as the system account by default, so the computer itself must have access to the share.</span></span>

### <a name="give-file-system-access-to-the-pull-client"></a><span data-ttu-id="2e9c6-124">ファイル システムにプル クライアントへのアクセス権限を付与する</span><span class="sxs-lookup"><span data-stu-id="2e9c6-124">Give file system access to the pull client</span></span>

<span data-ttu-id="2e9c6-125">クライアント ノードに **ReadAccess** を与えると、そのノードは SMB 共有にアクセスできるようになりますが、その共有内のファイルやフォルダーにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-125">Giving **ReadAccess** to a client node allows that node to access the SMB share, but not to files or folders within that share.</span></span> <span data-ttu-id="2e9c6-126">クライアント ノードに、SMB 共有のフォルダーやサブフォルダーに対するアクセス権限を明示的に許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-126">You have to explicitly grant client nodes access to the SMB share folder and subfolders.</span></span> <span data-ttu-id="2e9c6-127">DSC でこれを行うには、 [cNtfsAccessControl](https://www.powershellgallery.com/packages/cNtfsAccessControl/1.2.0) モジュールに含まれている **cNtfsPermissionEntry** リソースを使用して追加します。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-127">We can do this with DSC by adding using the **cNtfsPermissionEntry** resource, which is contained in the [CNtfsAccessControl](https://www.powershellgallery.com/packages/cNtfsAccessControl/1.2.0) module.</span></span>
<span data-ttu-id="2e9c6-128">次の構成では、プル クライアントに ReadAndExecute アクセスを付与する **cNtfsPermissionEntry** ブロックを追加します。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-128">The following configuration adds a **cNtfsPermissionEntry** block that grants ReadAndExecute access to the pull client:</span></span>

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

## <a name="placing-configurations-and-resources"></a><span data-ttu-id="2e9c6-129">構成とリソースの配置</span><span class="sxs-lookup"><span data-stu-id="2e9c6-129">Placing configurations and resources</span></span>

<span data-ttu-id="2e9c6-130">クライアント ノードがプルする必要のある構成 MOF ファイルや DSC リソースを SMB 共有フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-130">Save any configuration MOF files and/or DSC resources that you want client nodes to pull in the SMB share folder.</span></span>

<span data-ttu-id="2e9c6-131">すべての構成 MOF ファイルは、 *ConfigurationID* .mof という名前である必要があります。ここで、 *ConfigurationID* はターゲット ノードの LCM の **ConfigurationID** プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-131">Any configuration MOF file must be named *ConfigurationID* .mof, where *ConfigurationID* is the value of the **ConfigurationID** property of the target node's LCM.</span></span> <span data-ttu-id="2e9c6-132">プル クライアントの設定の詳細については、「[構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-132">For more information about setting up pull clients, see [Setting up a pull client using configuration ID](pullClientConfigID.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2e9c6-133">SMB プル サーバーを使っている場合は、構成 ID を使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-133">You must use configuration IDs if you are using an SMB pull server.</span></span> <span data-ttu-id="2e9c6-134">構成名は、SMB ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-134">Configuration names are not supported for SMB.</span></span>

<span data-ttu-id="2e9c6-135">各リソース モジュールは、圧縮し、`{Module Name}_{Module Version}.zip` というパターンで名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-135">Each resource module needs to be zipped and named according to the following pattern `{Module Name}_{Module Version}.zip`.</span></span> <span data-ttu-id="2e9c6-136">たとえば、モジュール名が xWebAdminstration で、バージョンが 3.1.2.0 のモジュールでは、'xWebAdministration_3.2.1.0.zip' という名前になります。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-136">For example, a module named xWebAdminstration with a module version of 3.1.2.0 would be named 'xWebAdministration_3.2.1.0.zip'.</span></span> <span data-ttu-id="2e9c6-137">各バージョンのモジュールを 1 つの zip ファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-137">Each version of a module must be contained in a single zip file.</span></span> <span data-ttu-id="2e9c6-138">zip ファイル内のモジュールの個別のバージョンはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-138">Separate versions of a module in a zip file are not supported.</span></span>
<span data-ttu-id="2e9c6-139">プル サーバーで使うための DSC リソース モジュールをパッケージ化する前に、ディレクトリ構造に少しの変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-139">Before packaging up DSC resource modules for use with pull server, you need to make a small change to the directory structure.</span></span>

<span data-ttu-id="2e9c6-140">WMF 5.0 の DSC リソースを含むモジュールの既定の形式は、`{Module Folder}\{Module Version}\DscResources\{DSC Resource Folder}\` です。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-140">The default format of modules containing DSC resource in WMF 5.0 is `{Module Folder}\{Module Version}\DscResources\{DSC Resource Folder}\`.</span></span>

<span data-ttu-id="2e9c6-141">プル サーバー用にパッケージ化する前に、パスが `{Module Folder}\DscResources\{DSC Resource Folder}\` になるように単純に `{Module version}` フォルダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-141">Before packaging up for the pull server simply remove the `{Module version}` folder so the path becomes `{Module Folder}\DscResources\{DSC Resource Folder}\`.</span></span> <span data-ttu-id="2e9c6-142">この変更を加えた後、上で説明したようにフォルダーを zip 圧縮し、これらの zip ファイルを SMB 共有フォルダーに置きます。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-142">With this change, zip the folder as described above and place these zip files in the SMB share folder.</span></span>

## <a name="creating-the-mof-checksum"></a><span data-ttu-id="2e9c6-143">MOF チェックサムの作成</span><span class="sxs-lookup"><span data-stu-id="2e9c6-143">Creating the MOF checksum</span></span>

<span data-ttu-id="2e9c6-144">ターゲット ノード上の LCM が構成を検証できるように、構成 MOF ファイルはチェックサム ファイルと組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-144">A configuration MOF file needs to be paired with a checksum file so that an LCM on a target node can validate the configuration.</span></span> <span data-ttu-id="2e9c6-145">チェックサムを作成するには、[New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-145">To create a checksum, call the [New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum) cmdlet.</span></span> <span data-ttu-id="2e9c6-146">このコマンドレットは、構成 MOF が存在するフォルダーが指定された `Path` パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-146">The cmdlet takes a `Path` parameter that specifies the folder where the configuration MOF is located.</span></span> <span data-ttu-id="2e9c6-147">このコマンドレットは、`ConfigurationMOFName.mof.checksum` という名前でチェックサム ファイルを作成します。ここで、`ConfigurationMOFName` は構成 MOF ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-147">The cmdlet creates a checksum file named `ConfigurationMOFName.mof.checksum`, where `ConfigurationMOFName` is the name of the configuration mof file.</span></span> <span data-ttu-id="2e9c6-148">指定のフォルダーに複数の構成 MOF ファイルがある場合は、そのフォルダー内の構成ごとにチェックサムが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-148">If there are more than one configuration MOF files in the specified folder, a checksum is created for each configuration in the folder.</span></span>

<span data-ttu-id="2e9c6-149">チェックサム ファイルは、構成 MOF ファイルと同じディレクトリ (既定では `$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration`) に存在し、拡張子として `.checksum` が付けられた同じ名前である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-149">The checksum file must be present in the same directory as the configuration MOF file (`$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration` by default), and have the same name with the `.checksum` extension appended.</span></span>

> [!NOTE]
> <span data-ttu-id="2e9c6-150">何らかの方法で構成 MOF ファイルを変更した場合は、チェックサム ファイルも作成し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-150">If you change the configuration MOF file in any way, you must also recreate the checksum file.</span></span>

## <a name="setting-up-a-pull-client-for-smb"></a><span data-ttu-id="2e9c6-151">SMB のプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="2e9c6-151">Setting up a pull client for SMB</span></span>

<span data-ttu-id="2e9c6-152">SMB 共有から構成とリソースの両方または一方をプルするクライアントを設定するには、構成と DSC リソースのプル元の共有を指定する **ConfigurationRepositoryShare** ブロックと **ResourceRepositoryShare** ブロックでクライアントのローカル構成マネージャー (LCM) を構成します。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-152">To set up a client that pulls configurations and/or resources from an SMB share, you configure the client's Local Configuration Manager (LCM) with **ConfigurationRepositoryShare** and **ResourceRepositoryShare** blocks that specify the share from which to pull configurations and DSC resources.</span></span>

<span data-ttu-id="2e9c6-153">LCM 構成の詳細については、「[構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-153">For more information about configuring the LCM, see [Setting up a pull client using configuration ID](pullClientConfigID.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2e9c6-154">わかりやすくする目的で、この例では **PSDscAllowPlainTextPassword** を使用し、 **Credential** パラメーターにプレーンテキスト パスワードを渡すようにしています。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-154">For simplicity, this example uses the **PSDscAllowPlainTextPassword** to allow passing a plaintext password to the **Credential** parameter.</span></span> <span data-ttu-id="2e9c6-155">資格情報をより安全に渡す方法については、「[構成データでの資格情報オプション](../configurations/configDataCredentials.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-155">For information about passing credentials more securely, see [Credentials Options in Configuration Data](../configurations/configDataCredentials.md).</span></span> <span data-ttu-id="2e9c6-156">リソースをプルするだけであっても、SMB プル サーバーのメタ構成の **設定** ブロックに **ConfigurationID** を指定する **必要があります** 。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-156">You **MUST** specify a **ConfigurationID** in the **Settings** block of a metaconfiguration for an SMB pull server, even if you are only pulling resources.</span></span>

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

## <a name="acknowledgements"></a><span data-ttu-id="2e9c6-157">謝辞</span><span class="sxs-lookup"><span data-stu-id="2e9c6-157">Acknowledgements</span></span>

<span data-ttu-id="2e9c6-158">次の方々に感謝します。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-158">Special thanks to the following individuals:</span></span>

- <span data-ttu-id="2e9c6-159">DSC で SMB を使用することに関する Mike F. Robbins 氏の投稿を、このトピックの内容として参考にしました。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-159">Mike F. Robbins, whose posts on using SMB for DSC helped inform the content in this topic.</span></span> <span data-ttu-id="2e9c6-160">彼のブログは [Mike F Robbins](http://mikefrobbins.com/) にあります。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-160">His blog is at [Mike F Robbins](http://mikefrobbins.com/).</span></span>
- <span data-ttu-id="2e9c6-161">**cNtfsAccessControl** モジュールを作成した Serge Nikalaichyk 氏。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-161">Serge Nikalaichyk, who authored the **cNtfsAccessControl** module.</span></span> <span data-ttu-id="2e9c6-162">このモジュールのソースは [cNtfsAccessControl](https://github.com/SNikalaichyk/cNtfsAccessControl) にあります。</span><span class="sxs-lookup"><span data-stu-id="2e9c6-162">The source for this module is at [cNtfsAccessControl](https://github.com/SNikalaichyk/cNtfsAccessControl).</span></span>

## <a name="see-also"></a><span data-ttu-id="2e9c6-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e9c6-163">See also</span></span>

[<span data-ttu-id="2e9c6-164">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="2e9c6-164">Windows PowerShell Desired State Configuration Overview</span></span>](../overview/overview.md)

[<span data-ttu-id="2e9c6-165">構成の適用</span><span class="sxs-lookup"><span data-stu-id="2e9c6-165">Enacting configurations</span></span>](enactingConfigurations.md)

[<span data-ttu-id="2e9c6-166">構成 ID を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="2e9c6-166">Setting up a pull client using configuration ID</span></span>](pullClientConfigID.md)
