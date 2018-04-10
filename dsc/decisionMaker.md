---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: 意思決定者向け Desired State Configuration の概要
ms.openlocfilehash: 8b410420ef30b066a32864a0d08a12a8485eaa4b
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="desired-state-configuration-overview-for-decision-makers"></a><span data-ttu-id="675ea-103">意思決定者向け Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="675ea-103">Desired State Configuration Overview for Decision Makers</span></span>

<span data-ttu-id="675ea-104">このドキュメントでは、PowerShell Desired State Configuration (DSC) を使用するビジネス上の利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="675ea-104">This document describes the business benefits of using PowerShell Desired State Configuration (DSC).</span></span> <span data-ttu-id="675ea-105">テクニカル ガイドではありません。</span><span class="sxs-lookup"><span data-stu-id="675ea-105">It is not a technical guide.</span></span>

## <a name="what-is-desired-state-configuration"></a><span data-ttu-id="675ea-106">Desired State Configuration とは</span><span class="sxs-lookup"><span data-stu-id="675ea-106">What Is Desired State Configuration?</span></span>

<span data-ttu-id="675ea-107">Windows PowerShell Desired State Configuration (DSC) は、オープン スタンダードに基づく、Windows に組み込まれた構成管理プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="675ea-107">Windows PowerShell Desired State Configuration (DSC) is a configuration management platform built into Windows that is based on open standards.</span></span> <span data-ttu-id="675ea-108">DSC は、展開ライフサイクル (開発、テスト、実稼働前、実稼働) の各段階、およびスケールアウト中に、機能の信頼性と一貫性を維持するために十分な柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="675ea-108">DSC is flexible enough to function reliably and consistently in each stage of the deployment lifecycle (development, test, pre-production, production), as well as during scale-out.</span></span>

<span data-ttu-id="675ea-109">DSC は"[構成](https://msdn.microsoft.com/powershell/dsc/configurations)"を中心としています。</span><span class="sxs-lookup"><span data-stu-id="675ea-109">DSC centers around "[configurations](https://msdn.microsoft.com/powershell/dsc/configurations)".</span></span>
<span data-ttu-id="675ea-110">構成とは、特定の特性を持つコンピューター ("ノード") で構成される環境を説明する読みやすいドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="675ea-110">A configuration is an easy-to-read document that describes an environment made up of computers ("nodes") with specific characteristics.</span></span>
<span data-ttu-id="675ea-111">これらの特性は、特定の Windows 機能が有効になっていることを確認するなどの単純な場合や、SharePoint の展開のように複雑な場合があります。</span><span class="sxs-lookup"><span data-stu-id="675ea-111">These characteristics can be as simple as ensuring a specific Windows feature is enabled or as complex as deploying SharePoint.</span></span>

<span data-ttu-id="675ea-112">DSC には監視とレポートも組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="675ea-112">DSC also has monitoring and reporting built in.</span></span>
<span data-ttu-id="675ea-113">システムが適合しなくなった場合、DSC は警告を生成し、システムを修正するために機能することができます。</span><span class="sxs-lookup"><span data-stu-id="675ea-113">If a system is no longer compliant, DSC can raise an alert and act to correct the system.</span></span>

## <a name="benefits-of-using-desired-state-configuration"></a><span data-ttu-id="675ea-114">Desired State Configuration を使用する利点</span><span class="sxs-lookup"><span data-stu-id="675ea-114">Benefits of Using Desired State Configuration</span></span>

<span data-ttu-id="675ea-115">構成は、簡単に読み取り、保存、および更新できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="675ea-115">Configurations are designed to be easily read, stored, and updated.</span></span>
<span data-ttu-id="675ea-116">構成では、ターゲット デバイスをあるべき状態にするための手順を記述するのではなく、ターゲット デバイスがあるべき状態を宣言します。</span><span class="sxs-lookup"><span data-stu-id="675ea-116">Configurations declare the state target devices should be in, instead of writing instructions for how to put them in that state.</span></span>
<span data-ttu-id="675ea-117">これにより、DSC によって構成を学習、導入、実装、および保守するコストが非常に低く抑えられます。</span><span class="sxs-lookup"><span data-stu-id="675ea-117">This makes it much less costly to learn, adopt, implement, and maintain configuration through DSC.</span></span>

<span data-ttu-id="675ea-118">構成を作成することは、複雑な展開手順が "信頼できる唯一の情報源" として 1 つの場所で取得されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="675ea-118">Creating configurations means that complex deployment steps are captured as a "single source of truth" in a single location.</span></span>
<span data-ttu-id="675ea-119">これにより、特定の一連のマシンの展開を繰り返す場合にエラーが発生する可能性が大幅に低下します。</span><span class="sxs-lookup"><span data-stu-id="675ea-119">This makes repeated deployments of a specific set of machines much less error-prone.</span></span>
<span data-ttu-id="675ea-120">そして、展開の速度と信頼性を高めることで、複雑な展開も迅速に実現できるようになります。</span><span class="sxs-lookup"><span data-stu-id="675ea-120">In turn, making deployments faster and more reliable which enables a quick turnaround on complex deployments.</span></span>

