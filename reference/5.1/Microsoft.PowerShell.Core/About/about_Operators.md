---
description: PowerShell でサポートされている演算子について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 11/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operators
ms.openlocfilehash: b783d2cb76fe8a0a66ec77b67ef915f3b78def04
ms.sourcegitcommit: 768816a5c05cc2d07ffd84bed95b0499f4b49f2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2020
ms.locfileid: "94483003"
---
# <a name="about-operators"></a><span data-ttu-id="6fee1-104">演算子について</span><span class="sxs-lookup"><span data-stu-id="6fee1-104">About Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="6fee1-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="6fee1-105">Short description</span></span>
<span data-ttu-id="6fee1-106">PowerShell でサポートされている演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-106">Describes the operators that are supported by PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="6fee1-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="6fee1-107">Long description</span></span>

<span data-ttu-id="6fee1-108">演算子は、コマンドまたは式で使用できる言語要素です。</span><span class="sxs-lookup"><span data-stu-id="6fee1-108">An operator is a language element that you can use in a command or expression.</span></span>
<span data-ttu-id="6fee1-109">PowerShell では、値の操作に役立ついくつかの種類の演算子がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6fee1-109">PowerShell supports several types of operators to help you manipulate values.</span></span>

### <a name="arithmetic-operators"></a><span data-ttu-id="6fee1-110">算術演算子</span><span class="sxs-lookup"><span data-stu-id="6fee1-110">Arithmetic Operators</span></span>

<span data-ttu-id="6fee1-111">算術演算子 (、、、、) を使用して、 `+` `-` `*` `/` `%` コマンドまたは式の値を計算します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-111">Use arithmetic operators (`+`, `-`, `*`, `/`, `%`) to calculate values in a command or expression.</span></span> <span data-ttu-id="6fee1-112">これらの演算子を使用すると、値の加算、減算、乗算、除算を行ったり、除算演算の剰余 (剰余) を計算したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-112">With these operators, you can add, subtract, multiply, or divide values, and calculate the remainder (modulus) of a division operation.</span></span>

<span data-ttu-id="6fee1-113">加算演算子は要素を連結します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-113">The addition operator concatenates elements.</span></span> <span data-ttu-id="6fee1-114">乗算演算子は、各要素の指定された数のコピーを返します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-114">The multiplication operator returns the specified number of copies of each element.</span></span> <span data-ttu-id="6fee1-115">算術演算子は、、、、、およびの各配列を実装するすべての .net 型で使用できます `Int` `String` `DateTime` `Hashtable` 。</span><span class="sxs-lookup"><span data-stu-id="6fee1-115">You can use arithmetic operators on any .NET type that implements them, such as: `Int`, `String`, `DateTime`, `Hashtable`, and Arrays.</span></span>

<span data-ttu-id="6fee1-116">ビットごとの演算子 ( `-band` 、、 `-bor` 、、 `-bxor` `-bnot` `-shl` 、 `-shr` ) は、値のビットパターンを操作します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-116">Bitwise operators (`-band`, `-bor`, `-bxor`, `-bnot`, `-shl`, `-shr`) manipulate the bit patterns in values.</span></span>

