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
# <span data-ttu-id="42099-103">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="42099-103">Set-ScheduledJobOption</span></span>

## <span data-ttu-id="42099-104">概要</span><span class="sxs-lookup"><span data-stu-id="42099-104">SYNOPSIS</span></span>
<span data-ttu-id="42099-105">スケジュールされたジョブのジョブ オプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="42099-105">Changes the job options of a scheduled job.</span></span>

## <span data-ttu-id="42099-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="42099-106">SYNTAX</span></span>

```
Set-ScheduledJobOption [-InputObject] <ScheduledJobOptions> [-PassThru] [-RunElevated] [-HideInTaskScheduler]
 [-RestartOnIdleResume] [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart]
 [-RequireNetwork] [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery]
 [-IdleTimeout <TimeSpan>] [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## <span data-ttu-id="42099-107">Description</span><span class="sxs-lookup"><span data-stu-id="42099-107">DESCRIPTION</span></span>
<span data-ttu-id="42099-108">**Set-ScheduledJobOptions** コマンドレットは、スケジュールされたジョブのジョブ オプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="42099-108">The **Set-ScheduledJobOptions** cmdlet changes the job options of scheduled jobs.</span></span>

<span data-ttu-id="42099-109">スケジュールされたジョブのオプションを変更するには、まず Get-ScheduledJobOption コマンドレットを使用して、スケジュールされたジョブのジョブオプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="42099-109">To change the options of a scheduled job, begin by using the Get-ScheduledJobOption cmdlet to get the job options of a scheduled job.</span></span>
<span data-ttu-id="42099-110">次に、パイプを使用してオプションを **Set-ScheduledJobOption** に渡すか、オプションを変数に保存し、 *Set-ScheduledJobOption* コマンドレットの **InputObject** パラメーターを使用して、オプションを特定します。</span><span class="sxs-lookup"><span data-stu-id="42099-110">Then, pipe the options to **Set-ScheduledJobOption** or save the options in a variable and use the *InputObject* parameter of **Set-ScheduledJobOption** cmdlet to identify the options.</span></span>
<span data-ttu-id="42099-111">**Set-ScheduledJobOption** の他のパラメーターを使用して、ジョブ オプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="42099-111">Use the remaining parameters of **Set-ScheduledJobOption** to change the job options.</span></span>

<span data-ttu-id="42099-112">ジョブ オプションを有効にするには、そのオプションを設定するパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="42099-112">To turn on a job option, use the parameter that sets that option.</span></span>
<span data-ttu-id="42099-113">オプションをオフにするには、パラメーター名、コロン (:)、および $False を入力します。</span><span class="sxs-lookup"><span data-stu-id="42099-113">To turn off an option, type the parameter name, a colon (:), and $False.</span></span>
<span data-ttu-id="42099-114">たとえば、 *Runelevated* オプションをオフにするには、「」と入力 `-RunElevated:$False` します。</span><span class="sxs-lookup"><span data-stu-id="42099-114">For example, to turn off the *RunElevated* option, type `-RunElevated:$False`.</span></span>

<span data-ttu-id="42099-115">各ジョブ オプション オブジェクトには、スケジュールされたジョブを含む JobDefinition プロパティが含まれています。そのため、ジョブ オプションを変更しても、スケジュールされたジョブとの関連付けは維持されます。</span><span class="sxs-lookup"><span data-stu-id="42099-115">Each job options object includes a JobDefinition property that contains the scheduled job, so the association with the scheduled job is retained when the job options are changed.</span></span>

<span data-ttu-id="42099-116">スケジュールされたジョブのオプションにより、タスク スケジューラによって開始されたジョブの実行方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="42099-116">The scheduled job options determine how the job runs when it is started by Task Scheduler.</span></span>
<span data-ttu-id="42099-117">これらのオプションは、Start-Job コマンドレットを使用してスケジュールされたジョブを開始する場合には適用されません。</span><span class="sxs-lookup"><span data-stu-id="42099-117">These options to not apply when you use the Start-Job cmdlet to start a scheduled job.</span></span>

<span data-ttu-id="42099-118">**Get-scheduledjoboption** は、Windows PowerShell に含まれている psscheduledjob モジュールのジョブスケジュールコマンドレットのコレクションの1つです。</span><span class="sxs-lookup"><span data-stu-id="42099-118">**Set-ScheduledJobOption** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="42099-119">スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42099-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="42099-120">PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42099-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="42099-121">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="42099-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="42099-122">例</span><span class="sxs-lookup"><span data-stu-id="42099-122">EXAMPLES</span></span>

### <span data-ttu-id="42099-123">例 1: ジョブオプションを変更する</span><span class="sxs-lookup"><span data-stu-id="42099-123">Example 1: Change job options</span></span>

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

<span data-ttu-id="42099-124">この例では、ローカル コンピューター上のスケジュールされたジョブのオプションを変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="42099-124">This example shows how to change the options of a scheduled job on the local computer.</span></span>

<span data-ttu-id="42099-125">最初のコマンドは、Get-ScheduledJobOption コマンドレットを使用して、スケジュールされたジョブ DeployPackage のジョブオプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="42099-125">The first command uses the Get-ScheduledJobOption cmdlet to get the job options of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="42099-126">出力には、WakeToRun プロパティと RunElevated プロパティが $False に設定されていることが示されています。</span><span class="sxs-lookup"><span data-stu-id="42099-126">The output shows that the WakeToRun and RunElevated properties are set to $False.</span></span>

<span data-ttu-id="42099-127">このコマンドは必須ではありません。オプションの変更の結果を表示するためにのみ含まれています。</span><span class="sxs-lookup"><span data-stu-id="42099-127">This command is not required; it is included only to show the effect of the option change.</span></span>

### <span data-ttu-id="42099-128">例 2: すべてのリモートスケジュールされたジョブのオプションを変更する</span><span class="sxs-lookup"><span data-stu-id="42099-128">Example 2: Change an option on all remote scheduled jobs</span></span>

```
PS C:\> Invoke-Command -Computer "Server01" -ScriptBlock {Get-ScheduledJob | Get-ScheduledJobOption | Set-ScheduledJobOption -IdleTimeout 2:00:00}
```

<span data-ttu-id="42099-129">このコマンドは、Server01 コンピューター上のスケジュールされたすべてのジョブの *IdleTimeout* の値を1時間 (既定値) から2時間に変更します。</span><span class="sxs-lookup"><span data-stu-id="42099-129">This command changes the value of the *IdleTimeout* from one hour (the default value) to two hours on all scheduled jobs on the Server01 computer.</span></span>

<span data-ttu-id="42099-130">このコマンドは、Invoke-Command コマンドレットを使用して、Server01 コンピューター上でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="42099-130">The command uses the Invoke-Command cmdlet to run a command on the Server01 computer.</span></span>

<span data-ttu-id="42099-131">リモートコマンドは、コンピューター上のスケジュールされたすべてのジョブを取得する Get-ScheduledJob コマンドで開始します。</span><span class="sxs-lookup"><span data-stu-id="42099-131">The remote command begins with a Get-ScheduledJob command that gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="42099-132">スケジュールされたジョブは Get-ScheduledJobOption コマンドレットにパイプ処理され、スケジュールされたジョブのジョブオプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="42099-132">The scheduled jobs are piped to the Get-ScheduledJobOption cmdlet, which gets the job options of the scheduled jobs.</span></span>
<span data-ttu-id="42099-133">各ジョブ オプション オブジェクトには、スケジュールされたジョブを含む JobDefinition プロパティが含まれています。そのため、オプション オブジェクトを変更しても、スケジュールされたジョブとの関連付けは維持されます。</span><span class="sxs-lookup"><span data-stu-id="42099-133">Each job options object contains a JobDefinition property that contains the scheduled job, so the options object remains associated with the scheduled job even when it is changed.</span></span>

<span data-ttu-id="42099-134">ジョブトリガーはパイプを使用して **get-scheduledjoboption** コマンドレットに渡されます。このコマンドレットは、 *IdleTimeout* オプションの値を2時間 (2:00:00) に変更します。</span><span class="sxs-lookup"><span data-stu-id="42099-134">The job triggers are piped to the **Set-ScheduledJobOption** cmdlet, which changes the value of the *IdleTimeout* option to two hours (2:00:00).</span></span>

## <span data-ttu-id="42099-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="42099-135">PARAMETERS</span></span>

### <span data-ttu-id="42099-136">-続行 Eifgoingonバッテリ</span><span class="sxs-lookup"><span data-stu-id="42099-136">-ContinueIfGoingOnBattery</span></span>
<span data-ttu-id="42099-137">ジョブの実行中に、コンピューターがバッテリ電源に切り替わっても (AC 電源から切断されても)、スケジュールされたジョブを停止しません。</span><span class="sxs-lookup"><span data-stu-id="42099-137">Do not stop the scheduled job if the computer switches to battery power (disconnects from AC power) while the job is running.</span></span>
<span data-ttu-id="42099-138">既定では、コンピューターが AC 電源から切断されると、スケジュールされたジョブは停止します。</span><span class="sxs-lookup"><span data-stu-id="42099-138">By default, scheduled jobs stop when the computer disconnects from AC power.</span></span>

<span data-ttu-id="42099-139">*続行 Eifgoingonバッテリ* パラメーターは、スケジュールされたジョブの StopIfGoingOnBatteries プロパティの値を $True に設定します。</span><span class="sxs-lookup"><span data-stu-id="42099-139">The *ContinueIfGoingOnBattery* parameter sets the value of the StopIfGoingOnBatteries property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="42099-140">-DoNotAllowDemandStart</span><span class="sxs-lookup"><span data-stu-id="42099-140">-DoNotAllowDemandStart</span></span>
<span data-ttu-id="42099-141">トリガーされた場合にのみ、ジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="42099-141">Start the job only when it is triggered.</span></span>
<span data-ttu-id="42099-142">ユーザーは、タスク スケジューラの実行機能などを使用して、手動でジョブを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="42099-142">Users cannot start the job manually, such as by using the Run feature in Task Scheduler.</span></span>

<span data-ttu-id="42099-143">このパラメーターは、タスク スケジューラにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="42099-143">This parameter only affects Task Scheduler.</span></span>
<span data-ttu-id="42099-144">ユーザーが Start-Job コマンドレットを使用してジョブを開始するのを防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="42099-144">It does not prevents users from using the Start-Job cmdlet to start the job.</span></span>

<span data-ttu-id="42099-145">*DoNotAllowDemandStart* パラメーターは、スケジュールされたジョブの DoNotAllowDemandStart プロパティの値を $True に設定します。</span><span class="sxs-lookup"><span data-stu-id="42099-145">The *DoNotAllowDemandStart* parameter sets the value of the DoNotAllowDemandStart property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="42099-146">-HideInTaskScheduler</span><span class="sxs-lookup"><span data-stu-id="42099-146">-HideInTaskScheduler</span></span>
<span data-ttu-id="42099-147">タスク スケジューラにジョブを表示しません。</span><span class="sxs-lookup"><span data-stu-id="42099-147">Do not display the job in Task Scheduler.</span></span>
<span data-ttu-id="42099-148">この値は、ジョブが実行されるコンピューターにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="42099-148">This value affects only the computer on which the job runs.</span></span>
<span data-ttu-id="42099-149">既定では、スケジュールされたタスクはタスク スケジューラに表示されます。</span><span class="sxs-lookup"><span data-stu-id="42099-149">By default, scheduled tasks appear in Task Scheduler.</span></span>

<span data-ttu-id="42099-150">タスクが非表示の場合でも、ユーザーはタスクスケジューラの [ **非表示のタスクビューを** 表示] オプションを選択することでタスクを表示できます。</span><span class="sxs-lookup"><span data-stu-id="42099-150">Even if a task is hidden, users can display the task by selecting the **Show hidden tasks** view option in Task Scheduler.</span></span>

<span data-ttu-id="42099-151">*HideInTaskScheduler* パラメーターは、スケジュールされたジョブの ShowInTaskScheduler プロパティの値を $False に設定します。</span><span class="sxs-lookup"><span data-stu-id="42099-151">The *HideInTaskScheduler* parameter sets the value of the ShowInTaskScheduler property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="42099-152">-IdleDuration</span><span class="sxs-lookup"><span data-stu-id="42099-152">-IdleDuration</span></span>
<span data-ttu-id="42099-153">コンピューターのアイドル状態がどれだけ続いたらジョブを開始するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="42099-153">Specifies how long the computer must be idle before the job starts.</span></span>
<span data-ttu-id="42099-154">既定値は 10 分です。</span><span class="sxs-lookup"><span data-stu-id="42099-154">The default value is 10 minutes.</span></span>
<span data-ttu-id="42099-155">*IdleTimeout* の値を過ぎる前に、コンピューターが指定された時間アイドル状態にならないと、(次のスケジュールされた時刻が設定されていれば、それまで) スケジュールされたジョブは実行されません。</span><span class="sxs-lookup"><span data-stu-id="42099-155">If the computer is not idle for the specified duration before the value of *IdleTimeout* expires, the scheduled job does not run until the next scheduled time, if any.</span></span>

<span data-ttu-id="42099-156">Timespan オブジェクトを入力します。たとえば、New-TimeSpan コマンドレットによって生成されたものや、 \<hours\> \<minutes\> \<seconds\> **timespan** オブジェクトに自動的に変換される:: format の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="42099-156">Enter a timespan object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="42099-157">この値を有効にするには、 *StartIfIdle* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="42099-157">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="42099-158">既定では、スケジュールされたジョブの StartIfNotIdle プロパティは $True に設定され、Windows PowerShell は *IdleDuration* と *IdleTimeout* の値を無視します。</span><span class="sxs-lookup"><span data-stu-id="42099-158">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

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

### <span data-ttu-id="42099-159">-IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="42099-159">-IdleTimeout</span></span>
<span data-ttu-id="42099-160">コンピューターのアイドル状態がどれだけ続いたらジョブを開始するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="42099-160">Specifies how long the computer must be idle before the job starts.</span></span>
<span data-ttu-id="42099-161">既定値は 10 分です。</span><span class="sxs-lookup"><span data-stu-id="42099-161">The default value is 10 minutes.</span></span>
<span data-ttu-id="42099-162">**IdleTimeout** の値を過ぎる前に、コンピューターが指定された時間アイドル状態にならないと、(次のスケジュールされた時刻が設定されていれば、それまで) スケジュールされたジョブは実行されません。</span><span class="sxs-lookup"><span data-stu-id="42099-162">If the computer is not idle for the specified duration before the value of **IdleTimeout** expires, the scheduled job does not run until the next scheduled time, if any.</span></span>

<span data-ttu-id="42099-163">Timespan オブジェクトを入力します。たとえば、New-TimeSpan コマンドレットによって生成されたものや、 \<hours\> \<minutes\> \<seconds\> **timespan** オブジェクトに自動的に変換される:: format の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="42099-163">Enter a timespan object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="42099-164">この値を有効にするには、 *StartIfIdle* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="42099-164">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="42099-165">既定では、スケジュールされたジョブの StartIfNotIdle プロパティは $True に設定され、Windows PowerShell は *IdleDuration* と *IdleTimeout* の値を無視します。</span><span class="sxs-lookup"><span data-stu-id="42099-165">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

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

### <span data-ttu-id="42099-166">-InputObject</span><span class="sxs-lookup"><span data-stu-id="42099-166">-InputObject</span></span>
<span data-ttu-id="42099-167">ジョブ オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="42099-167">Specifies the job options.</span></span>
<span data-ttu-id="42099-168">**ScheduledJobOptions** オブジェクトを含む変数を入力するか、Get-ScheduledJobOption コマンドなどの **ScheduledJobOptions** オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="42099-168">Enter a variable that contains **ScheduledJobOptions** objects or type a command or expression that gets **ScheduledJobOptions** objects, such as a Get-ScheduledJobOption command.</span></span>
<span data-ttu-id="42099-169">パイプを使用して **ScheduledJobOptions** オブジェクトを **get-scheduledjoboption** にパイプ処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="42099-169">You can also pipe a **ScheduledJobOptions** object to **Set-ScheduledJobOption** .</span></span>

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

### <span data-ttu-id="42099-170">-多重 Instancepolicy</span><span class="sxs-lookup"><span data-stu-id="42099-170">-MultipleInstancePolicy</span></span>
<span data-ttu-id="42099-171">スケジュールされたジョブのインスタンスの実行中にそのジョブの別のインスタンスを開始する要求に対するシステムの応答方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="42099-171">Determines how the system responds to a request to start an instance of a scheduled job while another instance of the job is running.</span></span>
<span data-ttu-id="42099-172">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="42099-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="42099-173">IgnoreNew.</span><span class="sxs-lookup"><span data-stu-id="42099-173">IgnoreNew.</span></span>
<span data-ttu-id="42099-174">新しいジョブ インスタンスを無視します。</span><span class="sxs-lookup"><span data-stu-id="42099-174">The new job instance is ignored.</span></span>
<span data-ttu-id="42099-175">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="42099-175">This is the default value.</span></span>
- <span data-ttu-id="42099-176">パラレル。</span><span class="sxs-lookup"><span data-stu-id="42099-176">Parallel.</span></span>
<span data-ttu-id="42099-177">新しいジョブ インスタンスをすぐに開始します。</span><span class="sxs-lookup"><span data-stu-id="42099-177">The new job instance starts immediately.</span></span>
- <span data-ttu-id="42099-178">キュー:</span><span class="sxs-lookup"><span data-stu-id="42099-178">Queue.</span></span>
<span data-ttu-id="42099-179">現在のジョブ インスタンスが完了したら、すぐに新しいインスタンスを開始します。</span><span class="sxs-lookup"><span data-stu-id="42099-179">The new job instance starts as soon as the current instance completes.</span></span>
- <span data-ttu-id="42099-180">StopExisting。</span><span class="sxs-lookup"><span data-stu-id="42099-180">StopExisting.</span></span>
<span data-ttu-id="42099-181">ジョブの現在のインスタンスを停止し、新しいインスタンスを開始します。</span><span class="sxs-lookup"><span data-stu-id="42099-181">The current instance of the job stop and the new instance starts.</span></span>

<span data-ttu-id="42099-182">ジョブを実行するには、ジョブ スケジュールのすべての条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="42099-182">To run the job, all conditions for the job schedule must be met.</span></span>
<span data-ttu-id="42099-183">たとえば、 *RequireNetwork* 、 *IdleDuration* 、および *IdleTimeout* パラメーターによって設定された条件が満たされない場合、このパラメーターの値に関係なく、ジョブインスタンスは開始されません。</span><span class="sxs-lookup"><span data-stu-id="42099-183">For example, if the conditions that are set by the *RequireNetwork* , *IdleDuration* , and *IdleTimeout* parameters are not satisfied, the job instance is not started, regardless of the value of this parameter.</span></span>

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

### <span data-ttu-id="42099-184">-PassThru</span><span class="sxs-lookup"><span data-stu-id="42099-184">-PassThru</span></span>
<span data-ttu-id="42099-185">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="42099-185">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="42099-186">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="42099-186">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="42099-187">-RequireNetwork</span><span class="sxs-lookup"><span data-stu-id="42099-187">-RequireNetwork</span></span>
<span data-ttu-id="42099-188">ネットワーク接続が利用可能な場合にのみ、スケジュールされたジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="42099-188">Runs the scheduled job only when network connections are available.</span></span>

<span data-ttu-id="42099-189">このパラメーターを指定し、スケジュールされた開始時刻にネットワークが利用できない場合は、(次のスケジュールされた開始時刻が設定されていれば、それまで) ジョブは実行されません。</span><span class="sxs-lookup"><span data-stu-id="42099-189">If you specify this parameter and the network is not available at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="42099-190">*RequireNetwork* パラメーターは、スケジュールされたジョブの Run network プロパティの値を $False に設定します。</span><span class="sxs-lookup"><span data-stu-id="42099-190">The *RequireNetwork* parameter sets the value of the RunWithoutNetwork property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="42099-191">-RestartOnIdleResume</span><span class="sxs-lookup"><span data-stu-id="42099-191">-RestartOnIdleResume</span></span>
<span data-ttu-id="42099-192">コンピューターがアイドル状態になると、スケジュールされたジョブを再開します。</span><span class="sxs-lookup"><span data-stu-id="42099-192">Restarts a scheduled job when the computer becomes idle.</span></span>
<span data-ttu-id="42099-193">このパラメーターは、コンピューターがアクティブになる (アイドル状態でなくなる) と実行中のスケジュールされたジョブを中断する *StopIfGoingOffIdle* パラメーターと連動しています。</span><span class="sxs-lookup"><span data-stu-id="42099-193">This parameter works with the *StopIfGoingOffIdle* parameter, which suspends a running scheduled job if the computer becomes active (leaves the idle state).</span></span>

<span data-ttu-id="42099-194">*RestartOnIdleResume* パラメーターは、スケジュールされたジョブの RestartOnIdleResume プロパティの値を $True に設定します。</span><span class="sxs-lookup"><span data-stu-id="42099-194">The *RestartOnIdleResume* parameter sets the value of the RestartOnIdleResume property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="42099-195">-RunElevated</span><span class="sxs-lookup"><span data-stu-id="42099-195">-RunElevated</span></span>
<span data-ttu-id="42099-196">ジョブが実行されるコンピューター上の Administrators グループのメンバーのアクセス許可で、スケジュールされたジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="42099-196">Runs the scheduled job with the permissions of a member of the Administrators group on the computer on which the job runs.</span></span>

<span data-ttu-id="42099-197">スケジュールされたジョブを管理者権限で実行できるようにするには、Register-ScheduledJob の *credential* パラメーターを使用して、ジョブに明示的な資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="42099-197">To enable a scheduled job to run with Administrator permissions, use the *Credential* parameter of Register-ScheduledJob to provide explicit credential for the job.</span></span>

<span data-ttu-id="42099-198">**Runelevated** されたパラメーターは、スケジュールされたジョブの **runelevated** されたプロパティの値を True に設定します。</span><span class="sxs-lookup"><span data-stu-id="42099-198">The **RunElevated** parameter sets the value of the **RunElevated** property of scheduled jobs to True.</span></span>

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

### <span data-ttu-id="42099-199">-StartIfIdle</span><span class="sxs-lookup"><span data-stu-id="42099-199">-StartIfIdle</span></span>
<span data-ttu-id="42099-200">**IdleTimeout** パラメーターに指定された時間を過ぎる前に、コンピューターが *IdleDuration* パラメーターに指定された時間アイドル状態になった場合に、スケジュールされたジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="42099-200">Starts the scheduled job if the computer has been idle for the time specified by the **IdleDuration** parameter before the time specified by the *IdleTimeout* parameter expires.</span></span>

<span data-ttu-id="42099-201">既定では、 *IdleDuration* パラメーターと *IdleTimeout* パラメーターは無視され、コンピューターがビジー状態でも、ジョブはスケジュールされた開始時刻に開始されます。</span><span class="sxs-lookup"><span data-stu-id="42099-201">By default, the *IdleDuration* and *IdleTimeout* parameters are ignored and the job starts at the scheduled start time even if the computer is busy.</span></span>

<span data-ttu-id="42099-202">このパラメーターを指定し、スケジュールされた開始時刻にコンピューターがビジー状態の場合 (アイドル状態でない場合) は、(次のスケジュールされた開始時刻が設定されていれば、それまで) ジョブは実行されません。</span><span class="sxs-lookup"><span data-stu-id="42099-202">If you specify this parameter and the computer is busy (not idle) at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="42099-203">*StartIfIdle* パラメーターは、スケジュールされたジョブの **StartIfNotIdle** プロパティの値を False に設定します。</span><span class="sxs-lookup"><span data-stu-id="42099-203">The *StartIfIdle* parameter sets the value of the **StartIfNotIdle** property of scheduled jobs to False.</span></span>

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

### <span data-ttu-id="42099-204">-Starti区別バッテリ</span><span class="sxs-lookup"><span data-stu-id="42099-204">-StartIfOnBattery</span></span>
<span data-ttu-id="42099-205">スケジュールされた開始時刻にコンピューターがバッテリで動作していても、スケジュールされたジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="42099-205">Starts the scheduled job even if the computer is running on batteries at the scheduled start time.</span></span>
<span data-ttu-id="42099-206">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="42099-206">The default value is False.</span></span>

<span data-ttu-id="42099-207">*Startiのバッテリ* パラメーターは、スケジュールされたジョブの **startiの電池** プロパティの値を $True に設定します。</span><span class="sxs-lookup"><span data-stu-id="42099-207">The *StartIfOnBattery* parameter sets the value of the **StartIfOnBatteries** property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="42099-208">-StopIfGoingOffIdle</span><span class="sxs-lookup"><span data-stu-id="42099-208">-StopIfGoingOffIdle</span></span>
<span data-ttu-id="42099-209">ジョブの実行中に、コンピューターがアクティブになる (アイドル状態でなくなる) と、実行中のスケジュールされたジョブを中断します。</span><span class="sxs-lookup"><span data-stu-id="42099-209">Suspends a running scheduled job if the computer becomes active (not idle) while the job is running.</span></span>

<span data-ttu-id="42099-210">既定では、コンピューターがアクティブになったときに中断されたスケジュールされたジョブは、コンピューターが再びアイドル状態になると再開されます。</span><span class="sxs-lookup"><span data-stu-id="42099-210">By default, a scheduled job that is suspended when the computer becomes active resumes when the computer becomes idle again.</span></span>
<span data-ttu-id="42099-211">この既定の動作を変更するには、 *RestartOnIdleResume* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="42099-211">To change this default behavior, use the *RestartOnIdleResume* parameter.</span></span>

<span data-ttu-id="42099-212">*StopIfGoingOffIdle* パラメーターは、スケジュールされたジョブの StopIfGoingOffIdle プロパティの値を $True に設定します。</span><span class="sxs-lookup"><span data-stu-id="42099-212">The *StopIfGoingOffIdle* parameter sets the value of the StopIfGoingOffIdle property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="42099-213">-WakeToRun</span><span class="sxs-lookup"><span data-stu-id="42099-213">-WakeToRun</span></span>
<span data-ttu-id="42099-214">スケジュールされた開始時刻にコンピューターの休止状態またはスリープ状態を解除して、ジョブを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="42099-214">Wakes the computer from a Hibernate or Sleep state at the scheduled start time so it can run the job.</span></span>
<span data-ttu-id="42099-215">既定では、スケジュールされた開始時刻にコンピューターが休止状態またはスリープ状態の場合、ジョブは実行されません。</span><span class="sxs-lookup"><span data-stu-id="42099-215">By default, if the computer is in a Hibernate or Sleep state at the scheduled start time, the job does not run.</span></span>

<span data-ttu-id="42099-216">*WakeToRun* パラメーターは、スケジュールされたジョブの WakeToRun プロパティの値を $True に設定します。</span><span class="sxs-lookup"><span data-stu-id="42099-216">The *WakeToRun* parameter sets the value of the WakeToRun property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="42099-217">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="42099-217">CommonParameters</span></span>
<span data-ttu-id="42099-218">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="42099-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="42099-219">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42099-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="42099-220">入力</span><span class="sxs-lookup"><span data-stu-id="42099-220">INPUTS</span></span>

### <span data-ttu-id="42099-221">ScheduledJobOptions (Microsoft PowerShell)</span><span class="sxs-lookup"><span data-stu-id="42099-221">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>
<span data-ttu-id="42099-222">パイプを使用して、スケジュールされたジョブのオプション オブジェクトを **Set-ScheduledJobOption** に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="42099-222">You can pipe a scheduled job options object to **Set-ScheduledJobOption** .</span></span>

## <span data-ttu-id="42099-223">出力</span><span class="sxs-lookup"><span data-stu-id="42099-223">OUTPUTS</span></span>

### <span data-ttu-id="42099-224">[なし] または [ScheduledJobOptions]</span><span class="sxs-lookup"><span data-stu-id="42099-224">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>
<span data-ttu-id="42099-225">*Passthru* パラメーターを使用すると、 **Set-ScheduledJobOption** は変更されたジョブ オプションを返します。</span><span class="sxs-lookup"><span data-stu-id="42099-225">When you use the *Passthru* parameter, **Set-ScheduledJobOption** returns the job options that were changed.</span></span>
<span data-ttu-id="42099-226">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="42099-226">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="42099-227">注</span><span class="sxs-lookup"><span data-stu-id="42099-227">NOTES</span></span>

## <span data-ttu-id="42099-228">関連リンク</span><span class="sxs-lookup"><span data-stu-id="42099-228">RELATED LINKS</span></span>

[<span data-ttu-id="42099-229">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="42099-229">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="42099-230">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="42099-230">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="42099-231">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="42099-231">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="42099-232">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="42099-232">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="42099-233">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="42099-233">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="42099-234">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="42099-234">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="42099-235">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="42099-235">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="42099-236">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="42099-236">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="42099-237">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="42099-237">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="42099-238">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="42099-238">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="42099-239">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="42099-239">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="42099-240">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="42099-240">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="42099-241">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="42099-241">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="42099-242">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="42099-242">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="42099-243">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="42099-243">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="42099-244">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="42099-244">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
