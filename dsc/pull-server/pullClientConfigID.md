---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: PowerShell 5.0 以降で、構成 Id を使用して、プル クライアントの設定します。
ms.openlocfilehash: 8d8cf478f9127e1b7005d1b9e832e84b11612c9c
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402782"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-50-and-later"></a><span data-ttu-id="01947-103">PowerShell 5.0 以降で、構成 Id を使用して、プル クライアントの設定します。</span><span class="sxs-lookup"><span data-stu-id="01947-103">Set up a Pull Client using Configuration IDs in PowerShell 5.0 and later</span></span>

> <span data-ttu-id="01947-104">適用先:Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="01947-104">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01947-105">プル サーバー (Windows Feature *DSC-Service*) は、Windows Server のサポート対象のコンポーネントですが、新機能がオファーされる予定はありません。</span><span class="sxs-lookup"><span data-stu-id="01947-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="01947-106">管理対象のクライアントは、(Windows Server のプル サーバー以降の機能が含まれる) [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) または、[こちら](pullserver.md#community-solutions-for-pull-service)に列挙されているコミュニティ ソリューションのいずれかに切り替えを開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="01947-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="01947-107">プル クライアントをセットアップする前に、プル サーバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01947-107">Before setting up a pull client, you should set up a pull server.</span></span> <span data-ttu-id="01947-108">この順序は必要ありませんが、トラブルシューティングに役立つし、登録が成功したことを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="01947-108">Though this order is not required, it helps with troubleshooting, and helps you ensure that the registration was successful.</span></span> <span data-ttu-id="01947-109">プル サーバーを設定するには、次のガイドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="01947-109">To set up a pull server, you can use the following guides:</span></span>

- [<span data-ttu-id="01947-110">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="01947-110">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="01947-111">DSC HTTP プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="01947-111">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="01947-112">各ターゲット ノードは、構成、リソースをダウンロードしてもその状態を報告を構成できます。</span><span class="sxs-lookup"><span data-stu-id="01947-112">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="01947-113">以下のセクションでは、SMB 共有または HTTP プル サーバーの DSC プル クライアントを構成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="01947-113">The sections below show you how to configure a pull client with an SMB share or HTTP DSC Pull Server.</span></span> <span data-ttu-id="01947-114">ノードの LCM が更新されるは、割り当てられた構成のダウンロードを構成した場所に連絡されます。</span><span class="sxs-lookup"><span data-stu-id="01947-114">When the Node's LCM refreshes, it will reach out to the configured location to download any assigned configurations.</span></span> <span data-ttu-id="01947-115">ノードで必要なリソースが存在しない場合に自動的に構成されている場所からダウンロードには。</span><span class="sxs-lookup"><span data-stu-id="01947-115">If any required resources do not exist on the Node, it will automatically download them from the configured location.</span></span> <span data-ttu-id="01947-116">ノードが構成されている場合、[レポート サーバー](reportServer.md)操作の状態は報告します。</span><span class="sxs-lookup"><span data-stu-id="01947-116">If the Node is configured with a [Report Server](reportServer.md), it will then report the status of the operation.</span></span>

> <span data-ttu-id="01947-117">**注**:このトピックでは、PowerShell 5.0 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="01947-117">**Note**: This topic applies to PowerShell 5.0.</span></span> <span data-ttu-id="01947-118">PowerShell 4.0 でのプル クライアントのセットアップについては、「[PowerShell 4.0 での構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID4.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="01947-118">For information on setting up a pull client in PowerShell 4.0, see [Setting up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md)</span></span>

## <a name="configure-the-pull-client-lcm"></a><span data-ttu-id="01947-119">プル クライアントの LCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="01947-119">Configure the pull client LCM</span></span>

<span data-ttu-id="01947-120">次の例のいずれかを実行するという名前の新しい出力フォルダーを作成**PullClientConfigID**と、メタ構成 MOF ファイルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="01947-120">Executing any of the examples below creates a new output folder named **PullClientConfigID** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="01947-121">この場合、メタ構成 MOF ファイルの名前は `localhost.meta.mof` になります。</span><span class="sxs-lookup"><span data-stu-id="01947-121">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="01947-122">構成を適用するには、**Path** をメタ構成 MOF ファイルの場所に設定して **Set-DscLocalConfigurationManager** コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="01947-122">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="01947-123">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="01947-123">For example:</span></span>

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a><span data-ttu-id="01947-124">構成 ID</span><span class="sxs-lookup"><span data-stu-id="01947-124">Configuration ID</span></span>

<span data-ttu-id="01947-125">セットの下の例、 **ConfigurationID**を LCM のプロパティを**Guid**を以前に作成したこの目的のためです。</span><span class="sxs-lookup"><span data-stu-id="01947-125">The examples below sets the **ConfigurationID** property of the LCM to a **Guid** that had been previously created for this purpose.</span></span> <span data-ttu-id="01947-126">**ConfigurationID** は、LCM がプル サーバーで適切な構成を検索する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="01947-126">The **ConfigurationID** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="01947-127">プル サーバー上の構成 MOF ファイルは、`ConfigurationID.mof` という名前にする必要があります。ここで、*ConfigurationID* はターゲット ノードの LCM の **ConfigurationID** プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="01947-127">The configuration MOF file on the pull server must be named `ConfigurationID.mof`, where *ConfigurationID* is the value of the **ConfigurationID** property of the target node's LCM.</span></span> <span data-ttu-id="01947-128">詳細については、次を参照してください。[構成プル サーバー (v4/v5) を発行](publishConfigs.md)します。</span><span class="sxs-lookup"><span data-stu-id="01947-128">For more information see [Publish Configurations to a Pull Server (v4/v5)](publishConfigs.md).</span></span>

<span data-ttu-id="01947-129">乱数を作成することができます**Guid**またはを使用して、次の例を使用して、 [New-guid](/powershell/module/microsoft.powershell.utility/new-guid)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="01947-129">You can create a random **Guid** using the example below, or by using the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) cmdlet.</span></span>

```powershell
[System.Guid]::NewGuid()
```

<span data-ttu-id="01947-130">使用しての詳細については**Guid** 、環境内で、次を参照してください。 [Guid の計画](/powershell/dsc/secureserver#guids)します。</span><span class="sxs-lookup"><span data-stu-id="01947-130">For more information about using **Guids** in your environment, see [Plan for Guids](/powershell/dsc/secureserver#guids).</span></span>

## <a name="set-up-a-pull-client-to-download-configurations"></a><span data-ttu-id="01947-131">プル クライアントの設定の構成をダウンロードするには</span><span class="sxs-lookup"><span data-stu-id="01947-131">Set up a Pull Client to download Configurations</span></span>

<span data-ttu-id="01947-132">各クライアントを構成する必要があります**プル**モードとその構成が格納されている、プル サーバーの url を指定します。</span><span class="sxs-lookup"><span data-stu-id="01947-132">Each client must be configured in **Pull** mode and given the pull server url where its configuration is stored.</span></span> <span data-ttu-id="01947-133">これを行うには、必要な情報を備えるようにローカル構成マネージャー (LCM) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01947-133">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="01947-134">LCM を構成するには、**DSCLocalConfigurationManager** 属性で修飾された特別な種類の構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="01947-134">To configure the LCM, you create a special type of configuration, decorated with the **DSCLocalConfigurationManager** attribute.</span></span> <span data-ttu-id="01947-135">LCM の構成の詳細については、「[ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="01947-135">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md).</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="01947-136">HTTP の DSC プル サーバー</span><span class="sxs-lookup"><span data-stu-id="01947-136">HTTP DSC Pull Server</span></span>

<span data-ttu-id="01947-137">次のスクリプトは、"CONTOSO-PullSrv" という名前のサーバーから構成をプルするように LCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="01947-137">The following script configures the LCM to pull configurations from a server named "CONTOSO-PullSrv".</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }
    }
}
PullClientConfigID
```

<span data-ttu-id="01947-138">このスクリプトでは、**ConfigurationRepositoryWeb** ブロックでプル サーバーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="01947-138">In the script, the **ConfigurationRepositoryWeb** block defines the pull server.</span></span> <span data-ttu-id="01947-139">**ServerUrl** DSC プルの url を指定します</span><span class="sxs-lookup"><span data-stu-id="01947-139">The **ServerUrl** specifies the url of the DSC Pull</span></span>

### <a name="smb-share"></a><span data-ttu-id="01947-140">SMB 共有</span><span class="sxs-lookup"><span data-stu-id="01947-140">SMB Share</span></span>

<span data-ttu-id="01947-141">次のスクリプトは SMB 共有から構成をプルする LCM を構成します`\\SMBPullServer\Pull`します。</span><span class="sxs-lookup"><span data-stu-id="01947-141">The following script configures the LCM to pull configurations from the SMB Share `\\SMBPullServer\Pull`.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryShare SMBPullServer
        {
            SourcePath = '\\SMBPullServer\Pull'
        }
    }
}
PullClientConfigID
```

