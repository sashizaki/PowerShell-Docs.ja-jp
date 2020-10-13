---
title: PSCustomObject について知りたかったことのすべて
description: PSCustomObject は、構造化データを作成するためのシンプルな方法です。
ms.date: 10/05/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: ccbdcdae5ad38f555233dffbed7e8a6ec2b0726b
ms.sourcegitcommit: 1695df0d241c0390cac71a7401e61198fc6ff756
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "91772322"
---
# <a name="everything-you-wanted-to-know-about-pscustomobject"></a><span data-ttu-id="fa160-103">PSCustomObject について知りたかったことのすべて</span><span class="sxs-lookup"><span data-stu-id="fa160-103">Everything you wanted to know about PSCustomObject</span></span>

<span data-ttu-id="fa160-104">`PSCustomObject` は、PowerShell のツール ベルトに追加できる優れたツールです。</span><span class="sxs-lookup"><span data-stu-id="fa160-104">`PSCustomObject`s are a great tool to add into your PowerShell tool belt.</span></span> <span data-ttu-id="fa160-105">基本事項から始めて、より高度な機能に進みましょう。</span><span class="sxs-lookup"><span data-stu-id="fa160-105">Let's start with the basics and work our way into the more advanced features.</span></span> <span data-ttu-id="fa160-106">`PSCustomObject` を使用する背景にあるアイデアは、構造化データを簡単に作成することです。</span><span class="sxs-lookup"><span data-stu-id="fa160-106">The idea behind using a `PSCustomObject` is to have a simple way to create structured data.</span></span> <span data-ttu-id="fa160-107">最初の例を見てみると、その意味がよく理解できるでしょう。</span><span class="sxs-lookup"><span data-stu-id="fa160-107">Take a look at the first example and you'll have a better idea of what that means.</span></span>

> [!NOTE]
> <span data-ttu-id="fa160-108">この記事の[オリジナル バージョン][]は、[@KevinMarquette][] 氏のブログ記事です。</span><span class="sxs-lookup"><span data-stu-id="fa160-108">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="fa160-109">このコンテンツを共有してくださった Kevin 氏に、PowerShell チームより感謝を申し上げます。</span><span class="sxs-lookup"><span data-stu-id="fa160-109">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="fa160-110">[PowerShellExplained.com][] のブログをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="fa160-110">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="creating-a-pscustomobject"></a><span data-ttu-id="fa160-111">PSCustomObject の作成</span><span class="sxs-lookup"><span data-stu-id="fa160-111">Creating a PSCustomObject</span></span>

<span data-ttu-id="fa160-112">私は PowerShell で `[PSCustomObject]` を使うことが気に入っています。</span><span class="sxs-lookup"><span data-stu-id="fa160-112">I love using `[PSCustomObject]` in PowerShell.</span></span> <span data-ttu-id="fa160-113">これ以上簡単に有用なオブジェクトを作成する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="fa160-113">Creating a usable object has never been easier.</span></span>
<span data-ttu-id="fa160-114">そのため、オブジェクトを作成するその他の方法はすべてスキップします。ただし、これらの例のほとんどは PowerShell v3.0 以降であることに言及しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa160-114">Because of that, I'm going to skip over all the other ways you can create an object but I need to mention that most of these examples are PowerShell v3.0 and newer.</span></span>

```powershell
$myObject = [PSCustomObject]@{
    Name     = 'Kevin'
    Language = 'PowerShell'
    State    = 'Texas'
}
```

<span data-ttu-id="fa160-115">私はほとんどすべてのものにハッシュテーブルを使用するため、この方法はうまく機能します。</span><span class="sxs-lookup"><span data-stu-id="fa160-115">This method works well for me because I use hashtables for just about everything.</span></span> <span data-ttu-id="fa160-116">しかし、PowerShell でハッシュテーブルをよりオブジェクトに近い方法で処理したい場合もあります。</span><span class="sxs-lookup"><span data-stu-id="fa160-116">But there are times when I would like PowerShell to treat hashtables more like an object.</span></span> <span data-ttu-id="fa160-117">その違いに初めて気付くのは、`Format-Table` または `Export-CSV` を使用するときに、ハッシュテーブルがキーと値のペアのコレクションに過ぎないことを認識したときです。</span><span class="sxs-lookup"><span data-stu-id="fa160-117">The first place you notice the difference is when you want to use `Format-Table` or `Export-CSV` and you realize that a hashtable is just a collection of key/value pairs.</span></span>

