---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-JobTrigger
ms.openlocfilehash: 236e6b7e6e450bd1f3f868f889a19cf796890127
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213491"
---
# <span data-ttu-id="b975c-103">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b975c-103">Disable-JobTrigger</span></span>

## <span data-ttu-id="b975c-104">概要</span><span class="sxs-lookup"><span data-stu-id="b975c-104">SYNOPSIS</span></span>
<span data-ttu-id="b975c-105">スケジュールされたジョブのジョブ トリガーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b975c-105">Disables the job triggers of scheduled jobs.</span></span>

## <span data-ttu-id="b975c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b975c-106">SYNTAX</span></span>

```
Disable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b975c-107">Description</span><span class="sxs-lookup"><span data-stu-id="b975c-107">DESCRIPTION</span></span>
<span data-ttu-id="b975c-108">**Disable-JobTrigger** コマンドレットは、スケジュールされたジョブのジョブ トリガーを一時的に無効にします。</span><span class="sxs-lookup"><span data-stu-id="b975c-108">The **Disable-JobTrigger** cmdlet temporarily disables the job triggers of scheduled jobs.</span></span>
<span data-ttu-id="b975c-109">無効にしても、ジョブ トリガーのプロパティはすべて保持されますが、スケジュールされたジョブがジョブ トリガーによって開始されることはありません。</span><span class="sxs-lookup"><span data-stu-id="b975c-109">Disabling preserves all job trigger properties, but it prevents the job trigger from starting the scheduled job.</span></span>

<span data-ttu-id="b975c-110">このコマンドレットを使用するには、Get-JobTrigger コマンドレットを使用してジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="b975c-110">To use this cmdlet, use the Get-JobTrigger cmdlet to get the job triggers.</span></span>
<span data-ttu-id="b975c-111">次に、パイプを使用してジョブ トリガーを **Disable-JobTrigger** に渡すか、 *InputObject* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b975c-111">Then pipe the job triggers to **Disable-JobTrigger** or use its *InputObject* parameter.</span></span>

<span data-ttu-id="b975c-112">ジョブトリガーを無効にするには、 **jobtrigger** コマンドレットを使用して、ジョブトリガーの Enabled プロパティを $False に設定します。</span><span class="sxs-lookup"><span data-stu-id="b975c-112">To disable a job trigger, the **Disable-JobTrigger** cmdlet sets the Enabled property of the job trigger to $False.</span></span>
<span data-ttu-id="b975c-113">ジョブトリガーを再度有効にするには、Enable-JobTrigger コマンドレットを使用します。これにより、ジョブトリガーの **Enabled** プロパティが $True に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b975c-113">To re-enable the job trigger, use the Enable-JobTrigger cmdlet, which sets the **Enabled** property of the job trigger to $True.</span></span>
<span data-ttu-id="b975c-114">ジョブトリガーを無効にしても、スケジュールされたジョブ (Disable-ScheduledJob コマンドレットによって実行されるなど) は無効になりませんが、すべてのジョブトリガーを無効にすると、スケジュールされたジョブを無効にした場合と同じ結果になります。</span><span class="sxs-lookup"><span data-stu-id="b975c-114">Disabling a job trigger does not disable the scheduled job, such as is done by the Disable-ScheduledJob cmdlet, but if you disable all job triggers, the effect is the same as disabling the scheduled job.</span></span>

<span data-ttu-id="b975c-115">スケジュールされたジョブを無効にした場合、またはスケジュールされたジョブのすべてのジョブトリガーを無効にした場合でも、Start-Job コマンドレットを使用してジョブを開始したり、無効にしたスケジュールされたジョブをテンプレートとして使用したりできます。</span><span class="sxs-lookup"><span data-stu-id="b975c-115">If you disable a scheduled job or disable all job triggers of a scheduled job, you can still start the job by using the Start-Job cmdlet or use the disabled scheduled job as a template.</span></span>

<span data-ttu-id="b975c-116">**Disable-scheduledjob** は、Windows PowerShell に含まれている **psscheduledjob** モジュールのジョブスケジュールコマンドレットのコレクションの1つです。</span><span class="sxs-lookup"><span data-stu-id="b975c-116">**Disable-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="b975c-117">スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b975c-117">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="b975c-118">PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b975c-118">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="b975c-119">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b975c-119">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="b975c-120">例</span><span class="sxs-lookup"><span data-stu-id="b975c-120">EXAMPLES</span></span>

### <span data-ttu-id="b975c-121">例 1: ジョブトリガーを無効にする</span><span class="sxs-lookup"><span data-stu-id="b975c-121">Example 1: Disable a job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name "Backup-Archives" -TriggerID 1 | Disable-JobTrigger
```

