---
description: PowerShell の値を比較する演算子について説明します。
Locale: en-US
ms.date: 01/20/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: 2ccd631083ddc06d25f2c3b4733223cca2e89d44
ms.sourcegitcommit: 77f6225ab0c8ea9faa1fe46b2ea15c178ec170e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2021
ms.locfileid: "100500248"
---
# <a name="about-comparison-operators"></a><span data-ttu-id="27251-103">比較演算子について</span><span class="sxs-lookup"><span data-stu-id="27251-103">About Comparison Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="27251-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="27251-104">Short description</span></span>

<span data-ttu-id="27251-105">PowerShell の比較演算子は、2つの値を比較するか、コレクションの要素を入力値に対してフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="27251-105">The comparison operators in PowerShell can either compare two values or filter elements of a collection against an input value.</span></span>

## <a name="long-description"></a><span data-ttu-id="27251-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="27251-106">Long description</span></span>

<span data-ttu-id="27251-107">比較演算子を使用すると、値を比較したり、指定したパターンに一致する値を検索したりできます。</span><span class="sxs-lookup"><span data-stu-id="27251-107">Comparison operators let you compare values or finding values that match specified patterns.</span></span> <span data-ttu-id="27251-108">PowerShell には、次の比較演算子が含まれています。</span><span class="sxs-lookup"><span data-stu-id="27251-108">PowerShell includes the following comparison operators:</span></span>

|    <span data-ttu-id="27251-109">型</span><span class="sxs-lookup"><span data-stu-id="27251-109">Type</span></span>     |   <span data-ttu-id="27251-110">演算子</span><span class="sxs-lookup"><span data-stu-id="27251-110">Operator</span></span>   |              <span data-ttu-id="27251-111">比較テスト</span><span class="sxs-lookup"><span data-stu-id="27251-111">Comparison test</span></span>              |
| ----------- | ------------ | ----------------------------------------- |
| <span data-ttu-id="27251-112">等価比較</span><span class="sxs-lookup"><span data-stu-id="27251-112">Equality</span></span>    | <span data-ttu-id="27251-113">-eq</span><span class="sxs-lookup"><span data-stu-id="27251-113">-eq</span></span>          | <span data-ttu-id="27251-114">equals</span><span class="sxs-lookup"><span data-stu-id="27251-114">equals</span></span>                                    |
|             | <span data-ttu-id="27251-115">-ne</span><span class="sxs-lookup"><span data-stu-id="27251-115">-ne</span></span>          | <span data-ttu-id="27251-116">等しくない</span><span class="sxs-lookup"><span data-stu-id="27251-116">not equals</span></span>                                |
|             | <span data-ttu-id="27251-117">-gt</span><span class="sxs-lookup"><span data-stu-id="27251-117">-gt</span></span>          | <span data-ttu-id="27251-118">より大きい</span><span class="sxs-lookup"><span data-stu-id="27251-118">greater than</span></span>                              |
|             | <span data-ttu-id="27251-119">-ge</span><span class="sxs-lookup"><span data-stu-id="27251-119">-ge</span></span>          | <span data-ttu-id="27251-120">以上</span><span class="sxs-lookup"><span data-stu-id="27251-120">greater than or equal</span></span>                     |
|             | <span data-ttu-id="27251-121">-lt</span><span class="sxs-lookup"><span data-stu-id="27251-121">-lt</span></span>          | <span data-ttu-id="27251-122">次の値未満</span><span class="sxs-lookup"><span data-stu-id="27251-122">less than</span></span>                                 |
|             | <span data-ttu-id="27251-123">-le</span><span class="sxs-lookup"><span data-stu-id="27251-123">-le</span></span>          | <span data-ttu-id="27251-124">以下</span><span class="sxs-lookup"><span data-stu-id="27251-124">less than or equal</span></span>                        |
| <span data-ttu-id="27251-125">Matching</span><span class="sxs-lookup"><span data-stu-id="27251-125">Matching</span></span>    | <span data-ttu-id="27251-126">-like</span><span class="sxs-lookup"><span data-stu-id="27251-126">-like</span></span>        | <span data-ttu-id="27251-127">ワイルドカードパターンに一致する文字列</span><span class="sxs-lookup"><span data-stu-id="27251-127">string matches wildcard pattern</span></span>           |
|             | <span data-ttu-id="27251-128">-notlike</span><span class="sxs-lookup"><span data-stu-id="27251-128">-notlike</span></span>     | <span data-ttu-id="27251-129">文字列がワイルドカードパターンと一致しません</span><span class="sxs-lookup"><span data-stu-id="27251-129">string does not match wildcard pattern</span></span>    |
|             | <span data-ttu-id="27251-130">-match</span><span class="sxs-lookup"><span data-stu-id="27251-130">-match</span></span>       | <span data-ttu-id="27251-131">文字列が regex パターンと一致します</span><span class="sxs-lookup"><span data-stu-id="27251-131">string matches regex pattern</span></span>              |
|             | <span data-ttu-id="27251-132">-notmatch</span><span class="sxs-lookup"><span data-stu-id="27251-132">-notmatch</span></span>    | <span data-ttu-id="27251-133">文字列が regex パターンと一致しません</span><span class="sxs-lookup"><span data-stu-id="27251-133">string does not match regex pattern</span></span>       |
| <span data-ttu-id="27251-134">代替</span><span class="sxs-lookup"><span data-stu-id="27251-134">Replacement</span></span> | <span data-ttu-id="27251-135">-replace</span><span class="sxs-lookup"><span data-stu-id="27251-135">-replace</span></span>     | <span data-ttu-id="27251-136">正規表現パターンに一致する文字列を置換します</span><span class="sxs-lookup"><span data-stu-id="27251-136">replaces strings matching a regex pattern</span></span> |
| <span data-ttu-id="27251-137">Containment</span><span class="sxs-lookup"><span data-stu-id="27251-137">Containment</span></span> | <span data-ttu-id="27251-138">-contains</span><span class="sxs-lookup"><span data-stu-id="27251-138">-contains</span></span>    | <span data-ttu-id="27251-139">コレクションに値が含まれています</span><span class="sxs-lookup"><span data-stu-id="27251-139">collection contains a value</span></span>               |
|             | <span data-ttu-id="27251-140">-notcontains</span><span class="sxs-lookup"><span data-stu-id="27251-140">-notcontains</span></span> | <span data-ttu-id="27251-141">コレクションに値が含まれていません</span><span class="sxs-lookup"><span data-stu-id="27251-141">collection does not contain a value</span></span>       |
|             | <span data-ttu-id="27251-142">-in</span><span class="sxs-lookup"><span data-stu-id="27251-142">-in</span></span>          | <span data-ttu-id="27251-143">値がコレクション内にあります</span><span class="sxs-lookup"><span data-stu-id="27251-143">value is in a collection</span></span>                  |
|             | <span data-ttu-id="27251-144">-notin</span><span class="sxs-lookup"><span data-stu-id="27251-144">-notin</span></span>       | <span data-ttu-id="27251-145">値がコレクション内にありません</span><span class="sxs-lookup"><span data-stu-id="27251-145">value is not in a collection</span></span>              |
| <span data-ttu-id="27251-146">Type</span><span class="sxs-lookup"><span data-stu-id="27251-146">Type</span></span>        | <span data-ttu-id="27251-147">-が</span><span class="sxs-lookup"><span data-stu-id="27251-147">-is</span></span>          | <span data-ttu-id="27251-148">両方のオブジェクトが同じ型です。</span><span class="sxs-lookup"><span data-stu-id="27251-148">both objects are the same type</span></span>            |
|             | <span data-ttu-id="27251-149">-isnot</span><span class="sxs-lookup"><span data-stu-id="27251-149">-isnot</span></span>       | <span data-ttu-id="27251-150">オブジェクトが同じ型ではありません</span><span class="sxs-lookup"><span data-stu-id="27251-150">the objects are not the same type</span></span>         |

