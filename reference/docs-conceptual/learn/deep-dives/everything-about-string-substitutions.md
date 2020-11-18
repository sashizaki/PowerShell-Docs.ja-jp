---
title: 文字列での変数の代入について知りたかったことのすべて
description: 文字列で変数を使用して、書式設定されたテキストを作成するには、多くの方法があります。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 786526fb98dbf1b3ec7c5c6c985ac95b85a96259
ms.sourcegitcommit: 4bb44f183dcbfa8dced57f075812e02d3b45fd70
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "86301320"
---
# <a name="everything-you-wanted-to-know-about-variable-substitution-in-strings"></a><span data-ttu-id="061ef-103">文字列での変数の代入について知りたかったことのすべて</span><span class="sxs-lookup"><span data-stu-id="061ef-103">Everything you wanted to know about variable substitution in strings</span></span>

<span data-ttu-id="061ef-104">文字列で変数を使用する方法は数多くあります。</span><span class="sxs-lookup"><span data-stu-id="061ef-104">There are many ways to use variables in strings.</span></span> <span data-ttu-id="061ef-105">この変数の代入を呼び出そうとしていますが、変数の値を含むように文字列を書式設定する場合はいつでも参照することになります。</span><span class="sxs-lookup"><span data-stu-id="061ef-105">I'm calling this variable substitution but I'm referring to any time you want to format a string to include values from variables.</span></span> <span data-ttu-id="061ef-106">これは、スクリプト作成の初心者にはたいてい説明していることです。</span><span class="sxs-lookup"><span data-stu-id="061ef-106">This is something that I often find myself explaining to new scripters.</span></span>

> [!NOTE]
> <span data-ttu-id="061ef-107">この記事の[オリジナル バージョン][]は、[@KevinMarquette][] 氏のブログに掲載されました。</span><span class="sxs-lookup"><span data-stu-id="061ef-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="061ef-108">このコンテンツを共有してくださった Kevin 氏に、PowerShell チームより感謝を申し上げます。</span><span class="sxs-lookup"><span data-stu-id="061ef-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="061ef-109">[PowerShellExplained.com][] のブログをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="061ef-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="concatenation"></a><span data-ttu-id="061ef-110">連結</span><span class="sxs-lookup"><span data-stu-id="061ef-110">Concatenation</span></span>

<span data-ttu-id="061ef-111">メソッドの最初のクラスは、連結として参照できます。</span><span class="sxs-lookup"><span data-stu-id="061ef-111">The first class of methods can be referred to as concatenation.</span></span> <span data-ttu-id="061ef-112">これは基本的に、いくつかの文字列を取得し、それらを一緒に結合することです。</span><span class="sxs-lookup"><span data-stu-id="061ef-112">It's basically taking several strings and joining them together.</span></span> <span data-ttu-id="061ef-113">書式設定された文字列を、連結を使用して構築することには長い歴史があります。</span><span class="sxs-lookup"><span data-stu-id="061ef-113">There's a long history of using concatenation to build formatted strings.</span></span>

```powershell
$name = 'Kevin Marquette'
$message = 'Hello, ' + $name
```

<span data-ttu-id="061ef-114">追加する値が少しの値のみである場合、連結は正しく機能します。</span><span class="sxs-lookup"><span data-stu-id="061ef-114">Concatenation works out OK when there are only a few values to add.</span></span> <span data-ttu-id="061ef-115">しかし、これはすぐに複雑になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="061ef-115">But this can get complicated quickly.</span></span>

```powershell
$first = 'Kevin'
$last = 'Marquette'
```

```powershell
$message = 'Hello, ' + $first + ' ' + $last + '.'
```

<span data-ttu-id="061ef-116">この簡単な例でさえ、読みにくさが増しています。</span><span class="sxs-lookup"><span data-stu-id="061ef-116">This simple example is already getting harder to read.</span></span>

## <a name="variable-substitution"></a><span data-ttu-id="061ef-117">変数の置換</span><span class="sxs-lookup"><span data-stu-id="061ef-117">Variable substitution</span></span>

<span data-ttu-id="061ef-118">PowerShell には、より簡単な別のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="061ef-118">PowerShell has another option that is easier.</span></span> <span data-ttu-id="061ef-119">文字列内で変数を直接指定できます。</span><span class="sxs-lookup"><span data-stu-id="061ef-119">You can specify your variables directly in the strings.</span></span>

