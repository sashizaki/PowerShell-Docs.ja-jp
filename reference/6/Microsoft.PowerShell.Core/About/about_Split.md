---
description: Split 演算子を使用して1つ以上の文字列を部分文字列に分割する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 12/20/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_split?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Split
ms.openlocfilehash: 520aac1fd1aae4f1f0f4a12a10bc4f5c7f258731
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221128"
---
# <a name="about-split"></a><span data-ttu-id="62575-104">分割について</span><span class="sxs-lookup"><span data-stu-id="62575-104">About Split</span></span>

## <a name="short-description"></a><span data-ttu-id="62575-105">概要</span><span class="sxs-lookup"><span data-stu-id="62575-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="62575-106">Split 演算子を使用して1つ以上の文字列を部分文字列に分割する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="62575-106">Explains how to use the Split operator to split one or more strings into substrings.</span></span>

## <a name="long-description"></a><span data-ttu-id="62575-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="62575-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="62575-108">Split 操作は、1つまたは複数の文字列を部分文字列に分割します。</span><span class="sxs-lookup"><span data-stu-id="62575-108">The Split operator splits one or more strings into substrings.</span></span> <span data-ttu-id="62575-109">Split 操作の次の要素を変更できます。</span><span class="sxs-lookup"><span data-stu-id="62575-109">You can change the following elements of the Split operation:</span></span>

- <span data-ttu-id="62575-110">区切り記号.</span><span class="sxs-lookup"><span data-stu-id="62575-110">Delimiter.</span></span> <span data-ttu-id="62575-111">既定値は空白ですが、区切り記号を指定する文字、文字列、パターン、またはスクリプトブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="62575-111">The default is whitespace, but you can specify characters, strings, patterns, or script blocks that specify the delimiter.</span></span> <span data-ttu-id="62575-112">PowerShell の Split 演算子は、単純な文字ではなく、区切り記号に正規表現を使用します。</span><span class="sxs-lookup"><span data-stu-id="62575-112">The Split operator in PowerShell uses a regular expression in the delimiter, rather than a simple character.</span></span>
- <span data-ttu-id="62575-113">部分文字列の最大数。</span><span class="sxs-lookup"><span data-stu-id="62575-113">Maximum number of substrings.</span></span> <span data-ttu-id="62575-114">既定では、すべての部分文字列が返されます。</span><span class="sxs-lookup"><span data-stu-id="62575-114">The default is to return all substrings.</span></span> <span data-ttu-id="62575-115">部分文字列の数よりも小さい数値を指定した場合、残りの部分文字列は最後の部分文字列で連結されます。</span><span class="sxs-lookup"><span data-stu-id="62575-115">If you specify a number less than the number of substrings, the remaining substrings are concatenated in the last substring.</span></span>
- <span data-ttu-id="62575-116">区切り記号が一致する条件を指定するオプション (SimpleMatch や Multiline など)。</span><span class="sxs-lookup"><span data-stu-id="62575-116">Options that specify the conditions under which the delimiter is matched, such as SimpleMatch and Multiline.</span></span>

## <a name="syntax"></a><span data-ttu-id="62575-117">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="62575-117">SYNTAX</span></span>

<span data-ttu-id="62575-118">次の図は、-split 演算子の構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="62575-118">The following diagram shows the syntax for the -split operator.</span></span>

<span data-ttu-id="62575-119">パラメーター名がコマンドに含まれていません。</span><span class="sxs-lookup"><span data-stu-id="62575-119">The parameter names do not appear in the command.</span></span> <span data-ttu-id="62575-120">パラメーター値のみを含めます。</span><span class="sxs-lookup"><span data-stu-id="62575-120">Include only the parameter values.</span></span> <span data-ttu-id="62575-121">値は、構文図に指定されている順序で表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="62575-121">The values must appear in the order specified in the syntax diagram.</span></span>

```
-Split <String>
-Split (<String[]>)
<String> -Split <Delimiter>[,<Max-substrings>[,"<Options>"]]
<String> -Split {<ScriptBlock>} [,<Max-substrings>]
```

