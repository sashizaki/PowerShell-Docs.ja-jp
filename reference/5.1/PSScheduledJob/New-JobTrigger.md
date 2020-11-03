---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-JobTrigger
ms.openlocfilehash: de49ab937c6f3a8187f5aecd6aafc81425b8cd00
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213424"
---
# <span data-ttu-id="befbe-103">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="befbe-103">New-JobTrigger</span></span>

## <span data-ttu-id="befbe-104">概要</span><span class="sxs-lookup"><span data-stu-id="befbe-104">SYNOPSIS</span></span>
<span data-ttu-id="befbe-105">スケジュールされたジョブのジョブ トリガーを作成します。</span><span class="sxs-lookup"><span data-stu-id="befbe-105">Creates a job trigger for a scheduled job.</span></span>

## <span data-ttu-id="befbe-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="befbe-106">SYNTAX</span></span>

### <span data-ttu-id="befbe-107">Once (既定値)</span><span class="sxs-lookup"><span data-stu-id="befbe-107">Once (Default)</span></span>

```
New-JobTrigger [-RandomDelay <TimeSpan>] -At <DateTime> [-Once] [-RepetitionInterval <TimeSpan>]
 [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely] [<CommonParameters>]
```

### <span data-ttu-id="befbe-108">毎日</span><span class="sxs-lookup"><span data-stu-id="befbe-108">Daily</span></span>

```
New-JobTrigger [-DaysInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> [-Daily] [<CommonParameters>]
```

### <span data-ttu-id="befbe-109">週単位</span><span class="sxs-lookup"><span data-stu-id="befbe-109">Weekly</span></span>

```
New-JobTrigger [-WeeksInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> -DaysOfWeek <DayOfWeek[]>
 [-Weekly] [<CommonParameters>]
```

### <span data-ttu-id="befbe-110">AtStartup</span><span class="sxs-lookup"><span data-stu-id="befbe-110">AtStartup</span></span>

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-AtStartup] [<CommonParameters>]
```

### <span data-ttu-id="befbe-111">AtLogon</span><span class="sxs-lookup"><span data-stu-id="befbe-111">AtLogon</span></span>

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-User <String>] [-AtLogOn] [<CommonParameters>]
```

## <span data-ttu-id="befbe-112">Description</span><span class="sxs-lookup"><span data-stu-id="befbe-112">DESCRIPTION</span></span>
<span data-ttu-id="befbe-113">**新しい-JobTrigger** コマンドレットは、スケジュールされたジョブを1回だけ、または定期的なスケジュールで開始するか、イベントが発生したときに開始するジョブトリガーを作成します。</span><span class="sxs-lookup"><span data-stu-id="befbe-113">The **New-JobTrigger** cmdlet creates a job trigger that starts a scheduled job on a one-time or recurring schedule, or when an event occurs.</span></span>

<span data-ttu-id="befbe-114">**New-JobTrigger** から返された **ScheduledJobTrigger** オブジェクトを使用して、新しいまたは既存のスケジュールされたジョブのジョブ トリガーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="befbe-114">You can use the **ScheduledJobTrigger** object that **New-JobTrigger** returns to set a job trigger for a new or existing scheduled job.</span></span>
<span data-ttu-id="befbe-115">また、Get-JobTrigger コマンドレットを使用して、既存のスケジュールされたジョブのジョブトリガーを取得したり、ジョブトリガーを表すハッシュテーブル値を使用して、ジョブトリガーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="befbe-115">You can also create a job trigger by using the Get-JobTrigger cmdlet to get the job trigger of an existing scheduled job, or by using a hash table value to represent a job trigger.</span></span>

<span data-ttu-id="befbe-116">ジョブトリガーを作成するときに、New-ScheduledJobOption コマンドレットによって指定されたオプションの既定値を確認します。</span><span class="sxs-lookup"><span data-stu-id="befbe-116">When creating a job trigger, review the default values of the options specified by the New-ScheduledJobOption cmdlet.</span></span>
<span data-ttu-id="befbe-117">これらのオプションは、有効な値と既定値が **Task Scheduler** の対応するオプションと同じで、スケジュールされたジョブのスケジュールとタイミングに影響します。</span><span class="sxs-lookup"><span data-stu-id="befbe-117">These options, which have the same valid and default values as the corresponding options in **Task Scheduler** , affect the scheduling and timing of scheduled jobs.</span></span>

<span data-ttu-id="befbe-118">**New-JobTrigger** は、Windows PowerShell に含まれている psscheduledjob モジュールのジョブスケジュールコマンドレットのコレクションの1つです。</span><span class="sxs-lookup"><span data-stu-id="befbe-118">**New-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="befbe-119">スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="befbe-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="befbe-120">PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="befbe-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="befbe-121">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="befbe-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="befbe-122">例</span><span class="sxs-lookup"><span data-stu-id="befbe-122">EXAMPLES</span></span>

