---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: ギャラリー検索構文
ms.openlocfilehash: aabcaa1f1b5b641ab5033c9ba2e358477c84a23b
ms.sourcegitcommit: e24525046dd37166b9d83eeecdc534726316f429
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2018
ms.locfileid: "52742858"
---
# <a name="gallery-search-syntax"></a><span data-ttu-id="98d93-103">ギャラリー検索構文</span><span class="sxs-lookup"><span data-stu-id="98d93-103">Gallery Search Syntax</span></span>

<span data-ttu-id="98d93-104">使用して、PowerShell ギャラリーを検索することができます、 [PowerShell ギャラリーの web サイト](https://www.powershellgallery.com/)します。</span><span class="sxs-lookup"><span data-stu-id="98d93-104">You can search the PowerShell Gallery using the [PowerShell Gallery's web site](https://www.powershellgallery.com/).</span></span>
<span data-ttu-id="98d93-105">PowerShell ギャラリーの web サイトでは、検索結果を絞り込むために単語、フレーズ、キーワード表現を使用できるテキストの検索ボックスを提供します。</span><span class="sxs-lookup"><span data-stu-id="98d93-105">PowerShell Gallery web site offers a text searchbox where you can use words, phrases and keyword expressions to narrow down search results.</span></span>

## <a name="search-by-keywords"></a><span data-ttu-id="98d93-106">キーワードで検索</span><span class="sxs-lookup"><span data-stu-id="98d93-106">Search by Keywords</span></span>

    dsc azure sql

<span data-ttu-id="98d93-107">検索は、3 つのキーワードを含む関連ドキュメントを検索して一致するドキュメントを返すを試行します。</span><span class="sxs-lookup"><span data-stu-id="98d93-107">Search attempts to find relevant documents containing all 3 keywords, and return matching documents.</span></span>

## <a name="search-using-phrases-and-keywords"></a><span data-ttu-id="98d93-108">フレーズとキーワードを使用して検索</span><span class="sxs-lookup"><span data-stu-id="98d93-108">Search using Phrases and keywords</span></span>

    "azure sql" deployment

<span data-ttu-id="98d93-109">引用符 ("") の間にフレーズを入力すると、個々のキーワードではなく、特定のフレーズの検索に変わります。</span><span class="sxs-lookup"><span data-stu-id="98d93-109">Entering a phrase between quotation marks ("") change the search to look for the particular phrase instead of separate keywords.</span></span>
<span data-ttu-id="98d93-110">一致するドキュメントには通常、大文字と小文字のバリエーション (例: "Azure SQL" など) を含む "azure sql" そのままのフレーズを含み、また通常は 'deployment' という単語も含まれます。</span><span class="sxs-lookup"><span data-stu-id="98d93-110">Matching documents should usually contain the exact phrase "azure sql", including variations on capitalization e.g. "Azure SQL", and also usually contain the word 'deployment'.</span></span>

## <a name="filtering-on-fields"></a><span data-ttu-id="98d93-111">フィールドのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="98d93-111">Filtering on fields</span></span>

<span data-ttu-id="98d93-112">特定のパッケージ ID (または 'Id'、'id') を検索するか、検索語句の前にフィールド名を付けて他の特定のフィールドを検索します。</span><span class="sxs-lookup"><span data-stu-id="98d93-112">You can search for a specific package ID (or 'Id' or 'id'), or certain other fields by prefixing search terms with the field name.</span></span>

<span data-ttu-id="98d93-113">検索可能フィールドは現在、'Id'、'Version'、'Tags'、'Author'、'Owner'、'Functions'、'Cmdlets'、'DscResources'、'PowerShellVersion' です。</span><span class="sxs-lookup"><span data-stu-id="98d93-113">Currently the searchable fields are 'Id', 'Version', 'Tags', 'Author', 'Owner', 'Functions', 'Cmdlets', 'DscResources' and 'PowerShellVersion'.</span></span>

<span data-ttu-id="98d93-114">[ID とタイトルの間の違いは何ですか。</span><span class="sxs-lookup"><span data-stu-id="98d93-114">[What's the difference between ID and Title?</span></span> <span data-ttu-id="98d93-115">ID とは、コンソールで使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="98d93-115">ID is the name you use in the console.</span></span> <span data-ttu-id="98d93-116">タイトルとは、検索結果のパッケージ ページの上部に表示される内容です。]</span><span class="sxs-lookup"><span data-stu-id="98d93-116">Title is what is shown at the top of the package page in search results.]</span></span>

## <a name="examples"></a><span data-ttu-id="98d93-117">例</span><span class="sxs-lookup"><span data-stu-id="98d93-117">Examples</span></span>

    ID:PSReadline
    
<span data-ttu-id="98d93-118">"PSReadline"を含む ID を持つパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="98d93-118">finds packages with an ID containing "PSReadline".</span></span>

    Id:"AzureRM.Profile"

<span data-ttu-id="98d93-119">ID フィールドで "AzureRM.Profile" のあるパッケージを検索する別の方法です。</span><span class="sxs-lookup"><span data-stu-id="98d93-119">is another way to find packages with "AzureRM.Profile" in their ID field.</span></span>

<span data-ttu-id="98d93-120">'Id' フィルターは部分文字列の一致のため、次のように検索した場合、</span><span class="sxs-lookup"><span data-stu-id="98d93-120">The 'Id' filter is a substring match, so if you search for the following:</span></span>

    Id:"azure"

<span data-ttu-id="98d93-121">これにより、結果を含む AzureRM.Profile' と 'azure.storage' します。</span><span class="sxs-lookup"><span data-stu-id="98d93-121">This provides results that include AzureRM.Profile' and 'Azure.Storage'.</span></span>

<span data-ttu-id="98d93-122">また、1 つのフィールドで複数のキーワードを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="98d93-122">You can also search for multiple keywords in a single field.</span></span> 

    id:azure tags:intellisense

<span data-ttu-id="98d93-123">二重引用符を使用して句の検索を実行できます。</span><span class="sxs-lookup"><span data-stu-id="98d93-123">And you can perform phrase searches using double quotes:</span></span>

    id:"azure.storage"

<span data-ttu-id="98d93-124">DSC タグのあるすべてのパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="98d93-124">To search all packages with DSC tag.</span></span>

    Tags:DSC

<span data-ttu-id="98d93-125">指定した関数のあるすべてのパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="98d93-125">To search all packages with the specified function.</span></span>

    Functions:Get-TreeSize

<span data-ttu-id="98d93-126">指定したコマンドレットのあるすべてのパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="98d93-126">To search all packages with the specified cmdlet.</span></span>

    Cmdlets:Get-AzureRmEnvironment

<span data-ttu-id="98d93-127">指定した DSC リソース名のあるすべてのパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="98d93-127">To search all packages with the specified DSC Resource name.</span></span>

    DscResources:xArchive

<span data-ttu-id="98d93-128">指定した PowerShellVersion のあるすべてのパッケージを検索します</span><span class="sxs-lookup"><span data-stu-id="98d93-128">To search all packages with the specified PowerShellVersion</span></span>

    PowerShellVersion:2.0

<span data-ttu-id="98d93-129">最後に、'commands' など、サポートされていないフィールドを使用すると、単に無視され、すべてのフィールドが検索されます。</span><span class="sxs-lookup"><span data-stu-id="98d93-129">Finally, if you use a field we don't support, such as 'commands', we'll just ignore it and search all the fields.</span></span> <span data-ttu-id="98d93-130">そのため、次のクエリ</span><span class="sxs-lookup"><span data-stu-id="98d93-130">So the following query</span></span>

    commands:blobs storage

<span data-ttu-id="98d93-131">は次のクエリと同じものとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="98d93-131">Is interpreted exactly the same as this query:</span></span>

    blobs storage
