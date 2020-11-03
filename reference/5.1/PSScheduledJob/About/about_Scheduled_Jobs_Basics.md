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
# <a name="about-scheduled-jobs-basics"></a><span data-ttu-id="0c770-104">スケジュールされたジョブについての基本事項</span><span class="sxs-lookup"><span data-stu-id="0c770-104">About Scheduled Jobs Basics</span></span>

## <a name="short-description"></a><span data-ttu-id="0c770-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="0c770-105">Short description</span></span>

<span data-ttu-id="0c770-106">ジョブをスケジュールし、管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c770-106">Explains how to create and manage scheduled jobs.</span></span>

## <a name="long-description"></a><span data-ttu-id="0c770-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="0c770-107">Long description</span></span>

<span data-ttu-id="0c770-108">このドキュメントでは、スケジュールされたジョブを作成および管理するための基本的なタスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c770-108">This document shows how to perform basic tasks of creating and managing scheduled jobs.</span></span> <span data-ttu-id="0c770-109">詳細なタスクについては、「 [about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c770-109">For information about more advanced tasks, see [about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md).</span></span>

<span data-ttu-id="0c770-110">**Psscheduledjob** モジュールに含まれるコマンドレットの詳細については、「 [psscheduledjob](xref:PSScheduledJob)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c770-110">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

## <a name="how-to-create-a-scheduled-job"></a><span data-ttu-id="0c770-111">スケジュールされたジョブを作成する方法</span><span class="sxs-lookup"><span data-stu-id="0c770-111">How to create a scheduled job</span></span>

<span data-ttu-id="0c770-112">スケジュールされたジョブを作成するには、コマンドレットを使用し `Register-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="0c770-112">To create a scheduled job, use the `Register-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="0c770-113">コマンドレットには、名前と、ジョブを実行するコマンドまたはスクリプトが必要です。</span><span class="sxs-lookup"><span data-stu-id="0c770-113">The cmdlet requires a name and the commands or script that the job runs.</span></span> <span data-ttu-id="0c770-114">**Runnow** パラメーターを追加するか、ジョブトリガーを作成し、ジョブを作成するときにジョブオプションを設定するか、既存のジョブを編集することによって、ジョブをすぐに実行することができます。</span><span class="sxs-lookup"><span data-stu-id="0c770-114">You can either run the job immediately by adding the **RunNow** parameter, or create a job trigger and set job options when you create the job, or edit an existing job.</span></span>

<span data-ttu-id="0c770-115">スクリプトを実行するジョブを作成するには、 **FilePath** パラメーターを使用して、スクリプトファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="0c770-115">To create a job that runs a script, use the **FilePath** parameter to specify the path to the script file.</span></span> <span data-ttu-id="0c770-116">コマンドを実行するジョブを作成するには、 **ScriptBlock** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="0c770-116">To create a job that runs commands, use the **ScriptBlock** parameter.</span></span>

<span data-ttu-id="0c770-117">コマンドレットでは、 `Register-ScheduledJob` コマンドを実行する **processjob** を作成し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="0c770-117">The `Register-ScheduledJob` cmdlet creates the **ProcessJob** , which runs a `Get-Process` command.</span></span> <span data-ttu-id="0c770-118">このスケジュールされたジョブには、既定のジョブオプションがあり、ジョブトリガーはありません。</span><span class="sxs-lookup"><span data-stu-id="0c770-118">This scheduled job has the default job options and no job trigger.</span></span>

```powershell
Register-ScheduledJob -Name ProcessJob -ScriptBlock { Get-Process }
```

```Output
Id         Name            Triggers        Command       Enabled
--         ----            --------        -------       -------
8          ProcessJob      {}              Get-Process   True
```

## <a name="how-to-create-a-job-trigger"></a><span data-ttu-id="0c770-119">ジョブトリガーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="0c770-119">How to create a job trigger</span></span>

