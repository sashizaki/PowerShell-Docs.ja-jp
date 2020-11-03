---
description: PowerShell の値を比較する演算子について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: fe00608edd4cbada275112cb3ce7c20b34f5c5c6
ms.sourcegitcommit: c9e56ec489522c706b8d6b8733f3f015d6d7e893
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224544"
---
# <a name="about-comparison-operators"></a><span data-ttu-id="4d64b-104">比較演算子について</span><span class="sxs-lookup"><span data-stu-id="4d64b-104">About Comparison Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="4d64b-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="4d64b-105">Short description</span></span>
<span data-ttu-id="4d64b-106">PowerShell の値を比較する演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-106">Describes the operators that compare values in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="4d64b-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="4d64b-107">Long description</span></span>

<span data-ttu-id="4d64b-108">比較演算子を使用すると、値を比較し、指定したパターンに一致する値を検索するための条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-108">Comparison operators let you specify conditions for comparing values and finding values that match specified patterns.</span></span> <span data-ttu-id="4d64b-109">比較演算子を使用するには、比較する値を、これらの値を区切る演算子と組み合わせて指定します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-109">To use a comparison operator, specify the values that you want to compare together with an operator that separates these values.</span></span>

<span data-ttu-id="4d64b-110">PowerShell には、次の比較演算子が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4d64b-110">PowerShell includes the following comparison operators:</span></span>

