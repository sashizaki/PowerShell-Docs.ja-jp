---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: 意思決定者向け Desired State Configuration の概要
ms.openlocfilehash: ce554d4bb994d4b1816d9d9c24599e4ef0e1c593
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953689"
---
# <a name="desired-state-configuration-overview-for-decision-makers"></a><span data-ttu-id="0dae2-103">意思決定者向け Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="0dae2-103">Desired State Configuration Overview for Decision Makers</span></span>

<span data-ttu-id="0dae2-104">このドキュメントでは、Windows PowerShell Desired State Configuration (DSC) を使用するビジネス上の利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="0dae2-104">This document describes the business benefits of using Windows PowerShell Desired State Configuration (DSC).</span></span> <span data-ttu-id="0dae2-105">テクニカル ガイドではありません。</span><span class="sxs-lookup"><span data-stu-id="0dae2-105">It is not a technical guide.</span></span>

## <a name="what-is-desired-state-configuration"></a><span data-ttu-id="0dae2-106">Desired State Configuration とは</span><span class="sxs-lookup"><span data-stu-id="0dae2-106">What Is Desired State Configuration?</span></span>

<span data-ttu-id="0dae2-107">PowerShell Desired State Configuration は、オープン スタンダードに基づく、Windows に組み込まれた構成管理プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="0dae2-107">PowerShell Desired State Configuration is a configuration management platform built into Windows that is based on open standards.</span></span> <span data-ttu-id="0dae2-108">DSC は、展開ライフサイクル (開発、テスト、実稼働前、実稼働) の各段階、およびスケールアウト中に、機能の信頼性と一貫性を維持するために十分な柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="0dae2-108">DSC is flexible enough to function reliably and consistently in each stage of the deployment lifecycle (development, test, pre-production, production), as well as during scale-out.</span></span>

<span data-ttu-id="0dae2-109">DSC は[構成](../configurations/configurations.md)を中心としています。</span><span class="sxs-lookup"><span data-stu-id="0dae2-109">DSC centers around [configurations](../configurations/configurations.md).</span></span>
<span data-ttu-id="0dae2-110">構成とは、特定の特性を持つコンピューター ("ノード") で構成される環境を説明する読みやすいドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="0dae2-110">A configuration is an easy-to-read document that describes an environment made up of computers ("nodes") with specific characteristics.</span></span>
<span data-ttu-id="0dae2-111">これらの特性は、特定の Windows 機能が有効になっていることを確認するなどの単純な場合や、SharePoint の展開のように複雑な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0dae2-111">These characteristics can be as simple as ensuring a specific Windows feature is enabled or as complex as deploying SharePoint.</span></span>

<span data-ttu-id="0dae2-112">DSC には監視とレポートも組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="0dae2-112">DSC also has monitoring and reporting built in.</span></span>
<span data-ttu-id="0dae2-113">システムが適合しなくなった場合、DSC は警告を生成し、システムを修正するために機能することができます。</span><span class="sxs-lookup"><span data-stu-id="0dae2-113">If a system is no longer compliant, DSC can raise an alert and act to correct the system.</span></span>

## <a name="benefits-of-using-desired-state-configuration"></a><span data-ttu-id="0dae2-114">Desired State Configuration を使用する利点</span><span class="sxs-lookup"><span data-stu-id="0dae2-114">Benefits of Using Desired State Configuration</span></span>

<span data-ttu-id="0dae2-115">構成は、簡単に読み取り、保存、および更新できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="0dae2-115">Configurations are designed to be easily read, stored, and updated.</span></span>
<span data-ttu-id="0dae2-116">構成では、ターゲット デバイスをあるべき状態にするための手順を記述するのではなく、ターゲット デバイスがあるべき状態を宣言します。</span><span class="sxs-lookup"><span data-stu-id="0dae2-116">Configurations declare the state target devices should be in, instead of writing instructions for how to put them in that state.</span></span>
<span data-ttu-id="0dae2-117">これにより、DSC によって構成を学習、導入、実装、および保守するコストが非常に低く抑えられます。</span><span class="sxs-lookup"><span data-stu-id="0dae2-117">This makes it much less costly to learn, adopt, implement, and maintain configuration through DSC.</span></span>

<span data-ttu-id="0dae2-118">構成を作成することは、複雑な展開手順が "信頼できる唯一の情報源" として 1 つの場所で取得されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="0dae2-118">Creating configurations means that complex deployment steps are captured as a "single source of truth" in a single location.</span></span>
<span data-ttu-id="0dae2-119">これにより、特定の一連のマシンの展開を繰り返す場合にエラーが発生する可能性が大幅に低下します。</span><span class="sxs-lookup"><span data-stu-id="0dae2-119">This makes repeated deployments of a specific set of machines much less error-prone.</span></span>
<span data-ttu-id="0dae2-120">そして、展開の速度と信頼性を高めることで、複雑な展開も迅速に実現できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0dae2-120">In turn, making deployments faster and more reliable which enables a quick turnaround on complex deployments.</span></span>

