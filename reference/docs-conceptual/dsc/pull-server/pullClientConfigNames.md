---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: PowerShell 5.0 以降での構成名を使用したプル クライアントのセットアップ
ms.openlocfilehash: d591e2a757130ccecaf4eaf9f363f607fca82b93
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953629"
---
# <a name="set-up-a-pull-client-using-configuration-names-in-powershell-50-and-later"></a><span data-ttu-id="f6bd8-103">PowerShell 5.0 以降での構成名を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="f6bd8-103">Set up a Pull Client using Configuration Names in PowerShell 5.0 and later</span></span>

> <span data-ttu-id="f6bd8-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="f6bd8-104">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6bd8-105">プル サーバー (Windows Feature *DSC-Service*) は、Windows Server のサポート対象のコンポーネントですが、新機能がオファーされる予定はありません。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="f6bd8-106">管理対象のクライアントは、(Windows Server のプル サーバー以降の機能が含まれる) [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) または、[こちら](pullserver.md#community-solutions-for-pull-service)に列挙されているコミュニティ ソリューションのいずれかに切り替えを開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="f6bd8-107">プル クライアントをセットアップする前に、プル サーバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-107">Before setting up a pull client, you should set up a pull server.</span></span> <span data-ttu-id="f6bd8-108">この順序は必須ではありませんが、トラブルシューティングに役立ち、登録を確実に成功させるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-108">Though this order is not required, it helps with troubleshooting, and helps you ensure that the registration was successful.</span></span> <span data-ttu-id="f6bd8-109">プル サーバーをセットアップするには、次のガイドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-109">To set up a pull server, you can use the following guides:</span></span>

- [<span data-ttu-id="f6bd8-110">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="f6bd8-110">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="f6bd8-111">DSC HTTP プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="f6bd8-111">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="f6bd8-112">各ターゲット ノードは、構成やリソースをダウンロードし、さらにその状態を報告するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-112">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="f6bd8-113">以下のセクションでは、SMB 共有または HTTP DSC プル サーバーを使用してプル クライアントを構成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-113">The sections below show you how to configure a pull client with an SMB share or HTTP DSC Pull Server.</span></span> <span data-ttu-id="f6bd8-114">ノードの LCM が更新されると、構成済みの場所にアクセスして、割り当てられたすべての構成がダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-114">When the Node's LCM refreshes, it will reach out to the configured location to download any assigned configurations.</span></span> <span data-ttu-id="f6bd8-115">ノードに必要なリソースが存在しない場合、構成済みの場所から自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-115">If any required resources do not exist on the Node, it will automatically download them from the configured location.</span></span> <span data-ttu-id="f6bd8-116">ノードに[レポート サーバー](reportServer.md)が構成されている場合、操作の状態が報告されます。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-116">If the Node is configured with a [Report Server](reportServer.md), it will then report the status of the operation.</span></span>

> [!NOTE]
> <span data-ttu-id="f6bd8-117">このトピックは、PowerShell 5.0 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-117">This topic applies to PowerShell 5.0.</span></span>
> <span data-ttu-id="f6bd8-118">PowerShell 4.0 でのプル クライアントのセットアップについては、「[PowerShell 4.0 での構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID4.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-118">For information on setting up a pull client in PowerShell 4.0, see [Set up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md)</span></span>

## <a name="configure-the-pull-client-lcm"></a><span data-ttu-id="f6bd8-119">プル クライアント LCM を構成する</span><span class="sxs-lookup"><span data-stu-id="f6bd8-119">Configure the pull client LCM</span></span>

<span data-ttu-id="f6bd8-120">以下のいずれかの例を実行すると、**PullClientConfigName** という名前の新しい出力フォルダーが作成され、そこにメタ構成 MOF ファイルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-120">Executing any of the examples below creates a new output folder named **PullClientConfigName** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="f6bd8-121">この場合、メタ構成 MOF ファイルの名前は `localhost.meta.mof` になります。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-121">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="f6bd8-122">構成を適用するには、**Path** をメタ構成 MOF ファイルの場所に設定して **Set-DscLocalConfigurationManager** コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-122">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="f6bd8-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-123">For example:</span></span>

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigName –Verbose.
```

## <a name="configuration-name"></a><span data-ttu-id="f6bd8-124">構成名</span><span class="sxs-lookup"><span data-stu-id="f6bd8-124">Configuration Name</span></span>

<span data-ttu-id="f6bd8-125">下の例では、この目的で作成され、前にコンパイルしてある Configuration の名前に LCM の **ConfigurationName** プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-125">The examples below sets the **ConfigurationName** property of the LCM to the name of a previously compiled Configuration, created for this purpose.</span></span> <span data-ttu-id="f6bd8-126">**ConfigurationName** は、LCM がプル サーバーで適切な構成を検索する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-126">The **ConfigurationName** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="f6bd8-127">プル サーバーの構成 MOF ファイルの名前は `<ConfigurationName>.mof` にする必要があります。今回は "ClientConfig.mof" です。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-127">The configuration MOF file on the pull server must be named `<ConfigurationName>.mof`, in this case, "ClientConfig.mof".</span></span> <span data-ttu-id="f6bd8-128">詳細については、[プル サーバーへの構成の発行 (v4/v5)](publishConfigs.md) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-128">For more information, see [Publish Configurations to a Pull Server (v4/v5)](publishConfigs.md).</span></span>

## <a name="set-up-a-pull-client-to-download-configurations"></a><span data-ttu-id="f6bd8-129">構成をダウンロードするようにプル クライアントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="f6bd8-129">Set up a Pull Client to download Configurations</span></span>

<span data-ttu-id="f6bd8-130">各クライアントを**プル** モードで構成し、その構成が格納されているプル サーバーの url を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-130">Each client must be configured in **Pull** mode and given the pull server url where its configuration is stored.</span></span> <span data-ttu-id="f6bd8-131">これを行うには、必要な情報を備えるようにローカル構成マネージャー (LCM) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-131">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="f6bd8-132">LCM を構成するには、**DSCLocalConfigurationManager** 属性で修飾された特別な種類の構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-132">To configure the LCM, you create a special type of configuration, decorated with the **DSCLocalConfigurationManager** attribute.</span></span> <span data-ttu-id="f6bd8-133">LCM の構成の詳細については、「[ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-133">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md).</span></span>

<span data-ttu-id="f6bd8-134">次のスクリプトは、"CONTOSO-PullSrv" という名前のサーバーから構成をプルするように LCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-134">The following script configures the LCM to pull configurations from a server named "CONTOSO-PullSrv".</span></span>

- <span data-ttu-id="f6bd8-135">このスクリプトでは、**ConfigurationRepositoryWeb** ブロックでプル サーバーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-135">In the script, the **ConfigurationRepositoryWeb** block defines the pull server.</span></span> <span data-ttu-id="f6bd8-136">**ServerURL** プロパティには、プル サーバー用のエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-136">The **ServerURL** property specifies the endpoint for the pull server.</span></span>

- <span data-ttu-id="f6bd8-137">**RegistrationKey** プロパティは、プル サーバーのすべてのクライアント ノードとそのプル サーバーとの間で共有されるキーです。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-137">The **RegistrationKey** property is a shared key between all client nodes for a pull server and that pull server.</span></span> <span data-ttu-id="f6bd8-138">同じ値がプル サーバー上のファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-138">The same value is stored in a file on the pull server.</span></span>
  > [!NOTE]
  > <span data-ttu-id="f6bd8-139">登録キーは、**Web** プル サーバーでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-139">Registration keys work only with **web** pull servers.</span></span> <span data-ttu-id="f6bd8-140">**SMB** プル サーバーでは、引き続き **ConfigurationID** を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-140">You must still use **ConfigurationID** with an **SMB** pull server.</span></span>
  > <span data-ttu-id="f6bd8-141">**ConfigurationID** を使用したプル サーバーの構成については、「[構成 ID を使用したプル クライアントのセットアップ](pullClientConfigId.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-141">For information about configuring a pull server by using **ConfigurationID**, see [Setting up a pull client using configuration ID](pullClientConfigId.md)</span></span>

- <span data-ttu-id="f6bd8-142">**ConfigurationNames** プロパティは、クライアント ノード用の構成の名前を指定する配列です。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-142">The **ConfigurationNames** property is an array that specifies the names of the configurations intended for the client node.</span></span>
  ><span data-ttu-id="f6bd8-143">**注:** **ConfigurationNames** に複数の値を指定する場合、構成に **PartialConfiguration** ブロックも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-143">**Note:** If you specify more than one value in the **ConfigurationNames**, you must also specify **PartialConfiguration** blocks in your configuration.</span></span>
  ><span data-ttu-id="f6bd8-144">部分構成の詳細については、「[PowerShell Desired State Configuration の部分構成](partialConfigs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-144">For information about partial configurations, see [PowerShell Desired State Configuration partial configurations](partialConfigs.md).</span></span>

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

## <a name="set-up-a-pull-client-to-download-resources"></a><span data-ttu-id="f6bd8-145">リソースをダウンロードするようにプル クライアントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="f6bd8-145">Set up a Pull Client to download Resources</span></span>

<span data-ttu-id="f6bd8-146">LCM 構成で **ConfigurationRepositoryWeb** ブロックまたは **ConfigurationRepositoryShare** ブロックのみを指定した場合 (前の例はこれに当たります)、プル クライアントは、".mof" ファイルが保存されている同じ場所からリソースをプルします。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-146">If you specify only a **ConfigurationRepositoryWeb** or **ConfigurationRepositoryShare** block in your LCM configuration (as in the previous example), the pull client will pull resources from same location where your ".mof" files are stored.</span></span> <span data-ttu-id="f6bd8-147">クライアントがリソースをダウンロードできる別の場所を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-147">You can also specify different locations where clients can download resources.</span></span> <span data-ttu-id="f6bd8-148">リソース サーバーを指定するには、**ResourceRepositoryWeb** (Web プル サーバーの場合) または **ResourceRepositoryShare** ブロック (SMB プル サーバーの場合) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-148">To specify a resource server, you use either a **ResourceRepositoryWeb** (for a web pull server) or a **ResourceRepositoryShare** block (for an SMB pull server).</span></span>

<span data-ttu-id="f6bd8-149">次の例は、プル サーバーから構成を、SMB 共有からリソースをダウンロードするようにクライアントをセットアップするメタ構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-149">The following example shows a metaconfiguration that sets up a client to download configurations from a Pull Server, and resources from an SMB share.</span></span>

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

## <a name="set-up-a-pull-client-to-report-status"></a><span data-ttu-id="f6bd8-150">状態を報告するようにプル クライアントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="f6bd8-150">Set up a Pull Client to report status</span></span>

<span data-ttu-id="f6bd8-151">構成、リソース、レポートについて単一のプル サーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-151">You can use a single pull server for configurations, resources, and reporting.</span></span> <span data-ttu-id="f6bd8-152">レポートはクライアントに対して既定では構成されません。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-152">Reporting is not configured for clients by default.</span></span> <span data-ttu-id="f6bd8-153">状態を報告するようにクライアントを構成するには、**ReportRepositoryWeb** ブロックを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-153">To configure a client to report status, you have to create a **ReportRepositoryWeb** block.</span></span> <span data-ttu-id="f6bd8-154">次の例は、単一のプル サーバーに対して構成とリソースをプルし、レポート データを送信するようにクライアントを設定するメタ構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-154">The following example shows a metaconfiguration that sets up a client to pull configurations and resources, and send reporting data, to a single pull server.</span></span>

> [!NOTE]
> <span data-ttu-id="f6bd8-155">レポート サーバーを SMB 共有にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f6bd8-155">A report server cannot be an SMB share.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f6bd8-156">参照</span><span class="sxs-lookup"><span data-stu-id="f6bd8-156">See Also</span></span>

* [<span data-ttu-id="f6bd8-157">構成 ID を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="f6bd8-157">Setting up a pull client with configuration ID</span></span>](PullClientConfigNames.md)
* [<span data-ttu-id="f6bd8-158">DSC Web プル サーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="f6bd8-158">Setting up a DSC web pull server</span></span>](pullServer.md)
