---
description: PowerShell の正規表現について説明します。
Locale: en-US
ms.date: 03/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_regular_expressions?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Regular_Expressions
ms.openlocfilehash: 4dc6ac670a31cbea4c35ee6540ce3368ad9b02ca
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599510"
---
# <a name="about-regular-expressions"></a><span data-ttu-id="4b32d-103">正規表現について</span><span class="sxs-lookup"><span data-stu-id="4b32d-103">About Regular Expressions</span></span>

## <a name="short-description"></a><span data-ttu-id="4b32d-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="4b32d-104">Short description</span></span>
<span data-ttu-id="4b32d-105">PowerShell の正規表現について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-105">Describes regular expressions in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="4b32d-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="4b32d-106">Long description</span></span>

> [!NOTE]
> <span data-ttu-id="4b32d-107">この記事では、すべての構文について説明するのではなく、PowerShell で正規表現を使用するための構文とメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-107">This article will show you the syntax and methods for using regular expressions in PowerShell, not all syntax is discussed.</span></span> <span data-ttu-id="4b32d-108">詳細なリファレンスについては、「 [正規表現言語-クイックリファレンス](/dotnet/standard/base-types/regular-expression-language-quick-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b32d-108">For a more complete reference, see the [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span></span>

<span data-ttu-id="4b32d-109">正規表現は、テキストの照合に使用されるパターンです。</span><span class="sxs-lookup"><span data-stu-id="4b32d-109">A regular expression is a pattern used to match text.</span></span> <span data-ttu-id="4b32d-110">これは、リテラル文字、演算子、およびその他の構成体で構成できます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-110">It can be made up of literal characters, operators, and other constructs.</span></span>

<span data-ttu-id="4b32d-111">この記事では、PowerShell での正規表現の構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-111">This article demonstrates regular expression syntax in PowerShell.</span></span> <span data-ttu-id="4b32d-112">PowerShell には、正規表現を使用する複数の演算子とコマンドレットがあります。</span><span class="sxs-lookup"><span data-stu-id="4b32d-112">PowerShell has several operators and cmdlets that use regular expressions.</span></span> <span data-ttu-id="4b32d-113">構文と使用法の詳細については、以下のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b32d-113">You can read more about their syntax and usage at the links below.</span></span>

- [<span data-ttu-id="4b32d-114">Select-String</span><span class="sxs-lookup"><span data-stu-id="4b32d-114">Select-String</span></span>](xref:Microsoft.PowerShell.Utility.Select-String)
- [<span data-ttu-id="4b32d-115">-match および-replace 演算子</span><span class="sxs-lookup"><span data-stu-id="4b32d-115">-match and -replace operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="4b32d-116">-分割</span><span class="sxs-lookup"><span data-stu-id="4b32d-116">-split</span></span>](about_Split.md)
- [<span data-ttu-id="4b32d-117">switch ステートメントと-regex オプション</span><span class="sxs-lookup"><span data-stu-id="4b32d-117">switch statement with -regex option</span></span>](about_Switch.md)

<span data-ttu-id="4b32d-118">PowerShell の正規表現では、既定では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="4b32d-118">PowerShell regular expressions are case-insensitive by default.</span></span> <span data-ttu-id="4b32d-119">上に示した各メソッドは、大文字と小文字の区別を強制する方法が異なります。</span><span class="sxs-lookup"><span data-stu-id="4b32d-119">Each method shown above has a different way to force case sensitivity.</span></span>

|       <span data-ttu-id="4b32d-120">メソッド</span><span class="sxs-lookup"><span data-stu-id="4b32d-120">Method</span></span>       |                      <span data-ttu-id="4b32d-121">大文字と小文字の区別</span><span class="sxs-lookup"><span data-stu-id="4b32d-121">Case Sensitivity</span></span>                      |
| ------------------ | ---------------------------------------------------------- |
| `Select-String`    | <span data-ttu-id="4b32d-122">スイッチの使用 `-CaseSensitive`</span><span class="sxs-lookup"><span data-stu-id="4b32d-122">use `-CaseSensitive` switch</span></span>                                |
| <span data-ttu-id="4b32d-123">`switch` ステートメント</span><span class="sxs-lookup"><span data-stu-id="4b32d-123">`switch` statement</span></span> | <span data-ttu-id="4b32d-124">オプションを使用する `-casesensitive`</span><span class="sxs-lookup"><span data-stu-id="4b32d-124">use the `-casesensitive` option</span></span>                            |
| <span data-ttu-id="4b32d-125">演算子</span><span class="sxs-lookup"><span data-stu-id="4b32d-125">operators</span></span>          | <span data-ttu-id="4b32d-126">**' c '** で始まるプレフィックス ( `-cmatch` 、、 `-csplit` または `-creplace` )</span><span class="sxs-lookup"><span data-stu-id="4b32d-126">prefix with **'c'** (`-cmatch`, `-csplit`, or `-creplace`)</span></span> |

### <a name="character-literals"></a><span data-ttu-id="4b32d-127">文字リテラル</span><span class="sxs-lookup"><span data-stu-id="4b32d-127">Character literals</span></span>

<span data-ttu-id="4b32d-128">正規表現には、リテラル文字または文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-128">A regular expression can be a literal character or a string.</span></span> <span data-ttu-id="4b32d-129">式を指定すると、エンジンは、指定されたテキストを正確に照合します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-129">The expression causes the engine to match the text specified exactly.</span></span>

```powershell
# This statement returns true because book contains the string "oo"
'book' -match 'oo'
```

### <a name="character-classes"></a><span data-ttu-id="4b32d-130">文字クラス</span><span class="sxs-lookup"><span data-stu-id="4b32d-130">Character classes</span></span>

<span data-ttu-id="4b32d-131">文字リテラルは、正確なパターンがわかっている場合には機能しますが、文字クラスを使用すると、より明確にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-131">While character literals work if you know the exact pattern, character classes allow you to be less specific.</span></span>

#### <a name="character-groups"></a><span data-ttu-id="4b32d-132">文字グループ</span><span class="sxs-lookup"><span data-stu-id="4b32d-132">Character groups</span></span>

<span data-ttu-id="4b32d-133">`[character group]` では、任意の数の文字を1回だけ照合でき `[^character group]` ます。一方、はグループに含まれていない文字にのみ一致します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-133">`[character group]` allows you to match any number of characters one time, while `[^character group]` only matches characters NOT in the group.</span></span>

```powershell
# This expression returns true if the pattern matches big, bog, or bug.
'big' -match 'b[iou]g'
```

<span data-ttu-id="4b32d-134">一致する文字の一覧にハイフン文字 () が含まれている場合は、 `-` 文字範囲式と区別するために、リストの先頭または末尾にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b32d-134">If your list of characters to match includes the hyphen character (`-`), it must be at the beginning or end of the list to distinguish it from a character range expression.</span></span>

#### <a name="character-ranges"></a><span data-ttu-id="4b32d-135">文字範囲</span><span class="sxs-lookup"><span data-stu-id="4b32d-135">Character ranges</span></span>

<span data-ttu-id="4b32d-136">パターンは、文字の範囲にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-136">A pattern can also be a range of characters.</span></span> <span data-ttu-id="4b32d-137">文字には、英字 `[A-Z]` 、数字 `[0-9]` 、または ASCII ベース `[ -~]` (印刷可能なすべての文字) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-137">The characters can be alphabetic `[A-Z]`, numeric `[0-9]`, or even ASCII-based `[ -~]` (all printable characters).</span></span>

```powershell
# This expression returns true if the pattern matches any 2 digit number.
42 -match '[0-9][0-9]'
```

#### <a name="numbers"></a><span data-ttu-id="4b32d-138">数値</span><span class="sxs-lookup"><span data-stu-id="4b32d-138">Numbers</span></span>

<span data-ttu-id="4b32d-139">`\d`文字クラスは、任意の10進数字と一致します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-139">The `\d` character class will match any decimal digit.</span></span> <span data-ttu-id="4b32d-140">反対に、 `\D` は10進数以外の数字と一致します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-140">Conversely, `\D` will match any non-decimal digit.</span></span>

```powershell
# This expression returns true if it matches a server name.
# (Server-01 - Server-99).
'Server-01' -match 'Server-\d\d'
```

#### <a name="word-characters"></a><span data-ttu-id="4b32d-141">単語の文字</span><span class="sxs-lookup"><span data-stu-id="4b32d-141">Word characters</span></span>

<span data-ttu-id="4b32d-142">`\w`文字クラスは、任意の単語文字と一致し `[a-zA-Z_0-9]` ます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-142">The `\w` character class will match any word character `[a-zA-Z_0-9]`.</span></span> <span data-ttu-id="4b32d-143">単語以外の文字と一致させるには、を使用し `\W` ます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-143">To match any non-word character, use `\W`.</span></span>

```powershell
# This expression returns true.
# The pattern matches the first word character 'B'.
'Book' -match '\w'
```

#### <a name="wildcards"></a><span data-ttu-id="4b32d-144">ワイルドカード</span><span class="sxs-lookup"><span data-stu-id="4b32d-144">Wildcards</span></span>

<span data-ttu-id="4b32d-145">ピリオド ( `.` ) は、正規表現でのワイルドカード文字です。</span><span class="sxs-lookup"><span data-stu-id="4b32d-145">The period (`.`) is a wildcard character in regular expressions.</span></span> <span data-ttu-id="4b32d-146">改行文字 () を除く任意の文字と一致し `\n` ます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-146">It will match any character except a newline (`\n`).</span></span>

```powershell
# This expression returns true.
# The pattern matches any 4 characters except the newline.
'a1\ ' -match '....'
```

#### <a name="whitespace"></a><span data-ttu-id="4b32d-147">空白文字</span><span class="sxs-lookup"><span data-stu-id="4b32d-147">Whitespace</span></span>

<span data-ttu-id="4b32d-148">空白は、文字クラスを使用して照合され `\s` ます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-148">Whitespace is matched using the `\s` character class.</span></span> <span data-ttu-id="4b32d-149">空白以外の文字は、を使用して照合され `\S` ます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-149">Any non-whitespace character is matched using `\S`.</span></span> <span data-ttu-id="4b32d-150">リテラルスペース文字 `' '` を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-150">Literal space characters `' '` can also be used.</span></span>

```powershell
# This expression returns true.
# The pattern uses both methods to match the space.
' - ' -match '\s- '
```

### <a name="quantifiers"></a><span data-ttu-id="4b32d-151">量指定子</span><span class="sxs-lookup"><span data-stu-id="4b32d-151">Quantifiers</span></span>

<span data-ttu-id="4b32d-152">量指定子は、入力文字列に含まれる各要素のインスタンスの数を制御します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-152">Quantifiers control how many instances of each element should be present in the input string.</span></span>

<span data-ttu-id="4b32d-153">PowerShell で使用可能な量指定子のいくつかを次に示します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-153">The following are a few of the quantifiers available in PowerShell:</span></span>

| <span data-ttu-id="4b32d-154">量指定子</span><span class="sxs-lookup"><span data-stu-id="4b32d-154">Quantifier</span></span> |                <span data-ttu-id="4b32d-155">説明</span><span class="sxs-lookup"><span data-stu-id="4b32d-155">Description</span></span>                |
| ---------- | ----------------------------------------- |
| `*`        | <span data-ttu-id="4b32d-156">0回以上。</span><span class="sxs-lookup"><span data-stu-id="4b32d-156">Zero or more times.</span></span>                       |
| `+`        | <span data-ttu-id="4b32d-157">1回以上。</span><span class="sxs-lookup"><span data-stu-id="4b32d-157">One or more times.</span></span>                        |
| `?`        | <span data-ttu-id="4b32d-158">0回または1回。</span><span class="sxs-lookup"><span data-stu-id="4b32d-158">Zero or one time.</span></span>                         |
| `{n,m}`    | <span data-ttu-id="4b32d-159">少なくとも、少なくとも 1 `n` `m` 回。</span><span class="sxs-lookup"><span data-stu-id="4b32d-159">At least `n`, but no more than `m` times.</span></span> |

<span data-ttu-id="4b32d-160">アスタリスク () は、 `*` 直前の要素の0回以上の繰り返しに一致します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-160">The asterisk (`*`) matches the previous element zero or more times.</span></span> <span data-ttu-id="4b32d-161">結果として、要素のない入力文字列も一致と見なされます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-161">The result is that even an input string without the element would be a match.</span></span>

```powershell
# This returns true for all account name strings even if the name is absent.
'ACCOUNT NAME:    Administrator' -match 'ACCOUNT NAME:\s*\w*'
```

<span data-ttu-id="4b32d-162">正符号 () は、 `+` 直前の要素と1回以上一致します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-162">The plus sign (`+`) matches the previous element one or more times.</span></span>

```powershell
# This returns true if it matches any server name.
'DC-01' -match '[A-Z]+-\d\d'
```

<span data-ttu-id="4b32d-163">疑問符は、 `?` 直前の要素と0回または1回一致します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-163">The question mark `?` matches the previous element zero or one time.</span></span> <span data-ttu-id="4b32d-164">アスタリスクと同様 `*` に、要素が存在しない文字列も一致します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-164">Like asterisk `*`, it will even match strings where the element is absent.</span></span>

```powershell
# This returns true for any server name, even server names without dashes.
'SERVER01' -match '[A-Z]+-?\d\d'
```

<span data-ttu-id="4b32d-165">量 `{n, m}` 指定子は、量指定子をきめ細かく制御できるように、いくつかの異なる方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-165">The `{n, m}` quantifier can be used several different ways to allow granular control over the quantifier.</span></span> <span data-ttu-id="4b32d-166">2番目の要素 `m` とコンマは `,` 省略可能です。</span><span class="sxs-lookup"><span data-stu-id="4b32d-166">The second element `m` and the comma `,` are optional.</span></span>

| <span data-ttu-id="4b32d-167">量指定子</span><span class="sxs-lookup"><span data-stu-id="4b32d-167">Quantifier</span></span> |                <span data-ttu-id="4b32d-168">説明</span><span class="sxs-lookup"><span data-stu-id="4b32d-168">Description</span></span>                 |
| ---------- | ------------------------------------------ |
| `{n}`      | <span data-ttu-id="4b32d-169">正確 `n` な回数に一致します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-169">Match EXACTLY `n` number of times.</span></span>         |
| `{n,}`     | <span data-ttu-id="4b32d-170">少なくとも回数に一致 `n` します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-170">Match at LEAST `n` number of times.</span></span>        |
| `{n,m}`    | <span data-ttu-id="4b32d-171">`n`と `m` の回数の間で一致します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-171">Match between `n` and `m` number of times.</span></span> |

```powershell
# This returns true if it matches any phone number.
'111-222-3333' -match '\d{3}-\d{3}-\d{4}'
```

### <a name="anchors"></a><span data-ttu-id="4b32d-172">アンカー</span><span class="sxs-lookup"><span data-stu-id="4b32d-172">Anchors</span></span>

<span data-ttu-id="4b32d-173">アンカーを使用すると、入力文字列内で一致する位置に基づいて、一致と見なされるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-173">Anchors allow you to cause a match to succeed or fail based on the matches position within the input string.</span></span>

<span data-ttu-id="4b32d-174">一般的に使用される2つのアンカーは `^` と `$` です。</span><span class="sxs-lookup"><span data-stu-id="4b32d-174">The two commonly used anchors are `^` and `$`.</span></span> <span data-ttu-id="4b32d-175">カレットは文字列の `^` 先頭に一致し、は `$` 文字列の末尾に一致します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-175">The caret `^` matches the start of a string, and `$`, which matches the end of a string.</span></span> <span data-ttu-id="4b32d-176">アンカーを使用すると、特定の位置にあるテキストを一致させながら、不要な文字を破棄することができます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-176">The anchors allow you to match your text at a specific position while also discarding unwanted characters.</span></span>

```powershell
# The pattern expects the string 'fish' to be the only thing on the line.
# This returns FALSE.
'fishing' -match '^fish$'
```

> [!NOTE]
> <span data-ttu-id="4b32d-177">アンカーを含む regex を定義する場合 `$` は、二重引用符 () ではなく単一引用符 () を使用して regex を囲む必要があります。そうしないと、 `'` PowerShell に `"` よって式が変数として拡張されます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-177">When defining a regex containing an `$` anchor, be sure to enclose the regex using single quotes (`'`) instead of double quotes (`"`) or PowerShell will expand the expression as a variable.</span></span>

<span data-ttu-id="4b32d-178">PowerShell でアンカーを使用する場合は、 **regexoptions.singleline** と **複数行** の正規表現オプションの違いを理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b32d-178">When using anchors in PowerShell, you should understand the difference between **Singleline** and **Multiline** regular expression options.</span></span>

- <span data-ttu-id="4b32d-179">**Multiline**: 複数行モードでは `^` 、 `$` 入力文字列の先頭と末尾ではなく、すべての行の先頭の末尾とが一致します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-179">**Multiline**: Multiline mode forces `^` and `$` to match the beginning end of every LINE instead of the beginning and end of the input string.</span></span>
- <span data-ttu-id="4b32d-180">**Regexoptions.singleline**: regexoptions.singleline モードでは、入力文字列が **regexoptions.singleline** として扱われます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-180">**Singleline**: Singleline mode treats the input string as a **SingleLine**.</span></span>
  <span data-ttu-id="4b32d-181">`.`改行を除くすべての文字に一致するのではなく、すべての文字が (改行を含めて) 一致するように強制し `\n` ます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-181">It forces the `.` character to match every character (including newlines), instead of matching every character EXCEPT the newline `\n`.</span></span>

<span data-ttu-id="4b32d-182">これらのオプションの詳細と使用方法については、「 [正規表現言語-クイックリファレンス](/dotnet/standard/base-types/regular-expression-language-quick-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b32d-182">To read more about these options and how to use them, visit the [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference).</span></span>

### <a name="escaping-characters"></a><span data-ttu-id="4b32d-183">文字のエスケープ</span><span class="sxs-lookup"><span data-stu-id="4b32d-183">Escaping characters</span></span>

<span data-ttu-id="4b32d-184">バックスラッシュ ( `\` ) は、正規表現エンジンによって解析されないように、文字をエスケープするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-184">The backslash (`\`) is used to escape characters so they aren't parsed by the regular expression engine.</span></span>

<span data-ttu-id="4b32d-185">次の文字が予約されています: `[]().\^$|?*+{}` 。</span><span class="sxs-lookup"><span data-stu-id="4b32d-185">The following characters are reserved: `[]().\^$|?*+{}`.</span></span>

<span data-ttu-id="4b32d-186">これらの文字を入力文字列内で照合するには、パターン内でエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b32d-186">You'll need to escape these characters in your patterns to match them in your input strings.</span></span>

```powershell
# This returns true and matches numbers with at least 2 digits of precision.
# The decimal point is escaped using the backslash.
'3.141' -match '3\.\d{2,}'
```

<span data-ttu-id="4b32d-187">Regex クラスの静的メソッドを使用すると、テキストをエスケープできます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-187">There\`s a static method of the regex class that can escape text for you.</span></span>

```powershell
[regex]::escape('3.\d{2,}')
```

```Output
3\.\\d\{2,}
```

> [!NOTE]
> <span data-ttu-id="4b32d-188">これにより、文字クラスで使用される既存の円記号を含む、予約済みの正規表現文字がすべてエスケープされます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-188">This escapes all reserved regular expression characters, including existing backslashes used in character classes.</span></span> <span data-ttu-id="4b32d-189">これは、エスケープする必要があるパターンの部分でのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="4b32d-189">Be sure to only use it on the portion of your pattern that you need to escape.</span></span>

#### <a name="other-character-escapes"></a><span data-ttu-id="4b32d-190">その他の文字のエスケープ</span><span class="sxs-lookup"><span data-stu-id="4b32d-190">Other character escapes</span></span>

<span data-ttu-id="4b32d-191">特殊文字の種類を一致させるために使用できる予約文字エスケープもあります。</span><span class="sxs-lookup"><span data-stu-id="4b32d-191">There are also reserved character escapes that you can use to match special character types.</span></span>

<span data-ttu-id="4b32d-192">一般的に使用される文字エスケープをいくつか次に示します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-192">The following are a few commonly used character escapes:</span></span>

|<span data-ttu-id="4b32d-193">文字エスケープ</span><span class="sxs-lookup"><span data-stu-id="4b32d-193">Character Escape</span></span>  |<span data-ttu-id="4b32d-194">説明</span><span class="sxs-lookup"><span data-stu-id="4b32d-194">Description</span></span>  |
|---------|---------|
|`\t`|<span data-ttu-id="4b32d-195">タブに一致します</span><span class="sxs-lookup"><span data-stu-id="4b32d-195">Matches a tab</span></span>|
|`\n`|<span data-ttu-id="4b32d-196">改行に一致します</span><span class="sxs-lookup"><span data-stu-id="4b32d-196">Matches a newline</span></span>|
|`\r`|<span data-ttu-id="4b32d-197">キャリッジリターンと一致します</span><span class="sxs-lookup"><span data-stu-id="4b32d-197">Matches a carriage return</span></span>|

### <a name="groups-captures-and-substitutions"></a><span data-ttu-id="4b32d-198">グループ、キャプチャ、および置換</span><span class="sxs-lookup"><span data-stu-id="4b32d-198">Groups, Captures, and Substitutions</span></span>

<span data-ttu-id="4b32d-199">グループ化構成体は、入力文字列をキャプチャまたは無視できる部分文字列に分割します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-199">Grouping constructs separate an input string into substrings that can be captured or ignored.</span></span> <span data-ttu-id="4b32d-200">グループ化された部分文字列を部分式と呼びます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-200">Grouped substrings are called subexpressions.</span></span> <span data-ttu-id="4b32d-201">既定では、部分式は番号付きグループにキャプチャされますが、名前を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-201">By default subexpressions are captured in numbered groups, though you can assign names to them as well.</span></span>

<span data-ttu-id="4b32d-202">グループ化構成体は、かっこで囲まれた正規表現です。</span><span class="sxs-lookup"><span data-stu-id="4b32d-202">A grouping construct is a regular expression surrounded by parentheses.</span></span> <span data-ttu-id="4b32d-203">囲まれた正規表現に一致するテキストがキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-203">Any text matched by the enclosed regular expression is captured.</span></span> <span data-ttu-id="4b32d-204">次の例では、入力テキストを2つのキャプチャグループに分割します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-204">The following example will break the input text into two capturing groups.</span></span>

```powershell
'The last logged on user was CONTOSO\jsmith' -match '(.+was )(.+)'
```

```Output
True
```

<span data-ttu-id="4b32d-205">`$Matches`キャプチャしたテキストを取得するには、 **Hashtable** 自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-205">Use the `$Matches` **Hashtable** automatic variable to retrieve captured text.</span></span>
<span data-ttu-id="4b32d-206">一致した文字列全体を表すテキストは、キーに格納され `0` ます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-206">The text representing the entire match is stored at key `0`.</span></span>

```powershell
$Matches.0
```

```Output
The last logged on user was CONTOSO\jsmith
```

<span data-ttu-id="4b32d-207">キャプチャは、左から右に増加する数値の **整数** キーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-207">Captures are stored in numeric **Integer** keys that increase from left to right.</span></span> <span data-ttu-id="4b32d-208">Capture には、 `1` ユーザー名になるまですべてのテキストが含まれており、capture には `2` ユーザー名だけが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b32d-208">Capture `1` contains all the text until the username, capture `2` contains just the username.</span></span>

```powershell
$Matches
```

```Output
Name                           Value
----                           -----
2                              CONTOSO\jsmith
1                              The last logged on user was
0                              The last logged on user was CONTOSO\jsmith
```

> [!IMPORTANT]
> <span data-ttu-id="4b32d-209">`0`キーは **整数** です。</span><span class="sxs-lookup"><span data-stu-id="4b32d-209">The `0` key is an **Integer**.</span></span> <span data-ttu-id="4b32d-210">任意の **ハッシュテーブル** メソッドを使用して、格納されている値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-210">You can use any **Hashtable** method to access the value stored.</span></span>
>
> ```
> PS> 'Good Dog' -match 'Dog'
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

#### <a name="named-captures"></a><span data-ttu-id="4b32d-211">名前付きキャプチャ</span><span class="sxs-lookup"><span data-stu-id="4b32d-211">Named Captures</span></span>

<span data-ttu-id="4b32d-212">既定では、キャプチャは左から右に昇順で格納されます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-212">By default, captures are stored in ascending numeric order, from left to right.</span></span>
<span data-ttu-id="4b32d-213">キャプチャグループに **名前** を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-213">You can also assign a **name** to a capturing group.</span></span> <span data-ttu-id="4b32d-214">この **名前** は、 `$Matches` **ハッシュテーブル** の自動変数のキーになります。</span><span class="sxs-lookup"><span data-stu-id="4b32d-214">This **name** becomes a key on the `$Matches` **Hashtable** automatic variable.</span></span>

<span data-ttu-id="4b32d-215">キャプチャグループ内で、を使用して、 `?<keyname>` キャプチャされたデータを名前付きキーの下に格納します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-215">Inside a capturing group, use `?<keyname>` to store captured data under a named key.</span></span>

```
PS> $string = 'The last logged on user was CONTOSO\jsmith'
PS> $string -match 'was (?<domain>.+)\\(?<user>.+)'
True

PS> $Matches

Name                           Value
----                           -----
domain                         CONTOSO
user                           jsmith
0                              was CONTOSO\jsmith

PS> $Matches.domain
CONTOSO

PS> $Matches.user
jsmith
```

<span data-ttu-id="4b32d-216">次の例では、Windows セキュリティログに最新のログエントリを格納します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-216">The following example stores the newest log entry in the Windows Security Log.</span></span>
<span data-ttu-id="4b32d-217">指定された正規表現は、メッセージからユーザー名とドメインを抽出し、キーの下に格納します。名前の場合は **N** 、ドメインの場合は **D** です。</span><span class="sxs-lookup"><span data-stu-id="4b32d-217">The provided regular expression extracts the username and domain from the message and stores them under the keys:**N** for name and **D** for domain.</span></span>

```powershell
$log = (Get-WinEvent -LogName Security -MaxEvents 1).message
$r = '(?s).*Account Name:\s*(?<N>.*).*Account Domain:\s*(?<D>[A-Z,0-9]*)'
$log -match $r
```

```Output
True
```

```powershell
$Matches
```

```Output
Name                           Value
----                           -----
D                              CONTOSO
N                              jsmith
0                              A process has exited....
```

<span data-ttu-id="4b32d-218">詳細については、「 [正規表現でのグループ化構成体](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b32d-218">For more information, see [Grouping Constructs in Regular Expressions](/dotnet/standard/base-types/grouping-constructs-in-regular-expressions).</span></span>

#### <a name="substitutions-in-regular-expressions"></a><span data-ttu-id="4b32d-219">正規表現での置換</span><span class="sxs-lookup"><span data-stu-id="4b32d-219">Substitutions in Regular Expressions</span></span>

<span data-ttu-id="4b32d-220">演算子で正規表現を使用すると、 `-replace` キャプチャしたテキストを使用してテキストを動的に置換できます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-220">Using the regular expressions with the `-replace` operator allows you to dynamically replace text using captured text.</span></span>

`<input> -replace <original>, <substitute>`

- <span data-ttu-id="4b32d-221">`<input>`: 検索する文字列</span><span class="sxs-lookup"><span data-stu-id="4b32d-221">`<input>`: The string to be searched</span></span>
- <span data-ttu-id="4b32d-222">`<original>`: 入力文字列の検索に使用する正規表現</span><span class="sxs-lookup"><span data-stu-id="4b32d-222">`<original>`: A regular expression used to search the input string</span></span>
- <span data-ttu-id="4b32d-223">`<substitute>`: 入力文字列で見つかった一致項目を置換する正規表現の置換式。</span><span class="sxs-lookup"><span data-stu-id="4b32d-223">`<substitute>`: A regular expression substitution expression to replace matches found in the input string.</span></span>

> [!NOTE]
> <span data-ttu-id="4b32d-224">`<original>`オペランドと `<substitute>` オペランドは、文字エスケープなどの正規表現エンジンの規則に従います。</span><span class="sxs-lookup"><span data-stu-id="4b32d-224">The `<original>` and `<substitute>` operands are subject to rules of the regular expression engine such as character escaping.</span></span>

<span data-ttu-id="4b32d-225">キャプチャグループは、文字列内で参照でき `<substitute>` ます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-225">Capturing groups can be referenced in the `<substitute>` string.</span></span> <span data-ttu-id="4b32d-226">置換を行うには、 `$` グループ識別子の前にある文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-226">The substitution is done by using the `$` character before the group identifier.</span></span>

<span data-ttu-id="4b32d-227">キャプチャグループを参照する2つの方法は、数値と **名前** で **指定** します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-227">Two ways to reference capturing groups are by **Number** and by **Name**.</span></span>

- <span data-ttu-id="4b32d-228">**数値** キャプチャグループには、左から右に番号が付けられます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-228">By **Number** - Capturing Groups are numbered from left to right.</span></span>

  ```powershell
  'John D. Smith' -replace '(\w+) (\w+)\. (\w+)', '$1.$2.$3@contoso.com'
  ```

  ```Output
  John.D.Smith@contoso.com
  ```

- <span data-ttu-id="4b32d-229">**名前** のキャプチャグループは、名前によって参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b32d-229">By **Name** - Capturing Groups can also be referenced by name.</span></span>

  ```powershell
  'CONTOSO\Administrator' -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  ```

  ```Output
  FABRIKAM\Administrator
  ```

<span data-ttu-id="4b32d-230">`$&`式は、一致したすべてのテキストを表します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-230">The `$&` expression represents all the text matched.</span></span>

```powershell
'Gobble' -replace 'Gobble', '$& $&'
```

```Output
Gobble Gobble
```

> [!WARNING]
> <span data-ttu-id="4b32d-231">文字は `$` 文字列の展開で使用されるため、置換でリテラル文字列を使用するか、 `$` 二重引用符を使用する場合は文字をエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b32d-231">Since the `$` character is used in string expansion, you'll need to use literal strings with substitution, or escape the `$` character when using double quotes.</span></span>
>
> ```powershell
> 'Hello World' -replace '(\w+) \w+', '$1 Universe'
> "Hello World" -replace "(\w+) \w+", "`$1 Universe"
> ```
>
> ```Output
> Hello Universe
> Hello Universe
> ```
>
> <span data-ttu-id="4b32d-232">また、を `$` リテラル文字として使用する場合は、 `$$` 通常のエスケープ文字の代わりにを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b32d-232">Additionally, if you want to have the `$` as a literal character, use `$$` instead of the normal escape characters.</span></span> <span data-ttu-id="4b32d-233">二重引用符を使用する場合でも、 `$` 不適切な置換を避けるために、のすべてのインスタンスをエスケープします。</span><span class="sxs-lookup"><span data-stu-id="4b32d-233">When using double quotes, still escape all instances of `$` to avoid incorrect substitution.</span></span>
>
> ```powershell
> '5.72' -replace '(.+)', '$$$1'
> "5.72" -replace "(.+)", "`$`$`$1"
> ```
>
> ```Output
> $5.72
> $5.72
> ```

<span data-ttu-id="4b32d-234">詳細については、「 [正規表現での置換](/dotnet/standard/base-types/substitutions-in-regular-expressions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b32d-234">For more information, see [Substitutions in Regular Expressions](/dotnet/standard/base-types/substitutions-in-regular-expressions).</span></span>

## <a name="see-also"></a><span data-ttu-id="4b32d-235">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b32d-235">See also</span></span>

[<span data-ttu-id="4b32d-236">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="4b32d-236">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="4b32d-237">about_Operators</span><span class="sxs-lookup"><span data-stu-id="4b32d-237">about_Operators</span></span>](about_Operators.md)

