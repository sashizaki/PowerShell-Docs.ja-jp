---
title: ハッシュテーブルについて知りたかったことのすべて
description: ハッシュテーブルは PowerShell で非常に重要であるため、十分に理解しておくことをお勧めします。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 1539cf6444cab718c1108384c640193d66c85daf
ms.sourcegitcommit: 0c31814bed14ff715dc7d4aace07cbdc6df2438e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "93354424"
---
# <a name="everything-you-wanted-to-know-about-hashtables"></a><span data-ttu-id="d45b9-103">ハッシュテーブルについて知りたかったことのすべて</span><span class="sxs-lookup"><span data-stu-id="d45b9-103">Everything you wanted to know about hashtables</span></span>

<span data-ttu-id="d45b9-104">ここでは、一歩下がって、[ハッシュテーブル][]について説明します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-104">I want to take a step back and talk about [hashtables][].</span></span> <span data-ttu-id="d45b9-105">私は現在は常に使用しています。</span><span class="sxs-lookup"><span data-stu-id="d45b9-105">I use them all the time now.</span></span> <span data-ttu-id="d45b9-106">昨晩ユーザー グループミーティングの後、これに関してあるユーザーに説明していたとき、私にも同じ混乱が生じていたことに気付きました。</span><span class="sxs-lookup"><span data-stu-id="d45b9-106">I was teaching someone about them after our user group meeting last night and I realized I had the same confusion about them as he had.</span></span> <span data-ttu-id="d45b9-107">ハッシュテーブルは PowerShell で非常に重要であるため、十分に理解しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d45b9-107">Hashtables are really important in PowerShell so it's good to have a solid understanding of them.</span></span>

> [!NOTE]
> <span data-ttu-id="d45b9-108">この記事の[オリジナル バージョン][]は、[@KevinMarquette][] 氏のブログ記事です。</span><span class="sxs-lookup"><span data-stu-id="d45b9-108">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="d45b9-109">このコンテンツを共有してくださった Kevin 氏に、PowerShell チームより感謝を申し上げます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-109">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="d45b9-110">[PowerShellExplained.com][] のブログをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="d45b9-110">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="hashtable-as-a-collection-of-things"></a><span data-ttu-id="d45b9-111">もののコレクションとしてのハッシュテーブル</span><span class="sxs-lookup"><span data-stu-id="d45b9-111">Hashtable as a collection of things</span></span>

<span data-ttu-id="d45b9-112">まず、ハッシュテーブルの従来の定義どおり、**ハッシュテーブル** をコレクションとして見てください。</span><span class="sxs-lookup"><span data-stu-id="d45b9-112">I want you to first see a **Hashtable** as a collection in the traditional definition of a hashtable.</span></span> <span data-ttu-id="d45b9-113">この定義により、後でより高度なことに使用する場合の動作に関する基本的な理解が得られます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-113">This definition gives you a fundamental understanding of how they work when they get used for more advanced stuff later.</span></span> <span data-ttu-id="d45b9-114">この理解をスキップすることは、多くの場合、混乱の原因になります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-114">Skipping this understanding is often a source of confusion.</span></span>

## <a name="what-is-an-array"></a><span data-ttu-id="d45b9-115">配列とは</span><span class="sxs-lookup"><span data-stu-id="d45b9-115">What is an array?</span></span>

<span data-ttu-id="d45b9-116">**ハッシュテーブル** とは何かを説明する前に、まず [配列][]について説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-116">Before I jump into what a **Hashtable** is, I need to mention [arrays][] first.</span></span> <span data-ttu-id="d45b9-117">このディスカッションでは、配列は値またはオブジェクトのリストまたはコレクションです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-117">For the purpose of this discussion, an array is a list or collection of values or objects.</span></span>

```powershell
$array = @(1,2,3,5,7,11)
```

<span data-ttu-id="d45b9-118">項目を配列に格納したら、`foreach` を使用してリストを反復処理するか、インデックスを使用して配列内の個々の要素にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-118">Once you have your items into an array, you can either use `foreach` to iterate over the list or use an index to access individual elements in the array.</span></span>

```powershell
foreach($item in $array)
{
    Write-Output $item
}

Write-Output $array[3]
```

<span data-ttu-id="d45b9-119">また、同じ方法でインデックスを使用して値を更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-119">You can also update values using an index in the same way.</span></span>

```powershell
$array[2] = 13
```

<span data-ttu-id="d45b9-120">配列のほんの一部に触れただけですが、ハッシュテーブルに進むときに、配列を適切なコンテキストに組み込んでくれるはずです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-120">I just scratched the surface on arrays but that should put them into the right context as I move onto hashtables.</span></span>

## <a name="what-is-a-hashtable"></a><span data-ttu-id="d45b9-121">ハッシュテーブルとは</span><span class="sxs-lookup"><span data-stu-id="d45b9-121">What is a hashtable?</span></span>

<span data-ttu-id="d45b9-122">まず、一般的な意味でハッシュテーブルとは何かについて基本的な技術説明を行った後、PowerShell でのその他の使用方法に移ります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-122">I'm going to start with a basic technical description of what hashtables are, in the general sense, before I shift into the other ways PowerShell uses them.</span></span>

<span data-ttu-id="d45b9-123">ハッシュテーブルは配列によく似たデータ構造ですが、キーを使用して各値 (オブジェクト) を格納する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-123">A hashtable is a data structure, much like an array, except you store each value (object) using a key.</span></span> <span data-ttu-id="d45b9-124">これは基本的なキー/値ストアです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-124">It's a basic key/value store.</span></span> <span data-ttu-id="d45b9-125">まず、空のハッシュテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-125">First, we create an empty hashtable.</span></span>

```powershell
$ageList = @{}
```

<span data-ttu-id="d45b9-126">ハッシュテーブルを定義するには、かっこではなく中かっこを使用することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d45b9-126">Notice that braces, instead of parentheses, are used to define a hashtable.</span></span> <span data-ttu-id="d45b9-127">その後、次のようなキーを使用して項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-127">Then we add an item using a key like this:</span></span>

```powershell
$key = 'Kevin'
$value = 36
$ageList.add( $key, $value )

$ageList.add( 'Alex', 9 )
```

<span data-ttu-id="d45b9-128">人の名前がキーで、その年齢が保存する値です。</span><span class="sxs-lookup"><span data-stu-id="d45b9-128">The person's name is the key and their age is the value that I want to save.</span></span>

## <a name="using-the-brackets-for-access"></a><span data-ttu-id="d45b9-129">アクセスに角かっこを使用する</span><span class="sxs-lookup"><span data-stu-id="d45b9-129">Using the brackets for access</span></span>

<span data-ttu-id="d45b9-130">ハッシュテーブルに値を追加したら、同じキーを使用してその値を取り出すことができます (配列の場合のように数値インデックスを使用するのではなく)。</span><span class="sxs-lookup"><span data-stu-id="d45b9-130">Once you add your values to the hashtable, you can pull them back out using that same key (instead of using a numeric index like you would have for an array).</span></span>

```powershell
$ageList['Kevin']
$ageList['Alex']
```

<span data-ttu-id="d45b9-131">Kevin の年齢を取得したい場合は、彼の名前を使用してアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d45b9-131">When I want Kevin's age, I use his name to access it.</span></span> <span data-ttu-id="d45b9-132">このアプローチを使用して、ハッシュテーブルの値の追加または更新もできます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-132">We can use this approach to add or update values into the hashtable too.</span></span> <span data-ttu-id="d45b9-133">これは、上記の `add()` 関数を使用する場合と似ています。</span><span class="sxs-lookup"><span data-stu-id="d45b9-133">This is just like using the `add()` function above.</span></span>

```powershell
$ageList = @{}

$key = 'Kevin'
$value = 36
$ageList[$key] = $value

$ageList['Alex'] = 9
```

<span data-ttu-id="d45b9-134">値にアクセスして更新するために使用できるもう 1 つの構文があり、それについては後のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-134">There's another syntax you can use for accessing and updating values that I'll cover in a later section.</span></span> <span data-ttu-id="d45b9-135">別の言語から PowerShell に移ってきたユーザーにとって、これらの例は、これまでハッシュテーブルを使用してきた方法に合致しているでしょう。</span><span class="sxs-lookup"><span data-stu-id="d45b9-135">If you're coming to PowerShell from another language, these examples should fit in with how you may have used hashtables before.</span></span>

### <a name="creating-hashtables-with-values"></a><span data-ttu-id="d45b9-136">値を含むハッシュテーブルの作成</span><span class="sxs-lookup"><span data-stu-id="d45b9-136">Creating hashtables with values</span></span>

<span data-ttu-id="d45b9-137">ここまでの例では、空のハッシュテーブルを作成しました。</span><span class="sxs-lookup"><span data-stu-id="d45b9-137">So far I've created an empty hashtable for these examples.</span></span> <span data-ttu-id="d45b9-138">作成時にキーと値をあらかじめ設定できます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-138">You can pre-populate the keys and values when you create them.</span></span>

```powershell
$ageList = @{
    Kevin = 36
    Alex  = 9
}
```

### <a name="as-a-lookup-table"></a><span data-ttu-id="d45b9-139">ルックアップ テーブルとして</span><span class="sxs-lookup"><span data-stu-id="d45b9-139">As a lookup table</span></span>

<span data-ttu-id="d45b9-140">この種類のハッシュテーブルは、ルックアップ テーブルとして使用できることに真の価値があります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-140">The real value of this type of a hashtable is that you can use them as a lookup table.</span></span> <span data-ttu-id="d45b9-141">単純な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-141">Here is a simple example.</span></span>

```powershell
$environments = @{
    Prod = 'SrvProd05'
    QA   = 'SrvQA02'
    Dev  = 'SrvDev12'
}

$server = $environments[$env]
```

