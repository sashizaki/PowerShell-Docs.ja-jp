---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: e4588e8c69efb965cd33c273ad09a8bef8e9bf16
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
ms.locfileid: "34189569"
---
# <a name="extract-and-parse-structured-objects-out-of-string"></a><span data-ttu-id="71b4f-102">文字列から構造化オブジェクトを抽出して分析する</span><span class="sxs-lookup"><span data-stu-id="71b4f-102">Extract and Parse Structured Objects out of String</span></span>
<span data-ttu-id="71b4f-103">これも、ConvertFrom-String コマンドレットに追加機能を導入します。</span><span class="sxs-lookup"><span data-stu-id="71b4f-103">This also introduces some additional functionality for the ConvertFrom-String cmdlet:</span></span>

-   <span data-ttu-id="71b4f-104">既定では、エクステント テキスト プロパティを削除します。</span><span class="sxs-lookup"><span data-stu-id="71b4f-104">Removes the extent text property by default.</span></span> <span data-ttu-id="71b4f-105">これを含めるには、-IncludeExtent パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="71b4f-105">You can include it with the -IncludeExtent parameter.</span></span>

-   <span data-ttu-id="71b4f-106">MVP やコミュニティのフィードバックから多くの学習アルゴリズムのバグを修正します。</span><span class="sxs-lookup"><span data-stu-id="71b4f-106">Many learning algorithm bug fixes from MVP and community feedback.</span></span>

-   <span data-ttu-id="71b4f-107">新しい -UpdateTemplate パラメーターを使って、学習アルゴリズムの結果をテンプレート ファイル内のコメントに保存します。</span><span class="sxs-lookup"><span data-stu-id="71b4f-107">A new -UpdateTemplate parameter to save the results of the learning algorithm into a comment in the template file.</span></span> <span data-ttu-id="71b4f-108">これにより、学習プロセス (最も時間のかかる段階) が 1 回限りのコストになります。</span><span class="sxs-lookup"><span data-stu-id="71b4f-108">This makes the learning process (the slowest stage) a one-time cost.</span></span> <span data-ttu-id="71b4f-109">エンコードされた学習アルゴリズムを含むテンプレートを使って Convert-String を実行すると、ほぼ瞬時に完了します。</span><span class="sxs-lookup"><span data-stu-id="71b4f-109">Running Convert-String with a template that contains the encoded learning algorithm is now nearly instantaneous.</span></span>


<a name="extract-and-parse-structured-objects-out-of-string-content"></a><span data-ttu-id="71b4f-110">文字列コンテンツから構造化オブジェクトを抽出して分析する</span><span class="sxs-lookup"><span data-stu-id="71b4f-110">Extract and parse structured objects out of string content</span></span>
----------------------------------------------------------

