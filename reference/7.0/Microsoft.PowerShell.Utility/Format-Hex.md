---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 6cb02f1c6f2583ce4146356fac3553e99a54c7c2
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211032"
---
# <span data-ttu-id="c4ad5-103">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="c4ad5-103">Format-Hex</span></span>

## <span data-ttu-id="c4ad5-104">概要</span><span class="sxs-lookup"><span data-stu-id="c4ad5-104">SYNOPSIS</span></span>

<span data-ttu-id="c4ad5-105">ファイルまたはその他の入力を16進数として表示します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-105">Displays a file or other input as hexadecimal.</span></span>

## <span data-ttu-id="c4ad5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c4ad5-106">SYNTAX</span></span>

### <span data-ttu-id="c4ad5-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="c4ad5-107">Path (Default)</span></span>

```
Format-Hex [-Path] <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### <span data-ttu-id="c4ad5-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c4ad5-108">LiteralPath</span></span>

```
Format-Hex -LiteralPath <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### <span data-ttu-id="c4ad5-109">ByInputObject</span><span class="sxs-lookup"><span data-stu-id="c4ad5-109">ByInputObject</span></span>
```
Format-Hex -InputObject <PSObject> [-Encoding <Encoding>] [-Count <Int64>] [-Offset <Int64>] [-Raw]
 [<CommonParameters>]
```

## <span data-ttu-id="c4ad5-110">Description</span><span class="sxs-lookup"><span data-stu-id="c4ad5-110">DESCRIPTION</span></span>

<span data-ttu-id="c4ad5-111">`Format-Hex`コマンドレットは、ファイルまたはその他の入力を16進数値として表示します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-111">The `Format-Hex` cmdlet displays a file or other input as hexadecimal values.</span></span> <span data-ttu-id="c4ad5-112">出力からの文字のオフセットを確認するには、行の左端にある数値をその文字の列の先頭にある数値に追加します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-112">To determine the offset of a character from the output, add the number at the leftmost of the row to the number at the top of the column for that character.</span></span>

<span data-ttu-id="c4ad5-113">`Format-Hex`コマンドレットを使用すると、破損したファイルのファイルの種類やファイル名の拡張子が付いていないファイルを特定できます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-113">The `Format-Hex` cmdlet can help you determine the file type of a corrupted file or a file that might not have a filename extension.</span></span> <span data-ttu-id="c4ad5-114">このコマンドレットを実行し、16進数の出力を読み取ってファイル情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-114">You can run this cmdlet, and then read the hexadecimal output to get file information.</span></span>

<span data-ttu-id="c4ad5-115">ファイルでを使用する場合 `Format-Hex` 、コマンドレットは、改行文字を無視して、改行文字が保持された1つの文字列内のファイルの内容全体を返します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-115">When using `Format-Hex` on a file, the cmdlet ignores newline characters and returns the entire contents of a file in one string with the newline characters preserved.</span></span>

## <span data-ttu-id="c4ad5-116">例</span><span class="sxs-lookup"><span data-stu-id="c4ad5-116">EXAMPLES</span></span>

### <span data-ttu-id="c4ad5-117">例 1: 文字列の16進数表現を取得する</span><span class="sxs-lookup"><span data-stu-id="c4ad5-117">Example 1: Get the hexadecimal representation of a string</span></span>

<span data-ttu-id="c4ad5-118">このコマンドは、文字列の16進数の値を返します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-118">This command returns the hexadecimal values of a string.</span></span>

```powershell
'Hello World' | Format-Hex
```

```Output
   Label: String (System.String) <2944BEC3>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 48 65 6C 6C 6F 20 57 6F 72 6C 64                Hello World
```

<span data-ttu-id="c4ad5-119">文字列 **Hello World** は、パイプラインを介してコマンドレットに送信され `Format-Hex` ます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-119">The string **Hello World** is sent down the pipeline to the `Format-Hex` cmdlet.</span></span> <span data-ttu-id="c4ad5-120">からの16進数の出力は、 `Format-Hex` 文字列の各文字の値を示しています。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-120">The hexadecimal output from `Format-Hex` shows the values of each character in the string.</span></span>

