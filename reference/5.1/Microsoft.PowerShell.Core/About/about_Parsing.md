---
description: PowerShell によるコマンドの解析方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parsing?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parsing
ms.openlocfilehash: d7b5af8c94ad6370c69773d2bc3796bace60ef7c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223360"
---
# <a name="about-parsing"></a><span data-ttu-id="102f5-104">解析の概要</span><span class="sxs-lookup"><span data-stu-id="102f5-104">About Parsing</span></span>

## <a name="short-description"></a><span data-ttu-id="102f5-105">概要</span><span class="sxs-lookup"><span data-stu-id="102f5-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="102f5-106">PowerShell によるコマンドの解析方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="102f5-106">Describes how PowerShell parses commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="102f5-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="102f5-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="102f5-108">コマンドプロンプトでコマンドを入力すると、PowerShell はコマンドテキストを _トークン_ と呼ばれる一連のセグメントに分割し、各トークンの解釈方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="102f5-108">When you enter a command at the command prompt, PowerShell breaks the command text into a series of segments called _tokens_ and then determines how to interpret each token.</span></span>

<span data-ttu-id="102f5-109">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="102f5-109">For example, if you type:</span></span>

```powershell
Write-Host book
```

<span data-ttu-id="102f5-110">PowerShell では、コマンドがとという2つのトークンに分割され、 `Write-Host` `book` 2 つの主要な解析モード (expression モードと argument モード) のいずれかを使用して各トークンが個別に解釈されます。</span><span class="sxs-lookup"><span data-stu-id="102f5-110">PowerShell breaks the command into two tokens, `Write-Host` and `book`, and interprets each token independently using one of two major parsing modes: expression mode and argument mode.</span></span>

