---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: ギャラリー検索構文
ms.openlocfilehash: 9aadb6771c85845cc3fa05cb56f0194b060d1c1b
ms.sourcegitcommit: 98b7cfd8ad5718efa8e320526ca76c3cc4141d78
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50003777"
---
# <a name="gallery-search-syntax"></a><span data-ttu-id="5818e-103">ギャラリー検索構文</span><span class="sxs-lookup"><span data-stu-id="5818e-103">Gallery Search Syntax</span></span>

<span data-ttu-id="5818e-104">PowerShell ギャラリーでは単語、フレーズ、キーワード表現を使用して検索結果を絞り込むテキスト検索ボックスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5818e-104">PowerShell Gallery offers a text searchbox where you can use words, phrases and keyword expressions to narrow down search results.</span></span>

## <a name="search-by-keywords"></a><span data-ttu-id="5818e-105">キーワードで検索</span><span class="sxs-lookup"><span data-stu-id="5818e-105">Search by Keywords</span></span>

    dsc azure sql

<span data-ttu-id="5818e-106">検索では、3 つのキーワードを含む関連ドキュメントを検索すると、最も効果的に一致ドキュメントが返されます。</span><span class="sxs-lookup"><span data-stu-id="5818e-106">Search will do its best effort to find relevant documents containing all 3 keywords, and return matching documents.</span></span>

## <a name="search-using-phrases-and-keywords"></a><span data-ttu-id="5818e-107">フレーズとキーワードを使用して検索</span><span class="sxs-lookup"><span data-stu-id="5818e-107">Search using Phrases and keywords</span></span>

    "azure sql" deployment

<span data-ttu-id="5818e-108">引用符 ("") の間にフレーズを入力すると、個々のキーワードではなく、特定のフレーズの検索に変わります。</span><span class="sxs-lookup"><span data-stu-id="5818e-108">Entering a phrase between quotation marks ("") change the search to look for the particular phrase instead of separate keywords.</span></span>
<span data-ttu-id="5818e-109">一致するドキュメントには通常、大文字と小文字のバリエーション (例: "Azure SQL" など) を含む "azure sql" そのままのフレーズを含み、また通常は 'deployment' という単語も含まれます。</span><span class="sxs-lookup"><span data-stu-id="5818e-109">Matching documents should usually contain the exact phrase "azure sql", including variations on capitalization e.g. "Azure SQL", and also usually contain the word 'deployment'.</span></span>

## <a name="filtering-on-fields"></a><span data-ttu-id="5818e-110">フィールドのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="5818e-110">Filtering on fields</span></span>

<span data-ttu-id="5818e-111">特定のパッケージ ID (または 'Id'、'id') を検索するか、検索語句の前にフィールド名を付けて他の特定のフィールドを検索します。</span><span class="sxs-lookup"><span data-stu-id="5818e-111">You can search for a specific package ID (or 'Id' or 'id'), or certain other fields by prefixing search terms with the field name.</span></span>

<span data-ttu-id="5818e-112">検索可能フィールドは現在、'Id'、'Version'、'Tags'、'Author'、'Owner'、'Functions'、'Cmdlets'、'DscResources'、'PowerShellVersion' です。</span><span class="sxs-lookup"><span data-stu-id="5818e-112">Currently the searchable fields are 'Id', 'Version', 'Tags', 'Author', 'Owner', 'Functions', 'Cmdlets', 'DscResources' and 'PowerShellVersion'.</span></span>