### <span data-ttu-id="c4ad5-121">例 2:16 進数の出力からファイルの種類を検索する</span><span class="sxs-lookup"><span data-stu-id="c4ad5-121">Example 2: Find a file type from hexadecimal output</span></span>

<span data-ttu-id="c4ad5-122">この例では、16進数の出力を使用して、ファイルの種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-122">This example uses the hexadecimal output to determine the file type.</span></span> <span data-ttu-id="c4ad5-123">コマンドレットにより、ファイルの完全なパスと16進値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-123">The cmdlet displays the file's full path and the hexadecimal values.</span></span>

<span data-ttu-id="c4ad5-124">次のコマンドをテストするには、ローカルコンピューター上の既存の PDF ファイルのコピーを作成し、コピーしたファイルの名前をに変更し `File.t7f` ます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-124">To test the following command, make a copy of an existing PDF file on your local computer and rename the copied file to `File.t7f`.</span></span>

```powershell
Format-Hex -Path .\File.t7f -Count 48
```

```Output
   Label: C:\Test\File.t7f

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 25 50 44 46 2D 31 2E 35 0D 0A 25 B5 B5 B5 B5 0D %PDF-1.5..%????.
0000000000000010 0A 31 20 30 20 6F 62 6A 0D 0A 3C 3C 2F 54 79 70 .1 0 obj..<</Typ
0000000000000020 65 2F 43 61 74 61 6C 6F 67 2F 50 61 67 65 73 20 e/Catalog/Pages
```

<span data-ttu-id="c4ad5-125">この `Format-Hex` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイル名を指定し `File.t7f` ます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-125">The `Format-Hex` cmdlet uses the **Path** parameter to specify a filename in the current directory, `File.t7f`.</span></span> <span data-ttu-id="c4ad5-126">ファイル拡張子は `.t7f` 一般的ではありませんが、16進数の出力は `%PDF` PDF ファイルであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-126">The file extension `.t7f` is uncommon, but the hexadecimal output `%PDF` shows that it is a PDF file.</span></span> <span data-ttu-id="c4ad5-127">この例では、 **Count** パラメーターを使用して、出力をファイルの最初の48バイトに制限しています。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-127">In this example, the **Count** parameter is used to limit the output to the first 48 bytes of the file.</span></span>

### <span data-ttu-id="c4ad5-128">例 3: 異なるデータ型の配列の書式を設定する</span><span class="sxs-lookup"><span data-stu-id="c4ad5-128">Example 3: Format an array of different data types</span></span>

<span data-ttu-id="c4ad5-129">この例では、さまざまなデータ型の配列を使用し `Format-Hex` て、がパイプライン内でどのように処理するかを強調します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-129">This example uses an array of different data types to highlight how `Format-Hex` handles them in the Pipeline.</span></span>

<span data-ttu-id="c4ad5-130">各オブジェクトは、パイプラインとプロセスを通じて個別に渡されます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-130">It will pass each object through the Pipeline and process individually.</span></span> <span data-ttu-id="c4ad5-131">ただし、数値データの場合、隣接するオブジェクトも数値である場合は、それらを1つの出力ブロックにグループ化します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-131">However, if it's numeric data, and the adjacent object is also numeric, it will group them into a single output block.</span></span>

```powershell
'Hello world!', 1, 1138, 'foo', 'bar', 0xdeadbeef, 1gb, 0b1101011100 , $true, $false | Format-Hex
```

