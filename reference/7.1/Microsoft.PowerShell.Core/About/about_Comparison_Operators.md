---
description: PowerShell の値を比較する演算子について説明します。
Locale: en-US
ms.date: 12/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: ea48d5928f71983f6d035f0e5e6074ce36754d80
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "97090513"
---
# <a name="about-comparison-operators"></a><span data-ttu-id="4fb86-103">比較演算子について</span><span class="sxs-lookup"><span data-stu-id="4fb86-103">About Comparison Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="4fb86-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="4fb86-104">Short description</span></span>
<span data-ttu-id="4fb86-105">PowerShell の値を比較する演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-105">Describes the operators that compare values in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="4fb86-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="4fb86-106">Long description</span></span>

<span data-ttu-id="4fb86-107">比較演算子を使用すると、値を比較し、指定したパターンに一致する値を検索するための条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-107">Comparison operators let you specify conditions for comparing values and finding values that match specified patterns.</span></span> <span data-ttu-id="4fb86-108">比較演算子を使用するには、比較する値を、これらの値を区切る演算子と組み合わせて指定します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-108">To use a comparison operator, specify the values that you want to compare together with an operator that separates these values.</span></span>

<span data-ttu-id="4fb86-109">PowerShell には、次の比較演算子が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4fb86-109">PowerShell includes the following comparison operators:</span></span>

| <span data-ttu-id="4fb86-110">Type</span><span class="sxs-lookup"><span data-stu-id="4fb86-110">Type</span></span>        | <span data-ttu-id="4fb86-111">演算子</span><span class="sxs-lookup"><span data-stu-id="4fb86-111">Operators</span></span>    | <span data-ttu-id="4fb86-112">説明</span><span class="sxs-lookup"><span data-stu-id="4fb86-112">Description</span></span>                                 |
| ----------- | ------------ | --------------------------------------------|
| <span data-ttu-id="4fb86-113">等式</span><span class="sxs-lookup"><span data-stu-id="4fb86-113">Equality</span></span>    | <span data-ttu-id="4fb86-114">-eq</span><span class="sxs-lookup"><span data-stu-id="4fb86-114">-eq</span></span>          | <span data-ttu-id="4fb86-115">equals</span><span class="sxs-lookup"><span data-stu-id="4fb86-115">equals</span></span>                                      |
|             | <span data-ttu-id="4fb86-116">-ne</span><span class="sxs-lookup"><span data-stu-id="4fb86-116">-ne</span></span>          | <span data-ttu-id="4fb86-117">等しくない</span><span class="sxs-lookup"><span data-stu-id="4fb86-117">not equals</span></span>                                  |
|             | <span data-ttu-id="4fb86-118">-gt</span><span class="sxs-lookup"><span data-stu-id="4fb86-118">-gt</span></span>          | <span data-ttu-id="4fb86-119">より大きい</span><span class="sxs-lookup"><span data-stu-id="4fb86-119">greater than</span></span>                                |
|             | <span data-ttu-id="4fb86-120">-ge</span><span class="sxs-lookup"><span data-stu-id="4fb86-120">-ge</span></span>          | <span data-ttu-id="4fb86-121">以上</span><span class="sxs-lookup"><span data-stu-id="4fb86-121">greater than or equal</span></span>                       |
|             | <span data-ttu-id="4fb86-122">-lt</span><span class="sxs-lookup"><span data-stu-id="4fb86-122">-lt</span></span>          | <span data-ttu-id="4fb86-123">次の値未満</span><span class="sxs-lookup"><span data-stu-id="4fb86-123">less than</span></span>                                   |
|             | <span data-ttu-id="4fb86-124">-le</span><span class="sxs-lookup"><span data-stu-id="4fb86-124">-le</span></span>          | <span data-ttu-id="4fb86-125">以下</span><span class="sxs-lookup"><span data-stu-id="4fb86-125">less than or equal</span></span>                          |
|             |              |                                             |
| <span data-ttu-id="4fb86-126">Matching</span><span class="sxs-lookup"><span data-stu-id="4fb86-126">Matching</span></span>    | <span data-ttu-id="4fb86-127">-like</span><span class="sxs-lookup"><span data-stu-id="4fb86-127">-like</span></span>        | <span data-ttu-id="4fb86-128">文字列がワイルドカードに一致する場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="4fb86-128">Returns true when string matches wildcard</span></span>   |
|             |              | <span data-ttu-id="4fb86-129">pattern</span><span class="sxs-lookup"><span data-stu-id="4fb86-129">pattern</span></span>                                     |
|             | <span data-ttu-id="4fb86-130">-notlike</span><span class="sxs-lookup"><span data-stu-id="4fb86-130">-notlike</span></span>     | <span data-ttu-id="4fb86-131">文字列が一致しない場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="4fb86-131">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="4fb86-132">ワイルドカードパターン</span><span class="sxs-lookup"><span data-stu-id="4fb86-132">wildcard pattern</span></span>                            |
|             | <span data-ttu-id="4fb86-133">-match</span><span class="sxs-lookup"><span data-stu-id="4fb86-133">-match</span></span>       | <span data-ttu-id="4fb86-134">文字列が regex と一致する場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="4fb86-134">Returns true when string matches regex</span></span>      |
|             |              | <span data-ttu-id="4fb86-135">種類$matches に一致する文字列が含まれています</span><span class="sxs-lookup"><span data-stu-id="4fb86-135">pattern; $matches contains matching strings</span></span> |
|             | <span data-ttu-id="4fb86-136">-notmatch</span><span class="sxs-lookup"><span data-stu-id="4fb86-136">-notmatch</span></span>    | <span data-ttu-id="4fb86-137">文字列が一致しない場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="4fb86-137">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="4fb86-138">regex パターン;一致する $matches が含まれています</span><span class="sxs-lookup"><span data-stu-id="4fb86-138">regex pattern; $matches contains matching</span></span>   |
|             |              | <span data-ttu-id="4fb86-139">文字列</span><span class="sxs-lookup"><span data-stu-id="4fb86-139">strings</span></span>                                     |
|             |              |                                             |
| <span data-ttu-id="4fb86-140">Containment</span><span class="sxs-lookup"><span data-stu-id="4fb86-140">Containment</span></span> | <span data-ttu-id="4fb86-141">-contains</span><span class="sxs-lookup"><span data-stu-id="4fb86-141">-contains</span></span>    | <span data-ttu-id="4fb86-142">参照値が含まれている場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="4fb86-142">Returns true when reference value contained</span></span> |
|             |              | <span data-ttu-id="4fb86-143">コレクション内</span><span class="sxs-lookup"><span data-stu-id="4fb86-143">in a collection</span></span>                             |
|             | <span data-ttu-id="4fb86-144">-notcontains</span><span class="sxs-lookup"><span data-stu-id="4fb86-144">-notcontains</span></span> | <span data-ttu-id="4fb86-145">参照値が指定されていない場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="4fb86-145">Returns true when reference value not</span></span>       |
|             |              | <span data-ttu-id="4fb86-146">コレクションに含まれる</span><span class="sxs-lookup"><span data-stu-id="4fb86-146">contained in a collection</span></span>                   |
|             | <span data-ttu-id="4fb86-147">-in</span><span class="sxs-lookup"><span data-stu-id="4fb86-147">-in</span></span>          | <span data-ttu-id="4fb86-148">テスト値がに含まれている場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="4fb86-148">Returns true when test value contained in a</span></span> |
|             |              | <span data-ttu-id="4fb86-149">collection</span><span class="sxs-lookup"><span data-stu-id="4fb86-149">collection</span></span>                                  |
|             | <span data-ttu-id="4fb86-150">-notin</span><span class="sxs-lookup"><span data-stu-id="4fb86-150">-notin</span></span>       | <span data-ttu-id="4fb86-151">テスト値が含まれていない場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="4fb86-151">Returns true when test value not contained</span></span>  |
|             |              | <span data-ttu-id="4fb86-152">コレクション内</span><span class="sxs-lookup"><span data-stu-id="4fb86-152">in a collection</span></span>                             |
|             |              |                                             |
| <span data-ttu-id="4fb86-153">Replacement</span><span class="sxs-lookup"><span data-stu-id="4fb86-153">Replacement</span></span> | <span data-ttu-id="4fb86-154">-replace</span><span class="sxs-lookup"><span data-stu-id="4fb86-154">-replace</span></span>     | <span data-ttu-id="4fb86-155">文字列パターンを置換します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-155">Replaces a string pattern</span></span>                   |
|             |              |                                             |
| <span data-ttu-id="4fb86-156">Type</span><span class="sxs-lookup"><span data-stu-id="4fb86-156">Type</span></span>        | <span data-ttu-id="4fb86-157">-が</span><span class="sxs-lookup"><span data-stu-id="4fb86-157">-is</span></span>          | <span data-ttu-id="4fb86-158">両方のオブジェクトが同じ場合に true を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-158">Returns true if both object are the same</span></span>    |
|             |              | <span data-ttu-id="4fb86-159">type</span><span class="sxs-lookup"><span data-stu-id="4fb86-159">type</span></span>                                        |
|             | <span data-ttu-id="4fb86-160">-isnot</span><span class="sxs-lookup"><span data-stu-id="4fb86-160">-isnot</span></span>       | <span data-ttu-id="4fb86-161">オブジェクトが同じでない場合に true を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-161">Returns true if the objects are not the same</span></span>|
|             |              | <span data-ttu-id="4fb86-162">type</span><span class="sxs-lookup"><span data-stu-id="4fb86-162">type</span></span>                                        |

