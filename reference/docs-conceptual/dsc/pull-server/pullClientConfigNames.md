---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: PowerShell 5.0 以降での構成名を使用したプル クライアントのセットアップ
description: この記事では、PowerShell 5.0 以降で構成名を使用してプル クライアントをセットアップする方法について説明します
ms.openlocfilehash: db2b08605dd8bc7e48d9d5153861ce9b36118e21
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644920"
---
# <a name="set-up-a-pull-client-using-configuration-names-in-powershell-50-and-later"></a><span data-ttu-id="2f29f-104">PowerShell 5.0 以降での構成名を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="2f29f-104">Set up a Pull Client using Configuration Names in PowerShell 5.0 and later</span></span>

> <span data-ttu-id="2f29f-105">適用先:Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="2f29f-105">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f29f-106">プル サーバー (Windows Feature *DSC-Service* ) は、Windows Server のサポート対象のコンポーネントですが、新機能がオファーされる予定はありません。</span><span class="sxs-lookup"><span data-stu-id="2f29f-106">The Pull Server (Windows Feature *DSC-Service* ) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="2f29f-107">管理対象のクライアントは、(Windows Server のプル サーバー以降の機能が含まれる) [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) または、[こちら](pullserver.md#community-solutions-for-pull-service)に列挙されているコミュニティ ソリューションのいずれかに切り替えを開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2f29f-107">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="2f29f-108">プル クライアントをセットアップする前に、プル サーバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f29f-108">Before setting up a pull client, you should set up a pull server.</span></span> <span data-ttu-id="2f29f-109">この順序は必須ではありませんが、トラブルシューティングに役立ち、登録を確実に成功させるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2f29f-109">Though this order is not required, it helps with troubleshooting, and helps you ensure that the registration was successful.</span></span> <span data-ttu-id="2f29f-110">プル サーバーをセットアップするには、次のガイドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f29f-110">To set up a pull server, you can use the following guides:</span></span>

