---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: ギャラリー検索構文
ms.openlocfilehash: 52fca21a00bcc6e3789bceb331acf5bc771bb0f2
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
ms.locfileid: "34188413"
---
# <a name="gallery-search-syntax"></a><span data-ttu-id="9d1f0-103">ギャラリー検索構文</span><span class="sxs-lookup"><span data-stu-id="9d1f0-103">Gallery Search Syntax</span></span>

<span data-ttu-id="9d1f0-104">PowerShell ギャラリーでは単語、フレーズ、キーワード表現を使用して検索結果を絞り込むテキスト検索ボックスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-104">PowerShell Gallery offers a text searchbox where you can use words, phrases and keyword expressions to narrow down search results.</span></span>

## <a name="search-by-keywords"></a><span data-ttu-id="9d1f0-105">キーワードで検索</span><span class="sxs-lookup"><span data-stu-id="9d1f0-105">Search by Keywords</span></span>

    dsc azure sql

<span data-ttu-id="9d1f0-106">検索では、3 つのキーワードを含む関連ドキュメントを検索すると、最も効果的に一致ドキュメントが返されます。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-106">Search will do its best effort to find relevant documents containing all 3 keywords, and return matching documents.</span></span>

## <a name="search-using-phrases-and-keywords"></a><span data-ttu-id="9d1f0-107">フレーズとキーワードを使用して検索</span><span class="sxs-lookup"><span data-stu-id="9d1f0-107">Search using Phrases and keywords</span></span>

    "azure sql" deployment

<span data-ttu-id="9d1f0-108">引用符 ("") の間にフレーズを入力すると、個々のキーワードではなく、特定のフレーズの検索に変わります。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-108">Entering a phrase between quotation marks ("") change the search to look for the particular phrase instead of separate keywords.</span></span>
<span data-ttu-id="9d1f0-109">一致するドキュメントには通常、大文字と小文字のバリエーション (例: "Azure SQL" など) を含む "azure sql" そのままのフレーズを含み、また通常は 'deployment' という単語も含まれます。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-109">Matching documents should usually contain the exact phrase "azure sql", including variations on capitalization e.g. "Azure SQL", and also usually contain the word 'deployment'.</span></span>

## <a name="filtering-on-fields"></a><span data-ttu-id="9d1f0-110">フィールドのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="9d1f0-110">Filtering on fields</span></span>

<span data-ttu-id="9d1f0-111">特定の項目 ID (または 'Id'、'id') を検索するか、検索語句の前にフィールド名を付けて他の特定のフィールドを検索します。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-111">You can search for a specific item ID (or 'Id' or 'id'), or certain other fields by prefixing search terms with the field name.</span></span>

<span data-ttu-id="9d1f0-112">検索可能フィールドは現在、'Id'、'Version'、'Tags'、'Author'、'Owner'、'Functions'、'Cmdlets'、'DscResources'、'PowerShellVersion' です。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-112">Currently the searchable fields are 'Id', 'Version', 'Tags', 'Author', 'Owner', 'Functions', 'Cmdlets', 'DscResources' and 'PowerShellVersion'.</span></span>

<span data-ttu-id="9d1f0-113">[ID とタイトルの間の違いは何ですか。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-113">[What's the difference between ID and Title?</span></span> <span data-ttu-id="9d1f0-114">ID とは、コンソールで使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-114">ID is the name you use in the console.</span></span> <span data-ttu-id="9d1f0-115">タイトルとは、検索結果の項目ページの上部に表示される内容です。]</span><span class="sxs-lookup"><span data-stu-id="9d1f0-115">Title is what is shown at the top of the item page in search results.]</span></span>

## <a name="examples"></a><span data-ttu-id="9d1f0-116">例</span><span class="sxs-lookup"><span data-stu-id="9d1f0-116">Examples</span></span>

    ID:"PSReadline"
    id:"AzureRM.Profile"

<span data-ttu-id="9d1f0-117">ID フィールドの "PSReadline" または "AzureRM.Profile" 項目をそれぞれ検索するとします。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-117">finds items with "PSReadline" or "AzureRM.Profile" in their ID field respectively.</span></span>

    Id:"AzureRM.Profile"

<span data-ttu-id="9d1f0-118">ID フィールドで "AzureRM.Profile" のある項目を検索する別の方法です。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-118">is another way to find items with "AzureRM.Profile" in their ID field.</span></span>

<span data-ttu-id="9d1f0-119">'Id' フィルターは部分文字列の一致のため、次のように検索した場合、</span><span class="sxs-lookup"><span data-stu-id="9d1f0-119">The 'Id' filter is a substring match, so if you search for the following:</span></span>

    Id:"azure"

<span data-ttu-id="9d1f0-120">'AzureRM.Profile' と 'Azure.Storage' のような結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-120">You'll get results like 'AzureRM.Profile' and 'Azure.Storage'.</span></span>

<span data-ttu-id="9d1f0-121">また、1 つのフィールドで複数のキーワードを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-121">You can also search for multiple keywords in a single field.</span></span> <span data-ttu-id="9d1f0-122">または、フィールドを組み合わせて一致させます。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-122">Or mix and match fields.</span></span>

    id:azure tags:intellisense
    id:azure id:storage

<span data-ttu-id="9d1f0-123">また、フレーズ検索も行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-123">And you can perform phrase searches:</span></span>

    id:"azure.storage"


<span data-ttu-id="9d1f0-124">DSC タグのあるすべての項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-124">To search all items with DSC tag.</span></span>

    Tags:"DSC"

<span data-ttu-id="9d1f0-125">指定した関数のあるすべての項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-125">To search all items with the specified function.</span></span>

    Functions:"Update-AzureRM"

<span data-ttu-id="9d1f0-126">指定したコマンドレットのあるすべての項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-126">To search all items with the specified cmdlet.</span></span>

    Cmdlets:"Get-AzureRmEnvironment"

<span data-ttu-id="9d1f0-127">指定した DSC リソース名のあるすべての項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-127">To search all items with the specified DSC Resource name.</span></span>

    DscResources:"xArchive"

<span data-ttu-id="9d1f0-128">指定した PowerShellVersion のあるすべての項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-128">To search all items with the specified PowerShellVersion</span></span>

    PowerShellVersion:"5.0"
    PowerShellVersion:"3.0"
    PowerShellVersion:"2.0"


<span data-ttu-id="9d1f0-129">最後に、'commands' など、サポートされていないフィールドを使用すると、単に無視され、すべてのフィールドが検索されます。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-129">Finally, if you use a field we don't support, such as 'commands', we'll just ignore it and search all the fields.</span></span> <span data-ttu-id="9d1f0-130">そのため、次のクエリ</span><span class="sxs-lookup"><span data-stu-id="9d1f0-130">So the following query</span></span>

    commands:blobs storage

<span data-ttu-id="9d1f0-131">は次のクエリと同じものとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="9d1f0-131">Is interpreted exactly the same as this query:</span></span>

    blobs storage