---
description: スケジュールされたジョブに関する問題の解決方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_troubleshooting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Troubleshooting
ms.openlocfilehash: 924205edb9d44724cfef201d84baa304ecde67ad
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221920"
---
# <a name="about-scheduled-jobs-troubleshooting"></a><span data-ttu-id="cd34c-104">スケジュールされたジョブのトラブルシューティングについて</span><span class="sxs-lookup"><span data-stu-id="cd34c-104">About Scheduled Jobs Troubleshooting</span></span>

## <a name="short-description"></a><span data-ttu-id="cd34c-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="cd34c-105">Short description</span></span>

<span data-ttu-id="cd34c-106">スケジュールされたジョブに関する問題の解決方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-106">Explains how to resolve problems with scheduled jobs</span></span>

## <a name="long-description"></a><span data-ttu-id="cd34c-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="cd34c-107">Long description</span></span>

<span data-ttu-id="cd34c-108">このドキュメントでは、PowerShell のスケジュールされたジョブ機能を使用するときに発生する可能性がある問題のいくつかについて説明し、これらの問題に対する解決策を提案します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-108">This document describes some of the problems that you might experience when using the scheduled job features of PowerShell and it suggests solutions to these problems.</span></span>

<span data-ttu-id="cd34c-109">PowerShell のスケジュールされたジョブを使用する前に、「 [about_Scheduled_Jobs](about_Scheduled_Jobs.md) 」および関連するスケジュールされたジョブに関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd34c-109">Before using PowerShell scheduled jobs, see [about_Scheduled_Jobs](about_Scheduled_Jobs.md) and the related scheduled jobs about topics.</span></span>

<span data-ttu-id="cd34c-110">**Psscheduledjob** モジュールに含まれるコマンドレットの詳細については、「 [psscheduledjob](xref:PSScheduledJob)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd34c-110">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

## <a name="cant-find-job-results"></a><span data-ttu-id="cd34c-111">ジョブの結果が見つかりません</span><span class="sxs-lookup"><span data-stu-id="cd34c-111">Can't find job results</span></span>

### <a name="basic-method-for-getting-job-results-in-powershell"></a><span data-ttu-id="cd34c-112">PowerShell でジョブ結果を取得するための基本的な方法</span><span class="sxs-lookup"><span data-stu-id="cd34c-112">Basic method for getting job results in PowerShell</span></span>

<span data-ttu-id="cd34c-113">スケジュールされたジョブを実行すると、スケジュールされたジョブのインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-113">When a scheduled job runs, it creates an instance of the scheduled job.</span></span> <span data-ttu-id="cd34c-114">スケジュールされたジョブインスタンスの結果を表示、管理、および取得するには、Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-114">To view, manage, and get the results of scheduled job instances, use the Job cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="cd34c-115">スケジュールされたジョブのインスタンスでジョブコマンドレットを使用するには、 **Psscheduledjob** モジュールをセッションにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd34c-115">To use the Job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="cd34c-116">**Psscheduledjob** モジュールをインポートするには、などの `Import-Module PSScheduledJob` スケジュールされたジョブコマンドレットを入力するか、使用し `Get-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-116">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

<span data-ttu-id="cd34c-117">スケジュールされたジョブのすべてのインスタンスの一覧を取得するには、コマンドレットを使用し `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-117">To get a list of all instances of a scheduled job, use the `Get-Job` cmdlet.</span></span>

```powershell
Import-Module PSScheduledJob
Get-Job ProcessJob
```

```Output
Id     Name         PSJobTypeName   State         HasMoreData     Location
--     ----         -------------   -----         -----------     --------
43     ProcessJob   PSScheduledJob  Completed     False           localhost
44     ProcessJob   PSScheduledJob  Completed     False           localhost
45     ProcessJob   PSScheduledJob  Completed     False           localhost
46     ProcessJob   PSScheduledJob  Completed     False           localhost
47     ProcessJob   PSScheduledJob  Completed     False           localhost
48     ProcessJob   PSScheduledJob  Completed     False           localhost
49     ProcessJob   PSScheduledJob  Completed     False           localhost
50     ProcessJob   PSScheduledJob  Completed     False           localhost
```

<span data-ttu-id="cd34c-118">コマンドレットでは、 `Get-Job` **プロセスジョブ** オブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-118">The `Get-Job` cmdlet sends **ProcessJob** objects down the pipeline.</span></span> <span data-ttu-id="cd34c-119">コマンドレットでは、 `Format-Table` スケジュールされたジョブインスタンスの **Name** 、 **ID** 、および **psbegintime** プロパティをテーブルに表示します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-119">The `Format-Table` cmdlet displays the **Name** , **ID** , and **PSBeginTime** properties of a scheduled job instance in a table.</span></span>

```powershell
Get-Job ProcessJob | Format-Table -Property Name, ID, PSBeginTime -Auto
```

```Output
Name       Id PSBeginTime
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

