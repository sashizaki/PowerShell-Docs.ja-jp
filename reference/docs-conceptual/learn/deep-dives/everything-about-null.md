---
title: $null について知りたかったことのすべて
description: PowerShell の $null は、単純なものと見なされがちですが、さまざまなニュアンスの違いがあります。 予期しない null 値が発生した場合に何が起きているのかを理解できるように、$null について詳しく見ていきましょう。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: e0553a5e17450d8044f548792649369e99903850
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149475"
---
# <a name="everything-you-wanted-to-know-about-null"></a><span data-ttu-id="86938-104">$null について知りたかったことのすべて</span><span class="sxs-lookup"><span data-stu-id="86938-104">Everything you wanted to know about $null</span></span>

<span data-ttu-id="86938-105">PowerShell の `$null` は、単純なものと見なされがちですが、さまざまなニュアンスの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="86938-105">The PowerShell `$null` often appears to be simple but it has a lot of nuances.</span></span> <span data-ttu-id="86938-106">予期しない `$null` 値が発生した場合に何が起きているのかを理解できるように、`$null` について詳しく見ていきましょう。</span><span class="sxs-lookup"><span data-stu-id="86938-106">Let's take a close look at `$null` so you know what happens when you unexpectedly run into a `$null` value.</span></span>

> [!NOTE]
> <span data-ttu-id="86938-107">この記事の[オリジナル バージョン][]は、[@KevinMarquette][] 氏のブログ記事です。</span><span class="sxs-lookup"><span data-stu-id="86938-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="86938-108">このコンテンツを共有してくださった Kevin 氏に、PowerShell チームより感謝を申し上げます。</span><span class="sxs-lookup"><span data-stu-id="86938-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="86938-109">[PowerShellExplained.com][] のブログをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="86938-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="what-is-null"></a><span data-ttu-id="86938-110">null 値とは</span><span class="sxs-lookup"><span data-stu-id="86938-110">What is NULL?</span></span>

<span data-ttu-id="86938-111">null 値を、不明な値や空の値を指すものとお考えかもしれません。</span><span class="sxs-lookup"><span data-stu-id="86938-111">You can think of NULL as an unknown or empty value.</span></span> <span data-ttu-id="86938-112">変数は、値やオブジェクトを割り当てるまでは null 値です。</span><span class="sxs-lookup"><span data-stu-id="86938-112">A variable is NULL until you assign a value or an object to it.</span></span> <span data-ttu-id="86938-113">このことを理解しておくことは重要です。なぜなら、コマンドの中には、値が必要で、その値が null 値の場合はエラーを生成するものがあるからです。</span><span class="sxs-lookup"><span data-stu-id="86938-113">This can be important because there are some commands that require a value and generate errors if the value is NULL.</span></span>

### <a name="powershell-null"></a><span data-ttu-id="86938-114">PowerShell の $null</span><span class="sxs-lookup"><span data-stu-id="86938-114">PowerShell $null</span></span>

<span data-ttu-id="86938-115">`$null` は、null 値を表すために PowerShell で使用される自動変数です。</span><span class="sxs-lookup"><span data-stu-id="86938-115">`$null` is an automatic variable in PowerShell used to represent NULL.</span></span> <span data-ttu-id="86938-116">これは、変数に割り当てること、比較で使用すること、コレクション内で null 値のプレース ホルダーとして使用することができます。</span><span class="sxs-lookup"><span data-stu-id="86938-116">You can assign it to variables, use it in comparisons and use it as a place holder for NULL in a collection.</span></span>

<span data-ttu-id="86938-117">PowerShell では、`$null` は、null 値を値として持つオブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="86938-117">PowerShell treats `$null` as an object with a value of NULL.</span></span> <span data-ttu-id="86938-118">これは、他の言語をこれまで使用してきた開発者にとって、想定と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="86938-118">This is different than what you may expect if you come from another language.</span></span>

## <a name="examples-of-null"></a><span data-ttu-id="86938-119">$null の例</span><span class="sxs-lookup"><span data-stu-id="86938-119">Examples of $null</span></span>

<span data-ttu-id="86938-120">初期化していない変数を使用しようとする場合、その値は常に `$null` です。</span><span class="sxs-lookup"><span data-stu-id="86938-120">Anytime you try to use a variable that you have not initialized, the value is `$null`.</span></span> <span data-ttu-id="86938-121">これは、`$null` 値がコードに忍び込む最もよくあるケースの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="86938-121">This is one of the most common ways that `$null` values sneak into your code.</span></span>

```powershell
PS> $null -eq $undefinedVariable
True
```

<span data-ttu-id="86938-122">開発者が変数名を誤って入力してしまうと、PowerShell はそれを別の変数と見なし、その値は `$null` になります。</span><span class="sxs-lookup"><span data-stu-id="86938-122">If you happen to mistype a variable name then PowerShell sees it as a different variable and the value is `$null`.</span></span>

<span data-ttu-id="86938-123">`$null` 値が発生するもう 1 つのケースは、結果を何も返さない別のコマンドに由来している場合です。</span><span class="sxs-lookup"><span data-stu-id="86938-123">The other way you find `$null` values is when they come from other commands that don't give you any results.</span></span>

```powershell
PS> function Get-Nothing {}
PS> $value = Get-Nothing
PS> $null -eq $value
True
```

## <a name="impact-of-null"></a><span data-ttu-id="86938-124">$null の影響</span><span class="sxs-lookup"><span data-stu-id="86938-124">Impact of $null</span></span>

<span data-ttu-id="86938-125">`$null` は、どこで発生するかによって、コードに異なる影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="86938-125">`$null` values impact your code differently depending on where they show up.</span></span>

### <a name="in-strings"></a><span data-ttu-id="86938-126">文字列の場合</span><span class="sxs-lookup"><span data-stu-id="86938-126">In strings</span></span>

<span data-ttu-id="86938-127">`$null` を文字列で使用する場合、これは空白の値 (または空の文字列) です。</span><span class="sxs-lookup"><span data-stu-id="86938-127">If you use `$null` in a string, then it's a blank value (or empty string).</span></span>

```powershell
PS> $value = $null
PS> Write-Output "The value is $value"
The value is
```

<span data-ttu-id="86938-128">これは、ログ メッセージ内で変数を使用する場合に、その変数を角かっこで囲むことを私が好む理由の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="86938-128">This is one of the reasons that I like to place brackets around variables when using them in log messages.</span></span> <span data-ttu-id="86938-129">さらに重要なのは、変数の値が文字列の末尾に来る場合に、変数の値の両端がはっきりわかるようにできることです。</span><span class="sxs-lookup"><span data-stu-id="86938-129">It's even more important to identify the edges of your variable values when the value is at the end of the string.</span></span>