<span data-ttu-id="5818e-113">[ID とタイトルの間の違いは何ですか。</span><span class="sxs-lookup"><span data-stu-id="5818e-113">[What's the difference between ID and Title?</span></span> <span data-ttu-id="5818e-114">ID とは、コンソールで使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="5818e-114">ID is the name you use in the console.</span></span> <span data-ttu-id="5818e-115">タイトルとは、検索結果のパッケージ ページの上部に表示される内容です。]</span><span class="sxs-lookup"><span data-stu-id="5818e-115">Title is what is shown at the top of the package page in search results.]</span></span>

## <a name="examples"></a><span data-ttu-id="5818e-116">例</span><span class="sxs-lookup"><span data-stu-id="5818e-116">Examples</span></span>

    ID:"PSReadline"
    id:"AzureRM.Profile"

<span data-ttu-id="5818e-117">ID フィールドの "PSReadline" または "AzureRM.Profile" のあるパッケージをそれぞれ検索するとします。</span><span class="sxs-lookup"><span data-stu-id="5818e-117">finds packages with "PSReadline" or "AzureRM.Profile" in their ID field respectively.</span></span>

    Id:"AzureRM.Profile"

<span data-ttu-id="5818e-118">ID フィールドで "AzureRM.Profile" のあるパッケージを検索する別の方法です。</span><span class="sxs-lookup"><span data-stu-id="5818e-118">is another way to find packages with "AzureRM.Profile" in their ID field.</span></span>

<span data-ttu-id="5818e-119">'Id' フィルターは部分文字列の一致のため、次のように検索した場合、</span><span class="sxs-lookup"><span data-stu-id="5818e-119">The 'Id' filter is a substring match, so if you search for the following:</span></span>

    Id:"azure"

<span data-ttu-id="5818e-120">'AzureRM.Profile' と 'Azure.Storage' のような結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="5818e-120">You'll get results like 'AzureRM.Profile' and 'Azure.Storage'.</span></span>

<span data-ttu-id="5818e-121">また、1 つのフィールドで複数のキーワードを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="5818e-121">You can also search for multiple keywords in a single field.</span></span> <span data-ttu-id="5818e-122">または、フィールドを組み合わせて一致させます。</span><span class="sxs-lookup"><span data-stu-id="5818e-122">Or mix and match fields.</span></span>

    id:azure tags:intellisense
    id:azure id:storage

<span data-ttu-id="5818e-123">また、フレーズ検索も行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5818e-123">And you can perform phrase searches:</span></span>

    id:"azure.storage"


<span data-ttu-id="5818e-124">DSC タグのあるすべてのパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="5818e-124">To search all packages with DSC tag.</span></span>

    Tags:"DSC"

<span data-ttu-id="5818e-125">指定した関数のあるすべてのパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="5818e-125">To search all packages with the specified function.</span></span>

    Functions:"Update-AzureRM"

<span data-ttu-id="5818e-126">指定したコマンドレットのあるすべてのパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="5818e-126">To search all packages with the specified cmdlet.</span></span>

    Cmdlets:"Get-AzureRmEnvironment"

<span data-ttu-id="5818e-127">指定した DSC リソース名のあるすべてのパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="5818e-127">To search all packages with the specified DSC Resource name.</span></span>

    DscResources:"xArchive"

<span data-ttu-id="5818e-128">指定した PowerShellVersion のあるすべてのパッケージを検索します</span><span class="sxs-lookup"><span data-stu-id="5818e-128">To search all packages with the specified PowerShellVersion</span></span>

    PowerShellVersion:"5.0"
    PowerShellVersion:"3.0"
    PowerShellVersion:"2.0"


<span data-ttu-id="5818e-129">最後に、'commands' など、サポートされていないフィールドを使用すると、単に無視され、すべてのフィールドが検索されます。</span><span class="sxs-lookup"><span data-stu-id="5818e-129">Finally, if you use a field we don't support, such as 'commands', we'll just ignore it and search all the fields.</span></span> <span data-ttu-id="5818e-130">そのため、次のクエリ</span><span class="sxs-lookup"><span data-stu-id="5818e-130">So the following query</span></span>

    commands:blobs storage

<span data-ttu-id="5818e-131">は次のクエリと同じものとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="5818e-131">Is interpreted exactly the same as this query:</span></span>

    blobs storage
