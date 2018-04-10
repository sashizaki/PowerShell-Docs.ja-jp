---
ms.date: 02/02/2018
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC プル サービス
ms.openlocfilehash: 1547092d5ea6733296bf89f05dd96f70c0a000ac
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="desired-state-configuration-pull-service"></a><span data-ttu-id="270d8-103">Desired State Configuration プル サービス</span><span class="sxs-lookup"><span data-stu-id="270d8-103">Desired State Configuration Pull Service</span></span>

> <span data-ttu-id="270d8-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="270d8-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="270d8-105">ローカル構成マネージャーは、プル サービス ソリューションで一元管理できます。</span><span class="sxs-lookup"><span data-stu-id="270d8-105">Local Configuration Manager can be centrally managed by a Pull Service solution.</span></span>
<span data-ttu-id="270d8-106">この方法を使用する場合、管理対象のノードはサービスに登録され、LCM 設定で構成が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="270d8-106">When using this approach, the node that is being managed is registered with a service and assigned a configuration in LCM settings.</span></span>
<span data-ttu-id="270d8-107">構成の依存関係として必要な構成とすべての DSC リソースは、マシンにダウンロードされ、構成を管理するために LCM によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="270d8-107">The configuration and all DSC resources needed as dependencies for the configuration are downloaded to the machine and used by LCM to manage the configuration.</span></span>
<span data-ttu-id="270d8-108">管理対象のマシンの状態に関する情報は、レポートのためにサービスにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="270d8-108">Information about the state of the machine being managed is uploaded to the service for reporting.</span></span>
<span data-ttu-id="270d8-109">この概念は "プル サービス" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="270d8-109">This concept is referred to as "pull service".</span></span>

<span data-ttu-id="270d8-110">現在選択できるプル サービスは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="270d8-110">The current options for pull service include:</span></span>

- <span data-ttu-id="270d8-111">Azure Automation Desired State Configuration サービス</span><span class="sxs-lookup"><span data-stu-id="270d8-111">Azure Automation Desired State Configuration service</span></span>
- <span data-ttu-id="270d8-112">Windows Server で実行されるプル サービス</span><span class="sxs-lookup"><span data-stu-id="270d8-112">A pull service running on Windows Server</span></span>
- <span data-ttu-id="270d8-113">コミュニティが維持するオープン ソースのソリューション</span><span class="sxs-lookup"><span data-stu-id="270d8-113">Community maintained open source solutions</span></span>
- <span data-ttu-id="270d8-114">SMB 共有</span><span class="sxs-lookup"><span data-stu-id="270d8-114">An SMB share</span></span>

