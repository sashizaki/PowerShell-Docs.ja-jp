---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC Web プル サーバーのセットアップ"
ms.openlocfilehash: 03d4d148c87854b146091aa0e8d815b8c35def72
ms.sourcegitcommit: 4102ecc35d473211f50a453f6ae3fbea31cb3428
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2017
---
# <a name="setting-up-a-dsc-web-pull-server"></a><span data-ttu-id="53a15-103">DSC Web プル サーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="53a15-103">Setting up a DSC web pull server</span></span>

> <span data-ttu-id="53a15-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="53a15-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="53a15-105">DSC Web プル サーバーは、OData インターフェイスを使用してターゲット ノードからの要求に応じて DSC 構成ファイルをそのターゲット ノードで使用できるようにする、IIS 内の Web サービスです。</span><span class="sxs-lookup"><span data-stu-id="53a15-105">A DSC web pull server is a web service in IIS that uses an OData interface to make DSC configuration files available to target nodes when those nodes ask for them.</span></span>

<span data-ttu-id="53a15-106">プル サーバーを使用するための要件:</span><span class="sxs-lookup"><span data-stu-id="53a15-106">Requirements for using a pull server:</span></span>

* <span data-ttu-id="53a15-107">次のものを実行するサーバー。</span><span class="sxs-lookup"><span data-stu-id="53a15-107">A server running:</span></span>
  - <span data-ttu-id="53a15-108">WMF/PowerShell 5.0 以降</span><span class="sxs-lookup"><span data-stu-id="53a15-108">WMF/PowerShell 5.0 or greater</span></span>
  - <span data-ttu-id="53a15-109">IIS サーバー ロール</span><span class="sxs-lookup"><span data-stu-id="53a15-109">IIS server role</span></span>
  - <span data-ttu-id="53a15-110">DSC サービス</span><span class="sxs-lookup"><span data-stu-id="53a15-110">DSC Service</span></span>
* <span data-ttu-id="53a15-111">理想としては、証明書を生成する何らかの手段。これは、ターゲット ノードのローカル構成マネージャー (LCM) に渡された資格情報をセキュリティ保護するためのものです。</span><span class="sxs-lookup"><span data-stu-id="53a15-111">Ideally, some means of generating a certificate, to secure credentials passed to the Local Configuration Manager (LCM) on target nodes</span></span>

<span data-ttu-id="53a15-112">IIS サーバー ロールと DSC サービスを追加するには、サーバー マネージャーで役割と機能の追加ウィザードを使用するか、または PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="53a15-112">You can add the IIS server role and DSC Service with the Add Roles and Features wizard in Server Manager, or by using PowerShell.</span></span> <span data-ttu-id="53a15-113">どちらの手順も、このトピックに含まれているサンプル スクリプトが自動的に処理します。</span><span class="sxs-lookup"><span data-stu-id="53a15-113">The sample scripts included in this topic will handle both of these steps for you as well.</span></span>

## <a name="using-the-xdscwebservice-resource"></a><span data-ttu-id="53a15-114">xDSCWebService リソースの使用</span><span class="sxs-lookup"><span data-stu-id="53a15-114">Using the xDSCWebService resource</span></span>
<span data-ttu-id="53a15-115">Web プル サーバーをセットアップする最も簡単な方法は、xPSDesiredStateConfiguration モジュールに含まれる xWebService リソースを使用することです。</span><span class="sxs-lookup"><span data-stu-id="53a15-115">The easiest way to set up a web pull server is to use the xWebService resource, included in the xPSDesiredStateConfiguration module.</span></span> <span data-ttu-id="53a15-116">次の手順では、Web サービスをセットアップする構成でリソースを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="53a15-116">The following steps explain how to use the resource in a configuration that sets up the web service.</span></span>