<span data-ttu-id="fa160-118">その後、通常のオブジェクトの場合と同様に値にアクセスして使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fa160-118">You can then access and use the values like you would a normal object.</span></span>

```powershell
$myObject.Name
```

### <a name="converting-a-hashtable"></a><span data-ttu-id="fa160-119">ハッシュテーブルの変換</span><span class="sxs-lookup"><span data-stu-id="fa160-119">Converting a hashtable</span></span>

<span data-ttu-id="fa160-120">本筋から外れないうちに、次のようにすることもできたことにお気付きでしょうか。</span><span class="sxs-lookup"><span data-stu-id="fa160-120">While I am on the topic, did you know you could do this:</span></span>

```powershell
$myHashtable = @{
    Name     = 'Kevin'
    Language = 'PowerShell'
    State    = 'Texas'
}
$myObject = [pscustomobject]$myHashtable
```

<span data-ttu-id="fa160-121">私は初めからオブジェクトを作成する方が好きですが、最初にハッシュテーブルを操作することが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="fa160-121">I do prefer to create the object from the start but there are times you have to work with a hashtable first.</span></span> <span data-ttu-id="fa160-122">コンストラクターがオブジェクト プロパティに対してハッシュテーブルを受け取るため、この例は適切です。</span><span class="sxs-lookup"><span data-stu-id="fa160-122">This example works because the constructor takes a hashtable for the object properties.</span></span> <span data-ttu-id="fa160-123">重要な注意事項の 1 つは、この方法は機能しますが、まったく同等ではないことです。</span><span class="sxs-lookup"><span data-stu-id="fa160-123">One important note is that while this method works, it isn't an exact equivalent.</span></span> <span data-ttu-id="fa160-124">最大の違いは、プロパティの順序が維持されないことです。</span><span class="sxs-lookup"><span data-stu-id="fa160-124">The biggest difference is that the order of the properties isn't preserved.</span></span>

### <a name="legacy-approach"></a><span data-ttu-id="fa160-125">従来の手法</span><span class="sxs-lookup"><span data-stu-id="fa160-125">Legacy approach</span></span>

<span data-ttu-id="fa160-126">カスタム オブジェクトを作成するために `New-Object` が使用されるのを見たことがあるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="fa160-126">You may have seen people use `New-Object` to create custom objects.</span></span>

```powershell
$myHashtable = @{
    Name     = 'Kevin'
    Language = 'PowerShell'
    State    = 'Texas'
}

$myObject = New-Object -TypeName PSObject -Property $myHashtable
```

<span data-ttu-id="fa160-127">この方法はかなり遅くなりますが、初期バージョンの PowerShell では最良の選択肢である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa160-127">This way is quite a bit slower but it may be your best option on early versions of PowerShell.</span></span>

### <a name="saving-to-a-file"></a><span data-ttu-id="fa160-128">ファイルへの保存</span><span class="sxs-lookup"><span data-stu-id="fa160-128">Saving to a file</span></span>

<span data-ttu-id="fa160-129">ハッシュテーブルをファイルに保存する最善の方法は、JSON として保存することだと考えられます。</span><span class="sxs-lookup"><span data-stu-id="fa160-129">I find the best way to save a hashtable to a file is to save it as JSON.</span></span> <span data-ttu-id="fa160-130">これをもう一度 `[PSCustomObject]` にインポートすることができます</span><span class="sxs-lookup"><span data-stu-id="fa160-130">You can import it back into a `[PSCustomObject]`</span></span>

```powershell
$myObject | ConvertTo-Json -depth 1- | Set-Content -Path $Path
$myObject = Get-Content -Path $Path | ConvertFrom-Json
```

<span data-ttu-id="fa160-131">[ファイルの読み取りと書き込みを行うさまざまな方法][]に関する記事では、オブジェクトをファイルに保存するその他の方法が説明されています。</span><span class="sxs-lookup"><span data-stu-id="fa160-131">I cover more ways to save objects to a file in my article on [The many ways to read and write to files][].</span></span>

## <a name="working-with-properties"></a><span data-ttu-id="fa160-132">プロパティの操作</span><span class="sxs-lookup"><span data-stu-id="fa160-132">Working with properties</span></span>

### <a name="adding-properties"></a><span data-ttu-id="fa160-133">プロパティの追加</span><span class="sxs-lookup"><span data-stu-id="fa160-133">Adding properties</span></span>

