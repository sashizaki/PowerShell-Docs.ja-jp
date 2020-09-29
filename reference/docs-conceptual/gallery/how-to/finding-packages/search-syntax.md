---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: ギャラリー検索構文
ms.openlocfilehash: 9eaabc22090655076dabe177f04130738e081179
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90847002"
---
# <a name="gallery-search-syntax"></a><span data-ttu-id="78136-103">ギャラリー検索構文</span><span class="sxs-lookup"><span data-stu-id="78136-103">Gallery Search Syntax</span></span>

<span data-ttu-id="78136-104">[PowerShell ギャラリーの Web サイト](https://www.powershellgallery.com/)を使って、PowerShell ギャラリーを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="78136-104">You can search the PowerShell Gallery using the [PowerShell Gallery's web site](https://www.powershellgallery.com/).</span></span> <span data-ttu-id="78136-105">PowerShell ギャラリーの Web サイトでは単語、フレーズ、キーワード表現を使用して検索結果を絞り込むテキスト検索ボックスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="78136-105">PowerShell Gallery web site offers a text searchbox where you can use words, phrases and keyword expressions to narrow down search results.</span></span>

## <a name="search-by-keywords"></a><span data-ttu-id="78136-106">キーワードで検索</span><span class="sxs-lookup"><span data-stu-id="78136-106">Search by Keywords</span></span>

```Syntax
dsc azure sql
```

<span data-ttu-id="78136-107">検索では、3 つのキーワードすべてを含む関連ドキュメントの検索が試みられ、一致するドキュメントが返されます。</span><span class="sxs-lookup"><span data-stu-id="78136-107">Search attempts to find relevant documents containing all 3 keywords, and return matching documents.</span></span>

## <a name="search-using-phrases-and-keywords"></a><span data-ttu-id="78136-108">フレーズとキーワードを使用して検索</span><span class="sxs-lookup"><span data-stu-id="78136-108">Search using Phrases and keywords</span></span>

```Syntax
"azure sql" deployment
```

<span data-ttu-id="78136-109">引用符 ("") の間にフレーズを入力すると、個々のキーワードではなく、特定のフレーズの検索に変わります。</span><span class="sxs-lookup"><span data-stu-id="78136-109">Entering a phrase between quotation marks ("") change the search to look for the particular phrase instead of separate keywords.</span></span> <span data-ttu-id="78136-110">一致するドキュメントには通常、大文字と小文字のバリエーション (例: "Azure SQL" など) を含む "azure sql" そのままのフレーズを含み、また通常は 'deployment' という単語も含まれます。</span><span class="sxs-lookup"><span data-stu-id="78136-110">Matching documents should usually contain the exact phrase "azure sql", including variations on capitalization e.g. "Azure SQL", and also usually contain the word 'deployment'.</span></span>

## <a name="filtering-on-fields"></a><span data-ttu-id="78136-111">フィールドのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="78136-111">Filtering on fields</span></span>

<span data-ttu-id="78136-112">特定のパッケージ ID (または 'Id'、'id') を検索するか、検索語句の前にフィールド名を付けて他の特定のフィールドを検索します。</span><span class="sxs-lookup"><span data-stu-id="78136-112">You can search for a specific package ID (or 'Id' or 'id'), or certain other fields by prefixing search terms with the field name.</span></span>

<span data-ttu-id="78136-113">検索可能フィールドは現在、'Id'、'Version'、'Tags'、'Author'、'Owner'、'Functions'、'Cmdlets'、'DscResources'、'PowerShellVersion' です。</span><span class="sxs-lookup"><span data-stu-id="78136-113">Currently the searchable fields are 'Id', 'Version', 'Tags', 'Author', 'Owner', 'Functions', 'Cmdlets', 'DscResources' and 'PowerShellVersion'.</span></span>

- <span data-ttu-id="78136-114">ID とは、コンソールで使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="78136-114">ID is the name you use in the console.</span></span>
- <span data-ttu-id="78136-115">タイトルとは、検索結果のパッケージ ページの上部に表示される内容です。</span><span class="sxs-lookup"><span data-stu-id="78136-115">Title is what is shown at the top of the package page in search results.</span></span>

## <a name="examples"></a><span data-ttu-id="78136-116">例</span><span class="sxs-lookup"><span data-stu-id="78136-116">Examples</span></span>

```Syntax
ID:PSReadline
```

<span data-ttu-id="78136-117">ID に "PSReadline" が含まれるパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="78136-117">finds packages with an ID containing "PSReadline".</span></span>

```Syntax
Id:"AzureRM.Profile"
```

<span data-ttu-id="78136-118">ID フィールドで "AzureRM.Profile" のあるパッケージを検索する別の方法です。</span><span class="sxs-lookup"><span data-stu-id="78136-118">is another way to find packages with "AzureRM.Profile" in their ID field.</span></span>

<span data-ttu-id="78136-119">'Id' フィルターは部分文字列の一致のため、次のように検索した場合、</span><span class="sxs-lookup"><span data-stu-id="78136-119">The 'Id' filter is a substring match, so if you search for the following:</span></span>

```Syntax
Id:"azure"
```

<span data-ttu-id="78136-120">これにより、"AzureRM.Profile" と "Azure.Storage" を含む結果が提供されます。</span><span class="sxs-lookup"><span data-stu-id="78136-120">This provides results that include AzureRM.Profile' and 'Azure.Storage'.</span></span>

<span data-ttu-id="78136-121">また、1 つのフィールドで複数のキーワードを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="78136-121">You can also search for multiple keywords in a single field.</span></span>

```Syntax
id:azure tags:intellisense
```

<span data-ttu-id="78136-122">また、二重引用符を使ってフレーズ検索を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="78136-122">And you can perform phrase searches using double quotes:</span></span>

```Syntax
id:"azure.storage"
```

<span data-ttu-id="78136-123">DSC タグのあるすべてのパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="78136-123">To search all packages with DSC tag.</span></span>

```Syntax
Tags:DSC
```

<span data-ttu-id="78136-124">指定した関数のあるすべてのパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="78136-124">To search all packages with the specified function.</span></span>

```Syntax
Functions:Get-TreeSize
```

<span data-ttu-id="78136-125">指定したコマンドレットのあるすべてのパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="78136-125">To search all packages with the specified cmdlet.</span></span>

```Syntax
Cmdlets:Get-AzureRmEnvironment
```

<span data-ttu-id="78136-126">指定した DSC リソース名のあるすべてのパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="78136-126">To search all packages with the specified DSC Resource name.</span></span>

```Syntax
DscResources:xArchive
```

<span data-ttu-id="78136-127">指定した PowerShellVersion のあるすべてのパッケージを検索します</span><span class="sxs-lookup"><span data-stu-id="78136-127">To search all packages with the specified PowerShellVersion</span></span>

```Syntax
PowerShellVersion:2.0
```

<span data-ttu-id="78136-128">最後に、'commands' など、サポートされていないフィールドを使用すると、単に無視され、すべてのフィールドが検索されます。</span><span class="sxs-lookup"><span data-stu-id="78136-128">Finally, if you use a field we don't support, such as 'commands', we'll just ignore it and search all the fields.</span></span> <span data-ttu-id="78136-129">そのため、次のクエリ</span><span class="sxs-lookup"><span data-stu-id="78136-129">So the following query</span></span>

```Syntax
commands:blobs storage
```

<span data-ttu-id="78136-130">は次のクエリと同じものとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="78136-130">Is interpreted exactly the same as this query:</span></span>

```Syntax
blobs storage
```