## <a name="common-features"></a><span data-ttu-id="27251-151">共通機能</span><span class="sxs-lookup"><span data-stu-id="27251-151">Common features</span></span>

<span data-ttu-id="27251-152">既定では、すべての比較演算子で大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="27251-152">By default, all comparison operators are case-insensitive.</span></span> <span data-ttu-id="27251-153">大文字と小文字を区別する比較演算子を作成するには、の後にを追加し `c` `-` ます。</span><span class="sxs-lookup"><span data-stu-id="27251-153">To make a comparison operator case-sensitive, add a `c` after the `-`.</span></span> <span data-ttu-id="27251-154">たとえば、 `-ceq` は、の大文字と小文字を区別するバージョンです `-eq` 。</span><span class="sxs-lookup"><span data-stu-id="27251-154">For example, `-ceq` is the case-sensitive version of `-eq`.</span></span> <span data-ttu-id="27251-155">大文字と小文字を区別しないようにするには、の前にを追加し `i` `-` ます。</span><span class="sxs-lookup"><span data-stu-id="27251-155">To make the case-insensitivity explicit, add an `i` before `-`.</span></span> <span data-ttu-id="27251-156">たとえば、 `-ieq` は、の大文字と小文字を区別しない明示的なバージョンです `-eq` 。</span><span class="sxs-lookup"><span data-stu-id="27251-156">For example, `-ieq` is the explicitly case-insensitive version of `-eq`.</span></span>

<span data-ttu-id="27251-157">演算子の入力がスカラー値の場合、演算子は **ブール** 値を返します。</span><span class="sxs-lookup"><span data-stu-id="27251-157">When the input of an operator is a scalar value, the operator returns a **Boolean** value.</span></span> <span data-ttu-id="27251-158">入力がコレクションの場合、演算子は、式の右辺の値に一致するコレクションの要素を返します。</span><span class="sxs-lookup"><span data-stu-id="27251-158">When the input is a collection, the operator returns the elements of the collection that match the right-hand value of the expression.</span></span>
<span data-ttu-id="27251-159">コレクション内に一致するものがない場合、比較演算子は空の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="27251-159">If there are no matches in the collection, comparison operators return an empty array.</span></span> <span data-ttu-id="27251-160">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="27251-160">For example:</span></span>

```powershell
$a = (1, 2 -eq 3)
$a.GetType().Name
$a.Count
```

```output
Object[]
0
```

<span data-ttu-id="27251-161">次のようにいくつかの例外があります。</span><span class="sxs-lookup"><span data-stu-id="27251-161">There are a few exceptions:</span></span>

- <span data-ttu-id="27251-162">含有演算子と型演算子は、常に **ブール** 値を返します。</span><span class="sxs-lookup"><span data-stu-id="27251-162">The containment and type operators always return a **Boolean** value</span></span>
- <span data-ttu-id="27251-163">演算子は、 `-replace` 置換結果を返します。</span><span class="sxs-lookup"><span data-stu-id="27251-163">The `-replace` operator returns the replacement result</span></span>
- <span data-ttu-id="27251-164">`-match`And `-notmatch` 演算子も `$Matches` 自動変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="27251-164">The `-match` and `-notmatch` operators also populate the `$Matches` automatic variable</span></span>

## <a name="equality-operators"></a><span data-ttu-id="27251-165">等値演算子</span><span class="sxs-lookup"><span data-stu-id="27251-165">Equality operators</span></span>

### <a name="-eq-and--ne"></a><span data-ttu-id="27251-166">-eq と -ne</span><span class="sxs-lookup"><span data-stu-id="27251-166">-eq and -ne</span></span>

<span data-ttu-id="27251-167">左辺がスカラーの場合、 `-eq` 右辺が完全に一致する場合は **True** を返し、それ以外の場合は False を返し `-eq` ます。 </span><span class="sxs-lookup"><span data-stu-id="27251-167">When the left-hand side is scalar, `-eq` returns **True** if the right-hand side is an exact match, otherwise, `-eq` returns **False**.</span></span> <span data-ttu-id="27251-168">`-ne` は逆になります。両辺が一致する場合は **False** を返します。それ以外の場合は `-ne` True を返します。</span><span class="sxs-lookup"><span data-stu-id="27251-168">`-ne` does the opposite; it returns **False** when both sides match; otherwise, `-ne` returns True.</span></span>

<span data-ttu-id="27251-169">例:</span><span class="sxs-lookup"><span data-stu-id="27251-169">Example:</span></span>

```powershell
2 -eq 2                 # Output: True
2 -eq 3                 # Output: False
"abc" -eq "abc"         # Output: True
"abc" -eq "abc", "def"  # Output: False
"abc" -ne "def"         # Output: True
"abc" -ne "abc"         # Output: False
"abc" -ne "abc", "def"  # Output: True
```