```powershell
PS> $value = $null
PS> Write-Output "The value is [$value]"
The value is []
```

<span data-ttu-id="86938-130">こうすることにより、空の文字列と `$null` の値を見つけやすくなります。</span><span class="sxs-lookup"><span data-stu-id="86938-130">This makes empty strings and `$null` values easy to spot.</span></span>

### <a name="in-numeric-equation"></a><span data-ttu-id="86938-131">数値式の場合</span><span class="sxs-lookup"><span data-stu-id="86938-131">In numeric equation</span></span>

<span data-ttu-id="86938-132">`$null` 値が数値式で使用される場合、エラーにならない限り、その結果は無効になります。</span><span class="sxs-lookup"><span data-stu-id="86938-132">When a `$null` value is used in a numeric equation then your results are invalid if they don't give an error.</span></span> <span data-ttu-id="86938-133">`$null` は `0` と評価される場合もあれば、それにより結果全体が `$null` になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="86938-133">Sometimes the `$null` evaluates to `0` and other times it makes the whole result `$null`.</span></span>
<span data-ttu-id="86938-134">値の順序によって、結果が 0 または `$null` になる乗算の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="86938-134">Here is an example with multiplication that gives 0 or `$null` depending on the order of the values.</span></span>

```powershell
PS> $null * 5
PS> $null -eq ( $null * 5 )
True

PS> 5 * $null
0
PS> $null -eq ( 5 * $null )
False
```

### <a name="in-place-of-a-collection"></a><span data-ttu-id="86938-135">コレクション内の場合</span><span class="sxs-lookup"><span data-stu-id="86938-135">In place of a collection</span></span>

<span data-ttu-id="86938-136">コレクションを使用すると、インデックスを使って値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="86938-136">A collection allow you use an index to access values.</span></span> <span data-ttu-id="86938-137">実際には `null` であるコレクションにインデックスを付けようとすると、エラー `Cannot index into a null array` が返されます。</span><span class="sxs-lookup"><span data-stu-id="86938-137">If you try to index into a collection that is actually `null`, you get this error: `Cannot index into a null array`.</span></span>

```powershell
PS> $value = $null
PS> $value[10]
Cannot index into a null array.
At line:1 char:1
+ $value[10]
+ ~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [], RuntimeException
    + FullyQualifiedErrorId : NullArray
```

<span data-ttu-id="86938-138">コレクションは存在するものの、そのコレクションに含まれていない要素にアクセスしようとすると、結果として `$null` が返されます。</span><span class="sxs-lookup"><span data-stu-id="86938-138">If you have a collection but try to access an element that is not in the collection, you get a `$null` result.</span></span>

```powershell
$array = @( 'one','two','three' )
$null -eq $array[100]
True
```

### <a name="in-place-of-an-object"></a><span data-ttu-id="86938-139">オブジェクト内の場合</span><span class="sxs-lookup"><span data-stu-id="86938-139">In place of an object</span></span>

<span data-ttu-id="86938-140">指定されたプロパティを持たないオブジェクトのプロパティやサブプロパティにアクセスしようとすると、未定義の変数の場合と同様に `$null` 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="86938-140">If you try to access a property or sub property of an object that doesn't have the specified property, you get a `$null` value like you would for an undefined variable.</span></span> <span data-ttu-id="86938-141">この場合、その変数が `$null` であるか実際のオブジェクトであるかは関係ありません。</span><span class="sxs-lookup"><span data-stu-id="86938-141">It doesn't matter if the variable is `$null` or an actual object in this case.</span></span>

```powershell
PS> $null -eq $undefined.some.fake.property
True

PS> $date = Get-Date
PS> $null -eq $date.some.fake.property
True
```

### <a name="method-on-a-null-valued-expression"></a><span data-ttu-id="86938-142">null 値式のメソッド</span><span class="sxs-lookup"><span data-stu-id="86938-142">Method on a null-valued expression</span></span>

<span data-ttu-id="86938-143">`$null` オブジェクトでメソッドを呼び出すと、`RuntimeException` がスローされます。</span><span class="sxs-lookup"><span data-stu-id="86938-143">Calling a method on a `$null` object throws a `RuntimeException`.</span></span>

```powershell
PS> $value = $null
PS> $value.toString()
You cannot call a method on a null-valued expression.
At line:1 char:1
+ $value.tostring()
+ ~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [], RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
```

<span data-ttu-id="86938-144">`You cannot call a method on a null-valued expression` が表示された場合、最初に `$null` がないかどうかメソッドを確認するのではなく、まず、変数でメソッドを呼び出している場所を探します。</span><span class="sxs-lookup"><span data-stu-id="86938-144">Whenever I see the phrase `You cannot call a method on a null-valued expression` then the first thing I look for are places where I am calling a method on a variable without first checking it for `$null`.</span></span>

## <a name="checking-for-null"></a><span data-ttu-id="86938-145">$null の確認</span><span class="sxs-lookup"><span data-stu-id="86938-145">Checking for $null</span></span>

<span data-ttu-id="86938-146">これまでの例で、`$null` を確認するときに、`$null` が常に左側に置かれていることにお気付きになったかもしれません。</span><span class="sxs-lookup"><span data-stu-id="86938-146">You may have noticed that I always place the `$null` on the left when checking for `$null` in my examples.</span></span> <span data-ttu-id="86938-147">これは意図的なもので、PowerShell ではベスト プラクティスとして受け入れられる方法です。</span><span class="sxs-lookup"><span data-stu-id="86938-147">This is intentional and accepted as a PowerShell best practice.</span></span> <span data-ttu-id="86938-148">右側に置くと期待どおりの結果が得られないシナリオがあるからです。</span><span class="sxs-lookup"><span data-stu-id="86938-148">There are some scenarios where placing it on the right doesn't give you the expected result.</span></span>

<span data-ttu-id="86938-149">次の例を見て、結果を予想してみてください。</span><span class="sxs-lookup"><span data-stu-id="86938-149">Look at this next example and try to predict the results:</span></span>

```powershell
if ( $value -eq $null )
{
    'The array is $null'
}
if ( $value -ne $null )
{
    'The array is not $null'
}
```

