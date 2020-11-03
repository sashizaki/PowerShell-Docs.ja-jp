---
description: ジョブをスケジュールし、管理する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_basics?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Basics
ms.openlocfilehash: d957c3267959c13b705e79fb220da4048e27a435
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221928"
---
# <a name="about-scheduled-jobs-basics"></a>スケジュールされたジョブについての基本事項

## <a name="short-description"></a>簡単な説明

ジョブをスケジュールし、管理する方法について説明します。

## <a name="long-description"></a>長い説明

このドキュメントでは、スケジュールされたジョブを作成および管理するための基本的なタスクを実行する方法について説明します。 詳細なタスクについては、「 [about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md)」を参照してください。

**Psscheduledjob** モジュールに含まれるコマンドレットの詳細については、「 [psscheduledjob](xref:PSScheduledJob)」を参照してください。

## <a name="how-to-create-a-scheduled-job"></a>スケジュールされたジョブを作成する方法

スケジュールされたジョブを作成するには、コマンドレットを使用し `Register-ScheduledJob` ます。 コマンドレットには、名前と、ジョブを実行するコマンドまたはスクリプトが必要です。 **Runnow** パラメーターを追加するか、ジョブトリガーを作成し、ジョブを作成するときにジョブオプションを設定するか、既存のジョブを編集することによって、ジョブをすぐに実行することができます。

スクリプトを実行するジョブを作成するには、 **FilePath** パラメーターを使用して、スクリプトファイルへのパスを指定します。 コマンドを実行するジョブを作成するには、 **ScriptBlock** パラメーターを使用します。

コマンドレットでは、 `Register-ScheduledJob` コマンドを実行する **processjob** を作成し `Get-Process` ます。 このスケジュールされたジョブには、既定のジョブオプションがあり、ジョブトリガーはありません。

```powershell
Register-ScheduledJob -Name ProcessJob -ScriptBlock { Get-Process }
```

```Output
Id         Name            Triggers        Command       Enabled
--         ----            --------        -------       -------
8          ProcessJob      {}              Get-Process   True
```

## <a name="how-to-create-a-job-trigger"></a>ジョブトリガーを作成する方法

ジョブトリガーは、スケジュールされたジョブを自動的に開始します。 ジョブトリガーには、1回だけ、定期的なスケジュール、またはユーザーがログオンしたときや Windows が起動したときなどのイベントがあります。 各ジョブには、0個、1個、または複数のジョブトリガーを含めることができます。

ジョブトリガーを作成するには、 `New-JobTrigger` コマンドレットを使用します。 次のコマンドは、月曜日と木曜日の午前5:00 時にジョブを開始するジョブトリガーを作成します。
このコマンドは、ジョブトリガーを変数に保存し `$T` ます。

```powershell
$T = New-JobTrigger -Weekly -DaysOfWeek "Monday", "Thursday" -At "5:00 AM"
```

ジョブ トリガーは省略可能です。 コマンドに **Runnow** パラメーターを追加する `Register-ScheduledJob` か、コマンドレットを使用して、スケジュールされたジョブをいつでも開始でき `Start-Job` ます。

## <a name="how-to-add-a-job-trigger"></a>ジョブトリガーを追加する方法

スケジュールされたジョブにジョブトリガーを追加すると、スケジュールされたジョブのスケジュールされたジョブの XML ファイルにジョブトリガーが追加され、スケジュールされたジョブの一部になります。

スケジュールされたジョブを作成するとき、または既存のジョブを編集するときに、スケジュールされたジョブにジョブトリガーを追加できます。 スケジュールされたジョブのジョブトリガーは、いつでも変更できます。

PowerShell では、タスクスケジューラ使用するのと同じジョブトリガーの一部が使用されます。 ジョブトリガーの詳細については、「 [New-JobTrigger](xref:PSScheduledJob.New-JobTrigger) コマンドレットのヘルプトピック」を参照してください。

次の例では、スプラッティングを使用し `$JobParms` て、コマンドレットに渡されるパラメーター値を作成し `Register-ScheduledJob` ます。 詳細については、 [about_Splatting](../../Microsoft.PowerShell.Core/About/about_Splatting.md)を参照してください。
は、 `Register-ScheduledJob` を使用して `@JobParms` スケジュールされたジョブを作成します。 **トリガー** パラメーターを使用して、変数内のジョブトリガーを指定し `$T` ます。

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Command}
  Trigger = $T
}