<span data-ttu-id="4fb86-163">既定では、すべての比較演算子で大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-163">By default, all comparison operators are case-insensitive.</span></span> <span data-ttu-id="4fb86-164">大文字と小文字を区別する比較演算子を作成するには、演算子名の前にを付け `c` ます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-164">To make a comparison operator case-sensitive, precede the operator name with a `c`.</span></span> <span data-ttu-id="4fb86-165">たとえば、の大文字と小文字を区別するバージョン `-eq` はです `-ceq` 。</span><span class="sxs-lookup"><span data-stu-id="4fb86-165">For example, the case-sensitive version of `-eq` is `-ceq`.</span></span> <span data-ttu-id="4fb86-166">大文字小文字を区別しないようにするには、演算子の前にを付け `i` ます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-166">To make the case-insensitivity explicit, precede the operator with an `i`.</span></span> <span data-ttu-id="4fb86-167">たとえば、の明示的な大文字と小文字を区別しないバージョン `-eq` はです `-ieq` 。</span><span class="sxs-lookup"><span data-stu-id="4fb86-167">For example, the explicitly case-insensitive version of `-eq` is `-ieq`.</span></span>

<span data-ttu-id="4fb86-168">演算子への入力がスカラー値の場合、比較演算子はブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-168">When the input to an operator is a scalar value, comparison operators return a Boolean value.</span></span> <span data-ttu-id="4fb86-169">入力が値のコレクションである場合、比較演算子は一致する値を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-169">When the input is a collection of values, the comparison operators return any matching values.</span></span> <span data-ttu-id="4fb86-170">コレクションに一致するものがない場合、比較演算子は空の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-170">If there are no matches in a collection, comparison operators return an empty array.</span></span>

```powershell
PS> (1, 2 -eq 3).GetType().FullName
System.Object[]
```