<span data-ttu-id="0dae2-121">また、構成は [PowerShell ギャラリー](https://powershellgallery.com)で共有することもできるため、実行する必要のある作業に適した一般的なシナリオやベスト プラクティスが既に存在している可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="0dae2-121">Configurations are also shareable via the [PowerShell Gallery](https://powershellgallery.com) meaning common scenarios and best practices might already exist for the work that needs to be done.</span></span>


## <a name="desired-state-configuration-and-devops"></a><span data-ttu-id="0dae2-122">Desired State Configuration と DevOps</span><span class="sxs-lookup"><span data-stu-id="0dae2-122">Desired State Configuration and DevOps</span></span>

<span data-ttu-id="0dae2-123">DSC は [DevOps](http://blogs.technet.com/b/ashleymcglone/archive/2015/11/20/devops-for-n00bs-ie-windows-people.aspx) を念頭に置いて設計され、内部や外部に関わらず、エンド ユーザーに価値を提供することに重点を置いた、迅速な展開と反復を可能にする人、プロセス、そしてツールが組み合わされたものです。</span><span class="sxs-lookup"><span data-stu-id="0dae2-123">DSC was designed with [DevOps](http://blogs.technet.com/b/ashleymcglone/archive/2015/11/20/devops-for-n00bs-ie-windows-people.aspx) in mind, a combination of people, processes, and tools that allow for rapid deployment and iteration focused on delivering value to end users whether internal or external.</span></span>
<span data-ttu-id="0dae2-124">単一の構成によって環境を定義することで、開発者は要件を構成にエンコードし、その構成をソース管理にチェックインでき、運用チームではエラーが発生しやすい手動プロセスを使用する必要なく、コードを簡単に展開できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0dae2-124">Having a single configuration define an environment means that developers can encode their requirements into a configuration, check that configuration into source control, and operation teams can easily deploy code without having to go through error-prone manual processes.</span></span>

<span data-ttu-id="0dae2-125">構成は[データ ドリブン](../configurations/configData.md)でもあるため、開発者が関与することなく、運用側で簡単に環境を特定および変更することができます。</span><span class="sxs-lookup"><span data-stu-id="0dae2-125">Configurations are also [data-driven](../configurations/configData.md), which makes it easier for ops to identify and change environments without developer intervention.</span></span>

## <a name="desired-state-configuration-on-premises-and-off-premises"></a><span data-ttu-id="0dae2-126">オンプレミスおよびオフプレミスの Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="0dae2-126">Desired State Configuration On-Premises and Off-Premises</span></span>
<span data-ttu-id="0dae2-127">DSC を使用して、オンプレミスとオフプレミスの両方の展開を管理できます。</span><span class="sxs-lookup"><span data-stu-id="0dae2-127">DSC can be used to manage both on-premise and off-premise deployments.</span></span>
<span data-ttu-id="0dae2-128">オンプレミスのソリューションの場合、DSC では[プル サーバー](../pull-server/pullServer.md)を使用してマシンの管理を一元化し、それらの状態をレポートできます。</span><span class="sxs-lookup"><span data-stu-id="0dae2-128">For on-premise solutions, DSC has a [pull server](../pull-server/pullServer.md) that can be used to centralize management of machines and report on their status.</span></span>
<span data-ttu-id="0dae2-129">クラウド ソリューションの場合、DSC は Windows が使用可能なすべての場所で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dae2-129">For cloud solutions, DSC is usable wherever Windows is usable.</span></span>
<span data-ttu-id="0dae2-130">Azure では、DSC のレポート作成を一元化する [Azure Automation](https://azure.microsoft.com/en-us/documentation/services/automation/) など、Desired State Configuration に基づいて構築された特定のサービスも提供しています。</span><span class="sxs-lookup"><span data-stu-id="0dae2-130">There are also specific offerings from Azure built on Desired State Configuration, such as [Azure Automation](https://azure.microsoft.com/en-us/documentation/services/automation/), which centralizes reporting of DSC.</span></span>

## <a name="dsc-and-compatibility"></a><span data-ttu-id="0dae2-131">DSC と互換性</span><span class="sxs-lookup"><span data-stu-id="0dae2-131">DSC and Compatibility</span></span>

<span data-ttu-id="0dae2-132">DSC は Windows Server 2012 R2 で導入されましたが、Windows Management Framework (WMF) パッケージを使用してダウンレベル オペレーティング システムで使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dae2-132">Although DSC was introduced in Windows Server 2012 R2, it is available for down-level operating systems via the Windows Management Framework (WMF) package.</span></span>
<span data-ttu-id="0dae2-133">WMF の詳細については、[PowerShell のホーム ページ](/powershell/)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0dae2-133">More information about the WMF can be found on the [PowerShell homepage](/powershell/).</span></span>

<span data-ttu-id="0dae2-134">DSC は、Linux の管理にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="0dae2-134">DSC can also be used to manage Linux.</span></span> <span data-ttu-id="0dae2-135">詳細については、[Linux 用 DSC の概要](../getting-started/lnxGettingStarted.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0dae2-135">For more information, see [Getting Started with DSC for Linux](../getting-started/lnxGettingStarted.md).</span></span>
