---
description: ジョブの高度なスケジュールに関するトピックについて説明します。ジョブのスケジュールの基礎となるファイル構造を含みます。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_advanced?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Advanced
ms.openlocfilehash: 7b09a72e8ad7e68641c73d2f7e59065dbf8f889b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221936"
---
# <a name="about-scheduled-jobs-advanced"></a>スケジュールされたジョブの詳細

## <a name="short-description"></a>簡単な説明

ジョブの高度なスケジュールに関するトピックについて説明します。ジョブのスケジュールの基礎となるファイル構造を含みます。

## <a name="long-description"></a>長い説明

**Psscheduledjob** モジュールに含まれるコマンドレットの詳細については、「 [psscheduledjob](xref:PSScheduledJob)」を参照してください。

## <a name="scheduled-job-directories-and-files"></a>スケジュールされたジョブのディレクトリとファイル

PowerShell のスケジュールされたジョブは、PowerShell ジョブとタスクスケジューラタスクの両方です。
スケジュールされた各ジョブはタスクスケジューラに登録され、Microsoft .NET Framework シリアル化 XML 形式でディスクに保存されます。

スケジュールされたジョブを作成すると、PowerShell によって、スケジュールされたジョブのディレクトリがローカルコンピューター上のディレクトリに作成され `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` ます。 ディレクトリ名はジョブ名と同じです。

**Scheduledjobs** ディレクトリの例を次に示します。

```powershell
Get-ChildItem $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs
```

```Output
Directory: C:\Users\User01\AppData\Local
               \Microsoft\Windows\PowerShell\ScheduledJobs

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         9/29/2011  10:03 AM            ArchiveProjects
d----         9/30/2011   1:18 PM            Inventory
d----        10/20/2011   9:15 AM            Backup-Scripts
d----         11/7/2011  10:40 AM            ProcessJob
d----         11/2/2011  10:25 AM            SecureJob
d----         9/27/2011   1:29 PM            Test-HelpFiles
d----         9/26/2011   4:22 PM            DeployPackage
```

スケジュールされた各ジョブには、独自のディレクトリがあります。 ディレクトリには、スケジュールされたジョブの XML ファイルと **出力** サブディレクトリが含まれています。

```powershell
$Path = "$home\AppData\Local\Microsoft\Windows\PowerShell"
$Path += "\ScheduledJobs\ProcessJob"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         11/1/2011   3:00 PM            Output
-a---         11/1/2011   3:43 PM       7281 ScheduledJobDefinition.xml
```

スケジュールされたジョブの **出力** ディレクトリには、実行履歴が含まれています。
ジョブトリガーによってスケジュールされたジョブが開始されるたびに、PowerShell は、タイムスタンプ付きのディレクトリを出力ディレクトリに作成します。 タイムスタンプディレクトリには、 **Results.xml** ファイル内のジョブの結果と、 **Status.xml** ファイル内のジョブの状態が含まれます。

次のコマンドは、スケジュールされたジョブ **Processjob** の実行履歴ディレクトリを示しています。

```powershell
$Path = "$home\AppData\Local\Microsoft"
$Path += "\Windows\PowerShell\ScheduledJobs\ProcessJob\Output"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft
               \Windows\PowerShell\ScheduledJobs\ProcessJob\Output

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         11/2/2011   3:00 AM            20111102-030002-260
d----         11/3/2011   3:00 AM            20111103-030002-277
d----         11/4/2011   3:00 AM            20111104-030002-209
d----         11/5/2011   3:00 AM            20111105-030002-251
d----         11/6/2011   3:00 AM            20111106-030002-174
d----         11/7/2011  12:00 AM            20111107-000001-914
d----         11/7/2011   3:00 AM            20111107-030002-376
```

```powershell
$Path = "$home\AppData\Local\Microsoft\Windows\PowerShell\"
$Path += "ScheduledJobs\ProcessJob\Output\20111102-030002-260"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output\20111102-030002-260

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---         11/2/2011   3:00 AM     581106 Results.xml
-a---         11/2/2011   3:00 AM       9451 Status.xml
```

**ScheduledJobDefinition.xml** を開いて確認し、ファイルを **Results.xml** して **Status.xml** します。または、コマンドレットを使用してファイルを解析することもでき `Select-XML` ます。

> [!WARNING]
> XML ファイルは編集しないでください。 XML ファイルに無効な XML が含まれている場合は、スケジュールされたジョブとその実行履歴 (ジョブの結果を含む) が PowerShell によって削除されます。

## <a name="start-a-scheduled-job-immediately"></a>スケジュールされたジョブをすぐに開始する

次の2つの方法のいずれかで、スケジュールされたジョブをすぐに開始できます。

- コマンドレットを実行して、 `Start-Job` スケジュールされたジョブを開始します。
- コマンドを実行した直後にジョブを開始するには、 **Runnow** パラメーターをコマンドに追加し `Register-ScheduledJob` ます。

コマンドレットを使用して開始されたジョブ `Start-Job` は、スケジュールされたジョブのインスタンスではなく、標準の PowerShell バックグラウンドジョブです。 すべてのバックグラウンドジョブと同様に、これらのジョブはすぐに開始され、ジョブのオプションやジョブトリガーの影響を受けません。 ジョブの出力は、スケジュールされたジョブディレクトリの **出力** ディレクトリに保存されません。

次のコマンドでは、コマンドレットの **Definitionname** パラメーターを使用して、 `Start-Job` スケジュールされたジョブ processjob を開始します。

```powershell
Start-Job -DefinitionName ProcessJob
```

ジョブを管理してジョブの結果を取得するには、job コマンドレットを使用します。 ジョブコマンドレットの詳細については、「 [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md)」を参照してください。