<span data-ttu-id="d45b9-142">この例では、`$env` 変数に環境を指定することで、適切なサーバーが選択されます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-142">In this example, you specify an environment for the `$env` variable and it will pick the correct server.</span></span> <span data-ttu-id="d45b9-143">このような選択には `switch($env){...}` を使用することもできますが、ハッシュテーブルは便利なオプションです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-143">You could use a `switch($env){...}` for a selection like this but a hashtable is a nice option.</span></span>

<span data-ttu-id="d45b9-144">これは、後で使用するためにルックアップ テーブルを動的に構築する場合に、さらに優れています。</span><span class="sxs-lookup"><span data-stu-id="d45b9-144">This gets even better when you dynamically build the lookup table to use it later.</span></span> <span data-ttu-id="d45b9-145">したがって、何かを相互参照する必要がある場合は、このアプローチの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="d45b9-145">So think about using this approach when you need to cross reference something.</span></span> <span data-ttu-id="d45b9-146">PowerShell での `Where-Object` によるパイプのフィルター処理がそれほど優れていなければ、これをさらに多く目にするだろうと思います。</span><span class="sxs-lookup"><span data-stu-id="d45b9-146">I think we would see this even more if PowerShell wasn't so good at filtering on the pipe with `Where-Object`.</span></span> <span data-ttu-id="d45b9-147">パフォーマンスが重要になる状況では、このアプローチを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-147">If you're ever in a situation where performance matters, this approach needs to be considered.</span></span>

<span data-ttu-id="d45b9-148">より高速であるとは言えませんが、[パフォーマンスが重要ならテストせよ][]という規則に適合します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-148">I won't say that it's faster, but it does fit into the rule of [If performance matters, test it][].</span></span>

#### <a name="multiselection"></a><span data-ttu-id="d45b9-149">複数選択</span><span class="sxs-lookup"><span data-stu-id="d45b9-149">Multiselection</span></span>

<span data-ttu-id="d45b9-150">一般に、ハッシュテーブルはキーと値のペアと考えることができます。そこでは、1 つのキーを指定し、1 つの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-150">Generally, you think of a hashtable as a key/value pair, where you provide one key and get one value.</span></span> <span data-ttu-id="d45b9-151">PowerShell では、複数の値を取得するためにキーの配列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-151">PowerShell allows you to provide an array of keys to get multiple values.</span></span>

```powershell
$environments[@('QA','DEV')]
$environments[('QA','DEV')]
$environments['QA','DEV']
```

<span data-ttu-id="d45b9-152">この例では、上記と同じルックアップ ハッシュテーブルを使用し、3 つの異なる配列スタイルを指定して一致項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-152">In this example, I use the same lookup hashtable from above and provide three different array styles to get the matches.</span></span> <span data-ttu-id="d45b9-153">これは、ほとんどの方が気付いていない PowerShell の隠された宝石です。</span><span class="sxs-lookup"><span data-stu-id="d45b9-153">This is a hidden gem in PowerShell that most people aren't aware of.</span></span>

## <a name="iterating-hashtables"></a><span data-ttu-id="d45b9-154">ハッシュテーブルの反復処理</span><span class="sxs-lookup"><span data-stu-id="d45b9-154">Iterating hashtables</span></span>

<span data-ttu-id="d45b9-155">ハッシュテーブルはキーと値のペアのコレクションであるため、配列または通常の項目リストとは異なる方法で反復処理します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-155">Because a hashtable is a collection of key/value pairs, you iterate over it differently than you do for an array or a normal list of items.</span></span>

<span data-ttu-id="d45b9-156">まず注目すべき点は、ハッシュテーブルをパイプ処理するとき、ハッシュテーブルは 1 つのオブジェクトのように扱われるということです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-156">The first thing to notice is that if you pipe your hashtable, the pipe treats it like one object.</span></span>

```powershell
PS> $ageList | Measure-Object
count : 1
```

<span data-ttu-id="d45b9-157">ただし、それに含まれる値の数は `.count` プロパティでわかります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-157">Even though the `.count` property tells you how many values it contains.</span></span>

```powershell
PS> $ageList.count
2
```

<span data-ttu-id="d45b9-158">値だけが必要な場合は、`.values` プロパティを使用してこの問題を回避します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-158">You get around this issue by using the `.values` property if all you need is just the values.</span></span>

```powershell
PS> $ageList.values | Measure-Object -Average
Count   : 2
Average : 22.5
```

<span data-ttu-id="d45b9-159">多くの場合、キーを列挙し、それらを使用して値にアクセスする方が便利です。</span><span class="sxs-lookup"><span data-stu-id="d45b9-159">It's often more useful to enumerate the keys and use them to access the values.</span></span>

```powershell
PS> $ageList.keys | ForEach-Object{
    $message = '{0} is {1} years old!' -f $_, $ageList[$_]
    Write-Output $message
}
Kevin is 36 years old
Alex is 9 years old
```

<span data-ttu-id="d45b9-160">`foreach(){...}` ループを使用した同じ例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-160">Here is the same example with a `foreach(){...}` loop.</span></span>

```powershell
foreach($key in $ageList.keys)
{
    $message = '{0} is {1} years old' -f $key, $ageList[$key]
    Write-Output $message
}
```

<span data-ttu-id="d45b9-161">ハッシュテーブルの各キーを順に調べ、それを使用して値にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d45b9-161">We are walking each key in the hashtable and then using it to access the value.</span></span> <span data-ttu-id="d45b9-162">これは、ハッシュテーブルをコレクションとして使用する場合の一般的なパターンです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-162">This is a common pattern when working with hashtables as a collection.</span></span>

### <a name="getenumerator"></a><span data-ttu-id="d45b9-163">GetEnumerator()</span><span class="sxs-lookup"><span data-stu-id="d45b9-163">GetEnumerator()</span></span>

<span data-ttu-id="d45b9-164">ここで、ハッシュテーブルを反復処理するために `GetEnumerator()` を使用します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-164">That brings us to `GetEnumerator()` for iterating over our hashtable.</span></span>

```powershell
$ageList.GetEnumerator() | ForEach-Object{
    $message = '{0} is {1} years old!' -f $_.key, $_.value
    Write-Output $message
}
```

<span data-ttu-id="d45b9-165">この列挙子は、各キーと値のペアを 1 つずつ渡してくれます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-165">The enumerator gives you each key/value pair one after another.</span></span> <span data-ttu-id="d45b9-166">このユース ケース専用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="d45b9-166">It was designed specifically for this use case.</span></span> <span data-ttu-id="d45b9-167">このことを思い出させてくれた [Mark Kraus](https://get-PowerShellblog.blogspot.com) さんに感謝いたします。</span><span class="sxs-lookup"><span data-stu-id="d45b9-167">Thank you to [Mark Kraus](https://get-PowerShellblog.blogspot.com) for reminding me of this one.</span></span>

### <a name="badenumeration"></a><span data-ttu-id="d45b9-168">BadEnumeration</span><span class="sxs-lookup"><span data-stu-id="d45b9-168">BadEnumeration</span></span>

<span data-ttu-id="d45b9-169">重要な詳細の 1 つは、列挙中はハッシュテーブルを変更できないことです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-169">One important detail is that you can't modify a hashtable while it's being enumerated.</span></span> <span data-ttu-id="d45b9-170">基本的な `$environments` の例から始めます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-170">If we start with our basic `$environments` example:</span></span>

```powershell
$environments = @{
    Prod = 'SrvProd05'
    QA   = 'SrvQA02'
    Dev  = 'SrvDev12'
}
```

<span data-ttu-id="d45b9-171">すべてのキーを同じサーバー値に設定しようとすると失敗します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-171">And trying to set every key to the same server value fails.</span></span>

```powershell
$environments.Keys | ForEach-Object {
    $environments[$_] = 'SrvDev03'
}

An error occurred while enumerating through a collection: Collection was modified; enumeration operation may not execute.
+ CategoryInfo          : InvalidOperation: tableEnumerator:HashtableEnumerator) [], RuntimeException
+ FullyQualifiedErrorId : BadEnumeration
```

<span data-ttu-id="d45b9-172">これも問題ないように見えますが、やはり失敗します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-172">This will also fail even though it looks like it should also be fine:</span></span>

```powershell
foreach($key in $environments.keys) {
    $environments[$key] = 'SrvDev03'
}

Collection was modified; enumeration operation may not execute.
    + CategoryInfo          : OperationStopped: (:) [], InvalidOperationException
    + FullyQualifiedErrorId : System.InvalidOperationException
```

<span data-ttu-id="d45b9-173">この状況に対処する秘訣は、列挙を行う前にキーを複製することです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-173">The trick to this situation is to clone the keys before doing the enumeration.</span></span>

```powershell
$environments.Keys.Clone() | ForEach-Object {
    $environments[$_] = 'SrvDev03'
}
```

## <a name="hashtable-as-a-collection-of-properties"></a><span data-ttu-id="d45b9-174">プロパティのコレクションとしてのハッシュテーブル</span><span class="sxs-lookup"><span data-stu-id="d45b9-174">Hashtable as a collection of properties</span></span>

