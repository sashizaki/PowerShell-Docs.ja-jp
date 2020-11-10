---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Json
ms.openlocfilehash: 062d29d033e0a84837a1593fb96df0c3a00dc392
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389421"
---
# <span data-ttu-id="085ad-103">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="085ad-103">ConvertFrom-Json</span></span>

## <span data-ttu-id="085ad-104">概要</span><span class="sxs-lookup"><span data-stu-id="085ad-104">SYNOPSIS</span></span>
<span data-ttu-id="085ad-105">JSON 形式の文字列をカスタムオブジェクトまたはハッシュテーブルに変換します。</span><span class="sxs-lookup"><span data-stu-id="085ad-105">Converts a JSON-formatted string to a custom object or a hash table.</span></span>

## <span data-ttu-id="085ad-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="085ad-106">SYNTAX</span></span>

```
ConvertFrom-Json [-InputObject] <String> [-AsHashtable] [-Depth <Int32>] [-NoEnumerate] [<CommonParameters>]
```

## <span data-ttu-id="085ad-107">Description</span><span class="sxs-lookup"><span data-stu-id="085ad-107">DESCRIPTION</span></span>

<span data-ttu-id="085ad-108">この `ConvertFrom-Json` コマンドレットは、json (JavaScript Object Notation) 形式の文字列を、json 文字列内の各フィールドのプロパティを持つカスタム **Pscustomobject** オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="085ad-108">The `ConvertFrom-Json` cmdlet converts a JavaScript Object Notation (JSON) formatted string to a custom **PSCustomObject** object that has a property for each field in the JSON string.</span></span> <span data-ttu-id="085ad-109">JSON は、オブジェクトのテキスト表現を提供する Web サイトで広く使用されています。</span><span class="sxs-lookup"><span data-stu-id="085ad-109">JSON is commonly used by web sites to provide a textual representation of objects.</span></span> <span data-ttu-id="085ad-110">JSON 標準では、 **Pscustomobject** 禁止されている使用は禁止されていません。</span><span class="sxs-lookup"><span data-stu-id="085ad-110">The JSON standard does not prohibit usage that is prohibited with a **PSCustomObject**.</span></span> <span data-ttu-id="085ad-111">たとえば、JSON 文字列に重複するキーが含まれている場合、このコマンドレットでは最後のキーのみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="085ad-111">For example, if the JSON string contains duplicate keys, only the last key is used by this cmdlet.</span></span> <span data-ttu-id="085ad-112">次の他の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="085ad-112">See other examples below.</span></span>

<span data-ttu-id="085ad-113">任意のオブジェクトから JSON 文字列を生成するには、コマンドレットを使用し `ConvertTo-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="085ad-113">To generate a JSON string from any object, use the `ConvertTo-Json` cmdlet.</span></span>

<span data-ttu-id="085ad-114">このコマンドレットは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="085ad-114">This cmdlet was introduced in PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="085ad-115">PowerShell 6 以降では、このコマンドレットは、コメント付きの JSON をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="085ad-115">Beginning with PowerShell 6, this cmdlet supports JSON with comments.</span></span> <span data-ttu-id="085ad-116">受け入れられるコメントは、2つのスラッシュ () で開始され `//` ます。</span><span class="sxs-lookup"><span data-stu-id="085ad-116">Accepted comments are started with two forward slashes (`//`).</span></span> <span data-ttu-id="085ad-117">コメントはデータ内では表示されません。また、PowerShell 5.1 の場合と同様に、データを破損させたりエラーをスローしたりすることなくファイルに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="085ad-117">The comment will not be represented in the data and can be written in the file without corrupting the data or throwing an error as it did in PowerShell 5.1.</span></span>

## <span data-ttu-id="085ad-118">例</span><span class="sxs-lookup"><span data-stu-id="085ad-118">EXAMPLES</span></span>

