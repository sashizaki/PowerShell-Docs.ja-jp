---
description: 1つまたは複数の条件付きテストの結果に基づいてステートメントリストを実行するために使用できる言語コマンドについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_If
ms.openlocfilehash: 33c0050cb5f8c3dfa623213b288ef3a84d10099d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220875"
---
# <a name="about-if"></a><span data-ttu-id="13a90-104">について</span><span class="sxs-lookup"><span data-stu-id="13a90-104">About If</span></span>

## <a name="short-description"></a><span data-ttu-id="13a90-105">概要</span><span class="sxs-lookup"><span data-stu-id="13a90-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="13a90-106">1つまたは複数の条件付きテストの結果に基づいてステートメントリストを実行するために使用できる言語コマンドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="13a90-106">Describes a language command you can use to run statement lists based on the results of one or more conditional tests.</span></span>

## <a name="long-description"></a><span data-ttu-id="13a90-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="13a90-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="13a90-108">`If`指定した条件テストが true と評価された場合に、ステートメントを使用してコードブロックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="13a90-108">You can use the `If` statement to run code blocks if a specified conditional test evaluates to true.</span></span> <span data-ttu-id="13a90-109">前のテストがすべて false と評価された場合に実行する1つ以上の条件付きテストを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="13a90-109">You can also specify one or more additional conditional tests to run if all the prior tests evaluate to false.</span></span> <span data-ttu-id="13a90-110">最後に、他の条件付きテストが true と評価されなかった場合に実行される追加のコードブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="13a90-110">Finally, you can specify an additional code block that is run if no other prior conditional test evaluates to true.</span></span>

### <a name="syntax"></a><span data-ttu-id="13a90-111">構文</span><span class="sxs-lookup"><span data-stu-id="13a90-111">Syntax</span></span>

<span data-ttu-id="13a90-112">次の例は、ステートメントの構文を示してい `If` ます。</span><span class="sxs-lookup"><span data-stu-id="13a90-112">The following example shows the `If` statement syntax:</span></span>

```powershell
if (<test1>)
    {<statement list 1>}
[elseif (<test2>)
    {<statement list 2>}]
[else
    {<statement list 3>}]
```

<span data-ttu-id="13a90-113">ステートメントを実行すると `If` 、PowerShell によっ `<test1>` て条件式が true または false として評価されます。</span><span class="sxs-lookup"><span data-stu-id="13a90-113">When you run an `If` statement, PowerShell evaluates the `<test1>` conditional expression as true or false.</span></span> <span data-ttu-id="13a90-114">`<test1>`が true の場合、が実行され、 `<statement list 1>` PowerShell によってステートメントが終了し `If` ます。</span><span class="sxs-lookup"><span data-stu-id="13a90-114">If `<test1>` is true, `<statement list 1>` runs, and PowerShell exits the `If` statement.</span></span> <span data-ttu-id="13a90-115">`<test1>`が false の場合、PowerShell は条件付きステートメントによって指定された条件を評価し `<test2>` ます。</span><span class="sxs-lookup"><span data-stu-id="13a90-115">If `<test1>` is false, PowerShell evaluates the condition specified by the `<test2>` conditional statement.</span></span>

<span data-ttu-id="13a90-116">`<test2>`が true の場合、が実行され、 `<statement list 2>` PowerShell によってステートメントが終了し `If` ます。</span><span class="sxs-lookup"><span data-stu-id="13a90-116">If `<test2>` is true, `<statement list 2>` runs, and PowerShell exits the `If` statement.</span></span> <span data-ttu-id="13a90-117">との両方が false と評価された場合 `<test1>` `<test2>` 、 `<statement list 3`> コードブロックが実行され、PowerShell は If ステートメントを終了します。</span><span class="sxs-lookup"><span data-stu-id="13a90-117">If both `<test1>` and `<test2>` evaluate to false, the `<statement list 3`> code block runs, and PowerShell exits the If statement.</span></span>

<span data-ttu-id="13a90-118">複数の Elseif ステートメントを使用して、一連の条件付きテストをチェーンすることができます。</span><span class="sxs-lookup"><span data-stu-id="13a90-118">You can use multiple Elseif statements to chain a series of conditional tests.</span></span> <span data-ttu-id="13a90-119">そのため、各テストは、前のすべてのテストが false の場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="13a90-119">So, that each test is run only if all the previous tests are false.</span></span>
<span data-ttu-id="13a90-120">多くの Elseif ステートメントを含むステートメントを作成する必要がある場合は `If` 、代わりに Switch ステートメントを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="13a90-120">If you need to create an `If` statement that contains many Elseif statements, consider using a Switch statement instead.</span></span>

<span data-ttu-id="13a90-121">例 :</span><span class="sxs-lookup"><span data-stu-id="13a90-121">Examples:</span></span>