<span data-ttu-id="cd34c-120">スケジュールされたジョブのインスタンスの結果を取得するには、コマンドレットを使用し `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-120">To get the results of an instance of a scheduled job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="cd34c-121">次のコマンドは、ProcessJob (ID = 50) の最新のインスタンスの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-121">The following command gets the results of the newest instance of the ProcessJob (ID = 50).</span></span>

```powershell
Receive-Job -ID 50
```

### <a name="basic-method-for-finding-job-results-on-disk"></a><span data-ttu-id="cd34c-122">ディスク上のジョブ結果を検索するための基本的な方法</span><span class="sxs-lookup"><span data-stu-id="cd34c-122">Basic method for finding job results on disk</span></span>

<span data-ttu-id="cd34c-123">スケジュールされたジョブを管理するには、やなどのジョブコマンドレットを使用し `Get-Job` `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-123">To manage scheduled jobs, use the job cmdlets, such as `Get-Job` and `Receive-Job`.</span></span>

<span data-ttu-id="cd34c-124">`Get-Job`がジョブインスタンスを取得しない場合、またはジョブの結果を取得しない場合は、 `Receive-Job` 実行履歴ファイルでディスク上のジョブを検索できます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-124">If `Get-Job` does not get the job instance or `Receive-Job` does not get the job results, you can search the execution history files for the job on disk.</span></span>
<span data-ttu-id="cd34c-125">実行履歴には、トリガーされたすべてのジョブインスタンスのレコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-125">The execution history contains a record of all triggered job instances.</span></span>

<span data-ttu-id="cd34c-126">スケジュールされたジョブのディレクトリに、次のパスにタイムスタンプ付きのディレクトリがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-126">Verify that there is a timestamp-named directory in the directory for a scheduled job in the following path:</span></span>

`$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJob\<ScheduledJobName>\Output`

<span data-ttu-id="cd34c-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-127">For example:</span></span>

`C:\Users<UserName>\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJob\<ScheduledJobName>\Output`

<span data-ttu-id="cd34c-128">たとえば、 `Get-ChildItem` コマンドレットは、スケジュールされたジョブ **processjob** のディスク上の実行履歴を取得します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-128">For example, the `Get-ChildItem` cmdlet gets the on-disk execution history of the **ProcessJob** scheduled job.</span></span>

