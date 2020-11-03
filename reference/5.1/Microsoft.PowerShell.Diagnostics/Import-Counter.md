---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/import-counter?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Counter
ms.openlocfilehash: 837f6b4b3b2869c6f74b3b02904dd43b73f6bcd5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212672"
---
# <span data-ttu-id="b3877-103">Import-Counter</span><span class="sxs-lookup"><span data-stu-id="b3877-103">Import-Counter</span></span>

## <span data-ttu-id="b3877-104">概要</span><span class="sxs-lookup"><span data-stu-id="b3877-104">SYNOPSIS</span></span>
<span data-ttu-id="b3877-105">パフォーマンスカウンターのログファイルをインポートし、ログ内の各カウンターサンプルを表すオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b3877-105">Imports performance counter log files and creates the objects that represent each counter sample in the log.</span></span>

## <span data-ttu-id="b3877-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b3877-106">SYNTAX</span></span>

### <span data-ttu-id="b3877-107">GetCounterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="b3877-107">GetCounterSet (Default)</span></span>

```
Import-Counter [-Path] <String[]> [-StartTime <DateTime>] [-EndTime <DateTime>] [-Counter <String[]>]
 [-MaxSamples <Int64>] [<CommonParameters>]
```

### <span data-ttu-id="b3877-108">ListSetSet</span><span class="sxs-lookup"><span data-stu-id="b3877-108">ListSetSet</span></span>

```
Import-Counter [-Path] <String[]> -ListSet <String[]> [<CommonParameters>]
```

### <span data-ttu-id="b3877-109">概要セット</span><span class="sxs-lookup"><span data-stu-id="b3877-109">SummarySet</span></span>

```
Import-Counter [-Path] <String[]> [-Summary] [<CommonParameters>]
```

## <span data-ttu-id="b3877-110">Description</span><span class="sxs-lookup"><span data-stu-id="b3877-110">DESCRIPTION</span></span>

<span data-ttu-id="b3877-111">この **コマンドレット** は、パフォーマンスカウンターのログファイルからパフォーマンスカウンターデータをインポートし、ファイル内の各カウンターサンプル用にオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b3877-111">The **Import-Counter** cmdlet imports performance counter data from performance counter log files and creates objects for each counter sample in the file.</span></span>
<span data-ttu-id="b3877-112">作成される **PerformanceCounterSampleSet** オブジェクトは、パフォーマンスカウンターデータを収集するときに、 **counter** が返すオブジェクトと同じです。</span><span class="sxs-lookup"><span data-stu-id="b3877-112">The **PerformanceCounterSampleSet** objects that it creates are identical to the objects that **Get-Counter** returns when it collects performance counter data.</span></span>

<span data-ttu-id="b3877-113">データは、コンマ区切り値 (.csv)、タブ区切り値 (.tsv)、およびバイナリ パフォーマンス ログ (.blg) のパフォーマンス ログ ファイルからインポートできます。</span><span class="sxs-lookup"><span data-stu-id="b3877-113">You can import data from comma-separated value (.csv), tab-separated value ( .tsv), and binary performance log (.blg) performance log files.</span></span>
<span data-ttu-id="b3877-114">.Blg ファイルを使用する場合は、各コマンドで最大32個のファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="b3877-114">If you are using .blg files, you can import up to 32 files in each command.</span></span>
<span data-ttu-id="b3877-115">インポートしたデータをフィルター処理するには、 **インポートカウンター** のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3877-115">You can use the parameters of **Import-Counter** to filter the data that you import.</span></span>

<span data-ttu-id="b3877-116">この機能を使用すると、Get-Counter および Export-Counter のコマンドレットと共に、Windows PowerShell 内のパフォーマンスカウンターデータの収集、エクスポート、インポート、結合、フィルター、操作、および再エクスポートを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b3877-116">Along with the Get-Counter and Export-Counter cmdlets, this feature lets you collect, export, import, combine, filter, manipulate, and re-export performance counter data within Windows PowerShell.</span></span>

## <span data-ttu-id="b3877-117">例</span><span class="sxs-lookup"><span data-stu-id="b3877-117">EXAMPLES</span></span>

### <span data-ttu-id="b3877-118">例 1: ファイルからすべてのカウンターデータをインポートする</span><span class="sxs-lookup"><span data-stu-id="b3877-118">Example 1: Import all counter data from a file</span></span>

```powershell
$Data = Import-Counter -Path ProcessorData.csv
```