```powershell
$message = "Hello, $first $last."
```

<span data-ttu-id="061ef-120">文字列を囲むのに使用する引用符の種類によって、違いが生じます。</span><span class="sxs-lookup"><span data-stu-id="061ef-120">The type of quotes you use around the string makes a difference.</span></span> <span data-ttu-id="061ef-121">二重引用符で囲まれた文字列では代入が可能ですが、単一引用符で囲まれた文字列ではできません。</span><span class="sxs-lookup"><span data-stu-id="061ef-121">A double quoted string allows the substitution but a single quoted string doesn't.</span></span> <span data-ttu-id="061ef-122">一方が必要なときも他方が必要なときもあるため、選択肢があるのです。</span><span class="sxs-lookup"><span data-stu-id="061ef-122">There are times you want one or the other so you have an option.</span></span>

## <a name="command-substitution"></a><span data-ttu-id="061ef-123">コマンドの代入</span><span class="sxs-lookup"><span data-stu-id="061ef-123">Command substitution</span></span>

<span data-ttu-id="061ef-124">プロパティの値を文字列で取得しようとしているときには、少し注意が必要になります。</span><span class="sxs-lookup"><span data-stu-id="061ef-124">Things get a little tricky when you start trying to get the values of properties into a string.</span></span> <span data-ttu-id="061ef-125">ここで多くの初心者がつまずきます。</span><span class="sxs-lookup"><span data-stu-id="061ef-125">This is where many new people get tripped up.</span></span> <span data-ttu-id="061ef-126">まず彼らが、何が機能するはずだと考えているかを説明しましょう (一見した限りはそうなるはずのように思えます)。</span><span class="sxs-lookup"><span data-stu-id="061ef-126">First let me show you what they think should work (and at face value almost looks like it should).</span></span>

```powershell
$directory = Get-Item 'c:\windows'
$message = "Time: $directory.CreationTime"
```

<span data-ttu-id="061ef-127">`$directory` から `CreationTime` を取得することを期待していますが、その代わり、値としてこの `Time: c:\windows.CreationTime` を取得します。</span><span class="sxs-lookup"><span data-stu-id="061ef-127">You would be expecting to get the `CreationTime` off of the `$directory`, but instead you get this `Time: c:\windows.CreationTime` as your value.</span></span> <span data-ttu-id="061ef-128">この種類の代入では、基本変数のみが参照されることが理由です。</span><span class="sxs-lookup"><span data-stu-id="061ef-128">The reason is that this type of substitution only sees the base variable.</span></span> <span data-ttu-id="061ef-129">ピリオドは文字列の一部と見なされるため、より深く値を解決する処理は停止されます。</span><span class="sxs-lookup"><span data-stu-id="061ef-129">It considers the period as part of the string so it stops resolving the value any deeper.</span></span>

<span data-ttu-id="061ef-130">この処理だけが発生し、このオブジェクトは、文字列内に配置されるときの既定値として文字列を提供します。</span><span class="sxs-lookup"><span data-stu-id="061ef-130">It just so happens that this object gives a string as a default value when placed into a string.</span></span>
<span data-ttu-id="061ef-131">一部のオブジェクトでは、代わりに `System.Collections.Hashtable` のような型名を提供します。</span><span class="sxs-lookup"><span data-stu-id="061ef-131">Some objects give you the type name instead like `System.Collections.Hashtable`.</span></span> <span data-ttu-id="061ef-132">注意だけしておいてください。</span><span class="sxs-lookup"><span data-stu-id="061ef-132">Just something to watch for.</span></span>

<span data-ttu-id="061ef-133">PowerShell では、特殊な構文を使用すると、文字列内でのコマンドの実行が可能です。</span><span class="sxs-lookup"><span data-stu-id="061ef-133">PowerShell allows you to do command execution inside the string with a special syntax.</span></span> <span data-ttu-id="061ef-134">これにより、これらのオブジェクトのプロパティを取得し、その他の任意のコマンドを実行して値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="061ef-134">This allows us to get the properties of these objects and run any other command to get a value.</span></span>

```powershell
$message = "Time: $($directory.CreationTime)"
```

<span data-ttu-id="061ef-135">これは、一部の状況では適切に機能しますが、数個の変数があるだけでも連結と同様に複雑になります。</span><span class="sxs-lookup"><span data-stu-id="061ef-135">This works great for some situations but it can get just as crazy as concatenation if you have just a few variables.</span></span>

