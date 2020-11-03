---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ScheduledJob
ms.openlocfilehash: 757402a348a6b694d2f2aee53053a1b7615dbb53
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213448"
---
# <span data-ttu-id="fa0a0-103">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fa0a0-103">Enable-ScheduledJob</span></span>

## <span data-ttu-id="fa0a0-104">概要</span><span class="sxs-lookup"><span data-stu-id="fa0a0-104">SYNOPSIS</span></span>
<span data-ttu-id="fa0a0-105">スケジュールされたジョブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-105">Enables a scheduled job.</span></span>

## <span data-ttu-id="fa0a0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fa0a0-106">SYNTAX</span></span>

### <span data-ttu-id="fa0a0-107">定義 (既定)</span><span class="sxs-lookup"><span data-stu-id="fa0a0-107">Definition (Default)</span></span>

```
Enable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="fa0a0-108">DefinitionId</span><span class="sxs-lookup"><span data-stu-id="fa0a0-108">DefinitionId</span></span>

```
Enable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fa0a0-109">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="fa0a0-109">DefinitionName</span></span>

```
Enable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fa0a0-110">Description</span><span class="sxs-lookup"><span data-stu-id="fa0a0-110">DESCRIPTION</span></span>
<span data-ttu-id="fa0a0-111">**Enable ScheduledJob** コマンドレットは、Disable-ScheduledJob コマンドレットを使用して無効になっているジョブなど、無効になっているスケジュールされたジョブを再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-111">The **Enable-ScheduledJob** cmdlet re-enables scheduled jobs that are disabled, such as those that are disabled by using the Disable-ScheduledJob cmdlet.</span></span>
<span data-ttu-id="fa0a0-112">有効にされたジョブは、トリガーされると、自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-112">Enabled jobs run automatically when triggered.</span></span>

<span data-ttu-id="fa0a0-113">スケジュールされたジョブを有効にするには、 **enable-scheduledjob** コマンドレットを使用して、スケジュールされたジョブの Enabled プロパティを $True に設定します。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-113">To enable a scheduled job, the **Enable-ScheduledJob** cmdlet sets the Enabled property of the scheduled job to $True.</span></span>

<span data-ttu-id="fa0a0-114">**有効-scheduledjob** は、Windows PowerShell に含まれている **psscheduledjob** モジュールのジョブスケジュールコマンドレットのコレクションの1つです。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-114">**Enabled-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="fa0a0-115">スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-115">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="fa0a0-116">PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-116">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="fa0a0-117">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-117">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="fa0a0-118">例</span><span class="sxs-lookup"><span data-stu-id="fa0a0-118">EXAMPLES</span></span>

### <span data-ttu-id="fa0a0-119">例 1: スケジュールされたジョブを有効にする</span><span class="sxs-lookup"><span data-stu-id="fa0a0-119">Example 1: Enable a scheduled job</span></span>

```
PS C:\> Enable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
```

<span data-ttu-id="fa0a0-120">このコマンドは、ローカル コンピューター上の ID が 2 のスケジュールされたジョブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-120">This command enables the scheduled job with ID 2 on the local computer.</span></span>
<span data-ttu-id="fa0a0-121">出力には、コマンドの結果が示されています。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-121">The output shows the effect of the command.</span></span>

### <span data-ttu-id="fa0a0-122">例 2: すべてのスケジュールされたジョブを有効にする</span><span class="sxs-lookup"><span data-stu-id="fa0a0-122">Example 2: Enable all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Enable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        True
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     True
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       True
```

<span data-ttu-id="fa0a0-123">このコマンドは、ローカル コンピューター上のスケジュールされたすべてのジョブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-123">This command enables all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="fa0a0-124">また、Get-ScheduledJob コマンドレットを使用してスケジュールされたすべてのジョブを取得し、 **enable-scheduledjob** コマンドレットを使用してそれらを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-124">It uses the Get-ScheduledJob cmdlet to get all scheduled job and the **Enable-ScheduledJob** cmdlet to enable them.</span></span>

<span data-ttu-id="fa0a0-125">**Enable-ScheduledJob** では、既に有効になっているスケジュールされたジョブを有効にした場合、警告やエラーは生成されません。そのため、すべてのスケジュールされたジョブを条件なしで有効にできます。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-125">**Enable-ScheduledJob** does not generate warnings or errors if you enable a scheduled job that is already enabled, so you can enable all scheduled jobs without conditions.</span></span>