<span data-ttu-id="fa160-134">`Add-Member` を使用して `PSCustomObject` に新しいプロパティを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa160-134">You can still add new properties to your `PSCustomObject` with `Add-Member`.</span></span>

```powershell
$myObject | Add-Member -MemberType NoteProperty -Name `ID` -Value 'KevinMarquette'

$myObject.ID
```

### <a name="remove-properties"></a><span data-ttu-id="fa160-135">プロパティの削除</span><span class="sxs-lookup"><span data-stu-id="fa160-135">Remove properties</span></span>

<span data-ttu-id="fa160-136">オブジェクトからプロパティを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa160-136">You can also remove properties off of an object.</span></span>

```powershell
$myObject.psobject.properties.remove('ID')
```

<span data-ttu-id="fa160-137">`psobject` は、ベース オブジェクトのメタデータへのアクセスを提供する非表示のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="fa160-137">The `psobject` is a hidden property that gives you access to base object metadata.</span></span>

### <a name="enumerating-property-names"></a><span data-ttu-id="fa160-138">プロパティ名の列挙</span><span class="sxs-lookup"><span data-stu-id="fa160-138">Enumerating property names</span></span>

<span data-ttu-id="fa160-139">オブジェクトのすべてのプロパティ名の一覧が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="fa160-139">Sometimes you need a list of all the property names on an object.</span></span>

```powershell
$myObject | Get-Member -MemberType NoteProperty | Select -ExpandProperty Name
```

<span data-ttu-id="fa160-140">この同じ一覧を `psobject` プロパティからも取得できます。</span><span class="sxs-lookup"><span data-stu-id="fa160-140">We can get this same list off of the `psobject` property too.</span></span>

```powershell
$myobject.psobject.properties.name
```

### <a name="dynamically-accessing-properties"></a><span data-ttu-id="fa160-141">プロパティへの動的なアクセス</span><span class="sxs-lookup"><span data-stu-id="fa160-141">Dynamically accessing properties</span></span>

<span data-ttu-id="fa160-142">プロパティ値に直接アクセスできることは既に説明しました。</span><span class="sxs-lookup"><span data-stu-id="fa160-142">I already mentioned that you can access property values directly.</span></span>

```powershell
$myObject.Name
```

<span data-ttu-id="fa160-143">プロパティ名に文字列を使用しても、やはり機能します。</span><span class="sxs-lookup"><span data-stu-id="fa160-143">You can use a string for the property name and it will still work.</span></span>

```powershell
$myObject.'Name'
```

<span data-ttu-id="fa160-144">これをもう一歩進めて、プロパティ名に変数を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fa160-144">We can take this one more step and use a variable for the property name.</span></span>

```powershell
$property = 'Name'
$myObject.$property
```

<span data-ttu-id="fa160-145">これは奇妙に見えますが、うまく機能します。</span><span class="sxs-lookup"><span data-stu-id="fa160-145">I know that looks strange, but it works.</span></span>

### <a name="convert-pscustomobject-into-a-hashtable"></a><span data-ttu-id="fa160-146">PSCustomObject をハッシュテーブルに変換する</span><span class="sxs-lookup"><span data-stu-id="fa160-146">Convert PSCustomObject into a hashtable</span></span>

<span data-ttu-id="fa160-147">最後のセクションから作業を続行する場合、プロパティを動的にウォークして、そこからハッシュテーブルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="fa160-147">To continue on from the last section, you can dynamically walk the properties and create a hashtable from them.</span></span>

```powershell
$hashtable = @{}
foreach( $property in $myobject.psobject.properties.name )
{
    $hashtable[$property] = $myObject.$property
}
```

### <a name="testing-for-properties"></a><span data-ttu-id="fa160-148">プロパティのテスト</span><span class="sxs-lookup"><span data-stu-id="fa160-148">Testing for properties</span></span>

<span data-ttu-id="fa160-149">プロパティが存在するかどうかを知る必要がある場合は、そのプロパティに値があるかどうかを確認するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="fa160-149">If you need to know if a property exists, you could just check for that property to have a value.</span></span>

```powershell
if( $null -ne $myObject.ID )
```

<span data-ttu-id="fa160-150">ただし、値が `$null` である可能性がある場合は、`psobject.properties` をチェックすることで、これが存在するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="fa160-150">But if the value could be `$null` you can check to see if it exists by checking the `psobject.properties` for it.</span></span>

