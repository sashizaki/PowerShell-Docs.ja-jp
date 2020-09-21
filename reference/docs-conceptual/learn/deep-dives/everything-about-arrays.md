---
title: 配列について知りたかったことのすべて
description: 配列は、ほとんどのプログラミング言語の基本的な言語機能の 1 つです。
ms.date: 07/07/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: e744878844a3cfd32d6124538a44a29ba90798ab
ms.sourcegitcommit: 57df49488015e7ac17ff1df402a94441aa6d6064
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "86092101"
---
# <a name="everything-you-wanted-to-know-about-arrays"></a><span data-ttu-id="90d33-103">配列について知りたかったことのすべて</span><span class="sxs-lookup"><span data-stu-id="90d33-103">Everything you wanted to know about arrays</span></span>

<span data-ttu-id="90d33-104">[配列][] は、ほとんどのプログラミング言語の基本的な言語機能の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="90d33-104">[Arrays][] are a fundamental language feature of most programming languages.</span></span> <span data-ttu-id="90d33-105">それらは、避けることが困難な値またはオブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="90d33-105">They're a collection of values or objects that are difficult to avoid.</span></span> <span data-ttu-id="90d33-106">配列と配列が提供するすべての機能について詳しく見ていきましょう。</span><span class="sxs-lookup"><span data-stu-id="90d33-106">Let's take a close look at arrays and everything they have to offer.</span></span>

> [!NOTE]
> <span data-ttu-id="90d33-107">この記事の[オリジナル バージョン][]は、[@KevinMarquette][] 氏のブログ記事です。</span><span class="sxs-lookup"><span data-stu-id="90d33-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="90d33-108">このコンテンツを共有してくださった Kevin 氏に、PowerShell チームより感謝を申し上げます。</span><span class="sxs-lookup"><span data-stu-id="90d33-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="90d33-109">[PowerShellExplained.com][] のブログをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="90d33-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="what-is-an-array"></a><span data-ttu-id="90d33-110">配列とは</span><span class="sxs-lookup"><span data-stu-id="90d33-110">What is an array?</span></span>

<span data-ttu-id="90d33-111">まず、配列の概要と、ほとんどのプログラミング言語でのその使用方法に関する基本的な技術説明を行ってから、PowerShell でのもう 1 つの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="90d33-111">I'm going to start with a basic technical description of what arrays are and how they are used by most programming languages before I shift into the other ways PowerShell makes use of them.</span></span>

<span data-ttu-id="90d33-112">配列とは、複数の項目のコレクションとして機能するデータ構造です。</span><span class="sxs-lookup"><span data-stu-id="90d33-112">An array is a data structure that serves as a collection of multiple items.</span></span> <span data-ttu-id="90d33-113">配列を反復処理したり、インデックスを使用して個々の項目にアクセスしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="90d33-113">You can iterate over the array or access individual items using an index.</span></span> <span data-ttu-id="90d33-114">配列は、各値が他の値のすぐ隣に格納される連続したメモリ チャンクとして作成されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-114">The array is created as a sequential chunk of memory where each value is stored right next to the other.</span></span>

<span data-ttu-id="90d33-115">それぞれの詳細については、説明を進めていく中で取り上げます。</span><span class="sxs-lookup"><span data-stu-id="90d33-115">I'll touch on each of those details as we go.</span></span>

## <a name="basic-usage"></a><span data-ttu-id="90d33-116">基本的な使用方法</span><span class="sxs-lookup"><span data-stu-id="90d33-116">Basic usage</span></span>

<span data-ttu-id="90d33-117">配列はこのような PowerShell の基本機能であるため、PowerShell で使用するための簡単な構文があります。</span><span class="sxs-lookup"><span data-stu-id="90d33-117">Because arrays are such a basic feature of PowerShell, there is a simple syntax for working with them in PowerShell.</span></span>

### <a name="create-an-array"></a><span data-ttu-id="90d33-118">配列を作成する</span><span class="sxs-lookup"><span data-stu-id="90d33-118">Create an array</span></span>

<span data-ttu-id="90d33-119">空の配列を作成するには、`@()` を使用します</span><span class="sxs-lookup"><span data-stu-id="90d33-119">An empty array can be created by using `@()`</span></span>

```powershell
PS> $data = @()
PS> $data.count
0
```

<span data-ttu-id="90d33-120">配列を作成して、値をシードするには、`@()` のかっこ内に値を配置するだけです。</span><span class="sxs-lookup"><span data-stu-id="90d33-120">We can create an array and seed it with values just by placing them in the `@()` parentheses.</span></span>

```powershell
PS> $data = @('Zero','One','Two','Three')
PS> $data.count
4

PS> $data
Zero
One
Two
Three
```

<span data-ttu-id="90d33-121">この配列には項目が 4 つあります。</span><span class="sxs-lookup"><span data-stu-id="90d33-121">This array has 4 items.</span></span> <span data-ttu-id="90d33-122">`$data` 変数を呼び出すと、それらの項目の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-122">When we call the `$data` variable, we see the list of our items.</span></span> <span data-ttu-id="90d33-123">文字列の配列の場合は、文字列ごとに 1 行返されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-123">If it's an array of strings, then we get one line per string.</span></span>

<span data-ttu-id="90d33-124">配列を複数の行で宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="90d33-124">We can declare an array on multiple lines.</span></span> <span data-ttu-id="90d33-125">この場合、コンマは省略可能であり、通常は省略されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-125">The comma is optional in this case and generally left out.</span></span>

```powershell
$data = @(
    'Zero'
    'One'
    'Two'
    'Three'
)
```

<span data-ttu-id="90d33-126">そのように複数の行で配列を宣言することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="90d33-126">I prefer to declare my arrays on multiple lines like that.</span></span> <span data-ttu-id="90d33-127">複数の項目がある場合に読みやすくなるだけでなく、ソース コード管理を使用する場合に以前のバージョンと比較しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="90d33-127">Not only does it get easier to read when you have multiple items, it also makes it easier to compare to previous versions when using source control.</span></span>

#### <a name="other-syntax"></a><span data-ttu-id="90d33-128">その他の構文</span><span class="sxs-lookup"><span data-stu-id="90d33-128">Other syntax</span></span>

<span data-ttu-id="90d33-129">`@()` が配列を作成するための構文であることは普通にわかりますが、ほとんどの場合はコンマ区切りリストが使用されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-129">It's commonly understood that `@()` is the syntax for creating an array, but comma-separated lists work most of the time.</span></span>

```powershell
$data = 'Zero','One','Two','Three'
```

#### <a name="write-output-to-create-arrays"></a><span data-ttu-id="90d33-130">Write-Output で配列を作成する</span><span class="sxs-lookup"><span data-stu-id="90d33-130">Write-Output to create arrays</span></span>

<span data-ttu-id="90d33-131">注目すべき優れた小技の 1 つは、`Write-Output` を使用してコンソールですばやく文字列を作成できることです。</span><span class="sxs-lookup"><span data-stu-id="90d33-131">One cool little trick worth mentioning is that you can use `Write-Output` to quickly create strings at the console.</span></span>

```powershell
$data = Write-Output Zero One Two Three
```

<span data-ttu-id="90d33-132">これが便利なのは、パラメーターで文字列を受け入れるときに文字列を引用符で囲む必要がないからです。</span><span class="sxs-lookup"><span data-stu-id="90d33-132">This is handy because you don't have to put quotes around the strings when the parameter accepts strings.</span></span> <span data-ttu-id="90d33-133">スクリプトでこれを行うことはありませんが、コンソールでは格好の技法です。</span><span class="sxs-lookup"><span data-stu-id="90d33-133">I would never do this in a script but it's fair game in the console.</span></span>

### <a name="accessing-items"></a><span data-ttu-id="90d33-134">項目へのアクセス</span><span class="sxs-lookup"><span data-stu-id="90d33-134">Accessing items</span></span>

<span data-ttu-id="90d33-135">項目が含まれている配列の用意ができたので、それらの項目にアクセスして更新してみてください。</span><span class="sxs-lookup"><span data-stu-id="90d33-135">Now that you have an array with items in it, you may want to access and update those items.</span></span>

#### <a name="offset"></a><span data-ttu-id="90d33-136">Offset</span><span class="sxs-lookup"><span data-stu-id="90d33-136">Offset</span></span>

<span data-ttu-id="90d33-137">個々の項目にアクセスするには、0 から始まるオフセット値と角かっこ `[]` を使用します。</span><span class="sxs-lookup"><span data-stu-id="90d33-137">To access individual items, we use the brackets `[]` with an offset value starting at 0.</span></span> <span data-ttu-id="90d33-138">配列内の最初の項目を取得する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="90d33-138">This is how we get the first item in our array:</span></span>

```powershell
PS> $data = 'Zero','One','Two','Three'
PS> $data[0]
Zero
```

<span data-ttu-id="90d33-139">ここで 0 を使用する理由は、最初の項目がリストの先頭にあるため、オフセット 0 の項目を使用してそれを取得するためです。</span><span class="sxs-lookup"><span data-stu-id="90d33-139">The reason why we use zero here is because the first item is at the beginning of the list so we use an offset of 0 items to get to it.</span></span> <span data-ttu-id="90d33-140">2 番目の項目を取得するには、オフセット 1 を使用して最初の項目をスキップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="90d33-140">To get to the second item, we would need to use an offset of 1 to skip the first item.</span></span>

```powershell
PS> $data[1]
One
```

<span data-ttu-id="90d33-141">つまり、最後の項目はオフセット 3 にあります。</span><span class="sxs-lookup"><span data-stu-id="90d33-141">This would mean that the last item is at offset 3.</span></span>

```powershell
PS> $data[3]
Three
```

#### <a name="index"></a><span data-ttu-id="90d33-142">インデックス</span><span class="sxs-lookup"><span data-stu-id="90d33-142">Index</span></span>

<span data-ttu-id="90d33-143">この例に向いている値を選択した理由がおわかりいただけるでしょう。</span><span class="sxs-lookup"><span data-stu-id="90d33-143">Now you can see why I picked the values that I did for this example.</span></span> <span data-ttu-id="90d33-144">これをオフセットとして紹介したのはそれが実際の値であるためですが、通常こうしたオフセットはインデックスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="90d33-144">I introduced this as an offset because that is what it really is, but this offset is more commonly referred to as an index.</span></span> <span data-ttu-id="90d33-145">インデックスは `0` から始まります。</span><span class="sxs-lookup"><span data-stu-id="90d33-145">An index that starts at `0`.</span></span> <span data-ttu-id="90d33-146">この記事の残りの部分では、このオフセットをインデックスと呼びます。</span><span class="sxs-lookup"><span data-stu-id="90d33-146">For the rest of this article I will call the offset an index.</span></span>

