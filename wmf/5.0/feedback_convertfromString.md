---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: fcf2adf67f36edb534df3e2a849459fb20e1c2de
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085356"
---
# <a name="extract-and-parse-structured-objects-out-of-string"></a><span data-ttu-id="1d7dd-102">文字列から構造化オブジェクトを抽出して分析する</span><span class="sxs-lookup"><span data-stu-id="1d7dd-102">Extract and Parse Structured Objects out of String</span></span>

<span data-ttu-id="1d7dd-103">また、`ConvertFrom-String` コマンドレットの追加機能についても説明します。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-103">This also introduces some additional functionality for the `ConvertFrom-String` cmdlet:</span></span>

- <span data-ttu-id="1d7dd-104">既定では、エクステント テキスト プロパティを削除します。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-104">Removes the extent text property by default.</span></span> <span data-ttu-id="1d7dd-105">これを含めるには、-IncludeExtent パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-105">You can include it with the -IncludeExtent parameter.</span></span>

- <span data-ttu-id="1d7dd-106">MVP やコミュニティのフィードバックから多くの学習アルゴリズムのバグを修正します。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-106">Many learning algorithm bug fixes from MVP and community feedback.</span></span>

- <span data-ttu-id="1d7dd-107">新しい -UpdateTemplate パラメーターを使って、学習アルゴリズムの結果をテンプレート ファイル内のコメントに保存します。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-107">A new -UpdateTemplate parameter to save the results of the learning algorithm into a comment in the template file.</span></span> <span data-ttu-id="1d7dd-108">これにより、学習プロセス (最も時間のかかる段階) が 1 回限りのコストになります。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-108">This makes the learning process (the slowest stage) a one-time cost.</span></span> <span data-ttu-id="1d7dd-109">エンコードされた学習アルゴリズムを含むテンプレートを使って Convert-String を実行すると、ほぼ瞬時に完了します。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-109">Running Convert-String with a template that contains the encoded learning algorithm is now nearly instantaneous.</span></span>

## <a name="extract-and-parse-structured-objects-out-of-string-content"></a><span data-ttu-id="1d7dd-110">文字列コンテンツから構造化オブジェクトを抽出して分析する</span><span class="sxs-lookup"><span data-stu-id="1d7dd-110">Extract and parse structured objects out of string content</span></span>

<span data-ttu-id="1d7dd-111">[Microsoft Research](https://www.microsoft.com/en-us/research/?from=http%3A%2F%2Fresearch.microsoft.com%2F) とのコラボレーションにより、新しい `ConvertFrom-String` コマンドレットが追加されました。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-111">In collaboration with [Microsoft Research](https://www.microsoft.com/en-us/research/?from=http%3A%2F%2Fresearch.microsoft.com%2F), a new `ConvertFrom-String` cmdlet has been added.</span></span>

<span data-ttu-id="1d7dd-112">このコマンドレットは、基本的な区切り記号による解析と、自動生成したサンプルに基づく解析という 2 つのモードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-112">This cmdlet supports two modes: basic delimited parsing, and auto generated example-driven parsing.</span></span>

<span data-ttu-id="1d7dd-113">区切り記号による解析では、既定で、入力を空白の位置で分割し、生成されるグループにプロパティ名を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-113">Delimited parsing, by default, splits the input at white space, and assigns property names to the resulting groups.</span></span> <span data-ttu-id="1d7dd-114">区切り記号は、カスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-114">You can customize the delimiter:</span></span>

```powershell
"Hello World" | ConvertFrom-String | Format-Table -Auto
```

```output
P1     P2
--     --
Hello  World
```

<span data-ttu-id="1d7dd-115">このコマンドレットは、[Microsoft Research](https://www.microsoft.com/en-us/research/?from=http%3A%2F%2Fresearch.microsoft.com%2F) による [FlashExtract](https://www.microsoft.com/en-us/research/publication/flashextract-framework-data-extraction-examples/?from=http%3A%2F%2Fresearch.microsoft.com%2Fen-us%2Fum%2Fpeople%2Fsumitg%2Fflashextract.html) の研究成果に基づく、自動生成したサンプルによる解析もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-115">The cmdlet also supports auto-generated example-driven parsing based on the [FlashExtract](https://www.microsoft.com/en-us/research/publication/flashextract-framework-data-extraction-examples/?from=http%3A%2F%2Fresearch.microsoft.com%2Fen-us%2Fum%2Fpeople%2Fsumitg%2Fflashextract.html) research work in [Microsoft Research](https://www.microsoft.com/en-us/research/?from=http%3A%2F%2Fresearch.microsoft.com%2F).</span></span>

<span data-ttu-id="1d7dd-116">まず手始めに、テキスト ベースのアドレス帳を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-116">To get started, consider a text-based address book:</span></span>

```
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
```

<span data-ttu-id="1d7dd-117">テンプレートとして使ういくつかの例をファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-117">Copy a few examples into a file, which you will use as your template:</span></span>

```
    Ana Trujillo

    Redmond, WA

    Antonio Moreno

    Renton, WA
```

<span data-ttu-id="1d7dd-118">抽出するデータを中かっこで囲み、それに任意の名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-118">Put curly braces around data that you want to extract, giving it a name as you do so.</span></span> <span data-ttu-id="1d7dd-119">**Name** プロパティ (およびそれに関連付けられている他のプロパティ) は複数回出現するので、アスタリスク (\*) を使って、この結果を (1 つのレコードに一連のプロパティを抽出するのではなく) 複数のレコードに抽出することを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-119">Because the **Name** property (and its associated other properties) can appear multiple times, use an asterisk (\*) to indicate that this results in multiple records (rather than extracting a bunch of properties into one record):</span></span>

```
    {Name\*:Ana Trujillo}

    {City:Redmond}, {State:WA}

    {Name\*:Antonio Moreno}

    {City:Renton}, {State:WA}
```

<span data-ttu-id="1d7dd-120">この一連の例から、`ConvertFrom-String` で、同様の構造を持つ入力ファイルからオブジェクト ベースの出力を自動的に抽出できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-120">From this set of examples, `ConvertFrom-String` can now automatically extract object-based output from input files with similar structure.</span></span>

```powershell
Get-Content .\addresses.output.txt | ConvertFrom-String -TemplateFile .\addresses.template.txt | Format-Table -Auto
```

```output
ExtentText                     Name               City     State
----------                     ----               ----     -----
Ana Trujillo...                Ana Trujillo       Redmond  WA
Antonio Moreno...              Antonio Moreno     Renton   WA
Thomas Hardy...                Thomas Hardy       Seattle  WA
Christina Berglund...          Christina Berglund Redmond  WA
Hanna Moos...                  Hanna Moos         Puyallup WA
```

<span data-ttu-id="1d7dd-121">抽出されたテキストに追加のデータ操作を行う目的で、**ExtentText** プロパティに、レコードの抽出元から未加工のテキストがキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-121">To do additional data manipulation on extracted text, the **ExtentText** property captures the raw text from which the record was extracted.</span></span> <span data-ttu-id="1d7dd-122">この機能にフィードバックを提供したり、例を書き出すのが難しいコンテンツについて相談したりするには、<psdmfb@microsoft.com> までメールでお知らせください。</span><span class="sxs-lookup"><span data-stu-id="1d7dd-122">To provide feedback on this feature, or to share content for which you are having difficulty writing examples, please email <psdmfb@microsoft.com>.</span></span>