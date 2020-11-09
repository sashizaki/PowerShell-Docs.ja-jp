---
title: switch ステートメントについて知りたかったことのすべて
description: PowerShell の switch ステートメントには、他の言語では見つからない機能が用意されています。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: c2e77aa5fb36d04fec1bc86f751291205120c729
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "93355121"
---
# <a name="everything-you-ever-wanted-to-know-about-the-switch-statement"></a><span data-ttu-id="a235d-103">switch ステートメントについて知りたかったことのすべて</span><span class="sxs-lookup"><span data-stu-id="a235d-103">Everything you ever wanted to know about the switch statement</span></span>

<span data-ttu-id="a235d-104">他の多くの言語と同様に、PowerShell には、スクリプト内の実行フローを制御するためのコマンドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a235d-104">Like many other languages, PowerShell has commands for controlling the flow of execution within your scripts.</span></span> <span data-ttu-id="a235d-105">このようなステートメントの 1 つが [switch][] ステートメントであり、PowerShell 内では他の言語にはない機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="a235d-105">One of those statements is the [switch][] statement and in PowerShell, it offers features that aren't found in other languages.</span></span> <span data-ttu-id="a235d-106">本日は、PowerShell `switch` の使用について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="a235d-106">Today, we take a deep dive into working with the PowerShell `switch`.</span></span>

> [!NOTE]
> <span data-ttu-id="a235d-107">この記事の[オリジナル バージョン][]は、[@KevinMarquette][] 氏のブログ記事です。</span><span class="sxs-lookup"><span data-stu-id="a235d-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="a235d-108">このコンテンツを共有してくださった Kevin 氏に、PowerShell チームより感謝を申し上げます。</span><span class="sxs-lookup"><span data-stu-id="a235d-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="a235d-109">[PowerShellExplained.com][] のブログをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="a235d-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="the-if-statement"></a><span data-ttu-id="a235d-110">`if` ステートメント</span><span class="sxs-lookup"><span data-stu-id="a235d-110">The `if` statement</span></span>

<span data-ttu-id="a235d-111">最初に学習するステートメントの 1 つは、`if` ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="a235d-111">One of the first statements that you learn is the `if` statement.</span></span> <span data-ttu-id="a235d-112">ステートメントが `$true` の場合にスクリプト ブロックが実行されるようにできます。</span><span class="sxs-lookup"><span data-stu-id="a235d-112">It lets you execute a script block if a statement is `$true`.</span></span>

``` powershell
if ( Test-Path $Path )
{
    Remove-Item $Path
}
```

<span data-ttu-id="a235d-113">`elseif` および `else` ステートメントを使用すると、より複雑なロジックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a235d-113">You can have much more complicated logic by using `elseif` and `else` statements.</span></span> <span data-ttu-id="a235d-114">ここでは、曜日の数値を使用して、名前を文字列として取得する例を示します。</span><span class="sxs-lookup"><span data-stu-id="a235d-114">Here is an example where I have a numeric value for day of the week and I want to get the name as a string.</span></span>

``` powershell
$day = 3

if ( $day -eq 0 ) { $result = 'Sunday'        }
elseif ( $day -eq 1 ) { $result = 'Monday'    }
elseif ( $day -eq 2 ) { $result = 'Tuesday'   }
elseif ( $day -eq 3 ) { $result = 'Wednesday' }
elseif ( $day -eq 4 ) { $result = 'Thursday'  }
elseif ( $day -eq 5 ) { $result = 'Friday'    }
elseif ( $day -eq 6 ) { $result = 'Saturday'  }

$result
```

```Output
Wednesday
```

<span data-ttu-id="a235d-115">これは一般的なパターンであり、これを処理する方法は多数あります。</span><span class="sxs-lookup"><span data-stu-id="a235d-115">It turns out that this is a common pattern and there are many ways to deal with this.</span></span> <span data-ttu-id="a235d-116">その 1 つに `switch` を使用する方法があります。</span><span class="sxs-lookup"><span data-stu-id="a235d-116">One of them is with a `switch`.</span></span>

## <a name="switch-statement"></a><span data-ttu-id="a235d-117">Switch ステートメント</span><span class="sxs-lookup"><span data-stu-id="a235d-117">Switch statement</span></span>

<span data-ttu-id="a235d-118">`switch` ステートメントを使用すると、変数と有効な値の一覧を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a235d-118">The `switch` statement allows you to provide a variable and a list of possible values.</span></span> <span data-ttu-id="a235d-119">値が変数に一致すると、そのスクリプト ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="a235d-119">If the value matches the variable, then its scriptblock is executed.</span></span>

``` powershell
$day = 3

switch ( $day )
{
    0 { $result = 'Sunday'    }
    1 { $result = 'Monday'    }
    2 { $result = 'Tuesday'   }
    3 { $result = 'Wednesday' }
    4 { $result = 'Thursday'  }
    5 { $result = 'Friday'    }
    6 { $result = 'Saturday'  }
}

$result
```

```Output
'Wednesday'
```

