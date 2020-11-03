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
# <a name="about-scheduled-jobs-advanced"></a><span data-ttu-id="41489-104">スケジュールされたジョブの詳細</span><span class="sxs-lookup"><span data-stu-id="41489-104">About Scheduled Jobs Advanced</span></span>

## <a name="short-description"></a><span data-ttu-id="41489-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="41489-105">Short description</span></span>

<span data-ttu-id="41489-106">ジョブの高度なスケジュールに関するトピックについて説明します。ジョブのスケジュールの基礎となるファイル構造を含みます。</span><span class="sxs-lookup"><span data-stu-id="41489-106">Explains advanced scheduled job topics, including the file structure that underlies scheduled jobs.</span></span>

## <a name="long-description"></a><span data-ttu-id="41489-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="41489-107">Long description</span></span>

<span data-ttu-id="41489-108">**Psscheduledjob** モジュールに含まれるコマンドレットの詳細については、「 [psscheduledjob](xref:PSScheduledJob)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41489-108">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

## <a name="scheduled-job-directories-and-files"></a><span data-ttu-id="41489-109">スケジュールされたジョブのディレクトリとファイル</span><span class="sxs-lookup"><span data-stu-id="41489-109">Scheduled job directories and files</span></span>

<span data-ttu-id="41489-110">PowerShell のスケジュールされたジョブは、PowerShell ジョブとタスクスケジューラタスクの両方です。</span><span class="sxs-lookup"><span data-stu-id="41489-110">PowerShell scheduled jobs are both PowerShell jobs and Task Scheduler tasks.</span></span>
<span data-ttu-id="41489-111">スケジュールされた各ジョブはタスクスケジューラに登録され、Microsoft .NET Framework シリアル化 XML 形式でディスクに保存されます。</span><span class="sxs-lookup"><span data-stu-id="41489-111">Each scheduled job is registered in Task Scheduler and saved on disk in Microsoft .NET Framework Serialization XML format.</span></span>

<span data-ttu-id="41489-112">スケジュールされたジョブを作成すると、PowerShell によって、スケジュールされたジョブのディレクトリがローカルコンピューター上のディレクトリに作成され `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` ます。</span><span class="sxs-lookup"><span data-stu-id="41489-112">When you create a scheduled job, PowerShell creates a directory for the scheduled job in the `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` directory on the local computer.</span></span> <span data-ttu-id="41489-113">ディレクトリ名はジョブ名と同じです。</span><span class="sxs-lookup"><span data-stu-id="41489-113">The directory name is the same as the job name.</span></span>

<span data-ttu-id="41489-114">**Scheduledjobs** ディレクトリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="41489-114">The following is a sample **ScheduledJobs** directory.</span></span>

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

<span data-ttu-id="41489-115">スケジュールされた各ジョブには、独自のディレクトリがあります。</span><span class="sxs-lookup"><span data-stu-id="41489-115">Each scheduled job has its own directory.</span></span> <span data-ttu-id="41489-116">ディレクトリには、スケジュールされたジョブの XML ファイルと **出力** サブディレクトリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="41489-116">The directory contains the scheduled job XML file and an **Output** subdirectory.</span></span>

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

<span data-ttu-id="41489-117">スケジュールされたジョブの **出力** ディレクトリには、実行履歴が含まれています。</span><span class="sxs-lookup"><span data-stu-id="41489-117">The **Output** directory for a scheduled job contains its execution history.</span></span>
<span data-ttu-id="41489-118">ジョブトリガーによってスケジュールされたジョブが開始されるたびに、PowerShell は、タイムスタンプ付きのディレクトリを出力ディレクトリに作成します。</span><span class="sxs-lookup"><span data-stu-id="41489-118">Each time a job trigger starts a scheduled job, PowerShell creates a timestamp-named directory in the output directory.</span></span> <span data-ttu-id="41489-119">タイムスタンプディレクトリには、 **Results.xml** ファイル内のジョブの結果と、 **Status.xml** ファイル内のジョブの状態が含まれます。</span><span class="sxs-lookup"><span data-stu-id="41489-119">The timestamp directory contains the results of the job in a **Results.xml** file and the job status in a **Status.xml** file.</span></span>

