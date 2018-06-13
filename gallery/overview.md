---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery, PsGet
title: PowerShell ギャラリー
ms.openlocfilehash: dc7e8dd7e4d96d8424a62cb3256c3164b63a3684
ms.sourcegitcommit: 01d6985ed190a222e9da1da41596f524f607a5bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "34482932"
---
# <a name="the-powershell-gallery"></a><span data-ttu-id="44ad8-103">PowerShell ギャラリー</span><span class="sxs-lookup"><span data-stu-id="44ad8-103">The PowerShell Gallery</span></span>

<span data-ttu-id="44ad8-104">PowerShell ギャラリーは、PowerShell コンテンツの中央リポジトリです。</span><span class="sxs-lookup"><span data-stu-id="44ad8-104">The PowerShell Gallery is the central repository for PowerShell content.</span></span> <span data-ttu-id="44ad8-105">ここには、PowerShell コマンドと Desired State Configuration (DSC) リソースを含む、便利な PowerShell モジュールがあります。</span><span class="sxs-lookup"><span data-stu-id="44ad8-105">In it, you can find useful PowerShell modules containing PowerShell commands and Desired State Configuration (DSC) resources.</span></span>
<span data-ttu-id="44ad8-106">また、PowerShell スクリプトもあり、その一部には一連のタスクとそのタスクの順序の概要を示す PowerShell ワークフローが含まれています。</span><span class="sxs-lookup"><span data-stu-id="44ad8-106">You can also find PowerShell scripts, some of which may contain PowerShell workflows, and which outline a set of tasks and provide sequencing for those tasks.</span></span> <span data-ttu-id="44ad8-107">この項目の一部は Microsoft によって作成されており、その他は PowerShell コミュニティによって作成されています。</span><span class="sxs-lookup"><span data-stu-id="44ad8-107">Some of these items are authored by Microsoft, and others are authored by the PowerShell community.</span></span>

## <a name="powershellget-overview"></a><span data-ttu-id="44ad8-108">PowerShellGet 概要</span><span class="sxs-lookup"><span data-stu-id="44ad8-108">PowerShellGet Overview</span></span>