<span data-ttu-id="6fee1-117">詳細については、「 [about_Arithmetic_Operators](about_Arithmetic_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fee1-117">For more information, see [about_Arithmetic_Operators](about_Arithmetic_Operators.md).</span></span>

### <a name="assignment-operators"></a><span data-ttu-id="6fee1-118">代入演算子</span><span class="sxs-lookup"><span data-stu-id="6fee1-118">Assignment Operators</span></span>

<span data-ttu-id="6fee1-119">代入演算子 ( `=` 、、 `+=` 、 `-=` 、 `*=` 、) を使用して `/=` `%=` 、変数に値を代入、変更、または追加します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-119">Use assignment operators (`=`, `+=`, `-=`, `*=`, `/=`, `%=`) to assign, change, or append values to variables.</span></span> <span data-ttu-id="6fee1-120">算術演算子を代入と組み合わせて、算術演算の結果を変数に代入することができます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-120">You can combine arithmetic operators with assignment to assign the result of the arithmetic operation to a variable.</span></span>

<span data-ttu-id="6fee1-121">詳細については、「 [about_Assignment_Operators](about_Assignment_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fee1-121">For more information, see [about_Assignment_Operators](about_Assignment_Operators.md).</span></span>

### <a name="comparison-operators"></a><span data-ttu-id="6fee1-122">比較演算子</span><span class="sxs-lookup"><span data-stu-id="6fee1-122">Comparison Operators</span></span>

<span data-ttu-id="6fee1-123">比較演算子 ( `-eq` 、、 `-ne` 、 `-gt` 、 `-lt` `-le` 、) を使用して、 `-ge` 値とテスト条件を比較します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-123">Use comparison operators (`-eq`, `-ne`, `-gt`, `-lt`, `-le`, `-ge`) to compare values and test conditions.</span></span> <span data-ttu-id="6fee1-124">たとえば、2つの文字列値を比較して、両者が等しいかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-124">For example, you can compare two string values to determine whether they are equal.</span></span>

<span data-ttu-id="6fee1-125">比較演算子には、テキストのパターンを検索または置換する演算子も含まれます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-125">The comparison operators also include operators that find or replace patterns in text.</span></span> <span data-ttu-id="6fee1-126">( `-match` , `-notmatch` ,) 演算子は、 `-replace` 正規表現を使用し、( `-like` , `-notlike` ) ワイルドカードを使用し `*` ます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-126">The (`-match`, `-notmatch`, `-replace`) operators use regular expressions, and (`-like`, `-notlike`) use wildcards `*`.</span></span>

<span data-ttu-id="6fee1-127">コンテインメント比較演算子は、テスト値が参照セット (、、、) に表示されるかどうかを決定 `-in` `-notin` `-contains` `-notcontains` します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-127">Containment comparison operators determine whether a test value appears in a reference set (`-in`, `-notin`, `-contains`, `-notcontains`).</span></span>

<span data-ttu-id="6fee1-128">型の比較演算子 ( `-is` , `-isnot` ) は、オブジェクトが特定の型であるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-128">Type comparison operators (`-is`, `-isnot`) determine whether an object is of a given type.</span></span>

<span data-ttu-id="6fee1-129">詳細については、「 [about_Comparison_Operators](about_Comparison_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fee1-129">For more information, see [about_Comparison_Operators](about_Comparison_Operators.md).</span></span>

### <a name="logical-operators"></a><span data-ttu-id="6fee1-130">論理演算子</span><span class="sxs-lookup"><span data-stu-id="6fee1-130">Logical Operators</span></span>

<span data-ttu-id="6fee1-131">論理演算子 (、、、、) を使用して、 `-and` `-or` `-xor` `-not` `!` 条件付きステートメントを1つの複雑な条件付きステートメントに接続します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-131">Use logical operators (`-and`, `-or`, `-xor`, `-not`, `!`) to connect conditional statements into a single complex conditional.</span></span> <span data-ttu-id="6fee1-132">たとえば、論理演算子を使用すると、 `-and` 2 つの異なる条件を持つオブジェクトフィルターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-132">For example, you can use a logical `-and` operator to create an object filter with two different conditions.</span></span>

<span data-ttu-id="6fee1-133">詳細については、「 [about_Logical_Operators](about_logical_operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fee1-133">For more information, see [about_Logical_Operators](about_logical_operators.md).</span></span>

### <a name="redirection-operators"></a><span data-ttu-id="6fee1-134">リダイレクト演算子</span><span class="sxs-lookup"><span data-stu-id="6fee1-134">Redirection Operators</span></span>

<span data-ttu-id="6fee1-135">`>` `>>` `2>` `2>>` `2>&1` コマンドまたは式の出力をテキストファイルに送信するには、リダイレクト演算子 (、、、、および) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-135">Use redirection operators (`>`, `>>`, `2>`, `2>>`, and `2>&1`) to send the output of a command or expression to a text file.</span></span> <span data-ttu-id="6fee1-136">リダイレクト演算子はコマンドレットのように機能し `Out-File` ますが (パラメーターなし)、指定されたファイルにエラー出力をリダイレクトすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-136">The redirection operators work like the `Out-File` cmdlet (without parameters) but they also let you redirect error output to specified files.</span></span> <span data-ttu-id="6fee1-137">コマンドレットを使用して、 `Tee-Object` 出力をリダイレクトすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-137">You can also use the `Tee-Object` cmdlet to redirect output.</span></span>

<span data-ttu-id="6fee1-138">詳細については、「」を参照してください [about_Redirection](about_Redirection.md)</span><span class="sxs-lookup"><span data-stu-id="6fee1-138">For more information, see [about_Redirection](about_Redirection.md)</span></span>

### <a name="split-and-join-operators"></a><span data-ttu-id="6fee1-139">Split 演算子と Join 演算子</span><span class="sxs-lookup"><span data-stu-id="6fee1-139">Split and Join Operators</span></span>

<span data-ttu-id="6fee1-140">`-split`演算子と演算子は、サブ `-join` ストリングを分割して結合します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-140">The `-split` and `-join` operators divide and combine substrings.</span></span> <span data-ttu-id="6fee1-141">演算子は、 `-split` 文字列を部分文字列に分割します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-141">The `-split` operator splits a string into substrings.</span></span> <span data-ttu-id="6fee1-142">演算子は、 `-join` 複数の文字列を連結して1つの文字列にします。</span><span class="sxs-lookup"><span data-stu-id="6fee1-142">The `-join` operator concatenates multiple strings into a single string.</span></span>

<span data-ttu-id="6fee1-143">詳細については、「 [about_Split](about_Split.md) 」および「 [about_Join](about_Join.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fee1-143">For more information, see [about_Split](about_Split.md) and [about_Join](about_Join.md).</span></span>

### <a name="type-operators"></a><span data-ttu-id="6fee1-144">型演算子</span><span class="sxs-lookup"><span data-stu-id="6fee1-144">Type Operators</span></span>

<span data-ttu-id="6fee1-145">`-is` `-isnot` `-as` オブジェクトの .NET Framework 型を検索または変更するには、型演算子 (、、) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-145">Use the type operators (`-is`, `-isnot`, `-as`) to find or change the .NET Framework type of an object.</span></span>

<span data-ttu-id="6fee1-146">詳細については、「 [about_Type_Operators](about_Type_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fee1-146">For more information, see [about_Type_Operators](about_Type_Operators.md).</span></span>

### <a name="unary-operators"></a><span data-ttu-id="6fee1-147">単項演算子</span><span class="sxs-lookup"><span data-stu-id="6fee1-147">Unary Operators</span></span>

<span data-ttu-id="6fee1-148">単項演算子を使用して、変数またはオブジェクトのプロパティをインクリメントまたはデクリメントし、整数を正または負の数値に設定します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-148">Use unary operators to increment or decrement variables or object properties and to set integers to positive or negative numbers.</span></span> <span data-ttu-id="6fee1-149">たとえば、変数をからにインクリメントするには `$a` `9` `10` 、「」と入力し `$a++` ます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-149">For example, to increment the variable `$a` from `9` to `10`, you type `$a++`.</span></span>

### <a name="special-operators"></a><span data-ttu-id="6fee1-150">特別な演算子</span><span class="sxs-lookup"><span data-stu-id="6fee1-150">Special Operators</span></span>

<span data-ttu-id="6fee1-151">特別な演算子には、他のどのオペレーターグループにも適合しない特定のユースケースがあります。</span><span class="sxs-lookup"><span data-stu-id="6fee1-151">Special operators have specific use-cases that do not fit into any other operator group.</span></span> <span data-ttu-id="6fee1-152">たとえば、特殊な演算子を使用すると、コマンドの実行、値のデータ型の変更、または配列からの要素の取得を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-152">For example, special operators allow you to run commands, change a value's data type, or retrieve elements from an array.</span></span>

#### <a name="grouping-operator--"></a><span data-ttu-id="6fee1-153">グループ化演算子 `( )`</span><span class="sxs-lookup"><span data-stu-id="6fee1-153">Grouping operator `( )`</span></span>

<span data-ttu-id="6fee1-154">他の言語と同様に、は `(...)` 式の演算子の優先順位をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="6fee1-154">As in other languages, `(...)` serves to override operator precedence in expressions.</span></span> <span data-ttu-id="6fee1-155">例: `(1 + 2) / 3`</span><span class="sxs-lookup"><span data-stu-id="6fee1-155">For example: `(1 + 2) / 3`</span></span>

<span data-ttu-id="6fee1-156">ただし、PowerShell には追加の動作があります。</span><span class="sxs-lookup"><span data-stu-id="6fee1-156">However, in PowerShell, there are additional behaviors.</span></span>

- <span data-ttu-id="6fee1-157">`(...)`_コマンド_ からの出力を式に参加させることができます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-157">`(...)` allows you to let output from a _command_ participate in an expression.</span></span> <span data-ttu-id="6fee1-158">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-158">For example:</span></span>

  ```powershell
  PS> (Get-Item *.txt).Count -gt 10
  True
  ```

- <span data-ttu-id="6fee1-159">パイプラインの最初のセグメントとして使用する場合は、コマンドまたは式をかっこで囲むことで、式の結果を _列挙_ することができます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-159">When used as the first segment of a pipeline, wrapping a command or expression in parentheses invariably causes _enumeration_ of the expression result.</span></span> <span data-ttu-id="6fee1-160">かっこによって _コマンド_ がラップされている場合は、パイプラインを介して結果が送信される前に、 _メモリに収集_ されたすべての出力を使用して完了します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-160">If the parentheses wrap a _command_ , it is run to completion with all output _collected in memory_ before the results are sent through the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="6fee1-161">コマンドをかっこで囲むと、囲まれた `$?` `$true` コマンド自体がに設定されている場合でも、自動変数がに設定され `$?` `$false` ます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-161">Wrapping a command in parentheses causes the automatic variable `$?` to be set to `$true`, even when the enclosed command itself set `$?` to `$false`.</span></span>
> <span data-ttu-id="6fee1-162">たとえば、は `(Get-Item /Nosuch); $?` 予期せず **True** を生成します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-162">For example, `(Get-Item /Nosuch); $?` unexpectedly yields **True**.</span></span> <span data-ttu-id="6fee1-163">の詳細について `$?` は、「 [about_Automatic_Variables](about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fee1-163">For more information about `$?`, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

#### <a name="subexpression-operator--"></a><span data-ttu-id="6fee1-164">部分式演算子 `$( )`</span><span class="sxs-lookup"><span data-stu-id="6fee1-164">Subexpression operator `$( )`</span></span>

<span data-ttu-id="6fee1-165">1つ以上のステートメントの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-165">Returns the result of one or more statements.</span></span> <span data-ttu-id="6fee1-166">1つの結果に対して、はスカラーを返します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-166">For a single result, returns a scalar.</span></span> <span data-ttu-id="6fee1-167">複数の結果に対して、は配列を返します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-167">For multiple results, returns an array.</span></span> <span data-ttu-id="6fee1-168">別の式の中で式を使用する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-168">Use this when you want to use an expression within another expression.</span></span> <span data-ttu-id="6fee1-169">たとえば、コマンドの結果を文字列式に埋め込むには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-169">For example, to embed the results of command in a string expression.</span></span>

```powershell
PS> "Today is $(Get-Date)"
Today is 12/02/2019 13:15:20

PS> "Folder list: $((dir c:\ -dir).Name -join ', ')"
Folder list: Program Files, Program Files (x86), Users, Windows
```

#### <a name="array-subexpression-operator--"></a><span data-ttu-id="6fee1-170">配列の部分式演算子 `@( )`</span><span class="sxs-lookup"><span data-stu-id="6fee1-170">Array subexpression operator `@( )`</span></span>

<span data-ttu-id="6fee1-171">1つ以上のステートメントの結果を配列として返します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-171">Returns the result of one or more statements as an array.</span></span> <span data-ttu-id="6fee1-172">項目が1つしかない場合、配列にはメンバーが1つだけ含まれます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-172">If there is only one item, the array has only one member.</span></span>

```powershell
@(Get-CimInstance win32_logicalDisk)
```

#### <a name="hash-table-literal-syntax-"></a><span data-ttu-id="6fee1-173">ハッシュテーブルリテラルの構文 `@{}`</span><span class="sxs-lookup"><span data-stu-id="6fee1-173">Hash table literal syntax `@{}`</span></span>

<span data-ttu-id="6fee1-174">配列の部分式と同様に、この構文はハッシュテーブルを宣言するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-174">Similar to the array subexpression, this syntax is used to declare a hash table.</span></span>
<span data-ttu-id="6fee1-175">詳細については、「 [about_Hash_Tables](about_Hash_Tables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fee1-175">For more information, see [about_Hash_Tables](about_Hash_Tables.md).</span></span>

#### <a name="call-operator-"></a><span data-ttu-id="6fee1-176">Call 演算子 `&`</span><span class="sxs-lookup"><span data-stu-id="6fee1-176">Call operator `&`</span></span>

<span data-ttu-id="6fee1-177">コマンド、スクリプト、またはスクリプトブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-177">Runs a command, script, or script block.</span></span> <span data-ttu-id="6fee1-178">呼び出し演算子 ("呼び出し演算子" とも呼ばれます) を使用すると、変数に格納され、文字列またはスクリプトブロックによって表されるコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-178">The call operator, also known as the "invocation operator", lets you run commands that are stored in variables and represented by strings or script blocks.</span></span> <span data-ttu-id="6fee1-179">呼び出し演算子は、子スコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-179">The call operator executes in a child scope.</span></span> <span data-ttu-id="6fee1-180">スコープの詳細については、「 [about_Scopes](about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fee1-180">For more about scopes, see [about_Scopes](about_Scopes.md).</span></span>

<span data-ttu-id="6fee1-181">この例では、コマンドを文字列に格納し、call 演算子を使用して実行します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-181">This example stores a command in a string and executes it using the call operator.</span></span>

```
PS> $c = "get-executionpolicy"
PS> $c
get-executionpolicy
PS> & $c
AllSigned
```

<span data-ttu-id="6fee1-182">呼び出し演算子は、文字列を解析しません。</span><span class="sxs-lookup"><span data-stu-id="6fee1-182">The call operator does not parse strings.</span></span> <span data-ttu-id="6fee1-183">これは、call 演算子を使用するときに、文字列内のコマンドパラメーターを使用できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-183">This means that you cannot use command parameters within a string when you use the call operator.</span></span>

```
PS> $c = "Get-Service -Name Spooler"
PS> $c
Get-Service -Name Spooler
PS> & $c
& : The term 'Get-Service -Name Spooler' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of
the name, or if a path was included, verify that the path is correct and
try again.
At line:1 char:2
+ & $c
+  ~~
    + CategoryInfo          : ObjectNotFound: (Get-Service -Name Spooler:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="6fee1-184">呼び出し演算子を使用する [と、解析](xref:Microsoft.PowerShell.Utility.Invoke-Expression) エラーを発生させるコードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-184">The [Invoke-Expression](xref:Microsoft.PowerShell.Utility.Invoke-Expression) cmdlet can execute code that causes parsing errors when using the call operator.</span></span>

```
PS> & "1+1"
& : The term '1+1' is not recognized as the name of a cmdlet, function, script
file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:2
+ & "1+1"
+  ~~~~~
    + CategoryInfo          : ObjectNotFound: (1+1:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
PS> Invoke-Expression "1+1"
2
```

<span data-ttu-id="6fee1-185">Call 演算子を使用して、ファイル名を使用してスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-185">You can use the call operator to execute scripts using their filenames.</span></span> <span data-ttu-id="6fee1-186">次の例では、スペースを含むスクリプトファイル名を示しています。</span><span class="sxs-lookup"><span data-stu-id="6fee1-186">The example below shows a script filename that contains spaces.</span></span> <span data-ttu-id="6fee1-187">スクリプトを実行しようとすると、PowerShell によって、ファイル名を含む引用符で囲まれた文字列の内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-187">When you try to execute the script, PowerShell instead displays the contents of the quoted string containing the filename.</span></span> <span data-ttu-id="6fee1-188">Call 演算子を使用すると、ファイル名を含む文字列の内容を実行できます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-188">The call operator allows you to execute the contents of the string containing the filename.</span></span>

```
PS C:\Scripts> Get-ChildItem

    Directory: C:\Scripts


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/28/2018   1:36 PM             58 script name with spaces.ps1

PS C:\Scripts> ".\script name with spaces.ps1"
.\script name with spaces.ps1
PS C:\Scripts> & ".\script name with spaces.ps1"
Hello World!
```

<span data-ttu-id="6fee1-189">スクリプトブロックの詳細については、「 [about_Script_Blocks](about_Script_Blocks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fee1-189">For more about script blocks, see [about_Script_Blocks](about_Script_Blocks.md).</span></span>

#### <a name="cast-operator--"></a><span data-ttu-id="6fee1-190">Cast 演算子 `[ ]`</span><span class="sxs-lookup"><span data-stu-id="6fee1-190">Cast operator `[ ]`</span></span>

<span data-ttu-id="6fee1-191">オブジェクトを指定した型に変換または制限します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-191">Converts or limits objects to the specified type.</span></span> <span data-ttu-id="6fee1-192">オブジェクトを変換できない場合は、PowerShell によってエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-192">If the objects cannot be converted, PowerShell generates an error.</span></span>

```powershell
[DateTime]"2/20/88" - [DateTime]"1/20/88"
[Int] (7/2)
[String] 1 + 0
[Int] '1' + 0
```

<span data-ttu-id="6fee1-193">キャストは、 [キャスト表記](about_Variables.md)を使用して変数が割り当てられている場合にも実行できます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-193">A cast can also be performed when a variable is assigned to using [cast notation](about_Variables.md).</span></span>

#### <a name="comma-operator-"></a><span data-ttu-id="6fee1-194">コンマ演算子 `,`</span><span class="sxs-lookup"><span data-stu-id="6fee1-194">Comma operator `,`</span></span>

<span data-ttu-id="6fee1-195">二項演算子として、コンマは配列を作成するか、作成される配列にを追加します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-195">As a binary operator, the comma creates an array or appends to the array being created.</span></span> <span data-ttu-id="6fee1-196">式モードでは、単項演算子として、コンマは1つのメンバーだけで配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-196">In expression mode, as a unary operator, the comma creates an array with just one member.</span></span> <span data-ttu-id="6fee1-197">メンバーの前にコンマを配置します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-197">Place the comma before the member.</span></span>

```powershell
$myArray = 1,2,3
$SingleArray = ,1
Write-Output (,1)
```

<span data-ttu-id="6fee1-198">`Write-Object`では引数が想定されているため、式をかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fee1-198">Since `Write-Object` expects an argument, you must put the expression in parentheses.</span></span>

#### <a name="dot-sourcing-operator-"></a><span data-ttu-id="6fee1-199">ドットソーシング演算子 `.`</span><span class="sxs-lookup"><span data-stu-id="6fee1-199">Dot sourcing operator `.`</span></span>

<span data-ttu-id="6fee1-200">現在のスコープでスクリプトを実行して、スクリプトによって作成されたすべての関数、エイリアス、および変数を現在のスコープに追加し、既存のスコープを上書きします。</span><span class="sxs-lookup"><span data-stu-id="6fee1-200">Runs a script in the current scope so that any functions, aliases, and variables that the script creates are added to the current scope, overriding existing ones.</span></span> <span data-ttu-id="6fee1-201">スクリプトによって宣言されたパラメーターは変数になります。</span><span class="sxs-lookup"><span data-stu-id="6fee1-201">Parameters declared by the script become variables.</span></span> <span data-ttu-id="6fee1-202">値が指定されていないパラメーターは、値のない変数になります。</span><span class="sxs-lookup"><span data-stu-id="6fee1-202">Parameters for which no value has been given become variables with no value.</span></span> <span data-ttu-id="6fee1-203">ただし、自動変数 `$args` は保持されます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-203">However, the automatic variable `$args` is preserved.</span></span>

```powershell
. c:\scripts\sample.ps1 1 2 -Also:3
```

> [!NOTE]
> <span data-ttu-id="6fee1-204">ドットソーシング演算子の後にスペースがあります。</span><span class="sxs-lookup"><span data-stu-id="6fee1-204">The dot sourcing operator is followed by a space.</span></span> <span data-ttu-id="6fee1-205">現在のディレクトリを表すドット () 記号とドットを区別するには、スペースを使用し `.` ます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-205">Use the space to distinguish the dot from the dot (`.`) symbol that represents the current directory.</span></span>
>
> <span data-ttu-id="6fee1-206">次の例では、現在のディレクトリの Sample.ps1 スクリプトが現在のスコープで実行されています。</span><span class="sxs-lookup"><span data-stu-id="6fee1-206">In the following example, the Sample.ps1 script in the current directory is run in the current scope.</span></span>
>
> ```powershell
> . .\sample.ps1
> ```

#### <a name="format-operator--f"></a><span data-ttu-id="6fee1-207">Format 演算子 `-f`</span><span class="sxs-lookup"><span data-stu-id="6fee1-207">Format operator `-f`</span></span>

<span data-ttu-id="6fee1-208">文字列オブジェクトの format メソッドを使用して文字列の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-208">Formats strings by using the format method of string objects.</span></span> <span data-ttu-id="6fee1-209">演算子の左側に書式文字列を入力し、演算子の右側に書式設定するオブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-209">Enter the format string on the left side of the operator and the objects to be formatted on the right side of the operator.</span></span>

```powershell
"{0} {1,-10} {2:N}" -f 1,"hello",[math]::pi
```

```output
1 hello      3.14
```

<span data-ttu-id="6fee1-210">書式設定された文字列で中かっこ () を保持する必要がある場合は、 `{}` 中かっこを2倍にしてエスケープすることができます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-210">If you need to keep the curly braces (`{}`) in the formatted string, you can escape them by doubling the curly braces.</span></span>

```powershell
"{0} vs. {{0}}" -f 'foo'
```

```Output
foo vs. {0}
```

<span data-ttu-id="6fee1-211">詳細については、「 [Format](/dotnet/api/system.string.format) メソッド」と「 [複合書式指定](/dotnet/standard/base-types/composite-formatting)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fee1-211">For more information, see the [String.Format](/dotnet/api/system.string.format) method and [Composite Formatting](/dotnet/standard/base-types/composite-formatting).</span></span>

#### <a name="index-operator--"></a><span data-ttu-id="6fee1-212">Index 演算子 `[ ]`</span><span class="sxs-lookup"><span data-stu-id="6fee1-212">Index operator `[ ]`</span></span>

<span data-ttu-id="6fee1-213">配列やハッシュテーブルなどのインデックス付きコレクションからオブジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-213">Selects objects from indexed collections, such as arrays and hash tables.</span></span> <span data-ttu-id="6fee1-214">配列インデックスは0から始まるため、最初のオブジェクトはとしてインデックスが作成され `[0]` ます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-214">Array indexes are zero-based, so the first object is indexed as `[0]`.</span></span> <span data-ttu-id="6fee1-215">配列の場合 (のみ)、負のインデックスを使用して最後の値を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-215">For arrays (only), you can also use negative indexes to get the last values.</span></span> <span data-ttu-id="6fee1-216">ハッシュテーブルには、キー値によってインデックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-216">Hash tables are indexed by key value.</span></span>

```
PS> $a = 1, 2, 3
PS> $a[0]
1
PS> $a[-1]
3
```

```powershell
(Get-HotFix | Sort-Object installedOn)[-1]
```

```powershell
$h = @{key="value"; name="PowerShell"; version="2.0"}
$h["name"]
```

```output
PowerShell
```

```powershell
$x = [xml]"<doc><intro>Once upon a time...</intro></doc>"
$x["doc"]
```

```output
intro
-----
Once upon a time...
```

#### <a name="pipeline-operator-"></a><span data-ttu-id="6fee1-217">パイプライン演算子 `|`</span><span class="sxs-lookup"><span data-stu-id="6fee1-217">Pipeline operator `|`</span></span>

<span data-ttu-id="6fee1-218">このコマンドの前に続くコマンドの出力を ("パイプ" で) 送信します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-218">Sends ("pipes") the output of the command that precedes it to the command that follows it.</span></span> <span data-ttu-id="6fee1-219">出力に複数のオブジェクト ("コレクション") が含まれている場合、パイプライン演算子はオブジェクトを一度に1つずつ送信します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-219">When the output includes more than one object (a "collection"), the pipeline operator sends the objects one at a time.</span></span>

```powershell
Get-Process | Get-Member
Get-Service | Where-Object {$_.StartType -eq 'Automatic'}
```

#### <a name="range-operator-"></a><span data-ttu-id="6fee1-220">範囲演算子 `..`</span><span class="sxs-lookup"><span data-stu-id="6fee1-220">Range operator `..`</span></span>

<span data-ttu-id="6fee1-221">上限と下限を指定して、整数配列内の連続する整数を表します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-221">Represents the sequential integers in an integer array, given an upper, and lower boundary.</span></span>

```powershell
1..10
foreach ($a in 1..$max) {Write-Host $a}
```

<span data-ttu-id="6fee1-222">範囲は逆順に作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-222">You can also create ranges in reverse order.</span></span>

```powershell
10..1
5..-5 | ForEach-Object {Write-Output $_}
```

#### <a name="member-access-operator-"></a><span data-ttu-id="6fee1-223">メンバーアクセス演算子 `.`</span><span class="sxs-lookup"><span data-stu-id="6fee1-223">Member access operator `.`</span></span>

<span data-ttu-id="6fee1-224">オブジェクトのプロパティおよびメソッドにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6fee1-224">Accesses the properties and methods of an object.</span></span> <span data-ttu-id="6fee1-225">メンバー名は式にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-225">The member name may be an expression.</span></span>

```powershell
$myProcess.peakWorkingSet
(Get-Process PowerShell).kill()
'OS', 'Platform' | Foreach-Object { $PSVersionTable. $_ }
```

#### <a name="static-member-operator-"></a><span data-ttu-id="6fee1-226">静的メンバー演算子 `::`</span><span class="sxs-lookup"><span data-stu-id="6fee1-226">Static member operator `::`</span></span>

<span data-ttu-id="6fee1-227">.NET Framework クラスの静的プロパティおよびメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6fee1-227">Calls the static properties and methods of a .NET Framework class.</span></span> <span data-ttu-id="6fee1-228">オブジェクトの静的なプロパティとメソッドを検索するには、コマンドレットの Static パラメーターを使用し `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-228">To find the static properties and methods of an object, use the Static parameter of the `Get-Member` cmdlet.</span></span>  <span data-ttu-id="6fee1-229">メンバー名は式にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6fee1-229">The member name may be an expression.</span></span>

```powershell
[datetime]::Now
'MinValue', 'MaxValue' | Foreach-Object { [int]:: $_ }
```

## <a name="see-also"></a><span data-ttu-id="6fee1-230">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fee1-230">See also</span></span>

[<span data-ttu-id="6fee1-231">about_Arithmetic_Operators</span><span class="sxs-lookup"><span data-stu-id="6fee1-231">about_Arithmetic_Operators</span></span>](about_Arithmetic_Operators.md)

[<span data-ttu-id="6fee1-232">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="6fee1-232">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)

[<span data-ttu-id="6fee1-233">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="6fee1-233">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="6fee1-234">about_Logical_Operators</span><span class="sxs-lookup"><span data-stu-id="6fee1-234">about_Logical_Operators</span></span>](about_logical_operators.md)

[<span data-ttu-id="6fee1-235">about_Operator_Precedence</span><span class="sxs-lookup"><span data-stu-id="6fee1-235">about_Operator_Precedence</span></span>](about_operator_precedence.md)

[<span data-ttu-id="6fee1-236">about_Type_Operators</span><span class="sxs-lookup"><span data-stu-id="6fee1-236">about_Type_Operators</span></span>](about_Type_Operators.md)

[<span data-ttu-id="6fee1-237">about_Split</span><span class="sxs-lookup"><span data-stu-id="6fee1-237">about_Split</span></span>](about_Split.md)

[<span data-ttu-id="6fee1-238">about_Join</span><span class="sxs-lookup"><span data-stu-id="6fee1-238">about_Join</span></span>](about_Join.md)

[<span data-ttu-id="6fee1-239">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="6fee1-239">about_Redirection</span></span>](about_Redirection.md)