```powershell
$Path = '$home\AppData\Local\Microsoft\Windows\PowerShell'
$Path += '\ScheduledJobs\ProcessJob\Output'
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output

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

<span data-ttu-id="cd34c-129">各タイムスタンプの名前付きディレクトリは、ジョブインスタンスを表します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-129">Each timestamp-named directory represents a job instance.</span></span> <span data-ttu-id="cd34c-130">各ジョブインスタンスの結果は、タイムスタンプが指定されたディレクトリの **Results.xml** ファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-130">The results of each job instance are saved in a **Results.xml** file in the timestamp-named directory.</span></span>

<span data-ttu-id="cd34c-131">たとえば、次のコマンドは、スケジュールされた **Processjob** ジョブのすべての保存済みインスタンスの **Results.xml** ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-131">For example, the following command gets the **Results.xml** files for every saved instance of the **ProcessJob** scheduled job.</span></span> <span data-ttu-id="cd34c-132">**Results.xml** ファイルがない場合、PowerShell はジョブの結果を返すことも表示することもできません。</span><span class="sxs-lookup"><span data-stu-id="cd34c-132">If the **Results.xml** file is missing, PowerShell cannot return or display the job results.</span></span>

```powershell
$Path = '$home\AppData\Local\Microsoft\Windows\PowerShell'
$Path += '\ScheduledJobs\ProcessJob\Output\*\Results.xml'
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\Appdata\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output
```

<span data-ttu-id="cd34c-133">ジョブコマンドレットは、 **Psscheduledjob** モジュールがセッションにインポートされていないため、スケジュールされたジョブインスタンスやその結果を取得できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd34c-133">The job cmdlet might not be able to get scheduled job instances or their results because the **PSScheduledJob** module is not imported into the session.</span></span>

> [!NOTE]
> <span data-ttu-id="cd34c-134">スケジュールされたジョブインスタンスでジョブコマンドレットを使用する前に、 **Psscheduledjob** モジュールがセッションに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-134">Before using a job cmdlet on scheduled job instances, verify that the **PSScheduledJob** module is included in the session.</span></span> <span data-ttu-id="cd34c-135">**Psscheduledjob** モジュールがないと、ジョブコマンドレットはスケジュールされたジョブインスタンスやその結果を取得できません。</span><span class="sxs-lookup"><span data-stu-id="cd34c-135">Without the **PSScheduledJob** module, the job cmdlets cannot get scheduled job instances or their results.</span></span>

<span data-ttu-id="cd34c-136">**Psscheduledjob** モジュールをインポートするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="cd34c-136">To import the **PSScheduledJob** module:</span></span>

```powershell
Import-Module PSScheduledJob
```

### <a name="receive-job-cmdlet-might-already-have-returned-the-results"></a><span data-ttu-id="cd34c-137">Receive-Job コマンドレットは既に結果を返している可能性があります</span><span class="sxs-lookup"><span data-stu-id="cd34c-137">Receive-Job cmdlet might already have returned the results</span></span>

<span data-ttu-id="cd34c-138">`Receive-Job`がジョブインスタンスの結果を返さない場合は、現在の `Receive-Job` セッションで、 **Keep** パラメーターを指定せずにそのジョブインスタンスに対してコマンドが実行されたことが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd34c-138">If `Receive-Job` does not return job instance results, it might be because a `Receive-Job` command has been run for that job instance in the current session without the **Keep** parameter.</span></span>

<span data-ttu-id="cd34c-139">`Receive-Job` **Keep** パラメーターを指定せずにを使用すると、ジョブの `Receive-Job` 結果が返され、ジョブインスタンスの **Hasのデータ** プロパティが **False** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-139">When you use `Receive-Job` without the **Keep** parameter, `Receive-Job` returns the job results and sets the job instance's **HasMoreData** property to **False**.</span></span> <span data-ttu-id="cd34c-140">**False** 値は、がジョブの結果を返し、インスタンスに返される結果がなくなったことを意味し `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-140">The **False** value means that `Receive-Job` returned the job's results and the instance has no more results to return.</span></span> <span data-ttu-id="cd34c-141">この設定は、標準のバックグラウンドジョブに適していますが、ディスクに保存されているスケジュールされたジョブのインスタンスには適していません。</span><span class="sxs-lookup"><span data-stu-id="cd34c-141">This setting is appropriate for standard background jobs, but not for instances of scheduled jobs, which are saved to disk.</span></span>

<span data-ttu-id="cd34c-142">ジョブインスタンスの結果を再度取得するには、「」と入力して、新しい PowerShell セッションを開始し `PowerShell` ます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-142">To get the job instance results again, start a new PowerShell session by typing `PowerShell`.</span></span> <span data-ttu-id="cd34c-143">**Psscheduledjob** モジュールをインポートしてから、コマンドを再試行してください `Receive-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cd34c-143">Import the **PSScheduledJob** module, and try the `Receive-Job` command again.</span></span>

```powershell
Receive-Job -ID 50
```

```Output
#No results
```

```powershell
PowerShell.exe
```

```Output
Windows PowerShell
Copyright (C) 2012 Microsoft Corporation. All rights reserved.
```

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 50
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id  ProcessName
-------  ------    -----      ----- -----   ------     --  -----------
1213         33    12348      21676    88    25.71   1608  CcmExec
29            4     1168       2920    43     0.02    748  conhost
46            6     2208       4612    45     0.03   1640  conhost
```

### <a name="using-keep-parameter-to-get-results-more-than-one-time-in-a-session"></a><span data-ttu-id="cd34c-144">Keep パラメーターを使用してセッションで結果を複数回取得する</span><span class="sxs-lookup"><span data-stu-id="cd34c-144">Using Keep parameter to get results more than one time in a session</span></span>

<span data-ttu-id="cd34c-145">1つのセッションでジョブインスタンスの結果を複数回取得するには、コマンドレットの **Keep** パラメーターを使用し `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-145">To get the result of a job instance more than one time in a session, use the **Keep** parameter of the `Receive-Job` cmdlet.</span></span>

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 50 -Keep
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id  ProcessName
-------  ------    -----      ----- -----   ------     --  -----------
1213         33    12348      21676    88    25.71   1608  CcmExec
29            4     1168       2920    43     0.02    748  conhost
46            6     2208       4612    45     0.03   1640  conhost
```

```powershell
Receive-Job -ID 50 -Keep
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id  ProcessName
-------  ------    -----      ----- -----   ------     --  -----------
1213         33    12348      21676    88    25.71   1608  CcmExec
29            4     1168       2920    43     0.02    748  conhost
46            6     2208       4612    45     0.03   1640  conhost
```

### <a name="the-scheduled-job-might-be-corrupted"></a><span data-ttu-id="cd34c-146">スケジュールされたジョブが破損している可能性があります</span><span class="sxs-lookup"><span data-stu-id="cd34c-146">The scheduled job might be corrupted</span></span>

<span data-ttu-id="cd34c-147">スケジュールされたジョブが破損した場合、PowerShell は、破損したスケジュールされたジョブとその結果を削除します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-147">If a scheduled job becomes corrupted, PowerShell deletes the corrupted scheduled job and its results.</span></span> <span data-ttu-id="cd34c-148">破損したスケジュールされたジョブの結果を回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="cd34c-148">You cannot recover the results of a corrupted scheduled job.</span></span>

<span data-ttu-id="cd34c-149">スケジュールされたジョブがまだ存在するかどうかを判断するには、コマンドレットを使用し `Get-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-149">To determine if a scheduled job still exists, use the `Get-ScheduledJob` cmdlet.</span></span>

