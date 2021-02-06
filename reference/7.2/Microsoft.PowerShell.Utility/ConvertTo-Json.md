---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-json?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Json
ms.openlocfilehash: d598fe2b1aefdae046b0f1a0893bf4fc407fa7a7
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "99600594"
---
# <span data-ttu-id="d2434-102">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="d2434-102">ConvertTo-Json</span></span>

## <span data-ttu-id="d2434-103">概要</span><span class="sxs-lookup"><span data-stu-id="d2434-103">SYNOPSIS</span></span>
<span data-ttu-id="d2434-104">オブジェクトを JSON 形式の文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="d2434-104">Converts an object to a JSON-formatted string.</span></span>

## <span data-ttu-id="d2434-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d2434-105">SYNTAX</span></span>

```
ConvertTo-Json [-InputObject] <Object> [-Depth <Int32>] [-Compress]
[-EnumsAsStrings] [-AsArray] [-EscapeHandling <StringEscapeHandling>]
[<CommonParameters>]
```

## <span data-ttu-id="d2434-106">Description</span><span class="sxs-lookup"><span data-stu-id="d2434-106">DESCRIPTION</span></span>

<span data-ttu-id="d2434-107">`ConvertTo-Json`コマンドレットは、任意の .net オブジェクトを JavaScript Object Notation (JSON) 形式の文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="d2434-107">The `ConvertTo-Json` cmdlet converts any .NET object to a string in JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="d2434-108">プロパティはフィールド名に変換され、フィールドの値はプロパティの値に変換されます。メソッドは削除されます。</span><span class="sxs-lookup"><span data-stu-id="d2434-108">The properties are converted to field names, the field values are converted to property values, and the methods are removed.</span></span>

<span data-ttu-id="d2434-109">次に、コマンドレットを使用して、 `ConvertFrom-Json` json 形式の文字列を json オブジェクトに変換します。これは、PowerShell で簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="d2434-109">You can then use the `ConvertFrom-Json` cmdlet to convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell.</span></span>

<span data-ttu-id="d2434-110">多くの Web サイトが、サーバーと Web ベースのアプリ間の通信のために、XML ではなく JSON を使用してデータをシリアル化しています。</span><span class="sxs-lookup"><span data-stu-id="d2434-110">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="d2434-111">PowerShell 7.2 では、 `ConvertTo-Json` 入力オブジェクトの深さがコマンドに指定された深さを超えた場合に、によって警告が出力されます。</span><span class="sxs-lookup"><span data-stu-id="d2434-111">As of PowerShell 7.2, `ConvertTo-Json` emits a warning if the depth of the input object exceeds the depth specified for the command.</span></span> <span data-ttu-id="d2434-112">これにより、オブジェクトを変換するときに不要なデータ損失を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="d2434-112">This prevents unwanted data loss when converting objects.</span></span>

<span data-ttu-id="d2434-113">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d2434-113">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="d2434-114">例</span><span class="sxs-lookup"><span data-stu-id="d2434-114">EXAMPLES</span></span>

### <span data-ttu-id="d2434-115">例 1</span><span class="sxs-lookup"><span data-stu-id="d2434-115">Example 1</span></span>

```powershell
(Get-UICulture).Calendar | ConvertTo-Json
```

```Output
{
  "MinSupportedDateTime": "0001-01-01T00:00:00",
  "MaxSupportedDateTime": "9999-12-31T23:59:59.9999999",
  "AlgorithmType": 1,
  "CalendarType": 1,
  "Eras": [
    1
  ],
  "TwoDigitYearMax": 2029,
  "IsReadOnly": true
}
```

<span data-ttu-id="d2434-116">このコマンドは、コマンドレットを使用して、 `ConvertTo-Json` いる gregoriancalendar オブジェクトを JSON 形式の文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="d2434-116">This command uses the `ConvertTo-Json` cmdlet to convert a GregorianCalendar object to a JSON-formatted string.</span></span>

### <span data-ttu-id="d2434-117">例 2</span><span class="sxs-lookup"><span data-stu-id="d2434-117">Example 2</span></span>

