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
# Import-Counter

## 概要
パフォーマンスカウンターのログファイルをインポートし、ログ内の各カウンターサンプルを表すオブジェクトを作成します。

## SYNTAX

### GetCounterSet (既定値)

```
Import-Counter [-Path] <String[]> [-StartTime <DateTime>] [-EndTime <DateTime>] [-Counter <String[]>]
 [-MaxSamples <Int64>] [<CommonParameters>]
```

### ListSetSet

```
Import-Counter [-Path] <String[]> -ListSet <String[]> [<CommonParameters>]
```

### 概要セット

```
Import-Counter [-Path] <String[]> [-Summary] [<CommonParameters>]
```

## Description

この **コマンドレット** は、パフォーマンスカウンターのログファイルからパフォーマンスカウンターデータをインポートし、ファイル内の各カウンターサンプル用にオブジェクトを作成します。
作成される **PerformanceCounterSampleSet** オブジェクトは、パフォーマンスカウンターデータを収集するときに、 **counter** が返すオブジェクトと同じです。

データは、コンマ区切り値 (.csv)、タブ区切り値 (.tsv)、およびバイナリ パフォーマンス ログ (.blg) のパフォーマンス ログ ファイルからインポートできます。
.Blg ファイルを使用する場合は、各コマンドで最大32個のファイルをインポートできます。
インポートしたデータをフィルター処理するには、 **インポートカウンター** のパラメーターを使用します。

この機能を使用すると、Get-Counter および Export-Counter のコマンドレットと共に、Windows PowerShell 内のパフォーマンスカウンターデータの収集、エクスポート、インポート、結合、フィルター、操作、および再エクスポートを行うことができます。

## 例

### 例 1: ファイルからすべてのカウンターデータをインポートする

```powershell
$Data = Import-Counter -Path ProcessorData.csv
```

このコマンドは、ProcessorData.csv ファイルから $Data 変数にすべてのカウンターデータをインポートします。

### 例 2: ファイルから特定のカウンターデータをインポートする

```
PS C:\> $I = Import-Counter -Path "ProcessorData.blg" -Counter "\\SERVER01\Processor(_Total)\Interrupts/sec"
```

このコマンドは、ProcessorData. .blg ファイルから $I 変数に **"Processor (_total) \ 割り込み/sec"** カウンターデータのみをインポートします。

### 例 3: パフォーマンスカウンターからデータを選択してファイルにエクスポートする

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

この例は、パフォーマンス カウンター ログ ファイル (.blg) からデータを選択し、そのデータを .csv ファイルにエクスポートする方法を示しています。
最初の4つのコマンドは、ファイルからカウンターパスを取得し、$Data という名前の変数に保存します。
最後の 2 つのコマンドは、選択されたデータをインポートし、選択されたデータのみをエクスポートします。

### 例 4: インポートされたカウンターセットのグループ内のすべてのカウンターパスを表示する

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

この例は、インポートされたカウンター セットのグループに含まれているカウンター パスをすべて表示する方法を示しています。

### 例 5: タイムスタンプの範囲からカウンターデータをインポートする

```
The first command lists in a table the time stamps of all of the data in the ProcessorData.blg file.
PS C:\> Import-Counter -Path ".\disk.blg" | Format-Table -Property Timestamp

The second command saves particular time stamps in the $Start and $End variables. The strings are cast to **DateTime** objects.
PS C:\> $Start = [datetime]"7/9/2008 3:47:00 PM"; $End = [datetime]"7/9/2008 3:47:59 PM"

The third command uses the **Import-Counter** cmdlet to get only counter data that has a time stamp between the start and end times (inclusive). The command uses the *StartTime* and *EndTime* parameters of **Import-Counter** to specify the range.
PS C:\> Import-Counter -Path Disk.blg -StartTime $start -EndTime $end
```

この例では、タイム スタンプがコマンドで指定された開始日時と終了日時の間であるカウンター データのみをインポートします。

### 例 6: 指定した数の古いサンプルをパフォーマンスカウンターログファイルからインポートする

```
The first command uses the **Import-Counter** cmdlet to import the first (oldest) five samples from the Disk.blg file. The command uses the *MaxSamples* parameter to limit the import to five counter samples.
PS C:\> Import-Counter -Path "Disk.blg" -MaxSamples 5

The second command uses array notation and the Windows PowerShell range operator (..) to get the last five counter samples from the file. These are the five newest samples.
PS C:\> (Import-Counter -Path Disk.blg)[-1 .. -5]
```

この例は、最も古いファイル 5 つと最も新しいファイル 5 つをパフォーマンス カウンター ログ ファイルからインポートする方法を示しています。

### 例 7: ファイルからカウンターデータの概要を取得する

```
PS C:\> Import-Counter "D:\Samples\Memory.blg" -Summary

OldestRecord            NewestRecord            SampleCount
------------            ------------            -----------
7/10/2008 2:59:18 PM    7/10/2008 3:00:27 PM    1000
```