<span data-ttu-id="0c770-120">ジョブトリガーは、スケジュールされたジョブを自動的に開始します。</span><span class="sxs-lookup"><span data-stu-id="0c770-120">Job triggers start a scheduled job automatically.</span></span> <span data-ttu-id="0c770-121">ジョブトリガーには、1回だけ、定期的なスケジュール、またはユーザーがログオンしたときや Windows が起動したときなどのイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="0c770-121">A job trigger can be one-time or recurring schedule or an event, such as when a user logs on or Windows starts.</span></span> <span data-ttu-id="0c770-122">各ジョブには、0個、1個、または複数のジョブトリガーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0c770-122">Each job can have zero, one, or multiple job triggers.</span></span>

<span data-ttu-id="0c770-123">ジョブトリガーを作成するには、 `New-JobTrigger` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="0c770-123">To create a job trigger, use the `New-JobTrigger` cmdlet.</span></span> <span data-ttu-id="0c770-124">次のコマンドは、月曜日と木曜日の午前5:00 時にジョブを開始するジョブトリガーを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c770-124">The following command creates a job trigger that starts a job every Monday and Thursday at 5:00 AM.</span></span>
<span data-ttu-id="0c770-125">このコマンドは、ジョブトリガーを変数に保存し `$T` ます。</span><span class="sxs-lookup"><span data-stu-id="0c770-125">The command saves the job trigger in the `$T` variable.</span></span>

```powershell
$T = New-JobTrigger -Weekly -DaysOfWeek "Monday", "Thursday" -At "5:00 AM"
```

<span data-ttu-id="0c770-126">ジョブ トリガーは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="0c770-126">Job triggers are optional.</span></span> <span data-ttu-id="0c770-127">コマンドに **Runnow** パラメーターを追加する `Register-ScheduledJob` か、コマンドレットを使用して、スケジュールされたジョブをいつでも開始でき `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="0c770-127">You can start a scheduled job at any time by adding the **RunNow** parameter to your `Register-ScheduledJob` command, or by using the `Start-Job` cmdlets.</span></span>

## <a name="how-to-add-a-job-trigger"></a><span data-ttu-id="0c770-128">ジョブトリガーを追加する方法</span><span class="sxs-lookup"><span data-stu-id="0c770-128">How to add a job trigger</span></span>

<span data-ttu-id="0c770-129">スケジュールされたジョブにジョブトリガーを追加すると、スケジュールされたジョブのスケジュールされたジョブの XML ファイルにジョブトリガーが追加され、スケジュールされたジョブの一部になります。</span><span class="sxs-lookup"><span data-stu-id="0c770-129">When you add a job trigger to a scheduled job, the job trigger is added to the scheduled job XML file for the scheduled job and becomes part of the scheduled job.</span></span>

<span data-ttu-id="0c770-130">スケジュールされたジョブを作成するとき、または既存のジョブを編集するときに、スケジュールされたジョブにジョブトリガーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="0c770-130">You can add a job trigger to a scheduled job when you create the scheduled job, or edit an existing job.</span></span> <span data-ttu-id="0c770-131">スケジュールされたジョブのジョブトリガーは、いつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="0c770-131">You can change the job trigger of a scheduled job at any time.</span></span>

<span data-ttu-id="0c770-132">PowerShell では、タスクスケジューラ使用するのと同じジョブトリガーの一部が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0c770-132">PowerShell uses some of the same job triggers that Task Scheduler uses.</span></span> <span data-ttu-id="0c770-133">ジョブトリガーの詳細については、「 [New-JobTrigger](xref:PSScheduledJob.New-JobTrigger) コマンドレットのヘルプトピック」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c770-133">For detailed information about job triggers, see the help topic for the [New-JobTrigger](xref:PSScheduledJob.New-JobTrigger) cmdlet.</span></span>

<span data-ttu-id="0c770-134">次の例では、スプラッティングを使用し `$JobParms` て、コマンドレットに渡されるパラメーター値を作成し `Register-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="0c770-134">The following example uses splatting to create `$JobParms` which are parameter values that are passed to the `Register-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="0c770-135">詳細については、 [about_Splatting](../../Microsoft.PowerShell.Core/About/about_Splatting.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c770-135">For more information, see [about_Splatting.md](../../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>
<span data-ttu-id="0c770-136">は、 `Register-ScheduledJob` を使用して `@JobParms` スケジュールされたジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c770-136">The `Register-ScheduledJob` uses `@JobParms` to create a scheduled job.</span></span> <span data-ttu-id="0c770-137">**トリガー** パラメーターを使用して、変数内のジョブトリガーを指定し `$T` ます。</span><span class="sxs-lookup"><span data-stu-id="0c770-137">It uses the **Trigger** parameter to specify the job trigger in the `$T` variable.</span></span>

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Command}
  Trigger = $T
}

Register-ScheduledJob @JobParms
```

