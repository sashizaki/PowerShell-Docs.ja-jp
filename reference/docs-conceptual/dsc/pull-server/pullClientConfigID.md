---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: PowerShell 5.0 以降での構成 ID を使用したプル クライアントのセットアップ
description: この記事では、PowerShell 5.0 以降で構成 ID を使用してプル クライアントをセットアップする方法について説明します
ms.openlocfilehash: 601858c08ce9a893a8941823d27fef3a60882b48
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92664301"
---
# <a name="set-up-a-pull-client-using-configuration-ids-in-powershell-50-and-later"></a><span data-ttu-id="91421-104">PowerShell 5.0 以降での構成 ID を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="91421-104">Set up a Pull Client using Configuration IDs in PowerShell 5.0 and later</span></span>

> <span data-ttu-id="91421-105">適用先:Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="91421-105">Applies To: Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91421-106">プル サーバー (Windows Feature *DSC-Service* ) は、Windows Server のサポート対象のコンポーネントですが、新機能がオファーされる予定はありません。</span><span class="sxs-lookup"><span data-stu-id="91421-106">The Pull Server (Windows Feature *DSC-Service* ) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="91421-107">管理対象のクライアントは、(Windows Server のプル サーバー以降の機能が含まれる) [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) または、[こちら](pullserver.md#community-solutions-for-pull-service)に列挙されているコミュニティ ソリューションのいずれかに切り替えを開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="91421-107">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="91421-108">プル クライアントをセットアップする前に、プル サーバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91421-108">Before setting up a pull client, you should set up a pull server.</span></span> <span data-ttu-id="91421-109">この順序は必須ではありませんが、トラブルシューティングに役立ち、登録を確実に成功させるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="91421-109">Though this order is not required, it helps with troubleshooting, and helps you ensure that the registration was successful.</span></span> <span data-ttu-id="91421-110">プル サーバーをセットアップするには、次のガイドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="91421-110">To set up a pull server, you can use the following guides:</span></span>

- [<span data-ttu-id="91421-111">DSC SMB プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="91421-111">Set up a DSC SMB Pull Server</span></span>](pullServerSmb.md)
- [<span data-ttu-id="91421-112">DSC HTTP プル サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="91421-112">Set up a DSC HTTP Pull Server</span></span>](pullServer.md)

<span data-ttu-id="91421-113">各ターゲット ノードは、構成やリソースをダウンロードし、さらにその状態を報告するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="91421-113">Each target node can be configured to download configurations, resources, and even report its status.</span></span> <span data-ttu-id="91421-114">以下のセクションでは、SMB 共有または HTTP DSC プル サーバーを使用してプル クライアントを構成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="91421-114">The sections below show you how to configure a pull client with an SMB share or HTTP DSC Pull Server.</span></span> <span data-ttu-id="91421-115">ノードの LCM が更新されると、構成済みの場所にアクセスして、割り当てられたすべての構成がダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="91421-115">When the Node's LCM refreshes, it will reach out to the configured location to download any assigned configurations.</span></span> <span data-ttu-id="91421-116">ノードに必要なリソースが存在しない場合、構成済みの場所から自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="91421-116">If any required resources do not exist on the Node, it will automatically download them from the configured location.</span></span> <span data-ttu-id="91421-117">ノードに[レポート サーバー](reportServer.md)が構成されている場合、操作の状態が報告されます。</span><span class="sxs-lookup"><span data-stu-id="91421-117">If the Node is configured with a [Report Server](reportServer.md), it will then report the status of the operation.</span></span>

