---
description: PowerShell で算術演算を実行する演算子について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 10/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arithmetic_operators?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Arithmetic_Operators
ms.openlocfilehash: 3ece7464198ff52fe6c22ccc54ceede84288bd7b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220952"
---
# <a name="about-arithmetic-operators"></a><span data-ttu-id="1b24f-104">算術演算子について</span><span class="sxs-lookup"><span data-stu-id="1b24f-104">About Arithmetic Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="1b24f-105">概要</span><span class="sxs-lookup"><span data-stu-id="1b24f-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="1b24f-106">PowerShell で算術演算を実行する演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-106">Describes the operators that perform arithmetic in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="1b24f-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="1b24f-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="1b24f-108">算術演算子は数値を計算します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-108">Arithmetic operators calculate numeric values.</span></span> <span data-ttu-id="1b24f-109">1つまたは複数の算術演算子を使用して、値の加算、減算、乗算、除算を行ったり、除算演算の剰余 (剰余) を計算したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-109">You can use one or more arithmetic operators to add, subtract, multiply, and divide values, and to calculate the remainder (modulus) of a division operation.</span></span>

<span data-ttu-id="1b24f-110">さらに、加算演算子 ( `+` ) と乗算演算子 () は、 `*` 文字列、配列、およびハッシュテーブルにも作用します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-110">In addition, the addition operator (`+`) and multiplication operator (`*`) also operate on strings, arrays, and hash tables.</span></span> <span data-ttu-id="1b24f-111">加算演算子は、入力を連結します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-111">The addition operator concatenates the input.</span></span> <span data-ttu-id="1b24f-112">乗算演算子は、入力の複数のコピーを返します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-112">The multiplication operator returns multiple copies of the input.</span></span> <span data-ttu-id="1b24f-113">算術ステートメントでは、オブジェクトの種類を混在させることもできます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-113">You can even mix object types in an arithmetic statement.</span></span> <span data-ttu-id="1b24f-114">ステートメントの評価に使用されるメソッドは、式の中で最も左にあるオブジェクトの型によって決まります。</span><span class="sxs-lookup"><span data-stu-id="1b24f-114">The method that is used to evaluate the statement is determined by the type of the leftmost object in the expression.</span></span>

<span data-ttu-id="1b24f-115">PowerShell 2.0 以降では、すべての算術演算子が64ビットの数値に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-115">Beginning in PowerShell 2.0, all arithmetic operators work on 64-bit numbers.</span></span>

<span data-ttu-id="1b24f-116">PowerShell 3.0 以降では、 `-shr` `-shl` powershell でビットごとの算術演算をサポートするために、(shift + right) と (shift + ←) が追加されます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-116">Beginning in PowerShell 3.0, the `-shr` (shift-right) and `-shl` (shift-left) are added to support bitwise arithmetic in PowerShell.</span></span>

<span data-ttu-id="1b24f-117">PowerShell では、次の算術演算子がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1b24f-117">PowerShell supports the following arithmetic operators:</span></span>

|<span data-ttu-id="1b24f-118">演算子</span><span class="sxs-lookup"><span data-stu-id="1b24f-118">Operator</span></span>|<span data-ttu-id="1b24f-119">説明</span><span class="sxs-lookup"><span data-stu-id="1b24f-119">Description</span></span>                       |<span data-ttu-id="1b24f-120">例</span><span class="sxs-lookup"><span data-stu-id="1b24f-120">Example</span></span>                      |
|--------|----------------------------------|-----------------------------|
| +      |<span data-ttu-id="1b24f-121">整数を加算します。を連結し</span><span class="sxs-lookup"><span data-stu-id="1b24f-121">Adds integers; concatenates</span></span>       |`6 + 2`                      |
|        |<span data-ttu-id="1b24f-122">文字列、配列、およびハッシュテーブル。</span><span class="sxs-lookup"><span data-stu-id="1b24f-122">strings, arrays, and hash tables.</span></span> |`"file" + "name"`            |
|        |                                  |`@(1, "one") + @(2.0, "two")`|
|        |                                  |`@{"one" = 1} + @{"two" = 2}`|
| -      |<span data-ttu-id="1b24f-123">ある値を別の値から減算する</span><span class="sxs-lookup"><span data-stu-id="1b24f-123">Subtracts one value from another</span></span>  |`6 - 2`                      |
|        |<span data-ttu-id="1b24f-124">value</span><span class="sxs-lookup"><span data-stu-id="1b24f-124">value</span></span>                             |                             |
| -      |<span data-ttu-id="1b24f-125">数値を負の数にします</span><span class="sxs-lookup"><span data-stu-id="1b24f-125">Makes a number a negative number</span></span>  |`-6`                         |
|        |                                  |`(Get-Date).AddDays(-1)`     |
| *      |<span data-ttu-id="1b24f-126">数値の乗算または文字列のコピー</span><span class="sxs-lookup"><span data-stu-id="1b24f-126">Multiply numbers or copy strings</span></span>  |`6 * 2`                      |
|        |<span data-ttu-id="1b24f-127">指定した数の配列と配列</span><span class="sxs-lookup"><span data-stu-id="1b24f-127">and arrays the specified number</span></span>   |`@("!") * 4`                 |
|        |<span data-ttu-id="1b24f-128">回です。</span><span class="sxs-lookup"><span data-stu-id="1b24f-128">of times.</span></span>                         |`"!" * 3`                    |
| /      |<span data-ttu-id="1b24f-129">2 つの値を除算します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-129">Divides two values.</span></span>               |`6 / 2`                      |
| %      |<span data-ttu-id="1b24f-130">剰余-の剰余を返します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-130">Modulus - returns the remainder of</span></span>|`7 % 2`                      |
|        |<span data-ttu-id="1b24f-131">除算演算。</span><span class="sxs-lookup"><span data-stu-id="1b24f-131">a division operation.</span></span>             |                             |
|<span data-ttu-id="1b24f-132">-帯域</span><span class="sxs-lookup"><span data-stu-id="1b24f-132">-band</span></span>   |<span data-ttu-id="1b24f-133">ビット演算子 AND</span><span class="sxs-lookup"><span data-stu-id="1b24f-133">Bitwise AND</span></span>                       |`5 -band 3`                  |
|<span data-ttu-id="1b24f-134">-bnot</span><span class="sxs-lookup"><span data-stu-id="1b24f-134">-bnot</span></span>   |<span data-ttu-id="1b24f-135">ビットごとの NOT</span><span class="sxs-lookup"><span data-stu-id="1b24f-135">Bitwise NOT</span></span>                       |`-bnot 5`                    |
|<span data-ttu-id="1b24f-136">-bor</span><span class="sxs-lookup"><span data-stu-id="1b24f-136">-bor</span></span>    |<span data-ttu-id="1b24f-137">ビットごとの OR</span><span class="sxs-lookup"><span data-stu-id="1b24f-137">Bitwise OR</span></span>                        |`5 -bor 0x03`                |
|<span data-ttu-id="1b24f-138">-bxor</span><span class="sxs-lookup"><span data-stu-id="1b24f-138">-bxor</span></span>   |<span data-ttu-id="1b24f-139">ビットごとの XOR</span><span class="sxs-lookup"><span data-stu-id="1b24f-139">Bitwise XOR</span></span>                       |`5 -bxor 3`                  |
|<span data-ttu-id="1b24f-140">-shl</span><span class="sxs-lookup"><span data-stu-id="1b24f-140">-shl</span></span>    |<span data-ttu-id="1b24f-141">ビットを左にシフトする</span><span class="sxs-lookup"><span data-stu-id="1b24f-141">Shifts bits to the left</span></span>           |`102 -shl 2`                 |
|<span data-ttu-id="1b24f-142">-shr</span><span class="sxs-lookup"><span data-stu-id="1b24f-142">-shr</span></span>    |<span data-ttu-id="1b24f-143">ビットを右にシフトする</span><span class="sxs-lookup"><span data-stu-id="1b24f-143">Shifts bits to the right</span></span>          |`102 -shr 2`                 |