```powershell
Get-Date | ConvertTo-Json; Get-Date | ConvertTo-Json -AsArray
```

```Output
{
  "value": "2018-10-12T23:07:18.8450248-05:00",
  "DisplayHint": 2,
  "DateTime": "October 12, 2018 11:07:18 PM"
}
[
  {
    "value": "2018-10-12T23:07:18.8480668-05:00",
    "DisplayHint": 2,
    "DateTime": "October 12, 2018 11:07:18 PM"
  }
]
```

<span data-ttu-id="d2434-118">この例は、 `ConvertTo-Json` **asarray** スイッチパラメーターを指定した場合と使用しない場合のコマンドレットからの出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="d2434-118">This example shows the output from `ConvertTo-Json` cmdlet with and without the **AsArray** switch parameter.</span></span> <span data-ttu-id="d2434-119">出力の2番目の部分が配列の角かっこで囲まれていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d2434-119">You can see the second portion of the output is wrapped in array brackets.</span></span>

### <span data-ttu-id="d2434-120">例 3</span><span class="sxs-lookup"><span data-stu-id="d2434-120">Example 3</span></span>

```powershell
@{Account="User01";Domain="Domain01";Admin="True"} | ConvertTo-Json -Compress
```

```Output
{"Domain":"Domain01","Account":"User01","Admin":"True"}
```

<span data-ttu-id="d2434-121">このコマンドは、の **Compress** パラメーターを使用した場合の効果を示し `ConvertTo-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="d2434-121">This command shows the effect of using the **Compress** parameter of `ConvertTo-Json`.</span></span> <span data-ttu-id="d2434-122">圧縮は、文字列の外観に影響を与えますが、有効性には影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="d2434-122">The compression affects only the appearance of the string, not its validity.</span></span>

### <span data-ttu-id="d2434-123">例 4</span><span class="sxs-lookup"><span data-stu-id="d2434-123">Example 4</span></span>

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json
```

```Output
{
  "DisplayHint": 2,
  "DateTime": "October 12, 2018 10:55:32 PM",
  "Date": "2018-10-12T00:00:00-05:00",
  "Day": 12,
  "DayOfWeek": 5,
  "DayOfYear": 285,
  "Hour": 22,
  "Kind": 2,
  "Millisecond": 639,
  "Minute": 55,
  "Month": 10,
  "Second": 32,
  "Ticks": 636749817326397744,
  "TimeOfDay": {
    "Ticks": 825326397744,
    "Days": 0,
    "Hours": 22,
    "Milliseconds": 639,
    "Minutes": 55,
    "Seconds": 32,
    "TotalDays": 0.95523888627777775,
    "TotalHours": 22.925733270666665,
    "TotalMilliseconds": 82532639.774400011,
    "TotalMinutes": 1375.54399624,
    "TotalSeconds": 82532.6397744
  },
  "Year": 2018
}
```

<span data-ttu-id="d2434-124">この例では、コマンドレットを使用して、 `ConvertTo-Json` system.string オブジェクト **を** `Get-Date` コマンドレットから JSON 形式の文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="d2434-124">This example uses the `ConvertTo-Json` cmdlet to convert a **System.DateTime** object from the `Get-Date` cmdlet to a JSON-formatted string.</span></span> <span data-ttu-id="d2434-125">このコマンドは、コマンドレットを使用して、 `Select-Object` `*` **DateTime** オブジェクトのすべてのプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="d2434-125">The command uses the `Select-Object` cmdlet to get all (`*`) of the properties of the **DateTime** object.</span></span> <span data-ttu-id="d2434-126">出力には、返された JSON 文字列が表示され `ConvertTo-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="d2434-126">The output shows the JSON string that `ConvertTo-Json` returned.</span></span>

### <span data-ttu-id="d2434-127">例 5</span><span class="sxs-lookup"><span data-stu-id="d2434-127">Example 5</span></span>

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json | ConvertFrom-Json
```

