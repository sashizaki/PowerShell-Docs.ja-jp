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
# <span data-ttu-id="f33ed-103">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f33ed-103">New-ScheduledJobOption</span></span>

## <span data-ttu-id="f33ed-104">概要</span><span class="sxs-lookup"><span data-stu-id="f33ed-104">SYNOPSIS</span></span>
<span data-ttu-id="f33ed-105">スケジュールされたジョブの詳細オプションを格納するオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-105">Creates an object that contains advanced options for a scheduled job.</span></span>

## <span data-ttu-id="f33ed-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f33ed-106">SYNTAX</span></span>

```
New-ScheduledJobOption [-RunElevated] [-HideInTaskScheduler] [-RestartOnIdleResume]
 [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart] [-RequireNetwork]
 [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery] [-IdleTimeout <TimeSpan>]
 [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## <span data-ttu-id="f33ed-107">Description</span><span class="sxs-lookup"><span data-stu-id="f33ed-107">DESCRIPTION</span></span>
<span data-ttu-id="f33ed-108">**New-ScheduledJobOption** コマンドレットは、スケジュールされたジョブの詳細オプションを格納するオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-108">The **New-ScheduledJobOption** cmdlet creates an object that contains advanced options for a scheduled job.</span></span>

<span data-ttu-id="f33ed-109">**New-ScheduledJobOption** から返された **ScheduledJobOptions** オブジェクトを使用して、新しいまたは既存のスケジュールされたジョブのジョブ オプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f33ed-109">You can use the **ScheduledJobOptions** object that **New-ScheduledJobOption** returns to set job options for a new or existing scheduled job.</span></span>
<span data-ttu-id="f33ed-110">または、Get-ScheduledJobOption コマンドレットを使用して、既存のスケジュールされたジョブのジョブオプションを取得したり、ジョブオプションを表すハッシュテーブル値を使用して、ジョブオプションを設定したりできます。</span><span class="sxs-lookup"><span data-stu-id="f33ed-110">Alternatively, you can set job options by using the Get-ScheduledJobOption cmdlet to get the job options of an existing scheduled job or by using a hash table value to represent the job options.</span></span>

<span data-ttu-id="f33ed-111">パラメーターを指定しない場合、 **get-scheduledjoboption** は、すべてのオプションの既定値を含むオブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-111">Without parameters, **New-ScheduledJobOption** generates an object that contains the default values for all of the options.</span></span>
<span data-ttu-id="f33ed-112">JobDefinition プロパティを除くすべてのプロパティを編集できるため、結果のオブジェクトをテンプレートとして使用し、企業の標準のオプション オブジェクトを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f33ed-112">Because all of the properties except for the JobDefinition property can be edited, you can use the resulting object as a template, and create standard option objects for your enterprise.</span></span>

<span data-ttu-id="f33ed-113">スケジュールされたジョブを作成し、スケジュールされたジョブのオプションを設定する際は、スケジュールされたジョブのすべてのオプションの既定値を確認してください。</span><span class="sxs-lookup"><span data-stu-id="f33ed-113">When creating scheduled jobs and setting scheduled job options, review the default values of all scheduled job options.</span></span>
<span data-ttu-id="f33ed-114">スケジュールされたジョブは、設定されている実行条件をすべて満たした場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="f33ed-114">Scheduled jobs run only when all conditions set for their execution are satisfied.</span></span>

<span data-ttu-id="f33ed-115">**Get-scheduledjoboption** は、Windows PowerShell に含まれている psscheduledjob モジュールのジョブスケジュールコマンドレットのコレクションの1つです。</span><span class="sxs-lookup"><span data-stu-id="f33ed-115">**New-ScheduledJobOption** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="f33ed-116">スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f33ed-116">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="f33ed-117">PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f33ed-117">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="f33ed-118">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f33ed-118">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="f33ed-119">例</span><span class="sxs-lookup"><span data-stu-id="f33ed-119">EXAMPLES</span></span>

### <span data-ttu-id="f33ed-120">例 1: スケジュールされたジョブオプションオブジェクトを既定値で作成する</span><span class="sxs-lookup"><span data-stu-id="f33ed-120">Example 1: Create a scheduled job option object with default values</span></span>

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

<span data-ttu-id="f33ed-121">このコマンドは、スケジュールされたジョブの、すべて既定値のオプション オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-121">This command creates a scheduled job option object that has all of the default values.</span></span>

### <span data-ttu-id="f33ed-122">例 2: スケジュールされたジョブオプションオブジェクトをカスタム値で作成する</span><span class="sxs-lookup"><span data-stu-id="f33ed-122">Example 2: Create a scheduled job option object with custom values</span></span>

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

<span data-ttu-id="f33ed-123">次のコマンドは、ネットワークを必要とし、コンピューターが AC 電源に接続されていない場合でもスケジュールされたジョブを実行するスケジュールされたジョブのオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-123">The following command creates a scheduled job object that requires the network and runs the scheduled job even if the computer is not connected to AC power.</span></span>

<span data-ttu-id="f33ed-124">出力には、 *RequireNetwork* パラメーターの値を $False に変更し、 *starti バッテリ* のパラメーターの値を $True に変更したことが示されています。</span><span class="sxs-lookup"><span data-stu-id="f33ed-124">The output shows that the *RequireNetwork* parameter changed the value of the RunWithoutNetwork property to $False and the *StartIfOnBattery* parameter changed the value of the StartIfOnBatteries property to $True.</span></span>

### <span data-ttu-id="f33ed-125">例 3: 新しいスケジュールされたジョブのオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="f33ed-125">Example 3: Set options for a new scheduled job</span></span>

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

<span data-ttu-id="f33ed-126">この例では、 **New-ScheduledJobOption** から返された **ScheduledJobOptions** オブジェクトを使用して、スケジュールされた新しいジョブのオプションを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-126">This example shows how to use the **ScheduledJobOptions** object that **New-ScheduledJobOption** returns to set the options for a new scheduled job.</span></span>

### <span data-ttu-id="f33ed-127">例 4: スケジュールされたジョブのオプションオブジェクトのプロパティを並べ替える</span><span class="sxs-lookup"><span data-stu-id="f33ed-127">Example 4: Sort the properties of a scheduled job option object</span></span>

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

<span data-ttu-id="f33ed-128">この例では、 **ScheduledJobOptions** オブジェクトのプロパティを見やすいようにアルファベット順で並べ替える方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-128">This example shows how to sort the properties of a **ScheduledJobOptions** object in alphabetical order for easy reading.</span></span>

<span data-ttu-id="f33ed-129">最初のコマンドは、 **New-ScheduledJobOption** コマンドレットを使用して、 **ScheduledJobOptions** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-129">The first command uses the **New-ScheduledJobOption** cmdlet to create a **ScheduledJobOptions** object.</span></span>
<span data-ttu-id="f33ed-130">このコマンドでは、 *WakeToRun* パラメーターを使用して、結果のオブジェクトを $Options 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-130">The command uses the *WakeToRun* parameter and saves the resulting object in the $Options variable.</span></span>

<span data-ttu-id="f33ed-131">オブジェクトとして $Options のプロパティを取得するために、2番目のコマンドは、すべての Windows PowerShell オブジェクトとその Properties プロパティの **PSObject** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-131">To get the properties of $Options as objects, the second command uses the **PSObject** property of all Windows PowerShell objects and its Properties property.</span></span>
<span data-ttu-id="f33ed-132">次に、コマンドを使用してプロパティオブジェクトを Sort-Object コマンドレットに渡します。このコマンドレットは、プロパティを名前順にアルファベット順に並べ替え、Format-Table コマンドレットに渡して、テーブルのプロパティの名前と値を表示します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-132">The command then pipes the property objects to the Sort-Object cmdlet, which sorts the properties in alphabetical order by name, and then to the Format-Table cmdlet, which displays the names and values of the properties in a table.</span></span>

<span data-ttu-id="f33ed-133">この形式を使用すると、$Options で **ScheduledJobOptions** オブジェクトの WakeToRun プロパティを検索し、その値が $False から $True に変更されたことを確認することが非常に簡単になります。</span><span class="sxs-lookup"><span data-stu-id="f33ed-133">This format makes it much easier to find the WakeToRun property of the **ScheduledJobOptions** object in $Options and to verify that its value was changed from $False to $True.</span></span>

## <span data-ttu-id="f33ed-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f33ed-134">PARAMETERS</span></span>

### <span data-ttu-id="f33ed-135">-続行 Eifgoingonバッテリ</span><span class="sxs-lookup"><span data-stu-id="f33ed-135">-ContinueIfGoingOnBattery</span></span>
<span data-ttu-id="f33ed-136">ジョブの実行中に、コンピューターがバッテリ電源に切り替わっても (AC 電源から切断されても)、スケジュールされたジョブを停止しません。</span><span class="sxs-lookup"><span data-stu-id="f33ed-136">Do not stop the scheduled job if the computer switches to battery power (disconnects from AC power) while the job is running.</span></span>
<span data-ttu-id="f33ed-137">既定では、コンピューターが AC 電源から切断されると、スケジュールされたジョブは停止します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-137">By default, scheduled jobs stop when the computer disconnects from AC power.</span></span>

<span data-ttu-id="f33ed-138">*続行 Eifgoingonバッテリ* パラメーターは、スケジュールされたジョブの StopIfGoingOnBatteries プロパティの値を $True に設定します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-138">The *ContinueIfGoingOnBattery* parameter sets the value of the StopIfGoingOnBatteries property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="f33ed-139">-DoNotAllowDemandStart</span><span class="sxs-lookup"><span data-stu-id="f33ed-139">-DoNotAllowDemandStart</span></span>
<span data-ttu-id="f33ed-140">トリガーされた場合にのみ、ジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-140">Start the job only when it is triggered.</span></span>
<span data-ttu-id="f33ed-141">ユーザーは、タスク スケジューラの実行機能などを使用して、手動でジョブを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="f33ed-141">Users cannot start the job manually, such as by using the Run feature in Task Scheduler.</span></span>

<span data-ttu-id="f33ed-142">このパラメーターは、タスク スケジューラにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-142">This parameter only affects Task Scheduler.</span></span>
<span data-ttu-id="f33ed-143">ユーザーが Start-Job コマンドレットを使用してジョブを開始するのを防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="f33ed-143">It does not prevents users from using the Start-Job cmdlet to start the job.</span></span>

<span data-ttu-id="f33ed-144">*DoNotAllowDemandStart* パラメーターは、スケジュールされたジョブの DoNotAllowDemandStart プロパティの値を $True に設定します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-144">The *DoNotAllowDemandStart* parameter sets the value of the DoNotAllowDemandStart property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="f33ed-145">-HideInTaskScheduler</span><span class="sxs-lookup"><span data-stu-id="f33ed-145">-HideInTaskScheduler</span></span>
<span data-ttu-id="f33ed-146">タスク スケジューラにジョブを表示しません。</span><span class="sxs-lookup"><span data-stu-id="f33ed-146">Do not display the job in Task Scheduler.</span></span>
<span data-ttu-id="f33ed-147">この値は、ジョブが実行されるコンピューターにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-147">This value affects only the computer on which the job runs.</span></span>
<span data-ttu-id="f33ed-148">既定では、スケジュールされたタスクはタスク スケジューラに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f33ed-148">By default, scheduled tasks appear in Task Scheduler.</span></span>

<span data-ttu-id="f33ed-149">タスクが非表示の場合でも、ユーザーはタスクスケジューラの [非表示のタスクビューを表示] オプションを選択することでタスクを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f33ed-149">Even if a task is hidden, users can display the task by selecting the Show hidden tasks view option in Task Scheduler.</span></span>

<span data-ttu-id="f33ed-150">*HideInTaskScheduler* パラメーターは、スケジュールされたジョブの ShowInTaskScheduler プロパティの値を $False に設定します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-150">The *HideInTaskScheduler* parameter sets the value of the ShowInTaskScheduler property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="f33ed-151">-IdleDuration</span><span class="sxs-lookup"><span data-stu-id="f33ed-151">-IdleDuration</span></span>
<span data-ttu-id="f33ed-152">コンピューターのアイドル状態がどれだけ続いたらジョブを開始するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-152">Specifies how long the computer must be idle before the job starts.</span></span>
<span data-ttu-id="f33ed-153">既定値は 10 分です。</span><span class="sxs-lookup"><span data-stu-id="f33ed-153">The default value is 10 minutes.</span></span>
<span data-ttu-id="f33ed-154">*IdleTimeout* の値を過ぎる前に、コンピューターが指定された時間アイドル状態にならないと、(次のスケジュールされた時刻が設定されていれば、それまで) スケジュールされたジョブは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f33ed-154">If the computer is not idle for the specified duration before the value of *IdleTimeout* expires, the scheduled job does not run until the next scheduled time, if any.</span></span>

<span data-ttu-id="f33ed-155">**Timespan** オブジェクトを入力します。たとえば、New-TimeSpan コマンドレットによって生成されたものや、 \<hours\> \<minutes\> \<seconds\> **timespan** オブジェクトに自動的に変換される:: format の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-155">Enter a **TimeSpan** object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format  that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="f33ed-156">この値を有効にするには、 *StartIfIdle* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-156">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="f33ed-157">既定では、スケジュールされたジョブの StartIfNotIdle プロパティは $True に設定され、Windows PowerShell は *IdleDuration* と *IdleTimeout* の値を無視します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-157">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

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

### <span data-ttu-id="f33ed-158">-IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="f33ed-158">-IdleTimeout</span></span>
<span data-ttu-id="f33ed-159">コンピューターがアイドル状態になるまでのスケジュールされたジョブの待機時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-159">Specifies how long the scheduled job waits for the computer to be idle.</span></span>
<span data-ttu-id="f33ed-160">コンピューターが *IdleDuration* パラメーターで指定された時間アイドル状態になる前に、このタイムアウトを過ぎた場合、(次のスケジュールされた時刻が設定されていれば、それまで) ジョブは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f33ed-160">If this timeout expires before the computer remains idle for the time period that is specified by the *IdleDuration* parameter, the job does not run until the next scheduled time, if any.</span></span>
<span data-ttu-id="f33ed-161">既定値は 1 時間です。</span><span class="sxs-lookup"><span data-stu-id="f33ed-161">The default value is one hour.</span></span>

<span data-ttu-id="f33ed-162">**Timespan** オブジェクトを入力します。たとえば、New-TimeSpan コマンドレットによって生成されたものや、 \<hours\> \<minutes\> \<seconds\> **timespan** オブジェクトに自動的に変換される:: format の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-162">Enter a **TimeSpan** object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="f33ed-163">この値を有効にするには、 *StartIfIdle* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-163">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="f33ed-164">既定では、スケジュールされたジョブの StartIfNotIdle プロパティは $True に設定され、Windows PowerShell は *IdleDuration* と *IdleTimeout* の値を無視します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-164">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

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

### <span data-ttu-id="f33ed-165">-多重 Instancepolicy</span><span class="sxs-lookup"><span data-stu-id="f33ed-165">-MultipleInstancePolicy</span></span>
<span data-ttu-id="f33ed-166">スケジュールされたジョブのインスタンスの実行中にそのジョブの別のインスタンスを開始する要求に対するシステムの応答方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-166">Determines how the system responds to a request to start an instance of a scheduled job while another instance of the job is running.</span></span>
<span data-ttu-id="f33ed-167">既定値は IgnoreNew です。</span><span class="sxs-lookup"><span data-stu-id="f33ed-167">The default value is IgnoreNew.</span></span>
<span data-ttu-id="f33ed-168">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f33ed-168">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f33ed-169">IgnoreNew.</span><span class="sxs-lookup"><span data-stu-id="f33ed-169">IgnoreNew.</span></span>
<span data-ttu-id="f33ed-170">新しいジョブ インスタンスを無視します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-170">The new job instance is ignored.</span></span>
- <span data-ttu-id="f33ed-171">パラレル。</span><span class="sxs-lookup"><span data-stu-id="f33ed-171">Parallel.</span></span>
<span data-ttu-id="f33ed-172">新しいジョブ インスタンスをすぐに開始します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-172">The new job instance starts immediately.</span></span>
- <span data-ttu-id="f33ed-173">キュー:</span><span class="sxs-lookup"><span data-stu-id="f33ed-173">Queue.</span></span>
<span data-ttu-id="f33ed-174">現在のジョブ インスタンスが完了したら、すぐに新しいインスタンスを開始します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-174">The new job instance starts as soon as the current instance completes.</span></span>
- <span data-ttu-id="f33ed-175">StopExisting。</span><span class="sxs-lookup"><span data-stu-id="f33ed-175">StopExisting.</span></span>
<span data-ttu-id="f33ed-176">ジョブの現在のインスタンスが停止し、新しいインスタンスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="f33ed-176">The current instance of the job stops and the new instance starts.</span></span>

<span data-ttu-id="f33ed-177">ジョブを実行するには、ジョブ スケジュールのすべての条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="f33ed-177">To run the job, all conditions for the job schedule must be met.</span></span>
<span data-ttu-id="f33ed-178">たとえば、 *RequireNetwork* 、 *IdleDuration* 、および *IdleTimeout* パラメーターによって設定された条件が満たされない場合、このパラメーターの値に関係なく、ジョブインスタンスは開始されません。</span><span class="sxs-lookup"><span data-stu-id="f33ed-178">For example, if the conditions that are set by the *RequireNetwork* , *IdleDuration* , and *IdleTimeout* parameters are not satisfied, the job instance is not started, regardless of the value of this parameter.</span></span>

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

### <span data-ttu-id="f33ed-179">-RequireNetwork</span><span class="sxs-lookup"><span data-stu-id="f33ed-179">-RequireNetwork</span></span>
<span data-ttu-id="f33ed-180">ネットワーク接続が利用可能な場合にのみ、スケジュールされたジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-180">Runs the scheduled job only when network connections are available.</span></span>

<span data-ttu-id="f33ed-181">このパラメーターを指定し、スケジュールされた開始時刻にネットワークが利用できない場合は、(次のスケジュールされた開始時刻が設定されていれば、それまで) ジョブは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f33ed-181">If you specify this parameter and the network is not available at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="f33ed-182">*RequireNetwork* パラメーターは、スケジュールされたジョブの Run network プロパティの値を $False に設定します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-182">The *RequireNetwork* parameter sets the value of the RunWithoutNetwork property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="f33ed-183">-RestartOnIdleResume</span><span class="sxs-lookup"><span data-stu-id="f33ed-183">-RestartOnIdleResume</span></span>
<span data-ttu-id="f33ed-184">コンピューターがアイドル状態になると、スケジュールされたジョブを再開します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-184">Restarts a scheduled job when the computer becomes idle.</span></span>
<span data-ttu-id="f33ed-185">このパラメーターは、コンピューターがアクティブになる (アイドル状態でなくなる) と実行中のスケジュールされたジョブを中断する *StopIfGoingOffIdle* パラメーターと連動しています。</span><span class="sxs-lookup"><span data-stu-id="f33ed-185">This parameter works with the *StopIfGoingOffIdle* parameter, which suspends a running scheduled job if the computer becomes active (leaves the idle state).</span></span>

<span data-ttu-id="f33ed-186">*RestartOnIdleResume* パラメーターは、スケジュールされたジョブの RestartOnIdleResume プロパティの値を $True に設定します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-186">The *RestartOnIdleResume* parameter sets the value of the RestartOnIdleResume property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="f33ed-187">-RunElevated</span><span class="sxs-lookup"><span data-stu-id="f33ed-187">-RunElevated</span></span>
<span data-ttu-id="f33ed-188">ジョブが実行されるコンピューター上の Administrators グループのメンバーのアクセス許可で、スケジュールされたジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-188">Runs the scheduled job with the permissions of a member of the Administrators group on the computer on which the job runs.</span></span>

<span data-ttu-id="f33ed-189">スケジュールされたジョブを管理者権限で実行できるようにするには、Register-ScheduledJob の *credential* パラメーターを使用して、ジョブに明示的な資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-189">To enable a scheduled job to run with Administrator permissions, use the *Credential* parameter of Register-ScheduledJob to provide explicit credential for the job.</span></span>

<span data-ttu-id="f33ed-190">*Runelevated* パラメーターは、スケジュールされたジョブの runelevated されたプロパティの値を $True に設定します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-190">The *RunElevated* parameter sets the value of the RunElevated property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="f33ed-191">-StartIfIdle</span><span class="sxs-lookup"><span data-stu-id="f33ed-191">-StartIfIdle</span></span>
<span data-ttu-id="f33ed-192">*IdleTimeout* パラメーターに指定された時間を過ぎる前に、コンピューターが *IdleDuration* パラメーターに指定された時間アイドル状態になった場合に、スケジュールされたジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-192">Starts the scheduled job if the computer has been idle for the time specified by the *IdleDuration* parameter before the time specified by the *IdleTimeout* parameter expires.</span></span>

<span data-ttu-id="f33ed-193">既定では、 *IdleDuration* パラメーターと *IdleTimeout* パラメーターは無視され、コンピューターがビジー状態でも、ジョブはスケジュールされた開始時刻に開始されます。</span><span class="sxs-lookup"><span data-stu-id="f33ed-193">By default, the *IdleDuration* and *IdleTimeout* parameters are ignored and the job starts at the scheduled start time even if the computer is busy.</span></span>

<span data-ttu-id="f33ed-194">このパラメーターを指定し、スケジュールされた開始時刻にコンピューターがビジー状態の場合 (アイドル状態でない場合) は、(次のスケジュールされた開始時刻が設定されていれば、それまで) ジョブは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f33ed-194">If you specify this parameter and the computer is busy (not idle) at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="f33ed-195">*StartIfIdle* パラメーターは、スケジュールされたジョブの StartIfNotIdle プロパティの値を $False に設定します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-195">The *StartIfIdle* parameter sets the value of the StartIfNotIdle property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="f33ed-196">-Starti区別バッテリ</span><span class="sxs-lookup"><span data-stu-id="f33ed-196">-StartIfOnBattery</span></span>
<span data-ttu-id="f33ed-197">スケジュールされた開始時刻にコンピューターがバッテリで動作していても、スケジュールされたジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-197">Starts the scheduled job even if the computer is running on batteries at the scheduled start time.</span></span>
<span data-ttu-id="f33ed-198">既定値は $False です。</span><span class="sxs-lookup"><span data-stu-id="f33ed-198">The default value is $False.</span></span>

<span data-ttu-id="f33ed-199">*Startiのバッテリ* パラメーターは、スケジュールされたジョブの startiの電池プロパティの値を $True に設定します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-199">The *StartIfOnBattery* parameter sets the value of the StartIfOnBatteries property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="f33ed-200">-StopIfGoingOffIdle</span><span class="sxs-lookup"><span data-stu-id="f33ed-200">-StopIfGoingOffIdle</span></span>
<span data-ttu-id="f33ed-201">ジョブの実行中に、コンピューターがアクティブになる (アイドル状態でなくなる) と、実行中のスケジュールされたジョブを中断します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-201">Suspends a running scheduled job if the computer becomes active (not idle) while the job is running.</span></span>

<span data-ttu-id="f33ed-202">既定では、コンピューターがアクティブになったときに中断されたスケジュールされたジョブは、コンピューターが再びアイドル状態になると再開されます。</span><span class="sxs-lookup"><span data-stu-id="f33ed-202">By default, a scheduled job that is suspended when the computer becomes active resumes when the computer becomes idle again.</span></span>
<span data-ttu-id="f33ed-203">この既定の動作を変更するには、 *RestartOnIdleResume* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-203">To change this default behavior, use the *RestartOnIdleResume* parameter.</span></span>

<span data-ttu-id="f33ed-204">*StopIfGoingOffIdle* パラメーターは、スケジュールされたジョブの StopIfGoingOffIdle プロパティの値を $True に設定します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-204">The *StopIfGoingOffIdle* parameter sets the value of the StopIfGoingOffIdle property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="f33ed-205">-WakeToRun</span><span class="sxs-lookup"><span data-stu-id="f33ed-205">-WakeToRun</span></span>
<span data-ttu-id="f33ed-206">スケジュールされた開始時刻にコンピューターの休止状態またはスリープ状態を解除して、ジョブを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f33ed-206">Wakes the computer from a Hibernate or Sleep state at the scheduled start time so it can run the job.</span></span>
<span data-ttu-id="f33ed-207">既定では、スケジュールされた開始時刻にコンピューターが休止状態またはスリープ状態の場合、ジョブは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f33ed-207">By default, if the computer is in a Hibernate or Sleep state at the scheduled start time, the job does not run.</span></span>

<span data-ttu-id="f33ed-208">*WakeToRun* パラメーターは、スケジュールされたジョブの WakeToRun プロパティの値を $True に設定します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-208">The *WakeToRun* parameter sets the value of the WakeToRun property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="f33ed-209">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f33ed-209">CommonParameters</span></span>
<span data-ttu-id="f33ed-210">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f33ed-210">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f33ed-211">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f33ed-211">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f33ed-212">入力</span><span class="sxs-lookup"><span data-stu-id="f33ed-212">INPUTS</span></span>

### <span data-ttu-id="f33ed-213">なし</span><span class="sxs-lookup"><span data-stu-id="f33ed-213">None</span></span>
<span data-ttu-id="f33ed-214">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="f33ed-214">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="f33ed-215">出力</span><span class="sxs-lookup"><span data-stu-id="f33ed-215">OUTPUTS</span></span>

### <span data-ttu-id="f33ed-216">ScheduledJobOptions (Microsoft PowerShell)</span><span class="sxs-lookup"><span data-stu-id="f33ed-216">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>

## <span data-ttu-id="f33ed-217">注</span><span class="sxs-lookup"><span data-stu-id="f33ed-217">NOTES</span></span>

* <span data-ttu-id="f33ed-218">**ScheduledJobOptions** オブジェクトを使用できます。 **get-scheduledjoboption** は、Register-ScheduledJob コマンドレットの *get-scheduledjoboption* パラメーターの値として作成されます。</span><span class="sxs-lookup"><span data-stu-id="f33ed-218">You can use the **ScheduledJobOptions** object that **New-ScheduledJobOption** creates as the value of the *ScheduledJobOption* parameter of the Register-ScheduledJob cmdlet.</span></span> <span data-ttu-id="f33ed-219">ただし、 *get-scheduledjoboption* パラメーターは、 **ScheduledJobOptions** オブジェクトのプロパティとその値を指定するハッシュテーブルの値を受け取ることもできます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f33ed-219">However, the *ScheduledJobOption* parameter can also take a hash table value that specifies the properties of the **ScheduledJobOptions** object and their values, such as:</span></span>

  `@{ShowInTaskScheduler=$False; RunElevated=$True; IdleDuration="00:05"}`

## <span data-ttu-id="f33ed-220">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f33ed-220">RELATED LINKS</span></span>

[<span data-ttu-id="f33ed-221">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f33ed-221">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="f33ed-222">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f33ed-222">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="f33ed-223">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f33ed-223">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="f33ed-224">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f33ed-224">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="f33ed-225">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f33ed-225">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="f33ed-226">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f33ed-226">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="f33ed-227">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f33ed-227">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="f33ed-228">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f33ed-228">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="f33ed-229">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f33ed-229">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="f33ed-230">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f33ed-230">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="f33ed-231">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f33ed-231">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="f33ed-232">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f33ed-232">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="f33ed-233">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f33ed-233">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="f33ed-234">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f33ed-234">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="f33ed-235">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f33ed-235">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="f33ed-236">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f33ed-236">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