### <span data-ttu-id="fa0a0-126">例 3: 選択したスケジュールされたジョブを有効にする</span><span class="sxs-lookup"><span data-stu-id="fa0a0-126">Example 3: Enable selected scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where-Object {$_.RunWithoutNetwork} | ForEach-Object {Enable-ScheduledJob -InputObject $_.JobDefinition}
```

<span data-ttu-id="fa0a0-127">このコマンドは、ネットワーク接続を必要としないスケジュールされたジョブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-127">This command enables scheduled jobs that do not require a network connection.</span></span>

<span data-ttu-id="fa0a0-128">このコマンドは、Get-ScheduledJob コマンドレットを使用して、コンピューター上のスケジュールされたすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-128">The command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the computer.</span></span>
<span data-ttu-id="fa0a0-129">パイプライン演算子は、スケジュールされたジョブを Get-ScheduledJobOption コマンドレットに送信します。このコマンドレットは、スケジュールされた各ジョブのジョブオプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-129">A pipeline operator sends the scheduled jobs to the Get-ScheduledJobOption cmdlet, which gets the job options of each scheduled job.</span></span>
<span data-ttu-id="fa0a0-130">各ジョブ オプション オブジェクトには、関連付けられているスケジュールされたジョブが含まれている JobDefinition プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-130">Each job options object has a JobDefinition property that contains the associated scheduled job.</span></span>
<span data-ttu-id="fa0a0-131">JobDefinition プロパティを使用して、コマンドを完了します。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-131">The JobDefinition property is used to complete the command.</span></span>

<span data-ttu-id="fa0a0-132">このコマンドは、パイプライン演算子 (|) を使用してジョブオプションを Where-Object コマンドレットに送信します。このコマンドレットは、 **Runno network** プロパティの値が True ($true) に設定されているスケジュールされたジョブオプションオブジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-132">The command uses a pipeline operator (|) to send the job options to the Where-Object cmdlet, which selects scheduled job option objects in which the **RunWithoutNetwork** property has a value of True ($true).</span></span>
<span data-ttu-id="fa0a0-133">もう1つのパイプライン演算子は、選択したスケジュールされたジョブオプションオブジェクトを ForEach-Object コマンドレットに送信します。このコマンドレットは、各ジョブオプションオブジェクトの JobDefinition プロパティの値で、スケジュールされたジョブに対して **Enable-ScheduledJob** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-133">Another pipeline operator sends the selected scheduled job options objects to the ForEach-Object cmdlet which runs an **Enable-ScheduledJob** command on the scheduled job in the value of the JobDefinition property of each job options object.</span></span>

### <span data-ttu-id="fa0a0-134">例 4: リモートコンピューターでスケジュールされたジョブを有効にする</span><span class="sxs-lookup"><span data-stu-id="fa0a0-134">Example 4: Enable scheduled jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName "Srv01,Srv10" -ScriptBlock {Enable-ScheduledJob -Name "Inventory"}
```

<span data-ttu-id="fa0a0-135">このコマンドは、Srv01 と Srv10 の 2 台のリモート コンピューター上の名前に "test" が含まれているスケジュールされたジョブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-135">This command enables scheduled jobs that have "test" in their names on two remote computers, Srv01 and Srv10.</span></span>

<span data-ttu-id="fa0a0-136">このコマンドは、Invoke-Command コマンドレットを使用して、Srv01 コンピューターと Srv10 コンピューター上で **ScheduledJob** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-136">The command uses the Invoke-Command cmdlet to run an **Enable-ScheduledJob** command on the Srv01 and Srv10 computers.</span></span>
<span data-ttu-id="fa0a0-137">このコマンドは、 *Enable-ScheduledJob* の **Name** パラメーターを使用して、各コンピューター上のスケジュールされたジョブ Inventory を有効にします。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-137">The command uses the *Name* parameter of **Enable-ScheduledJob** to enable the Inventory scheduled job on each computer.</span></span>

## <span data-ttu-id="fa0a0-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fa0a0-138">PARAMETERS</span></span>

