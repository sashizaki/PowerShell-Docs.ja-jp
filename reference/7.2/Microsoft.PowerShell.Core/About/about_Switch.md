---
description: スイッチを使用して複数のステートメントを処理する方法について説明 `If` します。
Locale: en-US
ms.date: 05/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_switch?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Switch
ms.openlocfilehash: 5ca12fe1d5052c1589c5dfecca8cf08cf68901e8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603239"
---
# <a name="about-switch"></a><span data-ttu-id="87745-103">スイッチの概要</span><span class="sxs-lookup"><span data-stu-id="87745-103">About Switch</span></span>

## <a name="short-description"></a><span data-ttu-id="87745-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="87745-104">Short description</span></span>
<span data-ttu-id="87745-105">スイッチを使用して複数のステートメントを処理する方法について説明 `If` します。</span><span class="sxs-lookup"><span data-stu-id="87745-105">Explains how to use a switch to handle multiple `If` statements.</span></span>

## <a name="long-description"></a><span data-ttu-id="87745-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="87745-106">Long description</span></span>

<span data-ttu-id="87745-107">スクリプトまたは関数で条件を確認するには、ステートメントを使用し `If` ます。</span><span class="sxs-lookup"><span data-stu-id="87745-107">To check a condition in a script or function, use an `If` statement.</span></span> <span data-ttu-id="87745-108">ステートメントでは `If` 、変数の値やオブジェクトのプロパティなど、さまざまな種類の条件を確認できます。</span><span class="sxs-lookup"><span data-stu-id="87745-108">The `If` statement can check many types of conditions, including the value of variables and the properties of objects.</span></span>

<span data-ttu-id="87745-109">複数の条件を確認するには、ステートメントを使用し `Switch` ます。</span><span class="sxs-lookup"><span data-stu-id="87745-109">To check multiple conditions, use a `Switch` statement.</span></span> <span data-ttu-id="87745-110">`Switch`ステートメントは一連のステートメントに相当しますが、より `If` 簡単です。</span><span class="sxs-lookup"><span data-stu-id="87745-110">The `Switch` statement is equivalent to a series of `If` statements, but it is simpler.</span></span> <span data-ttu-id="87745-111">ステートメントでは、 `Switch` 各条件とオプションのアクションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="87745-111">The `Switch` statement lists each condition and an optional action.</span></span> <span data-ttu-id="87745-112">条件がを取得すると、アクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="87745-112">If a condition obtains, the action is performed.</span></span>

<span data-ttu-id="87745-113">ステートメントでは、 `Switch` `$_` および自動変数を使用でき `$switch` ます。</span><span class="sxs-lookup"><span data-stu-id="87745-113">The `Switch` statement can use the `$_` and `$switch` automatic variables.</span></span> <span data-ttu-id="87745-114">詳細については、「 [about_Automatic_Variables](about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87745-114">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="87745-115">基本 `Switch` ステートメントの形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="87745-115">A basic `Switch` statement has the following format:</span></span>

```powershell
Switch (<test-value>)
{
    <condition> {<action>}
    <condition> {<action>}
}
```

<span data-ttu-id="87745-116">たとえば、次のステートメントでは、 `Switch` テスト値3を各条件に比較しています。</span><span class="sxs-lookup"><span data-stu-id="87745-116">For example, the following `Switch` statement compares the test value, 3, to each of the conditions.</span></span> <span data-ttu-id="87745-117">テスト値が条件に一致した場合、アクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="87745-117">When the test value matches the condition, the action is performed.</span></span>

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."}
    4 {"It is four."}
}
```

```Output
It is three.
```

<span data-ttu-id="87745-118">この簡単な例では、値3が一致する場合でも、値はリストの各条件と比較されます。</span><span class="sxs-lookup"><span data-stu-id="87745-118">In this simple example, the value is compared to each condition in the list, even though there is a match for the value 3.</span></span> <span data-ttu-id="87745-119">次の `Switch` ステートメントには、値が3の2つの条件があります。</span><span class="sxs-lookup"><span data-stu-id="87745-119">The following `Switch` statement has two conditions for a value of 3.</span></span> <span data-ttu-id="87745-120">既定では、すべての条件がテストされることを示しています。</span><span class="sxs-lookup"><span data-stu-id="87745-120">It demonstrates that, by default, all conditions are tested.</span></span>

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."}
    4 {"It is four."}
    3 {"Three again."}
}
```