<span data-ttu-id="86938-150">`$value` を定義しない場合、最初のものは `$true` と評価され、`The array is $null` というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="86938-150">If I do not define `$value`, the first one evaluates to `$true` and our message is `The array is $null`.</span></span> <span data-ttu-id="86938-151">落とし穴になるのは、どちらも `$false` となるような `$value` を作成できる点です。</span><span class="sxs-lookup"><span data-stu-id="86938-151">The trap here is that it's possible to create a `$value` that allows both of them to be `$false`</span></span>

```powershell
$value = @( $null )
```

<span data-ttu-id="86938-152">この場合、`$value` は `$null` を含む配列です。</span><span class="sxs-lookup"><span data-stu-id="86938-152">In this case, the `$value` is an array that contains a `$null`.</span></span> <span data-ttu-id="86938-153">`-eq` は、配列内のすべての値をチェックし、一致する `$null` を返します。</span><span class="sxs-lookup"><span data-stu-id="86938-153">The `-eq` checks every value in the array and returns the `$null` that is matched.</span></span> <span data-ttu-id="86938-154">これは、`$false` と評価されます。</span><span class="sxs-lookup"><span data-stu-id="86938-154">This evaluates to `$false`.</span></span> <span data-ttu-id="86938-155">`-ne` は、`$null` と一致しないものすべてを返します。この例の場合、結果はありません (こちらも `$false` と評価されます)。</span><span class="sxs-lookup"><span data-stu-id="86938-155">The `-ne` returns everything that doesn't match `$null` and in this case there are no results (This also evaluates to `$false`).</span></span> <span data-ttu-id="86938-156">一方は `$true` になりそうに思えますが、どちらもそうはならないのです。</span><span class="sxs-lookup"><span data-stu-id="86938-156">Neither one is `$true` even though it looks like one of them should be.</span></span>

<span data-ttu-id="86938-157">どちらも `$false` と評価される値を作成できるだけでなく、どちらも `$true` と評価される値を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="86938-157">Not only can we create a value that makes both of them evaluate to `$false`, it's possible to create a value where they both evaluate to `$true`.</span></span> <span data-ttu-id="86938-158">Mathias Jessen (@IISResetMe) 氏が、このシナリオを詳しく説明する[優れた記事][]を投稿しています。</span><span class="sxs-lookup"><span data-stu-id="86938-158">Mathias Jessen (@IISResetMe) has a [good post][] that dives into that scenario.</span></span>

### <a name="psscriptanalyzer-and-vscode"></a><span data-ttu-id="86938-159">PSScriptAnalyzer と VSCode</span><span class="sxs-lookup"><span data-stu-id="86938-159">PSScriptAnalyzer and VSCode</span></span>

<span data-ttu-id="86938-160">[PSScriptAnalyzer][] モジュールには、この問題を確認する、`PSPossibleIncorrectComparisonWithNull` という名前のルールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="86938-160">The [PSScriptAnalyzer][] module has a rule that checks for this issue called `PSPossibleIncorrectComparisonWithNull`.</span></span>

```powershell
PS> Invoke-ScriptAnalyzer ./myscript.ps1

RuleName                              Message
--------                              -------
PSPossibleIncorrectComparisonWithNull $null should be on the left side of equality comparisons.
```

<span data-ttu-id="86938-161">VS Code でも PSScriptAnalyser ルールが使用されるので、それによってもこれがスクリプト内の問題として強調表示または識別されます。</span><span class="sxs-lookup"><span data-stu-id="86938-161">Because VS Code uses the PSScriptAnalyser rules too, it also highlights or identifies this as a problem in your script.</span></span>

### <a name="simple-if-check"></a><span data-ttu-id="86938-162">単純な if によるチェック</span><span class="sxs-lookup"><span data-stu-id="86938-162">Simple if check</span></span>

<span data-ttu-id="86938-163">$null 以外の値を確認する一般的な方法としては、比較を含まない単純な `if()` ステートメントを使用する方法があります。</span><span class="sxs-lookup"><span data-stu-id="86938-163">A common way that people check for a non-$null value is to use a simple `if()` statement without the comparison.</span></span>

```powershell
if ( $value )
{
    Do-Something
}
```

<span data-ttu-id="86938-164">値が `$null` の場合、これは `$false` と評価されます。</span><span class="sxs-lookup"><span data-stu-id="86938-164">If the value is `$null`, this evaluates to `$false`.</span></span> <span data-ttu-id="86938-165">簡単そうに見えますが、このコードの実際の評価内容と、このコードが評価していると思っているものとが全く同じであるかに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86938-165">This is easy to read, but be careful that it's looking for exactly what you're expecting it to look for.</span></span> <span data-ttu-id="86938-166">このコード行は、次のように見えます。</span><span class="sxs-lookup"><span data-stu-id="86938-166">I read that line of code as:</span></span>

> <span data-ttu-id="86938-167">`$value` に値があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="86938-167">If `$value` has a value.</span></span>

<span data-ttu-id="86938-168">しかし、それだけではありません。</span><span class="sxs-lookup"><span data-stu-id="86938-168">But that's not the whole story.</span></span> <span data-ttu-id="86938-169">この行が実際に意味しているのは、次のことです。</span><span class="sxs-lookup"><span data-stu-id="86938-169">That line is actually saying:</span></span>

> <span data-ttu-id="86938-170">`$value` が、`$null` でも `0` でも `$false` でも `empty string` でもないかどうか。</span><span class="sxs-lookup"><span data-stu-id="86938-170">If `$value` is not `$null` or `0` or `$false` or an `empty string`</span></span>

<span data-ttu-id="86938-171">このステートメントをより完全に記述したサンプルを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="86938-171">Here is a more complete sample of that statement.</span></span>

```powershell
if ( $null -ne $value -and
        $value -ne 0 -and
        $value -ne '' -and
        $value -ne $false )
{
    Do-Something
}
```

<span data-ttu-id="86938-172">これらの他の値も `$false` としてカウントされるのであって、変数に値があることをただチェックしているわけではないことを意識している限り、基本的な `if` チェックを使用しても全く問題ありません。</span><span class="sxs-lookup"><span data-stu-id="86938-172">It's perfectly OK to use a basic `if` check as long as you remember those other values count as `$false` and not just that a variable has a value.</span></span>

<span data-ttu-id="86938-173">数日前にコードをリファクタリングしていたとき、私はこの問題に出くわしました。</span><span class="sxs-lookup"><span data-stu-id="86938-173">I ran into this issue when refactoring some code a few days ago.</span></span> <span data-ttu-id="86938-174">そのコードには、次のような基本的なプロパティ チェックが含まれていました。</span><span class="sxs-lookup"><span data-stu-id="86938-174">It had a basic property check like this.</span></span>