```powershell
if( $myobject.psobject.properties.match('ID').Count )
```

## <a name="adding-object-methods"></a><span data-ttu-id="fa160-151">オブジェクト メソッドの追加</span><span class="sxs-lookup"><span data-stu-id="fa160-151">Adding object methods</span></span>

<span data-ttu-id="fa160-152">スクリプト メソッドをオブジェクトに追加する必要がある場合は、`Add-Member` と `ScriptBlock` を使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="fa160-152">If you need to add a script method to an object, you can do it with `Add-Member` and a `ScriptBlock`.</span></span> <span data-ttu-id="fa160-153">現在のオブジェクトを参照するには、`this` 自動変数を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa160-153">You have to use the `this` automatic variable reference the current object.</span></span> <span data-ttu-id="fa160-154">オブジェクトをハッシュテーブルに変換する `scriptblock` を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fa160-154">Here is a `scriptblock` to turn an object into a hashtable.</span></span> <span data-ttu-id="fa160-155">(最後の例と同じコード形式)</span><span class="sxs-lookup"><span data-stu-id="fa160-155">(same code form the last example)</span></span>

```powershell
$ScriptBlock = {
    $hashtable = @{}
    foreach( $property in $this.psobject.properties.name )
    {
        $hashtable[$property] = $this.$property
    }
    return $hashtable
}
```

<span data-ttu-id="fa160-156">次に、それをスクリプト プロパティとしてオブジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="fa160-156">Then we add it to our object as a script property.</span></span>

```powershell
$memberParam = @{
    MemberType = "ScriptMethod"
    InputObject = $myobject
    Name = "ToHashtable"
    Value = $scriptBlock
}
Add-Member @memberParam
```

<span data-ttu-id="fa160-157">その後、次のように関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fa160-157">Then we can call our function like this:</span></span>

```powershell
$myObject.ToHashtable()
```

### <a name="objects-vs-value-types"></a><span data-ttu-id="fa160-158">オブジェクトと値の型</span><span class="sxs-lookup"><span data-stu-id="fa160-158">Objects vs Value types</span></span>

<span data-ttu-id="fa160-159">オブジェクトと値の型では、変数の割り当ての処理方法が異なります。</span><span class="sxs-lookup"><span data-stu-id="fa160-159">Objects and value types don't handle variable assignments the same way.</span></span> <span data-ttu-id="fa160-160">値の型を相互に割り当てた場合、値だけが新しい変数にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="fa160-160">If you assign value types to each other, only the value get copied to the new variable.</span></span>

```powershell
$first = 1
$second = $first
$second = 2
```

<span data-ttu-id="fa160-161">この場合、`$first` は 1、`$second` は 2 です。</span><span class="sxs-lookup"><span data-stu-id="fa160-161">In this case, `$first` is 1 and `$second` is 2.</span></span>

<span data-ttu-id="fa160-162">オブジェクト変数では、実際のオブジェクトへの参照が保持されます。</span><span class="sxs-lookup"><span data-stu-id="fa160-162">Object variables hold a reference to the actual object.</span></span> <span data-ttu-id="fa160-163">新しい変数に 1 つのオブジェクトを割り当てても、それらは引き続き同じオブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="fa160-163">When you assign one object to a new variable, they still reference the same object.</span></span>

```powershell
$third = [PSCustomObject]@{Key=3}
$fourth = $third
$fourth.Key = 4
```

<span data-ttu-id="fa160-164">`$third` と `$fourth` はオブジェクトの同じインスタンスを参照するため、`$third.key` と `$fourth.Key` の両方が 4 になります。</span><span class="sxs-lookup"><span data-stu-id="fa160-164">Because `$third` and `$fourth` reference the same instance of an object, both `$third.key` and `$fourth.Key` are 4.</span></span>

### <a name="psobjectcopy"></a><span data-ttu-id="fa160-165">psobject.copy()</span><span class="sxs-lookup"><span data-stu-id="fa160-165">psobject.copy()</span></span>

<span data-ttu-id="fa160-166">オブジェクトを本当にコピーする必要がある場合は、複製することができます。</span><span class="sxs-lookup"><span data-stu-id="fa160-166">If you need a true copy of an object, you can clone it.</span></span>

```powershell
$third = [PSCustomObject]@{Key=3}
$fourth = $third.psobject.copy()
$fourth.Key = 4
```

