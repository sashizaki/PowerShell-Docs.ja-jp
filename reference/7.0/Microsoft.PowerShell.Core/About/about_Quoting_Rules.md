---
description: PowerShell で単一引用符と二重引用符を使用するための規則について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_quoting_rules?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Quoting_Rules
ms.openlocfilehash: 8e30640c74976ac79634f5f7f648aafc16977f31
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223067"
---
# <a name="about-quoting-rules"></a><span data-ttu-id="8e332-104">引用符の規則について</span><span class="sxs-lookup"><span data-stu-id="8e332-104">About Quoting Rules</span></span>

## <a name="short-description"></a><span data-ttu-id="8e332-105">概要</span><span class="sxs-lookup"><span data-stu-id="8e332-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="8e332-106">PowerShell で単一引用符と二重引用符を使用するための規則について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e332-106">Describes rules for using single and double quotation marks in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="8e332-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="8e332-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="8e332-108">リテラル文字列を指定するには、引用符を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e332-108">Quotation marks are used to specify a literal string.</span></span> <span data-ttu-id="8e332-109">文字列は単一引用符 ( `'` ) または二重引用符 () で囲むことができ `"` ます。</span><span class="sxs-lookup"><span data-stu-id="8e332-109">You can enclose a string in single quotation marks (`'`) or double quotation marks (`"`).</span></span>

<span data-ttu-id="8e332-110">引用符は、ここで指定した文字列を作成するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="8e332-110">Quotation marks are also used to create a here-string.</span></span> <span data-ttu-id="8e332-111">ここでは、引用符が文字どおりに解釈される一重引用符または二重引用符で囲まれた文字列です。</span><span class="sxs-lookup"><span data-stu-id="8e332-111">A here-string is a single-quoted or double-quoted string in which quotation marks are interpreted literally.</span></span> <span data-ttu-id="8e332-112">ここでは、複数の行にわたって文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8e332-112">A here-string can span multiple lines.</span></span> <span data-ttu-id="8e332-113">ここで指定した文字列のすべての行は、引用符で囲まれていない場合でも、文字列として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="8e332-113">All the lines in a here-string are interpreted as strings, even though they are not enclosed in quotation marks.</span></span>

<span data-ttu-id="8e332-114">リモートコンピューターへのコマンドでは、引用符によって、リモートコンピューター上で実行されるコマンドの部分が定義されます。</span><span class="sxs-lookup"><span data-stu-id="8e332-114">In commands to remote computers, quotation marks define the parts of the command that are run on the remote computer.</span></span> <span data-ttu-id="8e332-115">リモートセッションでは、引用符は、コマンド内の変数がローカルコンピューターとリモートコンピューターのどちらで最初に解釈されるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="8e332-115">In a remote session, quotation marks also determine whether the variables in a command are interpreted first on the local computer or on the remote computer.</span></span>

### <a name="single-and-double-quoted-strings"></a><span data-ttu-id="8e332-116">単一引用符と二重引用符で囲まれた文字列</span><span class="sxs-lookup"><span data-stu-id="8e332-116">SINGLE AND DOUBLE-QUOTED STRINGS</span></span>

<span data-ttu-id="8e332-117">文字列を二重引用符で囲んだ場合 (二重引用符で囲まれた文字列の場合)、文字列が処理のためにコマンドに渡される前に、その前にドル記号 () が付いた変数名 `$` が変数の値に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="8e332-117">When you enclose a string in double quotation marks (a double-quoted string), variable names that are preceded by a dollar sign (`$`) are replaced with the variable's value before the string is passed to the command for processing.</span></span>

<span data-ttu-id="8e332-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e332-118">For example:</span></span>

```powershell
$i = 5
"The value of $i is $i."
```

<span data-ttu-id="8e332-119">このコマンドの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8e332-119">The output of this command is:</span></span>

```Output
The value of 5 is 5.
```

<span data-ttu-id="8e332-120">また、二重引用符で囲まれた文字列では、式が評価され、結果が文字列に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="8e332-120">Also, in a double-quoted string, expressions are evaluated, and the result is inserted in the string.</span></span> <span data-ttu-id="8e332-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e332-121">For example:</span></span>

```powershell
"The value of $(2+3) is 5."
```

<span data-ttu-id="8e332-122">このコマンドの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8e332-122">The output of this command is:</span></span>

```Output
The value of 5 is 5.
```