```powershell
Get-ScheduledJob
```

### <a name="the-number-of-results-might-have-exceeded-the-executionhistorylength"></a><span data-ttu-id="cd34c-150">結果の数が Executionhistory Length を超えている可能性があります</span><span class="sxs-lookup"><span data-stu-id="cd34c-150">The number of results might have exceeded the ExecutionHistoryLength</span></span>

<span data-ttu-id="cd34c-151">スケジュールされたジョブの **Executionhistory length** プロパティによって、ディスクに保存されるジョブインスタンスの数とその結果が決まります。</span><span class="sxs-lookup"><span data-stu-id="cd34c-151">The **ExecutionHistoryLength** property of a scheduled job determines how many job instances, and their results, are saved to disk.</span></span> <span data-ttu-id="cd34c-152">既定値は 32 です。</span><span class="sxs-lookup"><span data-stu-id="cd34c-152">The default value is 32.</span></span>
<span data-ttu-id="cd34c-153">スケジュールされたジョブのインスタンス数がこの値を超えると、PowerShell によって最も古いジョブインスタンスが削除され、新しいジョブインスタンスごとに領域が確保されます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-153">When the number of instances of a scheduled job exceeds this value, PowerShell deletes the oldest job instance to make room for each new job instance.</span></span>

<span data-ttu-id="cd34c-154">スケジュールされたジョブの **Executionhistory length** プロパティの値を取得するには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-154">To get the value of the **ExecutionHistoryLength** property of a scheduled job, use the following command format:</span></span>

```powershell
(Get-ScheduledJob <JobName>).ExecutionHistoryLength
```

<span data-ttu-id="cd34c-155">たとえば、次のコマンドは、スケジュールされた **processjob** ジョブの **executionhistory length** プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-155">For example, the following command gets the value of the **ExecutionHistoryLength** property of the **ProcessJob** scheduled job.</span></span>

```powershell
(Get-ScheduledJob ProcessJob).ExecutionHistoryLength
```

<span data-ttu-id="cd34c-156">**Executionhistory length** プロパティの値を設定または変更するには、コマンドレットとコマンドレットの **maxresultcount** パラメーターを使用し `Register-ScheduledJob` `Set-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-156">To set or change the value of the **ExecutionHistoryLength** property, use the **MaxResultCount** parameter of the `Register-ScheduledJob` and `Set-ScheduledJob` cmdlets.</span></span>

<span data-ttu-id="cd34c-157">次のコマンドは、 **Executionhistory length** プロパティの値を50に増やします。</span><span class="sxs-lookup"><span data-stu-id="cd34c-157">The following command increases the value of the **ExecutionHistoryLength** property to 50.</span></span>

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -MaxResultCount 50
```

### <a name="the-job-instance-results-might-have-been-deleted"></a><span data-ttu-id="cd34c-158">ジョブインスタンスの結果が削除された可能性があります</span><span class="sxs-lookup"><span data-stu-id="cd34c-158">The job instance results might have been deleted</span></span>

<span data-ttu-id="cd34c-159">コマンドレットの **ClearExecutionHistory** パラメーターは、 `Set-ScheduledJob` ジョブの実行履歴を削除します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-159">The **ClearExecutionHistory** parameter of the `Set-ScheduledJob` cmdlet deletes the execution history of a job.</span></span> <span data-ttu-id="cd34c-160">この機能を使用すると、ディスク領域を解放したり、不要な結果を削除したり、既に使用、分析、または別の場所に保存された結果を削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-160">You can use this feature to free up disk space or delete results that are not needed, or already used, analyzed or saved in a different location.</span></span>