<span data-ttu-id="a235d-120">この例では、`$day` の値が数値のいずれかに一致すると、正しい名前が `$result` に代入されます。</span><span class="sxs-lookup"><span data-stu-id="a235d-120">For this example, the value of `$day` matches one of the numeric values, then the correct name is assigned to `$result`.</span></span> <span data-ttu-id="a235d-121">この例では変数代入のみを行っていますが、これらのスクリプト ブロック内で任意の PowerShell を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a235d-121">We are only doing a variable assignment in this example, but any PowerShell can be executed in those script blocks.</span></span>

### <a name="assign-to-a-variable"></a><span data-ttu-id="a235d-122">変数に代入する</span><span class="sxs-lookup"><span data-stu-id="a235d-122">Assign to a variable</span></span>

<span data-ttu-id="a235d-123">この最後の例は、別の方法で記述できます。</span><span class="sxs-lookup"><span data-stu-id="a235d-123">We can write that last example in another way.</span></span>

``` powershell
$result = switch ( $day )
{
    0 { 'Sunday'    }
    1 { 'Monday'    }
    2 { 'Tuesday'   }
    3 { 'Wednesday' }
    4 { 'Thursday'  }
    5 { 'Friday'    }
    6 { 'Saturday'  }
}
```

<span data-ttu-id="a235d-124">PowerShell パイプラインに値を入れ、それを `$result` に代入しています。</span><span class="sxs-lookup"><span data-stu-id="a235d-124">We are placing the value on the PowerShell pipeline and assigning it to the `$result`.</span></span> <span data-ttu-id="a235d-125">これと同じことを、`if` および `foreach` ステートメントでも行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a235d-125">You can do this same thing with the `if` and `foreach` statements.</span></span>

### <a name="default"></a><span data-ttu-id="a235d-126">Default</span><span class="sxs-lookup"><span data-stu-id="a235d-126">Default</span></span>

<span data-ttu-id="a235d-127">`default` キーワードを使用すると、一致するものがない場合にどうするかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a235d-127">We can use the `default` keyword to identify the what should happen if there is no match.</span></span>

``` powershell
$result = switch ( $day )
{
    0 { 'Sunday' }
    # ...
    6 { 'Saturday' }
    default { 'Unknown' }
}
```

<span data-ttu-id="a235d-128">ここでは、既定のケースで `Unknown` 値を返します。</span><span class="sxs-lookup"><span data-stu-id="a235d-128">Here we return the value `Unknown` in the default case.</span></span>

### <a name="strings"></a><span data-ttu-id="a235d-129">文字列</span><span class="sxs-lookup"><span data-stu-id="a235d-129">Strings</span></span>

<span data-ttu-id="a235d-130">これらの最後の例では数値を照合しましたが、文字列を照合することもできます。</span><span class="sxs-lookup"><span data-stu-id="a235d-130">I was matching numbers in those last examples, but you can also match strings.</span></span>

``` powershell
$item = 'Role'

switch ( $item )
{
    Component
    {
        'is a component'
    }
    Role
    {
        'is a role'
    }
    Location
    {
        'is a location'
    }
}
```

```Output
is a role
```

<span data-ttu-id="a235d-131">ここでは、一致項目 `Component`、`Role`、および `Location` を引用符で囲まないことにしました。引用符は省略可能であることを示すためです。</span><span class="sxs-lookup"><span data-stu-id="a235d-131">I decided not to wrap the `Component`,`Role` and `Location` matches in quotes here to highlight that they're optional.</span></span> <span data-ttu-id="a235d-132">`switch` では、ほとんどの場合、これらは文字列として扱われます。</span><span class="sxs-lookup"><span data-stu-id="a235d-132">The `switch` treats those as a string in most cases.</span></span>

## <a name="arrays"></a><span data-ttu-id="a235d-133">配列</span><span class="sxs-lookup"><span data-stu-id="a235d-133">Arrays</span></span>

<span data-ttu-id="a235d-134">PowerShell `switch` の優れた機能の 1 つは、配列の処理方法です。</span><span class="sxs-lookup"><span data-stu-id="a235d-134">One of the cool features of the PowerShell `switch` is the way it handles arrays.</span></span> <span data-ttu-id="a235d-135">`switch` に配列 を与えると、そのコレクション内の各要素が処理されます。</span><span class="sxs-lookup"><span data-stu-id="a235d-135">If you give a `switch` an array, it processes each element in that collection.</span></span>

``` powershell
$roles = @('WEB','Database')

switch ( $roles ) {
    'Database'   { 'Configure SQL' }
    'WEB'        { 'Configure IIS' }
    'FileServer' { 'Configure Share' }
}
```

```Output
Configure IIS
Configure SQL
```

<span data-ttu-id="a235d-136">配列内に繰り返されている項目がある場合、それらは該当するセクションに複数回一致します。</span><span class="sxs-lookup"><span data-stu-id="a235d-136">If you have repeated items in your array, then they're matched multiple times by the appropriate section.</span></span>

### <a name="psitem"></a><span data-ttu-id="a235d-137">PSItem</span><span class="sxs-lookup"><span data-stu-id="a235d-137">PSItem</span></span>

