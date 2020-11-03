---
external help file: Microsoft.PowerShell.ScheduledJob.dll-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/add-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-JobTrigger
ms.openlocfilehash: 6066b8f91c99830fefb09a8bea13fac6ddf958e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213496"
---
# <span data-ttu-id="39f2c-103">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="39f2c-103">Add-JobTrigger</span></span>

## <span data-ttu-id="39f2c-104">概要</span><span class="sxs-lookup"><span data-stu-id="39f2c-104">SYNOPSIS</span></span>
<span data-ttu-id="39f2c-105">スケジュールされたジョブにジョブ トリガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-105">Adds job triggers to scheduled jobs.</span></span>

## <span data-ttu-id="39f2c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="39f2c-106">SYNTAX</span></span>

### <span data-ttu-id="39f2c-107">JobDefinition (既定値)</span><span class="sxs-lookup"><span data-stu-id="39f2c-107">JobDefinition (Default)</span></span>

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-InputObject] <ScheduledJobDefinition[]>
 [<CommonParameters>]
```

### <span data-ttu-id="39f2c-108">JobDefinitionId</span><span class="sxs-lookup"><span data-stu-id="39f2c-108">JobDefinitionId</span></span>

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="39f2c-109">JobDefinitionName</span><span class="sxs-lookup"><span data-stu-id="39f2c-109">JobDefinitionName</span></span>

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="39f2c-110">Description</span><span class="sxs-lookup"><span data-stu-id="39f2c-110">DESCRIPTION</span></span>
<span data-ttu-id="39f2c-111">**Add-JobTrigger** コマンドレットは、スケジュールされたジョブにジョブ トリガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-111">The **Add-JobTrigger** cmdlet adds job triggers to scheduled jobs.</span></span>
<span data-ttu-id="39f2c-112">このコマンドレットを使用すると、スケジュールされた複数のジョブに複数のトリガーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="39f2c-112">You can use it to add multiple triggers to multiple scheduled jobs.</span></span>

<span data-ttu-id="39f2c-113">ジョブトリガーは、スケジュールされたジョブを1回だけ、定期的なスケジュール、またはイベントが発生したときに開始します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-113">A job trigger starts a scheduled job on a one-time or recurring schedule or when an event occurs.</span></span>

<span data-ttu-id="39f2c-114">追加するジョブトリガーを特定するには、 **Add jobtrigger** の *Trigger* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-114">Use the *Trigger* parameter of **Add-JobTrigger** to identify the job triggers to add.</span></span>
<span data-ttu-id="39f2c-115">**Add jobtrigger** の *Name* 、 *ID* 、または *InputObject* パラメーターを使用して、トリガーが追加されるスケジュールされたジョブを特定します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-115">Use the *Name* , *ID* , or *InputObject* parameters of **Add-JobTrigger** to identify the scheduled job to which the triggers are added.</span></span>

<span data-ttu-id="39f2c-116">*Trigger* パラメーターの値に対してジョブトリガーを作成するには、New-JobTrigger コマンドレットを使用するか、またはハッシュテーブルを使用してジョブトリガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-116">To create job triggers for the value of the *Trigger* parameter, use the New-JobTrigger cmdlet or use a hash table to specify the job trigger.</span></span>

<span data-ttu-id="39f2c-117">**Add-JobTrigger** は、Windows PowerShell に含まれている **psscheduledjob** モジュールのジョブスケジュールコマンドレットのコレクションの1つです。</span><span class="sxs-lookup"><span data-stu-id="39f2c-117">**Add-JobTrigger** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="39f2c-118">スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39f2c-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="39f2c-119">PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39f2c-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="39f2c-120">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="39f2c-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="39f2c-121">例</span><span class="sxs-lookup"><span data-stu-id="39f2c-121">EXAMPLES</span></span>

### <span data-ttu-id="39f2c-122">例 1: スケジュールされたジョブにジョブトリガーを追加する</span><span class="sxs-lookup"><span data-stu-id="39f2c-122">Example 1: Add a job trigger to a scheduled job</span></span>

```
PS C:\> $Daily = New-JobTrigger -Daily -At 3AMPS
PS C:\> Add-JobTrigger -Trigger $Daily -Name "TestJob"
```

<span data-ttu-id="39f2c-123">これらのコマンドは、スケジュールされたジョブ TestJob に日単位のジョブ トリガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-123">These commands add the Daily job trigger to the TestJob scheduled job.</span></span>

<span data-ttu-id="39f2c-124">最初のコマンドは、New-JobTrigger コマンドレットを使用して、毎日午前3:00 にスケジュールされたジョブを開始するジョブトリガーを作成します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-124">The first command uses the New-JobTrigger cmdlet to create a job trigger that starts a scheduled job every day at 3:00 a.m.</span></span>
<span data-ttu-id="39f2c-125">このコマンドは、ジョブトリガーを $Daily 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-125">The command saves the job trigger in the $Daily variable.</span></span>

<span data-ttu-id="39f2c-126">2 番目のコマンドは、 **Add-JobTrigger** コマンドレットを使用して、スケジュールされたジョブ TestJob に $Startup 変数内のジョブ トリガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-126">The second command uses the **Add-JobTrigger** cmdlet to add the job trigger in the $Startup variable to the TestJob scheduled job.</span></span>

### <span data-ttu-id="39f2c-127">例 2: 複数のスケジュールされたジョブにジョブトリガーを追加する</span><span class="sxs-lookup"><span data-stu-id="39f2c-127">Example 2: Add a job trigger to several scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Add-JobTrigger -Trigger (New-JobTrigger -AtStartup)
```