### <span data-ttu-id="fa0a0-139">-Id</span><span class="sxs-lookup"><span data-stu-id="fa0a0-139">-Id</span></span>
<span data-ttu-id="fa0a0-140">指定された識別番号 (ID) のスケジュールされたジョブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-140">Enables the scheduled job with the specified identification number (ID).</span></span>
<span data-ttu-id="fa0a0-141">スケジュールされたジョブの ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-141">Enter the ID of a scheduled job.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fa0a0-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fa0a0-142">-InputObject</span></span>
<span data-ttu-id="fa0a0-143">有効にするスケジュールされたジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-143">Specifies the scheduled job to enable.</span></span>
<span data-ttu-id="fa0a0-144">**ScheduledJobDefinition** オブジェクトを含む変数を入力するか、Get-ScheduledJob コマンドなどの **ScheduledJobDefinition** オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-144">Enter a variable that contains **ScheduledJobDefinition** objects or type a command or expression that gets **ScheduledJobDefinition** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="fa0a0-145">パイプを使用して **ScheduledJobDefinition** オブジェクトを有効にし、 **-Scheduledjob を有効** にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-145">You can also pipe a **ScheduledJobDefinition** object to **Enable-ScheduledJob** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fa0a0-146">-Name</span><span class="sxs-lookup"><span data-stu-id="fa0a0-146">-Name</span></span>
<span data-ttu-id="fa0a0-147">指定された名前のスケジュールされたジョブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-147">Enables the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="fa0a0-148">スケジュールされたジョブの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-148">Enter the name of a scheduled job.</span></span>
<span data-ttu-id="fa0a0-149">ワイルドカードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-149">Wildcards are supported.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fa0a0-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="fa0a0-150">-PassThru</span></span>
<span data-ttu-id="fa0a0-151">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-151">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="fa0a0-152">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-152">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="fa0a0-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fa0a0-153">-Confirm</span></span>
<span data-ttu-id="fa0a0-154">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fa0a0-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fa0a0-155">-WhatIf</span></span>
<span data-ttu-id="fa0a0-156">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="fa0a0-157">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fa0a0-158">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fa0a0-158">CommonParameters</span></span>
<span data-ttu-id="fa0a0-159">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fa0a0-160">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fa0a0-161">入力</span><span class="sxs-lookup"><span data-stu-id="fa0a0-161">INPUTS</span></span>

### <span data-ttu-id="fa0a0-162">ScheduledJobDefinition (Microsoft PowerShell)</span><span class="sxs-lookup"><span data-stu-id="fa0a0-162">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="fa0a0-163">パイプを使用してスケジュールされたジョブを有効にし、 **-ScheduledJob を有効** にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-163">You can pipe a scheduled job to **Enable-ScheduledJob** .</span></span>

## <span data-ttu-id="fa0a0-164">出力</span><span class="sxs-lookup"><span data-stu-id="fa0a0-164">OUTPUTS</span></span>

### <span data-ttu-id="fa0a0-165">[なし] または [ScheduledJobDefinition]</span><span class="sxs-lookup"><span data-stu-id="fa0a0-165">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="fa0a0-166">**Passthru** パラメーターを使用すると、 **Enable-ScheduledJob** は有効にしたスケジュールされたジョブを返します。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-166">If you use the **Passthru** parameter, **Enable-ScheduledJob** returns the scheduled job that was enabled.</span></span>
<span data-ttu-id="fa0a0-167">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="fa0a0-168">注</span><span class="sxs-lookup"><span data-stu-id="fa0a0-168">NOTES</span></span>

* <span data-ttu-id="fa0a0-169">**Enable-ScheduledJob** を使用して、既に有効になっているスケジュールされたジョブを有効にすると、警告やエラーは生成されません。</span><span class="sxs-lookup"><span data-stu-id="fa0a0-169">**Enable-ScheduledJob** does not generate warnings or errors if you use it to enable a scheduled job that is already enabled.</span></span>

## <span data-ttu-id="fa0a0-170">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fa0a0-170">RELATED LINKS</span></span>

[<span data-ttu-id="fa0a0-171">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fa0a0-171">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="fa0a0-172">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fa0a0-172">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="fa0a0-173">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fa0a0-173">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="fa0a0-174">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fa0a0-174">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="fa0a0-175">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fa0a0-175">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="fa0a0-176">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fa0a0-176">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="fa0a0-177">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fa0a0-177">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="fa0a0-178">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="fa0a0-178">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="fa0a0-179">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fa0a0-179">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="fa0a0-180">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="fa0a0-180">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="fa0a0-181">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fa0a0-181">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="fa0a0-182">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fa0a0-182">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="fa0a0-183">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fa0a0-183">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="fa0a0-184">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fa0a0-184">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="fa0a0-185">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="fa0a0-185">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="fa0a0-186">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fa0a0-186">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
