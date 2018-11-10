---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery, PsGet
title: PowerShell ギャラリー
ms.openlocfilehash: d3e3b9d8bb3d6cefd3a3bfe79b012bb1dc1d8a2d
ms.sourcegitcommit: e76665315fd928bf85210778f1fea2be15264fea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2018
ms.locfileid: "50225620"
---
# <a name="the-powershell-gallery"></a><span data-ttu-id="2e1af-103">PowerShell ギャラリー</span><span class="sxs-lookup"><span data-stu-id="2e1af-103">The PowerShell Gallery</span></span>

<span data-ttu-id="2e1af-104">PowerShell ギャラリーは、PowerShell コンテンツの中央リポジトリです。</span><span class="sxs-lookup"><span data-stu-id="2e1af-104">The PowerShell Gallery is the central repository for PowerShell content.</span></span> <span data-ttu-id="2e1af-105">ここには、PowerShell コマンドと Desired State Configuration (DSC) リソースを含む、便利な PowerShell モジュールがあります。</span><span class="sxs-lookup"><span data-stu-id="2e1af-105">In it, you can find useful PowerShell modules containing PowerShell commands and Desired State Configuration (DSC) resources.</span></span>
<span data-ttu-id="2e1af-106">また、PowerShell スクリプトもあり、その一部には一連のタスクとそのタスクの順序の概要を示す PowerShell ワークフローが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e1af-106">You can also find PowerShell scripts, some of which may contain PowerShell workflows, and which outline a set of tasks and provide sequencing for those tasks.</span></span> <span data-ttu-id="2e1af-107">このパッケージの一部は Microsoft によって作成されており、その他は PowerShell コミュニティによって作成されています。</span><span class="sxs-lookup"><span data-stu-id="2e1af-107">Some of these packages are authored by Microsoft, and others are authored by the PowerShell community.</span></span>

## <a name="powershellget-overview"></a><span data-ttu-id="2e1af-108">PowerShellGet 概要</span><span class="sxs-lookup"><span data-stu-id="2e1af-108">PowerShellGet Overview</span></span>

