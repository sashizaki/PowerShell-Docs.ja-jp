---
ms.date: 09/25/2019
keywords: PowerShell, コマンドレット
title: PowerShell ドキュメントの使用方法
ms.openlocfilehash: 9e3d5828d6bdb4ef14701994f146354a041efaea
ms.sourcegitcommit: a80bb79b85deab8ae3c21de56d1ee432fdd92628
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2019
ms.locfileid: "72281654"
---
# <a name="how-to-use-the-powershell-documentation"></a><span data-ttu-id="e9848-103">PowerShell ドキュメントの使用方法</span><span class="sxs-lookup"><span data-stu-id="e9848-103">How to use the PowerShell documentation</span></span>

<span data-ttu-id="e9848-104">PowerShell のオンライン ドキュメントへようこそ。</span><span class="sxs-lookup"><span data-stu-id="e9848-104">Welcome to the PowerShell online documentation.</span></span> <span data-ttu-id="e9848-105">このサイトには、次のバージョンの PowerShell のコマンドレット リファレンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e9848-105">This site contains cmdlet reference for the following versions of PowerShell:</span></span>

- <span data-ttu-id="e9848-106">PowerShell 7 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e9848-106">PowerShell 7 (preview)</span></span>
- <span data-ttu-id="e9848-107">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="e9848-107">PowerShell 6</span></span>
- <span data-ttu-id="e9848-108">PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="e9848-108">PowerShell 5.1</span></span>
- <span data-ttu-id="e9848-109">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="e9848-109">PowerShell 5.0</span></span>
- <span data-ttu-id="e9848-110">PowerShell 4.0</span><span class="sxs-lookup"><span data-stu-id="e9848-110">PowerShell 4.0</span></span>
- <span data-ttu-id="e9848-111">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="e9848-111">PowerShell 3.0</span></span>

## <a name="selecting-your-version"></a><span data-ttu-id="e9848-112">バージョンの選択</span><span class="sxs-lookup"><span data-stu-id="e9848-112">Selecting your version</span></span>

<span data-ttu-id="e9848-113">既定では、このサイトには PowerShell の最新リリース バージョンのドキュメントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9848-113">By default, this site displays documentation for the latest released version of PowerShell.</span></span> <span data-ttu-id="e9848-114">コマンドレットの中には、PowerShell のバージョンによって動作が異なるものがあります。</span><span class="sxs-lookup"><span data-stu-id="e9848-114">Some cmdlets work differently in various versions of PowerShell.</span></span> <span data-ttu-id="e9848-115">使用している PowerShell のバージョンのドキュメントを表示していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e9848-115">Be sure you are viewing the documentation for the version of PowerShell you are using.</span></span>

<span data-ttu-id="e9848-116">ページの上部にあるバージョン ピッカーを使用し、目的の PowerShell のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="e9848-116">Use the version picker at the top of the page to select the version of PowerShell you want.</span></span>

![バージョン ピッカー](images/how-to-use-docs/picker-vall.gif)

<span data-ttu-id="e9848-118">`$PSversionTable.PSVersion` の値を調べることで、お客様が使用している PowerShell のバージョンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e9848-118">You can verify the version of PowerShell you are using by inspecting the `$PSversionTable.PSVersion` value.</span></span> <span data-ttu-id="e9848-119">次の例は、Windows PowerShell v5.1 に対する出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="e9848-119">The following example shows the output for Windows PowerShell v5.1.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      18362  145
```

## <a name="searching-for-articles"></a><span data-ttu-id="e9848-120">記事の検索</span><span class="sxs-lookup"><span data-stu-id="e9848-120">Searching for articles</span></span>

<span data-ttu-id="e9848-121">ドキュメントでコンテンツを検索する方法が 2 とおりあります。最も簡単な方法は、バージョン セレクターの下にあるフィルター ボックスを使用することです。</span><span class="sxs-lookup"><span data-stu-id="e9848-121">There are two ways to search for content in Docs. The simplest way is to use the filter box under the version selector.</span></span> <span data-ttu-id="e9848-122">記事のタイトルに表示される単語を入力してください。</span><span class="sxs-lookup"><span data-stu-id="e9848-122">Just enter a word that appears in the title of an article.</span></span> <span data-ttu-id="e9848-123">一致する記事の一覧がページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9848-123">The page displays a list of matching articles.</span></span> <span data-ttu-id="e9848-124">その一覧からサイト全体を検索するオプションを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9848-124">You can also select the option to search the entire site from that list.</span></span>

![フィルター ボックス](images/how-to-use-docs/filter-search.gif)