### <a name="command-execution"></a><span data-ttu-id="061ef-136">コマンド実行</span><span class="sxs-lookup"><span data-stu-id="061ef-136">Command execution</span></span>

<span data-ttu-id="061ef-137">文字列内でコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="061ef-137">You can run commands inside a string.</span></span> <span data-ttu-id="061ef-138">この選択肢があっても、私はそれが好きではありません。</span><span class="sxs-lookup"><span data-stu-id="061ef-138">Even though I have this option, I don't like it.</span></span> <span data-ttu-id="061ef-139">すぐに乱雑になり、デバッグが難しくなります。</span><span class="sxs-lookup"><span data-stu-id="061ef-139">It gets cluttered quickly and hard to debug.</span></span> <span data-ttu-id="061ef-140">私なら、コマンドを実行して変数に保存するか、書式設定文字列を使用するかのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="061ef-140">I either run the command and save to a variable or use a format string.</span></span>

```powershell
$message = "Date: $(Get-Date)"
```

## <a name="format-string"></a><span data-ttu-id="061ef-141">[書式設定文字列]</span><span class="sxs-lookup"><span data-stu-id="061ef-141">Format string</span></span>

<span data-ttu-id="061ef-142">.NET には、扱いがかなり容易だと思われる、文字列を書式設定する方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="061ef-142">.NET has a way to format strings that I find fairly easy to work with.</span></span> <span data-ttu-id="061ef-143">最初に、そのための静的メソッドについて説明してから、同じことを行う PowerShell ショートカットを示します。</span><span class="sxs-lookup"><span data-stu-id="061ef-143">First let me show you the static method for it before I show you the PowerShell shortcut to do the same thing.</span></span>

```powershell
# .NET string format string
[string]::Format('Hello, {0} {1}.',$first,$last)

# PowerShell format string
'Hello, {0} {1}.' -f $first, $last
```

<span data-ttu-id="061ef-144">ここで起きているのは、次のようなことです。文字列がトークン `{0}` および `{1}` に対して解析された後、その数値を使用して、指定された値からの選択を行っています。</span><span class="sxs-lookup"><span data-stu-id="061ef-144">What is happening here is that the string is parsed for the tokens `{0}` and `{1}`, then it uses that number to pick from the values provided.</span></span> <span data-ttu-id="061ef-145">文字列内のどこかにある 1 つの値を繰り返す場合は、その値番号を再利用できます。</span><span class="sxs-lookup"><span data-stu-id="061ef-145">If you want to repeat one value some place in the string, you can reuse that values number.</span></span>

<span data-ttu-id="061ef-146">文字列がより複雑になるほど、このアプローチからより多くの価値が得られます。</span><span class="sxs-lookup"><span data-stu-id="061ef-146">The more complicated the string gets, the more value you get out of this approach.</span></span>

### <a name="format-values-as-arrays"></a><span data-ttu-id="061ef-147">値を配列として書式設定する</span><span class="sxs-lookup"><span data-stu-id="061ef-147">Format values as arrays</span></span>

<span data-ttu-id="061ef-148">書式設定行が長くなりすぎる場合は、値をまず配列内に配置できます。</span><span class="sxs-lookup"><span data-stu-id="061ef-148">If your format line gets too long, you can place your values into an array first.</span></span>

```powershell
$values = @(
    "Kevin"
    "Marquette"
)
'Hello, {0} {1}.' -f $values
```

<span data-ttu-id="061ef-149">配列全体を渡すため、記述が長くなりませんが、考え方は同様です。</span><span class="sxs-lookup"><span data-stu-id="061ef-149">This is not splatting because I'm passing the whole array in, but the idea is similar.</span></span>

## <a name="advanced-formatting"></a><span data-ttu-id="061ef-150">高度な書式設定</span><span class="sxs-lookup"><span data-stu-id="061ef-150">Advanced formatting</span></span>

<span data-ttu-id="061ef-151">既に詳細に[文書化済み][]の書式設定オプションが多数存在するため、私は意図的に、これらのオプションは .NET 由来のものであると述べました。</span><span class="sxs-lookup"><span data-stu-id="061ef-151">I intentionally called these out as coming from .NET because there are lots of formatting options already well [documented][] on it.</span></span> <span data-ttu-id="061ef-152">さまざまなデータ型を書式設定するために、組み込みの方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="061ef-152">There are built in ways to format various data types.</span></span>

