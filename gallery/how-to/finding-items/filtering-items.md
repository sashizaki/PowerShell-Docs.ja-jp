---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: 検索結果のフィルター処理
ms.openlocfilehash: eafbc993a37eaee7413102ef9d669a6b07d6ff6e
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="filtering-search-results"></a><span data-ttu-id="8d8a7-103">検索結果のフィルター処理</span><span class="sxs-lookup"><span data-stu-id="8d8a7-103">Filtering search results</span></span>

<span data-ttu-id="8d8a7-104">[[項目] タブ](https://www.powershellgallery.com/items)には、PowerShell ギャラリーで利用可能なすべての項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-104">The [Items tab](https://www.powershellgallery.com/items) displays all available items in the PowerShell Gallery.</span></span>

<span data-ttu-id="8d8a7-105">項目のフィルター、並べ替え、検索には、複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-105">There are several ways to filter, sort, and search the items.</span></span>
<span data-ttu-id="8d8a7-106">特定の項目に関する詳細情報を表示するには、項目をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-106">To see more details about a particular item, click the item.</span></span>

## <a name="filter-by"></a><span data-ttu-id="8d8a7-107">フィルター条件</span><span class="sxs-lookup"><span data-stu-id="8d8a7-107">Filter By</span></span>

<span data-ttu-id="8d8a7-108">[フィルター条件] の下にあるドロップダウンでは、結果を次の条件でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-108">The drop-down under "Filter By" allows users to filter the results by:</span></span>
- <span data-ttu-id="8d8a7-109">プレリリースを含める</span><span class="sxs-lookup"><span data-stu-id="8d8a7-109">Include Prerelease</span></span>
- <span data-ttu-id="8d8a7-110">安定版パッケージのみ</span><span class="sxs-lookup"><span data-stu-id="8d8a7-110">Stable Only</span></span>

<span data-ttu-id="8d8a7-111">"プレリリース" と "安定版パッケージ" の詳細については、PowerShell チームのブログの「[Prerelease Versioning Added to PowerShellGet and PowerShell Gallery (PowerShellGet と PowerShell ギャラリーにプレリリースのバージョン管理が追加)](https://blogs.msdn.microsoft.com/powershell/2017/12/05/prerelease-versioning-added-to-powershellget-and-powershell-gallery/)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-111">For information about "Prerelease" and "Stable", see [Prerelease Versioning Added to PowerShellGet and PowerShell Gallery](https://blogs.msdn.microsoft.com/powershell/2017/12/05/prerelease-versioning-added-to-powershellget-and-powershell-gallery/) in the PowerShell Team Blog.</span></span>

<span data-ttu-id="8d8a7-112">ドロップダウンの下にあるチェック ボックスでは、結果を次の条件でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-112">The checkboxes under the drop-down allow users to filter the results by:</span></span>
- <span data-ttu-id="8d8a7-113">アイテムの種類</span><span class="sxs-lookup"><span data-stu-id="8d8a7-113">Item Types</span></span>
  - <span data-ttu-id="8d8a7-114">モジュール</span><span class="sxs-lookup"><span data-stu-id="8d8a7-114">Module</span></span>
  - <span data-ttu-id="8d8a7-115">スクリプト</span><span class="sxs-lookup"><span data-stu-id="8d8a7-115">Script</span></span>
- <span data-ttu-id="8d8a7-116">［カテゴリ］</span><span class="sxs-lookup"><span data-stu-id="8d8a7-116">Categories</span></span>
  - <span data-ttu-id="8d8a7-117">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="8d8a7-117">Cmdlet</span></span>
  - <span data-ttu-id="8d8a7-118">DSC リソース</span><span class="sxs-lookup"><span data-stu-id="8d8a7-118">DSC Resource</span></span>
  - <span data-ttu-id="8d8a7-119">機能</span><span class="sxs-lookup"><span data-stu-id="8d8a7-119">Function</span></span>
  - <span data-ttu-id="8d8a7-120">ロールの機能</span><span class="sxs-lookup"><span data-stu-id="8d8a7-120">Role Capability</span></span>
  - <span data-ttu-id="8d8a7-121">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="8d8a7-121">Workflow</span></span>

<span data-ttu-id="8d8a7-122">PowerShell ギャラリー内のモジュールのみを表示するには、[アイテムの種類] の [モジュール] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-122">To see only modules in the PowerShell Gallery, check Module in the Item Types.</span></span>
<span data-ttu-id="8d8a7-123">同様に、PowerShell ギャラリー内のスクリプトのみを表示するには、[アイテムの種類] の [スクリプト] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-123">Similarly, to see only scripts in the PowerShell Gallery, check Script in the Item Types.</span></span>

> [!NOTE]
> <span data-ttu-id="8d8a7-124">フィルターは包含です。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-124">Filters are inclusive.</span></span>
> <span data-ttu-id="8d8a7-125">例: [コマンドレット] または [関数] \(またはその両方) をオンにした場合、コマンドレットと関数の両方を含む項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-125">Example: An item containing both cmdlets and functions will appear if either Cmdlet or Function (or both) are checked.</span></span>
> <span data-ttu-id="8d8a7-126">選択されていない場合、項目は表示されません。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-126">If neither are selected, the item will not appear.</span></span>
> <span data-ttu-id="8d8a7-127">同様に、すべてのカテゴリが選択されている場合は、これらのカテゴリのいずれかを含む項目のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-127">Similarly, if all categories are selected, only items containing one of those categories will appear.</span></span>
> <span data-ttu-id="8d8a7-128">**これらのどのカテゴリにも属していない項目は表示されません。**</span><span class="sxs-lookup"><span data-stu-id="8d8a7-128">**Items that do not belong to any of those categories will not appear.**</span></span>

## <a name="sort-by"></a><span data-ttu-id="8d8a7-129">並べ替え条件</span><span class="sxs-lookup"><span data-stu-id="8d8a7-129">Sort By</span></span>

<span data-ttu-id="8d8a7-130">[並べ替え条件] ドロップダウンでは、結果を次の条件で並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-130">The Sort By drop-down allows users to sort the results by:</span></span>
- <span data-ttu-id="8d8a7-131">[人気度] - 人気度はダウンロード数によって決定します</span><span class="sxs-lookup"><span data-stu-id="8d8a7-131">Popularity - Popularity is determined by Download Count</span></span>
- <span data-ttu-id="8d8a7-132">[A - Z] - 項目名のアルファベット順です</span><span class="sxs-lookup"><span data-stu-id="8d8a7-132">A-Z - Alphabetically by item name</span></span>
- <span data-ttu-id="8d8a7-133">[最近使った項目] - 公開日に応じて項目が表示されます</span><span class="sxs-lookup"><span data-stu-id="8d8a7-133">Recent - Items appear in order of publish date</span></span>

## <a name="search-box"></a><span data-ttu-id="8d8a7-134">[検索] ボックス</span><span class="sxs-lookup"><span data-stu-id="8d8a7-134">Search Box</span></span>

<span data-ttu-id="8d8a7-135">[検索] ボックスでは、キーワードで項目を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-135">The Search Box allows users to search the items on keywords.</span></span>
<span data-ttu-id="8d8a7-136">詳細については、「[ギャラリー検索構文](search-syntax.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8d8a7-136">For more information, see [Gallery Search Syntax](search-syntax.md).</span></span>