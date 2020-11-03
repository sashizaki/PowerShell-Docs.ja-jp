---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convert-string?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-String
ms.openlocfilehash: 29ec9e21277bae02ab94ce5e862787c86a87b439
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214147"
---
# <span data-ttu-id="c5b9b-103">Convert-String</span><span class="sxs-lookup"><span data-stu-id="c5b9b-103">Convert-String</span></span>

## <span data-ttu-id="c5b9b-104">概要</span><span class="sxs-lookup"><span data-stu-id="c5b9b-104">SYNOPSIS</span></span>
<span data-ttu-id="c5b9b-105">例と一致するように文字列を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-105">Formats a string to match examples.</span></span>

## <span data-ttu-id="c5b9b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c5b9b-106">SYNTAX</span></span>

```
Convert-String [-Example <System.Collections.Generic.List`1[System.Management.Automation.PSObject]>]
 -InputObject <String> [<CommonParameters>]
```

## <span data-ttu-id="c5b9b-107">Description</span><span class="sxs-lookup"><span data-stu-id="c5b9b-107">DESCRIPTION</span></span>

<span data-ttu-id="c5b9b-108">**Convert 文字列** コマンドレットは、例の形式に一致するように文字列を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-108">The **Convert-String** cmdlet formats a string to match the format of examples.</span></span>

## <span data-ttu-id="c5b9b-109">例</span><span class="sxs-lookup"><span data-stu-id="c5b9b-109">EXAMPLES</span></span>

### <span data-ttu-id="c5b9b-110">例 1: 文字列の形式を変換する</span><span class="sxs-lookup"><span data-stu-id="c5b9b-110">Example 1: Convert format of a string</span></span>

```powershell
"Mu Han", "Jim Hance", "David Ahs", "Kim Akers" | Convert-String -Example "Ed Wilson=Wilson, E."
```

```output
Han, M.
Hance, J.
Ahs, D.
Akers, K.
```

<span data-ttu-id="c5b9b-111">最初のコマンドは、名と姓を含む配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-111">The first command creates an array that contains first and last names.</span></span>

<span data-ttu-id="c5b9b-112">2番目のコマンドは、例に従って名前を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-112">The second command formats the names according to the example.</span></span>
<span data-ttu-id="c5b9b-113">このメソッドは、出力の先頭に姓を付け、その後に最初のを配置します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-113">It puts the surname first in the output, followed by an initial.</span></span>

### <span data-ttu-id="c5b9b-114">例 2: 文字列の書式を簡略化する</span><span class="sxs-lookup"><span data-stu-id="c5b9b-114">Example 2: Simplify format of a string</span></span>

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=last, first"
```

```output
Bach, Johann
Mozart, Wolfgang
Chopin, Frederic
Brahms, Johannes
```

<span data-ttu-id="c5b9b-115">最初のコマンドは、名、ミドルネーム、および姓を含む配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-115">The first command creates an array that contains first, middle and last names.</span></span>
<span data-ttu-id="c5b9b-116">最後のエントリにはミドルネームが含まれていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-116">Note that the last entry has no middle name.</span></span>

<span data-ttu-id="c5b9b-117">2番目のコマンドは、例に従って名前を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-117">The second command formats the names according to the example.</span></span>
<span data-ttu-id="c5b9b-118">このメソッドは、出力の先頭に姓を置き、その後に名を付けます。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-118">It puts the last name first in the output, followed by the first name.</span></span>
<span data-ttu-id="c5b9b-119">すべてのミドルネームが削除されました。ミドルネームのないエントリが正しく処理されています。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-119">All middle names removed; entry without middle name is handled correctly.</span></span>

### <span data-ttu-id="c5b9b-120">例 3: 文字列が一致しない場合の出力管理の例</span><span class="sxs-lookup"><span data-stu-id="c5b9b-120">Example 3: Output management when strings don't match example</span></span>

```powershell
$composers = @("Johann Sebastian Bach", "Wolfgang Amadeus Mozart", "Frederic Francois Chopin", "Johannes Brahms")
$composers | Convert-String -Example "first middle last=middle, first"
```

```output
Sebastian, Johann
Amadeus, Wolfgang
Francois, Frederic
```

