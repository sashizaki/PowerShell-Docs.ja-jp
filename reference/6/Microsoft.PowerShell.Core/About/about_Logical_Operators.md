---
description: PowerShell のステートメントを接続する演算子について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logical_operators?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logical_Operators
ms.openlocfilehash: 483217e929d55097b56eade801682ea4484d2624
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224664"
---
# <a name="about_logical_operators"></a><span data-ttu-id="6b0f0-104">about_Logical_Operators</span><span class="sxs-lookup"><span data-stu-id="6b0f0-104">about_Logical_Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="6b0f0-105">概要</span><span class="sxs-lookup"><span data-stu-id="6b0f0-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="6b0f0-106">PowerShell のステートメントを接続する演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-106">Describes the operators that connect statements in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="6b0f0-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="6b0f0-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="6b0f0-108">PowerShell 論理演算子は、式とステートメントを接続します。これにより、1つの式を使用して複数の条件をテストできます。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-108">The PowerShell logical operators connect expressions and statements, allowing you to use a single expression to test for multiple conditions.</span></span>

<span data-ttu-id="6b0f0-109">たとえば、次のステートメントでは、and 演算子と or 演算子を使用して、3つの条件付きステートメントを接続しています。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-109">For example, the following statement uses the and operator and the or operator to connect three conditional statements.</span></span> <span data-ttu-id="6b0f0-110">$A の値が $b の値より大きく、$a または $b がより小さい場合にのみ、ステートメントが true になります。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-110">The statement is true only when the value of $a is greater than the value of $b, and either $a or $b is less than</span></span>
20.

```powershell
($a -gt $b) -and (($a -lt 20) -or ($b -lt 20))
```

<span data-ttu-id="6b0f0-111">PowerShell では、次の論理演算子がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-111">PowerShell supports the following logical operators.</span></span>

|<span data-ttu-id="6b0f0-112">演算子</span><span class="sxs-lookup"><span data-stu-id="6b0f0-112">Operator</span></span>|<span data-ttu-id="6b0f0-113">説明</span><span class="sxs-lookup"><span data-stu-id="6b0f0-113">Description</span></span>                        |<span data-ttu-id="6b0f0-114">例</span><span class="sxs-lookup"><span data-stu-id="6b0f0-114">Example</span></span>                   |
|--------|-----------------------------------|--------------------------|
|`-and`  |<span data-ttu-id="6b0f0-115">論理 AND。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-115">Logical AND.</span></span> <span data-ttu-id="6b0f0-116">両方の場合に TRUE</span><span class="sxs-lookup"><span data-stu-id="6b0f0-116">TRUE when both</span></span>        |`(1 -eq 1) -and (1 -eq 2)`|
|        |<span data-ttu-id="6b0f0-117">ステートメントは TRUE です。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-117">statements are TRUE.</span></span>               |`False`                   |
|`-or`   |<span data-ttu-id="6b0f0-118">論理 OR。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-118">Logical OR.</span></span> <span data-ttu-id="6b0f0-119">どちらかの場合は TRUE</span><span class="sxs-lookup"><span data-stu-id="6b0f0-119">TRUE when either</span></span>       |`(1 -eq 1) -or (1 -eq 2)` |
|        |<span data-ttu-id="6b0f0-120">ステートメントが TRUE です。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-120">statement is TRUE.</span></span>                 |`True`                    |
|`-xor`  |<span data-ttu-id="6b0f0-121">論理排他的 OR。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-121">Logical EXCLUSIVE OR.</span></span> <span data-ttu-id="6b0f0-122">TRUE の場合</span><span class="sxs-lookup"><span data-stu-id="6b0f0-122">TRUE when</span></span>    |`(1 -eq 1) -xor (2 -eq 2)`|
|        |<span data-ttu-id="6b0f0-123">1つのステートメントのみ TRUE</span><span class="sxs-lookup"><span data-stu-id="6b0f0-123">only one statement is TRUE</span></span>         |`False`                   |
|`-not`  |<span data-ttu-id="6b0f0-124">論理 not。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-124">Logical not.</span></span> <span data-ttu-id="6b0f0-125">ステートメントを否定します。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-125">Negates the statement</span></span> |`-not (1 -eq 1)`          |
|        |<span data-ttu-id="6b0f0-126">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-126">that follows.</span></span>                      |`False`                   |
|`!`     |<span data-ttu-id="6b0f0-127">`-not` と同じ</span><span class="sxs-lookup"><span data-stu-id="6b0f0-127">Same as `-not`</span></span>                     |`!(1 -eq 1)`              |
|        |                                   |`False`                   |

 <span data-ttu-id="6b0f0-128">注:</span><span class="sxs-lookup"><span data-stu-id="6b0f0-128">Note:</span></span>

<span data-ttu-id="6b0f0-129">前の例でも、等値比較演算子が使用されて `-eq` います。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-129">The previous examples also use the equal to comparison operator `-eq`.</span></span> <span data-ttu-id="6b0f0-130">詳細については、「 [about_Comparison_Operators](about_Comparison_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-130">For more information, see [about_Comparison_Operators](about_Comparison_Operators.md).</span></span> <span data-ttu-id="6b0f0-131">この例では、整数のブール値も使用します。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-131">The examples also use the Boolean values of integers.</span></span> <span data-ttu-id="6b0f0-132">整数0の値は FALSE です。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-132">The integer 0 has a value of FALSE.</span></span> <span data-ttu-id="6b0f0-133">その他のすべての整数の値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-133">All other integers have a value of TRUE.</span></span>

<span data-ttu-id="6b0f0-134">論理演算子の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-134">The syntax of the logical operators is as follows:</span></span>

```
<statement> {-AND | -OR | -XOR} <statement>
{! | -NOT} <statement>
```

<span data-ttu-id="6b0f0-135">論理演算子を使用するステートメントは、ブール値 (TRUE または FALSE) を返します。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-135">Statements that use the logical operators return Boolean (TRUE or FALSE) values.</span></span>

<span data-ttu-id="6b0f0-136">PowerShell 論理演算子は、ステートメントの実際の値を決定するために必要なステートメントのみを評価します。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-136">The PowerShell logical operators evaluate only the statements required to determine the truth value of the statement.</span></span> <span data-ttu-id="6b0f0-137">And 演算子を含むステートメントの左オペランドが FALSE の場合、右オペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-137">If the left operand in a statement that contains the and operator is FALSE, the right operand is not evaluated.</span></span>
<span data-ttu-id="6b0f0-138">ステートメントまたはステートメントが含まれているステートメントの左オペランドが TRUE の場合、右オペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-138">If the left operand in a statement that contains the or statement is TRUE, the right operand is not evaluated.</span></span> <span data-ttu-id="6b0f0-139">このため、ステートメントを使用する場合と同じ方法でこれらのステートメントを使用でき `If` ます。</span><span class="sxs-lookup"><span data-stu-id="6b0f0-139">As a result, you can use these statements in the same way that you would use the `If` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b0f0-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b0f0-140">SEE ALSO</span></span>

[<span data-ttu-id="6b0f0-141">about_Operators</span><span class="sxs-lookup"><span data-stu-id="6b0f0-141">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="6b0f0-142">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="6b0f0-142">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)

[<span data-ttu-id="6b0f0-143">about_Comparison_operators</span><span class="sxs-lookup"><span data-stu-id="6b0f0-143">about_Comparison_operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="6b0f0-144">about_If</span><span class="sxs-lookup"><span data-stu-id="6b0f0-144">about_If</span></span>](about_If.md)
