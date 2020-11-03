---
description: Split 演算子を使用して1つ以上の文字列を部分文字列に分割する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 12/20/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_split?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Split
ms.openlocfilehash: e93f68265bf560b03ac503ca914a11dde1f6b061
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222499"
---
# <a name="about-split"></a><span data-ttu-id="9130a-104">分割について</span><span class="sxs-lookup"><span data-stu-id="9130a-104">About Split</span></span>

## <a name="short-description"></a><span data-ttu-id="9130a-105">概要</span><span class="sxs-lookup"><span data-stu-id="9130a-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="9130a-106">Split 演算子を使用して1つ以上の文字列を部分文字列に分割する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9130a-106">Explains how to use the Split operator to split one or more strings into substrings.</span></span>

## <a name="long-description"></a><span data-ttu-id="9130a-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="9130a-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="9130a-108">Split 操作は、1つまたは複数の文字列を部分文字列に分割します。</span><span class="sxs-lookup"><span data-stu-id="9130a-108">The Split operator splits one or more strings into substrings.</span></span> <span data-ttu-id="9130a-109">Split 操作の次の要素を変更できます。</span><span class="sxs-lookup"><span data-stu-id="9130a-109">You can change the following elements of the Split operation:</span></span>

- <span data-ttu-id="9130a-110">区切り記号.</span><span class="sxs-lookup"><span data-stu-id="9130a-110">Delimiter.</span></span> <span data-ttu-id="9130a-111">既定値は空白ですが、区切り記号を指定する文字、文字列、パターン、またはスクリプトブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9130a-111">The default is whitespace, but you can specify characters, strings, patterns, or script blocks that specify the delimiter.</span></span> <span data-ttu-id="9130a-112">Windows PowerShell の Split 演算子は、単純な文字ではなく、区切り記号に正規表現を使用します。</span><span class="sxs-lookup"><span data-stu-id="9130a-112">The Split operator in Windows PowerShell uses a regular expression in the delimiter, rather than a simple character.</span></span>
- <span data-ttu-id="9130a-113">部分文字列の最大数。</span><span class="sxs-lookup"><span data-stu-id="9130a-113">Maximum number of substrings.</span></span> <span data-ttu-id="9130a-114">既定では、すべての部分文字列が返されます。</span><span class="sxs-lookup"><span data-stu-id="9130a-114">The default is to return all substrings.</span></span> <span data-ttu-id="9130a-115">部分文字列の数よりも小さい数値を指定した場合、残りの部分文字列は最後の部分文字列で連結されます。</span><span class="sxs-lookup"><span data-stu-id="9130a-115">If you specify a number less than the number of substrings, the remaining substrings are concatenated in the last substring.</span></span>
- <span data-ttu-id="9130a-116">区切り記号が一致する条件を指定するオプション (SimpleMatch や Multiline など)。</span><span class="sxs-lookup"><span data-stu-id="9130a-116">Options that specify the conditions under which the delimiter is matched, such as SimpleMatch and Multiline.</span></span>

## <a name="syntax"></a><span data-ttu-id="9130a-117">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9130a-117">SYNTAX</span></span>

<span data-ttu-id="9130a-118">次の図は、-split 演算子の構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="9130a-118">The following diagram shows the syntax for the -split operator.</span></span>

<span data-ttu-id="9130a-119">パラメーター名がコマンドに含まれていません。</span><span class="sxs-lookup"><span data-stu-id="9130a-119">The parameter names do not appear in the command.</span></span> <span data-ttu-id="9130a-120">パラメーター値のみを含めます。</span><span class="sxs-lookup"><span data-stu-id="9130a-120">Include only the parameter values.</span></span> <span data-ttu-id="9130a-121">値は、構文図に指定されている順序で表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="9130a-121">The values must appear in the order specified in the syntax diagram.</span></span>

```
-Split <String>
-Split (<String[]>)
<String> -Split <Delimiter>[,<Max-substrings>[,"<Options>"]]
<String> -Split {<ScriptBlock>} [,<Max-substrings>]
```