```Output
DisplayHint : 2
DateTime    : October 12, 2018 10:55:52 PM
Date        : 2018-10-12 12:00:00 AM
Day         : 12
DayOfWeek   : 5
DayOfYear   : 285
Hour        : 22
Kind        : 2
Millisecond : 768
Minute      : 55
Month       : 10
Second      : 52
Ticks       : 636749817527683372
TimeOfDay   : @{Ticks=825527683372; Days=0; Hours=22; Milliseconds=768; Minutes=55; Seconds=52;
              TotalDays=0.95547185575463; TotalHours=22.9313245381111; TotalMilliseconds=82552768.3372;
              TotalMinutes=1375.87947228667; TotalSeconds=82552.7683372}
Year        : 2018
```

<span data-ttu-id="d2434-128">この例では、 `ConvertTo-Json` コマンドレットとコマンドレットを使用して、 `ConvertFrom-Json` オブジェクトを json 文字列と json オブジェクトに変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d2434-128">This example shows how to use the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert an object to a JSON string and a JSON object.</span></span>

## <span data-ttu-id="d2434-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d2434-129">PARAMETERS</span></span>

### <span data-ttu-id="d2434-130">-AsArray</span><span class="sxs-lookup"><span data-stu-id="d2434-130">-AsArray</span></span>

<span data-ttu-id="d2434-131">入力が単一のオブジェクトであっても、配列の角かっこでオブジェクトを出力します。</span><span class="sxs-lookup"><span data-stu-id="d2434-131">Outputs the object in array brackets, even if the input is a single object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d2434-132">-圧縮</span><span class="sxs-lookup"><span data-stu-id="d2434-132">-Compress</span></span>

<span data-ttu-id="d2434-133">出力文字列内の空白文字とインデントが設定された書式設定は省略されます。</span><span class="sxs-lookup"><span data-stu-id="d2434-133">Omits white space and indented formatting in the output string.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d2434-134">-深さ</span><span class="sxs-lookup"><span data-stu-id="d2434-134">-Depth</span></span>

<span data-ttu-id="d2434-135">JSON 表現に含める子オブジェクトのレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d2434-135">Specifies how many levels of contained objects are included in the JSON representation.</span></span> <span data-ttu-id="d2434-136">既定値は 2 です。</span><span class="sxs-lookup"><span data-stu-id="d2434-136">The default value is 2.</span></span> <span data-ttu-id="d2434-137">PowerShell 7.2 では、 `ConvertTo-Json` 入力オブジェクトのレベル数がこの数値を超えた場合に、によって警告が出力されます。</span><span class="sxs-lookup"><span data-stu-id="d2434-137">As of PowerShell 7.2, `ConvertTo-Json` emits a warning if the number of levels in an input object exceeds this number.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d2434-138">-EnumsAsStrings</span><span class="sxs-lookup"><span data-stu-id="d2434-138">-EnumsAsStrings</span></span>

<span data-ttu-id="d2434-139">すべての列挙を文字列形式に変換する代替シリアル化オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="d2434-139">Provides an alternative serialization option that converts all enumerations to their string representation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d2434-140">-EscapeHandling</span><span class="sxs-lookup"><span data-stu-id="d2434-140">-EscapeHandling</span></span>

<span data-ttu-id="d2434-141">結果の JSON 出力で特定の文字をエスケープする方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="d2434-141">Controls how certain characters are escaped in the resulting JSON output.</span></span> <span data-ttu-id="d2434-142">既定では、制御文字 (改行など) のみがエスケープされます。</span><span class="sxs-lookup"><span data-stu-id="d2434-142">By default, only control characters (like newline) are escaped.</span></span>

<span data-ttu-id="d2434-143">使用可能な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d2434-143">Acceptable values are:</span></span>

