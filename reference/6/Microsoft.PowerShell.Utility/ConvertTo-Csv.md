---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: 5de6a3bd28b850d3fc1632e26998986f302b78f8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216827"
---
# <span data-ttu-id="fdf1e-103">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="fdf1e-103">ConvertTo-Csv</span></span>

## <span data-ttu-id="fdf1e-104">概要</span><span class="sxs-lookup"><span data-stu-id="fdf1e-104">SYNOPSIS</span></span>
<span data-ttu-id="fdf1e-105">.NET オブジェクトを一連の文字区切り値 (CSV) 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-105">Converts .NET objects into a series of character-separated value (CSV) strings.</span></span>

## <span data-ttu-id="fdf1e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fdf1e-106">SYNTAX</span></span>

### <span data-ttu-id="fdf1e-107">デリミターパス (既定)</span><span class="sxs-lookup"><span data-stu-id="fdf1e-107">DelimiterPath (Default)</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [-IncludeTypeInformation] [-NoTypeInformation]
 [<CommonParameters>]
```

### <span data-ttu-id="fdf1e-108">区切り記号</span><span class="sxs-lookup"><span data-stu-id="fdf1e-108">Delimiter</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [<CommonParameters>]
```

### <span data-ttu-id="fdf1e-109">UseCulture</span><span class="sxs-lookup"><span data-stu-id="fdf1e-109">UseCulture</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [<CommonParameters>]
```

## <span data-ttu-id="fdf1e-110">Description</span><span class="sxs-lookup"><span data-stu-id="fdf1e-110">DESCRIPTION</span></span>

<span data-ttu-id="fdf1e-111">`ConvertTo-CSV`コマンドレットは、送信したオブジェクトを表す一連のコンマ区切り値 (CSV) 文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-111">The `ConvertTo-CSV` cmdlet returns a series of comma-separated value (CSV) strings that represent the objects that you submit.</span></span> <span data-ttu-id="fdf1e-112">その後、コマンドレットを使用して `ConvertFrom-Csv` 、CSV 文字列からオブジェクトを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-112">You can then use the `ConvertFrom-Csv` cmdlet to recreate objects from the CSV strings.</span></span> <span data-ttu-id="fdf1e-113">CSV から変換されたオブジェクトは、プロパティ値とメソッドを含まない元のオブジェクトの文字列値です。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-113">The objects converted from CSV are string values of the original objects that contain property values and no methods.</span></span>

<span data-ttu-id="fdf1e-114">コマンドレットを使用して、 `Export-Csv` オブジェクトを CSV 文字列に変換できます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-114">You can use the `Export-Csv` cmdlet to convert objects to CSV strings.</span></span> <span data-ttu-id="fdf1e-115">`Export-CSV` はと似てい `ConvertTo-CSV` ますが、CSV 文字列をファイルに保存する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-115">`Export-CSV` is similar to `ConvertTo-CSV`, except that it saves the CSV strings to a file.</span></span>

<span data-ttu-id="fdf1e-116">コマンドレットには、 `ConvertTo-CSV` コンマ以外の区切り記号を指定するパラメーターや、現在のカルチャを区切り記号として使用するパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-116">The `ConvertTo-CSV` cmdlet has parameters to specify a delimiter other than a comma or use the current culture as the delimiter.</span></span>

## <span data-ttu-id="fdf1e-117">例</span><span class="sxs-lookup"><span data-stu-id="fdf1e-117">EXAMPLES</span></span>

### <span data-ttu-id="fdf1e-118">例 1: オブジェクトを CSV に変換する</span><span class="sxs-lookup"><span data-stu-id="fdf1e-118">Example 1: Convert an object to CSV</span></span>

<span data-ttu-id="fdf1e-119">この例では、 **プロセス** オブジェクトを CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-119">This example converts a **Process** object to a CSV string.</span></span>

```powershell
Get-Process -Name pwsh | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"pwsh","8","950","2204001161216","100925440","59686912","67104", ...
```

<span data-ttu-id="fdf1e-120">コマンドレットでは、 `Get-Process` **process** オブジェクトを取得し、 **Name** パラメーターを使用して PowerShell プロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-120">The `Get-Process` cmdlet gets the **Process** object and uses the **Name** parameter to specify the PowerShell process.</span></span> <span data-ttu-id="fdf1e-121">プロセスオブジェクトは、パイプラインの下にコマンドレットに送信され `ConvertTo-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-121">The process object is sent down the pipeline to the `ConvertTo-CSV` cmdlet.</span></span> <span data-ttu-id="fdf1e-122">`ConvertTo-CSV`コマンドレットでは、オブジェクトを CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-122">The `ConvertTo-CSV` cmdlet converts the object to CSV strings.</span></span> <span data-ttu-id="fdf1e-123">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-123">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