<span data-ttu-id="b975c-122">このコマンドは、ローカル コンピューター上のスケジュールされたジョブ Backup-Archives の最初のトリガー (ID=1) を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b975c-122">This command disables the first trigger (ID=1) of the Backup-Archives scheduled job on the local computer.</span></span>

<span data-ttu-id="b975c-123">このコマンドは、Get-JobTrigger コマンドレットを使用して、ジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="b975c-123">The command uses the Get-JobTrigger cmdlet to get the job trigger.</span></span>
<span data-ttu-id="b975c-124">パイプライン演算子により、ジョブ トリガーを **Disable-JobTrigger** コマンドレットに渡して、無効にします。</span><span class="sxs-lookup"><span data-stu-id="b975c-124">A pipeline operator sends the job trigger to the **Disable-JobTrigger** cmdlet, which disables it.</span></span>

### <span data-ttu-id="b975c-125">例 2: すべてのジョブトリガーを無効にする</span><span class="sxs-lookup"><span data-stu-id="b975c-125">Example 2: Disable all job triggers</span></span>

```
The first command uses the Get-ScheduledJob cmdlet to get the Backup-Archives and Inventory scheduled jobs. A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs. Another pipeline operator sends the job triggers to the **Disable-JobTrigger** cmdlet, which disables them.The first command uses the **Get-ScheduledJob** cmdlet to get the jobs, because its *Name* parameter takes multiple names.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Disable-JobTrigger

The second command displays the results. The command repeats the **Get-ScheduledJob** and **Get-JobTrigger** command. A pipeline operator sends the job triggers to the Format-Table cmdlet, which displays the job triggers in a table. The **Format-Table** command adds a JobName property that displays the value of the Name property of the scheduled job in the JobDefinition property of the job trigger object.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
1  Weekly    9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
2  Daily     9/29/2011 1:00:00 AM              False   Backup-Archive
1  Weekly    10/20/2011 11:00:00 PM {Friday}   False   Inventory
1  Weekly    11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

<span data-ttu-id="b975c-126">これらのコマンドは、スケジュールされた 2 つのジョブのすべてのジョブ トリガーを無効にし、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="b975c-126">These commands disable all job triggers on two scheduled jobs and display the results.</span></span>

### <span data-ttu-id="b975c-127">例 3: リモートコンピューター上のスケジュールされたジョブのジョブトリガーを無効にする</span><span class="sxs-lookup"><span data-stu-id="b975c-127">Example 3: Disable job trigger of a scheduled job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "Daily"} | Disable-JobTrigger}
```

<span data-ttu-id="b975c-128">このコマンドは、Server01 リモート コンピューター上のスケジュールされたジョブ DeployPackage の日単位のジョブ トリガーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b975c-128">This command disables the daily job triggers on the DeployPackage scheduled job on the Server01 remote computer.</span></span>

