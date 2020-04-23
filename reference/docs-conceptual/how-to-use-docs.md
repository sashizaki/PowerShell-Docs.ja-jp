---
ms.date: 10/20/2019
keywords: powershell,コマンドレット
title: PowerShell ドキュメントの使用方法
ms.openlocfilehash: 50b054ddc21d55946969414688306fc0d15a5adf
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "80082834"
---
# <a name="how-to-use-the-powershell-documentation"></a><span data-ttu-id="1d212-103">PowerShell ドキュメントの使用方法</span><span class="sxs-lookup"><span data-stu-id="1d212-103">How to use the PowerShell documentation</span></span>

<span data-ttu-id="1d212-104">PowerShell のオンライン ドキュメントへようこそ。</span><span class="sxs-lookup"><span data-stu-id="1d212-104">Welcome to the PowerShell online documentation.</span></span> <span data-ttu-id="1d212-105">このサイトには、次のバージョンの PowerShell のコマンドレット リファレンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1d212-105">This site contains cmdlet reference for the following versions of PowerShell:</span></span>

- <span data-ttu-id="1d212-106">PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="1d212-106">PowerShell 7</span></span>
- <span data-ttu-id="1d212-107">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="1d212-107">PowerShell 6</span></span>
- <span data-ttu-id="1d212-108">PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="1d212-108">PowerShell 5.1</span></span>

## <a name="finding-articles-and-selecting-a-version"></a><span data-ttu-id="1d212-109">記事の検索とバージョンの選択</span><span class="sxs-lookup"><span data-stu-id="1d212-109">Finding articles and selecting a version</span></span>

<span data-ttu-id="1d212-110">ドキュメントでコンテンツを検索する方法が 2 とおりあります。最も簡単な方法は、バージョン セレクターの下にあるフィルター ボックスを使用することです。</span><span class="sxs-lookup"><span data-stu-id="1d212-110">There are two ways to search for content in Docs. The simplest way is to use the filter box under the version selector.</span></span> <span data-ttu-id="1d212-111">記事のタイトルに表示される単語を入力してください。</span><span class="sxs-lookup"><span data-stu-id="1d212-111">Just enter a word that appears in the title of an article.</span></span> <span data-ttu-id="1d212-112">一致する記事の一覧がページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d212-112">The page displays a list of matching articles.</span></span> <span data-ttu-id="1d212-113">その一覧からサイト全体を検索するオプションを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="1d212-113">You can also select the option to search the entire site from that list.</span></span>

<span data-ttu-id="1d212-114">既定では、このサイトには PowerShell の最新リリース バージョンのドキュメントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d212-114">By default, this site displays documentation for the latest released version of PowerShell.</span></span> <span data-ttu-id="1d212-115">コマンドレットの中には、PowerShell のバージョンによって動作が異なるものがあります。</span><span class="sxs-lookup"><span data-stu-id="1d212-115">Some cmdlets work differently in various versions of PowerShell.</span></span> <span data-ttu-id="1d212-116">使用している PowerShell のバージョンのドキュメントを表示していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1d212-116">Be sure you are viewing the documentation for the version of PowerShell you are using.</span></span>

<span data-ttu-id="1d212-117">ページの上部にあるバージョン ピッカーを使用し、目的の PowerShell のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="1d212-117">Use the version picker at the top of the page to select the version of PowerShell you want.</span></span>

![バージョン ピッカー](media/how-to-use-docs/version-search.gif)

<span data-ttu-id="1d212-119">`$PSversionTable.PSVersion` の値を調べることで、お客様が使用している PowerShell のバージョンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1d212-119">You can verify the version of PowerShell you are using by inspecting the `$PSversionTable.PSVersion` value.</span></span> <span data-ttu-id="1d212-120">次の例は、Windows PowerShell v5.1 に対する出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="1d212-120">The following example shows the output for Windows PowerShell v5.1.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      18362  145
```