```Output
   Label: String (System.String) <24F1F0A3>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 48 65 6C 6C 6F 20 77 6F 72 6C 64 21             Hello world!

   Label: Int32 (System.Int32) <2EB933C5>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 01 00 00 00 72 04 00 00                         �   r�

   Label: String (System.String) <4078B66C>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 66 6F 6F                                        foo

   Label: String (System.String) <51E4A317>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 62 61 72                                        bar

   Label: Int32 (System.Int32) <5ADF167B>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 EF BE AD DE 00 00 00 40 5C 03 00 00             ï¾­Þ   @\�

   Label: Boolean (System.Boolean) <7D8C4C1D>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 01 00 00 00 00 00 00 00                         �
```

## <span data-ttu-id="c4ad5-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c4ad5-132">PARAMETERS</span></span>

### <span data-ttu-id="c4ad5-133">-Encoding</span><span class="sxs-lookup"><span data-stu-id="c4ad5-133">-Encoding</span></span>

<span data-ttu-id="c4ad5-134">入力文字列のエンコーディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-134">Specifies the encoding of the input strings.</span></span> <span data-ttu-id="c4ad5-135">これは、入力にのみ適用さ `[string]` れます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-135">This only applies to `[string]` input.</span></span> <span data-ttu-id="c4ad5-136">パラメーターは数値型には影響しません。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-136">The parameter has no effect on numeric types.</span></span> <span data-ttu-id="c4ad5-137">出力値は常に `utf8NoBOM` です。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-137">The output value is always `utf8NoBOM`.</span></span>

<span data-ttu-id="c4ad5-138">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-138">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="c4ad5-139">`ascii`: ASCII (7 ビット) 文字セットのエンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-139">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="c4ad5-140">`bigendianunicode`: ビッグエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-140">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="c4ad5-141">`oem`: MS-DOS およびコンソールプログラムの既定のエンコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-141">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="c4ad5-142">`unicode`: リトルエンディアンのバイト順を使用して UTF-16 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-142">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="c4ad5-143">`utf7`: UTF-7 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-143">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="c4ad5-144">`utf8`: UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-144">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="c4ad5-145">`utf8BOM`: バイト順マーク (BOM) を使用して UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-145">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="c4ad5-146">`utf8NoBOM`: バイトオーダーマーク (BOM) を使用せずに UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-146">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="c4ad5-147">`utf32`:32 UTF-8 形式でエンコードします。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-147">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="c4ad5-148">PowerShell 6.2 以降では、 **Encoding** パラメーターを使用して、登録されているコードページの数値 id (など) `-Encoding 1251` や、登録されているコードページの文字列名 (など) を使用することもでき `-Encoding "windows-1251"` ます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-148">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="c4ad5-149">詳細については、 [コードページ](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2)の .net ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-149">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c4ad5-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c4ad5-150">-InputObject</span></span>

<span data-ttu-id="c4ad5-151">パイプラインの入力に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-151">Used for pipeline input.</span></span> <span data-ttu-id="c4ad5-152">パイプライン入力は、パイプの特定のスカラー型とインスタンスのみをサポート `[system.io.fileinfo]` `Get-ChildItem` しています。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-152">Pipeline input supports only certain scalar types and `[system.io.fileinfo]` instances for piping from `Get-ChildItem`.</span></span>

<span data-ttu-id="c4ad5-153">サポートされているスカラー型は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-153">The supported scalar types are:</span></span>

- <span data-ttu-id="c4ad5-154">`[string]`, `[char]`</span><span class="sxs-lookup"><span data-stu-id="c4ad5-154">`[string]`, `[char]`</span></span>
- <span data-ttu-id="c4ad5-155">`[byte]`, `[sbyte]`</span><span class="sxs-lookup"><span data-stu-id="c4ad5-155">`[byte]`, `[sbyte]`</span></span>
- <span data-ttu-id="c4ad5-156">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span><span class="sxs-lookup"><span data-stu-id="c4ad5-156">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span></span>
- <span data-ttu-id="c4ad5-157">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span><span class="sxs-lookup"><span data-stu-id="c4ad5-157">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span></span>
- <span data-ttu-id="c4ad5-158">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="c4ad5-158">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span></span>
- <span data-ttu-id="c4ad5-159">`[single]`, `[float]`, `[double]`</span><span class="sxs-lookup"><span data-stu-id="c4ad5-159">`[single]`, `[float]`, `[double]`</span></span>
- `[boolean]`