<span data-ttu-id="1b24f-144">ビットごとの演算子は、整数型でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-144">The bitwise operators only work on integer types.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="1b24f-145">演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="1b24f-145">OPERATOR PRECEDENCE</span></span>

<span data-ttu-id="1b24f-146">PowerShell は、次の順序で算術演算子を処理します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-146">PowerShell processes arithmetic operators in the following order:</span></span>

|<span data-ttu-id="1b24f-147">優先順位</span><span class="sxs-lookup"><span data-stu-id="1b24f-147">Precedence</span></span>|<span data-ttu-id="1b24f-148">演算子</span><span class="sxs-lookup"><span data-stu-id="1b24f-148">Operator</span></span>          |<span data-ttu-id="1b24f-149">説明</span><span class="sxs-lookup"><span data-stu-id="1b24f-149">Description</span></span>                            |
|----------|------------------|---------------------------------------|
|<span data-ttu-id="1b24f-150">1</span><span class="sxs-lookup"><span data-stu-id="1b24f-150">1</span></span>         | `()`             |<span data-ttu-id="1b24f-151">かっこ</span><span class="sxs-lookup"><span data-stu-id="1b24f-151">Parentheses</span></span>                            |
|<span data-ttu-id="1b24f-152">2</span><span class="sxs-lookup"><span data-stu-id="1b24f-152">2</span></span>         | `-`              |<span data-ttu-id="1b24f-153">負の数または単項演算子の場合</span><span class="sxs-lookup"><span data-stu-id="1b24f-153">For a negative number or unary operator</span></span>|
|<span data-ttu-id="1b24f-154">3</span><span class="sxs-lookup"><span data-stu-id="1b24f-154">3</span></span>         | <span data-ttu-id="1b24f-155">`*`, `/`, `%`</span><span class="sxs-lookup"><span data-stu-id="1b24f-155">`*`, `/`, `%`</span></span>    |<span data-ttu-id="1b24f-156">乗算と除算の場合</span><span class="sxs-lookup"><span data-stu-id="1b24f-156">For multiplication and division</span></span>        |
|<span data-ttu-id="1b24f-157">4</span><span class="sxs-lookup"><span data-stu-id="1b24f-157">4</span></span>         | <span data-ttu-id="1b24f-158">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="1b24f-158">`+`, `-`</span></span>         |<span data-ttu-id="1b24f-159">加算と減算の場合</span><span class="sxs-lookup"><span data-stu-id="1b24f-159">For addition and subtraction</span></span>           |
|<span data-ttu-id="1b24f-160">5</span><span class="sxs-lookup"><span data-stu-id="1b24f-160">5</span></span>         | <span data-ttu-id="1b24f-161">`-band`, `-bnot`</span><span class="sxs-lookup"><span data-stu-id="1b24f-161">`-band`, `-bnot`</span></span> |<span data-ttu-id="1b24f-162">ビットごとの演算の場合</span><span class="sxs-lookup"><span data-stu-id="1b24f-162">For bitwise operations</span></span>                 |
|<span data-ttu-id="1b24f-163">5</span><span class="sxs-lookup"><span data-stu-id="1b24f-163">5</span></span>         | <span data-ttu-id="1b24f-164">`-bor`, `-bxor`</span><span class="sxs-lookup"><span data-stu-id="1b24f-164">`-bor`, `-bxor`</span></span>  |<span data-ttu-id="1b24f-165">ビットごとの演算の場合</span><span class="sxs-lookup"><span data-stu-id="1b24f-165">For bitwise operations</span></span>                 |
|<span data-ttu-id="1b24f-166">5</span><span class="sxs-lookup"><span data-stu-id="1b24f-166">5</span></span>         | <span data-ttu-id="1b24f-167">`-shr`, `-shl`</span><span class="sxs-lookup"><span data-stu-id="1b24f-167">`-shr`, `-shl`</span></span>   |<span data-ttu-id="1b24f-168">ビットごとの演算の場合</span><span class="sxs-lookup"><span data-stu-id="1b24f-168">For bitwise operations</span></span>                 |

<span data-ttu-id="1b24f-169">PowerShell は、優先順位の規則に従って、式を左から右に処理します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-169">PowerShell processes the expressions from left to right according to the precedence rules.</span></span> <span data-ttu-id="1b24f-170">次の例は、優先順位規則の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="1b24f-170">The following examples show the effect of the precedence rules:</span></span>

|<span data-ttu-id="1b24f-171">正規表現</span><span class="sxs-lookup"><span data-stu-id="1b24f-171">Expression</span></span> |<span data-ttu-id="1b24f-172">結果</span><span class="sxs-lookup"><span data-stu-id="1b24f-172">Result</span></span>|
|-----------|------|
|`3+6/3*4`  |`11`  |
|`3+6/(3*4)`|`3.5` |
|`(3+6)/3*4`|`12`  |

<span data-ttu-id="1b24f-173">PowerShell が式を評価する順序は、使用した他のプログラミング言語とスクリプト言語とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1b24f-173">The order in which PowerShell evaluates expressions might differ from other programming and scripting languages that you have used.</span></span> <span data-ttu-id="1b24f-174">次の例は、複雑な代入ステートメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="1b24f-174">The following example shows a complicated assignment statement.</span></span>

