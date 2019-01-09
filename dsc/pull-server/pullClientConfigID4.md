---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: PowerShell 4.0 では、構成 Id を使用して、プル クライアントの設定します。
ms.openlocfilehash: 9adc767e91ff19d373c122a0d493e7b8703d5476
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402990"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-40"></a><span data-ttu-id="6f544-103">PowerShell 4.0 では、構成 Id を使用して、プル クライアントの設定します。</span><span class="sxs-lookup"><span data-stu-id="6f544-103">Set up a Pull Client using Configuration IDs in PowerShell 4.0</span></span>

><span data-ttu-id="6f544-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="6f544-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f544-105">プル サーバー (Windows Feature *DSC-Service*) は、Windows Server のサポート対象のコンポーネントですが、新機能がオファーされる予定はありません。</span><span class="sxs-lookup"><span data-stu-id="6f544-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="6f544-106">管理対象のクライアントは、(Windows Server のプル サーバー以降の機能が含まれる) [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) または、[こちら](pullserver.md#community-solutions-for-pull-service)に列挙されているコミュニティ ソリューションのいずれかに切り替えを開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6f544-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="6f544-107">プル クライアントをセットアップする前に、プル サーバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f544-107">Before setting up a pull client, you should set up a pull server.</span></span> <span data-ttu-id="6f544-108">この順序は必要ありませんが、トラブルシューティングに役立つし、登録が成功したことを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6f544-108">Though this order is not required, it helps with troubleshooting, and helps you ensure that the registration was successful.</span></span> <span data-ttu-id="6f544-109">プル サーバーを設定するには、次のガイドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6f544-109">To set up a pull server, you can use the following guides:</span></span>

- [<span data-ttu-id="6f544-110">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="6f544-110">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="6f544-111">DSC HTTP プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="6f544-111">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="6f544-112">各ターゲット ノードは、構成、リソースをダウンロードしてもその状態を報告を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6f544-112">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="6f544-113">以下のセクションでは、SMB 共有または HTTP プル サーバーの DSC プル クライアントを構成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="6f544-113">The sections below show you how to configure a pull client with an SMB share or HTTP DSC Pull Server.</span></span> <span data-ttu-id="6f544-114">ノードの LCM が更新されるは、割り当てられた構成のダウンロードを構成した場所に連絡されます。</span><span class="sxs-lookup"><span data-stu-id="6f544-114">When the Node's LCM refreshes, it will reach out to the configured location to download any assigned configurations.</span></span> <span data-ttu-id="6f544-115">ノードで必要なリソースが存在しない場合に自動的に構成されている場所からダウンロードには。</span><span class="sxs-lookup"><span data-stu-id="6f544-115">If any required resources do not exist on the Node, it will automatically download them from the configured location.</span></span> <span data-ttu-id="6f544-116">ノードが構成されている場合、[レポート サーバー](reportServer.md)操作の状態は報告します。</span><span class="sxs-lookup"><span data-stu-id="6f544-116">If the Node is configured with a [Report Server](reportServer.md), it will then report the status of the operation.</span></span>

## <a name="configure-the-pull-client-lcm"></a><span data-ttu-id="6f544-117">プル クライアントの LCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="6f544-117">Configure the pull client LCM</span></span>

<span data-ttu-id="6f544-118">次の例のいずれかを実行するという名前の新しい出力フォルダーを作成**PullClientConfigID**と、メタ構成 MOF ファイルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="6f544-118">Executing any of the examples below creates a new output folder named **PullClientConfigID** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="6f544-119">この場合、メタ構成 MOF ファイルの名前は `localhost.meta.mof` になります。</span><span class="sxs-lookup"><span data-stu-id="6f544-119">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="6f544-120">構成を適用するには、**Path** をメタ構成 MOF ファイルの場所に設定して **Set-DscLocalConfigurationManager** コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6f544-120">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="6f544-121">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6f544-121">For example:</span></span>

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a><span data-ttu-id="6f544-122">構成 ID</span><span class="sxs-lookup"><span data-stu-id="6f544-122">Configuration ID</span></span>

<span data-ttu-id="6f544-123">以下の一連の例、 **ConfigurationID**を LCM のプロパティを**Guid**を以前に作成したこの目的のためです。</span><span class="sxs-lookup"><span data-stu-id="6f544-123">The examples below set the **ConfigurationID** property of the LCM to a **Guid** that had been previously created for this purpose.</span></span> <span data-ttu-id="6f544-124">**ConfigurationID** は、LCM がプル サーバーで適切な構成を検索する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="6f544-124">The **ConfigurationID** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="6f544-125">プル サーバー上の構成 MOF ファイルは、`ConfigurationID.mof` という名前にする必要があります。ここで、*ConfigurationID* はターゲット ノードの LCM の **ConfigurationID** プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="6f544-125">The configuration MOF file on the pull server must be named `ConfigurationID.mof`, where *ConfigurationID* is the value of the **ConfigurationID** property of the target node's LCM.</span></span> <span data-ttu-id="6f544-126">詳細については、次を参照してください。[構成プル サーバー (v4/v5) を発行](publishConfigs.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f544-126">For more information, see [Publish Configurations to a Pull Server (v4/v5)](publishConfigs.md).</span></span>

<span data-ttu-id="6f544-127">乱数を作成することができます**Guid**次の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f544-127">You can create a random **Guid** using the example below.</span></span>

```powershell
[System.Guid]::NewGuid()
```

## <a name="set-up-a-pull-client-to-download-configurations"></a><span data-ttu-id="6f544-128">プル クライアントの設定の構成をダウンロードするには</span><span class="sxs-lookup"><span data-stu-id="6f544-128">Set up a Pull Client to download Configurations</span></span>

<span data-ttu-id="6f544-129">各クライアントを構成する必要があります**プル**モードとその構成が格納されている、プル サーバーの url を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f544-129">Each client must be configured in **Pull** mode and given the pull server url where its configuration is stored.</span></span> <span data-ttu-id="6f544-130">これを行うには、必要な情報を備えるようにローカル構成マネージャー (LCM) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f544-130">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="6f544-131">LCM を構成すると、特別な種類の構成を作成する、 **LocalConfigurationManager**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="6f544-131">To configure the LCM, you create a special type of configuration, with a **LocalConfigurationManager** block.</span></span> <span data-ttu-id="6f544-132">LCM の構成の詳細については、「[ローカル構成マネージャーの構成](../managing-nodes/metaConfig4.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6f544-132">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig4.md).</span></span>

## <a name="http-dsc-pull-server"></a><span data-ttu-id="6f544-133">HTTP の DSC プル サーバー</span><span class="sxs-lookup"><span data-stu-id="6f544-133">HTTP DSC Pull Server</span></span>

<span data-ttu-id="6f544-134">プル サーバーは、web サービスとしてセットアップは、設定、 **DownloadManagerName**に**WebDownloadManager**します。</span><span class="sxs-lookup"><span data-stu-id="6f544-134">If the pull server is set up as a web service, you set the **DownloadManagerName** to **WebDownloadManager**.</span></span> <span data-ttu-id="6f544-135">**WebDownloadManager**指定する必要があります、 **ServerUrl**を**DownloadManagerCustomData**キー。</span><span class="sxs-lookup"><span data-stu-id="6f544-135">The **WebDownloadManager** requires that you specify a **ServerUrl** to the **DownloadManagerCustomData** key.</span></span> <span data-ttu-id="6f544-136">値を指定することもできます。 **AllowUnsecureConnection**次の例のようにします。</span><span class="sxs-lookup"><span data-stu-id="6f544-136">You can also specify a value for **AllowUnsecureConnection**, as in the example below.</span></span> <span data-ttu-id="6f544-137">次のスクリプトは、"PullServer" という名前のサーバーから構成をプルするように LCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="6f544-137">The following script configures the LCM to pull configurations from a server named "PullServer".</span></span>

```powershell
Configuration PullClientConfigId
{
    LocalConfigurationManager
    {
        ConfigurationID = "1C707B86-EF8E-4C29-B7C1-34DA2190AE24";
        RefreshMode = "PULL";
        DownloadManagerName = "WebDownloadManager";
        RebootNodeIfNeeded = $true;
        RefreshFrequencyMins = 30;
        ConfigurationModeFrequencyMins = 30;
        ConfigurationMode = "ApplyAndAutoCorrect";
        DownloadManagerCustomData = @{ServerUrl = "http://PullServer:8080/PSDSCPullServer/PSDSCPullServer.svc"; AllowUnsecureConnection = “TRUE”}
    }
}
PullClientConfigId -Output "."
```

## <a name="smb-share"></a><span data-ttu-id="6f544-138">SMB 共有</span><span class="sxs-lookup"><span data-stu-id="6f544-138">SMB Share</span></span>

<span data-ttu-id="6f544-139">プル サーバーは、web サービスではなく、SMB ファイル共有としてセットアップは、設定、 **DownloadManagerName**に**DscFileDownloadManager**なく**WebDownLoadManager**.</span><span class="sxs-lookup"><span data-stu-id="6f544-139">If the pull server is set up as an SMB file share, rather than a web service, you set the **DownloadManagerName** to **DscFileDownloadManager** rather than the **WebDownLoadManager**.</span></span> <span data-ttu-id="6f544-140">**DscFileDownloadManager**指定する必要があります、 **SourcePath**プロパティ、 **DownloadManagerCustomData**します。</span><span class="sxs-lookup"><span data-stu-id="6f544-140">The **DscFileDownloadManager** requires that you specify a **SourcePath** property in the **DownloadManagerCustomData**.</span></span> <span data-ttu-id="6f544-141">次のスクリプトは、"CONTOSO-SERVER" という名前のサーバーの "SmbDscShare" という名前の SMB 共有から構成をプルするように LCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="6f544-141">The following script configures the LCM to pull configurations from an SMB share named "SmbDscShare" on a server named "CONTOSO-SERVER".</span></span>

```powershell
Configuration PullClientConfigId
{
    LocalConfigurationManager
    {
        ConfigurationID = "1C707B86-EF8E-4C29-B7C1-34DA2190AE24";
        RefreshMode = "PULL";
        DownloadManagerName = "DscFileDownloadManager";
        RebootNodeIfNeeded = $true;
        RefreshFrequencyMins = 30;
        ConfigurationModeFrequencyMins = 30;
        ConfigurationMode = "ApplyAndAutoCorrect";
        DownloadManagerCustomData = @{ServerUrl = "\\CONTOSO-SERVER\SmbDscShare"}
    }
}
PullClientConfigId -Output "."
```

## <a name="next-steps"></a><span data-ttu-id="6f544-142">次の手順</span><span class="sxs-lookup"><span data-stu-id="6f544-142">Next Steps</span></span>

<span data-ttu-id="6f544-143">プル クライアントを構成すると、次の手順を実行するのに、次のガイドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6f544-143">Once the pull client has been configured, you can use the following guides to perform the next steps:</span></span>

- [<span data-ttu-id="6f544-144">プル サーバーに構成を発行する (v4/v5)</span><span class="sxs-lookup"><span data-stu-id="6f544-144">Publish Configurations to a Pull Server (v4/v5)</span></span>](publishConfigs.md)
- [<span data-ttu-id="6f544-145">リソースのパッケージ化とプル サーバーへのアップロード (v4)</span><span class="sxs-lookup"><span data-stu-id="6f544-145">Package and Upload Resources to a Pull Server (v4)</span></span>](package-upload-resources.md)

## <a name="see-also"></a><span data-ttu-id="6f544-146">参照</span><span class="sxs-lookup"><span data-stu-id="6f544-146">See Also</span></span>

- [<span data-ttu-id="6f544-147">DSC web プル サーバーをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="6f544-147">Set up a DSC web pull server</span></span>](pullServer.md)
- [<span data-ttu-id="6f544-148">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="6f544-148">Set up a DSC SMB pull server</span></span>](pullServerSMB.md)
