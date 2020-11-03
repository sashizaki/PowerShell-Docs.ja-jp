---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-JobTrigger
ms.openlocfilehash: 8d1b12b67ccf695e1c4b948e6eeecf292c588af4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213400"
---
# <span data-ttu-id="054ea-103">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="054ea-103">Set-JobTrigger</span></span>

## <span data-ttu-id="054ea-104">概要</span><span class="sxs-lookup"><span data-stu-id="054ea-104">SYNOPSIS</span></span>
<span data-ttu-id="054ea-105">スケジュールされたジョブのジョブ トリガーを変更します。</span><span class="sxs-lookup"><span data-stu-id="054ea-105">Changes the job trigger of a scheduled job.</span></span>

## <span data-ttu-id="054ea-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="054ea-106">SYNTAX</span></span>

```
Set-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-DaysInterval <Int32>] [-WeeksInterval <Int32>]
 [-RandomDelay <TimeSpan>] [-At <DateTime>] [-User <String>] [-DaysOfWeek <DayOfWeek[]>] [-AtStartup]
 [-AtLogOn] [-Once] [-RepetitionInterval <TimeSpan>] [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely]
 [-Daily] [-Weekly] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="054ea-107">Description</span><span class="sxs-lookup"><span data-stu-id="054ea-107">DESCRIPTION</span></span>
<span data-ttu-id="054ea-108">**Set-JobTrigger** コマンドレットは、スケジュールされたジョブのジョブ トリガーのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="054ea-108">The **Set-JobTrigger** cmdlet changes the properties of the job triggers of scheduled jobs.</span></span>
<span data-ttu-id="054ea-109">このコマンドレットを使用すると、ジョブを開始する時間や頻度を変更することや、時間ベースのスケジュールから、ログオンまたは起動によってトリガーされるスケジュールに変更することができます。</span><span class="sxs-lookup"><span data-stu-id="054ea-109">You can use it to change the time or frequency at which the jobs start or to change from a time-based schedules to schedules that are triggered by a logon or startup.</span></span>

<span data-ttu-id="054ea-110">ジョブトリガーは、スケジュールされたジョブを開始するための定期的なスケジュールまたは条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="054ea-110">A job trigger defines a recurring schedule or conditions for starting a scheduled job.</span></span>
<span data-ttu-id="054ea-111">ジョブ トリガーはディスクに保存されませんが、スケジュールされたジョブのジョブ トリガーを変更することはできます。スケジュールされたジョブは、ディスクに保存されます。</span><span class="sxs-lookup"><span data-stu-id="054ea-111">Although job triggers are not saved to disk, you can change the job triggers of scheduled jobs, which are saved to disk.</span></span>

<span data-ttu-id="054ea-112">スケジュールされたジョブのジョブトリガーを変更するには、まず Get-JobTrigger コマンドレットを使用して、スケジュールされたジョブのジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="054ea-112">To change a job trigger of a scheduled job, begin by using the Get-JobTrigger cmdlet to get the job trigger of a scheduled job.</span></span>
<span data-ttu-id="054ea-113">次に、パイプを使用してトリガーを **Set-JobTrigger** に渡すか、トリガーを変数に保存し、 *Set-JobTrigger* コマンドレットの **InputObject** パラメーターを使用して、トリガーを特定します。</span><span class="sxs-lookup"><span data-stu-id="054ea-113">Then, pipe the trigger to **Set-JobTrigger** or save the trigger in a variable and use the *InputObject* parameter of **Set-JobTrigger** cmdlet to identify the trigger.</span></span>
<span data-ttu-id="054ea-114">**Set-JobTrigger** の他のパラメーターを使用して、ジョブ トリガーを変更します。</span><span class="sxs-lookup"><span data-stu-id="054ea-114">Use the remaining parameters of **Set-JobTrigger** to change the job trigger.</span></span>

<span data-ttu-id="054ea-115">ジョブトリガーの種類 (たとえば、ジョブトリガーを毎日または毎週のトリガーから *Atlogon* トリガーに変更する) を変更すると、元のトリガーのプロパティが削除されます。</span><span class="sxs-lookup"><span data-stu-id="054ea-115">When you change the type of a job trigger, such as changing a job trigger from a daily or weekly trigger to an *AtLogon* trigger, the original trigger properties are deleted.</span></span>
<span data-ttu-id="054ea-116">ただし、週単位のトリガーの曜日の変更など、トリガーの種類ではなく、値を変更した場合は、指定したプロパティのみが変更されます。</span><span class="sxs-lookup"><span data-stu-id="054ea-116">However, if you change the values of the trigger, but not its type, such as changing the days in a weekly trigger, only the properties that you specify are changed.</span></span>
<span data-ttu-id="054ea-117">元のジョブ トリガーの他のすべてのプロパティは保持されます。</span><span class="sxs-lookup"><span data-stu-id="054ea-117">All other properties of the original job trigger are retained.</span></span>

<span data-ttu-id="054ea-118">**設定-JobTrigger** は、Windows PowerShell に含まれている psscheduledjob モジュールのジョブスケジュールコマンドレットのコレクションの1つです。</span><span class="sxs-lookup"><span data-stu-id="054ea-118">**Set-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="054ea-119">スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="054ea-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="054ea-120">PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*`  ます。または about_Scheduled_Jobs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="054ea-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*`  or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="054ea-121">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="054ea-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="054ea-122">例</span><span class="sxs-lookup"><span data-stu-id="054ea-122">EXAMPLES</span></span>

