---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: be590368539f396f0aac694e9565674393543f2c
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913204"
---
# <span data-ttu-id="53149-102">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="53149-102">ConvertTo-Csv</span></span>

## <span data-ttu-id="53149-103">概要</span><span class="sxs-lookup"><span data-stu-id="53149-103">SYNOPSIS</span></span>
<span data-ttu-id="53149-104">.NET オブジェクトを一連のコンマ区切り値 (CSV) 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="53149-104">Converts .NET objects into a series of comma-separated value (CSV) strings.</span></span>

## <span data-ttu-id="53149-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="53149-105">SYNTAX</span></span>

### <span data-ttu-id="53149-106">区切り記号 (既定値)</span><span class="sxs-lookup"><span data-stu-id="53149-106">Delimiter (Default)</span></span>

```
ConvertTo-Csv [-InputObject] <psobject> [[-Delimiter] <char>] [-NoTypeInformation]
 [<CommonParameters>]
```

### <span data-ttu-id="53149-107">UseCulture</span><span class="sxs-lookup"><span data-stu-id="53149-107">UseCulture</span></span>

```
ConvertTo-Csv [-InputObject] <psobject> [-UseCulture] [-NoTypeInformation] [<CommonParameters>]
```

## <span data-ttu-id="53149-108">Description</span><span class="sxs-lookup"><span data-stu-id="53149-108">DESCRIPTION</span></span>

<span data-ttu-id="53149-109">`ConvertTo-CSV`コマンドレットは、送信したオブジェクトを表す一連のコンマ区切り値 (CSV) 文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="53149-109">The `ConvertTo-CSV` cmdlet returns a series of comma-separated value (CSV) strings that represent the objects that you submit.</span></span> <span data-ttu-id="53149-110">その後、コマンドレットを使用して `ConvertFrom-Csv` 、CSV 文字列からオブジェクトを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="53149-110">You can then use the `ConvertFrom-Csv` cmdlet to recreate objects from the CSV strings.</span></span> <span data-ttu-id="53149-111">CSV から変換されたオブジェクトは、プロパティ値とメソッドを含まない元のオブジェクトの文字列値です。</span><span class="sxs-lookup"><span data-stu-id="53149-111">The objects converted from CSV are string values of the original objects that contain property values and no methods.</span></span>

<span data-ttu-id="53149-112">コマンドレットを使用して、 `Export-Csv` オブジェクトを CSV 文字列に変換できます。</span><span class="sxs-lookup"><span data-stu-id="53149-112">You can use the `Export-Csv` cmdlet to convert objects to CSV strings.</span></span> <span data-ttu-id="53149-113">`Export-CSV` はと似てい `ConvertTo-CSV` ますが、CSV 文字列をファイルに保存する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="53149-113">`Export-CSV` is similar to `ConvertTo-CSV`, except that it saves the CSV strings to a file.</span></span>

<span data-ttu-id="53149-114">コマンドレットには、 `ConvertTo-CSV` コンマ以外の区切り記号を指定するパラメーターや、現在のカルチャを区切り記号として使用するパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="53149-114">The `ConvertTo-CSV` cmdlet has parameters to specify a delimiter other than a comma or use the current culture as the delimiter.</span></span>

## <span data-ttu-id="53149-115">例</span><span class="sxs-lookup"><span data-stu-id="53149-115">EXAMPLES</span></span>

### <span data-ttu-id="53149-116">例 1: オブジェクトを CSV に変換する</span><span class="sxs-lookup"><span data-stu-id="53149-116">Example 1: Convert an object to CSV</span></span>

<span data-ttu-id="53149-117">この例では、 **プロセス** オブジェクトを CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="53149-117">This example converts a **Process** object to a CSV string.</span></span>

```powershell
Get-Process -Name 'PowerShell' | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"powershell","11","691","2204036739072","175943680","132665344","33312", ...
```