```Output
It is three.
Three again.
```

<span data-ttu-id="87745-121">一致後にを比較しないようにに指示するには、 `Switch` ステートメントを使用し `Break` ます。</span><span class="sxs-lookup"><span data-stu-id="87745-121">To direct the `Switch` to stop comparing after a match, use the `Break` statement.</span></span> <span data-ttu-id="87745-122">ステートメントは、 `Break` ステートメントを終了し `Switch` ます。</span><span class="sxs-lookup"><span data-stu-id="87745-122">The `Break` statement terminates the `Switch` statement.</span></span>

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."; Break}
    4 {"It is four."}
    3 {"Three again."}
}
```

```Output
It is three.
```

<span data-ttu-id="87745-123">テスト値が配列などのコレクションである場合、コレクション内の各項目は、出現する順序で評価されます。</span><span class="sxs-lookup"><span data-stu-id="87745-123">If the test value is a collection, such as an array, each item in the collection is evaluated in the order in which it appears.</span></span> <span data-ttu-id="87745-124">次の例では、4と2が評価されます。</span><span class="sxs-lookup"><span data-stu-id="87745-124">The following examples evaluates 4 and then 2.</span></span>

```powershell
switch (4, 2)
{
    1 {"It is one." }
    2 {"It is two." }
    3 {"It is three." }
    4 {"It is four." }
    3 {"Three again."}
}
```

```Output
It is four.
It is two.
```

<span data-ttu-id="87745-125">次の例に示すように、すべてのステートメントは、 `Break` 各値ではなく、コレクションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="87745-125">Any `Break` statements apply to the collection, not to each value, as shown in the following example.</span></span> <span data-ttu-id="87745-126">ステートメントは、 `Switch` `Break` 値4の条件でステートメントによって終了されます。</span><span class="sxs-lookup"><span data-stu-id="87745-126">The `Switch` statement is terminated by the `Break` statement in the condition of value 4.</span></span>

```powershell
switch (4, 2)
{
    1 {"It is one."; Break}
    2 {"It is two." ; Break }
    3 {"It is three." ; Break }
    4 {"It is four." ; Break }
    3 {"Three again."}
}
```

```Output
It is four.
```

### <a name="syntax"></a><span data-ttu-id="87745-127">構文</span><span class="sxs-lookup"><span data-stu-id="87745-127">Syntax</span></span>

<span data-ttu-id="87745-128">ステートメントの完全な `Switch` 構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="87745-128">The complete `Switch` statement syntax is as follows:</span></span>

```
switch [-regex|-wildcard|-exact][-casesensitive] (<value>)
{
    "string"|number|variable|{ expression } { statementlist }
    default { statementlist }
}
```

<span data-ttu-id="87745-129">または</span><span class="sxs-lookup"><span data-stu-id="87745-129">or</span></span>

```
switch [-regex|-wildcard|-exact][-casesensitive] -file filename
{
    "string"|number|variable|{ expression } { statementlist }
    default { statementlist }
}
```

<span data-ttu-id="87745-130">パラメーターを使用しない場合、は `Switch` **正確** なパラメーターを使用するのと同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="87745-130">If no parameters are used, `Switch` behaves the same as using the **Exact** parameter.</span></span> <span data-ttu-id="87745-131">値に対して大文字と小文字を区別しない一致を実行します。</span><span class="sxs-lookup"><span data-stu-id="87745-131">It performs a case-insensitive match for the value.</span></span> <span data-ttu-id="87745-132">値がコレクションの場合は、各要素が出現する順序で評価されます。</span><span class="sxs-lookup"><span data-stu-id="87745-132">If the value is a collection, each element is evaluated in the order in which it appears.</span></span>

<span data-ttu-id="87745-133">ステートメントには、 `Switch` 少なくとも1つの condition ステートメントを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="87745-133">The `Switch` statement must include at least one condition statement.</span></span>

<span data-ttu-id="87745-134">`Default`値がどの条件にも一致しない場合、句がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="87745-134">The `Default` clause is triggered when the value does not match any of the conditions.</span></span> <span data-ttu-id="87745-135">これは、 `Else` ステートメントの句に相当 `If` します。</span><span class="sxs-lookup"><span data-stu-id="87745-135">It is equivalent to an `Else` clause in an `If` statement.</span></span> <span data-ttu-id="87745-136">`Default`各ステートメントで使用できる句は1つだけです `Switch` 。</span><span class="sxs-lookup"><span data-stu-id="87745-136">Only one `Default` clause is permitted in each `Switch` statement.</span></span>

<span data-ttu-id="87745-137">`Switch` には次のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="87745-137">`Switch` has the following parameters:</span></span>

- <span data-ttu-id="87745-138">**ワイルドカード** -条件がワイルドカード文字列であることを示します。</span><span class="sxs-lookup"><span data-stu-id="87745-138">**Wildcard** - Indicates that the condition is a wildcard string.</span></span> <span data-ttu-id="87745-139">Match 句が文字列でない場合、パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="87745-139">If the match clause is not a string, the parameter is ignored.</span></span> <span data-ttu-id="87745-140">比較では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="87745-140">The comparison is case-insensitive.</span></span>
- <span data-ttu-id="87745-141">**Exact** -match 句が文字列である場合は、正確に一致する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="87745-141">**Exact** - Indicates that the match clause, if it is a string, must match exactly.</span></span> <span data-ttu-id="87745-142">Match 句が文字列でない場合、このパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="87745-142">If the match clause is not a string, this parameter is ignored.</span></span> <span data-ttu-id="87745-143">比較では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="87745-143">The comparison is case-insensitive.</span></span>
- <span data-ttu-id="87745-144">**CaseSensitive** -大文字と小文字を区別する一致を実行します。</span><span class="sxs-lookup"><span data-stu-id="87745-144">**CaseSensitive** - Performs a case-sensitive match.</span></span> <span data-ttu-id="87745-145">Match 句が文字列でない場合、このパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="87745-145">If the match clause is not a string, this parameter is ignored.</span></span>
- <span data-ttu-id="87745-146">**File**-値ステートメントではなく、ファイルからの入力を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="87745-146">**File**- Takes input from a file rather than a value statement.</span></span> <span data-ttu-id="87745-147">複数の **ファイル** パラメーターが含まれている場合は、最後のパラメーターのみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="87745-147">If multiple **File** parameters are included, only the last one is used.</span></span> <span data-ttu-id="87745-148">ファイルの各行は、ステートメントによって読み取られ、評価され `Switch` ます。</span><span class="sxs-lookup"><span data-stu-id="87745-148">Each line of the file is read and evaluated by the `Switch` statement.</span></span> <span data-ttu-id="87745-149">比較では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="87745-149">The comparison is case-insensitive.</span></span>
- <span data-ttu-id="87745-150">**Regex** -条件に対して値の正規表現の一致を実行します。</span><span class="sxs-lookup"><span data-stu-id="87745-150">**Regex** - Performs regular expression matching of the value to the condition.</span></span> <span data-ttu-id="87745-151">Match 句が文字列でない場合、このパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="87745-151">If the match clause is not a string, this parameter is ignored.</span></span>
  <span data-ttu-id="87745-152">比較では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="87745-152">The comparison is case-insensitive.</span></span> <span data-ttu-id="87745-153">`$matches`自動変数は、対応するステートメントブロック内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="87745-153">The `$matches` automatic variable is available for use within the matching statement block.</span></span>

> [!NOTE]
> <span data-ttu-id="87745-154">**Regex** や **ワイルドカード** などの競合する値を指定すると、指定された最後のパラメーターが優先され、競合するすべてのパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="87745-154">When specifying conflicting values, like **Regex** and **Wildcard**, the last parameter specified takes precedence, and all conflicting parameters are ignored.</span></span> <span data-ttu-id="87745-155">パラメーターの複数のインスタンスを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="87745-155">Multiple instances of parameters are also permitted.</span></span> <span data-ttu-id="87745-156">ただし、最後に使用されたパラメーターのみが有効です。</span><span class="sxs-lookup"><span data-stu-id="87745-156">However, only the last parameter used is effective.</span></span>

<span data-ttu-id="87745-157">この例では、文字列または数値データではないオブジェクトがに渡され `Switch` ます。</span><span class="sxs-lookup"><span data-stu-id="87745-157">In this example, an object that's not a string or numerical data is passed to the `Switch`.</span></span> <span data-ttu-id="87745-158">は、 `Switch` オブジェクトに対して文字列の強制変換を実行し、結果を評価します。</span><span class="sxs-lookup"><span data-stu-id="87745-158">The `Switch` performs a string coercion on the object and evaluates the outcome.</span></span>

```powershell
$test = @{
    Test  = 'test'
    Test2 = 'test2'
}