<span data-ttu-id="a235d-138">`$PSItem` または `$_` を使用すると、処理された現在の項目を参照できます。</span><span class="sxs-lookup"><span data-stu-id="a235d-138">You can use the `$PSItem` or `$_` to reference the current item that was processed.</span></span> <span data-ttu-id="a235d-139">単純な照合を行う場合、`$PSItem` は照合する値です。</span><span class="sxs-lookup"><span data-stu-id="a235d-139">When we do a simple match, `$PSItem` is the value that we are matching.</span></span> <span data-ttu-id="a235d-140">次のセクションでは、この変数を使用して高度な照合をいくつか実行します。</span><span class="sxs-lookup"><span data-stu-id="a235d-140">I'll be performing some advanced matches in the next section where this variable is used.</span></span>

## <a name="parameters"></a><span data-ttu-id="a235d-141">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a235d-141">Parameters</span></span>

<span data-ttu-id="a235d-142">PowerShell `switch` の固有の機能は、その実行方法を変更する[スイッチ パラメーター][]がいくつかあることです。</span><span class="sxs-lookup"><span data-stu-id="a235d-142">A unique feature of the PowerShell `switch` is that it has a number of [switch parameters][] that change how it performs.</span></span>

### <a name="-casesensitive"></a><span data-ttu-id="a235d-143">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="a235d-143">-CaseSensitive</span></span>

<span data-ttu-id="a235d-144">既定では、照合時に大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="a235d-144">The matches aren't case-sensitive by default.</span></span> <span data-ttu-id="a235d-145">大文字と小文字を区別する必要がある場合は、`-CaseSensitive` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a235d-145">If you need to be case-sensitive, you can use `-CaseSensitive`.</span></span> <span data-ttu-id="a235d-146">これは、他のスイッチ パラメーターと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="a235d-146">This can be used in combination with the other switch parameters.</span></span>

### <a name="-wildcard"></a><span data-ttu-id="a235d-147">-Wildcard</span><span class="sxs-lookup"><span data-stu-id="a235d-147">-Wildcard</span></span>

<span data-ttu-id="a235d-148">`-wildcard` スイッチを使用すると、ワイルドカードのサポートを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="a235d-148">We can enable wildcard support with the `-wildcard` switch.</span></span> <span data-ttu-id="a235d-149">これは、`-like` 演算子と同じワイルドカード ロジックを使用して、各照合を実行します。</span><span class="sxs-lookup"><span data-stu-id="a235d-149">This uses the same wildcard logic as the `-like` operator to do each match.</span></span>

``` powershell
$Message = 'Warning, out of disk space'

switch -Wildcard ( $message )
{
    'Error*'
    {
        Write-Error -Message $Message
    }
    'Warning*'
    {
        Write-Warning -Message $Message
    }
    default
    {
        Write-Information $message
    }
}
```

```Output
WARNING: Warning, out of disk space
```

<span data-ttu-id="a235d-150">ここでは、メッセージを処理し、コンテンツに基づいてさまざまなストリームに出力しています。</span><span class="sxs-lookup"><span data-stu-id="a235d-150">Here we are processing a message and then outputting it on different streams based on the contents.</span></span>

### <a name="-regex"></a><span data-ttu-id="a235d-151">-Regex</span><span class="sxs-lookup"><span data-stu-id="a235d-151">-Regex</span></span>

<span data-ttu-id="a235d-152">switch ステートメントでは、ワイルドカードと同様に、正規表現照合がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a235d-152">The switch statement supports regex matches just like it does wildcards.</span></span>

``` powershell
switch -Regex ( $message )
{
    '^Error'
    {
        Write-Error -Message $Message
    }
    '^Warning'
    {
        Write-Warning -Message $Message
    }
    default
    {
        Write-Information $message
    }
}
```

<span data-ttu-id="a235d-153">次の記事では、正規表現を使用するその他の例を記載しています。[正規表現を使用するさまざまな方法][]。</span><span class="sxs-lookup"><span data-stu-id="a235d-153">I have more examples of using regex in another article I wrote: [The many ways to use regex][].</span></span>

### <a name="-file"></a><span data-ttu-id="a235d-154">-File</span><span class="sxs-lookup"><span data-stu-id="a235d-154">-File</span></span>

<span data-ttu-id="a235d-155">switch ステートメントには、`-File` パラメーターを使用してファイルを処理できるという、あまり知られていない機能があります。</span><span class="sxs-lookup"><span data-stu-id="a235d-155">A little known feature of the switch statement is that it can process a file with the `-File` parameter.</span></span> <span data-ttu-id="a235d-156">変数式を指定する代わりに、`-file` をファイルへのパスと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="a235d-156">You use `-file` with a path to a file instead of giving it a variable expression.</span></span>

``` powershell
switch -Wildcard -File $path
{
    'Error*'
    {
        Write-Error -Message $PSItem
    }
    'Warning*'
    {
        Write-Warning -Message $PSItem
    }
    default
    {
        Write-Output $PSItem
    }
}
```

