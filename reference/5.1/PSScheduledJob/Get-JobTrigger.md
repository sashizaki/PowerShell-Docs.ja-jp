---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-JobTrigger
ms.openlocfilehash: 7a75a5a7e6875ed88fd31ea0f385c19f1991f8d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213440"
---
# <span data-ttu-id="56032-103">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="56032-103">Get-JobTrigger</span></span>

## <span data-ttu-id="56032-104">概要</span><span class="sxs-lookup"><span data-stu-id="56032-104">SYNOPSIS</span></span>
<span data-ttu-id="56032-105">スケジュールされたジョブのジョブ トリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="56032-105">Gets the job triggers of scheduled jobs.</span></span>

## <span data-ttu-id="56032-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="56032-106">SYNTAX</span></span>

### <span data-ttu-id="56032-107">JobDefinition (既定値)</span><span class="sxs-lookup"><span data-stu-id="56032-107">JobDefinition (Default)</span></span>

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### <span data-ttu-id="56032-108">JobDefinitionId</span><span class="sxs-lookup"><span data-stu-id="56032-108">JobDefinitionId</span></span>

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Id] <Int32> [<CommonParameters>]
```

### <span data-ttu-id="56032-109">JobDefinitionName</span><span class="sxs-lookup"><span data-stu-id="56032-109">JobDefinitionName</span></span>

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Name] <String> [<CommonParameters>]
```

## <span data-ttu-id="56032-110">Description</span><span class="sxs-lookup"><span data-stu-id="56032-110">DESCRIPTION</span></span>
<span data-ttu-id="56032-111">**Get-JobTrigger** コマンドレットは、スケジュールされたジョブのジョブ トリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="56032-111">The **Get-JobTrigger** cmdlet gets the job triggers of scheduled jobs.</span></span>
<span data-ttu-id="56032-112">このコマンドを使用すると、ジョブ トリガーを確認することや、パイプを使用してジョブ トリガーを他のコマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="56032-112">You can use this command to examine the job triggers or to pipe the job triggers to other cmdlets.</span></span>

<span data-ttu-id="56032-113">ジョブトリガーは、スケジュールされたジョブを開始するための定期的なスケジュールまたは条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="56032-113">A job trigger defines a recurring schedule or conditions for starting a scheduled job.</span></span>
<span data-ttu-id="56032-114">ジョブ トリガーは、スケジュールされたジョブの一部であり、ディスクに単独で保存されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="56032-114">Job triggers are not saved to disk independently; they are part of a scheduled job.</span></span>
<span data-ttu-id="56032-115">ジョブ トリガーを取得するには、そのトリガーによって開始されるスケジュールされたジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="56032-115">To get a job trigger, specify the scheduled job that the trigger starts.</span></span>

<span data-ttu-id="56032-116">**Get-JobTrigger** コマンドレットのパラメーターを使用して、スケジュールされたジョブを特定します。</span><span class="sxs-lookup"><span data-stu-id="56032-116">Use the parameters of the **Get-JobTrigger** cmdlet to identify the scheduled jobs.</span></span>
<span data-ttu-id="56032-117">スケジュールされたジョブは、名前または識別番号で識別できます。または、Get-ScheduledJob コマンドレットによって返されるものなどの **Scheduledjob** オブジェクトを入力するか、パイプを使用して、 **jobtrigger** に渡します。</span><span class="sxs-lookup"><span data-stu-id="56032-117">You can identify the scheduled jobs by their names or identification numbers, or by entering or piping **ScheduledJob** objects, such as those that are returned by the Get-ScheduledJob cmdlet, to **Get-JobTrigger** .</span></span>

<span data-ttu-id="56032-118">**Get-JobTrigger** は、Windows PowerShell に含まれている psscheduledjob モジュールのジョブスケジュールコマンドレットのコレクションの1つです。</span><span class="sxs-lookup"><span data-stu-id="56032-118">**Get-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="56032-119">スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="56032-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="56032-120">PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56032-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="56032-121">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="56032-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="56032-122">例</span><span class="sxs-lookup"><span data-stu-id="56032-122">EXAMPLES</span></span>

### <span data-ttu-id="56032-123">例 1: スケジュールされたジョブ名でジョブトリガーを取得する</span><span class="sxs-lookup"><span data-stu-id="56032-123">Example 1: Get a job trigger by scheduled job name</span></span>

```
PS C:\> Get-JobTrigger -Name "BackupJob"
```

