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
# <a name="about-scheduled-jobs"></a><span data-ttu-id="fd850-104">スケジュールされたジョブについて</span><span class="sxs-lookup"><span data-stu-id="fd850-104">About Scheduled Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="fd850-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="fd850-105">Short description</span></span>

<span data-ttu-id="fd850-106">スケジュールされたジョブについて説明し、PowerShell およびタスクスケジューラでスケジュールされたジョブを使用および管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fd850-106">Describes scheduled jobs and explains how to use and manage scheduled jobs in PowerShell and in Task Scheduler.</span></span>

## <a name="long-description"></a><span data-ttu-id="fd850-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="fd850-107">Long description</span></span>

<span data-ttu-id="fd850-108">PowerShell のスケジュールされたジョブは、PowerShell バックグラウンドジョブとタスクスケジューラタスクの便利なハイブリッドです。</span><span class="sxs-lookup"><span data-stu-id="fd850-108">PowerShell scheduled jobs are a useful hybrid of PowerShell background jobs and Task Scheduler tasks.</span></span>

<span data-ttu-id="fd850-109">PowerShell のバックグラウンドジョブと同様、スケジュールされたジョブはバックグラウンドで非同期に実行されます。</span><span class="sxs-lookup"><span data-stu-id="fd850-109">Like PowerShell background jobs, scheduled jobs run asynchronously in the background.</span></span> <span data-ttu-id="fd850-110">実行されたスケジュールされたジョブのインスタンスは、、、、などのジョブコマンドレットを使用して管理でき `Start-Job` `Get-Job` `Stop-Job` `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="fd850-110">Instances of scheduled jobs that have run can be managed by using the job cmdlets, such as `Start-Job`, `Get-Job`, `Stop-Job`, and `Receive-Job`.</span></span>

<span data-ttu-id="fd850-111">タスクスケジューラのタスクと同様に、スケジュールされたジョブはディスクに保存されます。</span><span class="sxs-lookup"><span data-stu-id="fd850-111">Like Task Scheduler tasks, scheduled jobs are saved to disk.</span></span> <span data-ttu-id="fd850-112">タスクスケジューラでジョブを表示して管理したり、必要に応じて有効または無効にしたり、実行したり、テンプレートとして使用したり、ジョブを開始するための1回限りまたは定期的なスケジュールを設定したり、ジョブを開始する条件を設定したりできます。</span><span class="sxs-lookup"><span data-stu-id="fd850-112">You can view and manage the jobs in Task Scheduler, enable and disable them as needed, run them or use them as templates, establish a one-time or recurring schedules for starting the jobs, or set conditions under which the jobs start.</span></span>

<span data-ttu-id="fd850-113">さらに、スケジュールされたジョブインスタンスの結果は、簡単にアクセスできる形式でディスクに保存され、ジョブ出力の実行ログが提供されます。</span><span class="sxs-lookup"><span data-stu-id="fd850-113">In addition, the results of scheduled job instances are saved to disk in an easily accessible format, providing a running log of job output.</span></span> <span data-ttu-id="fd850-114">スケジュールされたジョブには、それらを管理するためのカスタマイズされたコマンドレットセットが付属しています。</span><span class="sxs-lookup"><span data-stu-id="fd850-114">Scheduled jobs come with a customized set of cmdlets for managing them.</span></span> <span data-ttu-id="fd850-115">コマンドレットを使用すると、スケジュールされたジョブ、ジョブトリガー、およびジョブオプションの作成、編集、管理、無効化、および再有効化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fd850-115">The cmdlets let you create, edit, manage, disable, and re-enable scheduled jobs, job triggers and job options.</span></span>

<span data-ttu-id="fd850-116">この包括的で柔軟なツールセットによって、スケジュールされたジョブが多くの professional PowerShell IT ソリューションの重要なコンポーネントとなります。</span><span class="sxs-lookup"><span data-stu-id="fd850-116">This comprehensive and flexible set of tools make scheduled jobs an essential component of many professional PowerShell IT solutions.</span></span>

<span data-ttu-id="fd850-117">スケジュールされたジョブコマンドレットは、PowerShell と共にインストールされる **Psscheduledjob** モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="fd850-117">The scheduled job cmdlets are included in the **PSScheduledJob** module that is installed with PowerShell.</span></span> <span data-ttu-id="fd850-118">このモジュールは powershell 3.0 で導入され、powershell 3.0 以降のバージョンの PowerShell で動作します。</span><span class="sxs-lookup"><span data-stu-id="fd850-118">This module was introduced in PowerShell 3.0 and works in PowerShell 3.0 and later versions of PowerShell.</span></span> <span data-ttu-id="fd850-119">**Psscheduledjob** モジュールに含まれるコマンドレットの詳細については、「 [psscheduledjob](xref:PSScheduledJob)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd850-119">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

<span data-ttu-id="fd850-120">PowerShell バックグラウンドジョブの詳細については、「 [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd850-120">For more information about PowerShell background jobs, see [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

<span data-ttu-id="fd850-121">タスクスケジューラの詳細については、「 [タスクスケジューラ](/windows/desktop/TaskSchd/task-scheduler-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd850-121">For more information about Task Scheduler, see [Task Scheduler](/windows/desktop/TaskSchd/task-scheduler-reference).</span></span>

> [!NOTE]
> <span data-ttu-id="fd850-122">タスクスケジューラで、PowerShell のスケジュールされたジョブを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="fd850-122">You can view and manage PowerShell scheduled jobs in Task Scheduler.</span></span> <span data-ttu-id="fd850-123">PowerShell ジョブおよびスケジュールされたジョブコマンドレットは、PowerShell で作成されたスケジュールされたジョブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="fd850-123">The PowerShell jobs and scheduled job cmdlets work only on scheduled jobs that are created in PowerShell.</span></span>

## <a name="quick-start"></a><span data-ttu-id="fd850-124">クイック スタート</span><span class="sxs-lookup"><span data-stu-id="fd850-124">Quick start</span></span>

<span data-ttu-id="fd850-125">この例では、毎日 3:00 AM に開始し、コマンドレットを実行するスケジュールされたジョブを作成し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="fd850-125">This example creates a scheduled job that starts every day at 3:00 AM and runs the `Get-Process` cmdlet.</span></span> <span data-ttu-id="fd850-126">コンピューターがバッテリで動作している場合でもジョブは開始されます。</span><span class="sxs-lookup"><span data-stu-id="fd850-126">The job starts even if the computer is running on batteries.</span></span>

```powershell
$trigger = New-JobTrigger -Daily -At 3AM
$options = New-ScheduledJobOption -StartIfOnBattery
Register-ScheduledJob -Name ProcessJob -ScriptBlock {Get-Process} `
-Trigger $trigger -ScheduledJobOption $options
```

