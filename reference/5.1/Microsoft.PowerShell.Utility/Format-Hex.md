---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 514a66ebee3827de998622a738c75d4f8e0c7279
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214027"
---
# <span data-ttu-id="e3e7d-103">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="e3e7d-103">Format-Hex</span></span>

## <span data-ttu-id="e3e7d-104">概要</span><span class="sxs-lookup"><span data-stu-id="e3e7d-104">SYNOPSIS</span></span>

<span data-ttu-id="e3e7d-105">ファイルまたはその他の入力を16進数として表示します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-105">Displays a file or other input as hexadecimal.</span></span>

## <span data-ttu-id="e3e7d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e3e7d-106">SYNTAX</span></span>

### <span data-ttu-id="e3e7d-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="e3e7d-107">Path (Default)</span></span>

```
Format-Hex [-Path] <string[]> [<CommonParameters>]
```

### <span data-ttu-id="e3e7d-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e3e7d-108">LiteralPath</span></span>

```
Format-Hex -LiteralPath <string[]> [<CommonParameters>]
```

### <span data-ttu-id="e3e7d-109">ByInputObject</span><span class="sxs-lookup"><span data-stu-id="e3e7d-109">ByInputObject</span></span>

```
Format-Hex -InputObject <Object> [-Encoding <string>] [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="e3e7d-110">Description</span><span class="sxs-lookup"><span data-stu-id="e3e7d-110">DESCRIPTION</span></span>

<span data-ttu-id="e3e7d-111">`Format-Hex`コマンドレットは、ファイルまたはその他の入力を16進数値として表示します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-111">The `Format-Hex` cmdlet displays a file or other input as hexadecimal values.</span></span> <span data-ttu-id="e3e7d-112">出力からの文字のオフセットを確認するには、行の左端にある数値をその文字の列の先頭にある数値に追加します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-112">To determine the offset of a character from the output, add the number at the leftmost of the row to the number at the top of the column for that character.</span></span>

<span data-ttu-id="e3e7d-113">`Format-Hex`コマンドレットを使用すると、破損したファイルのファイルの種類やファイル名の拡張子が付いていないファイルを特定できます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-113">The `Format-Hex` cmdlet can help you determine the file type of a corrupted file or a file that might not have a filename extension.</span></span> <span data-ttu-id="e3e7d-114">このコマンドレットを実行し、16進数の出力を読み取ってファイル情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-114">You can run this cmdlet, and then read the hexadecimal output to get file information.</span></span>

<span data-ttu-id="e3e7d-115">ファイルでを使用する場合 `Format-Hex` 、コマンドレットは、改行文字を無視して、改行文字が保持された1つの文字列内のファイルの内容全体を返します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-115">When using `Format-Hex` on a file, the cmdlet ignores newline characters and returns the entire contents of a file in one string with the newline characters preserved.</span></span>

## <span data-ttu-id="e3e7d-116">例</span><span class="sxs-lookup"><span data-stu-id="e3e7d-116">EXAMPLES</span></span>

### <span data-ttu-id="e3e7d-117">例 1: 文字列の16進数表現を取得する</span><span class="sxs-lookup"><span data-stu-id="e3e7d-117">Example 1: Get the hexadecimal representation of a string</span></span>

<span data-ttu-id="e3e7d-118">このコマンドは、文字列の16進数の値を返します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-118">This command returns the hexadecimal values of a string.</span></span>

```powershell
'Hello World' | Format-Hex
```

```Output
           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   48 65 6C 6C 6F 20 57 6F 72 6C 64                 Hello World
