---
ms.date: 2017-10-16
author: eslesar;mgreenegit
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "構成の適用"
ms.openlocfilehash: f9f8889439e43d540b50b68ef13e8e088b8cadd3
ms.sourcegitcommit: 9a5da3f739b1eebb81ede58bd4fc8037bad87224
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2017
---
# <a name="enacting-configurations"></a><span data-ttu-id="70a2e-103">構成の適用</span><span class="sxs-lookup"><span data-stu-id="70a2e-103">Enacting configurations</span></span>

><span data-ttu-id="70a2e-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="70a2e-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="70a2e-105">PowerShell Desired State Configuration (DSC) 構成を適用するには、プッシュ モードとプル モードの 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="70a2e-105">There are two ways to enact PowerShell Desired State Configuration (DSC) configurations: push mode and pull mode.</span></span>

## <a name="push-mode"></a><span data-ttu-id="70a2e-106">プッシュ モード</span><span class="sxs-lookup"><span data-stu-id="70a2e-106">Push mode</span></span>

<span data-ttu-id="70a2e-107">![プッシュ モード](images/pushModel.png "プッシュ モードのしくみ")</span><span class="sxs-lookup"><span data-stu-id="70a2e-107">![Push mode](images/pushModel.png "How push mode works")</span></span>

<span data-ttu-id="70a2e-108">プッシュ モードは、[Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) コマンドレットを呼び出してターゲット ノードに構成を適用するユーザー アクティビティを示します。</span><span class="sxs-lookup"><span data-stu-id="70a2e-108">Push mode refers to a user actively applying a configuration to a target node by calling the [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) cmdlet.</span></span>

<span data-ttu-id="70a2e-109">構成を作成し、コンパイルした後、プッシュ モードで適用するには、[Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) コマンドレットを呼び出し、コマンドレットの -Path パラメーターを構成 MOF が配置されているパスに設定します。</span><span class="sxs-lookup"><span data-stu-id="70a2e-109">After creating and compiling a configuration, you can enact it in push mode by calling the [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) cmdlet, setting the -Path parameter of the cmdlet to the path where the configuration MOF is located.</span></span>
<span data-ttu-id="70a2e-110">たとえば、構成 MOF が `C:\DSC\Configurations\localhost.mof` にある場合は、`Start-DscConfiguration -Path 'C:\DSC\Configurations'` というコマンドを使用してローカル コンピューターに適用します。</span><span class="sxs-lookup"><span data-stu-id="70a2e-110">For example, if the configuration MOF is located at `C:\DSC\Configurations\localhost.mof`, you would apply it to the local machine with the following command: `Start-DscConfiguration -Path 'C:\DSC\Configurations'`</span></span>