### <span data-ttu-id="befbe-123">例 1: スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="befbe-123">Example 1: Once Schedule</span></span>

```
PS C:\> New-JobTrigger -Once -At "1/20/2012 3:00 AM"
```

<span data-ttu-id="befbe-124">このコマンドは、 **New-JobTrigger** コマンドレットを使用して、スケジュールされたジョブを 1 回だけ開始するジョブ トリガーを作成します。</span><span class="sxs-lookup"><span data-stu-id="befbe-124">This command uses the **New-JobTrigger** cmdlet to create a job trigger that starts a scheduled job only one time.</span></span>
<span data-ttu-id="befbe-125">*At* パラメーターの値は、Windows PowerShell によって **DateTime** オブジェクトに変換される文字列です。</span><span class="sxs-lookup"><span data-stu-id="befbe-125">The value of the *At* parameter is a string that Windows PowerShell converts into a **DateTime** object.</span></span>
<span data-ttu-id="befbe-126">*At* パラメーターの値には、時刻だけでなく、明示的な日付も含まれています。</span><span class="sxs-lookup"><span data-stu-id="befbe-126">The *At* parameter value includes an explicit date, not just a time.</span></span>
<span data-ttu-id="befbe-127">日付を省略すると、現在の日付の午前 3 時 00 分のトリガーが作成されます。これは、過去の時刻を表す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="befbe-127">If the date were omitted, the trigger would be created with the current date and 3:00 AM time, which is likely to represent a time in the past.</span></span>

### <span data-ttu-id="befbe-128">例 2: 日単位のスケジュール</span><span class="sxs-lookup"><span data-stu-id="befbe-128">Example 2: Daily Schedule</span></span>

```
PS C:\> New-JobTrigger -Daily -At "4:15 AM" -DaysInterval 3
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/21/2012 4:15:00 AM                           True
```

<span data-ttu-id="befbe-129">このコマンドは、3 日おきの午前 4 時 15 分にスケジュールされたジョブを開始するジョブ トリガーを作成します。</span><span class="sxs-lookup"><span data-stu-id="befbe-129">This command creates a job trigger that starts a scheduled job every 3 days at 4:15 a.m.</span></span>

<span data-ttu-id="befbe-130">*At* パラメーターの値には日付が含まれていないため、 **DateTime** オブジェクトの日付の値として現在の日付が使用されます。</span><span class="sxs-lookup"><span data-stu-id="befbe-130">Because the value of the *At* parameter does not include a date, the current date is used as the date value in the **DateTime** object.</span></span>
<span data-ttu-id="befbe-131">日時が過去の場合、スケジュールされたジョブは次の実行日 ( *At* パラメーターの値の 3 日後) に開始されます。</span><span class="sxs-lookup"><span data-stu-id="befbe-131">If the date and time is in the past, the scheduled job is started at the next occurrence, which is 3 days later from the *At* parameter value.</span></span>

### <span data-ttu-id="befbe-132">例 3: 週単位のスケジュール</span><span class="sxs-lookup"><span data-stu-id="befbe-132">Example 3: Weekly Schedule</span></span>

```
PS C:\> New-JobTrigger -Weekly -DaysOfWeek Monday, Wednesday, Friday -At "23:00" -WeeksInterval 4
Id Frequency Time                  DaysOfWeek                  Enabled
-- --------- ----                  ----------                  -------
0  Weekly    9/21/2012 11:00:00 PM {Monday, Wednesday, Friday} True
```

<span data-ttu-id="befbe-133">このコマンドは、4 週間おきの月曜日、水曜日、および金曜日の 23:00 (午後 11 時 00 分) にスケジュールされたジョブを開始するジョブ トリガーを作成します。</span><span class="sxs-lookup"><span data-stu-id="befbe-133">This command creates a job trigger that starts a scheduled job every 4 weeks on Monday, Wednesday, and Friday at 2300 hours (11:00 PM).</span></span>

<span data-ttu-id="befbe-134">*DaysOfWeek* パラメーターの値は、のような整数で入力することもでき `-DaysOfWeek 1, 5` ます。</span><span class="sxs-lookup"><span data-stu-id="befbe-134">You can also enter the *DaysOfWeek* parameter value in integers, such as `-DaysOfWeek 1, 5`.</span></span>

### <span data-ttu-id="befbe-135">例 4: ログオンスケジュール</span><span class="sxs-lookup"><span data-stu-id="befbe-135">Example 4: Logon Schedule</span></span>