<span data-ttu-id="cd34c-161">スケジュールされたジョブの実行履歴を削除するには、スケジュールされたジョブの **ClearExecutionHistory** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-161">To delete the execution history of a scheduled job, use the **ClearExecutionHistory** parameter of the scheduled job.</span></span>

<span data-ttu-id="cd34c-162">次のコマンドは、スケジュールされたジョブ **processjob** の実行履歴を削除します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-162">The following command deletes the execution history of the **ProcessJob** scheduled job.</span></span>

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -ClearExecutionHistory
```

<span data-ttu-id="cd34c-163">また、 `Remove-Job` コマンドレットはジョブの結果を削除します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-163">Also, the `Remove-Job` cmdlet deletes job results.</span></span> <span data-ttu-id="cd34c-164">を使用してスケジュールされたジョブを削除すると、 `Remove-Job` 実行履歴とすべてのジョブ結果を含む、ディスク上のジョブのすべてのインスタンスが削除されます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-164">When you use `Remove-Job` to delete a scheduled job, it deletes all instances of the job on disk, including the execution history and all job results.</span></span>

### <a name="jobs-started-by-using-the-start-job-cmdlet-are-not-saved-to-disk"></a><span data-ttu-id="cd34c-165">Start-Job コマンドレットを使用して開始されたジョブがディスクに保存されない</span><span class="sxs-lookup"><span data-stu-id="cd34c-165">Jobs started by using the Start-Job cmdlet are not saved to disk</span></span>

<span data-ttu-id="cd34c-166">を使用し `Start-Job` てスケジュールされたジョブを開始すると、ジョブトリガーを使用するのではなく、 `Start-Job` 標準のバックグラウンドジョブが開始されます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-166">When you use `Start-Job` to start a scheduled job, instead of using a job trigger, `Start-Job` starts a standard background job.</span></span> <span data-ttu-id="cd34c-167">バックグラウンドジョブとその結果は、ディスク上のジョブの実行履歴には格納されません。</span><span class="sxs-lookup"><span data-stu-id="cd34c-167">The background job and its results are not stored in the execution history of the job on disk.</span></span>

<span data-ttu-id="cd34c-168">コマンドレットを使用してジョブを取得し、コマンドレットを使用してジョブの結果を取得することはでき `Get-Job` `Receive-Job` ますが、コマンドレットの Keep パラメーターを使用しない限り、結果を受け取るまでは使用できません `Receive-Job` 。</span><span class="sxs-lookup"><span data-stu-id="cd34c-168">You can use the `Get-Job` cmdlet to get the job and the `Receive-Job` cmdlet to get the job results, but the results are available only until you receive them, unless you use the Keep parameter of the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="cd34c-169">また、バックグラウンドジョブとその結果はセッションに固有です。作成されたセッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-169">Also, background jobs and their results are session-specific; they exist only in the session in which they are created.</span></span> <span data-ttu-id="cd34c-170">でジョブを削除した場合 `Remove-Job` は、セッションを閉じるか PowerShell を閉じると、ジョブインスタンスとその結果が削除されます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-170">If you delete the job with `Remove-Job`, close the session or close PowerShell, the job instance and its results are deleted.</span></span>

## <a name="scheduled-job-doesnt-run"></a><span data-ttu-id="cd34c-171">スケジュールされたジョブは実行されません</span><span class="sxs-lookup"><span data-stu-id="cd34c-171">Scheduled job doesn't run</span></span>

<span data-ttu-id="cd34c-172">ジョブがトリガーされた場合、またはスケジュールされたジョブが無効になっている場合は、スケジュールされたジョブが自動的に実行</span><span class="sxs-lookup"><span data-stu-id="cd34c-172">Scheduled jobs don't run automatically if the job triggers or the scheduled job are disabled.</span></span>

<span data-ttu-id="cd34c-173">コマンドレットを使用し `Get-ScheduledJob` て、スケジュールされたジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-173">Use the `Get-ScheduledJob` cmdlet to get the scheduled job.</span></span> <span data-ttu-id="cd34c-174">スケジュールされたジョブの **Enabled** プロパティの値が **True** であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-174">Verify that the value of the **Enabled** property of the scheduled job is **True**.</span></span>

```powershell
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command         Enabled
--         ----            --------        -------         -------
4          ProcessJob      {1, 2}          Get-Process     True
```

```powershell
(Get-ScheduledJob ProcessJob).Enabled
```

```Output
True
```

<span data-ttu-id="cd34c-175">コマンドレットを使用して、スケジュールされた `Get-JobTrigger` ジョブのジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-175">Use the `Get-JobTrigger` cmdlet to get the job triggers of the scheduled job.</span></span>
<span data-ttu-id="cd34c-176">ジョブトリガーの **Enabled** プロパティの値が **True** であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-176">Verify that the value of the **Enabled** property of the job trigger is **True**.</span></span>

```powershell
Get-ScheduledJob ProcessJob | Get-JobTrigger
```

```Output
Id      Frequency    Time                   DaysOfWeek            Enabled
--      ---------    ----                   ----------            -------
1       Weekly       11/7/2011 5:00:00 AM   {Monday, Thursday}    True
2       Daily        11/7/2011 3:00:00 PM                         True
```

```powershell
Get-ScheduledJob ProcessJob|Get-JobTrigger|Format-Table ID, Enabled -Auto
```

```Output
Id Enabled
-- -------
1    True
2    True
```

### <a name="scheduled-jobs-dont-run-automatically-if-job-triggers-are-invalid"></a><span data-ttu-id="cd34c-177">ジョブトリガーが無効な場合、スケジュールされたジョブが自動的に実行されない</span><span class="sxs-lookup"><span data-stu-id="cd34c-177">Scheduled jobs don't run automatically if job triggers are invalid</span></span>

<span data-ttu-id="cd34c-178">たとえば、ジョブトリガーでは、過去の日付、または月の5番目の月曜日などの発生していない日付を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-178">For example, a job trigger might specify a date in the past or a date that does not occur, such as the 5th Monday of the month.</span></span>

<span data-ttu-id="cd34c-179">スケジュールされたジョブは、ジョブトリガーの条件またはジョブオプションが満たされていない場合、自動的には実行されません。</span><span class="sxs-lookup"><span data-stu-id="cd34c-179">Scheduled jobs do not run automatically if the conditions of the job trigger or the job options are not satisfied.</span></span>

<span data-ttu-id="cd34c-180">たとえば、特定のユーザーがコンピューターにログオンしたときにのみ実行されるスケジュールされたジョブは、そのユーザーがログオンしていない場合、またはリモートでのみ接続する場合には実行されません。</span><span class="sxs-lookup"><span data-stu-id="cd34c-180">For example, a scheduled job that runs only when a particular user logs on to the computer will not run if that user does not log on or only connects remotely.</span></span>

<span data-ttu-id="cd34c-181">スケジュールされたジョブのオプションを確認し、それらが満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-181">Examine the options of the scheduled job and make sure that they are satisfied.</span></span>
<span data-ttu-id="cd34c-182">たとえば、コンピューターがアイドル状態であるか、ネットワーク接続が必要であるか、または長い **IdleDuration** または Brief の **IdleTimeout** が実行されていない場合に、スケジュールされたジョブが実行されることはありません。</span><span class="sxs-lookup"><span data-stu-id="cd34c-182">For example, a scheduled job that requires that the computer be idle or requires a network connection, or has a long **IdleDuration** or a brief **IdleTimeout** might never run.</span></span>

<span data-ttu-id="cd34c-183">コマンドレットを使用して、 `Get-ScheduledJobOption` ジョブオプションとその値を確認します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-183">Use the `Get-ScheduledJobOption` cmdlet to examine the job options and their values.</span></span>

```powershell
Get-ScheduledJob -Name ProcessJob
```

```Output
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
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