> [!NOTE]
> スケジュールされたジョブのインスタンスでジョブコマンドレットを使用するには、 **Psscheduledjob** モジュールをセッションにインポートする必要があります。 **Psscheduledjob** モジュールをインポートするには、などの `Import-Module PSScheduledJob` スケジュールされたジョブコマンドレットを入力するか、使用し `Get-ScheduledJob` ます。

## <a name="rename-a-scheduled-job"></a>スケジュールされたジョブの名前を変更する

スケジュールされたジョブの名前を変更するには、コマンドレットの Name パラメーターを使用し `Set-ScheduledJob` ます。 スケジュールされたジョブの名前を変更すると、PowerShell によって、スケジュールされたジョブの名前とスケジュールされたジョブディレクトリが変更されます。 ただし、既に実行されているスケジュールされたジョブのインスタンスの名前は変更されません。

## <a name="get-start-and-end-times"></a>開始時刻と終了時刻を取得する

ジョブインスタンスの開始日時と終了時刻を取得するには、スケジュールされたジョブに対してを返す ScheduledJob オブジェクトの **Psbegintime** プロパティと **psendtime** プロパティを使用し `Get-Job` ます。

次の例では、コマンドレットの **Property** パラメーターを使用して、 `Format-Table` テーブル内の各ジョブインスタンスの **Psbegintime** および **psendtime** プロパティを表示します。 " **ラベル** " という名前の計算プロパティには、各ジョブインスタンスの経過時間が表示されます。

```powershell
Get-job -Name UpdateHelpJob | 
  Format-Table -Property ID, PSBeginTime, PSEndTime,
@{Label="Elapsed Time";Expression={$.PsEndTime - $.PSBeginTime}}
```

```Output
Id   PSBeginTime             PSEndTime                Elapsed Time
--   -----------             ---------                ------------
 2   11/3/2011 3:00:01 AM    11/3/2011 3:00:39 AM     00:00:38.0053854
 3   11/4/2011 3:00:02 AM    11/4/2011 3:01:01 AM     00:00:59.1188475
 4   11/5/2011 3:00:02 AM    11/5/2011 3:00:50 AM     00:00:48.3692034
 5   11/6/2011 3:00:01 AM    11/6/2011 3:00:54 AM     00:00:52.8013036
 6   11/7/2011 3:00:01 AM    11/7/2011 3:00:38 AM     00:00:37.1930350
 7   11/8/2011 3:00:01 AM    11/8/2011 3:00:57 AM     00:00:56.2570556
 8   11/9/2011 3:00:03 AM    11/9/2011 3:00:55 AM     00:00:51.8142222
 9   11/10/2011 3:00:02 AM   11/10/2011 3:00:42 AM    00:00:40.7195954
```

## <a name="manage-execution-history"></a>実行履歴の管理

スケジュールされたジョブごとに保存されるジョブインスタンスの結果の数を特定し、スケジュールされたジョブの実行履歴と保存されたジョブの結果を削除できます。

スケジュールされたジョブの **Executionhistory length** プロパティは、スケジュールされたジョブに対して保存されるジョブインスタンスの結果の数を決定します。 保存された結果の数が **Executionhistory length** プロパティの値を超えると、PowerShell は最も古いインスタンスの結果を削除して、最新のインスタンスの結果を格納するための領域を確保します。

既定では、PowerShell は、スケジュールされた各ジョブの実行履歴と32インスタンスの結果を保存します。 この値を変更するには、またはコマンドレットの **Maxresultcount** パラメーターを使用し `Register-ScheduledJob` `Set-ScheduledJob` ます。

スケジュールされたジョブの実行履歴とすべての結果を削除するには、コマンドレットの **ClearExecutionHistory** パラメーターを使用し `Set-ScheduledJob` ます。 この実行履歴を削除しても、スケジュールされたジョブの新しいインスタンスの結果が PowerShell によって保存されるのを防ぐことはできません。

次の例では、スプラッティングを使用し `$JobParms` て、コマンドレットに渡されるパラメーター値を作成し `Register-ScheduledJob` ます。 詳細については、 [about_Splatting](../../Microsoft.PowerShell.Core/About/about_Splatting.md)を参照してください。
は、 `Register-ScheduledJob` を使用して `@JobParms` スケジュールされたジョブを作成します。 このコマンドでは、 **Maxresultcount** パラメーターを値12として使用し、スケジュールされたジョブのジョブインスタンスの最新の12個の結果のみを保存します。

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  MaxResultCount = "12"
}

Register-ScheduledJob @JobParms
```

次のコマンドでは、コマンドレットの **Maxresultcount** パラメーターを使用して `Set-ScheduledJob` 、保存されたインスタンスの結果の数をに増やします。
15.

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -MaxResultCount 15
```

次のコマンドは、スケジュールされたジョブ **processjob** の実行履歴と現在保存されている結果を削除します。

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -ClearExecutionHistory
```

次のコマンドは、コンピューター上のスケジュールされたすべてのジョブの name プロパティと **Executionhistory length** プロパティの値を取得し、テーブルに表示します。

```powershell
Get-ScheduledJob | 
  Format-Table -Property Name, ExecutionHistoryLength -AutoSize
```

## <a name="see-also"></a>関連項目

[about_Scheduled_Jobs_Basics](about_Scheduled_Jobs_Basics.md)

[about_Scheduled_Jobs_Troubleshooting](about_Scheduled_Jobs_Troubleshooting.md)

[about_Scheduled_Jobs](about_Scheduled_Jobs.md)

[about_Splatting](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

[Psscheduledjob](xref:PSScheduledJob) モジュールのコマンドレット

[タスク スケジューラ](/windows/desktop/TaskSchd/task-scheduler-reference)
