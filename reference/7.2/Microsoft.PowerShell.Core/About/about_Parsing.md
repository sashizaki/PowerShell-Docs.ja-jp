---
description: PowerShell によるコマンドの解析方法について説明します。
Locale: en-US
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parsing?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parsing
ms.openlocfilehash: a5ce30b2ad9aff7dd8b54e7a62937013a61cd278
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603250"
---
# <a name="about-parsing"></a><span data-ttu-id="844a1-103">解析の概要</span><span class="sxs-lookup"><span data-stu-id="844a1-103">About Parsing</span></span>

## <a name="short-description"></a><span data-ttu-id="844a1-104">概要</span><span class="sxs-lookup"><span data-stu-id="844a1-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="844a1-105">PowerShell によるコマンドの解析方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="844a1-105">Describes how PowerShell parses commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="844a1-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="844a1-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="844a1-107">コマンドプロンプトでコマンドを入力すると、PowerShell はコマンドテキストを _トークン_ と呼ばれる一連のセグメントに分割し、各トークンの解釈方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="844a1-107">When you enter a command at the command prompt, PowerShell breaks the command text into a series of segments called _tokens_ and then determines how to interpret each token.</span></span>

<span data-ttu-id="844a1-108">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="844a1-108">For example, if you type:</span></span>

```powershell
Write-Host book
```

<span data-ttu-id="844a1-109">PowerShell では、コマンドがとという2つのトークンに分割され、 `Write-Host` `book` 2 つの主要な解析モード (expression モードと argument モード) のいずれかを使用して各トークンが個別に解釈されます。</span><span class="sxs-lookup"><span data-stu-id="844a1-109">PowerShell breaks the command into two tokens, `Write-Host` and `book`, and interprets each token independently using one of two major parsing modes: expression mode and argument mode.</span></span>