| <span data-ttu-id="4d64b-111">Type</span><span class="sxs-lookup"><span data-stu-id="4d64b-111">Type</span></span>        | <span data-ttu-id="4d64b-112">演算子</span><span class="sxs-lookup"><span data-stu-id="4d64b-112">Operators</span></span>    | <span data-ttu-id="4d64b-113">説明</span><span class="sxs-lookup"><span data-stu-id="4d64b-113">Description</span></span>                                 |
| ----------- | ------------ | --------------------------------------------|
| <span data-ttu-id="4d64b-114">等式</span><span class="sxs-lookup"><span data-stu-id="4d64b-114">Equality</span></span>    | <span data-ttu-id="4d64b-115">-eq</span><span class="sxs-lookup"><span data-stu-id="4d64b-115">-eq</span></span>          | <span data-ttu-id="4d64b-116">次の値に等しい</span><span class="sxs-lookup"><span data-stu-id="4d64b-116">equals</span></span>                                      |
|             | <span data-ttu-id="4d64b-117">-ne</span><span class="sxs-lookup"><span data-stu-id="4d64b-117">-ne</span></span>          | <span data-ttu-id="4d64b-118">等しくない</span><span class="sxs-lookup"><span data-stu-id="4d64b-118">not equals</span></span>                                  |
|             | <span data-ttu-id="4d64b-119">-gt</span><span class="sxs-lookup"><span data-stu-id="4d64b-119">-gt</span></span>          | <span data-ttu-id="4d64b-120">より大きい</span><span class="sxs-lookup"><span data-stu-id="4d64b-120">greater than</span></span>                                |
|             | <span data-ttu-id="4d64b-121">-ge</span><span class="sxs-lookup"><span data-stu-id="4d64b-121">-ge</span></span>          | <span data-ttu-id="4d64b-122">以上</span><span class="sxs-lookup"><span data-stu-id="4d64b-122">greater than or equal</span></span>                       |
|             | <span data-ttu-id="4d64b-123">-lt</span><span class="sxs-lookup"><span data-stu-id="4d64b-123">-lt</span></span>          | <span data-ttu-id="4d64b-124">次の値未満</span><span class="sxs-lookup"><span data-stu-id="4d64b-124">less than</span></span>                                   |
|             | <span data-ttu-id="4d64b-125">-le</span><span class="sxs-lookup"><span data-stu-id="4d64b-125">-le</span></span>          | <span data-ttu-id="4d64b-126">以下</span><span class="sxs-lookup"><span data-stu-id="4d64b-126">less than or equal</span></span>                          |
|             |              |                                             |
| <span data-ttu-id="4d64b-127">Matching</span><span class="sxs-lookup"><span data-stu-id="4d64b-127">Matching</span></span>    | <span data-ttu-id="4d64b-128">-like</span><span class="sxs-lookup"><span data-stu-id="4d64b-128">-like</span></span>        | <span data-ttu-id="4d64b-129">文字列がワイルドカードに一致する場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="4d64b-129">Returns true when string matches wildcard</span></span>   |
|             |              | <span data-ttu-id="4d64b-130">pattern</span><span class="sxs-lookup"><span data-stu-id="4d64b-130">pattern</span></span>                                     |
|             | <span data-ttu-id="4d64b-131">-notlike</span><span class="sxs-lookup"><span data-stu-id="4d64b-131">-notlike</span></span>     | <span data-ttu-id="4d64b-132">文字列が一致しない場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="4d64b-132">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="4d64b-133">ワイルドカードパターン</span><span class="sxs-lookup"><span data-stu-id="4d64b-133">wildcard pattern</span></span>                            |
|             | <span data-ttu-id="4d64b-134">-match</span><span class="sxs-lookup"><span data-stu-id="4d64b-134">-match</span></span>       | <span data-ttu-id="4d64b-135">文字列が regex と一致する場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="4d64b-135">Returns true when string matches regex</span></span>      |
|             |              | <span data-ttu-id="4d64b-136">種類$matches に一致する文字列が含まれています</span><span class="sxs-lookup"><span data-stu-id="4d64b-136">pattern; $matches contains matching strings</span></span> |
|             | <span data-ttu-id="4d64b-137">-notmatch</span><span class="sxs-lookup"><span data-stu-id="4d64b-137">-notmatch</span></span>    | <span data-ttu-id="4d64b-138">文字列が一致しない場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="4d64b-138">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="4d64b-139">regex パターン;一致する $matches が含まれています</span><span class="sxs-lookup"><span data-stu-id="4d64b-139">regex pattern; $matches contains matching</span></span>   |
|             |              | <span data-ttu-id="4d64b-140">文字列</span><span class="sxs-lookup"><span data-stu-id="4d64b-140">strings</span></span>                                     |
|             |              |                                             |
| <span data-ttu-id="4d64b-141">Containment</span><span class="sxs-lookup"><span data-stu-id="4d64b-141">Containment</span></span> | <span data-ttu-id="4d64b-142">-contains</span><span class="sxs-lookup"><span data-stu-id="4d64b-142">-contains</span></span>    | <span data-ttu-id="4d64b-143">参照値が含まれている場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="4d64b-143">Returns true when reference value contained</span></span> |
|             |              | <span data-ttu-id="4d64b-144">コレクション内</span><span class="sxs-lookup"><span data-stu-id="4d64b-144">in a collection</span></span>                             |
|             | <span data-ttu-id="4d64b-145">-notcontains</span><span class="sxs-lookup"><span data-stu-id="4d64b-145">-notcontains</span></span> | <span data-ttu-id="4d64b-146">参照値が指定されていない場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="4d64b-146">Returns true when reference value not</span></span>       |
|             |              | <span data-ttu-id="4d64b-147">コレクションに含まれる</span><span class="sxs-lookup"><span data-stu-id="4d64b-147">contained in a collection</span></span>                   |
|             | <span data-ttu-id="4d64b-148">-in</span><span class="sxs-lookup"><span data-stu-id="4d64b-148">-in</span></span>          | <span data-ttu-id="4d64b-149">テスト値がに含まれている場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="4d64b-149">Returns true when test value contained in a</span></span> |
|             |              | <span data-ttu-id="4d64b-150">collection</span><span class="sxs-lookup"><span data-stu-id="4d64b-150">collection</span></span>                                  |
|             | <span data-ttu-id="4d64b-151">-notin</span><span class="sxs-lookup"><span data-stu-id="4d64b-151">-notin</span></span>       | <span data-ttu-id="4d64b-152">テスト値が含まれていない場合に true を返します</span><span class="sxs-lookup"><span data-stu-id="4d64b-152">Returns true when test value not contained</span></span>  |
|             |              | <span data-ttu-id="4d64b-153">コレクション内</span><span class="sxs-lookup"><span data-stu-id="4d64b-153">in a collection</span></span>                             |
|             |              |                                             |
| <span data-ttu-id="4d64b-154">Replacement</span><span class="sxs-lookup"><span data-stu-id="4d64b-154">Replacement</span></span> | <span data-ttu-id="4d64b-155">-replace</span><span class="sxs-lookup"><span data-stu-id="4d64b-155">-replace</span></span>     | <span data-ttu-id="4d64b-156">文字列パターンを置換します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-156">Replaces a string pattern</span></span>                   |
|             |              |                                             |
| <span data-ttu-id="4d64b-157">Type</span><span class="sxs-lookup"><span data-stu-id="4d64b-157">Type</span></span>        | <span data-ttu-id="4d64b-158">-が</span><span class="sxs-lookup"><span data-stu-id="4d64b-158">-is</span></span>          | <span data-ttu-id="4d64b-159">両方のオブジェクトが同じ場合に true を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-159">Returns true if both object are the same</span></span>    |
|             |              | <span data-ttu-id="4d64b-160">type</span><span class="sxs-lookup"><span data-stu-id="4d64b-160">type</span></span>                                        |
|             | <span data-ttu-id="4d64b-161">-isnot</span><span class="sxs-lookup"><span data-stu-id="4d64b-161">-isnot</span></span>       | <span data-ttu-id="4d64b-162">オブジェクトが同じでない場合に true を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-162">Returns true if the objects are not the same</span></span>|
|             |              | <span data-ttu-id="4d64b-163">type</span><span class="sxs-lookup"><span data-stu-id="4d64b-163">type</span></span>                                        |