<span data-ttu-id="c5b9b-121">最初のコマンドは、名、ミドルネーム、および姓を含む配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-121">The first command creates an array that contains first, middle and last names.</span></span>
<span data-ttu-id="c5b9b-122">最後のエントリにはミドルネームが含まれていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-122">Note that the last entry has no middle name.</span></span>

<span data-ttu-id="c5b9b-123">2番目のコマンドは、例に従って名前を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-123">The second command formats the names according to the example.</span></span>
<span data-ttu-id="c5b9b-124">このメソッドは、出力の先頭に **ミドル** ネームを付け、その後に名を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-124">It puts the **middle name** first in the output, followed by the first name.</span></span>
<span data-ttu-id="c5b9b-125">**$Composers** の最後のエントリは、サンプルパターンと一致しないため、スキップされます。ミドルネームはありません。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-125">The last entry in **$Composers** is skipped, because it doesn't match the sample pattern: it has no middle name.</span></span>

### <span data-ttu-id="c5b9b-126">例 4: 美しさスペースでの注意事項</span><span class="sxs-lookup"><span data-stu-id="c5b9b-126">Example 4: Caution with beauty spaces</span></span>

```powershell
$composers = @("Antonio Vivaldi", "Richard Wagner ", "Franz Schubert", "Johannes Brahms ")
$composers | Convert-String -Example "Patti Fuller = Fuller, P."
```

```output
 Wagner, R.
 Brahms, J.
```

<span data-ttu-id="c5b9b-127">最初のコマンドは、姓と名の配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-127">The first command creates an array of first and last names.</span></span>
<span data-ttu-id="c5b9b-128">2番目と4番目の項目は、最後の名前の後に余分な末尾のスペースがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-128">Note that second and fourth items have an extra trailing space, after the last name.</span></span>

<span data-ttu-id="c5b9b-129">2番目のコマンドは、サンプルパターンに一致するすべての文字列を変換します。これは、 _単語、スペース、単語、および最後の末尾のスペース_ で、等号の前にあります。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-129">The second command converts all strings that match the sample pattern: _word, space, word, and final trailing space_ , all of this before the equal sign.</span></span>
<span data-ttu-id="c5b9b-130">また、出力の先頭のスペースに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-130">Also, note the leading space in the output.</span></span>

### <span data-ttu-id="c5b9b-131">例 5: 複数のパターンを使用したプロセス情報の書式設定</span><span class="sxs-lookup"><span data-stu-id="c5b9b-131">Example 5: Format process information with multiple patterns</span></span>

```powershell
$ExamplePatterns = @(
    @{before='"Hello","World"'; after='World: Hello'},
    @{before='"Hello","1"'; after='1: Hello'},
    @{before='"Hello-World","22"'; after='22: Hello-World'},
    @{before='"hello world","333"'; after='333: hello world'}
)
$Processes = Get-Process   | Select-Object -Property ProcessName, Id | ConvertTo-Csv -NoTypeInformation
$Processes | Convert-String -Example $ExamplePatterns
```

```output
Id: ProcessName
4368: AGSService
8896: Amazon Music Helper
4420: AppleMobileDeviceService
...
11140: git-bash
0: Idle
...
56: Secure System
...
13028: WmiPrvSE
2724: WUDFHost
2980: WUDFHost
3348: WUDFHost
```

<span data-ttu-id="c5b9b-132">**$ExamplePatterns** は、例を使用して、データ内のさまざまな予想されるパターンを定義します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-132">**$ExamplePatterns** defines different expected patterns in the data, through examples.</span></span>

<span data-ttu-id="c5b9b-133">最初のパターンであるは、次のように `@{before='"Hello","World"'; after='World: Hello'}` 読み取られます。 _単語が二重引用符で囲まれていること、コンマ、_ 
 _2 番目、最後の単語が引用符で囲ま_ れていることを想定しています。 
_文字列にスペースが含まれていません。出力: 2 番目の単語を_ 
 _引用符で囲まずに1つだけ配置します。次に、単一の空白と最初の単語を引用符で囲み_ ません。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-133">The first pattern, `@{before='"Hello","World"'; after='World: Hello'}`, reads as follows: _expect strings where a word comes enclosed in double quotes, then a comma,_
_and then the second, and last, word enclosed in quotes;_
_with no spaces in the string. On the output: place second word first,_
_without quotes, then a single space, and then the first word, without quotes._</span></span>