```powershell
if ( $object.property )
{
    $object.property = $value
}
```

<span data-ttu-id="86938-175">値が存在していた場合にのみ、オブジェクト プロパティに値を割り当てるのが目的でした。</span><span class="sxs-lookup"><span data-stu-id="86938-175">I wanted to assign a value to the object property only if it existed.</span></span> <span data-ttu-id="86938-176">ほとんどの場合、基になるオブジェクトには `if` ステートメントで `$true` と評価される値がありました。</span><span class="sxs-lookup"><span data-stu-id="86938-176">In most cases, the original object had a value that would evaluate to `$true` in the `if` statement.</span></span> <span data-ttu-id="86938-177">しかし、値が設定されていないものがあるという問題が発生していました。</span><span class="sxs-lookup"><span data-stu-id="86938-177">But I ran into an issue where the value was occasionally not getting set.</span></span> <span data-ttu-id="86938-178">コードをデバッグしてみると、そのオブジェクトにプロパティはあったのですが、そのプロパティは空の文字列値だったのです。</span><span class="sxs-lookup"><span data-stu-id="86938-178">I debugged the code and found that the object had the property but it was a blank string value.</span></span> <span data-ttu-id="86938-179">そのため、上の例のロジックでは値が更新されませんでした。</span><span class="sxs-lookup"><span data-stu-id="86938-179">This prevented it from ever getting updated with the previous logic.</span></span> <span data-ttu-id="86938-180">そこで、適切な `$null` チェックを追加したところ、問題はすべて解決しました。</span><span class="sxs-lookup"><span data-stu-id="86938-180">So I added a proper `$null` check and everything worked.</span></span>

```powershell
if ( $null -ne $object.property )
{
    $object.property = $value
}
```

<span data-ttu-id="86938-181">このような細かなバグは非常に見つけにくいので、`$null` の値は積極的にチェックするようにしています。</span><span class="sxs-lookup"><span data-stu-id="86938-181">It's little bugs like these that are hard to spot and make me aggressively check values for `$null`.</span></span>

## <a name="nullcount"></a><span data-ttu-id="86938-182">$null.Count</span><span class="sxs-lookup"><span data-stu-id="86938-182">$null.Count</span></span>

<span data-ttu-id="86938-183">`$null` 値のプロパティにアクセスしようとする場合、そのプロパティも `$null` です。</span><span class="sxs-lookup"><span data-stu-id="86938-183">If you try to access a property on a `$null` value, that the property is also `$null`.</span></span> <span data-ttu-id="86938-184">`count` プロパティは、このルールの例外です。</span><span class="sxs-lookup"><span data-stu-id="86938-184">The `count` property is the exception to this rule.</span></span>

```powershell
PS> $value = $null
PS> $value.count
0
```

<span data-ttu-id="86938-185">`$null` 値がある場合、その `count` は `0` になります。</span><span class="sxs-lookup"><span data-stu-id="86938-185">When you have a `$null` value, then the `count` is `0`.</span></span> <span data-ttu-id="86938-186">この特別なプロパティは、PowerShell によって追加されます。</span><span class="sxs-lookup"><span data-stu-id="86938-186">This special property is added by PowerShell.</span></span>

### <a name="pscustomobject-count"></a><span data-ttu-id="86938-187">[PSCustomObject] Count</span><span class="sxs-lookup"><span data-stu-id="86938-187">[PSCustomObject] Count</span></span>

<span data-ttu-id="86938-188">PowerShell のほとんどすべてのオブジェクトに、count プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="86938-188">Almost all objects in PowerShell have that count property.</span></span> <span data-ttu-id="86938-189">重要な例外の 1 つは、Windows PowerShell 5.1 の `[PSCustomObject]` です (PowerShell 6.0 では修正済み)。</span><span class="sxs-lookup"><span data-stu-id="86938-189">One important exception is the `[PSCustomObject]` in Windows PowerShell 5.1 (This is fixed in PowerShell 6.0).</span></span> <span data-ttu-id="86938-190">これには count プロパティがないため、使用しようとすると `$null` 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="86938-190">It doesn't have a count property so you get a `$null` value if you try to use it.</span></span> <span data-ttu-id="86938-191">`$null` チェックの代わりに `.Count` を使用しようとすることがないようにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="86938-191">I call this out here so that you don't try to use `.Count` instead of a `$null` check.</span></span>

<span data-ttu-id="86938-192">このサンプルを Windows PowerShell 5.1 と PowerShell 6.0 とで実行すると、異なる結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="86938-192">Running this example on Windows PowerShell 5.1 and PowerShell 6.0 gives you different results.</span></span>

```powershell
$value = [PSCustomObject]@{Name='MyObject'}
if ( $value.count -eq 1 )
{
    "We have a value"
}
```

## <a name="empty-null"></a><span data-ttu-id="86938-193">空の null 値</span><span class="sxs-lookup"><span data-stu-id="86938-193">Empty null</span></span>

<span data-ttu-id="86938-194">他と異なる動作をする、特殊な `$null` が 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="86938-194">There is one special type of `$null` that acts differently than the others.</span></span> <span data-ttu-id="86938-195">これを、空の `$null` と呼ぶことにします (実際には [System.Management.Automation.Internal.AutomationNull][] です)。</span><span class="sxs-lookup"><span data-stu-id="86938-195">I am going to call it the empty `$null` but it's really a [System.Management.Automation.Internal.AutomationNull][].</span></span> <span data-ttu-id="86938-196">この空の `$null` は、何も返さない (無効な結果を返す) 関数またはスクリプト ブロックの結果として返されるものです。</span><span class="sxs-lookup"><span data-stu-id="86938-196">This empty `$null` is the one you get as the result of a function or script block that returns nothing (a void result).</span></span>

```powershell
PS> function Get-Nothing {}
PS> $nothing = Get-Nothing
PS> $null -eq $nothing
True
```

<span data-ttu-id="86938-197">これを `$null` と比較すると、`$null` 値が得られます。</span><span class="sxs-lookup"><span data-stu-id="86938-197">If you compare it with `$null`, you get a `$null` value.</span></span> <span data-ttu-id="86938-198">値が必要な評価に使用される場合、その値は常に `$null` になります。</span><span class="sxs-lookup"><span data-stu-id="86938-198">When used in an evaluation where a value is required, the value is always `$null`.</span></span> <span data-ttu-id="86938-199">しかし、これを配列内に配置すると、空の配列と同じように扱われます。</span><span class="sxs-lookup"><span data-stu-id="86938-199">But if you place it inside an array, it's treated the same as an empty array.</span></span>