<span data-ttu-id="0c770-138">また、既存のスケジュールされたジョブにジョブトリガーをいつでも追加できます。</span><span class="sxs-lookup"><span data-stu-id="0c770-138">You can also add a job trigger to an existing scheduled job at any time.</span></span> <span data-ttu-id="0c770-139">この `Add-JobTrigger` コマンドレットは、変数内のジョブトリガー `$T` を、スケジュールされたジョブ **processjob** に追加します。</span><span class="sxs-lookup"><span data-stu-id="0c770-139">The `Add-JobTrigger` cmdlet adds the job trigger in the `$T` variable to the **ProcessJob** scheduled job.</span></span>

```powershell
Add-JobTrigger -Name ProcessJob -Trigger $T
```

<span data-ttu-id="0c770-140">その結果、ジョブトリガーは月曜日と木曜日の午前5:00 に自動的に **Processjob** を開始します。</span><span class="sxs-lookup"><span data-stu-id="0c770-140">As a result, the job trigger starts the **ProcessJob** automatically every Monday and Thursday at 5:00 AM.</span></span>

## <a name="how-to-get-a-job-trigger"></a><span data-ttu-id="0c770-141">ジョブトリガーを取得する方法</span><span class="sxs-lookup"><span data-stu-id="0c770-141">How to get a job trigger</span></span>

<span data-ttu-id="0c770-142">スケジュールされたジョブのジョブトリガーを取得するには、コマンドレットを使用し `Get-JobTrigger` ます。</span><span class="sxs-lookup"><span data-stu-id="0c770-142">To get the job trigger of a scheduled job, use the `Get-JobTrigger` cmdlet.</span></span> <span data-ttu-id="0c770-143">**Name** 、 **ID** 、および **InputObject** パラメーターを使用して、ジョブトリガーではなく、スケジュールされたジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="0c770-143">Use the **Name** , **ID** , and **InputObject** parameters to specify the scheduled job, not the job trigger.</span></span>

<span data-ttu-id="0c770-144">`Get-JobTrigger`**Processjob** のジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="0c770-144">`Get-JobTrigger` gets the job trigger of the **ProcessJob**.</span></span>

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id   Frequency       Time                   DaysOfWeek              Enabled
--   ---------       ----                   ----------              -------
1    Weekly          11/7/2011 5:00:00 AM   {Monday, Thursday}      True
```

## <a name="how-to-create-job-options"></a><span data-ttu-id="0c770-145">ジョブオプションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="0c770-145">How to create job options</span></span>

<span data-ttu-id="0c770-146">ジョブオプションは、ジョブを開始および実行するための条件を設定します。</span><span class="sxs-lookup"><span data-stu-id="0c770-146">Job options establish conditions for starting and running the job.</span></span> <span data-ttu-id="0c770-147">すべてのジョブには、変更しない限り、既定のジョブオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0c770-147">Every job has the default job options unless you change them.</span></span> <span data-ttu-id="0c770-148">ジョブオプションを使用すると、スケジュールされた時刻にジョブが実行されるのを防ぐことができるため、ジョブのオプションを理解し、それらを慎重に使用することが重要です。</span><span class="sxs-lookup"><span data-stu-id="0c770-148">Because job options can prevent a job from running at the scheduled time, it is important to understand the job options and use them carefully.</span></span>

<span data-ttu-id="0c770-149">PowerShell では、タスクスケジューラ使用するのと同じジョブオプションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0c770-149">PowerShell uses the same job options that Task Scheduler uses.</span></span> <span data-ttu-id="0c770-150">ジョブオプションの詳細については、 [get-scheduledjoboption](xref:PSScheduledJob.New-ScheduledJobOption)のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c770-150">For detailed information about the job options, see the help topic for [New-ScheduledJobOption](xref:PSScheduledJob.New-ScheduledJobOption).</span></span>

<span data-ttu-id="0c770-151">ジョブオプションは、スケジュールされたジョブの XML ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="0c770-151">Job options are stored in the scheduled job XML file.</span></span> <span data-ttu-id="0c770-152">ジョブオプションは、スケジュールされたジョブを作成するときに設定することも、いつでも変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="0c770-152">You can set job options when you create a scheduled job or change them at any time.</span></span>

<span data-ttu-id="0c770-153">コマンドレットでは、スケジュールされたジョブ `New-ScheduledJobOption` オプション **WakeToRun** を作成し、スケジュールされたジョブオプションを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="0c770-153">The `New-ScheduledJobOption` cmdlet creates a scheduled job option in which the **WakeToRun** scheduled job option is set to True.</span></span> <span data-ttu-id="0c770-154">**WakeToRun** オプションは、スケジュールされた開始時刻にコンピューターがスリープ状態または休止状態の場合でも、スケジュールされたジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="0c770-154">The **WakeToRun** option runs the scheduled job even if the computer is in the Sleep or Hibernate state at the scheduled start time.</span></span> <span data-ttu-id="0c770-155">このコマンドは、ジョブオプションを変数に保存し `$O` ます。</span><span class="sxs-lookup"><span data-stu-id="0c770-155">The command saves the job options in the `$O` variable.</span></span>

```powershell
$O = New-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-job-options"></a><span data-ttu-id="0c770-156">ジョブオプションを取得する方法</span><span class="sxs-lookup"><span data-stu-id="0c770-156">How to get job options</span></span>