### <span data-ttu-id="085ad-119">例 1: DateTime オブジェクトを JSON オブジェクトに変換する</span><span class="sxs-lookup"><span data-stu-id="085ad-119">Example 1: Convert a DateTime object to a JSON object</span></span>

<span data-ttu-id="085ad-120">このコマンドは、コマンドレットとコマンドレットを使用して、 `ConvertTo-Json` `ConvertFrom-Json` **DateTime** オブジェクトを `Get-Date` コマンドレットから JSON オブジェクトに変換し、 **pscustomobject** 実行します。</span><span class="sxs-lookup"><span data-stu-id="085ad-120">This command uses the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert a **DateTime** object from the `Get-Date` cmdlet to a JSON object then to a **PSCustomObject**.</span></span>

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

<span data-ttu-id="085ad-121">この例では、コマンドレットを使用して、 `Select-Object` **DateTime** オブジェクトのすべてのプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="085ad-121">The example uses the `Select-Object` cmdlet to get all of the properties of the **DateTime** object.</span></span> <span data-ttu-id="085ad-122">コマンドレットを使用し `ConvertTo-Json` て、 **DateTime** オブジェクトを json オブジェクトとして書式設定された文字列に変換し、コマンドレットを使用して `ConvertFrom-Json` json 形式の文字列を **pscustomobject** オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="085ad-122">It uses the `ConvertTo-Json` cmdlet to convert the **DateTime** object to a string formatted as a JSON object and the `ConvertFrom-Json` cmdlet to convert the JSON-formatted string to a **PSCustomObject** object.</span></span>

### <span data-ttu-id="085ad-123">例 2: web サービスから JSON 文字列を取得し、それを PowerShell オブジェクトに変換する</span><span class="sxs-lookup"><span data-stu-id="085ad-123">Example 2: Get JSON strings from a web service and convert them to PowerShell objects</span></span>

<span data-ttu-id="085ad-124">このコマンドは、コマンドレットを使用して `Invoke-WebRequest` web サービスから json 文字列を取得し、コマンドレットを使用して `ConvertFrom-Json` json コンテンツを PowerShell で管理できるオブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="085ad-124">This command uses the `Invoke-WebRequest` cmdlet to get JSON strings from a web service and then it uses the `ConvertFrom-Json` cmdlet to convert JSON content to objects that can be managed in PowerShell.</span></span>

```powershell
# Ensures that Invoke-WebRequest uses TLS 1.2
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$j = Invoke-WebRequest 'https://api.github.com/repos/PowerShell/PowerShell/issues' | ConvertFrom-Json
```

<span data-ttu-id="085ad-125">`Invoke-RestMethod`JSON コンテンツをオブジェクトに自動的に変換するコマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="085ad-125">You can also use the `Invoke-RestMethod` cmdlet, which automatically converts JSON content to objects.</span></span>

### <span data-ttu-id="085ad-126">例 3: JSON 文字列をカスタムオブジェクトに変換する</span><span class="sxs-lookup"><span data-stu-id="085ad-126">Example 3: Convert a JSON string to a custom object</span></span>

<span data-ttu-id="085ad-127">この例では、コマンドレットを使用して `ConvertFrom-Json` JSON ファイルを PowerShell カスタムオブジェクトに変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="085ad-127">This example shows how to use the `ConvertFrom-Json` cmdlet to convert a JSON file to a PowerShell custom object.</span></span>

```powershell
Get-Content JsonFile.JSON | ConvertFrom-Json
```

<span data-ttu-id="085ad-128">このコマンドは Get-Content コマンドレットを使用して、JSON ファイル内の文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="085ad-128">The command uses Get-Content cmdlet to get the strings in a JSON file.</span></span> <span data-ttu-id="085ad-129">次に、パイプライン演算子を使用して、区切られた文字列をコマンドレットに送信し `ConvertFrom-Json` 、それをカスタムオブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="085ad-129">Then it uses the pipeline operator to send the delimited string to the `ConvertFrom-Json` cmdlet, which converts it to a custom object.</span></span>