> [!NOTE]
> <span data-ttu-id="102f5-111">PowerShell によってコマンド入力が解析されるので、コマンド名をコマンドレットまたはネイティブの実行可能ファイルに解決しようとします。</span><span class="sxs-lookup"><span data-stu-id="102f5-111">As PowerShell parses command input it tries to resolve the command names to cmdlets or native executables.</span></span> <span data-ttu-id="102f5-112">コマンド名に完全に一致するものがない場合、PowerShell は `Get-` 既定の動詞としてコマンドの前に付加します。</span><span class="sxs-lookup"><span data-stu-id="102f5-112">If a command name does not have an exact match, PowerShell prepends `Get-` to the command as a default verb.</span></span> <span data-ttu-id="102f5-113">たとえば、PowerShell はとしてを解析し `Process` `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="102f5-113">For example, PowerShell parses `Process` as `Get-Process`.</span></span> <span data-ttu-id="102f5-114">この機能は、次の理由で使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="102f5-114">It's not recommended to use this feature for the following reasons:</span></span>
>
> - <span data-ttu-id="102f5-115">これは非効率的です。</span><span class="sxs-lookup"><span data-stu-id="102f5-115">It's inefficient.</span></span> <span data-ttu-id="102f5-116">これにより、PowerShell が複数回検索されます。</span><span class="sxs-lookup"><span data-stu-id="102f5-116">This causes PowerShell to search multiple times.</span></span>
> - <span data-ttu-id="102f5-117">同じ名前の外部プログラムが最初に解決されるため、目的のコマンドレットを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="102f5-117">External programs with the same name are resolved first, so you may not execute intended cmdlet.</span></span>
> - <span data-ttu-id="102f5-118">`Get-Help``Get-Command`動詞のない名前は認識されません。</span><span class="sxs-lookup"><span data-stu-id="102f5-118">`Get-Help` and `Get-Command` don't recognize verb-less names.</span></span>

### <a name="expression-mode"></a><span data-ttu-id="102f5-119">式モード</span><span class="sxs-lookup"><span data-stu-id="102f5-119">Expression mode</span></span>

<span data-ttu-id="102f5-120">式モードは、スクリプト言語での値の操作に必要な結合式を使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="102f5-120">Expression mode is intended for combining expressions, required for value manipulation in a scripting language.</span></span> <span data-ttu-id="102f5-121">式は PowerShell 構文の値の表現であり、単純型または複合型にすることができます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="102f5-121">Expressions are representations of values in PowerShell syntax, and can be simple or composite, for example:</span></span>

<span data-ttu-id="102f5-122">リテラル式は、値を直接表現したものです。</span><span class="sxs-lookup"><span data-stu-id="102f5-122">Literal expressions are direct representations of their values:</span></span>

```powershell
'hello', 32
```

<span data-ttu-id="102f5-123">変数式には、参照する変数の値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="102f5-123">Variable expressions carry the value of the variable they reference:</span></span>

```powershell
$x, $script:path
```

<span data-ttu-id="102f5-124">演算子は、評価のために他の式を結合します。</span><span class="sxs-lookup"><span data-stu-id="102f5-124">Operators combine other expressions for evaluation:</span></span>

```powershell
- 12, -not $Quiet, 3 + 7, $input.Length -gt 1
```

- <span data-ttu-id="102f5-125">_文字列リテラル_ は引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="102f5-125">_Character string literals_ must be contained in quotation marks.</span></span>
- <span data-ttu-id="102f5-126">_数値_ は、エスケープされない限り、一連の文字としてではなく、数値として扱われます。</span><span class="sxs-lookup"><span data-stu-id="102f5-126">_Numbers_ are treated as numerical values rather than as a series of characters (unless escaped).</span></span>
- <span data-ttu-id="102f5-127">_演算子_ (やなどの、やなどの二項演算子を含む) `-` `-not` `+` `-gt` は演算子として解釈され、それぞれの引数 (オペランド) に対してそれぞれの操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="102f5-127">_Operators_ , including unary operators like `-` and `-not` and binary operators like `+` and `-gt`, are interpreted as operators and apply their respective operations on their arguments (operands).</span></span>
- <span data-ttu-id="102f5-128">_属性および変換式_ は式として解析され、下位の式 (など) に適用され `[int] '7'` ます。</span><span class="sxs-lookup"><span data-stu-id="102f5-128">_Attribute and conversion expressions_ are parsed as expressions and applied to subordinate expressions, e.g. `[int] '7'`.</span></span>
- <span data-ttu-id="102f5-129">_変数参照_ はその値に評価されますが、 _スプラッティング_ (事前パラメーターセットの貼り付け) は禁止されているため、パーサーエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="102f5-129">_Variable references_ are evaluated to their values but _splatting_ (i.e. pasting prefilled parameter sets) is forbidden and causes a parser error.</span></span>
- <span data-ttu-id="102f5-130">それ以外のものは、呼び出されるコマンドとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="102f5-130">Anything else will be treated as a command to be invoked.</span></span>

### <a name="argument-mode"></a><span data-ttu-id="102f5-131">引数モード</span><span class="sxs-lookup"><span data-stu-id="102f5-131">Argument mode</span></span>

<span data-ttu-id="102f5-132">解析時に、PowerShell は最初に入力を式として解釈しようとします。</span><span class="sxs-lookup"><span data-stu-id="102f5-132">When parsing, PowerShell first looks to interpret input as an expression.</span></span> <span data-ttu-id="102f5-133">ただし、コマンド呼び出しが検出されると、引数モードで解析が続行されます。</span><span class="sxs-lookup"><span data-stu-id="102f5-133">But when a command invocation is encountered, parsing continues in argument mode.</span></span>

<span data-ttu-id="102f5-134">引数モードは、シェル環境でコマンドの引数とパラメーターを解析するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="102f5-134">Argument mode is designed for parsing arguments and parameters for commands in a shell environment.</span></span> <span data-ttu-id="102f5-135">次のいずれかの構文を使用しない限り、すべての入力は展開可能な文字列として扱われます。</span><span class="sxs-lookup"><span data-stu-id="102f5-135">All input is treated as an expandable string unless it uses one of the following syntaxes:</span></span>

- <span data-ttu-id="102f5-136">ドル記号 ( `$` ) は変数参照を開始します (その後に有効な変数名が続く場合のみ)。それ以外の場合は、展開可能な文字列の一部として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="102f5-136">Dollar sign (`$`) begins a variable reference (only if it is followed by a valid variable name, otherwise it is interpreted as part of the expandable string).</span></span>
- <span data-ttu-id="102f5-137">引用符 ( `'` および `"` ) の開始文字列値</span><span class="sxs-lookup"><span data-stu-id="102f5-137">Quotation marks (`'` and `"`) begin string values</span></span>
- <span data-ttu-id="102f5-138">かっこ ( `(` と `)` ) 区別新しい式です。</span><span class="sxs-lookup"><span data-stu-id="102f5-138">Parentheses (`(` and `)`) demarcate new expressions.</span></span>
- <span data-ttu-id="102f5-139">部分式演算子 ( `$(` ... `)` ) 区分埋め込み式。</span><span class="sxs-lookup"><span data-stu-id="102f5-139">Subexpression operator (`$(`…`)`) demarcates embedded expressions.</span></span>
- <span data-ttu-id="102f5-140">中かっこ ( `{` と `}` ) 区別は、新しいスクリプトブロックを作成します。</span><span class="sxs-lookup"><span data-stu-id="102f5-140">Braces (`{` and `}`) demarcate new script blocks.</span></span>
- <span data-ttu-id="102f5-141">最初のアットマーク ( `@` ) `@args` は、スプラッティング ()、配列 ()、 `@(1,2,3)` ハッシュテーブル () などの式の構文を開始し `@{a=1;b=2}` ます。</span><span class="sxs-lookup"><span data-stu-id="102f5-141">Initial at sign (`@`) begins expression syntaxes such as splatting (`@args`), arrays (`@(1,2,3)`) and hash tables (`@{a=1;b=2}`).</span></span>
- <span data-ttu-id="102f5-142">コンマ ( `,` ) は、配列として渡されるリストを導入します。ただし、呼び出されるコマンドがネイティブアプリケーションである場合を除きます。この場合、拡張可能な文字列の一部として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="102f5-142">Commas (`,`) introduce lists passed as arrays, except when the command to be called is a native application, in which case they are interpreted as part of the expandable string.</span></span> <span data-ttu-id="102f5-143">最初、連続、または末尾のコンマはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="102f5-143">Initial, consecutive or trailing commas are not supported.</span></span>

