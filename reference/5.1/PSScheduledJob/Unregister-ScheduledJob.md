---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/unregister-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-ScheduledJob
ms.openlocfilehash: 0c0b55513bcfdcebdcd5d8a6f17968a4a45e2839
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213371"
---
# <span data-ttu-id="c3997-103">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c3997-103">Unregister-ScheduledJob</span></span>

## <span data-ttu-id="c3997-104">概要</span><span class="sxs-lookup"><span data-stu-id="c3997-104">SYNOPSIS</span></span>
<span data-ttu-id="c3997-105">ローカル コンピューター上のスケジュールされたジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3997-105">Deletes scheduled jobs on the local computer.</span></span>

## <span data-ttu-id="c3997-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c3997-106">SYNTAX</span></span>

### <span data-ttu-id="c3997-107">定義 (既定)</span><span class="sxs-lookup"><span data-stu-id="c3997-107">Definition (Default)</span></span>

```
Unregister-ScheduledJob [-InputObject] <ScheduledJobDefinition[]> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="c3997-108">DefinitionId</span><span class="sxs-lookup"><span data-stu-id="c3997-108">DefinitionId</span></span>

```
Unregister-ScheduledJob [-Id] <Int32[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c3997-109">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="c3997-109">DefinitionName</span></span>

```
Unregister-ScheduledJob [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c3997-110">Description</span><span class="sxs-lookup"><span data-stu-id="c3997-110">DESCRIPTION</span></span>
<span data-ttu-id="c3997-111">**Unregister-ScheduledJob** コマンドレットは、ローカル コンピューターからスケジュールされたジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3997-111">The **Unregister-ScheduledJob** cmdlet deletes scheduled jobs from the local computer.</span></span>

<span data-ttu-id="c3997-112">スケジュールされたジョブを削除または登録 **解除** すると、\appdata\local\microsoft\windows\powershell\scheduledjobs ディレクトリに $home あるスケジュールされたジョブのディレクトリが削除されます。このディレクトリには、スケジュールされたジョブ、ジョブ実行履歴、およびすべてのジョブの結果を定義する XML ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c3997-112">When it deletes or unregisters a scheduled job, **Unregister-ScheduledJob** deletes the directory for the scheduled job (in the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs directory), which contains the XML file that defines the scheduled job, the job execution history, and all job results.</span></span>
<span data-ttu-id="c3997-113">この操作では、タスク スケジューラからもジョブが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c3997-113">This action also deletes the job from Task Scheduler.</span></span>

<span data-ttu-id="c3997-114">**登録解除-ScheduledJob** は、Register-ScheduledJob コマンドレットを使用して作成されたスケジュールされたジョブのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3997-114">**Unregister-ScheduledJob** deletes only the scheduled jobs that are created by using the Register-ScheduledJob cmdlet.</span></span>
<span data-ttu-id="c3997-115">タスク スケジューラで作成されたスケジュールされたジョブは削除しません。</span><span class="sxs-lookup"><span data-stu-id="c3997-115">It does not delete scheduled jobs that are created in Task Scheduler.</span></span>

<span data-ttu-id="c3997-116">ID または名前によってスケジュールされたジョブを削除するには、 **登録解除ジョブ** のパラメーターを使用します。また、スケジュールされたジョブを Get-ScheduledJob から **登録解除-scheduledjob** に渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="c3997-116">You can use the parameters of **Unregister-ScheduledJob** to delete scheduled jobs by ID or name, or pipe scheduled jobs from Get-ScheduledJob to **Unregister-ScheduledJob** .</span></span>

<span data-ttu-id="c3997-117">**登録解除-scheduledjob** は、Windows PowerShell に含まれている psscheduledjob モジュールのジョブスケジュールコマンドレットのコレクションの1つです。</span><span class="sxs-lookup"><span data-stu-id="c3997-117">**Unregister-ScheduledJob** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="c3997-118">スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3997-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="c3997-119">PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3997-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="c3997-120">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c3997-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="c3997-121">例</span><span class="sxs-lookup"><span data-stu-id="c3997-121">EXAMPLES</span></span>

### <span data-ttu-id="c3997-122">例 1: スケジュールされたジョブを削除する</span><span class="sxs-lookup"><span data-stu-id="c3997-122">Example 1: Delete a scheduled job</span></span>

```
PS C:\> Unregister-ScheduledJob TestJob
```

<span data-ttu-id="c3997-123">このコマンドは、ローカル コンピューター上のスケジュールされたジョブ TestJob を削除します。</span><span class="sxs-lookup"><span data-stu-id="c3997-123">This command deletes the TestJob scheduled job on the local computer.</span></span>

### <span data-ttu-id="c3997-124">例 2: スケジュールされたすべてのジョブを削除する</span><span class="sxs-lookup"><span data-stu-id="c3997-124">Example 2: Delete all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Unregister-ScheduledJob -Force
PS C:\> Unregister-ScheduledJob -Name "*" -Force
```

<span data-ttu-id="c3997-125">この例は、ローカルコンピューター上のスケジュールされたすべてのジョブを削除する2つの異なるコマンドを示しています。</span><span class="sxs-lookup"><span data-stu-id="c3997-125">This example shows two different commands that delete all scheduled jobs on the local computer.</span></span>

<span data-ttu-id="c3997-126">最初のコマンドは、Get-ScheduledJob コマンドレットを使用して、ローカルコンピューター上のスケジュールされたすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="c3997-126">The first command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="c3997-127">パイプライン演算子 (|) により、スケジュールされたジョブを **Unregister-ScheduleJob** に渡して、それらのジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3997-127">A pipeline operator (|) sends the scheduled jobs to **Unregister-ScheduleJob** , which deletes them.</span></span>

<span data-ttu-id="c3997-128">2 番目のコマンドは、 *Unregister-ScheduledJob* の **Name** パラメーターにすべての値 (\*) を指定して、スケジュールされたすべてのジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3997-128">The second command uses the *Name* parameter of **Unregister-ScheduledJob** with a value of all (\*) to delete all scheduled jobs.</span></span>

<span data-ttu-id="c3997-129">どちらのコマンドも *Force* パラメーターを使用しているため、ジョブのインスタンスが実行されている場合でも、スケジュールされたジョブが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c3997-129">Both commands use the *Force* parameter, which deletes a scheduled job even if an instance of the job is running.</span></span>

### <span data-ttu-id="c3997-130">例 3: リモートコンピューター上のスケジュールされたジョブを削除する</span><span class="sxs-lookup"><span data-stu-id="c3997-130">Example 3: Delete a scheduled job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName "Server01" { Unregister-ScheduledJob -Name "Test*"}
```

<span data-ttu-id="c3997-131">このコマンドは、Server01 リモートコンピューターで、名前が Test で始まるスケジュールされたジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3997-131">This command deletes scheduled jobs with names that begin with Test on the Server01 remote computer.</span></span>
<span data-ttu-id="c3997-132">このコマンドは、Invoke-Command コマンドレットを使用して、Server02 コンピューター上で **登録解除-ScheduledJob** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c3997-132">The command uses the Invoke-Command cmdlet to run the **Unregister-ScheduledJob** command on the Server02 computer.</span></span>

## <span data-ttu-id="c3997-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c3997-133">PARAMETERS</span></span>

### <span data-ttu-id="c3997-134">-Force</span><span class="sxs-lookup"><span data-stu-id="c3997-134">-Force</span></span>
<span data-ttu-id="c3997-135">ジョブのインスタンスが実行されている場合でも、スケジュールされたジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3997-135">Deletes the scheduled job even if an instance of the job is running.</span></span>
<span data-ttu-id="c3997-136">既定では、 **Unregister-ScheduledJob** は実行中のジョブを中断しません。</span><span class="sxs-lookup"><span data-stu-id="c3997-136">By default, **Unregister-ScheduledJob** does not interrupt running jobs.</span></span>

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

### <span data-ttu-id="c3997-137">-Id</span><span class="sxs-lookup"><span data-stu-id="c3997-137">-Id</span></span>
<span data-ttu-id="c3997-138">指定された識別番号 (ID) のスケジュールされたジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3997-138">Deletes the scheduled jobs with the specified identification numbers (ID).</span></span>
<span data-ttu-id="c3997-139">コンピューター上のスケジュールされたジョブの ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="c3997-139">Enter the IDs of scheduled jobs on the computer.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c3997-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c3997-140">-InputObject</span></span>
<span data-ttu-id="c3997-141">スケジュールされたジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="c3997-141">Specifies a scheduled job.</span></span>
<span data-ttu-id="c3997-142">**Scheduledjob** オブジェクトを含む変数を入力するか、Get-ScheduledJob コマンドなどの **scheduledjob** オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="c3997-142">Enter a variable that contains **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="c3997-143">また、パイプを使用して **Scheduledjob** オブジェクト **の登録を解除** することもできます。</span><span class="sxs-lookup"><span data-stu-id="c3997-143">You can also pipe **ScheduledJob** objects to **Unregister-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c3997-144">-Name</span><span class="sxs-lookup"><span data-stu-id="c3997-144">-Name</span></span>
<span data-ttu-id="c3997-145">指定された名前のスケジュールされたジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3997-145">Deletes the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="c3997-146">コンピューター上の 1 つまたは複数のスケジュールされたジョブの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c3997-146">Enter the names of one or more scheduled jobs on the computer.</span></span>
<span data-ttu-id="c3997-147">ワイルドカードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="c3997-147">Wildcards are supported.</span></span>

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

### <span data-ttu-id="c3997-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c3997-148">-Confirm</span></span>
<span data-ttu-id="c3997-149">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3997-149">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c3997-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c3997-150">-WhatIf</span></span>
<span data-ttu-id="c3997-151">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="c3997-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c3997-152">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c3997-152">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c3997-153">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3997-153">CommonParameters</span></span>
<span data-ttu-id="c3997-154">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c3997-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c3997-155">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3997-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c3997-156">入力</span><span class="sxs-lookup"><span data-stu-id="c3997-156">INPUTS</span></span>

### <span data-ttu-id="c3997-157">ScheduledJobDefinition (Microsoft PowerShell)</span><span class="sxs-lookup"><span data-stu-id="c3997-157">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="c3997-158">パイプを使用して、スケジュールされたジョブを Unregister-ScheduledJob に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="c3997-158">You can pipe scheduled jobs to Unregister-ScheduledJob</span></span>

## <span data-ttu-id="c3997-159">出力</span><span class="sxs-lookup"><span data-stu-id="c3997-159">OUTPUTS</span></span>

### <span data-ttu-id="c3997-160">なし</span><span class="sxs-lookup"><span data-stu-id="c3997-160">None</span></span>
<span data-ttu-id="c3997-161">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="c3997-161">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c3997-162">注</span><span class="sxs-lookup"><span data-stu-id="c3997-162">NOTES</span></span>

## <span data-ttu-id="c3997-163">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c3997-163">RELATED LINKS</span></span>

[<span data-ttu-id="c3997-164">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c3997-164">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="c3997-165">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c3997-165">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="c3997-166">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c3997-166">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="c3997-167">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c3997-167">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="c3997-168">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c3997-168">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="c3997-169">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c3997-169">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="c3997-170">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c3997-170">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="c3997-171">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="c3997-171">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="c3997-172">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c3997-172">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="c3997-173">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="c3997-173">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="c3997-174">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c3997-174">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="c3997-175">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c3997-175">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="c3997-176">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="c3997-176">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="c3997-177">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c3997-177">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="c3997-178">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="c3997-178">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="c3997-179">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="c3997-179">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