```
PS C:\> New-JobTrigger -AtLogOn -User Domain01\Admin01
```

<span data-ttu-id="befbe-136">このコマンドは、ドメイン管理者がコンピューターにログオンするたびに、スケジュールされたジョブを開始するジョブ トリガーを作成します。</span><span class="sxs-lookup"><span data-stu-id="befbe-136">This command creates a job trigger that starts a scheduled job whenever the domain administrator logs onto the computer.</span></span>

### <span data-ttu-id="befbe-137">例 5: ランダム遅延の使用</span><span class="sxs-lookup"><span data-stu-id="befbe-137">Example 5: Using a Random Delay</span></span>

```
PS C:\> New-JobTrigger -Daily -At 1:00 -RandomDelay 00:20:00
```

<span data-ttu-id="befbe-138">このコマンドは、毎日午前 1 時 00 分にスケジュールされたジョブを開始するジョブ トリガーを作成します。</span><span class="sxs-lookup"><span data-stu-id="befbe-138">This command creates a job trigger that starts a scheduled job every day at 1:00 in the morning.</span></span>
<span data-ttu-id="befbe-139">このコマンドでは、 *RandomDelay* パラメーターを使用して、遅延の最大値を 20 分に設定します。</span><span class="sxs-lookup"><span data-stu-id="befbe-139">The command uses the *RandomDelay* parameter to set the maximum delay to 20 minutes.</span></span>
<span data-ttu-id="befbe-140">その結果、ジョブは、毎日午前 1 時 00 分から 1 時 20 分の間に実行されます (時刻は擬似ランダムに変動します)。</span><span class="sxs-lookup"><span data-stu-id="befbe-140">As a result, the job runs every day between 1:00 AM and 1:20 AM, with the interval varying pseudo-randomly.</span></span>

<span data-ttu-id="befbe-141">ランダムな遅延は、サンプリング、負荷分散、およびその他の管理タスクに使用できます。</span><span class="sxs-lookup"><span data-stu-id="befbe-141">You can use a random delay for sampling, load balancing, and other administrative tasks.</span></span>
<span data-ttu-id="befbe-142">遅延値を設定するときは、New-ScheduledJobOption コマンドレットの有効値と既定値を確認し、オプション設定で遅延を調整します。</span><span class="sxs-lookup"><span data-stu-id="befbe-142">When setting the delay value, review the effective and default values of the New-ScheduledJobOption cmdlet and coordinate the delay with the option settings.</span></span>

### <span data-ttu-id="befbe-143">例 6: 新しいスケジュールされたジョブのジョブトリガーを作成する</span><span class="sxs-lookup"><span data-stu-id="befbe-143">Example 6: Create a Job Trigger for a New Scheduled Job</span></span>

```
The first command uses the **New-JobTrigger** cmdlet to create a job trigger that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The command saves the job trigger in the $T variable.
PS C:\> $T = New-JobTrigger -Weekly -DaysOfWeek 1,3,5 -At 12:01AM


The second command uses the Register-ScheduledJob cmdlet to create a scheduled job that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The value of the *Trigger* parameter is the trigger that is stored in the $T variable.
PS C:\> Register-ScheduledJob -Name Test-HelpFiles -FilePath C:\Scripts\Test-HelpFiles.ps1 -Trigger $T
```

<span data-ttu-id="befbe-144">これらのコマンドは、ジョブ トリガーを使用して、スケジュールされた新しいジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="befbe-144">These commands use a job trigger to create a new scheduled job.</span></span>

### <span data-ttu-id="befbe-145">例 7: スケジュールされたジョブにジョブトリガーを追加する</span><span class="sxs-lookup"><span data-stu-id="befbe-145">Example 7: Add a Job Trigger to a Scheduled Job</span></span>

```
PS C:\> Add-JobTrigger -Name SynchronizeApps -Trigger (New-JobTrigger -Daily -At 3:10AM)
```

<span data-ttu-id="befbe-146">この例では、既存のスケジュールされたジョブにジョブ トリガーを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="befbe-146">This example shows how to add a job trigger to an existing scheduled job.</span></span>
<span data-ttu-id="befbe-147">任意のスケジュールされたジョブに複数のジョブ トリガーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="befbe-147">You can add multiple job triggers to any scheduled job.</span></span>

<span data-ttu-id="befbe-148">このコマンドは、Add-JobTrigger コマンドレットを使用して、スケジュールされたジョブ SynchronizeApps にジョブトリガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="befbe-148">The command uses the Add-JobTrigger cmdlet to add the job trigger to the SynchronizeApps scheduled job.</span></span>
<span data-ttu-id="befbe-149">*Trigger* パラメーターの値は、毎日午前 3 時 10 分にジョブを実行する **New-JobTrigger** コマンドです。</span><span class="sxs-lookup"><span data-stu-id="befbe-149">The value of the *Trigger* parameter is a **New-JobTrigger** command that runs the job every day at 3:10 AM.</span></span>