<span data-ttu-id="01947-142">スクリプトでは、 **ConfigurationRepositoryShare**ブロックは、この場合は、SMB 共有だけであるプル サーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="01947-142">In the script, the **ConfigurationRepositoryShare** block defines the pull server, which in this case, is just an SMB share.</span></span>

## <a name="set-up-a-pull-client-to-download-resources"></a><span data-ttu-id="01947-143">プル クライアントのセットアップ リソースをダウンロードするには</span><span class="sxs-lookup"><span data-stu-id="01947-143">Set up a Pull Client to download Resources</span></span>

<span data-ttu-id="01947-144">のみを指定する場合、 **ConfigurationRepositoryWeb**または**ConfigurationRepositoryShare** (前の例では) のように LCM 構成でブロック、プル クライアントは、同じリソースをプルします。場所がその構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="01947-144">If you specify only the **ConfigurationRepositoryWeb** or **ConfigurationRepositoryShare** block in your LCM configuration (as in the previous examples), the pull client will pull resources from the same location it retrieves its configurations.</span></span> <span data-ttu-id="01947-145">リソースの別の場所を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="01947-145">You can also specify separate locations for resources.</span></span> <span data-ttu-id="01947-146">別のサーバーとして、リソースの場所を指定するには、使用、 **ResourceRepositoryWeb**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="01947-146">To specify a resource location as a separate server, use the **ResourceRepositoryWeb** block.</span></span> <span data-ttu-id="01947-147">SMB 共有として、リソースの場所を指定するには、使用、 **ResourceRepositoryShare**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="01947-147">To specify a resource location as an SMB share, use the **ResourceRepositoryShare** block.</span></span>