#### <a name="special-index-tricks"></a><span data-ttu-id="90d33-147">特殊なインデックスの技法</span><span class="sxs-lookup"><span data-stu-id="90d33-147">Special index tricks</span></span>

<span data-ttu-id="90d33-148">ほとんどの言語では、インデックスとして指定できるのは 1 つの数値のみで、返される項目も 1 つです。</span><span class="sxs-lookup"><span data-stu-id="90d33-148">In most languages, you can only specify a single number as the index and you get a single item back.</span></span>
<span data-ttu-id="90d33-149">それに比べて PowerShell にはかなり高い柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="90d33-149">PowerShell is much more flexible.</span></span> <span data-ttu-id="90d33-150">一度に複数のインデックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-150">You can use multiple indexes at once.</span></span> <span data-ttu-id="90d33-151">インデックスの一覧を指定することで、いくつかの項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-151">By providing a list of indexes, we can select several items.</span></span>

```powershell
PS> $data[0,2,3]
Zero
Two
Three
```

<span data-ttu-id="90d33-152">それらの項目は、指定されたインデックスの順序に基づいて返されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-152">The items are returned based on the order of the indexes provided.</span></span> <span data-ttu-id="90d33-153">インデックスを重複させると、どちらのときもその項目が返されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-153">If you duplicate an index, you get that item both times.</span></span>

```powershell
PS> $data[3,0,3]
Three
Zero
Three
```

<span data-ttu-id="90d33-154">組み込みの `..` 演算子を使用すると、一連の数値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-154">We can specify a sequence of numbers with the built-in `..` operator.</span></span>

```powershell
PS> $data[1..3]
One
Two
Three
```

<span data-ttu-id="90d33-155">これは逆順でも機能します。</span><span class="sxs-lookup"><span data-stu-id="90d33-155">This works in reverse too.</span></span>

```powershell
PS> $data[3..1]
Three
Two
One
```

<span data-ttu-id="90d33-156">負のインデックス値を使用すると、末尾からオフセットされます。</span><span class="sxs-lookup"><span data-stu-id="90d33-156">You can use negative index values to offset from the end.</span></span> <span data-ttu-id="90d33-157">したがって、リストの最後の項目が必要な場合は、`-1` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-157">So if you need the last item in the list, you can use `-1`.</span></span>

```powershell
PS> $data[-1]
Three
```

<span data-ttu-id="90d33-158">ここで、`..` 演算子を使用する場合の注意事項があります。</span><span class="sxs-lookup"><span data-stu-id="90d33-158">One word of caution here with the `..` operator.</span></span> <span data-ttu-id="90d33-159">`0..-1` と `-1..0` の各シーケンス は、それぞれ `0,-1` と `-1,0` の値に評価されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-159">The sequence `0..-1` and `-1..0` evaluate to the values `0,-1` and `-1,0`.</span></span> <span data-ttu-id="90d33-160">この詳細を忘れた場合は、`$data[0..-1]` を見て、それがすべての項目を列挙するものだと考えると簡単です。</span><span class="sxs-lookup"><span data-stu-id="90d33-160">It's easy to see `$data[0..-1]` and think it would enumerate all items if you forget this detail.</span></span> <span data-ttu-id="90d33-161">`$data[0..-1]` では、配列内の最初と最後の項目を返すことによって `$data[0,-1]` と同じ値が返されます (他の値は返されません)。</span><span class="sxs-lookup"><span data-stu-id="90d33-161">`$data[0..-1]` gives you the same value as `$data[0,-1]` by giving you the first and last item in the array (and none of the other values).</span></span>

#### <a name="out-of-bounds"></a><span data-ttu-id="90d33-162">範囲外</span><span class="sxs-lookup"><span data-stu-id="90d33-162">Out of bounds</span></span>

<span data-ttu-id="90d33-163">ほとんどの言語では、配列の末尾を越える項目のインデックスにアクセスしようとすると、ある種のエラーまたは例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="90d33-163">In most languages, if you try to access an index of an item that is past the end of the array, you would get some type of error or an exception.</span></span> <span data-ttu-id="90d33-164">PowerShell では何も返されず、通知もありません。</span><span class="sxs-lookup"><span data-stu-id="90d33-164">PowerShell silently returns nothing.</span></span>

```powershell
PS> $null -eq $data[9000]
True
```

#### <a name="cannot-index-into-a-null-array"></a><span data-ttu-id="90d33-165">null 配列にインデックスを作成できない</span><span class="sxs-lookup"><span data-stu-id="90d33-165">Cannot index into a null array</span></span>

<span data-ttu-id="90d33-166">変数が `$null` であるときに、配列のようにそれにインデックスを作成しようとすると、`System.Management.Automation.RuntimeException` 例外が発生してメッセージ `Cannot index into a null array` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-166">If your variable is `$null` and you try to index it like an array, you get a `System.Management.Automation.RuntimeException` exception with the message `Cannot index into a null array`.</span></span>

```powershell
PS> $empty = $null
SP> $empty[0]
Error: Cannot index into a null array.
```

<span data-ttu-id="90d33-167">そのため、配列内の要素にアクセスしようとする前に、配列が `$null` でないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="90d33-167">So make sure your arrays are not `$null` before you try to access elements inside them.</span></span>

#### <a name="count"></a><span data-ttu-id="90d33-168">Count</span><span class="sxs-lookup"><span data-stu-id="90d33-168">Count</span></span>

<span data-ttu-id="90d33-169">配列とその他のコレクションには、配列内の項目の数を通知する count プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="90d33-169">Arrays and other collections have a count property that tells you how many items are in the array.</span></span>

```powershell
PS> $data.count
4
```

<span data-ttu-id="90d33-170">PowerShell 3.0 では、ほとんどのオブジェクトに count プロパティが追加されました。</span><span class="sxs-lookup"><span data-stu-id="90d33-170">PowerShell 3.0 added a count property to most objects.</span></span> <span data-ttu-id="90d33-171">単一のオブジェクトを配置すると、カウント `1` が返されるはずです。</span><span class="sxs-lookup"><span data-stu-id="90d33-171">you can have a single object and it should give you a count of `1`.</span></span>

```powershell
PS> $date = Get-Date
PS> $date.count
1
```

<span data-ttu-id="90d33-172">`0` が返されることを除き、`$null` にも count プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="90d33-172">Even `$null` has a count property except it returns `0`.</span></span>

```powershell
PS> $null.count
0
```

<span data-ttu-id="90d33-173">ここにはいくつかのトラップがあります。これについては、この記事の後半で `$null` または空の配列がないかの確認方法について説明するときに再度取り上げます。</span><span class="sxs-lookup"><span data-stu-id="90d33-173">There are some traps here that I will revisit when I cover checking for `$null` or empty arrays later on in this article.</span></span>

#### <a name="off-by-one-errors"></a><span data-ttu-id="90d33-174">off-by-one エラー</span><span class="sxs-lookup"><span data-stu-id="90d33-174">Off-by-one errors</span></span>

<span data-ttu-id="90d33-175">配列はインデックス 0 から始まるため、一般的なプログラミング エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="90d33-175">A common programming error is created because arrays start at index 0.</span></span> <span data-ttu-id="90d33-176">off-by-one エラーが発生する可能性のある状況は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="90d33-176">Off-by-one errors can be introduced in two ways.</span></span>

<span data-ttu-id="90d33-177">1 つ目は、2 番目の項目が必要であると心の中で思っているときに、インデックス `2` を使用して、実際には 3 番目の項目を取得することによるものです。</span><span class="sxs-lookup"><span data-stu-id="90d33-177">The first is by mentally thinking you want the second item and using an index of `2` and really getting the third item.</span></span> <span data-ttu-id="90d33-178">または、項目が 4 つあり、最後の項目が必要なので、カウントを使用して最後の項目にアクセスしようと考えることによるものです。</span><span class="sxs-lookup"><span data-stu-id="90d33-178">Or by thinking that you have four items and you want last item, so you use the count to access the last item.</span></span>

```powershell
$data[ $data.count ]
```

<span data-ttu-id="90d33-179">PowerShell では幸いにも、この操作が可能であり、インデックス 4 に存在する項目 (`$null`) が正確に返されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-179">PowerShell is perfectly happy to let you do that and give you exactly what item exists at index 4: `$null`.</span></span> <span data-ttu-id="90d33-180">`$data.count - 1`、または上記で説明した `-1` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90d33-180">You should be using `$data.count - 1` or the `-1` that we learned about above.</span></span>

```powershell
PS> $data[ $data.count - 1 ]
Three
```

<span data-ttu-id="90d33-181">ここでは、`-1` インデックスを使用して最後の要素を取得できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-181">This is where you can use the `-1` index to get the last element.</span></span>

```powershell
PS> $data[ -1 ]
Three
```

<span data-ttu-id="90d33-182">Lee Dailey 氏は、`$data.GetUpperBound(0)` を使用して最大インデックス番号を取得できることも指摘しました。</span><span class="sxs-lookup"><span data-stu-id="90d33-182">Lee Dailey also pointed out to me that we can use `$data.GetUpperBound(0)` to get the max index number.</span></span>

```powershell
PS> $data.GetUpperBound(0)
3
PS> $data[ $data.GetUpperBound(0) ]
Three
```

<span data-ttu-id="90d33-183">2 つ目の最も一般的な状況は、リストを反復処理していて、適切なタイミングで停止しない場合です。</span><span class="sxs-lookup"><span data-stu-id="90d33-183">The second most common way is when iterating the list and not stopping at the right time.</span></span> <span data-ttu-id="90d33-184">これについては、`for` ループの使用方法について説明するときに再度取り上げます。</span><span class="sxs-lookup"><span data-stu-id="90d33-184">I'll revisit this when we talk about using the `for` loop.</span></span>

### <a name="updating-items"></a><span data-ttu-id="90d33-185">項目の更新</span><span class="sxs-lookup"><span data-stu-id="90d33-185">Updating items</span></span>

<span data-ttu-id="90d33-186">同じインデックスを使用して、配列内の既存の項目を更新できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-186">We can use the same index to update existing items in the array.</span></span> <span data-ttu-id="90d33-187">これにより、直接アクセスによって個々の項目を更新できるようになります。</span><span class="sxs-lookup"><span data-stu-id="90d33-187">This gives us direct access to update individual items.</span></span>

