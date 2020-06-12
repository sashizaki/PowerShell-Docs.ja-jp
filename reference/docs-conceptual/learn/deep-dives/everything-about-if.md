---
title: IF ステートメントについて知りたかったことのすべて
description: 他の多くの言語と同様に、PowerShell には、スクリプト内でコードを条件付き実行するためのステートメントがあります。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 6ffb70af694e80430d31991045b9fadc1a2cc3f0
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149525"
---
# <a name="everything-you-wanted-to-know-about-the-if-statement"></a><span data-ttu-id="62a4b-103">IF ステートメントについて知りたかったことのすべて</span><span class="sxs-lookup"><span data-stu-id="62a4b-103">Everything you wanted to know about the IF statement</span></span>

<span data-ttu-id="62a4b-104">他の多くの言語と同様に、PowerShell には、スクリプト内でコードを条件付き実行するためのステートメントがあります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-104">Like many other languages, PowerShell has statements for conditionally executing code in your scripts.</span></span> <span data-ttu-id="62a4b-105">それらのステートメントの 1 つが [if][] ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-105">One of those statements is the [if][] statement.</span></span> <span data-ttu-id="62a4b-106">本日は、PowerShell の最も基本的なコマンドの 1 つについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-106">Today we will take a deep dive into one of the most fundamental commands in PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="62a4b-107">この記事の[オリジナル バージョン][]は、[@KevinMarquette][] 氏のブログに掲載されました。</span><span class="sxs-lookup"><span data-stu-id="62a4b-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="62a4b-108">このコンテンツを共有してくださった Kevin 氏に、PowerShell チームより感謝を申し上げます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="62a4b-109">[PowerShellExplained.com][] のブログをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="62a4b-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="conditional-execution"></a><span data-ttu-id="62a4b-110">条件付き実行</span><span class="sxs-lookup"><span data-stu-id="62a4b-110">Conditional execution</span></span>

<span data-ttu-id="62a4b-111">多くの場合、スクリプトでは決定を下し、それらの決定に基づいて異なるロジックを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-111">Your scripts often need to make decisions and perform different logic based on those decisions.</span></span>
<span data-ttu-id="62a4b-112">これが、条件付き実行の意味です。</span><span class="sxs-lookup"><span data-stu-id="62a4b-112">This is what I mean by conditional execution.</span></span> <span data-ttu-id="62a4b-113">評価するステートメントまたは値が 1 つあると、その評価に基づいてコードの別のセクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-113">You have one statement or value to evaluate, then execute a different section of code based on that evaluation.</span></span> <span data-ttu-id="62a4b-114">これがまさに、`if` ステートメントで行われることです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-114">This is exactly what the `if` statement does.</span></span>

## <a name="the-if-statement"></a><span data-ttu-id="62a4b-115">if ステートメント</span><span class="sxs-lookup"><span data-stu-id="62a4b-115">The if statement</span></span>

<span data-ttu-id="62a4b-116">次に、`if` ステートメントの基本的な例を示します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-116">Here is a basic example of the `if` statement:</span></span>

```powershell
$condition = $true
if ( $condition )
{
    Write-Output "The condition was true"
}
```

<span data-ttu-id="62a4b-117">最初に `if` ステートメントが実行することは、かっこ内の式を評価することです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-117">The first thing the `if` statement does is evaluate the expression in parentheses.</span></span> <span data-ttu-id="62a4b-118">`$true` に評価されると、中かっこ内の `scriptblock` が実行されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-118">If it evaluates to `$true`, then it executes the `scriptblock` in the braces.</span></span> <span data-ttu-id="62a4b-119">値が `$false` であった場合、そのスクリプト ブロックはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-119">If the value was `$false`, then it would skip over that scriptblock.</span></span>

<span data-ttu-id="62a4b-120">前の例では、`if` ステートメントは `$condition` 変数を評価するだけでした。</span><span class="sxs-lookup"><span data-stu-id="62a4b-120">In the previous example, the `if` statement was just evaluating the `$condition` variable.</span></span> <span data-ttu-id="62a4b-121">`$true` であったため、スクリプト ブロック内の `Write-Output` コマンドが実行されたでしょう。</span><span class="sxs-lookup"><span data-stu-id="62a4b-121">It was `$true` and would have executed the `Write-Output` command inside the scriptblock.</span></span>

<span data-ttu-id="62a4b-122">一部の言語では、`if` ステートメントの後に単一行のコードを配置し、それを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-122">In some languages, you can place a single line of code after the `if` statement and it gets executed.</span></span> <span data-ttu-id="62a4b-123">それは PowerShell には当てはまりません。</span><span class="sxs-lookup"><span data-stu-id="62a4b-123">That isn't the case in PowerShell.</span></span> <span data-ttu-id="62a4b-124">正常に動作するには、中かっこで囲んだ完全な `scriptblock` を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-124">You must provide a full `scriptblock` with braces for it to work correctly.</span></span>

## <a name="comparison-operators"></a><span data-ttu-id="62a4b-125">比較演算子</span><span class="sxs-lookup"><span data-stu-id="62a4b-125">Comparison operators</span></span>

<span data-ttu-id="62a4b-126">`if` ステートメントの最も一般的な用途は、2 つの項目を互いに比較することです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-126">The most common use of the `if` statement for is comparing two items with each other.</span></span> <span data-ttu-id="62a4b-127">PowerShell には、さまざまな比較シナリオのために特別な演算子が用意されています。</span><span class="sxs-lookup"><span data-stu-id="62a4b-127">PowerShell has special operators for different comparison scenarios.</span></span> <span data-ttu-id="62a4b-128">比較演算子を使用する場合、左側の値が右側の値と比較されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-128">When you use a comparison operator, the value on the left-hand side is compared to the value on the right-hand side.</span></span>

### <a name="-eq-for-equality"></a><span data-ttu-id="62a4b-129">-eq (等価性)</span><span class="sxs-lookup"><span data-stu-id="62a4b-129">-eq for equality</span></span>

<span data-ttu-id="62a4b-130">`-eq` は、値が互いに等しいことを確認するため、2 つの値の間で等価性のチェックを行います。</span><span class="sxs-lookup"><span data-stu-id="62a4b-130">The `-eq` does an equality check between two values to make sure they're equal to each other.</span></span>

```powershell
$value = Get-MysteryValue
if ( 5 -eq $value )
{
    # do something
}
```

<span data-ttu-id="62a4b-131">この例では、既知の値 `5` を取得し、それを `$value` と比較して、それらが一致しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-131">In this example, I'm taking a known value of `5` and comparing it to my `$value` to see if they match.</span></span>

<span data-ttu-id="62a4b-132">考えられるユース ケースの 1 つは、値に対してアクションを実行する前に、値の状態をチェックすることです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-132">One possible use case is to check the status of a value before you take an action on it.</span></span> <span data-ttu-id="62a4b-133">サービスを取得し、その状態が実行中であることを確認してから、それに対して `Restart-Service` を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-133">You could get a service and check that the status was running before you called `Restart-Service` on it.</span></span>

<span data-ttu-id="62a4b-134">C# のような他の言語では、等価性のチェックに `==` を使用する (例: `5 == $value`) のが一般的ですが、これは PowerShell では機能しません。</span><span class="sxs-lookup"><span data-stu-id="62a4b-134">It's common in other languages like C# to use `==` for equality (ex: `5 == $value`) but that doesn't work with PowerShell.</span></span> <span data-ttu-id="62a4b-135">別のよくある誤りは、変数に値を代入するために予約されている等号 (例: `5 = $value`) を使用することです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-135">Another common mistake that people make is to use the equals sign (ex: `5 = $value`) that is reserved for assigning values to variables.</span></span> <span data-ttu-id="62a4b-136">既知の値を左側に配置することで、その誤りをより起こしにくくします。</span><span class="sxs-lookup"><span data-stu-id="62a4b-136">By placing your known value on the left, it makes that mistaken more awkward to make.</span></span>

<span data-ttu-id="62a4b-137">この演算子 (およびその他) には、いくつかのバリエーションがあります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-137">This operator (and others) has a few variations.</span></span>