```powershell
PS> $containempty = @( @() )
PS> $containnothing = @($nothing)
PS> $containnull = @($null)

PS> $containempty.count
0
PS> $containnothing.count
0
PS> $containnull.count
1
```

<span data-ttu-id="86938-200">`$null` 値を 1 つ含む配列を作成できます。その `count` は `1` です。</span><span class="sxs-lookup"><span data-stu-id="86938-200">You can have an array that contains one `$null` value and its `count` is `1`.</span></span> <span data-ttu-id="86938-201">しかし、配列内に空の結果を配置すると、それは項目としてカウントされません。</span><span class="sxs-lookup"><span data-stu-id="86938-201">But if you place an empty result inside an array then it's not counted as an item.</span></span> <span data-ttu-id="86938-202">そのカウントは `0` です。</span><span class="sxs-lookup"><span data-stu-id="86938-202">The count is `0`.</span></span>

<span data-ttu-id="86938-203">空の `$null` をコレクションのように扱うと、それは空になります。</span><span class="sxs-lookup"><span data-stu-id="86938-203">If you treat the empty `$null` like a collection, then it's empty.</span></span>

### <a name="pipeline"></a><span data-ttu-id="86938-204">パイプライン</span><span class="sxs-lookup"><span data-stu-id="86938-204">Pipeline</span></span>

<span data-ttu-id="86938-205">この違いが最もよく見られるのは、パイプラインを使用する場合です。</span><span class="sxs-lookup"><span data-stu-id="86938-205">The primary place you see the difference is when using the pipeline.</span></span> <span data-ttu-id="86938-206">`$null` 値はパイプを使用して渡し、空の `$null` 値は渡さないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="86938-206">You can pipe a `$null` value but not an empty `$null` value.</span></span>

```powershell
PS> $null | ForEach-Object{ Write-Output 'NULL Value' }
'NULL Value'
PS> $nothing | ForEach-Object{ Write-Output 'No Value' }
```

<span data-ttu-id="86938-207">コードによっては、ロジック内の `$null` を説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86938-207">Depending on your code, you should account for the `$null` in your logic.</span></span>

<span data-ttu-id="86938-208">まず `$null` をチェックするか、</span><span class="sxs-lookup"><span data-stu-id="86938-208">Either check for `$null` first</span></span>

- <span data-ttu-id="86938-209">パイプラインで null 値をフィルター処理して除外します (`... | Where {$null -ne $_} | ...`)</span><span class="sxs-lookup"><span data-stu-id="86938-209">Filter out null on the pipeline (`... | Where {$null -ne $_} | ...`)</span></span>
- <span data-ttu-id="86938-210">パイプライン関数で処理します</span><span class="sxs-lookup"><span data-stu-id="86938-210">Handle it in the pipeline function</span></span>

## <a name="foreach"></a><span data-ttu-id="86938-211">foreach</span><span class="sxs-lookup"><span data-stu-id="86938-211">foreach</span></span>

<span data-ttu-id="86938-212">`foreach` で私が気に入っている特徴の 1 つは、それが `$null` コレクションを列挙しないことです。</span><span class="sxs-lookup"><span data-stu-id="86938-212">One of my favorite features of `foreach` is that it doesn't enumerate over a `$null` collection.</span></span>

```powershell
foreach ( $node in $null )
{
    #skipped
}
```

<span data-ttu-id="86938-213">そのため、コレクションを列挙する前にそのコレクションに対して `$null` チェックをする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="86938-213">This saves me from having to `$null` check the collection before I enumerate it.</span></span> <span data-ttu-id="86938-214">`$null` 値のコレクションがある場合でも、`$node` はやはり `$null` になります。</span><span class="sxs-lookup"><span data-stu-id="86938-214">If you have a collection of `$null` values, the `$node` can still be `$null`.</span></span>

<span data-ttu-id="86938-215">foreach がこのように動作するようになったのは、PowerShell 3.0 からです。</span><span class="sxs-lookup"><span data-stu-id="86938-215">The foreach started working this way with PowerShell 3.0.</span></span> <span data-ttu-id="86938-216">これより古いバージョンを使用している場合は、動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="86938-216">If you happen to be on an older version, then this is not the case.</span></span> <span data-ttu-id="86938-217">これは、2.0 との互換性のためにコードをバックポートする際に意識する必要のある、重要な変更点の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="86938-217">This is one of the important changes to be aware of when back-porting code for 2.0 compatibility.</span></span>

## <a name="value-types"></a><span data-ttu-id="86938-218">値の型</span><span class="sxs-lookup"><span data-stu-id="86938-218">Value types</span></span>

<span data-ttu-id="86938-219">技術的には、参照型のみが `$null` になり得ます。</span><span class="sxs-lookup"><span data-stu-id="86938-219">Technically, only reference types can be `$null`.</span></span> <span data-ttu-id="86938-220">しかし、PowerShell は非常に寛容で、変数がどのような型であっても許容します。</span><span class="sxs-lookup"><span data-stu-id="86938-220">But PowerShell is very generous and allows for variables to be any type.</span></span> <span data-ttu-id="86938-221">値の型を厳密に型指定する場合は、`$null` にはできません。</span><span class="sxs-lookup"><span data-stu-id="86938-221">If you decide to strongly type a value type, it cannot be `$null`.</span></span>
<span data-ttu-id="86938-222">PowerShell では、多くの型で `$null` を既定値に変換します。</span><span class="sxs-lookup"><span data-stu-id="86938-222">PowerShell converts `$null` to a default value for many types.</span></span>

```powershell
PS> [int]$number = $null
PS> $number
0

PS> [bool]$boolean = $null
PS> $boolean
False

PS> [string]$string = $null
PS> $string -eq ''
True
```

<span data-ttu-id="86938-223">一部、`$null` から有効に変換されない型も存在します。</span><span class="sxs-lookup"><span data-stu-id="86938-223">There are some types that do not have a valid conversion from `$null`.</span></span> <span data-ttu-id="86938-224">このような型では、`Cannot convert null to type` エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="86938-224">These types generate a `Cannot convert null to type` error.</span></span>

```powershell
PS> [datetime]$date = $null
Cannot convert null to type "System.DateTime".
At line:1 char:1
+ [datetime]$date = $null
+ ~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : MetadataError: (:) [], ArgumentTransformationMetadataException
    + FullyQualifiedErrorId : RuntimeException
```