<span data-ttu-id="fd850-127">`Get-ScheduledJob`コマンドレットは、ローカルコンピューター上のスケジュールされたジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="fd850-127">The `Get-ScheduledJob` cmdlet gets the scheduled jobs on the local computer.</span></span>

```powershell
Get-ScheduledJob
```

```Output
Id         Name            Triggers        Command            Enabled
--         ----            --------        -------            -------
7          ProcessJob      {1}             Get-Process        True
```

<span data-ttu-id="fd850-128">`Get-JobTrigger`**processjob** のジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="fd850-128">`Get-JobTrigger` gets the job triggers of **ProcessJob**.</span></span> <span data-ttu-id="fd850-129">トリガーはスケジュールされたジョブに保存されるので、入力パラメーターでは、トリガーではなくスケジュールされたジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="fd850-129">The input parameters specify the scheduled job, not the trigger, because triggers are saved in a scheduled job.</span></span>

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id         Frequency       Time                   DaysOfWeek        Enabled
--         ---------       ----                   ----------        -------
1          Daily           11/5/2011 3:00:00 AM                     True
```

<span data-ttu-id="fd850-130">この例では、コマンドレットの **続行 Eifgoingonバッテリ** パラメーターを使用して、 `Set-ScheduledJob` **Processjob** の **stopifgoingonbatteries** プロパティを **False** に変更します。</span><span class="sxs-lookup"><span data-stu-id="fd850-130">This example uses the **ContinueIfGoingOnBattery** parameter of the `Set-ScheduledJob` cmdlet to change the **StopIfGoingOnBatteries** property of **ProcessJob** to **False**.</span></span>

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

<span data-ttu-id="fd850-131">コマンドレットでは、スケジュールされた `Get-ScheduledJob` **processjob** ジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="fd850-131">The `Get-ScheduledJob` cmdlet gets the **ProcessJob** scheduled job.</span></span>

```powershell
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command        Enabled
--         ----            --------        -------        -------
7          ProcessJob      {1}             Get-Process    True
```

<span data-ttu-id="fd850-132">`Get-Job`このコマンドレットは、これまでに実行された **processjob** スケジュールされたジョブのすべてのインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="fd850-132">The `Get-Job` cmdlet gets all instances of the **ProcessJob** scheduled job that have run thus far.</span></span> <span data-ttu-id="fd850-133">`Get-Job`コマンドレットは、 **Psscheduledjob** モジュールが現在のセッションにインポートされた場合にのみ、スケジュールされたジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="fd850-133">The `Get-Job` cmdlet gets scheduled jobs only when the **PSScheduledJob** module is imported into the current session.</span></span>

> [!TIP]
> <span data-ttu-id="fd850-134">スケジュールされたジョブコマンドレットを使用して、スケジュールされたジョブを管理しますが、スケジュールされたジョブのインスタンスを管理するには、job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd850-134">Notice that you use the scheduled job cmdlets to manage scheduled jobs, but you use the job cmdlets to manage instances of scheduled jobs.</span></span>

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

<span data-ttu-id="fd850-135">コマンドレットでは、 `Receive-Job` **processjob** スケジュールされたジョブ (ID = 51) の最新のインスタンスの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="fd850-135">The `Receive-Job` cmdlet gets the results of the most recent instance of the **ProcessJob** scheduled job (ID = 51).</span></span>

```powershell
Receive-Job -ID 51
```

<span data-ttu-id="fd850-136">`Receive-Job`コマンドに **Keep** パラメーターが含まれていなくても、ジョブが削除されるか、または結果の最大数を超えるまで、ジョブの結果がディスクに保存されます。</span><span class="sxs-lookup"><span data-stu-id="fd850-136">Even though the `Receive-Job` command did not include the **Keep** parameter, the results of the job are saved on disk until you delete them or the maximum number of results are exceeded.</span></span>

<span data-ttu-id="fd850-137">ジョブの結果はこのセッションでは利用できなくなりましたが、新しいセッションを開始するか、新しい PowerShell ウィンドウを開くと、ジョブの結果が再び使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="fd850-137">The job results are no longer available in this session, but if you start a new session or open a new PowerShell window, the results of the job are available again.</span></span>

<span data-ttu-id="fd850-138">次のコマンドでは、コマンドレットの **Definitionname** パラメーターを使用して、 `Start-Job` スケジュールされたジョブ **processjob** を開始します。</span><span class="sxs-lookup"><span data-stu-id="fd850-138">The following command uses the **DefinitionName** parameter of the `Start-Job` cmdlet to start the **ProcessJob** scheduled job.</span></span>

<span data-ttu-id="fd850-139">コマンドレットを使用して開始されたジョブ `Start-Job` は、スケジュールされたジョブのインスタンスではなく、標準の PowerShell バックグラウンドジョブです。</span><span class="sxs-lookup"><span data-stu-id="fd850-139">Jobs that are started by using the `Start-Job` cmdlet are standard PowerShell background jobs, not instances of the scheduled job.</span></span> <span data-ttu-id="fd850-140">すべてのバックグラウンドジョブと同様に、これらのジョブはすぐに開始され、ジョブのオプションやジョブトリガーの影響を受けません。また、それらの出力は、スケジュールされたジョブディレクトリの出力ディレクトリに保存されません。</span><span class="sxs-lookup"><span data-stu-id="fd850-140">Like all background jobs, these jobs start immediately, they aren't subject to job options or affected by job triggers, and their output is not saved in the output directory of the scheduled job directory.</span></span>

```powershell
Start-Job -DefinitionName ProcessJob
```

<span data-ttu-id="fd850-141">`Unregister-ScheduledJob`コマンドレットは、スケジュールされたジョブ **processjob** とそのジョブインスタンスの保存されたすべての結果を削除します。</span><span class="sxs-lookup"><span data-stu-id="fd850-141">The `Unregister-ScheduledJob` cmdlet deletes the **ProcessJob** scheduled job and all saved results of its job instances.</span></span>

```powershell
Unregister-ScheduledJob ProcessJob
```

## <a name="scheduled-jobs-concepts"></a><span data-ttu-id="fd850-142">スケジュールされたジョブの概念</span><span class="sxs-lookup"><span data-stu-id="fd850-142">Scheduled jobs concepts</span></span>

<span data-ttu-id="fd850-143">スケジュールされたジョブは、コマンドまたはスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd850-143">A scheduled job runs commands or a script.</span></span> <span data-ttu-id="fd850-144">スケジュールされたジョブには、ジョブを開始するジョブトリガーや、ジョブを実行するための条件を設定するジョブオプションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="fd850-144">A scheduled job can include job triggers that start the job and job options that set conditions for running the job.</span></span>

<span data-ttu-id="fd850-145">ジョブトリガーは、スケジュールされたジョブを自動的に開始します。</span><span class="sxs-lookup"><span data-stu-id="fd850-145">A job trigger starts a scheduled job automatically.</span></span> <span data-ttu-id="fd850-146">ジョブトリガーには、1回限りのスケジュールまたは定期的なスケジュールを含めることも、ユーザーがログオンしたときや Windows が起動したときなどのイベントを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="fd850-146">A job trigger can include a one-time or recurring schedule or specify an event, such as when a user logs on or Windows starts.</span></span> <span data-ttu-id="fd850-147">スケジュールされたジョブには、1つまたは複数のジョブトリガーを含めることができます。また、ジョブトリガーを作成、追加、有効化、無効化、および取得することができます。</span><span class="sxs-lookup"><span data-stu-id="fd850-147">A scheduled job can have one or more job triggers, and you can create, add, enable, disable, and get job triggers.</span></span>

<span data-ttu-id="fd850-148">ジョブ トリガーは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="fd850-148">Job triggers are optional.</span></span> <span data-ttu-id="fd850-149">を使用する `Start-Job cmdlet` か、コマンドに **runnow** パラメーターを追加することで、スケジュールされたジョブをすぐに開始でき `Register-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="fd850-149">You can start scheduled jobs immediately by using the `Start-Job cmdlet`, or by adding the **RunNow** parameter to your `Register-ScheduledJob` command.</span></span>