```powershell
$a = 0
$b = @(1,2)
$c = @(-1,-2)

$b[$a] = $c[$a++]
```

<span data-ttu-id="1b24f-175">この例では、式 `$a++` はの前に評価され `$b[$a]` ます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-175">In this example, the expression `$a++` is evaluated before `$b[$a]`.</span></span>
<span data-ttu-id="1b24f-176">を評価すると、 `$a++` ステートメントで使用された後のの値が変更され `$a` `$c[$a++]` ます。ただし、では、が使用され `$b[$a]` ます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-176">Evaluating `$a++` changes the value of `$a` after it is used in the statement `$c[$a++]`; but, before it is used in `$b[$a]`.</span></span> <span data-ttu-id="1b24f-177">の変数はではなくになります。したがって、ステートメントでは、では `$a` `$b[$a]` `1` `0` なく、に値が割り当てられ `$b[1]` `$b[0]` ます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-177">The variable `$a` in `$b[$a]` equals `1`, not `0`; so, the statement assigns a value to `$b[1]`, not `$b[0]`.</span></span>

<span data-ttu-id="1b24f-178">上記のコードは、次のコードに相当します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-178">The above code is equivalent to:</span></span>

```powershell
$a = 0
$b = @(1,2)
$c = @(-1,-2)

$tmp = $c[$a]
$a = $a + 1
$b[$a] = $tmp
```

## <a name="division-and-rounding"></a><span data-ttu-id="1b24f-179">除算と丸め</span><span class="sxs-lookup"><span data-stu-id="1b24f-179">DIVISION AND ROUNDING</span></span>

<span data-ttu-id="1b24f-180">除算演算の商が整数である場合、PowerShell は値を最も近い整数に丸めます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-180">When the quotient of a division operation is an integer, PowerShell rounds the value to the nearest integer.</span></span> <span data-ttu-id="1b24f-181">値がの場合は `.5` 、最も近い偶数の整数に丸められます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-181">When the value is `.5`, it rounds to the nearest even integer.</span></span>

<span data-ttu-id="1b24f-182">次の例は、最も近い偶数の整数に丸めた場合の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="1b24f-182">The following example shows the effect of rounding to the nearest even integer.</span></span>

|<span data-ttu-id="1b24f-183">正規表現</span><span class="sxs-lookup"><span data-stu-id="1b24f-183">Expression</span></span>      |<span data-ttu-id="1b24f-184">結果</span><span class="sxs-lookup"><span data-stu-id="1b24f-184">Result</span></span>|
|----------------|------|
|`[int]( 5 / 2 )`|`2`   |
|`[int]( 7 / 2 )`|`4`   |

<span data-ttu-id="1b24f-185">**_5/2_ = 2.5** が **2** に丸められていることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="1b24f-185">Notice how **_5/2_ = 2.5** gets rounded to **2**.</span></span> <span data-ttu-id="1b24f-186">しかし、 **_7/2_ = 3.5** は **4** に丸められます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-186">But, **_7/2_ = 3.5** gets rounded to **4**.</span></span>

<span data-ttu-id="1b24f-187">クラスを使用すると、 `[Math]` 異なる丸め動作を取得できます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-187">You can use the `[Math]` class to get different rounding behavior.</span></span>

|                          <span data-ttu-id="1b24f-188">正規表現</span><span class="sxs-lookup"><span data-stu-id="1b24f-188">Expression</span></span>                          | <span data-ttu-id="1b24f-189">結果</span><span class="sxs-lookup"><span data-stu-id="1b24f-189">Result</span></span> |
| ------------------------------------------------------------ | ------ |
| `[int][Math]::Round(5 / 2,[MidpointRounding]::AwayFromZero)` | `3`    |
| `[int][Math]::Ceiling(5 / 2)`                                | `3`    |
| `[int][Math]::Floor(5 / 2)`                                  | `2`    |

<span data-ttu-id="1b24f-190">詳細については、「 [Math. Round](/dotnet/api/system.math.round) メソッド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b24f-190">For more information, see the [Math.Round](/dotnet/api/system.math.round) method.</span></span>

## <a name="adding-and-multiplying-non-numeric-types"></a><span data-ttu-id="1b24f-191">数値以外の型の加算と乗算</span><span class="sxs-lookup"><span data-stu-id="1b24f-191">ADDING AND MULTIPLYING NON-NUMERIC TYPES</span></span>

<span data-ttu-id="1b24f-192">数値、文字列、配列、およびハッシュテーブルを追加できます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-192">You can add numbers, strings, arrays, and hash tables.</span></span> <span data-ttu-id="1b24f-193">また、数値、文字列、および配列を乗算することもできます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-193">And, you can multiply numbers, strings, and arrays.</span></span> <span data-ttu-id="1b24f-194">ただし、ハッシュテーブルを乗算することはできません。</span><span class="sxs-lookup"><span data-stu-id="1b24f-194">However, you cannot multiply hash tables.</span></span>

<span data-ttu-id="1b24f-195">文字列、配列、またはハッシュテーブルを追加すると、要素が連結されます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-195">When you add strings, arrays, or hash tables, the elements are concatenated.</span></span> <span data-ttu-id="1b24f-196">配列、ハッシュテーブルなどのコレクションを連結すると、両方のコレクションのオブジェクトを含む新しいオブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-196">When you concatenate collections, such as arrays or hash tables, a new object is created that contains the objects from both collections.</span></span> <span data-ttu-id="1b24f-197">同じキーを持つハッシュテーブルを連結しようとすると、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-197">If you try to concatenate hash tables that have the same key, the operation fails.</span></span>

<span data-ttu-id="1b24f-198">たとえば、次のコマンドでは、2つの配列を作成して追加します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-198">For example, the following commands create two arrays and then add them:</span></span>

```powershell
$a = 1,2,3
$b = "A","B","C"
$a + $b
```

```output
1
2
3
A
B
C
```