<span data-ttu-id="9130a-122">`-iSplit` `-cSplit` `-split` 任意のバイナリ split ステートメント (区切り記号またはスクリプトブロックを含む Split ステートメント) では、またはをに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="9130a-122">You can substitute `-iSplit` or `-cSplit` for `-split` in any binary Split statement (a Split statement that includes a delimiter or script block).</span></span> <span data-ttu-id="9130a-123">`-iSplit`演算子と `-split` 演算子では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="9130a-123">The `-iSplit` and `-split` operators are case-insensitive.</span></span> <span data-ttu-id="9130a-124">演算子では大文字と小文字が `-cSplit` 区別されます。つまり、区切り記号の規則が適用されるときに、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="9130a-124">The `-cSplit` operator is case-sensitive, meaning that case is considered when the delimiter rules are applied.</span></span>

## <a name="parameters"></a><span data-ttu-id="9130a-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9130a-125">PARAMETERS</span></span>

### <a name="string-or-string"></a><span data-ttu-id="9130a-126">\<String\> または \<String[]\></span><span class="sxs-lookup"><span data-stu-id="9130a-126">\<String\> or \<String[]\></span></span>

<span data-ttu-id="9130a-127">分割する1つ以上の文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="9130a-127">Specifies one or more strings to be split.</span></span> <span data-ttu-id="9130a-128">複数の文字列を送信する場合、すべての文字列は同じ区切り記号の規則を使用して分割されます。</span><span class="sxs-lookup"><span data-stu-id="9130a-128">If you submit multiple strings, all the strings are split using the same delimiter rules.</span></span>

<span data-ttu-id="9130a-129">例:</span><span class="sxs-lookup"><span data-stu-id="9130a-129">Example:</span></span>

```
-split "red yellow blue green"
red
yellow
blue
green
```

### \<Delimiter\>