<span data-ttu-id="44ad8-109">PowerShellGet モジュールには、[PowerShell ギャラリー](https://www.PowerShellGallery.com)やその他のプライベート リポジトリでモジュール、DSC リソース、ロール機能、スクリプトなどの PowerShell アーティファクトを検索、インストール、更新、公開するためのコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="44ad8-109">The PowerShellGet module contains cmdlets for discovering, installing, updating and publishing PowerShell artifacts such as Modules, DSC Resources, Role Capabilities and Scripts from the [PowerShell Gallery](https://www.PowerShellGallery.com) and other private repositories.</span></span>

## <a name="getting-started-with-the-gallery"></a><span data-ttu-id="44ad8-110">ギャラリーをお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="44ad8-110">Getting Started with the Gallery</span></span>

<span data-ttu-id="44ad8-111">ギャラリーから項目をインストールするには、最新バージョンの PowerShellGet モジュールが必要です。</span><span class="sxs-lookup"><span data-stu-id="44ad8-111">Installing items from the Gallery requires the latest version of the PowerShellGet module.</span></span>
<span data-ttu-id="44ad8-112">完全な手順については、「[PowerShellGet のインストール](installing-psget.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44ad8-112">See [Installing PowerShellGet](installing-psget.md) for complete instructions.</span></span>

<span data-ttu-id="44ad8-113">ギャラリーで PowerShellGet コマンドを使用する方法については、[[はじめに]](getting-started.md) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="44ad8-113">Check out the [Getting Started](getting-started.md) page for more information on how to use PowerShellGet commands with the Gallery.</span></span> <span data-ttu-id="44ad8-114">*Update-Help -Module PowerShellGet* を実行し、コマンドのローカル ヘルプをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="44ad8-114">You can also run *Update-Help -Module PowerShellGet* to install local help for these commands.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="44ad8-115">サポートされるオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="44ad8-115">Supported Operating Systems</span></span>

<span data-ttu-id="44ad8-116">**PowerShellGet** モジュールは、**Windows PowerShell 3.0 以降**、または **PowerShell Core 6.0 以降**を必要とします。</span><span class="sxs-lookup"><span data-stu-id="44ad8-116">The **PowerShellGet** module requires **Windows PowerShell 3.0 or newer**, or **PowerShell Core 6.0 or newer**.</span></span>

<span data-ttu-id="44ad8-117">**Windows PowerShell** の適切なバージョンは、次のオペレーティング システムに対して利用できます。</span><span class="sxs-lookup"><span data-stu-id="44ad8-117">A suitable version of **Windows PowerShell** is available for these operating systems:</span></span>

- <span data-ttu-id="44ad8-118">Windows 10</span><span class="sxs-lookup"><span data-stu-id="44ad8-118">Windows 10</span></span>
- <span data-ttu-id="44ad8-119">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="44ad8-119">Windows 8.1 Pro</span></span>
- <span data-ttu-id="44ad8-120">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="44ad8-120">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="44ad8-121">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="44ad8-121">Windows 7 SP1</span></span>
- <span data-ttu-id="44ad8-122">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="44ad8-122">Windows Server 2016</span></span>
- <span data-ttu-id="44ad8-123">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="44ad8-123">Windows Server 2012 R2</span></span>
- <span data-ttu-id="44ad8-124">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="44ad8-124">Windows Server 2008 R2 SP1</span></span>

<span data-ttu-id="44ad8-125">**PowerShellGet** には、.NET Framework 4.5 以降も必要です。</span><span class="sxs-lookup"><span data-stu-id="44ad8-125">**PowerShellGet** also requires .NET Framework 4.5 or above.</span></span> <span data-ttu-id="44ad8-126">.NET Framework 4.5 以降を[ここ](https://msdn.microsoft.com/library/5a4x27ek.aspx)からインストールできます。</span><span class="sxs-lookup"><span data-stu-id="44ad8-126">You can install .NET Framework 4.5 or above from [here](https://msdn.microsoft.com/library/5a4x27ek.aspx).</span></span>

<span data-ttu-id="44ad8-127">**PowerShell Core** では多数のオペレーティング システムがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="44ad8-127">**PowerShell Core** supports many operating systems.</span></span> <span data-ttu-id="44ad8-128">完全な一覧については、[この記事](https://blogs.msdn.microsoft.com/powershell/2018/01/10/powershell-core-6-0-generally-available-ga-and-supported/)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44ad8-128">See [this article](https://blogs.msdn.microsoft.com/powershell/2018/01/10/powershell-core-6-0-generally-available-ga-and-supported/) for a full list.</span></span>

<span data-ttu-id="44ad8-129">ギャラリーでホストされているモジュールの多くは、さまざまな OS をサポートしており、追加の要件があります。</span><span class="sxs-lookup"><span data-stu-id="44ad8-129">Many modules hosted in the gallery will support different OSes and have additional requirements.</span></span> <span data-ttu-id="44ad8-130">詳細については、モジュールのドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44ad8-130">Please refer to the documentation for the modules for more information.</span></span>

## <a name="got-a-question-have-feedback"></a><span data-ttu-id="44ad8-131">ご質問または</span><span class="sxs-lookup"><span data-stu-id="44ad8-131">Got a question?</span></span> <span data-ttu-id="44ad8-132">フィードバックがある場合は、</span><span class="sxs-lookup"><span data-stu-id="44ad8-132">Have feedback?</span></span>

<span data-ttu-id="44ad8-133">PowerShell ギャラリーと PowerShellGet の詳細を [[はじめに]](getting-started.md) ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="44ad8-133">More information about the PowerShell Gallery and PowerShellGet can be found in the [Getting Started](getting-started.md) page.</span></span> <span data-ttu-id="44ad8-134">[UserVoice](http://windowsserver.uservoice.com/forums/301869-powershell) でご意見とご感想をお寄せください。問題がございましたら、ご報告ください。</span><span class="sxs-lookup"><span data-stu-id="44ad8-134">Please provide feedback and report issues using [UserVoice](http://windowsserver.uservoice.com/forums/301869-powershell).</span></span>