<span data-ttu-id="cd34c-184">スケジュールされたジョブオプションの説明については、「 [get-scheduledjoboption](xref:PSScheduledJob.New-ScheduledJobOption)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd34c-184">For descriptions of the scheduled job options, see [New-ScheduledJobOption](xref:PSScheduledJob.New-ScheduledJobOption).</span></span>

### <a name="the-scheduled-job-instance-might-have-failed"></a><span data-ttu-id="cd34c-185">スケジュールされたジョブインスタンスが失敗した可能性があります</span><span class="sxs-lookup"><span data-stu-id="cd34c-185">The scheduled job instance might have failed</span></span>

<span data-ttu-id="cd34c-186">スケジュールされたジョブコマンドが失敗した場合、PowerShell はエラーメッセージを生成してすぐにレポートを報告します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-186">If a scheduled job command fails, PowerShell reports it immediately by generating an error message.</span></span> <span data-ttu-id="cd34c-187">ただし、タスクスケジューラによって実行が試行されたときにジョブが失敗した場合、PowerShell でエラーを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="cd34c-187">However, if the job fails when Task Scheduler tries to run it, the error is not available to PowerShell.</span></span>

<span data-ttu-id="cd34c-188">ジョブの失敗を検出して修正するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-188">Use the following methods to detect and correct job failures:</span></span>