<span data-ttu-id="1b24f-199">また、さまざまな型のオブジェクトに対して算術演算を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-199">You can also perform arithmetic operations on objects of different types.</span></span>
<span data-ttu-id="1b24f-200">PowerShell が実行する操作は、操作の左端のオブジェクトの Microsoft .NET Framework 型によって決まります。</span><span class="sxs-lookup"><span data-stu-id="1b24f-200">The operation that PowerShell performs is determined by the Microsoft .NET Framework type of the leftmost object in the operation.</span></span> <span data-ttu-id="1b24f-201">PowerShell は、操作内のすべてのオブジェクトを、最初のオブジェクトの .NET Framework 型に変換しようとします。</span><span class="sxs-lookup"><span data-stu-id="1b24f-201">PowerShell tries to convert all the objects in the operation to the .NET Framework type of the first object.</span></span> <span data-ttu-id="1b24f-202">オブジェクトの変換に成功した場合は、最初のオブジェクトの .NET Framework 型に適した操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-202">If it succeeds in converting the objects, it performs the operation appropriate to the .NET Framework type of the first object.</span></span> <span data-ttu-id="1b24f-203">オブジェクトの変換に失敗した場合、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-203">If it fails to convert any of the objects, the operation fails.</span></span>

<span data-ttu-id="1b24f-204">加算演算子と乗算演算子の使用例を次に示します。異なる種類のオブジェクトを含む操作。</span><span class="sxs-lookup"><span data-stu-id="1b24f-204">The following examples demonstrate the use of the addition and multiplication operators; in operations that include different object types.</span></span> <span data-ttu-id="1b24f-205">次の場合を想定し `$array = 1,2,3` ます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-205">Assume `$array = 1,2,3`:</span></span>

|<span data-ttu-id="1b24f-206">正規表現</span><span class="sxs-lookup"><span data-stu-id="1b24f-206">Expression</span></span>       |<span data-ttu-id="1b24f-207">結果</span><span class="sxs-lookup"><span data-stu-id="1b24f-207">Result</span></span>                 |
|-----------------|-----------------------|
|`"file" + 16`    |`file16`               |
|`$array + 16`    |<span data-ttu-id="1b24f-208">`1`,`2`,`3`,`16`</span><span class="sxs-lookup"><span data-stu-id="1b24f-208">`1`,`2`,`3`,`16`</span></span>       |
|`$array + "file"`|<span data-ttu-id="1b24f-209">`1`,`2`,`3`,`file`</span><span class="sxs-lookup"><span data-stu-id="1b24f-209">`1`,`2`,`3`,`file`</span></span>     |
|`$array * 2`     |<span data-ttu-id="1b24f-210">`1`,`2`,`3`,`1`,`2`,`3`</span><span class="sxs-lookup"><span data-stu-id="1b24f-210">`1`,`2`,`3`,`1`,`2`,`3`</span></span>|
|`"file" * 3`     |`filefilefile`         |

<span data-ttu-id="1b24f-211">ステートメントの評価に使用されるメソッドは左端のオブジェクトによって決定されるため、PowerShell での加算と乗算は厳密には可換ではありません。</span><span class="sxs-lookup"><span data-stu-id="1b24f-211">Because the method that is used to evaluate statements is determined by the leftmost object, addition and multiplication in PowerShell are not strictly commutative.</span></span> <span data-ttu-id="1b24f-212">たとえば、は常にと等しいとは限りません。また、は常にと同じではありませ `(a + b)` `(b + a)` `(ab)` ん `(ba)` 。</span><span class="sxs-lookup"><span data-stu-id="1b24f-212">For example, `(a + b)` does not always equal `(b + a)`, and `(ab)` does not always equal `(ba)`.</span></span>

<span data-ttu-id="1b24f-213">次の例は、この原則を示しています。</span><span class="sxs-lookup"><span data-stu-id="1b24f-213">The following examples demonstrate this principle:</span></span>

|<span data-ttu-id="1b24f-214">正規表現</span><span class="sxs-lookup"><span data-stu-id="1b24f-214">Expression</span></span>   |<span data-ttu-id="1b24f-215">結果</span><span class="sxs-lookup"><span data-stu-id="1b24f-215">Result</span></span>                                               |
|-------------|-----------------------------------------------------|
|`"file" + 16`|`file16`                                             |
|`16 + "file"`|`Cannot convert value "file" to type "System.Int32".`|
|             |`Error: "Input string was not in a correct format."` |
|             |`At line:1 char:1`                                   |
|             |<span data-ttu-id="1b24f-216">+ 16 + "ファイル"</span><span class="sxs-lookup"><span data-stu-id="1b24f-216">+ 16 + "file"\`</span></span>                                       |

<span data-ttu-id="1b24f-217">ハッシュテーブルのケースは少し異なります。</span><span class="sxs-lookup"><span data-stu-id="1b24f-217">Hash tables are a slightly different case.</span></span> <span data-ttu-id="1b24f-218">ハッシュテーブルを別のハッシュテーブルに追加することができます。ただし、追加されたハッシュテーブルに重複するキーはありません。</span><span class="sxs-lookup"><span data-stu-id="1b24f-218">You can add hash tables to another hash table, as long as, the added hash tables don't have duplicate keys.</span></span>

<span data-ttu-id="1b24f-219">次の例では、ハッシュテーブルを相互に追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-219">The following example show how to add hash tables to each other.</span></span>

```powershell
$hash1 = @{a=1; b=2; c=3}
$hash2 = @{c1="Server01"; c2="Server02"}
$hash1 + $hash2
```

```output
Name                           Value
----                           -----
c2                             Server02
a                              1
b                              2
c1                             Server01
c                              3
```

<span data-ttu-id="1b24f-220">次の例では、いずれかのキーが両方のハッシュテーブルで重複しているため、エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-220">The following example throws an error because one of the keys is duplicated in both hash tables.</span></span>

```powershell
$hash1 = @{a=1; b=2; c=3}
$hash2 = @{c1="Server01"; c="Server02"}
$hash1 + $hash2
```

```output
Item has already been added. Key in dictionary: 'c'  Key being added: 'c'
At line:3 char:1
+ $hash1 + $hash2
+ ~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (:) [], ArgumentException
    + FullyQualifiedErrorId : System.ArgumentException
```

<span data-ttu-id="1b24f-221">また、ハッシュテーブルを配列に追加することもできます。また、ハッシュテーブル全体が配列内の項目になります。</span><span class="sxs-lookup"><span data-stu-id="1b24f-221">Also, you can add a hash table to an array; and, the entire hash table becomes an item in the array.</span></span>

```powershell
$array1 = @(0, "Hello World", [datetime]::Now)
$hash1 = @{a=1; b=2}
$array2 = $array1 + $hash1
$array2
```

```output
0
Hello World

Monday, June 12, 2017 3:05:46 PM

Key   : a
Value : 1
Name  : a