<span data-ttu-id="27251-170">左側がコレクションの場合は、 `-eq` 右側に一致するメンバーを返し、 `-ne` フィルターで除外します。</span><span class="sxs-lookup"><span data-stu-id="27251-170">When the left-hand side is a collection, `-eq` returns those members that match the right-hand side, while `-ne` filters them out.</span></span>

<span data-ttu-id="27251-171">例:</span><span class="sxs-lookup"><span data-stu-id="27251-171">Example:</span></span>

```powershell
1,2,3 -eq 2             # Output: 2
"abc", "def" -eq "abc"  # Output: abc
"abc", "def" -ne "abc"  # Output: def
```

<span data-ttu-id="27251-172">これらの演算子は、コレクションのすべての要素を処理します。</span><span class="sxs-lookup"><span data-stu-id="27251-172">These operators process all elements of the collection.</span></span> <span data-ttu-id="27251-173">例:</span><span class="sxs-lookup"><span data-stu-id="27251-173">Example:</span></span>

```powershell
"zzz", "def", "zzz" -eq "zzz"
```

```output
zzz
zzz
```

<span data-ttu-id="27251-174">等値演算子は、スカラーまたはコレクションだけでなく、任意の2つのオブジェクトを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="27251-174">The equality operators accept any two objects, not just a scalar or collection.</span></span>
<span data-ttu-id="27251-175">ただし、比較結果はエンドユーザーにとって意味があるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="27251-175">But the comparison result is not guaranteed to be meaningful for the end-user.</span></span>
<span data-ttu-id="27251-176">次の例は、この問題を示しています。</span><span class="sxs-lookup"><span data-stu-id="27251-176">The following example demonstrates the issue.</span></span>

```powershell
class MyFileInfoSet {
    [String]$File
    [Int64]$Size
}
$a = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$b = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$a -eq $b
```

```Output
False
```

<span data-ttu-id="27251-177">この例では、同一のプロパティを持つ2つのオブジェクトを作成しました。</span><span class="sxs-lookup"><span data-stu-id="27251-177">In this example, we created two objects with identical properties.</span></span> <span data-ttu-id="27251-178">ただし、等価テストの結果は、異なるオブジェクトであるため **False** になります。</span><span class="sxs-lookup"><span data-stu-id="27251-178">Yet, the equality test result is **False** because they are different objects.</span></span> <span data-ttu-id="27251-179">同等のクラスを作成するには、クラスに[IEquatable \<T> ][2]を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27251-179">To create comparable classes, you need to implement [System.IEquatable\<T>][2] in your class.</span></span> <span data-ttu-id="27251-180">次の例は、 [IEquatable \<T>][2]を実装し、**ファイル** と **サイズ** の2つのプロパティを持つ、 **myfileinfoset** クラスの部分実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="27251-180">The following example demonstrates the partial implementation of a **MyFileInfoSet** class that implements [System.IEquatable\<T>][2] and has two properties, **File** and **Size**.</span></span> <span data-ttu-id="27251-181">`Equals()`2 つの **Myfileinfoset** オブジェクトの File プロパティと Size プロパティが同じである場合、メソッドは True を返します。</span><span class="sxs-lookup"><span data-stu-id="27251-181">The `Equals()` method returns True if the File and Size properties of two **MyFileInfoSet** objects are the same.</span></span>

```powershell
class MyFileInfoSet : System.IEquatable[Object] {
    [String]$File
    [Int64]$Size

    [bool] Equals([Object] $obj) {
        return ($this.File -eq $obj.File) -and ($this.Size -eq $obj.Size)
    }
}
$a = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$b = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$a -eq $b
```

```Output
True
```

<span data-ttu-id="27251-182">任意のオブジェクトを比較するための例として、null かどうかを確認することがあります。</span><span class="sxs-lookup"><span data-stu-id="27251-182">A prominent example of comparing arbitrary objects is to find out if they are null.</span></span> <span data-ttu-id="27251-183">ただし、変数がであるかどうかを判断する必要がある場合は `$null` 、 `$null` 等値演算子の左側に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27251-183">But if you need to determine whether a variable is `$null`, you must put `$null` on the left-hand side of the equality operator.</span></span> <span data-ttu-id="27251-184">これを右側に配置しても、期待どおりの処理は行われません。</span><span class="sxs-lookup"><span data-stu-id="27251-184">Putting it on the right-hand side does not do what you expect.</span></span>

<span data-ttu-id="27251-185">たとえば、次の `$a` ように null 要素を含む配列を使用します。</span><span class="sxs-lookup"><span data-stu-id="27251-185">For example, let `$a` be an array containing null elements:</span></span>

```powershell
$a = 1, 2, $null, 4, $null, 6
```

<span data-ttu-id="27251-186">次のテストは `$a` null ではありません。</span><span class="sxs-lookup"><span data-stu-id="27251-186">The following tests that `$a` is not null.</span></span>

```powershell
$null -ne $a
```

```output
False
```

