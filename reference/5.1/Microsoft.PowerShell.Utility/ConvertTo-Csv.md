---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: 7d399661e4514c0a39ad00601d554c41c2897ff9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214136"
---
# <span data-ttu-id="c98da-103">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="c98da-103">ConvertTo-Csv</span></span>

## <span data-ttu-id="c98da-104">概要</span><span class="sxs-lookup"><span data-stu-id="c98da-104">SYNOPSIS</span></span>
<span data-ttu-id="c98da-105">.NET オブジェクトを一連のコンマ区切り値 (CSV) 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="c98da-105">Converts .NET objects into a series of comma-separated value (CSV) strings.</span></span>

## <span data-ttu-id="c98da-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c98da-106">SYNTAX</span></span>

### <span data-ttu-id="c98da-107">区切り記号 (既定値)</span><span class="sxs-lookup"><span data-stu-id="c98da-107">Delimiter (Default)</span></span>

```
ConvertTo-Csv [-InputObject] <psobject> [[-Delimiter] <char>] [-NoTypeInformation]
 [<CommonParameters>]
```

### <span data-ttu-id="c98da-108">UseCulture</span><span class="sxs-lookup"><span data-stu-id="c98da-108">UseCulture</span></span>

```
ConvertTo-Csv [-InputObject] <psobject> [-UseCulture] [-NoTypeInformation] [<CommonParameters>]
```

## <span data-ttu-id="c98da-109">Description</span><span class="sxs-lookup"><span data-stu-id="c98da-109">DESCRIPTION</span></span>

<span data-ttu-id="c98da-110">`ConvertTo-CSV`コマンドレットは、送信したオブジェクトを表す一連のコンマ区切り値 (CSV) 文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="c98da-110">The `ConvertTo-CSV` cmdlet returns a series of comma-separated value (CSV) strings that represent the objects that you submit.</span></span> <span data-ttu-id="c98da-111">その後、コマンドレットを使用して `ConvertFrom-Csv` 、CSV 文字列からオブジェクトを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="c98da-111">You can then use the `ConvertFrom-Csv` cmdlet to recreate objects from the CSV strings.</span></span> <span data-ttu-id="c98da-112">CSV から変換されたオブジェクトは、プロパティ値とメソッドを含まない元のオブジェクトの文字列値です。</span><span class="sxs-lookup"><span data-stu-id="c98da-112">The objects converted from CSV are string values of the original objects that contain property values and no methods.</span></span>

<span data-ttu-id="c98da-113">コマンドレットを使用して、 `Export-Csv` オブジェクトを CSV 文字列に変換できます。</span><span class="sxs-lookup"><span data-stu-id="c98da-113">You can use the `Export-Csv` cmdlet to convert objects to CSV strings.</span></span> <span data-ttu-id="c98da-114">`Export-CSV` はと似てい `ConvertTo-CSV` ますが、CSV 文字列をファイルに保存する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="c98da-114">`Export-CSV` is similar to `ConvertTo-CSV`, except that it saves the CSV strings to a file.</span></span>

<span data-ttu-id="c98da-115">コマンドレットには、 `ConvertTo-CSV` コンマ以外の区切り記号を指定するパラメーターや、現在のカルチャを区切り記号として使用するパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="c98da-115">The `ConvertTo-CSV` cmdlet has parameters to specify a delimiter other than a comma or use the current culture as the delimiter.</span></span>

## <span data-ttu-id="c98da-116">例</span><span class="sxs-lookup"><span data-stu-id="c98da-116">EXAMPLES</span></span>

### <span data-ttu-id="c98da-117">例 1: オブジェクトを CSV に変換する</span><span class="sxs-lookup"><span data-stu-id="c98da-117">Example 1: Convert an object to CSV</span></span>

<span data-ttu-id="c98da-118">この例では、 **プロセス** オブジェクトを CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="c98da-118">This example converts a **Process** object to a CSV string.</span></span>

```powershell
Get-Process -Name 'PowerShell' | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"powershell","11","691","2204036739072","175943680","132665344","33312", ...
```

<span data-ttu-id="c98da-119">コマンドレットでは、 `Get-Process` **process** オブジェクトを取得し、 **Name** パラメーターを使用して PowerShell プロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c98da-119">The `Get-Process` cmdlet gets the **Process** object and uses the **Name** parameter to specify the PowerShell process.</span></span> <span data-ttu-id="c98da-120">プロセスオブジェクトは、パイプラインの下にコマンドレットに送信され `ConvertTo-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="c98da-120">The process object is sent down the pipeline to the `ConvertTo-CSV` cmdlet.</span></span> <span data-ttu-id="c98da-121">`ConvertTo-CSV`コマンドレットでは、オブジェクトを CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="c98da-121">The `ConvertTo-CSV` cmdlet converts the object to CSV strings.</span></span> <span data-ttu-id="c98da-122">**Notypeinformation** パラメーターは、CSV 出力から **#TYPE** 情報ヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c98da-122">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

