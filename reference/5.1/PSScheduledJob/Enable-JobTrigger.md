---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-JobTrigger
ms.openlocfilehash: d08b55f4ba78af69608ac74c097fc6851164093b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213443"
---
# <span data-ttu-id="a95be-103">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="a95be-103">Enable-JobTrigger</span></span>

## <span data-ttu-id="a95be-104">概要</span><span class="sxs-lookup"><span data-stu-id="a95be-104">SYNOPSIS</span></span>
<span data-ttu-id="a95be-105">スケジュールされたジョブのジョブ トリガーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a95be-105">Enables the job triggers of scheduled jobs.</span></span>

## <span data-ttu-id="a95be-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a95be-106">SYNTAX</span></span>

```
Enable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a95be-107">Description</span><span class="sxs-lookup"><span data-stu-id="a95be-107">DESCRIPTION</span></span>
<span data-ttu-id="a95be-108">**Enable-JobTrigger** コマンドレットは、Disable-JobTrigger コマンドレットを使用して無効になったジョブなど、スケジュールされたジョブのジョブトリガーを再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="a95be-108">The **Enable-JobTrigger** cmdlet re-enables job triggers of scheduled jobs, such as those that were disabled by using the Disable-JobTrigger cmdlet.</span></span>
<span data-ttu-id="a95be-109">ジョブ トリガーを有効および再度有効にして、スケジュールされたジョブをすぐに開始することができます。Windows や Windows PowerShell を再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a95be-109">Enabled and re-enabled job triggers can start scheduled jobs immediately; there is no need to restart Windows or Windows PowerShell.</span></span>

<span data-ttu-id="a95be-110">このコマンドレットを使用するには、Get-JobTrigger コマンドレットを使用してジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="a95be-110">To use this cmdlet, use the  Get-JobTrigger cmdlet to get the job triggers.</span></span>
<span data-ttu-id="a95be-111">次に、パイプを使用してジョブトリガーを有効にし、 **-JobTrigger を有効** にするか、 *InputObject* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a95be-111">Then pipe the job triggers to **Enable-JobTrigger** or use its *InputObject* parameter.</span></span>

<span data-ttu-id="a95be-112">ジョブトリガーを有効にするには、 **jobtrigger** コマンドレットを使用して、ジョブトリガーの Enabled プロパティを $True に設定します。</span><span class="sxs-lookup"><span data-stu-id="a95be-112">To enable a job trigger, the **Enable-JobTrigger** cmdlet sets the Enabled property of the job trigger to $True.</span></span>

<span data-ttu-id="a95be-113">**Enable-scheduledjob** は、Windows PowerShell に含まれている **psscheduledjob** モジュールのジョブスケジュールコマンドレットのコレクションの1つです。</span><span class="sxs-lookup"><span data-stu-id="a95be-113">**Enable-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="a95be-114">スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a95be-114">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="a95be-115">PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a95be-115">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="a95be-116">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a95be-116">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="a95be-117">例</span><span class="sxs-lookup"><span data-stu-id="a95be-117">EXAMPLES</span></span>

### <span data-ttu-id="a95be-118">例 1: ジョブトリガーを有効にする</span><span class="sxs-lookup"><span data-stu-id="a95be-118">Example 1: Enable a job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name Backup-Archives -TriggerID 1 | Enable-JobTrigger
```

<span data-ttu-id="a95be-119">このコマンドは、ローカル コンピューター上のスケジュールされたジョブ Backup-Archives の最初のトリガー (ID=1) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a95be-119">This command enables the first trigger (ID=1) of the Backup-Archives scheduled job on the local computer.</span></span>

<span data-ttu-id="a95be-120">このコマンドは、Get-JobTrigger コマンドレットを使用して、ジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="a95be-120">The command uses the Get-JobTrigger cmdlet to get the job trigger.</span></span>
<span data-ttu-id="a95be-121">パイプライン演算子により、ジョブ トリガーを **Enable-JobTrigger** コマンドレットに渡して、有効にします。</span><span class="sxs-lookup"><span data-stu-id="a95be-121">A pipeline operator sends the job trigger to the **Enable-JobTrigger** cmdlet, which enables it.</span></span>