<span data-ttu-id="a235d-157">配列の処理と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="a235d-157">It works just like processing an array.</span></span> <span data-ttu-id="a235d-158">この例では、これをワイルドカード照合と組み合わせ、`$PSItem` を使用します。</span><span class="sxs-lookup"><span data-stu-id="a235d-158">In this example, I combine it with wildcard matching and make use of the `$PSItem`.</span></span> <span data-ttu-id="a235d-159">これにより、ログ ファイルが処理され、正規表現の一致に応じて警告メッセージとエラーメッセージに変換されます。</span><span class="sxs-lookup"><span data-stu-id="a235d-159">This would process a log file and convert it to warning and error messages depending on the regex matches.</span></span>

## <a name="advanced-details"></a><span data-ttu-id="a235d-160">詳細情報</span><span class="sxs-lookup"><span data-stu-id="a235d-160">Advanced details</span></span>

<span data-ttu-id="a235d-161">ドキュメントに記載されているこれらすべての機能について理解したので、さらに高度な処理のコンテキストでそれらを使用してみましょう。</span><span class="sxs-lookup"><span data-stu-id="a235d-161">Now that you're aware of all these documented features, we can use them in the context of more advanced processing.</span></span>

### <a name="expressions"></a><span data-ttu-id="a235d-162">式</span><span class="sxs-lookup"><span data-stu-id="a235d-162">Expressions</span></span>

<span data-ttu-id="a235d-163">`switch` は、変数の代わりに式を対象にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a235d-163">The `switch` can be on an expression instead of a variable.</span></span>

``` powershell
switch ( ( Get-Service | Where status -eq 'running' ).name ) {...}
```

<span data-ttu-id="a235d-164">式の評価結果が、照合に使用される値です。</span><span class="sxs-lookup"><span data-stu-id="a235d-164">Whatever the expression evaluates to is the value used for the match.</span></span>

### <a name="multiple-matches"></a><span data-ttu-id="a235d-165">複数一致</span><span class="sxs-lookup"><span data-stu-id="a235d-165">Multiple matches</span></span>

<span data-ttu-id="a235d-166">既にお気付きかもしれませんが、`switch` は複数の条件に一致する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a235d-166">You may have already picked up on this, but a `switch` can match to multiple conditions.</span></span> <span data-ttu-id="a235d-167">これは、`-wildcard` または `-regex` 照合を使用する場合に特に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="a235d-167">This is especially true when using `-wildcard` or `-regex` matches.</span></span> <span data-ttu-id="a235d-168">同じ条件を複数回追加すれば、それらすべてがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="a235d-168">You can add the same condition multiple times and all of them are triggered.</span></span>

``` powershell
switch ( 'Word' )
{
    'word' { 'lower case word match' }
    'Word' { 'mixed case word match' }
    'WORD' { 'upper case word match' }
}
```

```Output
lower case word match
mixed case word match
upper case word match
```

<span data-ttu-id="a235d-169">これら 3 つのステートメントがすべてトリガーされています。</span><span class="sxs-lookup"><span data-stu-id="a235d-169">All three of these statements are fired.</span></span> <span data-ttu-id="a235d-170">これは、すべての条件が (順に) チェックされることを示しています。</span><span class="sxs-lookup"><span data-stu-id="a235d-170">This shows that every condition is checked (in order).</span></span> <span data-ttu-id="a235d-171">これは配列を処理する場合にも当てはまり、各項目で各条件がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="a235d-171">This holds true for processing arrays where each item checks each condition.</span></span>

### <a name="continue"></a><span data-ttu-id="a235d-172">Continue</span><span class="sxs-lookup"><span data-stu-id="a235d-172">Continue</span></span>

<span data-ttu-id="a235d-173">通常は、ここで `break` ステートメントを紹介しますが、まず `continue` を使用する方法を学習する方がよいでしょう。</span><span class="sxs-lookup"><span data-stu-id="a235d-173">Normally, this is where I would introduce the `break` statement, but it's better that we learn how to use `continue` first.</span></span> <span data-ttu-id="a235d-174">`foreach` ループと同様に、`continue` はコレクション内の次の項目に進み続け、それ以上項目がなくなると `switch` から抜けます。</span><span class="sxs-lookup"><span data-stu-id="a235d-174">Just like with a `foreach` loop, `continue` continues onto the next item in the collection or exits the `switch` if there are no more items.</span></span> <span data-ttu-id="a235d-175">ステートメントが 1 つだけ実行されるように、continue ステートメントを使用して最後の例を書き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="a235d-175">We can rewrite that last example with continue statements so that only one statement executes.</span></span>

``` powershell
switch ( 'Word' )
{
    'word'
    {
        'lower case word match'
        continue
    }
    'Word'
    {
        'mixed case word match'
        continue
    }
    'WORD'
    {
        'upper case word match'
        continue
    }
}
```

```Output
lower case word match
```

<span data-ttu-id="a235d-176">3 つの項目をすべて照合するのではなく、最初の項目が一致したところで switch は次の値に進みます。</span><span class="sxs-lookup"><span data-stu-id="a235d-176">Instead of matching all three items, the first one is matched and the switch continues to the next value.</span></span> <span data-ttu-id="a235d-177">処理する値が残っていないため、switch は終了します。</span><span class="sxs-lookup"><span data-stu-id="a235d-177">Because there are no values left to process, the switch exits.</span></span> <span data-ttu-id="a235d-178">次の例は、ワイルドカードが複数の項目とどのように一致するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="a235d-178">This next example is showing how a wildcard could match multiple items.</span></span>