```powershell
$data[2] = 'dos'
$data[3] = 'tres'
```

<span data-ttu-id="90d33-188">最後の要素を越える項目を更新しようとすると、`Index was outside the bounds of the array.` エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="90d33-188">If we try to update an item that is past the last element, then we get an `Index was outside the bounds of the array.` error.</span></span>

```powershell
PS> $data[4] = 'four'
Index was outside the bounds of the array.
At line:1 char:1
+ $data[4] = 'four'
+ ~~~~~~~~~~~~~
+ CategoryInfo          : OperationStopped: (:) [], IndexOutOfRangeException
+ FullyQualifiedErrorId : System.IndexOutOfRangeException
```

<span data-ttu-id="90d33-189">これについては、後で配列のサイズを大きくする方法について説明するときに再度取り上げます。</span><span class="sxs-lookup"><span data-stu-id="90d33-189">I'll revisit this later when I talk about how to make an array larger.</span></span>

### <a name="iteration"></a><span data-ttu-id="90d33-190">反復</span><span class="sxs-lookup"><span data-stu-id="90d33-190">Iteration</span></span>

<span data-ttu-id="90d33-191">ある時点で、リスト全体を調べたり反復処理したりして、配列内の項目ごとに何らかのアクションを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="90d33-191">At some point, you might need to walk or iterate the entire list and perform some action for each item in the array.</span></span>

#### <a name="pipeline"></a><span data-ttu-id="90d33-192">パイプライン</span><span class="sxs-lookup"><span data-stu-id="90d33-192">Pipeline</span></span>

<span data-ttu-id="90d33-193">配列と PowerShell パイプラインは最高の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="90d33-193">Arrays and the PowerShell pipeline are meant for each other.</span></span> <span data-ttu-id="90d33-194">これは、それらの値を処理する最も簡単な方法の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="90d33-194">This is one of the simplest ways to process over those values.</span></span> <span data-ttu-id="90d33-195">配列をパイプラインに渡すと、配列内の各項目が個別に処理されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-195">When you pass an array to a pipeline, each item inside the array is processed individually.</span></span>

```powershell
PS> $data = 'Zero','One','Two','Three'
PS> $data | ForEach-Object {"Item: [$PSItem]"}
Item: [Zero]
Item: [One]
Item: [Two]
Item: [Three]
```

<span data-ttu-id="90d33-196">`$PSItem` を今までに見たことがない場合は、それが `$_` と同じものであることがわかります。</span><span class="sxs-lookup"><span data-stu-id="90d33-196">If you have not seen `$PSItem` before, just know that it's the same thing as `$_`.</span></span> <span data-ttu-id="90d33-197">両方ともパイプライン内の現在のオブジェクトを表しているため、どちらを使用してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="90d33-197">You can use either one because they both represent the current object in the pipeline.</span></span>

#### <a name="foreach-loop"></a><span data-ttu-id="90d33-198">ForEach ループ</span><span class="sxs-lookup"><span data-stu-id="90d33-198">ForEach loop</span></span>

<span data-ttu-id="90d33-199">`ForEach` ループは、コレクションで適切に機能します。</span><span class="sxs-lookup"><span data-stu-id="90d33-199">The `ForEach` loop works well with collections.</span></span> <span data-ttu-id="90d33-200">使用する構文は `foreach ( <variable> in <collection> )` です。</span><span class="sxs-lookup"><span data-stu-id="90d33-200">Using the syntax: `foreach ( <variable> in <collection> )`</span></span>

```powershell
foreach ( $node in $data )
{
    "Item: [$node]"
}
```

#### <a name="foreach-method"></a><span data-ttu-id="90d33-201">ForEach メソッド</span><span class="sxs-lookup"><span data-stu-id="90d33-201">ForEach method</span></span>

<span data-ttu-id="90d33-202">これについては忘れがちですが、単純な操作に適しています。</span><span class="sxs-lookup"><span data-stu-id="90d33-202">I tend to forget about this one but it works well for simple operations.</span></span> <span data-ttu-id="90d33-203">PowerShell では、コレクションに対して `.ForEach()` を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="90d33-203">PowerShell allows you to call `.ForEach()` on a collection.</span></span>

```powershell
PS> $data.foreach({"Item [$PSItem]"})
Item [Zero]
Item [One]
Item [Two]
Item [Three]
```

<span data-ttu-id="90d33-204">`.foreach()` は、スクリプト ブロックであるパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="90d33-204">The `.foreach()` takes a parameter that is a script block.</span></span> <span data-ttu-id="90d33-205">かっこを削除して、スクリプト ブロックのみを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="90d33-205">You can drop the parentheses and just provide the script block.</span></span>

```powershell
$data.foreach{"Item [$PSItem]"}
```

<span data-ttu-id="90d33-206">これは、あまり知られていない構文ですが、まったく同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="90d33-206">This is a lesser known syntax but it works just the same.</span></span> <span data-ttu-id="90d33-207">この `foreach` メソッドは、PowerShell 4.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="90d33-207">This `foreach` method was added in PowerShell 4.0.</span></span>

#### <a name="for-loop"></a><span data-ttu-id="90d33-208">For ループ</span><span class="sxs-lookup"><span data-stu-id="90d33-208">For loop</span></span>

<span data-ttu-id="90d33-209">`for` ループは、他のほとんどの言語では頻繁に使用されますが、PowerShell ではあまり見かけません。</span><span class="sxs-lookup"><span data-stu-id="90d33-209">The `for` loop is used heavily in most other languages but you don't see it much in PowerShell.</span></span> <span data-ttu-id="90d33-210">これを見かけるとしたら、多くの場合、配列を調べるコンテキストにおいてです。</span><span class="sxs-lookup"><span data-stu-id="90d33-210">When you do see it, it's often in the context of walking an array.</span></span>

```powershell
for ( $index = 0; $index -lt $data.count; $index++)
{
    "Item: [{0}]" -f $data[$index]
}
```

<span data-ttu-id="90d33-211">最初に、`$index` を `0` に初期化します。</span><span class="sxs-lookup"><span data-stu-id="90d33-211">The first thing we do is initialize an `$index` to `0`.</span></span> <span data-ttu-id="90d33-212">次に、`$index` が `$data.count` より小さくなければならないという条件を追加します。</span><span class="sxs-lookup"><span data-stu-id="90d33-212">Then we add the condition that `$index` must be less than `$data.count`.</span></span> <span data-ttu-id="90d33-213">最後に、ループするたびにインデックスを `1` ずつ増やす必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="90d33-213">Finally, we specify that every time we loop that me must increase the index by `1`.</span></span> <span data-ttu-id="90d33-214">このケースでは、`$index++` は `$index = $index + 1` の短縮形です。</span><span class="sxs-lookup"><span data-stu-id="90d33-214">In this case `$index++` is short for `$index = $index + 1`.</span></span>

<span data-ttu-id="90d33-215">`for` ループを使用する場合は常に、条件に特別な注意を払ってください。</span><span class="sxs-lookup"><span data-stu-id="90d33-215">Whenever you're using a `for` loop, pay special attention to the condition.</span></span> <span data-ttu-id="90d33-216">ここでは `$index -lt $data.count` を使用しました。</span><span class="sxs-lookup"><span data-stu-id="90d33-216">I used `$index -lt $data.count` here.</span></span> <span data-ttu-id="90d33-217">条件を少し取り違えて、ロジック内に off-by-one エラーを発生させるのはたやすいことです。</span><span class="sxs-lookup"><span data-stu-id="90d33-217">It's easy to get the condition slightly wrong to get an off-by-one error in your logic.</span></span> <span data-ttu-id="90d33-218">`$index -le $data.count` または `$index -lt ($data.count - 1)` の使用には、若干の誤解があります。</span><span class="sxs-lookup"><span data-stu-id="90d33-218">Using `$index -le $data.count` or `$index -lt ($data.count - 1)` are ever so slightly wrong.</span></span> <span data-ttu-id="90d33-219">結果として、処理される項目の数が多すぎたり少なすぎたりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="90d33-219">That would cause your result to process too many or too few items.</span></span> <span data-ttu-id="90d33-220">これは、よくある off-by-one エラーです。</span><span class="sxs-lookup"><span data-stu-id="90d33-220">This is the classic off-by-one error.</span></span>

#### <a name="switch-loop"></a><span data-ttu-id="90d33-221">switch ループ</span><span class="sxs-lookup"><span data-stu-id="90d33-221">Switch loop</span></span>

<span data-ttu-id="90d33-222">これは見落としやすい技法です。</span><span class="sxs-lookup"><span data-stu-id="90d33-222">This is one that is easy to overlook.</span></span> <span data-ttu-id="90d33-223">配列を [switch ステートメント][]に指定すると、配列内の各項目がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="90d33-223">If you provide an array to a [switch statement][], it checks each item in the array.</span></span>

```powershell
$data = 'Zero','One','Two','Three'
switch( $data )
{
    'One'
    {
        'Tock'
    }
    'Three'
    {
        'Tock'
    }
    Default
    {
        'Tick'
    }
}
```

```Output
Tick
Tock
Tick
Tock
```

<span data-ttu-id="90d33-224">switch ステートメントを使用して実行できるすばらしい処理がたくさんあります。</span><span class="sxs-lookup"><span data-stu-id="90d33-224">There are a lot of cool things that we can do with the switch statement.</span></span> <span data-ttu-id="90d33-225">これに関する専用の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="90d33-225">I have another article dedicated to this.</span></span>

- <span data-ttu-id="90d33-226">[switch ステートメントについて知りたかったことのすべて][switch ステートメント]</span><span class="sxs-lookup"><span data-stu-id="90d33-226">[Everything you ever wanted to know about the switch statement][switch statement]</span></span>

#### <a name="updating-values"></a><span data-ttu-id="90d33-227">値の更新</span><span class="sxs-lookup"><span data-stu-id="90d33-227">Updating values</span></span>

<span data-ttu-id="90d33-228">配列が文字列または整数 (値型) のコレクションである場合、ループするときに配列内の値の更新が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="90d33-228">When your array is a collection of string or integers (value types), sometimes you may want to update the values in the array as you loop over them.</span></span> <span data-ttu-id="90d33-229">上記のほとんどのループでは、値のコピーを保持する変数をループ内で使用します。</span><span class="sxs-lookup"><span data-stu-id="90d33-229">Most of the loops above use a variable in the loop that holds a copy of the value.</span></span> <span data-ttu-id="90d33-230">その変数を更新しても、配列内の元の値は更新されません。</span><span class="sxs-lookup"><span data-stu-id="90d33-230">If you update that variable, the original value in the array is not updated.</span></span>