<span data-ttu-id="2e1af-109">PowerShellGet モジュールには、[PowerShell ギャラリー](https://www.PowerShellGallery.com)やその他のプライベート リポジトリでモジュール、DSC リソース、ロール機能、スクリプトなどのアーティファクトを含む PowerShell パッケージを検索、インストール、更新、公開するためのコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e1af-109">The PowerShellGet module contains cmdlets for discovering, installing, updating and publishing PowerShell packages which contain artifacts such as Modules, DSC Resources, Role Capabilities and Scripts from the [PowerShell Gallery](https://www.PowerShellGallery.com) and other private repositories.</span></span>

## <a name="getting-started-with-the-gallery"></a><span data-ttu-id="2e1af-110">ギャラリーをお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="2e1af-110">Getting Started with the Gallery</span></span>

<span data-ttu-id="2e1af-111">ギャラリーからパッケージをインストールするには、最新バージョンの PowerShellGet モジュールが必要です。</span><span class="sxs-lookup"><span data-stu-id="2e1af-111">Installing packages from the Gallery requires the latest version of the PowerShellGet module.</span></span>
<span data-ttu-id="2e1af-112">完全な手順については、「[PowerShellGet のインストール](installing-psget.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e1af-112">See [Installing PowerShellGet](installing-psget.md) for complete instructions.</span></span>

<span data-ttu-id="2e1af-113">ギャラリーで PowerShellGet コマンドを使用する方法については、[[はじめに]](getting-started.md) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e1af-113">Check out the [Getting Started](getting-started.md) page for more information on how to use PowerShellGet commands with the Gallery.</span></span> <span data-ttu-id="2e1af-114">*Update-Help -Module PowerShellGet* を実行し、コマンドのローカル ヘルプをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2e1af-114">You can also run *Update-Help -Module PowerShellGet* to install local help for these commands.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="2e1af-115">サポートされるオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="2e1af-115">Supported Operating Systems</span></span>

<span data-ttu-id="2e1af-116">**PowerShellGet** モジュールは、**Windows PowerShell 3.0 以降**、または **PowerShell Core 6.0 以降**を必要とします。</span><span class="sxs-lookup"><span data-stu-id="2e1af-116">The **PowerShellGet** module requires **Windows PowerShell 3.0 or newer**, or **PowerShell Core 6.0 or newer**.</span></span>

<span data-ttu-id="2e1af-117">**Windows PowerShell** の適切なバージョンは、次のオペレーティング システムに対して利用できます。</span><span class="sxs-lookup"><span data-stu-id="2e1af-117">A suitable version of **Windows PowerShell** is available for these operating systems:</span></span>

- <span data-ttu-id="2e1af-118">Windows 10</span><span class="sxs-lookup"><span data-stu-id="2e1af-118">Windows 10</span></span>
- <span data-ttu-id="2e1af-119">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="2e1af-119">Windows 8.1 Pro</span></span>
- <span data-ttu-id="2e1af-120">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2e1af-120">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="2e1af-121">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="2e1af-121">Windows 7 SP1</span></span>
- <span data-ttu-id="2e1af-122">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2e1af-122">Windows Server 2019</span></span>
- <span data-ttu-id="2e1af-123">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="2e1af-123">Windows Server 2016</span></span>
- <span data-ttu-id="2e1af-124">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="2e1af-124">Windows Server 2012 R2</span></span>
- <span data-ttu-id="2e1af-125">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="2e1af-125">Windows Server 2008 R2 SP1</span></span>

<span data-ttu-id="2e1af-126">**PowerShellGet** には、.NET Framework 4.5 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="2e1af-126">**PowerShellGet** requires .NET Framework 4.5 or above.</span></span> <span data-ttu-id="2e1af-127">.NET Framework 4.5 以降を[ここ](https://msdn.microsoft.com/library/5a4x27ek.aspx)からインストールできます。</span><span class="sxs-lookup"><span data-stu-id="2e1af-127">You can install .NET Framework 4.5 or above from [here](https://msdn.microsoft.com/library/5a4x27ek.aspx).</span></span>

<span data-ttu-id="2e1af-128">**PowerShell Core** はクロス プラットフォームであるため、Windows、Linux、MacOS で動作し、**PowerShellGet** をこれらのシステムで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="2e1af-128">Since **PowerShell Core** is cross-platform and that means it works on Windows, Linux and MacOS, that also makes **PowerShellGet** available on those systems.</span></span> <span data-ttu-id="2e1af-129">**PowerShell Core** でサポートされるシステムの完全な一覧については、[PowerShell のインストール](/powershell/scripting/setup/installing-powershell)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e1af-129">For a full list of systems supported by **PowerShell Core** see [Installing PowerShell](/powershell/scripting/setup/installing-powershell).</span></span>

<span data-ttu-id="2e1af-130">ギャラリーでホストされているモジュールの多くは、さまざまな OS をサポートしており、追加の要件があります。</span><span class="sxs-lookup"><span data-stu-id="2e1af-130">Many modules hosted in the gallery will support different OSes and have additional requirements.</span></span> <span data-ttu-id="2e1af-131">詳細については、モジュールのドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2e1af-131">Please refer to the documentation for the modules for more information.</span></span>

## <a name="got-a-question-have-feedback"></a><span data-ttu-id="2e1af-132">ご質問または</span><span class="sxs-lookup"><span data-stu-id="2e1af-132">Got a question?</span></span> <span data-ttu-id="2e1af-133">フィードバックがある場合は、</span><span class="sxs-lookup"><span data-stu-id="2e1af-133">Have feedback?</span></span>

<span data-ttu-id="2e1af-134">PowerShell ギャラリーと PowerShellGet の詳細を [[はじめに]](getting-started.md) ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="2e1af-134">More information about the PowerShell Gallery and PowerShellGet can be found in the [Getting Started](getting-started.md) page.</span></span> <span data-ttu-id="2e1af-135">[UserVoice](http://windowsserver.uservoice.com/forums/301869-powershell) でご意見とご感想をお寄せください。問題がございましたら、ご報告ください。</span><span class="sxs-lookup"><span data-stu-id="2e1af-135">Please provide feedback and report issues using [UserVoice](http://windowsserver.uservoice.com/forums/301869-powershell).</span></span>