``` powershell
switch -Wildcard -File $path
{
    '*Error*'
    {
        Write-Error -Message $PSItem
        continue
    }
    '*Warning*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    default
    {
        Write-Output $PSItem
    }
}
```

<span data-ttu-id="a235d-179">入力ファイル内の行に `Error` と `Warning` の両方の語が含まれている可能性があるため、最初のものだけを実行してから、ファイルの処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="a235d-179">Because a line in the input file could contain both the word `Error` and `Warning`, we only want the first one to execute and then continue processing the file.</span></span>

### <a name="break"></a><span data-ttu-id="a235d-180">Break</span><span class="sxs-lookup"><span data-stu-id="a235d-180">Break</span></span>

<span data-ttu-id="a235d-181">`break` ステートメントは、switch を終了します。</span><span class="sxs-lookup"><span data-stu-id="a235d-181">A `break` statement exits the switch.</span></span> <span data-ttu-id="a235d-182">これは、個々の値に対する `continue` の動作と同じです。</span><span class="sxs-lookup"><span data-stu-id="a235d-182">This is the same behavior that `continue` presents for single values.</span></span> <span data-ttu-id="a235d-183">配列を処理するときに違いが示されます。</span><span class="sxs-lookup"><span data-stu-id="a235d-183">The difference is shown when processing an array.</span></span> <span data-ttu-id="a235d-184">`break` は switch のすべての処理を停止し、`continue` は次の項目に移ります。</span><span class="sxs-lookup"><span data-stu-id="a235d-184">`break` stops all processing in the switch and `continue` moves onto the next item.</span></span>

``` powershell
$Messages = @(
    'Downloading update'
    'Ran into errors downloading file'
    'Error: out of disk space'
    'Sending email'
    '...'
)

switch -Wildcard ($Messages)
{
    'Error*'
    {
        Write-Error -Message $PSItem
        break
    }
    '*Error*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    '*Warning*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    default
    {
        Write-Output $PSItem
    }
}
```

```Output
Downloading update
WARNING: Ran into errors downloading file
write-error -message $PSItem : Error: out of disk space
+ CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
+ FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException
```

<span data-ttu-id="a235d-185">この場合、`Error` で始まる行に到達すると、エラーが表示され、switch が停止します。</span><span class="sxs-lookup"><span data-stu-id="a235d-185">In this case, if we hit any lines that start with `Error` then we get an error and the switch stops.</span></span>
<span data-ttu-id="a235d-186">これは、`break` ステートメントが行う処理です。</span><span class="sxs-lookup"><span data-stu-id="a235d-186">This is what that `break` statement is doing for us.</span></span> <span data-ttu-id="a235d-187">`Error` が文字列の内側または先頭に見つかった場合は、警告として記述します。</span><span class="sxs-lookup"><span data-stu-id="a235d-187">If we find `Error` inside the string and not just at the beginning, we write it as a warning.</span></span> <span data-ttu-id="a235d-188">`Warning` についても同じことを行います。</span><span class="sxs-lookup"><span data-stu-id="a235d-188">We do the same thing for `Warning`.</span></span> <span data-ttu-id="a235d-189">行には `Error` と `Warning` の両方の語が含まれている可能性ありますが、処理に必要なのは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="a235d-189">It's possible that a line could have both the word `Error` and `Warning`, but we only need one to process.</span></span> <span data-ttu-id="a235d-190">これは、`continue` ステートメントが行う処理です。</span><span class="sxs-lookup"><span data-stu-id="a235d-190">This is what the `continue` statement is doing for us.</span></span>

### <a name="break-labels"></a><span data-ttu-id="a235d-191">break ラベル</span><span class="sxs-lookup"><span data-stu-id="a235d-191">Break labels</span></span>

<span data-ttu-id="a235d-192">`foreach` と同様に、`switch` ステートメントでは `break/continue` ラベルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a235d-192">The `switch` statement supports `break/continue` labels just like `foreach`.</span></span>

``` powershell
:filelist foreach($path in $logs)
{
    :logFile switch -Wildcard -File $path
    {
        'Error*'
        {
            Write-Error -Message $PSItem
            break filelist
        }
        'Warning*'
        {
            Write-Error -Message $PSItem
            break logFile
        }
        default
        {
            Write-Output $PSItem
        }
    }
}
```

<span data-ttu-id="a235d-193">私自身は break ラベルを使用することを好みませんが、見たことがない場合はわかりにくいので、説明したいと思います。</span><span class="sxs-lookup"><span data-stu-id="a235d-193">I personally don't like the use of break labels but I wanted to point them out because they're confusing if you've never seen them before.</span></span> <span data-ttu-id="a235d-194">複数の `switch` または `foreach` ステートメントが入れ子になっているときに、最も内側から抜けるだけでなく、さらに外へ抜け出したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="a235d-194">When you have multiple `switch` or `foreach` statements that are nested, you may want to break out of more than the inner most item.</span></span> <span data-ttu-id="a235d-195">`break` のターゲットとなるラベルを `switch` に配置できます。</span><span class="sxs-lookup"><span data-stu-id="a235d-195">You can place a label on a `switch` that can be the target of your `break`.</span></span>

