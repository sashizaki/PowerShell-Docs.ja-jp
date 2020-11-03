---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 10/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/export-counter?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Counter
ms.openlocfilehash: 54498eb504a1d13a5b96a2583b5e5d6e4c08735e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220776"
---
# <span data-ttu-id="92ccf-103">Export-Counter</span><span class="sxs-lookup"><span data-stu-id="92ccf-103">Export-Counter</span></span>

## <span data-ttu-id="92ccf-104">概要</span><span class="sxs-lookup"><span data-stu-id="92ccf-104">SYNOPSIS</span></span>
<span data-ttu-id="92ccf-105">パフォーマンスカウンターデータをログファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="92ccf-105">Exports performance counter data to log files.</span></span>

## <span data-ttu-id="92ccf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="92ccf-106">SYNTAX</span></span>

```
Export-Counter [-Path] <String> [-FileFormat <String>] [-MaxSize <UInt32>]
 -InputObject <PerformanceCounterSampleSet[]> [-Force] [-Circular] [<CommonParameters>]
```

## <span data-ttu-id="92ccf-107">Description</span><span class="sxs-lookup"><span data-stu-id="92ccf-107">DESCRIPTION</span></span>

<span data-ttu-id="92ccf-108">`Export-Counter`コマンドレットは、パフォーマンスカウンターデータ (PerformanceCounterSampleSet オブジェクト) をバイナリパフォーマンスログ (.blg)、コンマ区切り値 (.csv)、またはタブ区切り値 (.tsv) 形式のログファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="92ccf-108">The `Export-Counter` cmdlet exports performance counter data (PerformanceCounterSampleSet objects) to log files in binary performance log (.blg), comma-separated value (.csv), or tab-separated value (.tsv) format.</span></span> <span data-ttu-id="92ccf-109">このコマンドレットを使用して、パフォーマンスカウンターデータをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="92ccf-109">You use this cmdlet to log performance counter data.</span></span>

<span data-ttu-id="92ccf-110">`Export-Counter`コマンドレットは、コマンド `Get-Counter` レットとコマンドレットによって返されるデータをエクスポートするように設計されてい `Import-Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-110">The `Export-Counter` cmdlet is designed to export data that is returned by the `Get-Counter` and `Import-Counter` cmdlets.</span></span>

<span data-ttu-id="92ccf-111">このコマンドレットは、windows 7、Windows Server 2008 R2、およびそれ以降のバージョンの Windows でのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-111">This cmdlet runs only on Windows 7, Windows Server 2008 R2, and later versions of Windows.</span></span>

## <span data-ttu-id="92ccf-112">例</span><span class="sxs-lookup"><span data-stu-id="92ccf-112">EXAMPLES</span></span>

### <span data-ttu-id="92ccf-113">例 1: カウンターデータをファイルにエクスポートする</span><span class="sxs-lookup"><span data-stu-id="92ccf-113">EXAMPLE 1: Export counter data to a file</span></span>

<span data-ttu-id="92ccf-114">この例では、カウンターデータを .BLG ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="92ccf-114">This example exports counter data to a BLG file.</span></span>

```powershell
Get-Counter "\Processor(*)\% Processor Time" | Export-Counter -Path $home\Counters.blg
```

<span data-ttu-id="92ccf-115">コマンドは、コマンド `Get-Counter` レットを使用してプロセッサ時間データを収集します。</span><span class="sxs-lookup"><span data-stu-id="92ccf-115">The command uses the `Get-Counter` cmdlet to collect processor time data.</span></span> <span data-ttu-id="92ccf-116">パイプライン演算子 (|) を使用して、データをコマンドレットに送信し `Export-Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-116">It uses a pipeline operator (|) to send the data to the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="92ccf-117">この `Export-Counter` コマンドは、 **Path** 変数を使用して出力ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="92ccf-117">The `Export-Counter` command uses the **Path** variable to specify the output file.</span></span>