<span data-ttu-id="b3877-119">このコマンドは、ProcessorData.csv ファイルから $Data 変数にすべてのカウンターデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="b3877-119">This command imports all counter data from the ProcessorData.csv file into the $Data variable.</span></span>

### <span data-ttu-id="b3877-120">例 2: ファイルから特定のカウンターデータをインポートする</span><span class="sxs-lookup"><span data-stu-id="b3877-120">Example 2: Import specific counter data from a file</span></span>

```
PS C:\> $I = Import-Counter -Path "ProcessorData.blg" -Counter "\\SERVER01\Processor(_Total)\Interrupts/sec"
```

<span data-ttu-id="b3877-121">このコマンドは、ProcessorData. .blg ファイルから $I 変数に **"Processor (_total) \ 割り込み/sec"** カウンターデータのみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="b3877-121">This command imports only the **"Processor(_total)\Interrupts/sec"** counter data from the ProcessorData.blg file into the $I variable.</span></span>

### <span data-ttu-id="b3877-122">例 3: パフォーマンスカウンターからデータを選択してファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="b3877-122">Example 3: Select data from a performance counter then export it to a file</span></span>

```
The first command uses **Import-Counter** to import all of the performance counter data from the ProcessorData.blg files. The command saves the data in the $Data variable.
PS C:\> $Data = Import-Counter .\ProcessorData.blg

The second command displays the counter paths in the $Data variable. To get the display shown in the command output, the example uses the Format-Table cmdlet to format as a table the counter paths of the first counter in the $Data variable.
PS C:\> $Data[0].CounterSamples | Format-Table -Property Path

Path
----
\\SERVER01\Processor(_Total)\DPC Rate
\\SERVER01\Processor(1)\DPC Rate
\\SERVER01\Processor(0)\DPC Rate
\\SERVER01\Processor(_Total)\% Idle Time
\\SERVER01\Processor(1)\% Idle Time
\\SERVER01\Processor(0)\% Idle Time
\\SERVER01\Processor(_Total)\% C3 Time
\\SERVER01\Processor(1)\% C3 Time

The third command gets the counter paths that end in "Interrupts/sec" and saves the paths in the $IntCtrs variable. It uses the Where-Object cmdlet to filter the counter paths and the ForEach-Object cmdlet to get only the value of the **Path** property of each selected path object.
PS C:\> $IntCtrs = $Data[0].Countersamples | Where-Object {$_.Path -like "*Interrupts/sec"} | ForEach-Object {$_.Path}

The fourth command displays the selected counter paths in the $IntCtrs variable.
PS C:\> $IntCtrs

\\SERVER01\Processor(_Total)\Interrupts/sec
\\SERVER01\Processor(1)\Interrupts/sec
\\SERVER01\Processor(0)\Interrupts/sec

The fifth command uses the **Import-Counter** cmdlet to import the data. It uses the $IntCtrs variable as the value of the *Counter* parameter to import only data for the counter paths in $IntCtrs.
PS C:\> $I = Import-Counter -Path .\ProcessorData.blg -Counter $intCtrs

The sixth command uses the Export-Counter cmdlet to export the data to the Interrupts.csv file.
PS C:\> $I | Export-Counter -Path .\Interrupts.csv -Format CSV
```

<span data-ttu-id="b3877-123">この例は、パフォーマンス カウンター ログ ファイル (.blg) からデータを選択し、そのデータを .csv ファイルにエクスポートする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b3877-123">This example shows how to select data from a performance counter log file (.blg) and then export the selected data to a .csv file.</span></span>
<span data-ttu-id="b3877-124">最初の4つのコマンドは、ファイルからカウンターパスを取得し、$Data という名前の変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="b3877-124">The first four commands get the counter paths from the file and save them in the variable named $Data.</span></span>
<span data-ttu-id="b3877-125">最後の 2 つのコマンドは、選択されたデータをインポートし、選択されたデータのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b3877-125">The last two commands import selected data and then export only the selected data.</span></span>

### <span data-ttu-id="b3877-126">例 4: インポートされたカウンターセットのグループ内のすべてのカウンターパスを表示する</span><span class="sxs-lookup"><span data-stu-id="b3877-126">Example 4: Display all counter paths in a group of imported counter sets</span></span>