<span data-ttu-id="9130a-130">部分文字列の末尾を識別する文字。</span><span class="sxs-lookup"><span data-stu-id="9130a-130">The characters that identify the end of a substring.</span></span> <span data-ttu-id="9130a-131">既定の区切り記号は空白文字で、スペースや印刷不可能な文字 (改行 ( \` n)、タブ ( \` t) など) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9130a-131">The default delimiter is whitespace, including spaces and non-printable characters, such as newline (\`n) and tab (\`t).</span></span> <span data-ttu-id="9130a-132">文字列が分割されると、すべての部分文字列の区切り記号が省略されます。</span><span class="sxs-lookup"><span data-stu-id="9130a-132">When the strings are split, the delimiter is omitted from all the substrings.</span></span> <span data-ttu-id="9130a-133">例:</span><span class="sxs-lookup"><span data-stu-id="9130a-133">Example:</span></span>

```
"Lastname:FirstName:Address" -split ":"
Lastname
FirstName
Address
```

<span data-ttu-id="9130a-134">既定では、区切り記号は結果から除外されます。</span><span class="sxs-lookup"><span data-stu-id="9130a-134">By default, the delimiter is omitted from the results.</span></span> <span data-ttu-id="9130a-135">区切り記号の全体または一部を保持するには、保持する部分をかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="9130a-135">To preserve all or part of the delimiter, enclose in parentheses the part that you want to preserve.</span></span>
<span data-ttu-id="9130a-136">パラメーターを \<Max-substrings\> 追加すると、コマンドによってコレクションが分割されるときに、これが優先されます。</span><span class="sxs-lookup"><span data-stu-id="9130a-136">If the \<Max-substrings\> parameter is added, this takes precedence when your command splits up the collection.</span></span> <span data-ttu-id="9130a-137">出力の一部として区切り記号を含めることを選択した場合、コマンドは出力の一部として区切り記号を返します。ただし、出力の一部として区切り記号を返すように文字列を分割することは、分割としてカウントされません。</span><span class="sxs-lookup"><span data-stu-id="9130a-137">If you opt to include a delimiter as part of the output, the command returns the delimiter as part of the output; however, splitting the string to return the delimiter as part of output does not count as a split.</span></span>

<span data-ttu-id="9130a-138">例 :</span><span class="sxs-lookup"><span data-stu-id="9130a-138">Examples:</span></span>

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

<span data-ttu-id="9130a-139">次の例で \<Max-substrings\> は、が3に設定されています。</span><span class="sxs-lookup"><span data-stu-id="9130a-139">In the following example, \<Max-substrings\> is set to 3.</span></span> <span data-ttu-id="9130a-140">この結果、文字列値は3つの分割が行われますが、結果の出力には合計5つの文字列が含まれます。分割の後に、最大3つの部分文字列に到達するまで、区切り記号が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9130a-140">This results in three splits of the string values, but a total of five strings in the resulting output; the delimiter is included after the splits, until the maximum of three substrings is reached.</span></span> <span data-ttu-id="9130a-141">最後の部分文字列の追加の区切り記号は、部分文字列の一部になります。</span><span class="sxs-lookup"><span data-stu-id="9130a-141">Additional delimiters in the final substring become part of the substring.</span></span>

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

<span data-ttu-id="9130a-142">文字列が分割される最大回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9130a-142">Specifies the maximum number of times that a string is split.</span></span> <span data-ttu-id="9130a-143">既定では、区切り記号によって分割されたすべての部分文字列です。</span><span class="sxs-lookup"><span data-stu-id="9130a-143">The default is all the substrings split by the delimiter.</span></span> <span data-ttu-id="9130a-144">複数の部分文字列がある場合、それらは最後の部分文字列に連結されます。</span><span class="sxs-lookup"><span data-stu-id="9130a-144">If there are more substrings, they are concatenated to the final substring.</span></span> <span data-ttu-id="9130a-145">部分文字列が少数の場合は、すべての部分文字列が返されます。</span><span class="sxs-lookup"><span data-stu-id="9130a-145">If there are fewer substrings, all the substrings are returned.</span></span> <span data-ttu-id="9130a-146">値0と負の値を指定すると、すべての部分文字列が返されます。</span><span class="sxs-lookup"><span data-stu-id="9130a-146">A value of 0 and negative values return all the substrings.</span></span>

<span data-ttu-id="9130a-147">Max 部分文字列には、返されるオブジェクトの最大数が指定されていません。この値は、文字列が分割される最大回数と同じです。</span><span class="sxs-lookup"><span data-stu-id="9130a-147">Max-substrings does not specify the maximum number of objects that are returned; its value equals the maximum number of times that a string is split.</span></span>
<span data-ttu-id="9130a-148">複数の文字列 (文字列の配列) を Split 演算子に送信すると、各文字列に対して最大部分文字列の制限が個別に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9130a-148">If you submit more than one string (an array of strings) to the Split operator , the Max-substrings limit is applied to each string separately.</span></span>

<span data-ttu-id="9130a-149">例:</span><span class="sxs-lookup"><span data-stu-id="9130a-149">Example:</span></span>

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

<span data-ttu-id="9130a-150">区切り記号を適用するための規則を指定する式。</span><span class="sxs-lookup"><span data-stu-id="9130a-150">An expression that specifies rules for applying the delimiter.</span></span> <span data-ttu-id="9130a-151">式は、$true または $false に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="9130a-151">The expression must evaluate to $true or $false.</span></span> <span data-ttu-id="9130a-152">スクリプトブロックを中かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="9130a-152">Enclose the script block in braces.</span></span>

<span data-ttu-id="9130a-153">例:</span><span class="sxs-lookup"><span data-stu-id="9130a-153">Example:</span></span>

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

<span data-ttu-id="9130a-154">オプション名を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="9130a-154">Enclose the option name in quotation marks.</span></span> <span data-ttu-id="9130a-155">オプションは、 \<Max-substrings\> ステートメントでパラメーターが使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="9130a-155">Options are valid only when the \<Max-substrings\> parameter is used in the statement.</span></span>

<span data-ttu-id="9130a-156">Options パラメーターの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9130a-156">The syntax for the Options parameter is:</span></span>

```
"SimpleMatch [,IgnoreCase]"

"[RegexMatch] [,IgnoreCase] [,CultureInvariant]
[,IgnorePatternWhitespace] [,ExplicitCapture]
[,Singleline | ,Multiline]"
```

<span data-ttu-id="9130a-157">SimpleMatch オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9130a-157">The SimpleMatch options are:</span></span>

- <span data-ttu-id="9130a-158">**SimpleMatch** : 区切り記号を評価するときに、単純な文字列比較を使用します。</span><span class="sxs-lookup"><span data-stu-id="9130a-158">**SimpleMatch** : Use simple string comparison when evaluating the delimiter.</span></span> <span data-ttu-id="9130a-159">RegexMatch と共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9130a-159">Cannot be used with RegexMatch.</span></span>
- <span data-ttu-id="9130a-160">**IgnoreCase** :-csplit 演算子が指定されている場合でも、大文字と小文字を区別しない一致を強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="9130a-160">**IgnoreCase** : Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>

<span data-ttu-id="9130a-161">RegexMatch オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9130a-161">The RegexMatch options are:</span></span>

- <span data-ttu-id="9130a-162">**RegexMatch** : 正規表現の照合を使用して、区切り記号を評価します。</span><span class="sxs-lookup"><span data-stu-id="9130a-162">**RegexMatch** : Use regular expression matching to evaluate the delimiter.</span></span> <span data-ttu-id="9130a-163">これは既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="9130a-163">This is the default behavior.</span></span> <span data-ttu-id="9130a-164">SimpleMatch と共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9130a-164">Cannot be used with SimpleMatch.</span></span>
- <span data-ttu-id="9130a-165">**IgnoreCase** :-csplit 演算子が指定されている場合でも、大文字と小文字を区別しない一致を強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="9130a-165">**IgnoreCase** : Forces case-insensitive matching, even if the -cSplit operator is specified.</span></span>
- <span data-ttu-id="9130a-166">**Regexoptions.cultureinvariant** : 区切り記号を評価するときに、言語のカルチャの違いを無視します。</span><span class="sxs-lookup"><span data-stu-id="9130a-166">**CultureInvariant** : Ignores cultural differences in language when evaluting the delimiter.</span></span> <span data-ttu-id="9130a-167">RegexMatch でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="9130a-167">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="9130a-168">**Ignorepattern whitespace** : エスケープされていない空白と、シャープ記号 (#) でマークされたコメントを無視します。</span><span class="sxs-lookup"><span data-stu-id="9130a-168">**IgnorePatternWhitespace** : Ignores unescaped whitespace and comments marked with the number sign (#).</span></span> <span data-ttu-id="9130a-169">RegexMatch でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="9130a-169">Valid only with RegexMatch.</span></span>
- <span data-ttu-id="9130a-170">**Multiline** : 複数行モードでは `^` 、 `$` 入力文字列の先頭と末尾ではなく、すべての行の先頭の末尾とが一致します。</span><span class="sxs-lookup"><span data-stu-id="9130a-170">**Multiline** : Multiline mode forces `^` and `$` to match the beginning end of every line instead of the beginning and end of the input string.</span></span>
- <span data-ttu-id="9130a-171">**Regexoptions.singleline** : regexoptions.singleline モードでは、入力文字列が *regexoptions.singleline* として扱われます。</span><span class="sxs-lookup"><span data-stu-id="9130a-171">**Singleline** : Singleline mode treats the input string as a *SingleLine*.</span></span>
  <span data-ttu-id="9130a-172">`.`改行を除くすべての文字に一致するのではなく、すべての文字が (改行を含めて) 一致するように強制し `\n` ます。</span><span class="sxs-lookup"><span data-stu-id="9130a-172">It forces the `.` character to match every character (including newlines), instead of matching every character EXCEPT the newline `\n`.</span></span>
- <span data-ttu-id="9130a-173">**Regexoptions.explicitcapture** : 明示的なキャプチャグループのみが結果一覧に返されるように、名前のない一致グループを無視します。</span><span class="sxs-lookup"><span data-stu-id="9130a-173">**ExplicitCapture** : Ignores non-named match groups so that only explicit capture groups are returned in the result list.</span></span> <span data-ttu-id="9130a-174">RegexMatch でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="9130a-174">Valid only with RegexMatch.</span></span>

> [!NOTE]
> <span data-ttu-id="9130a-175">Regexoptions.singleline は既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="9130a-175">SingleLine is the default behavior.</span></span> <span data-ttu-id="9130a-176">Regexoptions.singleline と Multiline は、options パラメーターと一緒に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9130a-176">Singleline and Multiline cannot be used together with the options parameter.</span></span> <span data-ttu-id="9130a-177">これは、PowerShell 6.0 で解決されました。</span><span class="sxs-lookup"><span data-stu-id="9130a-177">This was resolved in PowerShell 6.0.</span></span>
> <span data-ttu-id="9130a-178">これを回避するには、正規表現で *モード修飾子* を使用します。</span><span class="sxs-lookup"><span data-stu-id="9130a-178">The work around is by using *Mode-Modifiers* in your regular expression.</span></span>
> <span data-ttu-id="9130a-179">モードの修飾子の詳細については、「[正規表現のオプション](/dotnet/standard/base-types/regular-expression-options)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9130a-179">You can read more about mode modifiers in [Regular Expression Options](/dotnet/standard/base-types/regular-expression-options)</span></span>

## <a name="unary-and-binary-split-operators"></a><span data-ttu-id="9130a-180">単項分割演算子と二項分割演算子</span><span class="sxs-lookup"><span data-stu-id="9130a-180">UNARY and BINARY SPLIT OPERATORS</span></span>

<span data-ttu-id="9130a-181">単項分割演算子 ( `-split <string>` ) は、コンマよりも優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="9130a-181">The unary split operator (`-split <string>`) has higher precedence than a comma.</span></span> <span data-ttu-id="9130a-182">その結果、コンマ区切りの文字列リストを単項 split 演算子に送信した場合、最初の文字列 (最初のコンマの前) のみが分割されます。</span><span class="sxs-lookup"><span data-stu-id="9130a-182">As a result, if you submit a comma-separated list of strings to the unary split operator, only the first string (before the first comma) is split.</span></span>

<span data-ttu-id="9130a-183">次のパターンのいずれかを使用して、複数の文字列を分割します。</span><span class="sxs-lookup"><span data-stu-id="9130a-183">Use one of the following patterns to split more than one string:</span></span>

- <span data-ttu-id="9130a-184">バイナリ split 演算子 ( \<string[]\> -split) を使用する \<delimiter\></span><span class="sxs-lookup"><span data-stu-id="9130a-184">Use the binary split operator (\<string[]\> -split \<delimiter\>)</span></span>
- <span data-ttu-id="9130a-185">すべての文字列をかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="9130a-185">Enclose all the strings in parentheses</span></span>
- <span data-ttu-id="9130a-186">変数に文字列を格納し、その変数を split 演算子に送信します。</span><span class="sxs-lookup"><span data-stu-id="9130a-186">Store the strings in a variable then submit the variable to the split operator</span></span>

<span data-ttu-id="9130a-187">次の例を確認してください。</span><span class="sxs-lookup"><span data-stu-id="9130a-187">Consider the following example:</span></span>

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

## <a name="examples"></a><span data-ttu-id="9130a-188">例</span><span class="sxs-lookup"><span data-stu-id="9130a-188">EXAMPLES</span></span>

<span data-ttu-id="9130a-189">次のステートメントは、文字列を空白文字で分割します。</span><span class="sxs-lookup"><span data-stu-id="9130a-189">The following statement splits the string at whitespace.</span></span>

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

<span data-ttu-id="9130a-190">次のステートメントは、文字列を任意のコンマで分割します。</span><span class="sxs-lookup"><span data-stu-id="9130a-190">The following statement splits the string at any comma.</span></span>

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

<span data-ttu-id="9130a-191">次のステートメントは、パターン "er" で文字列を分割します。</span><span class="sxs-lookup"><span data-stu-id="9130a-191">The following statement splits the string at the pattern "er".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split 'er'
```

```output
M
cury,Venus,Earth,Mars,Jupit
,Saturn,Uranus,Neptune
```

<span data-ttu-id="9130a-192">次のステートメントは、文字 "N" で大文字と小文字を区別する分割を実行します。</span><span class="sxs-lookup"><span data-stu-id="9130a-192">The following statement performs a case-sensitive split at the letter "N".</span></span>

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -cSplit 'N'
```

```output
Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,
eptune
```

<span data-ttu-id="9130a-193">次のステートメントは、"e" と "t" の文字列を分割します。</span><span class="sxs-lookup"><span data-stu-id="9130a-193">The following statement splits the string at "e" and "t".</span></span>

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

<span data-ttu-id="9130a-194">次のステートメントは、"e" と "r" の文字列を分割しますが、結果として得られる部分文字列は6つの部分文字列に限定されます。</span><span class="sxs-lookup"><span data-stu-id="9130a-194">The following statement splits the string at "e" and "r", but limits the resulting substrings to six substrings.</span></span>

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

<span data-ttu-id="9130a-195">次のステートメントは、文字列を3つの部分文字列に分割します。</span><span class="sxs-lookup"><span data-stu-id="9130a-195">The following statement splits a string into three substrings.</span></span>

```powershell
"a,b,c,d,e,f,g,h" -split ",", 3
```

```output
a
b
c,d,e,f,g,h
```

<span data-ttu-id="9130a-196">次のステートメントは、2つの文字列を3つの部分文字列に分割します。</span><span class="sxs-lookup"><span data-stu-id="9130a-196">The following statement splits two strings into three substrings.</span></span>
<span data-ttu-id="9130a-197">(この制限は、各文字列に個別に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="9130a-197">(The limit is applied to each string independently.)</span></span>

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

<span data-ttu-id="9130a-198">次のステートメントは、1つ目の桁にある文字列の各行を分割します。</span><span class="sxs-lookup"><span data-stu-id="9130a-198">The following statement splits each line in the here-string at the first digit.</span></span> <span data-ttu-id="9130a-199">また、複数行オプションを使用して、各行と文字列の先頭を認識します。</span><span class="sxs-lookup"><span data-stu-id="9130a-199">It uses the Multiline option to recognize the beginning of each line and string.</span></span>

<span data-ttu-id="9130a-200">0は、最大部分文字列パラメーターの "return all" 値を表します。</span><span class="sxs-lookup"><span data-stu-id="9130a-200">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="9130a-201">マルチ部分文字列の値が指定されている場合にのみ、複数行のようなオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9130a-201">You can use options, such as Multiline, only when the Max-substrings value is specified.</span></span>

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

<span data-ttu-id="9130a-202">次のステートメントでは、円記号を使用して、ドット (.) 区切り記号をエスケープします。</span><span class="sxs-lookup"><span data-stu-id="9130a-202">The following statement uses the backslash character to escape the dot (.) delimiter.</span></span>

<span data-ttu-id="9130a-203">既定の RegexMatch では、引用符 (".") で囲まれたドットは、改行文字を除く任意の文字と一致するように解釈されます。</span><span class="sxs-lookup"><span data-stu-id="9130a-203">With the default, RegexMatch, the dot enclosed in quotation marks (".") is interpreted to match any character except for a newline character.</span></span> <span data-ttu-id="9130a-204">その結果、Split ステートメントは、改行を除くすべての文字に対して空白行を返します。</span><span class="sxs-lookup"><span data-stu-id="9130a-204">As a result, the Split statement returns a blank line for every character except newline.</span></span>

```powershell
"This.is.a.test" -split "\."
```

```output
This
is
a
test
```

<span data-ttu-id="9130a-205">次のステートメントでは、SimpleMatch オプションを使用して、-split 演算子がドット (.) 区切り記号を文字どおり解釈するように指定しています。</span><span class="sxs-lookup"><span data-stu-id="9130a-205">The following statement uses the SimpleMatch option to direct the -split operator to interpret the dot (.) delimiter literally.</span></span>

<span data-ttu-id="9130a-206">0は、最大部分文字列パラメーターの "return all" 値を表します。</span><span class="sxs-lookup"><span data-stu-id="9130a-206">The 0 represents the "return all" value of the Max-substrings parameter.</span></span> <span data-ttu-id="9130a-207">SimpleMatch などのオプションは、最大部分文字列の値が指定されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9130a-207">You can use options, such as SimpleMatch, only when the Max-substrings value is specified.</span></span>

```powershell
"This.is.a.test" -split ".", 0, "simplematch"
```

```output
This
is
a
test
```

<span data-ttu-id="9130a-208">次のステートメントは、変数の値に応じて、2つの区切り記号のいずれかで文字列を分割します。</span><span class="sxs-lookup"><span data-stu-id="9130a-208">The following statement splits the string at one of two delimiters, depending on the value of a variable.</span></span>

```powershell
$i = 1
$c = "LastName, FirstName; Address, City, State, Zip"
$c -split $(if ($i -lt 1) {","} else {";"})
```

```output
LastName, FirstName
 Address, City, State, Zip
```

## <a name="see-also"></a><span data-ttu-id="9130a-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="9130a-209">SEE ALSO</span></span>

[<span data-ttu-id="9130a-210">Split-Path</span><span class="sxs-lookup"><span data-stu-id="9130a-210">Split-Path</span></span>](xref:Microsoft.PowerShell.Management.Split-Path)

[<span data-ttu-id="9130a-211">about_Operators</span><span class="sxs-lookup"><span data-stu-id="9130a-211">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="9130a-212">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="9130a-212">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="9130a-213">about_Join</span><span class="sxs-lookup"><span data-stu-id="9130a-213">about_Join</span></span>](about_Join.md)