<span data-ttu-id="92ccf-118">データセットは非常に大きくなる可能性があるため、この例では、パイプラインを介してにデータを送信し `Export-Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-118">Because the data set might be very large, this example sends the data to `Export-Counter` through the pipeline.</span></span> <span data-ttu-id="92ccf-119">データが変数に保存されている場合は、膨大な量のメモリを使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="92ccf-119">If the data were saved in a variable, you might use a disproportionate amount of memory.</span></span>

### <span data-ttu-id="92ccf-120">例 2: ファイルをカウンターファイル形式にエクスポートする</span><span class="sxs-lookup"><span data-stu-id="92ccf-120">Example 2: Export a file to a counter file format</span></span>

<span data-ttu-id="92ccf-121">この例では、CSV ファイルをカウンターデータ .BLG 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="92ccf-121">This example converts a CSV file to a counter data BLG format.</span></span>

<span data-ttu-id="92ccf-122">`Import-Counter`コマンドレットは、ファイルからパフォーマンスカウンターデータをインポートし `Threads.csv` ます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-122">The `Import-Counter` cmdlet imports performance counter data from the `Threads.csv` file.</span></span> <span data-ttu-id="92ccf-123">この例では、このファイルが以前にコマンドレットを使用してエクスポートされたことを前提としてい `Export-Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-123">The example presumes that this file was previously exported by using the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="92ccf-124">パイプライン演算子 () は、インポートされた `|` データをコマンドレットに送信し `Export-Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-124">A pipeline operator (`|`) sends the imported data to the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="92ccf-125">このコマンドは、 **Path** パラメーターを使用して、出力ファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="92ccf-125">The command uses the **Path** parameter to specify the location of the output file.</span></span> <span data-ttu-id="92ccf-126">この例で **は、** コマンドレットを使用して、 **MaxSize** `Export-Counter` 1 GB でラップする循環ログを作成しています。</span><span class="sxs-lookup"><span data-stu-id="92ccf-126">It uses the **Circular** and **MaxSize** parameters to direct the `Export-Counter` cmdlet to create a circular log that wraps at 1 GB.</span></span> <span data-ttu-id="92ccf-127">**MaxSize** パラメーターは mb 単位で表されます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-127">The **MaxSize** parameter is expressed in megabytes.</span></span>

```powershell
$1GBInMB = 1024 # 1GB = 1024MB
Import-Counter Threads.csv | Export-Counter -Path ThreadTest.blg -Circular -MaxSize $1GBInMB
```

### <span data-ttu-id="92ccf-128">例 3: リモートコンピューターからカウンターデータを取得し、そのデータをファイルに保存する</span><span class="sxs-lookup"><span data-stu-id="92ccf-128">Example 3: Get counter data from a remote computer and save the data to a file</span></span>

<span data-ttu-id="92ccf-129">この例は、リモート コンピューターからパフォーマンス カウンター データを取得し、そのデータをリモート コンピューター上のファイルに保存する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="92ccf-129">This example shows how to get performance counter data from a remote computer and save the data in a file on the remote computer.</span></span>

<span data-ttu-id="92ccf-130">最初のコマンドは、コマンドレットを使用して、 `Get-Counter` リモートコンピューター Server01 からワーキングセットカウンターデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="92ccf-130">The first command uses the `Get-Counter` cmdlet to collect working set counter data from Server01, a remote computer.</span></span> <span data-ttu-id="92ccf-131">このコマンドは、データを変数に保存し `$C` ます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-131">The command saves the data in the `$C` variable.</span></span>

<span data-ttu-id="92ccf-132">2番目のコマンドは、パイプライン演算子 () を使用して、 `|` のデータをコマンドレットに送信します。これにより、 `$C` `Export-Counter` `Workingset.blg` Server01 コンピューターの Perf 共有内のファイルにデータが保存されます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-132">The second command uses a pipeline operator (`|`) to send the data in `$C` to the `Export-Counter` cmdlet, which saves it in the `Workingset.blg` file in the Perf share of the Server01 computer.</span></span>

