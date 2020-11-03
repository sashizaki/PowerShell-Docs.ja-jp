---
description: While または Until 条件に従って、ステートメントリストを1回以上実行します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_do?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Do
ms.openlocfilehash: 2cffc5293ee8c636eb58d1f9951e34852eb465f0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222107"
---
# <a name="about-do"></a><span data-ttu-id="0eb8d-104">作業の概要</span><span class="sxs-lookup"><span data-stu-id="0eb8d-104">About Do</span></span>

## <a name="short-description"></a><span data-ttu-id="0eb8d-105">概要</span><span class="sxs-lookup"><span data-stu-id="0eb8d-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="0eb8d-106">While または Until 条件に従って、ステートメントリストを1回以上実行します。</span><span class="sxs-lookup"><span data-stu-id="0eb8d-106">Runs a statement list one or more times, subject to a While or Until condition.</span></span>

## <a name="long-description"></a><span data-ttu-id="0eb8d-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="0eb8d-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="0eb8d-108">Do キーワードは、While キーワードまたは Until キーワードを使用して、スクリプトブロック内でステートメントを実行します。このとき、条件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="0eb8d-108">The Do keyword works with the While keyword or the Until keyword to run the statements in a script block, subject to a condition.</span></span> <span data-ttu-id="0eb8d-109">関連する While ループとは異なり、Do ループ内のスクリプトブロックは常に少なくとも1回は実行されます。</span><span class="sxs-lookup"><span data-stu-id="0eb8d-109">Unlike the related While loop, the script block in a Do loop always runs at least once.</span></span>

<span data-ttu-id="0eb8d-110">**Do while** ループは、さまざまな while ループです。</span><span class="sxs-lookup"><span data-stu-id="0eb8d-110">A **Do-While** loop is a variety of the While loop.</span></span> <span data-ttu-id="0eb8d-111">**Do while** ループでは、スクリプトブロックの実行後に条件が評価されます。</span><span class="sxs-lookup"><span data-stu-id="0eb8d-111">In a **Do-While** loop, the condition is evaluated after the script block has run.</span></span> <span data-ttu-id="0eb8d-112">While ループと同様に、条件が true と評価される限り、スクリプトブロックが繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="0eb8d-112">As in a While loop, the script block is repeated as long as the condition evaluates to true.</span></span>

<span data-ttu-id="0eb8d-113">**Do while** ループと同様に、 **do until** ループは、条件が評価される前に常に少なくとも1回は実行されます。</span><span class="sxs-lookup"><span data-stu-id="0eb8d-113">Like a **Do-While** loop, a **Do-Until** loop always runs at least once before the condition is evaluated.</span></span> <span data-ttu-id="0eb8d-114">ただし、スクリプトブロックは、条件が false のときにのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="0eb8d-114">However, the script block runs only while the condition is false.</span></span>

<span data-ttu-id="0eb8d-115">*Continue* および *Break* flow 制御キーワードは、 **Do While** ループまたは **do until** ループで使用できます。</span><span class="sxs-lookup"><span data-stu-id="0eb8d-115">The *Continue* and *Break* flow control keywords can be used in a **Do-While** loop or in a **Do-Until** loop.</span></span>

### <a name="syntax"></a><span data-ttu-id="0eb8d-116">構文</span><span class="sxs-lookup"><span data-stu-id="0eb8d-116">Syntax</span></span>

<span data-ttu-id="0eb8d-117">次に、 **Do While** ステートメントの構文を示します。</span><span class="sxs-lookup"><span data-stu-id="0eb8d-117">The following shows the syntax of the **Do-While** statement:</span></span>

```powershell
do {<statement list>} while (<condition>)
```

<span data-ttu-id="0eb8d-118">次に、 **Do Until** ステートメントの構文を示します。</span><span class="sxs-lookup"><span data-stu-id="0eb8d-118">The following shows the syntax of the **Do-Until** statement:</span></span>

```powershell
do {<statement list>} until (<condition>)
```

<span data-ttu-id="0eb8d-119">ステートメントの一覧には、ループが入力または繰り返されるたびに実行されるステートメントが1つ以上含まれています。</span><span class="sxs-lookup"><span data-stu-id="0eb8d-119">The statement list contains one or more statements that run each time the loop is entered or repeated.</span></span>

<span data-ttu-id="0eb8d-120">ステートメントの条件部分は、true または false に解決されます。</span><span class="sxs-lookup"><span data-stu-id="0eb8d-120">The condition portion of the statement resolves to true or false.</span></span>

### <a name="example"></a><span data-ttu-id="0eb8d-121">例</span><span class="sxs-lookup"><span data-stu-id="0eb8d-121">Example</span></span>

<span data-ttu-id="0eb8d-122">次の Do ステートメントの例では、値が0の項目に到達するまで配列内の項目をカウントします。</span><span class="sxs-lookup"><span data-stu-id="0eb8d-122">The following example of a Do statement counts the items in an array until it reaches an item with a value of 0.</span></span>

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } while ($x[$a] -ne 0)
C:\PS> $count
3
```

<span data-ttu-id="0eb8d-123">次の例では、Until キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="0eb8d-123">The following example uses the Until keyword.</span></span> <span data-ttu-id="0eb8d-124">不等号演算子 ( `-ne` ) が equal to 演算子 () に置き換えられていることに注意して `-eq` ください。</span><span class="sxs-lookup"><span data-stu-id="0eb8d-124">Notice that the not equal to operator (`-ne`) is replaced by the equal to operator (`-eq`).</span></span>

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } until ($x[$a] -eq 0)
C:\PS> $count
3
```

<span data-ttu-id="0eb8d-125">次の例では、0未満の値をすべてスキップして、配列のすべての値を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="0eb8d-125">The following example writes all the values of an array, skipping any value that is less than zero.</span></span>

```powershell
do {
  if ($x[$a] -lt 0) { continue }
  Write-Host $x[$a]
}
while (++$a -lt 10)
```

## <a name="see-also"></a><span data-ttu-id="0eb8d-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="0eb8d-126">SEE ALSO</span></span>

[<span data-ttu-id="0eb8d-127">about_While</span><span class="sxs-lookup"><span data-stu-id="0eb8d-127">about_While</span></span>](about_While.md)

[<span data-ttu-id="0eb8d-128">about_Operators</span><span class="sxs-lookup"><span data-stu-id="0eb8d-128">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="0eb8d-129">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="0eb8d-129">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)

[<span data-ttu-id="0eb8d-130">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="0eb8d-130">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="0eb8d-131">about_Break</span><span class="sxs-lookup"><span data-stu-id="0eb8d-131">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="0eb8d-132">about_Continue</span><span class="sxs-lookup"><span data-stu-id="0eb8d-132">about_Continue</span></span>](about_Continue.md)