<span data-ttu-id="0c770-157">スケジュールされたジョブのジョブオプションを取得するには、コマンドレットを使用し `Get-ScheduledJobOption` ます。</span><span class="sxs-lookup"><span data-stu-id="0c770-157">To get the job options of a scheduled job, use the `Get-ScheduledJobOption` cmdlet.</span></span> <span data-ttu-id="0c770-158">ジョブオプションではなく、 **Name** 、 **ID** 、および **InputObject** パラメーターを使用して、スケジュールされたジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="0c770-158">Use the **Name** , **ID** , and **InputObject** parameters to specify the scheduled job, not the job options.</span></span>

<span data-ttu-id="0c770-159">`Get-ScheduledJobOption`**processjob** のジョブオプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="0c770-159">`Get-ScheduledJobOption` gets the job options of the **ProcessJob**.</span></span>

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

## <a name="how-to-change-job-options"></a><span data-ttu-id="0c770-160">ジョブオプションを変更する方法</span><span class="sxs-lookup"><span data-stu-id="0c770-160">How to change job options</span></span>

<span data-ttu-id="0c770-161">スケジュールされたジョブを作成したり、既存のジョブを編集したりするときに、スケジュールされたジョブのジョブオプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="0c770-161">You can change the job options of a scheduled job when you create a scheduled job or edit an existing job.</span></span>

<span data-ttu-id="0c770-162">Splatted は、 `$JobParms` `Add-JobTrigger` プロセスジョブを作成するためにコマンドレットに渡されます。</span><span class="sxs-lookup"><span data-stu-id="0c770-162">The splatted `$JobParms` are passed to the `Add-JobTrigger` cmdlet to create the process job.</span></span> <span data-ttu-id="0c770-163">この例では、 **get-scheduledjoboption** パラメーターを使用して、変数のジョブオプションを指定して `$O` います。</span><span class="sxs-lookup"><span data-stu-id="0c770-163">It uses the **ScheduledJobOption** parameter to specify the job options in the `$O` variable.</span></span>

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  ScheduledJobOption = $O
}