```powershell
"{0:yyyyMMdd}" -f (Get-Date)
"Population {0:N0}" -f  8175133
```

<span data-ttu-id="061ef-153">それらについては説明しませんが、必要な場合には、これは非常に強力な書式設定エンジンであることを指摘させてください。</span><span class="sxs-lookup"><span data-stu-id="061ef-153">I'm not going to go into them but I just wanted to let you know that this is a very powerful formatting engine if you need it.</span></span>

## <a name="joining-strings"></a><span data-ttu-id="061ef-154">文字列の結合</span><span class="sxs-lookup"><span data-stu-id="061ef-154">Joining strings</span></span>

<span data-ttu-id="061ef-155">場合によっては、値のリストを連結することが実際に必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="061ef-155">Sometimes you actually do want to concatenate a list of values together.</span></span> <span data-ttu-id="061ef-156">これを行ってくれる `-join` 演算子があります。</span><span class="sxs-lookup"><span data-stu-id="061ef-156">There's a `-join` operator that can do that for you.</span></span> <span data-ttu-id="061ef-157">文字列の間をつなぐ文字を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="061ef-157">It even lets you specify a character to join between the strings.</span></span>

```powershell
$servers = @(
    'server1'
    'server2'
    'server3'
)

$servers  -join ','
```

<span data-ttu-id="061ef-158">区切り記号を使用せずに一部の文字列を `-join` する場合は、空の文字列 `''` を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="061ef-158">If you want to `-join` some strings without a separator, you need to specify an empty string `''`.</span></span>
<span data-ttu-id="061ef-159">しかし、それが必要なことのすべてであれば、より高速なオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="061ef-159">But if that is all you need, there's a faster option.</span></span>

```powershell
[string]::Concat('server1','server2','server3')
[string]::Concat($servers)
```

<span data-ttu-id="061ef-160">指摘しておくのに値するのは、文字列の `-split` も可能である点です。</span><span class="sxs-lookup"><span data-stu-id="061ef-160">It's also worth pointing out that you can also `-split` strings too.</span></span>

## <a name="join-path"></a><span data-ttu-id="061ef-161">Join-Path</span><span class="sxs-lookup"><span data-stu-id="061ef-161">Join-Path</span></span>

<span data-ttu-id="061ef-162">これはよく見過ごされますが、ファイル パスを構築するための優れたコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="061ef-162">This is often overlooked but a great cmdlet for building a file path.</span></span>

```powershell
$folder = 'Temp'
Join-Path -Path 'c:\windows' -ChildPath $folder
```

<span data-ttu-id="061ef-163">これの優れた点は、値を 1 つにまとめるときに円記号が正しく処理されることです。</span><span class="sxs-lookup"><span data-stu-id="061ef-163">The great thing about this is it works out the backslashes correctly when it puts the values together.</span></span> <span data-ttu-id="061ef-164">これが特に重要なのは、ユーザーまたは構成ファイルから値を取得しようとしている場合です。</span><span class="sxs-lookup"><span data-stu-id="061ef-164">This is especially important if you are taking values from users or config files.</span></span>

<span data-ttu-id="061ef-165">これは、`Split-Path` や `Test-Path` と使用するのにも適しています。</span><span class="sxs-lookup"><span data-stu-id="061ef-165">This also goes well with `Split-Path` and `Test-Path`.</span></span> <span data-ttu-id="061ef-166">これらについては、[ファイルに対する読み取りと保存][]に関する私の投稿でも取り上げています。</span><span class="sxs-lookup"><span data-stu-id="061ef-166">I also cover these in my post about [reading and saving to files][].</span></span>

## <a name="strings-are-arrays"></a><span data-ttu-id="061ef-167">文字列は配列である</span><span class="sxs-lookup"><span data-stu-id="061ef-167">Strings are arrays</span></span>

<span data-ttu-id="061ef-168">先に進む前に、ここで文字列の追加について言及する必要があります。</span><span class="sxs-lookup"><span data-stu-id="061ef-168">I do need to mention adding strings here before I go on.</span></span> <span data-ttu-id="061ef-169">文字列は、文字の配列にすぎないことを思い出してください。</span><span class="sxs-lookup"><span data-stu-id="061ef-169">Remember that a string is just an array of characters.</span></span> <span data-ttu-id="061ef-170">複数の文字列を一緒に追加すると、新しい配列が毎回作成されます。</span><span class="sxs-lookup"><span data-stu-id="061ef-170">When you add multiple strings together, a new array is created each time.</span></span>