<span data-ttu-id="d45b9-175">ここまでは、ハッシュテーブルに配置したオブジェクトの型はすべて同じ型のオブジェクトでした。</span><span class="sxs-lookup"><span data-stu-id="d45b9-175">So far the type of objects we placed in our hashtable were all the same type of object.</span></span> <span data-ttu-id="d45b9-176">これらのすべての例で年齢を使用し、キーは人の名前でした。</span><span class="sxs-lookup"><span data-stu-id="d45b9-176">I used ages in all those examples and the key was the person's name.</span></span> <span data-ttu-id="d45b9-177">これは、それぞれに名前が付いているオブジェクトのコレクションでは、それを確認するための優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="d45b9-177">This is a great way to look at it when your collection of objects each have a name.</span></span> <span data-ttu-id="d45b9-178">PowerShell でハッシュテーブルを使用するもう 1 つの一般的な方法は、プロパティの名前をキーとして持つプロパティのコレクションを保持することです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-178">Another common way to use hashtables in PowerShell is to hold a collection of properties where the key is the name of the property.</span></span> <span data-ttu-id="d45b9-179">次の例では、このことについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-179">I'll step into that idea in this next example.</span></span>

### <a name="property-based-access"></a><span data-ttu-id="d45b9-180">プロパティベースのアクセス</span><span class="sxs-lookup"><span data-stu-id="d45b9-180">Property-based access</span></span>

<span data-ttu-id="d45b9-181">プロパティベースのアクセスを使用すると、ハッシュテーブルのダイナミクスと PowerShell での使用方法が変わります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-181">The use of property-based access changes the dynamics of hashtables and how you can use them in PowerShell.</span></span> <span data-ttu-id="d45b9-182">上記の例で、キーをプロパティとして扱う例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-182">Here is our usual example from above treating the keys as properties.</span></span>

```powershell
$ageList = @{}
$ageList.Kevin = 35
$ageList.Alex = 9
```

<span data-ttu-id="d45b9-183">上記の例と同じように、この例では、まだハッシュテーブルに存在しないキーは追加されます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-183">Just like the examples above, this example adds those keys if they don't exist in the hashtable already.</span></span> <span data-ttu-id="d45b9-184">キーの定義方法と値の種類によって、これは少し奇妙なものか、最高の選択肢になります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-184">Depending on how you defined your keys and what your values are, this is either a little strange or a perfect fit.</span></span> <span data-ttu-id="d45b9-185">この時点までは、年齢リストの例はうまく機能しています。</span><span class="sxs-lookup"><span data-stu-id="d45b9-185">The age list example has worked great up until this point.</span></span> <span data-ttu-id="d45b9-186">納得して先へ進むには、このための新しい例が必要です。</span><span class="sxs-lookup"><span data-stu-id="d45b9-186">We need a new example for this to feel right going forward.</span></span>

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
}
```

<span data-ttu-id="d45b9-187">このように `$person` に属性を追加してアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-187">And we can add and access attributes on the `$person` like this.</span></span>

```powershell
$person.city = 'Austin'
$person.state = 'TX'
```

<span data-ttu-id="d45b9-188">このハッシュテーブルは、突然、オブジェクトのように機能し始めます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-188">All of a sudden this hashtable starts to feel and act like an object.</span></span> <span data-ttu-id="d45b9-189">まだもののコレクションであるため、上記のすべての例が引き続き適用されます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-189">It's still a collection of things, so all the examples above still apply.</span></span> <span data-ttu-id="d45b9-190">ここでは、別の観点からアプローチします。</span><span class="sxs-lookup"><span data-stu-id="d45b9-190">We just approach it from a different point of view.</span></span>

### <a name="checking-for-keys-and-values"></a><span data-ttu-id="d45b9-191">キーと値の確認</span><span class="sxs-lookup"><span data-stu-id="d45b9-191">Checking for keys and values</span></span>

<span data-ttu-id="d45b9-192">ほとんどの場合、次のような方法で値をテストできます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-192">In most cases, you can just test for the value with something like this:</span></span>

```powershell
if( $person.age ){...}
```

<span data-ttu-id="d45b9-193">これは単純ですが、私はこのロジックで 1 つの重要な詳細を見落とししていたため、多くのバグの原因になっていました。</span><span class="sxs-lookup"><span data-stu-id="d45b9-193">It's simple but has been the source of many bugs for me because I was overlooking one important detail in my logic.</span></span> <span data-ttu-id="d45b9-194">キーが存在するかどうかをテストするために使用しました。</span><span class="sxs-lookup"><span data-stu-id="d45b9-194">I started to use it to test if a key was present.</span></span> <span data-ttu-id="d45b9-195">値が `$false` または 0 の場合、そのステートメントは予期せず `$false` を返しました。</span><span class="sxs-lookup"><span data-stu-id="d45b9-195">When the value was `$false` or zero, that statement would return `$false` unexpectedly.</span></span>

```powershell
if( $person.age -ne $null ){...}
```

<span data-ttu-id="d45b9-196">これは、0 の値に対してはこの問題を回避しますが、$null と存在しないキーの比較では回避できません。</span><span class="sxs-lookup"><span data-stu-id="d45b9-196">This works around that issue for zero values but not $null vs non-existent keys.</span></span> <span data-ttu-id="d45b9-197">ほとんどの場合、この区別を行う必要はありませんが、区別が必要な場合にはそのための関数があります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-197">Most of the time you don't need to make that distinction but there are functions for when you do.</span></span>

```powershell
if( $person.ContainsKey('age') ){...}
```

<span data-ttu-id="d45b9-198">また、キーがわからない場合に値をテストする、またはコレクション全体を反復処理しながら値をテストする必要がある状況では、`ContainsValue()` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-198">We also have a `ContainsValue()` for the situation where you need to test for a value without knowing the key or iterating the whole collection.</span></span>

### <a name="removing-and-clearing-keys"></a><span data-ttu-id="d45b9-199">キーの削除とクリア</span><span class="sxs-lookup"><span data-stu-id="d45b9-199">Removing and clearing keys</span></span>

<span data-ttu-id="d45b9-200">`.Remove()` 関数を使用してキーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-200">You can remove keys with the `.Remove()` function.</span></span>

```powershell
$person.remove('age')
```

<span data-ttu-id="d45b9-201">`$null` 値を割り当てると、`$null` 値を持つキーが残ります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-201">Assigning them a `$null` value just leaves you with a key that has a `$null` value.</span></span>

<span data-ttu-id="d45b9-202">ハッシュテーブルをクリアする一般的な方法は、空のハッシュテーブルに初期化することです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-202">A common way to clear a hashtable is to just initialize it to an empty hashtable.</span></span>

```powershell
$person = @{}
```

<span data-ttu-id="d45b9-203">それでも機能しますが、代わりに `clear()` 関数を使用してみてください。</span><span class="sxs-lookup"><span data-stu-id="d45b9-203">While that does work, try to use the `clear()` function instead.</span></span>

```powershell
$person.clear()
```

<span data-ttu-id="d45b9-204">これは、関数を使用することで自己文書化コードを実現し、コードの意図を明確にできる事例の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-204">This is one of those instances where using the function creates self-documenting code and it makes the intentions of the code very clean.</span></span>

## <a name="all-the-fun-stuff"></a><span data-ttu-id="d45b9-205">すべての楽しいもの</span><span class="sxs-lookup"><span data-stu-id="d45b9-205">All the fun stuff</span></span>

### <a name="ordered-hashtables"></a><span data-ttu-id="d45b9-206">順序付きハッシュテーブル</span><span class="sxs-lookup"><span data-stu-id="d45b9-206">Ordered hashtables</span></span>

<span data-ttu-id="d45b9-207">既定では、ハッシュテーブルは順序付け (または並べ替え) されていません。</span><span class="sxs-lookup"><span data-stu-id="d45b9-207">By default, hashtables aren't ordered (or sorted).</span></span> <span data-ttu-id="d45b9-208">従来のコンテキストでは、常にキーを使用して値にアクセスする場合、順序は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="d45b9-208">In the traditional context, the order doesn't matter when you always use a key to access values.</span></span> <span data-ttu-id="d45b9-209">プロパティを定義した順序で維持する必要が生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-209">You may find that you want the properties to stay in the order that you define them.</span></span> <span data-ttu-id="d45b9-210">幸いにも、`ordered` キーワードを使用してこれを行う方法があります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-210">Thankfully, there's a way to do that with the `ordered` keyword.</span></span>

```powershell
$person = [ordered]@{
    name = 'Kevin'
    age  = 36
}
```

<span data-ttu-id="d45b9-211">これで、キーと値を列挙すると、その順序が維持されるようになります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-211">Now when you enumerate the keys and values, they stay in that order.</span></span>

### <a name="inline-hashtables"></a><span data-ttu-id="d45b9-212">インライン ハッシュテーブル</span><span class="sxs-lookup"><span data-stu-id="d45b9-212">Inline hashtables</span></span>

<span data-ttu-id="d45b9-213">1 行にハッシュテーブルを定義する場合は、キーと値のペアをセミコロンで区切ることができます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-213">When you're defining a hashtable on one line, you can separate the key/value pairs with a semicolon.</span></span>

```powershell
$person = @{ name = 'kevin'; age = 36; }
```

<span data-ttu-id="d45b9-214">これは、パイプで作成する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="d45b9-214">This will come in handy if you're creating them on the pipe.</span></span>

### <a name="custom-expressions-in-common-pipeline-commands"></a><span data-ttu-id="d45b9-215">一般的なパイプライン コマンドのカスタム式</span><span class="sxs-lookup"><span data-stu-id="d45b9-215">Custom expressions in common pipeline commands</span></span>

<span data-ttu-id="d45b9-216">ハッシュテーブルを使用してカスタム プロパティや計算されるプロパティを作成するためのコマンドレットがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-216">There are a few cmdlets that support the use of hashtables to create custom or calculated properties.</span></span> <span data-ttu-id="d45b9-217">これは一般的に `Select-Object` と `Format-Table` で使用されます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-217">You commonly see this with `Select-Object` and `Format-Table`.</span></span> <span data-ttu-id="d45b9-218">ハッシュテーブルには特殊な構文があり、完全に展開すると次のようなものです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-218">The hashtables have a special syntax that looks like this when fully expanded.</span></span>

```powershell
$property = @{
    name = 'totalSpaceGB'
    expression = { ($_.used + $_.free) / 1GB }
}
```

<span data-ttu-id="d45b9-219">`name` は、コマンドレットがその列に付けるラベルです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-219">The `name` is what the cmdlet would label that column.</span></span> <span data-ttu-id="d45b9-220">`expression` は実行されるスクリプト ブロックで、`$_` はパイプのオブジェクトの値です。</span><span class="sxs-lookup"><span data-stu-id="d45b9-220">The `expression` is a script block that is executed where `$_` is the value of the object on the pipe.</span></span> <span data-ttu-id="d45b9-221">このスクリプトの動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-221">Here is that script in action:</span></span>

```powershell
$drives = Get-PSDrive | Where Used
$drives | Select-Object -Properties name, $property