### <span data-ttu-id="fdf1e-124">例 2: DateTime オブジェクトを CSV に変換する</span><span class="sxs-lookup"><span data-stu-id="fdf1e-124">Example 2: Convert a DateTime object to CSV</span></span>

<span data-ttu-id="fdf1e-125">この例では、 **DateTime** オブジェクトを CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-125">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

<span data-ttu-id="fdf1e-126">`Get-Date`このコマンドレットは、 **DateTime** オブジェクトを取得し、変数に保存し `$Date` ます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-126">The `Get-Date` cmdlet gets the **DateTime** object and saves it in the `$Date` variable.</span></span> <span data-ttu-id="fdf1e-127">この `ConvertTo-Csv` コマンドレットは、 **DateTime** オブジェクトを文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-127">The `ConvertTo-Csv` cmdlet converts the **DateTime** object to strings.</span></span> <span data-ttu-id="fdf1e-128">**InputObject** パラメーターは、変数に格納されている **DateTime** オブジェクトを使用し `$Date` ます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-128">The **InputObject** parameter uses the **DateTime** object stored in the `$Date` variable.</span></span> <span data-ttu-id="fdf1e-129">**Delimiter** パラメーターでは、文字列値を区切るためのセミコロンを指定します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-129">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="fdf1e-130">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-130">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

### <span data-ttu-id="fdf1e-131">例 3: PowerShell イベントログを CSV に変換する</span><span class="sxs-lookup"><span data-stu-id="fdf1e-131">Example 3: Convert the PowerShell event log to CSV</span></span>

<span data-ttu-id="fdf1e-132">この例では、PowerShell の Windows イベントログを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-132">This example converts the Windows event log for PowerShell to a series of CSV strings.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'PowerShellCore/Operational' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error""4100","1",,"3","106","19","0","31716","PowerShellCore", ...
```

<span data-ttu-id="fdf1e-133">この `Get-Culture` コマンドレットは、入れ子になったプロパティの **TextInfo** と **listseparator** を使用し、現在のカルチャの既定のリスト区切り記号を表示します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-133">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="fdf1e-134">`Get-WinEvent`コマンドレットは、イベントログオブジェクトを取得し、 **LogName** パラメーターを使用してログファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-134">The `Get-WinEvent` cmdlet gets the event log objects and uses the **LogName** parameter to specify the log file name.</span></span> <span data-ttu-id="fdf1e-135">イベントログオブジェクトは、パイプラインを介してコマンドレットに送信され `ConvertTo-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-135">The event log objects are sent down the pipeline to the `ConvertTo-Csv` cmdlet.</span></span> <span data-ttu-id="fdf1e-136">`ConvertTo-Csv`コマンドレットは、イベントログオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-136">The `ConvertTo-Csv` cmdlet converts the event log objects to a series of CSV strings.</span></span> <span data-ttu-id="fdf1e-137">**UseCulture** パラメーターは、現在のカルチャの既定のリスト区切り記号を区切り記号として使用します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-137">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="fdf1e-138">**Notypeinformation** パラメーターを指定すると、CSV 出力から **#TYPE** 情報ヘッダーが削除され、PowerShell 6 では不要になります。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-138">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