<span data-ttu-id="90d33-231">そのステートメントの例外は、`for` ループです。</span><span class="sxs-lookup"><span data-stu-id="90d33-231">The exception to that statement is the `for` loop.</span></span> <span data-ttu-id="90d33-232">配列を調べてその内部の値を更新する場合、お探しのものは `for` ループです。</span><span class="sxs-lookup"><span data-stu-id="90d33-232">If you want to walk an array and update values inside it, then the `for` loop is what you're looking for.</span></span>

```powershell
for ( $index = 0; $index -lt $data.count; $index++ )
{
    $data[$index] = "Item: [{0}]" -f $data[$index]
}
```

<span data-ttu-id="90d33-233">この例では、インデックスによって値を受け取り、いくつかの変更を行ってから、同じインデックスを使用して値を割り当て直します。</span><span class="sxs-lookup"><span data-stu-id="90d33-233">This example takes a value by index, makes a few changes, and then uses that same index to assign it back.</span></span>

## <a name="arrays-of-objects"></a><span data-ttu-id="90d33-234">オブジェクトの配列</span><span class="sxs-lookup"><span data-stu-id="90d33-234">Arrays of Objects</span></span>

<span data-ttu-id="90d33-235">これまでは、値型だけを配列内に配置してきましたが、配列にはオブジェクトを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="90d33-235">So far, the only thing we've placed in an array is a value type, but arrays can also contain objects.</span></span>

```powershell
$data = @(
    [pscustomobject]@{FirstName='Kevin';LastName='Marquette'}
    [pscustomobject]@{FirstName='John'; LastName='Doe'}
)
```

<span data-ttu-id="90d33-236">多くのコマンドレットでは、変数にオブジェクトが割り当てられると、それらのオブジェクトのコレクションを配列として返します。</span><span class="sxs-lookup"><span data-stu-id="90d33-236">Many cmdlets return collections of objects as arrays when you assign them to a variable.</span></span>

```powershell
$processList = Get-Process
```

<span data-ttu-id="90d33-237">既に説明したすべての基本機能はオブジェクトの配列にも適用されますが、指摘しておくべき点がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="90d33-237">All of the basic features we already talked about still apply to arrays of objects with a few details worth pointing out.</span></span>

### <a name="accessing-properties"></a><span data-ttu-id="90d33-238">プロパティへのアクセス</span><span class="sxs-lookup"><span data-stu-id="90d33-238">Accessing properties</span></span>

<span data-ttu-id="90d33-239">値型と同様に、インデックスを使用してコレクション内の個々の項目にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="90d33-239">We can use an index to access an individual item in a collection just like with value types.</span></span>

```powershell
PS> $data[0]

FirstName LastName
-----     ----
Kevin     Marquette
```

<span data-ttu-id="90d33-240">プロパティは、直接アクセスして更新できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-240">We can access and update properties directly.</span></span>

```powershell
PS> $data[0].FirstName

Kevin

PS> $data[0].FirstName = 'Jay'
PS> $data[0]

FirstName LastName
-----     ----
Jay       Marquette
```

#### <a name="array-properties"></a><span data-ttu-id="90d33-241">配列のプロパティ</span><span class="sxs-lookup"><span data-stu-id="90d33-241">Array properties</span></span>

<span data-ttu-id="90d33-242">通常、すべてのプロパティにアクセスするには、次のようにリスト全体を列挙する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90d33-242">Normally you would have to enumerate the whole list like this to access all the properties:</span></span>

```powershell
PS> $data | ForEach-Object {$_.LastName}

Marquette
Doe
```

<span data-ttu-id="90d33-243">または、`Select-Object -ExpandProperty` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="90d33-243">Or by using the `Select-Object -ExpandProperty` cmdlet.</span></span>

```powershell
PS> $data | Select-Object -ExpandProperty LastName

Marquette
Doe
```

<span data-ttu-id="90d33-244">ただし、PowerShell では `LastName` を直接要求することができます。</span><span class="sxs-lookup"><span data-stu-id="90d33-244">But PowerShell offers us the ability to request `LastName` directly.</span></span> <span data-ttu-id="90d33-245">PowerShell では、ユーザーに代わってそれらをすべて列挙し、クリーンなリストを返します。</span><span class="sxs-lookup"><span data-stu-id="90d33-245">PowerShell enumerates them all for us and returns a clean list.</span></span>

```powershell
PS> $data.LastName

Marquette
Doe
```

<span data-ttu-id="90d33-246">列挙は今までどおり行われますが、その背後にある複雑な操作は表示されません。</span><span class="sxs-lookup"><span data-stu-id="90d33-246">The enumeration still happens but we don't see the complexity behind it.</span></span>

### <a name="where-object-filtering"></a><span data-ttu-id="90d33-247">Where-Object のフィルタリング</span><span class="sxs-lookup"><span data-stu-id="90d33-247">Where-Object filtering</span></span>

<span data-ttu-id="90d33-248">ここでは `Where-Object` が使用されるため、オブジェクトのプロパティに基づいて、配列から必要なものをフィルター処理して選択できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-248">This is where `Where-Object` comes in so we can filter and select what we want out of the array based on the properties of the object.</span></span>

```powershell
PS> $data | Where-Object {$_.FirstName -eq 'Kevin'}

FirstName LastName
-----     ----
Kevin     Marquette
```

<span data-ttu-id="90d33-249">これと同じクエリを作成して、探している `FirstName` を取得できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-249">We can write that same query to get the `FirstName` we are looking for.</span></span>

```powershell
$data | Where FirstName -eq Kevin
```

#### <a name="where"></a><span data-ttu-id="90d33-250">Where()</span><span class="sxs-lookup"><span data-stu-id="90d33-250">Where()</span></span>

<span data-ttu-id="90d33-251">配列には、フィルターとして `scriptblock` を指定できる `Where()` メソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="90d33-251">Arrays have a `Where()` method on them that allows you to specify a `scriptblock` for the filter.</span></span>

```powershell
$data.Where({$_.FirstName -eq 'Kevin'})
```

<span data-ttu-id="90d33-252">この機能は、PowerShell 4.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="90d33-252">This feature was added in PowerShell 4.0.</span></span>

### <a name="updating-objects-in-loops"></a><span data-ttu-id="90d33-253">ループ内のオブジェクトの更新</span><span class="sxs-lookup"><span data-stu-id="90d33-253">Updating objects in loops</span></span>

<span data-ttu-id="90d33-254">値型の場合、値を置き換えるインデックスを把握しておく必要があるため、配列を更新する唯一の方法は for ループを使用することです。</span><span class="sxs-lookup"><span data-stu-id="90d33-254">With value types, the only way to update the array is to use a for loop because we need to know the index to replace the value.</span></span> <span data-ttu-id="90d33-255">オブジェクトは参照型であるため、さらに多くの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="90d33-255">We have more options with objects because they are reference types.</span></span> <span data-ttu-id="90d33-256">以下に簡単な例を示します。</span><span class="sxs-lookup"><span data-stu-id="90d33-256">Here is a quick example:</span></span>

```powershell
foreach($person in $data)
{
    $person.FirstName = 'Kevin'
}
```

<span data-ttu-id="90d33-257">このループでは、`$data` 配列内のすべてのオブジェクトを調べています。</span><span class="sxs-lookup"><span data-stu-id="90d33-257">This loop is walking every object in the `$data` array.</span></span> <span data-ttu-id="90d33-258">オブジェクトは参照型であるため、`$person` 変数は配列内のまったく同じオブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="90d33-258">Because objects are reference types, the `$person` variable references the exact same object that is in the array.</span></span> <span data-ttu-id="90d33-259">そのため、そのオブジェクトのプロパティを更新すると、元のオブジェクトが更新されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-259">So updates to its properties do update the original.</span></span>

<span data-ttu-id="90d33-260">オブジェクト全体をこのように置き換えることはまだできません。</span><span class="sxs-lookup"><span data-stu-id="90d33-260">You still can't replace the whole object this way.</span></span> <span data-ttu-id="90d33-261">`$person` 変数に新しいオブジェクトを割り当てようとする場合は、配列内の元のオブジェクトをもう指さなくなった別のものに変数の参照を更新します。</span><span class="sxs-lookup"><span data-stu-id="90d33-261">If you try to assign a new object to the `$person` variable, you're updating the variable reference to something else that no longer points to the original object in the array.</span></span> <span data-ttu-id="90d33-262">これは期待どおりに機能しません。</span><span class="sxs-lookup"><span data-stu-id="90d33-262">This doesn't work like you would expect:</span></span>

```powershell
foreach($person in $data)
{
    $person = [pscustomobject]@{
        FirstName='Kevin'
        LastName='Marquette'
    }
}
```

## <a name="operators"></a><span data-ttu-id="90d33-263">オペレーター</span><span class="sxs-lookup"><span data-stu-id="90d33-263">Operators</span></span>

<span data-ttu-id="90d33-264">PowerShell の演算子は、配列でも機能します。</span><span class="sxs-lookup"><span data-stu-id="90d33-264">The operators in PowerShell also work on arrays.</span></span> <span data-ttu-id="90d33-265">それらの一部の動作は若干異なります。</span><span class="sxs-lookup"><span data-stu-id="90d33-265">Some of them work slightly differently.</span></span>

### <a name="-join"></a><span data-ttu-id="90d33-266">-join</span><span class="sxs-lookup"><span data-stu-id="90d33-266">-join</span></span>

<span data-ttu-id="90d33-267">`-join` 演算子が最もわかりやすいので、最初にそれを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="90d33-267">The `-join` operator is the most obvious one so let's look at it first.</span></span> <span data-ttu-id="90d33-268">`-join` 演算子は気に入っているため、頻繁に使用しています。</span><span class="sxs-lookup"><span data-stu-id="90d33-268">I like the `-join` operator and use it often.</span></span> <span data-ttu-id="90d33-269">これは、配列内のすべての要素を、指定した文字または文字列と結合します。</span><span class="sxs-lookup"><span data-stu-id="90d33-269">It joins all elements in the array with the character or string that you specify.</span></span>

```powershell
PS> $data = @(1,2,3,4)
PS> $data -join '-'
1-2-3-4
PS> $data -join ','
1,2,3,4
```