### <span data-ttu-id="c98da-123">例 2: DateTime オブジェクトを CSV に変換する</span><span class="sxs-lookup"><span data-stu-id="c98da-123">Example 2: Convert a DateTime object to CSV</span></span>

<span data-ttu-id="c98da-124">この例では、 **DateTime** オブジェクトを CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="c98da-124">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

<span data-ttu-id="c98da-125">`Get-Date`このコマンドレットは、 **DateTime** オブジェクトを取得し、変数に保存し `$Date` ます。</span><span class="sxs-lookup"><span data-stu-id="c98da-125">The `Get-Date` cmdlet gets the **DateTime** object and saves it in the `$Date` variable.</span></span> <span data-ttu-id="c98da-126">この `ConvertTo-Csv` コマンドレットは、 **DateTime** オブジェクトを文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="c98da-126">The `ConvertTo-Csv` cmdlet converts the **DateTime** object to strings.</span></span> <span data-ttu-id="c98da-127">**InputObject** パラメーターは、変数に格納されている **DateTime** オブジェクトを使用し `$Date` ます。</span><span class="sxs-lookup"><span data-stu-id="c98da-127">The **InputObject** parameter uses the **DateTime** object stored in the `$Date` variable.</span></span> <span data-ttu-id="c98da-128">**Delimiter** パラメーターでは、文字列値を区切るためのセミコロンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c98da-128">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="c98da-129">**Notypeinformation** パラメーターは、CSV 出力から **#TYPE** 情報ヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c98da-129">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

### <span data-ttu-id="c98da-130">例 3: PowerShell イベントログを CSV に変換する</span><span class="sxs-lookup"><span data-stu-id="c98da-130">Example 3: Convert the PowerShell event log to CSV</span></span>

<span data-ttu-id="c98da-131">この例では、PowerShell の Windows イベントログを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="c98da-131">This example converts the Windows event log for PowerShell to a series of CSV strings.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'Windows PowerShell' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error","403",,"0","4","4",,"36028797018963968","46891","PowerShell", ...
```

<span data-ttu-id="c98da-132">この `Get-Culture` コマンドレットは、入れ子になったプロパティの **TextInfo** と **listseparator** を使用し、現在のカルチャの既定のリスト区切り記号を表示します。</span><span class="sxs-lookup"><span data-stu-id="c98da-132">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="c98da-133">`Get-WinEvent`コマンドレットは、イベントログオブジェクトを取得し、 **LogName** パラメーターを使用してログファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="c98da-133">The `Get-WinEvent` cmdlet gets the event log objects and uses the **LogName** parameter to specify the log file name.</span></span> <span data-ttu-id="c98da-134">イベントログオブジェクトは、パイプラインを介してコマンドレットに送信され `ConvertTo-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="c98da-134">The event log objects are sent down the pipeline to the `ConvertTo-Csv` cmdlet.</span></span> <span data-ttu-id="c98da-135">`ConvertTo-Csv`コマンドレットは、イベントログオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="c98da-135">The `ConvertTo-Csv` cmdlet converts the event log objects to a series of CSV strings.</span></span> <span data-ttu-id="c98da-136">**UseCulture** パラメーターは、現在のカルチャの既定のリスト区切り記号を区切り記号として使用します。</span><span class="sxs-lookup"><span data-stu-id="c98da-136">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="c98da-137">**Notypeinformation** パラメーターは、CSV 出力から **#TYPE** 情報ヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c98da-137">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

## <span data-ttu-id="c98da-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c98da-138">PARAMETERS</span></span>

### <span data-ttu-id="c98da-139">-区切り記号</span><span class="sxs-lookup"><span data-stu-id="c98da-139">-Delimiter</span></span>

<span data-ttu-id="c98da-140">CSV 文字列内のプロパティ値を区切る区切り記号を指定します。</span><span class="sxs-lookup"><span data-stu-id="c98da-140">Specifies the delimiter to separate the property values in CSV strings.</span></span> <span data-ttu-id="c98da-141">既定値はコンマ ( `,` ) です。</span><span class="sxs-lookup"><span data-stu-id="c98da-141">The default is a comma (`,`).</span></span> <span data-ttu-id="c98da-142">コロン () などの文字を入力し `:` ます。</span><span class="sxs-lookup"><span data-stu-id="c98da-142">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="c98da-143">セミコロン () を指定するには、 `;` 単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c98da-143">To specify a semicolon (`;`) enclose it in single quotation marks.</span></span>

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

### <span data-ttu-id="c98da-144">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c98da-144">-InputObject</span></span>

<span data-ttu-id="c98da-145">CSV 文字列に変換されるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c98da-145">Specifies the objects that are converted to CSV strings.</span></span> <span data-ttu-id="c98da-146">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="c98da-146">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="c98da-147">パイプを使用してオブジェクトをにパイプ処理することもでき `ConvertTo-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="c98da-147">You can also pipe objects to `ConvertTo-CSV`.</span></span>

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

### <span data-ttu-id="c98da-148">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="c98da-148">-NoTypeInformation</span></span>