<span data-ttu-id="102f5-144">埋め込み式の値は、文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="102f5-144">Values of embedded expressions are converted to strings.</span></span>

<span data-ttu-id="102f5-145">次の表に、式モードおよび引数モードで処理される値の例と、それらの値の評価を示します。</span><span class="sxs-lookup"><span data-stu-id="102f5-145">The following table provides several examples of values processed in expression mode and argument mode and the evaluation of those values.</span></span> <span data-ttu-id="102f5-146">変数の値がであることを前提として `a` `4` います。</span><span class="sxs-lookup"><span data-stu-id="102f5-146">We assume that the value of the variable `a` is `4`.</span></span>

|       <span data-ttu-id="102f5-147">例</span><span class="sxs-lookup"><span data-stu-id="102f5-147">Example</span></span>        |    <span data-ttu-id="102f5-148">モード</span><span class="sxs-lookup"><span data-stu-id="102f5-148">Mode</span></span>    |      <span data-ttu-id="102f5-149">結果</span><span class="sxs-lookup"><span data-stu-id="102f5-149">Result</span></span>       |
| -------------------- | ---------- | ----------------- |
| `2`                  | <span data-ttu-id="102f5-150">式</span><span class="sxs-lookup"><span data-stu-id="102f5-150">Expression</span></span> | <span data-ttu-id="102f5-151">2 (整数)</span><span class="sxs-lookup"><span data-stu-id="102f5-151">2 (integer)</span></span>       |
| `` `2``              | <span data-ttu-id="102f5-152">Expression</span><span class="sxs-lookup"><span data-stu-id="102f5-152">Expression</span></span> | <span data-ttu-id="102f5-153">"2" (コマンド)</span><span class="sxs-lookup"><span data-stu-id="102f5-153">"2" (command)</span></span>     |
| `echo 2`             | <span data-ttu-id="102f5-154">Expression</span><span class="sxs-lookup"><span data-stu-id="102f5-154">Expression</span></span> | <span data-ttu-id="102f5-155">2 (整数)</span><span class="sxs-lookup"><span data-stu-id="102f5-155">2 (integer)</span></span>       |
| `2+2`                | <span data-ttu-id="102f5-156">Expression</span><span class="sxs-lookup"><span data-stu-id="102f5-156">Expression</span></span> | <span data-ttu-id="102f5-157">4 (整数)</span><span class="sxs-lookup"><span data-stu-id="102f5-157">4 (integer)</span></span>       |
| `echo 2+2`           | <span data-ttu-id="102f5-158">引数</span><span class="sxs-lookup"><span data-stu-id="102f5-158">Argument</span></span>   | <span data-ttu-id="102f5-159">"2 + 2" (文字列)</span><span class="sxs-lookup"><span data-stu-id="102f5-159">"2+2" (string)</span></span>    |
| `echo(2+2)`          | <span data-ttu-id="102f5-160">Expression</span><span class="sxs-lookup"><span data-stu-id="102f5-160">Expression</span></span> | <span data-ttu-id="102f5-161">4 (整数)</span><span class="sxs-lookup"><span data-stu-id="102f5-161">4 (integer)</span></span>       |
| `$a`                 | <span data-ttu-id="102f5-162">Expression</span><span class="sxs-lookup"><span data-stu-id="102f5-162">Expression</span></span> | <span data-ttu-id="102f5-163">4 (整数)</span><span class="sxs-lookup"><span data-stu-id="102f5-163">4 (integer)</span></span>       |
| `echo $a`            | <span data-ttu-id="102f5-164">Expression</span><span class="sxs-lookup"><span data-stu-id="102f5-164">Expression</span></span> | <span data-ttu-id="102f5-165">4 (整数)</span><span class="sxs-lookup"><span data-stu-id="102f5-165">4 (integer)</span></span>       |
| `$a+2`               | <span data-ttu-id="102f5-166">Expression</span><span class="sxs-lookup"><span data-stu-id="102f5-166">Expression</span></span> | <span data-ttu-id="102f5-167">6 (整数)</span><span class="sxs-lookup"><span data-stu-id="102f5-167">6 (integer)</span></span>       |
| `echo $a+2`          | <span data-ttu-id="102f5-168">引数</span><span class="sxs-lookup"><span data-stu-id="102f5-168">Argument</span></span>   | <span data-ttu-id="102f5-169">4 + 2 (文字列)</span><span class="sxs-lookup"><span data-stu-id="102f5-169">4+2 (string)</span></span>      |
| `$-`                 | <span data-ttu-id="102f5-170">引数</span><span class="sxs-lookup"><span data-stu-id="102f5-170">Argument</span></span>   | <span data-ttu-id="102f5-171">"$-" (コマンド)</span><span class="sxs-lookup"><span data-stu-id="102f5-171">"$-" (command)</span></span>    |
| `echo $-`            | <span data-ttu-id="102f5-172">引数</span><span class="sxs-lookup"><span data-stu-id="102f5-172">Argument</span></span>   | <span data-ttu-id="102f5-173">"$-" (文字列)</span><span class="sxs-lookup"><span data-stu-id="102f5-173">"$-" (string)</span></span>     |
| `a$a`                | <span data-ttu-id="102f5-174">Expression</span><span class="sxs-lookup"><span data-stu-id="102f5-174">Expression</span></span> | <span data-ttu-id="102f5-175">"a $ a" (コマンド)</span><span class="sxs-lookup"><span data-stu-id="102f5-175">"a$a" (command)</span></span>   |
| `echo a$a`           | <span data-ttu-id="102f5-176">引数</span><span class="sxs-lookup"><span data-stu-id="102f5-176">Argument</span></span>   | <span data-ttu-id="102f5-177">"a4" (文字列)</span><span class="sxs-lookup"><span data-stu-id="102f5-177">"a4" (string)</span></span>     |
| `a'$a'`              | <span data-ttu-id="102f5-178">Expression</span><span class="sxs-lookup"><span data-stu-id="102f5-178">Expression</span></span> | <span data-ttu-id="102f5-179">"a $ a" (コマンド)</span><span class="sxs-lookup"><span data-stu-id="102f5-179">"a$a" (command)</span></span>   |
| `echo a'$a'`         | <span data-ttu-id="102f5-180">引数</span><span class="sxs-lookup"><span data-stu-id="102f5-180">Argument</span></span>   | <span data-ttu-id="102f5-181">"a $ a" (文字列)</span><span class="sxs-lookup"><span data-stu-id="102f5-181">"a$a" (string)</span></span>    |
| `a"$a"`              | <span data-ttu-id="102f5-182">Expression</span><span class="sxs-lookup"><span data-stu-id="102f5-182">Expression</span></span> | <span data-ttu-id="102f5-183">"a $ a" (コマンド)</span><span class="sxs-lookup"><span data-stu-id="102f5-183">"a$a" (command)</span></span>   |
| `echo a"$a"`         | <span data-ttu-id="102f5-184">引数</span><span class="sxs-lookup"><span data-stu-id="102f5-184">Argument</span></span>   | <span data-ttu-id="102f5-185">"a4" (文字列)</span><span class="sxs-lookup"><span data-stu-id="102f5-185">"a4" (string)</span></span>     |
| `a$(2)`              | <span data-ttu-id="102f5-186">Expression</span><span class="sxs-lookup"><span data-stu-id="102f5-186">Expression</span></span> | <span data-ttu-id="102f5-187">"a $ (2)" (コマンド)</span><span class="sxs-lookup"><span data-stu-id="102f5-187">"a$(2)" (command)</span></span> |
| `echo a$(2)`         | <span data-ttu-id="102f5-188">引数</span><span class="sxs-lookup"><span data-stu-id="102f5-188">Argument</span></span>   | <span data-ttu-id="102f5-189">"a2" (文字列)</span><span class="sxs-lookup"><span data-stu-id="102f5-189">"a2" (string)</span></span>     |

<span data-ttu-id="102f5-190">すべてのトークンは、ブール値や文字列など、何らかの種類のオブジェクトとして解釈できます。</span><span class="sxs-lookup"><span data-stu-id="102f5-190">Every token can be interpreted as some kind of object type, such as Boolean or string.</span></span> <span data-ttu-id="102f5-191">PowerShell は、式からオブジェクトの種類を特定しようとします。</span><span class="sxs-lookup"><span data-stu-id="102f5-191">PowerShell attempts to determine the object type from the expression.</span></span>
<span data-ttu-id="102f5-192">オブジェクトの種類は、コマンドが想定するパラメーターの型と、引数を正しい型に変換する方法を PowerShell が認識しているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="102f5-192">The object type depends on the type of parameter a command expects and on whether PowerShell knows how to convert the argument to the correct type.</span></span> <span data-ttu-id="102f5-193">次の表に、式によって返される値に割り当てられる型の例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="102f5-193">The following table shows several examples of the types assigned to values returned by the expressions.</span></span>

|       <span data-ttu-id="102f5-194">例</span><span class="sxs-lookup"><span data-stu-id="102f5-194">Example</span></span>          |    <span data-ttu-id="102f5-195">モード</span><span class="sxs-lookup"><span data-stu-id="102f5-195">Mode</span></span>    |     <span data-ttu-id="102f5-196">結果</span><span class="sxs-lookup"><span data-stu-id="102f5-196">Result</span></span>      |
| ---------------------- | ---------- | --------------- |
| `Write-Output !1`      | <span data-ttu-id="102f5-197">引数</span><span class="sxs-lookup"><span data-stu-id="102f5-197">argument</span></span>   | <span data-ttu-id="102f5-198">"! 1" (文字列)</span><span class="sxs-lookup"><span data-stu-id="102f5-198">"!1" (string)</span></span>   |
| `Write-Output (!1)`    | <span data-ttu-id="102f5-199">expression</span><span class="sxs-lookup"><span data-stu-id="102f5-199">expression</span></span> | <span data-ttu-id="102f5-200">False (ブール値)</span><span class="sxs-lookup"><span data-stu-id="102f5-200">False (Boolean)</span></span> |
| `Write-Output (2)`     | <span data-ttu-id="102f5-201">expression</span><span class="sxs-lookup"><span data-stu-id="102f5-201">expression</span></span> | <span data-ttu-id="102f5-202">2 (整数)</span><span class="sxs-lookup"><span data-stu-id="102f5-202">2 (integer)</span></span>     |
| `Set-Variable AB A,B`  | <span data-ttu-id="102f5-203">引数</span><span class="sxs-lookup"><span data-stu-id="102f5-203">argument</span></span>   | <span data-ttu-id="102f5-204">' A '、' B ' (配列)</span><span class="sxs-lookup"><span data-stu-id="102f5-204">'A','B' (array)</span></span> |
| `CMD /CECHO A,B`       | <span data-ttu-id="102f5-205">引数</span><span class="sxs-lookup"><span data-stu-id="102f5-205">argument</span></span>   | <span data-ttu-id="102f5-206">' A, B ' (文字列)</span><span class="sxs-lookup"><span data-stu-id="102f5-206">'A,B' (string)</span></span>  |
| `CMD /CECHO $AB`       | <span data-ttu-id="102f5-207">expression</span><span class="sxs-lookup"><span data-stu-id="102f5-207">expression</span></span> | <span data-ttu-id="102f5-208">' A '、' B ' (配列)</span><span class="sxs-lookup"><span data-stu-id="102f5-208">'A','B' (array)</span></span> |
| `CMD /CECHO :$AB`      | <span data-ttu-id="102f5-209">引数</span><span class="sxs-lookup"><span data-stu-id="102f5-209">argument</span></span>   | <span data-ttu-id="102f5-210">': A B ' (文字列)</span><span class="sxs-lookup"><span data-stu-id="102f5-210">':A B' (string)</span></span> |

<span data-ttu-id="102f5-211">Powershell 3.0 で導入された解析の中止記号 () は、powershell `--%` コマンドまたは式として入力を解釈しないように powershell に指示します。</span><span class="sxs-lookup"><span data-stu-id="102f5-211">The stop-parsing symbol (`--%`), introduced in PowerShell 3.0, directs PowerShell to refrain from interpreting input as PowerShell commands or expressions.</span></span>

<span data-ttu-id="102f5-212">PowerShell で実行可能プログラムを呼び出す場合は、プログラムの引数の前にストップ解析のシンボルを配置します。</span><span class="sxs-lookup"><span data-stu-id="102f5-212">When calling an executable program in PowerShell, place the stop-parsing symbol before the program arguments.</span></span> <span data-ttu-id="102f5-213">この手法は、誤って解釈されないようにエスケープ文字を使用するよりもはるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="102f5-213">This technique is much easier than using escape characters to prevent misinterpretation.</span></span>

<span data-ttu-id="102f5-214">ストップ解析シンボルが検出されると、PowerShell は行の残りの文字をリテラルとして扱います。</span><span class="sxs-lookup"><span data-stu-id="102f5-214">When it encounters a stop-parsing symbol, PowerShell treats the remaining characters in the line as a literal.</span></span> <span data-ttu-id="102f5-215">実行する唯一の解釈は、など、標準の Windows 表記を使用する環境変数の値を置き換えることです `%USERPROFILE%` 。</span><span class="sxs-lookup"><span data-stu-id="102f5-215">The only interpretation it performs is to substitute values for environment variables that use standard Windows notation, such as `%USERPROFILE%`.</span></span>

<span data-ttu-id="102f5-216">ストップ解析シンボルは、次の改行文字またはパイプライン文字まで有効です。</span><span class="sxs-lookup"><span data-stu-id="102f5-216">The stop-parsing symbol is effective only until the next newline or pipeline character.</span></span> <span data-ttu-id="102f5-217">継続文字 () を使用して `` ` `` その効果を拡張したり、コマンド区切り記号 () を使用してその効果を終了したりすることはできません `;` 。</span><span class="sxs-lookup"><span data-stu-id="102f5-217">You cannot use a continuation character (`` ` ``) to extend its effect or use a command delimiter (`;`) to terminate its effect.</span></span>

<span data-ttu-id="102f5-218">たとえば、次のコマンドは、 **Icacls** プログラムを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="102f5-218">For example, the following command calls the **Icacls** program.</span></span>

```powershell
icacls X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="102f5-219">PowerShell 2.0 でこのコマンドを実行するには、エスケープ文字を使用して、PowerShell がかっこを誤って解釈できないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="102f5-219">To run this command in PowerShell 2.0, you must use escape characters to prevent PowerShell from misinterpreting the parentheses.</span></span>

```powershell
icacls X:\VMS /grant Dom\HVAdmin:`(CI`)`(OI`)F
```

<span data-ttu-id="102f5-220">PowerShell 3.0 以降では、ストップ解析シンボルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="102f5-220">Beginning in PowerShell 3.0, you can use the stop-parsing symbol.</span></span>

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="102f5-221">PowerShell は、次のコマンド文字列を **Icacls** プログラムに送信します。</span><span class="sxs-lookup"><span data-stu-id="102f5-221">PowerShell sends the following command string to the **Icacls** program:</span></span>

`X:\VMS /grant Dom\HVAdmin:(CI)(OI)F`

## <a name="see-also"></a><span data-ttu-id="102f5-222">関連項目</span><span class="sxs-lookup"><span data-stu-id="102f5-222">SEE ALSO</span></span>

[<span data-ttu-id="102f5-223">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="102f5-223">about_Command_Syntax</span></span>](about_Command_Syntax.md)