<span data-ttu-id="41489-120">次のコマンドは、スケジュールされたジョブ **Processjob** の実行履歴ディレクトリを示しています。</span><span class="sxs-lookup"><span data-stu-id="41489-120">The following command shows the execution history directories for the **ProcessJob** scheduled job.</span></span>

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

<span data-ttu-id="41489-121">**ScheduledJobDefinition.xml** を開いて確認し、ファイルを **Results.xml** して **Status.xml** します。または、コマンドレットを使用してファイルを解析することもでき `Select-XML` ます。</span><span class="sxs-lookup"><span data-stu-id="41489-121">You can open and examine the **ScheduledJobDefinition.xml** , **Results.xml** and **Status.xml** files or use the `Select-XML` cmdlet to parse the files.</span></span>

> [!WARNING]
> <span data-ttu-id="41489-122">XML ファイルは編集しないでください。</span><span class="sxs-lookup"><span data-stu-id="41489-122">Do not edit the XML files.</span></span> <span data-ttu-id="41489-123">XML ファイルに無効な XML が含まれている場合は、スケジュールされたジョブとその実行履歴 (ジョブの結果を含む) が PowerShell によって削除されます。</span><span class="sxs-lookup"><span data-stu-id="41489-123">If any XML file contains invalid XML, PowerShell deletes the scheduled job and its execution history, including job results.</span></span>

## <a name="start-a-scheduled-job-immediately"></a><span data-ttu-id="41489-124">スケジュールされたジョブをすぐに開始する</span><span class="sxs-lookup"><span data-stu-id="41489-124">Start a scheduled job immediately</span></span>

<span data-ttu-id="41489-125">次の2つの方法のいずれかで、スケジュールされたジョブをすぐに開始できます。</span><span class="sxs-lookup"><span data-stu-id="41489-125">You can start a scheduled job immediately in one of two ways:</span></span>

- <span data-ttu-id="41489-126">コマンドレットを実行して、 `Start-Job` スケジュールされたジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="41489-126">Run the `Start-Job` cmdlet to start any scheduled job.</span></span>
- <span data-ttu-id="41489-127">コマンドを実行した直後にジョブを開始するには、 **Runnow** パラメーターをコマンドに追加し `Register-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="41489-127">Add the **RunNow** parameter to your `Register-ScheduledJob` command to start the job as soon as the command is run.</span></span>

<span data-ttu-id="41489-128">コマンドレットを使用して開始されたジョブ `Start-Job` は、スケジュールされたジョブのインスタンスではなく、標準の PowerShell バックグラウンドジョブです。</span><span class="sxs-lookup"><span data-stu-id="41489-128">Jobs that are started by using the `Start-Job` cmdlet are standard PowerShell background jobs, not instances of the scheduled job.</span></span> <span data-ttu-id="41489-129">すべてのバックグラウンドジョブと同様に、これらのジョブはすぐに開始され、ジョブのオプションやジョブトリガーの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="41489-129">Like all background jobs, these jobs start immediately, they aren't subject to job options or affected by job triggers.</span></span> <span data-ttu-id="41489-130">ジョブの出力は、スケジュールされたジョブディレクトリの **出力** ディレクトリに保存されません。</span><span class="sxs-lookup"><span data-stu-id="41489-130">The job output isn't saved in the **Output** directory of the scheduled job directory.</span></span>

<span data-ttu-id="41489-131">次のコマンドでは、コマンドレットの **Definitionname** パラメーターを使用して、 `Start-Job` スケジュールされたジョブ processjob を開始します。</span><span class="sxs-lookup"><span data-stu-id="41489-131">The following command uses the **DefinitionName** parameter of the `Start-Job` cmdlet to start the ProcessJob scheduled job.</span></span>

```powershell
Start-Job -DefinitionName ProcessJob
```

<span data-ttu-id="41489-132">ジョブを管理してジョブの結果を取得するには、job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="41489-132">To manage the job and get the job results, use the job cmdlets.</span></span> <span data-ttu-id="41489-133">ジョブコマンドレットの詳細については、「 [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41489-133">For more information about the job cmdlets, see [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

> [!NOTE]
> <span data-ttu-id="41489-134">スケジュールされたジョブのインスタンスでジョブコマンドレットを使用するには、 **Psscheduledjob** モジュールをセッションにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="41489-134">To use the Job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="41489-135">**Psscheduledjob** モジュールをインポートするには、などの `Import-Module PSScheduledJob` スケジュールされたジョブコマンドレットを入力するか、使用し `Get-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="41489-135">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

