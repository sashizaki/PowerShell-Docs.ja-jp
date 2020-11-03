---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJob
ms.openlocfilehash: 40224432c208ee45efc20f556312fa250e9bb7a6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213435"
---
# <span data-ttu-id="1941c-103">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="1941c-103">Get-ScheduledJob</span></span>

## <span data-ttu-id="1941c-104">概要</span><span class="sxs-lookup"><span data-stu-id="1941c-104">SYNOPSIS</span></span>
<span data-ttu-id="1941c-105">ローカル コンピューター上のスケジュールされたジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="1941c-105">Gets scheduled jobs on the local computer.</span></span>

## <span data-ttu-id="1941c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1941c-106">SYNTAX</span></span>

### <span data-ttu-id="1941c-107">DefinitionId (既定値)</span><span class="sxs-lookup"><span data-stu-id="1941c-107">DefinitionId (Default)</span></span>

```
Get-ScheduledJob [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="1941c-108">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="1941c-108">DefinitionName</span></span>

```
Get-ScheduledJob [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="1941c-109">Description</span><span class="sxs-lookup"><span data-stu-id="1941c-109">DESCRIPTION</span></span>
<span data-ttu-id="1941c-110">**Get-ScheduledJob** コマンドレットは、ローカル コンピューター上のスケジュールされたジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="1941c-110">The **Get-ScheduledJob** cmdlet gets scheduled jobs on the local computer.</span></span>
<span data-ttu-id="1941c-111">**Get ScheduledJob** は、Register-ScheduledJob コマンドレットを使用して、現在のユーザーが作成したスケジュールされたジョブのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="1941c-111">**Get-ScheduledJob** gets only scheduled jobs that are created by the current user using the Register-ScheduledJob cmdlet.</span></span>

<span data-ttu-id="1941c-112">**Register-ScheduledJob** コマンドレットを使用して作成したジョブはタスク スケジューラに表示されますが、 **Get-ScheduledJob** はスケジュールされたジョブのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="1941c-112">Although jobs that are created by using the **Register-ScheduledJob** cmdlet appear in Task Scheduler, **Get-ScheduledJob** gets only scheduled jobs.</span></span>
<span data-ttu-id="1941c-113">タスク スケジューラで作成したスケジュールされたタスクは取得しません。</span><span class="sxs-lookup"><span data-stu-id="1941c-113">It does not get scheduled tasks created in Task Scheduler.</span></span>

<span data-ttu-id="1941c-114">パラメーターが指定されていない場合、 **Get-ScheduledJob** はコンピューター上のスケジュールされたすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="1941c-114">Without parameters, **Get-ScheduledJob** gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="1941c-115">**Get-ScheduledJob** のパラメーターを使用すると、スケジュールされたジョブを ID または名前で取得して確認することや、パイプを使用して他のコマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="1941c-115">You can use the parameters of **Get-ScheduledJob** to get scheduled jobs by ID or name and examine them or pipe them to other cmdlets.</span></span>

<span data-ttu-id="1941c-116">**Get scheduledjob** は、Windows PowerShell に含まれている **psscheduledjob** モジュールのジョブスケジュールコマンドレットのコレクションの1つです。</span><span class="sxs-lookup"><span data-stu-id="1941c-116">**Get-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="1941c-117">スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1941c-117">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="1941c-118">PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1941c-118">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="1941c-119">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1941c-119">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="1941c-120">例</span><span class="sxs-lookup"><span data-stu-id="1941c-120">EXAMPLES</span></span>

### <span data-ttu-id="1941c-121">例 1: スケジュールされたすべてのジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="1941c-121">Example 1: Get all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob
```

<span data-ttu-id="1941c-122">このコマンドは、ローカル コンピューター上のスケジュールされたすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="1941c-122">This command gets all scheduled jobs on the local computer.</span></span>

### <span data-ttu-id="1941c-123">例 2: 名前を指定してスケジュールされたジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="1941c-123">Example 2: Get scheduled jobs by name</span></span>

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive*
```

<span data-ttu-id="1941c-124">このコマンドは、バックアップまたはアーカイブを含む名前を持つ、コンピューター上のスケジュールされたすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="1941c-124">This command gets all scheduled jobs on the computer that have names that include Backup or Archive.</span></span>
<span data-ttu-id="1941c-125">このコマンドの形式を使用して、特定のジョブを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="1941c-125">This command format lets you search for particular jobs.</span></span>

### <span data-ttu-id="1941c-126">例 3: リモートコンピューター上のスケジュールされたジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="1941c-126">Example 3: Get scheduled jobs on remote computers</span></span>

```
PS C:\> Invoke-Command -ComputerName (Get-Content Servers.txt) {Get-ScheduledJob}
```

<span data-ttu-id="1941c-127">このコマンドは、Servers.txt ファイルに記載されているコンピューター上のスケジュールされたすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="1941c-127">This command gets all scheduled jobs on the computers that are listed in the Servers.txt file.</span></span>
<span data-ttu-id="1941c-128">このコマンドは、Invoke-Command コマンドレットを使用して、各コンピューターで **Get ScheduleJob** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1941c-128">The command uses the Invoke-Command cmdlet to run a **Get-ScheduleJob** command on each computer.</span></span>

### <span data-ttu-id="1941c-129">例 4: パイプを使用してスケジュールされたジョブを他のコマンドレットに設定する</span><span class="sxs-lookup"><span data-stu-id="1941c-129">Example 4: Pipe scheduled jobs to other cmdlets</span></span>

```
PS C:\> Get-ScheduledJob DailyBackup, WeeklyBackup | Get-JobTrigger
```

<span data-ttu-id="1941c-130">このコマンドは、スケジュールされたジョブ DailyBackup と WeeklyBackup のジョブ トリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="1941c-130">This command gets the job triggers of the DailyBackup and WeeklyBackup scheduled jobs.</span></span>
<span data-ttu-id="1941c-131">この例では、 **Get ScheduledJob** コマンドレットを使用してスケジュールされたジョブを取得し、Get-JobTrigger コマンドレットを使用して、スケジュールされたジョブのジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="1941c-131">It uses the **Get-ScheduledJob** cmdlet to get the scheduled jobs and the Get-JobTrigger cmdlet to get the job triggers of the scheduled jobs.</span></span>

## <span data-ttu-id="1941c-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1941c-132">PARAMETERS</span></span>

### <span data-ttu-id="1941c-133">-Id</span><span class="sxs-lookup"><span data-stu-id="1941c-133">-Id</span></span>
<span data-ttu-id="1941c-134">指定された識別番号 (ID) のスケジュールされたジョブのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="1941c-134">Gets only the scheduled jobs with the specified identification number (ID).</span></span>
<span data-ttu-id="1941c-135">コンピューター上のスケジュールされたジョブの 1 つまたは複数の ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="1941c-135">Enter one or more IDs of scheduled jobs on the computer.</span></span>
<span data-ttu-id="1941c-136">既定では、 **Get-ScheduledJob** はコンピューター上のスケジュールされたすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="1941c-136">By default, **Get-ScheduledJob** gets all scheduled jobs on the computer.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1941c-137">-Name</span><span class="sxs-lookup"><span data-stu-id="1941c-137">-Name</span></span>
<span data-ttu-id="1941c-138">指定された名前のスケジュールされたジョブのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="1941c-138">Gets only the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="1941c-139">コンピューター上のスケジュールされたジョブの 1 つまたは複数の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1941c-139">Enter one or more names of scheduled jobs on the computer.</span></span>
<span data-ttu-id="1941c-140">ワイルドカードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="1941c-140">Wildcards are supported.</span></span>
<span data-ttu-id="1941c-141">既定では、 **Get-ScheduledJob** はコンピューター上のスケジュールされたすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="1941c-141">By default, **Get-ScheduledJob** gets all scheduled jobs on the computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1941c-142">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1941c-142">CommonParameters</span></span>
<span data-ttu-id="1941c-143">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="1941c-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1941c-144">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1941c-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1941c-145">入力</span><span class="sxs-lookup"><span data-stu-id="1941c-145">INPUTS</span></span>

### <span data-ttu-id="1941c-146">なし</span><span class="sxs-lookup"><span data-stu-id="1941c-146">None</span></span>
<span data-ttu-id="1941c-147">入力を **Get ScheduledJob** にパイプすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1941c-147">You cannot pipe input to **Get-ScheduledJob** .</span></span>

## <span data-ttu-id="1941c-148">出力</span><span class="sxs-lookup"><span data-stu-id="1941c-148">OUTPUTS</span></span>

### <span data-ttu-id="1941c-149">ScheduledJobDefinition (Microsoft PowerShell)</span><span class="sxs-lookup"><span data-stu-id="1941c-149">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>

## <span data-ttu-id="1941c-150">注</span><span class="sxs-lookup"><span data-stu-id="1941c-150">NOTES</span></span>

* <span data-ttu-id="1941c-151">スケジュールされた各ジョブは、ローカル コンピューターの $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs ディレクトリのサブディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="1941c-151">Each scheduled job is saved in a subdirectory of the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs directory on the local computer.</span></span> <span data-ttu-id="1941c-152">サブディレクトリには、スケジュールされたジョブの名前が付けられ、スケジュールされたジョブの XML ファイルとその実行履歴のレコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1941c-152">The subdirectory is named for the scheduled job and contains the XML file for the scheduled job and records of its execution history.</span></span> <span data-ttu-id="1941c-153">ディスク上のスケジュールされたジョブの詳細については、「about_Scheduled_Jobs_Advanced」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1941c-153">For more information about scheduled jobs on disk, see about_Scheduled_Jobs_Advanced.</span></span>
* <span data-ttu-id="1941c-154">Windows PowerShell で作成したスケジュールされたジョブは、タスク スケジューラの Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs フォルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1941c-154">Scheduled jobs that you create in Windows PowerShell appear in Task Scheduler in the Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs folder.</span></span> <span data-ttu-id="1941c-155">タスク スケジューラを使用して、スケジュールされたジョブを表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="1941c-155">You can use Task Scheduler to view and edit the scheduled job.</span></span>
* <span data-ttu-id="1941c-156">スケジュールされたジョブ コマンドレットを使用して作成したスケジュールされたジョブは、タスク スケジューラ、SchTasks.exe コマンド ライン ツール、およびタスク スケジューラ コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="1941c-156">You can use Task Scheduler, the SchTasks.exe command-line tool, and the Task Scheduler cmdlets to manage scheduled jobs that you create with the Scheduled Job cmdlets.</span></span> <span data-ttu-id="1941c-157">ただし、タスク スケジューラで作成したタスクは、スケジュールされたジョブ コマンドレットを使用して管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="1941c-157">However, you cannot use the Scheduled Job cmdlets to manage tasks that you create in Task Scheduler.</span></span>

## <span data-ttu-id="1941c-158">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1941c-158">RELATED LINKS</span></span>

[<span data-ttu-id="1941c-159">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="1941c-159">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="1941c-160">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="1941c-160">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="1941c-161">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="1941c-161">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="1941c-162">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="1941c-162">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="1941c-163">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="1941c-163">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="1941c-164">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="1941c-164">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="1941c-165">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="1941c-165">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="1941c-166">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="1941c-166">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="1941c-167">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="1941c-167">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="1941c-168">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="1941c-168">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="1941c-169">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="1941c-169">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="1941c-170">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="1941c-170">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="1941c-171">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="1941c-171">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="1941c-172">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="1941c-172">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="1941c-173">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="1941c-173">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="1941c-174">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="1941c-174">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
