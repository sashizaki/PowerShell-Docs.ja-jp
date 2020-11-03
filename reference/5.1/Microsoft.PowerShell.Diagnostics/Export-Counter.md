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
# Export-Counter

## 概要
パフォーマンスカウンターデータをログファイルにエクスポートします。

## SYNTAX

```
Export-Counter [-Path] <String> [-FileFormat <String>] [-MaxSize <UInt32>]
 -InputObject <PerformanceCounterSampleSet[]> [-Force] [-Circular] [<CommonParameters>]
```

## Description

`Export-Counter`コマンドレットは、パフォーマンスカウンターデータ (PerformanceCounterSampleSet オブジェクト) をバイナリパフォーマンスログ (.blg)、コンマ区切り値 (.csv)、またはタブ区切り値 (.tsv) 形式のログファイルにエクスポートします。 このコマンドレットを使用して、パフォーマンスカウンターデータをログに記録します。

`Export-Counter`コマンドレットは、コマンド `Get-Counter` レットとコマンドレットによって返されるデータをエクスポートするように設計されてい `Import-Counter` ます。

このコマンドレットは、windows 7、Windows Server 2008 R2、およびそれ以降のバージョンの Windows でのみ実行されます。

## 例

### 例 1: カウンターデータをファイルにエクスポートする

この例では、カウンターデータを .BLG ファイルにエクスポートします。

```powershell
Get-Counter "\Processor(*)\% Processor Time" | Export-Counter -Path $home\Counters.blg
```

コマンドは、コマンド `Get-Counter` レットを使用してプロセッサ時間データを収集します。 パイプライン演算子 (|) を使用して、データをコマンドレットに送信し `Export-Counter` ます。 この `Export-Counter` コマンドは、 **Path** 変数を使用して出力ファイルを指定します。

データセットは非常に大きくなる可能性があるため、この例では、パイプラインを介してにデータを送信し `Export-Counter` ます。 データが変数に保存されている場合は、膨大な量のメモリを使用することがあります。

### 例 2: ファイルをカウンターファイル形式にエクスポートする

この例では、CSV ファイルをカウンターデータ .BLG 形式に変換します。

`Import-Counter`コマンドレットは、ファイルからパフォーマンスカウンターデータをインポートし `Threads.csv` ます。 この例では、このファイルが以前にコマンドレットを使用してエクスポートされたことを前提としてい `Export-Counter` ます。 パイプライン演算子 () は、インポートされた `|` データをコマンドレットに送信し `Export-Counter` ます。 このコマンドは、 **Path** パラメーターを使用して、出力ファイルの場所を指定します。 この例で **は、** コマンドレットを使用して、 **MaxSize** `Export-Counter` 1 GB でラップする循環ログを作成しています。 **MaxSize** パラメーターは mb 単位で表されます。

```powershell
$1GBInMB = 1024 # 1GB = 1024MB
Import-Counter Threads.csv | Export-Counter -Path ThreadTest.blg -Circular -MaxSize $1GBInMB
```

### 例 3: リモートコンピューターからカウンターデータを取得し、そのデータをファイルに保存する

この例は、リモート コンピューターからパフォーマンス カウンター データを取得し、そのデータをリモート コンピューター上のファイルに保存する方法を示しています。

最初のコマンドは、コマンドレットを使用して、 `Get-Counter` リモートコンピューター Server01 からワーキングセットカウンターデータを収集します。 このコマンドは、データを変数に保存し `$C` ます。

2番目のコマンドは、パイプライン演算子 () を使用して、 `|` のデータをコマンドレットに送信します。これにより、 `$C` `Export-Counter` `Workingset.blg` Server01 コンピューターの Perf 共有内のファイルにデータが保存されます。

```powershell
$C = Get-Counter -ComputerName Server01 -Counter "\Process(*)\Working Set - Private" -MaxSamples $C | Export-Counter -Path \\Server01\Perf\WorkingSet.blg
```

```Output
20
```

### 例 4: 既存のデータを再ログする

この例では、 `Import-Counter` コマンドレットとコマンドレットを使用して、既存のデータを再ログに記録する方法を示し `Export-Counter` ます。

