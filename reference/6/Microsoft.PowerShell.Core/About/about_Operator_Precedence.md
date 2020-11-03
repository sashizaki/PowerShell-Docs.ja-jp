---
description: PowerShell 演算子を優先順位順に一覧表示します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 10/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operator_precedence?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operator_Precedence
ms.openlocfilehash: 88a24c04d3d24d1df1b93ab2eefef401063252a2
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221464"
---
# <a name="about-operator-precedence"></a><span data-ttu-id="08a26-104">演算子の優先順位について</span><span class="sxs-lookup"><span data-stu-id="08a26-104">About Operator Precedence</span></span>

## <a name="short-description"></a><span data-ttu-id="08a26-105">概要</span><span class="sxs-lookup"><span data-stu-id="08a26-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="08a26-106">PowerShell 演算子を優先順位順に一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="08a26-106">Lists the PowerShell operators in precedence order.</span></span>

## <a name="long-description"></a><span data-ttu-id="08a26-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="08a26-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="08a26-108">PowerShell の演算子を使用すると、単純な式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="08a26-108">PowerShell operators let you construct simple, but powerful expressions.</span></span> <span data-ttu-id="08a26-109">このトピックでは、演算子を優先順位順に示します。</span><span class="sxs-lookup"><span data-stu-id="08a26-109">This topic lists the operators in precedence order.</span></span> <span data-ttu-id="08a26-110">優先順位は、同じ式に複数の演算子が含まれている場合に、PowerShell が演算子を評価する順序です。</span><span class="sxs-lookup"><span data-stu-id="08a26-110">Precedence order is the order in which PowerShell evaluates the operators when multiple operators appear in the same expression.</span></span>

<span data-ttu-id="08a26-111">演算子の優先順位が同じである場合、PowerShell は式の中に表示されているとおりに左から右に評価します。</span><span class="sxs-lookup"><span data-stu-id="08a26-111">When operators have equal precedence, PowerShell evaluates them from left to right as they appear within the expression.</span></span> <span data-ttu-id="08a26-112">例外として、代入演算子、キャスト演算子、および否定演算子 ( `!` 、 `-not` 、) があり `-bnot` ます。これは右から左に評価されます。</span><span class="sxs-lookup"><span data-stu-id="08a26-112">The exceptions are the assignment operators, the cast operators, and the negation operators (`!`, `-not`, `-bnot`), which are evaluated from right to left.</span></span>

<span data-ttu-id="08a26-113">かっこなどのエンクロージャを使用すると、標準の優先順位をオーバーライドし、PowerShell によって、囲まれていない部分の前に囲まれた式の部分を強制的に評価することができます。</span><span class="sxs-lookup"><span data-stu-id="08a26-113">You can use enclosures, such as parentheses, to override the standard precedence order and force PowerShell to evaluate the enclosed part of an expression before an unenclosed part.</span></span>

<span data-ttu-id="08a26-114">次の一覧では、演算子は評価される順序で一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="08a26-114">In the following list, operators are listed in the order that they are evaluated.</span></span> <span data-ttu-id="08a26-115">同じ行または同じグループ内の演算子は、同じ優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="08a26-115">Operators on the same line, or in the same group, have equal precedence.</span></span>