Name     totalSpaceGB
----     ------------
C    238.472652435303
```

<span data-ttu-id="d45b9-222">変数に配置しましたが、インラインで簡単に定義することもできます。また、`name` を `n` に短縮し、`expression` を `e` に短縮できます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-222">I placed that in a variable but it could easily be defined inline and you can shorten `name` to `n` and `expression` to `e` while you're at it.</span></span>

```powershell
$drives | Select-Object -properties name, @{n='totalSpaceGB';e={($_.used + $_.free) / 1GB}}
```

<span data-ttu-id="d45b9-223">コマンドが長くなるうえ、説明は省きますが問題のある行動を助長させることも多いため、個人的には好きではありません。</span><span class="sxs-lookup"><span data-stu-id="d45b9-223">I personally don't like how long that makes commands and it often promotes some bad behaviors that I won't get into.</span></span> <span data-ttu-id="d45b9-224">私なら、スクリプトでこのアプローチを使用する代わりに、必要なすべてのフィールドとプロパティを含む新しいハッシュテーブルまたは `pscustomobject` を作成するでしょう。</span><span class="sxs-lookup"><span data-stu-id="d45b9-224">I'm more likely to create a new hashtable or `pscustomobject` with all the fields and properties that I want instead of using this approach in scripts.</span></span> <span data-ttu-id="d45b9-225">しかし、これを行うコードはたくさんあるため、認識していただくことが目的でした。</span><span class="sxs-lookup"><span data-stu-id="d45b9-225">But there's a lot of code out there that does this so I wanted you to be aware of it.</span></span> <span data-ttu-id="d45b9-226">`pscustomobject` の作成については後で説明します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-226">I talk about creating a `pscustomobject` later on.</span></span>

### <a name="custom-sort-expression"></a><span data-ttu-id="d45b9-227">カスタムの並べ替え式</span><span class="sxs-lookup"><span data-stu-id="d45b9-227">Custom sort expression</span></span>

<span data-ttu-id="d45b9-228">並べ替えの対象となるデータがオブジェクトに含まれている場合は、コレクションを簡単に並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-228">It's easy to sort a collection if the objects have the data that you want to sort on.</span></span> <span data-ttu-id="d45b9-229">並べ替える前にオブジェクトにデータを追加するか、`Sort-Object` のカスタム式を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-229">You can either add the data to the object before you sort it or create a custom expression for `Sort-Object`.</span></span>

```powershell
Get-ADUser | Sort-Object -Parameter @{ e={ Get-TotalSales $_.Name } }
```

<span data-ttu-id="d45b9-230">この例では、ユーザーの一覧を取得し、いくつかのカスタム コマンドレットを使用して、並べ替えのためだけに追加情報を取得しています。</span><span class="sxs-lookup"><span data-stu-id="d45b9-230">In this example I'm taking a list of users and using some custom cmdlet to get additional information just for the sort.</span></span>

#### <a name="sort-a-list-of-hashtables"></a><span data-ttu-id="d45b9-231">ハッシュテーブルの一覧の並べ替え</span><span class="sxs-lookup"><span data-stu-id="d45b9-231">Sort a list of Hashtables</span></span>

<span data-ttu-id="d45b9-232">ハッシュテーブルの一覧を並べ替える場合、`Sort-Object` ではキーがプロパティとして扱われないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-232">If you have a list of hashtables that you want to sort, you'll find that the `Sort-Object` doesn't treat your keys as properties.</span></span> <span data-ttu-id="d45b9-233">カスタムの並べ替え式を使用することで、これを回避できます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-233">We can get a round that by using a custom sort expression.</span></span>

```powershell
$data = @(
    @{name='a'}
    @{name='c'}
    @{name='e'}
    @{name='f'}
    @{name='d'}
    @{name='b'}
)

$data | Sort-Object -Property @{e={$_.name}}
```

## <a name="splatting-hashtables-at-cmdlets"></a><span data-ttu-id="d45b9-234">コマンドレットでのハッシュテーブルのスプラッティング</span><span class="sxs-lookup"><span data-stu-id="d45b9-234">Splatting hashtables at cmdlets</span></span>

<span data-ttu-id="d45b9-235">これはハッシュテーブルに関する私のお気に入りの 1 つで、早い段階で気付く人は少ないでしょう。</span><span class="sxs-lookup"><span data-stu-id="d45b9-235">This is one of my favorite things about hashtables that many people don't discover early on.</span></span>
<span data-ttu-id="d45b9-236">すべてのプロパティを 1 行でコマンドレットに渡すのではなく、まずハッシュテーブルにパッケージ化するというアイデアです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-236">The idea is that instead of providing all the properties to a cmdlet on one line, you can instead pack them into a hashtable first.</span></span> <span data-ttu-id="d45b9-237">その後、特別な方法でハッシュテーブルを関数に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-237">Then you can give the hashtable to the function in a special way.</span></span>
<span data-ttu-id="d45b9-238">通常の方法で DHCP スコープを作成する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-238">Here is an example of creating a DHCP scope the normal way.</span></span>

```powershell
Add-DhcpServerv4Scope -Name 'TestNetwork' -StartRange'10.0.0.2' -EndRange '10.0.0.254' -SubnetMask '255.255.255.0' -Description 'Network for testlab A' -LeaseDuration (New-TimeSpan -Days 8) -Type "Both"
```

<span data-ttu-id="d45b9-239">[スプラッティング][]を使用しない場合は、これらすべてを 1 行で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-239">Without using [splatting][], all those things need to be defined on a single line.</span></span> <span data-ttu-id="d45b9-240">画面の外にはみ出るか、適当な場所で折り返されます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-240">It either scrolls off the screen or will wrap where ever it feels like.</span></span> <span data-ttu-id="d45b9-241">ここで、スプラッティングを使用するコマンドと比較します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-241">Now compare that to a command that uses splatting.</span></span>

```powershell
$DHCPScope = @{
    Name        = 'TestNetwork'
    StartRange  = '10.0.0.2'
    EndRange    = '10.0.0.254'
    SubnetMask  = '255.255.255.0'
    Description = 'Network for testlab A'
    LeaseDuration = (New-TimeSpan -Days 8)
    Type = "Both"
}
Add-DhcpServerv4Scope @DHCPScope
```

<span data-ttu-id="d45b9-242">`$` ではなく `@` 記号を使用することで、スプラッティング操作が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-242">The use of the `@` sign instead of the `$` is what invokes the splat operation.</span></span>

<span data-ttu-id="d45b9-243">少し時間を取って、その例がいかに読みやすいかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d45b9-243">Just take a moment to appreciate how easy that example is to read.</span></span> <span data-ttu-id="d45b9-244">これらはすべて同じ値を使用したまったく同じコマンドです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-244">They are the exact same command with all the same values.</span></span> <span data-ttu-id="d45b9-245">2 つ目の方法は、理解しやすく、今後も維持しやすくなっています。</span><span class="sxs-lookup"><span data-stu-id="d45b9-245">The second one is easier to understand and maintain going forward.</span></span>

<span data-ttu-id="d45b9-246">コマンドが長くなりすぎる場合、私は常にスプラッティングを使用します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-246">I use splatting anytime the command gets too long.</span></span> <span data-ttu-id="d45b9-247">定義が長すぎると、ウィンドウが右にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="d45b9-247">I define too long as causing my window to scroll right.</span></span> <span data-ttu-id="d45b9-248">関数に 3 つのプロパティを入力する場合は、スプラッティングされたハッシュテーブルを使用して書き直す方がよいでしょう。</span><span class="sxs-lookup"><span data-stu-id="d45b9-248">If I hit three properties for a function, odds are that I'll rewrite it using a splatted hashtable.</span></span>

### <a name="splatting-for-optional-parameters"></a><span data-ttu-id="d45b9-249">省略可能なパラメーターのスプラッティング</span><span class="sxs-lookup"><span data-stu-id="d45b9-249">Splatting for optional parameters</span></span>

<span data-ttu-id="d45b9-250">私がスプラッティングをよく使用する方法の 1 つは、スクリプト内の他の場所から取得された省略可能なパラメーターを処理することです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-250">One of the most common ways I use splatting is to deal with optional parameters that come from some place else in my script.</span></span> <span data-ttu-id="d45b9-251">たとえば、省略可能な `$Credential` 引数を持つ `Get-CIMInstance` 呼び出しをラップする関数があるとします。</span><span class="sxs-lookup"><span data-stu-id="d45b9-251">Let's say I have a function that wraps a `Get-CIMInstance` call that has an optional `$Credential` argument.</span></span>

```powershell
$CIMParams = @{
    ClassName = 'Win32_Bios'
    ComputerName = $ComputerName
}

if($Credential)
{
    $CIMParams.Credential = $Credential
}

