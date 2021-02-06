---
description: 、、、、 `foreach` `for` `while` `do` `switch` 、またはステートメントをすぐに終了するために使用できるステートメントについて説明し `trap` ます。
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_break?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Break
ms.openlocfilehash: 3c418f5bae11f957880c8b53ee0bcf2fb44515ee
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602422"
---
# <a name="about-break"></a><span data-ttu-id="20bb6-103">中断について</span><span class="sxs-lookup"><span data-stu-id="20bb6-103">About Break</span></span>

## <a name="short-description"></a><span data-ttu-id="20bb6-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="20bb6-104">Short description</span></span>

<span data-ttu-id="20bb6-105">、、、、 `foreach` `for` `while` `do` `switch` 、またはステートメントをすぐに終了するために使用できるステートメントについて説明し `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-105">Describes a statement you can use to immediately exit `foreach`, `for`, `while`, `do`, `switch`, or `trap` statements.</span></span>

## <a name="long-description"></a><span data-ttu-id="20bb6-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="20bb6-106">Long description</span></span>

<span data-ttu-id="20bb6-107">ステートメントは、 `break` 現在のコントロールブロックを終了する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="20bb6-107">The `break` statement provides a way to exit the current control block.</span></span>
<span data-ttu-id="20bb6-108">実行は、コントロールブロックの後の次のステートメントから続行されます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-108">Execution continues at the next statement after the control block.</span></span> <span data-ttu-id="20bb6-109">ステートメントでは、ラベルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="20bb6-109">The statement supports labels.</span></span> <span data-ttu-id="20bb6-110">ラベルは、スクリプト内のステートメントに割り当てる名前です。</span><span class="sxs-lookup"><span data-stu-id="20bb6-110">A label is a name you assign to a statement in a script.</span></span>

## <a name="using-break-in-loops"></a><span data-ttu-id="20bb6-111">Break in ループの使用</span><span class="sxs-lookup"><span data-stu-id="20bb6-111">Using break in loops</span></span>

<span data-ttu-id="20bb6-112">`break`ループ内にステートメントが含まれている場合 ( `foreach` 、 `for` 、 `do` 、またはループなど) `while` 、PowerShell はすぐにループを終了します。</span><span class="sxs-lookup"><span data-stu-id="20bb6-112">When a `break` statement appears in a loop, such as a `foreach`, `for`, `do`, or `while` loop, PowerShell immediately exits the loop.</span></span>

<span data-ttu-id="20bb6-113">ステートメントには、 `break` 埋め込みループを終了できるラベルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-113">A `break` statement can include a label that lets you exit embedded loops.</span></span> <span data-ttu-id="20bb6-114">ラベルには `foreach` 、スクリプト内で任意の loop キーワード (、、など) を指定でき `for` `while` ます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-114">A label can specify any loop keyword, such as `foreach`, `for`, or `while`, in a script.</span></span>

<span data-ttu-id="20bb6-115">ステートメントを使用してステートメントを終了する方法を次の例に示し `break` `for` ます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-115">The following example shows how to use a `break` statement to exit a `for` statement:</span></span>

```powershell
for($i=1; $i -le 10; $i++) {
   Write-Host $i
   break
}
```

<span data-ttu-id="20bb6-116">この例では、 `break` `for` 変数が1と等しい場合、ステートメントはループを終了し `$i` ます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-116">In this example, the `break` statement exits the `for` loop when the `$i` variable equals 1.</span></span> <span data-ttu-id="20bb6-117">`for`が10を超えるまでステートメントが **True** と評価された場合でも `$i` 、最初に `for` ループが実行されたときに PowerShell は break ステートメントに到達します。</span><span class="sxs-lookup"><span data-stu-id="20bb6-117">Even though the `for` statement evaluates to **True** until `$i` is greater than 10, PowerShell reaches the break statement the first time the `for` loop is run.</span></span>

<span data-ttu-id="20bb6-118">`break`内部条件を満たす必要があるループでは、ステートメントを使用するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="20bb6-118">It is more common to use the `break` statement in a loop where an inner condition must be met.</span></span> <span data-ttu-id="20bb6-119">次のステートメントの例を考えてみましょう `foreach` 。</span><span class="sxs-lookup"><span data-stu-id="20bb6-119">Consider the following `foreach` statement example:</span></span>

```powershell
$i=0
$varB = 10,20,30,40
foreach ($val in $varB) {
  if ($val -eq 30) {
    break
  }
  $i++
}
Write-Host "30 was found in array index $i"
```

<span data-ttu-id="20bb6-120">この例では、 `foreach` ステートメントは配列を反復処理し `$varB` ます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-120">In this example, the `foreach` statement iterates the `$varB` array.</span></span> <span data-ttu-id="20bb6-121">ステートメントは、 `if` ループの最初の2回の実行時に False と評価され、変数 `$i` は1ずつインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-121">The `if` statement evaluates to False the first two times the loop is run and the variable `$i` is incremented by 1.</span></span> <span data-ttu-id="20bb6-122">ループが3回実行された場合、は `$i` 2 に `$val` なり、変数は30と等しくなります。</span><span class="sxs-lookup"><span data-stu-id="20bb6-122">The third time the loop is run, `$i` equals 2, and the `$val` variable equals 30.</span></span> <span data-ttu-id="20bb6-123">この時点で、ステートメントが実行され、 `break` `foreach` ループが終了します。</span><span class="sxs-lookup"><span data-stu-id="20bb6-123">At this point, the `break` statement runs, and the `foreach` loop exits.</span></span>

### <a name="using-a-labeled-break-in-a-loop"></a><span data-ttu-id="20bb6-124">ループ内でラベル付きの改行を使用する</span><span class="sxs-lookup"><span data-stu-id="20bb6-124">Using a labeled break in a loop</span></span>

<span data-ttu-id="20bb6-125">ステートメントには `break` 、ラベルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-125">A `break` statement can include a label.</span></span> <span data-ttu-id="20bb6-126">`break`キーワードをラベルと共に使用すると、PowerShell は、現在のループを終了するのではなく、ラベルが付けられたループを終了します。</span><span class="sxs-lookup"><span data-stu-id="20bb6-126">If you use the `break` keyword with a label, PowerShell exits the labeled loop instead of exiting the current loop.</span></span>
<span data-ttu-id="20bb6-127">ラベルは、コロンの後に割り当てた名前を付けたものです。</span><span class="sxs-lookup"><span data-stu-id="20bb6-127">The label is a colon followed by a name that you assign.</span></span> <span data-ttu-id="20bb6-128">ラベルは、ステートメント内の最初のトークンである必要があります。また、のようなループキーワードが続く必要があり `while` ます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-128">The label must be the first token in a statement, and it must be followed by the looping keyword, such as `while`.</span></span>

<span data-ttu-id="20bb6-129">`break` 実行を、ラベルが付けられたループの外に移動します。</span><span class="sxs-lookup"><span data-stu-id="20bb6-129">`break` moves execution out of the labeled loop.</span></span> <span data-ttu-id="20bb6-130">埋め込みループでは、 `break` キーワードが単独で使用される場合とは異なる結果になります。</span><span class="sxs-lookup"><span data-stu-id="20bb6-130">In embedded loops, this has a different result than the `break` keyword has when it is used by itself.</span></span> <span data-ttu-id="20bb6-131">この例では、ステートメントにステートメントが含まれ `while` てい `for` ます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-131">This example has a `while` statement with a `for` statement:</span></span>

```powershell
:myLabel while (<condition 1>) {
  for ($item in $items) {
    if (<condition 2>) {
      break myLabel
    }
    $item = $x   # A statement inside the For-loop
  }
}
$a = $c  # A statement after the labeled While-loop
```

<span data-ttu-id="20bb6-132">Condition 2 が **True** と評価された場合、スクリプトの実行は、ラベル付けされたループの後のステートメントまでスキップされます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-132">If condition 2 evaluates to **True**, the execution of the script skips down to the statement after the labeled loop.</span></span> <span data-ttu-id="20bb6-133">この例では、ステートメントを使用して実行を再び開始し `$a = $c` ます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-133">In the example, execution starts again with the statement `$a = $c`.</span></span>

<span data-ttu-id="20bb6-134">次の例に示すように、多数のラベル付きループを入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-134">You can nest many labeled loops, as shown in the following example.</span></span>

```powershell
:red while (<condition1>) {
  :yellow while (<condition2>) {
    while (<condition3>) {
      if ($a) {break}
      if ($b) {break red}
      if ($c) {break yellow}
    }
    Write-Host "After innermost loop"
  }
  Write-Host "After yellow loop"
}
Write-Host "After red loop"
```

<span data-ttu-id="20bb6-135">変数が `$b` True と評価されると、"red" というラベルが付いたループの後にスクリプトの実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-135">If the `$b` variable evaluates to True, execution of the script resumes after the loop that is labeled "red".</span></span> <span data-ttu-id="20bb6-136">変数が `$c` True と評価された場合、スクリプトコントロールの実行は、"黄色" というラベルが付いたループの後に再開されます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-136">If the `$c` variable evaluates to True, execution of the script control resumes after the loop that is labeled "yellow".</span></span>

<span data-ttu-id="20bb6-137">変数が True と評価されると `$a` 、最も内側のループの後に実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-137">If the `$a` variable evaluates to True, execution resumes after the innermost loop.</span></span> <span data-ttu-id="20bb6-138">ラベルは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="20bb6-138">No label is needed.</span></span>

<span data-ttu-id="20bb6-139">PowerShell では、ラベルの実行を再開する距離を制限しません。</span><span class="sxs-lookup"><span data-stu-id="20bb6-139">PowerShell does not limit how far labels can resume execution.</span></span> <span data-ttu-id="20bb6-140">ラベルは、スクリプトと関数呼び出しの境界を越えて制御を渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-140">The label can even pass control across script and function call boundaries.</span></span>

## <a name="using-break-in-a-switch-statement"></a><span data-ttu-id="20bb6-141">Switch ステートメントでの break の使用</span><span class="sxs-lookup"><span data-stu-id="20bb6-141">Using break in a switch statement</span></span>

<span data-ttu-id="20bb6-142">コンストラクトでは `switch` 、 `break` PowerShell によってコードブロックが終了さ `switch` れます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-142">In a `switch`construct, `break` causes PowerShell to exit the `switch` code block.</span></span>

<span data-ttu-id="20bb6-143">キーワードは、 `break` コンストラクトを離れるために使用され `switch` ます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-143">The `break` keyword is used to leave the `switch` construct.</span></span> <span data-ttu-id="20bb6-144">たとえば、次のステートメントでは、 `switch` ステートメントを使用して、 `break` 最も具体的な条件をテストしています。</span><span class="sxs-lookup"><span data-stu-id="20bb6-144">For example, the following `switch` statement uses `break` statements to test for the most specific condition:</span></span>

```powershell
$var = "word2"
switch -regex ($var) {
    "word2" {
      Write-Host "Exact" $_
      break
    }

    "word.*" {
      Write-Host "Match on the prefix" $_
      break
    }

    "w.*" {
      Write-Host "Match on at least the first letter" $_
      break
    }

    default {
      Write-Host "No match" $_
      break
    }
}
```

<span data-ttu-id="20bb6-145">この例では、 `$var` 変数が作成され、文字列値に初期化され `word2` ます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-145">In this example, the `$var` variable is created and initialized to a string value of `word2`.</span></span> <span data-ttu-id="20bb6-146">このステートメントでは、Regex クラスを使用して、 `switch` 変数の値を最初に用語と照合し `word2` ます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-146">The `switch` statement uses the **Regex** class to match the variable value first with the term `word2`.</span></span> <span data-ttu-id="20bb6-147">変数の値とステートメント内の最初のテストが一致するため `switch` 、ステートメント内の最初のコードブロックが実行され `switch` ます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-147">Because the variable value and the first test in the `switch` statement match, the first code block in the `switch` statement runs.</span></span>

<span data-ttu-id="20bb6-148">PowerShell が最初のステートメントに到達すると、 `break` `switch` ステートメントは終了します。</span><span class="sxs-lookup"><span data-stu-id="20bb6-148">When PowerShell reaches the first `break` statement, the `switch` statement exits.</span></span> <span data-ttu-id="20bb6-149">この例から4つのステートメントを削除すると `break` 、4つの条件がすべて満たされます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-149">If the four `break` statements are removed from the example, all four conditions are met.</span></span> <span data-ttu-id="20bb6-150">この例では、ステートメントを使用して `break` 、最も具体的な条件が満たされたときに結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="20bb6-150">This example uses the `break` statement to display results when the most specific condition is met.</span></span>

## <a name="using-break-in-a-trap-statement"></a><span data-ttu-id="20bb6-151">トラップステートメントでの break の使用</span><span class="sxs-lookup"><span data-stu-id="20bb6-151">Using break in a trap statement</span></span>

<span data-ttu-id="20bb6-152">ステートメントの本体で最後に実行されたステートメントがの場合は `trap` `break` 、エラーオブジェクトが抑制され、例外が再スローされます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-152">If the final statement executed in the body of a `trap` statement is `break`, the error object is suppressed and the exception is re-thrown.</span></span>

<span data-ttu-id="20bb6-153">次の例では、ステートメントを使用してトラップされる **DivideByZeroException** 例外を作成し `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-153">The following example create a **DivideByZeroException** exception that is trapped using the `trap` statement.</span></span>

