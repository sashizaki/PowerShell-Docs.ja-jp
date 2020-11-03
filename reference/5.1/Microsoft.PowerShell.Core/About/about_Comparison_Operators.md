---
description: PowerShell の値を比較する演算子について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: b6076e20ad3ecbe9f2def157bb20bdb3bee5b7ad
ms.sourcegitcommit: c9e56ec489522c706b8d6b8733f3f015d6d7e893
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224531"
---
# <a name="about-comparison-operators"></a><span data-ttu-id="6f12f-104">比較演算子について</span><span class="sxs-lookup"><span data-stu-id="6f12f-104">About Comparison Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="6f12f-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="6f12f-105">Short description</span></span>
<span data-ttu-id="6f12f-106">PowerShell の値を比較する演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-106">Describes the operators that compare values in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="6f12f-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="6f12f-107">Long description</span></span>

<span data-ttu-id="6f12f-108">比較演算子を使用すると、値を比較し、指定したパターンに一致する値を検索するための条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-108">Comparison operators let you specify conditions for comparing values and finding values that match specified patterns.</span></span> <span data-ttu-id="6f12f-109">比較演算子を使用するには、比較する値を、これらの値を区切る演算子と組み合わせて指定します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-109">To use a comparison operator, specify the values that you want to compare together with an operator that separates these values.</span></span>

<span data-ttu-id="6f12f-110">PowerShell には、次の比較演算子が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6f12f-110">PowerShell includes the following comparison operators:</span></span>