<span data-ttu-id="4d64b-164">既定では、すべての比較演算子で大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-164">By default, all comparison operators are case-insensitive.</span></span> <span data-ttu-id="4d64b-165">大文字と小文字を区別する比較演算子を作成するには、演算子名の前にを付け `c` ます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-165">To make a comparison operator case-sensitive, precede the operator name with a `c`.</span></span> <span data-ttu-id="4d64b-166">たとえば、の大文字と小文字を区別するバージョン `-eq` はです `-ceq` 。</span><span class="sxs-lookup"><span data-stu-id="4d64b-166">For example, the case-sensitive version of `-eq` is `-ceq`.</span></span> <span data-ttu-id="4d64b-167">大文字小文字を区別しないようにするには、演算子の前にを付け `i` ます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-167">To make the case-insensitivity explicit, precede the operator with an `i`.</span></span> <span data-ttu-id="4d64b-168">たとえば、の明示的な大文字と小文字を区別しないバージョン `-eq` はです `-ieq` 。</span><span class="sxs-lookup"><span data-stu-id="4d64b-168">For example, the explicitly case-insensitive version of `-eq` is `-ieq`.</span></span>

<span data-ttu-id="4d64b-169">演算子への入力がスカラー値の場合、比較演算子はブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-169">When the input to an operator is a scalar value, comparison operators return a Boolean value.</span></span> <span data-ttu-id="4d64b-170">入力が値のコレクションである場合、比較演算子は一致する値を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-170">When the input is a collection of values, the comparison operators return any matching values.</span></span> <span data-ttu-id="4d64b-171">コレクションに一致するものがない場合、比較演算子は空の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-171">If there are no matches in a collection, comparison operators return an empty array.</span></span>

```powershell
PS> (1, 2 -eq 3).GetType().FullName
System.Object[]
```

<span data-ttu-id="4d64b-172">例外は、包含演算子、In 演算子、および型演算子で、常に **ブール** 値を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-172">The exceptions are the containment operators, the In operators, and the type operators, which always return a **Boolean** value.</span></span>

> [!NOTE]
> <span data-ttu-id="4d64b-173">値をと比較する必要がある場合は、 `$null` `$null` 比較の左側に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d64b-173">If you need to compare a value to `$null` you should put `$null` on the left-hand side of the comparison.</span></span> <span data-ttu-id="4d64b-174">`$null`**オブジェクト []** と比較すると、比較オブジェクトが配列であるため、結果は **False** になります。</span><span class="sxs-lookup"><span data-stu-id="4d64b-174">When you compare `$null` to an **Object[]** the result is **False** because the comparison object is an array.</span></span> <span data-ttu-id="4d64b-175">配列をと比較すると `$null` 、比較によって `$null` 配列に格納されているすべての値が除外されます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-175">When you compare an array to `$null`, the comparison filters out any `$null` values stored in the array.</span></span> <span data-ttu-id="4d64b-176">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-176">For example:</span></span>
>
> ```powershell
> PS> $null -ne $null, "hello"
> True
> PS> $null, "hello" -ne $null
> hello
> ```

### <a name="equality-operators"></a><span data-ttu-id="4d64b-177">等値演算子</span><span class="sxs-lookup"><span data-stu-id="4d64b-177">Equality Operators</span></span>

<span data-ttu-id="4d64b-178">等値演算子 ( `-eq` 、 `-ne` ) は、1つ以上の入力値が指定されたパターンと同じ場合に TRUE または一致する値を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-178">The equality operators (`-eq`, `-ne`) return a value of TRUE or the matches when one or more of the input values is identical to the specified pattern.</span></span> <span data-ttu-id="4d64b-179">パターン全体が値全体と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d64b-179">The entire pattern must match an entire value.</span></span>

<span data-ttu-id="4d64b-180">例:</span><span class="sxs-lookup"><span data-stu-id="4d64b-180">Example:</span></span>

#### <a name="-eq"></a><span data-ttu-id="4d64b-181">-eq</span><span class="sxs-lookup"><span data-stu-id="4d64b-181">-eq</span></span>

<span data-ttu-id="4d64b-182">説明: と等しい。</span><span class="sxs-lookup"><span data-stu-id="4d64b-182">Description: Equal to.</span></span> <span data-ttu-id="4d64b-183">には、同じ値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-183">Includes an identical value.</span></span>

<span data-ttu-id="4d64b-184">例:</span><span class="sxs-lookup"><span data-stu-id="4d64b-184">Example:</span></span>

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

#### <a name="-ne"></a><span data-ttu-id="4d64b-185">-ne</span><span class="sxs-lookup"><span data-stu-id="4d64b-185">-ne</span></span>

<span data-ttu-id="4d64b-186">説明: 等しくない。</span><span class="sxs-lookup"><span data-stu-id="4d64b-186">Description: Not equal to.</span></span> <span data-ttu-id="4d64b-187">に別の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4d64b-187">Includes a different value.</span></span>