## <a name="rename-a-scheduled-job"></a><span data-ttu-id="41489-136">スケジュールされたジョブの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="41489-136">Rename a scheduled job</span></span>

<span data-ttu-id="41489-137">スケジュールされたジョブの名前を変更するには、コマンドレットの Name パラメーターを使用し `Set-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="41489-137">To rename a scheduled job, use the Name parameter of the `Set-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="41489-138">スケジュールされたジョブの名前を変更すると、PowerShell によって、スケジュールされたジョブの名前とスケジュールされたジョブディレクトリが変更されます。</span><span class="sxs-lookup"><span data-stu-id="41489-138">When you rename a scheduled job, PowerShell changes the name of the scheduled job and the scheduled job directory.</span></span> <span data-ttu-id="41489-139">ただし、既に実行されているスケジュールされたジョブのインスタンスの名前は変更されません。</span><span class="sxs-lookup"><span data-stu-id="41489-139">However, it doesn't change the names of instances of the scheduled job that have already run.</span></span>

## <a name="get-start-and-end-times"></a><span data-ttu-id="41489-140">開始時刻と終了時刻を取得する</span><span class="sxs-lookup"><span data-stu-id="41489-140">Get start and end times</span></span>

<span data-ttu-id="41489-141">ジョブインスタンスの開始日時と終了時刻を取得するには、スケジュールされたジョブに対してを返す ScheduledJob オブジェクトの **Psbegintime** プロパティと **psendtime** プロパティを使用し `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="41489-141">To get the dates and times that job instances started and ended, use the **PSBeginTime** and **PSEndTime** properties of the ScheduledJob object that `Get-Job` returns for scheduled jobs.</span></span>

<span data-ttu-id="41489-142">次の例では、コマンドレットの **Property** パラメーターを使用して、 `Format-Table` テーブル内の各ジョブインスタンスの **Psbegintime** および **psendtime** プロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="41489-142">The following example uses the **Property** parameter of the `Format-Table` cmdlet to display the **PSBeginTime** and **PSEndTime** properties of each job instance in a table.</span></span> <span data-ttu-id="41489-143">" **ラベル** " という名前の計算プロパティには、各ジョブインスタンスの経過時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="41489-143">A calculated property named **Label** displays the elapsed time of each job instance.</span></span>

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

## <a name="manage-execution-history"></a><span data-ttu-id="41489-144">実行履歴の管理</span><span class="sxs-lookup"><span data-stu-id="41489-144">Manage execution history</span></span>

<span data-ttu-id="41489-145">スケジュールされたジョブごとに保存されるジョブインスタンスの結果の数を特定し、スケジュールされたジョブの実行履歴と保存されたジョブの結果を削除できます。</span><span class="sxs-lookup"><span data-stu-id="41489-145">You can determine the number of job instance results that are saved for each scheduled job and delete the execution history and saved job results of any scheduled job.</span></span>

<span data-ttu-id="41489-146">スケジュールされたジョブの **Executionhistory length** プロパティは、スケジュールされたジョブに対して保存されるジョブインスタンスの結果の数を決定します。</span><span class="sxs-lookup"><span data-stu-id="41489-146">The **ExecutionHistoryLength** property of a scheduled job determines how many job instance results are saved for the scheduled job.</span></span> <span data-ttu-id="41489-147">保存された結果の数が **Executionhistory length** プロパティの値を超えると、PowerShell は最も古いインスタンスの結果を削除して、最新のインスタンスの結果を格納するための領域を確保します。</span><span class="sxs-lookup"><span data-stu-id="41489-147">When the number of saved results exceeds the value of the **ExecutionHistoryLength** property, PowerShell deletes the results of the oldest instance to make room for the results of the newest instance.</span></span>

<span data-ttu-id="41489-148">既定では、PowerShell は、スケジュールされた各ジョブの実行履歴と32インスタンスの結果を保存します。</span><span class="sxs-lookup"><span data-stu-id="41489-148">By default, PowerShell saves the execution history and results of 32 instances of each scheduled job.</span></span> <span data-ttu-id="41489-149">この値を変更するには、またはコマンドレットの **Maxresultcount** パラメーターを使用し `Register-ScheduledJob` `Set-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="41489-149">To change that value, use the **MaxResultCount** parameters of the `Register-ScheduledJob` or `Set-ScheduledJob` cmdlets.</span></span>