<span data-ttu-id="fd850-150">ジョブオプションは、スケジュールされたジョブを実行するための条件を設定します。</span><span class="sxs-lookup"><span data-stu-id="fd850-150">Job options set the conditions for running a scheduled job.</span></span> <span data-ttu-id="fd850-151">スケジュールされたすべてのジョブには、1つのジョブオプションオブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="fd850-151">Every scheduled job has one job options object.</span></span> <span data-ttu-id="fd850-152">ジョブオプションオブジェクトを作成および編集して、1つまたは複数のスケジュールされたジョブに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="fd850-152">You can create and edit job options objects and add them to one or more scheduled jobs.</span></span>

<span data-ttu-id="fd850-153">スケジュールされたジョブが開始されるたびに、ジョブインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fd850-153">Each time a scheduled job starts, a job instance is created.</span></span> <span data-ttu-id="fd850-154">PowerShell ジョブのコマンドレットを使用して、ジョブインスタンスを表示および管理します。</span><span class="sxs-lookup"><span data-stu-id="fd850-154">Use the PowerShell job cmdlets to view and manage the job instance.</span></span>

<span data-ttu-id="fd850-155">スケジュールされたジョブはディスクに保存され、ではなく、コマンドレット動詞を使用し `Register` `New` ます。</span><span class="sxs-lookup"><span data-stu-id="fd850-155">Scheduled jobs are saved to disk and use the cmdlet verb, `Register`, instead of `New`.</span></span> <span data-ttu-id="fd850-156">XML ファイルは、ディレクトリ内のローカルコンピューターに配置され `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` ます。</span><span class="sxs-lookup"><span data-stu-id="fd850-156">The XML files are located on the local computer in the directory `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs`.</span></span>