### <span data-ttu-id="054ea-123">例 1: ジョブトリガーの日数を変更する</span><span class="sxs-lookup"><span data-stu-id="054ea-123">Example 1: Change the days in a job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name "DeployPackage"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Saturday}   True

The second command uses the Get-JobTrigger cmdlet to get the job trigger of the DeployPackage scheduled job. A pipeline operator (|) sends the trigger to the **Set-JobTrigger** cmdlet, which changes the job trigger so that it starts the DeployPackage job on Wednesdays and Sundays. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "DeployPackage" | Set-JobTrigger -DaysOfWeek "Wednesday", "Sunday" -Passthru
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Sunday}     True
```

<span data-ttu-id="054ea-124">この例では、週単位のジョブ トリガーの曜日を変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="054ea-124">This example shows how to change the days in a weekly job trigger.</span></span>

<span data-ttu-id="054ea-125">最初のコマンドは、Get-JobTrigger コマンドレットを使用して、スケジュールされたジョブ DeployPackage のジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="054ea-125">The first command uses the Get-JobTrigger cmdlet to get the job trigger of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="054ea-126">出力には、トリガーによって毎週水曜日と土曜日の午前 0 時にジョブが開始されることが示されています。</span><span class="sxs-lookup"><span data-stu-id="054ea-126">The output shows that the trigger starts the job at midnight on Wednesdays and Saturdays.</span></span>

<span data-ttu-id="054ea-127">このコマンドは必須ではありません。トリガーの変更の結果を表示するためにのみ含まれています。</span><span class="sxs-lookup"><span data-stu-id="054ea-127">This command is not required; it is included only to show the effect of the trigger change.</span></span>

### <span data-ttu-id="054ea-128">例 2: ジョブトリガーの種類を変更する</span><span class="sxs-lookup"><span data-stu-id="054ea-128">Example 2: Change the job trigger type</span></span>

```
PS C:\> Get-JobTrigger -Name "Inventory"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          AtStartup                                                      True

