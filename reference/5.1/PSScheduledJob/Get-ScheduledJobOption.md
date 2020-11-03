---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJobOption
ms.openlocfilehash: 5c317be9add0898137aceed6c39032f3e271bac1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213427"
---
# Get-ScheduledJobOption

## 概要
スケジュールされたジョブのジョブ オプションを取得します。

## SYNTAX

### JobDefinition (既定値)

```
Get-ScheduledJobOption [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### JobDefinitionId

```
Get-ScheduledJobOption [-Id] <Int32> [<CommonParameters>]
```

### JobDefinitionName

```
Get-ScheduledJobOption [-Name] <String> [<CommonParameters>]
```

## Description
**Get-scheduledjoboption** コマンドレットは、スケジュールされたジョブのジョブオプションを取得します。
このコマンドを使用すると、ジョブ オプションを確認することや、パイプを使用してジョブ オプションを他のコマンドレットに渡すことができます。

ジョブ オプションは、スケジュールされたジョブの一部であり、ディスクに単独で保存されるわけではありません。
スケジュールされたジョブのジョブ オプションを取得するには、スケジュールされたジョブを指定します。

**Get-ScheduledJobOption** コマンドレットのパラメーターを使用して、スケジュールされたジョブを特定します。
スケジュールされたジョブは、名前または識別番号で識別できます。または、Get-ScheduledJob コマンドレットによって返されたものなどの **Scheduledjob** オブジェクトを **get-scheduledjoboption** に入力するか、パイプを使用して識別することができます。

**Get-scheduledjoboption** は、Windows PowerShell に含まれている psscheduledjob モジュールのジョブスケジュールコマンドレットのコレクションの1つです。

スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。
PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: ジョブオプションを取得する

```
PS C:\> Get-ScheduledJobOption -Name "*Backup*"
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : False

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

このコマンドは、名前にバックアップが含まれるスケジュールされたジョブのジョブオプションを取得します。
結果には、 **Get-ScheduledJobOption** から返されたジョブ オプション オブジェクトが示されています。

### 例 2: すべてのジョブオプションを取得する

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption
```

このコマンドは、ローカル コンピューター上のスケジュールされたすべてのジョブのジョブ オプションを取得します。

Get-ScheduledJob コマンドレットを使用して、ローカルコンピューター上のスケジュールされたジョブを取得します。
パイプライン演算子 (|) によって、スケジュールされたジョブが **get-scheduledjoboption** コマンドレットに送信されます。このコマンドレットは、スケジュールされた各ジョブのジョブオプションを取得します。

### 例 3: 選択したジョブオプションを取得する

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun}
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : True

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The second command shows how to find to which scheduled job the job options belong. This command uses a pipeline operator (|) to send the selected job options to the ForEach-Object cmdlet, which gets the JobDefinition property of each options object. The JobDefinition property contains the originating job object. The results show that the selected options came from the DeployPkg scheduled job.
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun} | ForEach-Object {$_.JobDefinition}
Id         Name            Triggers        Command                                  Enabled

--         ----            --------        -------                                  -------

2          DeployPkg         {1, 2}        DeployPackage.ps1                        True
```

この例では、特定の値でジョブ オプション オブジェクトを検索する方法を示します。

最初のコマンドは、RunElevated されたプロパティの値が $True で、Runelevated Network プロパティの値が $False であるジョブオプションを取得します。
出力には、選択された **JobOptions** オブジェクトが示されます。

### 例 4: ジョブオプションを使用して新しいジョブを作成する

```
PS C:\> $Opts = Get-ScheduledJobOption -Name "BackupTestLogs"
PS C:\> Register-ScheduledJob -Name "Archive-Scripts" -FilePath "\\Srv01\Scripts\ArchiveScripts.ps1" -ScheduledJobOption $Opts
```

この例では、スケジュールされた新しいジョブで Get-ScheduledJobOption ジョブオプションを使用する方法を示します。

最初のコマンドは、 **get-scheduledjoboption** を使用して、スケジュールされたジョブ BackupTestLogs のジョブオプションを取得します。
このコマンドは、オプションを $Opts 変数に保存します。

2番目のコマンドは、Register-ScheduledJob コマンドレットを使用して、スケジュールされた新しいジョブを作成します。
*ScheduledJobOption* パラメーターの値は、$Opts 変数内のオプション オブジェクトです。

### 例 5: リモートコンピューターからジョブオプションを取得する

```
PS C:\> $O = Invoke-Command -ComputerName "Srv01" -ScriptBlock {Get-ScheduledJob -Name "DataDemon" }
```

このコマンドは、Invoke-Command コマンドレットを使用して、Srv01 コンピューター上の DataDemon ジョブのスケジュールされたジョブオプションを取得します。
このコマンドは、オプションを $O 変数に保存します。

## PARAMETERS

### -Id
スケジュールされたジョブの識別番号を指定します。
**Get-ScheduledJobOption** は、指定されたスケジュールされたジョブのジョブ オプションを取得します。

ローカルコンピューターまたはリモートコンピューター上のスケジュールされたジョブの識別番号を取得するには、Get-ScheduledJob コマンドレットを使用します。

```yaml
Type: System.Int32
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
パイプを使用して **ScheduledJob** オブジェクトを **Get-ScheduledJobOption** に渡すこともできます。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
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
**Get-ScheduledJobOption** は、指定されたスケジュールされたジョブのジョブ オプションを取得します。
ワイルドカードを利用できます。

ローカルコンピューターまたはリモートコンピューター上のスケジュールされたジョブの名前を取得するには、Get-ScheduledJob コマンドレットを使用します。

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### ScheduledJobDefinition (Microsoft PowerShell)
スケジュールされたジョブを Get-ScheduledJob から **get-scheduledjoboption** にパイプすることができます。

## 出力

### ScheduledJobOptions (Microsoft PowerShell)

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
