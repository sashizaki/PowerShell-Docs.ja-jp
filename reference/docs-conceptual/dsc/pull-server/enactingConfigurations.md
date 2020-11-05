---
ms.date: 10/16/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成の適用
description: PowerShell DSC 構成を適用するには、プッシュ モードとプル モードの 2 つの方法があります。
ms.openlocfilehash: 466eb43cd266ceb4ae81cc997a7b338e041f8a15
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92661732"
---
# <a name="enacting-configurations"></a><span data-ttu-id="ddf5d-104">構成の適用</span><span class="sxs-lookup"><span data-stu-id="ddf5d-104">Enacting configurations</span></span>

> <span data-ttu-id="ddf5d-105">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="ddf5d-105">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="ddf5d-106">PowerShell Desired State Configuration (DSC) 構成を適用するには、プッシュ モードとプル モードの 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-106">There are two ways to enact PowerShell Desired State Configuration (DSC) configurations: push mode and pull mode.</span></span>

## <a name="push-mode"></a><span data-ttu-id="ddf5d-107">プッシュ モード</span><span class="sxs-lookup"><span data-stu-id="ddf5d-107">Push mode</span></span>

<span data-ttu-id="ddf5d-108">![プッシュ モードの概要](media/enactingConfigurations/pushModel.png "プッシュ モードのしくみ")</span><span class="sxs-lookup"><span data-stu-id="ddf5d-108">![Overview of Push mode](media/enactingConfigurations/pushModel.png "How push mode works")</span></span>

<span data-ttu-id="ddf5d-109">プッシュ モードは、[Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) コマンドレットを呼び出してターゲット ノードに構成を適用するユーザー アクティビティを示します。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-109">Push mode refers to a user actively applying a configuration to a target node by calling the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

<span data-ttu-id="ddf5d-110">構成を作成し、コンパイルした後、プッシュ モードで適用するには、[Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) コマンドレットを呼び出し、コマンドレットの -Path パラメーターを構成 MOF が配置されているパスに設定します。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-110">After creating and compiling a configuration, you can enact it in push mode by calling the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet, setting the -Path parameter of the cmdlet to the path where the configuration MOF is located.</span></span> <span data-ttu-id="ddf5d-111">たとえば、構成 MOF が `C:\DSC\Configurations\localhost.mof` にある場合は、`Start-DscConfiguration -Path 'C:\DSC\Configurations'` というコマンドを使用してローカル コンピューターに適用します。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-111">For example, if the configuration MOF is located at `C:\DSC\Configurations\localhost.mof`, you would apply it to the local machine with the following command: `Start-DscConfiguration -Path 'C:\DSC\Configurations'`</span></span>

> [!NOTE]
> <span data-ttu-id="ddf5d-112">既定では、DSC はバックグラウンド ジョブとして構成を実行します。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-112">By default, DSC runs a configuration as a background job.</span></span> <span data-ttu-id="ddf5d-113">構成を対話的に実行するには、 **Wait** パラメーターを指定して [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-113">To run the configuration interactively, call the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) with the **Wait** parameter.</span></span>

## <a name="pull-mode"></a><span data-ttu-id="ddf5d-114">プル モード</span><span class="sxs-lookup"><span data-stu-id="ddf5d-114">Pull mode</span></span>

<span data-ttu-id="ddf5d-115">![プル モードの概要](media/enactingConfigurations/pullModel.png "プル モードのしくみ")</span><span class="sxs-lookup"><span data-stu-id="ddf5d-115">![Overview of Pull Mode](media/enactingConfigurations/pullModel.png "How pull mode works")</span></span>

