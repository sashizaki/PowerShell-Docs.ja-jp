---
description: 1つまたは複数の条件付きテストの結果に基づいてステートメントリストを実行するために使用できる言語コマンドについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_If
ms.openlocfilehash: 8b1be96167dab47e7e15e3e5b89c46126f117541
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223448"
---
# <a name="about-if"></a><span data-ttu-id="463df-104">について</span><span class="sxs-lookup"><span data-stu-id="463df-104">About If</span></span>

## <a name="short-description"></a><span data-ttu-id="463df-105">概要</span><span class="sxs-lookup"><span data-stu-id="463df-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="463df-106">1つまたは複数の条件付きテストの結果に基づいてステートメントリストを実行するために使用できる言語コマンドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="463df-106">Describes a language command you can use to run statement lists based on the results of one or more conditional tests.</span></span>

## <a name="long-description"></a><span data-ttu-id="463df-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="463df-107">LONG DESCRIPTION</span></span>
<span data-ttu-id="463df-108">`If`指定した条件テストが true と評価された場合に、ステートメントを使用してコードブロックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="463df-108">You can use the `If` statement to run code blocks if a specified conditional test evaluates to true.</span></span> <span data-ttu-id="463df-109">前のテストがすべて false と評価された場合に実行する1つ以上の条件付きテストを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="463df-109">You can also specify one or more additional conditional tests to run if all the prior tests evaluate to false.</span></span> <span data-ttu-id="463df-110">最後に、他の条件付きテストが true と評価されなかった場合に実行される追加のコードブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="463df-110">Finally, you can specify an additional code block that is run if no other prior conditional test evaluates to true.</span></span>

### <a name="syntax"></a><span data-ttu-id="463df-111">構文</span><span class="sxs-lookup"><span data-stu-id="463df-111">Syntax</span></span>

<span data-ttu-id="463df-112">次の例は、ステートメントの構文を示してい `If` ます。</span><span class="sxs-lookup"><span data-stu-id="463df-112">The following example shows the `If` statement syntax:</span></span>

```powershell
if (<test1>)
    {<statement list 1>}
[elseif (<test2>)
    {<statement list 2>}]
[else
    {<statement list 3>}]
```

<span data-ttu-id="463df-113">ステートメントを実行すると `If` 、PowerShell によっ `<test1>` て条件式が true または false として評価されます。</span><span class="sxs-lookup"><span data-stu-id="463df-113">When you run an `If` statement, PowerShell evaluates the `<test1>` conditional expression as true or false.</span></span> <span data-ttu-id="463df-114">`<test1>`が true の場合、が実行され、 `<statement list 1>` PowerShell によってステートメントが終了し `If` ます。</span><span class="sxs-lookup"><span data-stu-id="463df-114">If `<test1>` is true, `<statement list 1>` runs, and PowerShell exits the `If` statement.</span></span> <span data-ttu-id="463df-115">`<test1>`が false の場合、PowerShell は条件付きステートメントによって指定された条件を評価し `<test2>` ます。</span><span class="sxs-lookup"><span data-stu-id="463df-115">If `<test1>` is false, PowerShell evaluates the condition specified by the `<test2>` conditional statement.</span></span>

<span data-ttu-id="463df-116">`<test2>`が true の場合、が実行され、 `<statement list 2>` PowerShell によってステートメントが終了し `If` ます。</span><span class="sxs-lookup"><span data-stu-id="463df-116">If `<test2>` is true, `<statement list 2>` runs, and PowerShell exits the `If` statement.</span></span> <span data-ttu-id="463df-117">との両方が false と評価された場合 `<test1>` `<test2>` 、 `<statement list 3`> コードブロックが実行され、PowerShell は If ステートメントを終了します。</span><span class="sxs-lookup"><span data-stu-id="463df-117">If both `<test1>` and `<test2>` evaluate to false, the `<statement list 3`> code block runs, and PowerShell exits the If statement.</span></span>

<span data-ttu-id="463df-118">複数の Elseif ステートメントを使用して、一連の条件付きテストをチェーンすることができます。</span><span class="sxs-lookup"><span data-stu-id="463df-118">You can use multiple Elseif statements to chain a series of conditional tests.</span></span> <span data-ttu-id="463df-119">そのため、各テストは、前のすべてのテストが false の場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="463df-119">So, that each test is run only if all the previous tests are false.</span></span>
<span data-ttu-id="463df-120">多くの Elseif ステートメントを含むステートメントを作成する必要がある場合は `If` 、代わりに Switch ステートメントを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="463df-120">If you need to create an `If` statement that contains many Elseif statements, consider using a Switch statement instead.</span></span>

<span data-ttu-id="463df-121">例 :</span><span class="sxs-lookup"><span data-stu-id="463df-121">Examples:</span></span>

<span data-ttu-id="463df-122">最も単純 `If` なステートメントには1つのコマンドが含まれており、Elseif ステートメントや Else ステートメントは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="463df-122">The simplest `If` statement contains a single command and does not contain any Elseif statements or any Else statements.</span></span> <span data-ttu-id="463df-123">次の例は、ステートメントの最も単純な形式を示してい `If` ます。</span><span class="sxs-lookup"><span data-stu-id="463df-123">The following example shows the simplest form of the `If` statement:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
```

<span data-ttu-id="463df-124">この例では、$a 変数が2より大きい場合、条件は true に評価され、ステートメントリストが実行されます。</span><span class="sxs-lookup"><span data-stu-id="463df-124">In this example, if the $a variable is greater than 2, the condition evaluates to true, and the statement list runs.</span></span> <span data-ttu-id="463df-125">ただし、$a が2以下であるか、または既存の変数ではない場合、 `If` ステートメントはメッセージを表示しません。</span><span class="sxs-lookup"><span data-stu-id="463df-125">However, if $a is less than or equal to 2 or is not an existing variable, the `If` statement does not display a message.</span></span>

<span data-ttu-id="463df-126">Else ステートメントを追加すると、$a が2以下の場合にメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="463df-126">By adding an Else statement, a message is displayed when $a is less than or equal to 2.</span></span> <span data-ttu-id="463df-127">次の例に示すように、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="463df-127">As the next example shows:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
else {
    Write-Host ("The value $a is less than or equal to 2," +
        " is not created or is not initialized.")
}
```

<span data-ttu-id="463df-128">この例をさらに絞り込むために、$a の値が2に等しい場合に、Elseif ステートメントを使用してメッセージを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="463df-128">To further refine this example, you can use the Elseif statement to display a message when the value of $a is equal to 2.</span></span> <span data-ttu-id="463df-129">次の例に示すように、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="463df-129">As the next example shows:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="463df-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="463df-130">SEE ALSO</span></span>

[<span data-ttu-id="463df-131">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="463df-131">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="463df-132">about_Switch</span><span class="sxs-lookup"><span data-stu-id="463df-132">about_Switch</span></span>](about_Switch.md)