<span data-ttu-id="061ef-171">次の例を見てください。</span><span class="sxs-lookup"><span data-stu-id="061ef-171">Look at this example:</span></span>

```powershell
$message = "Numbers: "
foreach($number in 1..10000)
{
    $message += " $number"
}
```

<span data-ttu-id="061ef-172">非常に基本的な内容に見えますが、見えていないのは、文字列が `$message` に追加されるたびに、まったく新しい文字列全体が作成されていることです。</span><span class="sxs-lookup"><span data-stu-id="061ef-172">It looks very basic but what you don't see is that each time a string is added to `$message` that a whole new string is created.</span></span> <span data-ttu-id="061ef-173">メモリが割り当てられ、データがコピーされて、古いものが破棄されます。</span><span class="sxs-lookup"><span data-stu-id="061ef-173">Memory gets allocated, data gets copied and the old one is discarded.</span></span>
<span data-ttu-id="061ef-174">数回実行するだけの場合は気にする必要はありませんが、このようなループから実際に問題が明るみに出るでしょう。</span><span class="sxs-lookup"><span data-stu-id="061ef-174">Not a big deal when it's only done a few times, but a loop like this would really expose the issue.</span></span>

### <a name="stringbuilder"></a><span data-ttu-id="061ef-175">StringBuilder</span><span class="sxs-lookup"><span data-stu-id="061ef-175">StringBuilder</span></span>

<span data-ttu-id="061ef-176">多数の小さな文字列から大きな文字列を構築する場合には、StringBuilder もよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="061ef-176">StringBuilder is also very popular for building large strings from lots of smaller strings.</span></span> <span data-ttu-id="061ef-177">追加したすべての文字列をただ収集し、最後に値を取得するときにすべての文字列を連結するだけであるのが、その理由です。</span><span class="sxs-lookup"><span data-stu-id="061ef-177">The reason why is because it just collects all the strings you add to it and only concatenates all of them at the end when you retrieve the value.</span></span>

```powershell
$stringBuilder = New-Object -TypeName "System.Text.StringBuilder"

[void]$stringBuilder.Append("Numbers: ")
foreach($number in 1..10000)
{
    [void]$stringBuilder.Append(" $number")
}
$message = $stringBuilder.ToString()
```

<span data-ttu-id="061ef-178">これも、私が .NET の使用を考える処理内容です。</span><span class="sxs-lookup"><span data-stu-id="061ef-178">Again, this is something that I'm reaching out to .NET for.</span></span> <span data-ttu-id="061ef-179">私が頻繁に使用することはもうありませんが、それが存在することを覚えておくとよいでしょう。</span><span class="sxs-lookup"><span data-stu-id="061ef-179">I don't use it often anymore but it's good to know it's there.</span></span>

## <a name="delineation-with-braces"></a><span data-ttu-id="061ef-180">中かっこを使用した区切り</span><span class="sxs-lookup"><span data-stu-id="061ef-180">Delineation with braces</span></span>

<span data-ttu-id="061ef-181">これは、文字列内でのサフィックス連結に使用されます。</span><span class="sxs-lookup"><span data-stu-id="061ef-181">This is used for suffix concatenation within the string.</span></span> <span data-ttu-id="061ef-182">場合によっては、変数に明確なワード境界がないことがあります。</span><span class="sxs-lookup"><span data-stu-id="061ef-182">Sometimes your variable doesn't have a clean word boundary.</span></span>

```powershell
$test = "Bet"
$tester = "Better"
Write-Host "$test $tester ${test}ter"
```

<span data-ttu-id="061ef-183">このテーマについては、[/u/real_parbold][] に感謝です。</span><span class="sxs-lookup"><span data-stu-id="061ef-183">Thank you [/u/real_parbold][] for that one.</span></span>

<span data-ttu-id="061ef-184">次に、このアプローチに代わる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="061ef-184">Here is an alternate to this approach:</span></span>

```powershell
Write-Host "$test $tester $($test)ter"
Write-Host "{0} {1} {0}ter" -f $test, $tester
```