### <a name="function-parameters"></a><span data-ttu-id="86938-225">関数のパラメーター</span><span class="sxs-lookup"><span data-stu-id="86938-225">Function parameters</span></span>

<span data-ttu-id="86938-226">関数パラメーターで厳密に型指定された値を使用するのは、非常に一般的な方法です。</span><span class="sxs-lookup"><span data-stu-id="86938-226">Using a strongly typed values in function parameters is very common.</span></span> <span data-ttu-id="86938-227">スクリプトの他の変数の型を定義しようとは考えないとしても、パラメーターの型は定義することが習慣になっているものです。</span><span class="sxs-lookup"><span data-stu-id="86938-227">We generally learn to define the types of our parameters even if we tend not to define the types of other variables in our scripts.</span></span> <span data-ttu-id="86938-228">関数の中で厳密に型指定された変数を既に使用していても、それに気づいていないことさえあり得ます。</span><span class="sxs-lookup"><span data-stu-id="86938-228">You may already have some strongly typed variables in your functions and not even realize it.</span></span>

```powershell
function Do-Something
{
    param(
        [String] $Value
    )
}
```

<span data-ttu-id="86938-229">パラメーターの型を `string` として設定した時点で、その値は `$null` にはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="86938-229">As soon as you set the type of the parameter as a `string`, the value can never be `$null`.</span></span> <span data-ttu-id="86938-230">値が `$null` かどうかをチェックして、ユーザーが値を指定したかどうかを確認するのは一般的な方法です。</span><span class="sxs-lookup"><span data-stu-id="86938-230">It's common to check if a value is `$null` to see if the user provided a value or not.</span></span>

```powershell
if ( $null -ne $Value ){...}
```

<span data-ttu-id="86938-231">値が指定されない場合、`$Value` は空の文字列 `''` になります。</span><span class="sxs-lookup"><span data-stu-id="86938-231">`$Value` is an empty string `''` when no value is provided.</span></span> <span data-ttu-id="86938-232">代わりに、自動変数 `$PSBoundParameters.Value` を使用しましょう。</span><span class="sxs-lookup"><span data-stu-id="86938-232">Use the automatic variable `$PSBoundParameters.Value` instead.</span></span>

```powershell
if ( $null -ne $PSBoundParameters.Value ){...}
```

<span data-ttu-id="86938-233">`$PSBoundParameters` には、その関数が呼び出された時点で指定済みのパラメーターのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="86938-233">`$PSBoundParameters` only contains the parameters that were specified when the function was called.</span></span>
<span data-ttu-id="86938-234">`ContainsKey` メソッドを使用してプロパティを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="86938-234">You can also use the `ContainsKey` method to check for the property.</span></span>

```powershell
if ( $PSBoundParameters.ContainsKey('Value') ){...}
```

### <a name="isnotnullorempty"></a><span data-ttu-id="86938-235">IsNotNullOrEmpty</span><span class="sxs-lookup"><span data-stu-id="86938-235">IsNotNullOrEmpty</span></span>

<span data-ttu-id="86938-236">値が文字列の場合は、静的な文字列関数を使用して、値が `$null` であるか空の文字列であるかを同時に確認できます。</span><span class="sxs-lookup"><span data-stu-id="86938-236">If the value is a string, you can use a static string function to check if the value is `$null` or an empty string at the same time.</span></span>

```powershell
if ( -not [string]::IsNullOrEmpty( $value ) ){...}
```

<span data-ttu-id="86938-237">個人的には、その値の型が文字列でなければならないことがわかっている場合に、これをよく使用しています。</span><span class="sxs-lookup"><span data-stu-id="86938-237">I find myself using this often when I know the value type should be a string.</span></span>

## <a name="when-i-null-check"></a><span data-ttu-id="86938-238">$null チェックをする場面</span><span class="sxs-lookup"><span data-stu-id="86938-238">When I $null check</span></span>

<span data-ttu-id="86938-239">私は防御的なスクリプト作成者です。</span><span class="sxs-lookup"><span data-stu-id="86938-239">I am a defensive scripter.</span></span> <span data-ttu-id="86938-240">関数を呼び出して変数に割り当てるときは、それが `$null` でないかをいつも確認します。</span><span class="sxs-lookup"><span data-stu-id="86938-240">Anytime I call a function and assign it to a variable, I check it for `$null`.</span></span>

```powershell
$userList = Get-ADUser kevmar
if ($null -ne $userList){...}
```

<span data-ttu-id="86938-241">`try/catch` を使用するより、`if` や `foreach` を使用する方が断然好きです。</span><span class="sxs-lookup"><span data-stu-id="86938-241">I much prefer using `if` or `foreach` over using `try/catch`.</span></span> <span data-ttu-id="86938-242">もちろん、`try/catch` もかなり使用します。</span><span class="sxs-lookup"><span data-stu-id="86938-242">Don't get me wrong, I still use `try/catch` a lot.</span></span> <span data-ttu-id="86938-243">それでも、エラー条件をテストしたり、結果の空のセットをテストしたりできるのであれば、例外処理で真の例外を処理することを許容できます。</span><span class="sxs-lookup"><span data-stu-id="86938-243">But if I can test for an error condition or an empty set of results, I can allow my exception handling be for true exceptions.</span></span>

<span data-ttu-id="86938-244">値にインデックスを付けたり、オブジェクトでメソッドを呼び出したりする前にも、`$null` を確認するようにしています。</span><span class="sxs-lookup"><span data-stu-id="86938-244">I also tend to check for `$null` before I index into a value or call methods on an object.</span></span> <span data-ttu-id="86938-245">これらの 2 つのアクションは、`$null` オブジェクトの場合は失敗します。そのため、まずそれらを検証するのは重要なことだと考えています。</span><span class="sxs-lookup"><span data-stu-id="86938-245">These two actions fail for a `$null` object so I find it important to validate them first.</span></span> <span data-ttu-id="86938-246">これらのシナリオについては、この記事で既に説明しました。</span><span class="sxs-lookup"><span data-stu-id="86938-246">I already covered those scenarios earlier in this post.</span></span>

### <a name="no-results-scenario"></a><span data-ttu-id="86938-247">結果が存在しないシナリオ</span><span class="sxs-lookup"><span data-stu-id="86938-247">No results scenario</span></span>

