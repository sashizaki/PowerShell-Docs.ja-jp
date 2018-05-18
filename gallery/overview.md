---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery, PsGet
title: PowerShell ギャラリー
ms.openlocfilehash: cffb2f0182ffe9072f9fbbc7f4cdfcf28de276db
ms.sourcegitcommit: e9ad4d85fd7eb72fb5bc37f6ca3ae1282ae3c6d7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
---
# <a name="the-powershell-gallery"></a><span data-ttu-id="89fc5-103">PowerShell ギャラリー</span><span class="sxs-lookup"><span data-stu-id="89fc5-103">The PowerShell Gallery</span></span>

<span data-ttu-id="89fc5-104">PowerShell ギャラリーは、PowerShell コンテンツの中央リポジトリです。</span><span class="sxs-lookup"><span data-stu-id="89fc5-104">The PowerShell Gallery is the central repository for PowerShell content.</span></span> <span data-ttu-id="89fc5-105">ここには、PowerShell コマンドと Desired State Configuration (DSC) リソースを含む、便利な PowerShell モジュールがあります。</span><span class="sxs-lookup"><span data-stu-id="89fc5-105">In it, you can find useful PowerShell modules containing PowerShell commands and Desired State Configuration (DSC) resources.</span></span>
<span data-ttu-id="89fc5-106">また、PowerShell スクリプトもあり、その一部には一連のタスクとそのタスクの順序の概要を示す PowerShell ワークフローが含まれています。</span><span class="sxs-lookup"><span data-stu-id="89fc5-106">You can also find PowerShell scripts, some of which may contain PowerShell workflows, and which outline a set of tasks and provide sequencing for those tasks.</span></span> <span data-ttu-id="89fc5-107">この項目の一部は Microsoft によって作成されており、その他は PowerShell コミュニティによって作成されています。</span><span class="sxs-lookup"><span data-stu-id="89fc5-107">Some of these items are authored by Microsoft, and others are authored by the PowerShell community.</span></span>

## <a name="powershellget-overview"></a><span data-ttu-id="89fc5-108">PowerShellGet 概要</span><span class="sxs-lookup"><span data-stu-id="89fc5-108">PowerShellGet Overview</span></span>

<span data-ttu-id="89fc5-109">PowerShellGet モジュールには、[PowerShell ギャラリー](https://www.PowerShellGallery.com)やその他のプライベート リポジトリでモジュール、DSC リソース、ロール機能、スクリプトなどの PowerShell アーティファクトを検索、インストール、更新、公開するためのコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="89fc5-109">The PowerShellGet module contains cmdlets for discovering, installing, updating and publishing PowerShell artifacts such as Modules, DSC Resources, Role Capabilities and Scripts from the [PowerShell Gallery](https://www.PowerShellGallery.com) and other private repositories.</span></span>

## <a name="getting-started-with-the-gallery"></a><span data-ttu-id="89fc5-110">ギャラリーをお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="89fc5-110">Getting Started with the Gallery</span></span>

<span data-ttu-id="89fc5-111">ギャラリーから項目をインストールするには、最新バージョンの PowerShellGet モジュールが必要です。</span><span class="sxs-lookup"><span data-stu-id="89fc5-111">Installing items from the Gallery requires the latest version of the PowerShellGet module.</span></span>
<span data-ttu-id="89fc5-112">完全な手順については、「[PowerShellGet のインストール](installing-psget.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89fc5-112">See [Installing PowerShellGet](installing-psget.md) for complete instructions.</span></span>

<span data-ttu-id="89fc5-113">ギャラリーで PowerShellGet コマンドを使用する方法については、[[はじめに]](getting-started.md) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="89fc5-113">Check out the [Getting Started](getting-started.md) page for more information on how to use PowerShellGet commands with the Gallery.</span></span> <span data-ttu-id="89fc5-114">*Update-Help -Module PowerShellGet* を実行し、コマンドのローカル ヘルプをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="89fc5-114">You can also run *Update-Help -Module PowerShellGet* to install local help for these commands.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="89fc5-115">サポートされるオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="89fc5-115">Supported Operating Systems</span></span>

<span data-ttu-id="89fc5-116">**PowerShellGet** モジュールは **PowerShell 3.0 以降**を必要とします。</span><span class="sxs-lookup"><span data-stu-id="89fc5-116">The **PowerShellGet** module requires **PowerShell 3.0 or newer**.</span></span>

<span data-ttu-id="89fc5-117">そのため、**PowerShellGet** は次のいずれかのオペレーティング システムを必要とします。</span><span class="sxs-lookup"><span data-stu-id="89fc5-117">Therefore, **PowerShellGet** requires one of the following operating systems:</span></span>

- <span data-ttu-id="89fc5-118">Windows 10</span><span class="sxs-lookup"><span data-stu-id="89fc5-118">Windows 10</span></span>
- <span data-ttu-id="89fc5-119">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="89fc5-119">Windows 8.1 Pro</span></span>
- <span data-ttu-id="89fc5-120">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="89fc5-120">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="89fc5-121">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="89fc5-121">Windows 7 SP1</span></span>
- <span data-ttu-id="89fc5-122">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="89fc5-122">Windows Server 2016</span></span>
- <span data-ttu-id="89fc5-123">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="89fc5-123">Windows Server 2012 R2</span></span>
- <span data-ttu-id="89fc5-124">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="89fc5-124">Windows Server 2008 R2 SP1</span></span>

<span data-ttu-id="89fc5-125">**PowerShellGet** には、.NET Framework 4.5 以降も必要です。</span><span class="sxs-lookup"><span data-stu-id="89fc5-125">**PowerShellGet** also requires .NET Framework 4.5 or above.</span></span> <span data-ttu-id="89fc5-126">.NET Framework 4.5 以降を[ここ](https://msdn.microsoft.com/library/5a4x27ek.aspx)からインストールできます。</span><span class="sxs-lookup"><span data-stu-id="89fc5-126">You can install .NET Framework 4.5 or above from [here](https://msdn.microsoft.com/library/5a4x27ek.aspx).</span></span>

## <a name="got-a-question-have-feedback"></a><span data-ttu-id="89fc5-127">ご質問または</span><span class="sxs-lookup"><span data-stu-id="89fc5-127">Got a question?</span></span> <span data-ttu-id="89fc5-128">フィードバックがある場合は、</span><span class="sxs-lookup"><span data-stu-id="89fc5-128">Have feedback?</span></span>

<span data-ttu-id="89fc5-129">PowerShell ギャラリーと PowerShellGet の詳細を [[はじめに]](getting-started.md) ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="89fc5-129">More information about the PowerShell Gallery and PowerShellGet can be found in the [Getting Started](getting-started.md) page.</span></span> <span data-ttu-id="89fc5-130">[UserVoice](http://windowsserver.uservoice.com/forums/301869-powershell) でご意見とご感想をお寄せください。問題がございましたら、ご報告ください。</span><span class="sxs-lookup"><span data-stu-id="89fc5-130">Please provide feedback and report issues using [UserVoice](http://windowsserver.uservoice.com/forums/301869-powershell).</span></span>