```powershell
$C = Get-Counter -ComputerName Server01 -Counter "\Process(*)\Working Set - Private" -MaxSamples $C | Export-Counter -Path \\Server01\Perf\WorkingSet.blg
```

```Output
20
```

### <span data-ttu-id="92ccf-133">例 4: 既存のデータを再ログする</span><span class="sxs-lookup"><span data-stu-id="92ccf-133">Example 4: Re-log existing data</span></span>

<span data-ttu-id="92ccf-134">この例では、 `Import-Counter` コマンドレットとコマンドレットを使用して、既存のデータを再ログに記録する方法を示し `Export-Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-134">This example shows how to use the `Import-Counter` and `Export-Counter` cmdlets to re-log existing data.</span></span>

<span data-ttu-id="92ccf-135">最初のコマンドは、 `Import-Counter` コマンドレットを使用して、データディスクの .blg ログからパフォーマンスカウンターデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="92ccf-135">The first command uses the `Import-Counter` cmdlet to import performance counter data from the DiskSpace.blg log.</span></span> <span data-ttu-id="92ccf-136">データは変数に保存され `$All` ます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-136">It saves the data in the `$All` variable.</span></span> <span data-ttu-id="92ccf-137">このファイル \% には、企業内の200台以上のリモートコンピューターにおける "LogicalDisk Free Space" カウンターのサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="92ccf-137">This file contains samples of the "LogicalDisk\% Free Space" counter on more than 200 remote computers in the enterprise.</span></span>

<span data-ttu-id="92ccf-138">2番目のコマンドは、コマンドレットを使用し `Where-Object` て、 **CookedValue** が 15 (パーセント) 未満のオブジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="92ccf-138">The second command uses the `Where-Object` cmdlet to select objects with **CookedValue** of less than 15 (percent).</span></span> <span data-ttu-id="92ccf-139">このコマンドは、変数に結果を保存し `$LowSpace` ます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-139">The command saves the results in the `$LowSpace` variable.</span></span>

<span data-ttu-id="92ccf-140">3番目のコマンドは、パイプライン演算子 () を使用して、 `|` 変数内のデータを `$LowSpace` コマンドレットに送信し `Export-Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-140">The third command uses a pipeline operator (`|`) to send the data in the `$LowSpace` variable to the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="92ccf-141">このコマンドは、 **Path** パラメーターを使用して、選択したデータを LowDiskSpace.blg ファイルに記録する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="92ccf-141">The command uses the **Path** parameter to indicate that the selected data should be logged in the LowDiskSpace.blg file.</span></span>

```powershell
$All = Import-Counter DiskSpace.blg
$LowSpace = $All | Where-Object {$_.CounterSamples.CookedValue -lt 15}
$LowSpace | Export-Counter -Path LowDiskSpace.blg
```

## <span data-ttu-id="92ccf-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="92ccf-142">PARAMETERS</span></span>

### <span data-ttu-id="92ccf-143">-円形</span><span class="sxs-lookup"><span data-stu-id="92ccf-143">-Circular</span></span>

<span data-ttu-id="92ccf-144">出力ファイルが先入れ先出し (FIFO) 形式の循環ログであることを示します。</span><span class="sxs-lookup"><span data-stu-id="92ccf-144">Indicates that the output file is a circular log with first in, first out (FIFO) format.</span></span>
<span data-ttu-id="92ccf-145">このパラメーターを含める場合は、 **MaxSize** パラメーターが必須となります。</span><span class="sxs-lookup"><span data-stu-id="92ccf-145">When you include this parameter, the **MaxSize** parameter is required.</span></span>

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

### <span data-ttu-id="92ccf-146">-FileFormat</span><span class="sxs-lookup"><span data-stu-id="92ccf-146">-FileFormat</span></span>

<span data-ttu-id="92ccf-147">出力ログ ファイルの出力形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="92ccf-147">Specifies the output format of the output log file.</span></span>

