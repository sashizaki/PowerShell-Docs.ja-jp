---
ms.date: 05/22/2020
keywords: powershell,コマンドレット
title: PowerShell ドキュメントの使用方法
ms.openlocfilehash: 259eb1eea1dc7e8b5ae5730f97c938b838a320bf
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808267"
---
# <a name="how-to-use-the-powershell-documentation"></a><span data-ttu-id="30bd6-103">PowerShell ドキュメントの使用方法</span><span class="sxs-lookup"><span data-stu-id="30bd6-103">How to use the PowerShell documentation</span></span>

<span data-ttu-id="30bd6-104">PowerShell のオンライン ドキュメントへようこそ。</span><span class="sxs-lookup"><span data-stu-id="30bd6-104">Welcome to the PowerShell online documentation.</span></span> <span data-ttu-id="30bd6-105">このサイトには、次のバージョンの PowerShell のコマンドレット リファレンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="30bd6-105">This site contains cmdlet reference for the following versions of PowerShell:</span></span>

- <span data-ttu-id="30bd6-106">PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="30bd6-106">PowerShell 7</span></span>
- <span data-ttu-id="30bd6-107">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="30bd6-107">PowerShell 6</span></span>
- <span data-ttu-id="30bd6-108">PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="30bd6-108">PowerShell 5.1</span></span>

## <a name="finding-articles-and-selecting-a-version"></a><span data-ttu-id="30bd6-109">記事の検索とバージョンの選択</span><span class="sxs-lookup"><span data-stu-id="30bd6-109">Finding articles and selecting a version</span></span>

<span data-ttu-id="30bd6-110">ドキュメントでコンテンツを検索する方法が 2 とおりあります。最も簡単な方法は、バージョン セレクターの下にあるフィルター ボックスを使用することです。</span><span class="sxs-lookup"><span data-stu-id="30bd6-110">There are two ways to search for content in Docs. The simplest way is to use the filter box under the version selector.</span></span> <span data-ttu-id="30bd6-111">記事のタイトルに表示される単語を入力してください。</span><span class="sxs-lookup"><span data-stu-id="30bd6-111">Just enter a word that appears in the title of an article.</span></span> <span data-ttu-id="30bd6-112">一致する記事の一覧がページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="30bd6-112">The page displays a list of matching articles.</span></span> <span data-ttu-id="30bd6-113">その一覧からサイト全体を検索するオプションを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="30bd6-113">You can also select the option to search the entire site from that list.</span></span>

<span data-ttu-id="30bd6-114">既定では、このサイトには PowerShell の最新リリース バージョンのドキュメントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30bd6-114">By default, this site displays documentation for the latest released version of PowerShell.</span></span> <span data-ttu-id="30bd6-115">コマンドレットの中には、PowerShell のバージョンによって動作が異なるものがあります。</span><span class="sxs-lookup"><span data-stu-id="30bd6-115">Some cmdlets work differently in various versions of PowerShell.</span></span> <span data-ttu-id="30bd6-116">使用している PowerShell のバージョンのドキュメントを表示していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="30bd6-116">Be sure you are viewing the documentation for the version of PowerShell you are using.</span></span>

<span data-ttu-id="30bd6-117">ページの上部にあるバージョン ピッカーを使用し、目的の PowerShell のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="30bd6-117">Use the version picker at the top of the page to select the version of PowerShell you want.</span></span>

![バージョン ピッカー](media/how-to-use-docs/version-search.gif)

<span data-ttu-id="30bd6-119">`$PSversionTable.PSVersion` の値を調べることで、お客様が使用している PowerShell のバージョンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="30bd6-119">You can verify the version of PowerShell you are using by inspecting the `$PSversionTable.PSVersion` value.</span></span> <span data-ttu-id="30bd6-120">次の例は、Windows PowerShell v5.1 に対する出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="30bd6-120">The following example shows the output for Windows PowerShell v5.1.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      18362  145
```

## <a name="finding-articles-for-previous-versions"></a><span data-ttu-id="30bd6-121">以前のバージョンの記事の検索</span><span class="sxs-lookup"><span data-stu-id="30bd6-121">Finding articles for previous versions</span></span>

<span data-ttu-id="30bd6-122">PowerShell の以前のバージョンのドキュメントは、[以前のバージョン](https://aka.ms/PSLegacyDocs)のサイトにアーカイブされています。</span><span class="sxs-lookup"><span data-stu-id="30bd6-122">Documentation for older versions of PowerShell has been archived in our [Previous Versions](https://aka.ms/PSLegacyDocs) site.</span></span>

<span data-ttu-id="30bd6-123">このサイトには、次のトピックのドキュメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="30bd6-123">This site contains documentation for the following topics:</span></span>

- <span data-ttu-id="30bd6-124">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="30bd6-124">PowerShell 3.0</span></span>
- <span data-ttu-id="30bd6-125">PowerShell 4.0</span><span class="sxs-lookup"><span data-stu-id="30bd6-125">PowerShell 4.0</span></span>
- <span data-ttu-id="30bd6-126">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="30bd6-126">PowerShell 5.0</span></span>
- <span data-ttu-id="30bd6-127">PowerShell ワークフロー</span><span class="sxs-lookup"><span data-stu-id="30bd6-127">PowerShell Workflows</span></span>
- <span data-ttu-id="30bd6-128">PowerShell Web Access</span><span class="sxs-lookup"><span data-stu-id="30bd6-128">PowerShell Web Access</span></span>
