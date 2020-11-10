---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Json
ms.openlocfilehash: e1bab9250269dadf0d899f9e172e8a4a8387271d
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388129"
---
# <span data-ttu-id="6f2b5-103">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="6f2b5-103">ConvertFrom-Json</span></span>

## <span data-ttu-id="6f2b5-104">概要</span><span class="sxs-lookup"><span data-stu-id="6f2b5-104">SYNOPSIS</span></span>
<span data-ttu-id="6f2b5-105">JSON 形式の文字列をカスタム オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-105">Converts a JSON-formatted string to a custom object.</span></span>

## <span data-ttu-id="6f2b5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6f2b5-106">SYNTAX</span></span>

```
ConvertFrom-Json [-InputObject] <String> [<CommonParameters>]
```

## <span data-ttu-id="6f2b5-107">Description</span><span class="sxs-lookup"><span data-stu-id="6f2b5-107">DESCRIPTION</span></span>

<span data-ttu-id="6f2b5-108">この `ConvertFrom-Json` コマンドレットは、json (JavaScript Object Notation) 形式の文字列を、json 文字列内の各フィールドのプロパティを持つカスタム **Pscustomobject** オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-108">The `ConvertFrom-Json` cmdlet converts a JavaScript Object Notation (JSON) formatted string to a custom **PSCustomObject** object that has a property for each field in the JSON string.</span></span> <span data-ttu-id="6f2b5-109">JSON は、オブジェクトのテキスト表現を提供する Web サイトで広く使用されています。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-109">JSON is commonly used by web sites to provide a textual representation of objects.</span></span> <span data-ttu-id="6f2b5-110">JSON 標準では、 **Pscustomobject** 禁止されている使用は禁止されていません。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-110">The JSON standard does not prohibit usage that is prohibited with a **PSCustomObject**.</span></span> <span data-ttu-id="6f2b5-111">たとえば、JSON 文字列に重複するキーが含まれている場合、このコマンドレットでは最後のキーのみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-111">For example, if the JSON string contains duplicate keys, only the last key is used by this cmdlet.</span></span> <span data-ttu-id="6f2b5-112">次の他の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-112">See other examples below.</span></span>

<span data-ttu-id="6f2b5-113">任意のオブジェクトから JSON 文字列を生成するには、コマンドレットを使用し `ConvertTo-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-113">To generate a JSON string from any object, use the `ConvertTo-Json` cmdlet.</span></span>

<span data-ttu-id="6f2b5-114">このコマンドレットは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-114">This cmdlet was introduced in PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="6f2b5-115">このコマンドレットは、コメント付きの JSON をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-115">This cmdlet doesn't support JSON with comments.</span></span>

## <span data-ttu-id="6f2b5-116">例</span><span class="sxs-lookup"><span data-stu-id="6f2b5-116">EXAMPLES</span></span>

### <span data-ttu-id="6f2b5-117">例 1: DateTime オブジェクトを JSON オブジェクトに変換する</span><span class="sxs-lookup"><span data-stu-id="6f2b5-117">Example 1: Convert a DateTime object to a JSON object</span></span>

<span data-ttu-id="6f2b5-118">このコマンドは、コマンドレットとコマンドレットを使用して、 `ConvertTo-Json` `ConvertFrom-Json` **DateTime** オブジェクトを `Get-Date` コマンドレットから JSON オブジェクトに変換し、 **pscustomobject** 実行します。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-118">This command uses the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert a **DateTime** object from the `Get-Date` cmdlet to a JSON object then to a **PSCustomObject**.</span></span>

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json | ConvertFrom-Json
```

```Output
DisplayHint : 2
DateTime    : Friday, January 13, 2012 8:06:31 PM
Date        : 1/13/2012 8:00:00 AM
Day         : 13
DayOfWeek   : 5
DayOfYear   : 13
Hour        : 20
Kind        : 2
Millisecond : 400
Minute      : 6
Month       : 1
Second      : 31
Ticks       : 634620819914009002
TimeOfDay   : @{Ticks=723914009002; Days=0; Hours=20; Milliseconds=400; Minutes=6; Seconds=31; TotalDays=0.83786343634490734; TotalHours=20.108722472277776; TotalMilliseconds=72391400.900200009; TotalMinutes=1206.5233483366667;TotalSeconds=72391.4009002}
Year        : 2012
```

<span data-ttu-id="6f2b5-119">この例では、コマンドレットを使用して、 `Select-Object` **DateTime** オブジェクトのすべてのプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-119">The example uses the `Select-Object` cmdlet to get all of the properties of the **DateTime** object.</span></span> <span data-ttu-id="6f2b5-120">コマンドレットを使用し `ConvertTo-Json` て、 **DateTime** オブジェクトを json オブジェクトとして書式設定された文字列に変換し、コマンドレットを使用して `ConvertFrom-Json` json 形式の文字列を **pscustomobject** オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-120">It uses the `ConvertTo-Json` cmdlet to convert the **DateTime** object to a string formatted as a JSON object and the `ConvertFrom-Json` cmdlet to convert the JSON-formatted string to a **PSCustomObject** object.</span></span>

### <span data-ttu-id="6f2b5-121">例 2: web サービスから JSON 文字列を取得し、それを PowerShell オブジェクトに変換する</span><span class="sxs-lookup"><span data-stu-id="6f2b5-121">Example 2: Get JSON strings from a web service and convert them to PowerShell objects</span></span>

