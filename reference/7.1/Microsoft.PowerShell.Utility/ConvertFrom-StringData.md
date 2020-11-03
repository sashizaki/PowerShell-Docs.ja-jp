---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/21/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-stringdata?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-StringData
ms.openlocfilehash: 256807079f8ef47baf20cd70df326298e4ce9ed0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215907"
---
# <span data-ttu-id="70637-103">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="70637-103">ConvertFrom-StringData</span></span>

## <span data-ttu-id="70637-104">概要</span><span class="sxs-lookup"><span data-stu-id="70637-104">SYNOPSIS</span></span>
<span data-ttu-id="70637-105">1 つまたは複数のキーと値のペアを含む文字列をハッシュ テーブルに変換します。</span><span class="sxs-lookup"><span data-stu-id="70637-105">Converts a string containing one or more key and value pairs to a hash table.</span></span>

## <span data-ttu-id="70637-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="70637-106">SYNTAX</span></span>

### <span data-ttu-id="70637-107">All</span><span class="sxs-lookup"><span data-stu-id="70637-107">All</span></span>

```
ConvertFrom-StringData [-StringData] <String> [[-Delimiter] <Char>] [<CommonParameters>]
```

## <span data-ttu-id="70637-108">Description</span><span class="sxs-lookup"><span data-stu-id="70637-108">DESCRIPTION</span></span>

<span data-ttu-id="70637-109">`ConvertFrom-StringData`コマンドレットは、1つ以上のキーと値のペアを含む文字列をハッシュテーブルに変換します。</span><span class="sxs-lookup"><span data-stu-id="70637-109">The `ConvertFrom-StringData` cmdlet converts a string that contains one or more key and value pairs into a hash table.</span></span> <span data-ttu-id="70637-110">各キーと値のペアは別々の行に配置する必要があるため、ここでは多くの場合、入力形式として文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="70637-110">Because each key-value pair must be on a separate line, here-strings are often used as the input format.</span></span> <span data-ttu-id="70637-111">既定では、 **キー** は等号 () 文字で **値** から区切る必要があり `=` ます。</span><span class="sxs-lookup"><span data-stu-id="70637-111">By default, the **key** must be separated from the **value** by an equals sign (`=`) character.</span></span>