The second command uses the **Get-JobTrigger** cmdlet to get the *AtStartup* job trigger of the Inventory job. The command uses the *TriggerID* parameter to identify the job trigger. A pipeline operator (|) sends the job trigger to the **Set-JobTrigger** cmdlet, which changes it to a weekly job trigger that runs every four weeks on Monday at midnight. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "Inventory" -TriggerID 2 | Set-JobTrigger -Weekly -WeeksInterval 4 -DaysOfWeek Monday -At "12:00 AM"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          Weekly          10/31/2011 12:00:00 AM {Monday}                True
```

<span data-ttu-id="054ea-129">この例では、ジョブを開始するジョブ トリガーの種類を変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="054ea-129">This example shows how to change the type of job trigger that starts a job.</span></span>
<span data-ttu-id="054ea-130">この例のコマンドは、AtStartup ジョブ トリガーを週単位のトリガーに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="054ea-130">The commands in this example replace an AtStartup job trigger with a weekly trigger.</span></span>

<span data-ttu-id="054ea-131">最初のコマンドは、Get-JobTrigger コマンドレットを使用して、スケジュールされたインベントリジョブのジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="054ea-131">The first command uses the Get-JobTrigger cmdlet to get the job trigger of the Inventory scheduled job.</span></span>
<span data-ttu-id="054ea-132">出力には、ジョブに1日のトリガーと *Atstartup* トリガーという2つのトリガーがあることが示されています。</span><span class="sxs-lookup"><span data-stu-id="054ea-132">The output shows that the job has two triggers a daily trigger and an *AtStartup* trigger.</span></span>

<span data-ttu-id="054ea-133">このコマンドは必須ではありません。トリガーの変更の結果を表示するためにのみ含まれています。</span><span class="sxs-lookup"><span data-stu-id="054ea-133">This command is not required; it is included only to show the effect of the trigger change.</span></span>

### <span data-ttu-id="054ea-134">例 3: リモートジョブトリガーのユーザーを変更する</span><span class="sxs-lookup"><span data-stu-id="054ea-134">Example 3: Change the user on a remote job trigger</span></span>

```
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.User} | Set-JobTrigger -User "Domain01/Admin02"}
```

<span data-ttu-id="054ea-135">このコマンドは、Server01 コンピューター上のスケジュールされたジョブのすべての *Atlogon* ジョブトリガーのユーザーを変更します。</span><span class="sxs-lookup"><span data-stu-id="054ea-135">This command changes the user in all *AtLogon* job triggers of scheduled jobs on the Server01 computer.</span></span>

<span data-ttu-id="054ea-136">このコマンドは、Invoke-Command コマンドレットを使用して、Server01 コンピューター上でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="054ea-136">The command uses the Invoke-Command cmdlet to run a command on the Server01 computer.</span></span>

<span data-ttu-id="054ea-137">リモートコマンドは、コンピューター上のスケジュールされたすべてのジョブを取得する Get-ScheduledJob コマンドで開始します。</span><span class="sxs-lookup"><span data-stu-id="054ea-137">The remote command begins with a Get-ScheduledJob command that gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="054ea-138">スケジュールされたジョブは Get-JobTrigger コマンドレットにパイプ処理され、スケジュールされたジョブのジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="054ea-138">The scheduled jobs are piped to the Get-JobTrigger cmdlet, which gets the job triggers of the scheduled jobs.</span></span>
<span data-ttu-id="054ea-139">各ジョブ トリガーには、スケジュールされたジョブを含む JobDefinition プロパティが含まれています。そのため、トリガーを変更しても、スケジュールされたジョブとの関連付けは維持されます。</span><span class="sxs-lookup"><span data-stu-id="054ea-139">Each job trigger contains a JobDefinition property that contains the scheduled job, so the trigger remains associated with the scheduled job even when it is changed.</span></span>

<span data-ttu-id="054ea-140">ジョブトリガーは、パイプを使用して Where-Object コマンドレットに渡されます。このコマンドレットは、User プロパティを持つジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="054ea-140">The job triggers are piped to the Where-Object cmdlet, which gets job triggers that have the User property.</span></span>
<span data-ttu-id="054ea-141">パイプを使用して、選択されたジョブ トリガーを **Set-JobTrigger** コマンドレットに渡して、ユーザーを Domain01\Admin02 に変更します。</span><span class="sxs-lookup"><span data-stu-id="054ea-141">The selected job triggers are piped to the **Set-JobTrigger** cmdlet, which changes the user to Domain01\Admin02.</span></span>

### <span data-ttu-id="054ea-142">例 4: 多くのジョブトリガーのいずれかを変更する</span><span class="sxs-lookup"><span data-stu-id="054ea-142">Example 4: Change one of many job triggers</span></span>

```
PS C:\> Get-JobTrigger -Name "SecurityCheck"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           4/24/2013 3:00:00 AM                           True
2          Weekly          4/24/2013 4:00:00 PM   {Sunday}                True
3          Once            4/24/2013 4:00:00 PM                           True

The second command uses the **TriggerID** parameter of the **Get-JobTrigger** cmdlet to get the *Once* trigger of the SecurityCheck scheduled job. The command pipes the trigger to the Format-List cmdlet, which displays all of the properties of the *Once* job trigger.The output shows that the trigger starts the job once every hour (RepetitionInterval = 1 hour) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:00:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The third command changes the repetition interval of the job trigger from one hour to 90 minutes. The command does not return any output.
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerId 3 | Set-JobTrigger -RepetitionInterval (New-TimeSpan -Minutes 90)

The fourth command displays the effect of the change.The output shows that the trigger starts the job once every 90 minutes (RepetitionInterval = 1 hour, 30 minutes) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:30:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