<span data-ttu-id="cd34c-189">タスクスケジューライベントログでエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-189">Check the Task Scheduler event log for errors.</span></span> <span data-ttu-id="cd34c-190">ログを確認するには、イベントビューアーまたは次のような PowerShell コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-190">To check the log, use Event Viewer or a PowerShell command such as the following:</span></span>

```powershell
Get-WinEvent -LogName Microsoft-Windows-TaskScheduler/Operational |
 Where {$_.Message -like "fail"}
```

<span data-ttu-id="cd34c-191">タスクスケジューラのジョブレコードを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-191">Check the job record in Task Scheduler.</span></span> <span data-ttu-id="cd34c-192">PowerShell のスケジュールされたジョブは、次のタスクのスケジュールされたフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-192">PowerShell scheduled jobs are stored in the following Task Scheduled folder:</span></span>

`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs`

### <a name="the-scheduled-job-might-not-run-because-of-insufficient-permission"></a><span data-ttu-id="cd34c-193">十分な権限がないため、スケジュールされたジョブが実行されない可能性があります</span><span class="sxs-lookup"><span data-stu-id="cd34c-193">The scheduled job might not run because of insufficient permission</span></span>

<span data-ttu-id="cd34c-194">スケジュールされたジョブは、ジョブを作成したユーザーのアクセス許可か、またはコマンドで **Credential** パラメーターによって指定されたユーザーのアクセス許可を使用して実行され `Register-ScheduledJob` `Set-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-194">Scheduled jobs run with the permissions of the user who created the job or the permissions of the user who is specified by the **Credential** parameter in the `Register-ScheduledJob` or `Set-ScheduledJob` command.</span></span>

<span data-ttu-id="cd34c-195">コマンドまたはスクリプトを実行する権限がユーザーに与えられていない場合、ジョブは失敗します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-195">If that user does not have permission to run the commands or scripts, the job fails.</span></span>

## <a name="cant-get-scheduled-job-or-scheduled-job-is-corrupted"></a><span data-ttu-id="cd34c-196">スケジュールされたジョブを取得できないか、スケジュールされたジョブが破損しています</span><span class="sxs-lookup"><span data-stu-id="cd34c-196">Can't get scheduled job or scheduled job is corrupted</span></span>

<span data-ttu-id="cd34c-197">まれに、スケジュールされたジョブが破損したり、解決できない内部矛盾削除が含まれたりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="cd34c-197">On rare occasions, scheduled jobs can become corrupted or contain internal contradictions that cannot be resolved.</span></span> <span data-ttu-id="cd34c-198">通常、このエラーは、スケジュールされたジョブの XML ファイルが手動で編集され、XML が無効な場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-198">Typically, this happens when the XML files for the scheduled job are manually edited, resulting in invalid XML.</span></span>

<span data-ttu-id="cd34c-199">スケジュールされたジョブが破損した場合、PowerShell は、スケジュールされたジョブ、その実行履歴、およびディスクからの結果を削除しようとします。</span><span class="sxs-lookup"><span data-stu-id="cd34c-199">When a scheduled job is corrupted, PowerShell attempts to delete the scheduled job, its execution history, and its results from disk.</span></span>

<span data-ttu-id="cd34c-200">スケジュールされたジョブを削除できない場合は、コマンドレットを実行するたびに、破損したジョブのエラーメッセージが表示され `Get-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-200">If it cannot remove the scheduled job, you will get a corrupted job error message each time you run the `Get-ScheduledJob` cmdlet.</span></span>

<span data-ttu-id="cd34c-201">破損したスケジュールされたジョブを削除するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-201">To remove a corrupted scheduled job, use either one of the following methods:</span></span>

<span data-ttu-id="cd34c-202">スケジュールされた `<ScheduledJobName>` ジョブのディレクトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-202">Delete the `<ScheduledJobName>` directory for the scheduled job.</span></span> <span data-ttu-id="cd34c-203">**Scheduledjob** ディレクトリは削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="cd34c-203">Don't delete the **ScheduledJob** directory.</span></span>

<span data-ttu-id="cd34c-204">ディレクトリの場所:</span><span class="sxs-lookup"><span data-stu-id="cd34c-204">The directory's location:</span></span>

`$env:UserProfile\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>`

<span data-ttu-id="cd34c-205">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-205">For example:</span></span>

`C:\Users<UserName>\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>.`

