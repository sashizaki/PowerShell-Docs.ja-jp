---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScheduledJobOption
ms.openlocfilehash: 35ada8d5aaa6a6c1fdc74a089308aefe13598b10
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213419"
---
# New-ScheduledJobOption

## 概要
スケジュールされたジョブの詳細オプションを格納するオブジェクトを作成します。

## SYNTAX

```
New-ScheduledJobOption [-RunElevated] [-HideInTaskScheduler] [-RestartOnIdleResume]
 [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart] [-RequireNetwork]
 [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery] [-IdleTimeout <TimeSpan>]
 [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## Description
**New-ScheduledJobOption** コマンドレットは、スケジュールされたジョブの詳細オプションを格納するオブジェクトを作成します。

**New-ScheduledJobOption** から返された **ScheduledJobOptions** オブジェクトを使用して、新しいまたは既存のスケジュールされたジョブのジョブ オプションを設定できます。
または、Get-ScheduledJobOption コマンドレットを使用して、既存のスケジュールされたジョブのジョブオプションを取得したり、ジョブオプションを表すハッシュテーブル値を使用して、ジョブオプションを設定したりできます。

パラメーターを指定しない場合、 **get-scheduledjoboption** は、すべてのオプションの既定値を含むオブジェクトを生成します。
JobDefinition プロパティを除くすべてのプロパティを編集できるため、結果のオブジェクトをテンプレートとして使用し、企業の標準のオプション オブジェクトを作成することができます。

スケジュールされたジョブを作成し、スケジュールされたジョブのオプションを設定する際は、スケジュールされたジョブのすべてのオプションの既定値を確認してください。
スケジュールされたジョブは、設定されている実行条件をすべて満たした場合にのみ実行されます。

**Get-scheduledjoboption** は、Windows PowerShell に含まれている psscheduledjob モジュールのジョブスケジュールコマンドレットのコレクションの1つです。

スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。
PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: スケジュールされたジョブオプションオブジェクトを既定値で作成する

```
PS C:\> New-ScheduledJobOption
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : False
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

このコマンドは、スケジュールされたジョブの、すべて既定値のオプション オブジェクトを作成します。

### 例 2: スケジュールされたジョブオプションオブジェクトをカスタム値で作成する

```
PS C:\> New-ScheduledJobOption -RequireNetwork -StartIfOnBattery
StartIfOnBatteries     : True
StopIfGoingOnBatteries : True
WakeToRun              : False
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : False
DoNotAllowDemandStart  : False
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

次のコマンドは、ネットワークを必要とし、コンピューターが AC 電源に接続されていない場合でもスケジュールされたジョブを実行するスケジュールされたジョブのオブジェクトを作成します。

出力には、 *RequireNetwork* パラメーターの値を $False に変更し、 *starti バッテリ* のパラメーターの値を $True に変更したことが示されています。

### 例 3: 新しいスケジュールされたジョブのオプションを設定する

```
The first command creates a **ScheduledJobOptions** object with the *RunElevated* parameter. It saves the object in the $RunAsAdmin variable.
PS C:\> $RunAsAdmin = New-ScheduledJobOption -RunElevated

The second command uses the Register-ScheduledJob cmdlet to create a new scheduled job. The value of the *ScheduledJobOption* parameter is the option object in the value of the $RunAsAdmin variable.
PS C:\> Register-ScheduledJob -Name Backup -FilePath D:\Scripts\Backup.ps1 -Trigger $Mondays -ScheduledJobOption $RunAsAdmin

The third command uses the Get-ScheduledJobOption cmdlet to get the job options of the Backup scheduled job.The cmdlet output shows that the RunElevated property is set to $True and the JobDefinition property of the job option object is now populated with the scheduled job object for the Backup scheduled job.
PS C:\> Get-ScheduledJobOption -Name Backup
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
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

この例では、 **New-ScheduledJobOption** から返された **ScheduledJobOptions** オブジェクトを使用して、スケジュールされた新しいジョブのオプションを設定する方法を示します。

### 例 4: スケジュールされたジョブのオプションオブジェクトのプロパティを並べ替える

```
PS C:\> $Options = New-ScheduledJobOption -WakeToRun
PS C:\> $Options.PSObject.Properties | Sort-Object -Property Name | Format-Table -Property Name, Value -Autosize
Name                       Value
----                       -----
DoNotAllowDemandStart      False
IdleDuration            00:10:00
IdleTimeout             01:00:00
JobDefinition
MultipleInstancePolicy IgnoreNew
RestartOnIdleResume        False
RunElevated                False
RunWithoutNetwork           True
ShowInTaskScheduler         True
StartIfNotIdle              True
StartIfOnBatteries         False
StopIfGoingOffIdle         False
StopIfGoingOnBatteries      True
WakeToRun                   True
```