Key   : b
Value : 2
Name  : b
```

<span data-ttu-id="1b24f-222">ただし、他の型をハッシュテーブルに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="1b24f-222">However, you cannot add any other type to a hash table.</span></span>

```powershell
$hash1 + 2
```

```output
A hash table can only be added to another hash table.
At line:3 char:1
+ $hash1 + 2
```

<span data-ttu-id="1b24f-223">加算演算子は非常に便利ですが、代入演算子を使用して、ハッシュテーブルとハッシュ配列に要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-223">Although the addition operators are very useful, use the assignment operators to add elements to hash tables and arrays.</span></span> <span data-ttu-id="1b24f-224">詳細については、「 [about_assignment_operators](about_Assignment_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b24f-224">For more information see [about_assignment_operators](about_Assignment_Operators.md).</span></span> <span data-ttu-id="1b24f-225">次の例では、代入演算子を使用して、 `+=` 配列に項目を追加しています。</span><span class="sxs-lookup"><span data-stu-id="1b24f-225">The following examples use the `+=` assignment operator to add items to an array:</span></span>

```powershell
$array = @()
(0..9).foreach{ $array += $_ }
$array
```

```output
0
1
2
```

## <a name="type-conversion-to-accommodate-result"></a><span data-ttu-id="1b24f-226">結果に対応する型変換</span><span class="sxs-lookup"><span data-stu-id="1b24f-226">TYPE CONVERSION TO ACCOMMODATE RESULT</span></span>

<span data-ttu-id="1b24f-227">PowerShell では、有効桁数を失うことなく、結果を最もよく表現する .NET Framework の数値型が自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-227">PowerShell automatically selects the .NET Framework numeric type that best expresses the result without losing precision.</span></span> <span data-ttu-id="1b24f-228">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-228">For example:</span></span>

```powershell
2 + 3.1

(2). GetType().FullName
(2 + 3.1).GetType().FullName
```

```output
5.1
System.Int32
System.Double
```

<span data-ttu-id="1b24f-229">演算の結果が型に対して大きすぎる場合は、次の例のように、結果を格納できるように結果の型が拡張されます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-229">If the result of an operation is too large for the type, the type of the result is widened to accommodate the result, as in the following example:</span></span>

```powershell
(512MB).GetType().FullName
(512MB * 512MB).GetType().FullName
```

```output
System.Int32
System.Double
```

<span data-ttu-id="1b24f-230">結果の型は、必ずしもオペランドの1つと同じであるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="1b24f-230">The type of the result will not necessarily be the same as one of the operands.</span></span> <span data-ttu-id="1b24f-231">次の例では、負の値を符号なし整数にキャストすることはできません。また、符号なし整数が大きすぎてにキャストできません `Int32` 。</span><span class="sxs-lookup"><span data-stu-id="1b24f-231">In the following example, the negative value cannot be cast to an unsigned integer, and the unsigned integer is too large to be cast to `Int32`:</span></span>

```powershell
([int32]::minvalue + [uint32]::maxvalue).gettype().fullname
```

```output
System.Int64
```

<span data-ttu-id="1b24f-232">この例では、は `Int64` 両方の型に対応できます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-232">In this example, `Int64` can accommodate both types.</span></span>

<span data-ttu-id="1b24f-233">この `System.Decimal` 型は例外です。</span><span class="sxs-lookup"><span data-stu-id="1b24f-233">The `System.Decimal` type is an exception.</span></span> <span data-ttu-id="1b24f-234">いずれかのオペランドが10進数型の場合、結果は10進数型になります。</span><span class="sxs-lookup"><span data-stu-id="1b24f-234">If either operand has the Decimal type, the result will be of the Decimal type.</span></span> <span data-ttu-id="1b24f-235">結果が Decimal 型に対して大きすぎる場合、Double にキャストされません。</span><span class="sxs-lookup"><span data-stu-id="1b24f-235">If the result is too large for the Decimal type, it will not be cast to Double.</span></span> <span data-ttu-id="1b24f-236">代わりに、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-236">Instead, an error results.</span></span>

|<span data-ttu-id="1b24f-237">正規表現</span><span class="sxs-lookup"><span data-stu-id="1b24f-237">Expression</span></span>               |<span data-ttu-id="1b24f-238">結果</span><span class="sxs-lookup"><span data-stu-id="1b24f-238">Result</span></span>                                         |
|-------------------------|-----------------------------------------------|
|`[Decimal]::maxvalue`    |`79228162514264337593543950335`                |
|`[Decimal]::maxvalue + 1`|`Value was either too large or too small for a`|
|                         |`Decimal.`                                     |

## <a name="arithmetic-operators-and-variables"></a><span data-ttu-id="1b24f-239">算術演算子と変数</span><span class="sxs-lookup"><span data-stu-id="1b24f-239">ARITHMETIC OPERATORS AND VARIABLES</span></span>

<span data-ttu-id="1b24f-240">変数と共に算術演算子を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-240">You can also use arithmetic operators with variables.</span></span> <span data-ttu-id="1b24f-241">演算子は、変数の値に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-241">The operators act on the values of the variables.</span></span> <span data-ttu-id="1b24f-242">次の例では、変数で算術演算子を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-242">The following examples demonstrate the use of arithmetic operators with variables:</span></span>

| <span data-ttu-id="1b24f-243">正規表現</span><span class="sxs-lookup"><span data-stu-id="1b24f-243">Expression</span></span>                                    |<span data-ttu-id="1b24f-244">結果</span><span class="sxs-lookup"><span data-stu-id="1b24f-244">Result</span></span>      |
|-----------------------------------------------|------------|
|`$intA = 6`<br/>`$intB = 4`<br/>`$intA + $intB`|`10`        |
|`$a = "Power"`<br/>`$b = "Shell"`<br/>`$a + $b`|`PowerShell`|

## <a name="arithmetic-operators-and-commands"></a><span data-ttu-id="1b24f-245">算術演算子とコマンド</span><span class="sxs-lookup"><span data-stu-id="1b24f-245">ARITHMETIC OPERATORS AND COMMANDS</span></span>

<span data-ttu-id="1b24f-246">通常、数値、文字列、および配列を含む式では、算術演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-246">Typically, you use the arithmetic operators in expressions with numbers, strings, and arrays.</span></span> <span data-ttu-id="1b24f-247">ただし、コマンドが返すオブジェクトと、それらのオブジェクトのプロパティを使用して、算術演算子を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-247">However, you can also use arithmetic operators with the objects that commands return and with the properties of those objects.</span></span>

<span data-ttu-id="1b24f-248">次の例は、PowerShell コマンドを使用して式で算術演算子を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1b24f-248">The following examples show how to use the arithmetic operators in expressions with PowerShell commands:</span></span>

```powershell
(get-date) + (new-timespan -day 1)
```

<span data-ttu-id="1b24f-249">かっこ演算子は、 `get-date` コマンドレットとコマンドレットの式の評価を、この順序で強制的に実行し `new-timespan -day 1` ます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-249">The parenthesis operator forces the evaluation of the `get-date` cmdlet and the evaluation of the `new-timespan -day 1` cmdlet expression, in that order.</span></span> <span data-ttu-id="1b24f-250">その後、両方の結果が演算子を使用して追加され `+` ます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-250">Both results are then added using the `+` operator.</span></span>

```powershell
Get-Process | Where-Object { ($_.ws * 2) -gt 50mb }
```

```output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
   1896      39    50968      30620   264 1,572.55   1104 explorer
  12802      78   188468      81032   753 3,676.39   5676 OUTLOOK
    660       9    36168      26956   143    12.20    988 PowerShell
    561      14     6592      28144   110 1,010.09    496 services
   3476      80    34664      26092   234 ...45.69    876 svchost
    967      30    58804      59496   416   930.97   2508 WINWORD