<span data-ttu-id="cd34c-206">スケジュールされたジョブを削除するには、タスクスケジューラを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-206">Use Task Scheduler to delete the scheduled job.</span></span> <span data-ttu-id="cd34c-207">PowerShell のスケジュールされたタスクは、次のタスクスケジューラパスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-207">PowerShell scheduled tasks appear in the following Task Scheduler path:</span></span>

`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>`

## <a name="job-cmdlets-cant-consistently-find-scheduled-jobs"></a><span data-ttu-id="cd34c-208">ジョブコマンドレットがスケジュールされたジョブを一貫して検出できない</span><span class="sxs-lookup"><span data-stu-id="cd34c-208">Job cmdlets can't consistently find scheduled jobs</span></span>

<span data-ttu-id="cd34c-209">**Psscheduledjob** モジュールが現在のセッションにない場合、ジョブコマンドレットは、スケジュールされたジョブを取得したり、開始したり、結果を取得したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cd34c-209">When the **PSScheduledJob** module isn't in the current session, the job cmdlets cannot get scheduled jobs, start them, or get their results.</span></span>

<span data-ttu-id="cd34c-210">**Psscheduledjob** モジュールをインポートするには、コマンドレットなど、モジュールのコマンドレットを入力するか、 `Import-Module PSScheduledJob` または実行または取得し `Get-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-210">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or run or get any cmdlet in the module, such as the `Get-ScheduledJob` cmdlet.</span></span>
<span data-ttu-id="cd34c-211">PowerShell 3.0 以降では、モジュールのコマンドレットを取得または使用すると、モジュールは自動的にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-211">Beginning in PowerShell 3.0, modules are imported automatically when you get or use any cmdlet in the module.</span></span>

<span data-ttu-id="cd34c-212">**Psscheduledjob** モジュールが現在のセッションにない場合、次のコマンドシーケンスを実行できます。</span><span class="sxs-lookup"><span data-stu-id="cd34c-212">When the **PSScheduledJob** module isn't in the current session, the following command sequence is possible.</span></span>

```powershell
Get-Job ProcessJob
```

```Output
Get-Job : The command cannot find the job because the job name
ProcessJob was not found.
Verify the value of the Name parameter, and then try the command again.
+ CategoryInfo          : ObjectNotFound: (ProcessJob:String) [Get-Job],
PSArgumentException
+ FullyQualifiedErrorId : JobWithSpecifiedNameNotFound,Microsoft.PowerShell.
Commands.GetJobCommand
```

```powershell
Get-Job
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command      Enabled
--         ----            --------        -------      -------
4          ProcessJob      {1}             Get-Process  True
```

```powershell
Get-Job ProcessJob
```

```Output
Id     Name         PSJobTypeName   State       HasMoreData     Location
--     ----         -------------   -----       -----------     --------
43     ProcessJob   PSScheduledJob  Completed   True            localhost
44     ProcessJob   PSScheduledJob  Completed   True            localhost
45     ProcessJob   PSScheduledJob  Completed   True            localhost
46     ProcessJob   PSScheduledJob  Completed   True            localhost
47     ProcessJob   PSScheduledJob  Completed   True            localhost
48     ProcessJob   PSScheduledJob  Completed   True            localhost
49     ProcessJob   PSScheduledJob  Completed   True            localhost
50     ProcessJob   PSScheduledJob  Completed   True            localhost
```

<span data-ttu-id="cd34c-213">この動作は、コマンドによって `Get-ScheduledJob` **Psscheduledjob** モジュールが自動的にインポートされ、コマンドが実行されるために発生します。</span><span class="sxs-lookup"><span data-stu-id="cd34c-213">This behavior occurs because the `Get-ScheduledJob` command automatically imports the **PSScheduledJob** module, and then runs the command.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd34c-214">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd34c-214">See also</span></span>

[<span data-ttu-id="cd34c-215">about_Scheduled_Jobs_Basics</span><span class="sxs-lookup"><span data-stu-id="cd34c-215">about_Scheduled_Jobs_Basics</span></span>](about_Scheduled_Jobs_Basics.md)

[<span data-ttu-id="cd34c-216">about_Scheduled_Jobs_Advanced</span><span class="sxs-lookup"><span data-stu-id="cd34c-216">about_Scheduled_Jobs_Advanced</span></span>](about_Scheduled_Jobs_Advanced.md)

[<span data-ttu-id="cd34c-217">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="cd34c-217">about_Scheduled_Jobs</span></span>](about_Scheduled_Jobs.md)

<span data-ttu-id="cd34c-218">[Psscheduledjob](xref:PSScheduledJob) モジュールのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="cd34c-218">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="cd34c-219">タスク スケジューラ</span><span class="sxs-lookup"><span data-stu-id="cd34c-219">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