<span data-ttu-id="b975c-129">このコマンドは、Invoke-Command コマンドレットを使用して、Server01 コンピューター上でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b975c-129">The command uses the Invoke-Command cmdlet to run the commands on the Server01 computer.</span></span>
<span data-ttu-id="b975c-130">Remote コマンドは、Get-JobTrigger コマンドレットを使用して、スケジュールされたジョブ DeployPackage のジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="b975c-130">The remote command uses the Get-JobTrigger cmdlet to get the job triggers of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="b975c-131">パイプライン演算子は、ジョブトリガーを Where-Object コマンドレットに送信します。このコマンドレットは、1日のジョブトリガーのみを返します。</span><span class="sxs-lookup"><span data-stu-id="b975c-131">A pipeline operator sends the job triggers to the Where-Object cmdlet, which returns only daily job triggers.</span></span>
<span data-ttu-id="b975c-132">パイプライン演算子は、日単位のジョブトリガーを **無効** にして、無効にします。</span><span class="sxs-lookup"><span data-stu-id="b975c-132">A pipeline operator sends the daily job triggers to the **Disable-JobTrigger** cmdlet, which disables them.</span></span>

## <span data-ttu-id="b975c-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b975c-133">PARAMETERS</span></span>

### <span data-ttu-id="b975c-134">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b975c-134">-InputObject</span></span>
<span data-ttu-id="b975c-135">無効にするジョブ トリガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="b975c-135">Specifies the job trigger to be disabled.</span></span>
<span data-ttu-id="b975c-136">**Scheduledjobtrigger** オブジェクトを含む変数を入力するか、Get-JobTrigger コマンドなど、 **scheduledjobtrigger** オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="b975c-136">Enter a variable that contains  **ScheduledJobTrigger** objects or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="b975c-137">また、パイプを使用して **scheduledjobtrigger** オブジェクトを無効にし、 **-Jobtrigger を無効** にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b975c-137">You can also pipe a **ScheduledJobTrigger** object to **Disable-JobTrigger** .</span></span>

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

### <span data-ttu-id="b975c-138">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b975c-138">-PassThru</span></span>
<span data-ttu-id="b975c-139">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="b975c-139">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="b975c-140">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="b975c-140">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b975c-141">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b975c-141">-Confirm</span></span>
<span data-ttu-id="b975c-142">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b975c-142">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b975c-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b975c-143">-WhatIf</span></span>
<span data-ttu-id="b975c-144">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="b975c-144">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b975c-145">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="b975c-145">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b975c-146">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b975c-146">CommonParameters</span></span>
<span data-ttu-id="b975c-147">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b975c-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b975c-148">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b975c-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b975c-149">入力</span><span class="sxs-lookup"><span data-stu-id="b975c-149">INPUTS</span></span>

### <span data-ttu-id="b975c-150">Microsoft. ScheduledJob. ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="b975c-150">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="b975c-151">パイプを使用してジョブ トリガーを **Disable-JobTrigger** に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="b975c-151">You can pipe job triggers to **Disable-JobTrigger** .</span></span>

## <span data-ttu-id="b975c-152">出力</span><span class="sxs-lookup"><span data-stu-id="b975c-152">OUTPUTS</span></span>

### <span data-ttu-id="b975c-153">なし</span><span class="sxs-lookup"><span data-stu-id="b975c-153">None</span></span>
<span data-ttu-id="b975c-154">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="b975c-154">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b975c-155">注</span><span class="sxs-lookup"><span data-stu-id="b975c-155">NOTES</span></span>

* <span data-ttu-id="b975c-156">**無効化-JobTrigger** は、既に無効になっているジョブトリガーを無効にした場合、エラーまたは警告を生成しません。</span><span class="sxs-lookup"><span data-stu-id="b975c-156">**Disable-JobTrigger** does not generate errors or warnings if you disable a job trigger that is already disabled.</span></span>

## <span data-ttu-id="b975c-157">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b975c-157">RELATED LINKS</span></span>

[<span data-ttu-id="b975c-158">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b975c-158">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="b975c-159">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b975c-159">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="b975c-160">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b975c-160">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="b975c-161">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b975c-161">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="b975c-162">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b975c-162">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="b975c-163">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b975c-163">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="b975c-164">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b975c-164">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="b975c-165">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="b975c-165">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="b975c-166">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b975c-166">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="b975c-167">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="b975c-167">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="b975c-168">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b975c-168">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="b975c-169">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b975c-169">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="b975c-170">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b975c-170">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="b975c-171">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b975c-171">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="b975c-172">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="b975c-172">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="b975c-173">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b975c-173">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
