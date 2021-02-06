---
description: PowerShell のステートメントを接続する演算子について説明します。
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logical_operators?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logical_Operators
ms.openlocfilehash: 8602551f3ecf74027b59715e1f47aab1b10bea92
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605167"
---
# <a name="about_logical_operators"></a><span data-ttu-id="73a7b-103">about_Logical_Operators</span><span class="sxs-lookup"><span data-stu-id="73a7b-103">about_Logical_Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="73a7b-104">概要</span><span class="sxs-lookup"><span data-stu-id="73a7b-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="73a7b-105">PowerShell のステートメントを接続する演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="73a7b-105">Describes the operators that connect statements in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="73a7b-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="73a7b-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="73a7b-107">PowerShell 論理演算子は、式とステートメントを接続します。これにより、1つの式を使用して複数の条件をテストできます。</span><span class="sxs-lookup"><span data-stu-id="73a7b-107">The PowerShell logical operators connect expressions and statements, allowing you to use a single expression to test for multiple conditions.</span></span>

<span data-ttu-id="73a7b-108">たとえば、次のステートメントでは、and 演算子と or 演算子を使用して、3つの条件付きステートメントを接続しています。</span><span class="sxs-lookup"><span data-stu-id="73a7b-108">For example, the following statement uses the and operator and the or operator to connect three conditional statements.</span></span> <span data-ttu-id="73a7b-109">$A の値が $b の値より大きく、$a または $b がより小さい場合にのみ、ステートメントが true になります。</span><span class="sxs-lookup"><span data-stu-id="73a7b-109">The statement is true only when the value of $a is greater than the value of $b, and either $a or $b is less than</span></span>
20.

```powershell
($a -gt $b) -and (($a -lt 20) -or ($b -lt 20))
```

<span data-ttu-id="73a7b-110">PowerShell では、次の論理演算子がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="73a7b-110">PowerShell supports the following logical operators.</span></span>

|<span data-ttu-id="73a7b-111">演算子</span><span class="sxs-lookup"><span data-stu-id="73a7b-111">Operator</span></span>|<span data-ttu-id="73a7b-112">説明</span><span class="sxs-lookup"><span data-stu-id="73a7b-112">Description</span></span>                        |<span data-ttu-id="73a7b-113">例</span><span class="sxs-lookup"><span data-stu-id="73a7b-113">Example</span></span>                   |
|--------|-----------------------------------|--------------------------|
|`-and`  |<span data-ttu-id="73a7b-114">論理 AND。</span><span class="sxs-lookup"><span data-stu-id="73a7b-114">Logical AND.</span></span> <span data-ttu-id="73a7b-115">両方の場合に TRUE</span><span class="sxs-lookup"><span data-stu-id="73a7b-115">TRUE when both</span></span>        |`(1 -eq 1) -and (1 -eq 2)`|
|        |<span data-ttu-id="73a7b-116">ステートメントは TRUE です。</span><span class="sxs-lookup"><span data-stu-id="73a7b-116">statements are TRUE.</span></span>               |`False`                   |
|`-or`   |<span data-ttu-id="73a7b-117">論理 OR。</span><span class="sxs-lookup"><span data-stu-id="73a7b-117">Logical OR.</span></span> <span data-ttu-id="73a7b-118">どちらかの場合は TRUE</span><span class="sxs-lookup"><span data-stu-id="73a7b-118">TRUE when either</span></span>       |`(1 -eq 1) -or (1 -eq 2)` |
|        |<span data-ttu-id="73a7b-119">ステートメントが TRUE です。</span><span class="sxs-lookup"><span data-stu-id="73a7b-119">statement is TRUE.</span></span>                 |`True`                    |
|`-xor`  |<span data-ttu-id="73a7b-120">論理排他的 OR。</span><span class="sxs-lookup"><span data-stu-id="73a7b-120">Logical EXCLUSIVE OR.</span></span> <span data-ttu-id="73a7b-121">TRUE の場合</span><span class="sxs-lookup"><span data-stu-id="73a7b-121">TRUE when</span></span>    |`(1 -eq 1) -xor (2 -eq 2)`|
|        |<span data-ttu-id="73a7b-122">1つのステートメントのみ TRUE</span><span class="sxs-lookup"><span data-stu-id="73a7b-122">only one statement is TRUE</span></span>         |`False`                   |
|`-not`  |<span data-ttu-id="73a7b-123">論理 not。</span><span class="sxs-lookup"><span data-stu-id="73a7b-123">Logical not.</span></span> <span data-ttu-id="73a7b-124">ステートメントを否定します。</span><span class="sxs-lookup"><span data-stu-id="73a7b-124">Negates the statement</span></span> |`-not (1 -eq 1)`          |
|        |<span data-ttu-id="73a7b-125">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="73a7b-125">that follows.</span></span>                      |`False`                   |
|`!`     |<span data-ttu-id="73a7b-126">`-not` と同じ</span><span class="sxs-lookup"><span data-stu-id="73a7b-126">Same as `-not`</span></span>                     |`!(1 -eq 1)`              |
|        |                                   |`False`                   |

 <span data-ttu-id="73a7b-127">注:</span><span class="sxs-lookup"><span data-stu-id="73a7b-127">Note:</span></span>