### <span data-ttu-id="085ad-130">例 4: JSON 文字列をハッシュテーブルに変換する</span><span class="sxs-lookup"><span data-stu-id="085ad-130">Example 4: Convert a JSON string to a hash table</span></span>

<span data-ttu-id="085ad-131">このコマンドは、 `-AsHashtable` スイッチがコマンドの制限を克服できる例を示しています。</span><span class="sxs-lookup"><span data-stu-id="085ad-131">This command shows an example where the `-AsHashtable` switch can overcome limitations of the command.</span></span>

```powershell
'{ "key":"value1", "Key":"value2" }' | ConvertFrom-Json -AsHashtable
```

<span data-ttu-id="085ad-132">JSON 文字列には、大文字小文字のみが異なるキーを持つ2つのキーと値のペアが含まれています。</span><span class="sxs-lookup"><span data-stu-id="085ad-132">The JSON string contains two key value pairs with keys that differ only in casing.</span></span> <span data-ttu-id="085ad-133">スイッチがない場合、コマンドはエラーをスローしました。</span><span class="sxs-lookup"><span data-stu-id="085ad-133">Without the switch, the command would have thrown an error.</span></span>

### <span data-ttu-id="085ad-134">例 5: 1 つの要素配列をラウンドトリップする</span><span class="sxs-lookup"><span data-stu-id="085ad-134">Example 5: Round-trip a single element array</span></span>

<span data-ttu-id="085ad-135">このコマンドは、スイッチを使用して `-NoEnumerate` 1 つの要素 JSON 配列をラウンドトリップする例を示しています。</span><span class="sxs-lookup"><span data-stu-id="085ad-135">This command shows an example where the `-NoEnumerate` switch is used to round-trip a single element JSON array.</span></span>

```powershell
Write-Output "With -NoEnumerate: $('[1]' | ConvertFrom-Json -NoEnumerate | ConvertTo-Json -Compress)"
Write-Output "Without -NoEnumerate: $('[1]' | ConvertFrom-Json | ConvertTo-Json -Compress)"
```

```Output
With -NoEnumerate: [1]
Without -NoEnumerate: 1
```

<span data-ttu-id="085ad-136">JSON 文字列には、1つの要素を持つ配列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="085ad-136">The JSON string contains an array with a single element.</span></span> <span data-ttu-id="085ad-137">スイッチがない場合は、JSON を PSObject に変換してから、コマンドを使用して変換すると、 `ConvertTo-Json` 1 つの整数になります。</span><span class="sxs-lookup"><span data-stu-id="085ad-137">Without the switch, converting the JSON to a PSObject and then converting it back with the `ConvertTo-Json` command results in a single integer.</span></span>

## <span data-ttu-id="085ad-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="085ad-138">PARAMETERS</span></span>

### <span data-ttu-id="085ad-139">-AsHashtable</span><span class="sxs-lookup"><span data-stu-id="085ad-139">-AsHashtable</span></span>