| <span data-ttu-id="6f12f-111">Type</span><span class="sxs-lookup"><span data-stu-id="6f12f-111">Type</span></span>        | <span data-ttu-id="6f12f-112">演算子</span><span class="sxs-lookup"><span data-stu-id="6f12f-112">Operators</span></span>    | <span data-ttu-id="6f12f-113">説明</span><span class="sxs-lookup"><span data-stu-id="6f12f-113">Description</span></span>                                 |
| ----------- | ------------ | --------------------------------------------|
| <span data-ttu-id="6f12f-114">等式</span><span class="sxs-lookup"><span data-stu-id="6f12f-114">Equality</span></span>    | <span data-ttu-id="6f12f-115">-eq</span><span class="sxs-lookup"><span data-stu-id="6f12f-115">-eq</span></span>          | <span data-ttu-id="6f12f-116">次の値に等しい</span><span class="sxs-lookup"><span data-stu-id="6f12f-116">equals</span></span>                                      |
|             | <span data-ttu-id="6f12f-117">-ne</span><span class="sxs-lookup"><span data-stu-id="6f12f-117">-ne</span></span>          | <span data-ttu-id="6f12f-118">等しくない</span><span class="sxs-lookup"><span data-stu-id="6f12f-118">not equals</span></span>                                  |
|             | <span data-ttu-id="6f12f-119">-gt</span><span class="sxs-lookup"><span data-stu-id="6f12f-119">-gt</span></span>          | <span data-ttu-id="6f12f-120">より大きい</span><span class="sxs-lookup"><span data-stu-id="6f12f-120">greater than</span></span>                                |
|             | <span data-ttu-id="6f12f-121">-ge</span><span class="sxs-lookup"><span data-stu-id="6f12f-121">-ge</span></span>          | <span data-ttu-id="6f12f-122">以上</span><span class="sxs-lookup"><span data-stu-id="6f12f-122">greater than or equal</span></span>                       |
|             | <span data-ttu-id="6f12f-123">-lt</span><span class="sxs-lookup"><span data-stu-id="6f12f-123">-lt</span></span>          | <span data-ttu-id="6f12f-124">次の値未満</span><span class="sxs-lookup"><span data-stu-id="6f12f-124">less than</span></span>                                   |
|             | <span data-ttu-id="6f12f-125">-le</span><span class="sxs-lookup"><span data-stu-id="6f12f-125">-le</span></span>          | <span data-ttu-id="6f12f-126">以下</span><span class="sxs-lookup"><span data-stu-id="6f12f-126">less than or equal</span></span>                          |
|             |              |                                             |
| <span data-ttu-id="6f12f-127">Matching</span><span class="sxs-lookup"><span data-stu-id="6f12f-127">Matching</span></span>    | <span data-ttu-id="6f12f-128">-like</span><span class="sxs-lookup"><span data-stu-id="6f12f-128">-like</span></span>        | <span data-ttu-id="6f12f-129">文字列がワイルドカードに一致する場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="6f12f-129">Returns true when string matches wildcard</span></span>   |
|             |              | <span data-ttu-id="6f12f-130">pattern</span><span class="sxs-lookup"><span data-stu-id="6f12f-130">pattern</span></span>                                     |
|             | <span data-ttu-id="6f12f-131">-notlike</span><span class="sxs-lookup"><span data-stu-id="6f12f-131">-notlike</span></span>     | <span data-ttu-id="6f12f-132">文字列が一致しない場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="6f12f-132">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="6f12f-133">ワイルドカードパターン</span><span class="sxs-lookup"><span data-stu-id="6f12f-133">wildcard pattern</span></span>                            |
|             | <span data-ttu-id="6f12f-134">-match</span><span class="sxs-lookup"><span data-stu-id="6f12f-134">-match</span></span>       | <span data-ttu-id="6f12f-135">文字列が regex と一致する場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="6f12f-135">Returns true when string matches regex</span></span>      |
|             |              | <span data-ttu-id="6f12f-136">種類$matches に一致する文字列が含まれています</span><span class="sxs-lookup"><span data-stu-id="6f12f-136">pattern; $matches contains matching strings</span></span> |
|             | <span data-ttu-id="6f12f-137">-notmatch</span><span class="sxs-lookup"><span data-stu-id="6f12f-137">-notmatch</span></span>    | <span data-ttu-id="6f12f-138">文字列が一致しない場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="6f12f-138">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="6f12f-139">regex パターン;一致する $matches が含まれています</span><span class="sxs-lookup"><span data-stu-id="6f12f-139">regex pattern; $matches contains matching</span></span>   |
|             |              | <span data-ttu-id="6f12f-140">文字列</span><span class="sxs-lookup"><span data-stu-id="6f12f-140">strings</span></span>                                     |
|             |              |                                             |
| <span data-ttu-id="6f12f-141">Containment</span><span class="sxs-lookup"><span data-stu-id="6f12f-141">Containment</span></span> | <span data-ttu-id="6f12f-142">-contains</span><span class="sxs-lookup"><span data-stu-id="6f12f-142">-contains</span></span>    | <span data-ttu-id="6f12f-143">参照値が含まれている場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="6f12f-143">Returns true when reference value contained</span></span> |
|             |              | <span data-ttu-id="6f12f-144">コレクション内</span><span class="sxs-lookup"><span data-stu-id="6f12f-144">in a collection</span></span>                             |
|             | <span data-ttu-id="6f12f-145">-notcontains</span><span class="sxs-lookup"><span data-stu-id="6f12f-145">-notcontains</span></span> | <span data-ttu-id="6f12f-146">参照値が指定されていない場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="6f12f-146">Returns true when reference value not</span></span>       |
|             |              | <span data-ttu-id="6f12f-147">コレクションに含まれる</span><span class="sxs-lookup"><span data-stu-id="6f12f-147">contained in a collection</span></span>                   |
|             | <span data-ttu-id="6f12f-148">-in</span><span class="sxs-lookup"><span data-stu-id="6f12f-148">-in</span></span>          | <span data-ttu-id="6f12f-149">テスト値がに含まれている場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="6f12f-149">Returns true when test value contained in a</span></span> |
|             |              | <span data-ttu-id="6f12f-150">collection</span><span class="sxs-lookup"><span data-stu-id="6f12f-150">collection</span></span>                                  |
|             | <span data-ttu-id="6f12f-151">-notin</span><span class="sxs-lookup"><span data-stu-id="6f12f-151">-notin</span></span>       | <span data-ttu-id="6f12f-152">テスト値が含まれていない場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="6f12f-152">Returns true when test value not contained</span></span>  |
|             |              | <span data-ttu-id="6f12f-153">コレクション内</span><span class="sxs-lookup"><span data-stu-id="6f12f-153">in a collection</span></span>                             |
|             |              |                                             |
| <span data-ttu-id="6f12f-154">Replacement</span><span class="sxs-lookup"><span data-stu-id="6f12f-154">Replacement</span></span> | <span data-ttu-id="6f12f-155">-replace</span><span class="sxs-lookup"><span data-stu-id="6f12f-155">-replace</span></span>     | <span data-ttu-id="6f12f-156">文字列パターンを置換します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-156">Replaces a string pattern</span></span>                   |
|             |              |                                             |
| <span data-ttu-id="6f12f-157">Type</span><span class="sxs-lookup"><span data-stu-id="6f12f-157">Type</span></span>        | <span data-ttu-id="6f12f-158">-が</span><span class="sxs-lookup"><span data-stu-id="6f12f-158">-is</span></span>          | <span data-ttu-id="6f12f-159">両方のオブジェクトが同じ場合に true を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-159">Returns true if both object are the same</span></span>    |
|             |              | <span data-ttu-id="6f12f-160">type</span><span class="sxs-lookup"><span data-stu-id="6f12f-160">type</span></span>                                        |
|             | <span data-ttu-id="6f12f-161">-isnot</span><span class="sxs-lookup"><span data-stu-id="6f12f-161">-isnot</span></span>       | <span data-ttu-id="6f12f-162">オブジェクトが同じでない場合に true を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-162">Returns true if the objects are not the same</span></span>|
|             |              | <span data-ttu-id="6f12f-163">type</span><span class="sxs-lookup"><span data-stu-id="6f12f-163">type</span></span>                                        |