<span data-ttu-id="4fb86-171">例外は、包含演算子、In 演算子、および型演算子で、常に **ブール** 値を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-171">The exceptions are the containment operators, the In operators, and the type operators, which always return a **Boolean** value.</span></span>

> [!NOTE]
> <span data-ttu-id="4fb86-172">値をと比較する必要がある場合は、 `$null` `$null` 比較の左側に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fb86-172">If you need to compare a value to `$null` you should put `$null` on the left-hand side of the comparison.</span></span> <span data-ttu-id="4fb86-173">`$null`**オブジェクト []** と比較すると、比較オブジェクトが配列であるため、結果は **False** になります。</span><span class="sxs-lookup"><span data-stu-id="4fb86-173">When you compare `$null` to an **Object[]** the result is **False** because the comparison object is an array.</span></span> <span data-ttu-id="4fb86-174">配列をと比較すると `$null` 、比較によって `$null` 配列に格納されているすべての値が除外されます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-174">When you compare an array to `$null`, the comparison filters out any `$null` values stored in the array.</span></span> <span data-ttu-id="4fb86-175">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-175">For example:</span></span>
>
> ```powershell
> PS> $null -ne $null, "hello"
> True
> PS> $null, "hello" -ne $null
> hello
> ```

## <a name="equality-operators"></a><span data-ttu-id="4fb86-176">等値演算子</span><span class="sxs-lookup"><span data-stu-id="4fb86-176">Equality operators</span></span>

<span data-ttu-id="4fb86-177">等値演算子 ( `-eq` 、 `-ne` ) は、1つ以上の入力値が指定されたパターンと同じ場合に TRUE または一致する値を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-177">The equality operators (`-eq`, `-ne`) return a value of TRUE or the matches when one or more of the input values is identical to the specified pattern.</span></span> <span data-ttu-id="4fb86-178">パターン全体が値全体と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fb86-178">The entire pattern must match an entire value.</span></span>

<span data-ttu-id="4fb86-179">例:</span><span class="sxs-lookup"><span data-stu-id="4fb86-179">Example:</span></span>

### <a name="-eq"></a><span data-ttu-id="4fb86-180">-eq</span><span class="sxs-lookup"><span data-stu-id="4fb86-180">-eq</span></span>

<span data-ttu-id="4fb86-181">説明: と等しい。</span><span class="sxs-lookup"><span data-stu-id="4fb86-181">Description: Equal to.</span></span> <span data-ttu-id="4fb86-182">には、同じ値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-182">Includes an identical value.</span></span>

<span data-ttu-id="4fb86-183">例:</span><span class="sxs-lookup"><span data-stu-id="4fb86-183">Example:</span></span>

```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS> 1,2,3 -eq 2
2
PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```

### <a name="-ne"></a><span data-ttu-id="4fb86-184">-ne</span><span class="sxs-lookup"><span data-stu-id="4fb86-184">-ne</span></span>

<span data-ttu-id="4fb86-185">説明: 等しくない。</span><span class="sxs-lookup"><span data-stu-id="4fb86-185">Description: Not equal to.</span></span> <span data-ttu-id="4fb86-186">に別の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4fb86-186">Includes a different value.</span></span>

<span data-ttu-id="4fb86-187">例:</span><span class="sxs-lookup"><span data-stu-id="4fb86-187">Example:</span></span>

```powershell
PS> "abc" -ne "def"
True

PS> "abc" -ne "abc"
False

PS> "abc" -ne "abc", "def"
True

PS> "abc", "def" -ne "abc"
def
```

### <a name="-gt"></a><span data-ttu-id="4fb86-188">-gt</span><span class="sxs-lookup"><span data-stu-id="4fb86-188">-gt</span></span>

<span data-ttu-id="4fb86-189">説明: より大きい。</span><span class="sxs-lookup"><span data-stu-id="4fb86-189">Description: Greater-than.</span></span>

<span data-ttu-id="4fb86-190">例:</span><span class="sxs-lookup"><span data-stu-id="4fb86-190">Example:</span></span>

```powershell
PS> 8 -gt 6
True

PS> 7, 8, 9 -gt 8
9
```

