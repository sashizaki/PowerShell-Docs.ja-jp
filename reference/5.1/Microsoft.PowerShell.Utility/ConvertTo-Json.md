---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-json?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Json
ms.openlocfilehash: 9831249a9f1ffcc65fc275e44da04fde9348ae71
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388061"
---
# <span data-ttu-id="5f05e-103">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="5f05e-103">ConvertTo-Json</span></span>

## <span data-ttu-id="5f05e-104">概要</span><span class="sxs-lookup"><span data-stu-id="5f05e-104">SYNOPSIS</span></span>
<span data-ttu-id="5f05e-105">オブジェクトを JSON 形式の文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5f05e-105">Converts an object to a JSON-formatted string.</span></span>

## <span data-ttu-id="5f05e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5f05e-106">SYNTAX</span></span>

```
ConvertTo-Json [-InputObject] <Object> [-Depth <Int32>] [-Compress]
 [<CommonParameters>]
```

## <span data-ttu-id="5f05e-107">Description</span><span class="sxs-lookup"><span data-stu-id="5f05e-107">DESCRIPTION</span></span>

<span data-ttu-id="5f05e-108">`ConvertTo-Json`コマンドレットは、任意の .net オブジェクトを JavaScript Object Notation (JSON) 形式の文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5f05e-108">The `ConvertTo-Json` cmdlet converts any .NET object to a string in JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="5f05e-109">プロパティはフィールド名に変換され、フィールドの値はプロパティの値に変換されます。メソッドは削除されます。</span><span class="sxs-lookup"><span data-stu-id="5f05e-109">The properties are converted to field names, the field values are converted to property values, and the methods are removed.</span></span>

<span data-ttu-id="5f05e-110">次に、コマンドレットを使用して、 `ConvertFrom-Json` json 形式の文字列を json オブジェクトに変換します。これは、PowerShell で簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="5f05e-110">You can then use the `ConvertFrom-Json` cmdlet to convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell.</span></span>

<span data-ttu-id="5f05e-111">多くの Web サイトが、サーバーと Web ベースのアプリ間の通信のために、XML ではなく JSON を使用してデータをシリアル化しています。</span><span class="sxs-lookup"><span data-stu-id="5f05e-111">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="5f05e-112">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5f05e-112">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="5f05e-113">例</span><span class="sxs-lookup"><span data-stu-id="5f05e-113">EXAMPLES</span></span>

### <span data-ttu-id="5f05e-114">例 1</span><span class="sxs-lookup"><span data-stu-id="5f05e-114">Example 1</span></span>

```powershell
(Get-UICulture).Calendar | ConvertTo-Json
```

```Output
{
    "MinSupportedDateTime":  "\/Date(-62135596800000)\/",
    "MaxSupportedDateTime":  "\/Date(253402300799999)\/",
    "AlgorithmType":  1,
    "CalendarType":  1,
    "Eras":  [
                 1
             ],
    "TwoDigitYearMax":  2029,
    "IsReadOnly":  false
}
```

<span data-ttu-id="5f05e-115">このコマンドは、コマンドレットを使用して、 `ConvertTo-Json` いる gregoriancalendar オブジェクトを JSON 形式の文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5f05e-115">This command uses the `ConvertTo-Json` cmdlet to convert a GregorianCalendar object to a JSON-formatted string.</span></span>

### <span data-ttu-id="5f05e-116">例 2</span><span class="sxs-lookup"><span data-stu-id="5f05e-116">Example 2</span></span>

```powershell
@{Account="User01";Domain="Domain01";Admin="True"} | ConvertTo-Json -Compress
```

```Output
{"Domain":"Domain01","Account":"User01","Admin":"True"}
```

<span data-ttu-id="5f05e-117">このコマンドは、の **Compress** パラメーターを使用した場合の効果を示し `ConvertTo-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="5f05e-117">This command shows the effect of using the **Compress** parameter of `ConvertTo-Json`.</span></span> <span data-ttu-id="5f05e-118">圧縮は、文字列の外観に影響を与えますが、有効性には影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="5f05e-118">The compression affects only the appearance of the string, not its validity.</span></span>

### <span data-ttu-id="5f05e-119">例 3</span><span class="sxs-lookup"><span data-stu-id="5f05e-119">Example 3</span></span>

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json
```

```Output
{
    "DisplayHint":  2,
    "DateTime":  "Friday, January 13, 2012 8:06:16 PM",
    "Date":  "\/Date(1326441600000)\/",
    "Day":  13,
    "DayOfWeek":  5,
    "DayOfYear":  13,
    "Hour":  20,
    "Kind":  2,
    "Millisecond":  221,
    "Minute":  6,
    "Month":  1,
    "Second":  16,
    "Ticks":  634620819762218083,
    "TimeOfDay":  {
                      "Ticks":  723762218083,
                      "Days":  0,
                      "Hours":  20,
                      "Milliseconds":  221,
                      "Minutes":  6,
                      "Seconds":  16,
                      "TotalDays":  0.83768775241087956,
                      "TotalHours":  20.104506057861109,
                      "TotalMilliseconds":  72376221.8083,
                      "TotalMinutes":  1206.2703634716668,
                      "TotalSeconds":  72376.22180829999
                  },
    "Year":  2012
}
```