<span data-ttu-id="6f12f-164">既定では、すべての比較演算子で大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-164">By default, all comparison operators are case-insensitive.</span></span> <span data-ttu-id="6f12f-165">大文字と小文字を区別する比較演算子を作成するには、演算子名の前にを付け `c` ます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-165">To make a comparison operator case-sensitive, precede the operator name with a `c`.</span></span> <span data-ttu-id="6f12f-166">たとえば、の大文字と小文字を区別するバージョン `-eq` はです `-ceq` 。</span><span class="sxs-lookup"><span data-stu-id="6f12f-166">For example, the case-sensitive version of `-eq` is `-ceq`.</span></span> <span data-ttu-id="6f12f-167">大文字小文字を区別しないようにするには、演算子の前にを付け `i` ます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-167">To make the case-insensitivity explicit, precede the operator with an `i`.</span></span> <span data-ttu-id="6f12f-168">たとえば、の明示的な大文字と小文字を区別しないバージョン `-eq` はです `-ieq` 。</span><span class="sxs-lookup"><span data-stu-id="6f12f-168">For example, the explicitly case-insensitive version of `-eq` is `-ieq`.</span></span>

<span data-ttu-id="6f12f-169">演算子への入力がスカラー値の場合、比較演算子はブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-169">When the input to an operator is a scalar value, comparison operators return a Boolean value.</span></span> <span data-ttu-id="6f12f-170">入力が値のコレクションである場合、比較演算子は一致する値を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-170">When the input is a collection of values, the comparison operators return any matching values.</span></span> <span data-ttu-id="6f12f-171">コレクションに一致するものがない場合、比較演算子は空の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-171">If there are no matches in a collection, comparison operators return an empty array.</span></span>

```powershell
PS> (1, 2 -eq 3).GetType().FullName
System.Object[]
```

<span data-ttu-id="6f12f-172">例外は、包含演算子、In 演算子、および型演算子で、常に **ブール** 値を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-172">The exceptions are the containment operators, the In operators, and the type operators, which always return a **Boolean** value.</span></span>

> [!NOTE]
> <span data-ttu-id="6f12f-173">値をと比較する必要がある場合は、 `$null` `$null` 比較の左側に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f12f-173">If you need to compare a value to `$null` you should put `$null` on the left-hand side of the comparison.</span></span> <span data-ttu-id="6f12f-174">`$null`**オブジェクト []** と比較すると、比較オブジェクトが配列であるため、結果は **False** になります。</span><span class="sxs-lookup"><span data-stu-id="6f12f-174">When you compare `$null` to an **Object[]** the result is **False** because the comparison object is an array.</span></span> <span data-ttu-id="6f12f-175">配列をと比較すると `$null` 、比較によって `$null` 配列に格納されているすべての値が除外されます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-175">When you compare an array to `$null`, the comparison filters out any `$null` values stored in the array.</span></span> <span data-ttu-id="6f12f-176">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-176">For example:</span></span>
>
> ```powershell
> PS> $null -ne $null, "hello"
> True
> PS> $null, "hello" -ne $null
> hello
> ```

### <a name="equality-operators"></a><span data-ttu-id="6f12f-177">等値演算子</span><span class="sxs-lookup"><span data-stu-id="6f12f-177">Equality Operators</span></span>

<span data-ttu-id="6f12f-178">等値演算子 ( `-eq` 、 `-ne` ) は、1つ以上の入力値が指定されたパターンと同じ場合に TRUE または一致する値を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-178">The equality operators (`-eq`, `-ne`) return a value of TRUE or the matches when one or more of the input values is identical to the specified pattern.</span></span> <span data-ttu-id="6f12f-179">パターン全体が値全体と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f12f-179">The entire pattern must match an entire value.</span></span>

<span data-ttu-id="6f12f-180">例:</span><span class="sxs-lookup"><span data-stu-id="6f12f-180">Example:</span></span>

#### <a name="-eq"></a><span data-ttu-id="6f12f-181">-eq</span><span class="sxs-lookup"><span data-stu-id="6f12f-181">-eq</span></span>

<span data-ttu-id="6f12f-182">説明: と等しい。</span><span class="sxs-lookup"><span data-stu-id="6f12f-182">Description: Equal to.</span></span> <span data-ttu-id="6f12f-183">には、同じ値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-183">Includes an identical value.</span></span>

<span data-ttu-id="6f12f-184">例:</span><span class="sxs-lookup"><span data-stu-id="6f12f-184">Example:</span></span>

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

#### <a name="-ne"></a><span data-ttu-id="6f12f-185">-ne</span><span class="sxs-lookup"><span data-stu-id="6f12f-185">-ne</span></span>

<span data-ttu-id="6f12f-186">説明: 等しくない。</span><span class="sxs-lookup"><span data-stu-id="6f12f-186">Description: Not equal to.</span></span> <span data-ttu-id="6f12f-187">に別の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6f12f-187">Includes a different value.</span></span>

<span data-ttu-id="6f12f-188">例:</span><span class="sxs-lookup"><span data-stu-id="6f12f-188">Example:</span></span>

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

#### <a name="-gt"></a><span data-ttu-id="6f12f-189">-gt</span><span class="sxs-lookup"><span data-stu-id="6f12f-189">-gt</span></span>

<span data-ttu-id="6f12f-190">説明: より大きい。</span><span class="sxs-lookup"><span data-stu-id="6f12f-190">Description: Greater-than.</span></span>

