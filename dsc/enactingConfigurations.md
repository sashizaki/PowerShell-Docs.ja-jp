---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "構成の適用"
ms.openlocfilehash: db82788650186eb82f67b30b24cd45b719bbe314
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="enacting-configurations"></a><span data-ttu-id="bd4c5-103">構成の適用</span><span class="sxs-lookup"><span data-stu-id="bd4c5-103">Enacting configurations</span></span>

><span data-ttu-id="bd4c5-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="bd4c5-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="bd4c5-105">PowerShell Desired State Configuration (DSC) 構成を適用するには、プッシュ モードとプル モードの 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="bd4c5-105">There are two ways to enact PowerShell Desired State Configuration (DSC) configurations: push mode and pull mode.</span></span>

## <a name="push-mode"></a><span data-ttu-id="bd4c5-106">プッシュ モード</span><span class="sxs-lookup"><span data-stu-id="bd4c5-106">Push mode</span></span>

<span data-ttu-id="bd4c5-107">![プッシュ モード](images/Push.png "プッシュ モードのしくみ")</span><span class="sxs-lookup"><span data-stu-id="bd4c5-107">![Push mode](images/Push.png "How push mode works")</span></span>

<span data-ttu-id="bd4c5-108">プッシュ モードは、[Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) コマンドレットを呼び出してターゲット ノードに構成を適用するユーザー アクティビティを示します。</span><span class="sxs-lookup"><span data-stu-id="bd4c5-108">Push mode refers to a user actively applying a configuration to a target node by calling the [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) cmdlet.</span></span>

<span data-ttu-id="bd4c5-109">構成を作成し、コンパイルした後、プッシュ モードで適用するには、[Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) コマンドレットを呼び出し、コマンドレットの -Path パラメーターを構成 MOF が配置されているパスに設定します。</span><span class="sxs-lookup"><span data-stu-id="bd4c5-109">After creating and compiling a configuration, you can enact it in push mode by calling the [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) cmdlet, setting the -Path parameter of the cmdlet to the path where the configuration MOF is located.</span></span> <span data-ttu-id="bd4c5-110">たとえば、構成 MOF が `C:\DSC\Configurations\localhost.mof` にある場合は、`Start-DscConfiguration -Path 'C:\DSC\Configurations'` というコマンドを使用してローカル コンピューターに適用します。</span><span class="sxs-lookup"><span data-stu-id="bd4c5-110">For example, if the configuration MOF is located at `C:\DSC\Configurations\localhost.mof`, you would apply it to the local machine with the following command: `Start-DscConfiguration -Path 'C:\DSC\Configurations'`</span></span>