<span data-ttu-id="53149-118">コマンドレットでは、 `Get-Process` **process** オブジェクトを取得し、 **Name** パラメーターを使用して PowerShell プロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="53149-118">The `Get-Process` cmdlet gets the **Process** object and uses the **Name** parameter to specify the PowerShell process.</span></span> <span data-ttu-id="53149-119">プロセスオブジェクトは、パイプラインの下にコマンドレットに送信され `ConvertTo-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="53149-119">The process object is sent down the pipeline to the `ConvertTo-CSV` cmdlet.</span></span> <span data-ttu-id="53149-120">`ConvertTo-CSV`コマンドレットでは、オブジェクトを CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="53149-120">The `ConvertTo-CSV` cmdlet converts the object to CSV strings.</span></span> <span data-ttu-id="53149-121">**Notypeinformation** パラメーターは、CSV 出力から **#TYPE** 情報ヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="53149-121">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

### <span data-ttu-id="53149-122">例 2: DateTime オブジェクトを CSV に変換する</span><span class="sxs-lookup"><span data-stu-id="53149-122">Example 2: Convert a DateTime object to CSV</span></span>

<span data-ttu-id="53149-123">この例では、 **DateTime** オブジェクトを CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="53149-123">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

<span data-ttu-id="53149-124">`Get-Date`このコマンドレットは、 **DateTime** オブジェクトを取得し、変数に保存し `$Date` ます。</span><span class="sxs-lookup"><span data-stu-id="53149-124">The `Get-Date` cmdlet gets the **DateTime** object and saves it in the `$Date` variable.</span></span> <span data-ttu-id="53149-125">この `ConvertTo-Csv` コマンドレットは、 **DateTime** オブジェクトを文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="53149-125">The `ConvertTo-Csv` cmdlet converts the **DateTime** object to strings.</span></span> <span data-ttu-id="53149-126">**InputObject** パラメーターは、変数に格納されている **DateTime** オブジェクトを使用し `$Date` ます。</span><span class="sxs-lookup"><span data-stu-id="53149-126">The **InputObject** parameter uses the **DateTime** object stored in the `$Date` variable.</span></span> <span data-ttu-id="53149-127">**Delimiter** パラメーターでは、文字列値を区切るためのセミコロンを指定します。</span><span class="sxs-lookup"><span data-stu-id="53149-127">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="53149-128">**Notypeinformation** パラメーターは、CSV 出力から **#TYPE** 情報ヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="53149-128">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

### <span data-ttu-id="53149-129">例 3: PowerShell イベントログを CSV に変換する</span><span class="sxs-lookup"><span data-stu-id="53149-129">Example 3: Convert the PowerShell event log to CSV</span></span>

<span data-ttu-id="53149-130">この例では、PowerShell の Windows イベントログを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="53149-130">This example converts the Windows event log for PowerShell to a series of CSV strings.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'Windows PowerShell' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error","403",,"0","4","4",,"36028797018963968","46891","PowerShell", ...
```

<span data-ttu-id="53149-131">この `Get-Culture` コマンドレットは、入れ子になったプロパティの **TextInfo** と **listseparator** を使用し、現在のカルチャの既定のリスト区切り記号を表示します。</span><span class="sxs-lookup"><span data-stu-id="53149-131">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="53149-132">`Get-WinEvent`コマンドレットは、イベントログオブジェクトを取得し、 **LogName** パラメーターを使用してログファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="53149-132">The `Get-WinEvent` cmdlet gets the event log objects and uses the **LogName** parameter to specify the log file name.</span></span> <span data-ttu-id="53149-133">イベントログオブジェクトは、パイプラインを介してコマンドレットに送信され `ConvertTo-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="53149-133">The event log objects are sent down the pipeline to the `ConvertTo-Csv` cmdlet.</span></span> <span data-ttu-id="53149-134">`ConvertTo-Csv`コマンドレットは、イベントログオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="53149-134">The `ConvertTo-Csv` cmdlet converts the event log objects to a series of CSV strings.</span></span> <span data-ttu-id="53149-135">**UseCulture** パラメーターは、現在のカルチャの既定のリスト区切り記号を区切り記号として使用します。</span><span class="sxs-lookup"><span data-stu-id="53149-135">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="53149-136">**Notypeinformation** パラメーターは、CSV 出力から **#TYPE** 情報ヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="53149-136">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

## <span data-ttu-id="53149-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="53149-137">PARAMETERS</span></span>

### <span data-ttu-id="53149-138">-区切り記号</span><span class="sxs-lookup"><span data-stu-id="53149-138">-Delimiter</span></span>

<span data-ttu-id="53149-139">CSV 文字列内のプロパティ値を区切る区切り記号を指定します。</span><span class="sxs-lookup"><span data-stu-id="53149-139">Specifies the delimiter to separate the property values in CSV strings.</span></span> <span data-ttu-id="53149-140">既定値はコンマ ( `,` ) です。</span><span class="sxs-lookup"><span data-stu-id="53149-140">The default is a comma (`,`).</span></span> <span data-ttu-id="53149-141">コロン () などの文字を入力し `:` ます。</span><span class="sxs-lookup"><span data-stu-id="53149-141">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="53149-142">セミコロン () を指定するには、 `;` 単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="53149-142">To specify a semicolon (`;`) enclose it in single quotation marks.</span></span>

```yaml
Type: System.Char
Parameter Sets: Delimiter
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53149-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="53149-143">-InputObject</span></span>