<span data-ttu-id="6f12f-191">例:</span><span class="sxs-lookup"><span data-stu-id="6f12f-191">Example:</span></span>

```powershell
PS> 8 -gt 6
True

PS> 7, 8, 9 -gt 8
9
```

> [!NOTE]
> <span data-ttu-id="6f12f-192">`>`他の多くのプログラミング言語では、大なり演算子と混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="6f12f-192">This should not to be confused with `>`, the greater-than operator in many other programming languages.</span></span> <span data-ttu-id="6f12f-193">PowerShell で `>` は、はリダイレクトに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-193">In PowerShell, `>` is used for redirection.</span></span> <span data-ttu-id="6f12f-194">詳細については、「 [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f12f-194">For more information, see [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span></span>

#### <a name="-ge"></a><span data-ttu-id="6f12f-195">-ge</span><span class="sxs-lookup"><span data-stu-id="6f12f-195">-ge</span></span>

<span data-ttu-id="6f12f-196">説明: より大きいか等しい。</span><span class="sxs-lookup"><span data-stu-id="6f12f-196">Description: Greater-than or equal to.</span></span>

<span data-ttu-id="6f12f-197">例:</span><span class="sxs-lookup"><span data-stu-id="6f12f-197">Example:</span></span>

```powershell
PS> 8 -ge 8
True

PS> 7, 8, 9 -ge 8
8
9
```

#### <a name="-lt"></a><span data-ttu-id="6f12f-198">-lt</span><span class="sxs-lookup"><span data-stu-id="6f12f-198">-lt</span></span>

<span data-ttu-id="6f12f-199">説明: より小さい。</span><span class="sxs-lookup"><span data-stu-id="6f12f-199">Description: Less-than.</span></span>

<span data-ttu-id="6f12f-200">例:</span><span class="sxs-lookup"><span data-stu-id="6f12f-200">Example:</span></span>

```powershell

PS> 8 -lt 6
False

PS> 7, 8, 9 -lt 8
7
```

#### <a name="-le"></a><span data-ttu-id="6f12f-201">-le</span><span class="sxs-lookup"><span data-stu-id="6f12f-201">-le</span></span>

<span data-ttu-id="6f12f-202">説明: 次の値より小さいか等しい。</span><span class="sxs-lookup"><span data-stu-id="6f12f-202">Description: Less-than or equal to.</span></span>

<span data-ttu-id="6f12f-203">例:</span><span class="sxs-lookup"><span data-stu-id="6f12f-203">Example:</span></span>

```powershell
PS> 6 -le 8
True

PS> 7, 8, 9 -le 8
7
8
```

### <a name="matching-operators"></a><span data-ttu-id="6f12f-204">照合演算子</span><span class="sxs-lookup"><span data-stu-id="6f12f-204">Matching Operators</span></span>

<span data-ttu-id="6f12f-205">Like 演算子 ( `-like` および) は、 `-notlike` ワイルドカード式を使用して、指定したパターンに一致するか一致しない要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-205">The like operators (`-like` and `-notlike`) find elements that match or do not match a specified pattern using wildcard expressions.</span></span>

<span data-ttu-id="6f12f-206">の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6f12f-206">The syntax is:</span></span>

```powershell
<string[]> -like <wildcard-expression>
<string[]> -notlike <wildcard-expression>
```

<span data-ttu-id="6f12f-207">一致演算子 ( `-match` および) は、 `-notmatch` 正規表現を使用して、指定したパターンに一致するか一致しない要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-207">The match operators (`-match` and `-notmatch`) find elements that match or do not match a specified pattern using regular expressions.</span></span>

<span data-ttu-id="6f12f-208">一致演算子は、 `$Matches` 演算子への入力 (左側の引数) が単一のスカラーオブジェクトである場合に、自動変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-208">The match operators populate the `$Matches` automatic variable when the input (the left-side argument) to the operator is a single scalar object.</span></span> <span data-ttu-id="6f12f-209">入力がスカラーの場合、 `-match` および `-notmatch` 演算子はブール値を返し、 `$Matches` 自動変数の値を引数の一致するコンポーネントに設定します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-209">When the input is scalar, the `-match` and `-notmatch` operators return a Boolean value and set the value of the `$Matches` automatic variable to the matched components of the argument.</span></span>

<span data-ttu-id="6f12f-210">の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6f12f-210">The syntax is:</span></span>

```powershell
<string[]> -match <regular-expression>
<string[]> -notmatch <regular-expression>
```

#### <a name="-like"></a><span data-ttu-id="6f12f-211">-like</span><span class="sxs-lookup"><span data-stu-id="6f12f-211">-like</span></span>

<span data-ttu-id="6f12f-212">説明: ワイルドカード文字 () を使用して一致し \* ます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-212">Description: Match using the wildcard character (\*).</span></span>

<span data-ttu-id="6f12f-213">例:</span><span class="sxs-lookup"><span data-stu-id="6f12f-213">Example:</span></span>

```powershell
PS> "PowerShell" -like "*shell"
True

PS> "PowerShell", "Server" -like "*shell"
PowerShell
```

#### <a name="-notlike"></a><span data-ttu-id="6f12f-214">-notlike</span><span class="sxs-lookup"><span data-stu-id="6f12f-214">-notlike</span></span>

<span data-ttu-id="6f12f-215">説明: は、ワイルドカード文字 () を使用して一致しません \* 。</span><span class="sxs-lookup"><span data-stu-id="6f12f-215">Description: Does not match using the wildcard character (\*).</span></span>

<span data-ttu-id="6f12f-216">例:</span><span class="sxs-lookup"><span data-stu-id="6f12f-216">Example:</span></span>

```powershell
PS> "PowerShell" -notlike "*shell"
False

PS> "PowerShell", "Server" -notlike "*shell"
Server
```

### <a name="-match"></a><span data-ttu-id="6f12f-217">-match</span><span class="sxs-lookup"><span data-stu-id="6f12f-217">-match</span></span>

<span data-ttu-id="6f12f-218">説明: 正規表現を使用して文字列に一致します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-218">Description: Matches a string using regular expressions.</span></span> <span data-ttu-id="6f12f-219">入力がスカラーの場合は、自動変数が設定され `$Matches` ます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-219">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="6f12f-220">入力がコレクションの場合、演算子 `-match` と演算子は、 `-notmatch` そのコレクションの一致するメンバーを返しますが、演算子は変数に値を設定しません `$Matches` 。</span><span class="sxs-lookup"><span data-stu-id="6f12f-220">If the input is a collection, the `-match` and `-notmatch` operators return the matching members of that collection, but the operator does not populate the `$Matches` variable.</span></span>

<span data-ttu-id="6f12f-221">たとえば、次のコマンドは、文字列のコレクションを演算子に送信し `-match` ます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-221">For example, the following command submits a collection of strings to the `-match` operator.</span></span> <span data-ttu-id="6f12f-222">演算子は、 `-match` 一致するコレクション内の項目を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-222">The `-match` operator returns the items in the collection that match.</span></span> <span data-ttu-id="6f12f-223">自動変数は設定されません `$Matches` 。</span><span class="sxs-lookup"><span data-stu-id="6f12f-223">It does not populate the `$Matches` automatic variable.</span></span>

```powershell
PS> "Sunday", "Monday", "Tuesday" -match "sun"
Sunday

PS> $Matches
PS>
```

<span data-ttu-id="6f12f-224">これに対して、次のコマンドは、1つの文字列を演算子に送信し `-match` ます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-224">In contrast, the following command submits a single string to the `-match` operator.</span></span> <span data-ttu-id="6f12f-225">`-match`演算子はブール値を返し、自動変数を設定し `$Matches` ます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-225">The `-match` operator returns a Boolean value and populates the `$Matches` automatic variable.</span></span> <span data-ttu-id="6f12f-226">`$Matches`自動変数は **ハッシュテーブル** です。</span><span class="sxs-lookup"><span data-stu-id="6f12f-226">The `$Matches` automatic variable is a **Hashtable**.</span></span> <span data-ttu-id="6f12f-227">グループ化またはキャプチャが使用されていない場合は、1つのキーだけが設定されます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-227">If no grouping or capturing is used, only one key is populated.</span></span>
<span data-ttu-id="6f12f-228">キーは、 `0` 一致したすべてのテキストを表します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-228">The `0` key represents all text that was matched.</span></span> <span data-ttu-id="6f12f-229">正規表現を使用したグループ化とキャプチャの詳細については、「 [about_Regular_Expressions](about_Regular_Expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f12f-229">For more information about grouping and capturing using regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

```powershell
PS> "Sunday" -match "sun"
True

PS> $Matches

Name                           Value
----                           -----
0                              Sun
```

<span data-ttu-id="6f12f-230">ハッシュテーブルには、一致するパターンが最初に出現するだけが含まれていることに注意して `$Matches` ください。</span><span class="sxs-lookup"><span data-stu-id="6f12f-230">It is important to note that the `$Matches` hashtable will only contain the first occurrence of any matching pattern.</span></span>

```powershell
PS> "Banana" -match "na"
True

PS> $Matches

Name                           Value
----                           -----
0                              na
```

> [!IMPORTANT]
> <span data-ttu-id="6f12f-231">`0`キーは **整数** です。</span><span class="sxs-lookup"><span data-stu-id="6f12f-231">The `0` key is an **Integer**.</span></span> <span data-ttu-id="6f12f-232">任意の **ハッシュテーブル** メソッドを使用して、格納されている値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-232">You can use any **Hashtable** method to access the value stored.</span></span>
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

<span data-ttu-id="6f12f-233">演算子は、 `-notmatch` `$Matches` 入力がスカラーのときに自動変数を設定し、結果が False であること、つまり一致が検出されたときにその変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-233">The `-notmatch` operator populates the `$Matches` automatic variable when the input is scalar and the result is False, that it, when it detects a match.</span></span>

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

#### <a name="-notmatch"></a><span data-ttu-id="6f12f-234">-notmatch</span><span class="sxs-lookup"><span data-stu-id="6f12f-234">-notmatch</span></span>

<span data-ttu-id="6f12f-235">説明: が文字列と一致しません。</span><span class="sxs-lookup"><span data-stu-id="6f12f-235">Description: Does not match a string.</span></span> <span data-ttu-id="6f12f-236">正規表現を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-236">Uses regular expressions.</span></span> <span data-ttu-id="6f12f-237">入力がスカラーの場合は、自動変数が設定され `$Matches` ます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-237">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="6f12f-238">例:</span><span class="sxs-lookup"><span data-stu-id="6f12f-238">Example:</span></span>

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

### <a name="containment-operators"></a><span data-ttu-id="6f12f-239">含有演算子</span><span class="sxs-lookup"><span data-stu-id="6f12f-239">Containment Operators</span></span>

<span data-ttu-id="6f12f-240">含有演算子 ( `-contains` と `-notcontains` ) は、等値演算子に似ています。</span><span class="sxs-lookup"><span data-stu-id="6f12f-240">The containment operators (`-contains` and `-notcontains`) are similar to the equality operators.</span></span> <span data-ttu-id="6f12f-241">ただし、入力がコレクションの場合でも、コンテインメント演算子は常にブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-241">However, the containment operators always return a Boolean value, even when the input is a collection.</span></span>

<span data-ttu-id="6f12f-242">また、等値演算子とは異なり、コンテインメント演算子は、最初の一致を検出するとすぐに値を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-242">Also, unlike the equality operators, the containment operators return a value as soon as they detect the first match.</span></span> <span data-ttu-id="6f12f-243">等値演算子は、すべての入力を評価し、コレクション内のすべての一致を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-243">The equality operators evaluate all input and then return all the matches in the collection.</span></span>

#### <a name="-contains"></a><span data-ttu-id="6f12f-244">-contains</span><span class="sxs-lookup"><span data-stu-id="6f12f-244">-contains</span></span>

<span data-ttu-id="6f12f-245">説明: コンテインメント演算子。</span><span class="sxs-lookup"><span data-stu-id="6f12f-245">Description: Containment operator.</span></span> <span data-ttu-id="6f12f-246">参照値のコレクションに1つのテスト値が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-246">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="6f12f-247">常にブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-247">Always returns a Boolean value.</span></span> <span data-ttu-id="6f12f-248">テスト値が参照値の少なくとも1つと完全に一致する場合にのみ TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-248">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="6f12f-249">テスト値がコレクションの場合、Contains 演算子は参照の等価性を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-249">When the test value is a collection, the Contains operator uses reference equality.</span></span> <span data-ttu-id="6f12f-250">参照値の1つがテスト値オブジェクトの同じインスタンスである場合にのみ、TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-250">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="6f12f-251">非常に大きなコレクションでは、 `-contains` 演算子は equal to 演算子よりも結果を迅速に返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-251">In a very large collection, the `-contains` operator returns results quicker than the equal to operator.</span></span>

<span data-ttu-id="6f12f-252">構文:</span><span class="sxs-lookup"><span data-stu-id="6f12f-252">Syntax:</span></span>

`<Reference-values> -contains <Test-value>`

<span data-ttu-id="6f12f-253">例:</span><span class="sxs-lookup"><span data-stu-id="6f12f-253">Examples:</span></span>

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

#### <a name="-notcontains"></a><span data-ttu-id="6f12f-254">-notcontains</span><span class="sxs-lookup"><span data-stu-id="6f12f-254">-notcontains</span></span>

<span data-ttu-id="6f12f-255">説明: コンテインメント演算子。</span><span class="sxs-lookup"><span data-stu-id="6f12f-255">Description: Containment operator.</span></span> <span data-ttu-id="6f12f-256">参照値のコレクションに1つのテスト値が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-256">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="6f12f-257">常にブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-257">Always returns a Boolean value.</span></span> <span data-ttu-id="6f12f-258">テスト値が参照値の少なくとも1つと完全に一致しない場合に TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-258">Returns TRUE when the test value is not an exact matches for at least one of the reference values.</span></span>

<span data-ttu-id="6f12f-259">テスト値がコレクションの場合、NotContains 演算子は参照の等価性を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-259">When the test value is a collection, the NotContains operator uses reference equality.</span></span>

<span data-ttu-id="6f12f-260">構文:</span><span class="sxs-lookup"><span data-stu-id="6f12f-260">Syntax:</span></span>

`<Reference-values> -notcontains <Test-value>`

<span data-ttu-id="6f12f-261">例:</span><span class="sxs-lookup"><span data-stu-id="6f12f-261">Examples:</span></span>

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

#### <a name="-in"></a><span data-ttu-id="6f12f-262">-in</span><span class="sxs-lookup"><span data-stu-id="6f12f-262">-in</span></span>

<span data-ttu-id="6f12f-263">説明: In 演算子。</span><span class="sxs-lookup"><span data-stu-id="6f12f-263">Description: In operator.</span></span> <span data-ttu-id="6f12f-264">テスト値が参照値のコレクションに表示されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-264">Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="6f12f-265">常にブール値として返されます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-265">Always return as Boolean value.</span></span> <span data-ttu-id="6f12f-266">テスト値が参照値の少なくとも1つと完全に一致する場合にのみ TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-266">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="6f12f-267">テスト値がコレクションの場合、In 演算子は参照の等価性を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-267">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="6f12f-268">参照値の1つがテスト値オブジェクトの同じインスタンスである場合にのみ、TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-268">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="6f12f-269">演算子は、 `-in` PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6f12f-269">The `-in` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="6f12f-270">構文:</span><span class="sxs-lookup"><span data-stu-id="6f12f-270">Syntax:</span></span>

`<Test-value> -in <Reference-values>`

<span data-ttu-id="6f12f-271">例:</span><span class="sxs-lookup"><span data-stu-id="6f12f-271">Examples:</span></span>

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

#### <a name="-notin"></a><span data-ttu-id="6f12f-272">-notin</span><span class="sxs-lookup"><span data-stu-id="6f12f-272">-notin</span></span>

<span data-ttu-id="6f12f-273">Description: テスト値が参照値のコレクションに表示されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-273">Description: Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="6f12f-274">常にブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-274">Always returns a Boolean value.</span></span> <span data-ttu-id="6f12f-275">テスト値が参照値の少なくとも1つと完全に一致しない場合に TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-275">Returns TRUE when the test value is not an exact match for at least one of the reference values.</span></span>

<span data-ttu-id="6f12f-276">テスト値がコレクションの場合、In 演算子は参照の等価性を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-276">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="6f12f-277">参照値の1つがテスト値オブジェクトの同じインスタンスである場合にのみ、TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-277">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="6f12f-278">演算子は、 `-notin` PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6f12f-278">The `-notin` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="6f12f-279">構文:</span><span class="sxs-lookup"><span data-stu-id="6f12f-279">Syntax:</span></span>

`<Test-value> -notin <Reference-values>`

<span data-ttu-id="6f12f-280">例:</span><span class="sxs-lookup"><span data-stu-id="6f12f-280">Examples:</span></span>

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

### <a name="replacement-operator"></a><span data-ttu-id="6f12f-281">置換演算子</span><span class="sxs-lookup"><span data-stu-id="6f12f-281">Replacement Operator</span></span>

<span data-ttu-id="6f12f-282">演算子は、 `-replace` 値のすべてまたは一部を、正規表現を使用して、指定された値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-282">The `-replace` operator replaces all or part of a value with the specified value using regular expressions.</span></span> <span data-ttu-id="6f12f-283">`-replace`演算子は、ファイル名の変更など、多くの管理タスクに使用できます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-283">You can use the `-replace` operator for many administrative tasks, such as renaming files.</span></span> <span data-ttu-id="6f12f-284">たとえば、次のコマンドは、すべての .txt ファイルのファイル名拡張子を .log に変更します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-284">For example, the following command changes the file name extensions of all .txt files to .log:</span></span>

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

<span data-ttu-id="6f12f-285">演算子の構文は次のようになります。プレースホルダーは、置換する `-replace` 文字を表し、プレースホルダーはそれらを `<original>` `<substitute>` 置き換える文字を表します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-285">The syntax of the `-replace` operator is as follows, where the `<original>` placeholder represents the characters to be replaced, and the `<substitute>` placeholder represents the characters that will replace them:</span></span>

`<input> <operator> <original>, <substitute>`

<span data-ttu-id="6f12f-286">既定では、 `-replace` 演算子は大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="6f12f-286">By default, the `-replace` operator is case-insensitive.</span></span> <span data-ttu-id="6f12f-287">大文字と小文字を区別するには、を使用 `-creplace` します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-287">To make it case sensitive, use `-creplace`.</span></span> <span data-ttu-id="6f12f-288">大文字と小文字を区別しないようにするには、を使用 `-ireplace` します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-288">To make it explicitly case-insensitive, use `-ireplace`.</span></span>

<span data-ttu-id="6f12f-289">次の例を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="6f12f-289">Consider the following examples:</span></span>

```powershell
PS> "book" -replace "B", "C"
```

```Output
Cook
```

```powershell
"book" -ireplace "B", "C"
```

```Output
Cook
```

```powershell
"book" -creplace "B", "C"
```

```Output
book
```

<span data-ttu-id="6f12f-290">また、正規表現を使用して、キャプチャグループと置換を使用してテキストを動的に置換することもできます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-290">It is also possible to use regular expressions to dynamically replace text using capturing groups, and substitutions.</span></span> <span data-ttu-id="6f12f-291">詳細については、「 [about_Regular_Expressions](about_Regular_Expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f12f-291">For more information, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

#### <a name="substitutions-in-regular-expressions"></a><span data-ttu-id="6f12f-292">正規表現での置換</span><span class="sxs-lookup"><span data-stu-id="6f12f-292">Substitutions in Regular Expressions</span></span>

<span data-ttu-id="6f12f-293">さらに、キャプチャグループは文字列で参照でき \<substitute\> ます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-293">Additionally, capturing groups can be referenced in the \<substitute\> string.</span></span>
<span data-ttu-id="6f12f-294">これを行うには、 `$` グループ識別子の前にある文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-294">This is done by using the `$` character before the group identifier.</span></span>

<span data-ttu-id="6f12f-295">キャプチャグループを参照する2つの方法は、数値と **名前** で **指定** します。</span><span class="sxs-lookup"><span data-stu-id="6f12f-295">Two of the ways to reference capturing groups is by **Number** and by **Name**</span></span>

- <span data-ttu-id="6f12f-296">**数値** による -
   キャプチャグループには、左から右に番号が付けられます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-296">By **Number** -
Capturing Groups are numbered from left to right.</span></span>

  ```powershell
  "John D. Smith" -replace "(\w+) (\w+)\. (\w+)", '$1.$2.$3@contoso.com'
  ```

  ```Output
  John.D.Smith@contoso.com
  ```

- <span data-ttu-id="6f12f-297">名前 **によって** -
   キャプチャグループを名前で参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-297">By **Name** -
Capturing Groups can also be referenced by name.</span></span>

  ```powershell
  "CONTOSO\Administrator" -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  ```

  ```Output
  FABRIKOM\Administrator
  ```

> [!WARNING]
> <span data-ttu-id="6f12f-298">文字は `$` 文字列の展開で使用されるため、置換でリテラル文字列を使用するか、文字をエスケープする必要があり `$` ます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-298">Since the `$` character is used in string expansion, you will need to use literal strings with substitution, or escape the `$` character.</span></span>
>
> ```powershell
> 'Hello World' -replace '(\w+) \w+', "`$1 Universe"
> ```
>
> ```Output
> Hello Universe
> ```
>
> <span data-ttu-id="6f12f-299">また、 `$` 文字が置換で使用されるため、文字列内のすべてのインスタンスをエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f12f-299">Additionally, since the `$` character is used in substitution, you will need to escape any instances in your string.</span></span>
>
> ```powershell
> '5.72' -replace '(.+)', '$$$1'
> ```
>
> ```Output
> $5.72
> ```

<span data-ttu-id="6f12f-300">詳細については、「[正規表現での](/dotnet/standard/base-types/substitutions-in-regular-expressions) [about_Regular_Expressions](about_Regular_Expressions.md)と置換」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f12f-300">To learn more see [about_Regular_Expressions](about_Regular_Expressions.md) and [Substitutions in Regular Expressions](/dotnet/standard/base-types/substitutions-in-regular-expressions)</span></span>

### <a name="type-comparison"></a><span data-ttu-id="6f12f-301">型の比較</span><span class="sxs-lookup"><span data-stu-id="6f12f-301">Type comparison</span></span>

<span data-ttu-id="6f12f-302">型の比較演算子 ( `-is` と `-isnot` ) は、オブジェクトが特定の型であるかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6f12f-302">The type comparison operators (`-is` and `-isnot`) are used to determine if an object is a specific type.</span></span>

#### <a name="-is"></a><span data-ttu-id="6f12f-303">-が</span><span class="sxs-lookup"><span data-stu-id="6f12f-303">-is</span></span>

<span data-ttu-id="6f12f-304">構文:</span><span class="sxs-lookup"><span data-stu-id="6f12f-304">Syntax:</span></span>

`<object> -is <type reference>`

<span data-ttu-id="6f12f-305">例:</span><span class="sxs-lookup"><span data-stu-id="6f12f-305">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -is [int]
True
PS> $a -is $b.GetType()
False
```

#### <a name="-isnot"></a><span data-ttu-id="6f12f-306">-isnot</span><span class="sxs-lookup"><span data-stu-id="6f12f-306">-isnot</span></span>

<span data-ttu-id="6f12f-307">構文:</span><span class="sxs-lookup"><span data-stu-id="6f12f-307">Syntax:</span></span>

`<object> -isnot <type reference>`

<span data-ttu-id="6f12f-308">例:</span><span class="sxs-lookup"><span data-stu-id="6f12f-308">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -isnot $b.GetType()
True
PS> $b -isnot [int]
True
```

## <a name="see-also"></a><span data-ttu-id="6f12f-309">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f12f-309">SEE ALSO</span></span>

- [<span data-ttu-id="6f12f-310">about_Operators</span><span class="sxs-lookup"><span data-stu-id="6f12f-310">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="6f12f-311">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="6f12f-311">about_Regular_Expressions</span></span>](about_Regular_Expressions.md)
- [<span data-ttu-id="6f12f-312">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="6f12f-312">about_Wildcards</span></span>](about_Wildcards.md)
- [<span data-ttu-id="6f12f-313">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="6f12f-313">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [<span data-ttu-id="6f12f-314">Foreach-オブジェクト</span><span class="sxs-lookup"><span data-stu-id="6f12f-314">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [<span data-ttu-id="6f12f-315">Where-Object</span><span class="sxs-lookup"><span data-stu-id="6f12f-315">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
