---
ms.date: 12/01/2020
title: PowerShell ギャラリー
description: PowerShell ギャラリーは、PowerShell モジュール、スクリプト、および DSC リソースの中央リポジトリです。
ms.openlocfilehash: f1ce6a8e2d5d72ac14cf3e4854626ef612d27891
ms.sourcegitcommit: 62282bb9c36fea3b4290b9263c1cd8e9ac216e29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "96470317"
---
# <a name="the-powershell-gallery"></a><span data-ttu-id="b6a61-103">PowerShell ギャラリー</span><span class="sxs-lookup"><span data-stu-id="b6a61-103">The PowerShell Gallery</span></span>

<span data-ttu-id="b6a61-104">PowerShell ギャラリーは、PowerShell コンテンツの中央リポジトリです。</span><span class="sxs-lookup"><span data-stu-id="b6a61-104">The PowerShell Gallery is the central repository for PowerShell content.</span></span> <span data-ttu-id="b6a61-105">ここには、PowerShell コマンドと Desired State Configuration (DSC) リソースを含む、便利な PowerShell モジュールがあります。</span><span class="sxs-lookup"><span data-stu-id="b6a61-105">In it, you can find useful PowerShell modules containing PowerShell commands and Desired State Configuration (DSC) resources.</span></span>
<span data-ttu-id="b6a61-106">また、PowerShell スクリプトもあり、その一部には一連のタスクとそのタスクの順序の概要を示す PowerShell ワークフローが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b6a61-106">You can also find PowerShell scripts, some of which may contain PowerShell workflows, and which outline a set of tasks and provide sequencing for those tasks.</span></span> <span data-ttu-id="b6a61-107">このパッケージの一部は Microsoft によって作成されており、その他は PowerShell コミュニティによって作成されています。</span><span class="sxs-lookup"><span data-stu-id="b6a61-107">Some of these packages are authored by Microsoft, and others are authored by the PowerShell community.</span></span>

## <a name="powershellget-overview"></a><span data-ttu-id="b6a61-108">PowerShellGet 概要</span><span class="sxs-lookup"><span data-stu-id="b6a61-108">PowerShellGet Overview</span></span>

<span data-ttu-id="b6a61-109">PowerShellGet モジュールには、[PowerShell ギャラリー](https://www.PowerShellGallery.com)やその他のプライベート リポジトリでモジュール、DSC リソース、ロール機能、スクリプトなどのアーティファクトを含む PowerShell パッケージを検索、インストール、更新、公開するためのコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b6a61-109">The PowerShellGet module contains cmdlets for discovering, installing, updating and publishing PowerShell packages which contain artifacts such as Modules, DSC Resources, Role Capabilities and Scripts from the [PowerShell Gallery](https://www.PowerShellGallery.com) and other private repositories.</span></span>

## <a name="getting-started-with-the-gallery"></a><span data-ttu-id="b6a61-110">ギャラリーをお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="b6a61-110">Getting Started with the Gallery</span></span>

<span data-ttu-id="b6a61-111">ギャラリーからパッケージをインストールするには、最新バージョンの PowerShellGet モジュールが必要です。</span><span class="sxs-lookup"><span data-stu-id="b6a61-111">Installing packages from the Gallery requires the latest version of the PowerShellGet module.</span></span> <span data-ttu-id="b6a61-112">完全な手順については、「[PowerShellGet のインストール](installing-psget.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6a61-112">See [Installing PowerShellGet](installing-psget.md) for complete instructions.</span></span>

<span data-ttu-id="b6a61-113">ギャラリーで PowerShellGet コマンドを使用する方法については、[[はじめに]](getting-started.md) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6a61-113">Check out the [Getting Started](getting-started.md) page for more information on how to use PowerShellGet commands with the Gallery.</span></span> <span data-ttu-id="b6a61-114">*Update-Help -Module PowerShellGet* を実行し、コマンドのローカル ヘルプをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b6a61-114">You can also run *Update-Help -Module PowerShellGet* to install local help for these commands.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="b6a61-115">サポートされるオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="b6a61-115">Supported Operating Systems</span></span>

<span data-ttu-id="b6a61-116">**PowerShellGet** モジュールは **PowerShell 3.0 以降** を必要とします。</span><span class="sxs-lookup"><span data-stu-id="b6a61-116">The **PowerShellGet** module requires **PowerShell 3.0 or newer**.</span></span>

<span data-ttu-id="b6a61-117">**PowerShellGet** には、.NET Framework 4.5 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="b6a61-117">**PowerShellGet** requires .NET Framework 4.5 or above.</span></span> <span data-ttu-id="b6a61-118">詳細については、「[開発者向けの .NET Framework のインストール](/dotnet/framework/install/guide-for-developers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6a61-118">For more information, see [Install the .NET Framework for developers](/dotnet/framework/install/guide-for-developers).</span></span>

<span data-ttu-id="b6a61-119">**PowerShell Core** はクロス プラットフォームであるため、Windows、Linux、MacOS で動作し、**PowerShellGet** をこれらのシステムで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b6a61-119">Since **PowerShell Core** is cross-platform and that means it works on Windows, Linux and MacOS, that also makes **PowerShellGet** available on those systems.</span></span> <span data-ttu-id="b6a61-120">**PowerShell Core** でサポートされるシステムの完全な一覧については、[PowerShell のインストール](/powershell/scripting/install/installing-powershell)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6a61-120">For a full list of systems supported by **PowerShell Core** see [Installing PowerShell](/powershell/scripting/install/installing-powershell).</span></span>

<span data-ttu-id="b6a61-121">ギャラリーでホストされているモジュールの多くは、さまざまな OS をサポートしており、追加の要件があります。</span><span class="sxs-lookup"><span data-stu-id="b6a61-121">Many modules hosted in the gallery will support different OSes and have additional requirements.</span></span>
<span data-ttu-id="b6a61-122">詳細については、モジュールのドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b6a61-122">Please refer to the documentation for the modules for more information.</span></span>

## <a name="got-a-question-have-feedback"></a><span data-ttu-id="b6a61-123">ご質問または</span><span class="sxs-lookup"><span data-stu-id="b6a61-123">Got a question?</span></span> <span data-ttu-id="b6a61-124">ご意見およびご提案がある場合は、</span><span class="sxs-lookup"><span data-stu-id="b6a61-124">Have feedback?</span></span>

<span data-ttu-id="b6a61-125">PowerShell ギャラリーと PowerShellGet の詳細を [[はじめに]](getting-started.md) ページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="b6a61-125">More information about the PowerShell Gallery and PowerShellGet can be found in the [Getting Started](getting-started.md) page.</span></span>

<span data-ttu-id="b6a61-126">PowerShell ギャラリー サービスの現在の状態を確認するには、GitHub の [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6a61-126">To see the current status of the PowerShell Gallery services, see the [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) page on GitHub.</span></span>

<span data-ttu-id="b6a61-127">[GitHub リポジトリ](https://github.com/PowerShell/PowerShellGallery/issues)でご意見とご感想をお寄せください。問題がございましたら、ご報告ください。</span><span class="sxs-lookup"><span data-stu-id="b6a61-127">Please provide feedback and report issues the [GitHub repository](https://github.com/PowerShell/PowerShellGallery/issues).</span></span>