<span data-ttu-id="061ef-185">私個人としては、これには書式設定文字列を使用しますが、どこかで目にした場合に備えて知っておいてください。</span><span class="sxs-lookup"><span data-stu-id="061ef-185">I personally use format string for this, but this is good to know incase you see it in the wild.</span></span>

## <a name="find-and-replace-tokens"></a><span data-ttu-id="061ef-186">検索と置換のトークン</span><span class="sxs-lookup"><span data-stu-id="061ef-186">Find and replace tokens</span></span>

<span data-ttu-id="061ef-187">これらの多くの機能により、独自のソリューションを書く必要性は限られていますが、内部の文字列を置き換える必要がある大きなテンプレート ファイルがある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="061ef-187">While most of these features limit your need to roll your own solution, there are times where you may have large template files where you want to replace strings inside.</span></span>

<span data-ttu-id="061ef-188">ファイルからテンプレートを作成し、それには大量のテキストが含まれるとします。</span><span class="sxs-lookup"><span data-stu-id="061ef-188">Let us assume you pulled in a template from a file that has a lot of text.</span></span>

```powershell
$letter = Get-Content -Path TemplateLetter.txt -RAW
$letter = $letter -replace '#FULL_NAME#', 'Kevin Marquette'
```

<span data-ttu-id="061ef-189">多数のトークンを置換することもあります。</span><span class="sxs-lookup"><span data-stu-id="061ef-189">You may have lots of tokens to replace.</span></span> <span data-ttu-id="061ef-190">うまいやり方は、検索と置換が容易な、非常に明確なトークンを使用することです。</span><span class="sxs-lookup"><span data-stu-id="061ef-190">The trick is to use a very distinct token that is easy to find and replace.</span></span> <span data-ttu-id="061ef-191">私は得てして、区別しやすいように両端で特殊文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="061ef-191">I tend to use a special character at both ends to help distinguish it.</span></span>

<span data-ttu-id="061ef-192">最近、これに取り組む新しい方法を見つけました。</span><span class="sxs-lookup"><span data-stu-id="061ef-192">I recently found a new way to approach this.</span></span> <span data-ttu-id="061ef-193">これは一般的に使用されるパターンであるため、この記事ではこのセクションを残すことに決めました。</span><span class="sxs-lookup"><span data-stu-id="061ef-193">I decided to leave this section in here because this is a pattern that is commonly used.</span></span>

### <a name="replace-multiple-tokens"></a><span data-ttu-id="061ef-194">複数のトークンを置換する</span><span class="sxs-lookup"><span data-stu-id="061ef-194">Replace multiple tokens</span></span>

<span data-ttu-id="061ef-195">置換する必要があるトークンのリストがあるときには、より一般的なアプローチにします。</span><span class="sxs-lookup"><span data-stu-id="061ef-195">When I have a list of tokens that I need to replace, I take a more generic approach.</span></span> <span data-ttu-id="061ef-196">それをハッシュテーブル内に置き、反復処理して置換を実行します。</span><span class="sxs-lookup"><span data-stu-id="061ef-196">I would place them in a hashtable and iterate over them to do the replace.</span></span>

```powershell
$tokenList = @{
    Full_Name = 'Kevin Marquette'
    Location = 'Orange County'
    State = 'CA'
}

$letter = Get-Content -Path TemplateLetter.txt -RAW
foreach( $token in $tokenList.GetEnumerator() )
{
    $pattern = '#{0}#' -f $token.key
    $letter = $letter -replace $pattern, $token.Value
}
```

<span data-ttu-id="061ef-197">これらのトークンは、必要に応じて JSON や CSV から読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="061ef-197">Those tokens could be loaded from JSON or CSV if needed.</span></span>

### <a name="executioncontext-expandstring"></a><span data-ttu-id="061ef-198">ExecutionContext の ExpandString</span><span class="sxs-lookup"><span data-stu-id="061ef-198">ExecutionContext ExpandString</span></span>

<span data-ttu-id="061ef-199">単一引用符で囲んで置換文字列を定義し、後で変数を拡張する巧みな方法があります。</span><span class="sxs-lookup"><span data-stu-id="061ef-199">There's a clever way to define a substitution string with single quotes and expand the variables later.</span></span> <span data-ttu-id="061ef-200">次の例を見てください。</span><span class="sxs-lookup"><span data-stu-id="061ef-200">Look at this example:</span></span>