<span data-ttu-id="27251-187">ただし、次の例では、からすべての null 要素を除外してい `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="27251-187">The following, however, filers out all null elements from `$a`:</span></span>

```powershell
$a -ne $null # Output: 1, 2, 4, 6
```

```output
1
2
4
6
```

### <a name="-gt--ge--lt-and--le"></a><span data-ttu-id="27251-188">-gt、-ge、-lt、および-le</span><span class="sxs-lookup"><span data-stu-id="27251-188">-gt, -ge, -lt, and -le</span></span>

<span data-ttu-id="27251-189">`-gt`、 `-ge` 、 `-lt` 、およびは `-le` 同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="27251-189">`-gt`, `-ge`, `-lt`, and `-le` behave very similarly.</span></span> <span data-ttu-id="27251-190">両方の側がスカラーの場合は、2つの辺の比較に応じて、 **True** または **False** を返します。</span><span class="sxs-lookup"><span data-stu-id="27251-190">When both sides are scalar they return **True** or **False** depending on how the two sides compare:</span></span>

| <span data-ttu-id="27251-191">演算子</span><span class="sxs-lookup"><span data-stu-id="27251-191">Operator</span></span> | <span data-ttu-id="27251-192">True を返します。</span><span class="sxs-lookup"><span data-stu-id="27251-192">Returns True when...</span></span>                   |
| -------- | -------------------------------------- |
| <span data-ttu-id="27251-193">-gt</span><span class="sxs-lookup"><span data-stu-id="27251-193">-gt</span></span>      | <span data-ttu-id="27251-194">左側が大きくなっています</span><span class="sxs-lookup"><span data-stu-id="27251-194">The left-hand side is greater</span></span>          |
| <span data-ttu-id="27251-195">-ge</span><span class="sxs-lookup"><span data-stu-id="27251-195">-ge</span></span>      | <span data-ttu-id="27251-196">左辺が大きいか等しいです。</span><span class="sxs-lookup"><span data-stu-id="27251-196">The left-hand side is greater or equal</span></span> |
| <span data-ttu-id="27251-197">-lt</span><span class="sxs-lookup"><span data-stu-id="27251-197">-lt</span></span>      | <span data-ttu-id="27251-198">左側が小さくなっています</span><span class="sxs-lookup"><span data-stu-id="27251-198">The left-hand side is smaller</span></span>          |
| <span data-ttu-id="27251-199">-le</span><span class="sxs-lookup"><span data-stu-id="27251-199">-le</span></span>      | <span data-ttu-id="27251-200">左側が小さいか等しい</span><span class="sxs-lookup"><span data-stu-id="27251-200">The left-hand side is smaller or equal</span></span> |

<span data-ttu-id="27251-201">次の例では、すべてのステートメントが True を返します。</span><span class="sxs-lookup"><span data-stu-id="27251-201">In the following examples, all statements return True.</span></span>

```powershell
8 -gt 6  # Output: True
8 -ge 8  # Output: True
6 -lt 8  # Output: True
8 -le 8  # Output: True
```

> [!NOTE]
> <span data-ttu-id="27251-202">ほとんどのプログラミング言語では、大なり演算子は `>` です。</span><span class="sxs-lookup"><span data-stu-id="27251-202">In most programming languages the greater-than operator is `>`.</span></span> <span data-ttu-id="27251-203">PowerShell では、この文字がリダイレクトに使用されます。</span><span class="sxs-lookup"><span data-stu-id="27251-203">In PowerShell, this character is used for redirection.</span></span> <span data-ttu-id="27251-204">詳細については、「 [about_Redirection][3]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27251-204">For details, see [about_Redirection][3].</span></span>

<span data-ttu-id="27251-205">左側がコレクションの場合、これらの演算子は、コレクションの各メンバーを右側と比較します。</span><span class="sxs-lookup"><span data-stu-id="27251-205">When the left-hand side is a collection, these operators compare each member of the collection with the right-hand side.</span></span> <span data-ttu-id="27251-206">ロジックに応じて、メンバーを保持するか破棄します。</span><span class="sxs-lookup"><span data-stu-id="27251-206">Depending on their logic, they either keep or discard the member.</span></span>

<span data-ttu-id="27251-207">例:</span><span class="sxs-lookup"><span data-stu-id="27251-207">Example:</span></span>

```powershell
$a=5, 6, 7, 8, 9

Write-Output "Test collection:"
$a

Write-Output "`nMembers greater than 7"
$a -gt 7

Write-Output "`nMembers greater than or equal to 7"
$a -ge 7

Write-Output "`nMembers smaller than 7"
$a -lt 7

Write-Output "`nMembers smaller than or equal to 7"
$a -le 7
```

```output
Test collection:
5
6
7
8
9

Members greater than 7
8
9

Members greater than or equal to 7
7
8
9

Members smaller than 7
5
6

Members smaller than or equal to 7
5
6
7
```

<span data-ttu-id="27251-208">これらの演算子は、 [system.icomparable][1]を実装するすべてのクラスで機能します。</span><span class="sxs-lookup"><span data-stu-id="27251-208">These operators work with any class that implements [System.IComparable][1].</span></span>

<span data-ttu-id="27251-209">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="27251-209">Examples:</span></span>

```powershell
# Date comparison
[DateTime]'2001-11-12' -lt [DateTime]'2020-08-01' # True