<span data-ttu-id="62575-122">`-iSplit` `-cSplit` `-split` 任意のバイナリ split ステートメント (区切り記号またはスクリプトブロックを含む Split ステートメント) では、またはをに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="62575-122">You can substitute `-iSplit` or `-cSplit` for `-split` in any binary Split statement (a Split statement that includes a delimiter or script block).</span></span> <span data-ttu-id="62575-123">`-iSplit`演算子と `-split` 演算子では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="62575-123">The `-iSplit` and `-split` operators are case-insensitive.</span></span> <span data-ttu-id="62575-124">演算子では大文字と小文字が `-cSplit` 区別されます。つまり、区切り記号の規則が適用されるときに、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="62575-124">The `-cSplit` operator is case-sensitive, meaning that case is considered when the delimiter rules are applied.</span></span>

## <a name="parameters"></a><span data-ttu-id="62575-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="62575-125">PARAMETERS</span></span>

### <a name="string-or-string"></a><span data-ttu-id="62575-126">\<String\> または \<String[]\></span><span class="sxs-lookup"><span data-stu-id="62575-126">\<String\> or \<String[]\></span></span>

<span data-ttu-id="62575-127">分割する1つ以上の文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="62575-127">Specifies one or more strings to be split.</span></span> <span data-ttu-id="62575-128">複数の文字列を送信する場合、すべての文字列は同じ区切り記号の規則を使用して分割されます。</span><span class="sxs-lookup"><span data-stu-id="62575-128">If you submit multiple strings, all the strings are split using the same delimiter rules.</span></span>

<span data-ttu-id="62575-129">例:</span><span class="sxs-lookup"><span data-stu-id="62575-129">Example:</span></span>

```
-split "red yellow blue green"
red
yellow
blue
green
```

### \<Delimiter\>