Get-CIMInstance @CIMParams
```

<span data-ttu-id="d45b9-252">まず、共通パラメーターを使用してハッシュテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-252">I start by creating my hashtable with common parameters.</span></span> <span data-ttu-id="d45b9-253">`$Credential` が存在する場合は追加します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-253">Then I add the `$Credential` if it exists.</span></span>
<span data-ttu-id="d45b9-254">ここではスプラッティングを使用しているので、コード内で `Get-CIMInstance` を 1 回呼び出すだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-254">Because I'm using splatting here, I only need to have the call to `Get-CIMInstance` in my code once.</span></span> <span data-ttu-id="d45b9-255">この設計パターンは非常にクリーンであり、多数の省略可能なパラメーターを簡単に処理できます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-255">This design pattern is very clean and can handle lots of optional parameters easily.</span></span>

<span data-ttu-id="d45b9-256">実際には、パラメーターの `$null` 値を許可するようにコマンドを記述できるでしょう。</span><span class="sxs-lookup"><span data-stu-id="d45b9-256">To be fair, you could write your commands to allow `$null` values for parameters.</span></span> <span data-ttu-id="d45b9-257">呼び出している他のコマンドを常に制御できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d45b9-257">You just don't always have control over the other commands you're calling.</span></span>

### <a name="multiple-splats"></a><span data-ttu-id="d45b9-258">複数スプラッティング</span><span class="sxs-lookup"><span data-stu-id="d45b9-258">Multiple splats</span></span>

<span data-ttu-id="d45b9-259">複数のハッシュテーブルを同じコマンドレットにスプラッティングできます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-259">You can splat multiple hashtables to the same cmdlet.</span></span> <span data-ttu-id="d45b9-260">元のスプラッティングの例を見直すと、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-260">If we revisit our original splatting example:</span></span>

```powershell
$Common = @{
    SubnetMask  = '255.255.255.0'
    LeaseDuration = (New-TimeSpan -Days 8)
    Type = "Both"
}

$DHCPScope = @{
    Name        = 'TestNetwork'
    StartRange  = '10.0.0.2'
    EndRange    = '10.0.0.254'
    Description = 'Network for testlab A'
}

Add-DhcpServerv4Scope @DHCPScope @Common
```

<span data-ttu-id="d45b9-261">多くのコマンドに渡されるパラメーターの共通セットがある場合に、私はこの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-261">I'll use this method when I have a common set of parameters that I'm passing to lots of commands.</span></span>

### <a name="splatting-for-clean-code"></a><span data-ttu-id="d45b9-262">クリーンなコードのためのスプラッティング</span><span class="sxs-lookup"><span data-stu-id="d45b9-262">Splatting for clean code</span></span>

<span data-ttu-id="d45b9-263">コードをすっきりさせることができるなら、1 つのパラメーターをスプラッティングしてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="d45b9-263">There's nothing wrong with splatting a single parameter if makes you code cleaner.</span></span>

```powershell
$log = @{Path = '.\logfile.log'}
Add-Content "logging this command" @log
```

### <a name="splatting-executables"></a><span data-ttu-id="d45b9-264">実行可能ファイルのスプラッティング</span><span class="sxs-lookup"><span data-stu-id="d45b9-264">Splatting executables</span></span>

<span data-ttu-id="d45b9-265">スプラッティングは、`/param:value` 構文を使用する一部の実行可能ファイルでも機能します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-265">Splatting also works on some executables that use a `/param:value` syntax.</span></span> <span data-ttu-id="d45b9-266">たとえば、`Robocopy.exe` には、次のようないくつかのパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-266">`Robocopy.exe`, for example, has some parameters like this.</span></span>

```powershell
$robo = @{R=1;W=1;MT=8}
robocopy source destination @robo
```

<span data-ttu-id="d45b9-267">これは役に立つかどうかはわかりませんが、興味深いと思いました。</span><span class="sxs-lookup"><span data-stu-id="d45b9-267">I don't know that this is all that useful, but I found it interesting.</span></span>

## <a name="adding-hashtables"></a><span data-ttu-id="d45b9-268">ハッシュテーブルの追加</span><span class="sxs-lookup"><span data-stu-id="d45b9-268">Adding hashtables</span></span>

<span data-ttu-id="d45b9-269">ハッシュテーブルでは、2 つのハッシュテーブルを結合する加算演算子がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d45b9-269">Hashtables support the addition operator to combine two hashtables.</span></span>

```powershell
$person += @{Zip = '78701'}
```

<span data-ttu-id="d45b9-270">これは、2 つのハッシュテーブルがキーを共有していない場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-270">This only works if the two hashtables don't share a key.</span></span>

## <a name="nested-hashtables"></a><span data-ttu-id="d45b9-271">入れ子になったハッシュテーブル</span><span class="sxs-lookup"><span data-stu-id="d45b9-271">Nested hashtables</span></span>

<span data-ttu-id="d45b9-272">ハッシュテーブルは、ハッシュテーブル内の値として使用できます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-272">We can use hashtables as values inside a hashtable.</span></span>

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
}
$person.location = @{}
$person.location.city = 'Austin'
$person.location.state = 'TX'
```

<span data-ttu-id="d45b9-273">ここでは、2 つのキーを含む基本的なハッシュテーブルから始めました。</span><span class="sxs-lookup"><span data-stu-id="d45b9-273">I started with a basic hashtable containing two keys.</span></span> <span data-ttu-id="d45b9-274">空のハッシュテーブルを持つ `location` という名前のキーを追加しました。</span><span class="sxs-lookup"><span data-stu-id="d45b9-274">I added a key called `location` with an empty hashtable.</span></span> <span data-ttu-id="d45b9-275">次に、その `location` ハッシュテーブルに、最後の 2 つの項目を追加しました。</span><span class="sxs-lookup"><span data-stu-id="d45b9-275">Then I added the last two items to that `location` hashtable.</span></span> <span data-ttu-id="d45b9-276">これをすべてインラインで行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-276">We can do this all inline too.</span></span>

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
    location = @{
        city  = 'Austin'
        state = 'TX'
    }
}
```

<span data-ttu-id="d45b9-277">これにより、上記と同じハッシュテーブルが作成され、同じ方法でプロパティにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-277">This creates the same hashtable that we saw above and can access the properties the same way.</span></span>

```powershell
$person.location.city
Austin
```

<span data-ttu-id="d45b9-278">オブジェクトの構造にはさまざまな方法で対処できます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-278">There are many ways to approach the structure of your objects.</span></span> <span data-ttu-id="d45b9-279">入れ子になったハッシュテーブルを確認するもう 1 つの方法です。</span><span class="sxs-lookup"><span data-stu-id="d45b9-279">Here is a second way to look at a nested hashtable.</span></span>

```powershell
$people = @{
    Kevin = @{
        age  = 36
        city = 'Austin'
    }
    Alex = @{
        age  = 9
        city = 'Austin'
    }
}
```

<span data-ttu-id="d45b9-280">ここには、ハッシュテーブルをオブジェクトのコレクションとして使用する概念と、プロパティのコレクションとして使用する概念が混在しています。</span><span class="sxs-lookup"><span data-stu-id="d45b9-280">This mixes the concept of using hashtables as a collection of objects and a collection of properties.</span></span> <span data-ttu-id="d45b9-281">これらの値は、入れ子になっている場合でも、任意の方法で簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-281">The values are still easy to access even when they're nested using whatever approach you prefer.</span></span>

```powershell
PS> $people.kevin.age
36
PS> $people.kevin['city']
Austin
PS> $people['Alex'].age
9
PS> $people['Alex']['City']
Austin
```

<span data-ttu-id="d45b9-282">プロパティのように扱うときは、私はドット プロパティを使用する傾向があります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-282">I tend to use the dot property when I'm treating it like a property.</span></span> <span data-ttu-id="d45b9-283">これらは一般に、コード内で静的に定義してあり、すぐに思い出せるものです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-283">Those are generally things I've defined statically in my code and I know them off the top of my head.</span></span> <span data-ttu-id="d45b9-284">一覧を調べたり、キーにプログラムでアクセスしたりする必要がある場合は、角かっこを使用してキー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-284">If I need to walk the list or programmatically access the keys, I use the brackets to provide the key name.</span></span>

```powershell
foreach($name in $people.keys)
{
    $person = $people[$name]
    '{0}, age {1}, is in {2}' -f $name, $person.age, $person.city
}
```

<span data-ttu-id="d45b9-285">ハッシュテーブルを入れ子にできることにより、柔軟性と選択の幅が大きく向上します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-285">Having the ability to nest hashtables gives you a lot of flexibility and options.</span></span>

### <a name="looking-at-nested-hashtables"></a><span data-ttu-id="d45b9-286">入れ子になったハッシュテーブルの確認</span><span class="sxs-lookup"><span data-stu-id="d45b9-286">Looking at nested hashtables</span></span>

<span data-ttu-id="d45b9-287">ハッシュテーブルを入れ子にし始めるとすぐに、コンソールから簡単に確認する方法が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-287">As soon as you start nesting hashtables, you're going to need an easy way to look at them from the console.</span></span> <span data-ttu-id="d45b9-288">たとえば最後のハッシュテーブルでは、次のような出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-288">If I take that last hashtable, I get an output that looks like this and it only goes so deep:</span></span>

```powershell
PS> $people
Name                           Value
----                           -----
Kevin                          {age, city}
Alex                           {age, city}
```

<span data-ttu-id="d45b9-289">私がこれらを確認するために使用する go to コマンドは `ConvertTo-JSON` です。これは非常にクリーンであり、私は他の処理で JSON を頻繁に使用するためです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-289">My go to command for looking at these things is `ConvertTo-JSON` because it's very clean and I frequently use JSON on other things.</span></span>

```powershell
PS> $people | ConvertTo-Json
{
    "Kevin":  {
                "age":  36,
                "city":  "Austin"
            },
    "Alex":  {
                "age":  9,
                "city":  "Austin"
            }
}
```

<span data-ttu-id="d45b9-290">JSON について知らない場合でも、探しているものを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-290">Even if you don't know JSON, you should be able to see what you're looking for.</span></span> <span data-ttu-id="d45b9-291">このような構造化データ用には `Format-Custom` コマンドがありますが、私は JSON ビューの方が好きです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-291">There's a `Format-Custom` command for structured data like this but I still like the JSON view better.</span></span>

## <a name="creating-objects"></a><span data-ttu-id="d45b9-292">オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="d45b9-292">Creating objects</span></span>

<span data-ttu-id="d45b9-293">オブジェクトが必要な場合に、ハッシュテーブルを使用してプロパティを保持するだけでは目的を達成できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-293">Sometimes you just need to have an object and using a hashtable to hold properties just isn't getting the job done.</span></span> <span data-ttu-id="d45b9-294">キーを列名として表示したい場合がよくあります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-294">Most commonly you want to see the keys as column names.</span></span> <span data-ttu-id="d45b9-295">`pscustomobject` を使用すると、簡単に実現できます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-295">A `pscustomobject` makes that easy.</span></span>

```powershell
$person = [pscustomobject]@{
    name = 'Kevin'
    age  = 36
}