<span data-ttu-id="92ccf-148">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="92ccf-148">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="92ccf-149">CSV</span><span class="sxs-lookup"><span data-stu-id="92ccf-149">CSV</span></span>
- <span data-ttu-id="92ccf-150">TSV</span><span class="sxs-lookup"><span data-stu-id="92ccf-150">TSV</span></span>
- <span data-ttu-id="92ccf-151">.BLG</span><span class="sxs-lookup"><span data-stu-id="92ccf-151">BLG</span></span>

<span data-ttu-id="92ccf-152">既定値は BLG です。</span><span class="sxs-lookup"><span data-stu-id="92ccf-152">The default value is BLG.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92ccf-153">-Force</span><span class="sxs-lookup"><span data-stu-id="92ccf-153">-Force</span></span>

<span data-ttu-id="92ccf-154">**Path** パラメーターで指定された場所に存在する場合、既存のファイルを上書きして置き換えます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-154">Overwrites and replaces an existing file if one exists in the location specified by the **Path** parameter.</span></span>

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

### <span data-ttu-id="92ccf-155">-InputObject</span><span class="sxs-lookup"><span data-stu-id="92ccf-155">-InputObject</span></span>

<span data-ttu-id="92ccf-156">エクスポートするカウンターデータを配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="92ccf-156">Specifies, as an array, the counter data to export.</span></span> <span data-ttu-id="92ccf-157">データを含む変数、またはやコマンドレットなどのデータを取得するコマンドを入力し `Get-Counter` `Import-Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-157">Enter a variable that contains the data or a command that gets the data, such as the `Get-Counter` or `Import-Counter` cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="92ccf-158">-MaxSize</span><span class="sxs-lookup"><span data-stu-id="92ccf-158">-MaxSize</span></span>

<span data-ttu-id="92ccf-159">出力ファイルの最大サイズをメガバイト (MB) 単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="92ccf-159">Specifies the maximum size of the output file in megabytes (MB).</span></span>

<span data-ttu-id="92ccf-160">**循環** パラメーターが指定されている場合、ログファイルが指定された最大サイズに達すると、新しいエントリが追加されると、最も古いエントリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-160">If the **Circular** parameter is specified, then when the log file reaches the specified maximum size, the oldest entries are deleted as newer ones are added.</span></span> <span data-ttu-id="92ccf-161">**循環** パラメーターが指定されていない場合、ログファイルが指定された最大サイズに達すると、新しいデータは追加されず、コマンドレットは終了しないエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="92ccf-161">If the **Circular** parameter is not specified, then when the log file reaches the specified maximum size, no new data is added and the cmdlet generates a non-terminating error.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="92ccf-162">-Path</span><span class="sxs-lookup"><span data-stu-id="92ccf-162">-Path</span></span>

<span data-ttu-id="92ccf-163">出力ファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="92ccf-163">Specifies the path and file name of the output file.</span></span> <span data-ttu-id="92ccf-164">ローカルコンピューター上の相対パスまたは絶対パス、またはリモートコンピューターへの汎用名前付け規則 (UNC) パスを入力し `\\Computer\Share\file.blg` ます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-164">Enter a relative or absolute path on the local computer, or a Uniform Naming Convention (UNC) path to a remote computer, such as `\\Computer\Share\file.blg`.</span></span> <span data-ttu-id="92ccf-165">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="92ccf-165">This parameter is required.</span></span>

<span data-ttu-id="92ccf-166">ファイル形式は、パスのファイル名拡張子ではなく、 **FileFormat** パラメーターの値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="92ccf-166">The file format is determined by the value of the **FileFormat** parameter, not by the file name extension in the path.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="92ccf-167">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="92ccf-167">CommonParameters</span></span>

<span data-ttu-id="92ccf-168">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="92ccf-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="92ccf-169">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92ccf-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="92ccf-170">入力</span><span class="sxs-lookup"><span data-stu-id="92ccf-170">INPUTS</span></span>

### <span data-ttu-id="92ccf-171">PerformanceCounterSampleSet (Microsoft. PowerShell)</span><span class="sxs-lookup"><span data-stu-id="92ccf-171">Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet</span></span>

<span data-ttu-id="92ccf-172">パイプを使用して `Get-Counter` 、または `Import-Counter` このコマンドレットに対してパフォーマンスカウンターデータをパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-172">You can pipe performance counter data from `Get-Counter` or `Import-Counter` to this cmdlet.</span></span>

## <span data-ttu-id="92ccf-173">出力</span><span class="sxs-lookup"><span data-stu-id="92ccf-173">OUTPUTS</span></span>

### <span data-ttu-id="92ccf-174">なし</span><span class="sxs-lookup"><span data-stu-id="92ccf-174">None</span></span>

## <span data-ttu-id="92ccf-175">注</span><span class="sxs-lookup"><span data-stu-id="92ccf-175">NOTES</span></span>

<span data-ttu-id="92ccf-176">ログ ファイル ジェネレーターは、すべての入力オブジェクトが同じカウンター パスを保持し、オブジェクトが時間の昇順に並んでいることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="92ccf-176">The log file generator expects that all input objects have the same counter path and that the objects are arranged in ascending time order.</span></span>

<span data-ttu-id="92ccf-177">カウンターの種類と、最初の入力オブジェクトのパスによって、ログ ファイルに記録されるプロパティが決まります。</span><span class="sxs-lookup"><span data-stu-id="92ccf-177">The counter type and path of the first input object determines the properties recorded in the log file.</span></span> <span data-ttu-id="92ccf-178">その他の入力オブジェクトに記録されたプロパティの値がない場合、プロパティ フィールドは空になります。</span><span class="sxs-lookup"><span data-stu-id="92ccf-178">If other input objects do not have a value for a recorded property, the property field is empty.</span></span> <span data-ttu-id="92ccf-179">オブジェクトに記録されていないプロパティ値がある場合、余分なプロパティ値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-179">If the objects have property values that were not recorded, the extra property values are ignored.</span></span>

<span data-ttu-id="92ccf-180">パフォーマンスモニターは、が生成するすべてのログを読み取ることができない可能性があり `Export-Counter` ます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-180">Performance Monitor might not be able to read all logs that `Export-Counter` generates.</span></span> <span data-ttu-id="92ccf-181">たとえば、パフォーマンスモニターでは、すべてのオブジェクトが同じパスを持ち、すべてのオブジェクトが同じ時間間隔で区切られている必要があります。</span><span class="sxs-lookup"><span data-stu-id="92ccf-181">For instance, Performance Monitor requires that all objects have the same path and that all objects are separated by the same time interval.</span></span>

<span data-ttu-id="92ccf-182">`Import-Counter`コマンドレットに **ComputerName** パラメーターがありません。</span><span class="sxs-lookup"><span data-stu-id="92ccf-182">The `Import-Counter` cmdlet does not have a **ComputerName** parameter.</span></span> <span data-ttu-id="92ccf-183">ただし、コンピューターがリモートの Windows PowerShell Windows PowerShell 用に構成されている場合は、 `Invoke-Command` コマンドレットを使用して `Import-Counter` リモートコンピューターでコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="92ccf-183">However, if the computer is configured for remote Windows PowerShell Windows PowerShell, you can use the `Invoke-Command` cmdlet to run an `Import-Counter` command on a remote computer.</span></span>

## <span data-ttu-id="92ccf-184">関連リンク</span><span class="sxs-lookup"><span data-stu-id="92ccf-184">RELATED LINKS</span></span>

[<span data-ttu-id="92ccf-185">Get-Counter</span><span class="sxs-lookup"><span data-stu-id="92ccf-185">Get-Counter</span></span>](Get-Counter.md)

[<span data-ttu-id="92ccf-186">Import-Counter</span><span class="sxs-lookup"><span data-stu-id="92ccf-186">Import-Counter</span></span>](Import-Counter.md)