<span data-ttu-id="c5b9b-134">2番目のパターンは、次のように `@{before='"Hello","1"'; after='1: Hello'}` 読み取られます。 _単語が二重引用符で囲まれていること、コンマ、_ 
 _および引用符で囲ま_ れた数値であることが想定されます。 
_文字列にスペースが含まれていません。[出力]:_ 引用符を使用せずに数字を最初に配置します。次に、 
 _単一のスペースと単語を引用符で囲みません。_</span><span class="sxs-lookup"><span data-stu-id="c5b9b-134">The second pattern, `@{before='"Hello","1"'; after='1: Hello'}`, reads as follows: _expect strings where a word comes enclosed in double quotes, then a comma,_
_and then a number enclosed in quotes;_
_with no spaces in the string. On the output: place the number first,_
_without quotes, then a single space, and then the word, without quotes._</span></span>

<span data-ttu-id="c5b9b-135">3番目のパターンでは、は `@{before='"Hello-World","22"'; after='22: Hello-World'}` 次のように読み取られます。 _2 つの単語の間にハイフン_ が含まれている場合は、 
 _二重引用符、コンマ、および引用符で囲ま_ れた数字で囲まれます。 
_コンマと3番目の二重引用符の間にスペースを入れません。_ 
_出力の場合: 最初に数字を引用符で囲み、1つのスペース_ 
 を追加します。 _ハイフンで囲まれた単語は引用符で囲みません。_</span><span class="sxs-lookup"><span data-stu-id="c5b9b-135">The third pattern, `@{before='"Hello-World","22"'; after='22: Hello-World'}`, reads as follows: _expect strings where two words with a hyphen in between come enclosed in_
_double quotes, then a comma, and then a number enclosed in quotes;_
_with no spaces between the comma and the third double quote._
_On the output: place the number first, without quotes, then a single space,_
_and then the hyphenated words, without quotes._</span></span>

<span data-ttu-id="c5b9b-136">4番目と最後のパターンは、次のように `@{before='"hello world","333"'; after='333: hello world'}` 読み取られます。 _2 つの単語の間にスペースが含ま_ れている場合は、 
 _二重引用符、コンマ、および引用符で囲ま_ れた数字で囲まれます。 
_コンマと3番目の二重引用符の間にスペースを入れません。_ 
_出力の場合: 最初に数字を引用符で囲み、1つのスペース_ 
 を追加します。次に、引用符を使用 _せずに、between の間にスペースがある単語を指定します。_</span><span class="sxs-lookup"><span data-stu-id="c5b9b-136">The fourth, and final, pattern, `@{before='"hello world","333"'; after='333: hello world'}`, reads as follows: _expect strings where two words with a space in between come enclosed in_
_double quotes, then a comma, and then a number enclosed in quotes;_
_with no spaces between the comma and the third double quote._
_On the output: place the number first, without quotes, then a single space,_
_and then the words with the space in between, without quotes._</span></span>

<span data-ttu-id="c5b9b-137">最初のコマンドは、Get-Process コマンドレットを使用して、すべてのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-137">The first command gets all processes by using the Get-Process cmdlet.</span></span>
<span data-ttu-id="c5b9b-138">このコマンドは、プロセス名とプロセス ID を選択する Select-Object コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-138">The command passes them to the Select-Object cmdlet, which selects the process name and process ID.</span></span> <span data-ttu-id="c5b9b-139">パイプラインの最後では、ConvertTo-Csv コマンドレットを使用して、出力を型情報のないコンマ区切り値に変換します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-139">At the end of the pipeline, the command converts the output to comma separated values, without type information, by using the ConvertTo-Csv cmdlet.</span></span>
<span data-ttu-id="c5b9b-140">このコマンドは、結果を **$Processes** 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-140">The command stores the results in the **$Processes** variable.</span></span>
<span data-ttu-id="c5b9b-141">**$Processes** にプロセス名と PID が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-141">**$Processes** now contains process names and PID.</span></span>

<span data-ttu-id="c5b9b-142">2番目のコマンドは、入力項目の順序を変更するサンプル変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-142">The second command specifies an example variable that changes the order of the input items.</span></span>
<span data-ttu-id="c5b9b-143">このコマンドは、 **$Processes** 内の各文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-143">The command coverts each string in **$Processes** .</span></span>

