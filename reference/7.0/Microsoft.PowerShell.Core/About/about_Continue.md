---
description: ステートメントがプログラム `continue` フロー、 `switch` ステートメント、またはステートメントの先頭にプログラムフローを直ちに返す方法について説明し `trap` ます。
keywords: powershell,コマンドレット
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_continue?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Continue
ms.openlocfilehash: 96758fb110ec1496ebbc073cdacfd3dcc15ae486
ms.sourcegitcommit: 0c31814bed14ff715dc7d4aace07cbdc6df2438e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "97614083"
---
# <a name="about-continue"></a><span data-ttu-id="dffdf-104">続行について</span><span class="sxs-lookup"><span data-stu-id="dffdf-104">About Continue</span></span>

## <a name="short-description"></a><span data-ttu-id="dffdf-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="dffdf-105">Short description</span></span>

<span data-ttu-id="dffdf-106">ステートメントがプログラム `continue` フロー、 `switch` ステートメント、またはステートメントの先頭にプログラムフローを直ちに返す方法について説明し `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="dffdf-106">Describes how the `continue` statement immediately returns the program flow to the top of a program loop, a `switch` statement, or a `trap` statement.</span></span>

## <a name="long-description"></a><span data-ttu-id="dffdf-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="dffdf-107">Long description</span></span>

<span data-ttu-id="dffdf-108">ステートメントは、を `continue` 完全に終了するのではなく、現在のコントロールブロックを終了し、実行を継続する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="dffdf-108">The `continue` statement provides a way to exit the current control block but continue execution, rather than exit completely.</span></span> <span data-ttu-id="dffdf-109">ステートメントでは、ラベルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dffdf-109">The statement supports labels.</span></span>
<span data-ttu-id="dffdf-110">ラベルは、スクリプト内のステートメントに割り当てる名前です。</span><span class="sxs-lookup"><span data-stu-id="dffdf-110">A label is a name you assign to a statement in a script.</span></span>

## <a name="using-continue-in-loops"></a><span data-ttu-id="dffdf-111">Continue in ループの使用</span><span class="sxs-lookup"><span data-stu-id="dffdf-111">Using continue in loops</span></span>

<span data-ttu-id="dffdf-112">ラベル `continue` が付けられていないステートメントは `for` 、、、 `foreach` `do` 、またはステートメントによって制御される最も内側のループの一番上にプログラムフローを直ちに返し `while` ます。</span><span class="sxs-lookup"><span data-stu-id="dffdf-112">An unlabeled `continue` statement immediately returns the program flow to the top of the innermost loop that is controlled by a `for`, `foreach`, `do`, or `while` statement.</span></span> <span data-ttu-id="dffdf-113">ループの現在の反復処理が終了し、ループは次の反復処理で続行されます。</span><span class="sxs-lookup"><span data-stu-id="dffdf-113">The current iteration of the loop is terminated and the loop continues with the next iteration.</span></span>

<span data-ttu-id="dffdf-114">次の例では、 `while` `$ctr` 変数が5に等しい場合、プログラムフローがループの先頭に戻ります。</span><span class="sxs-lookup"><span data-stu-id="dffdf-114">In the following example, program flow returns to the top of the `while` loop if the `$ctr` variable is equal to 5.</span></span> <span data-ttu-id="dffdf-115">結果として、1から10までのすべての数値が表示されます (5 を除く)。</span><span class="sxs-lookup"><span data-stu-id="dffdf-115">As a result, all the numbers between 1 and 10 are displayed except for 5:</span></span>

```powershell
while ($ctr -lt 10)
{
    $ctr += 1
    if ($ctr -eq 5)
    {
        continue
    }

    Write-Host -Object $ctr
}
```

<span data-ttu-id="dffdf-116">ループを使用すると、ステートメントで実行が続行され、 `for` `<Repeat>` その後にテストが続き `<Condition>` ます。</span><span class="sxs-lookup"><span data-stu-id="dffdf-116">When using a `for` loop, execution continues at the `<Repeat>` statement, followed by the `<Condition>` test.</span></span> <span data-ttu-id="dffdf-117">次の例では、キーワードの後にのデクリメントが発生するため、無限ループは発生しません `$i` `continue` 。</span><span class="sxs-lookup"><span data-stu-id="dffdf-117">In the example below, an infinite loop will not occur because the decrement of `$i` occurs after the `continue` keyword.</span></span>

```powershell
#   <Init>  <Condition> <Repeat>
for ($i = 0; $i -lt 10; $i++)
{
    Write-Host -Object $i
    if ($i -eq 5)
    {
        continue
        # Will not result in an infinite loop.
        $i--
    }
}
```

### <a name="using-a-labeled-continue-in-a-loop"></a><span data-ttu-id="dffdf-118">ループ内でのラベル付き continue の使用</span><span class="sxs-lookup"><span data-stu-id="dffdf-118">Using a labeled continue in a loop</span></span>

<span data-ttu-id="dffdf-119">ラベルが付けられたステートメントは、 `continue` イテレーションの実行を終了し、対象となる対象のイテレーションまたはステートメントのラベルに制御を転送し `switch` ます。</span><span class="sxs-lookup"><span data-stu-id="dffdf-119">A labeled `continue` statement terminates execution of the iteration and transfers control to the targeted enclosing iteration or `switch` statement label.</span></span>

<span data-ttu-id="dffdf-120">次の例では、が True の場合、最も内側のが終了し、の `for` `$condition` 2 番目のループで反復処理が続行され `for` `labelB` ます。</span><span class="sxs-lookup"><span data-stu-id="dffdf-120">In the following example, the innermost `for` is terminated when `$condition` is **True** and iteration continues with the second `for` loop at `labelB`.</span></span>

```powershell
:labelA for ($i = 1; $i -le 10; $i++) {
    :labelB for ($j = 1; $j -le 10; $j++) {
        :labelC for ($k = 1; $k -le 10; $k++) {
            if ($condition) {
                continue labelB
            } else {
                $condition = Update-Condition
            }
        }
    }
}
```

## <a name="using-continue-in-a-switch-statement"></a><span data-ttu-id="dffdf-121">Switch ステートメントで continue を使用する</span><span class="sxs-lookup"><span data-stu-id="dffdf-121">Using continue in a switch statement</span></span>

<span data-ttu-id="dffdf-122">内のラベル付けされ `continue` ていないステートメントは、 `switch` 現在の反復の実行 `switch` を終了し、の先頭に制御を移して `switch` 次の入力項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="dffdf-122">An unlabeled `continue` statement within a `switch` terminates execution of the current `switch` iteration and transfers control to the top of the `switch` to get the next input item.</span></span>

<span data-ttu-id="dffdf-123">1つの入力項目がある場合 `continue` 、ステートメント全体が終了し `switch` ます。</span><span class="sxs-lookup"><span data-stu-id="dffdf-123">When there is a single input item `continue` exits the entire `switch` statement.</span></span>
<span data-ttu-id="dffdf-124">入力がコレクションの場合は、 `switch` によって `switch` コレクションの各要素がテストされます。</span><span class="sxs-lookup"><span data-stu-id="dffdf-124">When the `switch` input is a collection, the `switch` tests each element of the collection.</span></span> <span data-ttu-id="dffdf-125">は `continue` 現在の反復処理を終了し、は `switch` 次の要素に進みます。</span><span class="sxs-lookup"><span data-stu-id="dffdf-125">The `continue` exits the current iteration and the `switch` continues with the next element.</span></span>

```powershell
switch (1,2,3) {
  2 { continue }  # moves on to the next element, 3
  default { $_ }
}
```

```Output
1
3
```

## <a name="using-continue-in-a-trap-statement"></a><span data-ttu-id="dffdf-126">Trap ステートメントで continue を使用する</span><span class="sxs-lookup"><span data-stu-id="dffdf-126">Using continue in a trap statement</span></span>

<span data-ttu-id="dffdf-127">本体で実行された最後のステートメント `trap` がの場合 `continue` 、トラップされたエラーは警告なしで無視され、実行が発生したステートメントの直後にあるステートメントから実行が続行され `trap` ます。</span><span class="sxs-lookup"><span data-stu-id="dffdf-127">If the final statement executed in the body a `trap` statement is `continue`, the trapped error is silently ignored and execution continues with the statement immediately following the one that caused `trap` to occur.</span></span>

## <a name="do-not-use-continue-outside-of-a-loop-switch-or-trap"></a><span data-ttu-id="dffdf-128">ループ、スイッチ、またはトラップの外側で [続行] を使用しない</span><span class="sxs-lookup"><span data-stu-id="dffdf-128">Do not use continue outside of a loop, switch, or trap</span></span>

<span data-ttu-id="dffdf-129">`continue`を直接サポートするコンストラクト (ループ、、) の外部でを使用した場合 `switch` `trap` 、PowerShell は外側の構造体の _呼び出し履歴_ を検索します。</span><span class="sxs-lookup"><span data-stu-id="dffdf-129">When `continue` is used outside of a construct that directly supports it (loops, `switch`, `trap`), PowerShell looks _up the call stack_ for an enclosing construct.</span></span> <span data-ttu-id="dffdf-130">外側のコンストラクトが見つからない場合、現在の実行空間は自動的に終了します。</span><span class="sxs-lookup"><span data-stu-id="dffdf-130">If it can't find an enclosing construct, the current runspace is quietly terminated.</span></span>

<span data-ttu-id="dffdf-131">これは、それをサポートする外側のコンストラクトの外部でを使用する関数とスクリプトが `continue` 誤って _呼び出し元_ を終了する可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="dffdf-131">This means that functions and scripts that inadvertently use a `continue` outside of an enclosing construct that supports it, can inadvertently terminate their _callers_.</span></span>

<span data-ttu-id="dffdf-132">パイプライン内でを使用する `continue` と、 `ForEach-Object` パイプラインが終了するだけでなく、実行空間全体が終了する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dffdf-132">Using `continue` inside a pipeline, such as a `ForEach-Object` script block, not only exits the pipeline, it potentially terminates the entire runspace.</span></span>

## <a name="see-also"></a><span data-ttu-id="dffdf-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="dffdf-133">See also</span></span>

[<span data-ttu-id="dffdf-134">about_Break</span><span class="sxs-lookup"><span data-stu-id="dffdf-134">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="dffdf-135">about_For</span><span class="sxs-lookup"><span data-stu-id="dffdf-135">about_For</span></span>](about_For.md)

[<span data-ttu-id="dffdf-136">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="dffdf-136">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="dffdf-137">about_Throw</span><span class="sxs-lookup"><span data-stu-id="dffdf-137">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="dffdf-138">about_Trap</span><span class="sxs-lookup"><span data-stu-id="dffdf-138">about_Trap</span></span>](about_Trap.md)

[<span data-ttu-id="dffdf-139">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="dffdf-139">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)