### <span data-ttu-id="a95be-122">例 2: すべてのジョブトリガーを有効にする</span><span class="sxs-lookup"><span data-stu-id="a95be-122">Example 2: Enable all job triggers</span></span>

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Enable-JobTrigger
```

<span data-ttu-id="a95be-123">このコマンドは、Get-ScheduledJob コマンドレットを使用して、ローカルコンピューター上のスケジュールされたジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a95be-123">The command uses the Get-ScheduledJob cmdlet to get  the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="a95be-124">パイプライン演算子 (|) は、スケジュールされたジョブを Get-JobTrigger コマンドレットに送信します。このコマンドレットは、スケジュールされたジョブのすべてのジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="a95be-124">A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs.</span></span>
<span data-ttu-id="a95be-125">もう 1 つのパイプライン演算子により、ジョブ トリガーを **Enable-JobTrigger** コマンドレットに渡して、有効にします。</span><span class="sxs-lookup"><span data-stu-id="a95be-125">Another pipeline operator sends the job triggers to the **Enable-JobTrigger** cmdlet, which enables them.</span></span>

### <span data-ttu-id="a95be-126">例 3: リモートコンピューター上のスケジュールされたジョブのジョブトリガーを有効にする</span><span class="sxs-lookup"><span data-stu-id="a95be-126">Example 3: Enable the job trigger of a scheduled job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "AtLogon"} | Enable-JobTrigger}
```

<span data-ttu-id="a95be-127">このコマンドは、Server01 リモート コンピューター上のスケジュールされたジョブ DeployPackage の AtLogon ジョブ トリガーを再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="a95be-127">This command re-enables the AtLogon job triggers on the DeployPackage scheduled job on the Server01 remote computer.</span></span>

<span data-ttu-id="a95be-128">このコマンドは、Invoke-Command コマンドレットを使用して、Server01 コンピューター上でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a95be-128">The command uses the Invoke-Command cmdlet to run the commands on the Server01 computer.</span></span>
<span data-ttu-id="a95be-129">Remote コマンドは、Get-JobTrigger コマンドレットを使用して、スケジュールされたジョブ DeployPackage のジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="a95be-129">The remote command uses the Get-JobTrigger cmdlet to get the job triggers of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="a95be-130">パイプライン演算子は、AtLogon ジョブトリガーのみを返す Where-Object コマンドレットにジョブトリガーを送信します。</span><span class="sxs-lookup"><span data-stu-id="a95be-130">A pipeline operator sends the job triggers to the Where-Object cmdlet which returns only AtLogon job triggers.</span></span>
<span data-ttu-id="a95be-131">パイプライン演算子は、AtLogon ジョブトリガーを **Enable JobTrigger** コマンドレットに送信します。これにより、これらのトリガーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="a95be-131">A pipeline operator sends the AtLogon job triggers to the **Enable-JobTrigger** cmdlet, which enables them.</span></span>

### <span data-ttu-id="a95be-132">例 4: 無効になっているジョブトリガーを表示する</span><span class="sxs-lookup"><span data-stu-id="a95be-132">Example 4: Display disabled job triggers</span></span>

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | where {!$_.Enabled} | Format-Table Id, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}}
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
 1    Weekly 9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
 2    Daily  9/29/2011 1:00:00 AM              False   Backup-Archive
 1    Weekly 10/20/2011 11:00:00 PM {Friday}   False   Inventory
 1    Weekly 11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

<span data-ttu-id="a95be-133">このコマンドは、スケジュールされたすべてのジョブの無効になっているすべてのジョブ トリガーを表形式で表示します。</span><span class="sxs-lookup"><span data-stu-id="a95be-133">This command displays all disabled job triggers of all scheduled jobs in a table.</span></span>
<span data-ttu-id="a95be-134">このようなコマンドを使用して、有効にする必要があるジョブ トリガーを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="a95be-134">You can use a command like this one to discover job triggers that might need to be enabled.</span></span>

<span data-ttu-id="a95be-135">このコマンドは、Get-ScheduledJob コマンドレットを使用して、ローカルコンピューター上のスケジュールされたジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a95be-135">The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="a95be-136">パイプライン演算子 (|) は、スケジュールされたジョブを Get-JobTrigger コマンドレットに送信します。このコマンドレットは、スケジュールされたジョブのすべてのジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="a95be-136">A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs.</span></span>
<span data-ttu-id="a95be-137">もう1つのパイプライン演算子によって Where-Object コマンドレットにジョブトリガーが送信されます。このコマンドレットは、ジョブトリガーの Enabled プロパティの値が (!) true ではない、無効になっているジョブトリガーのみを返します。</span><span class="sxs-lookup"><span data-stu-id="a95be-137">Another pipeline operator sends the job triggers to the Where-Object cmdlet, which returns only job triggers that are disabled, that is, where the value of the Enabled property of the job trigger is not (!) true.</span></span>