> <span data-ttu-id="bd4c5-111">__注__: 既定では、DSC はバックグラウンド ジョブとして構成を実行します。</span><span class="sxs-lookup"><span data-stu-id="bd4c5-111">__Note__: By default, DSC runs a configuration as a background job.</span></span> <span data-ttu-id="bd4c5-112">構成を対話的に実行するには、__-Wait__ パラメーターを指定して [Start-DscConfiguration](https://technet.microsoft.com/library/dn521623.aspx) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="bd4c5-112">To run the configuration interactively, call the [Start-DscConfiguration](https://technet.microsoft.com/library/dn521623.aspx) with the __-Wait__ parameter.</span></span>


## <a name="pull-mode"></a><span data-ttu-id="bd4c5-113">プル モード</span><span class="sxs-lookup"><span data-stu-id="bd4c5-113">Pull mode</span></span>

<span data-ttu-id="bd4c5-114">![プル モード](images/Pull.png "プル モードのしくみ")</span><span class="sxs-lookup"><span data-stu-id="bd4c5-114">![Pull Mode](images/Pull.png "How pull mode works")</span></span>

<span data-ttu-id="bd4c5-115">プル モードでは、プル クライアントはリモート プル サーバーから Desired State Configuration を取得するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="bd4c5-115">In pull mode, pull clients are configured to get their desired state configurations from a remote pull server.</span></span> <span data-ttu-id="bd4c5-116">同様に、プル サーバーは、DSC サービスをホストするようにセットアップされ、プル クライアントに必要な構成とリソースを使用してプロビジョニングされています。</span><span class="sxs-lookup"><span data-stu-id="bd4c5-116">Likewise, the pull server has been set up to host the DSC service, and has been provisioned with the configurations and resources that are required by the pull clients.</span></span> <span data-ttu-id="bd4c5-117">それぞれのプル クライアントには、ノードの構成に対して定期的なコンプライアンス チェックを実行するタスクがスケジュールされています。</span><span class="sxs-lookup"><span data-stu-id="bd4c5-117">Each one of the pull clients has a scheduled task that performs a periodic compliance check on the configuration of the node.</span></span> <span data-ttu-id="bd4c5-118">イベントが最初にトリガーされたとき、プル クライアント上のローカル構成マネージャー (LCM) によって、LCM で指定された構成を取得するためのプル サーバーへの要求が行われます。</span><span class="sxs-lookup"><span data-stu-id="bd4c5-118">When the event is triggered the first time, it the Local Configuration Manager (LCM) on the pull client makes a request to the pull server to get the configuration specified in the LCM.</span></span> <span data-ttu-id="bd4c5-119">プル サーバーにその構成が存在し、最初の検証チェックに合格した場合、構成はプル クライアントに送信され、LCM によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="bd4c5-119">If that configuration exists on the pull server, and it passes initial validation checks, the configuration is transmitted to the pull client, where it is then executed by the LCM.</span></span>

<span data-ttu-id="bd4c5-120">LCM はクライアントが構成に準拠しているかどうかを、LCM の **ConfigurationModeFrequencyMins** プロパティで指定された間隔で定期的にチェックします。</span><span class="sxs-lookup"><span data-stu-id="bd4c5-120">The LCM checks that the client is in compliance with the configuration at regular intervals specified by the **ConfigurationModeFrequencyMins** property of the LCM.</span></span> <span data-ttu-id="bd4c5-121">LCM はプル サーバーで更新された構成を、LCM の **RefreshModeFrequency** プロパティで指定された間隔で定期的にチェックします。</span><span class="sxs-lookup"><span data-stu-id="bd4c5-121">The LCM checks for updated configurations on the pull server at regular intervals specified by the **RefreshModeFrequency** property of the LCM.</span></span> <span data-ttu-id="bd4c5-122">LCM の構成の詳細については、「[ローカル構成マネージャーの構成](metaConfig.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd4c5-122">For information about configuring the LCM, see [Configuring the Local Configuration Manager](metaConfig.md).</span></span>

<span data-ttu-id="bd4c5-123">DSC プル サーバーのセットアップについては、「[DSC Web プル サーバーのセットアップ](pullServer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd4c5-123">For more information on setting up a DSC Pull Server, see [Setting up a DSC web pull server](pullServer.md).</span></span>

<span data-ttu-id="bd4c5-124">オンライン サービスを利用してプル サーバー機能をホストする場合は、「[Azure Automation DSC の概要](https://azure.microsoft.com/en-us/documentation/articles/automation-dsc-overview/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd4c5-124">If you would prefer to take advantage of an online service to host Pull Server functionality, see the [Azure Automation DSC](https://azure.microsoft.com/en-us/documentation/articles/automation-dsc-overview/) service.</span></span>

<span data-ttu-id="bd4c5-125">次のトピックでは、プル サーバーとクライアントをセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bd4c5-125">The following topics explain how to set up pull servers and clients:</span></span>

- [<span data-ttu-id="bd4c5-126">Setting up a web pull server (Web プル サーバーのセットアップ)</span><span class="sxs-lookup"><span data-stu-id="bd4c5-126">Setting up a web pull server</span></span>](pullServer.md)
- [<span data-ttu-id="bd4c5-127">Setting up an SMB pull server (SMB プル サーバーのセットアップ)</span><span class="sxs-lookup"><span data-stu-id="bd4c5-127">Setting up an SMB pull server</span></span>](pullServerSMB.md)
- [<span data-ttu-id="bd4c5-128">Configuring a pull client (プル クライアントの構成)</span><span class="sxs-lookup"><span data-stu-id="bd4c5-128">Configuring a pull client</span></span>](pullClientConfigID.md)