- <span data-ttu-id="d2434-144">既定の制御文字はエスケープされます。</span><span class="sxs-lookup"><span data-stu-id="d2434-144">Default - Only control characters are escaped.</span></span>
- <span data-ttu-id="d2434-145">EscapeNonAscii-すべての非 ASCII および制御文字がエスケープされます。</span><span class="sxs-lookup"><span data-stu-id="d2434-145">EscapeNonAscii - All non-ASCII and control characters are escaped.</span></span>
- <span data-ttu-id="d2434-146">EscapeHtml-HTML ( `<` 、、、 `>` `&` `'` 、 `"` ) および制御文字はエスケープされます。</span><span class="sxs-lookup"><span data-stu-id="d2434-146">EscapeHtml - HTML (`<`, `>`, `&`, `'`, `"`) and control characters are escaped.</span></span>

<span data-ttu-id="d2434-147">このパラメーターは、PowerShell 6.2 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d2434-147">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: Newtonsoft.Json.StringEscapeHandling
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d2434-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d2434-148">-InputObject</span></span>

<span data-ttu-id="d2434-149">JSON 形式に変換するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d2434-149">Specifies the objects to convert to JSON format.</span></span> <span data-ttu-id="d2434-150">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="d2434-150">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="d2434-151">パイプを使用してオブジェクトをにパイプすることもでき `ConvertTo-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="d2434-151">You can also pipe an object to `ConvertTo-Json`.</span></span>

<span data-ttu-id="d2434-152">**InputObject** パラメーターは必須ですが、その値は null ( `$null` ) または空の文字列にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d2434-152">The **InputObject** parameter is required, but its value can be null (`$null`) or an empty string.</span></span>
<span data-ttu-id="d2434-153">入力オブジェクトがの場合 `$null` 、 `ConvertTo-Json` は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="d2434-153">When the input object is `$null`, `ConvertTo-Json` does not generate any output.</span></span> <span data-ttu-id="d2434-154">入力オブジェクトが空の文字列の場合、は `ConvertTo-Json` 空の文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="d2434-154">When the input object is an empty string, `ConvertTo-Json` returns an empty string.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d2434-155">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d2434-155">CommonParameters</span></span>

<span data-ttu-id="d2434-156">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d2434-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d2434-157">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2434-157">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d2434-158">入力</span><span class="sxs-lookup"><span data-stu-id="d2434-158">INPUTS</span></span>

### <span data-ttu-id="d2434-159">System.Object</span><span class="sxs-lookup"><span data-stu-id="d2434-159">System.Object</span></span>

<span data-ttu-id="d2434-160">パイプを使用して任意のオブジェクトをにパイプすることができ `ConvertTo-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="d2434-160">You can pipe any object to `ConvertTo-Json`.</span></span>

## <span data-ttu-id="d2434-161">出力</span><span class="sxs-lookup"><span data-stu-id="d2434-161">OUTPUTS</span></span>

### <span data-ttu-id="d2434-162">System.String</span><span class="sxs-lookup"><span data-stu-id="d2434-162">System.String</span></span>

## <span data-ttu-id="d2434-163">注</span><span class="sxs-lookup"><span data-stu-id="d2434-163">NOTES</span></span>

<span data-ttu-id="d2434-164">`ConvertTo-Json`コマンドレットは[Newtonsoft Json.NET](https://www.newtonsoft.com/json)を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="d2434-164">The `ConvertTo-Json` cmdlet is implemented using [Newtonsoft Json.NET](https://www.newtonsoft.com/json).</span></span>

## <span data-ttu-id="d2434-165">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d2434-165">RELATED LINKS</span></span>

<span data-ttu-id="d2434-166">[JavaScript および .NET での JavaScript Object Notation (JSON) の概要](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="d2434-166">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="d2434-167">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="d2434-167">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="d2434-168">Get-Content</span><span class="sxs-lookup"><span data-stu-id="d2434-168">Get-Content</span></span>](../Microsoft.PowerShell.Management/Get-Content.md)

[<span data-ttu-id="d2434-169">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="d2434-169">Get-UICulture</span></span>](Get-UICulture.md)

[<span data-ttu-id="d2434-170">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="d2434-170">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="d2434-171">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="d2434-171">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="d2434-172">NewtonSoft.Jsします。StringEscapeHandling</span><span class="sxs-lookup"><span data-stu-id="d2434-172">NewtonSoft.Json.StringEscapeHandling</span></span>](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm)