## <span data-ttu-id="fdf1e-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fdf1e-139">PARAMETERS</span></span>

### <span data-ttu-id="fdf1e-140">-区切り記号</span><span class="sxs-lookup"><span data-stu-id="fdf1e-140">-Delimiter</span></span>

<span data-ttu-id="fdf1e-141">CSV 文字列内のプロパティ値を区切る区切り記号を指定します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-141">Specifies the delimiter to separate the property values in CSV strings.</span></span> <span data-ttu-id="fdf1e-142">既定値はコンマ ( `,` ) です。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-142">The default is a comma (`,`).</span></span> <span data-ttu-id="fdf1e-143">コロン () などの文字を入力し `:` ます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-143">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="fdf1e-144">セミコロン () を指定するには、 `;` 単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-144">To specify a semicolon (`;`) enclose it in single quotation marks.</span></span>

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

### <span data-ttu-id="fdf1e-145">-IncludeTypeInformation</span><span class="sxs-lookup"><span data-stu-id="fdf1e-145">-IncludeTypeInformation</span></span>

<span data-ttu-id="fdf1e-146">このパラメーターを使用する場合、出力の最初の行には **#TYPE** が含まれ、その後にオブジェクト型の完全修飾名が続きます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-146">When this parameter is used the first line of the output contains **#TYPE** followed by the fully qualified name of the object type.</span></span> <span data-ttu-id="fdf1e-147">たとえば、 **#TYPE** のようにします。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-147">For example, **#TYPE System.Diagnostics.Process** .</span></span>

<span data-ttu-id="fdf1e-148">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-148">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ITI

Required: False
Position: Named
Default value: #TYPE <Object>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fdf1e-149">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fdf1e-149">-InputObject</span></span>

<span data-ttu-id="fdf1e-150">CSV 文字列に変換されるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-150">Specifies the objects that are converted to CSV strings.</span></span> <span data-ttu-id="fdf1e-151">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-151">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="fdf1e-152">パイプを使用してオブジェクトをにパイプ処理することもでき `ConvertTo-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-152">You can also pipe objects to `ConvertTo-CSV`.</span></span>

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

### <span data-ttu-id="fdf1e-153">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="fdf1e-153">-NoTypeInformation</span></span>

<span data-ttu-id="fdf1e-154">出力から **#TYPE** 情報ヘッダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-154">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="fdf1e-155">このパラメーターは、PowerShell 6.0 の既定値になり、下位互換性のために用意されています。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-155">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="fdf1e-156">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="fdf1e-156">-UseCulture</span></span>

<span data-ttu-id="fdf1e-157">現在のカルチャの区切り記号を項目の区切り記号として使用します。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-157">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="fdf1e-158">カルチャのリスト区切り記号を検索するには、コマンドを使用し `(Get-Culture).TextInfo.ListSeparator` ます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-158">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="fdf1e-159">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fdf1e-159">CommonParameters</span></span>

<span data-ttu-id="fdf1e-160">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-160">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fdf1e-161">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-161">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fdf1e-162">入力</span><span class="sxs-lookup"><span data-stu-id="fdf1e-162">INPUTS</span></span>

### <span data-ttu-id="fdf1e-163">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="fdf1e-163">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="fdf1e-164">パイプを使用して、拡張型システム (実行) アダプターを持つ任意のオブジェクトをにパイプでき `ConvertTo-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-164">You can pipe any object that has an Extended Type System (ETS) adapter to `ConvertTo-CSV`.</span></span>

## <span data-ttu-id="fdf1e-165">出力</span><span class="sxs-lookup"><span data-stu-id="fdf1e-165">OUTPUTS</span></span>

### <span data-ttu-id="fdf1e-166">System.String</span><span class="sxs-lookup"><span data-stu-id="fdf1e-166">System.String</span></span>

<span data-ttu-id="fdf1e-167">CSV 出力は、文字列のコレクションとして返されます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-167">The CSV output is returned as a collection of strings.</span></span>