<span data-ttu-id="62575-130">部分文字列の末尾を識別する文字。</span><span class="sxs-lookup"><span data-stu-id="62575-130">The characters that identify the end of a substring.</span></span> <span data-ttu-id="62575-131">既定の区切り記号は空白文字で、スペースや印刷不可能な文字 (改行 ( \` n)、タブ ( \` t) など) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="62575-131">The default delimiter is whitespace, including spaces and non-printable characters, such as newline (\`n) and tab (\`t).</span></span> <span data-ttu-id="62575-132">文字列が分割されると、すべての部分文字列の区切り記号が省略されます。</span><span class="sxs-lookup"><span data-stu-id="62575-132">When the strings are split, the delimiter is omitted from all the substrings.</span></span> <span data-ttu-id="62575-133">例:</span><span class="sxs-lookup"><span data-stu-id="62575-133">Example:</span></span>

```
"Lastname:FirstName:Address" -split ":"
Lastname
FirstName
Address
```

<span data-ttu-id="62575-134">既定では、区切り記号は結果から除外されます。</span><span class="sxs-lookup"><span data-stu-id="62575-134">By default, the delimiter is omitted from the results.</span></span> <span data-ttu-id="62575-135">区切り記号の全体または一部を保持するには、保持する部分をかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="62575-135">To preserve all or part of the delimiter, enclose in parentheses the part that you want to preserve.</span></span>
<span data-ttu-id="62575-136">パラメーターを \<Max-substrings\> 追加すると、コマンドによってコレクションが分割されるときに、これが優先されます。</span><span class="sxs-lookup"><span data-stu-id="62575-136">If the \<Max-substrings\> parameter is added, this takes precedence when your command splits up the collection.</span></span> <span data-ttu-id="62575-137">出力の一部として区切り記号を含めることを選択した場合、コマンドは出力の一部として区切り記号を返します。ただし、出力の一部として区切り記号を返すように文字列を分割することは、分割としてカウントされません。</span><span class="sxs-lookup"><span data-stu-id="62575-137">If you opt to include a delimiter as part of the output, the command returns the delimiter as part of the output; however, splitting the string to return the delimiter as part of output does not count as a split.</span></span>

<span data-ttu-id="62575-138">例 :</span><span class="sxs-lookup"><span data-stu-id="62575-138">Examples:</span></span>

```
"Lastname:FirstName:Address" -split "(:)"
Lastname
:
FirstName
:
Address

"Lastname/:/FirstName/:/Address" -split "/(:)/"
Lastname
:
FirstName
:
Address
```

<span data-ttu-id="62575-139">次の例で \<Max-substrings\> は、が3に設定されています。</span><span class="sxs-lookup"><span data-stu-id="62575-139">In the following example, \<Max-substrings\> is set to 3.</span></span> <span data-ttu-id="62575-140">この結果、文字列値は3つの分割が行われますが、結果の出力には合計5つの文字列が含まれます。分割の後に、最大3つの部分文字列に到達するまで、区切り記号が含まれます。</span><span class="sxs-lookup"><span data-stu-id="62575-140">This results in three splits of the string values, but a total of five strings in the resulting output; the delimiter is included after the splits, until the maximum of three substrings is reached.</span></span> <span data-ttu-id="62575-141">最後の部分文字列の追加の区切り記号は、部分文字列の一部になります。</span><span class="sxs-lookup"><span data-stu-id="62575-141">Additional delimiters in the final substring become part of the substring.</span></span>

```powershell
'Chocolate-Vanilla-Strawberry-Blueberry' -split '(-)', 3
```

```output
Chocolate
-
Vanilla
-
Strawberry-Blueberry
```

### \<Max-substrings\>

<span data-ttu-id="62575-142">文字列が分割される最大回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="62575-142">Specifies the maximum number of times that a string is split.</span></span> <span data-ttu-id="62575-143">既定では、区切り記号によって分割されたすべての部分文字列です。</span><span class="sxs-lookup"><span data-stu-id="62575-143">The default is all the substrings split by the delimiter.</span></span> <span data-ttu-id="62575-144">複数の部分文字列がある場合、それらは最後の部分文字列に連結されます。</span><span class="sxs-lookup"><span data-stu-id="62575-144">If there are more substrings, they are concatenated to the final substring.</span></span> <span data-ttu-id="62575-145">部分文字列が少数の場合は、すべての部分文字列が返されます。</span><span class="sxs-lookup"><span data-stu-id="62575-145">If there are fewer substrings, all the substrings are returned.</span></span> <span data-ttu-id="62575-146">値0と負の値を指定すると、すべての部分文字列が返されます。</span><span class="sxs-lookup"><span data-stu-id="62575-146">A value of 0 and negative values return all the substrings.</span></span>

<span data-ttu-id="62575-147">Max 部分文字列には、返されるオブジェクトの最大数が指定されていません。この値は、文字列が分割される最大回数と同じです。</span><span class="sxs-lookup"><span data-stu-id="62575-147">Max-substrings does not specify the maximum number of objects that are returned; its value equals the maximum number of times that a string is split.</span></span>
<span data-ttu-id="62575-148">複数の文字列 (文字列の配列) を Split 演算子に送信すると、各文字列に対して最大部分文字列の制限が個別に適用されます。</span><span class="sxs-lookup"><span data-stu-id="62575-148">If you submit more than one string (an array of strings) to the Split operator , the Max-substrings limit is applied to each string separately.</span></span>

<span data-ttu-id="62575-149">例:</span><span class="sxs-lookup"><span data-stu-id="62575-149">Example:</span></span>

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split ",", 5
```

```output
Mercury
Venus
Earth
Mars
Jupiter,Saturn,Uranus,Neptune
```

### \<ScriptBlock\>

<span data-ttu-id="62575-150">区切り記号を適用するための規則を指定する式。</span><span class="sxs-lookup"><span data-stu-id="62575-150">An expression that specifies rules for applying the delimiter.</span></span> <span data-ttu-id="62575-151">式は、$true または $false に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="62575-151">The expression must evaluate to $true or $false.</span></span> <span data-ttu-id="62575-152">スクリプトブロックを中かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="62575-152">Enclose the script block in braces.</span></span>

<span data-ttu-id="62575-153">例:</span><span class="sxs-lookup"><span data-stu-id="62575-153">Example:</span></span>

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split {$_ -eq "e" -or $_ -eq "p"}
```

```output
M
rcury,V
nus,
arth,Mars,Ju
it
r,Saturn,Uranus,N

tun
```

### \<Options\>

<span data-ttu-id="62575-154">オプション名を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="62575-154">Enclose the option name in quotation marks.</span></span> <span data-ttu-id="62575-155">オプションは、 \<Max-substrings\> ステートメントでパラメーターが使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="62575-155">Options are valid only when the \<Max-substrings\> parameter is used in the statement.</span></span>

<span data-ttu-id="62575-156">Options パラメーターの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="62575-156">The syntax for the Options parameter is:</span></span>

```
"SimpleMatch [,IgnoreCase]"

"[RegexMatch] [,IgnoreCase] [,CultureInvariant]
[,IgnorePatternWhitespace] [,ExplicitCapture]
[,Singleline | ,Multiline]"
```

<span data-ttu-id="62575-157">SimpleMatch オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="62575-157">The SimpleMatch options are:</span></span>

- <span data-ttu-id="62575-158">**SimpleMatch** : 区切り記号を評価するときに、単純な文字列比較を使用します。</span><span class="sxs-lookup"><span data-stu-id="62575-158">**SimpleMatch** : Use simple string comparison when evaluating the delimiter.</span></span> <span data-ttu-id="62575-159">RegexMatch と共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="62575-159">Cannot be used with RegexMatch.</span></span>
- <span data-ttu-id="62575-160">**IgnoreCase** :-csplit 演算子が指定されている場合でも、大文字と小文字を区別しない一致を強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="62575-160">**IgnoreCase** : Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>

<span data-ttu-id="62575-161">RegexMatch オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="62575-161">The RegexMatch options are:</span></span>

- <span data-ttu-id="62575-162">**RegexMatch** : 正規表現の照合を使用して、区切り記号を評価します。</span><span class="sxs-lookup"><span data-stu-id="62575-162">**RegexMatch** : Use regular expression matching to evaluate the delimiter.</span></span> <span data-ttu-id="62575-163">これは既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="62575-163">This is the default behavior.</span></span> <span data-ttu-id="62575-164">SimpleMatch と共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="62575-164">Cannot be used with SimpleMatch.</span></span>
- <span data-ttu-id="62575-165">**IgnoreCase** :-csplit 演算子が指定されている場合でも、大文字と小文字を区別しない一致を強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="62575-165">**IgnoreCase** : Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>
- <span data-ttu-id="62575-166">**Regexoptions.cultureinvariant** : 区切り記号を評価するときに、言語のカルチャの違いを無視します。</span><span class="sxs-lookup"><span data-stu-id="62575-166">**CultureInvariant** : Ignores cultural differences in language when evaluting the delimiter.</span></span> <span data-ttu-id="62575-167">RegexMatch でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="62575-167">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="62575-168">**Ignorepattern whitespace** : エスケープされていない空白と、シャープ記号 (#) でマークされたコメントを無視します。</span><span class="sxs-lookup"><span data-stu-id="62575-168">**IgnorePatternWhitespace** : Ignores unescaped whitespace and comments marked with the number sign (#).</span></span> <span data-ttu-id="62575-169">RegexMatch でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="62575-169">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="62575-170">**Multiline** : 複数行モードでは `^` 、 `$` 入力文字列の先頭と末尾ではなく、すべての行の先頭の末尾とが一致します。</span><span class="sxs-lookup"><span data-stu-id="62575-170">**Multiline** : Multiline mode forces `^` and `$` to match the beginning end of every line instead of the beginning and end of the input string.</span></span>
- <span data-ttu-id="62575-171">**Regexoptions.singleline** : regexoptions.singleline モードでは、入力文字列が *regexoptions.singleline* として扱われます。</span><span class="sxs-lookup"><span data-stu-id="62575-171">**Singleline** : Singleline mode treats the input string as a *SingleLine*.</span></span>
  <span data-ttu-id="62575-172">`.`改行を除くすべての文字に一致するのではなく、すべての文字が (改行を含めて) 一致するように強制し `\n` ます。</span><span class="sxs-lookup"><span data-stu-id="62575-172">It forces the `.` character to match every character (including newlines), instead of matching every character EXCEPT the newline `\n`.</span></span>
- <span data-ttu-id="62575-173">**Regexoptions.explicitcapture** : 明示的なキャプチャグループのみが結果一覧に返されるように、名前のない一致グループを無視します。</span><span class="sxs-lookup"><span data-stu-id="62575-173">**ExplicitCapture** : Ignores non-named match groups so that only explicit capture groups are returned in the result list.</span></span> <span data-ttu-id="62575-174">RegexMatch でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="62575-174">Valid only with RegexMatch.</span></span>

## <a name="unary-and-binary-split-operators"></a><span data-ttu-id="62575-175">単項分割演算子と二項分割演算子</span><span class="sxs-lookup"><span data-stu-id="62575-175">UNARY and BINARY SPLIT OPERATORS</span></span>

<span data-ttu-id="62575-176">単項分割演算子 ( `-split <string>` ) は、コンマよりも優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="62575-176">The unary split operator (`-split <string>`) has higher precedence than a comma.</span></span> <span data-ttu-id="62575-177">その結果、コンマ区切りの文字列リストを単項 split 演算子に送信した場合、最初の文字列 (最初のコンマの前) のみが分割されます。</span><span class="sxs-lookup"><span data-stu-id="62575-177">As a result, if you submit a comma-separated list of strings to the unary split operator, only the first string (before the first comma) is split.</span></span>

<span data-ttu-id="62575-178">次のパターンのいずれかを使用して、複数の文字列を分割します。</span><span class="sxs-lookup"><span data-stu-id="62575-178">Use one of the following patterns to split more than one string:</span></span>

- <span data-ttu-id="62575-179">バイナリ split 演算子 ( \<string[]\> -split) を使用する \<delimiter\></span><span class="sxs-lookup"><span data-stu-id="62575-179">Use the binary split operator (\<string[]\> -split \<delimiter\>)</span></span>
- <span data-ttu-id="62575-180">すべての文字列をかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="62575-180">Enclose all the strings in parentheses</span></span>
- <span data-ttu-id="62575-181">変数に文字列を格納し、その変数を split 演算子に送信します。</span><span class="sxs-lookup"><span data-stu-id="62575-181">Store the strings in a variable then submit the variable to the split operator</span></span>

<span data-ttu-id="62575-182">次の例を確認してください。</span><span class="sxs-lookup"><span data-stu-id="62575-182">Consider the following example:</span></span>

```
PS> -split "1 2", "a b"
1
2
a b
```

```
PS> "1 2", "a b" -split " "
1
2
a
b
```

```
PS> -split ("1 2", "a b")
1
2
a
b
```

```
PS> $a = "1 2", "a b"
PS> -split $a
1
2
a
b
```

## <a name="examples"></a><span data-ttu-id="62575-183">例</span><span class="sxs-lookup"><span data-stu-id="62575-183">EXAMPLES</span></span>

<span data-ttu-id="62575-184">次のステートメントは、文字列を空白文字で分割します。</span><span class="sxs-lookup"><span data-stu-id="62575-184">The following statement splits the string at whitespace.</span></span>

```powershell
-split "Windows PowerShell 2.0`nWindows PowerShell with remoting"
```

```output

Windows
PowerShell
2.0
Windows
PowerShell
with
remoting
```

<span data-ttu-id="62575-185">次のステートメントは、文字列を任意のコンマで分割します。</span><span class="sxs-lookup"><span data-stu-id="62575-185">The following statement splits the string at any comma.</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split ','
```

```output
Mercury
Venus
Earth
Mars
Jupiter
Saturn
Uranus
Neptune
```

<span data-ttu-id="62575-186">次のステートメントは、パターン "er" で文字列を分割します。</span><span class="sxs-lookup"><span data-stu-id="62575-186">The following statement splits the string at the pattern "er".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split 'er'
```

```output
M
cury,Venus,Earth,Mars,Jupit
,Saturn,Uranus,Neptune
```

<span data-ttu-id="62575-187">次のステートメントは、文字 "N" で大文字と小文字を区別する分割を実行します。</span><span class="sxs-lookup"><span data-stu-id="62575-187">The following statement performs a case-sensitive split at the letter "N".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -cSplit 'N'
```

```output
Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,
eptune
```

<span data-ttu-id="62575-188">次のステートメントは、"e" と "t" の文字列を分割します。</span><span class="sxs-lookup"><span data-stu-id="62575-188">The following statement splits the string at "e" and "t".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[et]'
```

```output
M
rcury,V
nus,
ar
h,Mars,Jupi

r,Sa
urn,Uranus,N
p
un
```

<span data-ttu-id="62575-189">次のステートメントは、"e" と "r" の文字列を分割しますが、結果として得られる部分文字列は6つの部分文字列に限定されます。</span><span class="sxs-lookup"><span data-stu-id="62575-189">The following statement splits the string at "e" and "r", but limits the resulting substrings to six substrings.</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[er]', 6
```

```output
M

cu
y,V
nus,
arth,Mars,Jupiter,Saturn,Uranus,Neptune
```

<span data-ttu-id="62575-190">次のステートメントは、文字列を3つの部分文字列に分割します。</span><span class="sxs-lookup"><span data-stu-id="62575-190">The following statement splits a string into three substrings.</span></span>

```powershell
"a,b,c,d,e,f,g,h" -split ",", 3
```

```output
a
b
c,d,e,f,g,h
```

<span data-ttu-id="62575-191">次のステートメントは、2つの文字列を3つの部分文字列に分割します。</span><span class="sxs-lookup"><span data-stu-id="62575-191">The following statement splits two strings into three substrings.</span></span>
<span data-ttu-id="62575-192">(この制限は、各文字列に個別に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="62575-192">(The limit is applied to each string independently.)</span></span>

```powershell
"a,b,c,d", "e,f,g,h" -split ",", 3
```

```output
a
b
c,d
e
f
g,h
```

<span data-ttu-id="62575-193">次のステートメントは、1つ目の桁にある文字列の各行を分割します。</span><span class="sxs-lookup"><span data-stu-id="62575-193">The following statement splits each line in the here-string at the first digit.</span></span> <span data-ttu-id="62575-194">また、複数行オプションを使用して、各行と文字列の先頭を認識します。</span><span class="sxs-lookup"><span data-stu-id="62575-194">It uses the Multiline option to recognize the beginning of each line and string.</span></span>

<span data-ttu-id="62575-195">0は、最大部分文字列パラメーターの "return all" 値を表します。</span><span class="sxs-lookup"><span data-stu-id="62575-195">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="62575-196">マルチ部分文字列の値が指定されている場合にのみ、複数行のようなオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="62575-196">You can use options, such as Multiline, only when the Max-substrings value is specified.</span></span>

```powershell
$a = @'
1The first line.
2The second line.
3The third of three lines.
'@
$a -split "^\d", 0, "multiline"
```

```output

The first line.

The second line.

The third of three lines.
```

<span data-ttu-id="62575-197">次のステートメントでは、円記号を使用して、ドット (.) 区切り記号をエスケープします。</span><span class="sxs-lookup"><span data-stu-id="62575-197">The following statement uses the backslash character to escape the dot (.) delimiter.</span></span>

<span data-ttu-id="62575-198">既定の RegexMatch では、引用符 (".") で囲まれたドットは、改行文字を除く任意の文字と一致するように解釈されます。</span><span class="sxs-lookup"><span data-stu-id="62575-198">With the default, RegexMatch, the dot enclosed in quotation marks (".") is interpreted to match any character except for a newline character.</span></span> <span data-ttu-id="62575-199">その結果、Split ステートメントは、改行を除くすべての文字に対して空白行を返します。</span><span class="sxs-lookup"><span data-stu-id="62575-199">As a result, the Split statement returns a blank line for every character except newline.</span></span>

```powershell
"This.is.a.test" -split "\."
```

```output
This
is
a
test
```

<span data-ttu-id="62575-200">次のステートメントでは、SimpleMatch オプションを使用して、-split 演算子がドット (.) 区切り記号を文字どおり解釈するように指定しています。</span><span class="sxs-lookup"><span data-stu-id="62575-200">The following statement uses the SimpleMatch option to direct the -split operator to interpret the dot (.) delimiter literally.</span></span>

<span data-ttu-id="62575-201">0は、最大部分文字列パラメーターの "return all" 値を表します。</span><span class="sxs-lookup"><span data-stu-id="62575-201">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="62575-202">SimpleMatch などのオプションは、最大部分文字列の値が指定されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="62575-202">You can use options, such as SimpleMatch, only when the Max-substrings value is specified.</span></span>

```powershell
"This.is.a.test" -split ".", 0, "simplematch"
```

```output
This
is
a
test
```

<span data-ttu-id="62575-203">次のステートメントは、変数の値に応じて、2つの区切り記号のいずれかで文字列を分割します。</span><span class="sxs-lookup"><span data-stu-id="62575-203">The following statement splits the string at one of two delimiters, depending on the value of a variable.</span></span>

```powershell
$i = 1
$c = "LastName, FirstName; Address, City, State, Zip"
$c -split $(if ($i -lt 1) {","} else {";"})
```

```output
LastName, FirstName
 Address, City, State, Zip
```

## <a name="see-also"></a><span data-ttu-id="62575-204">関連項目</span><span class="sxs-lookup"><span data-stu-id="62575-204">SEE ALSO</span></span>

[<span data-ttu-id="62575-205">Split-Path</span><span class="sxs-lookup"><span data-stu-id="62575-205">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)

[<span data-ttu-id="62575-206">about_Operators</span><span class="sxs-lookup"><span data-stu-id="62575-206">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="62575-207">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="62575-207">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="62575-208">about_Join</span><span class="sxs-lookup"><span data-stu-id="62575-208">about_Join</span></span>](about_Join.md)