```
The first command uses the *ListSet* parameter of the **Import-Counter** cmdlet to get all of the counter sets that are represented in a counter data file.
PS C:\> Import-Counter -Path ProcessorData.csv -ListSet *

CounterSetName     : Processor
MachineName        : \\SERVER01
CounterSetType     : MultiInstance
Description        :
Paths              : {\\SERVER01\Processor(*)\DPC Rate, \\SERVER01\Processor(*)\% Idle Time, \\SERVER01
\Processor(*)\% C3 Time, \\SERVER01\Processor(*)\% Interrupt Time...}
PathsWithInstances : {\\SERVER01\Processor(_Total)\DPC Rate, \\SERVER01\Processor(1)\DPC Rate, \\SERVER01
\Processor(0)\DPC Rate, \\SERVER01\Processor(_Total)\% Idle Time...}
Counter            : {\\SERVER01\Processor(*)\DPC Rate, \\SERVER01\Processor(*)\% Idle Time, \\SERVER01
\Processor(*)\% C3 Time, \\SERVER01\Processor(*)\% Interrupt Time...}

The second command gets all of the counter paths from the list set.
PS C:\> Import-Counter -Path ProcessorData.csv -ListSet * | ForEach-Object {$_.Paths}

\\SERVER01\Processor(*)\DPC Rate
\\SERVER01\Processor(*)\% Idle Time
\\SERVER01\Processor(*)\% C3 Time
\\SERVER01\Processor(*)\% Interrupt Time
\\SERVER01\Processor(*)\% C2 Time
\\SERVER01\Processor(*)\% User Time
\\SERVER01\Processor(*)\% C1 Time
\\SERVER01\Processor(*)\% Processor Time
\\SERVER01\Processor(*)\C1 Transitions/sec
\\SERVER01\Processor(*)\% DPC Time
\\SERVER01\Processor(*)\C2 Transitions/sec
\\SERVER01\Processor(*)\% Privileged Time
\\SERVER01\Processor(*)\C3 Transitions/sec
\\SERVER01\Processor(*)\DPCs Queued/sec
\\SERVER01\Processor(*)\Interrupts/sec
```

<span data-ttu-id="b3877-127">この例は、インポートされたカウンター セットのグループに含まれているカウンター パスをすべて表示する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b3877-127">This example shows how to display all the counter paths in a group of imported counter sets.</span></span>

### <span data-ttu-id="b3877-128">例 5: タイムスタンプの範囲からカウンターデータをインポートする</span><span class="sxs-lookup"><span data-stu-id="b3877-128">Example 5: Import counter data from a range of time stamps</span></span>

```
The first command lists in a table the time stamps of all of the data in the ProcessorData.blg file.
PS C:\> Import-Counter -Path ".\disk.blg" | Format-Table -Property Timestamp

The second command saves particular time stamps in the $Start and $End variables. The strings are cast to **DateTime** objects.
PS C:\> $Start = [datetime]"7/9/2008 3:47:00 PM"; $End = [datetime]"7/9/2008 3:47:59 PM"

The third command uses the **Import-Counter** cmdlet to get only counter data that has a time stamp between the start and end times (inclusive). The command uses the *StartTime* and *EndTime* parameters of **Import-Counter** to specify the range.
PS C:\> Import-Counter -Path Disk.blg -StartTime $start -EndTime $end
```

<span data-ttu-id="b3877-129">この例では、タイム スタンプがコマンドで指定された開始日時と終了日時の間であるカウンター データのみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="b3877-129">This example imports only the counter data that has a time stamp between the starting an ending ranges specified in the command.</span></span>

### <span data-ttu-id="b3877-130">例 6: 指定した数の古いサンプルをパフォーマンスカウンターログファイルからインポートする</span><span class="sxs-lookup"><span data-stu-id="b3877-130">Example 6: Import a specified number of the oldest samples from a performance counter log file</span></span>

```
The first command uses the **Import-Counter** cmdlet to import the first (oldest) five samples from the Disk.blg file. The command uses the *MaxSamples* parameter to limit the import to five counter samples.
PS C:\> Import-Counter -Path "Disk.blg" -MaxSamples 5

The second command uses array notation and the Windows PowerShell range operator (..) to get the last five counter samples from the file. These are the five newest samples.
PS C:\> (Import-Counter -Path Disk.blg)[-1 .. -5]
```

<span data-ttu-id="b3877-131">この例は、最も古いファイル 5 つと最も新しいファイル 5 つをパフォーマンス カウンター ログ ファイルからインポートする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b3877-131">This example shows how to import the five oldest and five newest samples from a performance counter log file.</span></span>