```powershell
$message = 'Hello, $Name!'
$name = 'Kevin Marquette'
$string = $ExecutionContext.InvokeCommand.ExpandString($message)
```

<span data-ttu-id="061ef-201">現在の実行コンテキストで `.InvokeCommand.ExpandString` を呼び出すと、置換には、現在のスコープ内の変数が使用されます。</span><span class="sxs-lookup"><span data-stu-id="061ef-201">The call to `.InvokeCommand.ExpandString` on the current execution context uses the variables in the current scope for substitution.</span></span> <span data-ttu-id="061ef-202">ここで重要なのは、`$message` は、変数が存在する前であっても非常に早い段階で定義できることです。</span><span class="sxs-lookup"><span data-stu-id="061ef-202">The key thing here is that the `$message` can be defined very early before the variables even exist.</span></span>

<span data-ttu-id="061ef-203">それを少しだけ拡張すれば、異なる値を使用して、この置換を何度も繰り返し実行できます。</span><span class="sxs-lookup"><span data-stu-id="061ef-203">If we expand on that just a little bit, we can perform this substitution over and over wih different values.</span></span>

```powershell
$message = 'Hello, $Name!'
$nameList = 'Mark Kraus','Kevin Marquette','Lee Dailey'
foreach($name in $nameList){
    $ExecutionContext.InvokeCommand.ExpandString($message)
}
```

<span data-ttu-id="061ef-204">このアイデアをさらに進める場合、テキスト ファイルから大きなメール テンプレートをインポートし、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="061ef-204">To keep going on this idea; you could be importing a large email template from a text file to do this.</span></span> <span data-ttu-id="061ef-205">この[提案][]については、[Mark Kraus][] に感謝しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="061ef-205">I have to thank [Mark Kraus][] for this [suggestion][].</span></span>

## <a name="whatever-works-the-best-for-you"></a><span data-ttu-id="061ef-206">あなたにとって最適に機能することが重要</span><span class="sxs-lookup"><span data-stu-id="061ef-206">Whatever works the best for you</span></span>

<span data-ttu-id="061ef-207">私は、書式指定文字列を使用するアプローチを愛好しています。</span><span class="sxs-lookup"><span data-stu-id="061ef-207">I'm a fan of the format string approach.</span></span> <span data-ttu-id="061ef-208">私は、より複雑な文字列を扱う場合でも、複数の変数がある場合でも、絶対にこれを行います。</span><span class="sxs-lookup"><span data-stu-id="061ef-208">I definitely do this with the more complicated strings or if there are multiple variables.</span></span> <span data-ttu-id="061ef-209">非常に短ければ何に対しても、これらのいずれかを使用できるでしょう。</span><span class="sxs-lookup"><span data-stu-id="061ef-209">On anything that is very short, I may use any one of these.</span></span>

## <a name="anything-else"></a><span data-ttu-id="061ef-210">その他</span><span class="sxs-lookup"><span data-stu-id="061ef-210">Anything else?</span></span>

<span data-ttu-id="061ef-211">この記事では多くの範囲を取り上げました。</span><span class="sxs-lookup"><span data-stu-id="061ef-211">I covered a lot of ground on this one.</span></span> <span data-ttu-id="061ef-212">何か新しいことを学び、この記事を終えていただければ幸いです。</span><span class="sxs-lookup"><span data-stu-id="061ef-212">My hope is that you walk away learning something new.</span></span>

<!-- link references -->
[オリジナル バージョン]: https://powershellexplained.com/2017-01-13-powershell-variable-substitution-in-strings/
[original version]: https://powershellexplained.com/2017-01-13-powershell-variable-substitution-in-strings/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[Mark Kraus]: https://get-powershellblog.blogspot.com/
[提案]: https://www.reddit.com/r/PowerShell/comments/5npf8h/kevmar_everything_you_wanted_to_know_about/dcdfia5/
[suggestion]: https://www.reddit.com/r/PowerShell/comments/5npf8h/kevmar_everything_you_wanted_to_know_about/dcdfia5/
[/u/real_parbold]: https://www.reddit.com/r/PowerShell/comments/5npf8h/kevmar_everything_you_wanted_to_know_about/dcdfm6p/
[ファイルに対する読み取りと保存]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files/
[reading and saving to files]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files/
[文書化済み]: /dotnet/api/system.string.format#overloads
[documented]: /dotnet/api/system.string.format#overloads