最初のコマンドは、 `Import-Counter` コマンドレットを使用して、データディスクの .blg ログからパフォーマンスカウンターデータをインポートします。 データは変数に保存され `$All` ます。 このファイル \% には、企業内の200台以上のリモートコンピューターにおける "LogicalDisk Free Space" カウンターのサンプルが含まれています。

2番目のコマンドは、コマンドレットを使用し `Where-Object` て、 **CookedValue** が 15 (パーセント) 未満のオブジェクトを選択します。 このコマンドは、変数に結果を保存し `$LowSpace` ます。

3番目のコマンドは、パイプライン演算子 () を使用して、 `|` 変数内のデータを `$LowSpace` コマンドレットに送信し `Export-Counter` ます。 このコマンドは、 **Path** パラメーターを使用して、選択したデータを LowDiskSpace.blg ファイルに記録する必要があることを示します。

```powershell
$All = Import-Counter DiskSpace.blg
$LowSpace = $All | Where-Object {$_.CounterSamples.CookedValue -lt 15}
$LowSpace | Export-Counter -Path LowDiskSpace.blg
```

## PARAMETERS

### -円形

出力ファイルが先入れ先出し (FIFO) 形式の循環ログであることを示します。
このパラメーターを含める場合は、 **MaxSize** パラメーターが必須となります。

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

### -FileFormat

出力ログ ファイルの出力形式を指定します。

このパラメーターの有効値は、次のとおりです。

- CSV
- TSV
- .BLG

既定値は BLG です。

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

### -Force

**Path** パラメーターで指定された場所に存在する場合、既存のファイルを上書きして置き換えます。

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

### -InputObject

エクスポートするカウンターデータを配列として指定します。 データを含む変数、またはやコマンドレットなどのデータを取得するコマンドを入力し `Get-Counter` `Import-Counter` ます。

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

### -MaxSize

出力ファイルの最大サイズをメガバイト (MB) 単位で指定します。

**循環** パラメーターが指定されている場合、ログファイルが指定された最大サイズに達すると、新しいエントリが追加されると、最も古いエントリが削除されます。 **循環** パラメーターが指定されていない場合、ログファイルが指定された最大サイズに達すると、新しいデータは追加されず、コマンドレットは終了しないエラーを生成します。

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

### -Path

出力ファイルのパスとファイル名を指定します。 ローカルコンピューター上の相対パスまたは絶対パス、またはリモートコンピューターへの汎用名前付け規則 (UNC) パスを入力し `\\Computer\Share\file.blg` ます。 このパラメーターは必須です。

ファイル形式は、パスのファイル名拡張子ではなく、 **FileFormat** パラメーターの値によって決まります。

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

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### PerformanceCounterSampleSet (Microsoft. PowerShell)

パイプを使用して `Get-Counter` 、または `Import-Counter` このコマンドレットに対してパフォーマンスカウンターデータをパイプすることができます。

## 出力

### なし

## 注

ログ ファイル ジェネレーターは、すべての入力オブジェクトが同じカウンター パスを保持し、オブジェクトが時間の昇順に並んでいることを前提とします。

カウンターの種類と、最初の入力オブジェクトのパスによって、ログ ファイルに記録されるプロパティが決まります。 その他の入力オブジェクトに記録されたプロパティの値がない場合、プロパティ フィールドは空になります。 オブジェクトに記録されていないプロパティ値がある場合、余分なプロパティ値は無視されます。

パフォーマンスモニターは、が生成するすべてのログを読み取ることができない可能性があり `Export-Counter` ます。 たとえば、パフォーマンスモニターでは、すべてのオブジェクトが同じパスを持ち、すべてのオブジェクトが同じ時間間隔で区切られている必要があります。

`Import-Counter`コマンドレットに **ComputerName** パラメーターがありません。 ただし、コンピューターがリモートの Windows PowerShell Windows PowerShell 用に構成されている場合は、 `Invoke-Command` コマンドレットを使用して `Import-Counter` リモートコンピューターでコマンドを実行できます。

## 関連リンク

[Get-Counter](Get-Counter.md)

[Import-Counter](Import-Counter.md)