<span data-ttu-id="054ea-143">この例のコマンドは、スケジュールされたジョブ SecurityCheck の *Once* ジョブ トリガーの繰り返し間隔を 60 分おきから 90 分おきに変更します。</span><span class="sxs-lookup"><span data-stu-id="054ea-143">The commands in this example changes the repetition interval of the *Once* job trigger of SecurityCheck scheduled job from every 60 minutes to every 90 minutes.</span></span>
<span data-ttu-id="054ea-144">セキュリティチェックのスケジュールされたジョブには3つのジョブトリガーがあるため、コマンドは Get-JobTrigger コマンドレットの *TriggerId* パラメーターを使用して、変更されているジョブトリガーを識別します。</span><span class="sxs-lookup"><span data-stu-id="054ea-144">The SecurityCheck scheduled job has three job triggers, so the commands use the *TriggerId* parameter of the Get-JobTrigger cmdlet to identify the job trigger that is being changed.</span></span>

<span data-ttu-id="054ea-145">最初のコマンドは、 **Get-JobTrigger** コマンドレットを使用して、スケジュールされたジョブ SecurityCheck のすべてのジョブ トリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="054ea-145">The first command uses the **Get-JobTrigger** cmdlet to get all job triggers of the SecurityCheck scheduled job.</span></span>
<span data-ttu-id="054ea-146">出力にはジョブ トリガーの ID が示されており、 *Once* ジョブ トリガーの ID が 3 であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="054ea-146">The output, which displays the IDs of the job triggers, reveals that the *Once* job trigger has an ID of 3.</span></span>

## <span data-ttu-id="054ea-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="054ea-147">PARAMETERS</span></span>