<span data-ttu-id="86938-248">関数やコマンドが異なると、結果が存在しないシナリオの処理方法が異なることを理解していることは重要です。</span><span class="sxs-lookup"><span data-stu-id="86938-248">It's important to know that different functions and commands handle the no results scenario differently.</span></span> <span data-ttu-id="86938-249">多くの PowerShell コマンドでは、空の `$null` とエラーがエラー ストリームで返されます。</span><span class="sxs-lookup"><span data-stu-id="86938-249">Many PowerShell commands return the empty `$null` and an error in the error stream.</span></span> <span data-ttu-id="86938-250">しかし、例外をスローするものや、ステータス オブジェクトを返すものもあります。</span><span class="sxs-lookup"><span data-stu-id="86938-250">But others throw exceptions or give you a status object.</span></span> <span data-ttu-id="86938-251">使用するコマンドが、結果が存在しないシナリオやエラー シナリオをどのように処理するかを理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="86938-251">It's still up to you to know how the commands you use deal with the no results and error scenarios.</span></span>

## <a name="initializing-to-null"></a><span data-ttu-id="86938-252">$null への初期化</span><span class="sxs-lookup"><span data-stu-id="86938-252">Initializing to $null</span></span>

<span data-ttu-id="86938-253">私は、変数を使用する前に、使用する変数すべてを初期化することを習慣にしています。</span><span class="sxs-lookup"><span data-stu-id="86938-253">One habit that I have picked up is initializing all my variables before I use them.</span></span> <span data-ttu-id="86938-254">これは、他の言語でも行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="86938-254">You are required to do this in other languages.</span></span> <span data-ttu-id="86938-255">関数の先頭か、foreach ループに入った時点で、使用する予定のすべての値を定義するようにします。</span><span class="sxs-lookup"><span data-stu-id="86938-255">At the top of my function or as I enter a foreach loop, I define all the values that I'm using.</span></span>

<span data-ttu-id="86938-256">注意してご覧いただきたいシナリオを次に示します。</span><span class="sxs-lookup"><span data-stu-id="86938-256">Here is a scenario that I want you to take a close look at.</span></span> <span data-ttu-id="86938-257">これは、私が以前に見つけ出す必要があったバグの例です。</span><span class="sxs-lookup"><span data-stu-id="86938-257">It's an example of a bug I had to chase down before.</span></span>

```powershell
function Do-Something
{
    foreach ( $node in 1..6 )
    {
        try
        {
            $result = Get-Something -ID $node
        }
        catch
        {
            Write-Verbose "[$result] not valid"
        }

        if ( $null -ne $result )
        {
            Update-Something $result
        }
    }
}
```

<span data-ttu-id="86938-258">ここでは、`Get-Something` が結果か空の `$null` のどちらかを返すものと想定されています。</span><span class="sxs-lookup"><span data-stu-id="86938-258">The expectation here is that `Get-Something` returns either a result or an empty `$null`.</span></span> <span data-ttu-id="86938-259">エラーが発生すると、ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="86938-259">If there is an error, we log it.</span></span> <span data-ttu-id="86938-260">次に、有効な結果が得られたことを確認してから、それを処理します。</span><span class="sxs-lookup"><span data-stu-id="86938-260">Then we check to make sure we got a valid result before processing it.</span></span>

<span data-ttu-id="86938-261">このコードに潜むバグは、`Get-Something` が例外をスローし、`$result` に値を割り当てない場合です。</span><span class="sxs-lookup"><span data-stu-id="86938-261">The bug hiding in this code is when `Get-Something` throws an exception and doesn't assign a value to `$result`.</span></span> <span data-ttu-id="86938-262">値を割り当てる前に失敗しているため、`$null` を `$result` 変数に割り当てることさえできていません。</span><span class="sxs-lookup"><span data-stu-id="86938-262">It fails before the assignment so we don't even assign `$null` to the `$result` variable.</span></span> <span data-ttu-id="86938-263">`$result` には、他のイテレーションで取得した、前の有効な `$result` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="86938-263">`$result` still contains the previous valid `$result` from other iterations.</span></span>
<span data-ttu-id="86938-264">この例では、`Update-Something` により、同一のオブジェクトに対する処理が複数回実行されることになります。</span><span class="sxs-lookup"><span data-stu-id="86938-264">`Update-Something` to execute multiple times on the same object in this example.</span></span>

<span data-ttu-id="86938-265">この問題を解決するため、foreach ループの先頭で `$result` を `$null` に設定してから、これを使用することにしました。</span><span class="sxs-lookup"><span data-stu-id="86938-265">I set `$result` to `$null` right inside the foreach loop before I use it to mitigate this issue.</span></span>

```powershell
foreach ( $node in 1..6 )
{
    $result = $null
    try
    {
        ...
```

### <a name="scope-issues"></a><span data-ttu-id="86938-266">スコープの問題</span><span class="sxs-lookup"><span data-stu-id="86938-266">Scope issues</span></span>

<span data-ttu-id="86938-267">これは、スコープの問題を軽減するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="86938-267">This also helps mitigate scoping issues.</span></span> <span data-ttu-id="86938-268">上の例では、ループ内で値を何度も `$result` に割り当てています。</span><span class="sxs-lookup"><span data-stu-id="86938-268">In that example, we assign values to `$result` over and over in a loop.</span></span> <span data-ttu-id="86938-269">しかし、PowerShell では、関数の外部から現在の関数のスコープに変数の値を入れられるため、関数内で変数の値を初期化することにより、そのような方法が原因で生じる可能性のあるバグを軽減できます。</span><span class="sxs-lookup"><span data-stu-id="86938-269">But because PowerShell allows variable values from outside the function to bleed into the scope of the current function, initializing them inside your function mitigates bugs that can be introduced that way.</span></span>

<span data-ttu-id="86938-270">関数内の初期化されていない変数は、親スコープで何らかの値に設定されている場合、`$null` ではありません。</span><span class="sxs-lookup"><span data-stu-id="86938-270">An uninitialized variable in your function is not `$null` if it's set to a value in a parent scope.</span></span>
<span data-ttu-id="86938-271">親スコープは、関数を呼び出し、同じ変数名を使用する別の関数である場合も考えられます。</span><span class="sxs-lookup"><span data-stu-id="86938-271">The parent scope could be another function that calls your function and uses the same variable names.</span></span>

<span data-ttu-id="86938-272">同じ `Do-something` の例を使ってループを削除すると、次の例のようなものが出来上がります。</span><span class="sxs-lookup"><span data-stu-id="86938-272">If I take that same `Do-something` example and remove the loop, I would end up with something that looks like this example:</span></span>

```powershell
function Invoke-Something
{
    $result = 'ParentScope'
    Do-Something
}

function Do-Something
{
    try
    {
        $result = Get-Something -ID $node
    }
    catch
    {
        Write-Verbose "[$result] not valid"
    }

    if ( $null -ne $result )
    {
        Update-Something $result
    }
}
```