```

<span data-ttu-id="1b24f-251">上の式では、各プロセスの作業領域 () にを乗算し、結果を比較して、より `$_.ws` `2` `50mb` 大きいかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-251">In the above expression, each process working space (`$_.ws`) is multiplied by `2`; and, the result, compared against `50mb` to see if it is greater than that.</span></span>

## <a name="bitwise-operators"></a><span data-ttu-id="1b24f-252">ビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="1b24f-252">Bitwise Operators</span></span>

<span data-ttu-id="1b24f-253">PowerShell では、ビットごとの and ( `-bAnd` )、包括的および排他的のビットごとの or 演算子 ( `-bOr` and)、 `-bXor` およびビットごとの-not () を含む、標準のビットごとの演算子をサポートしてい `-bNot` ます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-253">PowerShell supports the standard bitwise operators, including bitwise-AND (`-bAnd`), the inclusive and exclusive bitwise-OR operators (`-bOr` and `-bXor`), and bitwise-NOT (`-bNot`).</span></span>

<span data-ttu-id="1b24f-254">PowerShell 2.0 以降では、すべてのビットごとの演算子は64ビット整数で動作します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-254">Beginning in PowerShell 2.0, all bitwise operators work with 64-bit integers.</span></span>

<span data-ttu-id="1b24f-255">PowerShell 3.0 以降では、 `-shr` `-shl` powershell でビットごとの算術演算をサポートするために、(shift + right) と (shift + ←) が導入されています。</span><span class="sxs-lookup"><span data-stu-id="1b24f-255">Beginning in PowerShell 3.0, the `-shr` (shift-right) and `-shl` (shift-left) are introduced to support bitwise arithmetic in PowerShell.</span></span>

<span data-ttu-id="1b24f-256">PowerShell では、次のビットごとの演算子がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1b24f-256">PowerShell supports the following bitwise operators.</span></span>

| <span data-ttu-id="1b24f-257">演算子</span><span class="sxs-lookup"><span data-stu-id="1b24f-257">Operator</span></span> | <span data-ttu-id="1b24f-258">説明</span><span class="sxs-lookup"><span data-stu-id="1b24f-258">Description</span></span>            | <span data-ttu-id="1b24f-259">式</span><span class="sxs-lookup"><span data-stu-id="1b24f-259">Expression</span></span>   | <span data-ttu-id="1b24f-260">結果</span><span class="sxs-lookup"><span data-stu-id="1b24f-260">Result</span></span> |
| -------- | ---------------------- | ------------ | ------ |
| `-band`  | <span data-ttu-id="1b24f-261">ビット演算子 AND</span><span class="sxs-lookup"><span data-stu-id="1b24f-261">Bitwise AND</span></span>            | `10 -band 3` | <span data-ttu-id="1b24f-262">2</span><span class="sxs-lookup"><span data-stu-id="1b24f-262">2</span></span>      |
| `-bor`   | <span data-ttu-id="1b24f-263">ビットごとの OR (を含む)</span><span class="sxs-lookup"><span data-stu-id="1b24f-263">Bitwise OR (inclusive)</span></span> | `10 -bor 3`  | <span data-ttu-id="1b24f-264">11</span><span class="sxs-lookup"><span data-stu-id="1b24f-264">11</span></span>     |
| `-bxor`  | <span data-ttu-id="1b24f-265">ビットごとの OR (排他的)</span><span class="sxs-lookup"><span data-stu-id="1b24f-265">Bitwise OR (exclusive)</span></span> | `10 -bxor 3` | <span data-ttu-id="1b24f-266">9</span><span class="sxs-lookup"><span data-stu-id="1b24f-266">9</span></span>      |
| `-bnot`  | <span data-ttu-id="1b24f-267">ビットごとの NOT</span><span class="sxs-lookup"><span data-stu-id="1b24f-267">Bitwise NOT</span></span>            | `-bNot 10`   | <span data-ttu-id="1b24f-268">-11</span><span class="sxs-lookup"><span data-stu-id="1b24f-268">-11</span></span>    |
| `-shl`   | <span data-ttu-id="1b24f-269">左シフト</span><span class="sxs-lookup"><span data-stu-id="1b24f-269">Shift-left</span></span>             | `102 -shl 2` | <span data-ttu-id="1b24f-270">408</span><span class="sxs-lookup"><span data-stu-id="1b24f-270">408</span></span>    |
| `-shr`   | <span data-ttu-id="1b24f-271">右シフト</span><span class="sxs-lookup"><span data-stu-id="1b24f-271">Shift-right</span></span>            | `102 -shr 1` | <span data-ttu-id="1b24f-272">51</span><span class="sxs-lookup"><span data-stu-id="1b24f-272">51</span></span>     |

<span data-ttu-id="1b24f-273">ビットごとの演算子は、値のバイナリ形式に対して動作します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-273">Bitwise operators act on the binary format of a value.</span></span> <span data-ttu-id="1b24f-274">たとえば、10進数のビット構造は00001010で (1 バイトに基づいて)、数値3のビット構造は00000011です。</span><span class="sxs-lookup"><span data-stu-id="1b24f-274">For example, the bit structure for the number 10 is 00001010 (based on 1 byte), and the bit structure for the number 3 is 00000011.</span></span> <span data-ttu-id="1b24f-275">ビットごとの演算子を使用して10を3と比較すると、各バイトの個々のビットが比較されます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-275">When you use a bitwise operator to compare 10 to 3, the individual bits in each byte are compared.</span></span>

<span data-ttu-id="1b24f-276">ビットごとの AND 演算では、両方の入力ビットが1の場合にのみ、結果として得られるビットが1に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-276">In a bitwise AND operation, the resulting bit is set to 1 only when both input bits are 1.</span></span>

```
1010      (10)
0011      ( 3)
--------------  bAND
0010      ( 2)
```

<span data-ttu-id="1b24f-277">ビットごとの OR (包括) 演算では、いずれかまたは両方の入力ビットが1の場合、結果のビットは1に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-277">In a bitwise OR (inclusive) operation, the resulting bit is set to 1 when either or both input bits are 1.</span></span> <span data-ttu-id="1b24f-278">両方の入力ビットが0に設定されている場合にのみ、結果のビットが0に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-278">The resulting bit is set to 0 only when both input bits are set to 0.</span></span>

```
1010      (10)
0011      ( 3)
--------------  bOR (inclusive)
1011      (11)
```

<span data-ttu-id="1b24f-279">ビットごとの OR (排他的) 演算では、1つの入力ビットが1の場合にのみ、結果として得られるビットが1に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-279">In a bitwise OR (exclusive) operation, the resulting bit is set to 1 only when one input bit is 1.</span></span>

```
1010      (10)
0011      ( 3)
--------------  bXOR (exclusive)
1001      ( 9)
```

<span data-ttu-id="1b24f-280">ビットごとの NOT 演算子は、値のバイナリ補数を生成する単項演算子です。</span><span class="sxs-lookup"><span data-stu-id="1b24f-280">The bitwise NOT operator is a unary operator that produces the binary complement of the value.</span></span> <span data-ttu-id="1b24f-281">ビット1を0に設定し、ビット0を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-281">A bit of 1 is set to 0 and a bit of 0 is set to 1.</span></span>

<span data-ttu-id="1b24f-282">たとえば、0のバイナリ補数は-1、最大符号なし整数 (0xffffffff)、および-1 のバイナリ補数は0です。</span><span class="sxs-lookup"><span data-stu-id="1b24f-282">For example, the binary complement of 0 is -1, the maximum unsigned integer (0xffffffff), and the binary complement of -1 is 0.</span></span>

```powershell
-bNot 10
```

```Output
-11
```

```
0000 0000 0000 1010  (10)
------------------------- bNOT
1111 1111 1111 0101  (-11, xfffffff5)
```

<span data-ttu-id="1b24f-283">ビットごとのシフト左演算では、すべてのビットが "n" の位置を左に移動します。 "n" は右のオペランドの値です。</span><span class="sxs-lookup"><span data-stu-id="1b24f-283">In a bitwise shift-left operation, all bits are moved "n" places to the left, where "n" is the value of the right operand.</span></span> <span data-ttu-id="1b24f-284">1つの場所にゼロが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-284">A zero is inserted in the ones place.</span></span>

<span data-ttu-id="1b24f-285">左オペランドが整数 (32 ビット) 値の場合、右オペランドの下位5ビットによって左オペランドのビット数が決定されます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-285">When the left operand is an Integer (32-bit) value, the lower 5 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

<span data-ttu-id="1b24f-286">左側のオペランドが Long (64 ビット) 値の場合、右オペランドの下位6ビットによって左オペランドのビット数が決定されます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-286">When the left operand is a Long (64-bit) value, the lower 6 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

|<span data-ttu-id="1b24f-287">正規表現</span><span class="sxs-lookup"><span data-stu-id="1b24f-287">Expression</span></span> |<span data-ttu-id="1b24f-288">結果</span><span class="sxs-lookup"><span data-stu-id="1b24f-288">Result</span></span>|<span data-ttu-id="1b24f-289">バイナリの結果</span><span class="sxs-lookup"><span data-stu-id="1b24f-289">Binary Result</span></span>|
|-----------|------|-------------|
|`21 -shl 0`|<span data-ttu-id="1b24f-290">21</span><span class="sxs-lookup"><span data-stu-id="1b24f-290">21</span></span>    |<span data-ttu-id="1b24f-291">0001 0101</span><span class="sxs-lookup"><span data-stu-id="1b24f-291">0001 0101</span></span>    |
|`21 -shl 1`|<span data-ttu-id="1b24f-292">42</span><span class="sxs-lookup"><span data-stu-id="1b24f-292">42</span></span>    |<span data-ttu-id="1b24f-293">0010 1010</span><span class="sxs-lookup"><span data-stu-id="1b24f-293">0010 1010</span></span>    |
|`21 -shl 2`|<span data-ttu-id="1b24f-294">84</span><span class="sxs-lookup"><span data-stu-id="1b24f-294">84</span></span>    |<span data-ttu-id="1b24f-295">0101 0100</span><span class="sxs-lookup"><span data-stu-id="1b24f-295">0101 0100</span></span>    |

<span data-ttu-id="1b24f-296">ビットごとのシフト右演算では、すべてのビットが右側のオペランドによって指定されている "n" を右に移動します。</span><span class="sxs-lookup"><span data-stu-id="1b24f-296">In a bitwise shift-right operation, all bits are moved "n" places to the right, where "n" is specified by the right operand.</span></span> <span data-ttu-id="1b24f-297">右に正または符号なしの値をシフトすると、シフト右の演算子 (-shr) によって左端にゼロが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-297">The shift-right operator (-shr) inserts a zero in the left-most place when shifting a positive or unsigned value to the right.</span></span>

<span data-ttu-id="1b24f-298">左オペランドが整数 (32 ビット) 値の場合、右オペランドの下位5ビットによって左オペランドのビット数が決定されます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-298">When the left operand is an Integer (32-bit) value, the lower 5 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

<span data-ttu-id="1b24f-299">左側のオペランドが Long (64 ビット) 値の場合、右オペランドの下位6ビットによって左オペランドのビット数が決定されます。</span><span class="sxs-lookup"><span data-stu-id="1b24f-299">When the left operand is a Long (64-bit) value, the lower 6 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

|<span data-ttu-id="1b24f-300">正規表現</span><span class="sxs-lookup"><span data-stu-id="1b24f-300">Expression</span></span>              |<span data-ttu-id="1b24f-301">結果</span><span class="sxs-lookup"><span data-stu-id="1b24f-301">Result</span></span>      |<span data-ttu-id="1b24f-302">Binary</span><span class="sxs-lookup"><span data-stu-id="1b24f-302">Binary</span></span>     |<span data-ttu-id="1b24f-303">Hex</span><span class="sxs-lookup"><span data-stu-id="1b24f-303">Hex</span></span>         |
|------------------------|------------|-----------|------------|
|`21 -shr 0`             | <span data-ttu-id="1b24f-304">21</span><span class="sxs-lookup"><span data-stu-id="1b24f-304">21</span></span>         | <span data-ttu-id="1b24f-305">0001 0101</span><span class="sxs-lookup"><span data-stu-id="1b24f-305">0001 0101</span></span> | <span data-ttu-id="1b24f-306">0x15</span><span class="sxs-lookup"><span data-stu-id="1b24f-306">0x15</span></span>       |
|`21 -shr 1`             | <span data-ttu-id="1b24f-307">10</span><span class="sxs-lookup"><span data-stu-id="1b24f-307">10</span></span>         | <span data-ttu-id="1b24f-308">0000 1010</span><span class="sxs-lookup"><span data-stu-id="1b24f-308">0000 1010</span></span> | <span data-ttu-id="1b24f-309">0x0A</span><span class="sxs-lookup"><span data-stu-id="1b24f-309">0x0A</span></span>       |
|`21 -shr 2`             | <span data-ttu-id="1b24f-310">5</span><span class="sxs-lookup"><span data-stu-id="1b24f-310">5</span></span>          | <span data-ttu-id="1b24f-311">0000 0101</span><span class="sxs-lookup"><span data-stu-id="1b24f-311">0000 0101</span></span> | <span data-ttu-id="1b24f-312">0x05</span><span class="sxs-lookup"><span data-stu-id="1b24f-312">0x05</span></span>       |
|`21 -shr 31`            | <span data-ttu-id="1b24f-313">0</span><span class="sxs-lookup"><span data-stu-id="1b24f-313">0</span></span>          | <span data-ttu-id="1b24f-314">0000 0000</span><span class="sxs-lookup"><span data-stu-id="1b24f-314">0000 0000</span></span> | <span data-ttu-id="1b24f-315">0x00</span><span class="sxs-lookup"><span data-stu-id="1b24f-315">0x00</span></span>       |
|`21 -shr 32`            | <span data-ttu-id="1b24f-316">21</span><span class="sxs-lookup"><span data-stu-id="1b24f-316">21</span></span>         | <span data-ttu-id="1b24f-317">0001 0101</span><span class="sxs-lookup"><span data-stu-id="1b24f-317">0001 0101</span></span> | <span data-ttu-id="1b24f-318">0x15</span><span class="sxs-lookup"><span data-stu-id="1b24f-318">0x15</span></span>       |
|`21 -shr 64`            | <span data-ttu-id="1b24f-319">21</span><span class="sxs-lookup"><span data-stu-id="1b24f-319">21</span></span>         | <span data-ttu-id="1b24f-320">0001 0101</span><span class="sxs-lookup"><span data-stu-id="1b24f-320">0001 0101</span></span> | <span data-ttu-id="1b24f-321">0x15</span><span class="sxs-lookup"><span data-stu-id="1b24f-321">0x15</span></span>       |
|`21 -shr 65`            | <span data-ttu-id="1b24f-322">10</span><span class="sxs-lookup"><span data-stu-id="1b24f-322">10</span></span>         | <span data-ttu-id="1b24f-323">0000 1010</span><span class="sxs-lookup"><span data-stu-id="1b24f-323">0000 1010</span></span> | <span data-ttu-id="1b24f-324">0x0A</span><span class="sxs-lookup"><span data-stu-id="1b24f-324">0x0A</span></span>       |
|`21 -shr 66`            | <span data-ttu-id="1b24f-325">5</span><span class="sxs-lookup"><span data-stu-id="1b24f-325">5</span></span>          | <span data-ttu-id="1b24f-326">0000 0101</span><span class="sxs-lookup"><span data-stu-id="1b24f-326">0000 0101</span></span> | <span data-ttu-id="1b24f-327">0x05</span><span class="sxs-lookup"><span data-stu-id="1b24f-327">0x05</span></span>       |
|`[int]::MaxValue -shr 1`| <span data-ttu-id="1b24f-328">1073741823</span><span class="sxs-lookup"><span data-stu-id="1b24f-328">1073741823</span></span> |           | <span data-ttu-id="1b24f-329">0x3FFFFFFF</span><span class="sxs-lookup"><span data-stu-id="1b24f-329">0x3FFFFFFF</span></span> |
|`[int]::MinValue -shr 1`| <span data-ttu-id="1b24f-330">-1073741824</span><span class="sxs-lookup"><span data-stu-id="1b24f-330">-1073741824</span></span>|           | <span data-ttu-id="1b24f-331">0xC0000000</span><span class="sxs-lookup"><span data-stu-id="1b24f-331">0xC0000000</span></span> |
|`-1 -shr 1`             | <span data-ttu-id="1b24f-332">-1</span><span class="sxs-lookup"><span data-stu-id="1b24f-332">-1</span></span>         |           | <span data-ttu-id="1b24f-333">~</span><span class="sxs-lookup"><span data-stu-id="1b24f-333">0xFFFFFFFF</span></span> |

## <a name="see-also"></a><span data-ttu-id="1b24f-334">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b24f-334">SEE ALSO</span></span>

- [<span data-ttu-id="1b24f-335">about_arrays</span><span class="sxs-lookup"><span data-stu-id="1b24f-335">about_arrays</span></span>](about_Arrays.md)
- [<span data-ttu-id="1b24f-336">about_assignment_operators</span><span class="sxs-lookup"><span data-stu-id="1b24f-336">about_assignment_operators</span></span>](about_Assignment_Operators.md)
- [<span data-ttu-id="1b24f-337">about_comparison_operators</span><span class="sxs-lookup"><span data-stu-id="1b24f-337">about_comparison_operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="1b24f-338">about_hash_tables</span><span class="sxs-lookup"><span data-stu-id="1b24f-338">about_hash_tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="1b24f-339">about_operators</span><span class="sxs-lookup"><span data-stu-id="1b24f-339">about_operators</span></span>](about_Operators.md)
- [<span data-ttu-id="1b24f-340">about_variables</span><span class="sxs-lookup"><span data-stu-id="1b24f-340">about_variables</span></span>](about_Variables.md)
- [<span data-ttu-id="1b24f-341">Get-Date</span><span class="sxs-lookup"><span data-stu-id="1b24f-341">Get-Date</span></span>](xref:Microsoft.PowerShell.Utility.Get-Date)
- [<span data-ttu-id="1b24f-342">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="1b24f-342">New-TimeSpan</span></span>](xref:Microsoft.PowerShell.Utility.New-TimeSpan)