<span data-ttu-id="c4ad5-160">PowerShell 6.2 より前では、 `Format-Hex` は、すべてのオブジェクトをまとめてグループ化することで、複数の入力型を持つパイプライン入力を処理します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-160">Prior to PowerShell 6.2, `Format-Hex` would handle a Pipeline input with multiple input types by grouping all like objects together.</span></span> <span data-ttu-id="c4ad5-161">次に、パイプラインを通過するたびに個々のオブジェクトを処理し、オブジェクトが隣接している場合を除き、オブジェクトをグループ化しません。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-161">Now, it handles each individual object as it passes through the Pipeline and won't group objects together unless like objects are adjacent.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c4ad5-162">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c4ad5-162">-LiteralPath</span></span>

<span data-ttu-id="c4ad5-163">ファイルへの完全パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-163">Specifies the complete path to a file.</span></span> <span data-ttu-id="c4ad5-164">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-164">The value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="c4ad5-165">このパラメーターでは、ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-165">This parameter does not accept wildcard characters.</span></span> <span data-ttu-id="c4ad5-166">ファイルへの複数のパスを指定するには、パスをコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-166">To specify multiple paths to files, separate the paths with a comma.</span></span> <span data-ttu-id="c4ad5-167">**LiteralPath** パラメーターにエスケープ文字が含まれている場合は、そのパスを単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-167">If the **LiteralPath** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="c4ad5-168">PowerShell は、1つの引用符で囲まれた文字列内の文字をエスケープシーケンスとして解釈しません。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-168">PowerShell does not interpret any characters in a single quoted string as escape sequences.</span></span> <span data-ttu-id="c4ad5-169">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-169">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c4ad5-170">-Path</span><span class="sxs-lookup"><span data-stu-id="c4ad5-170">-Path</span></span>

<span data-ttu-id="c4ad5-171">ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-171">Specifies the path to files.</span></span> <span data-ttu-id="c4ad5-172">現在の場所を指定するには、ドット () を使用し `.` ます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-172">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="c4ad5-173">ワイルドカード文字 ( `*` ) は受け入れられ、場所のすべての項目を指定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-173">The wildcard character (`*`) is accepted and can be used to specify all the items in a location.</span></span> <span data-ttu-id="c4ad5-174">**Path** パラメーターにエスケープ文字が含まれている場合は、パスを単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-174">If the **Path** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="c4ad5-175">ファイルへの複数のパスを指定するには、パスをコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-175">To specify multiple paths to files, separate the paths with a comma.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="c4ad5-176">-Raw</span><span class="sxs-lookup"><span data-stu-id="c4ad5-176">-Raw</span></span>

<span data-ttu-id="c4ad5-177">このパラメーターでは何も行われなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-177">This parameter no longer does anything.</span></span> <span data-ttu-id="c4ad5-178">スクリプトの互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-178">It is retained for script compatibility.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c4ad5-179">-オフセット</span><span class="sxs-lookup"><span data-stu-id="c4ad5-179">-Offset</span></span>

<span data-ttu-id="c4ad5-180">これは、16進数の出力の一部としてスキップするバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-180">This represents the number of bytes to skip from being part of the hex output.</span></span>

<span data-ttu-id="c4ad5-181">このパラメーターは、PowerShell 6.2 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-181">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c4ad5-182">-カウント</span><span class="sxs-lookup"><span data-stu-id="c4ad5-182">-Count</span></span>

<span data-ttu-id="c4ad5-183">これは、16進数の出力に含めるバイト数を表します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-183">This represents the number of bytes to include in the hex output.</span></span>

<span data-ttu-id="c4ad5-184">このパラメーターは、PowerShell 6.2 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-184">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Int64.MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c4ad5-185">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c4ad5-185">CommonParameters</span></span>