$person

name  age
----  ---
Kevin  36
```

<span data-ttu-id="d45b9-296">最初から `pscustomobject` として作成していない場合でも、必要に応じていつでもキャストできます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-296">Even if you don't create it as a `pscustomobject` initially, you can always cast it later when needed.</span></span>

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
}

[pscustomobject]$person

name  age
----  ---
Kevin  36
```

<span data-ttu-id="d45b9-297">[pscustomobject][] については詳細な記事を既に書いたので、この記事の後で読むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d45b9-297">I already have detailed write-up for [pscustomobject][] that you should go read after this one.</span></span> <span data-ttu-id="d45b9-298">ここで学習したさまざまな要素に基づいて書かれています。</span><span class="sxs-lookup"><span data-stu-id="d45b9-298">It builds on a lot of the things learned here.</span></span>

## <a name="reading-and-writing-hashtables-to-file"></a><span data-ttu-id="d45b9-299">ファイルに対するハッシュテーブルの読み取りと書き込み</span><span class="sxs-lookup"><span data-stu-id="d45b9-299">Reading and writing hashtables to file</span></span>

### <a name="saving-to-csv"></a><span data-ttu-id="d45b9-300">CSV に保存する</span><span class="sxs-lookup"><span data-stu-id="d45b9-300">Saving to CSV</span></span>

<span data-ttu-id="d45b9-301">ハッシュテーブルを CSV に保存するために苦労することは、上記で言及した問題の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-301">Struggling with getting a hashtable to save to a CSV is one of the difficulties that I was referring to above.</span></span> <span data-ttu-id="d45b9-302">ハッシュテーブルを `pscustomobject` に変換すると、CSV に正しく保存されます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-302">Convert your hashtable to a `pscustomobject` and it will save correctly to CSV.</span></span> <span data-ttu-id="d45b9-303">列の順序が保持されるように `pscustomobject` から始めておけば役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-303">It helps if you start with a `pscustomobject` so the column order is preserved.</span></span> <span data-ttu-id="d45b9-304">ただし、必要な場合はインラインで `pscustomobject` にキャストできます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-304">But you can cast it to a `pscustomobject` inline if needed.</span></span>

```powershell
$person | ForEach-Object{ [pscustomobject]$_ } | Export-CSV -Path $path
```

<span data-ttu-id="d45b9-305">これについても、[pscustomobject][] の使用に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d45b9-305">Again, check out my write-up on using a [pscustomobject][].</span></span>

### <a name="saving-a-nested-hashtable-to-file"></a><span data-ttu-id="d45b9-306">入れ子になったハッシュテーブルをファイルに保存する</span><span class="sxs-lookup"><span data-stu-id="d45b9-306">Saving a nested hashtable to file</span></span>

<span data-ttu-id="d45b9-307">入れ子になったハッシュテーブルをファイルに保存し、再度読み取る必要がある場合は、JSON コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-307">If I need to save a nested hashtable to a file and then read it back in again, I use the JSON cmdlets to do it.</span></span>

```powershell
$people | ConvertTo-JSON | Set-Content -Path $path
$people = Get-Content -Path $path -Raw | ConvertFrom-JSON
```

<span data-ttu-id="d45b9-308">この方法には重要な点が 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-308">There are two important points about this method.</span></span> <span data-ttu-id="d45b9-309">1 点目は、JSON は複数行に書き出されるため、`-Raw` オプションを使用して 1 つの文字列に読み込み直す必要があるということです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-309">First is that the JSON is written out multiline so I need to use the `-Raw` option to read it back into a single string.</span></span> <span data-ttu-id="d45b9-310">2 点目は、インポートされたオブジェクトは `[hashtable]` ではなくなるということです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-310">The Second is that the imported object is no longer a `[hashtable]`.</span></span> <span data-ttu-id="d45b9-311">これは `[pscustomobject]` であり、予期していない場合は問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-311">It's now a `[pscustomobject]` and that can cause issues if you don't expect it.</span></span>

<span data-ttu-id="d45b9-312">深い入れ子になったハッシュテーブルを監視します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-312">Watch for deeply-nested hashtables.</span></span> <span data-ttu-id="d45b9-313">JSON に変換した場合、期待どおりの結果が得られないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-313">When you convert it to JSON you might not get the results you expect.</span></span>

```powershell
@{ a = @{ b = @{ c = @{ d = "e" }}}} | ConvertTo-Json

{
  "a": {
    "b": {
      "c": "System.Collections.Hashtable"
    }
  }
}
```

<span data-ttu-id="d45b9-314">**Depth** パラメーターを使用して、入れ子になったすべてのハッシュテーブルが展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-314">Use **Depth** parameter to ensure that you have expanded all the nested hashtables.</span></span>

```powershell
@{ a = @{ b = @{ c = @{ d = "e" }}}} | ConvertTo-Json -Depth 3

{
  "a": {
    "b": {
      "c": {
        "d": "e"
      }
    }
  }
}
```

<span data-ttu-id="d45b9-315">インポート時に `[hashtable]` であることが必要な場合は、`Export-CliXml` および `Import-CliXml` コマンドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-315">If you need it to be a `[hashtable]` on import, then you need to use the `Export-CliXml` and `Import-CliXml` commands.</span></span>

### <a name="converting-json-to-hashtable"></a><span data-ttu-id="d45b9-316">JSON をハッシュテーブルに変換する</span><span class="sxs-lookup"><span data-stu-id="d45b9-316">Converting JSON to Hashtable</span></span>

<span data-ttu-id="d45b9-317">JSON を `[hashtable]` に変換する必要がある場合に、.NET で [JavaScriptSerializer][] を使用して実行する方法を 1 つ知っています。</span><span class="sxs-lookup"><span data-stu-id="d45b9-317">If you need to convert JSON to a `[hashtable]`, there's one way that I know of to do it with the [JavaScriptSerializer][] in .NET.</span></span>

```powershell
[Reflection.Assembly]::LoadWithPartialName("System.Web.Script.Serialization")
$JSSerializer = [System.Web.Script.Serialization.JavaScriptSerializer]::new()
$JSSerializer.Deserialize($json,'Hashtable')
```

<span data-ttu-id="d45b9-318">PowerShell v6 以降では、JSON サポートに NewtonSoft JSON.NET が使用され、ハッシュテーブルのサポートが追加されます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-318">Beginning in PowerShell v6, JSON support uses the NewtonSoft JSON.NET and adds hashtable support.</span></span>

```powershell
'{ "a": "b" }' | ConvertFrom-Json -AsHashtable

Name      Value
----      -----
a         b
```

<span data-ttu-id="d45b9-319">PowerShell 6.2 が `ConvertFrom-Json` に **Depth** パラメーターを追加しました。</span><span class="sxs-lookup"><span data-stu-id="d45b9-319">PowerShell 6.2 added the **Depth** parameter to `ConvertFrom-Json`.</span></span> <span data-ttu-id="d45b9-320">既定の **Depth** は 1024 です。</span><span class="sxs-lookup"><span data-stu-id="d45b9-320">The default **Depth** is 1024.</span></span>

### <a name="reading-directly-from-a-file"></a><span data-ttu-id="d45b9-321">ファイルから直接読み取る</span><span class="sxs-lookup"><span data-stu-id="d45b9-321">Reading directly from a file</span></span>

<span data-ttu-id="d45b9-322">PowerShell 構文を使用しているハッシュテーブルを含むファイルがある場合は、それを直接インポートする方法があります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-322">If you have a file that contains a hashtable using PowerShell syntax, there's a way to import it directly.</span></span>

```powershell
$content = Get-Content -Path $Path -Raw -ErrorAction Stop
$scriptBlock = [scriptblock]::Create( $content )
$scriptBlock.CheckRestrictedLanguage( $allowedCommands, $allowedVariables, $true )
$hashtable = ( & $scriptBlock )
```

<span data-ttu-id="d45b9-323">ファイルの内容を `scriptblock` にインポートした後、それを実行する前に、他の PowerShell コマンドが含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-323">It imports the contents of the file into a `scriptblock`, then checks to make sure it doesn't have any other PowerShell commands in it before it executes it.</span></span>

<span data-ttu-id="d45b9-324">それに関連して、モジュール マニフェスト (psd1 ファイル) はハッシュテーブルであることを知っていましたか。</span><span class="sxs-lookup"><span data-stu-id="d45b9-324">On that note, did you know that a module manifest (the psd1 file) is just a hashtable?</span></span>