<span data-ttu-id="56032-124">このコマンドは、 **Get JobTrigger** の *Name* パラメーターを使用して、スケジュールされたジョブ backupjob のジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="56032-124">The command uses the *Name* parameter of **Get-JobTrigger** to get the job triggers of the BackupJob scheduled job.</span></span>

### <span data-ttu-id="56032-125">例 2: ID を使用してジョブトリガーを取得する</span><span class="sxs-lookup"><span data-stu-id="56032-125">Example 2: Get a job trigger by ID</span></span>

```
The first command uses the Get-ScheduledJob cmdlet to display the scheduled jobs on the local computer. The display includes the IDs of the scheduled jobs.
PS C:\> Get-ScheduledJob
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProjects {1}             \\Server\Share\Archive-Projects.ps1      True
2          Backup          {1,2}           \\Server\Share\Run-Backup.ps1            True
3          Test-HelpFiles  {1}             \\Server\Share\Test-HelpFiles.ps1        True
4          TestJob         {}              \\Server\Share\Run-AllTests.ps1          True

The second command uses the **Get-JobTrigger** cmdlet to get the job trigger for the Test-HelpFiles job (ID = 3)
PS C:\> Get-JobTrigger -ID 3
```

<span data-ttu-id="56032-126">この例では、 **Get JobTrigger** の *ID* パラメーターを使用して、スケジュールされたジョブのジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="56032-126">The example uses the *ID* parameter of **Get-JobTrigger** to get the job triggers of a scheduled job.</span></span>

### <span data-ttu-id="56032-127">例 3: ジョブをパイプ処理してジョブトリガーを取得する</span><span class="sxs-lookup"><span data-stu-id="56032-127">Example 3: Get job triggers by piping a job</span></span>

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive* | Get-JobTrigger
```

<span data-ttu-id="56032-128">このコマンドは、名前に Backup または Archive を含むすべてのジョブのジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="56032-128">This command gets the job triggers of all jobs that have Backup or Archive in their names.</span></span>

### <span data-ttu-id="56032-129">例 4: リモートコンピューター上のジョブのジョブトリガーを取得する</span><span class="sxs-lookup"><span data-stu-id="56032-129">Example 4: Get the job trigger of a job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Server01 { Get-ScheduledJob Backup | Get-JobTrigger -TriggerID 2 }
```

<span data-ttu-id="56032-130">このコマンドは、リモート コンピューター上のスケジュールされたジョブの 2 つのジョブ トリガーのうちの 1 つを取得します。</span><span class="sxs-lookup"><span data-stu-id="56032-130">This command gets one of the two job triggers of a scheduled job on a remote computer.</span></span>

<span data-ttu-id="56032-131">このコマンドは、Invoke-Command コマンドレットを使用して、Server01 コンピューター上でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="56032-131">The command uses the Invoke-Command cmdlet to run a command on the Server01 computer.</span></span>
<span data-ttu-id="56032-132">Get-ScheduledJob コマンドレットを使用して、スケジュールされたバックアップジョブを取得します。このジョブは、 **Get JobTrigger** コマンドレットにパイプします。</span><span class="sxs-lookup"><span data-stu-id="56032-132">It uses the Get-ScheduledJob cmdlet to get the Backup scheduled job, which it pipes to the **Get-JobTrigger** cmdlet.</span></span>
<span data-ttu-id="56032-133">*TriggerID* パラメーターを使用して、2番目のトリガーのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="56032-133">It uses the *TriggerID* parameter to get only the second trigger.</span></span>