$test.ToString()

switch -Exact ($test)
{
    'System.Collections.Hashtable'
    {
        'Hashtable string coercion'
    }
    'test'
    {
        'Hashtable value'
    }
}
```

```Output
System.Collections.Hashtable
Hashtable string coercion
```

<span data-ttu-id="87745-159">この例では、一致するケースがないため、出力はありません。</span><span class="sxs-lookup"><span data-stu-id="87745-159">In this example, there is no matching case so there is no output.</span></span>

```powershell
switch ("fourteen")
{
    1 {"It is one."; Break}
    2 {"It is two."; Break}
    3 {"It is three."; Break}
    4 {"It is four."; Break}
    "fo*" {"That's too many."}
}
```

<span data-ttu-id="87745-160">句を追加することで `Default` 、他の条件が成功しなかった場合にアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="87745-160">By adding the `Default` clause, you can perform an action when no other conditions succeed.</span></span>

```powershell
switch ("fourteen")
{
    1 {"It is one."; Break}
    2 {"It is two."; Break}
    3 {"It is three."; Break}
    4 {"It is four."; Break}
    "fo*" {"That's too many."}
    Default {
        "No matches"
    }
}
```

```Output
No matches
```

<span data-ttu-id="87745-161">"14" という語を大文字と小文字に一致させるに `-Wildcard` は、パラメーターまたはパラメーターを使用する必要があり `-Regex` ます。</span><span class="sxs-lookup"><span data-stu-id="87745-161">For the word "fourteen" to match a case you must use the `-Wildcard` or `-Regex` parameter.</span></span>

```powershell
   PS> switch -Wildcard ("fourteen")
       {
           1 {"It is one."; Break}
           2 {"It is two."; Break}
           3 {"It is three."; Break}
           4 {"It is four."; Break}
           "fo*" {"That's too many."}
       }
 ```

```Output
That's too many.
```

<span data-ttu-id="87745-162">次の例では、パラメーターを使用し `-Regex` ます。</span><span class="sxs-lookup"><span data-stu-id="87745-162">The following example uses the `-Regex` parameter.</span></span>

```powershell
$target = 'https://bing.com'
switch -Regex ($target)
{
    '^ftp\://.*$' { "$_ is an ftp address"; Break }
    '^\w+@\w+\.com|edu|org$' { "$_ is an email address"; Break }
    '^(http[s]?)\://.*$' { "$_ is a web address that uses $($matches[1])"; Break }
}
```

```Output
https://bing.com is a web address that uses https
```

<span data-ttu-id="87745-163">Switch ステートメントの条件には、次のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="87745-163">A Switch statement condition may be either:</span></span>

- <span data-ttu-id="87745-164">値が入力値と比較される式。</span><span class="sxs-lookup"><span data-stu-id="87745-164">An expression whose value is compared to the input value</span></span>
- <span data-ttu-id="87745-165">`$true`条件が満たされた場合にを返すスクリプトブロック。</span><span class="sxs-lookup"><span data-stu-id="87745-165">A script block which should return `$true` if a condition is met.</span></span>

<span data-ttu-id="87745-166">`$_`自動変数には switch ステートメントに渡される値が含まれており、condition ステートメントのスコープ内で評価および使用できます。</span><span class="sxs-lookup"><span data-stu-id="87745-166">The `$_` automatic variable contains the value passed to the switch statement and is available for evaluation and use within the scope of the condition statements.</span></span>

<span data-ttu-id="87745-167">各条件のアクションは、他の条件のアクションから独立しています。</span><span class="sxs-lookup"><span data-stu-id="87745-167">The action for each condition is independent of the actions in other conditions.</span></span>

<span data-ttu-id="87745-168">次の例では、ステートメントの条件としてスクリプトブロックを使用する方法を示し `Switch` ます。</span><span class="sxs-lookup"><span data-stu-id="87745-168">The following example demonstrates the use of script blocks as `Switch` statement conditions.</span></span>

```powershell
switch ("Test")
{
    {$_ -is [String]} {
        "Found a string"
    }
    "Test" {
        "This $_ executes as well"
    }
}
```

```Output
Found a string
This Test executes as well
```

<span data-ttu-id="87745-169">値が複数の条件に一致する場合は、各条件のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="87745-169">If the value matches multiple conditions, the action for each condition is executed.</span></span> <span data-ttu-id="87745-170">この動作を変更するに `Break` は、キーワードまたはキーワードを使用し `Continue` ます。</span><span class="sxs-lookup"><span data-stu-id="87745-170">To change this behavior, use the `Break` or `Continue` keywords.</span></span>

<span data-ttu-id="87745-171">`Break`キーワードは処理を停止し、ステートメントを終了し `Switch` ます。</span><span class="sxs-lookup"><span data-stu-id="87745-171">The `Break` keyword stops processing and exits the `Switch` statement.</span></span>

<span data-ttu-id="87745-172">キーワードは、 `Continue` 現在の値の処理を停止しますが、後続の値の処理は続行されます。</span><span class="sxs-lookup"><span data-stu-id="87745-172">The `Continue` keyword stops processing the current value, but continues processing any subsequent values.</span></span>

<span data-ttu-id="87745-173">次の例では、数値の配列を処理し、奇数または偶数であるかどうかを表示します。</span><span class="sxs-lookup"><span data-stu-id="87745-173">The following example processes an array of numbers and displays if they are odd or even.</span></span> <span data-ttu-id="87745-174">負の数値は、キーワードを使用してスキップされ `Continue` ます。</span><span class="sxs-lookup"><span data-stu-id="87745-174">Negative numbers are skipped with the `Continue` keyword.</span></span> <span data-ttu-id="87745-175">非数が検出された場合、実行はキーワードを使用して終了し `Break` ます。</span><span class="sxs-lookup"><span data-stu-id="87745-175">If a non-number is encountered, execution is terminated with the `Break` keyword.</span></span>

```powershell
switch (1,4,-1,3,"Hello",2,1)
{
    {$_ -lt 0} { Continue }
    {$_ -isnot [Int32]} { Break }
    {$_ % 2} {
        "$_ is Odd"
    }
    {-not ($_ % 2)} {
        "$_ is Even"
    }
}
```

```Output
1 is Odd
4 is Even
3 is Odd
```

## <a name="see-also"></a><span data-ttu-id="87745-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="87745-176">See also</span></span>

[<span data-ttu-id="87745-177">about_Break</span><span class="sxs-lookup"><span data-stu-id="87745-177">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="87745-178">about_Continue</span><span class="sxs-lookup"><span data-stu-id="87745-178">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="87745-179">about_If</span><span class="sxs-lookup"><span data-stu-id="87745-179">about_If</span></span>](about_If.md)

[<span data-ttu-id="87745-180">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="87745-180">about_Script_Blocks</span></span>](about_Script_Blocks.md)