```

<span data-ttu-id="e3e7d-119">文字列 **Hello World** は、パイプラインを介してコマンドレットに送信され `Format-Hex` ます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-119">The string **Hello World** is sent down the pipeline to the `Format-Hex` cmdlet.</span></span> <span data-ttu-id="e3e7d-120">からの16進数の出力は、 `Format-Hex` 文字列の各文字の値を示しています。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-120">The hexadecimal output from `Format-Hex` shows the values of each character in the string.</span></span>

### <span data-ttu-id="e3e7d-121">例 2:16 進数の出力からファイルの種類を検索する</span><span class="sxs-lookup"><span data-stu-id="e3e7d-121">Example 2: Find a file type from hexadecimal output</span></span>

<span data-ttu-id="e3e7d-122">この例では、16進数の出力を使用して、ファイルの種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-122">This example uses the hexadecimal output to determine the file type.</span></span> <span data-ttu-id="e3e7d-123">コマンドレットにより、ファイルの完全なパスと16進値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-123">The cmdlet displays the file's full path and the hexadecimal values.</span></span>

<span data-ttu-id="e3e7d-124">次のコマンドをテストするには、ローカルコンピューター上の既存の PDF ファイルのコピーを作成し、コピーしたファイルの名前を **t7f** に変更します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-124">To test the following command, make a copy of an existing PDF file on your local computer and rename the copied file to **File.t7f** .</span></span>

```powershell
Format-Hex -Path .\File.t7f
```

```Output
           Path: C:\Test\File.t7f

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   25 50 44 46 2D 31 2E 35 0D 0A 25 B5 B5 B5 B5 0D  %PDF-1.5..%????.
00000010   0A 31 20 30 20 6F 62 6A 0D 0A 3C 3C 2F 54 79 70  .1 0 obj..<</Typ
00000020   65 2F 43 61 74 61 6C 6F 67 2F 50 61 67 65 73 20  e/Catalog/Pages
```

<span data-ttu-id="e3e7d-125">この `Format-Hex` コマンドレットは、 **Path** パラメーターを使用して、現在のディレクトリにあるファイル名を指定し `File.t7f` ます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-125">The `Format-Hex` cmdlet uses the **Path** parameter to specify a filename in the current directory, `File.t7f`.</span></span> <span data-ttu-id="e3e7d-126">ファイル拡張子は `.t7f` 一般的ではありませんが、16進数の出力は `%PDF` PDF ファイルであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-126">The file extension `.t7f` is uncommon, but the hexadecimal output `%PDF` shows that it is a PDF file.</span></span>

### <span data-ttu-id="e3e7d-127">例 3: 生の16進数の出力を表示する</span><span class="sxs-lookup"><span data-stu-id="e3e7d-127">Example 3: Display raw hexadecimal output</span></span>

<span data-ttu-id="e3e7d-128">既定では `Format-Hex` 、数値データ型のコンパクト出力を指定します。値が十分小さい場合は、1バイトまたは2バイトのシーケンスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-128">By default `Format-Hex` opts for compact output of numeric data types: single-byte or double-byte sequences are used if the value is small enough.</span></span> <span data-ttu-id="e3e7d-129">**Raw** パラメーターは、この動作を非アクティブにします。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-129">The **Raw** parameter deactivates this behavior.</span></span>

```
PS> 1,2,3,1000 | Format-Hex

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 02 03 E8 03                                   ...è.


PS> 1,2,3,1000 | Format-Hex -Raw

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 00 00 00 02 00 00 00 03 00 00 00 E8 03 00 00  ............è...
```

<span data-ttu-id="e3e7d-130">出力の違いに注目してください。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-130">Notice the difference in output.</span></span> <span data-ttu-id="e3e7d-131">**Raw** パラメーターは、4バイト値として数値を表示します。これらの **Int32** 型には true を指定します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-131">The **Raw** parameter displays the numbers as 4-byte values, true to their **Int32** types.</span></span>

## <span data-ttu-id="e3e7d-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e3e7d-132">PARAMETERS</span></span>

### <span data-ttu-id="e3e7d-133">-Encoding</span><span class="sxs-lookup"><span data-stu-id="e3e7d-133">-Encoding</span></span>

<span data-ttu-id="e3e7d-134">出力のエンコーディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-134">Specifies the encoding of the output.</span></span> <span data-ttu-id="e3e7d-135">これは、入力にのみ適用さ `[string]` れます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-135">This only applies to `[string]` input.</span></span> <span data-ttu-id="e3e7d-136">パラメーターは数値型には影響しません。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-136">The parameter has no effect on numeric types.</span></span> <span data-ttu-id="e3e7d-137">既定値は `ASCII` です。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-137">The default value is `ASCII`.</span></span>

<span data-ttu-id="e3e7d-138">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-138">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="e3e7d-139">`Ascii` ASCII (7 ビット) 文字セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-139">`Ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="e3e7d-140">`BigEndianUnicode` は、ビッグエンディアンのバイト順で UTF-16 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-140">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="e3e7d-141">`Unicode` は、リトルエンディアンのバイト順で UTF-16 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-141">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="e3e7d-142">`UTF7` UTF-7 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-142">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="e3e7d-143">`UTF8` UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-143">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="e3e7d-144">`UTF32` は、リトルエンディアンのバイト順で 32 UTF-8 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-144">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