# Sorting order comparison
'a' -lt 'z'           # True; 'a' comes before 'z'
'macOS' -ilt 'MacOS'  # False
'MacOS' -ilt 'macOS'  # False
'macOS' -clt 'MacOS'  # True; 'm' comes before 'M'
```

<span data-ttu-id="27251-210">次の例は、"a" の後に並べ替えられる、アメリカ QWERTY キーボードにシンボルがないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="27251-210">The following example demonstrates that there is no symbol on an American QWERTY keyboard that gets sorted after 'a'.</span></span> <span data-ttu-id="27251-211">このようなすべての記号を含むセットを演算子にフィードして、 `-gt` ' a ' と比較します。</span><span class="sxs-lookup"><span data-stu-id="27251-211">It feeds a set containing all such symbols to the `-gt` operator to compare them against 'a'.</span></span> <span data-ttu-id="27251-212">出力は空の配列です。</span><span class="sxs-lookup"><span data-stu-id="27251-212">The output is an empty array.</span></span>

```powershell
$a=' ','`','~','!','@','#','$','%','^','&','*','(',')','_','+','-','=',
   '{','}','[',']',':',';','"','''','\','|','/','?','.','>',',','<'
$a -gt 'a'
# Output: Nothing
```

<span data-ttu-id="27251-213">演算子の両側が適度に比較できない場合、これらの演算子は終了しないエラーを発生させます。</span><span class="sxs-lookup"><span data-stu-id="27251-213">If the two sides of the operators are not reasonably comparable, these operators raise a non-terminating error.</span></span>

## <a name="matching-operators"></a><span data-ttu-id="27251-214">照合演算子</span><span class="sxs-lookup"><span data-stu-id="27251-214">Matching operators</span></span>

<span data-ttu-id="27251-215">一致する演算子 ( `-like` 、 `-notlike` 、 `-match` 、および `-notmatch` ) は、指定したパターンに一致するか一致しない要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="27251-215">The matching operators (`-like`, `-notlike`, `-match`, and `-notmatch`) find elements that match or do not match a specified pattern.</span></span> <span data-ttu-id="27251-216">とのパターン `-like` `-notlike` は、ワイルドカード式 (、、およびを含む `*` ) であり、とは `?` `[ ]` `-match` `-notmatch` 正規表現 (Regex) を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="27251-216">The pattern for `-like` and `-notlike` is a wildcard expression (containing `*`, `?`, and `[ ]`), while `-match` and `-notmatch` accept a regular expression (Regex).</span></span>

<span data-ttu-id="27251-217">の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="27251-217">The syntax is:</span></span>

```
<string[]> -like    <wildcard-expression>
<string[]> -notlike <wildcard-expression>
<string[]> -match    <regular-expression>
<string[]> -notmatch <regular-expression>
```

<span data-ttu-id="27251-218">これらの演算子の入力がスカラー値の場合は、 **ブール** 値が返されます。</span><span class="sxs-lookup"><span data-stu-id="27251-218">When the input of these operators is a scalar value, they return a **Boolean** value.</span></span> <span data-ttu-id="27251-219">入力が値のコレクションである場合、演算子は一致するメンバーを返します。</span><span class="sxs-lookup"><span data-stu-id="27251-219">When the input is a collection of values, the operators return any matching members.</span></span> <span data-ttu-id="27251-220">コレクション内に一致するものがない場合、これらの演算子は空の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="27251-220">If there are no matches in a collection, the operators return an empty array.</span></span>

### <a name="-like-and--notlike"></a><span data-ttu-id="27251-221">-like および-notlike</span><span class="sxs-lookup"><span data-stu-id="27251-221">-like and -notlike</span></span>

<span data-ttu-id="27251-222">`-like` およびは `-notlike` と同様に動作し `-eq` ますが、右側には `-ne` [ワイルドカード](about_Wildcards.md)を含む文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="27251-222">`-like` and `-notlike` behave similarly to `-eq` and `-ne`, but the right-hand side could be a string containing [wildcards](about_Wildcards.md).</span></span>

<span data-ttu-id="27251-223">例:</span><span class="sxs-lookup"><span data-stu-id="27251-223">Example:</span></span>

```powershell
"PowerShell" -like    "*shell"           # Output: True
"PowerShell" -notlike "*shell"           # Output: False
"PowerShell" -like    "Power?hell"       # Output: True
"PowerShell" -notlike "Power?hell"       # Output: False
"PowerShell" -like    "Power[p-w]hell"   # Output: True
"PowerShell" -notlike "Power[p-w]hell"   # Output: False

"PowerShell", "Server" -like "*shell"    # Output: PowerShell
"PowerShell", "Server" -notlike "*shell" # Output: Server
```

### <a name="-match-and--notmatch"></a><span data-ttu-id="27251-224">-match と-notmatch</span><span class="sxs-lookup"><span data-stu-id="27251-224">-match and -notmatch</span></span>

<span data-ttu-id="27251-225">`-match` と `-notmatch` は、正規表現を使用して、左側の値のパターンを検索します。</span><span class="sxs-lookup"><span data-stu-id="27251-225">`-match` and `-notmatch` use regular expressions to search for pattern in the left-hand side values.</span></span> <span data-ttu-id="27251-226">正規表現は、電子メールアドレス、UNC パス、書式設定された電話番号などの複雑なパターンに一致する場合があります。</span><span class="sxs-lookup"><span data-stu-id="27251-226">Regular expressions can match complex patterns like email addresses, UNC paths, or formatted phone numbers.</span></span> <span data-ttu-id="27251-227">右側の文字列は [正規表現](about_Regular_Expressions.md) の規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="27251-227">The right-hand side string must adhere to the [regular expressions](about_Regular_Expressions.md) rules.</span></span>

<span data-ttu-id="27251-228">スカラーの例:</span><span class="sxs-lookup"><span data-stu-id="27251-228">Scalar examples:</span></span>

```powershell
# Partial match test, showing how differently -match and -like behave
"PowerShell" -match 'shell'        # Output: True
"PowerShell" -like  'shell'        # Output: False

# Regex syntax test
"PowerShell" -match    '^Power\w+' # Output: True
'bag'        -notmatch 'b[iou]g'   # Output: True
```

<span data-ttu-id="27251-229">入力がコレクションの場合、演算子はそのコレクションの一致するメンバーを返します。</span><span class="sxs-lookup"><span data-stu-id="27251-229">If the input is a collection, the operators return the matching members of that collection.</span></span>

<span data-ttu-id="27251-230">コレクションの例:</span><span class="sxs-lookup"><span data-stu-id="27251-230">Collection examples:</span></span>

```powershell
"PowerShell", "Super PowerShell", "Power's hell" -match '^Power\w+'
# Output: PowerShell

"Rhell", "Chell", "Mel", "Smell", "Shell" -match "hell"
# Output: Rhell, Chell, Shell

"Bag", "Beg", "Big", "Bog", "Bug"  -match 'b[iou]g'
#Output: Big, Bog, Bug

"Bag", "Beg", "Big", "Bog", "Bug"  -notmatch 'b[iou]g'
#Output: Bag, Beg
```

<span data-ttu-id="27251-231">`-match` およびでは、 `-notmatch` regex キャプチャグループがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="27251-231">`-match` and `-notmatch` support regex capture groups.</span></span> <span data-ttu-id="27251-232">実行するたびに、自動変数が上書きさ `$Matches` れます。</span><span class="sxs-lookup"><span data-stu-id="27251-232">Each time they run, they overwrite the `$Matches` automatic variable.</span></span> <span data-ttu-id="27251-233">`<input>`がコレクションの場合、 `$Matches` 変数は `$null` です。</span><span class="sxs-lookup"><span data-stu-id="27251-233">When `<input>` is a collection the `$Matches` variable is `$null`.</span></span> <span data-ttu-id="27251-234">`$Matches` は、常に ' 0 ' という名前のキーを持つ **ハッシュテーブル** であり、一致した文字列全体が格納されます。</span><span class="sxs-lookup"><span data-stu-id="27251-234">`$Matches` is a **Hashtable** that always has a key named '0', which stores the entire match.</span></span> <span data-ttu-id="27251-235">正規表現にキャプチャグループが含まれている場合、には、 `$Matches` 各グループの追加のキーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="27251-235">If the regular expression contains capture groups, the `$Matches` contains additional keys for each group.</span></span>

<span data-ttu-id="27251-236">例:</span><span class="sxs-lookup"><span data-stu-id="27251-236">Example:</span></span>

```powershell
$string = 'The last logged on user was CONTOSO\jsmith'
$string -match 'was (?<domain>.+)\\(?<user>.+)'

$Matches

Write-Output "`nDomain name:"
$Matches.domain

Write-Output "`nUser name:"
$Matches.user
```

```output
True

Name                           Value
----                           -----
domain                         CONTOSO
user                           jsmith
0                              was CONTOSO\jsmith

Domain name:
CONTOSO

User name:
jsmith
```

<span data-ttu-id="27251-237">詳細については、「 [about_Regular_Expressions](about_Regular_Expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27251-237">For details, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

## <a name="replacement-operator"></a><span data-ttu-id="27251-238">置換演算子</span><span class="sxs-lookup"><span data-stu-id="27251-238">Replacement operator</span></span>

### <a name="replacement-with-regular-expressions"></a><span data-ttu-id="27251-239">正規表現での置換</span><span class="sxs-lookup"><span data-stu-id="27251-239">Replacement with regular expressions</span></span>

<span data-ttu-id="27251-240">と同様に `-match` 、 `-replace` 演算子は正規表現を使用して、指定されたパターンを検索します。</span><span class="sxs-lookup"><span data-stu-id="27251-240">Like `-match`, the `-replace` operator uses regular expressions to find the specified pattern.</span></span> <span data-ttu-id="27251-241">ただし、とは異なり、 `-match` 一致を別の指定された値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="27251-241">But unlike `-match`, it replaces the matches with another specified value.</span></span>

<span data-ttu-id="27251-242">構文:</span><span class="sxs-lookup"><span data-stu-id="27251-242">Syntax:</span></span>

```
<input> -replace <regular-expression>, <substitute>
```

<span data-ttu-id="27251-243">演算子は、値のすべてまたは一部を、正規表現を使用して、指定された値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="27251-243">The operator replaces all or part of a value with the specified value using regular expressions.</span></span> <span data-ttu-id="27251-244">演算子は、ファイル名の変更など、多くの管理タスクに使用できます。</span><span class="sxs-lookup"><span data-stu-id="27251-244">You can use the operator for many administrative tasks, such as renaming files.</span></span> <span data-ttu-id="27251-245">たとえば、次のコマンドは、すべてのファイルのファイル名拡張子 `.txt` をに変更し `.log` ます。</span><span class="sxs-lookup"><span data-stu-id="27251-245">For example, the following command changes the file name extensions of all `.txt` files to `.log`:</span></span>

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

<span data-ttu-id="27251-246">既定では、 `-replace` 演算子は大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="27251-246">By default, the `-replace` operator is case-insensitive.</span></span> <span data-ttu-id="27251-247">大文字と小文字を区別するには、を使用 `-creplace` します。</span><span class="sxs-lookup"><span data-stu-id="27251-247">To make it case sensitive, use `-creplace`.</span></span> <span data-ttu-id="27251-248">大文字と小文字を区別しないようにするには、を使用 `-ireplace` します。</span><span class="sxs-lookup"><span data-stu-id="27251-248">To make it explicitly case-insensitive, use `-ireplace`.</span></span>

<span data-ttu-id="27251-249">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="27251-249">Examples:</span></span>

```powershell
"book" -ireplace "B", "C" # Case insensitive
"book" -creplace "B", "C" # Case-sensitive; hence, nothing to replace
```

```Output
Cook
book
```

### <a name="regular-expressions-substitutions"></a><span data-ttu-id="27251-250">正規表現の置換</span><span class="sxs-lookup"><span data-stu-id="27251-250">Regular expressions substitutions</span></span>

<span data-ttu-id="27251-251">また、正規表現を使用して、キャプチャグループと置換を使用してテキストを動的に置換することもできます。</span><span class="sxs-lookup"><span data-stu-id="27251-251">It is also possible to use regular expressions to dynamically replace text using capturing groups, and substitutions.</span></span> <span data-ttu-id="27251-252">キャプチャグループは、 `<substitute>` `$` グループ識別子の前にドル記号 () を使用して、文字列内で参照できます。</span><span class="sxs-lookup"><span data-stu-id="27251-252">Capture groups can be referenced in the `<substitute>` string using the dollar sign (`$`) character before the group identifier.</span></span>

<span data-ttu-id="27251-253">次の例では、 `-replace` 演算子は、の形式でユーザー名を受け取り、 `DomainName\Username` 形式に変換し `Username@DomainName` ます。</span><span class="sxs-lookup"><span data-stu-id="27251-253">In the following example, the `-replace` operator accepts a username in the form of `DomainName\Username` and converts to the `Username@DomainName` format:</span></span>

```powershell
$SearchExp = '^(?<DomainName>[\w-.]+)\\(?<Username>[\w-.]+)$'
$ReplaceExp = '${Username}@${DomainName}'

'Contoso.local\John.Doe' -replace $SearchExp,$ReplaceExp
```

```output
John.Doe@Contoso.local
```

> [!WARNING]
> <span data-ttu-id="27251-254">この `$` 文字には、PowerShell と正規表現の両方で syntatic ロールがあります。</span><span class="sxs-lookup"><span data-stu-id="27251-254">The `$` character has syntatic roles in both PowerShell and regular expressions:</span></span>
>
> - <span data-ttu-id="27251-255">PowerShell では、2つの二重引用符の間に変数を指定し、部分式演算子として機能します。</span><span class="sxs-lookup"><span data-stu-id="27251-255">In PowerShell, between double quotation marks, it designates variables and acts as a subexpression operator.</span></span>
> - <span data-ttu-id="27251-256">正規表現の検索文字列では、行の終わりを示します。</span><span class="sxs-lookup"><span data-stu-id="27251-256">In Regex search strings, it denotes end of the line</span></span>
> - <span data-ttu-id="27251-257">Regex の置換文字列では、キャプチャされたグループを表します。1つの二重引用符の間に正規表現を配置するか、バックティック () 文字を挿入してください `` ` `` 。</span><span class="sxs-lookup"><span data-stu-id="27251-257">In Regex substitution strings, it denotes captured groups.Be sure to either put your regular expressions between single quotation marks or insert a backtick (`` ` ``) character before them.</span></span>

<span data-ttu-id="27251-258">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="27251-258">For example:</span></span>

```powershell
$1 = 'Goodbye'

'Hello World' -replace '(\w+) \w+', "$1 Universe"
# Output: Goodbye Universe

'Hello World' -replace '(\w+) \w+', '$1 Universe'
# Output: Hello Universe
```

<span data-ttu-id="27251-259">`$$` Regex のはリテラルを表し `$` ます。</span><span class="sxs-lookup"><span data-stu-id="27251-259">`$$` in Regex denotes a literal `$`.</span></span> <span data-ttu-id="27251-260">これは、置換後の `$$` 置換文字列に含まれ `$` ます。</span><span class="sxs-lookup"><span data-stu-id="27251-260">This `$$` in the substitution string to include a literal `$` in the resulting replacement.</span></span> <span data-ttu-id="27251-261">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="27251-261">For example:</span></span>

```powershell
'5.72' -replace '(.+)', '$ $1' # Output: $ 5.72
'5.72' -replace '(.+)', '$$$1' # Output: $5.72
'5.72' -replace '(.+)', '$$1'  # Output: $1
```

<span data-ttu-id="27251-262">詳細については、「[正規表現での][4] [about_Regular_Expressions](about_Regular_Expressions.md)と置換」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27251-262">To learn more, see [about_Regular_Expressions](about_Regular_Expressions.md) and [Substitutions in Regular Expressions][4].</span></span>

### <a name="substituting-in-a-collection"></a><span data-ttu-id="27251-263">コレクション内での置換</span><span class="sxs-lookup"><span data-stu-id="27251-263">Substituting in a collection</span></span>

<span data-ttu-id="27251-264">`<input>`演算子へのが `-replace` コレクションである場合、PowerShell はコレクションのすべての値に置換を適用します。</span><span class="sxs-lookup"><span data-stu-id="27251-264">When the `<input>` to the `-replace` operator is a collection, PowerShell applies the replacement to every value in the collection.</span></span> <span data-ttu-id="27251-265">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="27251-265">For example:</span></span>

```powershell
"B1","B2","B3","B4","B5" -replace "B", 'a'
a1
a2
a3
a4
a5
```

### <a name="replacement-with-a-script-block"></a><span data-ttu-id="27251-266">スクリプトブロックを使用した置換</span><span class="sxs-lookup"><span data-stu-id="27251-266">Replacement with a script block</span></span>

<span data-ttu-id="27251-267">PowerShell 6 以降では、演算子は、 `-replace` 置換を実行するスクリプトブロックも受け入れます。</span><span class="sxs-lookup"><span data-stu-id="27251-267">In PowerShell 6 and later, the `-replace` operator also accepts a script block that performs the replacement.</span></span> <span data-ttu-id="27251-268">スクリプトブロックは、一致するたびに1回実行されます。</span><span class="sxs-lookup"><span data-stu-id="27251-268">The script block runs once for every match.</span></span>

<span data-ttu-id="27251-269">構文:</span><span class="sxs-lookup"><span data-stu-id="27251-269">Syntax:</span></span>

```powershell
<String> -replace <regular-expression>, {<Script-block>}
```

<span data-ttu-id="27251-270">スクリプトブロック内では、自動変数を使用し `$_` て、置き換えられる入力テキストやその他の有用な情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="27251-270">Within the script block, use the `$_` automatic variable to access the input text being replaced and other useful information.</span></span> <span data-ttu-id="27251-271">この変数のクラス型は [system.text.regularexpressions.regexoptions][2]です。</span><span class="sxs-lookup"><span data-stu-id="27251-271">This variable's class type is [System.Text.RegularExpressions.Match][2].</span></span>

<span data-ttu-id="27251-272">次の例では、3桁の各シーケンスを、対応する文字に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="27251-272">The following example replaces each sequence of three digits with the character equivalents.</span></span> <span data-ttu-id="27251-273">スクリプトブロックは、置換する必要がある3桁のセットごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="27251-273">The script block runs for each set of three digits that needs to be replaced.</span></span>

```powershell
"072101108108111" -replace "\d{3}", {return [char][int]$_.Value}
```

```output
Hello
```

## <a name="containment-operators"></a><span data-ttu-id="27251-274">含有演算子</span><span class="sxs-lookup"><span data-stu-id="27251-274">Containment operators</span></span>

<span data-ttu-id="27251-275">含有演算子 ( `-contains` 、、 `-notcontains` `-in` 、および `-notin` ) は、等値演算子に似ていますが、入力がコレクションの場合でも、常に **ブール** 値を返す点が異なります。</span><span class="sxs-lookup"><span data-stu-id="27251-275">The containment operators (`-contains`, `-notcontains`, `-in`, and `-notin`) are similar to the equality operators, except that they always return a **Boolean** value, even when the input is a collection.</span></span> <span data-ttu-id="27251-276">これらの演算子は、最初の一致を検出するとすぐに比較を停止します。一方、等値演算子はすべての入力メンバーを評価します。</span><span class="sxs-lookup"><span data-stu-id="27251-276">These operators stop comparing as soon as they detect the first match, whereas the equality operators evaluate all input members.</span></span> <span data-ttu-id="27251-277">非常に大きなコレクションでは、これらの演算子は等値演算子よりも高速に戻ります。</span><span class="sxs-lookup"><span data-stu-id="27251-277">In a very large collection, these operators return quicker than the equality operators.</span></span>

<span data-ttu-id="27251-278">構文:</span><span class="sxs-lookup"><span data-stu-id="27251-278">Syntax:</span></span>

```
<Collection> -contains <Test-object>
<Collection> -notcontains <Test-object>
<Test-object> -in <Collection>
<Test-object> -notin <Collection>
```

### <a name="-contains-and--notcontains"></a><span data-ttu-id="27251-279">-contains と-notcontains</span><span class="sxs-lookup"><span data-stu-id="27251-279">-contains and -notcontains</span></span>

<span data-ttu-id="27251-280">これらの演算子は、セットに特定の要素が含まれているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="27251-280">These operators tell whether a set includes a certain element.</span></span> <span data-ttu-id="27251-281">`-contains` 右側 (テストオブジェクト) がセット内のいずれかの要素と一致する場合に True を返します。</span><span class="sxs-lookup"><span data-stu-id="27251-281">`-contains` returns True when the right-hand side (test object) matches one of the elements in the set.</span></span> <span data-ttu-id="27251-282">`-notcontains` 代わりに False を返します。</span><span class="sxs-lookup"><span data-stu-id="27251-282">`-notcontains` returns False instead.</span></span> <span data-ttu-id="27251-283">テストオブジェクトがコレクションの場合、これらの演算子は参照の等価性を使用します。つまり、セットの要素の1つがテストオブジェクトの同じインスタンスであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="27251-283">When the test object is a collection, these operators use reference equality, i.e. they check whether one of the set's elements is the same instance of the test object.</span></span>

<span data-ttu-id="27251-284">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="27251-284">Examples:</span></span>

```powershell
"abc", "def" -contains "def"                  # Output: True
"abc", "def" -notcontains "def"               # Output: False
"Windows", "PowerShell" -contains "Shell"     # Output: False
"Windows", "PowerShell" -notcontains "Shell"  # Output: True
"abc", "def", "ghi" -contains "abc", "def"    # Output: False
"abc", "def", "ghi" -notcontains "abc", "def" # Output: True
```

<span data-ttu-id="27251-285">より複雑な例:</span><span class="sxs-lookup"><span data-stu-id="27251-285">More complex examples:</span></span>

```powershell
$DomainServers = "ContosoDC1","ContosoDC2","ContosoFileServer","ContosoDNS",
                 "ContosoDHCP","ContosoWSUS"
$thisComputer  = "ContosoDC2"

$DomainServers -contains $thisComputer
# Output: True

$a = "abc", "def"
"abc", "def", "ghi" -contains $a # Output: False
$a, "ghi" -contains $a           # Output: True
```

### <a name="-in-and--notin"></a><span data-ttu-id="27251-286">-in および-notin</span><span class="sxs-lookup"><span data-stu-id="27251-286">-in and -notin</span></span>

<span data-ttu-id="27251-287">And 演算子は、 `-in` `notin` と演算子の構文の逆に、PowerShell 3 で導入されました `contains` `-notcontain` 。</span><span class="sxs-lookup"><span data-stu-id="27251-287">The `-in` and -`notin` operators were introduced in PowerShell 3 as the syntactic reverse of the of `contains` and `-notcontain` operators.</span></span> <span data-ttu-id="27251-288">`-in`左辺が `<test-object>` set 内のいずれかの要素と一致する場合に True を返します。</span><span class="sxs-lookup"><span data-stu-id="27251-288">`-in` returns **True** when the left-hand side `<test-object>` matches one of the elements in the set.</span></span> <span data-ttu-id="27251-289">`-notin` 代わりに **False** を返します。</span><span class="sxs-lookup"><span data-stu-id="27251-289">`-notin` returns **False** instead.</span></span> <span data-ttu-id="27251-290">テストオブジェクトがセットの場合、これらの演算子は参照の等価性を使用して、セットの要素の1つがテストオブジェクトの同じインスタンスであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="27251-290">When the test object is a set, these operators use reference equality to check whether one of the set's elements is the same instance of the test object.</span></span>

<span data-ttu-id="27251-291">次の例では、との例と同じことを行い `-contain` `-notcontain` ますが、代わりにとを使用して記述されてい `-in` `-notin` ます。</span><span class="sxs-lookup"><span data-stu-id="27251-291">The following examples do the same thing that the examples for `-contain` and `-notcontain` do, but they are written with `-in` and `-notin` instead.</span></span>

```powershell
"def" -in "abc", "def"                  # Output: True
"def" -notin "abc", "def"               # Output: False
"Shell" -in "Windows", "PowerShell"     # Output: False
"Shell" -notin "Windows", "PowerShell"  # Output: True
"abc", "def" -in "abc", "def", "ghi"    # Output: False
"abc", "def" -notin "abc", "def", "ghi" # Output: True
```

<span data-ttu-id="27251-292">より複雑な例:</span><span class="sxs-lookup"><span data-stu-id="27251-292">More complex examples:</span></span>

```powershell
$DomainServers = "ContosoDC1","ContosoDC2","ContosoFileServer","ContosoDNS",
                 "ContosoDHCP","ContosoWSUS"
$thisComputer  = "ContosoDC2"

$thisComputer -in $DomainServers
# Output: True

$a = "abc", "def"
$a -in "abc", "def", "ghi" # Output: False
$a -in $a, "ghi"           # Output: True
```

## <a name="type-comparison"></a><span data-ttu-id="27251-293">型の比較</span><span class="sxs-lookup"><span data-stu-id="27251-293">Type comparison</span></span>

<span data-ttu-id="27251-294">型の比較演算子 ( `-is` と `-isnot` ) は、オブジェクトが特定の型であるかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="27251-294">The type comparison operators (`-is` and `-isnot`) are used to determine if an object is a specific type.</span></span>

<span data-ttu-id="27251-295">構文:</span><span class="sxs-lookup"><span data-stu-id="27251-295">Syntax:</span></span>

```powershell
<object> -is <type-reference>
<object> -isnot <type-reference>
```

<span data-ttu-id="27251-296">例:</span><span class="sxs-lookup"><span data-stu-id="27251-296">Example:</span></span>

```powershell
$a = 1
$b = "1"
$a -is [int]           # Output: True
$a -is $b.GetType()    # Output: False
$b -isnot [int]        # Output: True
$a -isnot $b.GetType() # Output: True
```

## <a name="see-also"></a><span data-ttu-id="27251-297">関連項目</span><span class="sxs-lookup"><span data-stu-id="27251-297">SEE ALSO</span></span>

- [<span data-ttu-id="27251-298">about_Operators</span><span class="sxs-lookup"><span data-stu-id="27251-298">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="27251-299">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="27251-299">about_Regular_Expressions</span></span>](about_Regular_Expressions.md)
- [<span data-ttu-id="27251-300">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="27251-300">about_Wildcards</span></span>](about_Wildcards.md)
- [<span data-ttu-id="27251-301">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="27251-301">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [<span data-ttu-id="27251-302">Foreach-オブジェクト</span><span class="sxs-lookup"><span data-stu-id="27251-302">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [<span data-ttu-id="27251-303">Where-Object</span><span class="sxs-lookup"><span data-stu-id="27251-303">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)

[1]: /dotnet/api/system.icomparable
[2]: /dotnet/api/system.iequatable-1
[3]: /dotnet/api/system.text.regularexpressions.match
[4]: about_Redirection.md#potential-confusion-with-comparison-operators
[5]: /dotnet/standard/base-types/substitutions-in-regular-expressions