<span data-ttu-id="fa160-167">複製では、そのオブジェクトのシャロー コピーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fa160-167">Clone creates a shallow copy of the object.</span></span> <span data-ttu-id="fa160-168">この例では、それぞれが異なるインスタンスを持つようになり、`$third.key` が 3、`$fourth.Key` が 4 になります。</span><span class="sxs-lookup"><span data-stu-id="fa160-168">They have different instances now and `$third.key` is 3 and `$fourth.Key` is 4 in this example.</span></span>

<span data-ttu-id="fa160-169">これをシャロー コピーと呼んだのは、入れ子になったオブジェクトを使用する場合があるためです。</span><span class="sxs-lookup"><span data-stu-id="fa160-169">I call this a shallow copy because if you have nested objects.</span></span> <span data-ttu-id="fa160-170">(プロパティに他のオブジェクトが含まれている場合)。</span><span class="sxs-lookup"><span data-stu-id="fa160-170">(where the properties contain other objects).</span></span> <span data-ttu-id="fa160-171">最上位レベルの値のみがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="fa160-171">Only the top-level values are copied.</span></span> <span data-ttu-id="fa160-172">子オブジェクトはお互いを参照します。</span><span class="sxs-lookup"><span data-stu-id="fa160-172">The child objects will reference each other.</span></span>

### <a name="pstypename-for-custom-object-types"></a><span data-ttu-id="fa160-173">カスタム オブジェクトの型に対する PSTypeName</span><span class="sxs-lookup"><span data-stu-id="fa160-173">PSTypeName for custom object types</span></span>

<span data-ttu-id="fa160-174">これでオブジェクトを作成できたので、これを使用して、まったく明白ではないかもしれないその他の操作をいくつか実行できます。</span><span class="sxs-lookup"><span data-stu-id="fa160-174">Now that we have an object, there are a few more things we can do with it that may not be nearly as obvious.</span></span> <span data-ttu-id="fa160-175">まず、これに `PSTypeName` を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa160-175">First thing we need to do is give it a `PSTypeName`.</span></span> <span data-ttu-id="fa160-176">最もよく使用されている一般的な方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fa160-176">This is the most common way I see people do it:</span></span>

```powershell
$myObject.PSObject.TypeNames.Insert(0,"My.Object")
```

<span data-ttu-id="fa160-177">最近、こちらの [/u/markekraus による投稿][]から、これを行う別の方法を発見しました。</span><span class="sxs-lookup"><span data-stu-id="fa160-177">I recently discovered another way to do this from this [post by /u/markekraus][].</span></span> <span data-ttu-id="fa160-178">私はもう少し詳しく調べて、[Adam Bertram][] と [Mike Shepard][] によるこのアイデアについてのさらなる投稿を見つけました。そこでは、これをインラインで定義できるようにするアプローチが説明されています。</span><span class="sxs-lookup"><span data-stu-id="fa160-178">I did a little digging and more posts about the idea from [Adam Bertram][] and [Mike Shepard][] where they talk about this approach that allows you to define it inline.</span></span>

```powershell
$myObject = [PSCustomObject]@{
    PSTypeName = 'My.Object'
    Name       = 'Kevin'
    Language   = 'PowerShell'
    State      = 'Texas'
}
```

<span data-ttu-id="fa160-179">これはこの言語にとてもよく合っています。</span><span class="sxs-lookup"><span data-stu-id="fa160-179">I love how nicely this just fits into the language.</span></span> <span data-ttu-id="fa160-180">これで、適切な型名を持つオブジェクトを作成できたので、さらにいくつかの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fa160-180">Now that we have an object with a proper type name, we can do some more things.</span></span>

> [!NOTE]
> <span data-ttu-id="fa160-181">PowerShell クラスを使用して、カスタム PowerShell 型を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa160-181">You can also create custom PowerShell types using PowerShell classes.</span></span> <span data-ttu-id="fa160-182">詳細については、[PowerShell クラスの概要](/powershell/module/Microsoft.PowerShell.Core/About/about_Classes)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa160-182">For more information, see [PowerShell Class Overview](/powershell/module/Microsoft.PowerShell.Core/About/about_Classes).</span></span>

## <a name="using-defaultpropertyset-the-long-way"></a><span data-ttu-id="fa160-183">DefaultPropertySet の使用 (長い道のり)</span><span class="sxs-lookup"><span data-stu-id="fa160-183">Using DefaultPropertySet (the long way)</span></span>