```powershell
function test {
  trap [DivideByZeroException] {
    Write-Host 'divide by zero trapped'
    break
  }

  $i = 3
  'Before loop'
  while ($true) {
     "1 / $i = " + (1 / $i--)
  }
  'After loop'
}
test
```

例外で実行が停止することに注意してください。 <span data-ttu-id="20bb6-155">に `After loop` 到達していません。</span><span class="sxs-lookup"><span data-stu-id="20bb6-155">The `After loop` is never reached.</span></span>
<span data-ttu-id="20bb6-156">を実行すると、例外が再スローされ `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="20bb6-156">The exception is re-thrown after the `trap` executes.</span></span>

```Output
Before loop
1 / 3 = 0.333333333333333
1 / 2 = 0.5
1 / 1 = 1
divide by zero trapped
ParentContainsErrorRecordException:
Line |
  10 |       "1 / $i = " + (1 / $i--)
     |       ~~~~~~~~~~~~~~~~~~~~~~~~
     | Attempted to divide by zero.
```

## <a name="do-not-use-break-outside-of-a-loop-switch-or-trap"></a><span data-ttu-id="20bb6-157">ループ、スイッチ、またはトラップの外側では中断を使用しない</span><span class="sxs-lookup"><span data-stu-id="20bb6-157">Do not use break outside of a loop, switch, or trap</span></span>

<span data-ttu-id="20bb6-158">`break`を直接サポートするコンストラクト (ループ、、) の外部でを使用した場合 `switch` `trap` 、PowerShell は外側の構造体の _呼び出し履歴_ を検索します。</span><span class="sxs-lookup"><span data-stu-id="20bb6-158">When `break` is used outside of a construct that directly supports it (loops, `switch`, `trap`), PowerShell looks _up the call stack_ for an enclosing construct.</span></span> <span data-ttu-id="20bb6-159">外側のコンストラクトが見つからない場合、現在の実行空間は自動的に終了します。</span><span class="sxs-lookup"><span data-stu-id="20bb6-159">If it can't find an enclosing construct, the current runspace is quietly terminated.</span></span>

<span data-ttu-id="20bb6-160">これは、それをサポートする外側のコンストラクトの外部でを使用する関数とスクリプト `break` が誤って _呼び出し元_ を終了する可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="20bb6-160">This means that functions and scripts that inadvertently use a `break` outside of an enclosing construct that supports it can inadvertently terminate their _callers_.</span></span>

<span data-ttu-id="20bb6-161">パイプライン内でを使用する `break` `break` と、 `ForEach-Object` パイプラインが終了するだけでなく、実行空間全体が終了する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="20bb6-161">Using `break` inside a pipeline `break`, such as a `ForEach-Object` script block, not only exits the pipeline, it potentially terminates the entire runspace.</span></span>

## <a name="see-also"></a><span data-ttu-id="20bb6-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="20bb6-162">See also</span></span>

[<span data-ttu-id="20bb6-163">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="20bb6-163">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="20bb6-164">about_Continue</span><span class="sxs-lookup"><span data-stu-id="20bb6-164">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="20bb6-165">about_For</span><span class="sxs-lookup"><span data-stu-id="20bb6-165">about_For</span></span>](about_For.md)

[<span data-ttu-id="20bb6-166">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="20bb6-166">about_Foreach</span></span>](about_Foreach.md)

[<span data-ttu-id="20bb6-167">about_Switch</span><span class="sxs-lookup"><span data-stu-id="20bb6-167">about_Switch</span></span>](about_Switch.md)

[<span data-ttu-id="20bb6-168">about_Throw</span><span class="sxs-lookup"><span data-stu-id="20bb6-168">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="20bb6-169">about_Trap</span><span class="sxs-lookup"><span data-stu-id="20bb6-169">about_Trap</span></span>](about_Trap.md)

[<span data-ttu-id="20bb6-170">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="20bb6-170">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)

[<span data-ttu-id="20bb6-171">about_While</span><span class="sxs-lookup"><span data-stu-id="20bb6-171">about_While</span></span>](about_While.md)