<span data-ttu-id="fd850-157">PowerShell は、スケジュールされたジョブごとにディレクトリを作成し、ジョブコマンド、ジョブトリガー、ジョブオプション、ジョブの結果をスケジュールされたジョブディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="fd850-157">PowerShell creates a directory for each scheduled job and saves the job commands, job triggers, job options and job results in the scheduled job directory.</span></span> <span data-ttu-id="fd850-158">ジョブトリガーとジョブオプションは、個別にディスクに保存されません。</span><span class="sxs-lookup"><span data-stu-id="fd850-158">Job triggers and job options aren't saved to disk independently.</span></span>
<span data-ttu-id="fd850-159">これらのジョブは、関連付けられているスケジュールされたジョブごとに、スケジュールされたジョブの XML に保存されます。</span><span class="sxs-lookup"><span data-stu-id="fd850-159">They are saved in the scheduled job XML of each scheduled job with which they are associated.</span></span>

<span data-ttu-id="fd850-160">スケジュールされたジョブ、ジョブトリガー、およびジョブオプションは、オブジェクトとして PowerShell に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd850-160">Scheduled jobs, job triggers, and job options appear in PowerShell as objects.</span></span>
<span data-ttu-id="fd850-161">オブジェクトは interlinked であるため、コマンドやスクリプトで簡単に検出して使用できます。</span><span class="sxs-lookup"><span data-stu-id="fd850-161">The objects are interlinked, which makes them easy to discover and use in commands and scripts.</span></span>