<span data-ttu-id="675ea-121">また、構成は [PowerShell ギャラリー](https://powershellgallery.com)で共有することもできるため、実行する必要のある作業に適した一般的なシナリオやベスト プラクティスがすでに存在している可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="675ea-121">Configurations are also shareable via the [PowerShell Gallery](https://powershellgallery.com) meaning common scenarios and best practices might already exist for the work you need done.</span></span>


## <a name="desired-state-configuration-and-devops"></a><span data-ttu-id="675ea-122">Desired State Configuration と DevOps</span><span class="sxs-lookup"><span data-stu-id="675ea-122">Desired State Configuration and DevOps</span></span>

<span data-ttu-id="675ea-123">[DevOps](http://blogs.technet.com/b/ashleymcglone/archive/2015/11/20/devops-for-n00bs-ie-windows-people.aspx) とは、内部や外部に関わらず、エンド ユーザーに価値を提供することに重点を置いた、迅速な展開と反復を可能にする人、プロセス、そしてツールが組み合わされたものです。</span><span class="sxs-lookup"><span data-stu-id="675ea-123">[DevOps](http://blogs.technet.com/b/ashleymcglone/archive/2015/11/20/devops-for-n00bs-ie-windows-people.aspx) is a combination of people, process, and tools that allow for rapid deployment and iteration focused on delivering value to end users whether internal or external.</span></span>
<span data-ttu-id="675ea-124">DSC は、DevOps を意識して設計されました。</span><span class="sxs-lookup"><span data-stu-id="675ea-124">DSC was designed with DevOps in mind.</span></span>
<span data-ttu-id="675ea-125">単一の構成によって環境を定義することで、開発者は要件を構成にエンコードし、その構成をソース管理にチェックインでき、運用チームではエラーが発生しやすい手動プロセスを使用する必要なく、コードを簡単に展開できるようになります。</span><span class="sxs-lookup"><span data-stu-id="675ea-125">Having a single configuration define an environment means that developers can encode their requirements into a configuration, check that configuration into source control, and operations teams can easily deploy code without having to go through error-prone manual processes.</span></span>

<span data-ttu-id="675ea-126">構成は[データ ドリブン](https://msdn.microsoft.com/powershell/dsc/configdata)でもあるため、開発者が関与することなく、運用チームで簡単に環境を特定および変更することができます。</span><span class="sxs-lookup"><span data-stu-id="675ea-126">Configurations are also [data-driven](https://msdn.microsoft.com/powershell/dsc/configdata), which makes it easier for ops teams to identify and change environments without developer intervention.</span></span>

## <a name="desired-state-configuration-on--and-off-premises"></a><span data-ttu-id="675ea-127">オンプレミスおよびオフプレミスの Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="675ea-127">Desired State Configuration On- and Off-Premises</span></span>

<span data-ttu-id="675ea-128">DSC を使用して、オンプレミスとオフプレミスの両方の展開を管理できます。</span><span class="sxs-lookup"><span data-stu-id="675ea-128">DSC can be used to manage both on-premises and off-premises deployments.</span></span>
<span data-ttu-id="675ea-129">オンプレミスのソリューションの場合、DSC では[プル サーバー](https://msdn.microsoft.com/powershell/dsc/pullserver)を使用してマシンの管理を一元化し、それらの状態をレポートできます。</span><span class="sxs-lookup"><span data-stu-id="675ea-129">For on-premises solutions, DSC has a [pull server](https://msdn.microsoft.com/powershell/dsc/pullserver) that can be used to centralize management of machines and report on their status.</span></span>
<span data-ttu-id="675ea-130">クラウド ソリューションの場合、DSC は Windows が使用可能なすべての場所で使用できます。</span><span class="sxs-lookup"><span data-stu-id="675ea-130">For cloud solutions, DSC is usable wherever Windows is usable.</span></span>
<span data-ttu-id="675ea-131">Azure では、DSC のレポート作成を一元化する [Azure Automation](https://azure.microsoft.com/en-us/documentation/services/automation/) など、Desired State Configuration に基づいて構築された特定のサービスも提供しています。</span><span class="sxs-lookup"><span data-stu-id="675ea-131">There are also specific offerings from Azure built on Desired State Configuration, such as [Azure Automation](https://azure.microsoft.com/en-us/documentation/services/automation/), which centralizes reporting of DSC.</span></span>

## <a name="dsc-and-compatibility"></a><span data-ttu-id="675ea-132">DSC と互換性</span><span class="sxs-lookup"><span data-stu-id="675ea-132">DSC and Compatibility</span></span>

<span data-ttu-id="675ea-133">DSC は Windows Server 2012 R2 で導入されましたが、Windows Management Framework (WMF) パッケージを使用してダウンレベル オペレーティング システムで使用できます。</span><span class="sxs-lookup"><span data-stu-id="675ea-133">Although DSC was introduced in Windows Server 2012 R2, it is available for downlevel operating systems via the Windows Management Framework (WMF) package.</span></span>
<span data-ttu-id="675ea-134">WMF の詳細については、[PowerShell のホーム ページ](https://msdn.microsoft.com/en-us/powershell/)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="675ea-134">More information about the WMF can be found on the [PowerShell homepage](https://msdn.microsoft.com/en-us/powershell/).</span></span>

<span data-ttu-id="675ea-135">DSC は、Linux の管理にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="675ea-135">DSC can also be used to manage Linux.</span></span> <span data-ttu-id="675ea-136">詳細については、[Linux 用 DSC の概要](https://msdn.microsoft.com/en-us/powershell/dsc/lnxgettingstarted)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="675ea-136">For more information, see [Getting Started with DSC for Linux](https://msdn.microsoft.com/en-us/powershell/dsc/lnxgettingstarted).</span></span>