### <span data-ttu-id="054ea-148">-At</span><span class="sxs-lookup"><span data-stu-id="054ea-148">-At</span></span>
<span data-ttu-id="054ea-149">指定された日時にジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="054ea-149">Starts the job at the specified date and time.</span></span>
<span data-ttu-id="054ea-150">Get-Date コマンドレットによって返される **DateTime** オブジェクトや、時刻に変換できる文字列 ("April 19, 2012 15:00"、"12/31/2013 9:00 PM"、"3am" など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="054ea-150">Enter a **DateTime** object, such as one that the Get-Date cmdlet returns, or a string that can be converted to a time, such as "April 19, 2012 15:00", "12/31/2013 9:00 PM", or "3am".</span></span>

<span data-ttu-id="054ea-151">**DateTime** オブジェクトの要素 (秒など) を指定しない場合、ジョブトリガーのその要素は変更されません。</span><span class="sxs-lookup"><span data-stu-id="054ea-151">If you don't specify an element of the **DateTime** object, such as seconds, that element of the job trigger is not changed.</span></span>
<span data-ttu-id="054ea-152">元のジョブトリガーに **DateTime** オブジェクトが含まれておらず、要素を省略した場合は、現在の日付と時刻から対応する要素を使用してジョブトリガーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="054ea-152">If the original job trigger didn't include a **DateTime** object and you omit an element, the job trigger is created with the corresponding element from the current date and time.</span></span>

<span data-ttu-id="054ea-153">*Once* パラメーターを使用する場合は、 *At* パラメーターの値を特定の日時に設定します。</span><span class="sxs-lookup"><span data-stu-id="054ea-153">When using the *Once* parameter, set the value of the *At* parameter to a particular date and time.</span></span>
<span data-ttu-id="054ea-154">**DateTime** オブジェクトの既定値の日付は現在の日付です。そのため、日付を明示的に指定せずに、現在の時刻よりも前の時刻を指定すると、過去の時刻のジョブ トリガーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="054ea-154">Because the default date in a **DateTime** object is the current date, setting a time before the current time without an explicit date results in a job trigger for a time in the past.</span></span>

<span data-ttu-id="054ea-155">**Datetime オブジェクト** 、および **datetime** オブジェクトに変換された文字列は、コントロールパネルの [地域と言語] で選択した日付と時刻の形式と互換性があるように自動的に調整されます。</span><span class="sxs-lookup"><span data-stu-id="054ea-155">**DateTime** objects, and strings that are converted to **DateTime** objects, are automatically adjusted to be compatible with the date and time formats selected for the local computer in Region and Language in Control Panel.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="054ea-156">-AtLogOn</span><span class="sxs-lookup"><span data-stu-id="054ea-156">-AtLogOn</span></span>
<span data-ttu-id="054ea-157">指定されたユーザーがコンピューターにログオンしたときに、スケジュールされたジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="054ea-157">Starts the scheduled job when the specified users log on to the computer.</span></span>
<span data-ttu-id="054ea-158">ユーザーを指定するには、 *User* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="054ea-158">To specify a user, use the *User* parameter.</span></span>

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

### <span data-ttu-id="054ea-159">-AtStartup</span><span class="sxs-lookup"><span data-stu-id="054ea-159">-AtStartup</span></span>
<span data-ttu-id="054ea-160">Windows の起動時に、スケジュールされたジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="054ea-160">Starts the scheduled job when Windows starts.</span></span>

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

### <span data-ttu-id="054ea-161">-毎日</span><span class="sxs-lookup"><span data-stu-id="054ea-161">-Daily</span></span>
<span data-ttu-id="054ea-162">日単位の定期的なジョブ スケジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="054ea-162">Specifies a recurring daily job schedule.</span></span>
<span data-ttu-id="054ea-163">*Daily* パラメーターセットの他のパラメーターを使用して、スケジュールの詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="054ea-163">Use the other parameters in the *Daily* parameter set to specify the schedule details.</span></span>

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

### <span data-ttu-id="054ea-164">-DaysInterval</span><span class="sxs-lookup"><span data-stu-id="054ea-164">-DaysInterval</span></span>
<span data-ttu-id="054ea-165">日単位のスケジュールの実行間隔を日数で指定します。</span><span class="sxs-lookup"><span data-stu-id="054ea-165">Specifies the number of days between occurrences on a daily schedule.</span></span>
<span data-ttu-id="054ea-166">たとえば、値が 3 の場合、スケジュールされたジョブは、1 日、4 日、7 日というように 3 日おきに開始されます。</span><span class="sxs-lookup"><span data-stu-id="054ea-166">For example, a value of 3 starts the scheduled job on days 1, 4, 7 and so on.</span></span>
<span data-ttu-id="054ea-167">既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="054ea-167">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="054ea-168">-DaysOfWeek</span><span class="sxs-lookup"><span data-stu-id="054ea-168">-DaysOfWeek</span></span>
<span data-ttu-id="054ea-169">週単位でスケジュールされたジョブを実行する曜日を指定します。</span><span class="sxs-lookup"><span data-stu-id="054ea-169">Specifies the days of the week on which a weekly scheduled job runs.</span></span>
<span data-ttu-id="054ea-170">曜日を入力します。たとえば、月曜日、木曜日、整数0-6 のようになります。0は日曜日を表し、アスタリスク ( \* ) は毎日を表します。</span><span class="sxs-lookup"><span data-stu-id="054ea-170">Enter day names, such as Monday, Thursday, integers 0-6, where 0 represents Sunday, or an asterisk (\*) to represent every day.</span></span>
<span data-ttu-id="054ea-171">Weekly パラメーター セットでは、このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="054ea-171">This parameter is required in the Weekly parameter set.</span></span>

<span data-ttu-id="054ea-172">ジョブ トリガーでは、曜日名は整数値に変換されます。</span><span class="sxs-lookup"><span data-stu-id="054ea-172">Day names are converted to their integer values in the job trigger.</span></span>
<span data-ttu-id="054ea-173">コマンド内で曜日名を引用符で囲む場合は、"Monday", "Tuesday" など、各曜日名を別々に引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="054ea-173">When you enclose day names in quotation marks in a command, enclose each day name in separate quotation marks, such as "Monday", "Tuesday".</span></span>
<span data-ttu-id="054ea-174">複数の曜日名を 1 つの引用符のペアで囲んだ場合は、対応する整数値が合計されます。</span><span class="sxs-lookup"><span data-stu-id="054ea-174">If you enclose multiple day names in a single quotation mark pair, the corresponding integer values are summed.</span></span>
<span data-ttu-id="054ea-175">たとえば、"Monday, Tuesday" (1, 2) は、"Wednesday" (3) になります。</span><span class="sxs-lookup"><span data-stu-id="054ea-175">For example, "Monday, Tuesday" (1, 2) results in a value of "Wednesday" (3).</span></span>

```yaml
Type: System.DayOfWeek[]
Parameter Sets: (All)
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="054ea-176">-InputObject</span><span class="sxs-lookup"><span data-stu-id="054ea-176">-InputObject</span></span>
<span data-ttu-id="054ea-177">ジョブ トリガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="054ea-177">Specifies the job triggers.</span></span>
<span data-ttu-id="054ea-178">**Scheduledjobtrigger** オブジェクトを含む変数を入力するか、Get-JobTrigger コマンドなど、 **scheduledjobtrigger** オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="054ea-178">Enter a variable that contains **ScheduledJobTrigger** objects or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="054ea-179">また、パイプを使用して **scheduledjobtrigger** オブジェクトを **Set-jobtrigger** にパイプ処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="054ea-179">You can also pipe a **ScheduledJobTrigger** object to **Set-JobTrigger** .</span></span>

<span data-ttu-id="054ea-180">複数のジョブ トリガーを指定すると、 **Set-JobTrigger** はすべてのジョブ トリガーに同じ変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="054ea-180">If you specify multiple job triggers, **Set-JobTrigger** makes the same changes to all job triggers.</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="054ea-181">-1 回</span><span class="sxs-lookup"><span data-stu-id="054ea-181">-Once</span></span>
<span data-ttu-id="054ea-182">定期的ではない (1 回だけ) のスケジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="054ea-182">Specifies a non-recurring (one time) schedule.</span></span>

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

### <span data-ttu-id="054ea-183">-PassThru</span><span class="sxs-lookup"><span data-stu-id="054ea-183">-PassThru</span></span>
<span data-ttu-id="054ea-184">変更されたジョブ トリガーを返します。</span><span class="sxs-lookup"><span data-stu-id="054ea-184">Returns the job triggers that changed.</span></span>
<span data-ttu-id="054ea-185">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="054ea-185">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="054ea-186">-RandomDelay</span><span class="sxs-lookup"><span data-stu-id="054ea-186">-RandomDelay</span></span>
<span data-ttu-id="054ea-187">スケジュールされた開始時刻のランダムな遅延を有効にし、遅延の最大値を設定します。</span><span class="sxs-lookup"><span data-stu-id="054ea-187">Enables a random delay that begins at the scheduled start time, and sets the maximum delay value.</span></span>
<span data-ttu-id="054ea-188">遅延の長さは、開始ごとに擬似ランダムに設定され、遅延なしから、このパラメーターの値で指定された時間の間で変動します。</span><span class="sxs-lookup"><span data-stu-id="054ea-188">The length of the delay is set pseudo-randomly for each start and varies from no delay to the time specified by the value of this parameter.</span></span>
<span data-ttu-id="054ea-189">既定値のゼロ (00:00:00) では、ランダムな遅延が無効になります。</span><span class="sxs-lookup"><span data-stu-id="054ea-189">The default value, zero (00:00:00), disables the random delay.</span></span>

<span data-ttu-id="054ea-190">New-TimeSpan コマンドレットによって返されるような timespan オブジェクトを入力するか、:: format に値を入力します。この値は、 \<hours\> \<minutes\> \<seconds\> timespan オブジェクトに自動的に変換されます。</span><span class="sxs-lookup"><span data-stu-id="054ea-190">Enter a timespan object, such as one returned by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format, which is automatically converted to a timespan object.</span></span>

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

### <span data-ttu-id="054ea-191">-繰り返し (無期限)</span><span class="sxs-lookup"><span data-stu-id="054ea-191">-RepeatIndefinitely</span></span>
<span data-ttu-id="054ea-192">このパラメーターは、Windows PowerShell 4.0 以降で利用でき、 **RepetitionDuration** パラメーターの *TimeSpan.MaxValue* 値を指定することなく、スケジュールされたジョブを無期限に繰り返し実行します。</span><span class="sxs-lookup"><span data-stu-id="054ea-192">This parameter, available starting in Windows PowerShell 4.0, eliminates the necessity of specifying a **TimeSpan.MaxValue** value for the *RepetitionDuration* parameter to run a scheduled job repeatedly, for an indefinite period.</span></span>

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

### <span data-ttu-id="054ea-193">-RepetitionDuration</span><span class="sxs-lookup"><span data-stu-id="054ea-193">-RepetitionDuration</span></span>
<span data-ttu-id="054ea-194">指定された期間を過ぎるまでジョブを繰り返し実行します。</span><span class="sxs-lookup"><span data-stu-id="054ea-194">Repeats the job until the specified time expires.</span></span>
<span data-ttu-id="054ea-195">繰り返しの頻度は、 *RepetitionInterval* パラメーターの値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="054ea-195">The repetition frequency is determined by the value of the *RepetitionInterval* parameter.</span></span>
<span data-ttu-id="054ea-196">たとえば、 **RepetitionInterval** の値が 5 分で、 *RepetitionDuration* の値が 2 時間の場合、ジョブは 2 時間の間 5 分おきにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="054ea-196">For example, if the value of **RepetitionInterval** is 5 minutes and the value of *RepetitionDuration* is 2 hours, the job is triggered every five minutes for two hours.</span></span>

<span data-ttu-id="054ea-197">New-TimeSpan コマンドレットが返す timespan オブジェクトや、timespan オブジェクトに変換できる文字列 ("1:05:30" など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="054ea-197">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="054ea-198">ジョブを無期限に実行するには、代わりに *RepeatIndefinitely* パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="054ea-198">To run a job indefinitely, add the *RepeatIndefinitely* parameter instead.</span></span>

<span data-ttu-id="054ea-199">ジョブ トリガーの繰り返し期間を過ぎる前にジョブを停止するには、 **RepetitionDuration** の値をゼロ (0) に設定します。</span><span class="sxs-lookup"><span data-stu-id="054ea-199">To stop a job before the job trigger repetition duration expires, set the **RepetitionDuration** value to zero (0).</span></span>

<span data-ttu-id="054ea-200">*Once* ジョブ トリガーの繰り返し期間または繰り返し間隔を変更するには、コマンドに **RepetitionInterval** と **RepetitionDuration** の両方のパラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="054ea-200">To change the repetition duration or repetition interval of a *Once* job trigger, the command must include both the **RepetitionInterval** and **RepetitionDuration** parameters.</span></span>
<span data-ttu-id="054ea-201">他の種類のジョブ トリガーの繰り返し期間または繰り返し間隔を変更するには、コマンドに *Once* 、 *At* 、 *RepetitionInterval* 、および *RepetitionDuration* パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="054ea-201">To change the repetition duration or repetition intervals of other types of job triggers, the command must include the *Once* , *At* , *RepetitionInterval* and *RepetitionDuration* parameters.</span></span>

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

### <span data-ttu-id="054ea-202">-RepetitionInterval</span><span class="sxs-lookup"><span data-stu-id="054ea-202">-RepetitionInterval</span></span>
<span data-ttu-id="054ea-203">ジョブは、指定された時間間隔で繰り返し実行されます。</span><span class="sxs-lookup"><span data-stu-id="054ea-203">Repeats the job at the specified time interval.</span></span>
<span data-ttu-id="054ea-204">たとえば、このパラメーターの値が 2 時間の場合、ジョブは 2 時間おきにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="054ea-204">For example, if the value of this parameter is 2 hours, the job is triggered every two hours.</span></span>
<span data-ttu-id="054ea-205">既定値の 0 では、ジョブは繰り返し実行されません。</span><span class="sxs-lookup"><span data-stu-id="054ea-205">The default value, 0, does not repeat the job.</span></span>

<span data-ttu-id="054ea-206">New-TimeSpan コマンドレットが返す timespan オブジェクトや、timespan オブジェクトに変換できる文字列 ("1:05:30" など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="054ea-206">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="054ea-207">**Once** ジョブ トリガーの繰り返し期間または繰り返し間隔を変更するには、コマンドに **RepetitionInterval** と **RepetitionDuration** の両方のパラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="054ea-207">To change the repetition duration or repetition interval of a **Once** job trigger, the command must include both the **RepetitionInterval** and **RepetitionDuration** parameters.</span></span>
<span data-ttu-id="054ea-208">他の種類のジョブ トリガーの繰り返し期間または繰り返し間隔を変更するには、コマンドに **Once** 、 **At** 、 **RepetitionInterval** 、および **RepetitionDuration** パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="054ea-208">To change the repetition duration or repetition intervals of other types of job triggers, the command must include the **Once** , **At** , **RepetitionInterval** and **RepetitionDuration** parameters.</span></span>

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

### <span data-ttu-id="054ea-209">-User</span><span class="sxs-lookup"><span data-stu-id="054ea-209">-User</span></span>
<span data-ttu-id="054ea-210">スケジュールされたジョブの *AtLogon* 開始をトリガーするユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="054ea-210">Specifies the users who trigger an *AtLogon* start of a scheduled job.</span></span>
<span data-ttu-id="054ea-211">ユーザーの名前を \<UserName\> または形式で入力 \<Domain\Username\> するか、アスタリスク () を入力して \* すべてのユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="054ea-211">Enter the name of a user in \<UserName\> or \<Domain\Username\> format or enter an asterisk (\*) to represent all users.</span></span>
<span data-ttu-id="054ea-212">既定値は、すべてのユーザーです。</span><span class="sxs-lookup"><span data-stu-id="054ea-212">The default value is all users.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="054ea-213">-毎週</span><span class="sxs-lookup"><span data-stu-id="054ea-213">-Weekly</span></span>
<span data-ttu-id="054ea-214">週単位の定期的なジョブ スケジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="054ea-214">Specifies a recurring weekly job schedule.</span></span>
<span data-ttu-id="054ea-215">*週単位* のパラメーターセットの他のパラメーターを使用して、スケジュールの詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="054ea-215">Use the other parameters in the *Weekly* parameter set to specify the schedule details.</span></span>

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

### <span data-ttu-id="054ea-216">-WeeksInterval</span><span class="sxs-lookup"><span data-stu-id="054ea-216">-WeeksInterval</span></span>
<span data-ttu-id="054ea-217">週単位のジョブ スケジュールの実行間隔を週数で指定します。</span><span class="sxs-lookup"><span data-stu-id="054ea-217">Specifies the number of weeks between occurrences on a weekly job schedule.</span></span>
<span data-ttu-id="054ea-218">たとえば、値が 3 の場合、スケジュールされたジョブは、1 週目、4 週目、7 週目というように 3 週おきに開始されます。</span><span class="sxs-lookup"><span data-stu-id="054ea-218">For example, a value of 3 starts the scheduled job on weeks 1, 4, 7 and so on.</span></span>
<span data-ttu-id="054ea-219">既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="054ea-219">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="054ea-220">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="054ea-220">CommonParameters</span></span>
<span data-ttu-id="054ea-221">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="054ea-221">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="054ea-222">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="054ea-222">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="054ea-223">入力</span><span class="sxs-lookup"><span data-stu-id="054ea-223">INPUTS</span></span>

### <span data-ttu-id="054ea-224">Microsoft. ScheduledJob. ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="054ea-224">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="054ea-225">パイプを使用して複数のジョブトリガーを **設定-JobTrigger** にすることができます。</span><span class="sxs-lookup"><span data-stu-id="054ea-225">You can pipe multiple job triggers to **Set-JobTrigger** .</span></span>

## <span data-ttu-id="054ea-226">出力</span><span class="sxs-lookup"><span data-stu-id="054ea-226">OUTPUTS</span></span>

### <span data-ttu-id="054ea-227">None または Microsoft. PowerShell. ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="054ea-227">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="054ea-228">*Passthru* パラメーターを使用すると、 **Set-JobTrigger** は変更されたジョブ トリガーを返します。</span><span class="sxs-lookup"><span data-stu-id="054ea-228">When you use the *Passthru* parameter, **Set-JobTrigger** returns the job triggers that were changed.</span></span>
<span data-ttu-id="054ea-229">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="054ea-229">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="054ea-230">注</span><span class="sxs-lookup"><span data-stu-id="054ea-230">NOTES</span></span>

* <span data-ttu-id="054ea-231">ジョブ トリガーには、スケジュールされたジョブにジョブ トリガーを関連付ける JobDefintion プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="054ea-231">Job triggers have a JobDefintion property that associates them with the scheduled job.</span></span> <span data-ttu-id="054ea-232">スケジュールされたジョブのジョブ トリガーを変更すると、ジョブが変更されます。</span><span class="sxs-lookup"><span data-stu-id="054ea-232">When you change the job trigger of a scheduled job, the job is changed.</span></span> <span data-ttu-id="054ea-233">Set-ScheduledJob コマンドを使用して、変更したトリガーをスケジュールされたジョブに適用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="054ea-233">You do not need to use a Set-ScheduledJob command to apply the changed trigger to the scheduled job.</span></span>

## <span data-ttu-id="054ea-234">関連リンク</span><span class="sxs-lookup"><span data-stu-id="054ea-234">RELATED LINKS</span></span>

[<span data-ttu-id="054ea-235">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="054ea-235">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="054ea-236">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="054ea-236">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="054ea-237">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="054ea-237">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="054ea-238">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="054ea-238">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="054ea-239">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="054ea-239">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="054ea-240">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="054ea-240">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="054ea-241">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="054ea-241">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="054ea-242">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="054ea-242">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="054ea-243">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="054ea-243">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="054ea-244">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="054ea-244">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="054ea-245">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="054ea-245">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="054ea-246">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="054ea-246">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="054ea-247">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="054ea-247">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="054ea-248">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="054ea-248">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="054ea-249">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="054ea-249">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="054ea-250">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="054ea-250">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
