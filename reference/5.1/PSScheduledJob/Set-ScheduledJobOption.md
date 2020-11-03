---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJobOption
ms.openlocfilehash: 6647e9ba4e2ee49afa90dd382573d437d2deaee6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213376"
---
# Set-ScheduledJobOption

## 概要
スケジュールされたジョブのジョブ オプションを変更します。

## SYNTAX

```
Set-ScheduledJobOption [-InputObject] <ScheduledJobOptions> [-PassThru] [-RunElevated] [-HideInTaskScheduler]
 [-RestartOnIdleResume] [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart]
 [-RequireNetwork] [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery]
 [-IdleTimeout <TimeSpan>] [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## Description
**Set-ScheduledJobOptions** コマンドレットは、スケジュールされたジョブのジョブ オプションを変更します。

スケジュールされたジョブのオプションを変更するには、まず Get-ScheduledJobOption コマンドレットを使用して、スケジュールされたジョブのジョブオプションを取得します。
次に、パイプを使用してオプションを **Set-ScheduledJobOption** に渡すか、オプションを変数に保存し、 *Set-ScheduledJobOption* コマンドレットの **InputObject** パラメーターを使用して、オプションを特定します。
**Set-ScheduledJobOption** の他のパラメーターを使用して、ジョブ オプションを変更します。

ジョブ オプションを有効にするには、そのオプションを設定するパラメーターを使用します。
オプションをオフにするには、パラメーター名、コロン (:)、および $False を入力します。
たとえば、 *Runelevated* オプションをオフにするには、「」と入力 `-RunElevated:$False` します。

各ジョブ オプション オブジェクトには、スケジュールされたジョブを含む JobDefinition プロパティが含まれています。そのため、ジョブ オプションを変更しても、スケジュールされたジョブとの関連付けは維持されます。

スケジュールされたジョブのオプションにより、タスク スケジューラによって開始されたジョブの実行方法が決まります。
これらのオプションは、Start-Job コマンドレットを使用してスケジュールされたジョブを開始する場合には適用されません。

**Get-scheduledjoboption** は、Windows PowerShell に含まれている psscheduledjob モジュールのジョブスケジュールコマンドレットのコレクションの1つです。

スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。
PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: ジョブオプションを変更する

```
PS C:\> Get-ScheduledJobOption -Name "DeployPackage"
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
RunWithoutNetwork      : False
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          :