> <span data-ttu-id="70a2e-111">__注__: 既定では、DSC はバックグラウンド ジョブとして構成を実行します。</span><span class="sxs-lookup"><span data-stu-id="70a2e-111">__Note__: By default, DSC runs a configuration as a background job.</span></span> <span data-ttu-id="70a2e-112">構成を対話的に実行するには、__-Wait__ パラメーターを指定して [Start-DscConfiguration](https://technet.microsoft.com/library/dn521623.aspx) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="70a2e-112">To run the configuration interactively, call the [Start-DscConfiguration](https://technet.microsoft.com/library/dn521623.aspx) with the __-Wait__ parameter.</span></span>

## <a name="pull-mode"></a><span data-ttu-id="70a2e-113">プル モード</span><span class="sxs-lookup"><span data-stu-id="70a2e-113">Pull mode</span></span>

<span data-ttu-id="70a2e-114">![プル モード](images/pullModel.png "プル モードのしくみ")</span><span class="sxs-lookup"><span data-stu-id="70a2e-114">![Pull Mode](images/pullModel.png "How pull mode works")</span></span>

<span data-ttu-id="70a2e-115">プル モードでは、プル クライアントはリモート プル サービスから Desired State Configuration を取得するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="70a2e-115">In pull mode, pull clients are configured to get their desired state configurations from a remote pull service.</span></span>
<span data-ttu-id="70a2e-116">同様に、プル サービスは、DSC サービスをホストするようにセットアップされ、プル クライアントに必要な構成とリソースを使用してプロビジョニングされています。</span><span class="sxs-lookup"><span data-stu-id="70a2e-116">Likewise, the pull service has been set up to host the DSC service, and has been provisioned with the configurations and resources that are required by the pull clients.</span></span>
<span data-ttu-id="70a2e-117">それぞれのプル クライアントには、ノードの構成に対して定期的なコンプライアンス チェックを実行するイベントがスケジュールされています。</span><span class="sxs-lookup"><span data-stu-id="70a2e-117">Each of the pull clients has a scheduled event that performs a periodic compliance check on the configuration of the node.</span></span>
<span data-ttu-id="70a2e-118">イベントが最初にトリガーされたとき、プル クライアント上のローカル構成マネージャー (LCM) によって、LCM で指定された構成を取得するためのプル サービスへの要求が行われます。</span><span class="sxs-lookup"><span data-stu-id="70a2e-118">When the event is triggered the first time, the Local Configuration Manager (LCM) on the pull client makes a request to the pull service to get the configuration specified in the LCM.</span></span>
<span data-ttu-id="70a2e-119">プル サービスにその構成が存在し、最初の検証チェックに合格した場合、構成はプル クライアントにダウンロードされ、LCM によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="70a2e-119">If that configuration exists on the pull service, and it passes initial validation checks, the configuration is downloaded to the pull client, where it is then executed by the LCM.</span></span>

<span data-ttu-id="70a2e-120">LCM はクライアントが構成に準拠しているかどうかを、LCM の **ConfigurationModeFrequencyMins** プロパティで指定された間隔で定期的にチェックします。</span><span class="sxs-lookup"><span data-stu-id="70a2e-120">The LCM checks that the client is in compliance with the configuration at regular intervals specified by the **ConfigurationModeFrequencyMins** property of the LCM.</span></span>
<span data-ttu-id="70a2e-121">LCM はプル サービスで更新された構成を、LCM の **RefreshModeFrequency** プロパティで指定された間隔で定期的にチェックします。</span><span class="sxs-lookup"><span data-stu-id="70a2e-121">The LCM checks for updated configurations on the pull service at regular intervals specified by the **RefreshModeFrequency** property of the LCM.</span></span>
<span data-ttu-id="70a2e-122">LCM の構成の詳細については、「[ローカル構成マネージャーの構成](metaConfig.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70a2e-122">For information about configuring the LCM, see [Configuring the Local Configuration Manager](metaConfig.md).</span></span>

<span data-ttu-id="70a2e-123">プル サービスをホストするための推奨ソリューションは、DSC クラウド サービスである [Azure Automation](https://azure.microsoft.com/en-us/services/automation/) です。</span><span class="sxs-lookup"><span data-stu-id="70a2e-123">The recommended solution for hosting a Pull Service, is the DSC cloud service, [Azure Automation](https://azure.microsoft.com/en-us/services/automation/).</span></span>
<span data-ttu-id="70a2e-124">これはホスト型ソリューションであり、管理とレポートをグラフィカルに行い、管理を一元化できます。</span><span class="sxs-lookup"><span data-stu-id="70a2e-124">This is hosted solution provides graphical management, reporting, and centralized administration.</span></span>

<span data-ttu-id="70a2e-125">Windows Server でのプル サービスのセットアップについては、「[DSC Web プル サーバーのセットアップ](pullServer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70a2e-125">For more information on setting up a Pull Service on Windows Server, see [Setting up a DSC web pull server](pullServer.md).</span></span>
<span data-ttu-id="70a2e-126">ただし、この実装では機能が制限されており、統合の一部を "ユーザー自身で" 行う必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="70a2e-126">Understand however, that this implementation has limited features and does require some "do it yourself" integration.</span></span>

<span data-ttu-id="70a2e-127">次のトピックでは、プル サービスとクライアントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="70a2e-127">The following topics explain pull service and clients:</span></span>

- [<span data-ttu-id="70a2e-128">Azure Automation DSC の概要</span><span class="sxs-lookup"><span data-stu-id="70a2e-128">Azure Automation DSC Overview</span></span>](https://docs.microsoft.com/en-us/azure/automation/automation-dsc-overview)
- [<span data-ttu-id="70a2e-129">Setting up an SMB pull server (SMB プル サーバーのセットアップ)</span><span class="sxs-lookup"><span data-stu-id="70a2e-129">Setting up an SMB pull server</span></span>](pullServerSMB.md)
- [<span data-ttu-id="70a2e-130">Configuring a pull client (プル クライアントの構成)</span><span class="sxs-lookup"><span data-stu-id="70a2e-130">Configuring a pull client</span></span>](pullClientConfigID.md)
