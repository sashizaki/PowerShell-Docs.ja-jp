---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/21/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-csv?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Csv
ms.openlocfilehash: 68b101d0ff36fe9417118dd97d112c070672c9b7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216840"
---
# <span data-ttu-id="feaf9-103">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="feaf9-103">ConvertFrom-Csv</span></span>

## <span data-ttu-id="feaf9-104">概要</span><span class="sxs-lookup"><span data-stu-id="feaf9-104">SYNOPSIS</span></span>
<span data-ttu-id="feaf9-105">コンマ区切り値 (CSV) 形式のオブジェクトのプロパティを元のオブジェクトの CSV バージョンに変換します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-105">Converts object properties in comma-separated value (CSV) format into CSV versions of the original objects.</span></span>

## <span data-ttu-id="feaf9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="feaf9-106">SYNTAX</span></span>

### <span data-ttu-id="feaf9-107">デリミターパス (既定)</span><span class="sxs-lookup"><span data-stu-id="feaf9-107">DelimiterPath (Default)</span></span>

```
ConvertFrom-Csv [[-Delimiter] <Char>] [-InputObject] <PSObject[]> [-Header <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="feaf9-108">アルゴリズムの反復</span><span class="sxs-lookup"><span data-stu-id="feaf9-108">CultureLiteralPath</span></span>

```
ConvertFrom-Csv -UseCulture [-InputObject] <PSObject[]> [-Header <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="feaf9-109">CulturePath</span><span class="sxs-lookup"><span data-stu-id="feaf9-109">CulturePath</span></span>

```
ConvertFrom-Csv -UseCulture [-InputObject] <PSObject[]> [-Header <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="feaf9-110">Description</span><span class="sxs-lookup"><span data-stu-id="feaf9-110">DESCRIPTION</span></span>

<span data-ttu-id="feaf9-111">`ConvertFrom-Csv`コマンドレットでは、コマンドレットによって生成される CSV 可変長文字列からオブジェクトを作成し `ConvertTo-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-111">The `ConvertFrom-Csv` cmdlet creates objects from CSV variable-length strings that are generated by the `ConvertTo-Csv` cmdlet.</span></span>

<span data-ttu-id="feaf9-112">このコマンドレットのパラメーターを使用して、結果として生成されるオブジェクトのプロパティ名を決定する列ヘッダー行を指定したり、項目の区切り記号を指定したり、現在のカルチャの区切り記号を区切り記号として使用するようにこのコマンドレットに指示したりできます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-112">You can use the parameters of this cmdlet to specify the column header row, which determines the property names of the resulting objects, to specify the item delimiter, or to direct this cmdlet to use the list separator for the current culture as the delimiter.</span></span>

<span data-ttu-id="feaf9-113">によって作成されるオブジェクトは、 `ConvertFrom-Csv` 元のオブジェクトの CSV バージョンです。</span><span class="sxs-lookup"><span data-stu-id="feaf9-113">The objects that `ConvertFrom-Csv` creates are CSV versions of the original objects.</span></span> <span data-ttu-id="feaf9-114">CSV オブジェクトのプロパティ値は、元のオブジェクトのプロパティ値の文字列バージョンです。</span><span class="sxs-lookup"><span data-stu-id="feaf9-114">The property values of the CSV objects are string versions of the property values of the original objects.</span></span> <span data-ttu-id="feaf9-115">オブジェクトの CSV バージョンはメソッドを持ちません。</span><span class="sxs-lookup"><span data-stu-id="feaf9-115">The CSV versions of the objects do not have any methods.</span></span>

<span data-ttu-id="feaf9-116">また、 `Export-Csv` `Import-Csv` コマンドレットとコマンドレットを使用して、オブジェクトをファイル内の CSV 文字列に変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-116">You can also use the `Export-Csv` and `Import-Csv` cmdlets to convert objects to CSV strings in a file (and back).</span></span> <span data-ttu-id="feaf9-117">これらのコマンドレットは、 `ConvertTo-Csv` `ConvertFrom-Csv` コマンドレットとコマンドレットと同じですが、CSV 文字列をファイルに保存する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="feaf9-117">These cmdlets are the same as the `ConvertTo-Csv` and `ConvertFrom-Csv` cmdlets, except that they save the CSV strings in a file.</span></span>

## <span data-ttu-id="feaf9-118">例</span><span class="sxs-lookup"><span data-stu-id="feaf9-118">EXAMPLES</span></span>

### <span data-ttu-id="feaf9-119">例 1: ローカルコンピューター上のプロセスを CSV 形式に変換する</span><span class="sxs-lookup"><span data-stu-id="feaf9-119">Example 1: Convert processes on the local computer to CSV format</span></span>

<span data-ttu-id="feaf9-120">この例では、ローカルコンピューター上のプロセスを CSV 形式に変換してから、オブジェクト形式に復元する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-120">This example shows how to convert the processes on the local computer into CSV format and then restore them to object form.</span></span>

```powershell
$P = Get-Process | ConvertTo-Csv
$P | ConvertFrom-Csv
```

<span data-ttu-id="feaf9-121">`Get-Process`コマンドレットは、パイプラインの下にあるプロセスをに送信し `ConvertTo-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-121">The `Get-Process` cmdlet sends the processes down the pipeline to `ConvertTo-Csv`.</span></span> <span data-ttu-id="feaf9-122">コマンドレットでは、 `ConvertTo-Csv` プロセスオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-122">The `ConvertTo-Csv` cmdlet converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="feaf9-123">コマンドレットにより、 `ConvertFrom-Csv` csv 文字列が元のプロセスオブジェクトの csv バージョンに変換されます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-123">The `ConvertFrom-Csv` cmdlet converts the CSV strings into CSV versions of the original process objects.</span></span> <span data-ttu-id="feaf9-124">CSV 文字列は変数に保存され `$P` ます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-124">The CSV strings are saved in the `$P` variable.</span></span>

### <span data-ttu-id="feaf9-125">例 2: データオブジェクトを CSV 形式に変換してから CSV オブジェクト形式に変換する</span><span class="sxs-lookup"><span data-stu-id="feaf9-125">Example 2: Convert a data object to CSV format and then to CSV object format</span></span>

<span data-ttu-id="feaf9-126">この例では、データオブジェクトを CSV 形式に変換した後、CSV オブジェクト形式に変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-126">This example shows how to convert a data object to CSV format and then to CSV object format.</span></span>

```powershell
$Date = Get-Date | ConvertTo-Csv -Delimiter ';'
ConvertFrom-Csv -InputObject $Date -Delimiter ';'
```

<span data-ttu-id="feaf9-127">最初のコマンドは、を使用して、 `Get-Date` パイプラインの現在の日付と時刻をに送信し `ConvertTo-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-127">The first command uses `Get-Date` to send the current date and time down the pipeline to `ConvertTo-Csv`.</span></span> <span data-ttu-id="feaf9-128">この `ConvertTo-Csv` コマンドレットは、date オブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-128">The `ConvertTo-Csv` cmdlet converts the date object to a series of CSV strings.</span></span>
<span data-ttu-id="feaf9-129">**区切り** 記号パラメーターは、セミコロンの区切り記号を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-129">The **Delimiter** parameter is used to specify a semicolon delimiter.</span></span> <span data-ttu-id="feaf9-130">文字列は変数に保存され `$Date` ます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-130">The strings are saved in the `$Date` variable.</span></span>

### <span data-ttu-id="feaf9-131">例 3: header パラメーターを使用してプロパティの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="feaf9-131">Example 3: Use the header parameter to change the names of properties</span></span>

<span data-ttu-id="feaf9-132">この例では、の **Header** パラメーターを使用して `ConvertFrom-Csv` 、結果としてインポートされるオブジェクトのプロパティの名前を変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-132">This example shows how to use the **Header** parameter of `ConvertFrom-Csv` to change the names of properties in the resulting imported object.</span></span>

```powershell
$J = Start-Job -ScriptBlock { Get-Process } | ConvertTo-Csv  -NoTypeInformation
$Header = 'State', 'MoreData', 'StatusMessage', 'Location', 'Command', 'StateInfo', 'Finished', 'InstanceId', 'Id', 'Name', 'ChildJobs', 'BeginTime', 'EndTime', 'JobType', 'Output', 'Error', 'Progress', 'Verbose', 'Debug', 'Warning', 'Information'
# Delete the default header from $J
$J = $J[1..($J.count - 1)]
$J | ConvertFrom-Csv -Header $Header
```

```Output
State         : Running
MoreData      : True
StatusMessage :
Location      : localhost
Command       : Get-Process
StateInfo     : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : a259eb63-6824-4b97-a033-305108ae1c2e
Id            : 1
Name          : Job1
ChildJobs     : System.Collections.Generic.List`1[System.Management.Automation.Job]
BeginTime     : 12/20/2018 18:59:57
EndTime       :
JobType       : BackgroundJob
Output        : System.Management.Automation.PSDataCollection`1[System.Management.Automation.PSObject]
Error         : System.Management.Automation.PSDataCollection`1[System.Management.Automation.ErrorRecord]
Progress      : System.Management.Automation.PSDataCollection`1[System.Management.Automation.ProgressRecord]
Verbose       : System.Management.Automation.PSDataCollection`1[System.Management.Automation.VerboseRecord]
Debug         : System.Management.Automation.PSDataCollection`1[System.Management.Automation.DebugRecord]
Warning       : System.Management.Automation.PSDataCollection`1[System.Management.Automation.WarningRecord]
Information   : System.Management.Automation.PSDataCollection`1[System.Management.Automation.InformationRecord]
```

<span data-ttu-id="feaf9-133">コマンドレットでは、 `Start-Job` 実行するバックグラウンドジョブを開始し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-133">The `Start-Job` cmdlet starts a background job that runs `Get-Process`.</span></span> <span data-ttu-id="feaf9-134">ジョブオブジェクトは、パイプラインからに送信され、 `ConvertTo-Csv` CSV 文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-134">A job object is sent down the pipeline to `ConvertTo-Csv` and converted to a CSV string.</span></span> <span data-ttu-id="feaf9-135">**Notypeinformation** パラメーターは、CSV 出力から型情報ヘッダーを削除し、PowerShell Core では省略可能です。</span><span class="sxs-lookup"><span data-stu-id="feaf9-135">The **NoTypeInformation** parameter removes the type information header from CSV output and is optional in PowerShell Core.</span></span> <span data-ttu-id="feaf9-136">変数には、 `$Header` **HasPSJobTypeName data** 、 **jobstateinfo** 、 **Psbegintime** 、 **psendtime** 、および **PSJobTypeName** の既定値を置き換えるカスタムヘッダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="feaf9-136">The `$Header` variable contains a custom header that replaces the following default values: **HasMoreData** , **JobStateInfo** , **PSBeginTime** , **PSEndTime** , and **PSJobTypeName** .</span></span> <span data-ttu-id="feaf9-137">この `$J` 変数には CSV 文字列が含まれており、既定のヘッダーを削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-137">The `$J` variable contains the CSV string and is used to remove the default header.</span></span> <span data-ttu-id="feaf9-138">コマンドレットにより、 `ConvertFrom-Csv` CSV 文字列が **Pscustomobject** 変換され、 **Header** パラメーターを使用して変数が適用され `$Header` ます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-138">The `ConvertFrom-Csv` cmdlet converts the CSV string into a **PSCustomObject** and uses the **Header** parameter to apply the `$Header` variable.</span></span>

### <span data-ttu-id="feaf9-139">例 4: サービスオブジェクトの CSV 文字列を変換する</span><span class="sxs-lookup"><span data-stu-id="feaf9-139">Example 4: Convert CSV strings of service objects</span></span>

<span data-ttu-id="feaf9-140">この例では、UseCulture パラメーターを指定してコマンドレットを使用する方法を示し `ConvertFrom-Csv` ます。 **UseCulture**</span><span class="sxs-lookup"><span data-stu-id="feaf9-140">This example shows how to use the `ConvertFrom-Csv` cmdlet with the **UseCulture** parameter.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
$Services = (Get-Service | ConvertTo-Csv)
ConvertFrom-Csv -InputObject $Services -UseCulture
```

<span data-ttu-id="feaf9-141">この `Get-Culture` コマンドレットは、入れ子になったプロパティの **TextInfo** と **listseparator** を使用して、現在のカルチャの既定のリスト区切り記号を取得します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-141">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** to get the current culture's default list separator.</span></span> <span data-ttu-id="feaf9-142">`Get-Service`コマンドレットは、サービスオブジェクトをパイプラインからに送信し `ConvertTo-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-142">The `Get-Service` cmdlet sends service objects down the pipeline to `ConvertTo-Csv`.</span></span> <span data-ttu-id="feaf9-143">は、 `ConvertTo-Csv` サービスオブジェクトを一連の CSV 文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-143">The `ConvertTo-Csv` converts the service objects to a series of CSV strings.</span></span> <span data-ttu-id="feaf9-144">CSV 文字列は変数に格納され `$Services` ます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-144">The CSV strings are stored in the `$Services` variable.</span></span> <span data-ttu-id="feaf9-145">コマンドレットでは、 `ConvertFrom-Csv` **InputObject** パラメーターを使用して、変数から CSV 文字列を変換し `$Services` ます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-145">The `ConvertFrom-Csv` cmdlet uses the **InputObject** parameter and converts the CSV strings from the `$Services` variable.</span></span> <span data-ttu-id="feaf9-146">**UseCulture** パラメーターは、現在のカルチャの既定のリスト区切り記号を使用します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-146">The **UseCulture** parameter uses the current culture's default list separator.</span></span>

<span data-ttu-id="feaf9-147">**UseCulture** パラメーターを使用する場合は、現在のカルチャの既定のリスト区切り記号が、CSV 文字列で使用されている区切り記号と一致していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="feaf9-147">When the **UseCulture** parameter is used, be sure that the current culture's default list separator matches the delimiter used in the CSV strings.</span></span> <span data-ttu-id="feaf9-148">それ以外の場合、は `ConvertFrom-Csv` CSV 文字列からオブジェクトを生成できません。</span><span class="sxs-lookup"><span data-stu-id="feaf9-148">Otherwise, `ConvertFrom-Csv` cannot generate objects from the CSV strings.</span></span>

## <span data-ttu-id="feaf9-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="feaf9-149">PARAMETERS</span></span>

### <span data-ttu-id="feaf9-150">-区切り記号</span><span class="sxs-lookup"><span data-stu-id="feaf9-150">-Delimiter</span></span>

<span data-ttu-id="feaf9-151">CSV 文字列内のプロパティ値を区切る区切り記号を指定します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-151">Specifies the delimiter that separates the property values in the CSV strings.</span></span>
<span data-ttu-id="feaf9-152">既定値はコンマ (,) です。</span><span class="sxs-lookup"><span data-stu-id="feaf9-152">The default is a comma (,).</span></span>

<span data-ttu-id="feaf9-153">コロン (:) などの文字を入力します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-153">Enter a character, such as a colon (:).</span></span>
<span data-ttu-id="feaf9-154">セミコロン (;) を指定するには単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-154">To specify a semicolon (;) enclose it in single quotation marks.</span></span>

<span data-ttu-id="feaf9-155">ファイルに実際の文字列区切り記号以外の文字を指定すると、は `ConvertFrom-Csv` csv 文字列からオブジェクトを作成できず、csv 文字列が返されます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-155">If you specify a character other than the actual string delimiter in the file, `ConvertFrom-Csv` cannot create the objects from the CSV strings and will return the CSV strings.</span></span>

```yaml
Type: System.Char
Parameter Sets: DelimiterPath
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="feaf9-156">-ヘッダー</span><span class="sxs-lookup"><span data-stu-id="feaf9-156">-Header</span></span>

<span data-ttu-id="feaf9-157">インポートされた文字列の代替列ヘッダー行を指定します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-157">Specifies an alternate column header row for the imported string.</span></span> <span data-ttu-id="feaf9-158">列ヘッダーは、によって作成されるオブジェクトのプロパティ名を決定し `ConvertFrom-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-158">The column header determines the property names of the objects created by `ConvertFrom-Csv`.</span></span>

<span data-ttu-id="feaf9-159">列ヘッダーをコンマ区切りのリストとして入力します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-159">Enter column headers as a comma-separated list.</span></span> <span data-ttu-id="feaf9-160">ヘッダー文字列は引用符で囲まないでください。</span><span class="sxs-lookup"><span data-stu-id="feaf9-160">Do not enclose the header string in quotation marks.</span></span> <span data-ttu-id="feaf9-161">各列ヘッダーを単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-161">Enclose each column header in single quotation marks.</span></span>

<span data-ttu-id="feaf9-162">入力した列ヘッダーの数がデータ列の数を下回る場合は、残りのデータ列は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-162">If you enter fewer column headers than there are data columns, the remaining data columns are discarded.</span></span> <span data-ttu-id="feaf9-163">データ列よりも多くの列ヘッダーを入力すると、追加の列ヘッダーが空のデータ列で作成されます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-163">If you enter more column headers than there are data columns, the additional column headers are created with empty data columns.</span></span>

<span data-ttu-id="feaf9-164">**Header** パラメーターを使用する場合は、CSV 文字列から列ヘッダー文字列を省略します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-164">When using the **Header** parameter, omit the column header string from the CSV strings.</span></span> <span data-ttu-id="feaf9-165">それ以外の場合、このコマンドレットはヘッダー行の項目から追加のオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-165">Otherwise, this cmdlet creates an extra object from the items in the header row.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="feaf9-166">-InputObject</span><span class="sxs-lookup"><span data-stu-id="feaf9-166">-InputObject</span></span>

<span data-ttu-id="feaf9-167">オブジェクトに変換する CSV 文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-167">Specifies the CSV strings to be converted to objects.</span></span> <span data-ttu-id="feaf9-168">CSV 文字列が格納されている変数を入力するか、CSV 文字列を取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-168">Enter a variable that contains the CSV strings or type a command or expression that gets the CSV strings.</span></span> <span data-ttu-id="feaf9-169">また、CSV 文字列をにパイプ処理することもでき `ConvertFrom-Csv` ます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-169">You can also pipe the CSV strings to `ConvertFrom-Csv`.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="feaf9-170">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="feaf9-170">-UseCulture</span></span>

<span data-ttu-id="feaf9-171">現在のカルチャの区切り記号を項目の区切り記号として使用します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-171">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="feaf9-172">カルチャのリスト区切り記号を検索するには、コマンドを使用し `(Get-Culture).TextInfo.ListSeparator` ます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-172">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CultureLiteralPath, CulturePath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="feaf9-173">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="feaf9-173">CommonParameters</span></span>

<span data-ttu-id="feaf9-174">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="feaf9-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="feaf9-175">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="feaf9-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="feaf9-176">入力</span><span class="sxs-lookup"><span data-stu-id="feaf9-176">INPUTS</span></span>

### <span data-ttu-id="feaf9-177">System.String</span><span class="sxs-lookup"><span data-stu-id="feaf9-177">System.String</span></span>

<span data-ttu-id="feaf9-178">このコマンドレットには、CSV 文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-178">You can pipe CSV strings to this cmdlet.</span></span>

## <span data-ttu-id="feaf9-179">出力</span><span class="sxs-lookup"><span data-stu-id="feaf9-179">OUTPUTS</span></span>

### <span data-ttu-id="feaf9-180">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="feaf9-180">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="feaf9-181">このコマンドレットは、CSV 文字列のプロパティによって記述されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="feaf9-181">This cmdlet returns the objects described by the properties in the CSV strings.</span></span>

## <span data-ttu-id="feaf9-182">注</span><span class="sxs-lookup"><span data-stu-id="feaf9-182">NOTES</span></span>

<span data-ttu-id="feaf9-183">インポートされたオブジェクトはオブジェクト型の CSV バージョンであるため、オブジェクト型の非 CSV バージョンを書式設定する PowerShell の型書式設定エントリによって認識および書式設定されません。</span><span class="sxs-lookup"><span data-stu-id="feaf9-183">Because the imported objects are CSV versions of the object type, they are not recognized and formatted by the PowerShell type formatting entries that format the non-CSV versions of the object type.</span></span>

<span data-ttu-id="feaf9-184">CSV 形式では、各オブジェクトは、オブジェクトのプロパティ値のコンマ区切りリストで表されます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-184">In CSV format, each object is represented by a comma-separated list of the property values of the object.</span></span> <span data-ttu-id="feaf9-185">プロパティ値は、オブジェクトの **ToString ()** メソッドを使用して文字列に変換されるため、プロパティ値の名前で表されます。</span><span class="sxs-lookup"><span data-stu-id="feaf9-185">The property values are converted to strings (by using the **ToString()** method of the object), so they are represented by the name of the property value.</span></span> <span data-ttu-id="feaf9-186">このコマンドレットでは、オブジェクトのメソッドはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="feaf9-186">This cmdlet does not export the methods of the object.</span></span>

## <span data-ttu-id="feaf9-187">関連リンク</span><span class="sxs-lookup"><span data-stu-id="feaf9-187">RELATED LINKS</span></span>

[<span data-ttu-id="feaf9-188">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="feaf9-188">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="feaf9-189">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="feaf9-189">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="feaf9-190">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="feaf9-190">Import-Csv</span></span>](Import-Csv.md)