<span data-ttu-id="fa160-184">PowerShell では、既定で表示するプロパティが自動的に決定されます。</span><span class="sxs-lookup"><span data-stu-id="fa160-184">PowerShell decides for us what properties to display by default.</span></span> <span data-ttu-id="fa160-185">多くのネイティブ コマンドには、すべての複雑な処理を行う `.ps1xml` [書式設定ファイル][]があります。</span><span class="sxs-lookup"><span data-stu-id="fa160-185">A lot of the native commands have a `.ps1xml` [formatting file][] that does all the heavy lifting.</span></span> <span data-ttu-id="fa160-186">こちらの [Boe Prox による投稿][]から、PowerShell のみを使用してカスタム オブジェクトに対してこれを行う別の方法があります。</span><span class="sxs-lookup"><span data-stu-id="fa160-186">From this [post by Boe Prox][], there's another way for us to do this on our custom object using just PowerShell.</span></span> <span data-ttu-id="fa160-187">これに使用する `MemberSet` を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fa160-187">We can give it a `MemberSet` for it to use.</span></span>

```powershell
$defaultDisplaySet = 'Name','Language'
$defaultDisplayPropertySet = New-Object System.Management.Automation.PSPropertySet('DefaultDisplayPropertySet',[string[]]$defaultDisplaySet)
$PSStandardMembers = [System.Management.Automation.PSMemberInfo[]]@($defaultDisplayPropertySet)
$MyObject | Add-Member MemberSet PSStandardMembers $PSStandardMembers
```

<span data-ttu-id="fa160-188">これで、オブジェクトがシェルに表示されると、既定ではこれらのプロパティのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa160-188">Now when my object just falls to the shell, it will only show those properties by default.</span></span>

### <a name="update-typedata-with-defaultpropertyset"></a><span data-ttu-id="fa160-189">Update-TypeData と DefaultPropertySet</span><span class="sxs-lookup"><span data-stu-id="fa160-189">Update-TypeData with DefaultPropertySet</span></span>

<span data-ttu-id="fa160-190">これは便利ですが、最近、[Jeffrey Snover と Don Jones による PowerShell アンプラグド 2016][psunplugged] を見ていたときに、より良い方法を知りました。</span><span class="sxs-lookup"><span data-stu-id="fa160-190">This is nice but I recently saw a better way when watching [PowerShell unplugged 2016 with Jeffrey Snover & Don Jones][psunplugged].</span></span> <span data-ttu-id="fa160-191">Jeffrey は [Update-TypeData][] を使用して、既定のプロパティを指定していました。</span><span class="sxs-lookup"><span data-stu-id="fa160-191">Jeffrey was using [Update-TypeData][] to specify the default properties.</span></span>

```powershell
$TypeData = @{
    TypeName = 'My.Object'
    DefaultDisplayPropertySet = 'Name','Language'
}
Update-TypeData @TypeData
```

<span data-ttu-id="fa160-192">これは簡単なので、もし私がこの投稿をクイック リファレンスとして使えなくても、内容をほとんど覚えていたでしょう。</span><span class="sxs-lookup"><span data-stu-id="fa160-192">That is simple enough that I could almost remember it if I didn't have this post as a quick reference.</span></span> <span data-ttu-id="fa160-193">これで、多くのプロパティを持つオブジェクトを簡単に作成し、さらにシェルから見たときにわかりやすい表示にすることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fa160-193">Now I can easily create objects with lots of properties and still give it a nice clean view when looking at it from the shell.</span></span> <span data-ttu-id="fa160-194">その他のプロパティにアクセスしたり表示したりする必要がある場合も、それらはまだ存在しています。</span><span class="sxs-lookup"><span data-stu-id="fa160-194">If I need to access or see those other properties, they're still there.</span></span>

```powershell
$myObject | Format-List *
```

### <a name="update-typedata-with-scriptproperty"></a><span data-ttu-id="fa160-195">Update-TypeData と ScriptProperty</span><span class="sxs-lookup"><span data-stu-id="fa160-195">Update-TypeData with ScriptProperty</span></span>