><span data-ttu-id="c5b9b-144">**メモ** 4番目のパターンは、スペースで区切られた2つ以上の単語が一致することを暗黙的に示しています。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-144">**Note** The fourth pattern implicitly says that two or more words separated by spaces are matched.</span></span>
>
><span data-ttu-id="c5b9b-145">4番目のパターンを使用しない場合、二重引用符で囲まれた文字列の最初の単語のみが一致します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-145">Without the fourth pattern, only the first word of the string enclosed in double quotes is matched.</span></span>

## <span data-ttu-id="c5b9b-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c5b9b-146">PARAMETERS</span></span>

### <span data-ttu-id="c5b9b-147">-例</span><span class="sxs-lookup"><span data-stu-id="c5b9b-147">-Example</span></span>

<span data-ttu-id="c5b9b-148">対象の形式の例の一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-148">Specifies a list of examples of the target format.</span></span>
<span data-ttu-id="c5b9b-149">次の例のように、等号 (=) 記号で区切られたペアを指定します。次の例のように、左側にはソースパターン、右側にはターゲットパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-149">Specify pairs separated by the equal (=) sign, with the source pattern on the left and the target pattern on the right, as in the following examples:</span></span>

* `-Example "Hello World=World, Hello"`
* `-Example "Hello World=World: Hello",'"Hello","1"=1: Hello'`

><span data-ttu-id="c5b9b-150">**メモ** 2番目の例では、パターンの一覧を使用します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-150">**Note** The second example uses a list of patterns</span></span>

<span data-ttu-id="c5b9b-151">または、 **Before** および **After** プロパティを含むハッシュテーブルの一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-151">Alternatively, specify a list of hash tables that contain **Before** and **After** properties.</span></span>

* `-Example @{before='"Hello","World"'; after='World: Hello'}, @{before='"Hello","1"'; after='1: Hello'}`

><span data-ttu-id="c5b9b-152">**注意** 等号はパターンの一部として扱われるため、等号の周りにスペースを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-152">**Caution** Avoid using spaces around the equal sign, as they are treated as part of the pattern.</span></span>

```yaml
Type: System.Collections.Generic.List`1[System.Management.Automation.PSObject]
Parameter Sets: (All)
Aliases: E

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c5b9b-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c5b9b-153">-InputObject</span></span>

<span data-ttu-id="c5b9b-154">書式設定する文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-154">Specifies a string to format.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c5b9b-155">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c5b9b-155">CommonParameters</span></span>

<span data-ttu-id="c5b9b-156">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c5b9b-157">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c5b9b-158">入力</span><span class="sxs-lookup"><span data-stu-id="c5b9b-158">INPUTS</span></span>

### <span data-ttu-id="c5b9b-159">String</span><span class="sxs-lookup"><span data-stu-id="c5b9b-159">String</span></span>

<span data-ttu-id="c5b9b-160">このコマンドレットに文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-160">You can pipe strings to this cmdlet.</span></span>

## <span data-ttu-id="c5b9b-161">出力</span><span class="sxs-lookup"><span data-stu-id="c5b9b-161">OUTPUTS</span></span>

### <span data-ttu-id="c5b9b-162">String</span><span class="sxs-lookup"><span data-stu-id="c5b9b-162">String</span></span>

<span data-ttu-id="c5b9b-163">このコマンドレットは文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="c5b9b-163">This cmdlet returns a string.</span></span>

## <span data-ttu-id="c5b9b-164">注</span><span class="sxs-lookup"><span data-stu-id="c5b9b-164">NOTES</span></span>

## <span data-ttu-id="c5b9b-165">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c5b9b-165">RELATED LINKS</span></span>

[<span data-ttu-id="c5b9b-166">ConvertFrom-String</span><span class="sxs-lookup"><span data-stu-id="c5b9b-166">ConvertFrom-String</span></span>](ConvertFrom-String.md)

[<span data-ttu-id="c5b9b-167">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="c5b9b-167">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="c5b9b-168">Get-Process</span><span class="sxs-lookup"><span data-stu-id="c5b9b-168">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)

[<span data-ttu-id="c5b9b-169">Out-String</span><span class="sxs-lookup"><span data-stu-id="c5b9b-169">Out-String</span></span>](Out-String.md)

[<span data-ttu-id="c5b9b-170">Select-Object</span><span class="sxs-lookup"><span data-stu-id="c5b9b-170">Select-Object</span></span>](Select-Object.md)