<span data-ttu-id="13a90-122">最も単純 `If` なステートメントには1つのコマンドが含まれており、Elseif ステートメントや Else ステートメントは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="13a90-122">The simplest `If` statement contains a single command and does not contain any Elseif statements or any Else statements.</span></span> <span data-ttu-id="13a90-123">次の例は、ステートメントの最も単純な形式を示してい `If` ます。</span><span class="sxs-lookup"><span data-stu-id="13a90-123">The following example shows the simplest form of the `If` statement:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
```

<span data-ttu-id="13a90-124">この例では、$a 変数が2より大きい場合、条件は true に評価され、ステートメントリストが実行されます。</span><span class="sxs-lookup"><span data-stu-id="13a90-124">In this example, if the $a variable is greater than 2, the condition evaluates to true, and the statement list runs.</span></span> <span data-ttu-id="13a90-125">ただし、$a が2以下であるか、または既存の変数ではない場合、 `If` ステートメントはメッセージを表示しません。</span><span class="sxs-lookup"><span data-stu-id="13a90-125">However, if $a is less than or equal to 2 or is not an existing variable, the `If` statement does not display a message.</span></span>

<span data-ttu-id="13a90-126">Else ステートメントを追加すると、$a が2以下の場合にメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="13a90-126">By adding an Else statement, a message is displayed when $a is less than or equal to 2.</span></span> <span data-ttu-id="13a90-127">次の例に示すように、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="13a90-127">As the next example shows:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
else {
    Write-Host ("The value $a is less than or equal to 2," +
        " is not created or is not initialized.")
}
```

<span data-ttu-id="13a90-128">この例をさらに絞り込むために、$a の値が2に等しい場合に、Elseif ステートメントを使用してメッセージを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="13a90-128">To further refine this example, you can use the Elseif statement to display a message when the value of $a is equal to 2.</span></span> <span data-ttu-id="13a90-129">次の例に示すように、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="13a90-129">As the next example shows:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
elseif ($a -eq 2) {
    Write-Host "The value $a is equal to 2."
}
else {
    Write-Host ("The value $a is less than 2 or" +
        " was not created or initialized.")
}
```

### <a name="using-the-ternary-operator-syntax"></a><span data-ttu-id="13a90-130">三項演算子の構文の使用</span><span class="sxs-lookup"><span data-stu-id="13a90-130">Using the ternary operator syntax</span></span>

<span data-ttu-id="13a90-131">PowerShell 7.0 では、三項演算子を使用した新しい構文が導入されました。</span><span class="sxs-lookup"><span data-stu-id="13a90-131">PowerShell 7.0 introduced a new syntax using the ternary operator.</span></span> <span data-ttu-id="13a90-132">C# の三項演算子の構文に従います。</span><span class="sxs-lookup"><span data-stu-id="13a90-132">It follows the C# ternary operator syntax:</span></span>

```Syntax
<condition> ? <if-true> : <if-false>
```

<span data-ttu-id="13a90-133">三項演算子は、簡略化されたステートメントと同様に動作し `if-else` ます。</span><span class="sxs-lookup"><span data-stu-id="13a90-133">The ternary operator behaves like the simplified `if-else` statement.</span></span> <span data-ttu-id="13a90-134">`<condition>`式が評価され、結果がブール値に変換されて、次に評価する分岐を決定します。</span><span class="sxs-lookup"><span data-stu-id="13a90-134">The `<condition>` expression is evaluated and the result is converted to a boolean to determine which branch should be evaluated next:</span></span>

- <span data-ttu-id="13a90-135">`<if-true>` 式は、`<condition>` 式が true の場合に実行されます</span><span class="sxs-lookup"><span data-stu-id="13a90-135">The `<if-true>` expression is executed if the `<condition>` expression is true</span></span>
- <span data-ttu-id="13a90-136">`<if-false>` 式は、`<condition>` 式が false の場合に実行されます</span><span class="sxs-lookup"><span data-stu-id="13a90-136">The `<if-false>` expression is executed if the `<condition>` expression is false</span></span>

<span data-ttu-id="13a90-137">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="13a90-137">For example:</span></span>

```powershell
$message = (Test-Path $path) ? "Path exists" : "Path not found"
```

<span data-ttu-id="13a90-138">この例で `$message` は、がを返すと、の値は "Path exists" になり `Test-Path` `$true` ます。</span><span class="sxs-lookup"><span data-stu-id="13a90-138">In this example, the value of `$message` is "Path exists" when `Test-Path` returns `$true`.</span></span> <span data-ttu-id="13a90-139">`Test-Path`がを返す場合 `$false` 、の値 `$message` は "Path not found" になります。</span><span class="sxs-lookup"><span data-stu-id="13a90-139">When `Test-Path` returns `$false`, the value of `$message` is "Path not found".</span></span>

```powershell
$service = Get-Service BITS
$service.Status -eq 'Running' ? (Stop-Service $service) : (Start-Service $service)
```

<span data-ttu-id="13a90-140">この例では、サービスが実行されている場合は停止され、状態が **実行中** でない場合は開始されます。</span><span class="sxs-lookup"><span data-stu-id="13a90-140">In this example, if the service is running, it is stopped, and if its status is not **Running** , it is started.</span></span>

## <a name="see-also"></a><span data-ttu-id="13a90-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="13a90-141">SEE ALSO</span></span>

[<span data-ttu-id="13a90-142">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="13a90-142">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="13a90-143">about_Switch</span><span class="sxs-lookup"><span data-stu-id="13a90-143">about_Switch</span></span>](about_Switch.md)