この例では、 **ScheduledJobOptions** オブジェクトのプロパティを見やすいようにアルファベット順で並べ替える方法を示します。

最初のコマンドは、 **New-ScheduledJobOption** コマンドレットを使用して、 **ScheduledJobOptions** オブジェクトを作成します。
このコマンドでは、 *WakeToRun* パラメーターを使用して、結果のオブジェクトを $Options 変数に保存します。

オブジェクトとして $Options のプロパティを取得するために、2番目のコマンドは、すべての Windows PowerShell オブジェクトとその Properties プロパティの **PSObject** プロパティを使用します。
次に、コマンドを使用してプロパティオブジェクトを Sort-Object コマンドレットに渡します。このコマンドレットは、プロパティを名前順にアルファベット順に並べ替え、Format-Table コマンドレットに渡して、テーブルのプロパティの名前と値を表示します。

この形式を使用すると、$Options で **ScheduledJobOptions** オブジェクトの WakeToRun プロパティを検索し、その値が $False から $True に変更されたことを確認することが非常に簡単になります。

## PARAMETERS

### -続行 Eifgoingonバッテリ
ジョブの実行中に、コンピューターがバッテリ電源に切り替わっても (AC 電源から切断されても)、スケジュールされたジョブを停止しません。
既定では、コンピューターが AC 電源から切断されると、スケジュールされたジョブは停止します。

*続行 Eifgoingonバッテリ* パラメーターは、スケジュールされたジョブの StopIfGoingOnBatteries プロパティの値を $True に設定します。

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

### -DoNotAllowDemandStart
トリガーされた場合にのみ、ジョブを開始します。
ユーザーは、タスク スケジューラの実行機能などを使用して、手動でジョブを開始することはできません。

このパラメーターは、タスク スケジューラにのみ影響します。
ユーザーが Start-Job コマンドレットを使用してジョブを開始するのを防ぐことはできません。

*DoNotAllowDemandStart* パラメーターは、スケジュールされたジョブの DoNotAllowDemandStart プロパティの値を $True に設定します。

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

### -HideInTaskScheduler
タスク スケジューラにジョブを表示しません。
この値は、ジョブが実行されるコンピューターにのみ影響します。
既定では、スケジュールされたタスクはタスク スケジューラに表示されます。

タスクが非表示の場合でも、ユーザーはタスクスケジューラの [非表示のタスクビューを表示] オプションを選択することでタスクを表示できます。

*HideInTaskScheduler* パラメーターは、スケジュールされたジョブの ShowInTaskScheduler プロパティの値を $False に設定します。

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

### -IdleDuration
コンピューターのアイドル状態がどれだけ続いたらジョブを開始するかを指定します。
既定値は 10 分です。
*IdleTimeout* の値を過ぎる前に、コンピューターが指定された時間アイドル状態にならないと、(次のスケジュールされた時刻が設定されていれば、それまで) スケジュールされたジョブは実行されません。

**Timespan** オブジェクトを入力します。たとえば、New-TimeSpan コマンドレットによって生成されたものや、 \<hours\> \<minutes\> \<seconds\> **timespan** オブジェクトに自動的に変換される:: format の値を入力します。

この値を有効にするには、 *StartIfIdle* パラメーターを使用します。
既定では、スケジュールされたジョブの StartIfNotIdle プロパティは $True に設定され、Windows PowerShell は *IdleDuration* と *IdleTimeout* の値を無視します。

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdleTimeout
コンピューターがアイドル状態になるまでのスケジュールされたジョブの待機時間を指定します。
コンピューターが *IdleDuration* パラメーターで指定された時間アイドル状態になる前に、このタイムアウトを過ぎた場合、(次のスケジュールされた時刻が設定されていれば、それまで) ジョブは実行されません。
既定値は 1 時間です。

**Timespan** オブジェクトを入力します。たとえば、New-TimeSpan コマンドレットによって生成されたものや、 \<hours\> \<minutes\> \<seconds\> **timespan** オブジェクトに自動的に変換される:: format の値を入力します。

この値を有効にするには、 *StartIfIdle* パラメーターを使用します。
既定では、スケジュールされたジョブの StartIfNotIdle プロパティは $True に設定され、Windows PowerShell は *IdleDuration* と *IdleTimeout* の値を無視します。

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -多重 Instancepolicy
スケジュールされたジョブのインスタンスの実行中にそのジョブの別のインスタンスを開始する要求に対するシステムの応答方法を決定します。
既定値は IgnoreNew です。
このパラメーターの有効値は、次のとおりです。