1. <span data-ttu-id="53a15-117">[Install-Module](https://technet.microsoft.com/en-us/library/dn807162.aspx) コマンドレットを呼び出して、**xPSDesiredStateConfiguration** モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="53a15-117">Call the [Install-Module](https://technet.microsoft.com/en-us/library/dn807162.aspx) cmdlet to install the **xPSDesiredStateConfiguration** module.</span></span> <span data-ttu-id="53a15-118">**注**: **Install-Module** は、PowerShell 5.0 に含まれている **PowerShellGet** モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="53a15-118">**Note**: **Install-Module** is included in the **PowerShellGet** module, which is included in PowerShell 5.0.</span></span> <span data-ttu-id="53a15-119">「[PackageManagement PowerShell Modules Preview (PackageManagement PowerShell モジュールのプレビュー)](https://www.microsoft.com/en-us/download/details.aspx?id=49186)」で PowerShell 3.0 と 4.0 の **PowerShellGet** モジュールをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="53a15-119">You can download the **PowerShellGet** module for PowerShell 3.0 and 4.0 at [PackageManagement PowerShell Modules Preview](https://www.microsoft.com/en-us/download/details.aspx?id=49186).</span></span> 
1. <span data-ttu-id="53a15-120">DSC プル サーバーの SSL 証明書を、自社組織内またはパブリック証明機関のいずれかの信頼された証明機関から取得します。</span><span class="sxs-lookup"><span data-stu-id="53a15-120">Get an SSL certificate for the DSC Pull server from a trusted Certificate Authority, either within your organization or a public authority.</span></span> <span data-ttu-id="53a15-121">証明機関から受け取る証明書は、通常、PFX 形式です。</span><span class="sxs-lookup"><span data-stu-id="53a15-121">The certificate received from the authority is usually in the PFX format.</span></span> <span data-ttu-id="53a15-122">証明書は、DSC プル サーバーになるノードの既定の場所 (CERT:\LocalMachine\My である必要があります) にインストールします。</span><span class="sxs-lookup"><span data-stu-id="53a15-122">Install the certificate on the node that will become the DSC Pull server in the default location which should be CERT:\LocalMachine\My.</span></span> <span data-ttu-id="53a15-123">証明書の拇印をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="53a15-123">Make a note of the certificate thumbprint.</span></span>
1. <span data-ttu-id="53a15-124">登録キーとして使う GUID を選択します。</span><span class="sxs-lookup"><span data-stu-id="53a15-124">Select a GUID to be used as the Registration Key.</span></span> <span data-ttu-id="53a15-125">PowerShell を使って GUID を生成するには、PS プロンプトに「``` [guid]::newGuid()```」または「```New-Guid```」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="53a15-125">To generate one using PowerShell enter the following at the PS prompt and press enter: '``` [guid]::newGuid()```' or '```New-Guid```'.</span></span> <span data-ttu-id="53a15-126">このキーは、登録時にクライアント ノードによって認証のために共有キーとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="53a15-126">This key will be used by client nodes as a shared key to authenticate during registration.</span></span> <span data-ttu-id="53a15-127">詳細については、この後の「登録キー」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="53a15-127">For more information see the Registration Key section below.</span></span>
1. <span data-ttu-id="53a15-128">PowerShell ISE で、次の構成スクリプトを起動 (F5) します (このスクリプトは、**xPSDesiredStateConfiguration** モジュールの Example フォルダーに Sample_xDscWebService.ps1 として存在します)。</span><span class="sxs-lookup"><span data-stu-id="53a15-128">In the PowerShell ISE, start (F5) the following configuration script (included in the Example folder of the  **xPSDesiredStateConfiguration** module as Sample_xDscWebService.ps1).</span></span> <span data-ttu-id="53a15-129">このスクリプトは、プル サーバーをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="53a15-129">This script sets up the pull server.</span></span>
  
    ```powershell
    configuration Sample_xDscPullServer
    { 
        param  
        ( 
                [string[]]$NodeName = 'localhost', 

                [ValidateNotNullOrEmpty()] 
                [string] $certificateThumbPrint,

                [Parameter(Mandatory)]
                [ValidateNotNullOrEmpty()]
                [string] $RegistrationKey 
         ) 
         
         Import-DSCResource -ModuleName xPSDesiredStateConfiguration
         Import-DSCResource –ModuleName PSDesiredStateConfiguration

         Node $NodeName 
         { 
             WindowsFeature DSCServiceFeature 
             { 
                 Ensure = 'Present'
                 Name   = 'DSC-Service'             
             } 

             xDscWebService PSDSCPullServer 
             { 
                 Ensure                   = 'Present' 
                 EndpointName             = 'PSDSCPullServer' 
                 Port                     = 8080 
                 PhysicalPath             = "$env:SystemDrive\inetpub\PSDSCPullServer" 
                 CertificateThumbPrint    = $certificateThumbPrint          
                 ModulePath               = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules" 
                 ConfigurationPath        = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration" 
                 State                    = 'Started'
                 DependsOn                = '[WindowsFeature]DSCServiceFeature'     
                 UseSecurityBestPractices = $false
             } 

            File RegistrationKeyFile
            {
                Ensure          = 'Present'
                Type            = 'File'
                DestinationPath = "$env:ProgramFiles\WindowsPowerShell\DscService\RegistrationKeys.txt"
                Contents        = $RegistrationKey
            }
        }
    }

    ```

1. <span data-ttu-id="53a15-130">構成を実行します。このとき、SSL 証明書の拇印を **certificateThumbPrint** パラメーターとして渡し、GUID 登録キーを **RegistrationKey** パラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="53a15-130">Run the configuration, passing the thumbprint of the SSL certificate as the **certificateThumbPrint** parameter and a GUID registration key as the **RegistrationKey** parameter:</span></span>

    ```powershell
    # To find the Thumbprint for an installed SSL certificate for use with the pull server list all certificates in your local store 
    # and then copy the thumbprint for the appropriate certificate by reviewing the certificate subjects
    dir Cert:\LocalMachine\my

    # Then include this thumbprint when running the configuration
    Sample_xDSCPullServer -certificateThumbprint 'A7000024B753FA6FFF88E966FD6E19301FAE9CCC' -RegistrationKey '140a952b-b9d6-406b-b416-e0f759c9c0e4' -OutputPath c:\Configs\PullServer

    # Run the compiled configuration to make the target node a DSC Pull Server
    Start-DscConfiguration -Path c:\Configs\PullServer -Wait -Verbose
    ```

## <a name="registration-key"></a><span data-ttu-id="53a15-131">登録キー</span><span class="sxs-lookup"><span data-stu-id="53a15-131">Registration Key</span></span>
<span data-ttu-id="53a15-132">サーバーにクライアント ノードを登録して、構成 ID の代わりに構成名を使用できるように、上の構成で作成された登録キーは、`C:\Program Files\WindowsPowerShell\DscService` にある `RegistrationKeys.txt` という名前のファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="53a15-132">To allow client nodes to register with the server so that they can use configuration names instead of a configuration ID, a registration key which was created by the above configuration is saved in a file named `RegistrationKeys.txt` in `C:\Program Files\WindowsPowerShell\DscService`.</span></span> <span data-ttu-id="53a15-133">登録キーは、クライアントがプル サーバーに初期登録を行うときに共有シークレットとして機能します。</span><span class="sxs-lookup"><span data-stu-id="53a15-133">The registration key functions as a shared secret used during the initial registration by the client with the pull server.</span></span> <span data-ttu-id="53a15-134">登録が正常に完了すると、クライアントは、プル サーバーに一意に認証されるために使う自己署名証明書を生成します。</span><span class="sxs-lookup"><span data-stu-id="53a15-134">The client will generate a self-signed certificate which is used to uniquely authenticate to the pull server once registration is successfully completed.</span></span> <span data-ttu-id="53a15-135">この証明書の拇印がローカルに保存され、プル サーバーの URL に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="53a15-135">The thumbprint of this certificate is stored locally and associated with the URL of the pull server.</span></span>
> <span data-ttu-id="53a15-136">**注**: 登録キーは、PowerShell 4.0 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="53a15-136">**Note**: Registration keys are not supported in PowerShell 4.0.</span></span> 

<span data-ttu-id="53a15-137">プル サーバーで認証するようにノードを構成するには、登録キーが、このプル サーバーに登録されるすべてのターゲット ノードのメタ構成に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="53a15-137">In order to configure a node to authenticate with the pull server the registration key needs to be in the metaconfiguration for any target node that will be registering with this pull server.</span></span> <span data-ttu-id="53a15-138">なお、次のメタ構成にある **RegistrationKey** は、ターゲット コンピューターが正常に登録された後に削除され、値 '140a952b-b9d6-406b-b416-e0f759c9c0e4' はプル サーバーの RegistrationKeys.txt ファイルに格納されている値と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53a15-138">Note that the **RegistrationKey** in the metaconfiguration below is removed after the target machine has successfully registered, and that the value '140a952b-b9d6-406b-b416-e0f759c9c0e4' must match the value stored in the RegistrationKeys.txt file on the pull server.</span></span> <span data-ttu-id="53a15-139">登録キー値を知ると、任意のターゲット コンピューターをプル サーバーに登録できるようになるので、登録キー値は常にセキュリティで保護してください。</span><span class="sxs-lookup"><span data-stu-id="53a15-139">Always treat the registration key value securely, because knowing it allows any target machine to register with the pull server.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode          = 'Pull'
            RefreshFrequencyMins = 30 
            RebootNodeIfNeeded   = $true
        }
        
        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL          = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey    = '140a952b-b9d6-406b-b416-e0f759c9c0e4'
            ConfigurationNames = @('ClientConfig')
        }   
        
        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL       = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = '140a952b-b9d6-406b-b416-e0f759c9c0e4'
        }
    }
}