<span data-ttu-id="6f2b5-122">このコマンドは、コマンドレットを使用して `Invoke-WebRequest` web サービスから json 文字列を取得し、コマンドレットを使用して `ConvertFrom-Json` json コンテンツを PowerShell で管理できるオブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-122">This command uses the `Invoke-WebRequest` cmdlet to get JSON strings from a web service and then it uses the `ConvertFrom-Json` cmdlet to convert JSON content to objects that can be managed in PowerShell.</span></span>

```powershell
# Ensures that Invoke-WebRequest uses TLS 1.2
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$j = Invoke-WebRequest 'https://api.github.com/repos/PowerShell/PowerShell/issues' | ConvertFrom-Json
```

<span data-ttu-id="6f2b5-123">`Invoke-RestMethod`JSON コンテンツをオブジェクトに自動的に変換するコマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-123">You can also use the `Invoke-RestMethod` cmdlet, which automatically converts JSON content to objects.</span></span>

### <span data-ttu-id="6f2b5-124">例 3: JSON 文字列をカスタムオブジェクトに変換する</span><span class="sxs-lookup"><span data-stu-id="6f2b5-124">Example 3: Convert a JSON string to a custom object</span></span>

<span data-ttu-id="6f2b5-125">この例では、コマンドレットを使用して `ConvertFrom-Json` JSON ファイルを PowerShell カスタムオブジェクトに変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-125">This example shows how to use the `ConvertFrom-Json` cmdlet to convert a JSON file to a PowerShell custom object.</span></span>

```powershell
Get-Content JsonFile.JSON | ConvertFrom-Json
```

<span data-ttu-id="6f2b5-126">このコマンドは Get-Content コマンドレットを使用して、JSON ファイル内の文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-126">The command uses Get-Content cmdlet to get the strings in a JSON file.</span></span> <span data-ttu-id="6f2b5-127">次に、パイプライン演算子を使用して、区切られた文字列をコマンドレットに送信し `ConvertFrom-Json` 、それをカスタムオブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-127">Then it uses the pipeline operator to send the delimited string to the `ConvertFrom-Json` cmdlet, which converts it to a custom object.</span></span>

## <span data-ttu-id="6f2b5-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6f2b5-128">PARAMETERS</span></span>

### <span data-ttu-id="6f2b5-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6f2b5-129">-InputObject</span></span>

<span data-ttu-id="6f2b5-130">JSON オブジェクトに変換する JSON 文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-130">Specifies the JSON strings to convert to JSON objects.</span></span> <span data-ttu-id="6f2b5-131">文字列が格納されている変数を入力するか、文字列を取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-131">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="6f2b5-132">パイプを使用して文字列をにパイプすることもでき `ConvertFrom-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-132">You can also pipe a string to `ConvertFrom-Json`.</span></span>

<span data-ttu-id="6f2b5-133">**InputObject** パラメーターは必須ですが、その値に空の文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-133">The **InputObject** parameter is required, but its value can be an empty string.</span></span> <span data-ttu-id="6f2b5-134">入力オブジェクトが空の文字列の場合、 `ConvertFrom-Json` は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-134">When the input object is an empty string, `ConvertFrom-Json` does not generate any output.</span></span> <span data-ttu-id="6f2b5-135">**InputObject** 値をにすることはできません `$null` 。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-135">The **InputObject** value cannot be `$null`.</span></span>

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

### <span data-ttu-id="6f2b5-136">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6f2b5-136">CommonParameters</span></span>

<span data-ttu-id="6f2b5-137">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6f2b5-138">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6f2b5-139">入力</span><span class="sxs-lookup"><span data-stu-id="6f2b5-139">INPUTS</span></span>

### <span data-ttu-id="6f2b5-140">System.String</span><span class="sxs-lookup"><span data-stu-id="6f2b5-140">System.String</span></span>

<span data-ttu-id="6f2b5-141">パイプを使用して、JSON 文字列をにパイプすることができ `ConvertFrom-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-141">You can pipe a JSON string to `ConvertFrom-Json`.</span></span>

## <span data-ttu-id="6f2b5-142">出力</span><span class="sxs-lookup"><span data-stu-id="6f2b5-142">OUTPUTS</span></span>

### <span data-ttu-id="6f2b5-143">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="6f2b5-143">PSCustomObject</span></span>

## <span data-ttu-id="6f2b5-144">注</span><span class="sxs-lookup"><span data-stu-id="6f2b5-144">NOTES</span></span>

<span data-ttu-id="6f2b5-145">`ConvertFrom-Json`コマンドレットは、 [JavaScriptSerializer クラス](/dotnet/api/system.web.script.serialization.javascriptserializer)を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="6f2b5-145">The `ConvertFrom-Json` cmdlet is implemented using the [JavaScriptSerializer class](/dotnet/api/system.web.script.serialization.javascriptserializer).</span></span>

## <span data-ttu-id="6f2b5-146">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6f2b5-146">RELATED LINKS</span></span>

<span data-ttu-id="6f2b5-147">[JavaScript および .NET での JavaScript Object Notation (JSON) の概要](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="6f2b5-147">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="6f2b5-148">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="6f2b5-148">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="6f2b5-149">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="6f2b5-149">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="6f2b5-150">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="6f2b5-150">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