Register-ScheduledJob @JobParms
```

また、既存のスケジュールされたジョブにジョブトリガーをいつでも追加できます。 この `Add-JobTrigger` コマンドレットは、変数内のジョブトリガー `$T` を、スケジュールされたジョブ **processjob** に追加します。

```powershell
Add-JobTrigger -Name ProcessJob -Trigger $T
```

その結果、ジョブトリガーは月曜日と木曜日の午前5:00 に自動的に **Processjob** を開始します。

## <a name="how-to-get-a-job-trigger"></a>ジョブトリガーを取得する方法

スケジュールされたジョブのジョブトリガーを取得するには、コマンドレットを使用し `Get-JobTrigger` ます。 **Name** 、 **ID** 、および **InputObject** パラメーターを使用して、ジョブトリガーではなく、スケジュールされたジョブを指定します。

`Get-JobTrigger`**Processjob** のジョブトリガーを取得します。

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id   Frequency       Time                   DaysOfWeek              Enabled
--   ---------       ----                   ----------              -------
1    Weekly          11/7/2011 5:00:00 AM   {Monday, Thursday}      True
```

## <a name="how-to-create-job-options"></a>ジョブオプションを作成する方法

ジョブオプションは、ジョブを開始および実行するための条件を設定します。 すべてのジョブには、変更しない限り、既定のジョブオプションがあります。 ジョブオプションを使用すると、スケジュールされた時刻にジョブが実行されるのを防ぐことができるため、ジョブのオプションを理解し、それらを慎重に使用することが重要です。

PowerShell では、タスクスケジューラ使用するのと同じジョブオプションが使用されます。 ジョブオプションの詳細については、 [get-scheduledjoboption](xref:PSScheduledJob.New-ScheduledJobOption)のヘルプトピックを参照してください。

ジョブオプションは、スケジュールされたジョブの XML ファイルに格納されます。 ジョブオプションは、スケジュールされたジョブを作成するときに設定することも、いつでも変更することもできます。

コマンドレットでは、スケジュールされたジョブ `New-ScheduledJobOption` オプション **WakeToRun** を作成し、スケジュールされたジョブオプションを True に設定します。 **WakeToRun** オプションは、スケジュールされた開始時刻にコンピューターがスリープ状態または休止状態の場合でも、スケジュールされたジョブを実行します。 このコマンドは、ジョブオプションを変数に保存し `$O` ます。

```powershell
$O = New-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-job-options"></a>ジョブオプションを取得する方法

スケジュールされたジョブのジョブオプションを取得するには、コマンドレットを使用し `Get-ScheduledJobOption` ます。 ジョブオプションではなく、 **Name** 、 **ID** 、および **InputObject** パラメーターを使用して、スケジュールされたジョブを指定します。

`Get-ScheduledJobOption`**processjob** のジョブオプションを取得します。

```powershell
Get-ScheduledJobOption -Name ProcessJob
```

```Output
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
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

## <a name="how-to-change-job-options"></a>ジョブオプションを変更する方法

スケジュールされたジョブを作成したり、既存のジョブを編集したりするときに、スケジュールされたジョブのジョブオプションを変更できます。

Splatted は、 `$JobParms` `Add-JobTrigger` プロセスジョブを作成するためにコマンドレットに渡されます。 この例では、 **get-scheduledjoboption** パラメーターを使用して、変数のジョブオプションを指定して `$O` います。

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  ScheduledJobOption = $O
}

Add-JobTrigger @JobParms
```

ジョブのオプションは、いつでも既存のスケジュールされたジョブに変更することもできます。
次のコマンドでは、コマンドレットを使用して、 `Set-ScheduledJobOption` **processjob** Scheduledjob の **WakeToRun** オプションの値を **True** に変更します。

`Set`コマンドレットなど、 **Psscheduledjob** モジュールのコマンドレットに `Set-ScheduledJobOption` は、 **名前** または **ID** パラメーターがありません。 **InputObject** パラメーターを使用して、スケジュールされたジョブオプションを指定したり、スケジュールされたジョブをコマンドレットからにパイプ処理したりできます `Get-ScheduledJobOption` `Set-ScheduledJobOption` 。

この例では、 `Get-ScheduledJob` コマンドレットを使用して、ProcessJob を取得します。 コマンドレットを使用して `Get-ScheduledJobOption` **processjob** のジョブオプションを取得し、コマンドレットを使用して `Set-ScheduledJobOption` processjob の **WakeToRun** job オプションを True に変更します。

```powershell
Get-ScheduledJob -Name ProcessJob | Get-ScheduledJobOption |
 Set-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-scheduled-job-instances"></a>スケジュールされたジョブインスタンスを取得する方法