<span data-ttu-id="e3e7d-145">入力の ASCII 以外の文字は、リテラル文字として出力され、 `?` 情報が失われます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-145">Non-ASCII characters in the input are output as literal `?` characters resulting in a loss of information.</span></span>

```yaml
Type: System.String
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: ASCII
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3e7d-146">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e3e7d-146">-InputObject</span></span>

<span data-ttu-id="e3e7d-147">パイプラインの入力に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-147">Used for pipeline input.</span></span> <span data-ttu-id="e3e7d-148">パイプライン入力は、パイプの特定のスカラー型とインスタンスのみをサポート `[system.io.fileinfo]` `Get-ChildItem` しています。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-148">Pipeline input supports only certain scalar types and `[system.io.fileinfo]` instances for piping from `Get-ChildItem`.</span></span>

<span data-ttu-id="e3e7d-149">サポートされているスカラー型は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-149">The supported scalar types are:</span></span>

- `[string]`
- `[byte]`
- <span data-ttu-id="e3e7d-150">`[int]`, `[int32]`</span><span class="sxs-lookup"><span data-stu-id="e3e7d-150">`[int]`, `[int32]`</span></span>
- <span data-ttu-id="e3e7d-151">`[long]`, `[int64]`</span><span class="sxs-lookup"><span data-stu-id="e3e7d-151">`[long]`, `[int64]`</span></span>

```yaml
Type: System.Object
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e3e7d-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e3e7d-152">-LiteralPath</span></span>

<span data-ttu-id="e3e7d-153">ファイルへの完全パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-153">Specifies the complete path to a file.</span></span> <span data-ttu-id="e3e7d-154">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-154">The value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="e3e7d-155">このパラメーターでは、ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-155">This parameter does not accept wildcard characters.</span></span> <span data-ttu-id="e3e7d-156">ファイルへの複数のパスを指定するには、パスをコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-156">To specify multiple paths to files, separate the paths with a comma.</span></span> <span data-ttu-id="e3e7d-157">**LiteralPath** パラメーターにエスケープ文字が含まれている場合は、そのパスを単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-157">If the **LiteralPath** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="e3e7d-158">PowerShell は、1つの引用符で囲まれた文字列内の文字をエスケープシーケンスとして解釈しません。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-158">PowerShell does not interpret any characters in a single quoted string as escape sequences.</span></span> <span data-ttu-id="e3e7d-159">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-159">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e3e7d-160">-Path</span><span class="sxs-lookup"><span data-stu-id="e3e7d-160">-Path</span></span>

<span data-ttu-id="e3e7d-161">ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-161">Specifies the path to files.</span></span> <span data-ttu-id="e3e7d-162">現在の場所を指定するには、ドット () を使用し `.` ます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-162">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="e3e7d-163">ワイルドカード文字 ( `*` ) は受け入れられ、場所のすべての項目を指定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-163">The wildcard character (`*`) is accepted and can be used to specify all the items in a location.</span></span> <span data-ttu-id="e3e7d-164">**Path** パラメーターにエスケープ文字が含まれている場合は、パスを単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-164">If the **Path** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="e3e7d-165">ファイルへの複数のパスを指定するには、パスをコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-165">To specify multiple paths to files, separate the paths with a comma.</span></span>

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

### <span data-ttu-id="e3e7d-166">-Raw</span><span class="sxs-lookup"><span data-stu-id="e3e7d-166">-Raw</span></span>