Add-JobTrigger @JobParms
```

<span data-ttu-id="0c770-164">ジョブのオプションは、いつでも既存のスケジュールされたジョブに変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="0c770-164">You can also change the job options to an existing scheduled job at any time.</span></span>
<span data-ttu-id="0c770-165">次のコマンドでは、コマンドレットを使用して、 `Set-ScheduledJobOption` **processjob** Scheduledjob の **WakeToRun** オプションの値を **True** に変更します。</span><span class="sxs-lookup"><span data-stu-id="0c770-165">The following command uses the `Set-ScheduledJobOption` cmdlet to change the value of the **WakeToRun** option of the **ProcessJob** scheduledJob to **True**.</span></span>

<span data-ttu-id="0c770-166">`Set`コマンドレットなど、 **Psscheduledjob** モジュールのコマンドレットに `Set-ScheduledJobOption` は、 **名前** または **ID** パラメーターがありません。</span><span class="sxs-lookup"><span data-stu-id="0c770-166">The `Set` cmdlets in the **PSScheduledJob** module, such as the `Set-ScheduledJobOption` cmdlet, don't have **Name** or **ID** parameters.</span></span> <span data-ttu-id="0c770-167">**InputObject** パラメーターを使用して、スケジュールされたジョブオプションを指定したり、スケジュールされたジョブをコマンドレットからにパイプ処理したりできます `Get-ScheduledJobOption` `Set-ScheduledJobOption` 。</span><span class="sxs-lookup"><span data-stu-id="0c770-167">You can use the **InputObject** parameter to specify the scheduled job options or pipe a scheduled job from `Get-ScheduledJobOption` cmdlet to `Set-ScheduledJobOption`.</span></span>

<span data-ttu-id="0c770-168">この例では、 `Get-ScheduledJob` コマンドレットを使用して、ProcessJob を取得します。</span><span class="sxs-lookup"><span data-stu-id="0c770-168">This example uses the `Get-ScheduledJob` cmdlet to get the ProcessJob.</span></span> <span data-ttu-id="0c770-169">コマンドレットを使用して `Get-ScheduledJobOption` **processjob** のジョブオプションを取得し、コマンドレットを使用して `Set-ScheduledJobOption` processjob の **WakeToRun** job オプションを True に変更します。</span><span class="sxs-lookup"><span data-stu-id="0c770-169">It uses the `Get-ScheduledJobOption` cmdlet to get the job options in the **ProcessJob** and the `Set-ScheduledJobOption` cmdlet to change the **WakeToRun** job option in the ProcessJob to True.</span></span>

```powershell
Get-ScheduledJob -Name ProcessJob | Get-ScheduledJobOption |
 Set-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-scheduled-job-instances"></a><span data-ttu-id="0c770-170">スケジュールされたジョブインスタンスを取得する方法</span><span class="sxs-lookup"><span data-stu-id="0c770-170">How to get scheduled job instances</span></span>

<span data-ttu-id="0c770-171">スケジュールされたジョブが開始されると、PowerShell は標準の PowerShell バックグラウンドジョブに似たジョブインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c770-171">When a scheduled job is started, PowerShell creates a job instance that is similar to a standard PowerShell background job.</span></span> <span data-ttu-id="0c770-172">ジョブのコマンドレット (やなど) を使用して、 `Get-Job` `Stop-Job` `Receive-Job` ジョブインスタンスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="0c770-172">You can use the job cmdlets, such as `Get-Job`, `Stop-Job` and `Receive-Job` to manage the job instances.</span></span>

> [!NOTE]
> <span data-ttu-id="0c770-173">スケジュールされたジョブのインスタンスでジョブコマンドレットを使用するには、 **Psscheduledjob** モジュールをセッションにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c770-173">To use the job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="0c770-174">**Psscheduledjob** モジュールをインポートするには、などの `Import-Module PSScheduledJob` スケジュールされたジョブコマンドレットを入力するか、使用し `Get-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="0c770-174">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