## <span data-ttu-id="fdf1e-168">注</span><span class="sxs-lookup"><span data-stu-id="fdf1e-168">NOTES</span></span>

<span data-ttu-id="fdf1e-169">CSV 形式では、各オブジェクトはそのプロパティ値のコンマ区切りリストで表されます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-169">In CSV format, each object is represented by a comma-separated list of its property value.</span></span> <span data-ttu-id="fdf1e-170">プロパティ値は、オブジェクトの **ToString ()** メソッドを使用して文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-170">The property values are converted to strings using the object's **ToString()** method.</span></span> <span data-ttu-id="fdf1e-171">文字列は、プロパティ値の名前で表されます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-171">The strings are represented by the property value name.</span></span> <span data-ttu-id="fdf1e-172">`ConvertTo-CSV` では、オブジェクトのメソッドはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-172">`ConvertTo-CSV` does not export the object's methods.</span></span>

<span data-ttu-id="fdf1e-173">CSV 文字列は次のように出力されます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-173">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="fdf1e-174">**Includetypeinformation** を使用する場合、最初の文字列は **#TYPE** で構成され、その後にオブジェクト型の完全修飾名が続きます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-174">If **IncludeTypeInformation** is used, the first string consists of **#TYPE** followed by the object type's fully qualified name.</span></span> <span data-ttu-id="fdf1e-175">たとえば、 **#TYPE** のようにします。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-175">For example, **#TYPE System.Diagnostics.Process** .</span></span>
- <span data-ttu-id="fdf1e-176">**Includetypeinformation** が使用されていない場合、最初の文字列には列ヘッダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-176">If **IncludeTypeInformation** is not used the first string includes the column headers.</span></span> <span data-ttu-id="fdf1e-177">ヘッダーには、コンマ区切りのリストとして、最初のオブジェクトのプロパティ名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-177">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="fdf1e-178">残りの文字列には、各オブジェクトのプロパティ値のコンマ区切りのリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-178">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="fdf1e-179">PowerShell 6.0 以降では、の既定の動作で `ConvertTo-CSV` は、 **#TYPE** 情報が CSV に含められず、 **notypeinformation** が暗黙的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-179">Beginning with PowerShell 6.0 the default behavior of `ConvertTo-CSV` is to not include the **#TYPE** information in the CSV and **NoTypeInformation** is implied.</span></span> <span data-ttu-id="fdf1e-180">**Includetypeinformation** を使用して **#TYPE** 情報を含め、PowerShell 6.0 より前のの既定の動作をエミュレートすることができ `ConvertTo-CSV` ます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-180">**IncludeTypeInformation** can be used to include the **#TYPE** information and emulate the default behavior of `ConvertTo-CSV` prior to PowerShell 6.0.</span></span>

<span data-ttu-id="fdf1e-181">複数のオブジェクトをに送信すると `ConvertTo-CSV` 、は、 `ConvertTo-CSV` 最初に送信したオブジェクトのプロパティに基づいて文字列を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-181">When you submit multiple objects to `ConvertTo-CSV`, `ConvertTo-CSV` orders the strings based on the properties of the first object that you submit.</span></span> <span data-ttu-id="fdf1e-182">残りのオブジェクトに指定されたプロパティのいずれかがない場合、そのオブジェクトのプロパティ値は、連続する2つのコンマで表される Null になります。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-182">If the remaining objects do not have one of the specified properties, the property value of that object is Null, as represented by two consecutive commas.</span></span> <span data-ttu-id="fdf1e-183">残りのオブジェクトに追加のプロパティがある場合、これらのプロパティ値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="fdf1e-183">If the remaining objects have additional properties, those property values are ignored.</span></span>

## <span data-ttu-id="fdf1e-184">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fdf1e-184">RELATED LINKS</span></span>

[<span data-ttu-id="fdf1e-185">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="fdf1e-185">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="fdf1e-186">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="fdf1e-186">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="fdf1e-187">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="fdf1e-187">Import-Csv</span></span>](Import-Csv.md)
