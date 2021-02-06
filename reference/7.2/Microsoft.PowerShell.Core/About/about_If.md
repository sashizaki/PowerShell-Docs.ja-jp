---
description: 1つまたは複数の条件付きテストの結果に基づいてステートメントリストを実行するために使用できる言語コマンドについて説明します。
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_If
ms.openlocfilehash: 04c610af36e17c02d2440ab79b7de5330e5063ab
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600405"
---
# <a name="about-if"></a><span data-ttu-id="d6a1f-103">について</span><span class="sxs-lookup"><span data-stu-id="d6a1f-103">About If</span></span>

## <a name="short-description"></a><span data-ttu-id="d6a1f-104">概要</span><span class="sxs-lookup"><span data-stu-id="d6a1f-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="d6a1f-105">1つまたは複数の条件付きテストの結果に基づいてステートメントリストを実行するために使用できる言語コマンドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-105">Describes a language command you can use to run statement lists based on the results of one or more conditional tests.</span></span>

## <a name="long-description"></a><span data-ttu-id="d6a1f-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="d6a1f-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="d6a1f-107">`If`指定した条件テストが true と評価された場合に、ステートメントを使用してコードブロックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-107">You can use the `If` statement to run code blocks if a specified conditional test evaluates to true.</span></span> <span data-ttu-id="d6a1f-108">前のテストがすべて false と評価された場合に実行する1つ以上の条件付きテストを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-108">You can also specify one or more additional conditional tests to run if all the prior tests evaluate to false.</span></span> <span data-ttu-id="d6a1f-109">最後に、他の条件付きテストが true と評価されなかった場合に実行される追加のコードブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-109">Finally, you can specify an additional code block that is run if no other prior conditional test evaluates to true.</span></span>

### <a name="syntax"></a><span data-ttu-id="d6a1f-110">構文</span><span class="sxs-lookup"><span data-stu-id="d6a1f-110">Syntax</span></span>

<span data-ttu-id="d6a1f-111">次の例は、ステートメントの構文を示してい `If` ます。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-111">The following example shows the `If` statement syntax:</span></span>

```powershell
if (<test1>)
    {<statement list 1>}
[elseif (<test2>)
    {<statement list 2>}]
[else
    {<statement list 3>}]
```

<span data-ttu-id="d6a1f-112">ステートメントを実行すると `If` 、PowerShell によっ `<test1>` て条件式が true または false として評価されます。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-112">When you run an `If` statement, PowerShell evaluates the `<test1>` conditional expression as true or false.</span></span> <span data-ttu-id="d6a1f-113">`<test1>`が true の場合、が実行され、 `<statement list 1>` PowerShell によってステートメントが終了し `If` ます。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-113">If `<test1>` is true, `<statement list 1>` runs, and PowerShell exits the `If` statement.</span></span> <span data-ttu-id="d6a1f-114">`<test1>`が false の場合、PowerShell は条件付きステートメントによって指定された条件を評価し `<test2>` ます。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-114">If `<test1>` is false, PowerShell evaluates the condition specified by the `<test2>` conditional statement.</span></span>

<span data-ttu-id="d6a1f-115">`<test2>`が true の場合、が実行され、 `<statement list 2>` PowerShell によってステートメントが終了し `If` ます。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-115">If `<test2>` is true, `<statement list 2>` runs, and PowerShell exits the `If` statement.</span></span> <span data-ttu-id="d6a1f-116">との両方が false と評価された場合 `<test1>` `<test2>` 、 `<statement list 3`> コードブロックが実行され、PowerShell は If ステートメントを終了します。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-116">If both `<test1>` and `<test2>` evaluate to false, the `<statement list 3`> code block runs, and PowerShell exits the If statement.</span></span>

<span data-ttu-id="d6a1f-117">複数の Elseif ステートメントを使用して、一連の条件付きテストをチェーンすることができます。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-117">You can use multiple Elseif statements to chain a series of conditional tests.</span></span> <span data-ttu-id="d6a1f-118">そのため、各テストは、前のすべてのテストが false の場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-118">So, that each test is run only if all the previous tests are false.</span></span>
<span data-ttu-id="d6a1f-119">多くの Elseif ステートメントを含むステートメントを作成する必要がある場合は `If` 、代わりに Switch ステートメントを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-119">If you need to create an `If` statement that contains many Elseif statements, consider using a Switch statement instead.</span></span>

<span data-ttu-id="d6a1f-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-120">Examples:</span></span>