<span data-ttu-id="41489-150">スケジュールされたジョブの実行履歴とすべての結果を削除するには、コマンドレットの **ClearExecutionHistory** パラメーターを使用し `Set-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="41489-150">To delete the execution history and all results for a scheduled job, use the **ClearExecutionHistory** parameter of the `Set-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="41489-151">この実行履歴を削除しても、スケジュールされたジョブの新しいインスタンスの結果が PowerShell によって保存されるのを防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="41489-151">Deleting this execution history does not prevent PowerShell from saving the results of new instances of the scheduled job.</span></span>

<span data-ttu-id="41489-152">次の例では、スプラッティングを使用し `$JobParms` て、コマンドレットに渡されるパラメーター値を作成し `Register-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="41489-152">The following example uses splatting to create `$JobParms` which are parameter values that are passed to the `Register-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="41489-153">詳細については、 [about_Splatting](../../Microsoft.PowerShell.Core/About/about_Splatting.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41489-153">For more information, see [about_Splatting.md](../../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>
<span data-ttu-id="41489-154">は、 `Register-ScheduledJob` を使用して `@JobParms` スケジュールされたジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="41489-154">The `Register-ScheduledJob` uses `@JobParms` to create a scheduled job.</span></span> <span data-ttu-id="41489-155">このコマンドでは、 **Maxresultcount** パラメーターを値12として使用し、スケジュールされたジョブのジョブインスタンスの最新の12個の結果のみを保存します。</span><span class="sxs-lookup"><span data-stu-id="41489-155">The command uses the **MaxResultCount** parameter with a value of 12 to save only the 12 newest job instance results of the scheduled job.</span></span>

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  MaxResultCount = "12"
}

Register-ScheduledJob @JobParms
```

<span data-ttu-id="41489-156">次のコマンドでは、コマンドレットの **Maxresultcount** パラメーターを使用して `Set-ScheduledJob` 、保存されたインスタンスの結果の数をに増やします。</span><span class="sxs-lookup"><span data-stu-id="41489-156">The following command uses the **MaxResultCount** parameter of the `Set-ScheduledJob` cmdlet to increase the number of saved instance results to</span></span>
15.

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -MaxResultCount 15
```

<span data-ttu-id="41489-157">次のコマンドは、スケジュールされたジョブ **processjob** の実行履歴と現在保存されている結果を削除します。</span><span class="sxs-lookup"><span data-stu-id="41489-157">The following command deletes the execution history and the current saved results of the **ProcessJob** scheduled job.</span></span>

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -ClearExecutionHistory
```

<span data-ttu-id="41489-158">次のコマンドは、コンピューター上のスケジュールされたすべてのジョブの name プロパティと **Executionhistory length** プロパティの値を取得し、テーブルに表示します。</span><span class="sxs-lookup"><span data-stu-id="41489-158">The following command gets the values of the name and **ExecutionHistoryLength** properties of all scheduled jobs on the computer and displays them in a table.</span></span>

```powershell
Get-ScheduledJob | 
  Format-Table -Property Name, ExecutionHistoryLength -AutoSize
```

## <a name="see-also"></a><span data-ttu-id="41489-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="41489-159">See also</span></span>

[<span data-ttu-id="41489-160">about_Scheduled_Jobs_Basics</span><span class="sxs-lookup"><span data-stu-id="41489-160">about_Scheduled_Jobs_Basics</span></span>](about_Scheduled_Jobs_Basics.md)

[<span data-ttu-id="41489-161">about_Scheduled_Jobs_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="41489-161">about_Scheduled_Jobs_Troubleshooting</span></span>](about_Scheduled_Jobs_Troubleshooting.md)

[<span data-ttu-id="41489-162">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="41489-162">about_Scheduled_Jobs</span></span>](about_Scheduled_Jobs.md)

[<span data-ttu-id="41489-163">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="41489-163">about_Splatting.md</span></span>](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

<span data-ttu-id="41489-164">[Psscheduledjob](xref:PSScheduledJob) モジュールのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="41489-164">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="41489-165">タスク スケジューラ</span><span class="sxs-lookup"><span data-stu-id="41489-165">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