PullClientConfigID -OutputPath c:\Configs\TargetNodes
```
> <span data-ttu-id="53a15-140">**注**: **ReportServerWeb** セクションでは、レポートするデータをプル サーバーに送信できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="53a15-140">**Note**: The **ReportServerWeb** section allows reporting data to be sent to the pull server.</span></span> 

<span data-ttu-id="53a15-141">メタ構成ファイルに **ConfigurationID** プロパティがないことは、暗黙的に、そのプル サーバーが V2 バージョンのプル サーバー プロトコルをサポートしていることを示すので、初期登録が必要になります。</span><span class="sxs-lookup"><span data-stu-id="53a15-141">The lack of the **ConfigurationID** property in the metaconfiguration file implicitly means that pull server is supporting the V2 version of the pull server protocol so an initial registration is required.</span></span> <span data-ttu-id="53a15-142">逆に、**ConfigurationID** が存在することは、V1 バージョンのプル サーバー プロトコルが使用され、登録処理がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="53a15-142">Conversely, the presence of a **ConfigurationID** means that the V1 version of the pull server protocol is used and there is no registration processing.</span></span>

><span data-ttu-id="53a15-143">**注**: プッシュのシナリオでは、現在のリリースにバグが存在するため、プル サーバーに登録されていないノードについても、メタ構成ファイルで ConfigurationID プロパティを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53a15-143">**Note**: In a PUSH scenario, a bug exists in the current relase that makes it necessary to define a ConfigurationID property in the metaconfiguration file for nodes that have never registered with a pull server.</span></span> <span data-ttu-id="53a15-144">こうすると、V1 プル サーバー プロトコルが強制されるので、登録エラーのメッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="53a15-144">This will force the V1 Pull Server protocol and avoid registration failure messages.</span></span>

## <a name="placing-configurations-and-resources"></a><span data-ttu-id="53a15-145">構成とリソースの配置</span><span class="sxs-lookup"><span data-stu-id="53a15-145">Placing configurations and resources</span></span>

<span data-ttu-id="53a15-146">プル サーバーのセットアップが完了すると、プル サーバーの構成で **ConfigurationPath** プロパティと **ModulePath** プロパティによって定義されているフォルダーは、プルするためにターゲット ノードで使用可能にするモジュールと構成を配置する場所になります。</span><span class="sxs-lookup"><span data-stu-id="53a15-146">After the pull server setup completes, the folders defined by the **ConfigurationPath** and **ModulePath** properties in the pull server configuration are where you will place modules and configurations that will be available for target nodes to pull.</span></span> <span data-ttu-id="53a15-147">これらのファイルをプル サーバーが正しく処理するためには、特定の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="53a15-147">These files need to be in a specific format in order for the pull server to correctly process them.</span></span> 

### <a name="dsc-resource-module-package-format"></a><span data-ttu-id="53a15-148">DSC リソース モジュールのパッケージの形式</span><span class="sxs-lookup"><span data-stu-id="53a15-148">DSC resource module package format</span></span>

<span data-ttu-id="53a15-149">各リソース モジュールは、圧縮し、`{Module Name}_{Module Version}.zip` というパターンで名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="53a15-149">Each resource module needs to be zipped and named according the following pattern `{Module Name}_{Module Version}.zip`.</span></span> <span data-ttu-id="53a15-150">たとえば、モジュール名が xWebAdminstration で、バージョンが 3.1.2.0 のモジュールでは、'xWebAdministration_3.2.1.0.zip' という名前になります。</span><span class="sxs-lookup"><span data-stu-id="53a15-150">For example, a module named xWebAdminstration with a module version of 3.1.2.0 would be named 'xWebAdministration_3.2.1.0.zip'.</span></span> <span data-ttu-id="53a15-151">各バージョンのモジュールを 1 つの zip ファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="53a15-151">Each version of a module must be contained in a single zip file.</span></span> <span data-ttu-id="53a15-152">各 zip ファイルには 1 つのバージョンのリソースのみが含まれるので、WMF 5.0 で追加された、単一のディレクトリに複数のモジュール バージョンを入れるモジュール形式はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="53a15-152">Since there is only a single version of a resource in each zip file the module format added in WMF 5.0 with support for multiple module versions in a single directory is not supported.</span></span> <span data-ttu-id="53a15-153">このため、プル サーバーで使うための DSC リソース モジュールをパッケージ化する前に、ディレクトリ構造に少しの変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="53a15-153">This means that before packaging up DSC resource modules for use with pull server you will need to make a small change to the directory structure.</span></span> <span data-ttu-id="53a15-154">WMF 5.0 の DSC リソースを含むモジュールの既定の形式は、'{モジュール フォルダー}\{モジュールのバージョン}\DscResources\{DSC リソース フォルダー}\' です。</span><span class="sxs-lookup"><span data-stu-id="53a15-154">The default format of modules containing DSC resource in WMF 5.0 is '{Module Folder}\{Module Version}\DscResources\{DSC Resource Folder}\'.</span></span> <span data-ttu-id="53a15-155">プル サーバー用にパッケージ化する前には、単純に **{モジュールのバージョン}** フォルダーを削除して、'{モジュール フォルダー}\DscResources\{DSC リソース フォルダー}\' というパスにします。</span><span class="sxs-lookup"><span data-stu-id="53a15-155">Before packaging up for the pull server simply remove the **{Module version}** folder so the path becomes '{Module Folder}\DscResources\{DSC Resource Folder}\'.</span></span> <span data-ttu-id="53a15-156">この変更を加えた後、上で説明したようにフォルダーを zip 圧縮し、これらの zip ファイルを **ModulePath** フォルダーに置きます。</span><span class="sxs-lookup"><span data-stu-id="53a15-156">With this change, zip the folder as described above and place these zip files in the **ModulePath** folder.</span></span>

<span data-ttu-id="53a15-157">新しく追加したモジュールのチェックサム ファイルを作成するには、`new-dscchecksum {module zip file}` を使用します。</span><span class="sxs-lookup"><span data-stu-id="53a15-157">Use `new-dscchecksum {module zip file}` to create a checksum file for the newly-added module.</span></span>

### <a name="configuration-mof-format"></a><span data-ttu-id="53a15-158">構成 MOF の形式</span><span class="sxs-lookup"><span data-stu-id="53a15-158">Configuration MOF format</span></span> 
<span data-ttu-id="53a15-159">ターゲット ノード上の LCM が構成を検証できるように、構成 MOF ファイルはチェックサム ファイルと組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53a15-159">A configuration MOF file needs to be paired with a checksum file so that an LCM on a target node can validate the configuration.</span></span> <span data-ttu-id="53a15-160">チェックサムを作成するには、[New-DSCCheckSum](https://technet.microsoft.com/en-us/library/dn521622.aspx) コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="53a15-160">To create a checksum, call the [New-DSCCheckSum](https://technet.microsoft.com/en-us/library/dn521622.aspx) cmdlet.</span></span> <span data-ttu-id="53a15-161">このコマンドレットは、構成 MOF が存在するフォルダーが指定された **Path** パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="53a15-161">The cmdlet takes a **Path** parameter that specifies the folder where the configuration MOF is located.</span></span> <span data-ttu-id="53a15-162">このコマンドレットは、`ConfigurationMOFName.mof.checksum` という名前でチェックサム ファイルを作成します。ここで、`ConfigurationMOFName` は構成 MOF ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="53a15-162">The cmdlet creates a checksum file named `ConfigurationMOFName.mof.checksum`, where `ConfigurationMOFName` is the name of the configuration mof file.</span></span> <span data-ttu-id="53a15-163">指定のフォルダーに複数の構成 MOF ファイルがある場合は、そのフォルダー内の構成ごとにチェックサムが作成されます。</span><span class="sxs-lookup"><span data-stu-id="53a15-163">If there are more than one configuration MOF files in the specified folder, a checksum is created for each configuration in the folder.</span></span> <span data-ttu-id="53a15-164">MOF ファイルと、それに関連するチェックサム ファイルは、**ConfigurationPath** フォルダーに配置します。</span><span class="sxs-lookup"><span data-stu-id="53a15-164">Place the MOF files and their associated checksum files in the the **ConfigurationPath** folder.</span></span>

><span data-ttu-id="53a15-165">**注**: 何らかの方法で構成 MOF ファイルを変更した場合は、チェックサム ファイルも作成し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="53a15-165">**Note**: If you change the configuration MOF file in any way, you must also recreate the checksum file.</span></span>

## <a name="tooling"></a><span data-ttu-id="53a15-166">ツール</span><span class="sxs-lookup"><span data-stu-id="53a15-166">Tooling</span></span>
<span data-ttu-id="53a15-167">プル サーバーのセットアップ、検証、管理を簡素化するために、次のツールが、xPSDesiredStateConfiguration モジュールの最新バージョンに例として含まれています。</span><span class="sxs-lookup"><span data-stu-id="53a15-167">In order to make setting up, validating and managing the pull server easier, the following tools are included as examples in the latest version of the xPSDesiredStateConfiguration module:</span></span>
1. <span data-ttu-id="53a15-168">プル サーバーに使用する DSC リソース モジュールおよび構成ファイルをパッケージ化するために役立つモジュール。</span><span class="sxs-lookup"><span data-stu-id="53a15-168">A module that will help with packaging DSC resource modules and configuration files for use on the pull server.</span></span> <span data-ttu-id="53a15-169">[PublishModulesAndMofsToPullServer.psm1](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/dev/DSCPullServerSetup/PublishModulesAndMofsToPullServer.psm1)。</span><span class="sxs-lookup"><span data-stu-id="53a15-169">[PublishModulesAndMofsToPullServer.psm1](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/dev/DSCPullServerSetup/PublishModulesAndMofsToPullServer.psm1).</span></span> <span data-ttu-id="53a15-170">次の例です。</span><span class="sxs-lookup"><span data-stu-id="53a15-170">Examples below:</span></span>

    ```powershell
        # Example 1 - Package all versions of given modules installed locally and MOF files are in c:\LocalDepot
         $moduleList = @("xWebAdministration", "xPhp") 
         Publish-DSCModuleAndMof -Source C:\LocalDepot -ModuleNameList $moduleList 

         # Example 2 - Package modules and mof documents from c:\LocalDepot
         Publish-DSCModuleAndMof -Source C:\LocalDepot -Force
    ```

1. <span data-ttu-id="53a15-171">プル サーバーが正しく構成されていることを検証するスクリプト。</span><span class="sxs-lookup"><span data-stu-id="53a15-171">A script that validates the pull server is configured correctly.</span></span> <span data-ttu-id="53a15-172">[PullServerSetupTests.ps1](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/dev/DSCPullServerSetup/PullServerDeploymentVerificationTest/PullServerSetupTests.ps1)。</span><span class="sxs-lookup"><span data-stu-id="53a15-172">[PullServerSetupTests.ps1](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/dev/DSCPullServerSetup/PullServerDeploymentVerificationTest/PullServerSetupTests.ps1).</span></span>


## <a name="pull-client-configuration"></a><span data-ttu-id="53a15-173">プル クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="53a15-173">Pull client configuration</span></span> 
<span data-ttu-id="53a15-174">次のトピックでは、プル クライアントのセットアップについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="53a15-174">The following topics describe setting up pull clients in detail:</span></span>

* [<span data-ttu-id="53a15-175">構成 ID を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="53a15-175">Setting up a DSC pull client using a configuration ID</span></span>](pullClientConfigID.md)
* [<span data-ttu-id="53a15-176">構成名を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="53a15-176">Setting up a DSC pull client using configuration names</span></span>](pullClientConfigNames.md)
* [<span data-ttu-id="53a15-177">部分構成</span><span class="sxs-lookup"><span data-stu-id="53a15-177">Partial configurations</span></span>](partialConfigs.md)


## <a name="see-also"></a><span data-ttu-id="53a15-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="53a15-178">See also</span></span>
* [<span data-ttu-id="53a15-179">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="53a15-179">Windows PowerShell Desired State Configuration Overview</span></span>](overview.md)
* [<span data-ttu-id="53a15-180">構成の適用</span><span class="sxs-lookup"><span data-stu-id="53a15-180">Enacting configurations</span></span>](enactingConfigurations.md)
* [<span data-ttu-id="53a15-181">DSC レポート サーバーの使用</span><span class="sxs-lookup"><span data-stu-id="53a15-181">Using a DSC report server</span></span>](reportServer.md)

