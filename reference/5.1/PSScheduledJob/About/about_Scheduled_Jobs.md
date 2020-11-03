---
description: スケジュールされたジョブについて説明し、PowerShell およびタスクスケジューラでスケジュールされたジョブを使用および管理する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs
ms.openlocfilehash: 4d4e86957a584bb4deb47cadcd8588c1236455ac
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221939"
---
# <a name="about-scheduled-jobs"></a>スケジュールされたジョブについて

## <a name="short-description"></a>簡単な説明

スケジュールされたジョブについて説明し、PowerShell およびタスクスケジューラでスケジュールされたジョブを使用および管理する方法について説明します。

## <a name="long-description"></a>長い説明

PowerShell のスケジュールされたジョブは、PowerShell バックグラウンドジョブとタスクスケジューラタスクの便利なハイブリッドです。

PowerShell のバックグラウンドジョブと同様、スケジュールされたジョブはバックグラウンドで非同期に実行されます。 実行されたスケジュールされたジョブのインスタンスは、、、、などのジョブコマンドレットを使用して管理でき `Start-Job` `Get-Job` `Stop-Job` `Receive-Job` ます。

タスクスケジューラのタスクと同様に、スケジュールされたジョブはディスクに保存されます。 タスクスケジューラでジョブを表示して管理したり、必要に応じて有効または無効にしたり、実行したり、テンプレートとして使用したり、ジョブを開始するための1回限りまたは定期的なスケジュールを設定したり、ジョブを開始する条件を設定したりできます。

さらに、スケジュールされたジョブインスタンスの結果は、簡単にアクセスできる形式でディスクに保存され、ジョブ出力の実行ログが提供されます。 スケジュールされたジョブには、それらを管理するためのカスタマイズされたコマンドレットセットが付属しています。 コマンドレットを使用すると、スケジュールされたジョブ、ジョブトリガー、およびジョブオプションの作成、編集、管理、無効化、および再有効化を行うことができます。

この包括的で柔軟なツールセットによって、スケジュールされたジョブが多くの professional PowerShell IT ソリューションの重要なコンポーネントとなります。

スケジュールされたジョブコマンドレットは、PowerShell と共にインストールされる **Psscheduledjob** モジュールに含まれています。 このモジュールは powershell 3.0 で導入され、powershell 3.0 以降のバージョンの PowerShell で動作します。 **Psscheduledjob** モジュールに含まれるコマンドレットの詳細については、「 [psscheduledjob](xref:PSScheduledJob)」を参照してください。

PowerShell バックグラウンドジョブの詳細については、「 [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md)」を参照してください。

タスクスケジューラの詳細については、「 [タスクスケジューラ](/windows/desktop/TaskSchd/task-scheduler-reference)」を参照してください。

> [!NOTE]
> タスクスケジューラで、PowerShell のスケジュールされたジョブを表示および管理できます。 PowerShell ジョブおよびスケジュールされたジョブコマンドレットは、PowerShell で作成されたスケジュールされたジョブでのみ機能します。

## <a name="quick-start"></a>クイック スタート

この例では、毎日 3:00 AM に開始し、コマンドレットを実行するスケジュールされたジョブを作成し `Get-Process` ます。 コンピューターがバッテリで動作している場合でもジョブは開始されます。

```powershell
$trigger = New-JobTrigger -Daily -At 3AM
$options = New-ScheduledJobOption -StartIfOnBattery
Register-ScheduledJob -Name ProcessJob -ScriptBlock {Get-Process} `
-Trigger $trigger -ScheduledJobOption $options
```

`Get-ScheduledJob`コマンドレットは、ローカルコンピューター上のスケジュールされたジョブを取得します。

```powershell
Get-ScheduledJob
```

```Output
Id         Name            Triggers        Command            Enabled
--         ----            --------        -------            -------
7          ProcessJob      {1}             Get-Process        True
```

`Get-JobTrigger`**processjob** のジョブトリガーを取得します。 トリガーはスケジュールされたジョブに保存されるので、入力パラメーターでは、トリガーではなくスケジュールされたジョブを指定します。

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id         Frequency       Time                   DaysOfWeek        Enabled
--         ---------       ----                   ----------        -------
1          Daily           11/5/2011 3:00:00 AM                     True
```

この例では、コマンドレットの **続行 Eifgoingonバッテリ** パラメーターを使用して、 `Set-ScheduledJob` **Processjob** の **stopifgoingonbatteries** プロパティを **False** に変更します。

```powershell
Get-ScheduledJob -Name ProcessJob | Set-ScheduledJobOption `
-ContinueIfGoingOnBattery -Passthru
```

```Output
StartIfOnBatteries     : True
StopIfGoingOnBatteries : False
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
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

コマンドレットでは、スケジュールされた `Get-ScheduledJob` **processjob** ジョブを取得します。

```powershell
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command        Enabled
--         ----            --------        -------        -------
7          ProcessJob      {1}             Get-Process    True
```

`Get-Job`このコマンドレットは、これまでに実行された **processjob** スケジュールされたジョブのすべてのインスタンスを取得します。 `Get-Job`コマンドレットは、 **Psscheduledjob** モジュールが現在のセッションにインポートされた場合にのみ、スケジュールされたジョブを取得します。