<span data-ttu-id="fa160-196">このビデオから得たその他の情報は、オブジェクトのスクリプト プロパティを作成することです。</span><span class="sxs-lookup"><span data-stu-id="fa160-196">Something else I got out of that video was creating script properties for your objects.</span></span> <span data-ttu-id="fa160-197">これは既存のオブジェクトに対しても同様に機能することを、ここで指摘しておきましょう。</span><span class="sxs-lookup"><span data-stu-id="fa160-197">This would be a good time to point out that this works for existing objects too.</span></span>

```powershell
$TypeData = @{
    TypeName = 'My.Object'
    MemberType = 'ScriptProperty'
    MemberName = 'UpperCaseName'
    Value = {$this.Name.toUpper()}
}
Update-TypeData @TypeData
```

<span data-ttu-id="fa160-198">これは、オブジェクトが作成される前に実行しても後に実行しても機能します。</span><span class="sxs-lookup"><span data-stu-id="fa160-198">You can do this before your object is created or after and it will still work.</span></span> <span data-ttu-id="fa160-199">これが、スクリプト プロパティで `Add-Member` を使用する場合との相違点です。</span><span class="sxs-lookup"><span data-stu-id="fa160-199">This is what makes this different then using `Add-Member` with a script property.</span></span> <span data-ttu-id="fa160-200">以前に言及した方法で `Add-Member` を使用した場合、これはオブジェクトのその特定のインスタンス上にのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="fa160-200">When you use `Add-Member` the way I referenced earlier, it only exists on that specific instance of the object.</span></span> <span data-ttu-id="fa160-201">これは、この `TypeName` を持つすべてのオブジェクトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="fa160-201">This one applies to all objects with this `TypeName`.</span></span>

## <a name="function-parameters"></a><span data-ttu-id="fa160-202">関数のパラメーター</span><span class="sxs-lookup"><span data-stu-id="fa160-202">Function parameters</span></span>

<span data-ttu-id="fa160-203">これで、これらのパラメーターのカスタム型を関数やスクリプト内で使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fa160-203">You can now use these custom types for parameters in your functions and scripts.</span></span> <span data-ttu-id="fa160-204">1 つの関数でこれらのカスタム オブジェクトを作成し、他の関数に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="fa160-204">You can have one function create these custom objects and then pass them into other functions.</span></span>

```powershell
param( [PSTypeName('My.Object')]$Data )
```

<span data-ttu-id="fa160-205">PowerShell では、オブジェクトが指定した型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa160-205">PowerShell requires that the object is the type you specified.</span></span> <span data-ttu-id="fa160-206">型が自動的に一致しない場合は検証エラーがスローされるため、自分のコードでそれをテストする手間が省けます。</span><span class="sxs-lookup"><span data-stu-id="fa160-206">It throws a validation error if the type doesn't match automatically to save you the step of testing for it in your code.</span></span> <span data-ttu-id="fa160-207">これは PowerShell に得意な処理を任せる場合の優れた例です。</span><span class="sxs-lookup"><span data-stu-id="fa160-207">A great example of letting PowerShell do what it does best.</span></span>

### <a name="function-outputtype"></a><span data-ttu-id="fa160-208">関数の OutputType</span><span class="sxs-lookup"><span data-stu-id="fa160-208">Function OutputType</span></span>

<span data-ttu-id="fa160-209">また、高度な関数の `OutputType` を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa160-209">You can also define an `OutputType` for your advanced functions.</span></span>

```powershell
function Get-MyObject
{
    [OutputType('My.Object')]
    [CmdletBinding()]
        param
        (
            ...
```

<span data-ttu-id="fa160-210">**OutputType** 属性値は、ドキュメントのメモにすぎません。</span><span class="sxs-lookup"><span data-stu-id="fa160-210">The **OutputType** attribute value is only a documentation note.</span></span> <span data-ttu-id="fa160-211">これを関数のコードから派生させたり、実際の関数の出力と比較したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fa160-211">It isn't derived from the function code or compared to the actual function output.</span></span>

<span data-ttu-id="fa160-212">出力型を使用する主な理由は、関数に関するメタ情報に自分の意図を反映させることです。</span><span class="sxs-lookup"><span data-stu-id="fa160-212">The main reason you would use an output type is so that meta information about your function reflects your intentions.</span></span> <span data-ttu-id="fa160-213">開発環境で利用できる `Get-Command` や `Get-Help` のようなものです。</span><span class="sxs-lookup"><span data-stu-id="fa160-213">Things like `Get-Command` and `Get-Help` that your development environment can take advantage of.</span></span> <span data-ttu-id="fa160-214">詳細については、そのヘルプを参照してください: [about_Functions_OutputTypeAttribute][]。</span><span class="sxs-lookup"><span data-stu-id="fa160-214">If you want more information, then take a look at the help for it: [about_Functions_OutputTypeAttribute][].</span></span>

