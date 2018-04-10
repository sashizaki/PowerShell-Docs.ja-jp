---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: Windows PowerShell Desired State Configuration の概要
ms.openlocfilehash: 3f357ea11a388a05b73539a63e52e639ee906f68
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="windows-powershell-desired-state-configuration-overview"></a><span data-ttu-id="18415-103">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="18415-103">Windows PowerShell Desired State Configuration Overview</span></span>

> <span data-ttu-id="18415-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="18415-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="18415-105">DSC は PowerShell による管理プラットフォームであり、IT と開発インフラストラクチャを構成を用いてコードで管理できます。</span><span class="sxs-lookup"><span data-stu-id="18415-105">DSC is a management platform in PowerShell that enables you to manage your IT and development infrastructure with configuration as code.</span></span>

- <span data-ttu-id="18415-106">DSC を使用するビジネス上の利点の概要については、「[意思決定者向け Desired State Configuration の概要](decisionMaker.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="18415-106">For an overview of the business benefits of using DSC, see [Desired State Configuration Overview for Decision Makers](decisionMaker.md).</span></span>
- <span data-ttu-id="18415-107">DSC を使用するエンジニアリングの利点の概要については、[「エンジニア向けの Desired State Configuration の概要」](DscForEngineers.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="18415-107">For an overview of the engineering benefits of using DSC, see [Desired State Configuration Overview for Engineers](DscForEngineers.md).</span></span>
- <span data-ttu-id="18415-108">DSC を簡単に使用するには、[「DSC クイック スタート」](quickStart.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="18415-108">To start using DSC quickly, see [DSC quick start](quickStart.md).</span></span>

## <a name="key-concepts"></a><span data-ttu-id="18415-109">主要概念</span><span class="sxs-lookup"><span data-stu-id="18415-109">Key Concepts</span></span>

<span data-ttu-id="18415-110">DSC は、システムの構成、展開、および管理に使用する宣言型プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="18415-110">DSC is a declarative platform used for configuration, deployment, and management of systems.</span></span> <span data-ttu-id="18415-111">次の 3 つの主要なコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="18415-111">It consists of three primary components:</span></span>

- <span data-ttu-id="18415-112">[構成](configurations.md)は、リソースのインスタンスを定義および構成する宣言型の PowerShell スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="18415-112">[Configurations](configurations.md) are declarative PowerShell scripts which define and configure instances of resources.</span></span>
    <span data-ttu-id="18415-113">構成を実行すると、DSC (および構成によって呼び出されるリソース) は、構成によってレイアウトされた状態でシステムが存在するように、単に、指定されたことを実現します。</span><span class="sxs-lookup"><span data-stu-id="18415-113">Upon running the configuration, DSC (and the resources being called by the configuration) will simply “make it so”, ensuring that the system exists in the state laid out by the configuration.</span></span>
    <span data-ttu-id="18415-114">DSC 構成は、べき等でもあります。ローカル構成マネージャー (LCM) によって、構成によって宣言された状態でマシンが構成されることが、継続的に保証されます。</span><span class="sxs-lookup"><span data-stu-id="18415-114">DSC configurations are also idempotent: the Local Configuration Manager (LCM) will continue to ensure that machines are configured in whatever state the configuration declares.</span></span>
- <span data-ttu-id="18415-115">[リソース](resources.md)は DSC の "指定されたことを実現する" 部分です。</span><span class="sxs-lookup"><span data-stu-id="18415-115">[Resources](resources.md) are the "make it so" part of DSC.</span></span> <span data-ttu-id="18415-116">リソースには構成のターゲットを指定された状態で保持するコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="18415-116">They contain the code that put and keep the target of a configuration in the specified state.</span></span>
    <span data-ttu-id="18415-117">リソースは PowerShell モジュール内に存在し、ファイルまたは Windows プロセスのように汎用的なものをモデル化したり、IIS サーバーまたは Azure で実行されている VM のように具体的なものをモデル化するために作成できます。</span><span class="sxs-lookup"><span data-stu-id="18415-117">Resources reside in PowerShell modules and can be written to model something as generic as a file or a Windows process, or as specific as an IIS server or a VM running in Azure.</span></span>
- <span data-ttu-id="18415-118">[ローカル構成マネージャー (LCM)](metaConfig.md) は、DSC でのリソースと構成の間の対話を容易にするエンジンです。</span><span class="sxs-lookup"><span data-stu-id="18415-118">The [Local Configuration Manager (LCM)](metaConfig.md) is the engine by which DSC facilitates the interaction between resources and configurations.</span></span>
    <span data-ttu-id="18415-119">LCM は、リソースによって実装される制御フローを使用してシステムを定期的にポーリングし、構成によって定義された状態が維持されるようにします。</span><span class="sxs-lookup"><span data-stu-id="18415-119">The LCM regularly polls the system using the control flow implemented by resources to ensure that the state defined by a configuration is maintained.</span></span>
    <span data-ttu-id="18415-120">システムが状態外の場合、LCM はリソース内のコードに対して呼び出しを行い、構成に従って「指定されたことを実現」します。</span><span class="sxs-lookup"><span data-stu-id="18415-120">If the system is out of state, the LCM makes calls to the code in resources to “make it so” according to the configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="18415-121">参照</span><span class="sxs-lookup"><span data-stu-id="18415-121">See Also</span></span>

- [<span data-ttu-id="18415-122">DSC 構成</span><span class="sxs-lookup"><span data-stu-id="18415-122">DSC Configurations</span></span>](configurations.md)
- [<span data-ttu-id="18415-123">DSC リソース</span><span class="sxs-lookup"><span data-stu-id="18415-123">DSC Resources</span></span>](resources.md)
- [<span data-ttu-id="18415-124">ローカル構成マネージャーの構成</span><span class="sxs-lookup"><span data-stu-id="18415-124">Configuring The Local Configuration Manager</span></span>](metaConfig.md)