<span data-ttu-id="08a26-116">演算子列には、演算子が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="08a26-116">The Operator column lists the operators.</span></span> <span data-ttu-id="08a26-117">[参照列には、演算子が記述されている PowerShell ヘルプトピックが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="08a26-117">The Reference column lists the PowerShell Help topic in which the operator is described.</span></span> <span data-ttu-id="08a26-118">トピックを表示するには、「」と入力 `get-help <topic-name>` します。</span><span class="sxs-lookup"><span data-stu-id="08a26-118">To display the topic, type `get-help <topic-name>`.</span></span>

|         <span data-ttu-id="08a26-119">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="08a26-119">OPERATOR</span></span>         |           <span data-ttu-id="08a26-120">リファレンス</span><span class="sxs-lookup"><span data-stu-id="08a26-120">REFERENCE</span></span>            |
| ------------------------ | ------------------------------ |
| `$() @() ()`             | <span data-ttu-id="08a26-121">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-121">[about_Operators][]</span></span>            |
| <span data-ttu-id="08a26-122">`.` (メンバーアクセス)</span><span class="sxs-lookup"><span data-stu-id="08a26-122">`.` (member access)</span></span>      | <span data-ttu-id="08a26-123">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-123">[about_Operators][]</span></span>            |
| <span data-ttu-id="08a26-124">`::` 雑音</span><span class="sxs-lookup"><span data-stu-id="08a26-124">`::` (static)</span></span>            | <span data-ttu-id="08a26-125">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-125">[about_Operators][]</span></span>            |
| <span data-ttu-id="08a26-126">`[0]` (インデックス演算子)</span><span class="sxs-lookup"><span data-stu-id="08a26-126">`[0]` (index operator)</span></span>   | <span data-ttu-id="08a26-127">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-127">[about_Operators][]</span></span>            |
| <span data-ttu-id="08a26-128">`[int]` (cast 演算子)</span><span class="sxs-lookup"><span data-stu-id="08a26-128">`[int]` (cast operators)</span></span> | <span data-ttu-id="08a26-129">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-129">[about_Operators][]</span></span>            |
| <span data-ttu-id="08a26-130">`-split` 前置</span><span class="sxs-lookup"><span data-stu-id="08a26-130">`-split` (unary)</span></span>         | <span data-ttu-id="08a26-131">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="08a26-131">[about_Split][]</span></span>                |
| <span data-ttu-id="08a26-132">`-join` 前置</span><span class="sxs-lookup"><span data-stu-id="08a26-132">`-join` (unary)</span></span>          | <span data-ttu-id="08a26-133">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="08a26-133">[about_Join][]</span></span>                 |
| <span data-ttu-id="08a26-134">`,` (コンマ演算子)</span><span class="sxs-lookup"><span data-stu-id="08a26-134">`,` (comma operator)</span></span>     | <span data-ttu-id="08a26-135">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-135">[about_Operators][]</span></span>            |
| `++ --`                  | <span data-ttu-id="08a26-136">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-136">[about_Assignment_Operators][]</span></span> |
| `! -not`                 | <span data-ttu-id="08a26-137">[about_Logical_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-137">[about_Logical_Operators][]</span></span>    |
| <span data-ttu-id="08a26-138">`..` (範囲演算子)</span><span class="sxs-lookup"><span data-stu-id="08a26-138">`..` (range operator)</span></span>    | <span data-ttu-id="08a26-139">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-139">[about_Operators][]</span></span>            |
| <span data-ttu-id="08a26-140">`-f` (format 演算子)</span><span class="sxs-lookup"><span data-stu-id="08a26-140">`-f` (format operator)</span></span>   | <span data-ttu-id="08a26-141">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-141">[about_Operators][]</span></span>            |
| <span data-ttu-id="08a26-142">`-` (単項/負)</span><span class="sxs-lookup"><span data-stu-id="08a26-142">`-` (unary/negative)</span></span>     | <span data-ttu-id="08a26-143">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-143">[about_Arithmetic_Operators][]</span></span> |
| `* / %`                  | <span data-ttu-id="08a26-144">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-144">[about_Arithmetic_Operators][]</span></span> |
| `+ -`                    | <span data-ttu-id="08a26-145">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-145">[about_Arithmetic_Operators][]</span></span> |

<span data-ttu-id="08a26-146">次の演算子グループは、優先順位が同じです。</span><span class="sxs-lookup"><span data-stu-id="08a26-146">The following group of operators have equal precedence.</span></span> <span data-ttu-id="08a26-147">大文字小文字を区別し、大文字小文字を区別しないバリアントは、同じ優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="08a26-147">Their case-sensitive and explicitly case-insensitive variants have the same precedence.</span></span>

|         <span data-ttu-id="08a26-148">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="08a26-148">OPERATOR</span></span>          |           <span data-ttu-id="08a26-149">リファレンス</span><span class="sxs-lookup"><span data-stu-id="08a26-149">REFERENCE</span></span>            |
| ------------------------- | ------------------------------ |
| <span data-ttu-id="08a26-150">`-split` バイナリ</span><span class="sxs-lookup"><span data-stu-id="08a26-150">`-split` (binary)</span></span>         | <span data-ttu-id="08a26-151">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="08a26-151">[about_Split][]</span></span>                |
| <span data-ttu-id="08a26-152">`-join` バイナリ</span><span class="sxs-lookup"><span data-stu-id="08a26-152">`-join` (binary)</span></span>          | <span data-ttu-id="08a26-153">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="08a26-153">[about_Join][]</span></span>                 |
| `-is -isnot -as`          | <span data-ttu-id="08a26-154">[about_Type_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-154">[about_Type_Operators][]</span></span>       |
| `-eq -ne -gt -gt -lt -le` | <span data-ttu-id="08a26-155">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-155">[about_Comparison_Operators][]</span></span> |
| `-like -notlike`          | <span data-ttu-id="08a26-156">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-156">[about_Comparison_Operators][]</span></span> |
| `-match -notmatch`        | <span data-ttu-id="08a26-157">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-157">[about_Comparison_Operators][]</span></span> |
| `-in -notIn`              | <span data-ttu-id="08a26-158">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-158">[about_Comparison_Operators][]</span></span> |
| `-contains -notContains`  | <span data-ttu-id="08a26-159">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-159">[about_Comparison_Operators][]</span></span> |
| `-replace`                | <span data-ttu-id="08a26-160">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-160">[about_Comparison_Operators][]</span></span> |

<span data-ttu-id="08a26-161">リストは、次の演算子を優先順位順に使用してここで再開します。</span><span class="sxs-lookup"><span data-stu-id="08a26-161">The list resumes here with the following operators in precedence order:</span></span>

|                <span data-ttu-id="08a26-162">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="08a26-162">OPERATOR</span></span>                 |           <span data-ttu-id="08a26-163">リファレンス</span><span class="sxs-lookup"><span data-stu-id="08a26-163">REFERENCE</span></span>            |
| --------------------------------------- | ------------------------------ |
| `-band -bnot -bor -bxor -shr -shl`      | <span data-ttu-id="08a26-164">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-164">[about_Arithmetic_Operators][]</span></span> |
| `-and -or -xor`                         | <span data-ttu-id="08a26-165">[about_Logical_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-165">[about_Logical_Operators][]</span></span>    |

<span data-ttu-id="08a26-166">次の項目は、真の演算子ではありません。</span><span class="sxs-lookup"><span data-stu-id="08a26-166">The following items are not true operators.</span></span> <span data-ttu-id="08a26-167">これらは、式の構文ではなく、PowerShell のコマンド構文に含まれています。</span><span class="sxs-lookup"><span data-stu-id="08a26-167">They are part of PowerShell's command syntax, not expression syntax.</span></span> <span data-ttu-id="08a26-168">割り当ては常に最後に行われる操作です。</span><span class="sxs-lookup"><span data-stu-id="08a26-168">Assignment is always the last action that happens.</span></span>

|                <span data-ttu-id="08a26-169">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="08a26-169">SYNTAX</span></span>                   |           <span data-ttu-id="08a26-170">リファレンス</span><span class="sxs-lookup"><span data-stu-id="08a26-170">REFERENCE</span></span>            |
| --------------------------------------- | ------------------------------ |
| <span data-ttu-id="08a26-171">`.` (ドット-ソース)</span><span class="sxs-lookup"><span data-stu-id="08a26-171">`.` (dot-source)</span></span>                        | <span data-ttu-id="08a26-172">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-172">[about_Operators][]</span></span>            |
| <span data-ttu-id="08a26-173">`&` 発信</span><span class="sxs-lookup"><span data-stu-id="08a26-173">`&` (call)</span></span>                              | <span data-ttu-id="08a26-174">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-174">[about_Operators][]</span></span>            |
| <span data-ttu-id="08a26-175"><code>&#124;</code> (パイプライン演算子)</span><span class="sxs-lookup"><span data-stu-id="08a26-175"><code>&#124;</code> (pipeline operator)</span></span> | <span data-ttu-id="08a26-176">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-176">[about_Operators][]</span></span>            |
| `> >> 2> 2>> 2>&1`                      | <span data-ttu-id="08a26-177">[about_Redirection][]</span><span class="sxs-lookup"><span data-stu-id="08a26-177">[about_Redirection][]</span></span>          |
| `= += -= *= /= %=`                      | <span data-ttu-id="08a26-178">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-178">[about_Assignment_Operators][]</span></span> |

## <a name="examples"></a><span data-ttu-id="08a26-179">例</span><span class="sxs-lookup"><span data-stu-id="08a26-179">EXAMPLES</span></span>

<span data-ttu-id="08a26-180">次の2つのコマンドは、算術演算子と、かっこを使用して、式の囲まれた部分を最初に評価するように PowerShell に強制する効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="08a26-180">The following two commands show the arithmetic operators and the effect of using parentheses to force PowerShell to evaluate the enclosed part of the expression first.</span></span>

```powershell
PS> 2 + 3 * 4
14

PS> (2 + 3) * 4
20
```

<span data-ttu-id="08a26-181">次の例では、ローカルディレクトリから読み取り専用のテキストファイルを取得し、変数に保存し `$read_only` ます。</span><span class="sxs-lookup"><span data-stu-id="08a26-181">The following example gets the read-only text files from the local directory and saves them in the `$read_only` variable.</span></span>

```powershell
$read_only = Get-ChildItem *.txt | Where-Object {$_.isReadOnly}
```

<span data-ttu-id="08a26-182">これは、次の例と同じです。</span><span class="sxs-lookup"><span data-stu-id="08a26-182">It is equivalent to the following example.</span></span>

```powershell
$read_only = ( Get-ChildItem *.txt | Where-Object {$_.isReadOnly} )
```

<span data-ttu-id="08a26-183">パイプライン演算子 () は `|` 代入演算子 () より優先順位が高いため `=` 、コマンドレットによって `Get-ChildItem` 取得されるファイルは、 `Where-Object` 変数に割り当てられる前に、フィルター処理のためにコマンドレットに送信され `$read_only` ます。</span><span class="sxs-lookup"><span data-stu-id="08a26-183">Because the pipeline operator (`|`) has a higher precedence than the assignment operator (`=`), the files that the `Get-ChildItem` cmdlet gets are sent to the `Where-Object` cmdlet for filtering before they are assigned to the `$read_only` variable.</span></span>

<span data-ttu-id="08a26-184">次の例では、index 演算子がキャスト演算子よりも優先されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="08a26-184">The following example demonstrates that the index operator takes precedence over the cast operator.</span></span>

<span data-ttu-id="08a26-185">この式は、3つの文字列の配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="08a26-185">This expression creates an array of three strings.</span></span> <span data-ttu-id="08a26-186">次に、値が0の index 演算子を使用して、配列内の最初のオブジェクト (最初の文字列) を選択します。</span><span class="sxs-lookup"><span data-stu-id="08a26-186">Then, it uses the index operator with a value of 0 to select the first object in the array, which is the first string.</span></span> <span data-ttu-id="08a26-187">最後に、選択したオブジェクトを文字列としてキャストします。</span><span class="sxs-lookup"><span data-stu-id="08a26-187">Finally, it casts the selected object as a string.</span></span> <span data-ttu-id="08a26-188">この場合、キャストは無効です。</span><span class="sxs-lookup"><span data-stu-id="08a26-188">In this case, the cast has no effect.</span></span>

```powershell
PS> [string]@('Windows','PowerShell','2.0')[0]
Windows
```

<span data-ttu-id="08a26-189">この式では、かっこを使用して、インデックス選択の前にキャスト操作を強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="08a26-189">This expression uses parentheses to force the cast operation to occur before the index selection.</span></span> <span data-ttu-id="08a26-190">その結果、配列全体が (単一の) 文字列としてキャストされます。</span><span class="sxs-lookup"><span data-stu-id="08a26-190">As a result, the entire array is cast as a (single) string.</span></span> <span data-ttu-id="08a26-191">次に、index 演算子は、文字列配列内の最初の項目 (最初の文字) を選択します。</span><span class="sxs-lookup"><span data-stu-id="08a26-191">Then, the index operator selects the first item in the string array, which is the first character.</span></span>

```powershell
PS> ([string]@('Windows','PowerShell','2.0'))[0]
W
```

<span data-ttu-id="08a26-192">次の例では、 `-gt` (大なり) 演算子が (論理 and) 演算子よりも優先順位が高いため、 `-and` 式の結果は FALSE になります。</span><span class="sxs-lookup"><span data-stu-id="08a26-192">In the following example, because the `-gt` (greater-than) operator has a higher precedence than the `-and` (logical AND) operator, the result of the expression is FALSE.</span></span>

```powershell
PS> 2 -gt 4 -and 1
False
```

<span data-ttu-id="08a26-193">これは、次の式と同じです。</span><span class="sxs-lookup"><span data-stu-id="08a26-193">It is equivalent to the following expression.</span></span>

```powershell
PS> (2 -gt 4) -and 1
False
```

<span data-ttu-id="08a26-194">-And 演算子の優先順位が高い場合、答えは TRUE になります。</span><span class="sxs-lookup"><span data-stu-id="08a26-194">If the -and operator had higher precedence, the answer would be TRUE.</span></span>

```powershell
PS> 2 -gt (4 -and 1)
True
```

<span data-ttu-id="08a26-195">ただし、この例では、演算子の優先順位を管理するための重要な原則を示しています。</span><span class="sxs-lookup"><span data-stu-id="08a26-195">However, this example demonstrates an important principle of managing operator precedence.</span></span> <span data-ttu-id="08a26-196">式の解釈が難しい場合は、かっこを使用して、既定の演算子の優先順位を強制的に適用する場合でも、評価順序を強制します。</span><span class="sxs-lookup"><span data-stu-id="08a26-196">When an expression is difficult for people to interpret, use parentheses to force the evaluation order, even when it forces the default operator precedence.</span></span> <span data-ttu-id="08a26-197">かっこを使用すると、スクリプトを読んで管理している人に対して意図が明確になります。</span><span class="sxs-lookup"><span data-stu-id="08a26-197">The parentheses make your intentions clear to people who are reading and maintaining your scripts.</span></span>

## <a name="see-also"></a><span data-ttu-id="08a26-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="08a26-198">SEE ALSO</span></span>

<span data-ttu-id="08a26-199">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-199">[about_Operators][]</span></span>

<span data-ttu-id="08a26-200">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-200">[about_Assignment_Operators][]</span></span>

<span data-ttu-id="08a26-201">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-201">[about_Comparison_Operators][]</span></span>

<span data-ttu-id="08a26-202">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-202">[about_Arithmetic_Operators][]</span></span>

<span data-ttu-id="08a26-203">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="08a26-203">[about_Join][]</span></span>

<span data-ttu-id="08a26-204">[about_Redirection][]</span><span class="sxs-lookup"><span data-stu-id="08a26-204">[about_Redirection][]</span></span>

<span data-ttu-id="08a26-205">[about_Scopes][]</span><span class="sxs-lookup"><span data-stu-id="08a26-205">[about_Scopes][]</span></span>

<span data-ttu-id="08a26-206">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="08a26-206">[about_Split][]</span></span>

<span data-ttu-id="08a26-207">[about_Type_Operators][]</span><span class="sxs-lookup"><span data-stu-id="08a26-207">[about_Type_Operators][]</span></span>

<!-- reference links -->
[about_Arithmetic_Operators]: about_Arithmetic_Operators.md
[about_Assignment_Operators]: about_Assignment_Operators.md
[about_Comparison_Operators]: about_Comparison_Operators.md
[about_Join]: about_Join.md
[about_Logical_Operators]: about_logical_operators.md
[about_Operators]: about_Operators.md
[about_Redirection]: about_Redirection.md
[about_Scopes]: about_Scopes.md
[about_Split]: about_Split.md
[about_Type_Operators]: about_Type_Operators.md