> [!TIP]
> スケジュールされたジョブコマンドレットを使用して、スケジュールされたジョブを管理しますが、スケジュールされたジョブのインスタンスを管理するには、job コマンドレットを使用します。

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

コマンドレットでは、 `Receive-Job` **processjob** スケジュールされたジョブ (ID = 51) の最新のインスタンスの結果を取得します。

```powershell
Receive-Job -ID 51
```

`Receive-Job`コマンドに **Keep** パラメーターが含まれていなくても、ジョブが削除されるか、または結果の最大数を超えるまで、ジョブの結果がディスクに保存されます。

ジョブの結果はこのセッションでは利用できなくなりましたが、新しいセッションを開始するか、新しい PowerShell ウィンドウを開くと、ジョブの結果が再び使用可能になります。

次のコマンドでは、コマンドレットの **Definitionname** パラメーターを使用して、 `Start-Job` スケジュールされたジョブ **processjob** を開始します。

コマンドレットを使用して開始されたジョブ `Start-Job` は、スケジュールされたジョブのインスタンスではなく、標準の PowerShell バックグラウンドジョブです。 すべてのバックグラウンドジョブと同様に、これらのジョブはすぐに開始され、ジョブのオプションやジョブトリガーの影響を受けません。また、それらの出力は、スケジュールされたジョブディレクトリの出力ディレクトリに保存されません。

```powershell
Start-Job -DefinitionName ProcessJob
```

`Unregister-ScheduledJob`コマンドレットは、スケジュールされたジョブ **processjob** とそのジョブインスタンスの保存されたすべての結果を削除します。

```powershell
Unregister-ScheduledJob ProcessJob
```

## <a name="scheduled-jobs-concepts"></a>スケジュールされたジョブの概念

スケジュールされたジョブは、コマンドまたはスクリプトを実行します。 スケジュールされたジョブには、ジョブを開始するジョブトリガーや、ジョブを実行するための条件を設定するジョブオプションを含めることができます。

ジョブトリガーは、スケジュールされたジョブを自動的に開始します。 ジョブトリガーには、1回限りのスケジュールまたは定期的なスケジュールを含めることも、ユーザーがログオンしたときや Windows が起動したときなどのイベントを指定することもできます。 スケジュールされたジョブには、1つまたは複数のジョブトリガーを含めることができます。また、ジョブトリガーを作成、追加、有効化、無効化、および取得することができます。

ジョブ トリガーは省略可能です。 を使用する `Start-Job cmdlet` か、コマンドに **runnow** パラメーターを追加することで、スケジュールされたジョブをすぐに開始でき `Register-ScheduledJob` ます。

ジョブオプションは、スケジュールされたジョブを実行するための条件を設定します。 スケジュールされたすべてのジョブには、1つのジョブオプションオブジェクトがあります。 ジョブオプションオブジェクトを作成および編集して、1つまたは複数のスケジュールされたジョブに追加することができます。

スケジュールされたジョブが開始されるたびに、ジョブインスタンスが作成されます。 PowerShell ジョブのコマンドレットを使用して、ジョブインスタンスを表示および管理します。

スケジュールされたジョブはディスクに保存され、ではなく、コマンドレット動詞を使用し `Register` `New` ます。 XML ファイルは、ディレクトリ内のローカルコンピューターに配置され `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` ます。

PowerShell は、スケジュールされたジョブごとにディレクトリを作成し、ジョブコマンド、ジョブトリガー、ジョブオプション、ジョブの結果をスケジュールされたジョブディレクトリに保存します。 ジョブトリガーとジョブオプションは、個別にディスクに保存されません。
これらのジョブは、関連付けられているスケジュールされたジョブごとに、スケジュールされたジョブの XML に保存されます。

スケジュールされたジョブ、ジョブトリガー、およびジョブオプションは、オブジェクトとして PowerShell に表示されます。
オブジェクトは interlinked であるため、コマンドやスクリプトで簡単に検出して使用できます。

スケジュールされたジョブは、 **ScheduledJobDefinition** オブジェクトとして表示されます。 **ScheduledJobDefinition** オブジェクトには、スケジュールされたジョブのジョブトリガーと、ジョブオプションを含む **options** プロパティを含む **jobtriggers** プロパティがあります。 ジョブトリガーとジョブオプションを表す **Scheduledjobtriggers** および **ScheduledJobOptions** オブジェクトにはそれぞれ、関連付けられているスケジュールされたジョブを含む **JobDefinition** プロパティがあります。 この再帰的な相互接続により、スケジュールされたジョブのトリガーとオプションを簡単に見つけて、ジョブトリガーまたはジョブオプションが関連付けられているスケジュールされたジョブを検索、スクリプト化、および表示することができます。

## <a name="see-also"></a>関連項目

[about_Scheduled_Jobs_Basics](about_Scheduled_Jobs_Basics.md)

[about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md)

[about_Scheduled_Jobs_Troubleshooting](about_Scheduled_Jobs_Troubleshooting.md)

[Psscheduledjob](xref:PSScheduledJob) モジュールのコマンドレット

[タスク スケジューラ](/windows/desktop/TaskSchd/task-scheduler-reference)
