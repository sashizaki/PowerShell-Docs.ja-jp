---
external help file: Microsoft.PowerShell.ScheduledJob.dll-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/add-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-JobTrigger
ms.openlocfilehash: 6066b8f91c99830fefb09a8bea13fac6ddf958e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213496"
---
# Add-JobTrigger

## 概要
スケジュールされたジョブにジョブ トリガーを追加します。

## SYNTAX

### JobDefinition (既定値)

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-InputObject] <ScheduledJobDefinition[]>
 [<CommonParameters>]
```

### JobDefinitionId

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Id] <Int32[]> [<CommonParameters>]
```

### JobDefinitionName

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Name] <String[]> [<CommonParameters>]
```

## Description
**Add-JobTrigger** コマンドレットは、スケジュールされたジョブにジョブ トリガーを追加します。
このコマンドレットを使用すると、スケジュールされた複数のジョブに複数のトリガーを追加できます。

ジョブトリガーは、スケジュールされたジョブを1回だけ、定期的なスケジュール、またはイベントが発生したときに開始します。

追加するジョブトリガーを特定するには、 **Add jobtrigger** の *Trigger* パラメーターを使用します。
**Add jobtrigger** の *Name* 、 *ID* 、または *InputObject* パラメーターを使用して、トリガーが追加されるスケジュールされたジョブを特定します。

*Trigger* パラメーターの値に対してジョブトリガーを作成するには、New-JobTrigger コマンドレットを使用するか、またはハッシュテーブルを使用してジョブトリガーを指定します。

**Add-JobTrigger** は、Windows PowerShell に含まれている **psscheduledjob** モジュールのジョブスケジュールコマンドレットのコレクションの1つです。

スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。
PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: スケジュールされたジョブにジョブトリガーを追加する

```
PS C:\> $Daily = New-JobTrigger -Daily -At 3AMPS
PS C:\> Add-JobTrigger -Trigger $Daily -Name "TestJob"
```

これらのコマンドは、スケジュールされたジョブ TestJob に日単位のジョブ トリガーを追加します。

最初のコマンドは、New-JobTrigger コマンドレットを使用して、毎日午前3:00 にスケジュールされたジョブを開始するジョブトリガーを作成します。
このコマンドは、ジョブトリガーを $Daily 変数に保存します。

2 番目のコマンドは、 **Add-JobTrigger** コマンドレットを使用して、スケジュールされたジョブ TestJob に $Startup 変数内のジョブ トリガーを追加します。

### 例 2: 複数のスケジュールされたジョブにジョブトリガーを追加する

```
PS C:\> Get-ScheduledJob | Add-JobTrigger -Trigger (New-JobTrigger -AtStartup)
```

このコマンドは、ローカル コンピューター上のスケジュールされたすべてのジョブに AtStartup ジョブ トリガーを追加します。
Get-ScheduledJob を使用して、コンピューター上のスケジュールされたすべてのジョブを取得します。
パイプライン演算子 (|) により、ジョブを **Add-JobTrigger** コマンドレットに渡して、スケジュールされた各ジョブにジョブ トリガーを追加します。
*Trigger* パラメーターの値は、atstartup ジョブトリガーを作成する New-JobTrigger コマンドです。

### 例 3: ジョブトリガーをコピーする

```
PS C:\> $T = Get-JobTrigger -Name "BackupArchives"
PS C:\> Add-JobTrigger -Name "TestBackup,BackupLogs" -Trigger $T
```

これらのコマンドは、スケジュールされたジョブ BackupArchives のジョブ トリガーをコピーして、スケジュールされたジョブ TestBackup と BackupLogs に追加します。

最初のコマンドは、Get-JobTrigger コマンドレットを使用して、スケジュールされたジョブ BackupArchives のジョブトリガーを取得します。
このコマンドは、トリガーを $t 変数に保存します。

2 番目のコマンドは、 **Add-JobTrigger** コマンドレットを使用して、スケジュールされたジョブ TestBackup と BackupLogs に $t 内のジョブ トリガーを追加します。

## PARAMETERS

### -Id
スケジュールされたジョブの識別番号を指定します。
**Add-JobTrigger** は、指定されたスケジュールされたジョブにジョブ トリガーを追加します。

ローカルコンピューターまたはリモートコンピューター上のスケジュールされたジョブの識別番号を取得するには、Get-ScheduledJob コマンドレットを使用します。

```yaml
Type: System.Int32[]
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
スケジュールされたジョブを指定します。
**Scheduledjob** オブジェクトを含む変数を入力するか、Get-ScheduledJob コマンドなどの **scheduledjob** オブジェクトを取得するコマンドまたは式を入力します。
また、パイプを使用して **Scheduledjob** オブジェクトを追加して **、Jobtrigger を追加** することもできます。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
スケジュールされたジョブの名前を指定します。
**Add-JobTrigger** は、指定されたスケジュールされたジョブにジョブ トリガーを追加します。
ワイルドカードを利用できます。

ローカルコンピューターまたはリモートコンピューター上のスケジュールされたジョブの名前を取得するには、Get-ScheduledJob コマンドレットを使用します。

```yaml
Type: System.String[]
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -トリガー
追加するジョブトリガーを指定します。
ジョブトリガーまたは **Scheduledjobtrigger** オブジェクトを含む変数を指定するハッシュテーブルを入力するか、Get-JobTrigger コマンドなど、 **scheduledjobtrigger** オブジェクトを取得するコマンドまたは式を入力します。
また、パイプを使用して **scheduledjobtrigger** オブジェクトを **追加** することもできます。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### ScheduledJobDefinition の場合は、microsoft... ScheduledJobTrigger です。
パイプを使用して、ジョブ トリガーまたはスケジュールされたジョブを **Add-JobTrigger** に渡すことができます。

## 出力

### なし
このコマンドレットによる戻り値はありません。

## 注

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