- <span data-ttu-id="62a4b-138">`-eq` (大文字と小文字が区別されない等価性)</span><span class="sxs-lookup"><span data-stu-id="62a4b-138">`-eq` case-insensitive equality</span></span>
- <span data-ttu-id="62a4b-139">`-ieq` (大文字と小文字が区別されない等価性)</span><span class="sxs-lookup"><span data-stu-id="62a4b-139">`-ieq` case-insensitive equality</span></span>
- <span data-ttu-id="62a4b-140">`-ceq` (大文字と小文字が区別される等価性)</span><span class="sxs-lookup"><span data-stu-id="62a4b-140">`-ceq` case-sensitive equality</span></span>

### <a name="-ne-not-equal"></a><span data-ttu-id="62a4b-141">-ne (等しくない)</span><span class="sxs-lookup"><span data-stu-id="62a4b-141">-ne not equal</span></span>

<span data-ttu-id="62a4b-142">多くの演算子には、逆の結果をチェックする、関連する演算子があります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-142">Many operators have a related operator that is checking for the opposite result.</span></span> <span data-ttu-id="62a4b-143">`-ne` は、値が互いに等しくないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-143">`-ne` verifies that the values don't equal each other.</span></span>

```powershell
if ( 5 -ne $value )
{
    # do something
}
```

<span data-ttu-id="62a4b-144">値が `5` でない場合にのみアクションが実行されるようにするには、これを使用します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-144">Use this to make sure that the action only executes if the value isn't `5`.</span></span> <span data-ttu-id="62a4b-145">適切なユース ケースとしては、サービスが実行中の状態かどうかを確認してからその起動を試みる場合が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-145">A good use-cases where would be to check if a service was in the running state before you try to start it.</span></span>

<span data-ttu-id="62a4b-146">**バリエーション:**</span><span class="sxs-lookup"><span data-stu-id="62a4b-146">**Variations:**</span></span>

- <span data-ttu-id="62a4b-147">`-ne` (大文字と小文字が区別されない、等しくない)</span><span class="sxs-lookup"><span data-stu-id="62a4b-147">`-ne` case-insensitive not equal</span></span>
- <span data-ttu-id="62a4b-148">`-ine` (大文字と小文字が区別されない、等しくない)</span><span class="sxs-lookup"><span data-stu-id="62a4b-148">`-ine` case-insensitive not equal</span></span>
- <span data-ttu-id="62a4b-149">`-cne` (大文字と小文字が区別される、等しくない)</span><span class="sxs-lookup"><span data-stu-id="62a4b-149">`-cne` case-sensitive not equal</span></span>

<span data-ttu-id="62a4b-150">これらは、`-eq` の逆のバリエーションです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-150">These are inverse variations of `-eq`.</span></span> <span data-ttu-id="62a4b-151">私は、他の演算子のバリエーションをリストにするときには、これらの型を一緒にグループ化します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-151">I'll group these types together when I list variations for other operators.</span></span>

### <a name="-gt--ge--lt--le-for-greater-than-or-less-than"></a><span data-ttu-id="62a4b-152">-gt -ge -lt -le (より大きい、より小さい)</span><span class="sxs-lookup"><span data-stu-id="62a4b-152">-gt -ge -lt -le for greater than or less than</span></span>

<span data-ttu-id="62a4b-153">これらの演算子は、ある値が別の値より大きいか小さいかを調べて確認するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-153">These operators are used when checking to see if a value is larger or smaller than another value.</span></span>
<span data-ttu-id="62a4b-154">`-gt -ge -lt -le` は、GreaterThan、GreaterThanOrEqual、LessThan、および LessThanOrEqual を表しています。</span><span class="sxs-lookup"><span data-stu-id="62a4b-154">The `-gt -ge -lt -le` stand for GreaterThan, GreaterThanOrEqual, LessThan, and LessThanOrEqual.</span></span>

```powershell
if ( $value -gt 5 )
{
    # do something
}
```

<span data-ttu-id="62a4b-155">**バリエーション:**</span><span class="sxs-lookup"><span data-stu-id="62a4b-155">**Variations:**</span></span>

- <span data-ttu-id="62a4b-156">`-gt` (より大きい)</span><span class="sxs-lookup"><span data-stu-id="62a4b-156">`-gt` greater than</span></span>
- <span data-ttu-id="62a4b-157">`-igt` (より大きい、大文字と小文字が区別されない)</span><span class="sxs-lookup"><span data-stu-id="62a4b-157">`-igt` greater than, case-insensitive</span></span>
- <span data-ttu-id="62a4b-158">`-cgt` (より大きい、大文字と小文字が区別される)</span><span class="sxs-lookup"><span data-stu-id="62a4b-158">`-cgt` greater than, case-sensitive</span></span>
- <span data-ttu-id="62a4b-159">`-ge` (以上)</span><span class="sxs-lookup"><span data-stu-id="62a4b-159">`-ge` greater than or equal</span></span>
- <span data-ttu-id="62a4b-160">`-ige` (以上、大文字と小文字が区別されない)</span><span class="sxs-lookup"><span data-stu-id="62a4b-160">`-ige` greater than or equal, case-insensitive</span></span>
- <span data-ttu-id="62a4b-161">`-cge` (以上、大文字と小文字が区別される)</span><span class="sxs-lookup"><span data-stu-id="62a4b-161">`-cge` greater than or equal, case-sensitive</span></span>
- <span data-ttu-id="62a4b-162">`-lt` (より小さい)</span><span class="sxs-lookup"><span data-stu-id="62a4b-162">`-lt` less than</span></span>
- <span data-ttu-id="62a4b-163">`-ilt` (より小さい、大文字と小文字が区別されない)</span><span class="sxs-lookup"><span data-stu-id="62a4b-163">`-ilt` less than, case-insensitive</span></span>
- <span data-ttu-id="62a4b-164">`-clt` (より小さい、大文字と小文字が区別される)</span><span class="sxs-lookup"><span data-stu-id="62a4b-164">`-clt` less than, case-sensitive</span></span>
- <span data-ttu-id="62a4b-165">`-le` (以下)</span><span class="sxs-lookup"><span data-stu-id="62a4b-165">`-le` less than or equal</span></span>
- <span data-ttu-id="62a4b-166">`-ile` (以下、大文字と小文字が区別されない)</span><span class="sxs-lookup"><span data-stu-id="62a4b-166">`-ile` less than or equal, case-insensitive</span></span>
- <span data-ttu-id="62a4b-167">`-cle` (以下、大文字と小文字が区別される)</span><span class="sxs-lookup"><span data-stu-id="62a4b-167">`-cle` less than or equal, case-sensitive</span></span>

<span data-ttu-id="62a4b-168">私には、これらの演算子で、大文字と小文字を区別するオプション、区別しないオプションを使用する理由がわかりません。</span><span class="sxs-lookup"><span data-stu-id="62a4b-168">I don't know why you would use case-sensitive and insensitive options for these operators.</span></span>

### <a name="-like-wildcard-matches"></a><span data-ttu-id="62a4b-169">-like (ワイルドカードの一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-169">-like wildcard matches</span></span>

<span data-ttu-id="62a4b-170">PowerShell には、ワイルドカード ベースの独自のパターン一致構文があり、`-like` 演算子と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-170">PowerShell has its own wildcard-based pattern matching syntax and you can use it with the `-like` operator.</span></span> <span data-ttu-id="62a4b-171">これらのワイルドカード パターンは、かなり基本的なものです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-171">These wildcard patterns are fairly basic.</span></span>

- <span data-ttu-id="62a4b-172">`?` は任意の 1 文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-172">`?` matches any single character</span></span>
- <span data-ttu-id="62a4b-173">`*` は任意の数の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-173">`*` matches any number of characters</span></span>

```powershell
$value = 'S-ATX-SQL01'
if ( $value -like 'S-*-SQL??')
{
    # do something
}
```

<span data-ttu-id="62a4b-174">指摘しておくことが重要なのは、パターンは文字列全体に一致するという点です。</span><span class="sxs-lookup"><span data-stu-id="62a4b-174">It's important to point out that the pattern matches the whole string.</span></span> <span data-ttu-id="62a4b-175">文字列の途中にある何かと一致させる必要がある場合は、文字列の両端に `*` を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-175">If you need to match something in the middle of the string, you need to place the `*` on both ends of the string.</span></span>

```powershell
$value = 'S-ATX-SQL02'
if ( $value -like '*SQL*')
{
    # do something
}
```

<span data-ttu-id="62a4b-176">**バリエーション:**</span><span class="sxs-lookup"><span data-stu-id="62a4b-176">**Variations:**</span></span>