<span data-ttu-id="71b4f-111">Microsoft は、[Microsoft Research](http://research.microsoft.com/) とのコラボレーションにより、新しい **ConvertFrom-String** コマンドレットを追加しました。</span><span class="sxs-lookup"><span data-stu-id="71b4f-111">In collaboration with [Microsoft Research](http://research.microsoft.com/), a new **ConvertFrom-String** cmdlet has been added.</span></span>

<span data-ttu-id="71b4f-112">このコマンドレットは、基本的な区切り記号による解析と、自動生成したサンプルに基づく解析という 2 つのモードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="71b4f-112">This cmdlet supports two modes: basic delimited parsing, and auto generated example-driven parsing.</span></span>

<span data-ttu-id="71b4f-113">区切り記号による解析では、既定で、入力を空白の位置で分割し、生成されるグループにプロパティ名を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="71b4f-113">Delimited parsing, by default, splits the input at white space, and assigns property names to the resulting groups.</span></span> <span data-ttu-id="71b4f-114">区切り記号は、カスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="71b4f-114">You can customize the delimiter:</span></span>

> <span data-ttu-id="71b4f-115">1 \[C:\\temp\] &gt;&gt; "Hello World" | ConvertFrom-String | Format-Table -Auto</span><span class="sxs-lookup"><span data-stu-id="71b4f-115">1 \[C:\\temp\] &gt;&gt; "Hello World" | ConvertFrom-String | Format-Table -Auto</span></span>

<span data-ttu-id="71b4f-116">P1    P2</span><span class="sxs-lookup"><span data-stu-id="71b4f-116">P1    P2</span></span>
--    --

<span data-ttu-id="71b4f-117">このコマンドレットは、[Microsoft Research](http://research.microsoft.com) による [FlashExtract](http://research.microsoft.com/en-us/um/people/sumitg/flashextract.html) の研究成果に基づく、自動生成したサンプルによる解析もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="71b4f-117">The cmdlet also supports auto-generated example-driven parsing based on the [FlashExtract](http://research.microsoft.com/en-us/um/people/sumitg/flashextract.html) research work in [Microsoft Research](http://research.microsoft.com).</span></span>

<span data-ttu-id="71b4f-118">まず手始めに、テキスト ベースのアドレス帳を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="71b4f-118">To get started, consider a text-based address book:</span></span>

    Ana Trujillo

    Redmond, WA

    Antonio Moreno

    Renton, WA

    Thomas Hardy

    Seattle, WA

    Christina Berglund

    Redmond, WA

    Hanna Moos

    Puyallup, WA

<span data-ttu-id="71b4f-119">テンプレートとして使ういくつかの例をファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="71b4f-119">Copy a few examples into a file, which you will use as your template:</span></span>

    Ana Trujillo

    Redmond, WA

    Antonio Moreno

    Renton, WA



<span data-ttu-id="71b4f-120">抽出するデータを中かっこで囲み、それに任意の名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="71b4f-120">Put curly braces around data that you want to extract, giving it a name as you do so.</span></span> <span data-ttu-id="71b4f-121">**Name** プロパティ (およびそれに関連付けられている他のプロパティ) は複数回出現するので、アスタリスク (\*) を使って、この結果を (1 つのレコードに一連のプロパティを抽出するのではなく) 複数のレコードに抽出することを指定します。</span><span class="sxs-lookup"><span data-stu-id="71b4f-121">Because the **Name** property (and its associated other properties) can appear multiple times, use an asterisk (\*) to indicate that this results in multiple records (rather than extracting a bunch of properties into one record):</span></span>

    {Name\*:Ana Trujillo}

    {City:Redmond}, {State:WA}

    {Name\*:Antonio Moreno}

    {City:Renton}, {State:WA}

<span data-ttu-id="71b4f-122">この一連の例から、**ConvertFrom-String** は、同様の構造を持つ入力ファイルからオブジェクト ベースの出力を自動的に抽出できるようになります。</span><span class="sxs-lookup"><span data-stu-id="71b4f-122">From this set of examples, **ConvertFrom-String** can now automatically extract object-based output from input files with similar structure.</span></span>

> <span data-ttu-id="71b4f-123">2 \[C:\\temp\]</span><span class="sxs-lookup"><span data-stu-id="71b4f-123">2 \[C:\\temp\]</span></span>
>
> <span data-ttu-id="71b4f-124">&gt;&gt; Get-Content .\\addresses.output.txt | ConvertFrom-String -TemplateFile .\\addresses.template.txt | &gt;&gt;&gt; Format-Table -Auto</span><span class="sxs-lookup"><span data-stu-id="71b4f-124">&gt;&gt; Get-Content .\\addresses.output.txt | ConvertFrom-String -TemplateFile .\\addresses.template.txt | &gt;&gt;&gt; Format-Table -Auto</span></span>
>
> <span data-ttu-id="71b4f-125">ExtentText                     Name               City     State</span><span class="sxs-lookup"><span data-stu-id="71b4f-125">ExtentText                     Name               City     State</span></span>
> ----------                     ----               ----     -----
> <span data-ttu-id="71b4f-126">Ana Trujillo...              Ana Trujillo       Redmond  WA Antonio Moreno...            Antonio Moreno     Renton   WA Thomas Hardy...              Thomas Hardy       Seattle  WA Christina Berglund...        Christina Berglund Redmond  WA Hanna Moos...                Hanna Moos         Puyallup WA</span><span class="sxs-lookup"><span data-stu-id="71b4f-126">Ana Trujillo...                Ana Trujillo       Redmond  WA Antonio Moreno...              Antonio Moreno     Renton   WA Thomas Hardy...                Thomas Hardy       Seattle  WA Christina Berglund...          Christina Berglund Redmond  WA Hanna Moos...                  Hanna Moos         Puyallup WA</span></span>

<span data-ttu-id="71b4f-127">抽出されたテキストに追加のデータ操作を行う目的で、**ExtentText** プロパティに、レコードの抽出元から未加工のテキストがキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="71b4f-127">To do additional data manipulation on extracted text, the **ExtentText** property captures the raw text from which the record was extracted.</span></span> <span data-ttu-id="71b4f-128">この機能にフィードバックを提供したり、例を書き出すのが難しいコンテンツについて相談したりするには、<psdmfb@microsoft.com> までメールでお知らせください。</span><span class="sxs-lookup"><span data-stu-id="71b4f-128">To provide feedback on this feature, or to share content for which you are having difficulty writing examples, please email <psdmfb@microsoft.com>.</span></span>