### <span data-ttu-id="b3877-132">例 7: ファイルからカウンターデータの概要を取得する</span><span class="sxs-lookup"><span data-stu-id="b3877-132">Example 7: Get a summary of counter data from a file</span></span>

```
PS C:\> Import-Counter "D:\Samples\Memory.blg" -Summary

OldestRecord            NewestRecord            SampleCount
------------            ------------            -----------
7/10/2008 2:59:18 PM    7/10/2008 3:00:27 PM    1000
```

<span data-ttu-id="b3877-133">このコマンドは、 *Import-Counter* コマンドレットの **Summary** パラメーターを使用して、Memory.blg ファイルからカウンター データの概要を取得します。</span><span class="sxs-lookup"><span data-stu-id="b3877-133">This command uses the *Summary* parameter of the **Import-Counter** cmdlet to get a summary of the counter data in the Memory.blg file.</span></span>

### <span data-ttu-id="b3877-134">例 8: パフォーマンスカウンターログファイルを更新する</span><span class="sxs-lookup"><span data-stu-id="b3877-134">Example 8: Update a performance counter log file</span></span>

```
The first command uses the *ListSet* parameter of **Import-Counter** to get the counters in OldData.blg, an existing counter log file. The command uses a pipeline operator (|) to send the data to a ForEach-Object command that gets only the values of the **PathsWithInstances** property of each object
PS C:\> $Counters = Import-Counter OldData.blg -ListSet * | ForEach-Object {$_.PathsWithInstances}

The second command gets updated data for the counters in the $Counters variable. It uses the Get-Counter cmdlet to get a current sample, and then export the results to the NewData.blg file.
PS C:\> Get-Counter -Counter $Counters -MaxSamples 20 | Export-Counter C:\Logs\NewData.blg
```

<span data-ttu-id="b3877-135">この例は、パフォーマンス カウンター ログ ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="b3877-135">This example updates a performance counter log file.</span></span>

### <span data-ttu-id="b3877-136">例 9: 複数のファイルからパフォーマンスログデータをインポートして保存する</span><span class="sxs-lookup"><span data-stu-id="b3877-136">Example 9: Import performance log data from multiple files and then save it</span></span>

```
PS C:\> $Counters = "D:\test\pdata.blg", "D:\samples\netlog.blg" | Import-Counter
```

<span data-ttu-id="b3877-137">このコマンドは、2 つのログからパフォーマンス ログ データをインポートし、データを $Counters 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="b3877-137">This command imports performance log data from two logs and saves the data in the $Counters variable.</span></span>
<span data-ttu-id="b3877-138">このコマンドは、パイプライン演算子 (|) を使用して、パフォーマンス ログ パスを Import-Counter に送信します。Import-Counter は、指定されたそのパスからデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="b3877-138">The command uses a pipeline operator to send the performance log paths to Import-Counter, which imports the data from the specified paths.</span></span>

<span data-ttu-id="b3877-139">各パスが引用符で囲まれており、パスが互いにコンマで区切られていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b3877-139">Notice that each path is enclosed in quotation marks and that the paths are separated from each other by a comma.</span></span>

## <span data-ttu-id="b3877-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b3877-140">PARAMETERS</span></span>

### <span data-ttu-id="b3877-141">-カウンター</span><span class="sxs-lookup"><span data-stu-id="b3877-141">-Counter</span></span>

<span data-ttu-id="b3877-142">文字列配列として、パフォーマンスカウンターを指定します。</span><span class="sxs-lookup"><span data-stu-id="b3877-142">Specifies, as a string array, the performance counters.</span></span>
<span data-ttu-id="b3877-143">既定では、 **インポートカウンター** は、入力ファイル内のすべてのカウンターからすべてのデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="b3877-143">By default, **Import-Counter** imports all data from all counters in the input files.</span></span>
<span data-ttu-id="b3877-144">1 つまたは複数のカウンター パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="b3877-144">Enter one or more counter paths.</span></span>
<span data-ttu-id="b3877-145">ワイルドカードはパスの  部分で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3877-145">Wildcards are permitted in the Instance part of the path.</span></span>

<span data-ttu-id="b3877-146">各カウンター パスの形式は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b3877-146">Each counter path has the following format.</span></span>
<span data-ttu-id="b3877-147">パスには ComputerName 値が必要です。</span><span class="sxs-lookup"><span data-stu-id="b3877-147">The ComputerName value is required in the path.</span></span>
<span data-ttu-id="b3877-148">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b3877-148">For instance:</span></span>