<span data-ttu-id="39f2c-128">このコマンドは、ローカル コンピューター上のスケジュールされたすべてのジョブに AtStartup ジョブ トリガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-128">This command adds an AtStartup job trigger to all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="39f2c-129">Get-ScheduledJob を使用して、コンピューター上のスケジュールされたすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-129">It uses the Get-ScheduledJob to get all of the scheduled jobs on the computer.</span></span>
<span data-ttu-id="39f2c-130">パイプライン演算子 (|) により、ジョブを **Add-JobTrigger** コマンドレットに渡して、スケジュールされた各ジョブにジョブ トリガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-130">It uses a pipeline operator (|) to send the jobs to the **Add-JobTrigger** cmdlet, which adds the job trigger to each of the scheduled jobs.</span></span>
<span data-ttu-id="39f2c-131">*Trigger* パラメーターの値は、atstartup ジョブトリガーを作成する New-JobTrigger コマンドです。</span><span class="sxs-lookup"><span data-stu-id="39f2c-131">The value of the *Trigger* parameter is a New-JobTrigger command that creates the AtStartup job trigger.</span></span>

### <span data-ttu-id="39f2c-132">例 3: ジョブトリガーをコピーする</span><span class="sxs-lookup"><span data-stu-id="39f2c-132">Example 3: Copy a job trigger</span></span>

```
PS C:\> $T = Get-JobTrigger -Name "BackupArchives"
PS C:\> Add-JobTrigger -Name "TestBackup,BackupLogs" -Trigger $T
```

<span data-ttu-id="39f2c-133">これらのコマンドは、スケジュールされたジョブ BackupArchives のジョブ トリガーをコピーして、スケジュールされたジョブ TestBackup と BackupLogs に追加します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-133">These commands copy the job trigger from the BackupArchives scheduled job and add it to the TestBackup and BackupLogs scheduled jobs.</span></span>

<span data-ttu-id="39f2c-134">最初のコマンドは、Get-JobTrigger コマンドレットを使用して、スケジュールされたジョブ BackupArchives のジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-134">The first command uses the Get-JobTrigger cmdlet to get the job trigger of the BackupArchives scheduled job.</span></span>
<span data-ttu-id="39f2c-135">このコマンドは、トリガーを $t 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-135">The command saves the trigger in the $t variable.</span></span>

<span data-ttu-id="39f2c-136">2 番目のコマンドは、 **Add-JobTrigger** コマンドレットを使用して、スケジュールされたジョブ TestBackup と BackupLogs に $t 内のジョブ トリガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-136">The second command uses the **Add-JobTrigger** cmdlet to add the job trigger in $t to the TestBackup and BackupLogs scheduled jobs.</span></span>

## <span data-ttu-id="39f2c-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="39f2c-137">PARAMETERS</span></span>

### <span data-ttu-id="39f2c-138">-Id</span><span class="sxs-lookup"><span data-stu-id="39f2c-138">-Id</span></span>
<span data-ttu-id="39f2c-139">スケジュールされたジョブの識別番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-139">Specifies the identification numbers of the scheduled jobs.</span></span>
<span data-ttu-id="39f2c-140">**Add-JobTrigger** は、指定されたスケジュールされたジョブにジョブ トリガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-140">**Add-JobTrigger** adds the job trigger to the specified scheduled jobs.</span></span>