<span data-ttu-id="085ad-140">JSON をハッシュテーブルオブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="085ad-140">Converts the JSON to a hash table object.</span></span> <span data-ttu-id="085ad-141">このスイッチは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="085ad-141">This switch was introduced in PowerShell 6.0.</span></span> <span data-ttu-id="085ad-142">いくつかのシナリオでは、コマンドレットのいくつかの制限を克服でき `ConvertFrom-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="085ad-142">There are several scenarios where it can overcome some limitations of the `ConvertFrom-Json` cmdlet.</span></span>

- <span data-ttu-id="085ad-143">大文字と小文字の違いが異なるキーを持つリストが JSON に含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="085ad-143">If the JSON contains a list with keys that only differ in casing.</span></span> <span data-ttu-id="085ad-144">スイッチを指定しないと、これらのキーは同じキーと見なされるため、最後のキーのみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="085ad-144">Without the switch, those keys would be seen as identical keys and therefore only the last one would get used.</span></span>
- <span data-ttu-id="085ad-145">JSON に空の文字列であるキーが含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="085ad-145">If the JSON contains a key that is an empty string.</span></span> <span data-ttu-id="085ad-146">スイッチを指定しないと、では、ハッシュテーブルでは許可されないため、コマンドレットでエラーがスロー `PSCustomObject` されます。</span><span class="sxs-lookup"><span data-stu-id="085ad-146">Without the switch, the cmdlet would throw an error since a `PSCustomObject` does not allow for that but a hash table does.</span></span> <span data-ttu-id="085ad-147">これが発生する可能性のあるユースケースの例としては、 `project.lock.json` ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="085ad-147">An example use case where this can occurs are `project.lock.json` files.</span></span>
- <span data-ttu-id="085ad-148">ハッシュテーブルは、特定のデータ構造に対してより高速に処理できます。</span><span class="sxs-lookup"><span data-stu-id="085ad-148">Hash tables can be processed faster for certain data structures.</span></span>

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

### <span data-ttu-id="085ad-149">-深さ</span><span class="sxs-lookup"><span data-stu-id="085ad-149">-Depth</span></span>

<span data-ttu-id="085ad-150">JSON 入力に許可されている最大の深さを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="085ad-150">Gets or sets the maximum depth the JSON input is allowed to have.</span></span> <span data-ttu-id="085ad-151">既定では、1024です。</span><span class="sxs-lookup"><span data-stu-id="085ad-151">By default, it is 1024.</span></span>

<span data-ttu-id="085ad-152">このパラメーターは、PowerShell 6.2 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="085ad-152">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="085ad-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="085ad-153">-InputObject</span></span>

<span data-ttu-id="085ad-154">JSON オブジェクトに変換する JSON 文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="085ad-154">Specifies the JSON strings to convert to JSON objects.</span></span> <span data-ttu-id="085ad-155">文字列が格納されている変数を入力するか、文字列を取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="085ad-155">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="085ad-156">パイプを使用して文字列をにパイプすることもでき `ConvertFrom-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="085ad-156">You can also pipe a string to `ConvertFrom-Json`.</span></span>

<span data-ttu-id="085ad-157">**InputObject** パラメーターは必須ですが、その値に空の文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="085ad-157">The **InputObject** parameter is required, but its value can be an empty string.</span></span> <span data-ttu-id="085ad-158">入力オブジェクトが空の文字列の場合、 `ConvertFrom-Json` は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="085ad-158">When the input object is an empty string, `ConvertFrom-Json` does not generate any output.</span></span> <span data-ttu-id="085ad-159">**InputObject** 値をにすることはできません `$null` 。</span><span class="sxs-lookup"><span data-stu-id="085ad-159">The **InputObject** value cannot be `$null`.</span></span>

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

### <span data-ttu-id="085ad-160">-NoEnumerate</span><span class="sxs-lookup"><span data-stu-id="085ad-160">-NoEnumerate</span></span>

<span data-ttu-id="085ad-161">出力が列挙されないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="085ad-161">Specifies that output is not enumerated.</span></span>

<span data-ttu-id="085ad-162">このパラメーターを設定すると、すべての要素を個別に送信する代わりに、配列が単一のオブジェクトとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="085ad-162">Setting this parameter causes arrays to be sent as a single object instead of sending every element separately.</span></span> <span data-ttu-id="085ad-163">これにより、で JSON をラウンドトリップできることが保証さ `ConvertTo-Json` れます。</span><span class="sxs-lookup"><span data-stu-id="085ad-163">This guarantees that JSON can be round-tripped via `ConvertTo-Json`.</span></span>

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

### <span data-ttu-id="085ad-164">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="085ad-164">CommonParameters</span></span>