- [<span data-ttu-id="2f29f-111">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="2f29f-111">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="2f29f-112">DSC HTTP プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="2f29f-112">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="2f29f-113">各ターゲット ノードは、構成やリソースをダウンロードし、さらにその状態を報告するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="2f29f-113">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="2f29f-114">以下のセクションでは、SMB 共有または HTTP DSC プル サーバーを使用してプル クライアントを構成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="2f29f-114">The sections below show you how to configure a pull client with an SMB share or HTTP DSC Pull Server.</span></span> <span data-ttu-id="2f29f-115">ノードの LCM が更新されると、構成済みの場所にアクセスして、割り当てられたすべての構成がダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="2f29f-115">When the Node's LCM refreshes, it will reach out to the configured location to download any assigned configurations.</span></span> <span data-ttu-id="2f29f-116">ノードに必要なリソースが存在しない場合、構成済みの場所から自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="2f29f-116">If any required resources do not exist on the Node, it will automatically download them from the configured location.</span></span> <span data-ttu-id="2f29f-117">ノードに[レポート サーバー](reportServer.md)が構成されている場合、操作の状態が報告されます。</span><span class="sxs-lookup"><span data-stu-id="2f29f-117">If the Node is configured with a [Report Server](reportServer.md), it will then report the status of the operation.</span></span>

> [!NOTE]
> <span data-ttu-id="2f29f-118">このトピックは、PowerShell 5.0 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2f29f-118">This topic applies to PowerShell 5.0.</span></span> <span data-ttu-id="2f29f-119">PowerShell 4.0 でのプル クライアントのセットアップについては、「[PowerShell 4.0 での構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID4.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2f29f-119">For information on setting up a pull client in PowerShell 4.0, see [Set up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md)</span></span>

## <a name="configure-the-pull-client-lcm"></a><span data-ttu-id="2f29f-120">プル クライアント LCM を構成する</span><span class="sxs-lookup"><span data-stu-id="2f29f-120">Configure the pull client LCM</span></span>

<span data-ttu-id="2f29f-121">以下のいずれかの例を実行すると、 **PullClientConfigName** という名前の新しい出力フォルダーが作成され、そこにメタ構成 MOF ファイルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="2f29f-121">Executing any of the examples below creates a new output folder named **PullClientConfigName** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="2f29f-122">この場合、メタ構成 MOF ファイルの名前は `localhost.meta.mof` になります。</span><span class="sxs-lookup"><span data-stu-id="2f29f-122">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="2f29f-123">構成を適用するには、 **Path** をメタ構成 MOF ファイルの場所に設定して **Set-DscLocalConfigurationManager** コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2f29f-123">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="2f29f-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2f29f-124">For example:</span></span>

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigName –Verbose.
```

## <a name="configuration-name"></a><span data-ttu-id="2f29f-125">構成名</span><span class="sxs-lookup"><span data-stu-id="2f29f-125">Configuration Name</span></span>

<span data-ttu-id="2f29f-126">下の例では、この目的で作成され、前にコンパイルしてある Configuration の名前に LCM の **ConfigurationName** プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="2f29f-126">The examples below sets the **ConfigurationName** property of the LCM to the name of a previously compiled Configuration, created for this purpose.</span></span> <span data-ttu-id="2f29f-127">**ConfigurationName** は、LCM がプル サーバーで適切な構成を検索する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="2f29f-127">The **ConfigurationName** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="2f29f-128">プル サーバーの構成 MOF ファイルの名前は `<ConfigurationName>.mof` にする必要があります。今回は "ClientConfig.mof" です。</span><span class="sxs-lookup"><span data-stu-id="2f29f-128">The configuration MOF file on the pull server must be named `<ConfigurationName>.mof`, in this case, "ClientConfig.mof".</span></span> <span data-ttu-id="2f29f-129">詳細については、[プル サーバーへの構成の発行 (v4/v5)](publishConfigs.md) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f29f-129">For more information, see [Publish Configurations to a Pull Server (v4/v5)](publishConfigs.md).</span></span>

## <a name="set-up-a-pull-client-to-download-configurations"></a><span data-ttu-id="2f29f-130">構成をダウンロードするようにプル クライアントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="2f29f-130">Set up a Pull Client to download Configurations</span></span>

<span data-ttu-id="2f29f-131">各クライアントを **プル** モードで構成し、その構成が格納されているプル サーバーの url を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f29f-131">Each client must be configured in **Pull** mode and given the pull server url where its configuration is stored.</span></span> <span data-ttu-id="2f29f-132">これを行うには、必要な情報を備えるようにローカル構成マネージャー (LCM) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f29f-132">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="2f29f-133">LCM を構成するには、 **DSCLocalConfigurationManager** 属性で修飾された特別な種類の構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="2f29f-133">To configure the LCM, you create a special type of configuration, decorated with the **DSCLocalConfigurationManager** attribute.</span></span> <span data-ttu-id="2f29f-134">LCM の構成の詳細については、「[ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2f29f-134">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md).</span></span>

<span data-ttu-id="2f29f-135">次のスクリプトは、"CONTOSO-PullSrv" という名前のサーバーから構成をプルするように LCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="2f29f-135">The following script configures the LCM to pull configurations from a server named "CONTOSO-PullSrv".</span></span>

- <span data-ttu-id="2f29f-136">このスクリプトでは、 **ConfigurationRepositoryWeb** ブロックでプル サーバーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="2f29f-136">In the script, the **ConfigurationRepositoryWeb** block defines the pull server.</span></span> <span data-ttu-id="2f29f-137">**ServerURL** プロパティには、プル サーバー用のエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="2f29f-137">The **ServerURL** property specifies the endpoint for the pull server.</span></span>

- <span data-ttu-id="2f29f-138">**RegistrationKey** プロパティは、プル サーバーのすべてのクライアント ノードとそのプル サーバーとの間で共有されるキーです。</span><span class="sxs-lookup"><span data-stu-id="2f29f-138">The **RegistrationKey** property is a shared key between all client nodes for a pull server and that pull server.</span></span> <span data-ttu-id="2f29f-139">同じ値がプル サーバー上のファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="2f29f-139">The same value is stored in a file on the pull server.</span></span><span data-ttu-id="2f29f-140"> > [!NOTE] > 登録キーは、 **Web** プル サーバーでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="2f29f-140"> > [!NOTE] > Registration keys work only with **web** pull servers.</span></span> <span data-ttu-id="2f29f-141">**SMB** プル サーバーでは、引き続き **ConfigurationID** を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f29f-141">You must still use **ConfigurationID** with an **SMB** pull server.</span></span> <span data-ttu-id="2f29f-142">> **ConfigurationID** を使用したプル サーバーの構成については、「[構成 ID を使用したプル クライアントのセットアップ](pullClientConfigId.md)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="2f29f-142">> For information about configuring a pull server by using **ConfigurationID** , see [Setting up a pull client using configuration ID](pullClientConfigId.md)</span></span>

- <span data-ttu-id="2f29f-143">**ConfigurationNames** プロパティは、クライアント ノード用の構成の名前を指定する配列です。</span><span class="sxs-lookup"><span data-stu-id="2f29f-143">The **ConfigurationNames** property is an array that specifies the names of the configurations intended for the client node.</span></span><span data-ttu-id="2f29f-144"> > **"注:** **ConfigurationNames** に複数の値を指定する場合、構成に **PartialConfiguration** ブロックも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f29f-144"> >**Note:** If you specify more than one value in the **ConfigurationNames** , you must also specify **PartialConfiguration** blocks in your configuration.</span></span> <span data-ttu-id="2f29f-145">>部分構成の詳細については、「[PowerShell Desired State Configuration の部分構成](partialConfigs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f29f-145">>For information about partial configurations, see [PowerShell Desired State Configuration partial configurations](partialConfigs.md).</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }
        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = '140a952b-b9d6-406b-b416-e0f759c9c0e4'
            ConfigurationNames = @('ClientConfig')
        }
    }
}
PullClientConfigNames
```

## <a name="set-up-a-pull-client-to-download-resources"></a><span data-ttu-id="2f29f-146">リソースをダウンロードするようにプル クライアントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="2f29f-146">Set up a Pull Client to download Resources</span></span>

<span data-ttu-id="2f29f-147">LCM 構成で **ConfigurationRepositoryWeb** ブロックまたは **ConfigurationRepositoryShare** ブロックのみを指定した場合 (前の例はこれに当たります)、プル クライアントは、".mof" ファイルが保存されている同じ場所からリソースをプルします。</span><span class="sxs-lookup"><span data-stu-id="2f29f-147">If you specify only a **ConfigurationRepositoryWeb** or **ConfigurationRepositoryShare** block in your LCM configuration (as in the previous example), the pull client will pull resources from same location where your ".mof" files are stored.</span></span> <span data-ttu-id="2f29f-148">クライアントがリソースをダウンロードできる別の場所を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2f29f-148">You can also specify different locations where clients can download resources.</span></span> <span data-ttu-id="2f29f-149">リソース サーバーを指定するには、 **ResourceRepositoryWeb** (Web プル サーバーの場合) または **ResourceRepositoryShare** ブロック (SMB プル サーバーの場合) を使用します。</span><span class="sxs-lookup"><span data-stu-id="2f29f-149">To specify a resource server, you use either a **ResourceRepositoryWeb** (for a web pull server) or a **ResourceRepositoryShare** block (for an SMB pull server).</span></span>

<span data-ttu-id="2f29f-150">次の例は、プル サーバーから構成を、SMB 共有からリソースをダウンロードするようにクライアントをセットアップするメタ構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="2f29f-150">The following example shows a metaconfiguration that sets up a client to download configurations from a Pull Server, and resources from an SMB share.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }

        ResourceRepositoryShare SMBResources
        {
            SourcePath = '\\SMBPullServer\Resources'
        }
    }
}
PullClientConfigNames
```

## <a name="set-up-a-pull-client-to-report-status"></a><span data-ttu-id="2f29f-151">状態を報告するようにプル クライアントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="2f29f-151">Set up a Pull Client to report status</span></span>

<span data-ttu-id="2f29f-152">構成、リソース、レポートについて単一のプル サーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f29f-152">You can use a single pull server for configurations, resources, and reporting.</span></span> <span data-ttu-id="2f29f-153">レポートはクライアントに対して既定では構成されません。</span><span class="sxs-lookup"><span data-stu-id="2f29f-153">Reporting is not configured for clients by default.</span></span> <span data-ttu-id="2f29f-154">状態を報告するようにクライアントを構成するには、 **ReportRepositoryWeb** ブロックを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f29f-154">To configure a client to report status, you have to create a **ReportRepositoryWeb** block.</span></span> <span data-ttu-id="2f29f-155">次の例は、単一のプル サーバーに対して構成とリソースをプルし、レポート データを送信するようにクライアントを設定するメタ構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="2f29f-155">The following example shows a metaconfiguration that sets up a client to pull configurations and resources, and send reporting data, to a single pull server.</span></span>

> [!NOTE]
> <span data-ttu-id="2f29f-156">レポート サーバーを SMB 共有にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2f29f-156">A report server cannot be an SMB share.</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientConfigNames
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }

        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }

        ReportServerWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = 'fbc6ef09-ad98-4aad-a062-92b0e0327562'
        }
    }
}
PullClientConfigNames
```

## <a name="see-also"></a><span data-ttu-id="2f29f-157">参照</span><span class="sxs-lookup"><span data-stu-id="2f29f-157">See Also</span></span>

- [<span data-ttu-id="2f29f-158">構成 ID を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="2f29f-158">Setting up a pull client with configuration ID</span></span>](PullClientConfigNames.md)
- [<span data-ttu-id="2f29f-159">DSC Web プル サーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="2f29f-159">Setting up a DSC web pull server</span></span>](pullServer.md)
