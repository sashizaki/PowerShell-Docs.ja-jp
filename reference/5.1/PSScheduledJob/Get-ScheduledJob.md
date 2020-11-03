---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJob
ms.openlocfilehash: 40224432c208ee45efc20f556312fa250e9bb7a6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213435"
---
# Get-ScheduledJob

## 概要
ローカル コンピューター上のスケジュールされたジョブを取得します。

## SYNTAX

### DefinitionId (既定値)

```
Get-ScheduledJob [[-Id] <Int32[]>] [<CommonParameters>]
```

### DefinitionName

```
Get-ScheduledJob [-Name] <String[]> [<CommonParameters>]
```

## Description
**Get-ScheduledJob** コマンドレットは、ローカル コンピューター上のスケジュールされたジョブを取得します。
**Get ScheduledJob** は、Register-ScheduledJob コマンドレットを使用して、現在のユーザーが作成したスケジュールされたジョブのみを取得します。

**Register-ScheduledJob** コマンドレットを使用して作成したジョブはタスク スケジューラに表示されますが、 **Get-ScheduledJob** はスケジュールされたジョブのみを取得します。
タスク スケジューラで作成したスケジュールされたタスクは取得しません。

パラメーターが指定されていない場合、 **Get-ScheduledJob** はコンピューター上のスケジュールされたすべてのジョブを取得します。
**Get-ScheduledJob** のパラメーターを使用すると、スケジュールされたジョブを ID または名前で取得して確認することや、パイプを使用して他のコマンドレットに渡すことができます。

**Get scheduledjob** は、Windows PowerShell に含まれている **psscheduledjob** モジュールのジョブスケジュールコマンドレットのコレクションの1つです。

スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。
PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: スケジュールされたすべてのジョブを取得する

```
PS C:\> Get-ScheduledJob
```

このコマンドは、ローカル コンピューター上のスケジュールされたすべてのジョブを取得します。

### 例 2: 名前を指定してスケジュールされたジョブを取得する

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive*
```

このコマンドは、バックアップまたはアーカイブを含む名前を持つ、コンピューター上のスケジュールされたすべてのジョブを取得します。
このコマンドの形式を使用して、特定のジョブを検索することができます。

### 例 3: リモートコンピューター上のスケジュールされたジョブを取得する

```
PS C:\> Invoke-Command -ComputerName (Get-Content Servers.txt) {Get-ScheduledJob}
```

このコマンドは、Servers.txt ファイルに記載されているコンピューター上のスケジュールされたすべてのジョブを取得します。
このコマンドは、Invoke-Command コマンドレットを使用して、各コンピューターで **Get ScheduleJob** コマンドを実行します。

### 例 4: パイプを使用してスケジュールされたジョブを他のコマンドレットに設定する

```
PS C:\> Get-ScheduledJob DailyBackup, WeeklyBackup | Get-JobTrigger
```

このコマンドは、スケジュールされたジョブ DailyBackup と WeeklyBackup のジョブ トリガーを取得します。
この例では、 **Get ScheduledJob** コマンドレットを使用してスケジュールされたジョブを取得し、Get-JobTrigger コマンドレットを使用して、スケジュールされたジョブのジョブトリガーを取得します。

## PARAMETERS

### -Id
指定された識別番号 (ID) のスケジュールされたジョブのみを取得します。
コンピューター上のスケジュールされたジョブの 1 つまたは複数の ID を入力します。
既定では、 **Get-ScheduledJob** はコンピューター上のスケジュールされたすべてのジョブを取得します。

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
指定された名前のスケジュールされたジョブのみを取得します。
コンピューター上のスケジュールされたジョブの 1 つまたは複数の名前を入力します。
ワイルドカードを利用できます。
既定では、 **Get-ScheduledJob** はコンピューター上のスケジュールされたすべてのジョブを取得します。

```yaml
Type: System.String[]
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし
入力を **Get ScheduledJob** にパイプすることはできません。

## 出力

### ScheduledJobDefinition (Microsoft PowerShell)

## 注

* スケジュールされた各ジョブは、ローカル コンピューターの $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs ディレクトリのサブディレクトリに保存されます。 サブディレクトリには、スケジュールされたジョブの名前が付けられ、スケジュールされたジョブの XML ファイルとその実行履歴のレコードが含まれます。 ディスク上のスケジュールされたジョブの詳細については、「about_Scheduled_Jobs_Advanced」を参照してください。
* Windows PowerShell で作成したスケジュールされたジョブは、タスク スケジューラの Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs フォルダーに表示されます。 タスク スケジューラを使用して、スケジュールされたジョブを表示および編集できます。
* スケジュールされたジョブ コマンドレットを使用して作成したスケジュールされたジョブは、タスク スケジューラ、SchTasks.exe コマンド ライン ツール、およびタスク スケジューラ コマンドレットを使用して管理できます。 ただし、タスク スケジューラで作成したタスクは、スケジュールされたジョブ コマンドレットを使用して管理することはできません。

## 関連リンク

[Add-JobTrigger](Add-JobTrigger.md)

[Disable-JobTrigger](Disable-JobTrigger.md)

[Disable-ScheduledJob](Disable-ScheduledJob.md)

[Enable-JobTrigger](Enable-JobTrigger.md)

[Enable-ScheduledJob](Enable-ScheduledJob.md)

[Get-JobTrigger](Get-JobTrigger.md)

[Get-ScheduledJob](Get-ScheduledJob.md)

[Get-ScheduledJobOption](Get-ScheduledJobOption.md)

[New-JobTrigger](New-JobTrigger.md)

[New-ScheduledJobOption](New-ScheduledJobOption.md)

[Register-ScheduledJob](Register-ScheduledJob.md)

[Remove-JobTrigger](Remove-JobTrigger.md)

[Set-JobTrigger](Set-JobTrigger.md)

[Set-ScheduledJob](Set-ScheduledJob.md)

[Set-ScheduledJobOption](Set-ScheduledJobOption.md)

[Unregister-ScheduledJob](Unregister-ScheduledJob.md)