<span data-ttu-id="e3e7d-167">既定では `Format-Hex` 、数値データ型のコンパクト出力を指定します。値が十分小さい場合は、1バイトまたは2バイトのシーケンスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-167">By default `Format-Hex` opts for compact output of numeric data types: single-byte or double-byte sequences are used if the value is small enough.</span></span> <span data-ttu-id="e3e7d-168">**Raw** パラメーターは、この動作を非アクティブにします。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-168">The **Raw** parameter deactivates this behavior.</span></span>

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

### <span data-ttu-id="e3e7d-169">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e3e7d-169">CommonParameters</span></span>

<span data-ttu-id="e3e7d-170">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-170">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e3e7d-171">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-171">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e3e7d-172">入力</span><span class="sxs-lookup"><span data-stu-id="e3e7d-172">INPUTS</span></span>

### <span data-ttu-id="e3e7d-173">System.String</span><span class="sxs-lookup"><span data-stu-id="e3e7d-173">System.String</span></span>

<span data-ttu-id="e3e7d-174">パイプを使用してこのコマンドレットに文字列を送ることができます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-174">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="e3e7d-175">出力</span><span class="sxs-lookup"><span data-stu-id="e3e7d-175">OUTPUTS</span></span>

### <span data-ttu-id="e3e7d-176">ByteCollection です。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-176">Microsoft.PowerShell.Commands.ByteCollection</span></span>

<span data-ttu-id="e3e7d-177">このコマンドレットは、 **ByteCollection** を返します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-177">This cmdlet returns a **ByteCollection** .</span></span> <span data-ttu-id="e3e7d-178">このオブジェクトは、バイトのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-178">This object represents a collection of bytes.</span></span> <span data-ttu-id="e3e7d-179">これには、バイトのコレクションを、によって返される出力の各行のように書式設定された文字列に変換するメソッドが含まれてい `Format-Hex` ます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-179">It includes methods that convert the collection of bytes to a string formatted like each line of output returned by `Format-Hex`.</span></span> <span data-ttu-id="e3e7d-180">**Path** または **LiteralPath** パラメーターを指定した場合、オブジェクトには、各バイトを含むファイルのパスも含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-180">If you specify the **Path** or **LiteralPath** parameter, the object also contains the path of the file that contains each byte.</span></span>

## <span data-ttu-id="e3e7d-181">注</span><span class="sxs-lookup"><span data-stu-id="e3e7d-181">NOTES</span></span>

<span data-ttu-id="e3e7d-182">出力の右端の列は、バイトを文字として表示しようとします。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-182">The right-most column of output tries to render the bytes as characters:</span></span>

<span data-ttu-id="e3e7d-183">通常、各バイトは Unicode コードポイントとして解釈されます。これは、次のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-183">Generally, each byte is interpreted as a Unicode code point, which means that:</span></span>

- <span data-ttu-id="e3e7d-184">印刷可能な ASCII 文字は、常に正しく表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-184">Printable ASCII characters are always rendered correctly</span></span>
- <span data-ttu-id="e3e7d-185">複数バイトの UTF-8 文字が正しく表示されることはありません</span><span class="sxs-lookup"><span data-stu-id="e3e7d-185">Multi-byte UTF-8 characters never render correctly</span></span>
- <span data-ttu-id="e3e7d-186">UTF-16 文字は、上位バイトが発生した場合にのみ正しくレンダリングさ `NUL` れます。</span><span class="sxs-lookup"><span data-stu-id="e3e7d-186">UTF-16 characters render correctly only if their high-order byte happens be `NUL`.</span></span>

## <span data-ttu-id="e3e7d-187">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e3e7d-187">RELATED LINKS</span></span>

[<span data-ttu-id="e3e7d-188">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="e3e7d-188">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="e3e7d-189">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="e3e7d-189">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="e3e7d-190">Format-List</span><span class="sxs-lookup"><span data-stu-id="e3e7d-190">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="e3e7d-191">Format-Table</span><span class="sxs-lookup"><span data-stu-id="e3e7d-191">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="e3e7d-192">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="e3e7d-192">Format-Wide</span></span>](Format-Wide.md)