<span data-ttu-id="70637-112">`ConvertFrom-StringData`コマンドレットは、 `DATA` スクリプトまたは関数のセクションで使用できる安全なコマンドレットと見なされます。</span><span class="sxs-lookup"><span data-stu-id="70637-112">The `ConvertFrom-StringData` cmdlet is considered to be a safe cmdlet that can be used in the `DATA` section of a script or function.</span></span> <span data-ttu-id="70637-113">セクションで使用する場合、 `DATA` 文字列の内容は、データセクションの規則に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="70637-113">When used in a `DATA` section, the contents of the string must conform to the rules for a DATA section.</span></span> <span data-ttu-id="70637-114">詳細については、「 [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70637-114">For more information, see [about_Data_Sections](../Microsoft.PowerShell.Core/About/about_Data_Sections.md).</span></span>

<span data-ttu-id="70637-115">`ConvertFrom-StringData` では、従来の機械翻訳ツールで許可されているエスケープ文字シーケンスがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="70637-115">`ConvertFrom-StringData` supports escape character sequences that are allowed by conventional machine translation tools.</span></span> <span data-ttu-id="70637-116">つまり、コマンドレットでは、Unescape メソッドを使用して、文字列データ内のバックスラッシュ () をエスケープ文字として解釈できます。これは `\` 通常、 [Regex.Unescape Method](/dotnet/api/system.text.regularexpressions.regex.unescape) \` スクリプト内の行の末尾を示す PowerShell バックティック character () ではありません。</span><span class="sxs-lookup"><span data-stu-id="70637-116">That is, the cmdlet can interpret backslashes (`\`) as escape characters in the string data by using the [Regex.Unescape Method](/dotnet/api/system.text.regularexpressions.regex.unescape), instead of the PowerShell backtick character (\`) that would normally signal the end of a line in a script.</span></span> <span data-ttu-id="70637-117">ヒア文字列内では、アクサン グラーブ文字は機能しません。</span><span class="sxs-lookup"><span data-stu-id="70637-117">Inside the here-string, the backtick character does not work.</span></span> <span data-ttu-id="70637-118">また、次のように、前の円記号でエスケープすることで、結果のリテラルバックスラッシュを保持することもできます `\\` 。</span><span class="sxs-lookup"><span data-stu-id="70637-118">You can also preserve a literal backslash in your results by escaping it with a preceding backslash, like this: `\\`.</span></span> <span data-ttu-id="70637-119">ファイルのパスでよく使用されるような、エスケープされていない円記号は、結果内で無効なエスケープ シーケンスとして扱われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="70637-119">Unescaped backslash characters, such as those that are commonly used in file paths, can render as illegal escape sequences in your results.</span></span>

<span data-ttu-id="70637-120">PowerShell 7 は、 **Delimiter** パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="70637-120">PowerShell 7 adds the **Delimiter** parameter.</span></span>

## <span data-ttu-id="70637-121">例</span><span class="sxs-lookup"><span data-stu-id="70637-121">EXAMPLES</span></span>

### <span data-ttu-id="70637-122">例 1: 単一引用符で囲まれた文字列をハッシュテーブルに変換する</span><span class="sxs-lookup"><span data-stu-id="70637-122">Example 1: Convert a single-quoted here-string to a hash table</span></span>

<span data-ttu-id="70637-123">この例では、ユーザーメッセージの単一引用符で囲まれた文字列をハッシュテーブルに変換します。</span><span class="sxs-lookup"><span data-stu-id="70637-123">This example converts a single-quoted here-string of user messages into a hash table.</span></span> <span data-ttu-id="70637-124">単一引用符で囲まれた文字列内では、値は変数と置き換えられず、式も評価されません。</span><span class="sxs-lookup"><span data-stu-id="70637-124">In a single-quoted string, values are not substituted for variables and expressions are not evaluated.</span></span>
<span data-ttu-id="70637-125">`ConvertFrom-StringData`コマンドレットは、変数の値を `$Here` ハッシュテーブルに変換します。</span><span class="sxs-lookup"><span data-stu-id="70637-125">The `ConvertFrom-StringData` cmdlet converts the value in the `$Here` variable to a hash table.</span></span>

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
ConvertFrom-StringData -StringData $Here
```

```Output
Name                           Value
----                           -----
Msg3                           The specified variable does not exist.
Msg2                           Credentials are required for this command.
Msg1                           The string parameter is required.
```

### <span data-ttu-id="70637-126">例 2: 別の区切り記号を使用して文字列データを変換する</span><span class="sxs-lookup"><span data-stu-id="70637-126">Example 2: Convert string data using a different delimiter</span></span>

<span data-ttu-id="70637-127">この例では、区切り記号として別の文字を使用する文字列データを変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="70637-127">This example shows how to convert string data that uses a different character as a delimiter.</span></span> <span data-ttu-id="70637-128">この例では、文字列データは、区切り記号としてパイプ文字 () を使用してい `|` ます。</span><span class="sxs-lookup"><span data-stu-id="70637-128">In this example the string data is using the pipe character (`|`) as the delimiter.</span></span>

```powershell
$StringData = @'
color|red
model|coupe
year|1965
condition|mint
'@
$carData = ConvertFrom-StringData -StringData $StringData -Delimiter '|'
$carData
```

```Output
Name                           Value
----                           -----
condition                      mint
model                          coupe
color                          red
year                           1965
```

### <span data-ttu-id="70637-129">例 3: コメントを含む文字列を変換する</span><span class="sxs-lookup"><span data-stu-id="70637-129">Example 3: Convert a here-string containing a comment</span></span>

<span data-ttu-id="70637-130">この例では、コメントと複数のキーと値のペアを含む文字列をハッシュテーブルに変換します。</span><span class="sxs-lookup"><span data-stu-id="70637-130">This example converts a here-string that contains a comment and multiple key-value pairs into a hash table.</span></span>

```powershell
ConvertFrom-StringData -StringData @'
Name = Disks.ps1

# Category is optional.

Category = Storage
Cost = Free
'@
```

```Output
Name                           Value
----                           -----
Cost                           Free
Category                       Storage
Name                           Disks.ps1
```

<span data-ttu-id="70637-131">**Convertfrom-stringdata** パラメーターの値は、ここで指定した文字列を含む変数ではなく、ここで指定した文字列です。</span><span class="sxs-lookup"><span data-stu-id="70637-131">The value of the **StringData** parameter is a here-string, instead of a variable that contains a here-string.</span></span> <span data-ttu-id="70637-132">どちらの形式も有効です。</span><span class="sxs-lookup"><span data-stu-id="70637-132">Either format is valid.</span></span> <span data-ttu-id="70637-133">ヒア文字列には、文字列の 1 つについてのコメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="70637-133">The here-string includes a comment about one of the strings.</span></span>
<span data-ttu-id="70637-134">`ConvertFrom-StringData` 単一行コメントは無視されますが、 `#` 文字は行の最初の空白以外の文字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="70637-134">`ConvertFrom-StringData` ignores single-line comments, but the `#` character must be the first non-whitespace character on the line.</span></span> <span data-ttu-id="70637-135">の後の行のすべての文字 `#` が無視されます。</span><span class="sxs-lookup"><span data-stu-id="70637-135">All characters on the line after the `#` are ignored.</span></span>

### <span data-ttu-id="70637-136">例 4: 文字列をハッシュテーブルに変換する</span><span class="sxs-lookup"><span data-stu-id="70637-136">Example 4: Convert a string to a hash table</span></span>

<span data-ttu-id="70637-137">この例では、通常の二重引用符で囲まれた文字列 (ここではない文字列) をハッシュテーブルに変換し、変数に保存し `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="70637-137">This example converts a regular double-quoted string (not a here-string) into a hash table and saves it in the `$A` variable.</span></span>

```powershell
$A = ConvertFrom-StringData -StringData "Top = Red `n Bottom = Blue"
$A
```

```Output
Name             Value
----             -----
Bottom           Blue
Top              Red
```

<span data-ttu-id="70637-138">各キーと値のペアが別々の行に存在する必要があるという条件を満たすために、文字列は PowerShell の改行文字 ( \` n) を使用してペアを区切ります。</span><span class="sxs-lookup"><span data-stu-id="70637-138">To satisfy the condition that each key-value pair must be on a separate line, the string uses the PowerShell newline character (\`n) to separate the pairs.</span></span>

### <span data-ttu-id="70637-139">例 5: スクリプトの DATA セクションで ConvertFrom-StringData を使用する</span><span class="sxs-lookup"><span data-stu-id="70637-139">Example 5: Use ConvertFrom-StringData in the DATA section of a script</span></span>

<span data-ttu-id="70637-140">この例は、 `ConvertFrom-StringData` スクリプトの DATA セクションで使用されるコマンドを示しています。</span><span class="sxs-lookup"><span data-stu-id="70637-140">This example shows a `ConvertFrom-StringData` command used in the DATA section of a script.</span></span>
<span data-ttu-id="70637-141">DATA セクションの下のステートメントによって、テキストがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="70637-141">The statements below the DATA section display the text to the user.</span></span>

```powershell
$TextMsgs = DATA {
ConvertFrom-StringData @'
Text001 = The $Notebook variable contains the name of the user's system notebook.
Text002 = The $MyNotebook variable contains the name of the user's private notebook.
'@
}
$TextMsgs
```

```Output
Name             Value
----             -----
Text001          The $Notebook variable contains the name of the user's system notebook.
Text002          The $MyNotebook variable contains the name of the user's private notebook.
```

<span data-ttu-id="70637-142">テキストには変数名が含まれています。変数が展開されずにリテラルとして解釈されるようにするには、これを単一引用符の文字列で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="70637-142">Because the text includes variable names, it must be enclosed in a single-quoted string so that the variables are interpreted literally and not expanded.</span></span> <span data-ttu-id="70637-143">**データ** セクションでは変数は使用できません。</span><span class="sxs-lookup"><span data-stu-id="70637-143">Variables are not permitted in the **DATA** section.</span></span>

### <span data-ttu-id="70637-144">例 6: パイプライン演算子を使用して文字列を渡す</span><span class="sxs-lookup"><span data-stu-id="70637-144">Example 6: Use the pipeline operator to pass a string</span></span>

<span data-ttu-id="70637-145">この例は、パイプライン演算子 () を使用して、に文字列を送信できることを示して `|` `ConvertFrom-StringData` います。</span><span class="sxs-lookup"><span data-stu-id="70637-145">This example shows that you can use a pipeline operator (`|`) to send a string to `ConvertFrom-StringData`.</span></span> <span data-ttu-id="70637-146">変数の値 `$Here` がにパイプされ、 `ConvertFrom-StringData` 変数の結果になり `$Hash` ます。</span><span class="sxs-lookup"><span data-stu-id="70637-146">The the value of the `$Here` variable is piped to `ConvertFrom-StringData` and the result in the `$Hash` variable.</span></span>

```powershell
$Here = @'
Msg1 = The string parameter is required.
Msg2 = Credentials are required for this command.
Msg3 = The specified variable does not exist.
'@
$Hash = $Here | ConvertFrom-StringData
$Hash
```

```Output
Name     Value
----     -----
Msg3     The specified variable does not exist.
Msg2     Credentials are required for this command.
Msg1     The string parameter is required.
```

### <span data-ttu-id="70637-147">例 7: エスケープ文字を使用して新しい行と文字を追加する</span><span class="sxs-lookup"><span data-stu-id="70637-147">Example 7: Use escape characters to add new lines and return characters</span></span>

<span data-ttu-id="70637-148">この例では、エスケープ文字を使用して、ソースデータに新しい行を作成し、文字を返す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="70637-148">This example shows the use of escape characters to create new lines and return characters in source data.</span></span> <span data-ttu-id="70637-149">エスケープシーケンス `\n` は、結果のハッシュテーブル内の名前または項目に関連付けられたテキストのブロック内に新しい行を作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="70637-149">The escape sequence `\n` is used to create new lines within a block of text that is associated with a name or item in the resulting hash table.</span></span>

```powershell
ConvertFrom-StringData @"
Vincentio = Heaven doth with us as we with torches do,\nNot light them for themselves; for if our virtues\nDid not go forth of us, 'twere all alike\nAs if we had them not.
Angelo = Let there be some more test made of my metal,\nBefore so noble and so great a figure\nBe stamp'd upon it.
"@ | Format-List
```

```Output
Name  : Angelo
Value : Let there be some more test made of my metal,
        Before so noble and so great a figure
        Be stamp'd upon it.

Name  : Vincentio
Value : Heaven doth with us as we with torches do,
        Not light them for themselves; for if our virtues
        Did not go forth of us, 'twere all alike
        As if we had them not.
```

### <span data-ttu-id="70637-150">例 8: ファイルパスを正しく表示するには、円記号のエスケープ文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="70637-150">Example 8: Use backslash escape character to correctly render a file path</span></span>

<span data-ttu-id="70637-151">この例では、文字列データ内の円記号のエスケープ文字を使用して、結果のハッシュテーブルでファイルパスが正しくレンダリングされるようにする方法を示し `ConvertFrom-StringData` ます。</span><span class="sxs-lookup"><span data-stu-id="70637-151">This example shows how to use of the backslash escape character in the string data to allow a file path to render correctly in the resulting `ConvertFrom-StringData` hash table.</span></span> <span data-ttu-id="70637-152">円記号を二重にすることにより、リテラルの円記号がハッシュ テーブルの出力で正しく表示されます。</span><span class="sxs-lookup"><span data-stu-id="70637-152">The double backslash ensures that the literal backslash characters render correctly in the hash table output.</span></span>

```powershell
ConvertFrom-StringData "Message=Look in c:\\Windows\\System32"
```

```Output
Name                           Value
----                           -----
Message                        Look in c:\Windows\System32
```

## <span data-ttu-id="70637-153">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="70637-153">PARAMETERS</span></span>

### <span data-ttu-id="70637-154">-Convertfrom-stringdata</span><span class="sxs-lookup"><span data-stu-id="70637-154">-StringData</span></span>

<span data-ttu-id="70637-155">変換する文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="70637-155">Specifies the string to be converted.</span></span> <span data-ttu-id="70637-156">このパラメーターを使用するか、パイプを使用してに文字列を渡し `ConvertFrom-StringData` ます。</span><span class="sxs-lookup"><span data-stu-id="70637-156">You can use this parameter or pipe a string to `ConvertFrom-StringData`.</span></span> <span data-ttu-id="70637-157">パラメーター名は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="70637-157">The parameter name is optional.</span></span>

<span data-ttu-id="70637-158">このパラメーターの値は、1つまたは複数のキーと値のペアを含む文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="70637-158">The value of this parameter must be a string that contains one or more key-value pairs.</span></span> <span data-ttu-id="70637-159">各キーと値のペアは別々の行に記述する必要があります。または、各ペアを改行文字 (n) で区切る必要があり \` ます。</span><span class="sxs-lookup"><span data-stu-id="70637-159">Each key-value pair must be on a separate line, or each pair must be separated by newline characters (\`n).</span></span>

<span data-ttu-id="70637-160">文字列にコメントを含めることはできますが、コメントをキーと値のペアと同じ行に記述することはできません。</span><span class="sxs-lookup"><span data-stu-id="70637-160">You can include comments in the string, but the comments cannot be on the same line as a key-value pair.</span></span> <span data-ttu-id="70637-161">`ConvertFrom-StringData` 単一行コメントを無視します。</span><span class="sxs-lookup"><span data-stu-id="70637-161">`ConvertFrom-StringData` ignores single-line comments.</span></span> <span data-ttu-id="70637-162">この `#` 文字は、行の空白以外の最初の文字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="70637-162">The `#` character must be the first non-whitespace character on the line.</span></span> <span data-ttu-id="70637-163">の後の行のすべての文字 `#` が無視されます。</span><span class="sxs-lookup"><span data-stu-id="70637-163">All characters on the line after the `#` are ignored.</span></span> <span data-ttu-id="70637-164">コメントは、ハッシュ テーブルに含まれません。</span><span class="sxs-lookup"><span data-stu-id="70637-164">The comments are not included in the hash table.</span></span>

<span data-ttu-id="70637-165">ここでは、1つ以上の行で構成される文字列です。</span><span class="sxs-lookup"><span data-stu-id="70637-165">A here-string is a string consisting of one or more lines.</span></span> <span data-ttu-id="70637-166">ここで指定した文字列内の引用符は、文字列データの一部として文字どおり解釈されます。</span><span class="sxs-lookup"><span data-stu-id="70637-166">Quotation marks within the here-string are interpreted literally as part of the string data.</span></span> <span data-ttu-id="70637-167">詳細については、「 [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70637-167">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="70637-168">-区切り記号</span><span class="sxs-lookup"><span data-stu-id="70637-168">-Delimiter</span></span>

<span data-ttu-id="70637-169">変換される文字列の **値** データから **キー** を区切るために使用される文字。</span><span class="sxs-lookup"><span data-stu-id="70637-169">The character used to separate the **key** from the **value** data in the string being converted.</span></span>
<span data-ttu-id="70637-170">既定の区切り記号は等号 ( `=` ) です。</span><span class="sxs-lookup"><span data-stu-id="70637-170">The default delimiter is the equals sign (`=`) character.</span></span> <span data-ttu-id="70637-171">このパラメーターは、PowerShell 7 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="70637-171">This parameter was added in PowerShell 7.</span></span>

```yaml
Type: System.Char
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: '='
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70637-172">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="70637-172">CommonParameters</span></span>

<span data-ttu-id="70637-173">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="70637-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="70637-174">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70637-174">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="70637-175">入力</span><span class="sxs-lookup"><span data-stu-id="70637-175">INPUTS</span></span>

### <span data-ttu-id="70637-176">System.String</span><span class="sxs-lookup"><span data-stu-id="70637-176">System.String</span></span>

<span data-ttu-id="70637-177">パイプを使用して、キーと値のペアを含む文字列をにパイプすることができ `ConvertFrom-StringData` ます。</span><span class="sxs-lookup"><span data-stu-id="70637-177">You can pipe a string containing a key-value pair to `ConvertFrom-StringData`.</span></span>

## <span data-ttu-id="70637-178">出力</span><span class="sxs-lookup"><span data-stu-id="70637-178">OUTPUTS</span></span>

### <span data-ttu-id="70637-179">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="70637-179">System.Collections.Hashtable</span></span>

<span data-ttu-id="70637-180">このコマンドレットは、キーと値のペアから作成されたハッシュテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="70637-180">This cmdlet returns a hash table that it creates from the key-value pairs.</span></span>

## <span data-ttu-id="70637-181">注</span><span class="sxs-lookup"><span data-stu-id="70637-181">NOTES</span></span>

<span data-ttu-id="70637-182">ヒア文字列は、1 つまたは複数の行から構成される文字列で、引用符はリテラルとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="70637-182">A here-string is a string consisting of one or more lines within which quotation marks are interpreted literally.</span></span>

<span data-ttu-id="70637-183">このコマンドレットは、複数の音声言語でユーザーメッセージを表示するスクリプトで役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="70637-183">This cmdlet can be useful in scripts that display user messages in multiple spoken languages.</span></span> <span data-ttu-id="70637-184">辞書形式のハッシュ テーブルを使用すると、リソース ファイルのようにコードからテキスト文字列を分離したり、翻訳ツールで使用するためにテキスト文字列を書式設定したりできます。</span><span class="sxs-lookup"><span data-stu-id="70637-184">You can use the dictionary-style hash tables to isolate text strings from code, such as in resource files, and to format the text strings for use in translation tools.</span></span>

## <span data-ttu-id="70637-185">関連リンク</span><span class="sxs-lookup"><span data-stu-id="70637-185">RELATED LINKS</span></span>