> [!NOTE]
> <span data-ttu-id="4fb86-191">`>`他の多くのプログラミング言語では、大なり演算子と混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="4fb86-191">This should not to be confused with `>`, the greater-than operator in many other programming languages.</span></span> <span data-ttu-id="4fb86-192">PowerShell で `>` は、はリダイレクトに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-192">In PowerShell, `>` is used for redirection.</span></span> <span data-ttu-id="4fb86-193">詳細については、「 [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fb86-193">For more information, see [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span></span>

### <a name="-ge"></a><span data-ttu-id="4fb86-194">-ge</span><span class="sxs-lookup"><span data-stu-id="4fb86-194">-ge</span></span>

<span data-ttu-id="4fb86-195">説明: より大きいか等しい。</span><span class="sxs-lookup"><span data-stu-id="4fb86-195">Description: Greater-than or equal to.</span></span>

<span data-ttu-id="4fb86-196">例:</span><span class="sxs-lookup"><span data-stu-id="4fb86-196">Example:</span></span>

```powershell
PS> 8 -ge 8
True

PS> 7, 8, 9 -ge 8
8
9
```

### <a name="-lt"></a><span data-ttu-id="4fb86-197">-lt</span><span class="sxs-lookup"><span data-stu-id="4fb86-197">-lt</span></span>

<span data-ttu-id="4fb86-198">説明: より小さい。</span><span class="sxs-lookup"><span data-stu-id="4fb86-198">Description: Less-than.</span></span>

<span data-ttu-id="4fb86-199">例:</span><span class="sxs-lookup"><span data-stu-id="4fb86-199">Example:</span></span>

```powershell

PS> 8 -lt 6
False

PS> 7, 8, 9 -lt 8
7
```

### <a name="-le"></a><span data-ttu-id="4fb86-200">-le</span><span class="sxs-lookup"><span data-stu-id="4fb86-200">-le</span></span>

<span data-ttu-id="4fb86-201">説明: 次の値より小さいか等しい。</span><span class="sxs-lookup"><span data-stu-id="4fb86-201">Description: Less-than or equal to.</span></span>

<span data-ttu-id="4fb86-202">例:</span><span class="sxs-lookup"><span data-stu-id="4fb86-202">Example:</span></span>

```powershell
PS> 6 -le 8
True

PS> 7, 8, 9 -le 8
7
8
```

## <a name="matching-operators"></a><span data-ttu-id="4fb86-203">照合演算子</span><span class="sxs-lookup"><span data-stu-id="4fb86-203">Matching operators</span></span>

<span data-ttu-id="4fb86-204">Like 演算子 ( `-like` および) は、 `-notlike` ワイルドカード式を使用して、指定したパターンに一致するか一致しない要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-204">The like operators (`-like` and `-notlike`) find elements that match or do not match a specified pattern using wildcard expressions.</span></span>

<span data-ttu-id="4fb86-205">の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4fb86-205">The syntax is:</span></span>

```powershell
<string[]> -like <wildcard-expression>
<string[]> -notlike <wildcard-expression>
```

<span data-ttu-id="4fb86-206">一致演算子 ( `-match` および) は、 `-notmatch` 正規表現を使用して、指定したパターンに一致するか一致しない要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-206">The match operators (`-match` and `-notmatch`) find elements that match or do not match a specified pattern using regular expressions.</span></span>

<span data-ttu-id="4fb86-207">一致演算子は、 `$Matches` 演算子への入力 (左側の引数) が単一のスカラーオブジェクトである場合に、自動変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-207">The match operators populate the `$Matches` automatic variable when the input (the left-side argument) to the operator is a single scalar object.</span></span> <span data-ttu-id="4fb86-208">入力がスカラーの場合、 `-match` および `-notmatch` 演算子はブール値を返し、 `$Matches` 自動変数の値を引数の一致するコンポーネントに設定します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-208">When the input is scalar, the `-match` and `-notmatch` operators return a Boolean value and set the value of the `$Matches` automatic variable to the matched components of the argument.</span></span>

<span data-ttu-id="4fb86-209">の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4fb86-209">The syntax is:</span></span>

```powershell
<string[]> -match <regular-expression>
<string[]> -notmatch <regular-expression>
```

### <a name="-like"></a><span data-ttu-id="4fb86-210">-like</span><span class="sxs-lookup"><span data-stu-id="4fb86-210">-like</span></span>

<span data-ttu-id="4fb86-211">説明: ワイルドカード文字 () を使用して一致し \* ます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-211">Description: Match using the wildcard character (\*).</span></span>

<span data-ttu-id="4fb86-212">例:</span><span class="sxs-lookup"><span data-stu-id="4fb86-212">Example:</span></span>

```powershell
PS> "PowerShell" -like "*shell"
True

PS> "PowerShell", "Server" -like "*shell"
PowerShell
```

### <a name="-notlike"></a><span data-ttu-id="4fb86-213">-notlike</span><span class="sxs-lookup"><span data-stu-id="4fb86-213">-notlike</span></span>

<span data-ttu-id="4fb86-214">説明: は、ワイルドカード文字 () を使用して一致しません \* 。</span><span class="sxs-lookup"><span data-stu-id="4fb86-214">Description: Does not match using the wildcard character (\*).</span></span>

<span data-ttu-id="4fb86-215">例:</span><span class="sxs-lookup"><span data-stu-id="4fb86-215">Example:</span></span>

```powershell
PS> "PowerShell" -notlike "*shell"
False

PS> "PowerShell", "Server" -notlike "*shell"
Server
```

### <a name="-match"></a><span data-ttu-id="4fb86-216">-match</span><span class="sxs-lookup"><span data-stu-id="4fb86-216">-match</span></span>

<span data-ttu-id="4fb86-217">説明: 正規表現を使用して文字列に一致します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-217">Description: Matches a string using regular expressions.</span></span> <span data-ttu-id="4fb86-218">入力がスカラーの場合は、自動変数が設定され `$Matches` ます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-218">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="4fb86-219">入力がコレクションの場合、演算子 `-match` と演算子は、 `-notmatch` そのコレクションの一致するメンバーを返しますが、演算子は変数に値を設定しません `$Matches` 。</span><span class="sxs-lookup"><span data-stu-id="4fb86-219">If the input is a collection, the `-match` and `-notmatch` operators return the matching members of that collection, but the operator does not populate the `$Matches` variable.</span></span>

<span data-ttu-id="4fb86-220">たとえば、次のコマンドは、文字列のコレクションを演算子に送信し `-match` ます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-220">For example, the following command submits a collection of strings to the `-match` operator.</span></span> <span data-ttu-id="4fb86-221">演算子は、 `-match` 一致するコレクション内の項目を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-221">The `-match` operator returns the items in the collection that match.</span></span> <span data-ttu-id="4fb86-222">自動変数は設定されません `$Matches` 。</span><span class="sxs-lookup"><span data-stu-id="4fb86-222">It does not populate the `$Matches` automatic variable.</span></span>

```powershell
PS> "Sunday", "Monday", "Tuesday" -match "sun"
Sunday

PS> $Matches
PS>
```

<span data-ttu-id="4fb86-223">これに対して、次のコマンドは、1つの文字列を演算子に送信し `-match` ます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-223">In contrast, the following command submits a single string to the `-match` operator.</span></span> <span data-ttu-id="4fb86-224">`-match`演算子はブール値を返し、自動変数を設定し `$Matches` ます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-224">The `-match` operator returns a Boolean value and populates the `$Matches` automatic variable.</span></span> <span data-ttu-id="4fb86-225">`$Matches`自動変数は **ハッシュテーブル** です。</span><span class="sxs-lookup"><span data-stu-id="4fb86-225">The `$Matches` automatic variable is a **Hashtable**.</span></span> <span data-ttu-id="4fb86-226">グループ化またはキャプチャが使用されていない場合は、1つのキーだけが設定されます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-226">If no grouping or capturing is used, only one key is populated.</span></span>
<span data-ttu-id="4fb86-227">キーは、 `0` 一致したすべてのテキストを表します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-227">The `0` key represents all text that was matched.</span></span> <span data-ttu-id="4fb86-228">正規表現を使用したグループ化とキャプチャの詳細については、「 [about_Regular_Expressions](about_Regular_Expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fb86-228">For more information about grouping and capturing using regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

```powershell
PS> "Sunday" -match "sun"
True

PS> $Matches

Name                           Value
----                           -----
0                              Sun
```

<span data-ttu-id="4fb86-229">ハッシュテーブルには、一致するパターンが最初に出現するだけが含まれていることに注意して `$Matches` ください。</span><span class="sxs-lookup"><span data-stu-id="4fb86-229">It is important to note that the `$Matches` hashtable will only contain the first occurrence of any matching pattern.</span></span>

```powershell
PS> "Banana" -match "na"
True

PS> $Matches

Name                           Value
----                           -----
0                              na
```

> [!IMPORTANT]
> <span data-ttu-id="4fb86-230">`0`キーは **整数** です。</span><span class="sxs-lookup"><span data-stu-id="4fb86-230">The `0` key is an **Integer**.</span></span> <span data-ttu-id="4fb86-231">任意の **ハッシュテーブル** メソッドを使用して、格納されている値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-231">You can use any **Hashtable** method to access the value stored.</span></span>
>
> ```powershell
> PS> "Good Dog" -match "Dog"
> True
>
> PS> $Matches[0]
> Dog
>
> PS> $Matches.Item(0)
> Dog
>
> PS> $Matches.0
> Dog
> ```

<span data-ttu-id="4fb86-232">演算子は、 `-notmatch` `$Matches` 入力がスカラーのときに自動変数を設定し、結果が False であること、つまり一致が検出されたときにその変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-232">The `-notmatch` operator populates the `$Matches` automatic variable when the input is scalar and the result is False, that it, when it detects a match.</span></span>

```powershell
PS> "Sunday" -notmatch "rain"
True

PS> $matches
PS>

PS> "Sunday" -notmatch "day"
False

PS> $matches

Name                           Value
----                           -----
0                              day
```

### <a name="-notmatch"></a><span data-ttu-id="4fb86-233">-notmatch</span><span class="sxs-lookup"><span data-stu-id="4fb86-233">-notmatch</span></span>

<span data-ttu-id="4fb86-234">説明: が文字列と一致しません。</span><span class="sxs-lookup"><span data-stu-id="4fb86-234">Description: Does not match a string.</span></span> <span data-ttu-id="4fb86-235">正規表現を使用します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-235">Uses regular expressions.</span></span> <span data-ttu-id="4fb86-236">入力がスカラーの場合は、自動変数が設定され `$Matches` ます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-236">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="4fb86-237">例:</span><span class="sxs-lookup"><span data-stu-id="4fb86-237">Example:</span></span>

```powershell
PS> "Sunday" -notmatch "sun"
False

PS> $matches
Name Value
---- -----
0    sun

PS> "Sunday", "Monday" -notmatch "sun"
Monday
```

## <a name="containment-operators"></a><span data-ttu-id="4fb86-238">含有演算子</span><span class="sxs-lookup"><span data-stu-id="4fb86-238">Containment operators</span></span>

<span data-ttu-id="4fb86-239">含有演算子 ( `-contains` と `-notcontains` ) は、等値演算子に似ています。</span><span class="sxs-lookup"><span data-stu-id="4fb86-239">The containment operators (`-contains` and `-notcontains`) are similar to the equality operators.</span></span> <span data-ttu-id="4fb86-240">ただし、入力がコレクションの場合でも、コンテインメント演算子は常にブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-240">However, the containment operators always return a Boolean value, even when the input is a collection.</span></span>

<span data-ttu-id="4fb86-241">また、等値演算子とは異なり、コンテインメント演算子は、最初の一致を検出するとすぐに値を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-241">Also, unlike the equality operators, the containment operators return a value as soon as they detect the first match.</span></span> <span data-ttu-id="4fb86-242">等値演算子は、すべての入力を評価し、コレクション内のすべての一致を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-242">The equality operators evaluate all input and then return all the matches in the collection.</span></span>

### <a name="-contains"></a><span data-ttu-id="4fb86-243">-contains</span><span class="sxs-lookup"><span data-stu-id="4fb86-243">-contains</span></span>

<span data-ttu-id="4fb86-244">説明: コンテインメント演算子。</span><span class="sxs-lookup"><span data-stu-id="4fb86-244">Description: Containment operator.</span></span> <span data-ttu-id="4fb86-245">参照値のコレクションに1つのテスト値が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-245">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="4fb86-246">常にブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-246">Always returns a Boolean value.</span></span> <span data-ttu-id="4fb86-247">テスト値が参照値の少なくとも1つと完全に一致する場合にのみ TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-247">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="4fb86-248">テスト値がコレクションの場合、Contains 演算子は参照の等価性を使用します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-248">When the test value is a collection, the Contains operator uses reference equality.</span></span> <span data-ttu-id="4fb86-249">参照値の1つがテスト値オブジェクトの同じインスタンスである場合にのみ、TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-249">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="4fb86-250">非常に大きなコレクションでは、 `-contains` 演算子は equal to 演算子よりも結果を迅速に返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-250">In a very large collection, the `-contains` operator returns results quicker than the equal to operator.</span></span>

<span data-ttu-id="4fb86-251">構文:</span><span class="sxs-lookup"><span data-stu-id="4fb86-251">Syntax:</span></span>

`<Reference-values> -contains <Test-value>`

<span data-ttu-id="4fb86-252">例:</span><span class="sxs-lookup"><span data-stu-id="4fb86-252">Examples:</span></span>

```powershell
PS> "abc", "def" -contains "def"
True

PS> "Windows", "PowerShell" -contains "Shell"
False  #Not an exact match

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $DomainServers -contains $thisComputer
True

PS> "abc", "def", "ghi" -contains "abc", "def"
False

PS> $a = "abc", "def"
PS> "abc", "def", "ghi" -contains $a
False
PS> $a, "ghi" -contains $a
True
```

### <a name="-notcontains"></a><span data-ttu-id="4fb86-253">-notcontains</span><span class="sxs-lookup"><span data-stu-id="4fb86-253">-notcontains</span></span>

<span data-ttu-id="4fb86-254">説明: コンテインメント演算子。</span><span class="sxs-lookup"><span data-stu-id="4fb86-254">Description: Containment operator.</span></span> <span data-ttu-id="4fb86-255">参照値のコレクションに1つのテスト値が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-255">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="4fb86-256">常にブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-256">Always returns a Boolean value.</span></span> <span data-ttu-id="4fb86-257">テスト値が参照値の少なくとも1つと完全に一致しない場合に TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-257">Returns TRUE when the test value is not an exact matches for at least one of the reference values.</span></span>

<span data-ttu-id="4fb86-258">テスト値がコレクションの場合、NotContains 演算子は参照の等価性を使用します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-258">When the test value is a collection, the NotContains operator uses reference equality.</span></span>

<span data-ttu-id="4fb86-259">構文:</span><span class="sxs-lookup"><span data-stu-id="4fb86-259">Syntax:</span></span>

`<Reference-values> -notcontains <Test-value>`

<span data-ttu-id="4fb86-260">例:</span><span class="sxs-lookup"><span data-stu-id="4fb86-260">Examples:</span></span>

```powershell
PS> "Windows", "PowerShell" -notcontains "Shell"
True  #Not an exact match

# Get cmdlet parameters, but exclude common parameters
function get-parms ($cmdlet)
{
    $Common = "Verbose", "Debug", "WarningAction", "WarningVariable",
      "ErrorAction", "ErrorVariable", "OutVariable", "OutBuffer"

    $allparms = (Get-Command $Cmdlet).parametersets |
      foreach {$_.Parameters} |
        foreach {$_.Name} | Sort-Object | Get-Unique

    $allparms | where {$Common -notcontains $_ }
}

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $myVerbs = Get-Command -Module MyModule | foreach {$_.verb}
PS> $myVerbs | where {$ApprovedVerbs -notcontains $_}
ForEach
Sort
Tee
Where
```

### <a name="-in"></a><span data-ttu-id="4fb86-261">-in</span><span class="sxs-lookup"><span data-stu-id="4fb86-261">-in</span></span>

<span data-ttu-id="4fb86-262">説明: In 演算子。</span><span class="sxs-lookup"><span data-stu-id="4fb86-262">Description: In operator.</span></span> <span data-ttu-id="4fb86-263">テスト値が参照値のコレクションに表示されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-263">Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="4fb86-264">常にブール値として返されます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-264">Always return as Boolean value.</span></span> <span data-ttu-id="4fb86-265">テスト値が参照値の少なくとも1つと完全に一致する場合にのみ TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-265">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="4fb86-266">テスト値がコレクションの場合、In 演算子は参照の等価性を使用します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-266">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="4fb86-267">参照値の1つがテスト値オブジェクトの同じインスタンスである場合にのみ、TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-267">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="4fb86-268">演算子は、 `-in` PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4fb86-268">The `-in` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="4fb86-269">構文:</span><span class="sxs-lookup"><span data-stu-id="4fb86-269">Syntax:</span></span>

`<Test-value> -in <Reference-values>`

<span data-ttu-id="4fb86-270">例:</span><span class="sxs-lookup"><span data-stu-id="4fb86-270">Examples:</span></span>

```powershell
PS> "def" -in "abc", "def"
True

PS> "Shell" -in "Windows", "PowerShell"
False  #Not an exact match

PS> "Windows" -in "Windows", "PowerShell"
True  #An exact match

PS> "Windows", "PowerShell" -in "Windows", "PowerShell", "ServerManager"
False  #Using reference equality

PS> $a = "Windows", "PowerShell"
PS> $a -in $a, "ServerManager"
True  #Using reference equality

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $thisComputer -in  $domainServers
True
```

### <a name="-notin"></a><span data-ttu-id="4fb86-271">-notin</span><span class="sxs-lookup"><span data-stu-id="4fb86-271">-notin</span></span>

<span data-ttu-id="4fb86-272">Description: テスト値が参照値のコレクションに表示されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-272">Description: Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="4fb86-273">常にブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-273">Always returns a Boolean value.</span></span> <span data-ttu-id="4fb86-274">テスト値が参照値の少なくとも1つと完全に一致しない場合に TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-274">Returns TRUE when the test value is not an exact match for at least one of the reference values.</span></span>

<span data-ttu-id="4fb86-275">テスト値がコレクションの場合、In 演算子は参照の等価性を使用します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-275">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="4fb86-276">参照値の1つがテスト値オブジェクトの同じインスタンスである場合にのみ、TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-276">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="4fb86-277">演算子は、 `-notin` PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4fb86-277">The `-notin` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="4fb86-278">構文:</span><span class="sxs-lookup"><span data-stu-id="4fb86-278">Syntax:</span></span>

`<Test-value> -notin <Reference-values>`

<span data-ttu-id="4fb86-279">例:</span><span class="sxs-lookup"><span data-stu-id="4fb86-279">Examples:</span></span>

```powershell
PS> "def" -notin "abc", "def"
False

PS> "ghi" -notin "abc", "def"
True

PS> "Shell" -notin "Windows", "PowerShell"
True  #Not an exact match

PS> "Windows" -notin "Windows", "PowerShell"
False  #An exact match

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $MyVerbs = Get-Command -Module MyModule | foreach {$_.verb}

PS> $MyVerbs | where {$_ -notin $ApprovedVerbs}
ForEach
Sort
Tee
Where
```

## <a name="replacement-operator"></a><span data-ttu-id="4fb86-280">置換演算子</span><span class="sxs-lookup"><span data-stu-id="4fb86-280">Replacement Operator</span></span>

<span data-ttu-id="4fb86-281">`-replace`演算子の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4fb86-281">The `-replace` operator has the following syntax:</span></span>

`<input> -replace <original>, <substitute>`

<span data-ttu-id="4fb86-282">`<original>`プレースホルダーは、置換する文字と一致する正規表現です。</span><span class="sxs-lookup"><span data-stu-id="4fb86-282">The `<original>` placeholder is a regular expression matching the characters to be replaced.</span></span> <span data-ttu-id="4fb86-283">`<substitute>`プレースホルダーは、それらを置き換えるリテラル文字列です。</span><span class="sxs-lookup"><span data-stu-id="4fb86-283">The `<substitute>` placeholder is a literal string that replaces them.</span></span>

<span data-ttu-id="4fb86-284">演算子は、値のすべてまたは一部を、正規表現を使用して、指定された値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-284">The operator replaces all or part of a value with the specified value using regular expressions.</span></span> <span data-ttu-id="4fb86-285">演算子は、ファイル名の変更など、多くの管理タスクに使用できます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-285">You can use the operator for many administrative tasks, such as renaming files.</span></span> <span data-ttu-id="4fb86-286">たとえば、次のコマンドは、すべてのファイルのファイル名拡張子 `.txt` をに変更し `.log` ます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-286">For example, the following command changes the file name extensions of all `.txt` files to `.log`:</span></span>

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

### <a name="case-sensitive-matches"></a><span data-ttu-id="4fb86-287">大文字と小文字を区別する一致</span><span class="sxs-lookup"><span data-stu-id="4fb86-287">Case-sensitive matches</span></span>

<span data-ttu-id="4fb86-288">既定では、 `-replace` 演算子は大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="4fb86-288">By default, the `-replace` operator is case-insensitive.</span></span> <span data-ttu-id="4fb86-289">大文字と小文字を区別するには、を使用 `-creplace` します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-289">To make it case sensitive, use `-creplace`.</span></span> <span data-ttu-id="4fb86-290">大文字と小文字を区別しないようにするには、を使用 `-ireplace` します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-290">To make it explicitly case-insensitive, use `-ireplace`.</span></span>

<span data-ttu-id="4fb86-291">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-291">Consider the following examples:</span></span>

```powershell
PS> "book" -replace "B", "C"
Cook
```

```powershell
PS> "book" -ireplace "B", "C"
Cook
```

```powershell
PS> "book" -creplace "B", "C"
book
```

### <a name="substitutions-in-regular-expressions"></a><span data-ttu-id="4fb86-292">正規表現での置換</span><span class="sxs-lookup"><span data-stu-id="4fb86-292">Substitutions in regular expressions</span></span>

<span data-ttu-id="4fb86-293">また、正規表現を使用して、キャプチャグループと置換を使用してテキストを動的に置換することもできます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-293">It is also possible to use regular expressions to dynamically replace text using capturing groups, and substitutions.</span></span> <span data-ttu-id="4fb86-294">キャプチャグループは、 `<substitute>` `$` グループ識別子の前にドル記号 () を使用して、文字列内で参照できます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-294">Capture groups can be referenced in the `<substitute>` string using the dollar sign (`$`) character before the group identifier.</span></span>

<span data-ttu-id="4fb86-295">キャプチャグループは、**数値** または **名前** で参照できます</span><span class="sxs-lookup"><span data-stu-id="4fb86-295">Capture groups can be referenced by **Number** or **Name**</span></span>

- <span data-ttu-id="4fb86-296">**数値** キャプチャグループには、左から右に番号が付けられます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-296">By **Number** - Capturing Groups are numbered from left to right.</span></span>

  ```powershell
  PS> "John D. Smith" -replace "(\w+) (\w+)\. (\w+)", '$1.$2.$3@contoso.com'
  John.D.Smith@contoso.com
  ```

- <span data-ttu-id="4fb86-297">**名前** のキャプチャグループは、名前によって参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-297">By **Name** - Capturing Groups can also be referenced by name.</span></span>

  ```powershell
  PS> "CONTOSO\Administrator" -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  FABRIKAM\Administrator
  ```

> [!WARNING]
> <span data-ttu-id="4fb86-298">文字は `$` 文字列の展開で使用されるため、リテラル文字列を使用するか、文字をエスケープする必要があり `$` ます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-298">Since the `$` character is used in string expansion, you will must use literal strings or escape the `$` character.</span></span>
>
> ```powershell
> PS> 'Hello World' -replace '(\w+) \w+', "`$1 Universe"
> Hello Universe
> ```
>
> <span data-ttu-id="4fb86-299">また、文字は `$` 代入で使用されるため、文字列内のすべてのインスタンスをエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fb86-299">Additionally, since the `$` character is used in substitution, you must escape any instances in your string.</span></span>
>
> ```powershell
> PS> '5.72' -replace '(.+)', '$$$1'
> $5.72
> ```

<span data-ttu-id="4fb86-300">詳細については、「[正規表現での](/dotnet/standard/base-types/substitutions-in-regular-expressions) [about_Regular_Expressions](about_Regular_Expressions.md)と置換」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fb86-300">To learn more see [about_Regular_Expressions](about_Regular_Expressions.md) and [Substitutions in Regular Expressions](/dotnet/standard/base-types/substitutions-in-regular-expressions)</span></span>

### <a name="substituting-in-a-collection"></a><span data-ttu-id="4fb86-301">コレクション内での置換</span><span class="sxs-lookup"><span data-stu-id="4fb86-301">Substituting in a collection</span></span>

<span data-ttu-id="4fb86-302">`<input>`演算子へのが `-replace` コレクションである場合、PowerShell はコレクションのすべての値に置換を適用します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-302">When the `<input>` to the `-replace` operator is a collection, PowerShell applies the replacement to every value in the collection.</span></span> <span data-ttu-id="4fb86-303">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-303">For example:</span></span>

```powershell
"B1","B2","B3","B4","B5" -replace "B", 'a'
a1
a2
a3
a4
a5
```

### <a name="scriptblock-substitutions"></a><span data-ttu-id="4fb86-304">ScriptBlock の置換</span><span class="sxs-lookup"><span data-stu-id="4fb86-304">ScriptBlock substitutions</span></span>

<span data-ttu-id="4fb86-305">PowerShell 6 以降では、_代替_ テキストに **ScriptBlock** 引数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-305">Beginning in PowerShell 6, you can use a **ScriptBlock** argument for the _Substitution_ text.</span></span> <span data-ttu-id="4fb86-306">**ScriptBlock** は、_入力_ 文字列で見つかった一致ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-306">The **ScriptBlock** will execute for each match found in the _input_ string.</span></span>

<span data-ttu-id="4fb86-307">**ScriptBlock** 内では、自動変数を使用し `$_` て、現在の **system.text.regularexpressions.regexoptions** オブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="4fb86-307">Within the **ScriptBlock**, use the `$_` automatic variable to refer to the current **System.Text.RegularExpressions.Match** object.</span></span> <span data-ttu-id="4fb86-308">**Match** オブジェクトを使用すると、置き換えられる現在の入力テキストに加えて、その他の有用な情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-308">The **Match** object gives you access to the current input text being replaced, as well as other useful information.</span></span>

<span data-ttu-id="4fb86-309">この例では、3つの10進数の各シーケンスを、それと等価な文字に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-309">This example replaces each sequence of three decimals with the character equivalent.</span></span> <span data-ttu-id="4fb86-310">**ScriptBlock** は、置換する必要がある3つの10進数のセットごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-310">The **ScriptBlock** is run for each set of three decimals that needs to be replaced.</span></span>

```powershell
PS> "072101108108111" -replace "\d{3}", {[char][int]$_.Value}
Hello
```

## <a name="type-comparison"></a><span data-ttu-id="4fb86-311">型の比較</span><span class="sxs-lookup"><span data-stu-id="4fb86-311">Type comparison</span></span>

<span data-ttu-id="4fb86-312">型の比較演算子 ( `-is` と `-isnot` ) は、オブジェクトが特定の型であるかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4fb86-312">The type comparison operators (`-is` and `-isnot`) are used to determine if an object is a specific type.</span></span>

### <a name="-is"></a><span data-ttu-id="4fb86-313">-が</span><span class="sxs-lookup"><span data-stu-id="4fb86-313">-is</span></span>

<span data-ttu-id="4fb86-314">構文:</span><span class="sxs-lookup"><span data-stu-id="4fb86-314">Syntax:</span></span>

`<object> -is <type reference>`

<span data-ttu-id="4fb86-315">例:</span><span class="sxs-lookup"><span data-stu-id="4fb86-315">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -is [int]
True
PS> $a -is $b.GetType()
False
```

### <a name="-isnot"></a><span data-ttu-id="4fb86-316">-isnot</span><span class="sxs-lookup"><span data-stu-id="4fb86-316">-isnot</span></span>

<span data-ttu-id="4fb86-317">構文:</span><span class="sxs-lookup"><span data-stu-id="4fb86-317">Syntax:</span></span>

`<object> -isnot <type reference>`

<span data-ttu-id="4fb86-318">例:</span><span class="sxs-lookup"><span data-stu-id="4fb86-318">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -isnot $b.GetType()
True
PS> $b -isnot [int]
True
```

## <a name="see-also"></a><span data-ttu-id="4fb86-319">関連項目</span><span class="sxs-lookup"><span data-stu-id="4fb86-319">See also</span></span>

- [<span data-ttu-id="4fb86-320">about_Operators</span><span class="sxs-lookup"><span data-stu-id="4fb86-320">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="4fb86-321">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="4fb86-321">about_Regular_Expressions</span></span>](about_Regular_Expressions.md)
- [<span data-ttu-id="4fb86-322">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="4fb86-322">about_Wildcards</span></span>](about_Wildcards.md)
- [<span data-ttu-id="4fb86-323">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="4fb86-323">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [<span data-ttu-id="4fb86-324">Foreach-オブジェクト</span><span class="sxs-lookup"><span data-stu-id="4fb86-324">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [<span data-ttu-id="4fb86-325">Where-Object</span><span class="sxs-lookup"><span data-stu-id="4fb86-325">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
