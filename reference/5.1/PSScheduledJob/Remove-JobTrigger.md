---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/remove-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-JobTrigger
ms.openlocfilehash: adcd74361b1a045a57c7db2f15996f4ea53d6d5b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213411"
---
# <span data-ttu-id="143a2-103">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="143a2-103">Remove-JobTrigger</span></span>

## <span data-ttu-id="143a2-104">概要</span><span class="sxs-lookup"><span data-stu-id="143a2-104">SYNOPSIS</span></span>
<span data-ttu-id="143a2-105">スケジュールされたジョブからジョブトリガーを削除します。</span><span class="sxs-lookup"><span data-stu-id="143a2-105">Delete job triggers from scheduled jobs.</span></span>

## <span data-ttu-id="143a2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="143a2-106">SYNTAX</span></span>

### <span data-ttu-id="143a2-107">JobDefinition (既定値)</span><span class="sxs-lookup"><span data-stu-id="143a2-107">JobDefinition (Default)</span></span>

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-InputObject] <ScheduledJobDefinition[]> [<CommonParameters>]
```

### <span data-ttu-id="143a2-108">JobDefinitionId</span><span class="sxs-lookup"><span data-stu-id="143a2-108">JobDefinitionId</span></span>

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="143a2-109">JobDefinitionName</span><span class="sxs-lookup"><span data-stu-id="143a2-109">JobDefinitionName</span></span>

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="143a2-110">Description</span><span class="sxs-lookup"><span data-stu-id="143a2-110">DESCRIPTION</span></span>
<span data-ttu-id="143a2-111">Delete **JobTrigger** コマンドレットは、スケジュールされたジョブからジョブトリガーを削除します。</span><span class="sxs-lookup"><span data-stu-id="143a2-111">The **Remove-JobTrigger** cmdlet deletes job triggers from scheduled jobs.</span></span>

<span data-ttu-id="143a2-112">ジョブトリガーは、スケジュールされたジョブを開始するための定期的なスケジュールまたは条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="143a2-112">A job trigger defines a recurring schedule or conditions for starting a scheduled job.</span></span>
<span data-ttu-id="143a2-113">ジョブトリガーを管理するには、New-JobTrigger、Add JobTrigger、Set JobTrigger、および Set-ScheduledJob コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="143a2-113">To manage job triggers, use the New-JobTrigger, Add-JobTrigger, Set-JobTrigger, and Set-ScheduledJob cmdlets.</span></span>

<span data-ttu-id="143a2-114">トリガーを削除するスケジュールされたジョブを特定するには、 *Remove-JobTrigger* の *Name* 、 *ID* 、または **InputObject** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="143a2-114">Use the *Name* , *ID* , or *InputObject* parameters of **Remove-JobTrigger** to identify the scheduled jobs from which the triggers are removed.</span></span>
<span data-ttu-id="143a2-115">削除するジョブトリガーを特定するには、 *TriggerID* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="143a2-115">Use the *TriggerID* parameter to identify the job triggers to delete.</span></span>
<span data-ttu-id="143a2-116">既定では、 **Remove-JobTrigger** は、スケジュールされたジョブのすべてのジョブ トリガーを削除します。</span><span class="sxs-lookup"><span data-stu-id="143a2-116">By default, **Remove-JobTrigger** deletes all job triggers of a scheduled job.</span></span>

<span data-ttu-id="143a2-117">**削除-JobTrigger** は、Windows PowerShell に含まれている psscheduledjob モジュールのジョブスケジュールコマンドレットのコレクションの1つです。</span><span class="sxs-lookup"><span data-stu-id="143a2-117">**Remove-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="143a2-118">スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="143a2-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="143a2-119">PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="143a2-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="143a2-120">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="143a2-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="143a2-121">例</span><span class="sxs-lookup"><span data-stu-id="143a2-121">EXAMPLES</span></span>

### <span data-ttu-id="143a2-122">例 1: すべてのジョブトリガーを削除する</span><span class="sxs-lookup"><span data-stu-id="143a2-122">Example 1: Delete all job triggers</span></span>

```
PS C:\> Remove-JobTrigger -Name "Test*"
```

<span data-ttu-id="143a2-123">このコマンドは、名前が Test で始まるスケジュールされたジョブからすべてのジョブトリガーを削除します。</span><span class="sxs-lookup"><span data-stu-id="143a2-123">This command deletes all job triggers from scheduled job that have names that begin with Test.</span></span>

### <span data-ttu-id="143a2-124">例 2: 選択したジョブトリガーを削除する</span><span class="sxs-lookup"><span data-stu-id="143a2-124">Example 2: Delete selected job triggers</span></span>

```
PS C:\> Remove-JobTrigger -Name "BackupArchive" -TriggerID 3
```

<span data-ttu-id="143a2-125">このコマンドは、スケジュールされたジョブ BackupArchive から 3 番目のトリガー (ID = 3) のみを削除します。</span><span class="sxs-lookup"><span data-stu-id="143a2-125">This command deletes only the third trigger (ID = 3) from the BackupArchive scheduled job.</span></span>

### <span data-ttu-id="143a2-126">例 3: すべてのスケジュールされたジョブから AtStartup ジョブトリガーを削除する</span><span class="sxs-lookup"><span data-stu-id="143a2-126">Example 3: Delete AtStartup job triggers from all scheduled jobs</span></span>

```
PS C:\> function Delete-AtStartup
{
    Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.Frequency -eq "AtStartup"} | ForEach-Object { Remove-JobTrigger -InputObject $_.JobDefinition -TriggerID $_.ID}
}
```

<span data-ttu-id="143a2-127">この関数は、ローカル コンピューター上のすべてのジョブからすべての AtStartup ジョブ トリガーを削除します。</span><span class="sxs-lookup"><span data-stu-id="143a2-127">This function deletes all AtStartup job triggers from all jobs on the local computer.</span></span>
<span data-ttu-id="143a2-128">関数を使用するには、セッションで関数を実行し、「」と入力し `Delete-AtStartup` ます。</span><span class="sxs-lookup"><span data-stu-id="143a2-128">To use the function, run the function in your session and then type `Delete-AtStartup`.</span></span>

<span data-ttu-id="143a2-129">Delete-AtStartup 関数には、1 つのコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="143a2-129">The Delete-AtStartup function contains a single command.</span></span>
<span data-ttu-id="143a2-130">このコマンドは、Get-ScheduledJob コマンドレットを使用して、ローカルコンピューター上のスケジュールされたジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="143a2-130">The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="143a2-131">パイプライン演算子 (|) によって、スケジュールされたジョブが Get-JobTrigger コマンドレットに送信されます。このコマンドレットは、スケジュールされた各ジョブからすべてのジョブトリガーを取得します。</span><span class="sxs-lookup"><span data-stu-id="143a2-131">A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all of the job triggers from each of the scheduled jobs.</span></span>
<span data-ttu-id="143a2-132">パイプライン演算子は、ジョブトリガーを Where-Object コマンドレットに送信します。このコマンドレットは、ジョブトリガーの Frequency プロパティの値が AtStartup と等しいジョブトリガーを選択します。</span><span class="sxs-lookup"><span data-stu-id="143a2-132">A pipeline operator sends the job triggers to the Where-Object cmdlet, which selects job triggers where the value of the Frequency property of the job trigger equals AtStartup.</span></span>

<span data-ttu-id="143a2-133">**Jobtrigger** オブジェクトには、トリガーされるスケジュールされたジョブを含む **JobDefinition** プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="143a2-133">**JobTrigger** objects have a **JobDefinition** property that contains the scheduled job that they trigger.</span></span>
<span data-ttu-id="143a2-134">このコマンドの残りの部分では、その便利な機能を使用しています。</span><span class="sxs-lookup"><span data-stu-id="143a2-134">The remainder of the command uses that valuable feature.</span></span>

<span data-ttu-id="143a2-135">パイプライン演算子は、AtStartup ジョブトリガーを ForEach-Object コマンドレットに送信します。このコマンドレットは、各 AtStartup トリガーで **Remove jobtrigger** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="143a2-135">A pipeline operator sends the AtStartup job triggers to the ForEach-Object cmdlet, which runs a **Remove-JobTrigger** command on each AtStartup trigger.</span></span>
<span data-ttu-id="143a2-136">*Remove-JobTrigger* の **InputObject** パラメーターの値は、ジョブ トリガーの JobDefinition プロパティに格納されているスケジュールされたジョブです。</span><span class="sxs-lookup"><span data-stu-id="143a2-136">The value of the *InputObject* parameter of **Remove-JobTrigger** is the scheduled job in the JobDefinition property of the job trigger.</span></span>
<span data-ttu-id="143a2-137">*TriggerID* パラメーターの値は、ジョブ トリガーの ID プロパティに格納されている ID です。</span><span class="sxs-lookup"><span data-stu-id="143a2-137">The value of the *TriggerID* parameter is the identifier in the ID property of the job trigger.</span></span>

### <span data-ttu-id="143a2-138">例 4: リモートのスケジュールされたジョブからジョブトリガーを削除する</span><span class="sxs-lookup"><span data-stu-id="143a2-138">Example 4: Delete a job trigger from a remote scheduled job</span></span>

```
PS C:\> Invoke-Command -ComputerName "Server01" { Remove-JobTrigger -ID 38 -TriggerID 1 }
```

<span data-ttu-id="143a2-139">このコマンドは、Server01 コンピューター上の Inventory ジョブから最初のジョブ トリガーを削除します。</span><span class="sxs-lookup"><span data-stu-id="143a2-139">This command deletes the first job trigger from the Inventory job on the Server01 computer.</span></span>

<span data-ttu-id="143a2-140">このコマンド **は、Server01 コマンドレットを** 使用して、コンピューター上で **Remove jobtrigger** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="143a2-140">The command uses the **Invoke-Command** cmdlet to run the **Remove-JobTrigger** cmdlet on the Server01 computer.</span></span>
<span data-ttu-id="143a2-141">**削除 JobTrigger** コマンドレットは、 *ID* パラメーターを使用して、スケジュールされたジョブのインベントリを識別し、 *TriggerID* パラメーターを使用して最初のトリガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="143a2-141">The **Remove-JobTrigger** cmdlet uses the *ID* parameter to identify the Inventory scheduled job and the *TriggerID* parameter to specify the first trigger.</span></span>
<span data-ttu-id="143a2-142">*ID* パラメーターは、スケジュールされた複数のジョブが同じ名前または類似した名前を持つ場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="143a2-142">The *ID* parameter is especially useful when multiple scheduled jobs have the same or similar names.</span></span>

## <span data-ttu-id="143a2-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="143a2-143">PARAMETERS</span></span>

### <span data-ttu-id="143a2-144">-Id</span><span class="sxs-lookup"><span data-stu-id="143a2-144">-Id</span></span>
<span data-ttu-id="143a2-145">スケジュールされたジョブの識別番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="143a2-145">Specifies the identification numbers of the scheduled jobs.</span></span>
<span data-ttu-id="143a2-146">**Remove-JobTrigger** は、指定されたスケジュールされたジョブからジョブ トリガーを削除します。</span><span class="sxs-lookup"><span data-stu-id="143a2-146">**Remove-JobTrigger** deletes job triggers from the specified scheduled jobs.</span></span>

<span data-ttu-id="143a2-147">ローカルコンピューターまたはリモートコンピューター上のスケジュールされたジョブの識別番号を取得するには、Get-ScheduledJob コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="143a2-147">To get the identification number of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

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

### <span data-ttu-id="143a2-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="143a2-148">-InputObject</span></span>
<span data-ttu-id="143a2-149">スケジュールされたジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="143a2-149">Specifies the scheduled jobs.</span></span>
<span data-ttu-id="143a2-150">**Scheduledjob** オブジェクトを含む変数を入力するか、Get-ScheduledJob コマンドなどの **scheduledjob** オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="143a2-150">Enter a variable that contains **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="143a2-151">また、パイプを使用して **Scheduledjob** オブジェクトを **削除し、-Jobtrigger を削除** することもできます。</span><span class="sxs-lookup"><span data-stu-id="143a2-151">You can also pipe **ScheduledJob** objects to **Remove-JobTrigger** .</span></span>

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

### <span data-ttu-id="143a2-152">-Name</span><span class="sxs-lookup"><span data-stu-id="143a2-152">-Name</span></span>
<span data-ttu-id="143a2-153">スケジュールされたジョブの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="143a2-153">Specifies the names of the scheduled jobs.</span></span>
<span data-ttu-id="143a2-154">**Remove-JobTrigger** は、指定されたスケジュールされたジョブからジョブ トリガーを削除します。</span><span class="sxs-lookup"><span data-stu-id="143a2-154">**Remove-JobTrigger** deletes the job triggers from the specified scheduled jobs.</span></span>
<span data-ttu-id="143a2-155">ワイルドカードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="143a2-155">Wildcards are supported.</span></span>

<span data-ttu-id="143a2-156">ローカルコンピューターまたはリモートコンピューター上のスケジュールされたジョブの名前を取得するには、Get-ScheduledJob コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="143a2-156">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

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

### <span data-ttu-id="143a2-157">-TriggerId</span><span class="sxs-lookup"><span data-stu-id="143a2-157">-TriggerId</span></span>
<span data-ttu-id="143a2-158">指定されたジョブ トリガーのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="143a2-158">Deletes only the specified job triggers.</span></span>
<span data-ttu-id="143a2-159">既定では、 **Remove-JobTrigger** は、スケジュールされたジョブからすべてのトリガーを削除します。</span><span class="sxs-lookup"><span data-stu-id="143a2-159">By default, **Remove-JobTrigger** deletes all triggers from the scheduled jobs.</span></span>
<span data-ttu-id="143a2-160">スケジュールされたジョブに複数のジョブ トリガーが設定されている場合に、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="143a2-160">Use this parameter when the scheduled jobs have multiple job triggers.</span></span>

<span data-ttu-id="143a2-161">スケジュールされたジョブの 1 つまたは複数のジョブ トリガーの ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="143a2-161">Enter the trigger IDs of one or more job triggers of a scheduled job.</span></span>
<span data-ttu-id="143a2-162">複数のスケジュールされたジョブを指定した場合、 **-JobTrigger を削除** すると、指定した ID を持つジョブトリガーがすべてのスケジュールされたジョブから削除されます。</span><span class="sxs-lookup"><span data-stu-id="143a2-162">If you specify multiple scheduled jobs, **Remove-JobTrigger** deletes the job trigger with the specified ID from all scheduled jobs.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="143a2-163">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="143a2-163">CommonParameters</span></span>
<span data-ttu-id="143a2-164">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="143a2-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="143a2-165">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="143a2-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="143a2-166">入力</span><span class="sxs-lookup"><span data-stu-id="143a2-166">INPUTS</span></span>

### <span data-ttu-id="143a2-167">ScheduledJobDefinition (Microsoft PowerShell)</span><span class="sxs-lookup"><span data-stu-id="143a2-167">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="143a2-168">パイプを使用して、スケジュールされたジョブを **Remove-JobTrigger** コマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="143a2-168">You can pipe scheduled jobs to the **Remove-JobTrigger** cmdlet.</span></span>

## <span data-ttu-id="143a2-169">出力</span><span class="sxs-lookup"><span data-stu-id="143a2-169">OUTPUTS</span></span>

### <span data-ttu-id="143a2-170">なし</span><span class="sxs-lookup"><span data-stu-id="143a2-170">None</span></span>
<span data-ttu-id="143a2-171">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="143a2-171">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="143a2-172">注</span><span class="sxs-lookup"><span data-stu-id="143a2-172">NOTES</span></span>

## <span data-ttu-id="143a2-173">関連リンク</span><span class="sxs-lookup"><span data-stu-id="143a2-173">RELATED LINKS</span></span>

[<span data-ttu-id="143a2-174">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="143a2-174">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="143a2-175">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="143a2-175">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="143a2-176">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="143a2-176">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="143a2-177">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="143a2-177">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="143a2-178">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="143a2-178">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="143a2-179">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="143a2-179">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="143a2-180">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="143a2-180">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="143a2-181">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="143a2-181">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="143a2-182">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="143a2-182">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="143a2-183">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="143a2-183">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="143a2-184">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="143a2-184">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="143a2-185">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="143a2-185">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="143a2-186">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="143a2-186">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="143a2-187">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="143a2-187">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="143a2-188">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="143a2-188">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="143a2-189">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="143a2-189">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
