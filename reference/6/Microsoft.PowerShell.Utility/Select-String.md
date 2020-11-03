---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-string?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-String
ms.openlocfilehash: 89880bc5ae45f442bea2d9c1f71d7df4cfa5e333
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "93219707"
---
# <span data-ttu-id="1de0d-103">Select-String</span><span class="sxs-lookup"><span data-stu-id="1de0d-103">Select-String</span></span>

## <span data-ttu-id="1de0d-104">概要</span><span class="sxs-lookup"><span data-stu-id="1de0d-104">SYNOPSIS</span></span>
<span data-ttu-id="1de0d-105">文字列とファイル内のテキストを検索します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-105">Finds text in strings and files.</span></span>

## <span data-ttu-id="1de0d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1de0d-106">SYNTAX</span></span>

### <span data-ttu-id="1de0d-107">File (既定値)</span><span class="sxs-lookup"><span data-stu-id="1de0d-107">File (Default)</span></span>

```
Select-String [-Pattern] <String[]> [-Path] <String[]> [-SimpleMatch] [-CaseSensitive] [-Quiet]
 [-List] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch] [-AllMatches]
 [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="1de0d-108">Object</span><span class="sxs-lookup"><span data-stu-id="1de0d-108">Object</span></span>

```
Select-String -InputObject <PSObject> [-Pattern] <String[]> [-SimpleMatch] [-CaseSensitive] [-Quiet]
 [-List] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch] [-AllMatches]
 [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="1de0d-109">LiteralFile</span><span class="sxs-lookup"><span data-stu-id="1de0d-109">LiteralFile</span></span>

```
Select-String [-Pattern] <String[]> -LiteralPath <String[]> [-SimpleMatch] [-CaseSensitive] [-Quiet]
 [-List] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch] [-AllMatches]
 [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

## <span data-ttu-id="1de0d-110">Description</span><span class="sxs-lookup"><span data-stu-id="1de0d-110">DESCRIPTION</span></span>

<span data-ttu-id="1de0d-111">コマンドレットでは、 `Select-String` 入力文字列とファイル内のテキストパターンとテキストパターンを検索します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-111">The `Select-String` cmdlet searches for text and text patterns in input strings and files.</span></span> <span data-ttu-id="1de0d-112">`Select-String`UNIX または Windows の **findstr.exe** と同様に **、を使用** することもできます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-112">You can use `Select-String` similar to **grep** in UNIX or **findstr.exe** in Windows.</span></span>

<span data-ttu-id="1de0d-113">`Select-String` は、テキストの行に基づいています。</span><span class="sxs-lookup"><span data-stu-id="1de0d-113">`Select-String` is based on lines of text.</span></span> <span data-ttu-id="1de0d-114">既定では、は各行 `Select-String` で最初の一致を検索し、一致するたびに、ファイル名、行番号、および一致を含む行のすべてのテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-114">By default, `Select-String` finds the first match in each line and, for each match, it displays the file name, line number, and all text in the line containing the match.</span></span> <span data-ttu-id="1de0d-115">`Select-String`1 行に複数の一致項目を検索したり、一致の前後のテキストを表示したり、一致が見つかったかどうかを示すブール値 (True または False) を表示したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-115">You can direct `Select-String` to find multiple matches per line, display text before and after the match, or display a Boolean value (True or False) that indicates whether a match is found.</span></span>

<span data-ttu-id="1de0d-116">`Select-String` 正規表現の照合を使用しますが、指定したテキストの入力を検索する一致も実行できます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-116">`Select-String` uses regular expression matching, but it can also perform a match that searches the input for the text that you specify.</span></span>

<span data-ttu-id="1de0d-117">`Select-String` 各入力ファイルで、すべてのテキストの一致を表示するか、最初の一致の後に停止します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-117">`Select-String` can display all the text matches or stop after the first match in each input file.</span></span>
<span data-ttu-id="1de0d-118">`Select-String` を使用すると、指定したパターンに一致しないすべてのテキストを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-118">`Select-String` can be used to display all text that doesn't match the specified pattern.</span></span>

<span data-ttu-id="1de0d-119">`Select-String`Unicode テキストのファイルを検索する場合など、で特定の文字エンコーディングを使用するように指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-119">You can also specify that `Select-String` should expect a particular character encoding, such as when you're searching files of Unicode text.</span></span> <span data-ttu-id="1de0d-120">`Select-String` バイト順マーク (BOM) を使用して、ファイルのエンコード形式を検出します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-120">`Select-String` uses the byte-order-mark (BOM) to detect the encoding format of the file.</span></span> <span data-ttu-id="1de0d-121">ファイルに BOM がない場合は、エンコードが UTF8 であると想定されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-121">If the file has no BOM, it assumes the encoding is UTF8.</span></span>

## <span data-ttu-id="1de0d-122">例</span><span class="sxs-lookup"><span data-stu-id="1de0d-122">EXAMPLES</span></span>

### <span data-ttu-id="1de0d-123">例 1: 大文字と小文字を区別する一致を検索する</span><span class="sxs-lookup"><span data-stu-id="1de0d-123">Example 1: Find a case-sensitive match</span></span>

<span data-ttu-id="1de0d-124">この例では、コマンドレットにパイプラインで送信されたテキストの大文字と小文字が区別され `Select-String` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-124">This example does a case-sensitive match of the text that was sent down the pipeline to the `Select-String` cmdlet.</span></span>

```powershell
'Hello', 'HELLO' | Select-String -Pattern 'HELLO' -CaseSensitive -SimpleMatch
```

<span data-ttu-id="1de0d-125">テキスト文字列 **hello** と **hello** は、パイプラインの下にコマンドレットに送信され `Select-String` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-125">The text strings **Hello** and **HELLO** are sent down the pipeline to the `Select-String` cmdlet.</span></span>
<span data-ttu-id="1de0d-126">`Select-String`**Pattern** パラメーターを使用して **HELLO** を指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-126">`Select-String` uses the **Pattern** parameter to specify **HELLO**.</span></span> <span data-ttu-id="1de0d-127">**CaseSensitive** パラメーターは、大文字と小文字のパターンのみが一致する必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-127">The **CaseSensitive** parameter specifies that the case must match only the upper-case pattern.</span></span> <span data-ttu-id="1de0d-128">**SimpleMatch** は省略可能なパラメーターで、パターン内の文字列が正規表現として解釈されないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-128">**SimpleMatch** is an optional parameter and specifies that the string in the pattern isn't interpreted as a regular expression.</span></span>
<span data-ttu-id="1de0d-129">`Select-String` PowerShell コンソールに " **HELLO** " と表示されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-129">`Select-String` displays **HELLO** in the PowerShell console.</span></span>

### <span data-ttu-id="1de0d-130">例 2: テキストファイル内の一致項目を検索する</span><span class="sxs-lookup"><span data-stu-id="1de0d-130">Example 2: Find matches in text files</span></span>

<span data-ttu-id="1de0d-131">このコマンドは、現在のディレクトリ内のファイル名拡張子を持つすべてのファイルを検索 `.txt` します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-131">This command searches all files with the `.txt` file name extension in the current directory.</span></span> <span data-ttu-id="1de0d-132">出力には、指定した文字列を含むファイル内の行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-132">The output displays the lines in those files that include the specified string.</span></span>

```powershell
Get-Alias | Out-File -FilePath .\Alias.txt
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\*.txt -Pattern 'Get-'
```

```Output
Alias.txt:8:Alias            cat -> Get-Content
Alias.txt:28:Alias           dir -> Get-ChildItem
Alias.txt:43:Alias           gal -> Get-Alias
Command.txt:966:Cmdlet       Get-Acl
Command.txt:967:Cmdlet       Get-Alias
```

<span data-ttu-id="1de0d-133">この例で `Get-Alias` は、とを `Get-Command` コマンドレットと共に使用して、現在の `Out-File` ディレクトリに2つのテキストファイルを作成し、 **Alias.txt** と **Command.txt** します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-133">In this example, `Get-Alias` and `Get-Command` are used with the `Out-File` cmdlet to create two text files in the current directory, **Alias.txt** and **Command.txt**.</span></span>

<span data-ttu-id="1de0d-134">`Select-String`**Path** パラメーターをアスタリスク () ワイルドカードと共に使用して、 `*` 現在のディレクトリ内のすべてのファイルをファイル名拡張子で検索し `.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-134">`Select-String` uses the **Path** parameter with the asterisk (`*`) wildcard to search all files in the current directory with the file name extension `.txt`.</span></span> <span data-ttu-id="1de0d-135">**Pattern** パラメーターは、 **Get** と一致するテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-135">The **Pattern** parameter specifies the text to match **Get-**.</span></span> <span data-ttu-id="1de0d-136">`Select-String` PowerShell コンソールに出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-136">`Select-String` displays the output in the PowerShell console.</span></span> <span data-ttu-id="1de0d-137">**Pattern** パラメーターの一致が含まれているコンテンツの各行の前にあるファイル名と行番号。</span><span class="sxs-lookup"><span data-stu-id="1de0d-137">The file name and line number precede each line of content that contains a match for the **Pattern** parameter.</span></span>

### <span data-ttu-id="1de0d-138">例 3: パターン一致を検索する</span><span class="sxs-lookup"><span data-stu-id="1de0d-138">Example 3: Find a pattern match</span></span>

<span data-ttu-id="1de0d-139">この例では、複数のファイルを検索して、指定したパターンに一致するものを検索します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-139">In this example, multiple files are searched to find matches for the specified pattern.</span></span> <span data-ttu-id="1de0d-140">このパターンでは、正規表現の量指定子を使用します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-140">The pattern uses a regular expression quantifier.</span></span> <span data-ttu-id="1de0d-141">詳細については、「 [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/About_Regular_Expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de0d-141">For more information, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/About_Regular_Expressions.md).</span></span>

```powershell
Select-String -Path "$PSHOME\en-US\*.txt" -Pattern '\?'
```

```Output
C:\Program Files\PowerShell\6\en-US\default.help.txt:27:    beginning at https://go.microsoft.com/fwlink/?LinkID=108518.
C:\Program Files\PowerShell\6\en-US\default.help.txt:50:    or go to: https://go.microsoft.com/fwlink/?LinkID=210614
```

<span data-ttu-id="1de0d-142">`Select-String`コマンドレットでは、 **Path** と **Pattern** の2つのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-142">The `Select-String` cmdlet uses two parameters, **Path** and **Pattern**.</span></span> <span data-ttu-id="1de0d-143">**Path** パラメーターでは、PowerShell ディレクトリを指定する変数を使用し `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-143">The **Path** parameter uses the variable `$PSHOME` that specifies the PowerShell directory.</span></span> <span data-ttu-id="1de0d-144">パスの残りの部分には、 **en-us** というサブディレクトリが含まれ、ディレクトリ内の各ファイルを指定し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-144">The remainder of the path includes the subdirectory **en-US** and specifies each `*.txt` file in the directory.</span></span> <span data-ttu-id="1de0d-145">**Pattern** パラメーターは、各ファイルの疑問符 () に一致するように指定し `?` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-145">The **Pattern** parameter specifies to match a question mark (`?`) in each file.</span></span> <span data-ttu-id="1de0d-146">円記号 ( `\` ) はエスケープ文字として使用され `?` ます。疑問符 () は正規表現の量指定子であるため、これが必要です。</span><span class="sxs-lookup"><span data-stu-id="1de0d-146">A backslash (`\`) is used as an escape character and is necessary because the question mark (`?`) is a regular expression quantifier.</span></span> <span data-ttu-id="1de0d-147">`Select-String` PowerShell コンソールに出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-147">`Select-String` displays the output in the PowerShell console.</span></span> <span data-ttu-id="1de0d-148">**Pattern** パラメーターの一致が含まれているコンテンツの各行の前にあるファイル名と行番号。</span><span class="sxs-lookup"><span data-stu-id="1de0d-148">The file name and line number precede each line of content that contains a match for the **Pattern** parameter.</span></span>

### <span data-ttu-id="1de0d-149">例 4: 関数で Select-String を使用する</span><span class="sxs-lookup"><span data-stu-id="1de0d-149">Example 4: Use Select-String in a function</span></span>

<span data-ttu-id="1de0d-150">この例では、PowerShell のヘルプファイルでパターンを検索する関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-150">This example creates a function to search for a pattern in the PowerShell help files.</span></span> <span data-ttu-id="1de0d-151">この例では、関数は PowerShell セッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-151">For this example, the function only exists in the PowerShell session.</span></span> <span data-ttu-id="1de0d-152">PowerShell セッションが閉じられると、関数は削除されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-152">When the PowerShell session is closed, the function is deleted.</span></span> <span data-ttu-id="1de0d-153">詳細については、「 [about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de0d-153">For more information, see [about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md).</span></span>

```
PS> Function Search-Help
>> {
>> $PSHelp = "$PSHOME\en-US\*.txt"
>> Select-String -Path $PSHelp -Pattern 'About_'
>> }
PS>

PS> Search-Help

C:\Program Files\PowerShell\6\en-US\default.help.txt:67:    The titles of conceptual topics begin with "About_".
C:\Program Files\PowerShell\6\en-US\default.help.txt:70:    Get-Help About_<topic-name>
C:\Program Files\PowerShell\6\en-US\default.help.txt:93:    Get-Help About_Modules : Displays help about PowerShell modules.
C:\Program Files\PowerShell\6\en-US\default.help.txt:97:    about_Updatable_Help
```

<span data-ttu-id="1de0d-154">関数は、PowerShell コマンドラインで作成されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-154">The function is created on the PowerShell command line.</span></span> <span data-ttu-id="1de0d-155">このコマンドでは、と `Function` いう名前の **検索ヘルプ** を使用します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-155">The `Function` command uses the name **Search-Help**.</span></span> <span data-ttu-id="1de0d-156">Enter **キーを** 押して、関数へのステートメントの追加を開始します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-156">Press **Enter** to begin adding statements to the function.</span></span> <span data-ttu-id="1de0d-157">プロンプトで `>>` 、次の例に示すように、各ステートメントを追加し、 **enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-157">From the `>>` prompt, add each statement and press **Enter** as shown in the example.</span></span> <span data-ttu-id="1de0d-158">閉じかっこを追加すると、PowerShell プロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="1de0d-158">After the closing bracket is added, you're returned to a PowerShell prompt.</span></span>

<span data-ttu-id="1de0d-159">関数には、2つのコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1de0d-159">The function contains two commands.</span></span> <span data-ttu-id="1de0d-160">変数には、 `$PSHelp` PowerShell ヘルプファイルへのパスが格納されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-160">The `$PSHelp` variable stores the path to the PowerShell help files.</span></span> <span data-ttu-id="1de0d-161">`$PSHOME` は、ディレクトリ内の各ファイルを指定する **en-us** サブディレクトリを持つ PowerShell インストールディレクトリです `*.txt` 。</span><span class="sxs-lookup"><span data-stu-id="1de0d-161">`$PSHOME` is the PowerShell installation directory with the subdirectory **en-US** that specifies each `*.txt` file in the directory.</span></span>

<span data-ttu-id="1de0d-162">`Select-String`関数内のコマンドは、 **Path** パラメーターと **Pattern** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-162">The `Select-String` command in the function uses the **Path** and **Pattern** parameters.</span></span> <span data-ttu-id="1de0d-163">**Path** パラメーターは、変数を使用して `$PSHelp` パスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-163">The **Path** parameter uses the `$PSHelp` variable to get the path.</span></span> <span data-ttu-id="1de0d-164">**Pattern** パラメーターでは、検索条件として文字列 **About_** を使用します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-164">The **Pattern** parameter uses the string **About_** as the search criteria.</span></span>

<span data-ttu-id="1de0d-165">関数を実行するには、「」と入力 `Search-Help` します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-165">To run the function, type `Search-Help`.</span></span> <span data-ttu-id="1de0d-166">関数のコマンドを実行すると、 `Select-String` PowerShell コンソールに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-166">The function's `Select-String` command displays the output in the PowerShell console.</span></span>

### <span data-ttu-id="1de0d-167">例 5: Windows イベントログで文字列を検索する</span><span class="sxs-lookup"><span data-stu-id="1de0d-167">Example 5: Search for a string in a Windows event log</span></span>

<span data-ttu-id="1de0d-168">この例では、Windows イベントログ内の文字列を検索します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-168">This example searches for a string in a Windows event log.</span></span> <span data-ttu-id="1de0d-169">変数は、 `$_` パイプライン内の現在のオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-169">The variable `$_` represents the current object in the pipeline.</span></span> <span data-ttu-id="1de0d-170">詳細については、「 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de0d-170">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
$Events = Get-WinEvent -LogName Application -MaxEvents 50
$Events | Select-String -InputObject {$_.message} -Pattern 'Failed'
```

<span data-ttu-id="1de0d-171">`Get-WinEvent`コマンドレットでは、 **LogName** パラメーターを使用してアプリケーションログを指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-171">The `Get-WinEvent` cmdlet uses the **LogName** parameter to specify the Application log.</span></span> <span data-ttu-id="1de0d-172">**Maxevents** パラメーターは、ログから最新の50のイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-172">The **MaxEvents** parameter gets the 50 most recent events from the log.</span></span> <span data-ttu-id="1de0d-173">ログの内容は、という名前の変数に格納され `$Events` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-173">The log content is stored in the variable named `$Events`.</span></span>

<span data-ttu-id="1de0d-174">変数は、パイプラインを介して `$Events` コマンドレットに送信され `Select-String` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-174">The `$Events` variable is sent down the pipeline to the `Select-String` cmdlet.</span></span> <span data-ttu-id="1de0d-175">`Select-String`**InputObject** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-175">`Select-String` uses the **InputObject** parameter.</span></span> <span data-ttu-id="1de0d-176">変数は、 `$_` 現在のオブジェクトを表し、 `message` イベントのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="1de0d-176">The `$_` variable represents the current object and `message` is a property of the event.</span></span> <span data-ttu-id="1de0d-177">**Pattern** パラメーターは、文字列が **失敗した** ことを検出し、で一致を検索し `$_.message` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-177">The **Pattern** parameter species the string **Failed** and searches for matches in `$_.message`.</span></span> <span data-ttu-id="1de0d-178">`Select-String` PowerShell コンソールに出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-178">`Select-String` displays the output in the PowerShell console.</span></span>

### <span data-ttu-id="1de0d-179">例 6: サブディレクトリ内の文字列を検索する</span><span class="sxs-lookup"><span data-stu-id="1de0d-179">Example 6: Find a string in subdirectories</span></span>

<span data-ttu-id="1de0d-180">この例では、特定のテキスト文字列のディレクトリとそのすべてのサブディレクトリを検索します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-180">This example searches a directory and all of its subdirectories for a specific text string.</span></span>

```powershell
Get-ChildItem -Path C:\Windows\System32\*.txt -Recurse | Select-String -Pattern 'Microsoft' -CaseSensitive
```

<span data-ttu-id="1de0d-181">`Get-ChildItem`**Path** パラメーターを使用して **C:\Windows\System32 \*** を指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-181">`Get-ChildItem` uses the **Path** parameter to specify **C:\Windows\System32\*.txt**.</span></span> <span data-ttu-id="1de0d-182">**再帰** パラメーターには、サブディレクトリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-182">The **Recurse** parameter includes the subdirectories.</span></span> <span data-ttu-id="1de0d-183">オブジェクトは、パイプラインの下位に送信され `Select-String` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-183">The objects are sent down the pipeline to `Select-String`.</span></span>

<span data-ttu-id="1de0d-184">`Select-String`**Pattern** パラメーターを使用し、 **Microsoft** という文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-184">`Select-String` uses the **Pattern** parameter and specifies the string **Microsoft**.</span></span> <span data-ttu-id="1de0d-185">**CaseSensitive** パラメーターは、文字列の大文字と小文字を区別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-185">The **CaseSensitive** parameter is used to match the exact case of the string.</span></span> <span data-ttu-id="1de0d-186">`Select-String` PowerShell コンソールに出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-186">`Select-String` displays the output in the PowerShell console.</span></span>

> [!NOTE]
> <span data-ttu-id="1de0d-187">アクセス許可に応じて、出力に **アクセス拒否** メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1de0d-187">Dependent upon your permissions, you might see **Access denied** messages in the output.</span></span>

### <span data-ttu-id="1de0d-188">例 7: パターンに一致しない文字列を検索する</span><span class="sxs-lookup"><span data-stu-id="1de0d-188">Example 7: Find strings that do not match a pattern</span></span>

<span data-ttu-id="1de0d-189">この例では、パターンに一致しないデータ行を除外する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-189">This example shows how to exclude lines of data that don't match a pattern.</span></span>

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get', 'Set'  -NotMatch
```

<span data-ttu-id="1de0d-190">`Get-Command`コマンドレットは、オブジェクトをパイプライン内でに送信して、 `Out-File` 現在のディレクトリに **Command.txt** ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-190">The `Get-Command` cmdlet sends objects down the pipeline to the `Out-File` to create the **Command.txt** file in the current directory.</span></span> <span data-ttu-id="1de0d-191">`Select-String`**Path** パラメーターを使用して、 **Command.txt** ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-191">`Select-String` uses the **Path** parameter to specify the **Command.txt** file.</span></span> <span data-ttu-id="1de0d-192">**Pattern** パラメーターは、検索パターンとして **Get** と **Set** を指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-192">The **Pattern** parameter specifies **Get** and **Set** as the search pattern.</span></span> <span data-ttu-id="1de0d-193">**Notmatch** パラメーターでは、 **Get** と **Set** が結果から除外されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-193">The **NotMatch** parameter excludes **Get** and **Set** from the results.</span></span>
<span data-ttu-id="1de0d-194">`Select-String`**Get** または **Set** を含まない PowerShell コンソールに出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-194">`Select-String` displays the output in the PowerShell console that doesn't include **Get** or **Set**.</span></span>

### <span data-ttu-id="1de0d-195">例 8: 一致の前後の行を検索する</span><span class="sxs-lookup"><span data-stu-id="1de0d-195">Example 8: Find lines before and after a match</span></span>

<span data-ttu-id="1de0d-196">この例では、一致したパターンの前後の行を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-196">This example shows how to get the lines before and after the matched pattern.</span></span>

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get-Computer' -Context 2, 3
```

```Output
  Command.txt:986:Cmdlet          Get-CmsMessage           6.1.0.0    Microsoft.PowerShell.Security
  Command.txt:987:Cmdlet          Get-Command              6.1.2.0    Microsoft.PowerShell.Core
> Command.txt:988:Cmdlet          Get-ComputerInfo         6.1.0.0    Microsoft.PowerShell.Management
  Command.txt:990:Cmdlet          Get-Content              6.1.0.0    Microsoft.PowerShell.Management
  Command.txt:991:Cmdlet          Get-ControlPanelItem     3.1.0.0    Microsoft.PowerShell.Management
  Command.txt:992:Cmdlet          Get-Credential           6.1.0.0    Microsoft.PowerShell.Security
```

<span data-ttu-id="1de0d-197">`Get-Command`コマンドレットは、オブジェクトをパイプライン内でに送信して、 `Out-File` 現在のディレクトリに **Command.txt** ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-197">The `Get-Command` cmdlet sends objects down the pipeline to the `Out-File` to create the **Command.txt** file in the current directory.</span></span> <span data-ttu-id="1de0d-198">`Select-String`**Path** パラメーターを使用して、 **Command.txt** ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-198">`Select-String` uses the **Path** parameter to specify the **Command.txt** file.</span></span> <span data-ttu-id="1de0d-199">**Pattern** パラメーターは、検索パターンとして **取得コンピューター** を指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-199">The **Pattern** parameter specifies **Get-Computer** as the search pattern.</span></span> <span data-ttu-id="1de0d-200">**Context** パラメーターでは、before と after の2つの値を使用して、出力のパターン一致を山かっこ () でマークし `>` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-200">The **Context** parameter uses two values, before and after, and marks pattern matches in the output with an angle bracket (`>`).</span></span> <span data-ttu-id="1de0d-201">**Context** パラメーターを指定すると、最初のパターンに一致する2行と最後のパターンが一致した後の3行が出力されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-201">The **Context** parameter outputs the two lines before the first pattern match and three lines after the last pattern match.</span></span>

### <span data-ttu-id="1de0d-202">例 9: すべてのパターン一致を検索する</span><span class="sxs-lookup"><span data-stu-id="1de0d-202">Example 9: Find all pattern matches</span></span>

<span data-ttu-id="1de0d-203">この例では、 **Allmatches** パラメーターがテキスト行の各パターン一致を検索する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1de0d-203">This example shows how the **AllMatches** parameter finds each pattern match in a line of text.</span></span> <span data-ttu-id="1de0d-204">既定では、では、 `Select-String` 最初に出現したパターンがテキスト行で検索されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-204">By default, `Select-String` only finds the first occurrence of a pattern in a line of text.</span></span> <span data-ttu-id="1de0d-205">この例では、コマンドレットを使用して検出されたオブジェクトプロパティを使用 `Get-Member` します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-205">This example uses object properties that are found with the `Get-Member` cmdlet.</span></span>

```
PS> $A = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell'

PS> $A

C:\Program Files\PowerShell\6\en-US\default.help.txt:3:    PowerShell Help System
C:\Program Files\PowerShell\6\en-US\default.help.txt:6:    Displays help about PowerShell cmdlets and concepts.
C:\Program Files\PowerShell\6\en-US\default.help.txt:9:    PowerShell Help describes PowerShell cmdlets

PS> $A.Matches

Groups   : {0}
Success  : True
Name     : 0
Captures : {0}
Index    : 4
Length   : 10
Value    : PowerShell

PS> $A.Matches.Length

8

PS> $B = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell' -AllMatches

PS> $B.Matches.Length

9
```

<span data-ttu-id="1de0d-206">`Get-ChildItem`コマンドレットでは、 **Path** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-206">The `Get-ChildItem` cmdlet uses the **Path** parameter.</span></span> <span data-ttu-id="1de0d-207">**Path** パラメーターでは、PowerShell ディレクトリを指定する変数を使用し `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-207">The **Path** parameter uses the variable `$PSHOME` that specifies the PowerShell directory.</span></span> <span data-ttu-id="1de0d-208">パスの残りの部分には、 **en-us** というサブディレクトリが含まれ、ディレクトリ内の各ファイルを指定し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-208">The remainder of the path includes the subdirectory **en-US** and specifies each `*.txt` file in the directory.</span></span> <span data-ttu-id="1de0d-209">`Get-ChildItem`オブジェクトは変数に格納され `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-209">The `Get-ChildItem` objects are stored in the `$A` variable.</span></span> <span data-ttu-id="1de0d-210">変数は、パイプラインを介して `$A` コマンドレットに送信され `Select-String` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-210">The `$A` variable is sent down the pipeline to the `Select-String` cmdlet.</span></span> <span data-ttu-id="1de0d-211">`Select-String`**Pattern** パラメーターを使用して、各ファイルで文字列 **PowerShell** を検索します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-211">`Select-String` uses the **Pattern** parameter to search each file for the string **PowerShell**.</span></span>

<span data-ttu-id="1de0d-212">PowerShell コマンドラインから、変数の `$A` 内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-212">From the PowerShell command line, the `$A` variable contents are displayed.</span></span> <span data-ttu-id="1de0d-213">文字列 **PowerShell** の2回の出現を含む行があります。</span><span class="sxs-lookup"><span data-stu-id="1de0d-213">There's a line that contains two occurrences of the string **PowerShell**.</span></span>

<span data-ttu-id="1de0d-214">プロパティは、 `$A.Matches` 各行で最初に見つかったパターンの **PowerShell** を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-214">The `$A.Matches` property lists the first occurrence of the pattern **PowerShell** on each line.</span></span>

<span data-ttu-id="1de0d-215">プロパティは、 `$A.Matches.Length` 各行で最初に見つかったパターンの **PowerShell** をカウントします。</span><span class="sxs-lookup"><span data-stu-id="1de0d-215">The `$A.Matches.Length` property counts the first occurrence of the pattern **PowerShell** on each line.</span></span>

<span data-ttu-id="1de0d-216">変数は、 `$B` 同じ `Get-ChildItem` `Select-String` コマンドレットとコマンドレットを使用しますが、 **allmatches** パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-216">The `$B` variable uses the same `Get-ChildItem` and `Select-String` cmdlets, but adds the **AllMatches** parameter.</span></span> <span data-ttu-id="1de0d-217">**Allmatches** は、各行に各パターンの **PowerShell** の出現箇所を検索します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-217">**AllMatches** finds each occurrence of the pattern **PowerShell** on each line.</span></span> <span data-ttu-id="1de0d-218">変数と変数に格納されて `$A` `$B` いるオブジェクトは同一です。</span><span class="sxs-lookup"><span data-stu-id="1de0d-218">The objects stored in the `$A` and `$B` variables are identical.</span></span>

<span data-ttu-id="1de0d-219">このプロパティは、各行 `$B.Matches.Length` について、すべてのパターンが **PowerShell** カウントされるため、増加します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-219">The `$B.Matches.Length` property increases because for each line, every occurrence of the pattern **PowerShell** is counted.</span></span>

## <span data-ttu-id="1de0d-220">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1de0d-220">PARAMETERS</span></span>

### <span data-ttu-id="1de0d-221">-AllMatches</span><span class="sxs-lookup"><span data-stu-id="1de0d-221">-AllMatches</span></span>

<span data-ttu-id="1de0d-222">コマンドレットによって、テキストの各行で複数の一致が検索されることを示します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-222">Indicates that the cmdlet searches for more than one match in each line of text.</span></span> <span data-ttu-id="1de0d-223">このパラメーターを指定しない場合、では、 `Select-String` テキストの各行で最初の一致のみが検索されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-223">Without this parameter, `Select-String` finds only the first match in each line of text.</span></span>

<span data-ttu-id="1de0d-224">`Select-String`は、1行のテキストで複数の一致を検出すると、その行に対して1つの **matchinfo** オブジェクトのみを出力しますが、オブジェクトの **matches** プロパティにはすべての一致が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-224">When `Select-String` finds more than one match in a line of text, it still emits only one **MatchInfo** object for the line, but the **Matches** property of the object contains all the matches.</span></span>

> [!NOTE]
> <span data-ttu-id="1de0d-225">**SimpleMatch** パラメーターと組み合わせて使用する場合、このパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-225">This parameter is ignored when used in combination with the **SimpleMatch** parameter.</span></span> <span data-ttu-id="1de0d-226">すべての一致を返し、検索するパターンに正規表現文字が含まれている場合は、 **SimpleMatch** を使用するのではなく、これらの文字をエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1de0d-226">If you wish to return all matches and the pattern that you are searching for contains regular expression characters, you must escape those characters rather than using **SimpleMatch**.</span></span> <span data-ttu-id="1de0d-227">正規表現のエスケープの詳細については、「 [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de0d-227">See [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md) for more information about escaping regular expressions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1de0d-228">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="1de0d-228">-CaseSensitive</span></span>

<span data-ttu-id="1de0d-229">コマンドレットの照合で大文字と小文字が区別されることを示します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-229">Indicates that the cmdlet matches are case-sensitive.</span></span> <span data-ttu-id="1de0d-230">既定では、の一致では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="1de0d-230">By default, matches aren't case-sensitive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1de0d-231">-Context</span><span class="sxs-lookup"><span data-stu-id="1de0d-231">-Context</span></span>

<span data-ttu-id="1de0d-232">パターンに一致する行の前後の指定された行数をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="1de0d-232">Captures the specified number of lines before and after the line that matches the pattern.</span></span>

<span data-ttu-id="1de0d-233">このパラメーターの値として 1 つの数値を入力すると、その数値が一致の前後でキャプチャされる行数となります。</span><span class="sxs-lookup"><span data-stu-id="1de0d-233">If you enter one number as the value of this parameter, that number determines the number of lines captured before and after the match.</span></span> <span data-ttu-id="1de0d-234">値として 2 つの数値を入力すると、最初の数値が一致の前の行数となり、2 番目の数値が一致の後の行数となります。</span><span class="sxs-lookup"><span data-stu-id="1de0d-234">If you enter two numbers as the value, the first number determines the number of lines before the match and the second number determines the number of lines after the match.</span></span> <span data-ttu-id="1de0d-235">たとえば、「 `-Context 2,3` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-235">For example, `-Context 2,3`.</span></span>

<span data-ttu-id="1de0d-236">既定の表示では、一致する行は、 `>` 表示の最初の列に右山かっこ () (ASCII 62) で示されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-236">In the default display, lines with a match are indicated by a right angle bracket (`>`) (ASCII 62) in the first column of the display.</span></span> <span data-ttu-id="1de0d-237">マークされていない行は、コンテキストです。</span><span class="sxs-lookup"><span data-stu-id="1de0d-237">Unmarked lines are the context.</span></span>

<span data-ttu-id="1de0d-238">**Context** パラメーターは、によって生成されるオブジェクトの数を変更しません `Select-String` 。</span><span class="sxs-lookup"><span data-stu-id="1de0d-238">The **Context** parameter doesn't change the number of objects generated by `Select-String`.</span></span>
<span data-ttu-id="1de0d-239">`Select-String` 一致するごとに1つの [Matchinfo](/dotnet/api/microsoft.powershell.commands.matchinfo) オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-239">`Select-String` generates one [MatchInfo](/dotnet/api/microsoft.powershell.commands.matchinfo) object for each match.</span></span> <span data-ttu-id="1de0d-240">コンテキストは、オブジェクトの **コンテキスト** プロパティに文字列の配列として格納されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-240">The context is stored as an array of strings in the **Context** property of the object.</span></span>

<span data-ttu-id="1de0d-241">コマンドの出力 `Select-String` がパイプライン内で別のコマンドに送信されると、 `Select-String` 受信コマンドは一致した行のテキストだけを検索します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-241">When the output of a `Select-String` command is sent down the pipeline to another `Select-String` command, the receiving command searches only the text in the matched line.</span></span> <span data-ttu-id="1de0d-242">一致した行は、コンテキスト行のテキストではなく、 **Matchinfo** オブジェクトの **line** プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="1de0d-242">The matched line is the value of the **Line** property of the **MatchInfo** object, not the text in the context lines.</span></span> <span data-ttu-id="1de0d-243">その結果、 **コンテキスト** パラメーターは、受信コマンドでは無効になり `Select-String` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-243">As a result, the **Context** parameter isn't valid on the receiving `Select-String` command.</span></span>

<span data-ttu-id="1de0d-244">コンテキストに一致が含まれている場合、各一致の **Matchinfo** オブジェクトにはすべてのコンテキスト行が含まれますが、重複する行は表示に1回だけ表示されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-244">When the context includes a match, the **MatchInfo** object for each match includes all the context lines, but the overlapping lines appear only once in the display.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1de0d-245">-Encoding</span><span class="sxs-lookup"><span data-stu-id="1de0d-245">-Encoding</span></span>

<span data-ttu-id="1de0d-246">ターゲット ファイルのエンコードの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-246">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="1de0d-247">既定値は `utf8NoBOM` です。</span><span class="sxs-lookup"><span data-stu-id="1de0d-247">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="1de0d-248">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1de0d-248">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="1de0d-249">`ascii`: ASCII (7 ビット) 文字セットのエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-249">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="1de0d-250">`bigendianunicode`: ビッグエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="1de0d-250">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="1de0d-251">`oem`: MS-DOS およびコンソールプログラムの既定のエンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-251">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="1de0d-252">`unicode`: リトルエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="1de0d-252">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="1de0d-253">`utf7`: UTF-7 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="1de0d-253">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="1de0d-254">`utf8`: UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="1de0d-254">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="1de0d-255">`utf8BOM`: バイト順マーク (BOM) を使用して UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="1de0d-255">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="1de0d-256">`utf8NoBOM`: バイトオーダーマーク (BOM) を使用せずに UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="1de0d-256">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="1de0d-257">`utf32`:32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="1de0d-257">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="1de0d-258">PowerShell 6.2 以降では、 **Encoding** パラメーターを使用して、登録されているコードページの数値 id (など) `-Encoding 1251` や、登録されているコードページの文字列名 (など) を使用することもでき `-Encoding "windows-1251"` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-258">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="1de0d-259">詳細については、 [コードページ](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)の .net ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de0d-259">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1de0d-260">-除外</span><span class="sxs-lookup"><span data-stu-id="1de0d-260">-Exclude</span></span>

<span data-ttu-id="1de0d-261">指定された項目を除外します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-261">Exclude the specified items.</span></span> <span data-ttu-id="1de0d-262">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-262">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="1de0d-263">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-263">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="1de0d-264">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-264">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="1de0d-265">-Include</span><span class="sxs-lookup"><span data-stu-id="1de0d-265">-Include</span></span>

<span data-ttu-id="1de0d-266">指定した項目を処理対象に含めます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-266">Includes the specified items.</span></span> <span data-ttu-id="1de0d-267">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-267">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="1de0d-268">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-268">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="1de0d-269">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-269">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="1de0d-270">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1de0d-270">-InputObject</span></span>

<span data-ttu-id="1de0d-271">検索するテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-271">Specifies the text to be searched.</span></span> <span data-ttu-id="1de0d-272">テキストが格納されている変数を入力するか、テキストを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-272">Enter a variable that contains the text, or type a command or expression that gets the text.</span></span>

<span data-ttu-id="1de0d-273">**InputObject** パラメーターの使用は、パイプラインの下にある文字列をに送信する場合と同じではありません `Select-String` 。</span><span class="sxs-lookup"><span data-stu-id="1de0d-273">Using the **InputObject** parameter isn't the same as sending strings down the pipeline to `Select-String`.</span></span>

<span data-ttu-id="1de0d-274">パイプを使用して複数の文字列をコマンドレットに渡した場合 `Select-String` 、各文字列で指定したテキストが検索され、検索テキストを含む各文字列が返されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-274">When you pipe more than one string to the `Select-String` cmdlet, it searches for the specified text in each string and returns each string that contains the search text.</span></span>

<span data-ttu-id="1de0d-275">**InputObject** パラメーターを使用して文字列のコレクションを送信すると、では `Select-String` コレクションが1つの結合された文字列として扱われます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-275">When you use the **InputObject** parameter to submit a collection of strings, `Select-String` treats the collection as a single combined string.</span></span> <span data-ttu-id="1de0d-276">`Select-String` 文字列内の検索テキストが見つかった場合は、文字列を単位として返します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-276">`Select-String` returns the strings as a unit if it finds the search text in any string.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ObjectRaw, Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1de0d-277">-List</span><span class="sxs-lookup"><span data-stu-id="1de0d-277">-List</span></span>

<span data-ttu-id="1de0d-278">一致するテキストの最初のインスタンスのみが各入力ファイルから返されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-278">Only the first instance of matching text is returned from each input file.</span></span> <span data-ttu-id="1de0d-279">これは、正規表現に一致する内容を含むファイルの一覧を取得するための最も効率的な方法です。</span><span class="sxs-lookup"><span data-stu-id="1de0d-279">This is the most efficient way to retrieve a list of files that have contents matching the regular expression.</span></span>

<span data-ttu-id="1de0d-280">既定では、は、 `Select-String` 見つかった一致ごとに **matchinfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-280">By default, `Select-String` returns a **MatchInfo** object for each match it finds.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1de0d-281">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1de0d-281">-LiteralPath</span></span>

<span data-ttu-id="1de0d-282">検索するファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-282">Specifies the path to the files to be searched.</span></span> <span data-ttu-id="1de0d-283">**LiteralPath** パラメーターの値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-283">The value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="1de0d-284">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="1de0d-284">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="1de0d-285">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-285">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="1de0d-286">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="1de0d-286">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span> <span data-ttu-id="1de0d-287">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de0d-287">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralFile
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1de0d-288">-NotMatch</span><span class="sxs-lookup"><span data-stu-id="1de0d-288">-NotMatch</span></span>

<span data-ttu-id="1de0d-289">**Notmatch** パラメーターは、指定されたパターンに一致しないテキストを検索します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-289">The **NotMatch** parameter finds text that doesn't match the specified pattern.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1de0d-290">-Path</span><span class="sxs-lookup"><span data-stu-id="1de0d-290">-Path</span></span>

<span data-ttu-id="1de0d-291">検索するファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-291">Specifies the path to the files to search.</span></span> <span data-ttu-id="1de0d-292">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-292">Wildcards are permitted.</span></span> <span data-ttu-id="1de0d-293">既定の場所は、ローカル ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="1de0d-293">The default location is the local directory.</span></span>

<span data-ttu-id="1de0d-294">ディレクトリ内のファイル (、、など) を指定し `log1.txt` `*.doc` `*.*` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-294">Specify files in the directory, such as `log1.txt`, `*.doc`, or `*.*`.</span></span> <span data-ttu-id="1de0d-295">ディレクトリのみを指定すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-295">If you specify only a directory, the command fails.</span></span>

```yaml
Type: System.String[]
Parameter Sets: File
Aliases:

Required: True
Position: 1
Default value: Local directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="1de0d-296">-Pattern</span><span class="sxs-lookup"><span data-stu-id="1de0d-296">-Pattern</span></span>

<span data-ttu-id="1de0d-297">各行で検索するテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-297">Specifies the text to find on each line.</span></span> <span data-ttu-id="1de0d-298">Pattern 値は正規表現として扱われます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-298">The pattern value is treated as a regular expression.</span></span>

<span data-ttu-id="1de0d-299">正規表現の詳細については、「 [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de0d-299">To learn about regular expressions, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1de0d-300">-非表示</span><span class="sxs-lookup"><span data-stu-id="1de0d-300">-Quiet</span></span>

<span data-ttu-id="1de0d-301">コマンドレットが **Matchinfo** オブジェクトの代わりにブール値 (True または False) を返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-301">Indicates that the cmdlet returns a Boolean value (True or False), instead of a **MatchInfo** object.</span></span> <span data-ttu-id="1de0d-302">パターンが見つかった場合、値は True になります。それ以外の場合、値は False になります。</span><span class="sxs-lookup"><span data-stu-id="1de0d-302">The value is True if the pattern is found; otherwise the value is False.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1de0d-303">-SimpleMatch</span><span class="sxs-lookup"><span data-stu-id="1de0d-303">-SimpleMatch</span></span>

<span data-ttu-id="1de0d-304">コマンドレットが正規表現と一致するのではなく、単純一致を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-304">Indicates that the cmdlet uses a simple match rather than a regular expression match.</span></span> <span data-ttu-id="1de0d-305">単純一致では、 `Select-String` 入力で **Pattern** パラメーターのテキストを検索します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-305">In a simple match, `Select-String` searches the input for the text in the **Pattern** parameter.</span></span> <span data-ttu-id="1de0d-306">**Pattern** パラメーターの値は、正規表現ステートメントとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="1de0d-306">It doesn't interpret the value of the **Pattern** parameter as a regular expression statement.</span></span>

<span data-ttu-id="1de0d-307">また、 **SimpleMatch** を使用すると、返される **Matchinfo** オブジェクトの **Matches** プロパティは空になります。</span><span class="sxs-lookup"><span data-stu-id="1de0d-307">Also, when **SimpleMatch** is used, the **Matches** property of the **MatchInfo** object returned is empty.</span></span>

> [!NOTE]
> <span data-ttu-id="1de0d-308">このパラメーターを **Allmatches** パラメーターと共に使用すると、 **allmatches** は無視されます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-308">When this parameter is used with the **AllMatches** parameter, the **AllMatches** is ignored.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1de0d-309">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1de0d-309">CommonParameters</span></span>

<span data-ttu-id="1de0d-310">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="1de0d-310">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1de0d-311">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de0d-311">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1de0d-312">入力</span><span class="sxs-lookup"><span data-stu-id="1de0d-312">INPUTS</span></span>

### <span data-ttu-id="1de0d-313">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="1de0d-313">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="1de0d-314">パイプを使用して、 **ToString** メソッドを持つ任意のオブジェクトをにパイプすることができ `Select-String` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-314">You can pipe any object that has a **ToString** method to `Select-String`.</span></span>

## <span data-ttu-id="1de0d-315">出力</span><span class="sxs-lookup"><span data-stu-id="1de0d-315">OUTPUTS</span></span>

### <span data-ttu-id="1de0d-316">Microsoft. PowerShell. MatchInfo または system.string</span><span class="sxs-lookup"><span data-stu-id="1de0d-316">Microsoft.PowerShell.Commands.MatchInfo or System.Boolean</span></span>

<span data-ttu-id="1de0d-317">既定では、出力は、見つかった一致ごとに1つずつの **Matchinfo** オブジェクトのセットです。</span><span class="sxs-lookup"><span data-stu-id="1de0d-317">By default, the output is a set of **MatchInfo** objects with one for each match found.</span></span> <span data-ttu-id="1de0d-318">**Quiet** パラメーターを使用する場合、出力は、パターンが見つかったかどうかを示すブール値です。</span><span class="sxs-lookup"><span data-stu-id="1de0d-318">If you use the **Quiet** parameter, the output is a Boolean value indicating whether the pattern was found.</span></span>

## <span data-ttu-id="1de0d-319">注</span><span class="sxs-lookup"><span data-stu-id="1de0d-319">NOTES</span></span>

<span data-ttu-id="1de0d-320">`Select-String` は、UNIX では **grep** 、Windows では **findstr.exe** に似ています。</span><span class="sxs-lookup"><span data-stu-id="1de0d-320">`Select-String` is similar to **grep** in UNIX or **findstr.exe** in Windows.</span></span>

<span data-ttu-id="1de0d-321">コマンドレットの **sls** エイリアスは、 `Select-String` PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1de0d-321">The **sls** alias for the `Select-String` cmdlet was introduced in PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="1de0d-322">[PowerShell コマンドの承認](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands)された動詞によれば、コマンドレットの公式のエイリアスプレフィックス `Select-*` は `sc` ではなくです `sl` 。</span><span class="sxs-lookup"><span data-stu-id="1de0d-322">According to [Approved Verbs for PowerShell Commands](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands), the official alias prefix for `Select-*` cmdlets is `sc`, not `sl`.</span></span> <span data-ttu-id="1de0d-323">したがって、の適切なエイリアスはで `Select-String` はなくである必要があり `scs` `sls` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-323">Therefore, the proper alias for `Select-String` should be `scs`, not `sls`.</span></span> <span data-ttu-id="1de0d-324">これは、このルールの例外です。</span><span class="sxs-lookup"><span data-stu-id="1de0d-324">This is an exception to this rule.</span></span>

<span data-ttu-id="1de0d-325">を使用するには `Select-String` 、 **パターン** パラメーターの値として検索するテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-325">To use `Select-String`, type the text that you want to find as the value of the **Pattern** parameter.</span></span> <span data-ttu-id="1de0d-326">検索するテキストを指定するには、次の条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-326">To specify the text to be searched, use the following criteria:</span></span>

- <span data-ttu-id="1de0d-327">引用符で囲まれた文字列にテキストを入力し、それをにパイプし `Select-String` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-327">Type the text in a quoted string, and then pipe it to `Select-String`.</span></span>
- <span data-ttu-id="1de0d-328">変数にテキスト文字列を格納し、 **InputObject** パラメーターの値として変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-328">Store a text string in a variable, and then specify the variable as the value of the **InputObject** parameter.</span></span>
- <span data-ttu-id="1de0d-329">テキストがファイルに格納されている場合は、 **path** パラメーターを使用して、ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-329">If the text is stored in files, use the **Path** parameter to specify the path to the files.</span></span>

<span data-ttu-id="1de0d-330">既定では、は、 `Select-String` **Pattern** パラメーターの値を正規表現として解釈します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-330">By default, `Select-String` interprets the value of the **Pattern** parameter as a regular expression.</span></span> <span data-ttu-id="1de0d-331">詳細については、「 [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de0d-331">For more information, see [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).</span></span> <span data-ttu-id="1de0d-332">**SimpleMatch** パラメーターを使用して、正規表現の一致をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-332">You can use the **SimpleMatch** parameter to override the regular expression matching.</span></span> <span data-ttu-id="1de0d-333">**SimpleMatch** パラメーターは、入力内の **Pattern** パラメーターの値のインスタンスを検索します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-333">The **SimpleMatch** parameter finds instances of the value of the **Pattern** parameter in the input.</span></span>

<span data-ttu-id="1de0d-334">の既定の出力 `Select-String` は **matchinfo** オブジェクトで、一致に関する詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1de0d-334">The default output of `Select-String` is a **MatchInfo** object, which includes detailed information about the matches.</span></span> <span data-ttu-id="1de0d-335">**Matchinfo** オブジェクトには **Filename** や **Line** などのプロパティがあるため、オブジェクトの情報は、ファイル内のテキストを検索するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-335">The information in the object is useful when you're searching for text in files, because **MatchInfo** objects have properties such as **Filename** and **Line**.</span></span> <span data-ttu-id="1de0d-336">入力がファイルからのものではない場合、これらのパラメーターの値は **InputStream** になります。</span><span class="sxs-lookup"><span data-stu-id="1de0d-336">When the input isn't from the file, the value of these parameters is **InputStream**.</span></span>

<span data-ttu-id="1de0d-337">**Matchinfo** オブジェクト内の情報が不要な場合は、 **Quiet** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-337">If you don't need the information in the **MatchInfo** object, use the **Quiet** parameter.</span></span> <span data-ttu-id="1de0d-338">**Quiet** パラメーターは、 **matchinfo** オブジェクトではなく、一致が見つかったかどうかを示すブール値 (True または False) を返します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-338">The **Quiet** parameter returns a Boolean value (True or False) to indicate whether it found a match, instead of a **MatchInfo** object.</span></span>

<span data-ttu-id="1de0d-339">一致する語句の場合は、 `Select-String` システムに設定されている現在のカルチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-339">When matching phrases, `Select-String` uses the current culture that is set for the system.</span></span> <span data-ttu-id="1de0d-340">現在のカルチャを検索するには、コマンドレットを使用し `Get-Culture` ます。</span><span class="sxs-lookup"><span data-stu-id="1de0d-340">To find the current culture, use the `Get-Culture` cmdlet.</span></span>

<span data-ttu-id="1de0d-341">**Matchinfo** オブジェクトのプロパティを検索するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="1de0d-341">To find the properties of a **MatchInfo** object, type the following command:</span></span>

`Select-String -Path test.txt -Pattern 'test' | Get-Member | Format-List -Property *`

## <span data-ttu-id="1de0d-342">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1de0d-342">RELATED LINKS</span></span>

[<span data-ttu-id="1de0d-343">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="1de0d-343">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="1de0d-344">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="1de0d-344">about_Comparison_Operators</span></span>](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md)

[<span data-ttu-id="1de0d-345">about_Functions</span><span class="sxs-lookup"><span data-stu-id="1de0d-345">about_Functions</span></span>](../Microsoft.PowerShell.Core/About/about_Functions.md)

[<span data-ttu-id="1de0d-346">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="1de0d-346">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="1de0d-347">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="1de0d-347">about_Regular_Expressions</span></span>](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md)

[<span data-ttu-id="1de0d-348">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="1de0d-348">Get-Alias</span></span>](Get-Alias.md)

[<span data-ttu-id="1de0d-349">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="1de0d-349">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="1de0d-350">Get-Command</span><span class="sxs-lookup"><span data-stu-id="1de0d-350">Get-Command</span></span>](../Microsoft.PowerShell.Core/Get-Command.md)

[<span data-ttu-id="1de0d-351">Get-Member</span><span class="sxs-lookup"><span data-stu-id="1de0d-351">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="1de0d-352">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="1de0d-352">Get-WinEvent</span></span>](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[<span data-ttu-id="1de0d-353">Out-File</span><span class="sxs-lookup"><span data-stu-id="1de0d-353">Out-File</span></span>](Out-File.md)