<span data-ttu-id="fa160-215">ただし、関数の単体テストを行うために Pester を使用している場合は、出力オブジェクトが **OutputType** と一致することを検証することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fa160-215">With that said, if you're using Pester to unit test your functions then it would be a good idea to validate the output objects match your **OutputType**.</span></span> <span data-ttu-id="fa160-216">これにより、不適切な場合にパイプに送られた変数をキャッチできます。</span><span class="sxs-lookup"><span data-stu-id="fa160-216">This could catch variables that just fall to the pipe when they shouldn't.</span></span>

## <a name="closing-thoughts"></a><span data-ttu-id="fa160-217">最後に</span><span class="sxs-lookup"><span data-stu-id="fa160-217">Closing thoughts</span></span>

<span data-ttu-id="fa160-218">このコンテキストはすべて `[PSCustomObject]` に関するものでしたが、この情報の大部分はオブジェクト全般に適用されます。</span><span class="sxs-lookup"><span data-stu-id="fa160-218">The context of this was all about `[PSCustomObject]`, but a lot of this information applies to objects in general.</span></span>

<span data-ttu-id="fa160-219">これらの機能のほとんどは以前にどこかで見たことがありましたが、`PSCustomObject` に関する情報のコレクションとして提示されているのは見たことがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="fa160-219">I have seen most of these features in passing before but never saw them presented as a collection of information on `PSCustomObject`.</span></span> <span data-ttu-id="fa160-220">つい先週、私はもう一つを偶然見つけて、それを前に見ていなかったことに驚きました。</span><span class="sxs-lookup"><span data-stu-id="fa160-220">Just this last week I stumbled upon another one and was surprised that I had not seen it before.</span></span> <span data-ttu-id="fa160-221">私は、これらすべてのアイデアをまとめて、皆様が全体像を確認し、使用する機会があればそれらを認識できるようにしたいと思いました。</span><span class="sxs-lookup"><span data-stu-id="fa160-221">I wanted to pull all these ideas together so you can hopefully see the bigger picture and be aware of them when you have an opportunity to use them.</span></span> <span data-ttu-id="fa160-222">皆様が何かを学び、ご自分のスクリプトで使用する方法を見つけられれば幸いです。</span><span class="sxs-lookup"><span data-stu-id="fa160-222">I hope you learned something and can find a way to work this into your scripts.</span></span>

<!-- link references -->
[オリジナル バージョン]: https://powershellexplained.com/2016-10-28-powershell-everything-you-wanted-to-know-about-pscustomobject/
[original version]: https://powershellexplained.com/2016-10-28-powershell-everything-you-wanted-to-know-about-pscustomobject/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[Boe Prox による投稿]: https://learn-PowerShell.net/2013/08/03/quick-hits-set-the-default-property-display-in-PowerShell-on-custom-objects/
[post by Boe Prox]: https://learn-PowerShell.net/2013/08/03/quick-hits-set-the-default-property-display-in-PowerShell-on-custom-objects/
[書式設定ファイル]: https://mcpmag.com/articles/2014/05/13/PowerShell-properties-part-3.aspx
[formatting file]: https://mcpmag.com/articles/2014/05/13/PowerShell-properties-part-3.aspx
[about_Functions_OutputTypeAttribute]: /powershell/module/microsoft.powershell.core/about/about_functions_outputtypeattribute
[ファイルの読み取りと書き込みを行うさまざまな方法]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files
[The many ways to read and write to files]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files
[/u/markekraus による投稿]: https://www.reddit.com/r/PowerShell/comments/590awc/is_it_possible_to_initialize_a_pscustoobject_with/
[post by /u/markekraus]: https://www.reddit.com/r/PowerShell/comments/590awc/is_it_possible_to_initialize_a_pscustoobject_with/
[Adam Bertram]: http://www.adamtheautomator.com/building-custom-object-types-PowerShell-pstypename/
[Mike Shepard]: https://powershellstation.com/2016/05/22/custom-objects-and-pstypename/
[psunplugged]: https://www.youtube.com/watch?v=Ab46gHXNm8Q
[Update-TypeData]: /powershell/module/microsoft.powershell.utility/update-typedata