<span data-ttu-id="53149-144">CSV 文字列に変換されるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="53149-144">Specifies the objects that are converted to CSV strings.</span></span> <span data-ttu-id="53149-145">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="53149-145">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="53149-146">パイプを使用してオブジェクトをにパイプ処理することもでき `ConvertTo-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="53149-146">You can also pipe objects to `ConvertTo-CSV`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="53149-147">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="53149-147">-NoTypeInformation</span></span>

<span data-ttu-id="53149-148">出力から **#TYPE** 情報ヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="53149-148">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="53149-149">このパラメーターは、PowerShell 6.0 の既定値になり、下位互換性のために用意されています。</span><span class="sxs-lookup"><span data-stu-id="53149-149">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NTI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53149-150">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="53149-150">-UseCulture</span></span>

<span data-ttu-id="53149-151">現在のカルチャの区切り記号を項目の区切り記号として使用します。</span><span class="sxs-lookup"><span data-stu-id="53149-151">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="53149-152">カルチャのリスト区切り記号を検索するには、コマンドを使用し `(Get-Culture).TextInfo.ListSeparator` ます。</span><span class="sxs-lookup"><span data-stu-id="53149-152">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseCulture
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53149-153">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="53149-153">CommonParameters</span></span>

<span data-ttu-id="53149-154">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="53149-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="53149-155">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53149-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="53149-156">入力</span><span class="sxs-lookup"><span data-stu-id="53149-156">INPUTS</span></span>

### <span data-ttu-id="53149-157">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="53149-157">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="53149-158">パイプを使用して、拡張型システム (実行) アダプターを持つ任意のオブジェクトをにパイプでき `ConvertTo-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="53149-158">You can pipe any object that has an Extended Type System (ETS) adapter to `ConvertTo-CSV`.</span></span>

## <span data-ttu-id="53149-159">出力</span><span class="sxs-lookup"><span data-stu-id="53149-159">OUTPUTS</span></span>

### <span data-ttu-id="53149-160">System.String</span><span class="sxs-lookup"><span data-stu-id="53149-160">System.String</span></span>

<span data-ttu-id="53149-161">CSV 出力は、文字列のコレクションとして返されます。</span><span class="sxs-lookup"><span data-stu-id="53149-161">The CSV output is returned as a collection of strings.</span></span>

## <span data-ttu-id="53149-162">注</span><span class="sxs-lookup"><span data-stu-id="53149-162">NOTES</span></span>

<span data-ttu-id="53149-163">CSV 形式では、各オブジェクトはそのプロパティ値のコンマ区切りリストで表されます。</span><span class="sxs-lookup"><span data-stu-id="53149-163">In CSV format, each object is represented by a comma-separated list of its property value.</span></span> <span data-ttu-id="53149-164">プロパティ値は、オブジェクトの **ToString ()** メソッドを使用して文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="53149-164">The property values are converted to strings using the object's **ToString()** method.</span></span> <span data-ttu-id="53149-165">文字列は、プロパティ値の名前で表されます。</span><span class="sxs-lookup"><span data-stu-id="53149-165">The strings are represented by the property value name.</span></span> <span data-ttu-id="53149-166">`ConvertTo-CSV` では、オブジェクトのメソッドはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="53149-166">`ConvertTo-CSV` does not export the object's methods.</span></span>

<span data-ttu-id="53149-167">CSV 文字列は次のように出力されます。</span><span class="sxs-lookup"><span data-stu-id="53149-167">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="53149-168">既定では、最初の文字列には **#TYPE** 情報ヘッダーの後にオブジェクトの種類の完全修飾名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="53149-168">By default the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span> <span data-ttu-id="53149-169">たとえば、 **#TYPE** のようにします。</span><span class="sxs-lookup"><span data-stu-id="53149-169">For example, **#TYPE System.Diagnostics.Process**.</span></span>
- <span data-ttu-id="53149-170">**Notypeinformation** が使用されている場合、最初の文字列には列ヘッダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="53149-170">If **NoTypeInformation** is used the first string includes the column headers.</span></span> <span data-ttu-id="53149-171">ヘッダーには、コンマ区切りのリストとして、最初のオブジェクトのプロパティ名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="53149-171">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="53149-172">残りの文字列には、各オブジェクトのプロパティ値のコンマ区切りのリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="53149-172">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="53149-173">複数のオブジェクトをに送信すると `ConvertTo-CSV` 、は、 `ConvertTo-CSV` 最初に送信したオブジェクトのプロパティに基づいて文字列を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="53149-173">When you submit multiple objects to `ConvertTo-CSV`, `ConvertTo-CSV` orders the strings based on the properties of the first object that you submit.</span></span> <span data-ttu-id="53149-174">残りのオブジェクトに指定されたプロパティのいずれかがない場合、そのオブジェクトのプロパティ値は、連続する2つのコンマで表される Null になります。</span><span class="sxs-lookup"><span data-stu-id="53149-174">If the remaining objects do not have one of the specified properties, the property value of that object is Null, as represented by two consecutive commas.</span></span> <span data-ttu-id="53149-175">残りのオブジェクトに追加のプロパティがある場合、これらのプロパティ値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="53149-175">If the remaining objects have additional properties, those property values are ignored.</span></span>

## <span data-ttu-id="53149-176">関連リンク</span><span class="sxs-lookup"><span data-stu-id="53149-176">RELATED LINKS</span></span>

[<span data-ttu-id="53149-177">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="53149-177">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="53149-178">エクスポート-Csv</span><span class="sxs-lookup"><span data-stu-id="53149-178">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="53149-179">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="53149-179">Import-Csv</span></span>](Import-Csv.md)