<span data-ttu-id="a95be-138">もう1つのパイプライン演算子は、無効になっているジョブトリガーを Format-Table コマンドレットに送信します。このコマンドレットには、テーブル内のジョブトリガーの選択されたプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a95be-138">Another pipeline operator sends the disabled job triggers to the Format-Table cmdlet, which displays the selected properties of the job triggers in a table.</span></span>
<span data-ttu-id="a95be-139">これらのプロパティには、ジョブ トリガーの JobDefinition プロパティのスケジュールされたジョブの名前を表示する新しい JobName プロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a95be-139">The properties include a new JobName property that displays the name of the scheduled job in the JobDefinition property of the job trigger.</span></span>

## <span data-ttu-id="a95be-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a95be-140">PARAMETERS</span></span>

### <span data-ttu-id="a95be-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a95be-141">-InputObject</span></span>
<span data-ttu-id="a95be-142">有効にするジョブトリガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="a95be-142">Specifies the job trigger to enable.</span></span>
<span data-ttu-id="a95be-143">**Scheduledjobtrigger** オブジェクトを含む変数を入力するか、Get-JobTrigger コマンドなど、 **scheduledjobtrigger** オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="a95be-143">Enter a variable that contains **ScheduledJobTrigger** objects or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="a95be-144">また、パイプを使用して **scheduledjobtrigger** オブジェクトを **有効** にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a95be-144">You can also pipe a **ScheduledJobTrigger** object to **Enable-JobTrigger** .</span></span>

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

### <span data-ttu-id="a95be-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a95be-145">-PassThru</span></span>
<span data-ttu-id="a95be-146">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a95be-146">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="a95be-147">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="a95be-147">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="a95be-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a95be-148">-Confirm</span></span>
<span data-ttu-id="a95be-149">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a95be-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a95be-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a95be-150">-WhatIf</span></span>
<span data-ttu-id="a95be-151">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="a95be-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a95be-152">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a95be-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a95be-153">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a95be-153">CommonParameters</span></span>
<span data-ttu-id="a95be-154">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a95be-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a95be-155">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a95be-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a95be-156">入力</span><span class="sxs-lookup"><span data-stu-id="a95be-156">INPUTS</span></span>

### <span data-ttu-id="a95be-157">Microsoft. ScheduledJob. ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="a95be-157">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="a95be-158">パイプを使用してジョブトリガーを **有効** にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a95be-158">You can pipe job triggers to **Enable-JobTrigger** .</span></span>

## <span data-ttu-id="a95be-159">出力</span><span class="sxs-lookup"><span data-stu-id="a95be-159">OUTPUTS</span></span>

### <span data-ttu-id="a95be-160">なし</span><span class="sxs-lookup"><span data-stu-id="a95be-160">None</span></span>
<span data-ttu-id="a95be-161">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="a95be-161">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a95be-162">注</span><span class="sxs-lookup"><span data-stu-id="a95be-162">NOTES</span></span>

* <span data-ttu-id="a95be-163">**Enable-JobTrigger** は、既に有効になっているジョブトリガーを有効にすると、エラーまたは警告を生成しません。</span><span class="sxs-lookup"><span data-stu-id="a95be-163">**Enable-JobTrigger** does not generate errors or warnings if you enable a job trigger that is already enabled.</span></span>

## <span data-ttu-id="a95be-164">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a95be-164">RELATED LINKS</span></span>

[<span data-ttu-id="a95be-165">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="a95be-165">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="a95be-166">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="a95be-166">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="a95be-167">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="a95be-167">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="a95be-168">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="a95be-168">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="a95be-169">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="a95be-169">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="a95be-170">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="a95be-170">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="a95be-171">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="a95be-171">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="a95be-172">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="a95be-172">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="a95be-173">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="a95be-173">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="a95be-174">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="a95be-174">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="a95be-175">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="a95be-175">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="a95be-176">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="a95be-176">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="a95be-177">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="a95be-177">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="a95be-178">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="a95be-178">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="a95be-179">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="a95be-179">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="a95be-180">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="a95be-180">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
