---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: ギャラリー検索構文
ms.openlocfilehash: aabcaa1f1b5b641ab5033c9ba2e358477c84a23b
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71328453"
---
# <a name="gallery-search-syntax"></a><span data-ttu-id="99eb9-103">ギャラリー検索構文</span><span class="sxs-lookup"><span data-stu-id="99eb9-103">Gallery Search Syntax</span></span>

<span data-ttu-id="99eb9-104">[PowerShell ギャラリーの Web サイト](https://www.powershellgallery.com/)を使って、PowerShell ギャラリーを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="99eb9-104">You can search the PowerShell Gallery using the [PowerShell Gallery's web site](https://www.powershellgallery.com/).</span></span>
<span data-ttu-id="99eb9-105">PowerShell ギャラリーの Web サイトでは単語、フレーズ、キーワード表現を使用して検索結果を絞り込むテキスト検索ボックスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="99eb9-105">PowerShell Gallery web site offers a text searchbox where you can use words, phrases and keyword expressions to narrow down search results.</span></span>

## <a name="search-by-keywords"></a><span data-ttu-id="99eb9-106">キーワードで検索</span><span class="sxs-lookup"><span data-stu-id="99eb9-106">Search by Keywords</span></span>

    dsc azure sql

<span data-ttu-id="99eb9-107">検索では、3 つのキーワードすべてを含む関連ドキュメントの検索が試みられ、一致するドキュメントが返されます。</span><span class="sxs-lookup"><span data-stu-id="99eb9-107">Search attempts to find relevant documents containing all 3 keywords, and return matching documents.</span></span>

## <a name="search-using-phrases-and-keywords"></a><span data-ttu-id="99eb9-108">フレーズとキーワードを使用して検索</span><span class="sxs-lookup"><span data-stu-id="99eb9-108">Search using Phrases and keywords</span></span>

    "azure sql" deployment

<span data-ttu-id="99eb9-109">引用符 ("") の間にフレーズを入力すると、個々のキーワードではなく、特定のフレーズの検索に変わります。</span><span class="sxs-lookup"><span data-stu-id="99eb9-109">Entering a phrase between quotation marks ("") change the search to look for the particular phrase instead of separate keywords.</span></span>
<span data-ttu-id="99eb9-110">一致するドキュメントには通常、大文字と小文字のバリエーション (例: "Azure SQL" など) を含む "azure sql" そのままのフレーズを含み、また通常は 'deployment' という単語も含まれます。</span><span class="sxs-lookup"><span data-stu-id="99eb9-110">Matching documents should usually contain the exact phrase "azure sql", including variations on capitalization e.g. "Azure SQL", and also usually contain the word 'deployment'.</span></span>

## <a name="filtering-on-fields"></a><span data-ttu-id="99eb9-111">フィールドのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="99eb9-111">Filtering on fields</span></span>

<span data-ttu-id="99eb9-112">特定のパッケージ ID (または 'Id'、'id') を検索するか、検索語句の前にフィールド名を付けて他の特定のフィールドを検索します。</span><span class="sxs-lookup"><span data-stu-id="99eb9-112">You can search for a specific package ID (or 'Id' or 'id'), or certain other fields by prefixing search terms with the field name.</span></span>

<span data-ttu-id="99eb9-113">検索可能フィールドは現在、'Id'、'Version'、'Tags'、'Author'、'Owner'、'Functions'、'Cmdlets'、'DscResources'、'PowerShellVersion' です。</span><span class="sxs-lookup"><span data-stu-id="99eb9-113">Currently the searchable fields are 'Id', 'Version', 'Tags', 'Author', 'Owner', 'Functions', 'Cmdlets', 'DscResources' and 'PowerShellVersion'.</span></span>

<span data-ttu-id="99eb9-114">[ID とタイトルの間の違いは何ですか。</span><span class="sxs-lookup"><span data-stu-id="99eb9-114">[What's the difference between ID and Title?</span></span> <span data-ttu-id="99eb9-115">ID とは、コンソールで使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="99eb9-115">ID is the name you use in the console.</span></span> <span data-ttu-id="99eb9-116">タイトルとは、検索結果のパッケージ ページの上部に表示される内容です。]</span><span class="sxs-lookup"><span data-stu-id="99eb9-116">Title is what is shown at the top of the package page in search results.]</span></span>

## <a name="examples"></a><span data-ttu-id="99eb9-117">例</span><span class="sxs-lookup"><span data-stu-id="99eb9-117">Examples</span></span>

    ID:PSReadline
    
<span data-ttu-id="99eb9-118">ID に "PSReadline" が含まれるパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="99eb9-118">finds packages with an ID containing "PSReadline".</span></span>

    Id:"AzureRM.Profile"

<span data-ttu-id="99eb9-119">ID フィールドで "AzureRM.Profile" のあるパッケージを検索する別の方法です。</span><span class="sxs-lookup"><span data-stu-id="99eb9-119">is another way to find packages with "AzureRM.Profile" in their ID field.</span></span>

<span data-ttu-id="99eb9-120">'Id' フィルターは部分文字列の一致のため、次のように検索した場合、</span><span class="sxs-lookup"><span data-stu-id="99eb9-120">The 'Id' filter is a substring match, so if you search for the following:</span></span>

    Id:"azure"

<span data-ttu-id="99eb9-121">これにより、"AzureRM.Profile" と "Azure.Storage" を含む結果が提供されます。</span><span class="sxs-lookup"><span data-stu-id="99eb9-121">This provides results that include AzureRM.Profile' and 'Azure.Storage'.</span></span>

<span data-ttu-id="99eb9-122">また、1 つのフィールドで複数のキーワードを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="99eb9-122">You can also search for multiple keywords in a single field.</span></span> 

    id:azure tags:intellisense

<span data-ttu-id="99eb9-123">また、二重引用符を使ってフレーズ検索を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="99eb9-123">And you can perform phrase searches using double quotes:</span></span>

    id:"azure.storage"

<span data-ttu-id="99eb9-124">DSC タグのあるすべてのパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="99eb9-124">To search all packages with DSC tag.</span></span>

    Tags:DSC

<span data-ttu-id="99eb9-125">指定した関数のあるすべてのパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="99eb9-125">To search all packages with the specified function.</span></span>

    Functions:Get-TreeSize

<span data-ttu-id="99eb9-126">指定したコマンドレットのあるすべてのパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="99eb9-126">To search all packages with the specified cmdlet.</span></span>

    Cmdlets:Get-AzureRmEnvironment

<span data-ttu-id="99eb9-127">指定した DSC リソース名のあるすべてのパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="99eb9-127">To search all packages with the specified DSC Resource name.</span></span>

    DscResources:xArchive

<span data-ttu-id="99eb9-128">指定した PowerShellVersion のあるすべてのパッケージを検索します</span><span class="sxs-lookup"><span data-stu-id="99eb9-128">To search all packages with the specified PowerShellVersion</span></span>

    PowerShellVersion:2.0

<span data-ttu-id="99eb9-129">最後に、'commands' など、サポートされていないフィールドを使用すると、単に無視され、すべてのフィールドが検索されます。</span><span class="sxs-lookup"><span data-stu-id="99eb9-129">Finally, if you use a field we don't support, such as 'commands', we'll just ignore it and search all the fields.</span></span> <span data-ttu-id="99eb9-130">そのため、次のクエリ</span><span class="sxs-lookup"><span data-stu-id="99eb9-130">So the following query</span></span>

    commands:blobs storage

<span data-ttu-id="99eb9-131">は次のクエリと同じものとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="99eb9-131">Is interpreted exactly the same as this query:</span></span>

    blobs storage