<span data-ttu-id="90d33-270">`-join` 演算子に関して気に入っている機能の 1 つに、単一の項目を処理することが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="90d33-270">One of the features that I like about the `-join` operator is that it handles single items.</span></span>

```powershell
PS> 1 -join '-'
1
```

<span data-ttu-id="90d33-271">これは、ログ記録や詳細メッセージの内部で使用します。</span><span class="sxs-lookup"><span data-stu-id="90d33-271">I use this inside logging and verbose messages.</span></span>

```powershell
PS> $data = @(1,2,3,4)
PS> "Data is $($data -join ',')."
Data is 1,2,3,4.
```

#### <a name="-join-array"></a><span data-ttu-id="90d33-272">-join $array</span><span class="sxs-lookup"><span data-stu-id="90d33-272">-join $array</span></span>

<span data-ttu-id="90d33-273">Lee Dailey 氏が指摘した巧みな技法の 1 つを次に示します。</span><span class="sxs-lookup"><span data-stu-id="90d33-273">Here is a clever trick that Lee Dailey pointed out to me.</span></span> <span data-ttu-id="90d33-274">区切り記号を使用せずにすべてを結合する場合は、次のようにするのではなく、</span><span class="sxs-lookup"><span data-stu-id="90d33-274">If you ever want to join everything without a delimiter, instead of doing this:</span></span>

```powershell
PS> $data = @(1,2,3,4)
PS> $data -join $null
1234
```

<span data-ttu-id="90d33-275">`-join` をプレフィックスなしのパラメーターとして配列で使用できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-275">You can use `-join` with the array as the parameter with no prefix.</span></span> <span data-ttu-id="90d33-276">次の例を見て、私が説明していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="90d33-276">Take a look at this example to see that I'm talking about.</span></span>

```powershell
PS> $data = @(1,2,3,4)
PS> -join $data
1234
```

### <a name="-replace-and--split"></a><span data-ttu-id="90d33-277">-replace と -split</span><span class="sxs-lookup"><span data-stu-id="90d33-277">-replace and -split</span></span>

<span data-ttu-id="90d33-278">`-replace` や `-split` などの他の演算子は、配列内の各項目に対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-278">The other operators like `-replace` and `-split` execute on each item in the array.</span></span> <span data-ttu-id="90d33-279">それらをこのように使用したことはありませんが、次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="90d33-279">I can't say that I have ever used them this way but here is an example.</span></span>

```powershell
PS> $data = @('ATX-SQL-01','ATX-SQL-02','ATX-SQL-03')
PS> $data -replace 'ATX','LAX'
LAX-SQL-01
LAX-SQL-02
LAX-SQL-03
```

### <a name="-contains"></a><span data-ttu-id="90d33-280">-contains</span><span class="sxs-lookup"><span data-stu-id="90d33-280">-contains</span></span>

<span data-ttu-id="90d33-281">`-contains` 演算子を使用すると、値の配列を調べて、指定した値が含まれているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-281">The `-contains` operator allows you to check an array of values to see if it contains a specified value.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data -contains 'green'
True
```

### <a name="-in"></a><span data-ttu-id="90d33-282">-in</span><span class="sxs-lookup"><span data-stu-id="90d33-282">-in</span></span>

<span data-ttu-id="90d33-283">1 つの値が複数の値のいずれかに一致するかどうかを確認する場合は、`-in` 演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-283">When you have a single value that you would like to verify matches one of several values, you can use the `-in` operator.</span></span> <span data-ttu-id="90d33-284">演算子の左側に値が置かれ、右側に配列が置かれます。</span><span class="sxs-lookup"><span data-stu-id="90d33-284">The value would be on the left and the array on the right-hand side of the operator.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> 'green' -in $data
True
```

<span data-ttu-id="90d33-285">この方法は、リストが大きい場合にコストが高くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90d33-285">This can get expensive if the list is large.</span></span> <span data-ttu-id="90d33-286">多くの値を確認する場合は、正規表現パターンがよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-286">I often use a regex pattern if I'm checking more than a few values.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $pattern = "^({0})$" -f ($data -join '|')
PS> $pattern
^(red|green|blue)$

PS> 'green' -match $pattern
True
```

### <a name="-eq-and--ne"></a><span data-ttu-id="90d33-287">-eq と -ne</span><span class="sxs-lookup"><span data-stu-id="90d33-287">-eq and -ne</span></span>

<span data-ttu-id="90d33-288">等価と配列は複雑になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90d33-288">Equality and arrays can get complicated.</span></span> <span data-ttu-id="90d33-289">配列が左側にある場合は、すべての項目が比較されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-289">When the array is on the left side, every item gets compared.</span></span> <span data-ttu-id="90d33-290">`True` が返されるのではなく、一致するオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-290">Instead of returning `True`, it returns the object that matches.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data -eq 'green'
green
```

<span data-ttu-id="90d33-291">`-ne` 演算子を使用する場合は、指定した値と等しくないすべての値が返されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-291">When you use the `-ne` operator, we get all the values that are not equal to our value.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data -ne 'green'
red
blue
```

<span data-ttu-id="90d33-292">`if()` ステートメントでこれを使用する場合、返される値は `True` 値になります。</span><span class="sxs-lookup"><span data-stu-id="90d33-292">When you use this in an `if()` statement, a value that is returned is a `True` value.</span></span> <span data-ttu-id="90d33-293">返される値がない場合は、`False` 値になります。</span><span class="sxs-lookup"><span data-stu-id="90d33-293">If no value is returned, then it's a `False` value.</span></span> <span data-ttu-id="90d33-294">次に示すこれらのステートメントはどちらも `True` に評価されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-294">Both of these next statements evaluate to `True`.</span></span>

```powershell
$data = @('red','green','blue')
if ( $data -eq 'green' )
{
    'Green was found'
}
if ( $data -ne 'green' )
{
    'And green was not found'
}
```

<span data-ttu-id="90d33-295">これについては、`$null` のテスト方法について説明するときに再度取り上げます。</span><span class="sxs-lookup"><span data-stu-id="90d33-295">I'll revisit this in a moment when we talk about testing for `$null`.</span></span>

### <a name="-match"></a><span data-ttu-id="90d33-296">-match</span><span class="sxs-lookup"><span data-stu-id="90d33-296">-match</span></span>

<span data-ttu-id="90d33-297">`-match` 演算子は、コレクション内の各項目を一致させようとします。</span><span class="sxs-lookup"><span data-stu-id="90d33-297">The `-match` operator tries to match each item in the collection.</span></span>

```powershell
PS> $servers = @(
    'LAX-SQL-01'
    'LAX-API-01'
    'ATX-SQL-01'
    'ATX-API-01'
)
PS> $servers -match 'SQL'
LAX-SQL-01
ATX-SQL-01
```

<span data-ttu-id="90d33-298">1 つの値で `-match` を使用する場合は、特殊変数 `$Matches` に一致情報が入力されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-298">When you use `-match` with a single value, a special variable `$Matches` gets populated with match info.</span></span> <span data-ttu-id="90d33-299">配列がこのように処理される場合、これは当てはまりません。</span><span class="sxs-lookup"><span data-stu-id="90d33-299">This isn't the case when an array is processed this way.</span></span>

<span data-ttu-id="90d33-300">`Select-String` を使用して同様の手法をとることができます。</span><span class="sxs-lookup"><span data-stu-id="90d33-300">We can take the same approach with `Select-String`.</span></span>

```powershell
$servers | Select-String SQL
```

<span data-ttu-id="90d33-301">`Select-String`、`-match`、および `$matches` 変数については、[正規表現を使用するさまざまな方法][]という別の投稿で詳しく説明しています。</span><span class="sxs-lookup"><span data-stu-id="90d33-301">I take a closer look at `Select-String`,`-match` and the `$matches` variable in another post called [The many ways to use regex][].</span></span>

### <a name="null-or-empty"></a><span data-ttu-id="90d33-302">$null または空</span><span class="sxs-lookup"><span data-stu-id="90d33-302">$null or empty</span></span>

<span data-ttu-id="90d33-303">`$null` または空の配列かどうかのテストは、難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="90d33-303">Testing for `$null` or empty arrays can be tricky.</span></span> <span data-ttu-id="90d33-304">配列を使用した一般的なトラップを次に示します。</span><span class="sxs-lookup"><span data-stu-id="90d33-304">Here are the common traps with arrays.</span></span>

<span data-ttu-id="90d33-305">一見すると、このステートメントは正しく機能するように見えます。</span><span class="sxs-lookup"><span data-stu-id="90d33-305">At a glance, this statement looks like it should work.</span></span>

```powershell
if ( $array -eq $null)
{
    'Array is $null'
}
```

<span data-ttu-id="90d33-306">しかし、`-eq` が配列内の各項目を確認する方法について説明したばかりです。</span><span class="sxs-lookup"><span data-stu-id="90d33-306">But I just went over how `-eq` checks each item in the array.</span></span> <span data-ttu-id="90d33-307">そのため、1 つの $null 値を含む、複数の項目の配列を作成することができ、それは `$true` に評価されます</span><span class="sxs-lookup"><span data-stu-id="90d33-307">So we can have an array of several items with a single $null value and it would evaluate to `$true`</span></span>

```powershell
$array = @('one',$null,'three')
if ( $array -eq $null)
{
    'I think Array is $null, but I would be wrong'
}
```

<span data-ttu-id="90d33-308">演算子の左側に `$null` を配置することがベスト プラクティスであるのはそのためです。</span><span class="sxs-lookup"><span data-stu-id="90d33-308">This is why it's a best practice to place the `$null` on the left side of the operator.</span></span> <span data-ttu-id="90d33-309">これにより、このシナリオが問題になることはありません。</span><span class="sxs-lookup"><span data-stu-id="90d33-309">This makes this scenario a non-issue.</span></span>

```powershell
if ( $null -eq $array )
{
    'Array actually is $null'
}
```

<span data-ttu-id="90d33-310">`$null` 配列は、空の配列と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="90d33-310">A `$null` array isn't the same thing as an empty array.</span></span> <span data-ttu-id="90d33-311">配列があることがわかっている場合は、その中のオブジェクトの数を確認します。</span><span class="sxs-lookup"><span data-stu-id="90d33-311">If you know you have an array, check the count of objects in it.</span></span> <span data-ttu-id="90d33-312">配列が `$null` の場合、カウントは `0` です。</span><span class="sxs-lookup"><span data-stu-id="90d33-312">If the array is `$null`, the count is `0`.</span></span>

```powershell
if ( $array.count -gt 0 )
{
    'Array isn't empty'
}
```

<span data-ttu-id="90d33-313">ここで注意すべきトラップがもう 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="90d33-313">There is one more trap to watch out for here.</span></span> <span data-ttu-id="90d33-314">オブジェクトが `PSCustomObject` である場合を除き、オブジェクトが 1 つしかない場合でも `count` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-314">You can use the `count` even if you have a single object, unless that object is a `PSCustomObject`.</span></span> <span data-ttu-id="90d33-315">これは、PowerShell 6.1 で修正されたバグです。</span><span class="sxs-lookup"><span data-stu-id="90d33-315">This is a bug that is fixed in PowerShell 6.1.</span></span>
<span data-ttu-id="90d33-316">これはよいニュースですが、多くのユーザーがまだ 5.1 を使用しているため、注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="90d33-316">That's good news, but a lot of people are still on 5.1 and need to watch out for it.</span></span>

```powershell
PS> $object = [PSCustomObject]@{Name='TestObject'}
PS> $object.count
$null
```

<span data-ttu-id="90d33-317">PowerShell 5.1 をまだ使用している場合は、配列内でそのオブジェクトをラップしてから、カウントを確認して正確な数を取得できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-317">If you're still on PowerShell 5.1, you can wrap the object in an array before checking the count to get an accurate count.</span></span>

```powershell
if ( @($array).count -gt 0 )
{
    'Array isn't empty'
}
```

<span data-ttu-id="90d33-318">十分に安全な方法をとるには、`$null` がないか確認してから、カウントを調べます。</span><span class="sxs-lookup"><span data-stu-id="90d33-318">To fully play it safe, check for `$null`, then check the count.</span></span>

```powershell
if ( $null -ne $array -and @($array).count -gt 0 )
{
    'Array isn't empty'
}
```

### <a name="all--eq"></a><span data-ttu-id="90d33-319">All -eq</span><span class="sxs-lookup"><span data-stu-id="90d33-319">All -eq</span></span>

<span data-ttu-id="90d33-320">[配列内のすべての値が指定された値と一致するかどうかを確認する方法][]について、だれかが最近質問していました。</span><span class="sxs-lookup"><span data-stu-id="90d33-320">I recently saw someone ask [how to verify that every value in an array matches a given value][].</span></span>
<span data-ttu-id="90d33-321">Reddit ユーザーの **/u/bis** には、不適切な値がないかどうかを確認してから結果を反転させるという巧妙な[解決方法][]が載っていました。</span><span class="sxs-lookup"><span data-stu-id="90d33-321">Reddit user **/u/bis** had this clever [solution][] that checks for any incorrect values and then flips the result.</span></span>

```powershell
$results = Test-Something
if ( -not ( $results -ne 'Passed') )
{
    'All results a Passed'
}
```

## <a name="adding-to-arrays"></a><span data-ttu-id="90d33-322">配列への追加</span><span class="sxs-lookup"><span data-stu-id="90d33-322">Adding to arrays</span></span>

<span data-ttu-id="90d33-323">ここにきて、配列に項目を追加する方法が気になり始めています。</span><span class="sxs-lookup"><span data-stu-id="90d33-323">At this point, you're starting to wonder how to add items to an array.</span></span> <span data-ttu-id="90d33-324">簡単に答えると、それはできません。</span><span class="sxs-lookup"><span data-stu-id="90d33-324">The quick answer is that you can't.</span></span> <span data-ttu-id="90d33-325">配列は、メモリ内で固定サイズです。</span><span class="sxs-lookup"><span data-stu-id="90d33-325">An array is a fixed size in memory.</span></span> <span data-ttu-id="90d33-326">それを拡張したり、それに単一の項目を追加したりする必要がある場合は、新しい配列を作成して、古い配列からすべての値をコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="90d33-326">If you need to grow it or add a single item to it, then you need to create a new array and copy all the values over from the old array.</span></span> <span data-ttu-id="90d33-327">これには高いコストと多大な労力がかかるように思われますが、PowerShell では新しい配列の作成の複雑さは見えません。</span><span class="sxs-lookup"><span data-stu-id="90d33-327">This sounds expensive and like a lot of work, however, PowerShell hides the complexity of creating the new array.</span></span>

### <a name="array-addition"></a><span data-ttu-id="90d33-328">配列の加算</span><span class="sxs-lookup"><span data-stu-id="90d33-328">Array addition</span></span>

<span data-ttu-id="90d33-329">配列で加算演算子を使用すると、新しい配列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-329">We can use the addition operator with arrays to create a new array.</span></span> <span data-ttu-id="90d33-330">そのため、次の 2 つの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="90d33-330">So given these two arrays:</span></span>

```powershell
$first = @(
    'Zero'
    'One'
)
$second = @(
    'Two'
    'Three'
)
```

<span data-ttu-id="90d33-331">これらを合算して、新しい配列を取得できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-331">We can add them together to get a new array.</span></span>

```powershell
PS> $first + $second

