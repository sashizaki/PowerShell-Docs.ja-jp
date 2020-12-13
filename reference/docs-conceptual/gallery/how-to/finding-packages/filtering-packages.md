---
ms.date: 06/12/2017
title: 検索結果のフィルター処理
description: この記事では、PowerShell ギャラリーでコンテンツをフィルター処理するために使用されるユーザー インターフェイスについて説明します。
ms.openlocfilehash: a769daae903e614b96be1056e3ff14eca41970bd
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389829"
---
# <a name="filtering-search-results"></a><span data-ttu-id="4d259-103">検索結果のフィルター処理</span><span class="sxs-lookup"><span data-stu-id="4d259-103">Filtering search results</span></span>

<span data-ttu-id="4d259-104">[[パッケージ] タブ](https://www.powershellgallery.com/packages)には、PowerShell ギャラリーで利用可能なすべてのパッケージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d259-104">The [Packages tab](https://www.powershellgallery.com/packages) displays all available packages in the PowerShell Gallery.</span></span>

<span data-ttu-id="4d259-105">パッケージのフィルター、並べ替え、検索には、複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="4d259-105">There are several ways to filter, sort, and search the packages.</span></span> <span data-ttu-id="4d259-106">特定のパッケージに関する詳細情報を表示するには、そのパッケージをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d259-106">To see more details about a particular package, click the package.</span></span>

## <a name="filter-by"></a><span data-ttu-id="4d259-107">フィルター条件</span><span class="sxs-lookup"><span data-stu-id="4d259-107">Filter By</span></span>

<span data-ttu-id="4d259-108">[フィルター条件] の下にあるドロップダウンでは、結果を次の条件でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="4d259-108">The drop-down under "Filter By" allows users to filter the results by:</span></span>

- <span data-ttu-id="4d259-109">プレリリースを含める</span><span class="sxs-lookup"><span data-stu-id="4d259-109">Include Prerelease</span></span>
- <span data-ttu-id="4d259-110">安定版パッケージのみ</span><span class="sxs-lookup"><span data-stu-id="4d259-110">Stable Only</span></span>

<span data-ttu-id="4d259-111">"プレリリース" と "安定版パッケージ" の詳細については、PowerShell チームのブログの「[Prerelease Versioning Added to PowerShellGet and PowerShell Gallery (PowerShellGet と PowerShell ギャラリーにプレリリースのバージョン管理が追加)](https://devblogs.microsoft.com/powershell/prerelease-versioning-added-to-powershellget-and-powershell-gallery/)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4d259-111">For information about "Prerelease" and "Stable", see [Prerelease Versioning Added to PowerShellGet and PowerShell Gallery](https://devblogs.microsoft.com/powershell/prerelease-versioning-added-to-powershellget-and-powershell-gallery/) in the PowerShell Team Blog.</span></span>

<span data-ttu-id="4d259-112">ドロップダウンの下にあるチェック ボックスでは、結果を次の条件でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="4d259-112">The checkboxes under the drop-down allow users to filter the results by:</span></span>

- <span data-ttu-id="4d259-113">パッケージの種類</span><span class="sxs-lookup"><span data-stu-id="4d259-113">Package Types</span></span>
  - <span data-ttu-id="4d259-114">Module</span><span class="sxs-lookup"><span data-stu-id="4d259-114">Module</span></span>
  - <span data-ttu-id="4d259-115">スクリプト</span><span class="sxs-lookup"><span data-stu-id="4d259-115">Script</span></span>
- <span data-ttu-id="4d259-116">Categories</span><span class="sxs-lookup"><span data-stu-id="4d259-116">Categories</span></span>
  - <span data-ttu-id="4d259-117">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="4d259-117">Cmdlet</span></span>
  - <span data-ttu-id="4d259-118">DSC リソース</span><span class="sxs-lookup"><span data-stu-id="4d259-118">DSC Resource</span></span>
  - <span data-ttu-id="4d259-119">機能</span><span class="sxs-lookup"><span data-stu-id="4d259-119">Function</span></span>
  - <span data-ttu-id="4d259-120">ロール機能</span><span class="sxs-lookup"><span data-stu-id="4d259-120">Role Capability</span></span>
  - <span data-ttu-id="4d259-121">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="4d259-121">Workflow</span></span>

<span data-ttu-id="4d259-122">PowerShell ギャラリー内のモジュールのみを表示するには、[パッケージの種類] の [モジュール] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="4d259-122">To see only modules in the PowerShell Gallery, check Module in the Package Types.</span></span> <span data-ttu-id="4d259-123">同様に、PowerShell ギャラリー内のスクリプトのみを表示するには、[パッケージの種類] の [スクリプト] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="4d259-123">Similarly, to see only scripts in the PowerShell Gallery, check Script in the Package Types.</span></span>

> [!NOTE]
> <span data-ttu-id="4d259-124">フィルターは包含です。</span><span class="sxs-lookup"><span data-stu-id="4d259-124">Filters are inclusive.</span></span> <span data-ttu-id="4d259-125">例:[コマンドレット] または [関数] (またはその両方) をオンにした場合、コマンドレットと関数の両方を含むパッケージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d259-125">Example: A package containing both cmdlets and functions will appear if either Cmdlet or Function (or both) are checked.</span></span> <span data-ttu-id="4d259-126">選択されていない場合、パッケージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="4d259-126">If neither are selected, the package will not appear.</span></span> <span data-ttu-id="4d259-127">同様に、すべてのカテゴリが選択されている場合は、これらのカテゴリのいずれかを含むパッケージのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d259-127">Similarly, if all categories are selected, only packages containing one of those categories will appear.</span></span> <span data-ttu-id="4d259-128">**これらのどのカテゴリにも属していないパッケージは表示されません。**</span><span class="sxs-lookup"><span data-stu-id="4d259-128">**Packages that do not belong to any of those categories will not appear.**</span></span>

## <a name="sort-by"></a><span data-ttu-id="4d259-129">並べ替え条件</span><span class="sxs-lookup"><span data-stu-id="4d259-129">Sort By</span></span>

<span data-ttu-id="4d259-130">[並べ替え条件] ドロップダウンでは、結果を次の条件で並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="4d259-130">The Sort By drop-down allows users to sort the results by:</span></span>

- <span data-ttu-id="4d259-131">[人気度] - 人気度はダウンロード数によって決定します</span><span class="sxs-lookup"><span data-stu-id="4d259-131">Popularity - Popularity is determined by Download Count</span></span>
- <span data-ttu-id="4d259-132">[A - Z] - パッケージ名のアルファベット順です</span><span class="sxs-lookup"><span data-stu-id="4d259-132">A-Z - Alphabetically by package name</span></span>
- <span data-ttu-id="4d259-133">[最近使ったパッケージ] - 公開日に応じてパッケージが表示されます</span><span class="sxs-lookup"><span data-stu-id="4d259-133">Recent - Packages appear in order of publish date</span></span>

## <a name="search-box"></a><span data-ttu-id="4d259-134">[検索] ボックス</span><span class="sxs-lookup"><span data-stu-id="4d259-134">Search Box</span></span>

<span data-ttu-id="4d259-135">[検索] ボックスでは、キーワードでパッケージを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="4d259-135">The Search Box allows users to search the packages on keywords.</span></span>
<span data-ttu-id="4d259-136">詳細については、「[ギャラリー検索構文](search-syntax.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4d259-136">For more information, see [Gallery Search Syntax](search-syntax.md).</span></span>