<span data-ttu-id="befbe-150">コマンドが完了すると、SynchronizeApps は、ジョブ トリガーで指定された時刻に実行されるスケジュールされたジョブになります。</span><span class="sxs-lookup"><span data-stu-id="befbe-150">When the command completes, SynchronizeApps is a scheduled job that runs at the times specified by the job trigger.</span></span>

### <span data-ttu-id="befbe-151">例 8: 繰り返しジョブトリガーを作成する</span><span class="sxs-lookup"><span data-stu-id="befbe-151">Example 8: Create a repeating job trigger</span></span>

```
PS C:\> New-JobTrigger -Once -At "09/12/2013 1:00:00" -RepetitionInterval (New-TimeSpan -Hours 1) -RepetitionDuration (New-Timespan -Hours 48)
```

<span data-ttu-id="befbe-152">このコマンドを実行すると、60年9月 2013 12 日から 1:00 AM に48時間、ジョブを実行するジョブトリガーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="befbe-152">This command creates a job trigger that runs a job every 60 minutes for 48 hours beginning on September 12, 2013 at 1:00 AM.</span></span>

### <span data-ttu-id="befbe-153">例 9: 繰り返しのジョブトリガーを停止する</span><span class="sxs-lookup"><span data-stu-id="befbe-153">Example 9: Stop a repeating job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name SecurityCheck | Set-JobTrigger -RepetitionInterval 0:00 -RepetitionDuration 0:00
```

<span data-ttu-id="befbe-154">このコマンドは、トリガーされた SecurityCheck ジョブ (ジョブ トリガーの期限が過ぎるまで 60 分おきに実行されます) を強制的に停止します。</span><span class="sxs-lookup"><span data-stu-id="befbe-154">This command forcibly stops the SecurityCheck job, which is triggered to run every 60 minutes until its job trigger expires.</span></span>

<span data-ttu-id="befbe-155">ジョブが繰り返されないようにするには、Get-JobTrigger を使用して SecurityCheck ジョブのジョブトリガーを取得し、Set-JobTrigger コマンドレットを使用して、ジョブトリガーの繰り返し間隔と繰り返し期間をゼロ (0) に変更します。</span><span class="sxs-lookup"><span data-stu-id="befbe-155">To prevent the job from repeating, the command uses the Get-JobTrigger to get the job trigger of the SecurityCheck job and the Set-JobTrigger cmdlet to change the repetition interval and repetition duration of the job trigger to zero (0).</span></span>

### <span data-ttu-id="befbe-156">例 10: 1 時間ごとのジョブトリガーを作成する</span><span class="sxs-lookup"><span data-stu-id="befbe-156">Example 10: Create an hourly job trigger</span></span>

```
PS C:\> New-JobTrigger -Once -At "9/21/2012 0am" -RepetitionInterval (New-TimeSpan -Hour 12) -RepetitionDuration ([TimeSpan]::MaxValue)
```

<span data-ttu-id="befbe-157">次のコマンドは、無期限で、12 時間おきに 1 回スケジュールされたジョブを実行するジョブ トリガーを作成します。</span><span class="sxs-lookup"><span data-stu-id="befbe-157">The following command creates a job trigger that runs a scheduled job once every 12 hours for an indefinite period of time.</span></span>
<span data-ttu-id="befbe-158">スケジュールは、翌日 (2012 年 9 月 21 日) の午前 0 時 (0:00 AM) に開始されます。</span><span class="sxs-lookup"><span data-stu-id="befbe-158">The schedule begins tomorrow (9/21/2012) at midnight (0:00 AM).</span></span>

## <span data-ttu-id="befbe-159">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="befbe-159">PARAMETERS</span></span>

### <span data-ttu-id="befbe-160">-At</span><span class="sxs-lookup"><span data-stu-id="befbe-160">-At</span></span>
<span data-ttu-id="befbe-161">指定された日時にジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="befbe-161">Starts the job at the specified date and time.</span></span>
<span data-ttu-id="befbe-162">Get-Date コマンドレットが返す **DateTime** オブジェクト、または日付と時刻に変換できる文字列 ("April 19, 2012 15:00"、"12/31"、または "3am" など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="befbe-162">Enter a **DateTime** object, such as one that the Get-Date cmdlet returns, or a string that can be converted to a date and time, such as "April 19, 2012 15:00", "12/31", or "3am".</span></span>
<span data-ttu-id="befbe-163">年などの日付の要素を指定しない場合、トリガーの日付には、現在の日付の対応する要素が使用されます。</span><span class="sxs-lookup"><span data-stu-id="befbe-163">If you don't specify an element of the date, such as the year, the date in the trigger has the corresponding element from the current date.</span></span>

<span data-ttu-id="befbe-164">*Once* パラメーターを使用する場合は、 *At* パラメーターの値の設定を未来の日時に設定します。</span><span class="sxs-lookup"><span data-stu-id="befbe-164">When using the *Once* parameter, set the value of the *At* parameter to a future date and time.</span></span>
<span data-ttu-id="befbe-165">**DateTime** オブジェクトの既定の日付は現在の日付です。そのため、日付を明示的に指定せずに、現在の時刻より前の時刻を指定すると、過去の時刻のジョブ トリガーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="befbe-165">Because the default date in a **DateTime** object is the current date, if you specify a time before the current time without an explicit date, the job trigger is created for a time in the past.</span></span>

<span data-ttu-id="befbe-166">**Datetime オブジェクト** 、および **datetime** オブジェクトに変換された文字列は、コントロールパネルの [地域と言語] で選択した日付と時刻の形式と互換性があるように自動的に調整されます。</span><span class="sxs-lookup"><span data-stu-id="befbe-166">**DateTime** objects, and strings that are converted to **DateTime** objects, are automatically adjusted to be compatible with the date and time formats selected for the local computer in Region and Language in Control Panel.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Once, Daily, Weekly
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="befbe-167">-AtLogOn</span><span class="sxs-lookup"><span data-stu-id="befbe-167">-AtLogOn</span></span>
<span data-ttu-id="befbe-168">指定されたユーザーがコンピューターにログオンしたときに、スケジュールされたジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="befbe-168">Starts the scheduled job when the specified users log on to the computer.</span></span>
<span data-ttu-id="befbe-169">ユーザーを指定するには、 *User* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="befbe-169">To specify a user, use the *User* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtLogon
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="befbe-170">-AtStartup</span><span class="sxs-lookup"><span data-stu-id="befbe-170">-AtStartup</span></span>
<span data-ttu-id="befbe-171">Windows の起動時に、スケジュールされたジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="befbe-171">Starts the scheduled job when Windows starts.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtStartup
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="befbe-172">-毎日</span><span class="sxs-lookup"><span data-stu-id="befbe-172">-Daily</span></span>
<span data-ttu-id="befbe-173">日単位の定期的なジョブ スケジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="befbe-173">Specifies a recurring daily job schedule.</span></span>
<span data-ttu-id="befbe-174">*Daily* パラメーターセットの他のパラメーターを使用して、スケジュールの詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="befbe-174">Use the other parameters in the *Daily* parameter set to specify the schedule details.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Daily
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="befbe-175">-DaysInterval</span><span class="sxs-lookup"><span data-stu-id="befbe-175">-DaysInterval</span></span>
<span data-ttu-id="befbe-176">日単位のスケジュールの実行間隔を日数で指定します。</span><span class="sxs-lookup"><span data-stu-id="befbe-176">Specifies the number of days between occurrences on a daily schedule.</span></span>
<span data-ttu-id="befbe-177">たとえば、値が 3 の場合、スケジュールされたジョブは、1 日、4 日、7 日というように 3 日おきに開始されます。</span><span class="sxs-lookup"><span data-stu-id="befbe-177">For example, a value of 3 starts the scheduled job on days 1, 4, 7 and so on.</span></span>
<span data-ttu-id="befbe-178">既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="befbe-178">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Daily
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="befbe-179">-DaysOfWeek</span><span class="sxs-lookup"><span data-stu-id="befbe-179">-DaysOfWeek</span></span>
<span data-ttu-id="befbe-180">週単位でスケジュールされたジョブを実行する曜日を指定します。</span><span class="sxs-lookup"><span data-stu-id="befbe-180">Specifies the days of the week on which a weekly scheduled job runs.</span></span>
<span data-ttu-id="befbe-181">"Monday" などの曜日名または 0 ～ 6 の整数 (0 は日曜日を表します) を入力します。</span><span class="sxs-lookup"><span data-stu-id="befbe-181">Enter day names, such as "Monday" or integers 0-6, where 0 represents Sunday.</span></span>
<span data-ttu-id="befbe-182">Weekly パラメーター セットでは、このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="befbe-182">This parameter is required in the Weekly parameter set.</span></span>

<span data-ttu-id="befbe-183">ジョブ トリガーでは、曜日名は整数値に変換されます。</span><span class="sxs-lookup"><span data-stu-id="befbe-183">Day names are converted to their integer values in the job trigger.</span></span>
<span data-ttu-id="befbe-184">コマンド内で曜日名を引用符で囲む場合は、"Monday", "Tuesday" など、各曜日名を別々に引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="befbe-184">When you enclose day names in quotation marks in a command, enclose each day name in separate quotation marks, such as "Monday", "Tuesday".</span></span>
<span data-ttu-id="befbe-185">複数の曜日名を 1 つの引用符のペアで囲んだ場合は、対応する整数値が合計されます。</span><span class="sxs-lookup"><span data-stu-id="befbe-185">If you enclose multiple day names in a single quotation mark pair, the corresponding integer values are summed.</span></span>
<span data-ttu-id="befbe-186">たとえば、"Monday, Tuesday" (1, 2) は、"Wednesday" (3) になります。</span><span class="sxs-lookup"><span data-stu-id="befbe-186">For example, "Monday, Tuesday" (1, 2) results in a value of "Wednesday" (3).</span></span>

```yaml
Type: System.DayOfWeek[]
Parameter Sets: Weekly
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="befbe-187">-1 回</span><span class="sxs-lookup"><span data-stu-id="befbe-187">-Once</span></span>
<span data-ttu-id="befbe-188">非定期的な (1 回だけの) スケジュールまたは繰り返しのカスタム スケジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="befbe-188">Specifies a non-recurring (one time) or custom repeating schedule.</span></span>
<span data-ttu-id="befbe-189">繰り返しのスケジュールを作成するには、 *Once* パラメーターと一緒に *RepetitionDuration* パラメーターと *RepetitionInterval* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="befbe-189">To create a repeating schedule, use the *Once* parameter with the *RepetitionDuration* and *RepetitionInterval* parameters.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="befbe-190">-RandomDelay</span><span class="sxs-lookup"><span data-stu-id="befbe-190">-RandomDelay</span></span>
<span data-ttu-id="befbe-191">スケジュールされた開始時刻のランダムな遅延を有効にし、遅延の最大値を設定します。</span><span class="sxs-lookup"><span data-stu-id="befbe-191">Enables a random delay that begins at the scheduled start time, and sets the maximum delay value.</span></span>
<span data-ttu-id="befbe-192">遅延の長さは、開始ごとに擬似ランダムに設定され、遅延なしから、このパラメーターの値で指定された時間の間で変動します。</span><span class="sxs-lookup"><span data-stu-id="befbe-192">The length of the delay is set pseudo-randomly for each start and varies from no delay to the time specified by the value of this parameter.</span></span>
<span data-ttu-id="befbe-193">既定値のゼロ (00:00:00) では、ランダムな遅延が無効になります。</span><span class="sxs-lookup"><span data-stu-id="befbe-193">The default value, zero (00:00:00), disables the random delay.</span></span>