<span data-ttu-id="ddf5d-116">プル モードでは、プル クライアントはリモート プル サービスから Desired State Configuration を取得するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-116">In pull mode, pull clients are configured to get their desired state configurations from a remote pull service.</span></span> <span data-ttu-id="ddf5d-117">同様に、プル サービスは、DSC サービスをホストするようにセットアップされ、プル クライアントに必要な構成とリソースを使用してプロビジョニングされています。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-117">Likewise, the pull service has been set up to host the DSC service, and has been provisioned with the configurations and resources that are required by the pull clients.</span></span> <span data-ttu-id="ddf5d-118">それぞれのプル クライアントには、ノードの構成に対して定期的なコンプライアンス チェックを実行するイベントがスケジュールされています。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-118">Each of the pull clients has a scheduled event that performs a periodic compliance check on the configuration of the node.</span></span> <span data-ttu-id="ddf5d-119">イベントが最初にトリガーされたとき、プル クライアント上のローカル構成マネージャー (LCM) によって、LCM で指定された構成を取得するためのプル サービスへの要求が行われます。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-119">When the event is triggered the first time, the Local Configuration Manager (LCM) on the pull client makes a request to the pull service to get the configuration specified in the LCM.</span></span> <span data-ttu-id="ddf5d-120">プル サービスにその構成が存在し、最初の検証チェックに合格した場合、構成はプル クライアントにダウンロードされ、LCM によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-120">If that configuration exists on the pull service, and it passes initial validation checks, the configuration is downloaded to the pull client, where it is then executed by the LCM.</span></span>

<span data-ttu-id="ddf5d-121">LCM はクライアントが構成に準拠しているかどうかを、LCM の **ConfigurationModeFrequencyMins** プロパティで指定された間隔で定期的にチェックします。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-121">The LCM checks that the client is in compliance with the configuration at regular intervals specified by the **ConfigurationModeFrequencyMins** property of the LCM.</span></span> <span data-ttu-id="ddf5d-122">LCM はプル サービスで更新された構成を、LCM の **RefreshModeFrequency** プロパティで指定された間隔で定期的にチェックします。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-122">The LCM checks for updated configurations on the pull service at regular intervals specified by the **RefreshModeFrequency** property of the LCM.</span></span> <span data-ttu-id="ddf5d-123">LCM の構成の詳細については、「[ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-123">For information about configuring the LCM, see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md).</span></span>

<span data-ttu-id="ddf5d-124">プル サービスをホストするための推奨ソリューションは、DSC クラウド サービスである [Azure Automation](https://azure.microsoft.com/services/automation/) です。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-124">The recommended solution for hosting a Pull Service, is the DSC cloud service, [Azure Automation](https://azure.microsoft.com/services/automation/).</span></span> <span data-ttu-id="ddf5d-125">これはホスト型ソリューションであり、管理とレポートをグラフィカルに行い、管理を一元化できます。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-125">This is hosted solution provides graphical management, reporting, and centralized administration.</span></span>

<span data-ttu-id="ddf5d-126">Windows Server でのプル サービスのセットアップについては、「[DSC Web プル サーバーのセットアップ](pullServer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-126">For more information on setting up a Pull Service on Windows Server, see [Setting up a DSC web pull server](pullServer.md).</span></span> <span data-ttu-id="ddf5d-127">ただし、この実装では機能が制限されており、統合の一部を "ユーザー自身で" 行う必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-127">Understand however, that this implementation has limited features and does require some "do it yourself" integration.</span></span>

<span data-ttu-id="ddf5d-128">次のトピックでは、プル サービスとクライアントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ddf5d-128">The following topics explain pull service and clients:</span></span>

- [<span data-ttu-id="ddf5d-129">Azure Automation DSC の概要</span><span class="sxs-lookup"><span data-stu-id="ddf5d-129">Azure Automation DSC Overview</span></span>](/azure/automation/automation-dsc-overview)
- [<span data-ttu-id="ddf5d-130">SMB プル サーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="ddf5d-130">Setting up an SMB pull server</span></span>](pullServerSMB.md)
- [<span data-ttu-id="ddf5d-131">Configuring a pull client (プル クライアントの構成)</span><span class="sxs-lookup"><span data-stu-id="ddf5d-131">Configuring a pull client</span></span>](pullClientConfigID.md)