スケジュールされたジョブが開始されると、PowerShell は標準の PowerShell バックグラウンドジョブに似たジョブインスタンスを作成します。 ジョブのコマンドレット (やなど) を使用して、 `Get-Job` `Stop-Job` `Receive-Job` ジョブインスタンスを管理できます。

> [!NOTE]
> スケジュールされたジョブのインスタンスでジョブコマンドレットを使用するには、 **Psscheduledjob** モジュールをセッションにインポートする必要があります。 **Psscheduledjob** モジュールをインポートするには、などの `Import-Module PSScheduledJob` スケジュールされたジョブコマンドレットを入力するか、使用し `Get-ScheduledJob` ます。

PowerShell のスケジュールされたジョブのすべてのインスタンスとすべてのアクティブな標準ジョブを取得するには、コマンドレットを使用し `Get-Job` ます。 `Import-Module`コマンドレットは、 **Psscheduledjob** モジュールをインポートし、 `Get-Job` ローカルコンピューター上のジョブを取得します。

```powershell
Import-Module PSScheduledJob
Get-Job
```

`Get-Job` ローカルコンピューター上の **Processjob** のインスタンスを取得します。

```powershell
Get-Job -Name ProcessJob
```

```Output
Id     Name        PSJobTypeName  State    HasMoreData   Location   Command
--     ----        ------------   -----    -----------   --------   -------
45     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
46     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
47     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
48     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
49     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
50     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
51     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
```

既定の表示では、開始時刻は表示されません。通常、スケジュールされた同じジョブのインスタンスが区別されます。

コマンドレットにより、 `Get-Job` オブジェクトがパイプラインから送信されます。 コマンドレットにより、 `Format-Table` スケジュールされたジョブの **Name** 、 **ID** 、および **begintime** の各プロパティが表示されます。

```powershell
Get-Job ProcessJob | Format-Table -Property Name, ID, BeginTime
```

```Output
Name       Id BeginTime
----       -- ---------
ProcessJob 43 11/2/2011 3:00:02 AM
ProcessJob 44 11/3/2011 3:00:02 AM
ProcessJob 45 11/4/2011 3:00:02 AM
ProcessJob 46 11/5/2011 3:00:02 AM
ProcessJob 47 11/6/2011 3:00:02 AM
ProcessJob 48 11/7/2011 12:00:01 AM
ProcessJob 49 11/7/2011 3:00:02 AM
ProcessJob 50 11/8/2011 3:00:02 AM
```

## <a name="get-scheduled-job-results"></a>スケジュールされたジョブの結果を取得する

スケジュールされたジョブのインスタンスの結果を取得するには、コマンドレットを使用し `Receive-Job` ます。

> [!NOTE]
> スケジュールされたジョブのインスタンスでジョブコマンドレットを使用するには、 **Psscheduledjob** モジュールをセッションにインポートする必要があります。 **Psscheduledjob** モジュールをインポートするには、などの `Import-Module PSScheduledJob` スケジュールされたジョブコマンドレットを入力するか、使用し `Get-ScheduledJob` ます。

この例では、 **processjob** スケジュールされたジョブ (ID = 51) の最新のインスタンスの結果を取得します。

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 51 -Keep
```

スケジュールされたジョブの結果はディスクに保存されるため、の **Keep** パラメーター `Receive-Job` は必要ありません。 ただし、 **Keep** パラメーターを指定しないと、スケジュールされたジョブの結果を各 PowerShell セッションで1回だけ取得できます。 新しい powershell セッションを開始するに `PowerShell` は、新しい powershell ウィンドウを入力するか、開いてください。

## <a name="see-also"></a>関連項目

[about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md)

[about_Scheduled_Jobs_Troubleshooting](about_Scheduled_Jobs_Troubleshooting.md)

[about_Scheduled_Jobs](about_Scheduled_Jobs.md)

[about_Splatting](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

[Psscheduledjob](xref:PSScheduledJob) モジュールのコマンドレット

[タスク スケジューラ](/windows/desktop/TaskSchd/task-scheduler-reference)