<span data-ttu-id="befbe-194">New-TimeSpan コマンドレットによって返されるような timespan オブジェクトを入力するか、:: format に値を入力します。この値は、 \<hours\> \<minutes\> \<seconds\> **timespan** オブジェクトに自動的に変換されます。</span><span class="sxs-lookup"><span data-stu-id="befbe-194">Enter a timespan object, such as one returned by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format, which is automatically converted to a **TimeSpan** object.</span></span>

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

### <span data-ttu-id="befbe-195">-繰り返し (無期限)</span><span class="sxs-lookup"><span data-stu-id="befbe-195">-RepeatIndefinitely</span></span>
<span data-ttu-id="befbe-196">このパラメーターは、Windows PowerShell 4.0 以降で利用でき、 **RepetitionDuration** パラメーターの *TimeSpan.MaxValue* 値を指定することなく、スケジュールされたジョブを無期限に繰り返し実行します。</span><span class="sxs-lookup"><span data-stu-id="befbe-196">This parameter, available starting in Windows PowerShell 4.0, eliminates the necessity of specifying a **TimeSpan.MaxValue** value for the *RepetitionDuration* parameter to run a scheduled job repeatedly, for an indefinite period.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="befbe-197">-RepetitionDuration</span><span class="sxs-lookup"><span data-stu-id="befbe-197">-RepetitionDuration</span></span>
<span data-ttu-id="befbe-198">指定された期間を過ぎるまでジョブを繰り返し実行します。</span><span class="sxs-lookup"><span data-stu-id="befbe-198">Repeats the job until the specified time expires.</span></span>
<span data-ttu-id="befbe-199">繰り返しの頻度は、 *RepetitionInterval* パラメーターの値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="befbe-199">The repetition frequency is determined by the value of the *RepetitionInterval* parameter.</span></span>
<span data-ttu-id="befbe-200">たとえば、 **RepetitionInterval** の値が 5 分で、 **RepetitionDuration** の値が 2 時間の場合、ジョブは 2 時間の間 5 分おきにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="befbe-200">For example, if the value of **RepetitionInterval** is 5 minutes and the value of **RepetitionDuration** is 2 hours, the job is triggered every five minutes for two hours.</span></span>