## <a name="keys-can-be-any-object"></a><span data-ttu-id="d45b9-325">キーには任意のオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-325">Keys can be any object</span></span>

<span data-ttu-id="d45b9-326">ほとんどの場合、キーは文字列にすぎません。</span><span class="sxs-lookup"><span data-stu-id="d45b9-326">Most of the time, the keys are just strings.</span></span> <span data-ttu-id="d45b9-327">したがって、任意のものを引用符で囲んで、キーにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-327">So we can put quotes around anything and make it a key.</span></span>

```powershell
$person = @{
    'full name' = 'Kevin Marquette'
    '#' = 3978
}
$person['full name']
```

<span data-ttu-id="d45b9-328">気付いていないかもしれませんが、いくつかの奇妙なことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-328">You can do some odd things that you may not have realized you could do.</span></span>

```powershell
$person.'full name'

$key = 'full name'
$person.$key
```

<span data-ttu-id="d45b9-329">何かを行うことができるからといって、推奨されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d45b9-329">Just because you can do something, it doesn't mean that you should.</span></span> <span data-ttu-id="d45b9-330">最後のものは、バグが発生するのを待っているようです。このコードを読む人によって簡単に誤解されるでしょう。</span><span class="sxs-lookup"><span data-stu-id="d45b9-330">That last one just looks like a bug waiting to happen and would be easily misunderstood by anyone reading your code.</span></span>

<span data-ttu-id="d45b9-331">厳密に言うと、キーは文字列である必要はありませんが、文字列のみを使用する方が考えやすくなります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-331">Technically your key doesn't have to be a string but they're easier to think about if you only use strings.</span></span> <span data-ttu-id="d45b9-332">ただし、インデックス作成は複雑なキーでは適切に機能しません。</span><span class="sxs-lookup"><span data-stu-id="d45b9-332">However, indexing doesn't work well with the complex keys.</span></span>

```powershell
$ht = @{ @(1,2,3) = "a" }
$ht

Name                           Value
----                           -----
{1, 2, 3}                      a
```

<span data-ttu-id="d45b9-333">キーによってハッシュテーブルの値にアクセスするのは、常に機能するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d45b9-333">Accessing a value in the hashtable by its key doesn't always work.</span></span> <span data-ttu-id="d45b9-334">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-334">For example:</span></span>

```powershell
$key = $ht.keys[0]
$ht.$($key)
a
$ht[$key]
a
```

<span data-ttu-id="d45b9-335">キーが配列の場合は、メンバー アクセス (`.`) 表記で使用できるように、`$key` 変数を部分式でラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-335">When the key is an array, you must wrap the `$key` variable in a subexpression so that it can be used with member access (`.`) notation.</span></span> <span data-ttu-id="d45b9-336">または、配列インデックス (`[]`) 表記を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-336">Or, you can use array index (`[]`) notation.</span></span>

## <a name="use-in-automatic-variables"></a><span data-ttu-id="d45b9-337">自動変数での使用</span><span class="sxs-lookup"><span data-stu-id="d45b9-337">Use in automatic variables</span></span>

### <a name="psboundparameters"></a><span data-ttu-id="d45b9-338">$PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="d45b9-338">$PSBoundParameters</span></span>

<span data-ttu-id="d45b9-339">[$PSBoundParameters][] は、関数のコンテキスト内にのみ存在する自動変数です。</span><span class="sxs-lookup"><span data-stu-id="d45b9-339">[$PSBoundParameters][] is an automatic variable that only exists inside the context of a function.</span></span>
<span data-ttu-id="d45b9-340">これには、関数の呼び出し時に指定されたすべてのパラメーターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-340">It contains all the parameters that the function was called with.</span></span> <span data-ttu-id="d45b9-341">これは厳密にはハッシュテーブルではありませんがよく似ているため、そのように扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-341">This isn't exactly a hashtable but close enough that you can treat it like one.</span></span>

<span data-ttu-id="d45b9-342">これには、キーの削除と他の関数へのスプラッティングが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-342">That includes removing keys and splatting it to other functions.</span></span> <span data-ttu-id="d45b9-343">プロキシ関数を作成する場合は、これについて詳細を調べてください。</span><span class="sxs-lookup"><span data-stu-id="d45b9-343">If you find yourself writing proxy functions, take a closer look at this one.</span></span>

<span data-ttu-id="d45b9-344">詳細については、[about_Automatic_Variables][]に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d45b9-344">See [about_Automatic_Variables][] for more details.</span></span>

### <a name="psboundparameters-gotcha"></a><span data-ttu-id="d45b9-345">PSBoundParameters の注意事項</span><span class="sxs-lookup"><span data-stu-id="d45b9-345">PSBoundParameters gotcha</span></span>

<span data-ttu-id="d45b9-346">覚えておくべき重要な点の 1 つは、これにはパラメーターとして渡された値のみが含まれることです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-346">One important thing to remember is that this only includes the values that are passed in as parameters.</span></span> <span data-ttu-id="d45b9-347">既定値を持つパラメーターもある場合、それらが呼び出し元から渡されないときは、`$PSBoundParameters` にはこれらの値が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d45b9-347">If you also have parameters with default values but aren't passed in by the caller, `$PSBoundParameters` doesn't contain those values.</span></span> <span data-ttu-id="d45b9-348">これはよく見落とされます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-348">This is commonly overlooked.</span></span>

### <a name="psdefaultparametervalues"></a><span data-ttu-id="d45b9-349">$PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="d45b9-349">$PSDefaultParameterValues</span></span>

<span data-ttu-id="d45b9-350">この自動変数を使用すると、コマンドレットを変更せずに、任意のコマンドレットに既定値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-350">This automatic variable lets you assign default values to any cmdlet without changing the cmdlet.</span></span>
<span data-ttu-id="d45b9-351">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d45b9-351">Take a look at this example.</span></span>

```powershell
$PSDefaultParameterValues["Out-File:Encoding"] = "UTF8"
```

<span data-ttu-id="d45b9-352">これにより、`UTF8` を `Out-File -Encoding` パラメーターの既定値として設定するエントリが `$PSDefaultParameterValues` ハッシュテーブルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-352">This adds an entry to the `$PSDefaultParameterValues` hashtable that sets `UTF8` as the default value for the `Out-File -Encoding` parameter.</span></span> <span data-ttu-id="d45b9-353">これはセッション固有であるため、自分の `$profile` 内に置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-353">This is session-specific so you should place it in your `$profile`.</span></span>

<span data-ttu-id="d45b9-354">私は頻繁に入力する値を事前に割り当てるために、これをよく使用します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-354">I use this often to pre-assign values that I type quite often.</span></span>

```powershell
$PSDefaultParameterValues[ "Connect-VIServer:Server" ] = 'VCENTER01.contoso.local'
```

<span data-ttu-id="d45b9-355">また、ワイルドカードも使用できるため、値を一括して設定できます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-355">This also accepts wildcards so you can set values in bulk.</span></span> <span data-ttu-id="d45b9-356">次のような方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-356">Here are some ways you can use that:</span></span>

```powershell
$PSDefaultParameterValues[ "Get-*:Verbose" ] = $true
$PSDefaultParameterValues[ "*:Credential" ] = Get-Credential
```

<span data-ttu-id="d45b9-357">詳細については、[Michael Sorens][] 氏による[自動既定値][]に関するすばらしい記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d45b9-357">For a more in-depth breakdown, see this great article on [Automatic Defaults][] by [Michael Sorens][].</span></span>

## <a name="regex-matches"></a><span data-ttu-id="d45b9-358">正規表現の $Matches</span><span class="sxs-lookup"><span data-stu-id="d45b9-358">Regex $Matches</span></span>

<span data-ttu-id="d45b9-359">`-match` 演算子を使用すると、一致の結果を保持する `$matches` という名前の自動変数が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-359">When you use the `-match` operator, an automatic variable called `$matches` is created with the results of the match.</span></span> <span data-ttu-id="d45b9-360">正規表現に部分式がある場合は、それらの部分一致も一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-360">If you have any sub expressions in your regex, those sub matches are also listed.</span></span>

```powershell
$message = 'My SSN is 123-45-6789.'

$message -match 'My SSN is (.+)\.'
$Matches[0]
$Matches[1]
```

### <a name="named-matches"></a><span data-ttu-id="d45b9-361">名前付き一致</span><span class="sxs-lookup"><span data-stu-id="d45b9-361">Named matches</span></span>

<span data-ttu-id="d45b9-362">これは、ほとんどの人が知らないお気に入りの機能の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-362">This is one of my favorite features that most people don't know about.</span></span> <span data-ttu-id="d45b9-363">名前付き正規表現照合を使用すると、一致項目に名前でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-363">If you use a named regex match, then you can access that match by name on the matches.</span></span>

```powershell
$message = 'My Name is Kevin and my SSN is 123-45-6789.'

if($message -match 'My Name is (?<Name>.+) and my SSN is (?<SSN>.+)\.')
{
    $Matches.Name
    $Matches.SSN
}
```

<span data-ttu-id="d45b9-364">上記の例では、`(?<Name>.*)` は名前付きの部分式です。</span><span class="sxs-lookup"><span data-stu-id="d45b9-364">In the example above, the `(?<Name>.*)` is a named sub expression.</span></span> <span data-ttu-id="d45b9-365">その後、この値は `$Matches.Name` プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-365">This value is then placed in the `$Matches.Name` property.</span></span>

## <a name="group-object--ashashtable"></a><span data-ttu-id="d45b9-366">Group-Object -AsHashtable</span><span class="sxs-lookup"><span data-stu-id="d45b9-366">Group-Object -AsHashtable</span></span>

<span data-ttu-id="d45b9-367">`Group-Object` のあまり知られていない機能の 1 つとして、一部のデータセットをハッシュテーブルに変換できるという点があります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-367">One little known feature of `Group-Object` is that it can turn some datasets into a hashtable for you.</span></span>