<span data-ttu-id="86938-273">`Get-Something` への呼び出しが例外をスローすると、`$null` チェックで `Invoke-Something` の `$result` が見つかります。</span><span class="sxs-lookup"><span data-stu-id="86938-273">If the call to `Get-Something` throws an exception, then my `$null` check finds the `$result` from `Invoke-Something`.</span></span> <span data-ttu-id="86938-274">関数内で値を初期化することにより、この問題を軽減できます。</span><span class="sxs-lookup"><span data-stu-id="86938-274">Initializing the value inside your function mitigates this issue.</span></span>

<span data-ttu-id="86938-275">変数に名前を付けるのは大変な作業であり、作成者が複数の関数で同じ変数名を使用するのはよくあることです。</span><span class="sxs-lookup"><span data-stu-id="86938-275">Naming variables is hard and it's common for an author to use the same variable names in multiple functions.</span></span> <span data-ttu-id="86938-276">私自身、いつも `$node` や `$result` や `$data` を使っています。</span><span class="sxs-lookup"><span data-stu-id="86938-276">I know I use `$node`,`$result`,`$data` all the time.</span></span> <span data-ttu-id="86938-277">このため、異なるスコープの値が、使用されるべきでない場所で使用されることは十分に起こりうる問題なのです。</span><span class="sxs-lookup"><span data-stu-id="86938-277">So it would be very easy for values from different scopes to show up in places where they should not be.</span></span>

## <a name="redirect-output-to-null"></a><span data-ttu-id="86938-278">$null への出力のリダイレクト</span><span class="sxs-lookup"><span data-stu-id="86938-278">Redirect output to $null</span></span>

<span data-ttu-id="86938-279">この記事全体で `$null` 値について説明してきましたが、出力を `$null` にリダイレクトする方法に言及せずに説明を終えることはできません。</span><span class="sxs-lookup"><span data-stu-id="86938-279">I have been talking about `$null` values for this entire article but the topic is not complete if I didn't mention redirecting output to `$null`.</span></span> <span data-ttu-id="86938-280">コマンドが出力する情報やオブジェクトを、非表示にすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="86938-280">There are times when you have commands that output information or objects that you want to suppress.</span></span> <span data-ttu-id="86938-281">出力を `$null` にリダイレクトすると、この処理を実現できます。</span><span class="sxs-lookup"><span data-stu-id="86938-281">Redirecting output to `$null` does that.</span></span>

### <a name="out-null"></a><span data-ttu-id="86938-282">Out-Null</span><span class="sxs-lookup"><span data-stu-id="86938-282">Out-Null</span></span>

<span data-ttu-id="86938-283">Out-Null コマンドは、パイプライン データを `$null` にリダイレクトするためにあらかじめ用意された方法です。</span><span class="sxs-lookup"><span data-stu-id="86938-283">The Out-Null command is the built-in way to redirect pipeline data to `$null`.</span></span>

```powershell
New-Item -Type Directory -Path $path | Out-Null
```

### <a name="assign-to-null"></a><span data-ttu-id="86938-284">$null への割り当て</span><span class="sxs-lookup"><span data-stu-id="86938-284">Assign to $null</span></span>

<span data-ttu-id="86938-285">`$null` にコマンドの結果を割り当てることにより、`Out-Null` を使用するのと同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="86938-285">You can assign the results of a command to `$null` for the same effect as using `Out-Null`.</span></span>

```powershell
$null = New-Item -Type Directory -Path $path
```

<span data-ttu-id="86938-286">`$null` は定数値であるため、上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="86938-286">Because `$null` is a constant value, you can never overwrite it.</span></span> <span data-ttu-id="86938-287">個人的にはコードの見た目が好きではないのですが、`Out-Null` よりも処理が速いことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="86938-287">I don't like the way it looks in my code but it often performs faster than `Out-Null`.</span></span>

### <a name="redirect-to-null"></a><span data-ttu-id="86938-288">$null へのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="86938-288">Redirect to $null</span></span>

<span data-ttu-id="86938-289">リダイレクト演算子を使用して出力を `$null` に送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="86938-289">You can also use the redirection operator to send output to `$null`.</span></span>

```powershell
New-Item -Type Directory -Path $path > $null
```

<span data-ttu-id="86938-290">異なるストリームに出力するコマンドライン実行可能ファイルを処理する場合は、</span><span class="sxs-lookup"><span data-stu-id="86938-290">If you're dealing with command-line executables that output on the different streams.</span></span> <span data-ttu-id="86938-291">次のようにすると、すべての出力ストリームを `$null` にリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="86938-291">You can redirect all output streams to `$null` like this:</span></span>

```powershell
git status *> $null
```

## <a name="summary"></a><span data-ttu-id="86938-292">まとめ</span><span class="sxs-lookup"><span data-stu-id="86938-292">Summary</span></span>

<span data-ttu-id="86938-293">この点についてさまざまな説明を行ってきました。この記事は、私の詳細説明のほとんどより断片的なものです。</span><span class="sxs-lookup"><span data-stu-id="86938-293">I covered a lot of ground on this one and I know this article is more fragmented than most of my deep dives.</span></span> <span data-ttu-id="86938-294">それは、`$null` 値が PowerShell のさまざまな場所に現れ、出現箇所によってその意味合いが微妙に異なるからです。</span><span class="sxs-lookup"><span data-stu-id="86938-294">That is because `$null` values can pop up in many different places in PowerShell and all the nuances are specific to where you find it.</span></span> <span data-ttu-id="86938-295">この記事が、`$null` に関する皆さまの理解と、遭遇する可能性のある難解なシナリオの理解のお役に立てば幸いです。</span><span class="sxs-lookup"><span data-stu-id="86938-295">I hope you walk away from this with a better understanding of `$null` and an awareness of the more obscure scenarios you may run into.</span></span>

<!-- link references -->
[オリジナル バージョン]: https://powershellexplained.com/2018-12-23-Powershell-null-everything-you-wanted-to-know/
[original version]: https://powershellexplained.com/2018-12-23-Powershell-null-everything-you-wanted-to-know/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[優れた記事]: https://blog.iisreset.me/schrodingers-argumentlist
[good post]: https://blog.iisreset.me/schrodingers-argumentlist
[PSScriptAnalyzer]: https://www.powershellgallery.com/packages/PSScriptAnalyzer
[System.Management.Automation.Internal.AutomationNull]: /dotnet/api/system.management.automation.internal.automationnull