このコマンドは、 *Import-Counter* コマンドレットの **Summary** パラメーターを使用して、Memory.blg ファイルからカウンター データの概要を取得します。

### 例 8: パフォーマンスカウンターログファイルを更新する

```
The first command uses the *ListSet* parameter of **Import-Counter** to get the counters in OldData.blg, an existing counter log file. The command uses a pipeline operator (|) to send the data to a ForEach-Object command that gets only the values of the **PathsWithInstances** property of each object
PS C:\> $Counters = Import-Counter OldData.blg -ListSet * | ForEach-Object {$_.PathsWithInstances}

The second command gets updated data for the counters in the $Counters variable. It uses the Get-Counter cmdlet to get a current sample, and then export the results to the NewData.blg file.
PS C:\> Get-Counter -Counter $Counters -MaxSamples 20 | Export-Counter C:\Logs\NewData.blg
```

この例は、パフォーマンス カウンター ログ ファイルを更新します。

### 例 9: 複数のファイルからパフォーマンスログデータをインポートして保存する

```
PS C:\> $Counters = "D:\test\pdata.blg", "D:\samples\netlog.blg" | Import-Counter
```

このコマンドは、2 つのログからパフォーマンス ログ データをインポートし、データを $Counters 変数に保存します。
このコマンドは、パイプライン演算子 (|) を使用して、パフォーマンス ログ パスを Import-Counter に送信します。Import-Counter は、指定されたそのパスからデータをインポートします。

各パスが引用符で囲まれており、パスが互いにコンマで区切られていることに注意してください。

## PARAMETERS

### -カウンター

文字列配列として、パフォーマンスカウンターを指定します。
既定では、 **インポートカウンター** は、入力ファイル内のすべてのカウンターからすべてのデータをインポートします。
1 つまたは複数のカウンター パスを入力します。
ワイルドカードはパスの  部分で使用できます。

各カウンター パスの形式は、次のとおりです。
パスには ComputerName 値が必要です。
次に例を示します。

- `\\<ComputerName>\<CounterSet>(<Instance>)\<CounterName>`

次に例を示します。

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

### -EndTime

このコマンドレットが *StartTime* とこのパラメーターのタイムスタンプの間のカウンターデータをインポートする終了日時を指定します。
Get-Date コマンドレットによって作成された日時などの **DateTime** オブジェクトを入力します。
既定では、 **Import-counter** は *Path* パラメーターで指定されたファイル内のすべてのカウンターデータをインポートします。

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

### -ListSet

エクスポートされたファイルで表されるパフォーマンスカウンターセットを指定します。
このパラメーターを指定したコマンドは、データをインポートしません。

1 つ以上のカウンター セット名を入力します。
ワイルドカードを使用できます。
ファイル内のすべてのカウンターセットを取得するには、「」と入力 `Import-Counter -ListSet *` します。

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

### -MaxSamples

インポートする各カウンターのサンプルの最大数を指定します。
既定では、 **Get カウンター** は *Path* パラメーターで指定されたファイル内のすべてのデータをインポートします。

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

### -Path

インポートするファイルのファイル パスを指定します。
このパラメーターは必須です。

**Export-Counter** コマンドレットを使用してエクスポートした、.csv,,. tsv、または .blg ファイルのパスとファイル名を入力します。
コマンドごとに、.csv ファイルまたは .tsv ファイルでは 1 つのファイルのみ、.blg ファイルでは複数 (最大 32 個) のファイルを指定できます。
パイプを使用してファイルパス文字列 (引用符で囲まれた) を **インポート** することもできます。

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

### -StartTime

このコマンドレットがカウンターデータを取得する開始日時を指定します。
**DateTime** オブジェクトを入力します (例: **Get Date** コマンドレットによって作成されたもの)。
既定では、 **Import-counter** は *Path* パラメーターで指定されたファイル内のすべてのカウンターデータをインポートします。

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

### -Summary

このコマンドレットが、個々のカウンターデータサンプルを取得するのではなく、インポートされたデータの概要を取得することを示します。

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

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### System.String

パイプを使用して、パフォーマンスカウンターのログパスをこのコマンドレットに渡します。

## 出力

### PerformanceCounterSampleSet、microsoft. powershell... counter。 CounterFileInfo。 CounterFileInfo............。

このコマンドレットは、 **PerformanceCounterSampleSet** を返します。
*Listset* パラメーターを使用すると、このコマンドレットは、 **Microsoft. PowerShell.** ........... counter オブジェクトを返します。
*Summary* パラメーターを使用した場合、このコマンドレットは、 **Microsoft. PowerShell. コマンド** のオブジェクトを返します。

## 注

* このコマンドレットには、 *ComputerName* パラメーターがありません。 ただし、コンピューターが Windows PowerShell リモート処理用に構成されている場合は、Invoke-Command コマンドレットを使用して、リモートコンピューターで [ **カウンターのインポート** ] コマンドを実行できます。

## 関連リンク

[Export-Counter](Export-Counter.md)

[Get-Counter](Get-Counter.md)