> [!NOTE]
> <span data-ttu-id="844a1-110">PowerShell によってコマンド入力が解析されるので、コマンド名をコマンドレットまたはネイティブの実行可能ファイルに解決しようとします。</span><span class="sxs-lookup"><span data-stu-id="844a1-110">As PowerShell parses command input it tries to resolve the command names to cmdlets or native executables.</span></span> <span data-ttu-id="844a1-111">コマンド名に完全に一致するものがない場合、PowerShell は `Get-` 既定の動詞としてコマンドの前に付加します。</span><span class="sxs-lookup"><span data-stu-id="844a1-111">If a command name does not have an exact match, PowerShell prepends `Get-` to the command as a default verb.</span></span> <span data-ttu-id="844a1-112">たとえば、PowerShell はとしてを解析し `Process` `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="844a1-112">For example, PowerShell parses `Process` as `Get-Process`.</span></span> <span data-ttu-id="844a1-113">この機能は、次の理由で使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="844a1-113">It's not recommended to use this feature for the following reasons:</span></span>
>
> - <span data-ttu-id="844a1-114">これは非効率的です。</span><span class="sxs-lookup"><span data-stu-id="844a1-114">It's inefficient.</span></span> <span data-ttu-id="844a1-115">これにより、PowerShell が複数回検索されます。</span><span class="sxs-lookup"><span data-stu-id="844a1-115">This causes PowerShell to search multiple times.</span></span>
> - <span data-ttu-id="844a1-116">同じ名前の外部プログラムが最初に解決されるため、目的のコマンドレットを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="844a1-116">External programs with the same name are resolved first, so you may not execute intended cmdlet.</span></span>
> - <span data-ttu-id="844a1-117">`Get-Help``Get-Command`動詞のない名前は認識されません。</span><span class="sxs-lookup"><span data-stu-id="844a1-117">`Get-Help` and `Get-Command` don't recognize verb-less names.</span></span>

### <a name="expression-mode"></a><span data-ttu-id="844a1-118">式モード</span><span class="sxs-lookup"><span data-stu-id="844a1-118">Expression mode</span></span>

<span data-ttu-id="844a1-119">式モードは、スクリプト言語での値の操作に必要な結合式を使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="844a1-119">Expression mode is intended for combining expressions, required for value manipulation in a scripting language.</span></span> <span data-ttu-id="844a1-120">式は PowerShell 構文の値の表現であり、単純型または複合型にすることができます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="844a1-120">Expressions are representations of values in PowerShell syntax, and can be simple or composite, for example:</span></span>

<span data-ttu-id="844a1-121">リテラル式は、値を直接表現したものです。</span><span class="sxs-lookup"><span data-stu-id="844a1-121">Literal expressions are direct representations of their values:</span></span> 

```powershell
'hello', 32
```

<span data-ttu-id="844a1-122">変数式には、参照する変数の値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="844a1-122">Variable expressions carry the value of the variable they reference:</span></span> 

```powershell
$x, $script:path
```
<span data-ttu-id="844a1-123">演算子は、評価のために他の式を結合します。</span><span class="sxs-lookup"><span data-stu-id="844a1-123">Operators combine other expressions for evaluation:</span></span> 

```powershell
- 12, -not $Quiet, 3 + 7, $input.Length -gt 1
```

- <span data-ttu-id="844a1-124">_文字列リテラル_ は引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="844a1-124">_Character string literals_ must be contained in quotation marks.</span></span>
- <span data-ttu-id="844a1-125">_数値_ は、エスケープされない限り、一連の文字としてではなく、数値として扱われます。</span><span class="sxs-lookup"><span data-stu-id="844a1-125">_Numbers_ are treated as numerical values rather than as a series of characters (unless escaped).</span></span>
- <span data-ttu-id="844a1-126">_演算子_(やなどの、やなどの二項演算子を含む) `-` `-not` `+` `-gt` は演算子として解釈され、それぞれの引数 (オペランド) に対してそれぞれの操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="844a1-126">_Operators_, including unary operators like `-` and `-not` and binary operators like `+` and `-gt`, are interpreted as operators and apply their respective operations on their arguments (operands).</span></span>
- <span data-ttu-id="844a1-127">_属性および変換式_ は式として解析され、下位の式 (など) に適用され `[int] '7'` ます。</span><span class="sxs-lookup"><span data-stu-id="844a1-127">_Attribute and conversion expressions_ are parsed as expressions and applied to subordinate expressions, e.g. `[int] '7'`.</span></span>
- <span data-ttu-id="844a1-128">_変数参照_ はその値に評価されますが、 _スプラッティング_ (事前パラメーターセットの貼り付け) は禁止されているため、パーサーエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="844a1-128">_Variable references_ are evaluated to their values but _splatting_ (i.e. pasting prefilled parameter sets) is forbidden and causes a parser error.</span></span>
- <span data-ttu-id="844a1-129">それ以外のものは、呼び出されるコマンドとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="844a1-129">Anything else will be treated as a command to be invoked.</span></span>

### <a name="argument-mode"></a><span data-ttu-id="844a1-130">引数モード</span><span class="sxs-lookup"><span data-stu-id="844a1-130">Argument mode</span></span>

<span data-ttu-id="844a1-131">解析時に、PowerShell は最初に入力を式として解釈しようとします。</span><span class="sxs-lookup"><span data-stu-id="844a1-131">When parsing, PowerShell first looks to interpret input as an expression.</span></span> <span data-ttu-id="844a1-132">ただし、コマンド呼び出しが検出されると、引数モードで解析が続行されます。</span><span class="sxs-lookup"><span data-stu-id="844a1-132">But when a command invocation is encountered, parsing continues in argument mode.</span></span>

<span data-ttu-id="844a1-133">引数モードは、シェル環境でコマンドの引数とパラメーターを解析するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="844a1-133">Argument mode is designed for parsing arguments and parameters for commands in a shell environment.</span></span> <span data-ttu-id="844a1-134">次のいずれかの構文を使用しない限り、すべての入力は展開可能な文字列として扱われます。</span><span class="sxs-lookup"><span data-stu-id="844a1-134">All input is treated as an expandable string unless it uses one of the following syntaxes:</span></span>

- <span data-ttu-id="844a1-135">ドル記号 ( `$` ) は変数参照を開始します (その後に有効な変数名が続く場合のみ)。それ以外の場合は、展開可能な文字列の一部として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="844a1-135">Dollar sign (`$`) begins a variable reference (only if it is followed by a valid variable name, otherwise it is interpreted as part of the expandable string).</span></span>
- <span data-ttu-id="844a1-136">引用符 ( `'` および `"` ) の開始文字列値</span><span class="sxs-lookup"><span data-stu-id="844a1-136">Quotation marks (`'` and `"`) begin string values</span></span>
- <span data-ttu-id="844a1-137">かっこ ( `(` と `)` ) 区別新しい式です。</span><span class="sxs-lookup"><span data-stu-id="844a1-137">Parentheses (`(` and `)`) demarcate new expressions.</span></span>
- <span data-ttu-id="844a1-138">部分式演算子 ( `$(` ... `)` ) 区分埋め込み式。</span><span class="sxs-lookup"><span data-stu-id="844a1-138">Subexpression operator (`$(`…`)`) demarcates embedded expressions.</span></span>
- <span data-ttu-id="844a1-139">中かっこ ( `{` と `}` ) 区別は、新しいスクリプトブロックを作成します。</span><span class="sxs-lookup"><span data-stu-id="844a1-139">Braces (`{` and `}`) demarcate new script blocks.</span></span>
- <span data-ttu-id="844a1-140">最初のアットマーク ( `@` ) `@args` は、スプラッティング ()、配列 ()、 `@(1,2,3)` ハッシュテーブル () などの式の構文を開始し `@{a=1;b=2}` ます。</span><span class="sxs-lookup"><span data-stu-id="844a1-140">Initial at sign (`@`) begins expression syntaxes such as splatting (`@args`), arrays (`@(1,2,3)`) and hash tables (`@{a=1;b=2}`).</span></span>
- <span data-ttu-id="844a1-141">コンマ ( `,` ) は、配列として渡されるリストを導入します。ただし、呼び出されるコマンドがネイティブアプリケーションである場合を除きます。この場合、拡張可能な文字列の一部として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="844a1-141">Commas (`,`) introduce lists passed as arrays, except when the command to be called is a native application, in which case they are interpreted as part of the expandable string.</span></span> <span data-ttu-id="844a1-142">最初、連続、または末尾のコンマはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="844a1-142">Initial, consecutive or trailing commas are not supported.</span></span>