- `\\<ComputerName>\<CounterSet>(<Instance>)\<CounterName>`

<span data-ttu-id="b3877-149">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b3877-149">For example:</span></span>

- `\\Server01\Processor(2)\% User Time`
- `\\Server01\Processor(*)\% Processor Time`

```yaml
Type: System.String[]
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: All counter
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b3877-150">-EndTime</span><span class="sxs-lookup"><span data-stu-id="b3877-150">-EndTime</span></span>

<span data-ttu-id="b3877-151">このコマンドレットが *StartTime* とこのパラメーターのタイムスタンプの間のカウンターデータをインポートする終了日時を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3877-151">Specifies an end date and time that this cmdlet imports counter data between the *StartTime* and this parameter timestamps.</span></span>
<span data-ttu-id="b3877-152">Get-Date コマンドレットによって作成された日時などの **DateTime** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="b3877-152">Enter a **DateTime** object, such as one created by the Get-Date cmdlet.</span></span>
<span data-ttu-id="b3877-153">既定では、 **Import-counter** は *Path* パラメーターで指定されたファイル内のすべてのカウンターデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="b3877-153">By default, **Import-Counter** imports all counter data in the files specified by the *Path* parameter.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: No end time
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b3877-154">-ListSet</span><span class="sxs-lookup"><span data-stu-id="b3877-154">-ListSet</span></span>

<span data-ttu-id="b3877-155">エクスポートされたファイルで表されるパフォーマンスカウンターセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="b3877-155">Specifies the performance counter sets that are represented in the exported files.</span></span>
<span data-ttu-id="b3877-156">このパラメーターを指定したコマンドは、データをインポートしません。</span><span class="sxs-lookup"><span data-stu-id="b3877-156">Commands with this parameter do not import any data.</span></span>

<span data-ttu-id="b3877-157">1 つ以上のカウンター セット名を入力します。</span><span class="sxs-lookup"><span data-stu-id="b3877-157">Enter one or more counter set names.</span></span>
<span data-ttu-id="b3877-158">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3877-158">Wildcards are permitted.</span></span>
<span data-ttu-id="b3877-159">ファイル内のすべてのカウンターセットを取得するには、「」と入力 `Import-Counter -ListSet *` します。</span><span class="sxs-lookup"><span data-stu-id="b3877-159">To get all counter sets in the file, type `Import-Counter -ListSet *`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ListSetSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b3877-160">-MaxSamples</span><span class="sxs-lookup"><span data-stu-id="b3877-160">-MaxSamples</span></span>

<span data-ttu-id="b3877-161">インポートする各カウンターのサンプルの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3877-161">Specifies the maximum number of samples of each counter to import.</span></span>
<span data-ttu-id="b3877-162">既定では、 **Get カウンター** は *Path* パラメーターで指定されたファイル内のすべてのデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="b3877-162">By default, **Get-Counter** imports all of the data in the files specified by the *Path* parameter.</span></span>

```yaml
Type: System.Int64
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: No maximum
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b3877-163">-Path</span><span class="sxs-lookup"><span data-stu-id="b3877-163">-Path</span></span>

<span data-ttu-id="b3877-164">インポートするファイルのファイル パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b3877-164">Specifies the file paths of the files to be imported.</span></span>
<span data-ttu-id="b3877-165">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="b3877-165">This parameter is required.</span></span>

<span data-ttu-id="b3877-166">**Export-Counter** コマンドレットを使用してエクスポートした、.csv,,. tsv、または .blg ファイルのパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="b3877-166">Enter the path and file name of a, .csv,, .tsv, or .blg file that you exported by using the **Export-Counter** cmdlet.</span></span>
<span data-ttu-id="b3877-167">コマンドごとに、.csv ファイルまたは .tsv ファイルでは 1 つのファイルのみ、.blg ファイルでは複数 (最大 32 個) のファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b3877-167">You can specify only one .csv or .tsv file, but you can specify multiple .blg files (up to 32) in each command.</span></span>
<span data-ttu-id="b3877-168">パイプを使用してファイルパス文字列 (引用符で囲まれた) を **インポート** することもできます。</span><span class="sxs-lookup"><span data-stu-id="b3877-168">You can also pipe file path strings (in quotation marks) to **Import-Counter** .</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="b3877-169">-StartTime</span><span class="sxs-lookup"><span data-stu-id="b3877-169">-StartTime</span></span>