<span data-ttu-id="c4ad5-186">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c4ad5-187">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c4ad5-188">入力</span><span class="sxs-lookup"><span data-stu-id="c4ad5-188">INPUTS</span></span>

### <span data-ttu-id="c4ad5-189">System.String</span><span class="sxs-lookup"><span data-stu-id="c4ad5-189">System.String</span></span>

<span data-ttu-id="c4ad5-190">パイプを使用してこのコマンドレットに文字列を送ることができます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-190">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="c4ad5-191">出力</span><span class="sxs-lookup"><span data-stu-id="c4ad5-191">OUTPUTS</span></span>

### <span data-ttu-id="c4ad5-192">ByteCollection です。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-192">Microsoft.PowerShell.Commands.ByteCollection</span></span>

<span data-ttu-id="c4ad5-193">このコマンドレットは、 **ByteCollection** を返します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-193">This cmdlet returns a **ByteCollection**.</span></span> <span data-ttu-id="c4ad5-194">このオブジェクトは、バイトのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-194">This object represents a collection of bytes.</span></span> <span data-ttu-id="c4ad5-195">これには、バイトのコレクションを、によって返される出力の各行のように書式設定された文字列に変換するメソッドが含まれてい `Format-Hex` ます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-195">It includes methods that convert the collection of bytes to a string formatted like each line of output returned by `Format-Hex`.</span></span> <span data-ttu-id="c4ad5-196">出力では、処理されているバイトの種類も示されます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-196">The output also states they type of bytes being processed.</span></span> <span data-ttu-id="c4ad5-197">**Path** または **LiteralPath** パラメーターを指定した場合、オブジェクトには、各バイトを含むファイルのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-197">If you specify the **Path** or **LiteralPath** parameter, the object contains the path of the file that contains each byte.</span></span> <span data-ttu-id="c4ad5-198">文字列、ブール値、整数などを渡すと、適切なラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-198">If you pass a string, boolean, integer, etc, it will be labeled appropriately.</span></span>

## <span data-ttu-id="c4ad5-199">注</span><span class="sxs-lookup"><span data-stu-id="c4ad5-199">NOTES</span></span>

<span data-ttu-id="c4ad5-200">出力の右端の列は、バイトを ASCII 文字として表示しようとします。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-200">The right-most column of output tries to render the bytes as ASCII characters:</span></span>

<span data-ttu-id="c4ad5-201">通常、各バイトは Unicode コードポイントとして解釈されます。これは、次のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-201">Generally, each byte is interpreted as a Unicode code point, which means that:</span></span>

- <span data-ttu-id="c4ad5-202">印刷可能な ASCII 文字は、常に正しく表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-202">Printable ASCII characters are always rendered correctly</span></span>
- <span data-ttu-id="c4ad5-203">複数バイトの UTF-8 文字が正しく表示されることはありません</span><span class="sxs-lookup"><span data-stu-id="c4ad5-203">Multi-byte UTF-8 characters never render correctly</span></span>
- <span data-ttu-id="c4ad5-204">UTF-16 文字は、上位バイトが発生した場合にのみ正しくレンダリングさ `NUL` れます。</span><span class="sxs-lookup"><span data-stu-id="c4ad5-204">UTF-16 characters render correctly only if their high-order byte happens be `NUL`.</span></span>

## <span data-ttu-id="c4ad5-205">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c4ad5-205">RELATED LINKS</span></span>

[<span data-ttu-id="c4ad5-206">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="c4ad5-206">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="c4ad5-207">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="c4ad5-207">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="c4ad5-208">Format-List</span><span class="sxs-lookup"><span data-stu-id="c4ad5-208">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="c4ad5-209">Format-Table</span><span class="sxs-lookup"><span data-stu-id="c4ad5-209">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="c4ad5-210">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="c4ad5-210">Format-Wide</span></span>](Format-Wide.md)