<span data-ttu-id="4d64b-188">例:</span><span class="sxs-lookup"><span data-stu-id="4d64b-188">Example:</span></span>

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

#### <a name="-gt"></a><span data-ttu-id="4d64b-189">-gt</span><span class="sxs-lookup"><span data-stu-id="4d64b-189">-gt</span></span>

<span data-ttu-id="4d64b-190">説明: より大きい。</span><span class="sxs-lookup"><span data-stu-id="4d64b-190">Description: Greater-than.</span></span>

<span data-ttu-id="4d64b-191">例:</span><span class="sxs-lookup"><span data-stu-id="4d64b-191">Example:</span></span>

```powershell
PS> 8 -gt 6
True

PS> 7, 8, 9 -gt 8
9
```

> [!NOTE]
> <span data-ttu-id="4d64b-192">`>`他の多くのプログラミング言語では、大なり演算子と混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="4d64b-192">This should not to be confused with `>`, the greater-than operator in many other programming languages.</span></span> <span data-ttu-id="4d64b-193">PowerShell で `>` は、はリダイレクトに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-193">In PowerShell, `>` is used for redirection.</span></span> <span data-ttu-id="4d64b-194">詳細については、「 [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d64b-194">For more information, see [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span></span>

#### <a name="-ge"></a><span data-ttu-id="4d64b-195">-ge</span><span class="sxs-lookup"><span data-stu-id="4d64b-195">-ge</span></span>

<span data-ttu-id="4d64b-196">説明: より大きいか等しい。</span><span class="sxs-lookup"><span data-stu-id="4d64b-196">Description: Greater-than or equal to.</span></span>

<span data-ttu-id="4d64b-197">例:</span><span class="sxs-lookup"><span data-stu-id="4d64b-197">Example:</span></span>

```powershell
PS> 8 -ge 8
True

PS> 7, 8, 9 -ge 8
8
9
```

#### <a name="-lt"></a><span data-ttu-id="4d64b-198">-lt</span><span class="sxs-lookup"><span data-stu-id="4d64b-198">-lt</span></span>

<span data-ttu-id="4d64b-199">説明: より小さい。</span><span class="sxs-lookup"><span data-stu-id="4d64b-199">Description: Less-than.</span></span>

<span data-ttu-id="4d64b-200">例:</span><span class="sxs-lookup"><span data-stu-id="4d64b-200">Example:</span></span>

```powershell

PS> 8 -lt 6
False

PS> 7, 8, 9 -lt 8
7
```

#### <a name="-le"></a><span data-ttu-id="4d64b-201">-le</span><span class="sxs-lookup"><span data-stu-id="4d64b-201">-le</span></span>

<span data-ttu-id="4d64b-202">説明: 次の値より小さいか等しい。</span><span class="sxs-lookup"><span data-stu-id="4d64b-202">Description: Less-than or equal to.</span></span>

<span data-ttu-id="4d64b-203">例:</span><span class="sxs-lookup"><span data-stu-id="4d64b-203">Example:</span></span>

```powershell
PS> 6 -le 8
True

PS> 7, 8, 9 -le 8
7
8
```

### <a name="matching-operators"></a><span data-ttu-id="4d64b-204">照合演算子</span><span class="sxs-lookup"><span data-stu-id="4d64b-204">Matching Operators</span></span>

<span data-ttu-id="4d64b-205">Like 演算子 ( `-like` および) は、 `-notlike` ワイルドカード式を使用して、指定したパターンに一致するか一致しない要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-205">The like operators (`-like` and `-notlike`) find elements that match or do not match a specified pattern using wildcard expressions.</span></span>

<span data-ttu-id="4d64b-206">の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4d64b-206">The syntax is:</span></span>

```powershell
<string[]> -like <wildcard-expression>
<string[]> -notlike <wildcard-expression>
```

<span data-ttu-id="4d64b-207">一致演算子 ( `-match` および) は、 `-notmatch` 正規表現を使用して、指定したパターンに一致するか一致しない要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-207">The match operators (`-match` and `-notmatch`) find elements that match or do not match a specified pattern using regular expressions.</span></span>

<span data-ttu-id="4d64b-208">一致演算子は、 `$Matches` 演算子への入力 (左側の引数) が単一のスカラーオブジェクトである場合に、自動変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-208">The match operators populate the `$Matches` automatic variable when the input (the left-side argument) to the operator is a single scalar object.</span></span> <span data-ttu-id="4d64b-209">入力がスカラーの場合、 `-match` および `-notmatch` 演算子はブール値を返し、 `$Matches` 自動変数の値を引数の一致するコンポーネントに設定します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-209">When the input is scalar, the `-match` and `-notmatch` operators return a Boolean value and set the value of the `$Matches` automatic variable to the matched components of the argument.</span></span>

<span data-ttu-id="4d64b-210">の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4d64b-210">The syntax is:</span></span>

```powershell
<string[]> -match <regular-expression>
<string[]> -notmatch <regular-expression>
```

#### <a name="-like"></a><span data-ttu-id="4d64b-211">-like</span><span class="sxs-lookup"><span data-stu-id="4d64b-211">-like</span></span>

<span data-ttu-id="4d64b-212">説明: ワイルドカード文字 () を使用して一致し \* ます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-212">Description: Match using the wildcard character (\*).</span></span>

<span data-ttu-id="4d64b-213">例:</span><span class="sxs-lookup"><span data-stu-id="4d64b-213">Example:</span></span>

```powershell
PS> "PowerShell" -like "*shell"
True

PS> "PowerShell", "Server" -like "*shell"
PowerShell
```

#### <a name="-notlike"></a><span data-ttu-id="4d64b-214">-notlike</span><span class="sxs-lookup"><span data-stu-id="4d64b-214">-notlike</span></span>

<span data-ttu-id="4d64b-215">説明: は、ワイルドカード文字 () を使用して一致しません \* 。</span><span class="sxs-lookup"><span data-stu-id="4d64b-215">Description: Does not match using the wildcard character (\*).</span></span>

<span data-ttu-id="4d64b-216">例:</span><span class="sxs-lookup"><span data-stu-id="4d64b-216">Example:</span></span>

```powershell
PS> "PowerShell" -notlike "*shell"
False

PS> "PowerShell", "Server" -notlike "*shell"
Server
```

### <a name="-match"></a><span data-ttu-id="4d64b-217">-match</span><span class="sxs-lookup"><span data-stu-id="4d64b-217">-match</span></span>

<span data-ttu-id="4d64b-218">説明: 正規表現を使用して文字列に一致します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-218">Description: Matches a string using regular expressions.</span></span> <span data-ttu-id="4d64b-219">入力がスカラーの場合は、自動変数が設定され `$Matches` ます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-219">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="4d64b-220">入力がコレクションの場合、演算子 `-match` と演算子は、 `-notmatch` そのコレクションの一致するメンバーを返しますが、演算子は変数に値を設定しません `$Matches` 。</span><span class="sxs-lookup"><span data-stu-id="4d64b-220">If the input is a collection, the `-match` and `-notmatch` operators return the matching members of that collection, but the operator does not populate the `$Matches` variable.</span></span>

<span data-ttu-id="4d64b-221">たとえば、次のコマンドは、文字列のコレクションを演算子に送信し `-match` ます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-221">For example, the following command submits a collection of strings to the `-match` operator.</span></span> <span data-ttu-id="4d64b-222">演算子は、 `-match` 一致するコレクション内の項目を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-222">The `-match` operator returns the items in the collection that match.</span></span> <span data-ttu-id="4d64b-223">自動変数は設定されません `$Matches` 。</span><span class="sxs-lookup"><span data-stu-id="4d64b-223">It does not populate the `$Matches` automatic variable.</span></span>

```powershell
PS> "Sunday", "Monday", "Tuesday" -match "sun"
Sunday

PS> $Matches
PS>
```

<span data-ttu-id="4d64b-224">これに対して、次のコマンドは、1つの文字列を演算子に送信し `-match` ます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-224">In contrast, the following command submits a single string to the `-match` operator.</span></span> <span data-ttu-id="4d64b-225">`-match`演算子はブール値を返し、自動変数を設定し `$Matches` ます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-225">The `-match` operator returns a Boolean value and populates the `$Matches` automatic variable.</span></span> <span data-ttu-id="4d64b-226">`$Matches`自動変数は **ハッシュテーブル** です。</span><span class="sxs-lookup"><span data-stu-id="4d64b-226">The `$Matches` automatic variable is a **Hashtable**.</span></span> <span data-ttu-id="4d64b-227">グループ化またはキャプチャが使用されていない場合は、1つのキーだけが設定されます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-227">If no grouping or capturing is used, only one key is populated.</span></span>
<span data-ttu-id="4d64b-228">キーは、 `0` 一致したすべてのテキストを表します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-228">The `0` key represents all text that was matched.</span></span> <span data-ttu-id="4d64b-229">正規表現を使用したグループ化とキャプチャの詳細については、「 [about_Regular_Expressions](about_Regular_Expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d64b-229">For more information about grouping and capturing using regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

```powershell
PS> "Sunday" -match "sun"
True

PS> $Matches

Name                           Value
----                           -----
0                              Sun
```

<span data-ttu-id="4d64b-230">ハッシュテーブルには、一致するパターンが最初に出現するだけが含まれていることに注意して `$Matches` ください。</span><span class="sxs-lookup"><span data-stu-id="4d64b-230">It is important to note that the `$Matches` hashtable will only contain the first occurrence of any matching pattern.</span></span>

```powershell
PS> "Banana" -match "na"
True

PS> $Matches

Name                           Value
----                           -----
0                              na
```

> [!IMPORTANT]
> <span data-ttu-id="4d64b-231">`0`キーは **整数** です。</span><span class="sxs-lookup"><span data-stu-id="4d64b-231">The `0` key is an **Integer**.</span></span> <span data-ttu-id="4d64b-232">任意の **ハッシュテーブル** メソッドを使用して、格納されている値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-232">You can use any **Hashtable** method to access the value stored.</span></span>
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

<span data-ttu-id="4d64b-233">演算子は、 `-notmatch` `$Matches` 入力がスカラーのときに自動変数を設定し、結果が False であること、つまり一致が検出されたときにその変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-233">The `-notmatch` operator populates the `$Matches` automatic variable when the input is scalar and the result is False, that it, when it detects a match.</span></span>

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

#### <a name="-notmatch"></a><span data-ttu-id="4d64b-234">-notmatch</span><span class="sxs-lookup"><span data-stu-id="4d64b-234">-notmatch</span></span>

<span data-ttu-id="4d64b-235">説明: が文字列と一致しません。</span><span class="sxs-lookup"><span data-stu-id="4d64b-235">Description: Does not match a string.</span></span> <span data-ttu-id="4d64b-236">正規表現を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-236">Uses regular expressions.</span></span> <span data-ttu-id="4d64b-237">入力がスカラーの場合は、自動変数が設定され `$Matches` ます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-237">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="4d64b-238">例:</span><span class="sxs-lookup"><span data-stu-id="4d64b-238">Example:</span></span>

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

### <a name="containment-operators"></a><span data-ttu-id="4d64b-239">含有演算子</span><span class="sxs-lookup"><span data-stu-id="4d64b-239">Containment Operators</span></span>

<span data-ttu-id="4d64b-240">含有演算子 ( `-contains` と `-notcontains` ) は、等値演算子に似ています。</span><span class="sxs-lookup"><span data-stu-id="4d64b-240">The containment operators (`-contains` and `-notcontains`) are similar to the equality operators.</span></span> <span data-ttu-id="4d64b-241">ただし、入力がコレクションの場合でも、コンテインメント演算子は常にブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-241">However, the containment operators always return a Boolean value, even when the input is a collection.</span></span>

<span data-ttu-id="4d64b-242">また、等値演算子とは異なり、コンテインメント演算子は、最初の一致を検出するとすぐに値を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-242">Also, unlike the equality operators, the containment operators return a value as soon as they detect the first match.</span></span> <span data-ttu-id="4d64b-243">等値演算子は、すべての入力を評価し、コレクション内のすべての一致を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-243">The equality operators evaluate all input and then return all the matches in the collection.</span></span>

#### <a name="-contains"></a><span data-ttu-id="4d64b-244">-contains</span><span class="sxs-lookup"><span data-stu-id="4d64b-244">-contains</span></span>

<span data-ttu-id="4d64b-245">説明: コンテインメント演算子。</span><span class="sxs-lookup"><span data-stu-id="4d64b-245">Description: Containment operator.</span></span> <span data-ttu-id="4d64b-246">参照値のコレクションに1つのテスト値が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-246">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="4d64b-247">常にブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-247">Always returns a Boolean value.</span></span> <span data-ttu-id="4d64b-248">テスト値が参照値の少なくとも1つと完全に一致する場合にのみ TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-248">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="4d64b-249">テスト値がコレクションの場合、Contains 演算子は参照の等価性を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-249">When the test value is a collection, the Contains operator uses reference equality.</span></span> <span data-ttu-id="4d64b-250">参照値の1つがテスト値オブジェクトの同じインスタンスである場合にのみ、TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-250">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="4d64b-251">非常に大きなコレクションでは、 `-contains` 演算子は equal to 演算子よりも結果を迅速に返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-251">In a very large collection, the `-contains` operator returns results quicker than the equal to operator.</span></span>

<span data-ttu-id="4d64b-252">構文:</span><span class="sxs-lookup"><span data-stu-id="4d64b-252">Syntax:</span></span>

`<Reference-values> -contains <Test-value>`

<span data-ttu-id="4d64b-253">例:</span><span class="sxs-lookup"><span data-stu-id="4d64b-253">Examples:</span></span>

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

#### <a name="-notcontains"></a><span data-ttu-id="4d64b-254">-notcontains</span><span class="sxs-lookup"><span data-stu-id="4d64b-254">-notcontains</span></span>

<span data-ttu-id="4d64b-255">説明: コンテインメント演算子。</span><span class="sxs-lookup"><span data-stu-id="4d64b-255">Description: Containment operator.</span></span> <span data-ttu-id="4d64b-256">参照値のコレクションに1つのテスト値が含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-256">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="4d64b-257">常にブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-257">Always returns a Boolean value.</span></span> <span data-ttu-id="4d64b-258">テスト値が参照値の少なくとも1つと完全に一致しない場合に TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-258">Returns TRUE when the test value is not an exact matches for at least one of the reference values.</span></span>

<span data-ttu-id="4d64b-259">テスト値がコレクションの場合、NotContains 演算子は参照の等価性を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-259">When the test value is a collection, the NotContains operator uses reference equality.</span></span>

<span data-ttu-id="4d64b-260">構文:</span><span class="sxs-lookup"><span data-stu-id="4d64b-260">Syntax:</span></span>

`<Reference-values> -notcontains <Test-value>`

<span data-ttu-id="4d64b-261">例:</span><span class="sxs-lookup"><span data-stu-id="4d64b-261">Examples:</span></span>

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

#### <a name="-in"></a><span data-ttu-id="4d64b-262">-in</span><span class="sxs-lookup"><span data-stu-id="4d64b-262">-in</span></span>

<span data-ttu-id="4d64b-263">説明: In 演算子。</span><span class="sxs-lookup"><span data-stu-id="4d64b-263">Description: In operator.</span></span> <span data-ttu-id="4d64b-264">テスト値が参照値のコレクションに表示されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-264">Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="4d64b-265">常にブール値として返されます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-265">Always return as Boolean value.</span></span> <span data-ttu-id="4d64b-266">テスト値が参照値の少なくとも1つと完全に一致する場合にのみ TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-266">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="4d64b-267">テスト値がコレクションの場合、In 演算子は参照の等価性を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-267">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="4d64b-268">参照値の1つがテスト値オブジェクトの同じインスタンスである場合にのみ、TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-268">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="4d64b-269">演算子は、 `-in` PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4d64b-269">The `-in` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="4d64b-270">構文:</span><span class="sxs-lookup"><span data-stu-id="4d64b-270">Syntax:</span></span>

`<Test-value> -in <Reference-values>`

<span data-ttu-id="4d64b-271">例:</span><span class="sxs-lookup"><span data-stu-id="4d64b-271">Examples:</span></span>

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

#### <a name="-notin"></a><span data-ttu-id="4d64b-272">-notin</span><span class="sxs-lookup"><span data-stu-id="4d64b-272">-notin</span></span>

<span data-ttu-id="4d64b-273">Description: テスト値が参照値のコレクションに表示されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-273">Description: Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="4d64b-274">常にブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-274">Always returns a Boolean value.</span></span> <span data-ttu-id="4d64b-275">テスト値が参照値の少なくとも1つと完全に一致しない場合に TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-275">Returns TRUE when the test value is not an exact match for at least one of the reference values.</span></span>

<span data-ttu-id="4d64b-276">テスト値がコレクションの場合、In 演算子は参照の等価性を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-276">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="4d64b-277">参照値の1つがテスト値オブジェクトの同じインスタンスである場合にのみ、TRUE を返します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-277">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="4d64b-278">演算子は、 `-notin` PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4d64b-278">The `-notin` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="4d64b-279">構文:</span><span class="sxs-lookup"><span data-stu-id="4d64b-279">Syntax:</span></span>

`<Test-value> -notin <Reference-values>`

<span data-ttu-id="4d64b-280">例:</span><span class="sxs-lookup"><span data-stu-id="4d64b-280">Examples:</span></span>

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

### <a name="replacement-operator"></a><span data-ttu-id="4d64b-281">置換演算子</span><span class="sxs-lookup"><span data-stu-id="4d64b-281">Replacement Operator</span></span>

<span data-ttu-id="4d64b-282">演算子は、 `-replace` 値のすべてまたは一部を、正規表現を使用して、指定された値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-282">The `-replace` operator replaces all or part of a value with the specified value using regular expressions.</span></span> <span data-ttu-id="4d64b-283">`-replace`演算子は、ファイル名の変更など、多くの管理タスクに使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-283">You can use the `-replace` operator for many administrative tasks, such as renaming files.</span></span> <span data-ttu-id="4d64b-284">たとえば、次のコマンドは、すべての .txt ファイルのファイル名拡張子を .log に変更します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-284">For example, the following command changes the file name extensions of all .txt files to .log:</span></span>

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

<span data-ttu-id="4d64b-285">演算子の構文は次のようになります。プレースホルダーは、置換する `-replace` 文字を表し、プレースホルダーはそれらを `<original>` `<substitute>` 置き換える文字を表します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-285">The syntax of the `-replace` operator is as follows, where the `<original>` placeholder represents the characters to be replaced, and the `<substitute>` placeholder represents the characters that will replace them:</span></span>

`<input> <operator> <original>, <substitute>`

<span data-ttu-id="4d64b-286">既定では、 `-replace` 演算子は大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="4d64b-286">By default, the `-replace` operator is case-insensitive.</span></span> <span data-ttu-id="4d64b-287">大文字と小文字を区別するには、を使用 `-creplace` します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-287">To make it case sensitive, use `-creplace`.</span></span> <span data-ttu-id="4d64b-288">大文字と小文字を区別しないようにするには、を使用 `-ireplace` します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-288">To make it explicitly case-insensitive, use `-ireplace`.</span></span>

<span data-ttu-id="4d64b-289">次の例を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="4d64b-289">Consider the following examples:</span></span>

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

<span data-ttu-id="4d64b-290">また、正規表現を使用して、キャプチャグループと置換を使用してテキストを動的に置換することもできます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-290">It is also possible to use regular expressions to dynamically replace text using capturing groups, and substitutions.</span></span> <span data-ttu-id="4d64b-291">詳細については、「 [about_Regular_Expressions](about_Regular_Expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d64b-291">For more information, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

### <a name="scriptblock-substitutions"></a><span data-ttu-id="4d64b-292">ScriptBlock の置換</span><span class="sxs-lookup"><span data-stu-id="4d64b-292">ScriptBlock substitutions</span></span>

<span data-ttu-id="4d64b-293">PowerShell 6 以降では、 *代替* テキストに **ScriptBlock** 引数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-293">Beginning in PowerShell 6, you can use a **ScriptBlock** argument for the *Substitution* text.</span></span> <span data-ttu-id="4d64b-294">**ScriptBlock** は、 *入力* 文字列で見つかった一致ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-294">The **ScriptBlock** will execute for each match found in the *input* string.</span></span>

<span data-ttu-id="4d64b-295">**ScriptBlock** 内では、自動変数を使用し `$_` て、現在の **system.text.regularexpressions.regexoptions** オブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="4d64b-295">Within the **ScriptBlock** , use the `$_` automatic variable to refer to the current **System.Text.RegularExpressions.Match** object.</span></span> <span data-ttu-id="4d64b-296">**Match** オブジェクトを使用すると、置き換えられる現在の入力テキストに加えて、その他の有用な情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-296">The **Match** object gives you access to the current input text being replaced, as well as other useful information.</span></span>

<span data-ttu-id="4d64b-297">この例では、3つの10進数の各シーケンスを、それと等価な文字に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-297">This example replaces each sequence of three decimals with the character equivalent.</span></span> <span data-ttu-id="4d64b-298">**ScriptBlock** は、置換する必要がある3つの10進数のセットごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-298">The **ScriptBlock** is run for each set of three decimals that needs to be replaced.</span></span>

```powershell
PS> "072101108108111" -replace "\d{3}", {[char][int]$_.Value}
Hello
```

### <a name="type-comparison"></a><span data-ttu-id="4d64b-299">型の比較</span><span class="sxs-lookup"><span data-stu-id="4d64b-299">Type comparison</span></span>

<span data-ttu-id="4d64b-300">型の比較演算子 ( `-is` と `-isnot` ) は、オブジェクトが特定の型であるかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4d64b-300">The type comparison operators (`-is` and `-isnot`) are used to determine if an object is a specific type.</span></span>

#### <a name="-is"></a><span data-ttu-id="4d64b-301">-が</span><span class="sxs-lookup"><span data-stu-id="4d64b-301">-is</span></span>

<span data-ttu-id="4d64b-302">構文:</span><span class="sxs-lookup"><span data-stu-id="4d64b-302">Syntax:</span></span>

`<object> -is <type reference>`

<span data-ttu-id="4d64b-303">例:</span><span class="sxs-lookup"><span data-stu-id="4d64b-303">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -is [int]
True
PS> $a -is $b.GetType()
False
```

#### <a name="-isnot"></a><span data-ttu-id="4d64b-304">-isnot</span><span class="sxs-lookup"><span data-stu-id="4d64b-304">-isnot</span></span>

<span data-ttu-id="4d64b-305">構文:</span><span class="sxs-lookup"><span data-stu-id="4d64b-305">Syntax:</span></span>

`<object> -isnot <type reference>`

<span data-ttu-id="4d64b-306">例:</span><span class="sxs-lookup"><span data-stu-id="4d64b-306">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -isnot $b.GetType()
True
PS> $b -isnot [int]
True
```

## <a name="see-also"></a><span data-ttu-id="4d64b-307">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d64b-307">SEE ALSO</span></span>

- [<span data-ttu-id="4d64b-308">about_Operators</span><span class="sxs-lookup"><span data-stu-id="4d64b-308">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="4d64b-309">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="4d64b-309">about_Regular_Expressions</span></span>](about_Regular_Expressions.md)
- [<span data-ttu-id="4d64b-310">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="4d64b-310">about_Wildcards</span></span>](about_Wildcards.md)
- [<span data-ttu-id="4d64b-311">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="4d64b-311">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [<span data-ttu-id="4d64b-312">Foreach-オブジェクト</span><span class="sxs-lookup"><span data-stu-id="4d64b-312">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [<span data-ttu-id="4d64b-313">Where-Object</span><span class="sxs-lookup"><span data-stu-id="4d64b-313">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)