### <a name="enum"></a><span data-ttu-id="a235d-196">列挙型</span><span class="sxs-lookup"><span data-stu-id="a235d-196">Enum</span></span>

<span data-ttu-id="a235d-197">PowerShell 5.0 では列挙型が提供されており、switch で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a235d-197">PowerShell 5.0 gave us enums and we can use them in a switch.</span></span>

``` powershell
enum Context {
    Component
    Role
    Location
}

$item = [Context]::Role

switch ( $item )
{
    Component
    {
        'is a component'
    }
    Role
    {
        'is a role'
    }
    Location
    {
        'is a location'
    }
}
```

```Output
is a role
```

<span data-ttu-id="a235d-198">厳密に型指定された列挙型としてすべてを保持する場合は、かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="a235d-198">If you want to keep everything as strongly typed enums, then you can place them in parentheses.</span></span>

``` powershell
switch ($item )
{
    ([Context]::Component)
    {
        'is a component'
    }
    ([Context]::Role)
    {
        'is a role'
    }
    ([Context]::Location)
    {
        'is a location'
    }
}
```

<span data-ttu-id="a235d-199">ここでは、switch で値 `[Context]::Location` がリテラル文字列として処理されないようにするために、かっこが必要です。</span><span class="sxs-lookup"><span data-stu-id="a235d-199">The parentheses are needed here so that the switch doesn't treat the value `[Context]::Location` as a literal string.</span></span>

### <a name="scriptblock"></a><span data-ttu-id="a235d-200">スクリプト ブロック</span><span class="sxs-lookup"><span data-stu-id="a235d-200">ScriptBlock</span></span>

<span data-ttu-id="a235d-201">必要に応じて、スクリプト ブロックを使用して評価を実行して照合に利用できます。</span><span class="sxs-lookup"><span data-stu-id="a235d-201">We can use a scriptblock to perform the evaluation for a match if needed.</span></span>

``` powershell
$age = 37

switch ( $age )
{
    {$PSItem -le 18}
    {
        'child'
    }
    {$PSItem -gt 18}
    {
        'adult'
    }
}
```

```Output
'adult'
```

<span data-ttu-id="a235d-202">これにより、複雑さが増し、`switch` が読みにくくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a235d-202">This adds complexity and can make your `switch` hard to read.</span></span> <span data-ttu-id="a235d-203">ほとんどの場合、このようなステートメントを使用するところでは、`if` および `elseif` ステートメントを使用する方が適しています。</span><span class="sxs-lookup"><span data-stu-id="a235d-203">In most cases where you would use something like this it would be better to use `if` and `elseif` statements.</span></span> <span data-ttu-id="a235d-204">既に大規模な switch があり、同じ評価ブロックにヒットさせるために 2 つの項目が必要になるような場合は、これを使用することを検討します。</span><span class="sxs-lookup"><span data-stu-id="a235d-204">I would consider using this if I already had a large switch in place and I needed two items to hit the same evaluation block.</span></span>

<span data-ttu-id="a235d-205">読みやすくするために、スクリプト ブロックをかっこ内に配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a235d-205">One thing that I think helps with legibility is to place the scriptblock in parentheses.</span></span>

``` powershell
switch ( $age )
{
    ({$PSItem -le 18})
    {
        'child'
    }
    ({$PSItem -gt 18})
    {
        'adult'
    }
}
```

<span data-ttu-id="a235d-206">それでも同じように実行され、さっと見るときに目に留まりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="a235d-206">It still executes the same way and gives a better visual break when quickly looking at it.</span></span>

### <a name="regex-matches"></a><span data-ttu-id="a235d-207">正規表現の $matches</span><span class="sxs-lookup"><span data-stu-id="a235d-207">Regex $matches</span></span>

<span data-ttu-id="a235d-208">正規表現を見直して、すぐにはわからない点について説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a235d-208">We need to revisit regex to touch on something that isn't immediately obvious.</span></span> <span data-ttu-id="a235d-209">正規表現を使用すると、`$matches` 変数が設定されます。</span><span class="sxs-lookup"><span data-stu-id="a235d-209">The use of regex populates the `$matches` variable.</span></span> <span data-ttu-id="a235d-210">`$matches` の使用については、[正規表現を使用するさまざまな方法][]について説明するときに詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="a235d-210">I do go into the use of `$matches` more when I talk about [The many ways to use regex][].</span></span> <span data-ttu-id="a235d-211">これを名前付き一致と共に使用する簡単な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a235d-211">Here is a quick sample to show it in action with named matches.</span></span>