<span data-ttu-id="befbe-201">New-TimeSpan コマンドレットが返す timespan オブジェクトや、timespan オブジェクトに変換できる文字列 ("1:05:30" など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="befbe-201">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="befbe-202">ジョブを無期限に実行するには、代わりに *RepeatIndefinitely* パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="befbe-202">To run a job indefinitely, add the *RepeatIndefinitely* parameter instead.</span></span>

<span data-ttu-id="befbe-203">ジョブトリガーの繰り返し期間の有効期限が切れる前にジョブを停止するには、Set-JobTrigger コマンドレットを使用して *RepetitionDuration* 値をゼロ (0) に設定します。</span><span class="sxs-lookup"><span data-stu-id="befbe-203">To stop a job before the job trigger repetition duration expires, use the Set-JobTrigger cmdlet to set the *RepetitionDuration* value to zero (0).</span></span>

<span data-ttu-id="befbe-204">このパラメーターは、 *Once* 、 *At* 、および *RepetitionInterval* パラメーターがコマンドで使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="befbe-204">This parameter is valid only when the *Once* , *At* and *RepetitionInterval* parameters are used in the command.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="befbe-205">-RepetitionInterval</span><span class="sxs-lookup"><span data-stu-id="befbe-205">-RepetitionInterval</span></span>
<span data-ttu-id="befbe-206">ジョブは、指定された時間間隔で繰り返し実行されます。</span><span class="sxs-lookup"><span data-stu-id="befbe-206">Repeats the job at the specified time interval.</span></span>
<span data-ttu-id="befbe-207">たとえば、このパラメーターの値が 2 時間の場合、ジョブは 2 時間おきにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="befbe-207">For example, if the value of this parameter is 2 hours, the job is triggered every two hours.</span></span>
<span data-ttu-id="befbe-208">既定値の 0 では、ジョブは繰り返し実行されません。</span><span class="sxs-lookup"><span data-stu-id="befbe-208">The default value, 0, does not repeat the job.</span></span>

<span data-ttu-id="befbe-209">New-TimeSpan コマンドレットが返す timespan オブジェクトや、timespan オブジェクトに変換できる文字列 ("1:05:30" など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="befbe-209">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="befbe-210">このパラメーターは、 *Once* 、 *At* 、および *RepetitionDuration* パラメーターがコマンドで使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="befbe-210">This parameter is valid only when the *Once* , *At* , and *RepetitionDuration* parameters are used in the command.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="befbe-211">-User</span><span class="sxs-lookup"><span data-stu-id="befbe-211">-User</span></span>
<span data-ttu-id="befbe-212">スケジュールされたジョブの *AtLogon* 開始をトリガーするユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="befbe-212">Specifies the users who trigger an *AtLogon* start of a scheduled job.</span></span>
<span data-ttu-id="befbe-213">ユーザーの名前を \<UserName\> または形式で入力 \<Domain\Username\> するか、アスタリスク () を入力して \* すべてのユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="befbe-213">Enter the name of a user in \<UserName\> or \<Domain\Username\> format or enter an asterisk (\*) to represent all users.</span></span>
<span data-ttu-id="befbe-214">既定値は、すべてのユーザーです。</span><span class="sxs-lookup"><span data-stu-id="befbe-214">The default value is all users.</span></span>

```yaml
Type: System.String
Parameter Sets: AtLogon
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="befbe-215">-毎週</span><span class="sxs-lookup"><span data-stu-id="befbe-215">-Weekly</span></span>
<span data-ttu-id="befbe-216">週単位の定期的なジョブ スケジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="befbe-216">Specifies a recurring weekly job schedule.</span></span>
<span data-ttu-id="befbe-217">Weekly パラメーター セットの他のパラメーターを使用して、スケジュールの詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="befbe-217">Use the other parameters in the Weekly parameter set to specify the schedule details.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Weekly
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="befbe-218">-WeeksInterval</span><span class="sxs-lookup"><span data-stu-id="befbe-218">-WeeksInterval</span></span>
<span data-ttu-id="befbe-219">週単位のジョブ スケジュールの実行間隔を週数で指定します。</span><span class="sxs-lookup"><span data-stu-id="befbe-219">Specifies the number of weeks between occurrences on a weekly job schedule.</span></span>
<span data-ttu-id="befbe-220">たとえば、値が 3 の場合、スケジュールされたジョブは、1 週目、4 週目、7 週目というように 3 週おきに開始されます。</span><span class="sxs-lookup"><span data-stu-id="befbe-220">For example, a value of 3 starts the scheduled job on weeks 1, 4, 7 and so on.</span></span>
<span data-ttu-id="befbe-221">既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="befbe-221">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Weekly
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="befbe-222">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="befbe-222">CommonParameters</span></span>
<span data-ttu-id="befbe-223">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="befbe-223">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="befbe-224">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="befbe-224">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="befbe-225">入力</span><span class="sxs-lookup"><span data-stu-id="befbe-225">INPUTS</span></span>

### <span data-ttu-id="befbe-226">なし</span><span class="sxs-lookup"><span data-stu-id="befbe-226">None</span></span>
<span data-ttu-id="befbe-227">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="befbe-227">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="befbe-228">出力</span><span class="sxs-lookup"><span data-stu-id="befbe-228">OUTPUTS</span></span>

### <span data-ttu-id="befbe-229">Microsoft. ScheduledJob. ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="befbe-229">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>

## <span data-ttu-id="befbe-230">注</span><span class="sxs-lookup"><span data-stu-id="befbe-230">NOTES</span></span>

* <span data-ttu-id="befbe-231">ジョブ トリガーはディスクに保存されません。</span><span class="sxs-lookup"><span data-stu-id="befbe-231">Job triggers are not saved to disk.</span></span> <span data-ttu-id="befbe-232">ただし、スケジュールされたジョブはディスクに保存されるので、Get-JobTrigger を使用して、スケジュールされたジョブのジョブトリガーを取得できます。</span><span class="sxs-lookup"><span data-stu-id="befbe-232">However, scheduled jobs are saved to disk, and you can use the Get-JobTrigger to get the job trigger of any scheduled job.</span></span>
* <span data-ttu-id="befbe-233">**新しい-JobTrigger** では、過去の日付の1回限りのトリガーなど、スケジュールされたジョブを実行しないジョブトリガーを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="befbe-233">**New-JobTrigger** does not prevent you from creating a job trigger that will not run a scheduled job, such as one-time trigger for a date in the past.</span></span>
* <span data-ttu-id="befbe-234">Register-ScheduledJob コマンドレットは、 **新しい-jobtrigger** または Get-JobTrigger コマンドレットによって返されるものや、トリガー値を含むハッシュテーブルなど、scheduledjobtrigger オブジェクトを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="befbe-234">The Register-ScheduledJob cmdlet accepts a ScheduledJobTrigger object, such as one returned by the **New-JobTrigger** or Get-JobTrigger cmdlets, or a hash table with trigger values.</span></span>

  <span data-ttu-id="befbe-235">ハッシュ テーブルを渡すには、次のキーを使用します。</span><span class="sxs-lookup"><span data-stu-id="befbe-235">To submit a hash table, use the following keys.</span></span>

  <span data-ttu-id="befbe-236">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (または任意の有効な時刻文字列)。 `DaysOfWeek="Monday", "Wednesday"` (または曜日名の任意の組み合わせ)。 `Interval=2` (または任意の有効な頻度の間隔)。 `RandomDelay="30minutes"` (または任意の有効な timespan 文字列)。 `User="Domain1\User01` (または任意の有効なユーザーです。 *Atlogon* frequency 値を指定した場合にのみ使用されます)}</span><span class="sxs-lookup"><span data-stu-id="befbe-236">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (or any valid time string); `DaysOfWeek="Monday", "Wednesday"` (or any combination of day names); `Interval=2` (or any valid frequency interval); `RandomDelay="30minutes"` (or any valid timespan string); `User="Domain1\User01` (or any valid user; used only with the *AtLogon* frequency value) }</span></span>

## <span data-ttu-id="befbe-237">関連リンク</span><span class="sxs-lookup"><span data-stu-id="befbe-237">RELATED LINKS</span></span>

[<span data-ttu-id="befbe-238">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="befbe-238">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="befbe-239">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="befbe-239">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="befbe-240">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="befbe-240">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="befbe-241">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="befbe-241">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="befbe-242">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="befbe-242">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="befbe-243">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="befbe-243">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="befbe-244">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="befbe-244">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="befbe-245">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="befbe-245">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="befbe-246">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="befbe-246">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="befbe-247">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="befbe-247">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="befbe-248">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="befbe-248">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="befbe-249">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="befbe-249">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="befbe-250">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="befbe-250">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="befbe-251">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="befbe-251">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="befbe-252">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="befbe-252">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="befbe-253">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="befbe-253">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