Zero
One
Two
Three
```

### <a name="plus-equals-"></a><span data-ttu-id="90d33-332">プラス イコール (+=)</span><span class="sxs-lookup"><span data-stu-id="90d33-332">Plus equals +=</span></span>

<span data-ttu-id="90d33-333">新しい配列を所定の場所に作成し、次のように項目を追加できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-333">We can create a new array in place and add an item to it like this:</span></span>

```powershell
$data = @(
    'Zero'
    'One'
    'Two'
    'Three'
)
$data += 'four'
```

<span data-ttu-id="90d33-334">`+=` を使用するたびに、新しい配列を複製して作成していることを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="90d33-334">Just remember that every time you use `+=` that you're duplicating and creating a new array.</span></span> <span data-ttu-id="90d33-335">これは小規模なデータセットでは問題になりませんが、非常に不適切にスケーリングされます。</span><span class="sxs-lookup"><span data-stu-id="90d33-335">This is a not an issue for small datasets but it scales extremely poorly.</span></span>

### <a name="pipeline-assignment"></a><span data-ttu-id="90d33-336">パイプラインによる代入</span><span class="sxs-lookup"><span data-stu-id="90d33-336">Pipeline assignment</span></span>

<span data-ttu-id="90d33-337">どのパイプラインの結果も変数に代入することができます。</span><span class="sxs-lookup"><span data-stu-id="90d33-337">You can assign the results of any pipeline into a variable.</span></span> <span data-ttu-id="90d33-338">複数の項目が含まれている場合、それは配列です。</span><span class="sxs-lookup"><span data-stu-id="90d33-338">It's an array if it contains multiple items.</span></span>

```powershell
$array = 1..5 | ForEach-Object {
    "ATX-SQL-$PSItem"
}
```

<span data-ttu-id="90d33-339">通常、パイプラインの使用を検討しているときは、一般的な PowerShell ワンライナーのことが浮かびます。</span><span class="sxs-lookup"><span data-stu-id="90d33-339">Normally when we think of using the pipeline, we think of the typical PowerShell one-liners.</span></span> <span data-ttu-id="90d33-340">パイプラインは、`foreach()` ステートメントやその他のループと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-340">We can leverage the pipeline with `foreach()` statements and other loops.</span></span> <span data-ttu-id="90d33-341">したがって、ループ内の配列に項目を追加するのではなく、パイプラインに項目をドロップできます。</span><span class="sxs-lookup"><span data-stu-id="90d33-341">So instead of adding items to an array in a loop, we can drop items onto the pipeline.</span></span>

```powershell
$array = foreach ( $node in (1..5))
{
    "ATX-SQL-$node"
}
```

<span data-ttu-id="90d33-342">`foreach` の結果を変数に代入すると、すべてのオブジェクトがキャプチャされ、1 つの配列が作成されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-342">By assigning the results of the `foreach` to a variable, we capture all the objects and create a single array.</span></span>

## <a name="array-types"></a><span data-ttu-id="90d33-343">配列の型</span><span class="sxs-lookup"><span data-stu-id="90d33-343">Array Types</span></span>

<span data-ttu-id="90d33-344">既定では、PowerShell の配列は `[PSObject[]]` 型として作成されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-344">By default, an array in PowerShell is created as a `[PSObject[]]` type.</span></span> <span data-ttu-id="90d33-345">これにより、任意の型のオブジェクトまたは値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="90d33-345">This allows it to contain any type of object or value.</span></span> <span data-ttu-id="90d33-346">これが機能するのは、`PSObject` 型からすべてが継承されるためです。</span><span class="sxs-lookup"><span data-stu-id="90d33-346">This works because everything is inherited from the `PSObject` type.</span></span>

### <a name="strongly-typed-arrays"></a><span data-ttu-id="90d33-347">厳密に型指定された配列</span><span class="sxs-lookup"><span data-stu-id="90d33-347">Strongly typed arrays</span></span>

<span data-ttu-id="90d33-348">同様の構文を使用して、任意の型の配列を作成できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-348">You can create an array of any type using a similar syntax.</span></span> <span data-ttu-id="90d33-349">厳密に型指定された配列を作成すると、指定した型の値またはオブジェクトのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="90d33-349">When you create a strongly typed array, it can only contain values or objects the specified type.</span></span>

```powershell
PS> [int[]] $numbers = 1,2,3
PS> [int[]] $numbers2 = 'one','two','three'
ERROR: Cannot convert value "one" to type "System.Int32". Input string was not in a correct format."