<span data-ttu-id="270d8-115">**推奨されるソリューション**であり、最も多くの機能を使用できる選択肢は [Azure Automation DSC](https://docs.microsoft.com/en-us/azure/automation/automation-dsc-getting-started) です。</span><span class="sxs-lookup"><span data-stu-id="270d8-115">**The recommended solution**, and the option with the most features available, is [Azure Automation DSC](https://docs.microsoft.com/en-us/azure/automation/automation-dsc-getting-started).</span></span>

<span data-ttu-id="270d8-116">Azure サービスでは、プライベート データセンター内にあるオンプレミス ノードと、パブリック クラウド （Azure や AWS など) 内にあるノードのどちらも管理できます。</span><span class="sxs-lookup"><span data-stu-id="270d8-116">The Azure service can manage nodes on-premises in private datacenters, or in public clouds such as Azure and AWS.</span></span>
<span data-ttu-id="270d8-117">インターネットへのサーバーの直接接続が許可されないプライベート環境の場合は、公開されている Azure の IP 範囲 ([Azure データセンターの IP 範囲](https://www.microsoft.com/en-us/download/details.aspx?id=41653)に関するページを参照) のみに送信トラフィックを制限することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="270d8-117">For private environments where servers cannot directly connect to the Internet, consider limiting outbound traffic to only the published Azure IP range (see [Azure Datacenter IP Ranges](https://www.microsoft.com/en-us/download/details.aspx?id=41653)).</span></span>

<span data-ttu-id="270d8-118">現時点で Windows Server 上のプル サービスでは利用できないオンライン サービスの機能は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="270d8-118">Features of the online service that are not currently available in the pull service on Windows Server include:</span></span>
- <span data-ttu-id="270d8-119">転送中および保存中のすべてのデータの暗号化</span><span class="sxs-lookup"><span data-stu-id="270d8-119">All data is encrypted in transit and at rest</span></span>
- <span data-ttu-id="270d8-120">クライアント証明書の自動作成および管理</span><span class="sxs-lookup"><span data-stu-id="270d8-120">Client certificates are created and managed automatically</span></span>
- <span data-ttu-id="270d8-121">[パスワード/資格情報](https://docs.microsoft.com/en-us/azure/automation/automation-credentials) または[変数](https://docs.microsoft.com/en-us/azure/automation/automation-variables) (サーバー名や接続文字列など) を一元管理するためのシークレット ストア</span><span class="sxs-lookup"><span data-stu-id="270d8-121">Secrets store for centrally managing [passwords/credentials](https://docs.microsoft.com/en-us/azure/automation/automation-credentials), or [variables](https://docs.microsoft.com/en-us/azure/automation/automation-variables) such as server names or connection strings</span></span>
- <span data-ttu-id="270d8-122">[LCM 構成](metaConfig.md#basic-settings)ノードの一元管理</span><span class="sxs-lookup"><span data-stu-id="270d8-122">Centrally manage node [LCM configuration](metaConfig.md#basic-settings)</span></span>
- <span data-ttu-id="270d8-123">クライアント ノードへ構成を一元的に割り当てる</span><span class="sxs-lookup"><span data-stu-id="270d8-123">Centrally assign configurations to client nodes</span></span>
- <span data-ttu-id="270d8-124">運用環境への適用前に "カナリア グループ" へ構成の変更をリリースしてテストする</span><span class="sxs-lookup"><span data-stu-id="270d8-124">Release configuration changes to "canary groups" for testing before reaching production</span></span>
- <span data-ttu-id="270d8-125">グラフィカル レポート</span><span class="sxs-lookup"><span data-stu-id="270d8-125">Graphical reporting</span></span>
  - <span data-ttu-id="270d8-126">きめ細かな DSC リソース レベルでの状態の詳細</span><span class="sxs-lookup"><span data-stu-id="270d8-126">Status detail at the DSC resource level of granularity</span></span>
  - <span data-ttu-id="270d8-127">クライアント マシンからの詳細なエラー メッセージによるトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="270d8-127">Verbose error messages from client machines for troubleshooting</span></span>
- <span data-ttu-id="270d8-128">[Azure Log Analytics との統合](https://docs.microsoft.com/en-us/azure/automation/automation-dsc-diagnostics)によるアラートとタスクの自動化、およびレポートとアラート用の Android/iOS アプリ</span><span class="sxs-lookup"><span data-stu-id="270d8-128">[Integration with Azure Log Analytics](https://docs.microsoft.com/en-us/azure/automation/automation-dsc-diagnostics) for alerting, automated tasks, Android/iOS app for reporting and alerting</span></span>

## <a name="dsc-pull-service-in-windows-server"></a><span data-ttu-id="270d8-129">Windows Server の DSC プル サービス</span><span class="sxs-lookup"><span data-stu-id="270d8-129">DSC pull service in Windows Server</span></span>

<span data-ttu-id="270d8-130">Windows Server 上でプル サービスを実行するように構成することができます。</span><span class="sxs-lookup"><span data-stu-id="270d8-130">It is possible to configuring a pull service to run on Windows Server.</span></span>
<span data-ttu-id="270d8-131">Windows Server に含まれるプル サービス ソリューションには、ダウンロード用の構成/モジュールを格納する機能と、レポート データをデータベースにキャプチャする機能のみが含まれている点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="270d8-131">Please be advised that the pull service solution included in Windows Server includes only capabilities of storing configurations/modules for download and capturing report data in to database.</span></span>
<span data-ttu-id="270d8-132">Azure のサービスで提供される機能の多くは含まれていないため、サービスの使用方法を評価する場合に適したツールではありません。</span><span class="sxs-lookup"><span data-stu-id="270d8-132">It does not include many of the capabilities offered by the service in Azure and so is not a good tool for evaluating how the service would be used.</span></span>

<span data-ttu-id="270d8-133">Windows Server で提供されるプル サービスは、OData インターフェイスを使用してターゲット ノードからの要求に応じて DSC 構成ファイルをそのターゲット ノードで使用できるようにする、IIS 内の Web サービスです。</span><span class="sxs-lookup"><span data-stu-id="270d8-133">The pull service offered in Windows Server is a web service in IIS that uses an OData interface to make DSC configuration files available to target nodes when those nodes ask for them.</span></span>

<span data-ttu-id="270d8-134">プル サーバーを使用するための要件:</span><span class="sxs-lookup"><span data-stu-id="270d8-134">Requirements for using a pull server:</span></span>

- <span data-ttu-id="270d8-135">次のものを実行するサーバー。</span><span class="sxs-lookup"><span data-stu-id="270d8-135">A server running:</span></span>
  - <span data-ttu-id="270d8-136">WMF/PowerShell 5.0 以降</span><span class="sxs-lookup"><span data-stu-id="270d8-136">WMF/PowerShell 5.0 or greater</span></span>
  - <span data-ttu-id="270d8-137">IIS サーバー ロール</span><span class="sxs-lookup"><span data-stu-id="270d8-137">IIS server role</span></span>
  - <span data-ttu-id="270d8-138">DSC サービス</span><span class="sxs-lookup"><span data-stu-id="270d8-138">DSC Service</span></span>
- <span data-ttu-id="270d8-139">理想としては、証明書を生成する何らかの手段。これは、ターゲット ノードのローカル構成マネージャー (LCM) に渡された資格情報をセキュリティ保護するためのものです。</span><span class="sxs-lookup"><span data-stu-id="270d8-139">Ideally, some means of generating a certificate, to secure credentials passed to the Local Configuration Manager (LCM) on target nodes</span></span>

<span data-ttu-id="270d8-140">プル サービスをホストするように Windows Server を構成するには、DSC 構成を使用する方法が最適です。</span><span class="sxs-lookup"><span data-stu-id="270d8-140">The best way to configure Windows Server to host pull service is to use a DSC configuration.</span></span>
<span data-ttu-id="270d8-141">スクリプトの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="270d8-141">An example script is provided below.</span></span>

### <a name="using-the-xdscwebservice-resource"></a><span data-ttu-id="270d8-142">xDSCWebService リソースの使用</span><span class="sxs-lookup"><span data-stu-id="270d8-142">Using the xDSCWebService resource</span></span>

<span data-ttu-id="270d8-143">Web プル サーバーをセットアップする最も簡単な方法は、xPSDesiredStateConfiguration モジュールに含まれる xWebService リソースを使用することです。</span><span class="sxs-lookup"><span data-stu-id="270d8-143">The easiest way to set up a web pull server is to use the xWebService resource, included in the xPSDesiredStateConfiguration module.</span></span>
<span data-ttu-id="270d8-144">次の手順では、Web サービスをセットアップする構成でリソースを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="270d8-144">The following steps explain how to use the resource in a configuration that sets up the web service.</span></span>

1. <span data-ttu-id="270d8-145">[Install-Module](https://technet.microsoft.com/en-us/library/dn807162.aspx) コマンドレットを呼び出して、**xPSDesiredStateConfiguration** モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="270d8-145">Call the [Install-Module](https://technet.microsoft.com/en-us/library/dn807162.aspx) cmdlet to install the **xPSDesiredStateConfiguration** module.</span></span> <span data-ttu-id="270d8-146">**注**: **Install-Module** は、PowerShell 5.0 に含まれている **PowerShellGet** モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="270d8-146">**Note**: **Install-Module** is included in the **PowerShellGet** module, which is included in PowerShell 5.0.</span></span> <span data-ttu-id="270d8-147">「[PackageManagement PowerShell Modules Preview (PackageManagement PowerShell モジュールのプレビュー)](https://www.microsoft.com/en-us/download/details.aspx?id=49186)」で PowerShell 3.0 と 4.0 の **PowerShellGet** モジュールをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="270d8-147">You can download the **PowerShellGet** module for PowerShell 3.0 and 4.0 at [PackageManagement PowerShell Modules Preview](https://www.microsoft.com/en-us/download/details.aspx?id=49186).</span></span>
1. <span data-ttu-id="270d8-148">DSC プル サーバーの SSL 証明書を、自社組織内またはパブリック証明機関のいずれかの信頼された証明機関から取得します。</span><span class="sxs-lookup"><span data-stu-id="270d8-148">Get an SSL certificate for the DSC Pull server from a trusted Certificate Authority, either within your organization or a public authority.</span></span> <span data-ttu-id="270d8-149">証明機関から受け取る証明書は、通常、PFX 形式です。</span><span class="sxs-lookup"><span data-stu-id="270d8-149">The certificate received from the authority is usually in the PFX format.</span></span> <span data-ttu-id="270d8-150">証明書は、DSC プル サーバーになるノードの既定の場所 (CERT:\LocalMachine\My である必要があります) にインストールします。</span><span class="sxs-lookup"><span data-stu-id="270d8-150">Install the certificate on the node that will become the DSC Pull server in the default location which should be CERT:\LocalMachine\My.</span></span> <span data-ttu-id="270d8-151">証明書の拇印をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="270d8-151">Make a note of the certificate thumbprint.</span></span>
1. <span data-ttu-id="270d8-152">登録キーとして使う GUID を選択します。</span><span class="sxs-lookup"><span data-stu-id="270d8-152">Select a GUID to be used as the Registration Key.</span></span> <span data-ttu-id="270d8-153">PowerShell を使って GUID を生成するには、PS プロンプトに「``` [guid]::newGuid()```」または「```New-Guid```」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="270d8-153">To generate one using PowerShell enter the following at the PS prompt and press enter: '``` [guid]::newGuid()```' or '```New-Guid```'.</span></span> <span data-ttu-id="270d8-154">このキーは、登録時にクライアント ノードによって認証のために共有キーとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="270d8-154">This key will be used by client nodes as a shared key to authenticate during registration.</span></span> <span data-ttu-id="270d8-155">詳細については、この後の「登録キー」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="270d8-155">For more information see the Registration Key section below.</span></span>
1. <span data-ttu-id="270d8-156">PowerShell ISE で、次の構成スクリプトを起動 (F5) します (このスクリプトは、**xPSDesiredStateConfiguration** モジュールの Example フォルダーに Sample_xDscWebService.ps1 として存在します)。</span><span class="sxs-lookup"><span data-stu-id="270d8-156">In the PowerShell ISE, start (F5) the following configuration script (included in the Example folder of the  **xPSDesiredStateConfiguration** module as Sample_xDscWebService.ps1).</span></span> <span data-ttu-id="270d8-157">このスクリプトは、プル サーバーをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="270d8-157">This script sets up the pull server.</span></span>

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

1. <span data-ttu-id="270d8-158">構成を実行します。このとき、SSL 証明書の拇印を **certificateThumbPrint** パラメーターとして渡し、GUID 登録キーを **RegistrationKey** パラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="270d8-158">Run the configuration, passing the thumbprint of the SSL certificate as the **certificateThumbPrint** parameter and a GUID registration key as the **RegistrationKey** parameter:</span></span>

```powershell
    # To find the Thumbprint for an installed SSL certificate for use with the pull server list all certificates in your local store
    # and then copy the thumbprint for the appropriate certificate by reviewing the certificate subjects
    dir Cert:\LocalMachine\my

    # Then include this thumbprint when running the configuration
    Sample_xDSCPullServer -certificateThumbprint 'A7000024B753FA6FFF88E966FD6E19301FAE9CCC' -RegistrationKey '140a952b-b9d6-406b-b416-e0f759c9c0e4' -OutputPath c:\Configs\PullServer

    # Run the compiled configuration to make the target node a DSC Pull Server
    Start-DscConfiguration -Path c:\Configs\PullServer -Wait -Verbose

```

#### <a name="registration-key"></a><span data-ttu-id="270d8-159">登録キー</span><span class="sxs-lookup"><span data-stu-id="270d8-159">Registration Key</span></span>

<span data-ttu-id="270d8-160">サーバーにクライアント ノードを登録して、構成 ID の代わりに構成名を使用できるように、上の構成で作成された登録キーは、`C:\Program Files\WindowsPowerShell\DscService` にある `RegistrationKeys.txt` という名前のファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="270d8-160">To allow client nodes to register with the server so that they can use configuration names instead of a configuration ID, a registration key which was created by the above configuration is saved in a file named `RegistrationKeys.txt` in `C:\Program Files\WindowsPowerShell\DscService`.</span></span> <span data-ttu-id="270d8-161">登録キーは、クライアントがプル サーバーに初期登録を行うときに共有シークレットとして機能します。</span><span class="sxs-lookup"><span data-stu-id="270d8-161">The registration key functions as a shared secret used during the initial registration by the client with the pull server.</span></span> <span data-ttu-id="270d8-162">登録が正常に完了すると、クライアントは、プル サーバーに一意に認証されるために使う自己署名証明書を生成します。</span><span class="sxs-lookup"><span data-stu-id="270d8-162">The client will generate a self-signed certificate which is used to uniquely authenticate to the pull server once registration is successfully completed.</span></span> <span data-ttu-id="270d8-163">この証明書の拇印がローカルに保存され、プル サーバーの URL に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="270d8-163">The thumbprint of this certificate is stored locally and associated with the URL of the pull server.</span></span>
> <span data-ttu-id="270d8-164">**注**: 登録キーは、PowerShell 4.0 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="270d8-164">**Note**: Registration keys are not supported in PowerShell 4.0.</span></span>

<span data-ttu-id="270d8-165">プル サーバーで認証するようにノードを構成するには、登録キーが、このプル サーバーに登録されるすべてのターゲット ノードのメタ構成に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="270d8-165">In order to configure a node to authenticate with the pull server the registration key needs to be in the metaconfiguration for any target node that will be registering with this pull server.</span></span> <span data-ttu-id="270d8-166">なお、次のメタ構成にある **RegistrationKey** は、ターゲット コンピューターが正常に登録された後に削除され、値 '140a952b-b9d6-406b-b416-e0f759c9c0e4' はプル サーバーの RegistrationKeys.txt ファイルに格納されている値と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="270d8-166">Note that the **RegistrationKey** in the metaconfiguration below is removed after the target machine has successfully registered, and that the value '140a952b-b9d6-406b-b416-e0f759c9c0e4' must match the value stored in the RegistrationKeys.txt file on the pull server.</span></span> <span data-ttu-id="270d8-167">登録キー値を知ると、任意のターゲット コンピューターをプル サーバーに登録できるようになるので、登録キー値は常にセキュリティで保護してください。</span><span class="sxs-lookup"><span data-stu-id="270d8-167">Always treat the registration key value securely, because knowing it allows any target machine to register with the pull server.</span></span>

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

> <span data-ttu-id="270d8-168">**注**: **ReportServerWeb** セクションでは、レポートするデータをプル サーバーに送信できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="270d8-168">**Note**: The **ReportServerWeb** section allows reporting data to be sent to the pull server.</span></span>

<span data-ttu-id="270d8-169">メタ構成ファイルに **ConfigurationID** プロパティがないことは、暗黙的に、そのプル サーバーが V2 バージョンのプル サーバー プロトコルをサポートしていることを示すので、初期登録が必要になります。</span><span class="sxs-lookup"><span data-stu-id="270d8-169">The lack of the **ConfigurationID** property in the metaconfiguration file implicitly means that pull server is supporting the V2 version of the pull server protocol so an initial registration is required.</span></span>
<span data-ttu-id="270d8-170">逆に、**ConfigurationID** が存在することは、V1 バージョンのプル サーバー プロトコルが使用され、登録処理がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="270d8-170">Conversely, the presence of a **ConfigurationID** means that the V1 version of the pull server protocol is used and there is no registration processing.</span></span>

><span data-ttu-id="270d8-171">**注**: プッシュのシナリオでは、現在のリリースにバグが存在するため、プル サーバーに登録されていないノードについても、メタ構成ファイルで ConfigurationID プロパティを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="270d8-171">**Note**: In a PUSH scenario, a bug exists in the current relase that makes it necessary to define a ConfigurationID property in the metaconfiguration file for nodes that have never registered with a pull server.</span></span> <span data-ttu-id="270d8-172">こうすると、V1 プル サーバー プロトコルが強制されるので、登録エラーのメッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="270d8-172">This will force the V1 Pull Server protocol and avoid registration failure messages.</span></span>

## <a name="placing-configurations-and-resources"></a><span data-ttu-id="270d8-173">構成とリソースの配置</span><span class="sxs-lookup"><span data-stu-id="270d8-173">Placing configurations and resources</span></span>

<span data-ttu-id="270d8-174">プル サーバーのセットアップが完了すると、プル サーバーの構成で **ConfigurationPath** プロパティと **ModulePath** プロパティによって定義されているフォルダーは、プルするためにターゲット ノードで使用可能にするモジュールと構成を配置する場所になります。</span><span class="sxs-lookup"><span data-stu-id="270d8-174">After the pull server setup completes, the folders defined by the **ConfigurationPath** and **ModulePath** properties in the pull server configuration are where you will place modules and configurations that will be available for target nodes to pull.</span></span>
<span data-ttu-id="270d8-175">これらのファイルをプル サーバーが正しく処理するためには、特定の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="270d8-175">These files need to be in a specific format in order for the pull server to correctly process them.</span></span>

### <a name="dsc-resource-module-package-format"></a><span data-ttu-id="270d8-176">DSC リソース モジュールのパッケージの形式</span><span class="sxs-lookup"><span data-stu-id="270d8-176">DSC resource module package format</span></span>

<span data-ttu-id="270d8-177">各リソース モジュールは、圧縮し、`{Module Name}_{Module Version}.zip` というパターンで名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="270d8-177">Each resource module needs to be zipped and named according the following pattern `{Module Name}_{Module Version}.zip`.</span></span>
<span data-ttu-id="270d8-178">たとえば、モジュール名が xWebAdminstration で、バージョンが 3.1.2.0 のモジュールでは、'xWebAdministration_3.2.1.0.zip' という名前になります。</span><span class="sxs-lookup"><span data-stu-id="270d8-178">For example, a module named xWebAdminstration with a module version of 3.1.2.0 would be named 'xWebAdministration_3.2.1.0.zip'.</span></span>
<span data-ttu-id="270d8-179">各バージョンのモジュールを 1 つの zip ファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="270d8-179">Each version of a module must be contained in a single zip file.</span></span>
<span data-ttu-id="270d8-180">各 zip ファイルには 1 つのバージョンのリソースのみが含まれるので、WMF 5.0 で追加された、単一のディレクトリに複数のモジュール バージョンを入れるモジュール形式はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="270d8-180">Since there is only a single version of a resource in each zip file the module format added in WMF 5.0 with support for multiple module versions in a single directory is not supported.</span></span>
<span data-ttu-id="270d8-181">このため、プル サーバーで使うための DSC リソース モジュールをパッケージ化する前に、ディレクトリ構造に少しの変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="270d8-181">This means that before packaging up DSC resource modules for use with pull server you will need to make a small change to the directory structure.</span></span>
<span data-ttu-id="270d8-182">WMF 5.0 の DSC リソースを含むモジュールの既定の形式は、'{モジュール フォルダー}\{モジュールのバージョン}\DscResources\{DSC リソース フォルダー}\' です。</span><span class="sxs-lookup"><span data-stu-id="270d8-182">The default format of modules containing DSC resource in WMF 5.0 is '{Module Folder}\{Module Version}\DscResources\{DSC Resource Folder}\'.</span></span>
<span data-ttu-id="270d8-183">プル サーバー用にパッケージ化する前には、単純に **{モジュールのバージョン}** フォルダーを削除して、'{モジュール フォルダー}\DscResources\{DSC リソース フォルダー}\' というパスにします。</span><span class="sxs-lookup"><span data-stu-id="270d8-183">Before packaging up for the pull server simply remove the **{Module version}** folder so the path becomes '{Module Folder}\DscResources\{DSC Resource Folder}\'.</span></span>
<span data-ttu-id="270d8-184">この変更を加えた後、上で説明したようにフォルダーを zip 圧縮し、これらの zip ファイルを **ModulePath** フォルダーに置きます。</span><span class="sxs-lookup"><span data-stu-id="270d8-184">With this change, zip the folder as described above and place these zip files in the **ModulePath** folder.</span></span>

<span data-ttu-id="270d8-185">新しく追加したモジュールのチェックサム ファイルを作成するには、`new-dscchecksum {module zip file}` を使用します。</span><span class="sxs-lookup"><span data-stu-id="270d8-185">Use `new-dscchecksum {module zip file}` to create a checksum file for the newly-added module.</span></span>

### <a name="configuration-mof-format"></a><span data-ttu-id="270d8-186">構成 MOF の形式</span><span class="sxs-lookup"><span data-stu-id="270d8-186">Configuration MOF format</span></span>

<span data-ttu-id="270d8-187">ターゲット ノード上の LCM が構成を検証できるように、構成 MOF ファイルはチェックサム ファイルと組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="270d8-187">A configuration MOF file needs to be paired with a checksum file so that an LCM on a target node can validate the configuration.</span></span>
<span data-ttu-id="270d8-188">チェックサムを作成するには、[New-DSCCheckSum](https://technet.microsoft.com/en-us/library/dn521622.aspx) コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="270d8-188">To create a checksum, call the [New-DSCCheckSum](https://technet.microsoft.com/en-us/library/dn521622.aspx) cmdlet.</span></span>
<span data-ttu-id="270d8-189">このコマンドレットは、構成 MOF が存在するフォルダーが指定された **Path** パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="270d8-189">The cmdlet takes a **Path** parameter that specifies the folder where the configuration MOF is located.</span></span>
<span data-ttu-id="270d8-190">このコマンドレットは、`ConfigurationMOFName.mof.checksum` という名前でチェックサム ファイルを作成します。ここで、`ConfigurationMOFName` は構成 MOF ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="270d8-190">The cmdlet creates a checksum file named `ConfigurationMOFName.mof.checksum`, where `ConfigurationMOFName` is the name of the configuration mof file.</span></span>
<span data-ttu-id="270d8-191">指定のフォルダーに複数の構成 MOF ファイルがある場合は、そのフォルダー内の構成ごとにチェックサムが作成されます。</span><span class="sxs-lookup"><span data-stu-id="270d8-191">If there are more than one configuration MOF files in the specified folder, a checksum is created for each configuration in the folder.</span></span>
<span data-ttu-id="270d8-192">MOF ファイルと、それに関連するチェックサム ファイルは、**ConfigurationPath** フォルダーに配置します。</span><span class="sxs-lookup"><span data-stu-id="270d8-192">Place the MOF files and their associated checksum files in the **ConfigurationPath** folder.</span></span>

><span data-ttu-id="270d8-193">**注**: 何らかの方法で構成 MOF ファイルを変更した場合は、チェックサム ファイルも作成し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="270d8-193">**Note**: If you change the configuration MOF file in any way, you must also recreate the checksum file.</span></span>

### <a name="tooling"></a><span data-ttu-id="270d8-194">ツール</span><span class="sxs-lookup"><span data-stu-id="270d8-194">Tooling</span></span>

<span data-ttu-id="270d8-195">プル サーバーのセットアップ、検証、管理を簡素化するために、次のツールが、xPSDesiredStateConfiguration モジュールの最新バージョンに例として含まれています。</span><span class="sxs-lookup"><span data-stu-id="270d8-195">In order to make setting up, validating and managing the pull server easier, the following tools are included as examples in the latest version of the xPSDesiredStateConfiguration module:</span></span>

1. <span data-ttu-id="270d8-196">プル サーバーに使用する DSC リソース モジュールおよび構成ファイルをパッケージ化するために役立つモジュール。</span><span class="sxs-lookup"><span data-stu-id="270d8-196">A module that will help with packaging DSC resource modules and configuration files for use on the pull server.</span></span> <span data-ttu-id="270d8-197">[PublishModulesAndMofsToPullServer.psm1](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/dev/DSCPullServerSetup/PublishModulesAndMofsToPullServer.psm1)。</span><span class="sxs-lookup"><span data-stu-id="270d8-197">[PublishModulesAndMofsToPullServer.psm1](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/dev/DSCPullServerSetup/PublishModulesAndMofsToPullServer.psm1).</span></span> <span data-ttu-id="270d8-198">次の例です。</span><span class="sxs-lookup"><span data-stu-id="270d8-198">Examples below:</span></span>

    ```powershell
        # Example 1 - Package all versions of given modules installed locally and MOF files are in c:\LocalDepot
         $moduleList = @("xWebAdministration", "xPhp")
         Publish-DSCModuleAndMof -Source C:\LocalDepot -ModuleNameList $moduleList

         # Example 2 - Package modules and mof documents from c:\LocalDepot
         Publish-DSCModuleAndMof -Source C:\LocalDepot -Force
    ```

1. <span data-ttu-id="270d8-199">プル サーバーが正しく構成されていることを検証するスクリプト。</span><span class="sxs-lookup"><span data-stu-id="270d8-199">A script that validates the pull server is configured correctly.</span></span> <span data-ttu-id="270d8-200">[PullServerSetupTests.ps1](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/dev/DSCPullServerSetup/PullServerDeploymentVerificationTest/PullServerSetupTests.ps1)。</span><span class="sxs-lookup"><span data-stu-id="270d8-200">[PullServerSetupTests.ps1](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/dev/DSCPullServerSetup/PullServerDeploymentVerificationTest/PullServerSetupTests.ps1).</span></span>

## <a name="community-solutions-for-pull-service"></a><span data-ttu-id="270d8-201">プル サービスのコミュニティ ソリューション</span><span class="sxs-lookup"><span data-stu-id="270d8-201">Community Solutions for Pull Service</span></span>

<span data-ttu-id="270d8-202">DSC コミュニティは、プル サービス プロトコルを実装するための複数のソリューションを作成しています。</span><span class="sxs-lookup"><span data-stu-id="270d8-202">The DSC community has authored multiple solutions to implement the pull service protocol.</span></span>
<span data-ttu-id="270d8-203">これらはオンプレミス環境向けに、プル サービス機能と、段階的な機能強化でコミュニティに貢献する機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="270d8-203">For on-premises environments these offer pull service capabilities and an opportunity to contribute back to the community with incremental enhancements.</span></span>

- [<span data-ttu-id="270d8-204">Tug</span><span class="sxs-lookup"><span data-stu-id="270d8-204">Tug</span></span>](https://github.com/powershellorg/tug)
- [<span data-ttu-id="270d8-205">DSC-TRÆK</span><span class="sxs-lookup"><span data-stu-id="270d8-205">DSC-TRÆK</span></span>](https://github.com/powershellorg/dsc-traek)

## <a name="pull-client-configuration"></a><span data-ttu-id="270d8-206">プル クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="270d8-206">Pull client configuration</span></span>

<span data-ttu-id="270d8-207">次のトピックでは、プル クライアントのセットアップについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="270d8-207">The following topics describe setting up pull clients in detail:</span></span>

- [<span data-ttu-id="270d8-208">構成 ID を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="270d8-208">Setting up a DSC pull client using a configuration ID</span></span>](pullClientConfigID.md)
- [<span data-ttu-id="270d8-209">構成名を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="270d8-209">Setting up a DSC pull client using configuration names</span></span>](pullClientConfigNames.md)
- [<span data-ttu-id="270d8-210">部分構成</span><span class="sxs-lookup"><span data-stu-id="270d8-210">Partial configurations</span></span>](partialConfigs.md)

## <a name="see-also"></a><span data-ttu-id="270d8-211">関連項目</span><span class="sxs-lookup"><span data-stu-id="270d8-211">See also</span></span>

- [<span data-ttu-id="270d8-212">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="270d8-212">Windows PowerShell Desired State Configuration Overview</span></span>](overview.md)
- [<span data-ttu-id="270d8-213">構成の適用</span><span class="sxs-lookup"><span data-stu-id="270d8-213">Enacting configurations</span></span>](enactingConfigurations.md)
- [<span data-ttu-id="270d8-214">DSC レポート サーバーの使用</span><span class="sxs-lookup"><span data-stu-id="270d8-214">Using a DSC report server</span></span>](reportServer.md)