```powershell
Import-CSV $Path | Group-Object -AsHashtable -Property email
```

<span data-ttu-id="d45b9-368">これにより、各行がハッシュテーブルに追加され、指定されたプロパティがそれにアクセスするためのキーとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-368">This will add each row into a hashtable and use the specified property as the key to access it.</span></span>

## <a name="copying-hashtables"></a><span data-ttu-id="d45b9-369">ハッシュテーブルのコピー</span><span class="sxs-lookup"><span data-stu-id="d45b9-369">Copying Hashtables</span></span>

<span data-ttu-id="d45b9-370">覚えておくべき重要な点の 1 つは、ハッシュテーブルがオブジェクトであることです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-370">One important thing to know is that hashtables are objects.</span></span> <span data-ttu-id="d45b9-371">各変数は、オブジェクトへの参照にすぎません。</span><span class="sxs-lookup"><span data-stu-id="d45b9-371">And each variable is just a reference to an object.</span></span> <span data-ttu-id="d45b9-372">つまり、ハッシュテーブルの有効なコピーを作成するには、より多くの作業が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-372">This means that it takes more work to make a valid copy of a hashtable.</span></span>

### <a name="assigning-reference-types"></a><span data-ttu-id="d45b9-373">参照型を割り当てる</span><span class="sxs-lookup"><span data-stu-id="d45b9-373">Assigning reference types</span></span>

<span data-ttu-id="d45b9-374">ハッシュテーブルが 1 つある場合に、それを 2 つ目の変数に割り当てると、両方の変数が同じハッシュテーブルを指します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-374">When you have one hashtable and assign it to a second variable, both variables point to the same hashtable.</span></span>

```powershell
PS> $orig = @{name='orig'}
PS> $copy = $orig
PS> $copy.name = 'copy'
PS> 'Copy: [{0}]' -f $copy.name
PS> 'Orig: [{0}]' -f $orig.name

Copy: [copy]
Orig: [copy]
```

<span data-ttu-id="d45b9-375">一方の値を変更するともう一方の値も変更されるため、これらは同じであることがよくわかります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-375">This highlights that they're the same because altering the values in one will also alter the values in the other.</span></span> <span data-ttu-id="d45b9-376">これは、ハッシュテーブルを他の関数に渡すときにも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-376">This also applies when passing hashtables into other functions.</span></span> <span data-ttu-id="d45b9-377">これらの関数がハッシュテーブルに変更を加えた場合、元のハッシュテーブルも変更されます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-377">If those functions make changes to that hashtable, your original is also altered.</span></span>

### <a name="shallow-copies-single-level"></a><span data-ttu-id="d45b9-378">シャロー コピー、単一レベル</span><span class="sxs-lookup"><span data-stu-id="d45b9-378">Shallow copies, single level</span></span>

<span data-ttu-id="d45b9-379">上記の例のような単純なハッシュテーブルがある場合は、`.Clone()` を使用してシャロー コピーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-379">If we have a simple hashtable like our example above, we can use `.Clone()` to make a shallow copy.</span></span>

```powershell
PS> $orig = @{name='orig'}
PS> $copy = $orig.Clone()
PS> $copy.name = 'copy'
PS> 'Copy: [{0}]' -f $copy.name
PS> 'Orig: [{0}]' -f $orig.name

Copy: [copy]
Orig: [orig]
```

<span data-ttu-id="d45b9-380">これにより、他方に影響を与えずに、一方に対していくつかの基本的な変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d45b9-380">This will allow us to make some basic changes to one that don't impact the other.</span></span>

### <a name="shallow-copies-nested"></a><span data-ttu-id="d45b9-381">シャロー コピー、入れ子</span><span class="sxs-lookup"><span data-stu-id="d45b9-381">Shallow copies, nested</span></span>

<span data-ttu-id="d45b9-382">シャロー コピーと呼ばれる理由は、基本レベルのプロパティのみがコピーされるためです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-382">The reason why it's called a shallow copy is because it only copies the base level properties.</span></span> <span data-ttu-id="d45b9-383">これらのプロパティのいずれかが参照型 (別のハッシュテーブルなど) である場合、入れ子になったオブジェクトは引き続き互いを指します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-383">If one of those properties is a reference type (like another hashtable), then those nested objects will still point to each other.</span></span>

```powershell
PS> $orig = @{
        person=@{
            name='orig'
        }
    }
PS> $copy = $orig.Clone()
PS> $copy.person.name = 'copy'
PS> 'Copy: [{0}]' -f $copy.person.name
PS> 'Orig: [{0}]' -f $orig.person.name

Copy: [copy]
Orig: [copy]
```

<span data-ttu-id="d45b9-384">ハッシュテーブルを複製したにもかかわらず、`person` への参照は複製されていないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-384">So you can see that even though I cloned the hashtable, the reference to `person` wasn't cloned.</span></span> <span data-ttu-id="d45b9-385">最初のハッシュテーブルにリンクされていない、本当の意味で 2 つ目のハッシュテーブルを作成するには、ディープ コピーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-385">We need to make a deep copy to truly have a second hashtable that isn't linked to the first.</span></span>

### <a name="deep-copies"></a><span data-ttu-id="d45b9-386">ディープ コピー</span><span class="sxs-lookup"><span data-stu-id="d45b9-386">Deep copies</span></span>

<span data-ttu-id="d45b9-387">この記事の執筆時点で、ハッシュテーブルのディープ コピーを作成する (そしてハッシュテーブルとして保持する) ための巧妙な方法を私は知りません。</span><span class="sxs-lookup"><span data-stu-id="d45b9-387">At the time of writing this, I'm not aware of any clever ways to just make a deep copy of a hashtable (and keep it as a hashtable).</span></span> <span data-ttu-id="d45b9-388">これについてはだれかが執筆する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d45b9-388">That's just one of those things that someone needs to write.</span></span>
<span data-ttu-id="d45b9-389">これを行う簡単な方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d45b9-389">Here is a quick method to do that.</span></span>

```powershell
function Get-DeepClone
{
    [CmdletBinding()]
    param(
        $InputObject
    )
    process
    {
        if($InputObject -is [hashtable]) {
            $clone = @{}
            foreach($key in $InputObject.keys)
            {
                $clone[$key] = Get-DeepClone $InputObject[$key]
            }
            return $clone
        } else {
            return $InputObject
        }
    }
}
```

<span data-ttu-id="d45b9-390">他の参照型または配列は処理されませんが、出発点として適しています。</span><span class="sxs-lookup"><span data-stu-id="d45b9-390">It doesn't handle any other reference types or arrays, but it's a good starting point.</span></span>

## <a name="anything-else"></a><span data-ttu-id="d45b9-391">その他</span><span class="sxs-lookup"><span data-stu-id="d45b9-391">Anything else?</span></span>

<span data-ttu-id="d45b9-392">この記事では、多岐にわたって手早く説明しました。</span><span class="sxs-lookup"><span data-stu-id="d45b9-392">I covered a lot of ground quickly.</span></span> <span data-ttu-id="d45b9-393">この記事を読むたびに、新しいことを学んだり、理解を深めたりしていただければ幸いです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-393">My hope is that you walk away leaning something new or understanding it better every time you read this.</span></span> <span data-ttu-id="d45b9-394">この機能の全範囲について説明したので、すぐにはご自身に該当しない側面もあるでしょう。</span><span class="sxs-lookup"><span data-stu-id="d45b9-394">Because I covered the full spectrum of this feature, there are aspects that just may not apply to you right now.</span></span> <span data-ttu-id="d45b9-395">それはまったく問題ではなく、どの程度 PowerShell を使用するかに応じて予想されることです。</span><span class="sxs-lookup"><span data-stu-id="d45b9-395">That is perfectly OK and is kind of expected depending on how much you work with PowerShell.</span></span>

<!-- link references -->
[オリジナル バージョン]: https://powershellexplained.com/2016-11-06-powershell-hashtable-everything-you-wanted-to-know-about/
[original version]: https://powershellexplained.com/2016-11-06-powershell-hashtable-everything-you-wanted-to-know-about/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[ハッシュテーブル]: /powershell/module/microsoft.powershell.core/about/about_hash_tables
[hashtables]: /powershell/module/microsoft.powershell.core/about/about_hash_tables
[配列]: /powershell/module/microsoft.powershell.core/about/about_arrays
[arrays]: /powershell/module/microsoft.powershell.core/about/about_arrays
[パフォーマンスが重要ならテストせよ]: https://github.com/PoshCode/PowerShellPracticeAndStyle/blob/master/Best-Practices/Performance.md
[If performance matters, test it]: https://github.com/PoshCode/PowerShellPracticeAndStyle/blob/master/Best-Practices/Performance.md
[スプラッティング]: /powershell/module/microsoft.powershell.core/about/about_splatting
[splatting]: /powershell/module/microsoft.powershell.core/about/about_splatting
[pscustomobject]: everything-about-pscustomobject.md
[JavaScriptSerializer]: /dotnet/api/system.web.script.serialization.javascriptserializer?view=netframework-4.8&preserve-view=true
[PSBoundParameters]: https://tommymaynard.com/the-psboundparameters-automatic-variable-2016/
[about_Automatic_Variables]: /powershell/module/microsoft.powershell.core/about/about_automatic_variables
[自動既定値]: https://www.simple-talk.com/sysadmin/PowerShell/PowerShell-time-saver-automatic-defaults/
[Automatic Defaults]: https://www.simple-talk.com/sysadmin/PowerShell/PowerShell-time-saver-automatic-defaults/
[Michael Sorens]: http://cleancode.sourceforge.net/wwwdoc/about.html