PS> [string[]] $strings = 'one','two','three'
```

### <a name="arraylist"></a><span data-ttu-id="90d33-350">ArrayList</span><span class="sxs-lookup"><span data-stu-id="90d33-350">ArrayList</span></span>

<span data-ttu-id="90d33-351">配列への項目の追加は最大の制限事項の 1 つですが、この問題を解決するために使用できる他のコレクションがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="90d33-351">Adding items to an array is one of its biggest limitations, but there are a few other collections that we can turn to that solve this problem.</span></span>

<span data-ttu-id="90d33-352">`ArrayList` は通常、迅速に処理できる配列が必要な場合に最初に思い付くものの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="90d33-352">The `ArrayList` is commonly one of the first things that we think of when we need an array that is faster to work with.</span></span> <span data-ttu-id="90d33-353">それが必要となるすべての場所でオブジェクトの配列のように動作しますが、項目の追加をすばやく処理します。</span><span class="sxs-lookup"><span data-stu-id="90d33-353">It acts like an object array every place that we need it, but it handles adding items quickly.</span></span>

<span data-ttu-id="90d33-354">ここでは、`ArrayList` を作成し、それに項目を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="90d33-354">Here is how we create an `ArrayList` and add items to it.</span></span>

```powershell
$myarray = [System.Collections.ArrayList]::new()
[void]$myArray.Add('Value')
```

<span data-ttu-id="90d33-355">この型を取得するために .NET を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="90d33-355">We are calling into .NET to get this type.</span></span> <span data-ttu-id="90d33-356">この場合、既定のコンストラクターを使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="90d33-356">In this case, we are using the default constructor to create it.</span></span> <span data-ttu-id="90d33-357">次に、`Add` メソッドを呼び出して項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="90d33-357">Then we call the `Add` method to add an item to it.</span></span>

<span data-ttu-id="90d33-358">行の先頭で `[void]` を使用している理由は、リターン コードが表示されないようにするためです。</span><span class="sxs-lookup"><span data-stu-id="90d33-358">The reason I'm using `[void]` at the beginning of the line is to suppress the return code.</span></span> <span data-ttu-id="90d33-359">一部の .NET 呼び出しではこれを実行して、予期しない出力が作成されることがあります。</span><span class="sxs-lookup"><span data-stu-id="90d33-359">Some .NET calls do this and can create unexpected output.</span></span>

<span data-ttu-id="90d33-360">配列に格納されているデータが文字列のみの場合は、[StringBuilder][] の使用方法もご確認ください。</span><span class="sxs-lookup"><span data-stu-id="90d33-360">If the only data that you have in your array is strings, then also take a look at using [StringBuilder][].</span></span> <span data-ttu-id="90d33-361">これはほぼ同じものですが、文字列を処理するためだけのメソッドがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="90d33-361">It's almost the same thing but has some methods that are just for dealing with strings.</span></span> <span data-ttu-id="90d33-362">`StringBuilder` は、特にパフォーマンスを考慮して設計されています。</span><span class="sxs-lookup"><span data-stu-id="90d33-362">The `StringBuilder` is specially designed for performance.</span></span>

<span data-ttu-id="90d33-363">ユーザーが配列から `ArrayList` に変えることはよくあります。</span><span class="sxs-lookup"><span data-stu-id="90d33-363">It's common to see people move to `ArrayList` from arrays.</span></span> <span data-ttu-id="90d33-364">しかし、これは C# にジェネリックのサポートがなかったときに作られたものです。</span><span class="sxs-lookup"><span data-stu-id="90d33-364">But it comes from a time where C# didn't have generic support.</span></span> <span data-ttu-id="90d33-365">`ArrayList` は、ジェネリックの `List[]` のサポートでは非推奨です</span><span class="sxs-lookup"><span data-stu-id="90d33-365">The `ArrayList` is deprecated in support for the generic `List[]`</span></span>

### <a name="generic-list"></a><span data-ttu-id="90d33-366">ジェネリックのリスト</span><span class="sxs-lookup"><span data-stu-id="90d33-366">Generic List</span></span>

<span data-ttu-id="90d33-367">ジェネリック型は、汎用化されたクラスを定義する C# の特殊な型で あり、ユーザーは作成時にそれが使用するデータ型を指定します。</span><span class="sxs-lookup"><span data-stu-id="90d33-367">A generic type is a special type in C# that defines a generalized class and the user specifies the data types it uses when created.</span></span> <span data-ttu-id="90d33-368">したがって、数値または文字列のリストが必要な場合は、`int` または `string` 型のリストが必要であることを定義します。</span><span class="sxs-lookup"><span data-stu-id="90d33-368">So if you want a list of numbers or strings, you would define that you want list of `int` or `string` types.</span></span>

<span data-ttu-id="90d33-369">ここでは、文字列のリストを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="90d33-369">Here is how you create a List for strings.</span></span>

```powershell
$mylist = [System.Collections.Generic.List[string]]::new()
```

<span data-ttu-id="90d33-370">または数値のリストを作成します。</span><span class="sxs-lookup"><span data-stu-id="90d33-370">Or a list for numbers.</span></span>

```powershell
$mylist = [System.Collections.Generic.List[int]]::new()
```

<span data-ttu-id="90d33-371">オブジェクトを最初に作成せずに、次のように既存の配列をリストにキャストできます。</span><span class="sxs-lookup"><span data-stu-id="90d33-371">We can cast an existing array to a list like this without creating the object first:</span></span>

```powershell
$mylist = [System.Collections.Generic.List[int]]@(1,2,3)
```

<span data-ttu-id="90d33-372">PowerShell 5 以降では、`using namespace` ステートメントを使用して構文を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-372">We can shorten the syntax with the `using namespace` statement in PowerShell 5 and newer.</span></span> <span data-ttu-id="90d33-373">`using` ステートメントは、スクリプトの最初の行である必要があります。</span><span class="sxs-lookup"><span data-stu-id="90d33-373">The `using` statement needs to be the first line of your script.</span></span> <span data-ttu-id="90d33-374">名前空間を宣言することで、PowerShell ではデータ型を参照するときにデータ型からそれを省くことができます。</span><span class="sxs-lookup"><span data-stu-id="90d33-374">By declaring a namespace, PowerShell lets you leave it off of the data types when you reference them.</span></span>

```powershell
using namespace System.Collections.Generic
$myList = [List[int]]@(1,2,3)
```

<span data-ttu-id="90d33-375">これにより、`List` がはるかに使いやすくなります。</span><span class="sxs-lookup"><span data-stu-id="90d33-375">This makes the `List` much more usable.</span></span>

<span data-ttu-id="90d33-376">同様の `Add` メソッドも用意されています。</span><span class="sxs-lookup"><span data-stu-id="90d33-376">You have a similar `Add` method available to you.</span></span> <span data-ttu-id="90d33-377">ArrayList とは異なり、`Add` メソッドには戻り値がないため、それを `void` する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="90d33-377">Unlike the ArrayList, there is no return value on the `Add` method so we don't have to `void` it.</span></span>

```powershell
$myList.Add(10)
```

<span data-ttu-id="90d33-378">また、他の配列のように要素にアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="90d33-378">And we can still access the elements like other arrays.</span></span>

```powershell
PS> $myList[-1]
10
```

#### <a name="listpsobject"></a><span data-ttu-id="90d33-379">List[PSObject]</span><span class="sxs-lookup"><span data-stu-id="90d33-379">List[PSObject]</span></span>

<span data-ttu-id="90d33-380">任意の型のリストを持つことができますが、オブジェクトの型がわからない場合は、`[List[PSObject]]` を使用してそれらを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="90d33-380">You can have a list of any type, but when you don't know the type of objects, you can use `[List[PSObject]]` to contain them.</span></span>

```powershell
$list = [List[PSObject]]::new()
```

#### <a name="remove"></a><span data-ttu-id="90d33-381">Remove()</span><span class="sxs-lookup"><span data-stu-id="90d33-381">Remove()</span></span>

<span data-ttu-id="90d33-382">`ArrayList` とジェネリックの `List[]` はどちらも、コレクションからの項目の削除をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="90d33-382">The `ArrayList` and the generic `List[]` both support removing items from the collection.</span></span>

```powershell
using namespace System.Collections.Generic
$myList = [List[string]]@('Zero','One','Two','Three')
[void]$myList.Remove("Two")
Zero
One
Three
```

<span data-ttu-id="90d33-383">値型を使用する場合は、リストから最初の値が削除されます。</span><span class="sxs-lookup"><span data-stu-id="90d33-383">When working with value types, it removes the first one from the list.</span></span> <span data-ttu-id="90d33-384">それを何度も繰り返して呼び出すと、その値を削除し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="90d33-384">You can call it over and over again to keep removing that value.</span></span> <span data-ttu-id="90d33-385">参照型がある場合は、削除するオブジェクトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90d33-385">If you have reference types, you have to provide the object that you want removed.</span></span>

```powershell
[list[System.Management.Automation.PSDriveInfo]]$drives = Get-PSDrive
$drives.remove($drives[2])
```

```powershell
$delete = $drives[2]
$drives.remove($delete)
```

<span data-ttu-id="90d33-386">remove メソッドは、項目を検索してコレクションから削除できる場合は `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="90d33-386">The remove method returns `true` if it was able to find and remove the item from the collection.</span></span>

### <a name="more-collections"></a><span data-ttu-id="90d33-387">その他のコレクション</span><span class="sxs-lookup"><span data-stu-id="90d33-387">More collections</span></span>