- IgnoreNew.
新しいジョブ インスタンスを無視します。
- パラレル。
新しいジョブ インスタンスをすぐに開始します。
- キュー:
現在のジョブ インスタンスが完了したら、すぐに新しいインスタンスを開始します。
- StopExisting。
ジョブの現在のインスタンスが停止し、新しいインスタンスが開始されます。

ジョブを実行するには、ジョブ スケジュールのすべての条件を満たす必要があります。
たとえば、 *RequireNetwork* 、 *IdleDuration* 、および *IdleTimeout* パラメーターによって設定された条件が満たされない場合、このパラメーターの値に関係なく、ジョブインスタンスは開始されません。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.TaskMultipleInstancePolicy
Parameter Sets: (All)
Aliases:
Accepted values: None, IgnoreNew, Parallel, Queue, StopExisting

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequireNetwork
ネットワーク接続が利用可能な場合にのみ、スケジュールされたジョブを実行します。

このパラメーターを指定し、スケジュールされた開始時刻にネットワークが利用できない場合は、(次のスケジュールされた開始時刻が設定されていれば、それまで) ジョブは実行されません。

*RequireNetwork* パラメーターは、スケジュールされたジョブの Run network プロパティの値を $False に設定します。

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

### -RestartOnIdleResume
コンピューターがアイドル状態になると、スケジュールされたジョブを再開します。
このパラメーターは、コンピューターがアクティブになる (アイドル状態でなくなる) と実行中のスケジュールされたジョブを中断する *StopIfGoingOffIdle* パラメーターと連動しています。

*RestartOnIdleResume* パラメーターは、スケジュールされたジョブの RestartOnIdleResume プロパティの値を $True に設定します。

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

### -RunElevated
ジョブが実行されるコンピューター上の Administrators グループのメンバーのアクセス許可で、スケジュールされたジョブを実行します。

スケジュールされたジョブを管理者権限で実行できるようにするには、Register-ScheduledJob の *credential* パラメーターを使用して、ジョブに明示的な資格情報を指定します。

*Runelevated* パラメーターは、スケジュールされたジョブの runelevated されたプロパティの値を $True に設定します。

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

### -StartIfIdle
*IdleTimeout* パラメーターに指定された時間を過ぎる前に、コンピューターが *IdleDuration* パラメーターに指定された時間アイドル状態になった場合に、スケジュールされたジョブを開始します。

既定では、 *IdleDuration* パラメーターと *IdleTimeout* パラメーターは無視され、コンピューターがビジー状態でも、ジョブはスケジュールされた開始時刻に開始されます。

このパラメーターを指定し、スケジュールされた開始時刻にコンピューターがビジー状態の場合 (アイドル状態でない場合) は、(次のスケジュールされた開始時刻が設定されていれば、それまで) ジョブは実行されません。

*StartIfIdle* パラメーターは、スケジュールされたジョブの StartIfNotIdle プロパティの値を $False に設定します。

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

### -Starti区別バッテリ
スケジュールされた開始時刻にコンピューターがバッテリで動作していても、スケジュールされたジョブを開始します。
既定値は $False です。

*Startiのバッテリ* パラメーターは、スケジュールされたジョブの startiの電池プロパティの値を $True に設定します。

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

### -StopIfGoingOffIdle
ジョブの実行中に、コンピューターがアクティブになる (アイドル状態でなくなる) と、実行中のスケジュールされたジョブを中断します。

既定では、コンピューターがアクティブになったときに中断されたスケジュールされたジョブは、コンピューターが再びアイドル状態になると再開されます。
この既定の動作を変更するには、 *RestartOnIdleResume* パラメーターを使用します。

*StopIfGoingOffIdle* パラメーターは、スケジュールされたジョブの StopIfGoingOffIdle プロパティの値を $True に設定します。

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

### -WakeToRun
スケジュールされた開始時刻にコンピューターの休止状態またはスリープ状態を解除して、ジョブを実行できるようにします。
既定では、スケジュールされた開始時刻にコンピューターが休止状態またはスリープ状態の場合、ジョブは実行されません。

*WakeToRun* パラメーターは、スケジュールされたジョブの WakeToRun プロパティの値を $True に設定します。

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

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし
パイプを使用してこのコマンドレットに入力を渡すことはできません。

## 出力

### ScheduledJobOptions (Microsoft PowerShell)

## 注

* **ScheduledJobOptions** オブジェクトを使用できます。 **get-scheduledjoboption** は、Register-ScheduledJob コマンドレットの *get-scheduledjoboption* パラメーターの値として作成されます。 ただし、 *get-scheduledjoboption* パラメーターは、 **ScheduledJobOptions** オブジェクトのプロパティとその値を指定するハッシュテーブルの値を受け取ることもできます。次に例を示します。

  `@{ShowInTaskScheduler=$False; RunElevated=$True; IdleDuration="00:05"}`

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