<span data-ttu-id="b3877-170">このコマンドレットがカウンターデータを取得する開始日時を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3877-170">Specifies the start date and time in which this cmdlet gets counter data.</span></span>
<span data-ttu-id="b3877-171">**DateTime** オブジェクトを入力します (例: **Get Date** コマンドレットによって作成されたもの)。</span><span class="sxs-lookup"><span data-stu-id="b3877-171">Enter a **DateTime** object, such as one created by the **Get-Date** cmdlet.</span></span>
<span data-ttu-id="b3877-172">既定では、 **Import-counter** は *Path* パラメーターで指定されたファイル内のすべてのカウンターデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="b3877-172">By default, **Import-Counter** imports all counter data in the files specified by the *Path* parameter.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: No start time
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b3877-173">-Summary</span><span class="sxs-lookup"><span data-stu-id="b3877-173">-Summary</span></span>

<span data-ttu-id="b3877-174">このコマンドレットが、個々のカウンターデータサンプルを取得するのではなく、インポートされたデータの概要を取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="b3877-174">Indicates that this cmdlet gets a summary of the imported data, instead of getting individual counter data samples.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SummarySet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b3877-175">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b3877-175">CommonParameters</span></span>

<span data-ttu-id="b3877-176">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b3877-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b3877-177">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3877-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b3877-178">入力</span><span class="sxs-lookup"><span data-stu-id="b3877-178">INPUTS</span></span>

### <span data-ttu-id="b3877-179">System.String</span><span class="sxs-lookup"><span data-stu-id="b3877-179">System.String</span></span>

<span data-ttu-id="b3877-180">パイプを使用して、パフォーマンスカウンターのログパスをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="b3877-180">You can pipe performance counter log paths to this cmdlet.</span></span>

## <span data-ttu-id="b3877-181">出力</span><span class="sxs-lookup"><span data-stu-id="b3877-181">OUTPUTS</span></span>

### <span data-ttu-id="b3877-182">PerformanceCounterSampleSet、microsoft. powershell... counter。 CounterFileInfo。 CounterFileInfo............。</span><span class="sxs-lookup"><span data-stu-id="b3877-182">Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet, Microsoft.PowerShell.Commands.GetCounter.CounterSet, Microsoft.PowerShell.Commands.GetCounter.CounterFileInfo</span></span>

<span data-ttu-id="b3877-183">このコマンドレットは、 **PerformanceCounterSampleSet** を返します。</span><span class="sxs-lookup"><span data-stu-id="b3877-183">This cmdlet returns a **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet** .</span></span>
<span data-ttu-id="b3877-184">*Listset* パラメーターを使用すると、このコマンドレットは、 **Microsoft. PowerShell.** ........... counter オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="b3877-184">If you use the *ListSet* parameter, this cmdlet returns a **Microsoft.PowerShell.Commands.GetCounter.CounterSet** object.</span></span>
<span data-ttu-id="b3877-185">*Summary* パラメーターを使用した場合、このコマンドレットは、 **Microsoft. PowerShell. コマンド** のオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="b3877-185">If you use the *Summary* parameter, this cmdlet returns a **Microsoft.PowerShell.Commands.GetCounter.CounterFileInfo** object.</span></span>

## <span data-ttu-id="b3877-186">注</span><span class="sxs-lookup"><span data-stu-id="b3877-186">NOTES</span></span>

* <span data-ttu-id="b3877-187">このコマンドレットには、 *ComputerName* パラメーターがありません。</span><span class="sxs-lookup"><span data-stu-id="b3877-187">This cmdlet does not have a *ComputerName* parameter.</span></span> <span data-ttu-id="b3877-188">ただし、コンピューターが Windows PowerShell リモート処理用に構成されている場合は、Invoke-Command コマンドレットを使用して、リモートコンピューターで [ **カウンターのインポート** ] コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b3877-188">However, if the computer is configured for Windows PowerShell remoting, you can use the Invoke-Command cmdlet to run an **Import-Counter** command on a remote computer.</span></span>

## <span data-ttu-id="b3877-189">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b3877-189">RELATED LINKS</span></span>

[<span data-ttu-id="b3877-190">Export-Counter</span><span class="sxs-lookup"><span data-stu-id="b3877-190">Export-Counter</span></span>](Export-Counter.md)

[<span data-ttu-id="b3877-191">Get-Counter</span><span class="sxs-lookup"><span data-stu-id="b3877-191">Get-Counter</span></span>](Get-Counter.md)