<span data-ttu-id="39f2c-141">ローカルコンピューターまたはリモートコンピューター上のスケジュールされたジョブの識別番号を取得するには、Get-ScheduledJob コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-141">To get the identification number of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39f2c-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="39f2c-142">-InputObject</span></span>
<span data-ttu-id="39f2c-143">スケジュールされたジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-143">Specifies the scheduled jobs.</span></span>
<span data-ttu-id="39f2c-144">**Scheduledjob** オブジェクトを含む変数を入力するか、Get-ScheduledJob コマンドなどの **scheduledjob** オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-144">Enter a variable that contains **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="39f2c-145">また、パイプを使用して **Scheduledjob** オブジェクトを追加して **、Jobtrigger を追加** することもできます。</span><span class="sxs-lookup"><span data-stu-id="39f2c-145">You can also pipe **ScheduledJob** objects to **Add-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="39f2c-146">-Name</span><span class="sxs-lookup"><span data-stu-id="39f2c-146">-Name</span></span>
<span data-ttu-id="39f2c-147">スケジュールされたジョブの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-147">Specifies the names of the scheduled jobs.</span></span>
<span data-ttu-id="39f2c-148">**Add-JobTrigger** は、指定されたスケジュールされたジョブにジョブ トリガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-148">**Add-JobTrigger** adds the job triggers to the specified scheduled jobs.</span></span>
<span data-ttu-id="39f2c-149">ワイルドカードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="39f2c-149">Wildcards are supported.</span></span>

<span data-ttu-id="39f2c-150">ローカルコンピューターまたはリモートコンピューター上のスケジュールされたジョブの名前を取得するには、Get-ScheduledJob コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-150">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="39f2c-151">-トリガー</span><span class="sxs-lookup"><span data-stu-id="39f2c-151">-Trigger</span></span>
<span data-ttu-id="39f2c-152">追加するジョブトリガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-152">Specifies the job triggers to add.</span></span>
<span data-ttu-id="39f2c-153">ジョブトリガーまたは **Scheduledjobtrigger** オブジェクトを含む変数を指定するハッシュテーブルを入力するか、Get-JobTrigger コマンドなど、 **scheduledjobtrigger** オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="39f2c-153">Enter a hash table that specifies job triggers or a variable that contains **ScheduledJobTrigger** objects, or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="39f2c-154">また、パイプを使用して **scheduledjobtrigger** オブジェクトを **追加** することもできます。</span><span class="sxs-lookup"><span data-stu-id="39f2c-154">You can also pipe **ScheduledJobTrigger** objects to **Add-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="39f2c-155">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="39f2c-155">CommonParameters</span></span>
<span data-ttu-id="39f2c-156">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="39f2c-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="39f2c-157">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39f2c-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="39f2c-158">入力</span><span class="sxs-lookup"><span data-stu-id="39f2c-158">INPUTS</span></span>

### <span data-ttu-id="39f2c-159">ScheduledJobDefinition の場合は、microsoft... ScheduledJobTrigger です。</span><span class="sxs-lookup"><span data-stu-id="39f2c-159">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger, Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="39f2c-160">パイプを使用して、ジョブ トリガーまたはスケジュールされたジョブを **Add-JobTrigger** に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="39f2c-160">You can pipe job triggers or scheduled jobs to **Add-JobTrigger** .</span></span>

## <span data-ttu-id="39f2c-161">出力</span><span class="sxs-lookup"><span data-stu-id="39f2c-161">OUTPUTS</span></span>

### <span data-ttu-id="39f2c-162">なし</span><span class="sxs-lookup"><span data-stu-id="39f2c-162">None</span></span>
<span data-ttu-id="39f2c-163">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="39f2c-163">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="39f2c-164">注</span><span class="sxs-lookup"><span data-stu-id="39f2c-164">NOTES</span></span>

## <span data-ttu-id="39f2c-165">関連リンク</span><span class="sxs-lookup"><span data-stu-id="39f2c-165">RELATED LINKS</span></span>

[<span data-ttu-id="39f2c-166">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="39f2c-166">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="39f2c-167">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="39f2c-167">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="39f2c-168">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="39f2c-168">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="39f2c-169">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="39f2c-169">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="39f2c-170">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="39f2c-170">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="39f2c-171">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="39f2c-171">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="39f2c-172">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="39f2c-172">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="39f2c-173">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="39f2c-173">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="39f2c-174">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="39f2c-174">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="39f2c-175">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="39f2c-175">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="39f2c-176">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="39f2c-176">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="39f2c-177">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="39f2c-177">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="39f2c-178">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="39f2c-178">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="39f2c-179">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="39f2c-179">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="39f2c-180">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="39f2c-180">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="39f2c-181">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="39f2c-181">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