<span data-ttu-id="085ad-165">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="085ad-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="085ad-166">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="085ad-166">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="085ad-167">入力</span><span class="sxs-lookup"><span data-stu-id="085ad-167">INPUTS</span></span>

### <span data-ttu-id="085ad-168">System.String</span><span class="sxs-lookup"><span data-stu-id="085ad-168">System.String</span></span>

<span data-ttu-id="085ad-169">パイプを使用して、JSON 文字列をにパイプすることができ `ConvertFrom-Json` ます。</span><span class="sxs-lookup"><span data-stu-id="085ad-169">You can pipe a JSON string to `ConvertFrom-Json`.</span></span>

## <span data-ttu-id="085ad-170">出力</span><span class="sxs-lookup"><span data-stu-id="085ad-170">OUTPUTS</span></span>

### <span data-ttu-id="085ad-171">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="085ad-171">PSCustomObject</span></span>

### <span data-ttu-id="085ad-172">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="085ad-172">System.Collections.Hashtable</span></span>

## <span data-ttu-id="085ad-173">注</span><span class="sxs-lookup"><span data-stu-id="085ad-173">NOTES</span></span>

<span data-ttu-id="085ad-174">このコマンドレットは [Newtonsoft Json.NET](https://www.newtonsoft.com/json)を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="085ad-174">This cmdlet is implemented using [Newtonsoft Json.NET](https://www.newtonsoft.com/json).</span></span>

<span data-ttu-id="085ad-175">PowerShell 6 以降では、 `ConvertTo-Json` タイムスタンプとして書式設定された文字列を **DateTime** 値に変換しようとします。</span><span class="sxs-lookup"><span data-stu-id="085ad-175">Beginning in PowerShell 6, `ConvertTo-Json` attempts to convert strings formatted as timestamps to **DateTime** values.</span></span> <span data-ttu-id="085ad-176">変換後の値は、プロパティが次のよう `[datetime]` に設定されたインスタンスです `Kind` 。</span><span class="sxs-lookup"><span data-stu-id="085ad-176">The converted value is a `[datetime]` instance with a `Kind` property set as follows:</span></span>

- <span data-ttu-id="085ad-177">`Unspecified`入力文字列にタイムゾーン情報がない場合は。</span><span class="sxs-lookup"><span data-stu-id="085ad-177">`Unspecified`, if there is no time zone information in the input string.</span></span>
- <span data-ttu-id="085ad-178">`Utc`タイムゾーン情報が末尾である場合は `Z` 。</span><span class="sxs-lookup"><span data-stu-id="085ad-178">`Utc`, if the time zone information is a trailing `Z`.</span></span>
- <span data-ttu-id="085ad-179">`Local`タイムゾーン情報が、のような末尾の UTC _オフセット_ として指定されている場合は `+02:00` 。</span><span class="sxs-lookup"><span data-stu-id="085ad-179">`Local`, if the time zone information is given as a trailing UTC _offset_ like `+02:00`.</span></span> <span data-ttu-id="085ad-180">オフセットは、呼び出し元の構成されたタイムゾーンに適切に変換されます。</span><span class="sxs-lookup"><span data-stu-id="085ad-180">The offset is properly converted to the caller's configured time zone.</span></span> <span data-ttu-id="085ad-181">既定の出力書式設定では、元のタイムゾーンオフセットは示されません。</span><span class="sxs-lookup"><span data-stu-id="085ad-181">The default output formatting does not indicate the original time zone offset.</span></span>

## <span data-ttu-id="085ad-182">関連リンク</span><span class="sxs-lookup"><span data-stu-id="085ad-182">RELATED LINKS</span></span>

<span data-ttu-id="085ad-183">[JavaScript および .NET での JavaScript Object Notation (JSON) の概要](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="085ad-183">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="085ad-184">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="085ad-184">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="085ad-185">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="085ad-185">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="085ad-186">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="085ad-186">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