- <span data-ttu-id="62a4b-177">`-like` (大文字と小文字が区別されないワイルドカード)</span><span class="sxs-lookup"><span data-stu-id="62a4b-177">`-like` case-insensitive wildcard</span></span>
- <span data-ttu-id="62a4b-178">`-ilike` (大文字と小文字が区別されないワイルドカード)</span><span class="sxs-lookup"><span data-stu-id="62a4b-178">`-ilike` case-insensitive wildcard</span></span>
- <span data-ttu-id="62a4b-179">`-clike` (大文字と小文字が区別されるワイルドカード)</span><span class="sxs-lookup"><span data-stu-id="62a4b-179">`-clike` case-sensitive wildcard</span></span>
- <span data-ttu-id="62a4b-180">`-notlike` (大文字と小文字が区別されないワイルドカード不一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-180">`-notlike` case-insensitive wildcard not matched</span></span>
- <span data-ttu-id="62a4b-181">`-inotlike` (大文字と小文字が区別されないワイルドカード不一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-181">`-inotlike` case-insensitive wildcard not matched</span></span>
- <span data-ttu-id="62a4b-182">`-cnotlike` (大文字と小文字が区別されるワイルドカード不一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-182">`-cnotlike` case-sensitive wildcard not matched</span></span>

### <a name="-match-regular-expression"></a><span data-ttu-id="62a4b-183">-match (正規表現)</span><span class="sxs-lookup"><span data-stu-id="62a4b-183">-match regular expression</span></span>

<span data-ttu-id="62a4b-184">`-match` 演算子を使用すると、正規表現に基づく一致があるか、文字列を調べられます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-184">The `-match` operator allows you to check a string for a regular-expression-based match.</span></span> <span data-ttu-id="62a4b-185">これは、ワイルドカード パターンでは十分な柔軟性が得られない場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-185">Use this when the wildcard patterns aren't flexible enough for you.</span></span>

```powershell
$value = 'S-ATX-SQL01'
if ( $value -match 'S-\w\w\w-SQL\d\d')
{
    # do something
}
```

<span data-ttu-id="62a4b-186">正規表現パターンは、既定では文字列内の任意の場所に一致します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-186">A regex pattern matches anywhere in the string by default.</span></span> <span data-ttu-id="62a4b-187">そのため次のように、一致させる部分文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-187">So you can specify a substring that you want matched like this:</span></span>

```powershell
$value = 'S-ATX-SQL01'
if ( $value -match 'SQL')
{
    # do something
}
```

<span data-ttu-id="62a4b-188">正規表現は独自の複雑な言語であり、詳しく調べる価値があります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-188">Regex is a complex language of its own and worth looking into.</span></span> <span data-ttu-id="62a4b-189">私は別の記事で、`-match` の詳細と[正規表現を使用するさまざまな方法][]について説明しています。</span><span class="sxs-lookup"><span data-stu-id="62a4b-189">I talk more about `-match` and [the many ways to use regex][] in another article.</span></span>

<span data-ttu-id="62a4b-190">**バリエーション:**</span><span class="sxs-lookup"><span data-stu-id="62a4b-190">**Variations:**</span></span>

- <span data-ttu-id="62a4b-191">`-match` (大文字と小文字が区別されない正規表現)</span><span class="sxs-lookup"><span data-stu-id="62a4b-191">`-match` case-insensitive regex</span></span>
- <span data-ttu-id="62a4b-192">`-imatch` (大文字と小文字が区別されない正規表現)</span><span class="sxs-lookup"><span data-stu-id="62a4b-192">`-imatch` case-insensitive regex</span></span>
- <span data-ttu-id="62a4b-193">`-cmatch` (大文字と小文字が区別される正規表現)</span><span class="sxs-lookup"><span data-stu-id="62a4b-193">`-cmatch` case-sensitive regex</span></span>
- <span data-ttu-id="62a4b-194">`-notmatch` (大文字と小文字が区別されない正規表現不一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-194">`-notmatch` case-insensitive regex not matched</span></span>
- <span data-ttu-id="62a4b-195">`-inotmatch` (大文字と小文字が区別されない正規表現不一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-195">`-inotmatch` case-insensitive regex not matched</span></span>
- <span data-ttu-id="62a4b-196">`-cnotmatch` (大文字と小文字が区別される正規表現不一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-196">`-cnotmatch` case-sensitive regex not matched</span></span>

### <a name="-is-of-type"></a><span data-ttu-id="62a4b-197">-is (型)</span><span class="sxs-lookup"><span data-stu-id="62a4b-197">-is of type</span></span>

<span data-ttu-id="62a4b-198">`-is` 演算子を使用して値の型を調べられます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-198">You can check a value's type with the `-is` operator.</span></span>

```powershell
if ( $value -is [string] )
{
    # do something
}
```

<span data-ttu-id="62a4b-199">これは、複数のクラスを使用している場合や、パイプライン上でさまざまなオブジェクトを受け入れている場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-199">You may use this if you're working with classes or accepting various objects over the pipeline.</span></span> <span data-ttu-id="62a4b-200">入力として、サービスまたはサービス名のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-200">You could have either a service or a service name as your input.</span></span> <span data-ttu-id="62a4b-201">次に、サービスがあるかどうかを調べて、名前しかない場合はサービスをフェッチします。</span><span class="sxs-lookup"><span data-stu-id="62a4b-201">Then check to see if you have a service and fetch the service if you only have the name.</span></span>

```powershell
if ( $Service -isnot [System.ServiceProcess.ServiceController] )
{
    $Service = Get-Service -Name $Service
}
```

<span data-ttu-id="62a4b-202">**バリエーション:**</span><span class="sxs-lookup"><span data-stu-id="62a4b-202">**Variations:**</span></span>

- <span data-ttu-id="62a4b-203">`-is` (型)</span><span class="sxs-lookup"><span data-stu-id="62a4b-203">`-is` of type</span></span>
- <span data-ttu-id="62a4b-204">`-isnot` (型でない)</span><span class="sxs-lookup"><span data-stu-id="62a4b-204">`-isnot` not of type</span></span>

## <a name="collection-operators"></a><span data-ttu-id="62a4b-205">コレクション演算子</span><span class="sxs-lookup"><span data-stu-id="62a4b-205">Collection operators</span></span>

<span data-ttu-id="62a4b-206">1 つの値を指定して前出の演算子を使用すると、結果は `$true` または `$false` になります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-206">When you use the previous operators with a single value, the result is `$true` or `$false`.</span></span> <span data-ttu-id="62a4b-207">これは、コレクションの操作時には少し異なる方法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-207">This is handled slightly differently when working with a collection.</span></span> <span data-ttu-id="62a4b-208">コレクション内の各項目が評価されて、演算子からは、`$true` に評価されるすべての値が返されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-208">Each item in the collection gets evaluated and the operator returns every value that evaluates to `$true`.</span></span>

```powershell
PS> 1,2,3,4 -eq 3
3
```

<span data-ttu-id="62a4b-209">これは、`if` ステートメントでも正しく機能します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-209">This still works correctly in a `if` statement.</span></span> <span data-ttu-id="62a4b-210">そのため、演算子によって値が返されると、ステートメント全体は `$true` になります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-210">So a value is returned by your operator, then the whole statement is `$true`.</span></span>

```powershell
$array = 1..6
if ( $array -gt 3 )
{
    # do something
}
```

<span data-ttu-id="62a4b-211">これについては、指摘する必要がある小さな罠が細部に潜んでいます。このように `-ne` 演算子を使用すると、誤ってロジックを逆に考えてしまいやすくなります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-211">There's one small trap hiding in the details here that I need to point out. When using the `-ne` operator this way, it's easy to mistakenly look at the logic backwards.</span></span> <span data-ttu-id="62a4b-212">コレクションで `-ne` を使用すると、コレクション内のいずれかの項目が値と一致しない場合に、`$true` が返されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-212">Using `-ne` with a collection returns `$true` if any item in the collection doesn't match your value.</span></span>

```powershell
PS> 1,2,3 -ne 4
1
2
3
```

<span data-ttu-id="62a4b-213">これは巧みな技法のようですが、これをより効率的に処理する演算子 `-contains` および `-in` が用意されています。</span><span class="sxs-lookup"><span data-stu-id="62a4b-213">This may look like a clever trick, but we have operators `-contains` and `-in` that handle this more efficiently.</span></span> <span data-ttu-id="62a4b-214">そして、期待したことは `-notcontains` によって行われます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-214">And `-notcontains` does what you expect.</span></span>

### <a name="-contains"></a><span data-ttu-id="62a4b-215">-contains</span><span class="sxs-lookup"><span data-stu-id="62a4b-215">-contains</span></span>

<span data-ttu-id="62a4b-216">`-contains` 演算子は、値があるか、コレクションを調べます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-216">The `-contains` operator checks the collection for your value.</span></span> <span data-ttu-id="62a4b-217">一致が見つかるとすぐに `$true` が返されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-217">As soon as it finds a match, it returns `$true`.</span></span>

```powershell
$array = 1..6
if ( $array -contains 3 )
{
    # do something
}
```

<span data-ttu-id="62a4b-218">これは、コレクションに値が含まれているかどうかを確認する場合の推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="62a4b-218">This is the preferred way to see if a collection contains your value.</span></span> <span data-ttu-id="62a4b-219">`Where-Object` (または `-eq`) を使用すると、毎回リスト全体が処理され、大幅に低速になります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-219">Using `Where-Object` (or `-eq`) walks the entire list every time and is significantly slower.</span></span>

<span data-ttu-id="62a4b-220">**バリエーション:**</span><span class="sxs-lookup"><span data-stu-id="62a4b-220">**Variations:**</span></span>

- <span data-ttu-id="62a4b-221">`-contains` (大文字と小文字が区別されない一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-221">`-contains` case-insensitive match</span></span>
- <span data-ttu-id="62a4b-222">`-icontains` (大文字と小文字が区別されない一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-222">`-icontains` case-insensitive match</span></span>
- <span data-ttu-id="62a4b-223">`-ccontains` (大文字と小文字が区別される一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-223">`-ccontains` case-sensitive match</span></span>
- <span data-ttu-id="62a4b-224">`-notcontains` (大文字と小文字が区別されない不一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-224">`-notcontains` case-insensitive not matched</span></span>
- <span data-ttu-id="62a4b-225">`-inotcontains` (大文字と小文字が区別されない不一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-225">`-inotcontains` case-insensitive not matched</span></span>
- <span data-ttu-id="62a4b-226">`-cnotcontains` (大文字と小文字が区別される不一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-226">`-cnotcontains` case-sensitive not matched</span></span>

### <a name="-in"></a><span data-ttu-id="62a4b-227">-in</span><span class="sxs-lookup"><span data-stu-id="62a4b-227">-in</span></span>

<span data-ttu-id="62a4b-228">`-in` 演算子は、右側にコレクションがあること以外は、`-contains` 演算子とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-228">The `-in` operator is just like the `-contains` operator except the collection is on the right-hand side.</span></span>

```powershell
$array = 1..6
if ( 3 -in $array )
{
    # do something
}
```

<span data-ttu-id="62a4b-229">**バリエーション:**</span><span class="sxs-lookup"><span data-stu-id="62a4b-229">**Variations:**</span></span>

- <span data-ttu-id="62a4b-230">`-in` (大文字と小文字が区別されない一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-230">`-in` case-insensitive match</span></span>
- <span data-ttu-id="62a4b-231">`-iin` (大文字と小文字が区別されない一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-231">`-iin` case-insensitive match</span></span>
- <span data-ttu-id="62a4b-232">`-cin` (大文字と小文字が区別される一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-232">`-cin` case-sensitive match</span></span>
- <span data-ttu-id="62a4b-233">`-notin` (大文字と小文字が区別されない不一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-233">`-notin` case-insensitive not matched</span></span>
- <span data-ttu-id="62a4b-234">`-inotin` (大文字と小文字が区別されない不一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-234">`-inotin` case-insensitive not matched</span></span>
- <span data-ttu-id="62a4b-235">`-cnotin` (大文字と小文字が区別される不一致)</span><span class="sxs-lookup"><span data-stu-id="62a4b-235">`-cnotin` case-sensitive not matched</span></span>

## <a name="logical-operators"></a><span data-ttu-id="62a4b-236">論理演算子</span><span class="sxs-lookup"><span data-stu-id="62a4b-236">Logical operators</span></span>

<span data-ttu-id="62a4b-237">論理演算子は、他の式を反転または結合するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-237">Logical operators are used to invert or combine other expressions.</span></span>

### <a name="-not"></a><span data-ttu-id="62a4b-238">-not</span><span class="sxs-lookup"><span data-stu-id="62a4b-238">-not</span></span>

<span data-ttu-id="62a4b-239">`-not` 演算子は、式を `$false` から `$true` に、または `$true` から `$false` に反転させます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-239">The `-not` operator flips an expression from `$false` to `$true` or from `$true` to `$false`.</span></span> <span data-ttu-id="62a4b-240">次に、`Test-Path` が `$false` であるときにアクションを実行する例を示します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-240">Here is an example where we want to perform an action when `Test-Path` is `$false`.</span></span>

```powershell
if ( -not ( Test-Path -Path $path ) )
```

<span data-ttu-id="62a4b-241">説明してきたほとんどの演算子には、`-not` 演算子を使用する必要がないバリエーションがあります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-241">Most of the operators we talked about do have a variation where you do not need to use the `-not` operator.</span></span> <span data-ttu-id="62a4b-242">しかし、それでも役に立つ場面があります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-242">But there are still times it is useful.</span></span>

### <a name="-operator"></a><span data-ttu-id="62a4b-243">!</span><span class="sxs-lookup"><span data-stu-id="62a4b-243">!</span></span> <span data-ttu-id="62a4b-244">operator</span><span class="sxs-lookup"><span data-stu-id="62a4b-244">operator</span></span>

<span data-ttu-id="62a4b-245">`-not` の別名として `!` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-245">You can use `!` as an alias for `-not`.</span></span>

```powershell
if ( -not $value ){}
if ( !$value ){}
```

<span data-ttu-id="62a4b-246">C# などの別の言語が専門のユーザーは、`!` をより多用することに気付くかも知れません。</span><span class="sxs-lookup"><span data-stu-id="62a4b-246">You may see `!` used more by people that come from another languages like C#.</span></span> <span data-ttu-id="62a4b-247">私は、スクリプトをすばやく調べるときに見にくいと感じるため、これを文字で入力することを好んでいます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-247">I prefer to type it out because I find it hard to see when quickly looking at my scripts.</span></span>

### <a name="-and"></a><span data-ttu-id="62a4b-248">-and</span><span class="sxs-lookup"><span data-stu-id="62a4b-248">-and</span></span>

<span data-ttu-id="62a4b-249">式を `-and` 演算子と組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-249">You can combine expressions with the `-and` operator.</span></span> <span data-ttu-id="62a4b-250">それを行うときには、式全体が `$true` になるには、両方の側が `$true` になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-250">When you do that, both sides need to be `$true` for the whole expression to be `$true`.</span></span>

```powershell
if ( ($age -gt 13) -and ($age -lt 55) )
```

<span data-ttu-id="62a4b-251">この例では、`$age` は左側で 13 以上、右側で 55 未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-251">In that example, `$age` must be 13 or older for the left side and less than 55 for the right side.</span></span> <span data-ttu-id="62a4b-252">その例で、より明確にするために私がかっこを余分に追加しましたが、式が単純である限り、これらのかっこは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="62a4b-252">I added extra parentheses to make it clearer in that example but they're optional as long as the expression is simple.</span></span> <span data-ttu-id="62a4b-253">それらがない同じ例を示します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-253">Here is the same example without them.</span></span>

```powershell
if ( $age -gt 13 -and $age -lt 55 )
```

<span data-ttu-id="62a4b-254">評価は左から右に実行されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-254">Evaluation happens from left to right.</span></span> <span data-ttu-id="62a4b-255">最初の項目が `$false` に評価された場合は早期に終了し、右側の比較は実行されません。</span><span class="sxs-lookup"><span data-stu-id="62a4b-255">If the first item evaluates to `$false`, it exits early and doesn't perform the right comparison.</span></span> <span data-ttu-id="62a4b-256">これは、使用する前に値が存在することを確認する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="62a4b-256">This is handy when you need to make sure a value exists before you use it.</span></span> <span data-ttu-id="62a4b-257">たとえば、`$null` パスを指定した場合、`Test-Path` からエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-257">For example, `Test-Path` throws an error if you give it a `$null` path.</span></span>

```powershell
if ( $null -ne $path -and (Test-Path -Path $path) )
```

### <a name="-or"></a><span data-ttu-id="62a4b-258">-or</span><span class="sxs-lookup"><span data-stu-id="62a4b-258">-or</span></span>

<span data-ttu-id="62a4b-259">`-or` を使用すると、2 つの式を指定し、その 1 つが `$true` である場合に `$true` を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-259">The `-or` allows for you to specify two expressions and returns `$true` if either one of them is `$true`.</span></span>

```powershell
if ( $age -le 13 -or $age -ge 55 )
```

<span data-ttu-id="62a4b-260">`-and` 演算子と同様に、評価は左から右に実行されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-260">Just like with the `-and` operator, the evaluation happens from left to right.</span></span> <span data-ttu-id="62a4b-261">最初の部分が `$true` である場合は、ステートメント全体が `$true` になるので、式の残りの部分は処理されません。</span><span class="sxs-lookup"><span data-stu-id="62a4b-261">Except that if the first part is `$true`, then the whole statement is `$true` and it doesn't process the rest of the expression.</span></span>

<span data-ttu-id="62a4b-262">これらの演算子の構文がどのように機能するかもメモしておいてください。</span><span class="sxs-lookup"><span data-stu-id="62a4b-262">Also make note of how the syntax works for these operators.</span></span> <span data-ttu-id="62a4b-263">2 つの別個の式が必要です。</span><span class="sxs-lookup"><span data-stu-id="62a4b-263">You need two separate expressions.</span></span> <span data-ttu-id="62a4b-264">私は、自分のミスに気付かずに、このようなこと (`$value -eq 5 -or 6`) を実行しようとしたユーザーを見てきました。</span><span class="sxs-lookup"><span data-stu-id="62a4b-264">I have seen users try to do something like this `$value -eq 5 -or 6` without realizing their mistake.</span></span>

### <a name="-xor-exclusive-or"></a><span data-ttu-id="62a4b-265">-xor (排他的 OR)</span><span class="sxs-lookup"><span data-stu-id="62a4b-265">-xor exclusive or</span></span>

<span data-ttu-id="62a4b-266">これは少し変わっています。</span><span class="sxs-lookup"><span data-stu-id="62a4b-266">This one is a little unusual.</span></span> <span data-ttu-id="62a4b-267">`-xor` では、1 つの式だけが `$true` に評価されることができます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-267">`-xor` allows only one expression to evaluate to `$true`.</span></span> <span data-ttu-id="62a4b-268">そのため、両方の項目が `$false` か、両方の項目が `$true` である場合に、式全体が `$false` になります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-268">So if both items are `$false` or both items are `$true`, then the whole expression is `$false`.</span></span> <span data-ttu-id="62a4b-269">式の結果が異なるときにだけ、式が `$true` になる、というのがこれの別の見方です。</span><span class="sxs-lookup"><span data-stu-id="62a4b-269">Another way to look at this is the expression is only `$true` when the results of the expression are different.</span></span>

<span data-ttu-id="62a4b-270">この論理演算子を使用することはめったになく、私はこれを使用する理由について、適切な例を思い付くことができません。</span><span class="sxs-lookup"><span data-stu-id="62a4b-270">It's rare that anyone would ever use this logical operator and I can't think up a good example as to why I would ever use it.</span></span>

## <a name="bitwise-operators"></a><span data-ttu-id="62a4b-271">ビットごとの演算子</span><span class="sxs-lookup"><span data-stu-id="62a4b-271">Bitwise operators</span></span>

<span data-ttu-id="62a4b-272">ビットごとの演算子は、値内のビットに対して演算を実行し、結果として新しい値を生成します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-272">Bitwise operators perform calculations on the bits within the values and produce a new value as the result.</span></span> <span data-ttu-id="62a4b-273">[ビットごとの演算子][]について教えることは、この記事の範囲外ですが、次にそれらのリストを示します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-273">Teaching [bitwise operators][] is beyond the scope of this article, but here is the list the them.</span></span>

- <span data-ttu-id="62a4b-274">`-band` (2 項 AND)</span><span class="sxs-lookup"><span data-stu-id="62a4b-274">`-band` binary AND</span></span>
- <span data-ttu-id="62a4b-275">`-bor` (2 項 OR)</span><span class="sxs-lookup"><span data-stu-id="62a4b-275">`-bor` binary OR</span></span>
- <span data-ttu-id="62a4b-276">`-bxor` (2 項排他的 OR)</span><span class="sxs-lookup"><span data-stu-id="62a4b-276">`-bxor` binary exclusive OR</span></span>
- <span data-ttu-id="62a4b-277">`-bnot` (2 項 NOT)</span><span class="sxs-lookup"><span data-stu-id="62a4b-277">`-bnot` binary NOT</span></span>
- <span data-ttu-id="62a4b-278">`-shl` (左シフト)</span><span class="sxs-lookup"><span data-stu-id="62a4b-278">`-shl` shift left</span></span>
- <span data-ttu-id="62a4b-279">`-shr` (右シフト)</span><span class="sxs-lookup"><span data-stu-id="62a4b-279">`-shr` shift right</span></span>

## <a name="powershell-expressions"></a><span data-ttu-id="62a4b-280">PowerShell の式</span><span class="sxs-lookup"><span data-stu-id="62a4b-280">PowerShell expressions</span></span>

<span data-ttu-id="62a4b-281">条件ステートメント内で通常の PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-281">We can use normal PowerShell inside the condition statement.</span></span>

```powershell
if ( Test-Path -Path $Path )
```

<span data-ttu-id="62a4b-282">`Test-Path` は、実行されると `$true` または `$false` を返します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-282">`Test-Path` returns `$true` or `$false` when it executes.</span></span> <span data-ttu-id="62a4b-283">これは、他の値を返すコマンドにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-283">This also applies to commands that return other values.</span></span>

```powershell
if ( Get-Process Notepad* )
```

<span data-ttu-id="62a4b-284">返されたプロセスがある場合は `$true` に、何もない場合は `$false` に評価されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-284">It evaluates to `$true` if there's a returned process and `$false` if there'sn'thing.</span></span> <span data-ttu-id="62a4b-285">次のようにパイプライン式やその他の PowerShell ステートメントを使用することは、完全に有効です。</span><span class="sxs-lookup"><span data-stu-id="62a4b-285">It's perfectly valid to use pipeline expressions or other PowerShell statements like this:</span></span>

```powershell
if ( Get-Process | Where Name -eq Notepad )
```

<span data-ttu-id="62a4b-286">これらの式は、`-and` 演算子と `-or` 演算子を使用して相互に結合できますが、かっこを使用して部分式に分割することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-286">These expressions can be combined with each other with the `-and` and `-or` operators, but you may have to use parenthesis to break them into subexpressions.</span></span>

```powershell
if ( (Get-Process) -and (Get-Service) )
```

### <a name="checking-for-null"></a><span data-ttu-id="62a4b-287">$null の確認</span><span class="sxs-lookup"><span data-stu-id="62a4b-287">Checking for $null</span></span>

<span data-ttu-id="62a4b-288">結果がなかったり、`if` ステートメントで `$null` 値が `$false` と評価されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-288">Having a no result or a `$null` value evaluates to `$false` in the `if` statement.</span></span> <span data-ttu-id="62a4b-289">`$null` を特に調べる場合は、左側に `$null` を配置することがベスト プラクティスです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-289">When checking specifically for `$null`, it's a best practice to place the `$null` on the left-hand side.</span></span>

```powershell
if ( $null -eq $value )
```

<span data-ttu-id="62a4b-290">PowerShell で `$null` 値を扱う際には、かなり多くの微妙な差異があります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-290">There are quite a few nuances when dealing with `$null` values in PowerShell.</span></span> <span data-ttu-id="62a4b-291">詳細についてお知りになりたい場合は、[$null について知りたかったことのすべて][]に関する記事があります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-291">If you're interested in diving deeper, I have an article about [everything you wanted to know about $null][].</span></span>

### <a name="variable-assignment"></a><span data-ttu-id="62a4b-292">変数の代入</span><span class="sxs-lookup"><span data-stu-id="62a4b-292">Variable assignment</span></span>

<span data-ttu-id="62a4b-293">[Prasoon Karunan V][] に思い出させてもらうまで、この部分を追加するのをほとんど忘れていました。</span><span class="sxs-lookup"><span data-stu-id="62a4b-293">I almost forgot to add this one until [Prasoon Karunan V][] reminded me of it.</span></span>

```powershell
if ($process=Get-Process notepad -ErrorAction ignore) {$process} else {$false}
```

<span data-ttu-id="62a4b-294">通常、変数に値を代入するときに、値はパイプラインやコンソールに渡されません。</span><span class="sxs-lookup"><span data-stu-id="62a4b-294">Normally when you assign a value to a variable, the value isn't passed onto the pipeline or console.</span></span> <span data-ttu-id="62a4b-295">部分式で変数の代入を行うと、確かにパイプラインに渡されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-295">When you do a variable assignment in a sub expression, it does get passed on to the pipeline.</span></span>

```powershell
PS> $first = 1
PS> ($second = 2)
2
```

<span data-ttu-id="62a4b-296">`$first` の代入には出力がなく、`$second` の代入には出力がある様子を確認してください。</span><span class="sxs-lookup"><span data-stu-id="62a4b-296">See how the `$first` assignment has no output and the `$second` assignment does?</span></span> <span data-ttu-id="62a4b-297">`if` ステートメントで代入が行われると、上の `$second` の代入と同様に実行されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-297">When an assignment is done in an `if` statement, it executes just like the `$second` assignment above.</span></span> <span data-ttu-id="62a4b-298">次に、使用方法のはっきりした例を示します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-298">Here is a clean example on how you could use it:</span></span>

```powershell
if ( $process = Get-Process Notepad* )
{
    $process | Stop-Process
}
```

<span data-ttu-id="62a4b-299">`$process` が代入された値を取得すると、ステートメントは `$true` になり、`$process` は停止されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-299">If `$process` gets assigned a value, then the statement is `$true` and `$process` gets stopped.</span></span>

<span data-ttu-id="62a4b-300">これは等価性チェックではないため、`-eq` と混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="62a4b-300">Make sure you don't confuse this with `-eq` because this isn't an equality check.</span></span> <span data-ttu-id="62a4b-301">これは、ほとんどの人がこのように動作することを認識していない、わかりにくい機能です。</span><span class="sxs-lookup"><span data-stu-id="62a4b-301">This is a more obscure feature that most people don't realize works this way.</span></span>

## <a name="alternate-execution-path"></a><span data-ttu-id="62a4b-302">代替実行パス</span><span class="sxs-lookup"><span data-stu-id="62a4b-302">Alternate execution path</span></span>

<span data-ttu-id="62a4b-303">`if` ステートメントを使用すると、ステートメントが `$true` のときだけでなく、`$false` のときのためにもアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-303">The `if` statement allows you to specify an action for not only when the statement is `$true`, but also for when it's `$false`.</span></span> <span data-ttu-id="62a4b-304">ここで `else` ステートメントが登場します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-304">This is where the `else` statement comes into play.</span></span>

### <a name="else"></a><span data-ttu-id="62a4b-305">else</span><span class="sxs-lookup"><span data-stu-id="62a4b-305">else</span></span>

<span data-ttu-id="62a4b-306">`else` ステートメントは、使用されるときには常に `if` ステートメントの最後の部分です。</span><span class="sxs-lookup"><span data-stu-id="62a4b-306">The `else` statement is always the last part of the `if` statement when used.</span></span>

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
else
{
    Write-Warning "$path doesn't exist or isn't a file."
}
```

<span data-ttu-id="62a4b-307">この例では、`$path` を調べて、それがファイルであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-307">In this example, we check the `$path` to make sure it's a file.</span></span> <span data-ttu-id="62a4b-308">ファイルが見つかった場合は、それを移動します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-308">If we find the file, we move it.</span></span> <span data-ttu-id="62a4b-309">そうでない場合は、警告を書き出します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-309">If not, we write a warning.</span></span> <span data-ttu-id="62a4b-310">この種類の分岐ロジックは非常に一般的です。</span><span class="sxs-lookup"><span data-stu-id="62a4b-310">This type of branching logic is very common.</span></span>

### <a name="nested-if"></a><span data-ttu-id="62a4b-311">入れ子の if</span><span class="sxs-lookup"><span data-stu-id="62a4b-311">Nested if</span></span>

<span data-ttu-id="62a4b-312">`if` ステートメントと `else` ステートメントではスクリプト ブロックを取るため、その他の `if` ステートメントを含め、任意の PowerShell コマンドをブロック内に配置できます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-312">The `if` and `else` statements take a script block, so we can place any PowerShell command inside them, including another `if` statement.</span></span> <span data-ttu-id="62a4b-313">これにより、はるかに複雑なロジックを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-313">This allows you to make use of much more complicated logic.</span></span>

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
else
{
    if ( Test-Path -Path $Path )
    {
        Write-Warning "A file was required but a directory was found instead."
    }
    else
    {
        Write-Warning "$path could not be found."
    }
}
```

<span data-ttu-id="62a4b-314">この例では、まずハッピー パスをテストしてから、それに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-314">In this example, we test the happy path first and then take action on it.</span></span> <span data-ttu-id="62a4b-315">失敗した場合は別のチェックを行い、より詳細な情報を、ユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-315">If that fails, we do another check and to provide more detailed information to the user.</span></span>

### <a name="elseif"></a><span data-ttu-id="62a4b-316">elseif</span><span class="sxs-lookup"><span data-stu-id="62a4b-316">elseif</span></span>

<span data-ttu-id="62a4b-317">単一の条件付きチェックのみに限定されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="62a4b-317">We aren't limited to just a single conditional check.</span></span> <span data-ttu-id="62a4b-318">`elseif` ステートメントを使用してステートメントを入れ子にするのではなく、`if` ステートメントと `else` ステートメントをまとめて連結できます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-318">We can chain `if` and `else` statements together instead of nesting them by using the `elseif` statement.</span></span>

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
elseif ( Test-Path -Path $Path )
{
    Write-Warning "A file was required but a directory was found instead."
}
else
{
    Write-Warning "$path could not be found."
}
```

<span data-ttu-id="62a4b-319">実行は、最上部から最下部へと行われます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-319">The execution happens from the top to the bottom.</span></span> <span data-ttu-id="62a4b-320">最上位の `if` ステートメントが最初に評価されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-320">The top `if` statement is evaluated first.</span></span> <span data-ttu-id="62a4b-321">それが `$false` の場合は、リスト内で次にある `elseif` または `else` まで移動します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-321">If that is `$false`, then it moves down to the next `elseif` or `else` in the list.</span></span> <span data-ttu-id="62a4b-322">最後の `else` は、他のどれからも `$true` が返されない場合に実行する既定のアクションです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-322">That last `else` is the default action to take if none of the others return `$true`.</span></span>

### <a name="switch"></a><span data-ttu-id="62a4b-323">スイッチ</span><span class="sxs-lookup"><span data-stu-id="62a4b-323">switch</span></span>

<span data-ttu-id="62a4b-324">この時点で、`switch` ステートメントに触れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-324">At this point, I need to mention the `switch` statement.</span></span> <span data-ttu-id="62a4b-325">1 つの値で複数の比較を行うための代替構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-325">It provides an alternate syntax for doing multiple comparisons with a value.</span></span> <span data-ttu-id="62a4b-326">`switch` を使用して、式を指定し、その結果を異なるいくつかの値と比較します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-326">With the `switch`, you specify an expression and that result gets compared with several different values.</span></span> <span data-ttu-id="62a4b-327">それらの値のいずれかが一致すると、一致するコード ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-327">If one of those values match, the matching code block is executed.</span></span> <span data-ttu-id="62a4b-328">次の例を見てください。</span><span class="sxs-lookup"><span data-stu-id="62a4b-328">Take a look at this example:</span></span>

```powershell
$itemType = 'Role'
switch ( $itemType )
{
    'Component'
    {
        'is a component'
    }
    'Role'
    {
        'is a role'
    }
    'Location'
    {
        'is a location'
    }
}
```

<span data-ttu-id="62a4b-329">`$itemType` と一致する可能性がある候補の値が 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-329">There three possible values that can match the `$itemType`.</span></span> <span data-ttu-id="62a4b-330">この場合は `Role` と一致します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-330">In this case, it matches with `Role`.</span></span> <span data-ttu-id="62a4b-331">`switch` 演算子に触れる機会となるように、私は単純な例を使用しました。</span><span class="sxs-lookup"><span data-stu-id="62a4b-331">I used a simple example just to give you some exposure to the `switch` operator.</span></span> <span data-ttu-id="62a4b-332">別の記事で、[switch ステートメントについて知りたかったことのすべて][]について詳しく説明しています。</span><span class="sxs-lookup"><span data-stu-id="62a4b-332">I talk more about [everything you ever wanted to know about the switch statement][] in another article.</span></span>

## <a name="pipeline"></a><span data-ttu-id="62a4b-333">パイプライン</span><span class="sxs-lookup"><span data-stu-id="62a4b-333">Pipeline</span></span>

<span data-ttu-id="62a4b-334">パイプラインは、PowerShell の独特で重要な機能です。</span><span class="sxs-lookup"><span data-stu-id="62a4b-334">The pipeline is a unique and important feature of PowerShell.</span></span> <span data-ttu-id="62a4b-335">抑制されていない、または変数に代入されていない任意の値を、パイプライン内に配置します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-335">Any value that isn't suppressed or assigned to a variable gets placed in the pipeline.</span></span> <span data-ttu-id="62a4b-336">`if` では、常に明白であるとは限らない方法でパイプラインを利用する方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-336">The `if` provides us a way to take advantage of the pipeline in a way that isn't always obvious.</span></span>

```powershell
$discount = if ( $age -ge 55 )
{
    Get-SeniorDiscount
}
elseif ( $age -le 13 )
{
    Get-ChildDiscount
}
else
{
    0.00
}
```

<span data-ttu-id="62a4b-337">各スクリプト ブロックでは、コマンドの結果または値をパイプラインに配置しています。</span><span class="sxs-lookup"><span data-stu-id="62a4b-337">Each script block is placing the results the commands or the value into the pipeline.</span></span> <span data-ttu-id="62a4b-338">次に、if ステートメントの結果を `$discount` 変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-338">Then we assign the result of the if statement to the `$discount` variable.</span></span> <span data-ttu-id="62a4b-339">その例では、それらの値を直接、各スクリプト ブロック内の `$discount` 変数に簡単に割り当てることができました。</span><span class="sxs-lookup"><span data-stu-id="62a4b-339">That example could have just as easily assigned those values to the `$discount` variable directly in each scriptblock.</span></span> <span data-ttu-id="62a4b-340">私は、`if` ステートメントでこれを頻繁に使用しているとは言えませんが、確かにこれを最近使用した例があります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-340">I can't say that I use this with the `if` statement often, but I do have an example where I used this recently.</span></span>

### <a name="array-inline"></a><span data-ttu-id="62a4b-341">インライン配列</span><span class="sxs-lookup"><span data-stu-id="62a4b-341">Array inline</span></span>

<span data-ttu-id="62a4b-342">いくつかのコマンドライン引数を指定して実行可能ファイルを起動する、[Invoke-SnowSql][] という名前の関数があります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-342">I have a function called [Invoke-SnowSql][] that launches an executable with several command-line arguments.</span></span> <span data-ttu-id="62a4b-343">ここに、引数の配列を構築する関数からのクリップを示します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-343">Here is a clip from that function where I build the array of arguments.</span></span>

```powershell
$snowSqlParam = @(
    '--accountname', $Endpoint
    '--username', $Credential.UserName
    '--option', 'exit_on_error=true'
    '--option', 'output_format=csv'
    '--option', 'friendly=false'
    '--option', 'timing=false'
    if ($Debug)
    {
        '--option', 'log_level=DEBUG'
    }
    if ($Path)
    {
        '--filename', $Path
    }
    else
    {
        '--query', $singleLineQuery
    }
)
```

<span data-ttu-id="62a4b-344">`$Debug` 変数と `$Path` 変数は、エンド ユーザーによって指定される、関数に対するパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-344">The `$Debug` and `$Path` variables are parameters on the function that are provided by the end user.</span></span>
<span data-ttu-id="62a4b-345">これらは、配列の初期化中にインラインで評価します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-345">I evaluate them inline inside the initialization of my array.</span></span> <span data-ttu-id="62a4b-346">`$Debug` が true の場合、それらの値は正しい場所の `$snowSqlParam` に格納されます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-346">If `$Debug` is true, then those values fall into the `$snowSqlParam` in the correct place.</span></span> <span data-ttu-id="62a4b-347">`$Path` 変数についても、同じことが当てはまります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-347">Same holds true for the `$Path` variable.</span></span>

## <a name="simplify-complex-operations"></a><span data-ttu-id="62a4b-348">複雑な操作を簡略化する</span><span class="sxs-lookup"><span data-stu-id="62a4b-348">Simplify complex operations</span></span>

<span data-ttu-id="62a4b-349">調べる比較の数があまりにも多すぎて、if ステートメントが画面右側のずっと遠くへスクロールするような状況におちいることは避けられません。</span><span class="sxs-lookup"><span data-stu-id="62a4b-349">It's inevitable that you run into a situation that has way too many comparisons to check and your if statement scrolls way off the right side of the screen.</span></span>

```powershell
$user = Get-ADUser -Identity $UserName
if ( $null -ne $user -and $user.Department -eq 'Finance' -and $user.Title -match 'Senior' -and $user.HomeDrive -notlike '\\server\*' )
{
    # Do Something
}
```

<span data-ttu-id="62a4b-350">読むのが難しい場合があり、それが理由でよりミスをしやすくなります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-350">They can be hard to read and that make you more prone to make mistakes.</span></span> <span data-ttu-id="62a4b-351">これについては、できることがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-351">There are a few things we can do about that.</span></span>

### <a name="line-continuation"></a><span data-ttu-id="62a4b-352">行の連結</span><span class="sxs-lookup"><span data-stu-id="62a4b-352">Line continuation</span></span>

<span data-ttu-id="62a4b-353">PowerShell には、コマンドを次の行にラップするための演算子がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-353">There some operators in PowerShell that let you wrap you command to the next line.</span></span> <span data-ttu-id="62a4b-354">論理演算子 `-and` および `-or` は、式を複数行に分割する場合に使うのに適した演算子です。</span><span class="sxs-lookup"><span data-stu-id="62a4b-354">The logical operators `-and` and `-or` are good operators to use if you want to break your expression into multiple lines.</span></span>

```powershell
if ($null -ne $user -and
    $user.Department -eq 'Finance' -and
    $user.Title -match 'Senior' -and
    $user.HomeDrive -notlike '\\server\*'
)
{
    # Do Something
}
```

<span data-ttu-id="62a4b-355">それでも続行する作業は多数ありますが、各部分をそれぞれの行に配置することで大きな違いが生じます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-355">There's still a lot going on there, but placing each piece on its own line makes a big difference.</span></span>
<span data-ttu-id="62a4b-356">私が通常これを使用するのは、2 つ以上の比較を取得する場合や、ロジックを読むために右にスクロールする必要がある場合です。</span><span class="sxs-lookup"><span data-stu-id="62a4b-356">I generally use this when I get more than two comparisons or if I have to scroll to the right to read any of the logic.</span></span>

### <a name="pre-calculating-results"></a><span data-ttu-id="62a4b-357">結果の事前計算</span><span class="sxs-lookup"><span data-stu-id="62a4b-357">Pre-calculating results</span></span>

<span data-ttu-id="62a4b-358">if ステートメントから目的のステートメントを取り出して、結果だけを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-358">We can take that statement out of the if statement and only check the result.</span></span>

```powershell
$needsSecureHomeDrive = $null -ne $user -and
    $user.Department -eq 'Finance' -and
    $user.Title -match 'Senior' -and
    $user.HomeDrive -notlike '\\server\*'

if ( $needsSecureHomeDrive )
{
    # Do Something
}
```

<span data-ttu-id="62a4b-359">これはただ、前の例よりずっとすっきりしているように感じます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-359">This just feels much cleaner than the previous example.</span></span> <span data-ttu-id="62a4b-360">また、実際に調べようとしていることが何であるかを説明する変数名を使用できます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-360">You also are given an opportunity to use a variable name that explains what it's that you're really checking.</span></span> <span data-ttu-id="62a4b-361">これは、不要なコメントを節約する自己文書化コードの例でもあります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-361">This is also and example of self-documenting code that saves unnecessary comments.</span></span>

### <a name="multiple-if-statements"></a><span data-ttu-id="62a4b-362">複数の if ステートメント</span><span class="sxs-lookup"><span data-stu-id="62a4b-362">Multiple if statements</span></span>

<span data-ttu-id="62a4b-363">これを複数のステートメントに分割し、一度に 1 つずつ調べることができます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-363">We can break this up into multiple statements and check them one at a time.</span></span> <span data-ttu-id="62a4b-364">この場合、結果を結合するためにフラグまたは追跡用の変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-364">In this case, we use a flag or a tracking variable to combine the results.</span></span>

```powershell

$skipUser = $false

if( $null -eq $user )
{
    $skipUser = $true
}

if( $user.Department -ne 'Finance' )
{
    Write-Verbose "isn't in Finance department"
    $skipUser = $true
}

if( $user.Title -match 'Senior' )
{
    Write-Verbose "Doesn't have Senior title"
    $skipUser = $true
}

if( $user.HomeDrive -like '\\server\*' )
{
    Write-Verbose "Home drive already configured"
    $skipUser = $true
}

if ( -not $skipUser )
{
    # do something
}
```

<span data-ttu-id="62a4b-365">実際には、フラグ ロジックが正しく機能するように、ロジックを反転する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="62a4b-365">I did have to invert the logic to make the flag logic work correctly.</span></span> <span data-ttu-id="62a4b-366">各評価は、個々の `if` ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-366">Each evaluation is an individual `if` statement.</span></span> <span data-ttu-id="62a4b-367">この利点は、デバッグ中に、ロジックで何を実行中であるかを正確に知ることができることです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-367">The advantage of this is that when you're debugging, you can tell exactly what the logic is doing.</span></span> <span data-ttu-id="62a4b-368">同時に、ずっと役立つ詳細を追加できました。</span><span class="sxs-lookup"><span data-stu-id="62a4b-368">I was able to add much better verbosity at the same time.</span></span>

<span data-ttu-id="62a4b-369">明らかなマイナス面は、記述するコードがずっと多いことです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-369">The obvious downside is that it's so much more code to write.</span></span> <span data-ttu-id="62a4b-370">コードは、1 行のロジックを取得し、それを 25 行以上に展開するため、より複雑に見えます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-370">The code is more complex to look at as it takes a single line of logic and explodes it into 25 or more lines.</span></span>

### <a name="using-functions"></a><span data-ttu-id="62a4b-371">関数の使用</span><span class="sxs-lookup"><span data-stu-id="62a4b-371">Using functions</span></span>

<span data-ttu-id="62a4b-372">そうした検証ロジックすべてを、1 つの関数に移すこともできます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-372">We can also move all that validation logic into a function.</span></span> <span data-ttu-id="62a4b-373">一目で、これがどれほどすっきりしているかがわかります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-373">Look at how clean this looks at a glance.</span></span>

```powershell
if ( Test-SecureDriveConfiguration -ADUser $user )
{
    # do something
}
```

<span data-ttu-id="62a4b-374">まだ、検証を実行する関数を作成する必要はありますが、このコードはずっと扱いやすくなっています。</span><span class="sxs-lookup"><span data-stu-id="62a4b-374">You still have to create the function to do the validation, but it makes this code much easier to work with.</span></span> <span data-ttu-id="62a4b-375">このコードをテストするのも容易になっています。</span><span class="sxs-lookup"><span data-stu-id="62a4b-375">It makes this code easier to test.</span></span> <span data-ttu-id="62a4b-376">テストでは、`Test-ADDriveConfiguration` への呼び出しを模倣できるので、この関数に必要なテストは 2 つだけです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-376">In your tests, you can mock the call to `Test-ADDriveConfiguration` and you only need two tests for this function.</span></span> <span data-ttu-id="62a4b-377">1 つはそこで `$true` を返し、もう 1 つはそこで `$false` を返します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-377">One where it returns `$true` and one where it returns `$false`.</span></span> <span data-ttu-id="62a4b-378">その他の関数のテストは、関数が非常に小さいためより簡単です。</span><span class="sxs-lookup"><span data-stu-id="62a4b-378">Testing the other function is simpler because it's so small.</span></span>

<span data-ttu-id="62a4b-379">その関数の本体は、開始時に使った 1 行バージョンである場合も、最後のセクションで使用した、展開されたロジックと同じである場合もあります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-379">The body of that function could still be that one-liner we started with or the exploded logic that we used in the last section.</span></span> <span data-ttu-id="62a4b-380">これは、どちらのシナリオでも正しく機能し、後でその実装を簡単に変更できます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-380">This works well for both scenarios and allows you to easily change that implementation later.</span></span>

## <a name="error-handling"></a><span data-ttu-id="62a4b-381">エラー処理</span><span class="sxs-lookup"><span data-stu-id="62a4b-381">Error handling</span></span>

<span data-ttu-id="62a4b-382">`if` ステートメントの重要な用途の 1 つは、エラーが発生する前にエラー条件を調べることです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-382">One important use of the `if` statement is to check for error conditions before you run into errors.</span></span> <span data-ttu-id="62a4b-383">フォルダーが既に存在するかどうかを確認してからフォルダーを作成することが、良い例です。</span><span class="sxs-lookup"><span data-stu-id="62a4b-383">A good example is to check if a folder already exists before you try to create it.</span></span>

```powershell
if ( -not (Test-Path -Path $folder) )
{
    New-Item -Type Directory -Path $folder
}
```

<span data-ttu-id="62a4b-384">例外の発生を予期している場合、それは実際には例外ではないとも言えます。</span><span class="sxs-lookup"><span data-stu-id="62a4b-384">I like to say that if you expect an exception to happen, then it's not really an exception.</span></span> <span data-ttu-id="62a4b-385">そのため、値を確認し、可能な場合は条件を検証します。</span><span class="sxs-lookup"><span data-stu-id="62a4b-385">So check your values and validate your conditions where you can.</span></span>

<span data-ttu-id="62a4b-386">実際の例外処理についてもう少し詳しく知りたい場合は、[例外について知りたかったことのすべて][]に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="62a4b-386">If you want to dive a little more into actual exception handling, I have an article on [everything you ever wanted to know about exceptions][].</span></span>

## <a name="final-words"></a><span data-ttu-id="62a4b-387">まとめ</span><span class="sxs-lookup"><span data-stu-id="62a4b-387">Final words</span></span>

<span data-ttu-id="62a4b-388">`if` ステートメントはあのように単純なステートメントですが、PowerShell の基本となっている部分です。</span><span class="sxs-lookup"><span data-stu-id="62a4b-388">The `if` statement is such a simple statement but is a fundamental piece of PowerShell.</span></span> <span data-ttu-id="62a4b-389">これは、自分が記述するほとんどすべてのスクリプトで、複数回使用しているのに気付くことになります。</span><span class="sxs-lookup"><span data-stu-id="62a4b-389">You will find yourself using this multiple times in almost every script you write.</span></span> <span data-ttu-id="62a4b-390">以前よりも理解を深めていただけたならば幸いです。</span><span class="sxs-lookup"><span data-stu-id="62a4b-390">I hope you have a better understanding than you had before.</span></span>

<!-- link references -->
[オリジナル バージョン]: https://powershellexplained.com/2019-08-11-PowerShell-if-then-else-equals-operator/
[original version]: https://powershellexplained.com/2019-08-11-PowerShell-if-then-else-equals-operator/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[if]: /powershell/module/microsoft.powershell.core/about/about_if
[ビットごとの演算子]: https://powershellexplained.com/powershell/module/microsoft.powershell.core/about/about_arithmetic_operators#bitwise-operators
[bitwise operators]: https://powershellexplained.com/powershell/module/microsoft.powershell.core/about/about_arithmetic_operators#bitwise-operators
[正規表現を使用するさまざまな方法]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[the many ways to use regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[例外について知りたかったことのすべて]: everything-about-exceptions.md
[everything you ever wanted to know about exceptions]: everything-about-exceptions.md
[$null について知りたかったことのすべて]: everything-about-null.md
[everything you wanted to know about $null]: everything-about-null.md
[Prasoon Karunan V]: https://twitter.com/prasoonkarunan
[switch ステートメントについて知りたかったことのすべて]: everything-about-switch.md
[everything you ever wanted to know about the switch statement]: everything-about-switch.md
[Invoke-SnowSql]: https://github.com/loanDepot/SnowSQL/blob/a3731b52e4ab4ecb503fb81e2d8cb131e8f90410/SnowSQL/public/Invoke-SnowSql.ps1#L90