> [!NOTE]
> <span data-ttu-id="01947-148">組み合わせることができます**ConfigurationRepositoryWeb**で**ResourceRepositoryShare**または**ConfigurationRepositoryShare**で**ResourceRepositoryWeb**.</span><span class="sxs-lookup"><span data-stu-id="01947-148">You can combine **ConfigurationRepositoryWeb** with **ResourceRepositoryShare** or **ConfigurationRepositoryShare** with **ResourceRepositoryWeb**.</span></span> <span data-ttu-id="01947-149">この例は、以下は表示されません。</span><span class="sxs-lookup"><span data-stu-id="01947-149">Examples of this are not shown below.</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="01947-150">HTTP の DSC プル サーバー</span><span class="sxs-lookup"><span data-stu-id="01947-150">HTTP DSC Pull Server</span></span>

<span data-ttu-id="01947-151">次のメタ構成から構成を取得するプル クライアント**Contoso-pullsrv**とそのリソースから**Contoso-resourcesrv**します。</span><span class="sxs-lookup"><span data-stu-id="01947-151">The following metaconfiguration configures a pull client to get its configurations from **CONTOSO-PullSrv** and its resources from **CONTOSO-ResourceSrv**.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }

        ResourceRepositoryWeb CONTOSO-ResourceSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

### <a name="smb-share"></a><span data-ttu-id="01947-152">SMB 共有</span><span class="sxs-lookup"><span data-stu-id="01947-152">SMB Share</span></span>

<span data-ttu-id="01947-153">次の例では、SMB 共有から構成をプルするクライアントを設定するメタ構成を`\\SMBPullServer\Configurations`、および SMB 共有からリソース`\\SMBPullServer\Resources`します。</span><span class="sxs-lookup"><span data-stu-id="01947-153">The following example shows a metaconfiguration that sets up a client to pull configurations from the SMB share `\\SMBPullServer\Configurations`, and resources from the SMB share `\\SMBPullServer\Resources`.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryShare SMBPullServer
        {
            SourcePath = '\\SMBPullServer\Configurations'
        }

        ResourceRepositoryShare SMBResourceServer
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigID
```

#### <a name="automatically-download-resources-in-push-mode"></a><span data-ttu-id="01947-154">プッシュ モードでリソースを自動的にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="01947-154">Automatically download Resources in Push Mode</span></span>

<span data-ttu-id="01947-155">PowerShell 5.0 以降では、プル クライアントできますからモジュールをダウンロード、SMB 共有が構成されている場合でも**プッシュ**モード。</span><span class="sxs-lookup"><span data-stu-id="01947-155">Beginning in PowerShell 5.0, your pull clients can download modules from an SMB share, even when they are configured for **Push** mode.</span></span> <span data-ttu-id="01947-156">これは、プル サーバーをセットアップしないシナリオで特に便利です。</span><span class="sxs-lookup"><span data-stu-id="01947-156">This is especially useful in scenarios where you do not want to set up a Pull Server.</span></span> <span data-ttu-id="01947-157">**ResourceRepositoryShare**ブロックを指定することがなく使用できる、 **ConfigurationRepositoryShare**します。</span><span class="sxs-lookup"><span data-stu-id="01947-157">The **ResourceRepositoryShare** block can be used without specifying a **ConfigurationRepositoryShare**.</span></span> <span data-ttu-id="01947-158">次の例では、SMB 共有からプル リソースへのクライアントを設定するメタ構成を`\\SMBPullServer\Resources`します。</span><span class="sxs-lookup"><span data-stu-id="01947-158">The following example shows a metaconfiguration that sets up a client to pull resources from an SMB Share `\\SMBPullServer\Resources`.</span></span> <span data-ttu-id="01947-159">とき**PUSHED**構成では、そのは自動的にダウンロード必要なリソースをすべて指定された共有から。</span><span class="sxs-lookup"><span data-stu-id="01947-159">When the Node is **PUSHED** a configuration, it will automatically download any required resources, from the share specified.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Push'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
        }

        ResourceRepositoryShare SMBResourceServer
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigID
```