``` powershell
$message = 'my ssn is 123-23-3456 and credit card: 1234-5678-1234-5678'

switch -regex ($message)
{
    '(?<SSN>\d\d\d-\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a SSN: $($matches.SSN)"
    }
    '(?<CC>\d\d\d\d-\d\d\d\d-\d\d\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a credit card number: $($matches.CC)"
    }
    '(?<Phone>\d\d\d-\d\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a phone number: $($matches.Phone)"
    }
}
```

```Output
WARNING: message may contain a SSN: 123-23-3456
WARNING: message may contain a credit card number: 1234-5678-1234-5678
```

### <a name="null"></a><span data-ttu-id="a235d-212">$null</span><span class="sxs-lookup"><span data-stu-id="a235d-212">$null</span></span>

<span data-ttu-id="a235d-213">既定値である必要のない `$null` 値と照合できます。</span><span class="sxs-lookup"><span data-stu-id="a235d-213">You can match a `$null` value that doesn't have to be the default.</span></span>

``` powershell
$value = $null

switch ( $value )
{
    $null
    {
        'Value is null'
    }
    default
    {
        'value is not null'
    }
}

```Output
Value is null
```

<span data-ttu-id="a235d-214">空の文字列の場合と同様になります。</span><span class="sxs-lookup"><span data-stu-id="a235d-214">Same goes for an empty string.</span></span>

``` powershell
switch ( '' )
{
    ''
    {
        'Value is empty'
    }
    default
    {
        'value is a empty string'
    }
}

```Output
Value is empty
```

### <a name="constant-expression"></a><span data-ttu-id="a235d-215">定数式</span><span class="sxs-lookup"><span data-stu-id="a235d-215">Constant expression</span></span>

<span data-ttu-id="a235d-216">Lee Dailey は、定数 `$true` 式を使用して `[bool]` 項目を評価できると指摘しています。</span><span class="sxs-lookup"><span data-stu-id="a235d-216">Lee Dailey pointed out that we can use a constant `$true` expression to evaluate `[bool]` items.</span></span>
<span data-ttu-id="a235d-217">いくつかのブール値チェックを実行する必要がある場合を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="a235d-217">Imagine if we have several boolean checks that need to happen.</span></span>

``` powershell
$isVisible = $false
$isEnabled = $true
$isSecure = $true

switch ( $true )
{
    $isEnabled
    {
        'Do-Action'
    }
    $isVisible
    {
        'Show-Animation'
    }
    $isSecure
    {
        'Enable-AdminMenu'
    }
}
```

```Output
Do-Action
Enabled-AdminMenu
```

<span data-ttu-id="a235d-218">これは、複数のブール値フィールドのステータスを評価してアクションを実行するためのクリーンな方法です。</span><span class="sxs-lookup"><span data-stu-id="a235d-218">This is a clean way to evaluate and take action on the status of several boolean fields.</span></span> <span data-ttu-id="a235d-219">これのおもしろい点は、まだ評価されていない値のステータスを 1 つの照合で反転させられることです。</span><span class="sxs-lookup"><span data-stu-id="a235d-219">The cool thing about this is that you can have one match flip the status of a value that hasn't been evaluated yet.</span></span>

``` powershell
$isVisible = $false
$isEnabled = $true
$isAdmin = $false

switch ( $true )
{
    $isEnabled
    {
        'Do-Action'
        $isVisible = $true
    }
    $isVisible
    {
        'Show-Animation'
    }
    $isAdmin
    {
        'Enable-AdminMenu'
    }
}
```

```Output
Do-Action
Show-Animation
```

<span data-ttu-id="a235d-220">この例では、`$isEnabled` を `$true` に設定することで、`$isVisible` も `$true` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a235d-220">Setting `$isEnabled` to `$true` in this example makes sure that `$isVisible` is also set to `$true`.</span></span> <span data-ttu-id="a235d-221">その後、`$isVisible` が評価されるときには、そのスクリプト ブロックが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a235d-221">Then when `$isVisible` gets evaluated, its scriptblock is invoked.</span></span> <span data-ttu-id="a235d-222">これは、少し直観に反していますが、このしくみの巧妙な使い方です。</span><span class="sxs-lookup"><span data-stu-id="a235d-222">This is a bit counter-intuitive but is a clever use of the mechanics.</span></span>

### <a name="switch-automatic-variable"></a><span data-ttu-id="a235d-223">$switch 自動変数</span><span class="sxs-lookup"><span data-stu-id="a235d-223">$switch automatic variable</span></span>

<span data-ttu-id="a235d-224">`switch` は、その値を処理するときに、`$switch` という列挙子を作成します。</span><span class="sxs-lookup"><span data-stu-id="a235d-224">When the `switch` is processing its values, it creates an enumerator and calls it `$switch`.</span></span> <span data-ttu-id="a235d-225">これは、PowerShell によって作成される自動変数で、ユーザーが直接操作できます。</span><span class="sxs-lookup"><span data-stu-id="a235d-225">This is an automatic variable created by PowerShell and you can manipulate it directly.</span></span>

```powershell
$a = 1, 2, 3, 4

switch($a) {
    1 { [void]$switch.MoveNext(); $switch.Current }
    3 { [void]$switch.MoveNext(); $switch.Current }
}
```