<span data-ttu-id="5f05e-120">この例では、コマンドレットを使用して、 `ConvertTo-Json` system.string オブジェクト **を** `Get-Date` コマンドレットから JSON 形式の文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="5f05e-120">This example uses the `ConvertTo-Json` cmdlet to convert a **System.DateTime** object from the `Get-Date` cmdlet to a JSON-formatted string.</span></span> <span data-ttu-id="5f05e-121">このコマンドは、コマンドレットを使用して、 `Select-Object` `*` **DateTime** オブジェクトのすべてのプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="5f05e-121">The command uses the `Select-Object` cmdlet to get all (`*`) of the properties of the **DateTime** object.</span></span> <span data-ttu-id="5f05e-122">出力には、返された JSON 文字列が表示され `ConvertTo-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="5f05e-122">The output shows the JSON string that `ConvertTo-Json` returned.</span></span>

### <span data-ttu-id="5f05e-123">例 4</span><span class="sxs-lookup"><span data-stu-id="5f05e-123">Example 4</span></span>

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

<span data-ttu-id="5f05e-124">この例では、 `ConvertTo-Json` コマンドレットとコマンドレットを使用して、 `ConvertFrom-Json` オブジェクトを json 文字列と json オブジェクトに変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5f05e-124">This example shows how to use the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert an object to a JSON string and a JSON object.</span></span>

## <span data-ttu-id="5f05e-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5f05e-125">PARAMETERS</span></span>

### <span data-ttu-id="5f05e-126">-圧縮</span><span class="sxs-lookup"><span data-stu-id="5f05e-126">-Compress</span></span>

<span data-ttu-id="5f05e-127">出力文字列内の空白文字とインデントが設定された書式設定は省略されます。</span><span class="sxs-lookup"><span data-stu-id="5f05e-127">Omits white space and indented formatting in the output string.</span></span>

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

### <span data-ttu-id="5f05e-128">-深さ</span><span class="sxs-lookup"><span data-stu-id="5f05e-128">-Depth</span></span>

<span data-ttu-id="5f05e-129">JSON 表現に含める子オブジェクトのレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="5f05e-129">Specifies how many levels of contained objects are included in the JSON representation.</span></span> <span data-ttu-id="5f05e-130">既定値は 2 です。</span><span class="sxs-lookup"><span data-stu-id="5f05e-130">The default value is 2.</span></span>

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

### <span data-ttu-id="5f05e-131">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5f05e-131">-InputObject</span></span>

<span data-ttu-id="5f05e-132">JSON 形式に変換するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="5f05e-132">Specifies the objects to convert to JSON format.</span></span> <span data-ttu-id="5f05e-133">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f05e-133">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="5f05e-134">パイプを使用してオブジェクトをにパイプすることもでき `ConvertTo-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="5f05e-134">You can also pipe an object to `ConvertTo-Json`.</span></span>

<span data-ttu-id="5f05e-135">**InputObject** パラメーターは必須ですが、その値は null ( `$null` ) または空の文字列にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5f05e-135">The **InputObject** parameter is required, but its value can be null (`$null`) or an empty string.</span></span>
<span data-ttu-id="5f05e-136">入力オブジェクトがの場合 `$null` 、 `ConvertTo-Json` は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="5f05e-136">When the input object is `$null`, `ConvertTo-Json` does not generate any output.</span></span> <span data-ttu-id="5f05e-137">入力オブジェクトが空の文字列の場合、は `ConvertTo-Json` 空の文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="5f05e-137">When the input object is an empty string, `ConvertTo-Json` returns an empty string.</span></span>

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

### <span data-ttu-id="5f05e-138">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5f05e-138">CommonParameters</span></span>

<span data-ttu-id="5f05e-139">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5f05e-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5f05e-140">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f05e-140">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="5f05e-141">入力</span><span class="sxs-lookup"><span data-stu-id="5f05e-141">INPUTS</span></span>

### <span data-ttu-id="5f05e-142">System.Object</span><span class="sxs-lookup"><span data-stu-id="5f05e-142">System.Object</span></span>

<span data-ttu-id="5f05e-143">パイプを使用して任意のオブジェクトをにパイプすることができ `ConvertTo-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="5f05e-143">You can pipe any object to `ConvertTo-Json`.</span></span>

## <span data-ttu-id="5f05e-144">出力</span><span class="sxs-lookup"><span data-stu-id="5f05e-144">OUTPUTS</span></span>

### <span data-ttu-id="5f05e-145">System.String</span><span class="sxs-lookup"><span data-stu-id="5f05e-145">System.String</span></span>

## <span data-ttu-id="5f05e-146">注</span><span class="sxs-lookup"><span data-stu-id="5f05e-146">NOTES</span></span>

<span data-ttu-id="5f05e-147">`ConvertTo-Json`コマンドレットは、 [JavaScriptSerializer クラス](/dotnet/api/system.web.script.serialization.javascriptserializer)を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="5f05e-147">The `ConvertTo-Json` cmdlet is implemented using the [JavaScriptSerializer class](/dotnet/api/system.web.script.serialization.javascriptserializer).</span></span>

## <span data-ttu-id="5f05e-148">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5f05e-148">RELATED LINKS</span></span>

<span data-ttu-id="5f05e-149">[JavaScript および .NET での JavaScript Object Notation (JSON) の概要](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="5f05e-149">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="5f05e-150">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="5f05e-150">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="5f05e-151">Get-Content</span><span class="sxs-lookup"><span data-stu-id="5f05e-151">Get-Content</span></span>](../Microsoft.PowerShell.Management/Get-Content.md)

[<span data-ttu-id="5f05e-152">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="5f05e-152">Get-UICulture</span></span>](Get-UICulture.md)

[<span data-ttu-id="5f05e-153">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="5f05e-153">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="5f05e-154">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="5f05e-154">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