> [!NOTE]
> <span data-ttu-id="91421-118">このトピックは、PowerShell 5.0 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="91421-118">This topic applies to PowerShell 5.0.</span></span> <span data-ttu-id="91421-119">PowerShell 4.0 でのプル クライアントのセットアップについては、「[PowerShell 4.0 での構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID4.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="91421-119">For information on setting up a pull client in PowerShell 4.0, see [Setting up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md)</span></span>

## <a name="configure-the-pull-client-lcm"></a><span data-ttu-id="91421-120">プル クライアント LCM を構成する</span><span class="sxs-lookup"><span data-stu-id="91421-120">Configure the pull client LCM</span></span>

<span data-ttu-id="91421-121">以下のいずれかの例を実行すると、 **PullClientConfigID** という名前の新しい出力フォルダーが作成され、そこにメタ構成 MOF ファイルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="91421-121">Executing any of the examples below creates a new output folder named **PullClientConfigID** and puts a metaconfiguration MOF file there.</span></span> <span data-ttu-id="91421-122">この場合、メタ構成 MOF ファイルの名前は `localhost.meta.mof` になります。</span><span class="sxs-lookup"><span data-stu-id="91421-122">In this case, the metaconfiguration MOF file will be named `localhost.meta.mof`.</span></span>

<span data-ttu-id="91421-123">構成を適用するには、 **Path** をメタ構成 MOF ファイルの場所に設定して **Set-DscLocalConfigurationManager** コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="91421-123">To apply the configuration, call the **Set-DscLocalConfigurationManager** cmdlet, with the **Path** set to the location of the metaconfiguration MOF file.</span></span> <span data-ttu-id="91421-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="91421-124">For example:</span></span>

```powershell
Set-DSCLocalConfigurationManager –ComputerName localhost –Path .\PullClientConfigId –Verbose.
```

## <a name="configuration-id"></a><span data-ttu-id="91421-125">構成 ID</span><span class="sxs-lookup"><span data-stu-id="91421-125">Configuration ID</span></span>

<span data-ttu-id="91421-126">以下の例は、LCM の **ConfigurationID** プロパティをこの目的で以前に作成した **Guid** に設定します。</span><span class="sxs-lookup"><span data-stu-id="91421-126">The examples below sets the **ConfigurationID** property of the LCM to a **Guid** that had been previously created for this purpose.</span></span> <span data-ttu-id="91421-127">**ConfigurationID** は、LCM がプル サーバーで適切な構成を検索する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="91421-127">The **ConfigurationID** is what the LCM uses to find the appropriate configuration on the pull server.</span></span> <span data-ttu-id="91421-128">プル サーバー上の構成 MOF ファイルは、`ConfigurationID.mof` という名前にする必要があります。ここで、 *ConfigurationID* はターゲット ノードの LCM の **ConfigurationID** プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="91421-128">The configuration MOF file on the pull server must be named `ConfigurationID.mof`, where *ConfigurationID* is the value of the **ConfigurationID** property of the target node's LCM.</span></span> <span data-ttu-id="91421-129">詳細については、[プル サーバーへの構成の発行 (v4/v5)](publishConfigs.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="91421-129">For more information see [Publish Configurations to a Pull Server (v4/v5)](publishConfigs.md).</span></span>

<span data-ttu-id="91421-130">以下の例を使用するか、または [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) コマンドレットを使用して、ランダムな **Guid** を作成できます。</span><span class="sxs-lookup"><span data-stu-id="91421-130">You can create a random **Guid** using the example below, or by using the [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) cmdlet.</span></span>

```powershell
[System.Guid]::NewGuid()
```

<span data-ttu-id="91421-131">環境で **Guid** を使用する詳細については、 [Guid の計画](secureserver.md#guids)に関する項を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91421-131">For more information about using **Guids** in your environment, see [Plan for Guids](secureserver.md#guids).</span></span>

## <a name="set-up-a-pull-client-to-download-configurations"></a><span data-ttu-id="91421-132">構成をダウンロードするようにプル クライアントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="91421-132">Set up a Pull Client to download Configurations</span></span>

<span data-ttu-id="91421-133">各クライアントを **プル** モードで構成し、その構成が格納されているプル サーバーの url を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91421-133">Each client must be configured in **Pull** mode and given the pull server url where its configuration is stored.</span></span> <span data-ttu-id="91421-134">これを行うには、必要な情報を備えるようにローカル構成マネージャー (LCM) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91421-134">To do this, you have to configure the Local Configuration Manager (LCM) with the necessary information.</span></span> <span data-ttu-id="91421-135">LCM を構成するには、 **DSCLocalConfigurationManager** 属性で修飾された特別な種類の構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="91421-135">To configure the LCM, you create a special type of configuration, decorated with the **DSCLocalConfigurationManager** attribute.</span></span> <span data-ttu-id="91421-136">LCM の構成の詳細については、「[ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="91421-136">For more information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md).</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="91421-137">HTTP DSC プル サーバー</span><span class="sxs-lookup"><span data-stu-id="91421-137">HTTP DSC Pull Server</span></span>

<span data-ttu-id="91421-138">次のスクリプトは、"CONTOSO-PullSrv" という名前のサーバーから構成をプルするように LCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="91421-138">The following script configures the LCM to pull configurations from a server named "CONTOSO-PullSrv".</span></span>

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

<span data-ttu-id="91421-139">このスクリプトでは、 **ConfigurationRepositoryWeb** ブロックでプル サーバーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="91421-139">In the script, the **ConfigurationRepositoryWeb** block defines the pull server.</span></span> <span data-ttu-id="91421-140">**ServerUrl** は DSC プルの url を指定します</span><span class="sxs-lookup"><span data-stu-id="91421-140">The **ServerUrl** specifies the url of the DSC Pull</span></span>

### <a name="smb-share"></a><span data-ttu-id="91421-141">SMB 共有</span><span class="sxs-lookup"><span data-stu-id="91421-141">SMB Share</span></span>

<span data-ttu-id="91421-142">次のスクリプトは、SMB 共有 `\\SMBPullServer\Pull` から構成をプルするように LCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="91421-142">The following script configures the LCM to pull configurations from the SMB Share `\\SMBPullServer\Pull`.</span></span>

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

<span data-ttu-id="91421-143">このスクリプトでは、 **ConfigurationRepositoryShare** ブロックでプル サーバーを定義していますが、この例では、単なる SMB 共有です。</span><span class="sxs-lookup"><span data-stu-id="91421-143">In the script, the **ConfigurationRepositoryShare** block defines the pull server, which in this case, is just an SMB share.</span></span>

## <a name="set-up-a-pull-client-to-download-resources"></a><span data-ttu-id="91421-144">リソースをダウンロードするようにプル クライアントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="91421-144">Set up a Pull Client to download Resources</span></span>

<span data-ttu-id="91421-145">LCM 構成で **ConfigurationRepositoryWeb** ブロックまたは **ConfigurationRepositoryShare** ブロックのみを指定した場合 (前の例はこれに当たります)、プル クライアントは、その構成を取得する同じ場所から、リソースをプルします。</span><span class="sxs-lookup"><span data-stu-id="91421-145">If you specify only the **ConfigurationRepositoryWeb** or **ConfigurationRepositoryShare** block in your LCM configuration (as in the previous examples), the pull client will pull resources from the same location it retrieves its configurations.</span></span> <span data-ttu-id="91421-146">リソース用に別の場所を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="91421-146">You can also specify separate locations for resources.</span></span> <span data-ttu-id="91421-147">リソースの場所を別のサーバーとして指定するには、 **ResourceRepositoryWeb** ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="91421-147">To specify a resource location as a separate server, use the **ResourceRepositoryWeb** block.</span></span> <span data-ttu-id="91421-148">リソースの場所を SMB 共有として指定するには、 **ResourceRepositoryShare** ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="91421-148">To specify a resource location as an SMB share, use the **ResourceRepositoryShare** block.</span></span>

> [!NOTE]
> <span data-ttu-id="91421-149">**ConfigurationRepositoryWeb** を **ResourceRepositoryShare** と、または **ConfigurationRepositoryShare** を **ResourceRepositoryWeb** と組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="91421-149">You can combine **ConfigurationRepositoryWeb** with **ResourceRepositoryShare** or **ConfigurationRepositoryShare** with **ResourceRepositoryWeb**.</span></span> <span data-ttu-id="91421-150">この例は、以下に示していません。</span><span class="sxs-lookup"><span data-stu-id="91421-150">Examples of this are not shown below.</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="91421-151">HTTP DSC プル サーバー</span><span class="sxs-lookup"><span data-stu-id="91421-151">HTTP DSC Pull Server</span></span>

<span data-ttu-id="91421-152">次のメタ構成は、プル クライアントが **CONTOSO-PullSrv** からその構成を取得し、 **CONTOSO-ResourceSrv** からそのリソースを取得するように、プル クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="91421-152">The following metaconfiguration configures a pull client to get its configurations from **CONTOSO-PullSrv** and its resources from **CONTOSO-ResourceSrv**.</span></span>

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

### <a name="smb-share"></a><span data-ttu-id="91421-153">SMB 共有</span><span class="sxs-lookup"><span data-stu-id="91421-153">SMB Share</span></span>

<span data-ttu-id="91421-154">次の例は、SMB 共有 `\\SMBPullServer\Configurations` から構成を、SMB 共有 `\\SMBPullServer\Resources` からリソースをプルするように、クライアントをセットアップするメタ構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="91421-154">The following example shows a metaconfiguration that sets up a client to pull configurations from the SMB share `\\SMBPullServer\Configurations`, and resources from the SMB share `\\SMBPullServer\Resources`.</span></span>

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

#### <a name="automatically-download-resources-in-push-mode"></a><span data-ttu-id="91421-155">プッシュ モードでリソースを自動的にダウンロードする</span><span class="sxs-lookup"><span data-stu-id="91421-155">Automatically download Resources in Push Mode</span></span>

<span data-ttu-id="91421-156">PowerShell 5.0 以降では、プル クライアントは、 **プッシュ** モードで構成されている場合でも、SMB 共有からモジュールをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="91421-156">Beginning in PowerShell 5.0, your pull clients can download modules from an SMB share, even when they are configured for **Push** mode.</span></span> <span data-ttu-id="91421-157">これは、プル サーバーをセットアップしないシナリオで特に便利です。</span><span class="sxs-lookup"><span data-stu-id="91421-157">This is especially useful in scenarios where you do not want to set up a Pull Server.</span></span> <span data-ttu-id="91421-158">**ResourceRepositoryShare** ブロックは、 **ConfigurationRepositoryShare** を指定しなくても使用できます。</span><span class="sxs-lookup"><span data-stu-id="91421-158">The **ResourceRepositoryShare** block can be used without specifying a **ConfigurationRepositoryShare**.</span></span> <span data-ttu-id="91421-159">次の例に、SMB 共有 `\\SMBPullServer\Resources` からリソースをプルするようにクライアントをセットアップするメタ構成を示します。</span><span class="sxs-lookup"><span data-stu-id="91421-159">The following example shows a metaconfiguration that sets up a client to pull resources from an SMB Share `\\SMBPullServer\Resources`.</span></span> <span data-ttu-id="91421-160">ノードに構成が **プッシュ** されると、指定された共有から必要なすべてのリソースが自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="91421-160">When the Node is **PUSHED** a configuration, it will automatically download any required resources, from the share specified.</span></span>

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

## <a name="set-up-a-pull-client-to-report-status"></a><span data-ttu-id="91421-161">状態を報告するようにプル クライアントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="91421-161">Set up a Pull Client to report status</span></span>

<span data-ttu-id="91421-162">既定では、ノードは構成済みプル サーバーにレポートを送信しません。</span><span class="sxs-lookup"><span data-stu-id="91421-162">By default, Nodes will not send reports to a configured Pull Server.</span></span> <span data-ttu-id="91421-163">構成、リソース、およびレポートについて単一のプル サーバーを使うことができますが、レポートをセットアップするために **ReportRepositoryWeb** ブロックを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91421-163">You can use a single pull server for configurations, resources, and reporting, but you have to create a **ReportRepositoryWeb** block to set up reporting.</span></span>

### <a name="http-dsc-pull-server"></a><span data-ttu-id="91421-164">HTTP DSC プル サーバー</span><span class="sxs-lookup"><span data-stu-id="91421-164">HTTP DSC Pull Server</span></span>

<span data-ttu-id="91421-165">次の例は、単一のプル サーバーに対して構成とリソースをプルし、レポート データを送信するようにクライアントを設定するメタ構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="91421-165">The following example shows a metaconfiguration that sets up a client to pull configurations and resources, and send reporting data, to a single pull server.</span></span>

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

<span data-ttu-id="91421-166">レポート サーバーを指定するには、 **ReportRepositoryWeb** ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="91421-166">To specify a report server, you use a **ReportRepositoryWeb** block.</span></span> <span data-ttu-id="91421-167">レポート サーバーを SMB サーバーにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="91421-167">A report server cannot be an SMB server.</span></span> <span data-ttu-id="91421-168">次のメタ構成は、 **CONTOSO-PullSrv** から構成を取得し、 **CONTOSO-ResourceSrv** からリソースを取得し、 **CONTOSO-ReportSrv** に状態レポートを送信するように、プル クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="91421-168">The following metaconfiguration configures a pull client to get its configurations from **CONTOSO-PullSrv** and its resources from **CONTOSO-ResourceSrv** , and to send status reports to **CONTOSO-ReportSrv** :</span></span>

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

### <a name="smb-share"></a><span data-ttu-id="91421-169">SMB 共有</span><span class="sxs-lookup"><span data-stu-id="91421-169">SMB Share</span></span>

<span data-ttu-id="91421-170">レポート サーバーを SMB 共有にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="91421-170">A report server cannot be an SMB share.</span></span>

## <a name="next-steps"></a><span data-ttu-id="91421-171">次の手順</span><span class="sxs-lookup"><span data-stu-id="91421-171">Next Steps</span></span>

<span data-ttu-id="91421-172">プル クライアントを構成したら、次のガイドを使用して、次の手順を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="91421-172">Once the pull client has been configured, you can use the following guides to perform the next steps:</span></span>

- [<span data-ttu-id="91421-173">プル サーバーに構成を発行する (v4/v5)</span><span class="sxs-lookup"><span data-stu-id="91421-173">Publish Configurations to a Pull Server (v4/v5)</span></span>](publishConfigs.md)
- [<span data-ttu-id="91421-174">リソースのパッケージ化とプル サーバーへのアップロード (v4)</span><span class="sxs-lookup"><span data-stu-id="91421-174">Package and Upload Resources to a Pull Server (v4)</span></span>](package-upload-resources.md)

## <a name="see-also"></a><span data-ttu-id="91421-175">参照</span><span class="sxs-lookup"><span data-stu-id="91421-175">See Also</span></span>

- [<span data-ttu-id="91421-176">構成名を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="91421-176">Setting up a pull client with configuration names</span></span>](pullClientConfigNames.md)