<span data-ttu-id="fd850-162">スケジュールされたジョブは、 **ScheduledJobDefinition** オブジェクトとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd850-162">Scheduled jobs appear as **ScheduledJobDefinition** objects.</span></span> <span data-ttu-id="fd850-163">**ScheduledJobDefinition** オブジェクトには、スケジュールされたジョブのジョブトリガーと、ジョブオプションを含む **options** プロパティを含む **jobtriggers** プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="fd850-163">The **ScheduledJobDefinition** object has a **JobTriggers** property that contains the job triggers of the scheduled job and an **Options** property that contains the job options.</span></span> <span data-ttu-id="fd850-164">ジョブトリガーとジョブオプションを表す **Scheduledjobtriggers** および **ScheduledJobOptions** オブジェクトにはそれぞれ、関連付けられているスケジュールされたジョブを含む **JobDefinition** プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="fd850-164">The **ScheduledJobTriggers** and **ScheduledJobOptions** objects that represent job triggers and job options, respectively, each have a **JobDefinition** property that contains the scheduled job with which they are associated.</span></span> <span data-ttu-id="fd850-165">この再帰的な相互接続により、スケジュールされたジョブのトリガーとオプションを簡単に見つけて、ジョブトリガーまたはジョブオプションが関連付けられているスケジュールされたジョブを検索、スクリプト化、および表示することができます。</span><span class="sxs-lookup"><span data-stu-id="fd850-165">This recursive interconnection makes it easy to find the triggers and options of a scheduled job and to find, script, and display the scheduled job to which any job trigger or job option is associated.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd850-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd850-166">See also</span></span>

[<span data-ttu-id="fd850-167">about_Scheduled_Jobs_Basics</span><span class="sxs-lookup"><span data-stu-id="fd850-167">about_Scheduled_Jobs_Basics</span></span>](about_Scheduled_Jobs_Basics.md)

[<span data-ttu-id="fd850-168">about_Scheduled_Jobs_Advanced</span><span class="sxs-lookup"><span data-stu-id="fd850-168">about_Scheduled_Jobs_Advanced</span></span>](about_Scheduled_Jobs_Advanced.md)

[<span data-ttu-id="fd850-169">about_Scheduled_Jobs_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="fd850-169">about_Scheduled_Jobs_Troubleshooting</span></span>](about_Scheduled_Jobs_Troubleshooting.md)

<span data-ttu-id="fd850-170">[Psscheduledjob](xref:PSScheduledJob) モジュールのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="fd850-170">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="fd850-171">タスク スケジューラ</span><span class="sxs-lookup"><span data-stu-id="fd850-171">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