<span data-ttu-id="c98da-149">出力から **#TYPE** 情報ヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c98da-149">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="c98da-150">このパラメーターは、PowerShell 6.0 の既定値になり、下位互換性のために用意されています。</span><span class="sxs-lookup"><span data-stu-id="c98da-150">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="c98da-151">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="c98da-151">-UseCulture</span></span>

<span data-ttu-id="c98da-152">現在のカルチャの区切り記号を項目の区切り記号として使用します。</span><span class="sxs-lookup"><span data-stu-id="c98da-152">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="c98da-153">カルチャのリスト区切り記号を検索するには、コマンドを使用し `(Get-Culture).TextInfo.ListSeparator` ます。</span><span class="sxs-lookup"><span data-stu-id="c98da-153">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="c98da-154">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c98da-154">CommonParameters</span></span>

<span data-ttu-id="c98da-155">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c98da-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c98da-156">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c98da-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c98da-157">入力</span><span class="sxs-lookup"><span data-stu-id="c98da-157">INPUTS</span></span>

### <span data-ttu-id="c98da-158">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="c98da-158">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="c98da-159">パイプを使用して、拡張型システム (実行) アダプターを持つ任意のオブジェクトをにパイプでき `ConvertTo-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="c98da-159">You can pipe any object that has an Extended Type System (ETS) adapter to `ConvertTo-CSV`.</span></span>

## <span data-ttu-id="c98da-160">出力</span><span class="sxs-lookup"><span data-stu-id="c98da-160">OUTPUTS</span></span>

### <span data-ttu-id="c98da-161">System.String</span><span class="sxs-lookup"><span data-stu-id="c98da-161">System.String</span></span>

<span data-ttu-id="c98da-162">CSV 出力は、文字列のコレクションとして返されます。</span><span class="sxs-lookup"><span data-stu-id="c98da-162">The CSV output is returned as a collection of strings.</span></span>

## <span data-ttu-id="c98da-163">注</span><span class="sxs-lookup"><span data-stu-id="c98da-163">NOTES</span></span>

<span data-ttu-id="c98da-164">CSV 形式では、各オブジェクトはそのプロパティ値のコンマ区切りリストで表されます。</span><span class="sxs-lookup"><span data-stu-id="c98da-164">In CSV format, each object is represented by a comma-separated list of its property value.</span></span> <span data-ttu-id="c98da-165">プロパティ値は、オブジェクトの **ToString ()** メソッドを使用して文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="c98da-165">The property values are converted to strings using the object's **ToString()** method.</span></span> <span data-ttu-id="c98da-166">文字列は、プロパティ値の名前で表されます。</span><span class="sxs-lookup"><span data-stu-id="c98da-166">The strings are represented by the property value name.</span></span> <span data-ttu-id="c98da-167">`ConvertTo-CSV` では、オブジェクトのメソッドはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="c98da-167">`ConvertTo-CSV` does not export the object's methods.</span></span>

<span data-ttu-id="c98da-168">CSV 文字列は次のように出力されます。</span><span class="sxs-lookup"><span data-stu-id="c98da-168">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="c98da-169">既定では、最初の文字列には **#TYPE** 情報ヘッダーの後にオブジェクトの種類の完全修飾名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c98da-169">By default the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span> <span data-ttu-id="c98da-170">たとえば、 **#TYPE** のようにします。</span><span class="sxs-lookup"><span data-stu-id="c98da-170">For example, **#TYPE System.Diagnostics.Process** .</span></span>
- <span data-ttu-id="c98da-171">**Notypeinformation** が使用されている場合、最初の文字列には列ヘッダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c98da-171">If **NoTypeInformation** is used the first string includes the column headers.</span></span> <span data-ttu-id="c98da-172">ヘッダーには、コンマ区切りのリストとして、最初のオブジェクトのプロパティ名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c98da-172">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="c98da-173">残りの文字列には、各オブジェクトのプロパティ値のコンマ区切りのリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c98da-173">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="c98da-174">複数のオブジェクトをに送信すると `ConvertTo-CSV` 、は、 `ConvertTo-CSV` 最初に送信したオブジェクトのプロパティに基づいて文字列を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="c98da-174">When you submit multiple objects to `ConvertTo-CSV`, `ConvertTo-CSV` orders the strings based on the properties of the first object that you submit.</span></span> <span data-ttu-id="c98da-175">残りのオブジェクトに指定されたプロパティのいずれかがない場合、そのオブジェクトのプロパティ値は、連続する2つのコンマで表される Null になります。</span><span class="sxs-lookup"><span data-stu-id="c98da-175">If the remaining objects do not have one of the specified properties, the property value of that object is Null, as represented by two consecutive commas.</span></span> <span data-ttu-id="c98da-176">残りのオブジェクトに追加のプロパティがある場合、これらのプロパティ値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="c98da-176">If the remaining objects have additional properties, those property values are ignored.</span></span>

## <span data-ttu-id="c98da-177">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c98da-177">RELATED LINKS</span></span>

[<span data-ttu-id="c98da-178">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="c98da-178">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="c98da-179">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="c98da-179">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="c98da-180">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="c98da-180">Import-Csv</span></span>](Import-Csv.md)