## <a name="set-up-a-pull-client-to-report-status"></a><span data-ttu-id="01947-160">レポートの状態をプル クライアントをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="01947-160">Set up a Pull Client to report status</span></span>

<span data-ttu-id="01947-161">既定では、ノードはレポートを構成プル サーバーに送信するはしません。</span><span class="sxs-lookup"><span data-stu-id="01947-161">By default, Nodes will not send reports to a configured Pull Server.</span></span> <span data-ttu-id="01947-162">構成、リソース、およびレポートについて単一のプル サーバーを使うことができますが、レポートをセットアップするために **ReportRepositoryWeb** ブロックを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01947-162">You can use a single pull server for configurations, resources, and reporting, but you have to create a **ReportRepositoryWeb** block to set up reporting.</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="01947-163">HTTP の DSC プル サーバー</span><span class="sxs-lookup"><span data-stu-id="01947-163">HTTP DSC Pull Server</span></span>

<span data-ttu-id="01947-164">次の例は、単一のプル サーバーに対して構成とリソースをプルし、レポート データを送信するようにクライアントを設定するメタ構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="01947-164">The following example shows a metaconfiguration that sets up a client to pull configurations and resources, and send reporting data, to a single pull server.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
        }

        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

<span data-ttu-id="01947-165">レポート サーバーを指定するには、**ReportRepositoryWeb** ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="01947-165">To specify a report server, you use a **ReportRepositoryWeb** block.</span></span> <span data-ttu-id="01947-166">レポート サーバーを SMB サーバーにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="01947-166">A report server cannot be an SMB server.</span></span>
<span data-ttu-id="01947-167">次のメタ構成は、**CONTOSO-PullSrv** から構成を取得し、**CONTOSO-ResourceSrv** からリソースを取得し、**CONTOSO-ReportSrv** に状態レポートを送信するように、プル クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="01947-167">The following metaconfiguration configures a pull client to get its configurations from **CONTOSO-PullSrv** and its resources from **CONTOSO-ResourceSrv**, and to send status reports to **CONTOSO-ReportSrv**:</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigID
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            ConfigurationID = '1d545e3b-60c3-47a0-bf65-5afc05182fd0'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'

        }

        ResourceRepositoryWeb CONTOSO-ResourceSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }

        ReportServerWeb CONTOSO-ReportSrv
        {
            ServerURL = 'https://CONTOSO-REsourceSrv:8080/PSDSCPullServer.svc'
        }
    }
}
PullClientConfigID
```

### <a name="smb-share"></a><span data-ttu-id="01947-168">SMB 共有</span><span class="sxs-lookup"><span data-stu-id="01947-168">SMB Share</span></span>

<span data-ttu-id="01947-169">レポート サーバーは、SMB 共有にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="01947-169">A report server cannot be an SMB share.</span></span>

## <a name="next-steps"></a><span data-ttu-id="01947-170">次の手順</span><span class="sxs-lookup"><span data-stu-id="01947-170">Next Steps</span></span>

<span data-ttu-id="01947-171">プル クライアントを構成すると、次の手順を実行するのに、次のガイドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="01947-171">Once the pull client has been configured, you can use the following guides to perform the next steps:</span></span>

- [<span data-ttu-id="01947-172">プル サーバーに構成を発行する (v4/v5)</span><span class="sxs-lookup"><span data-stu-id="01947-172">Publish Configurations to a Pull Server (v4/v5)</span></span>](publishConfigs.md)
- [<span data-ttu-id="01947-173">リソースのパッケージ化とプル サーバーへのアップロード (v4)</span><span class="sxs-lookup"><span data-stu-id="01947-173">Package and Upload Resources to a Pull Server (v4)</span></span>](package-upload-resources.md)

## <a name="see-also"></a><span data-ttu-id="01947-174">参照</span><span class="sxs-lookup"><span data-stu-id="01947-174">See Also</span></span>

* [<span data-ttu-id="01947-175">構成名を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="01947-175">Setting up a pull client with configuration names</span></span>](pullClientConfigNames.md)