<span data-ttu-id="0c770-175">PowerShell のスケジュールされたジョブのすべてのインスタンスとすべてのアクティブな標準ジョブを取得するには、コマンドレットを使用し `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="0c770-175">To get all instances of PowerShell scheduled jobs, and all active standard jobs, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="0c770-176">`Import-Module`コマンドレットは、 **Psscheduledjob** モジュールをインポートし、 `Get-Job` ローカルコンピューター上のジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="0c770-176">The `Import-Module` cmdlet imports the **PSScheduledJob** module and `Get-Job` gets the jobs on the local computer.</span></span>

```powershell
Import-Module PSScheduledJob
Get-Job
```

<span data-ttu-id="0c770-177">`Get-Job` ローカルコンピューター上の **Processjob** のインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="0c770-177">`Get-Job` gets instances of **ProcessJob** on the local computer.</span></span>

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

<span data-ttu-id="0c770-178">既定の表示では、開始時刻は表示されません。通常、スケジュールされた同じジョブのインスタンスが区別されます。</span><span class="sxs-lookup"><span data-stu-id="0c770-178">The default display does not show the start time, which typically distinguishes instances of the same scheduled job.</span></span>

<span data-ttu-id="0c770-179">コマンドレットにより、 `Get-Job` オブジェクトがパイプラインから送信されます。</span><span class="sxs-lookup"><span data-stu-id="0c770-179">The `Get-Job` cmdlet sends objects down the pipeline.</span></span> <span data-ttu-id="0c770-180">コマンドレットにより、 `Format-Table` スケジュールされたジョブの **Name** 、 **ID** 、および **begintime** の各プロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c770-180">The `Format-Table` cmdlet displays the **Name** , **ID** , and **BeginTime** properties of the scheduled job.</span></span>

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

## <a name="get-scheduled-job-results"></a><span data-ttu-id="0c770-181">スケジュールされたジョブの結果を取得する</span><span class="sxs-lookup"><span data-stu-id="0c770-181">Get scheduled job results</span></span>

<span data-ttu-id="0c770-182">スケジュールされたジョブのインスタンスの結果を取得するには、コマンドレットを使用し `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="0c770-182">To get the results of an instance of a scheduled job, use the `Receive-Job` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="0c770-183">スケジュールされたジョブのインスタンスでジョブコマンドレットを使用するには、 **Psscheduledjob** モジュールをセッションにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c770-183">To use the Job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="0c770-184">**Psscheduledjob** モジュールをインポートするには、などの `Import-Module PSScheduledJob` スケジュールされたジョブコマンドレットを入力するか、使用し `Get-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="0c770-184">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

<span data-ttu-id="0c770-185">この例では、 **processjob** スケジュールされたジョブ (ID = 51) の最新のインスタンスの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="0c770-185">This examples gets the results of the newest instance of the **ProcessJob** scheduled job (ID = 51).</span></span>

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 51 -Keep
```

<span data-ttu-id="0c770-186">スケジュールされたジョブの結果はディスクに保存されるため、の **Keep** パラメーター `Receive-Job` は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0c770-186">The results of scheduled jobs are saved on disk, so the **Keep** parameter of `Receive-Job` is not required.</span></span> <span data-ttu-id="0c770-187">ただし、 **Keep** パラメーターを指定しないと、スケジュールされたジョブの結果を各 PowerShell セッションで1回だけ取得できます。</span><span class="sxs-lookup"><span data-stu-id="0c770-187">However, without the **Keep** parameter, you can get the results of a scheduled job only once in each PowerShell session.</span></span> <span data-ttu-id="0c770-188">新しい powershell セッションを開始するに `PowerShell` は、新しい powershell ウィンドウを入力するか、開いてください。</span><span class="sxs-lookup"><span data-stu-id="0c770-188">To start a new PowerShell session, type `PowerShell` or open a new PowerShell window.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c770-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c770-189">See also</span></span>

[<span data-ttu-id="0c770-190">about_Scheduled_Jobs_Advanced</span><span class="sxs-lookup"><span data-stu-id="0c770-190">about_Scheduled_Jobs_Advanced</span></span>](about_Scheduled_Jobs_Advanced.md)

[<span data-ttu-id="0c770-191">about_Scheduled_Jobs_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="0c770-191">about_Scheduled_Jobs_Troubleshooting</span></span>](about_Scheduled_Jobs_Troubleshooting.md)

[<span data-ttu-id="0c770-192">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="0c770-192">about_Scheduled_Jobs</span></span>](about_Scheduled_Jobs.md)

[<span data-ttu-id="0c770-193">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="0c770-193">about_Splatting.md</span></span>](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

<span data-ttu-id="0c770-194">[Psscheduledjob](xref:PSScheduledJob) モジュールのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="0c770-194">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="0c770-195">タスク スケジューラ</span><span class="sxs-lookup"><span data-stu-id="0c770-195">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