<span data-ttu-id="d6a1f-121">最も単純 `If` なステートメントには1つのコマンドが含まれており、Elseif ステートメントや Else ステートメントは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-121">The simplest `If` statement contains a single command and does not contain any Elseif statements or any Else statements.</span></span> <span data-ttu-id="d6a1f-122">次の例は、ステートメントの最も単純な形式を示してい `If` ます。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-122">The following example shows the simplest form of the `If` statement:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
```

<span data-ttu-id="d6a1f-123">この例では、$a 変数が2より大きい場合、条件は true に評価され、ステートメントリストが実行されます。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-123">In this example, if the $a variable is greater than 2, the condition evaluates to true, and the statement list runs.</span></span> <span data-ttu-id="d6a1f-124">ただし、$a が2以下であるか、または既存の変数ではない場合、 `If` ステートメントはメッセージを表示しません。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-124">However, if $a is less than or equal to 2 or is not an existing variable, the `If` statement does not display a message.</span></span>

<span data-ttu-id="d6a1f-125">Else ステートメントを追加すると、$a が2以下の場合にメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-125">By adding an Else statement, a message is displayed when $a is less than or equal to 2.</span></span> <span data-ttu-id="d6a1f-126">次の例に示すように、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-126">As the next example shows:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
else {
    Write-Host ("The value $a is less than or equal to 2," +
        " is not created or is not initialized.")
}
```

<span data-ttu-id="d6a1f-127">この例をさらに絞り込むために、$a の値が2に等しい場合に、Elseif ステートメントを使用してメッセージを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-127">To further refine this example, you can use the Elseif statement to display a message when the value of $a is equal to 2.</span></span> <span data-ttu-id="d6a1f-128">次の例に示すように、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-128">As the next example shows:</span></span>

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

### <a name="using-the-ternary-operator-syntax"></a><span data-ttu-id="d6a1f-129">三項演算子の構文の使用</span><span class="sxs-lookup"><span data-stu-id="d6a1f-129">Using the ternary operator syntax</span></span>

<span data-ttu-id="d6a1f-130">PowerShell 7.0 では、三項演算子を使用した新しい構文が導入されました。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-130">PowerShell 7.0 introduced a new syntax using the ternary operator.</span></span> <span data-ttu-id="d6a1f-131">C# の三項演算子の構文に従います。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-131">It follows the C# ternary operator syntax:</span></span>

```Syntax
<condition> ? <if-true> : <if-false>
```

<span data-ttu-id="d6a1f-132">三項演算子は、簡略化されたステートメントと同様に動作し `if-else` ます。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-132">The ternary operator behaves like the simplified `if-else` statement.</span></span> <span data-ttu-id="d6a1f-133">`<condition>`式が評価され、結果がブール値に変換されて、次に評価する分岐を決定します。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-133">The `<condition>` expression is evaluated and the result is converted to a boolean to determine which branch should be evaluated next:</span></span>

- <span data-ttu-id="d6a1f-134">`<if-true>` 式は、`<condition>` 式が true の場合に実行されます</span><span class="sxs-lookup"><span data-stu-id="d6a1f-134">The `<if-true>` expression is executed if the `<condition>` expression is true</span></span>
- <span data-ttu-id="d6a1f-135">`<if-false>` 式は、`<condition>` 式が false の場合に実行されます</span><span class="sxs-lookup"><span data-stu-id="d6a1f-135">The `<if-false>` expression is executed if the `<condition>` expression is false</span></span>

<span data-ttu-id="d6a1f-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-136">For example:</span></span>

```powershell
$message = (Test-Path $path) ? "Path exists" : "Path not found"
```

<span data-ttu-id="d6a1f-137">この例で `$message` は、がを返すと、の値は "Path exists" になり `Test-Path` `$true` ます。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-137">In this example, the value of `$message` is "Path exists" when `Test-Path` returns `$true`.</span></span> <span data-ttu-id="d6a1f-138">`Test-Path`がを返す場合 `$false` 、の値 `$message` は "Path not found" になります。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-138">When `Test-Path` returns `$false`, the value of `$message` is "Path not found".</span></span>

```powershell
$service = Get-Service BITS
$service.Status -eq 'Running' ? (Stop-Service $service) : (Start-Service $service)
```

<span data-ttu-id="d6a1f-139">この例では、サービスが実行されている場合は停止され、状態が **実行中** でない場合は開始されます。</span><span class="sxs-lookup"><span data-stu-id="d6a1f-139">In this example, if the service is running, it is stopped, and if its status is not **Running**, it is started.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6a1f-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6a1f-140">SEE ALSO</span></span>

[<span data-ttu-id="d6a1f-141">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="d6a1f-141">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="d6a1f-142">about_Switch</span><span class="sxs-lookup"><span data-stu-id="d6a1f-142">about_Switch</span></span>](about_Switch.md)