<span data-ttu-id="8e332-123">文字列を単一引用符で囲むと (単一引用符で囲まれた文字列)、入力したとおりに文字列がコマンドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="8e332-123">When you enclose a string in single-quotation marks (a single-quoted string), the string is passed to the command exactly as you type it.</span></span> <span data-ttu-id="8e332-124">置換は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8e332-124">No substitution is performed.</span></span> <span data-ttu-id="8e332-125">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e332-125">For example:</span></span>

```powershell
$i = 5
'The value of $i is $i.'
```

<span data-ttu-id="8e332-126">このコマンドの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8e332-126">The output of this command is:</span></span>

```Output
The value $i is $i.
```

<span data-ttu-id="8e332-127">同様に、単一引用符で囲まれた文字列の式は評価されません。</span><span class="sxs-lookup"><span data-stu-id="8e332-127">Similarly, expressions in single-quoted strings are not evaluated.</span></span> <span data-ttu-id="8e332-128">これらはリテラルとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="8e332-128">They are interpreted as literals.</span></span> <span data-ttu-id="8e332-129">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e332-129">For example:</span></span>

```powershell
'The value of $(2+3) is 5.'
```

<span data-ttu-id="8e332-130">このコマンドの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8e332-130">The output of this command is:</span></span>

```Output
The value of $(2+3) is 5.
```

<span data-ttu-id="8e332-131">変数値が二重引用符で囲まれた文字列に代入されないようにするには、PowerShell のエスケープ文字であるバックティック character ( `` ` `` ) (ASCII 96) を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e332-131">To prevent the substitution of a variable value in a double-quoted string, use the backtick character (`` ` ``)(ASCII 96), which is the PowerShell escape character.</span></span>

<span data-ttu-id="8e332-132">次の例では、最初の $i 変数の前にあるバックティック文字によって、PowerShell が変数名をその値に置き換えることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="8e332-132">In the following example, the backtick character that precedes the first $i variable prevents PowerShell from replacing the variable name with its value.</span></span>
<span data-ttu-id="8e332-133">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e332-133">For example:</span></span>