<span data-ttu-id="73a7b-128">前の例でも、等値比較演算子が使用されて `-eq` います。</span><span class="sxs-lookup"><span data-stu-id="73a7b-128">The previous examples also use the equal to comparison operator `-eq`.</span></span> <span data-ttu-id="73a7b-129">詳細については、「 [about_Comparison_Operators](about_Comparison_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73a7b-129">For more information, see [about_Comparison_Operators](about_Comparison_Operators.md).</span></span> <span data-ttu-id="73a7b-130">この例では、整数のブール値も使用します。</span><span class="sxs-lookup"><span data-stu-id="73a7b-130">The examples also use the Boolean values of integers.</span></span> <span data-ttu-id="73a7b-131">整数0の値は FALSE です。</span><span class="sxs-lookup"><span data-stu-id="73a7b-131">The integer 0 has a value of FALSE.</span></span> <span data-ttu-id="73a7b-132">その他のすべての整数の値は TRUE です。</span><span class="sxs-lookup"><span data-stu-id="73a7b-132">All other integers have a value of TRUE.</span></span>

<span data-ttu-id="73a7b-133">論理演算子の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="73a7b-133">The syntax of the logical operators is as follows:</span></span>

```
<statement> {-AND | -OR | -XOR} <statement>
{! | -NOT} <statement>
```

<span data-ttu-id="73a7b-134">論理演算子を使用するステートメントは、ブール値 (TRUE または FALSE) を返します。</span><span class="sxs-lookup"><span data-stu-id="73a7b-134">Statements that use the logical operators return Boolean (TRUE or FALSE) values.</span></span>

<span data-ttu-id="73a7b-135">PowerShell 論理演算子は、ステートメントの実際の値を決定するために必要なステートメントのみを評価します。</span><span class="sxs-lookup"><span data-stu-id="73a7b-135">The PowerShell logical operators evaluate only the statements required to determine the truth value of the statement.</span></span> <span data-ttu-id="73a7b-136">And 演算子を含むステートメントの左オペランドが FALSE の場合、右オペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="73a7b-136">If the left operand in a statement that contains the and operator is FALSE, the right operand is not evaluated.</span></span>
<span data-ttu-id="73a7b-137">ステートメントまたはステートメントが含まれているステートメントの左オペランドが TRUE の場合、右オペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="73a7b-137">If the left operand in a statement that contains the or statement is TRUE, the right operand is not evaluated.</span></span> <span data-ttu-id="73a7b-138">このため、ステートメントを使用する場合と同じ方法でこれらのステートメントを使用でき `If` ます。</span><span class="sxs-lookup"><span data-stu-id="73a7b-138">As a result, you can use these statements in the same way that you would use the `If` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="73a7b-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="73a7b-139">SEE ALSO</span></span>

[<span data-ttu-id="73a7b-140">about_Operators</span><span class="sxs-lookup"><span data-stu-id="73a7b-140">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="73a7b-141">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="73a7b-141">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)

[<span data-ttu-id="73a7b-142">about_Comparison_operators</span><span class="sxs-lookup"><span data-stu-id="73a7b-142">about_Comparison_operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="73a7b-143">about_If</span><span class="sxs-lookup"><span data-stu-id="73a7b-143">about_If</span></span>](about_If.md)