<!--
01234567890123456789012345678901234567890123456789012345678901234567890123456789
-->
<span data-ttu-id="844a1-143">埋め込み式の値は、文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="844a1-143">Values of embedded expressions are converted to strings.</span></span>

<span data-ttu-id="844a1-144">次の表に、式モードおよび引数モードで処理される値の例と、それらの値の評価を示します。</span><span class="sxs-lookup"><span data-stu-id="844a1-144">The following table provides several examples of values processed in expression mode and argument mode and the evaluation of those values.</span></span> <span data-ttu-id="844a1-145">変数の値がであることを前提として `a` `4` います。</span><span class="sxs-lookup"><span data-stu-id="844a1-145">We assume that the value of the variable `a` is `4`.</span></span>

|       <span data-ttu-id="844a1-146">例</span><span class="sxs-lookup"><span data-stu-id="844a1-146">Example</span></span>        |    <span data-ttu-id="844a1-147">モード</span><span class="sxs-lookup"><span data-stu-id="844a1-147">Mode</span></span>    |      <span data-ttu-id="844a1-148">結果</span><span class="sxs-lookup"><span data-stu-id="844a1-148">Result</span></span>       |
| -------------------- | ---------- | ----------------- |
| `2`                  | <span data-ttu-id="844a1-149">式</span><span class="sxs-lookup"><span data-stu-id="844a1-149">Expression</span></span> | <span data-ttu-id="844a1-150">2 (整数)</span><span class="sxs-lookup"><span data-stu-id="844a1-150">2 (integer)</span></span>       |
| `` `2``              | <span data-ttu-id="844a1-151">Expression</span><span class="sxs-lookup"><span data-stu-id="844a1-151">Expression</span></span> | <span data-ttu-id="844a1-152">"2" (コマンド)</span><span class="sxs-lookup"><span data-stu-id="844a1-152">"2" (command)</span></span>     |
| `echo 2`             | <span data-ttu-id="844a1-153">Expression</span><span class="sxs-lookup"><span data-stu-id="844a1-153">Expression</span></span> | <span data-ttu-id="844a1-154">2 (整数)</span><span class="sxs-lookup"><span data-stu-id="844a1-154">2 (integer)</span></span>       |
| `2+2`                | <span data-ttu-id="844a1-155">Expression</span><span class="sxs-lookup"><span data-stu-id="844a1-155">Expression</span></span> | <span data-ttu-id="844a1-156">4 (整数)</span><span class="sxs-lookup"><span data-stu-id="844a1-156">4 (integer)</span></span>       |
| `echo 2+2`           | <span data-ttu-id="844a1-157">引数</span><span class="sxs-lookup"><span data-stu-id="844a1-157">Argument</span></span>   | <span data-ttu-id="844a1-158">"2 + 2" (文字列)</span><span class="sxs-lookup"><span data-stu-id="844a1-158">"2+2" (string)</span></span>    |
| `echo(2+2)`          | <span data-ttu-id="844a1-159">Expression</span><span class="sxs-lookup"><span data-stu-id="844a1-159">Expression</span></span> | <span data-ttu-id="844a1-160">4 (整数)</span><span class="sxs-lookup"><span data-stu-id="844a1-160">4 (integer)</span></span>       |
| `$a`                 | <span data-ttu-id="844a1-161">Expression</span><span class="sxs-lookup"><span data-stu-id="844a1-161">Expression</span></span> | <span data-ttu-id="844a1-162">4 (整数)</span><span class="sxs-lookup"><span data-stu-id="844a1-162">4 (integer)</span></span>       |
| `echo $a`            | <span data-ttu-id="844a1-163">Expression</span><span class="sxs-lookup"><span data-stu-id="844a1-163">Expression</span></span> | <span data-ttu-id="844a1-164">4 (整数)</span><span class="sxs-lookup"><span data-stu-id="844a1-164">4 (integer)</span></span>       |
| `$a+2`               | <span data-ttu-id="844a1-165">Expression</span><span class="sxs-lookup"><span data-stu-id="844a1-165">Expression</span></span> | <span data-ttu-id="844a1-166">6 (整数)</span><span class="sxs-lookup"><span data-stu-id="844a1-166">6 (integer)</span></span>       |
| `echo $a+2`          | <span data-ttu-id="844a1-167">引数</span><span class="sxs-lookup"><span data-stu-id="844a1-167">Argument</span></span>   | <span data-ttu-id="844a1-168">4 + 2 (文字列)</span><span class="sxs-lookup"><span data-stu-id="844a1-168">4+2 (string)</span></span>      |
| `$-`                 | <span data-ttu-id="844a1-169">引数</span><span class="sxs-lookup"><span data-stu-id="844a1-169">Argument</span></span>   | <span data-ttu-id="844a1-170">"$-" (コマンド)</span><span class="sxs-lookup"><span data-stu-id="844a1-170">"$-" (command)</span></span>    |
| `echo $-`            | <span data-ttu-id="844a1-171">引数</span><span class="sxs-lookup"><span data-stu-id="844a1-171">Argument</span></span>   | <span data-ttu-id="844a1-172">"$-" (文字列)</span><span class="sxs-lookup"><span data-stu-id="844a1-172">"$-" (string)</span></span>     |
| `a$a`                | <span data-ttu-id="844a1-173">Expression</span><span class="sxs-lookup"><span data-stu-id="844a1-173">Expression</span></span> | <span data-ttu-id="844a1-174">"a $ a" (コマンド)</span><span class="sxs-lookup"><span data-stu-id="844a1-174">"a$a" (command)</span></span>   |
| `echo a$a`           | <span data-ttu-id="844a1-175">引数</span><span class="sxs-lookup"><span data-stu-id="844a1-175">Argument</span></span>   | <span data-ttu-id="844a1-176">"a4" (文字列)</span><span class="sxs-lookup"><span data-stu-id="844a1-176">"a4" (string)</span></span>     |
| `a'$a'`              | <span data-ttu-id="844a1-177">Expression</span><span class="sxs-lookup"><span data-stu-id="844a1-177">Expression</span></span> | <span data-ttu-id="844a1-178">"a $ a" (コマンド)</span><span class="sxs-lookup"><span data-stu-id="844a1-178">"a$a" (command)</span></span>   |
| `echo a'$a'`         | <span data-ttu-id="844a1-179">引数</span><span class="sxs-lookup"><span data-stu-id="844a1-179">Argument</span></span>   | <span data-ttu-id="844a1-180">"a $ a" (文字列)</span><span class="sxs-lookup"><span data-stu-id="844a1-180">"a$a" (string)</span></span>    |
| `a"$a"`              | <span data-ttu-id="844a1-181">Expression</span><span class="sxs-lookup"><span data-stu-id="844a1-181">Expression</span></span> | <span data-ttu-id="844a1-182">"a $ a" (コマンド)</span><span class="sxs-lookup"><span data-stu-id="844a1-182">"a$a" (command)</span></span>   |
| `echo a"$a"`         | <span data-ttu-id="844a1-183">引数</span><span class="sxs-lookup"><span data-stu-id="844a1-183">Argument</span></span>   | <span data-ttu-id="844a1-184">"a4" (文字列)</span><span class="sxs-lookup"><span data-stu-id="844a1-184">"a4" (string)</span></span>     |
| `a$(2)`              | <span data-ttu-id="844a1-185">Expression</span><span class="sxs-lookup"><span data-stu-id="844a1-185">Expression</span></span> | <span data-ttu-id="844a1-186">"a $ (2)" (コマンド)</span><span class="sxs-lookup"><span data-stu-id="844a1-186">"a$(2)" (command)</span></span> |
| `echo a$(2)`         | <span data-ttu-id="844a1-187">引数</span><span class="sxs-lookup"><span data-stu-id="844a1-187">Argument</span></span>   | <span data-ttu-id="844a1-188">"a2" (文字列)</span><span class="sxs-lookup"><span data-stu-id="844a1-188">"a2" (string)</span></span>     |

<span data-ttu-id="844a1-189">すべてのトークンは、ブール値や文字列など、何らかの種類のオブジェクトとして解釈できます。</span><span class="sxs-lookup"><span data-stu-id="844a1-189">Every token can be interpreted as some kind of object type, such as Boolean or string.</span></span> <span data-ttu-id="844a1-190">PowerShell は、式からオブジェクトの種類を特定しようとします。</span><span class="sxs-lookup"><span data-stu-id="844a1-190">PowerShell attempts to determine the object type from the expression.</span></span>
<span data-ttu-id="844a1-191">オブジェクトの種類は、コマンドが想定するパラメーターの型と、引数を正しい型に変換する方法を PowerShell が認識しているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="844a1-191">The object type depends on the type of parameter a command expects and on whether PowerShell knows how to convert the argument to the correct type.</span></span> <span data-ttu-id="844a1-192">次の表に、式によって返される値に割り当てられる型の例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="844a1-192">The following table shows several examples of the types assigned to values returned by the expressions.</span></span>

|       <span data-ttu-id="844a1-193">例</span><span class="sxs-lookup"><span data-stu-id="844a1-193">Example</span></span>          |    <span data-ttu-id="844a1-194">モード</span><span class="sxs-lookup"><span data-stu-id="844a1-194">Mode</span></span>    |     <span data-ttu-id="844a1-195">結果</span><span class="sxs-lookup"><span data-stu-id="844a1-195">Result</span></span>      |
| ---------------------- | ---------- | --------------- |
| `Write-Output !1`      | <span data-ttu-id="844a1-196">引数</span><span class="sxs-lookup"><span data-stu-id="844a1-196">argument</span></span>   | <span data-ttu-id="844a1-197">"! 1" (文字列)</span><span class="sxs-lookup"><span data-stu-id="844a1-197">"!1" (string)</span></span>   |
| `Write-Output (!1)`    | <span data-ttu-id="844a1-198">expression</span><span class="sxs-lookup"><span data-stu-id="844a1-198">expression</span></span> | <span data-ttu-id="844a1-199">False (ブール値)</span><span class="sxs-lookup"><span data-stu-id="844a1-199">False (Boolean)</span></span> |
| `Write-Output (2)`     | <span data-ttu-id="844a1-200">expression</span><span class="sxs-lookup"><span data-stu-id="844a1-200">expression</span></span> | <span data-ttu-id="844a1-201">2 (整数)</span><span class="sxs-lookup"><span data-stu-id="844a1-201">2 (integer)</span></span>     |
| `Set-Variable AB A,B`  | <span data-ttu-id="844a1-202">引数</span><span class="sxs-lookup"><span data-stu-id="844a1-202">argument</span></span>   | <span data-ttu-id="844a1-203">' A '、' B ' (配列)</span><span class="sxs-lookup"><span data-stu-id="844a1-203">'A','B' (array)</span></span> |
| `CMD /CECHO A,B`       | <span data-ttu-id="844a1-204">引数</span><span class="sxs-lookup"><span data-stu-id="844a1-204">argument</span></span>   | <span data-ttu-id="844a1-205">' A, B ' (文字列)</span><span class="sxs-lookup"><span data-stu-id="844a1-205">'A,B' (string)</span></span>  |
| `CMD /CECHO $AB`       | <span data-ttu-id="844a1-206">expression</span><span class="sxs-lookup"><span data-stu-id="844a1-206">expression</span></span> | <span data-ttu-id="844a1-207">' A '、' B ' (配列)</span><span class="sxs-lookup"><span data-stu-id="844a1-207">'A','B' (array)</span></span> |
| `CMD /CECHO :$AB`      | <span data-ttu-id="844a1-208">引数</span><span class="sxs-lookup"><span data-stu-id="844a1-208">argument</span></span>   | <span data-ttu-id="844a1-209">': A B ' (文字列)</span><span class="sxs-lookup"><span data-stu-id="844a1-209">':A B' (string)</span></span> |

<span data-ttu-id="844a1-210">Powershell 3.0 で導入された解析の中止記号 () は、powershell `--%` コマンドまたは式として入力を解釈しないように powershell に指示します。</span><span class="sxs-lookup"><span data-stu-id="844a1-210">The stop-parsing symbol (`--%`), introduced in PowerShell 3.0, directs PowerShell to refrain from interpreting input as PowerShell commands or expressions.</span></span>

<span data-ttu-id="844a1-211">PowerShell で実行可能プログラムを呼び出す場合は、プログラムの引数の前にストップ解析のシンボルを配置します。</span><span class="sxs-lookup"><span data-stu-id="844a1-211">When calling an executable program in PowerShell, place the stop-parsing symbol before the program arguments.</span></span> <span data-ttu-id="844a1-212">この手法は、誤って解釈されないようにエスケープ文字を使用するよりもはるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="844a1-212">This technique is much easier than using escape characters to prevent misinterpretation.</span></span>

<span data-ttu-id="844a1-213">ストップ解析シンボルが検出されると、PowerShell は行の残りの文字をリテラルとして扱います。</span><span class="sxs-lookup"><span data-stu-id="844a1-213">When it encounters a stop-parsing symbol, PowerShell treats the remaining characters in the line as a literal.</span></span> <span data-ttu-id="844a1-214">実行する唯一の解釈は、など、標準の Windows 表記を使用する環境変数の値を置き換えることです `%USERPROFILE%` 。</span><span class="sxs-lookup"><span data-stu-id="844a1-214">The only interpretation it performs is to substitute values for environment variables that use standard Windows notation, such as `%USERPROFILE%`.</span></span>

<span data-ttu-id="844a1-215">ストップ解析シンボルは、次の改行文字またはパイプライン文字まで有効です。</span><span class="sxs-lookup"><span data-stu-id="844a1-215">The stop-parsing symbol is effective only until the next newline or pipeline character.</span></span> <span data-ttu-id="844a1-216">継続文字 () を使用して `` ` `` その効果を拡張したり、コマンド区切り記号 () を使用してその効果を終了したりすることはできません `;` 。</span><span class="sxs-lookup"><span data-stu-id="844a1-216">You cannot use a continuation character (`` ` ``) to extend its effect or use a command delimiter (`;`) to terminate its effect.</span></span>

<span data-ttu-id="844a1-217">たとえば、次のコマンドは、 **Icacls** プログラムを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="844a1-217">For example, the following command calls the **Icacls** program.</span></span>

```powershell
icacls X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="844a1-218">PowerShell 2.0 でこのコマンドを実行するには、エスケープ文字を使用して、PowerShell がかっこを誤って解釈できないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="844a1-218">To run this command in PowerShell 2.0, you must use escape characters to prevent PowerShell from misinterpreting the parentheses.</span></span>

```powershell
icacls X:\VMS /grant Dom\HVAdmin:`(CI`)`(OI`)F
```

<span data-ttu-id="844a1-219">PowerShell 3.0 以降では、ストップ解析シンボルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="844a1-219">Beginning in PowerShell 3.0, you can use the stop-parsing symbol.</span></span>

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="844a1-220">PowerShell は、次のコマンド文字列を **Icacls** プログラムに送信します。</span><span class="sxs-lookup"><span data-stu-id="844a1-220">PowerShell sends the following command string to the **Icacls** program:</span></span>

`X:\VMS /grant Dom\HVAdmin:(CI)(OI)F`

> [!NOTE]
> <span data-ttu-id="844a1-221">ストップ解析シンボルは、Windows プラットフォームでの使用のみを目的としています。</span><span class="sxs-lookup"><span data-stu-id="844a1-221">The stop-parsing symbol only intended for use on Windows platforms.</span></span>

## <a name="see-also"></a><span data-ttu-id="844a1-222">関連項目</span><span class="sxs-lookup"><span data-stu-id="844a1-222">SEE ALSO</span></span>

[<span data-ttu-id="844a1-223">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="844a1-223">about_Command_Syntax</span></span>](about_Command_Syntax.md)