```powershell
$i = 5
"The value of `$i is $i."
```

<span data-ttu-id="8e332-134">このコマンドの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8e332-134">The output of this command is:</span></span>

```Output
The value $i is 5.
```

<span data-ttu-id="8e332-135">文字列内に二重引用符を表示するには、文字列全体を単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="8e332-135">To make double-quotation marks appear in a string, enclose the entire string in single quotation marks.</span></span> <span data-ttu-id="8e332-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e332-136">For example:</span></span>

```powershell
'As they say, "live and learn."'
```

<span data-ttu-id="8e332-137">このコマンドの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8e332-137">The output of this command is:</span></span>

```Output
As they say, "live and learn."
```

<span data-ttu-id="8e332-138">また、単一引用符で囲まれた文字列を二重引用符で囲むこともできます。</span><span class="sxs-lookup"><span data-stu-id="8e332-138">You can also enclose a single-quoted string in a double-quoted string.</span></span> <span data-ttu-id="8e332-139">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e332-139">For example:</span></span>

```powershell
"As they say, 'live and learn.'"
```

<span data-ttu-id="8e332-140">このコマンドの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8e332-140">The output of this command is:</span></span>

```Output
As they say, 'live and learn.'
```

<span data-ttu-id="8e332-141">または、二重引用符で囲まれた語句を二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="8e332-141">Or, double the quotation marks around a double-quoted phrase.</span></span> <span data-ttu-id="8e332-142">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e332-142">For example:</span></span>

```powershell
"As they say, ""live and learn."""
```

<span data-ttu-id="8e332-143">このコマンドの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8e332-143">The output of this command is:</span></span>

```Output
As they say, "live and learn."
```

<span data-ttu-id="8e332-144">単一引用符で囲まれた文字列に単一引用符を含めるには、2つ目の連続する単一引用符を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e332-144">To include a single quotation mark in a single-quoted string, use a second consecutive single quote.</span></span> <span data-ttu-id="8e332-145">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e332-145">For example:</span></span>

```powershell
'don''t'
```

<span data-ttu-id="8e332-146">このコマンドの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8e332-146">The output of this command is:</span></span>

```Output
don't
```

<span data-ttu-id="8e332-147">PowerShell によって二重引用符が文字どおりに解釈されるようにするには、バックティック文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e332-147">To force PowerShell to interpret a double quotation mark literally, use a backtick character.</span></span> <span data-ttu-id="8e332-148">これにより、PowerShell によって引用符が文字列の区切り記号として解釈されるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="8e332-148">This prevents PowerShell from interpreting the quotation mark as a string delimiter.</span></span> <span data-ttu-id="8e332-149">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e332-149">For example:</span></span>

```powershell
PS> "Use a quotation mark (`") to begin a string."
Use a quotation mark (") to begin a string.
PS> 'Use a quotation mark (`") to begin a string.'
Use a quotation mark (`") to begin a string.
```

<span data-ttu-id="8e332-150">単一引用符で囲まれた文字列の内容は文字どおりに解釈されるため、バックティック文字はリテラル文字として扱われ、出力に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8e332-150">Because the contents of single-quoted strings are interpreted literally, you the backtick character is treated as a literal character and displayed in the output.</span></span>

### <a name="here-strings"></a><span data-ttu-id="8e332-151">ここ-文字列</span><span class="sxs-lookup"><span data-stu-id="8e332-151">HERE-STRINGS</span></span>

<span data-ttu-id="8e332-152">ここでは、文字列の引用規則が少し異なります。</span><span class="sxs-lookup"><span data-stu-id="8e332-152">The quotation rules for here-strings are slightly different.</span></span>

<span data-ttu-id="8e332-153">ここでは、引用符が文字どおりに解釈される一重引用符または二重引用符で囲まれた文字列です。</span><span class="sxs-lookup"><span data-stu-id="8e332-153">A here-string is a single-quoted or double-quoted string in which quotation marks are interpreted literally.</span></span> <span data-ttu-id="8e332-154">ここでは、複数の行にわたって文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8e332-154">A here-string can span multiple lines.</span></span> <span data-ttu-id="8e332-155">ここで指定した文字列のすべての行は、引用符で囲まれていなくても文字列として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="8e332-155">All the lines in a here-string are interpreted as strings even though they are not enclosed in quotation marks.</span></span>

<span data-ttu-id="8e332-156">通常の文字列と同様に、変数は、二重引用符で囲まれた文字列の値に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="8e332-156">Like regular strings, variables are replaced by their values in double-quoted here-strings.</span></span> <span data-ttu-id="8e332-157">ここでは、単一引用符で囲まれた文字列では、変数は値に置き換えられません。</span><span class="sxs-lookup"><span data-stu-id="8e332-157">In single-quoted here-strings, variables are not replaced by their values.</span></span>

<span data-ttu-id="8e332-158">ここでは任意のテキストを使用できますが、次の種類のテキストには特に便利です。</span><span class="sxs-lookup"><span data-stu-id="8e332-158">You can use here-strings for any text, but they are particularly useful for the following kinds of text:</span></span>

- <span data-ttu-id="8e332-159">リテラル引用符を含むテキスト</span><span class="sxs-lookup"><span data-stu-id="8e332-159">Text that contains literal quotation marks</span></span>
- <span data-ttu-id="8e332-160">HTML または XML 内のテキストなどの複数行のテキスト</span><span class="sxs-lookup"><span data-stu-id="8e332-160">Multiple lines of text, such as the text in an HTML or XML</span></span>
- <span data-ttu-id="8e332-161">スクリプトまたは関数ドキュメントのヘルプテキスト</span><span class="sxs-lookup"><span data-stu-id="8e332-161">The Help text for a script or function document</span></span>

<span data-ttu-id="8e332-162">ここでは、次のいずれかの形式を使用できます。は、 `<Enter>` <kbd>enter</kbd> キーを押したときに追加される改行または改行の非表示文字を表します。</span><span class="sxs-lookup"><span data-stu-id="8e332-162">A here-string can have either of the following formats, where `<Enter>` represents the linefeed or newline hidden character that is added when you press the <kbd>ENTER</kbd> key.</span></span>

<span data-ttu-id="8e332-163">二重引用符:</span><span class="sxs-lookup"><span data-stu-id="8e332-163">Double-quotes:</span></span>

```
@"<Enter>
<string> [string] ...<Enter>
"@
```

<span data-ttu-id="8e332-164">単一引用符:</span><span class="sxs-lookup"><span data-stu-id="8e332-164">Single-quotes:</span></span>

```
@'<Enter>
<string> [string] ...<Enter>
'@
```

<span data-ttu-id="8e332-165">どちらの形式でも、終わりの引用符は、行の最初の文字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e332-165">In either format, the closing quotation mark must be the first character in the line.</span></span>

<span data-ttu-id="8e332-166">ここでは、2つの非表示文字間のすべてのテキストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8e332-166">A here-string contains all the text between the two hidden characters.</span></span> <span data-ttu-id="8e332-167">この文字列では、すべての引用符が文字どおりに解釈されます。</span><span class="sxs-lookup"><span data-stu-id="8e332-167">In the here-string, all quotation marks are interpreted literally.</span></span> <span data-ttu-id="8e332-168">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e332-168">For example:</span></span>

```powershell
@"
For help, type "get-help"
"@
```

<span data-ttu-id="8e332-169">このコマンドの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8e332-169">The output of this command is:</span></span>

```Output
For help, type "get-help"
```

<span data-ttu-id="8e332-170">ここで説明した文字列を使用すると、コマンド内での文字列の使用が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="8e332-170">Using a here-string can simplify using a string in a command.</span></span> <span data-ttu-id="8e332-171">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e332-171">For example:</span></span>

```powershell
@"
Use a quotation mark (') to begin a string.
"@
```

<span data-ttu-id="8e332-172">このコマンドの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8e332-172">The output of this command is:</span></span>

```Output
Use a quotation mark (') to begin a string.
```

<span data-ttu-id="8e332-173">ここでは、単一引用符で囲まれた文字列では、変数は文字どおりに解釈され、正確に再現されます。</span><span class="sxs-lookup"><span data-stu-id="8e332-173">In single-quoted here-strings, variables are interpreted literally and reproduced exactly.</span></span> <span data-ttu-id="8e332-174">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e332-174">For example:</span></span>

```powershell
@'
The $profile variable contains the path
of your PowerShell profile.
'@
```

<span data-ttu-id="8e332-175">このコマンドの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8e332-175">The output of this command is:</span></span>

```Output
The $profile variable contains the path
of your PowerShell profile.
```

<span data-ttu-id="8e332-176">ここで二重引用符で囲まれた文字列は、変数の値に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="8e332-176">In double-quoted here-strings, variables are replaced by their values.</span></span> <span data-ttu-id="8e332-177">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8e332-177">For example:</span></span>

```powershell
@"
Even if you have not created a profile,
the path of the profile file is:
$profile.
"@
```

<span data-ttu-id="8e332-178">このコマンドの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8e332-178">The output of this command is:</span></span>

```Output
Even if you have not created a profile,
the path of the profile file is:
C:\Users\User1\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1.
```

<span data-ttu-id="8e332-179">ここでは、通常、複数行を変数に割り当てるために文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e332-179">Here-strings are typically used to assign multiple lines to a variable.</span></span> <span data-ttu-id="8e332-180">たとえば、次の文字列では、XML のページが $page 変数に代入されます。</span><span class="sxs-lookup"><span data-stu-id="8e332-180">For example, the following here-string assigns a page of XML to the $page variable.</span></span>

```powershell
$page = [XML] @"
<command:command xmlns:maml="http://schemas.microsoft.com/maml/2004/10"
xmlns:command="http://schemas.microsoft.com/maml/dev/command/2004/10"
xmlns:dev="http://schemas.microsoft.com/maml/dev/2004/10">
<command:details>
        <command:name>
               Format-Table
        </command:name>
        <maml:description>
            <maml:para>Formats the output as a table.</maml:para>
        </maml:description>
        <command:verb>format</command:verb>
        <command:noun>table</command:noun>
        <dev:version></dev:version>
</command:details>
...
</command:command>
"@
```

<span data-ttu-id="8e332-181">ここでは、コマンドレットへの入力に便利な形式として、ここで指定した `ConvertFrom-StringData` 文字列をハッシュテーブルに変換します。</span><span class="sxs-lookup"><span data-stu-id="8e332-181">Here-strings are also a convenient format for input to the `ConvertFrom-StringData` cmdlet, which converts here-strings to hash tables.</span></span>
<span data-ttu-id="8e332-182">詳細については、「`ConvertFrom-StringData`」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e332-182">For more information, see `ConvertFrom-StringData`.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e332-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e332-183">SEE ALSO</span></span>

[<span data-ttu-id="8e332-184">about_Special_Characters</span><span class="sxs-lookup"><span data-stu-id="8e332-184">about_Special_Characters</span></span>](about_Special_Characters.md)

[<span data-ttu-id="8e332-185">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="8e332-185">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)