The second command uses the **Set-ScheduledJobOpton** cmdlet to change the job options so the values of the WakeToRun and RunWithoutNetwork properties are $True. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-ScheduledJobOption -Name "DeployPackage" | Set-ScheduledJobOption -WakeToRun -RequireNetwork:$False -Passthru
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : True
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNewJobDefinition          :
```

この例では、ローカル コンピューター上のスケジュールされたジョブのオプションを変更する方法を示します。

最初のコマンドは、Get-ScheduledJobOption コマンドレットを使用して、スケジュールされたジョブ DeployPackage のジョブオプションを取得します。
出力には、WakeToRun プロパティと RunElevated プロパティが $False に設定されていることが示されています。

このコマンドは必須ではありません。オプションの変更の結果を表示するためにのみ含まれています。

### 例 2: すべてのリモートスケジュールされたジョブのオプションを変更する

```
PS C:\> Invoke-Command -Computer "Server01" -ScriptBlock {Get-ScheduledJob | Get-ScheduledJobOption | Set-ScheduledJobOption -IdleTimeout 2:00:00}
```

このコマンドは、Server01 コンピューター上のスケジュールされたすべてのジョブの *IdleTimeout* の値を1時間 (既定値) から2時間に変更します。

このコマンドは、Invoke-Command コマンドレットを使用して、Server01 コンピューター上でコマンドを実行します。

リモートコマンドは、コンピューター上のスケジュールされたすべてのジョブを取得する Get-ScheduledJob コマンドで開始します。
スケジュールされたジョブは Get-ScheduledJobOption コマンドレットにパイプ処理され、スケジュールされたジョブのジョブオプションを取得します。
各ジョブ オプション オブジェクトには、スケジュールされたジョブを含む JobDefinition プロパティが含まれています。そのため、オプション オブジェクトを変更しても、スケジュールされたジョブとの関連付けは維持されます。

ジョブトリガーはパイプを使用して **get-scheduledjoboption** コマンドレットに渡されます。このコマンドレットは、 *IdleTimeout* オプションの値を2時間 (2:00:00) に変更します。

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

タスクが非表示の場合でも、ユーザーはタスクスケジューラの [ **非表示のタスクビューを** 表示] オプションを選択することでタスクを表示できます。

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

Timespan オブジェクトを入力します。たとえば、New-TimeSpan コマンドレットによって生成されたものや、 \<hours\> \<minutes\> \<seconds\> **timespan** オブジェクトに自動的に変換される:: format の値を入力します。

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
コンピューターのアイドル状態がどれだけ続いたらジョブを開始するかを指定します。
既定値は 10 分です。
**IdleTimeout** の値を過ぎる前に、コンピューターが指定された時間アイドル状態にならないと、(次のスケジュールされた時刻が設定されていれば、それまで) スケジュールされたジョブは実行されません。

Timespan オブジェクトを入力します。たとえば、New-TimeSpan コマンドレットによって生成されたものや、 \<hours\> \<minutes\> \<seconds\> **timespan** オブジェクトに自動的に変換される:: format の値を入力します。

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

### -InputObject
ジョブ オプションを指定します。
**ScheduledJobOptions** オブジェクトを含む変数を入力するか、Get-ScheduledJobOption コマンドなどの **ScheduledJobOptions** オブジェクトを取得するコマンドまたは式を入力します。
パイプを使用して **ScheduledJobOptions** オブジェクトを **get-scheduledjoboption** にパイプ処理することもできます。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -多重 Instancepolicy
スケジュールされたジョブのインスタンスの実行中にそのジョブの別のインスタンスを開始する要求に対するシステムの応答方法を決定します。
このパラメーターの有効値は、次のとおりです。

- IgnoreNew.
新しいジョブ インスタンスを無視します。
これが既定値です。
- パラレル。
新しいジョブ インスタンスをすぐに開始します。
- キュー:
現在のジョブ インスタンスが完了したら、すぐに新しいインスタンスを開始します。
- StopExisting。
ジョブの現在のインスタンスを停止し、新しいインスタンスを開始します。

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

### -PassThru
作業中の項目を表すオブジェクトを返します。
既定では、このコマンドレットによる出力はありません。

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

**Runelevated** されたパラメーターは、スケジュールされたジョブの **runelevated** されたプロパティの値を True に設定します。

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
**IdleTimeout** パラメーターに指定された時間を過ぎる前に、コンピューターが *IdleDuration* パラメーターに指定された時間アイドル状態になった場合に、スケジュールされたジョブを開始します。

既定では、 *IdleDuration* パラメーターと *IdleTimeout* パラメーターは無視され、コンピューターがビジー状態でも、ジョブはスケジュールされた開始時刻に開始されます。

このパラメーターを指定し、スケジュールされた開始時刻にコンピューターがビジー状態の場合 (アイドル状態でない場合) は、(次のスケジュールされた開始時刻が設定されていれば、それまで) ジョブは実行されません。

*StartIfIdle* パラメーターは、スケジュールされたジョブの **StartIfNotIdle** プロパティの値を False に設定します。

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
既定値は False です。

*Startiのバッテリ* パラメーターは、スケジュールされたジョブの **startiの電池** プロパティの値を $True に設定します。

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

### ScheduledJobOptions (Microsoft PowerShell)
パイプを使用して、スケジュールされたジョブのオプション オブジェクトを **Set-ScheduledJobOption** に渡すことができます。

## 出力

### [なし] または [ScheduledJobOptions]
*Passthru* パラメーターを使用すると、 **Set-ScheduledJobOption** は変更されたジョブ オプションを返します。
それ以外の場合、このコマンドレットによる出力はありません。

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