<span data-ttu-id="a235d-226">これにより、次の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="a235d-226">This gives you the results of:</span></span>

```Output
2
4
```

<span data-ttu-id="a235d-227">列挙子を前方に移動すると、次の項目は `switch` によって処理されませんが、その値に直接アクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="a235d-227">By moving the enumerator forward, the next item doesn't get processed by the `switch` but you can access that value directly.</span></span> <span data-ttu-id="a235d-228">私には狂気に思えます。</span><span class="sxs-lookup"><span data-stu-id="a235d-228">I would call it madness.</span></span>

## <a name="other-patterns"></a><span data-ttu-id="a235d-229">その他のパターン</span><span class="sxs-lookup"><span data-stu-id="a235d-229">Other patterns</span></span>

### <a name="hashtables"></a><span data-ttu-id="a235d-230">ハッシュテーブル</span><span class="sxs-lookup"><span data-stu-id="a235d-230">Hashtables</span></span>

<span data-ttu-id="a235d-231">私の投稿の中で最も人気のあるものの 1 つは、[ハッシュテーブル][]で行ったものです。</span><span class="sxs-lookup"><span data-stu-id="a235d-231">One of my most popular posts is the one I did on [hashtables][].</span></span> <span data-ttu-id="a235d-232">`hashtable` のユース ケースの 1 つはルックアップ テーブルです。</span><span class="sxs-lookup"><span data-stu-id="a235d-232">One of the use cases for a `hashtable` is to be a lookup table.</span></span> <span data-ttu-id="a235d-233">これは、`switch` ステートメントで対処することがよくある一般的なパターンに代わるアプローチです。</span><span class="sxs-lookup"><span data-stu-id="a235d-233">That is an alternate approach to a common pattern that a `switch` statement is often addressing.</span></span>

``` powershell
$day = 3

$lookup = @{
    0 = 'Sunday'
    1 = 'Monday'
    2 = 'Tuesday'
    3 = 'Wednesday'
    4 = 'Thursday'
    5 = 'Friday'
    6 = 'Saturday'
}

$lookup[$day]
```

```Output
Wednesday
```

<span data-ttu-id="a235d-234">`switch` をルックアップとしてのみ使用する場合、私は代わりに `hashtable` を使用することが多いです。</span><span class="sxs-lookup"><span data-stu-id="a235d-234">If I'm only using a `switch` as a lookup, I often use a `hashtable` instead.</span></span>

### <a name="enum"></a><span data-ttu-id="a235d-235">列挙型</span><span class="sxs-lookup"><span data-stu-id="a235d-235">Enum</span></span>

<span data-ttu-id="a235d-236">PowerShell 5.0 では `Enum` が導入されており、この場合にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="a235d-236">PowerShell 5.0 introduced the `Enum` and it's also an option in this case.</span></span>

``` powershell
$day = 3

enum DayOfTheWeek {
    Sunday
    Monday
    Tuesday
    Wednesday
    Thursday
    Friday
    Saturday
}

[DayOfTheWeek]$day
```

```Output
Wednesday
```

<span data-ttu-id="a235d-237">この問題の解決には他にもさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="a235d-237">We could go all day looking at different ways to solve this problem.</span></span> <span data-ttu-id="a235d-238">ここでは、さまざまなオプションがあることを認識していただくことが目的でした。</span><span class="sxs-lookup"><span data-stu-id="a235d-238">I just wanted to make sure you knew you had options.</span></span>

## <a name="final-words"></a><span data-ttu-id="a235d-239">まとめ</span><span class="sxs-lookup"><span data-stu-id="a235d-239">Final words</span></span>

<span data-ttu-id="a235d-240">switch ステートメントは表面上は単純ですが、あまり知られていない高度な機能を持っています。</span><span class="sxs-lookup"><span data-stu-id="a235d-240">The switch statement is simple on the surface but it offers some advanced features that most people don't realize are available.</span></span> <span data-ttu-id="a235d-241">これらの機能を組み合わせることで、強力な機能になります。</span><span class="sxs-lookup"><span data-stu-id="a235d-241">Stringing those features together makes this a powerful feature.</span></span> <span data-ttu-id="a235d-242">これまで気付がなかったことを学んでいただければ幸いです。</span><span class="sxs-lookup"><span data-stu-id="a235d-242">I hope you learned something that you had not realized before.</span></span>

<!-- link references -->
[オリジナル バージョン]: https://powershellexplained.com/2018-01-12-Powershell-switch-statement/
[original version]: https://powershellexplained.com/2018-01-12-Powershell-switch-statement/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[switch]: /powershell/module/microsoft.powershell.core/about/about_switch
[スイッチ パラメーター]: https://www.powershellmagazine.com/2013/12/20/using-powershell-switch-vs-boolean-parameters-in-sma-runbooks/
[switch parameters]: https://www.powershellmagazine.com/2013/12/20/using-powershell-switch-vs-boolean-parameters-in-sma-runbooks/
[正規表現を使用するさまざまな方法]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression
[The many ways to use regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression
[ハッシュテーブル]: everything-about-hashtable.md
[hashtables]: everything-about-hashtable.md