<span data-ttu-id="90d33-388">使用できるコレクションは他にも多数ありますが、これらは優れたジェネリックの配列の置換です。</span><span class="sxs-lookup"><span data-stu-id="90d33-388">There are many other collections that can be used but these are the good generic array replacements.</span></span>
<span data-ttu-id="90d33-389">これらのオプションに関心をお持ちの場合は、[Mark Kraus 氏](https://get-powershellblog.blogspot.com/2016/11/about-mark-kraus.html)がまとめたこちらの[Gist](https://gist.github.com/kevinblumenfeld/4a698dbc90272a336ed9367b11d91f1c) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="90d33-389">If you're interested in learning about more of these options, take a look at this [Gist](https://gist.github.com/kevinblumenfeld/4a698dbc90272a336ed9367b11d91f1c) that [Mark Kraus](https://get-powershellblog.blogspot.com/2016/11/about-mark-kraus.html) put together.</span></span>

## <a name="other-nuances"></a><span data-ttu-id="90d33-390">その他の微妙な違い</span><span class="sxs-lookup"><span data-stu-id="90d33-390">Other nuances</span></span>

<span data-ttu-id="90d33-391">すべての主要な機能について説明したので、これを終わりにする前に触れておきたかったいくつかの点を挙げます。</span><span class="sxs-lookup"><span data-stu-id="90d33-391">Now that I have covered all the major functionality, here are a few more things that I wanted to mention before I wrap this up.</span></span>

### <a name="pre-sized-arrays"></a><span data-ttu-id="90d33-392">事前にサイズ調整された配列</span><span class="sxs-lookup"><span data-stu-id="90d33-392">Pre-sized arrays</span></span>

<span data-ttu-id="90d33-393">配列の作成後にそのサイズを変更できないことについては説明しました。</span><span class="sxs-lookup"><span data-stu-id="90d33-393">I mentioned that you can't change the size of an array once it's created.</span></span> <span data-ttu-id="90d33-394">事前に決められたサイズの配列を作成するには、`new($size)` コンストラクターを使用してそれを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="90d33-394">We can create an array of a pre-determined size by calling it with the `new($size)` constructor.</span></span>

```powershell
$data = [Object[]]::new(4)
$data.count
4
```

### <a name="multiplying-arrays"></a><span data-ttu-id="90d33-395">配列の乗算</span><span class="sxs-lookup"><span data-stu-id="90d33-395">Multiplying arrays</span></span>

<span data-ttu-id="90d33-396">興味深い小技の 1 つに、配列と整数を乗算できることがあります。</span><span class="sxs-lookup"><span data-stu-id="90d33-396">An interesting little trick is that you can multiply an array by an integer.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data * 3
red
green
blue
red
green
blue
red
green
blue
```

### <a name="initialize-with-0"></a><span data-ttu-id="90d33-397">0 で初期化</span><span class="sxs-lookup"><span data-stu-id="90d33-397">Initialize with 0</span></span>

<span data-ttu-id="90d33-398">一般的なシナリオでは、すべてゼロで配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="90d33-398">A common scenario is that you want to create an array with all zeros.</span></span> <span data-ttu-id="90d33-399">整数のみを使用する場合は、厳密に型指定された整数の配列の既定値がすべて 0 になります。</span><span class="sxs-lookup"><span data-stu-id="90d33-399">If you're only going to have integers, a strongly typed array of integers defaults to all zeros.</span></span>

```powershell
PS> [int[]]::new(4)
0
0
0
0
```

<span data-ttu-id="90d33-400">乗算技法を使用してこれを行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="90d33-400">We can use the multiplying trick to do this too.</span></span>

```powershell
PS> $data = @(0) * 4
PS> $data
0
0
0
0
```

<span data-ttu-id="90d33-401">乗算技法には、任意の値を使用できるという良い点があります。</span><span class="sxs-lookup"><span data-stu-id="90d33-401">The nice thing about the multiplying trick is that you can use any value.</span></span> <span data-ttu-id="90d33-402">したがって、既定値として `255` を使用する場合は、この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="90d33-402">So if you would rather have `255` as your default value, this would be a good way to do it.</span></span>

```powershell
PS> $data = @(255) * 4
PS> $data
255
255
255
255
```

### <a name="nested-arrays"></a><span data-ttu-id="90d33-403">入れ子になった配列</span><span class="sxs-lookup"><span data-stu-id="90d33-403">Nested arrays</span></span>

<span data-ttu-id="90d33-404">配列内の配列は、入れ子になった配列と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="90d33-404">An array inside an array is called a nested array.</span></span> <span data-ttu-id="90d33-405">PowerShell ではあまり使用しませんが、他の言語では使用していました。</span><span class="sxs-lookup"><span data-stu-id="90d33-405">I don't use these much in PowerShell but I have used them more in other languages.</span></span> <span data-ttu-id="90d33-406">データがパターンのようなグリッドに収まる場合は、配列の配列を使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="90d33-406">Consider using an array of arrays when your data fits in a grid like pattern.</span></span>

<span data-ttu-id="90d33-407">2 次元配列を作成するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="90d33-407">Here are two ways we can create a two-dimensional array.</span></span>

```powershell
$data = @(@(1,2,3),@(4,5,6),@(7,8,9))

$data2 = @(
    @(1,2,3),
    @(4,5,6),
    @(7,8,9)
)
```

<span data-ttu-id="90d33-408">これらの例では、コンマは非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="90d33-408">The comma is very important in those examples.</span></span> <span data-ttu-id="90d33-409">以前に示した通常の複数行での配列の例では、コンマは省略可能でした。</span><span class="sxs-lookup"><span data-stu-id="90d33-409">I gave an earlier example of a normal array on multiple lines where the comma was optional.</span></span> <span data-ttu-id="90d33-410">多次元配列の場合はそうではありません。</span><span class="sxs-lookup"><span data-stu-id="90d33-410">That isn't the case with a multi-dimensional array.</span></span>

<span data-ttu-id="90d33-411">インデックス表記を使用する方法は、入れ子になった配列を使用するようになったところで多少変更されています。</span><span class="sxs-lookup"><span data-stu-id="90d33-411">The way we use the index notation changes slightly now that we've a nested array.</span></span> <span data-ttu-id="90d33-412">上記の `$data` を使用して、値 3 にアクセスする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="90d33-412">Using the `$data` above, this is how we would access the value 3.</span></span>

```powershell
PS> $outside = 0
PS> $inside = 2
PS> $data[$outside][$inside]
3
```

<span data-ttu-id="90d33-413">配列の入れ子のレベルごとに 1 組の角かっこを追加します。</span><span class="sxs-lookup"><span data-stu-id="90d33-413">Add a set of bracket for each level of array nesting.</span></span> <span data-ttu-id="90d33-414">最初の 1 組の角かっこは、一番外側の配列を対象とし、そこから順番に内側に入っていきます。</span><span class="sxs-lookup"><span data-stu-id="90d33-414">The first set of brackets is for the outer most array and then you work your way in from there.</span></span>

### <a name="write-output--noenumerate"></a><span data-ttu-id="90d33-415">Write-Output -NoEnumerate</span><span class="sxs-lookup"><span data-stu-id="90d33-415">Write-Output -NoEnumerate</span></span>

<span data-ttu-id="90d33-416">PowerShell では、配列のラップ解除または列挙が好まれます。</span><span class="sxs-lookup"><span data-stu-id="90d33-416">PowerShell likes to unwrap or enumerate arrays.</span></span> <span data-ttu-id="90d33-417">これは、PowerShell がパイプラインを使用する方法の主要な側面ですが、場合によってはそれを発生させたくないことがあります。</span><span class="sxs-lookup"><span data-stu-id="90d33-417">This is a core aspect of the way PowerShell uses the pipeline but there are times that you don't want that to happen.</span></span>

<span data-ttu-id="90d33-418">通常、オブジェクトの詳細を学習するには、パイプを使用してオブジェクトを `Get-Member` に渡します。</span><span class="sxs-lookup"><span data-stu-id="90d33-418">I commonly pipe objects to `Get-Member` to learn more about them.</span></span> <span data-ttu-id="90d33-419">パイプを使用して配列をそれに渡すと、ラップが解除され、Get-Member は実際の配列ではなく配列のメンバーを認識します。</span><span class="sxs-lookup"><span data-stu-id="90d33-419">When I pipe an array to it, it gets unwrapped and Get-Member sees the members of the array and not the actual array.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data | Get-Member
TypeName: System.String
...
```

<span data-ttu-id="90d33-420">こうした配列のラップ解除を回避するには、`Write-Object -NoEnumerate` を使用します。</span><span class="sxs-lookup"><span data-stu-id="90d33-420">To prevent that unwrap of the array, you can use `Write-Object -NoEnumerate`.</span></span>

```powershell
PS> Write-Output -NoEnumerate $data | Get-Member
TypeName: System.Object[]
...
```

<span data-ttu-id="90d33-421">ハッキングのような 2 つ目の方法もあります (このようなハッキングは避けるようにしています)。</span><span class="sxs-lookup"><span data-stu-id="90d33-421">I have a second way that's more of a hack (and I try to avoid hacks like this).</span></span> <span data-ttu-id="90d33-422">パイプを使用する前に、配列の前にコンマを配置できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-422">You can place a comma in front of the array before you pipe it.</span></span>

```powershell
PS> ,$data | Get-Member
TypeName: System.Object[]
...
```

### <a name="return-an-array"></a><span data-ttu-id="90d33-423">配列を返す</span><span class="sxs-lookup"><span data-stu-id="90d33-423">Return an array</span></span>

<span data-ttu-id="90d33-424">こうした配列のラップ解除は、関数から値を出力または返す場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="90d33-424">This unwrapping of arrays also happens when you output or return values from a function.</span></span> <span data-ttu-id="90d33-425">出力を変数に割り当てた場合でも配列を取得できるため、通常は問題になりません。</span><span class="sxs-lookup"><span data-stu-id="90d33-425">You can still get an array if you assign the output to a variable so this isn't commonly an issue.</span></span>

<span data-ttu-id="90d33-426">新しい配列があることをキャッチします。</span><span class="sxs-lookup"><span data-stu-id="90d33-426">The catch is that you have a new array.</span></span> <span data-ttu-id="90d33-427">これが問題になる場合は、`Write-Output -NoEnumerate $array` または `return ,$array` を使用して回避できます。</span><span class="sxs-lookup"><span data-stu-id="90d33-427">If that is ever a problem, you can use `Write-Output -NoEnumerate $array` or `return ,$array` to work around it.</span></span>

## <a name="anything-else"></a><span data-ttu-id="90d33-428">その他</span><span class="sxs-lookup"><span data-stu-id="90d33-428">Anything else?</span></span>

<span data-ttu-id="90d33-429">覚えることがたくさんあって大変なことはわかっています。</span><span class="sxs-lookup"><span data-stu-id="90d33-429">I know this is all a lot to take in.</span></span> <span data-ttu-id="90d33-430">これから長い期間にわたって、この記事を読むたびにそこから何かを学び、それがご自身にとってよい参考となれば幸いです。</span><span class="sxs-lookup"><span data-stu-id="90d33-430">My hope is that you learn something from this article every time you read it and that it turns out to be a good reference for you for a long time to come.</span></span> <span data-ttu-id="90d33-431">これが役に立つことがわかった場合は、そこから価値を得ることができると思われる他のユーザーと共有してください。</span><span class="sxs-lookup"><span data-stu-id="90d33-431">If you found this to be helpful, please share it with others you think may get value out of it.</span></span>

<span data-ttu-id="90d33-432">この場から、[ハッシュテーブル][]について記述した同様の投稿を確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="90d33-432">From here, I would recommend you check out a similar post that I wrote about [hashtables][].</span></span>

<!-- link references -->
[オリジナル バージョン]: https://powershellexplained.com/2018-10-15-Powershell-arrays-Everything-you-wanted-to-know/
[original version]: https://powershellexplained.com/2018-10-15-Powershell-arrays-Everything-you-wanted-to-know/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[配列]: /powershell/module/microsoft.powershell.core/about/about_arrays
[Arrays]: /powershell/module/microsoft.powershell.core/about/about_arrays
[switch ステートメント]: everything-about-switch.md
[switch statement]: everything-about-switch.md
[ハッシュテーブル]: everything-about-hashtable.md
[hashtables]: everything-about-hashtable.md
[正規表現を使用するさまざまな方法]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[The many ways to use regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[配列内のすべての値が指定された値と一致するかどうかを確認する方法]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition
[how to verify that every value in an array matches a given value]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition
[解決方法]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition/e7iizca
[solution]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition/e7iizca
[StringBuilder]: https://powershellexplained.com/2017-11-20-Powershell-StringBuilder/