### <span data-ttu-id="56032-134">例 5: すべてのジョブトリガーを取得する</span><span class="sxs-lookup"><span data-stu-id="56032-134">Example 5: Get all job triggers</span></span>

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="ScheduledJob";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                    DaysOfWeek Enabled ScheduledJob
-- --------- --                    ---------- ------- ------------
1    Weekly  9/28/2011 3:00:00 AM  {Monday}   True    Backup
1    Daily   9/27/2011 11:00:00 PM            True    Test-HelpFiles
```

<span data-ttu-id="56032-135">このコマンドは、ローカル コンピューター上のスケジュールされたすべてのジョブのすべてのジョブ トリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="56032-135">This command gets all job triggers of all scheduled jobs on the local computer.</span></span>

<span data-ttu-id="56032-136">このコマンドは、Get-ScheduledJob を使用して、ローカルコンピューター上のスケジュールされたジョブを取得し、そのジョブを **Get JobTrigger** にパイプします。このトリガーは、スケジュールされた各ジョブ (存在する場合) のジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="56032-136">The command uses the Get-ScheduledJob to get the scheduled jobs on the local computer and pipes them to **Get-JobTrigger** , which gets the job trigger of each scheduled job (if any).</span></span>

<span data-ttu-id="56032-137">スケジュールされたジョブの名前をジョブトリガーの表示に追加するには、Format-Table コマンドレットの計算されたプロパティ機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="56032-137">To add the name of the scheduled job to the job trigger display, the command uses the calculated property feature of the Format-Table cmdlet.</span></span>
<span data-ttu-id="56032-138">既定で表示されるジョブトリガーのプロパティに加えて、このコマンドは、スケジュールされたジョブの名前を表示する新しい ScheduledJob プロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="56032-138">In addition to the job trigger properties that are displayed by default, the command creates a new ScheduledJob property that displays the name of the scheduled job.</span></span>

### <span data-ttu-id="56032-139">例 6: スケジュールされたジョブのジョブトリガーのプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="56032-139">Example 6: Get the job trigger property of a scheduled job</span></span>

```
The command uses the Get-ScheduledJob cmdlet to get the Test-HelpFiles scheduled job. Then it uses the dot method (.) to get the JobTriggers property of the Test-HelpFiles scheduled job.
PS C:\> (Get-ScheduledJob Test-HelpFiles).JobTriggers

The second command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the local computer. It uses the ForEach-Object cmdlet to get the value of the JobTrigger property of each scheduled job.
PS C:\> Get-ScheduledJob | foreach {$_.JobTriggers}
```

<span data-ttu-id="56032-140">スケジュールされたジョブのジョブ トリガーは、ジョブの JobTriggers プロパティに格納されています。</span><span class="sxs-lookup"><span data-stu-id="56032-140">The job triggers of a scheduled job are stored in the JobTriggers property of the job.</span></span>
<span data-ttu-id="56032-141">この例では、 **Get JobTrigger** コマンドレットを使用してジョブトリガーを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="56032-141">This example shows alternatives to using the **Get-JobTrigger** cmdlet to get job triggers.</span></span>
<span data-ttu-id="56032-142">結果は **Get-JobTrigger** コマンドレットを使用した場合と同じです。どちらの手法を使用しても変わりはありません。</span><span class="sxs-lookup"><span data-stu-id="56032-142">The results are identical to using the **Get-JobTrigger** cmdlet and the techniques can be used interchangeably.</span></span>

### <span data-ttu-id="56032-143">例 7: ジョブトリガーを比較する</span><span class="sxs-lookup"><span data-stu-id="56032-143">Example 7: Compare job triggers</span></span>

```
The first command gets the job trigger of the ArchiveProjects scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T1 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name ArchiveProjects | Get-JobTrigger | Tee-Object -Variable T1
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The second command gets the job trigger of the Test-HelpFiles scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T2 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name "Test-HelpFiles" | Get-JobTrigger | Tee-Object -Variable T2
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The third command compares the job triggers in the $t1 and $t2 variables. It uses the Get-Member cmdlet to get the properties of the job trigger in the $t1 variable. It pipes the properties to the ForEach-Object cmdlet, which compares each property to the properties of the job trigger in the $t2 variable by name. The command then pipes the differing properties to the Format-List cmdlet, which displays them in a list.The output indicates that, although the job triggers appear to be the same, the HelpFiles job trigger includes a random delay of three (3) minutes.
PS C:\> $T1 | Get-Member -Type Property | ForEach-Object { Compare-Object $T1 $T2 -Property $_.Name}
RandomDelay                                                 SideIndicator
-----------                                                 -------------
00:00:00                                                    =>
00:03:00                                                    <=
```

<span data-ttu-id="56032-144">この例では、スケジュールされた 2 つのジョブのジョブ トリガーを比較する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="56032-144">This example shows how to compare the job triggers of two scheduled jobs.</span></span>

## <span data-ttu-id="56032-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="56032-145">PARAMETERS</span></span>

### <span data-ttu-id="56032-146">-Id</span><span class="sxs-lookup"><span data-stu-id="56032-146">-Id</span></span>
<span data-ttu-id="56032-147">スケジュールされたジョブの識別番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="56032-147">Specifies the identification number of a scheduled job.</span></span>
<span data-ttu-id="56032-148">**Get-JobTrigger** は、指定されたスケジュールされたジョブのジョブ トリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="56032-148">**Get-JobTrigger** gets the job trigger of the specified scheduled job.</span></span>

<span data-ttu-id="56032-149">ローカルコンピューターまたはリモートコンピューター上のスケジュールされたジョブの識別番号を取得するには、Get-ScheduledJob コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="56032-149">To get the identification number of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="56032-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="56032-150">-InputObject</span></span>
<span data-ttu-id="56032-151">スケジュールされたジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="56032-151">Specifies a scheduled job.</span></span>
<span data-ttu-id="56032-152">**Scheduledjob** オブジェクトを含む変数を入力するか、Get-ScheduledJob コマンドなどの **scheduledjob** オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="56032-152">Enter a variable that contains  **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="56032-153">また、 **Scheduledjob** オブジェクトを **Get jobtrigger** にパイプすることもできます。</span><span class="sxs-lookup"><span data-stu-id="56032-153">You can also pipe **ScheduledJob** objects to **Get-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="56032-154">-Name</span><span class="sxs-lookup"><span data-stu-id="56032-154">-Name</span></span>
<span data-ttu-id="56032-155">スケジュールされたジョブの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="56032-155">Specifies the name of a scheduled job.</span></span>
<span data-ttu-id="56032-156">**Get-JobTrigger** は、指定されたスケジュールされたジョブのジョブ トリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="56032-156">**Get-JobTrigger** gets the job trigger of the specified scheduled job.</span></span>
<span data-ttu-id="56032-157">ワイルドカードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="56032-157">Wildcards are supported.</span></span>

<span data-ttu-id="56032-158">ローカルコンピューターまたはリモートコンピューター上のスケジュールされたジョブの名前を取得するには、Get-ScheduledJob コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="56032-158">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="56032-159">-TriggerId</span><span class="sxs-lookup"><span data-stu-id="56032-159">-TriggerId</span></span>
<span data-ttu-id="56032-160">指定されたジョブ トリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="56032-160">Gets the specified job triggers.</span></span>
<span data-ttu-id="56032-161">スケジュールされたジョブの 1 つまたは複数のジョブ トリガーの ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="56032-161">Enter the trigger IDs of one or more job triggers of a scheduled job.</span></span>
<span data-ttu-id="56032-162">*Name* 、 *ID* 、または *InputObject* パラメーターで指定したスケジュールされたジョブに複数のジョブ トリガーが設定されている場合に、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="56032-162">Use this parameter when the scheduled job that is specified by the *Name* , *ID* , or *InputObject* parameters has multiple job triggers.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="56032-163">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="56032-163">CommonParameters</span></span>
<span data-ttu-id="56032-164">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="56032-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="56032-165">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56032-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="56032-166">入力</span><span class="sxs-lookup"><span data-stu-id="56032-166">INPUTS</span></span>

### <span data-ttu-id="56032-167">ScheduledJobDefinition (Microsoft PowerShell)</span><span class="sxs-lookup"><span data-stu-id="56032-167">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="56032-168">スケジュールされたジョブを Get-ScheduledJob から **Get JobTrigger** にパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="56032-168">You can pipe a scheduled job from Get-ScheduledJob to **Get-JobTrigger** .</span></span>

## <span data-ttu-id="56032-169">出力</span><span class="sxs-lookup"><span data-stu-id="56032-169">OUTPUTS</span></span>

### <span data-ttu-id="56032-170">Microsoft. ScheduledJob. ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="56032-170">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>

## <span data-ttu-id="56032-171">注</span><span class="sxs-lookup"><span data-stu-id="56032-171">NOTES</span></span>

## <span data-ttu-id="56032-172">関連リンク</span><span class="sxs-lookup"><span data-stu-id="56032-172">RELATED LINKS</span></span>

[<span data-ttu-id="56032-173">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="56032-173">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="56032-174">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="56032-174">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="56032-175">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="56032-175">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="56032-176">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="56032-176">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="56032-177">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="56032-177">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="56032-178">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="56032-178">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="56032-179">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="56032-179">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="56032-180">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="56032-180">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="56032-181">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="56032-181">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="56032-182">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="56032-182">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="56032-183">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="56032-183">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="56032-184">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="56032-184">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="56032-185">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="56032-185">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="56032-186">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="56032-186">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="56032-187">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="56032-187">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="56032-188">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="56032-188">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
