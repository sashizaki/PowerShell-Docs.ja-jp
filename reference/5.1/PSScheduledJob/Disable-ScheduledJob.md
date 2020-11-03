---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ScheduledJob
ms.openlocfilehash: a7ea520d7d0365fd0de8c9d0bb767981b68467c6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213475"
---
# <span data-ttu-id="f66bb-103">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f66bb-103">Disable-ScheduledJob</span></span>

## <span data-ttu-id="f66bb-104">概要</span><span class="sxs-lookup"><span data-stu-id="f66bb-104">SYNOPSIS</span></span>
<span data-ttu-id="f66bb-105">スケジュールされたジョブを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f66bb-105">Disables a scheduled job.</span></span>

## <span data-ttu-id="f66bb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f66bb-106">SYNTAX</span></span>

### <span data-ttu-id="f66bb-107">定義 (既定)</span><span class="sxs-lookup"><span data-stu-id="f66bb-107">Definition (Default)</span></span>

```
Disable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="f66bb-108">DefinitionId</span><span class="sxs-lookup"><span data-stu-id="f66bb-108">DefinitionId</span></span>

```
Disable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f66bb-109">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="f66bb-109">DefinitionName</span></span>

```
Disable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f66bb-110">Description</span><span class="sxs-lookup"><span data-stu-id="f66bb-110">DESCRIPTION</span></span>
<span data-ttu-id="f66bb-111">**Disable-ScheduledJob** コマンドレットは、スケジュールされたジョブを一時的に無効にします。</span><span class="sxs-lookup"><span data-stu-id="f66bb-111">The **Disable-ScheduledJob** cmdlet temporarily disables scheduled jobs.</span></span>
<span data-ttu-id="f66bb-112">無効にしても、ジョブのプロパティはすべて保持され、ジョブ トリガーは無効になりません。ただし、スケジュールされたジョブはトリガーされても自動的に開始されることはありません。</span><span class="sxs-lookup"><span data-stu-id="f66bb-112">Disabling preserves all job properties and does not disable the job triggers, but it prevents the scheduled jobs from starting automatically when triggered.</span></span>
<span data-ttu-id="f66bb-113">無効なスケジュールされたジョブを開始するには、Start-Job コマンドレットを使用するか、無効なスケジュールされたジョブをテンプレートとして使用します。</span><span class="sxs-lookup"><span data-stu-id="f66bb-113">You can start a disabled scheduled job by using the Start-Job cmdlet or use a disabled scheduled job as a template.</span></span>

<span data-ttu-id="f66bb-114">スケジュールされたジョブを無効にするために、 **Disable-ScheduledJob** コマンドレットは、スケジュールされたジョブの **Enabled** プロパティを False ($false) に設定します。</span><span class="sxs-lookup"><span data-stu-id="f66bb-114">To disable a scheduled job, the **Disable-ScheduledJob** cmdlet sets the **Enabled** property of the scheduled job to False ($false).</span></span>
<span data-ttu-id="f66bb-115">スケジュールされたジョブを再度有効にするには、Enable-ScheduledJob コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f66bb-115">To re-enable the scheduled job, use the Enable-ScheduledJob cmdlet.</span></span>

<span data-ttu-id="f66bb-116">**Disable-scheduledjob** は、Windows PowerShell に含まれている **psscheduledjob** モジュールのジョブスケジュールコマンドレットのコレクションの1つです。</span><span class="sxs-lookup"><span data-stu-id="f66bb-116">**Disable-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="f66bb-117">スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f66bb-117">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="f66bb-118">PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f66bb-118">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="f66bb-119">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f66bb-119">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="f66bb-120">例</span><span class="sxs-lookup"><span data-stu-id="f66bb-120">EXAMPLES</span></span>

### <span data-ttu-id="f66bb-121">例 1: スケジュールされたジョブを無効にする</span><span class="sxs-lookup"><span data-stu-id="f66bb-121">Example 1: Disable a scheduled job</span></span>

```
PS C:\> Disable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
```

<span data-ttu-id="f66bb-122">このコマンドは、ローカル コンピューター上の ID が 2 のスケジュールされたジョブを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f66bb-122">This command disables the scheduled job with ID 2 on the local computer.</span></span>
<span data-ttu-id="f66bb-123">出力には、コマンドの結果が示されています。</span><span class="sxs-lookup"><span data-stu-id="f66bb-123">The output shows the effect of the command.</span></span>

### <span data-ttu-id="f66bb-124">例 2: すべてのスケジュールされたジョブを無効にする</span><span class="sxs-lookup"><span data-stu-id="f66bb-124">Example 2: Disable all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Disable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        False
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     False
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       False
```

<span data-ttu-id="f66bb-125">このコマンドは、ローカル コンピューター上のスケジュールされたすべてのジョブを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f66bb-125">This command disables all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="f66bb-126">また、Get-ScheduledJob コマンドレットを使用してスケジュールされたすべてのジョブを取得し、 **無効化-scheduledjob** コマンドレットを使用してそれらを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f66bb-126">It uses the Get-ScheduledJob cmdlet to get all scheduled job and the **Disable-ScheduledJob** cmdlet to disable them.</span></span>

<span data-ttu-id="f66bb-127">Enable-ScheduledJob コマンドレットを使用してスケジュールされたジョブを再度有効にし、Start-Job コマンドレットを使用して、無効になっているスケジュールされたジョブを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f66bb-127">You can re-enable scheduled job by using the Enable-ScheduledJob cmdlet and run a disabled scheduled job by using the Start-Job cmdlet.</span></span>

<span data-ttu-id="f66bb-128">無効 **-ScheduledJob** は、既に無効になっているスケジュールされたジョブを無効にした場合に、警告やエラーを生成しません。そのため、すべてのスケジュールされたジョブを条件なしで無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f66bb-128">**Disable-ScheduledJob** does not generate warnings or errors if you disable a scheduled job that is already disabled, so you can disable all scheduled jobs without conditions.</span></span>

### <span data-ttu-id="f66bb-129">例 3: 選択したスケジュールされたジョブを無効にする</span><span class="sxs-lookup"><span data-stu-id="f66bb-129">Example 3: Disable selected scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Where-Object {!$_.Credential} | Disable-ScheduledJob
```

<span data-ttu-id="f66bb-130">このコマンドは、資格情報が含まれていないスケジュールされたジョブを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f66bb-130">This command disables scheduled job do not include a credential.</span></span>
<span data-ttu-id="f66bb-131">資格情報が含まれていないジョブは、そのジョブを作成したユーザーのアクセス許可で実行されます。</span><span class="sxs-lookup"><span data-stu-id="f66bb-131">Jobs without credentials run with the permission of the user who created them.</span></span>

<span data-ttu-id="f66bb-132">このコマンドは、Get-ScheduledJob コマンドレットを使用して、コンピューター上のスケジュールされたすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="f66bb-132">The command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the computer.</span></span>
<span data-ttu-id="f66bb-133">パイプライン演算子は、スケジュールされたジョブを Where-Object コマンドレットに送信します。これにより、資格情報のないスケジュールされたジョブが選択されます。</span><span class="sxs-lookup"><span data-stu-id="f66bb-133">A pipeline operator sends the scheduled jobs to the Where-Object cmdlet, which selects scheduled jobs that do not have credentials.</span></span>
<span data-ttu-id="f66bb-134">このコマンドは、not (!) 演算子を使用し、スケジュールされたジョブの Credential プロパティを参照します。</span><span class="sxs-lookup"><span data-stu-id="f66bb-134">The command uses the not (!) operator and references the Credential property of the scheduled job.</span></span>
<span data-ttu-id="f66bb-135">もう 1 つのパイプライン演算子により、選択されたスケジュールされたジョブを **Disable-ScheduledJob** コマンドレットに渡して、無効にします。</span><span class="sxs-lookup"><span data-stu-id="f66bb-135">Another pipeline operator sends the selected scheduled jobs to the **Disable-ScheduledJob** cmdlet, which disables them.</span></span>

### <span data-ttu-id="f66bb-136">例 4: リモートコンピューター上のスケジュールされたジョブを無効にする</span><span class="sxs-lookup"><span data-stu-id="f66bb-136">Example 4: Disable scheduled jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01, Srv10 -ScriptBlock {Disable-ScheduledJob -Name TestJob}
```

<span data-ttu-id="f66bb-137">このコマンドは、2 台のリモート コンピューター Srv01 と Srv10 上のスケジュールされたジョブ TestJob を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f66bb-137">This command disables the TestJob scheduled job on two remote computers, Srv01 and Srv10.</span></span>

<span data-ttu-id="f66bb-138">このコマンドは、Invoke-Command コマンドレットを使用して、Srv01 および Srv10 コンピューターで無効になっている **ScheduledJob** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f66bb-138">The command uses the Invoke-Command cmdlet to run a **Disable-ScheduledJob** command on the Srv01 and Srv10 computers.</span></span>
<span data-ttu-id="f66bb-139">このコマンドは、 *Disable-ScheduledJob* の **Name** パラメーターを使用して、各コンピューター上のスケジュールされたジョブ TestJob を選択します。</span><span class="sxs-lookup"><span data-stu-id="f66bb-139">The command uses the *Name* parameter of **Disable-ScheduledJob** to select the TestJob scheduled job on each computer.</span></span>

### <span data-ttu-id="f66bb-140">例 5: スケジュールされたジョブをグローバル ID で無効にする</span><span class="sxs-lookup"><span data-stu-id="f66bb-140">Example 5: Disable a scheduled job by its global ID</span></span>

```
The first command demonstrates one way of finding the GlobalID of a scheduled job. The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Format-Table cmdlet, which displays the Name, GlobalID, and Command properties of each job in a table.
PS C:\> Get-ScheduledJob | Format-Table -Property Name, GlobalID, Command -Autosize
Name             GlobalId                             Command
----             --------                             -------
ArchiveProjects1 a26a0b3d-b4e6-44d3-8b95-8706ef621f7c C:\Scripts\Archive-DxProjects.ps1
Inventory        3ac37e5d-84c0-4a8f-9661-7e88ebb8f914 \\Srv01\Scripts\Get-FullInventory.ps1
Backup-Scripts   4d0cc6be-c082-48d1-baec-1bd8278f3c81  Copy-Item C:\CurrentScripts\*.ps1 -Destination C:\BackupScripts
Test-HelpFiles   d77020ca-f20d-42be-86c8-fc64df97db90 .\Test-HelpFiles.ps1
Test-HelpFiles   2f1606d2-c6cf-4bef-8b1c-ae36a9cc9934 .\Test-DomainHelpFiles.ps1

The second command uses the  Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Where-Object cmdlet, which selects the scheduled job with the specified global ID. Another pipeline operator sends the job to the **Disable-ScheduledJob** cmdlet, which disables it.
PS C:\> Get-ScheduledJob | Where-Object {$_.GlobalID = d77020ca-f20d-42be-86c8-fc64df97db90} | Disable-ScheduledJob
```

<span data-ttu-id="f66bb-141">この例では、グローバル識別子を使用して、スケジュールされたジョブを無効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f66bb-141">This examples shows how to disable a scheduled job by using its global identifier.</span></span>
<span data-ttu-id="f66bb-142">スケジュールされたジョブの GlobalID プロパティの値は一意識別子 (GUID) です。</span><span class="sxs-lookup"><span data-stu-id="f66bb-142">The value of the GlobalID property of a scheduled job is a unique identifier (GUID).</span></span>
<span data-ttu-id="f66bb-143">複数のコンピューター上のスケジュールされたジョブを無効にする場合など、正確性が求められる場合に、GlobalID 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="f66bb-143">Use the GlobalID value when precision is required, such as when you are disabling scheduled jobs on multiple computers.</span></span>

## <span data-ttu-id="f66bb-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f66bb-144">PARAMETERS</span></span>

### <span data-ttu-id="f66bb-145">-Id</span><span class="sxs-lookup"><span data-stu-id="f66bb-145">-Id</span></span>
<span data-ttu-id="f66bb-146">指定された識別番号 (ID) のスケジュールされたジョブを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f66bb-146">Disables the scheduled job with the specified identification number (ID).</span></span>
<span data-ttu-id="f66bb-147">スケジュールされたジョブの ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="f66bb-147">Enter the ID of a scheduled job.</span></span>

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

### <span data-ttu-id="f66bb-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f66bb-148">-InputObject</span></span>
<span data-ttu-id="f66bb-149">無効にするスケジュールされたジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="f66bb-149">Specifies the scheduled job to be disabled.</span></span>
<span data-ttu-id="f66bb-150">**ScheduledJobDefinition** オブジェクトを含む変数を入力するか、Get-ScheduledJob コマンドなどの **ScheduledJobDefinition** オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="f66bb-150">Enter a variable that contains  **ScheduledJobDefinition** objects or type a command or expression that gets **ScheduledJobDefinition** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="f66bb-151">パイプを使用して **ScheduledJobDefinition** オブジェクトを無効にし、 **-Scheduledjob を無効** にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f66bb-151">You can also pipe a **ScheduledJobDefinition** object to **Disable-ScheduledJob** .</span></span>

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

### <span data-ttu-id="f66bb-152">-Name</span><span class="sxs-lookup"><span data-stu-id="f66bb-152">-Name</span></span>
<span data-ttu-id="f66bb-153">指定された名前のスケジュールされたジョブを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f66bb-153">Disables the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="f66bb-154">スケジュールされたジョブの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f66bb-154">Enter the name of a scheduled job.</span></span>
<span data-ttu-id="f66bb-155">ワイルドカードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="f66bb-155">Wildcards are supported.</span></span>

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

### <span data-ttu-id="f66bb-156">-PassThru</span><span class="sxs-lookup"><span data-stu-id="f66bb-156">-PassThru</span></span>
<span data-ttu-id="f66bb-157">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="f66bb-157">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="f66bb-158">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="f66bb-158">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="f66bb-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f66bb-159">-Confirm</span></span>
<span data-ttu-id="f66bb-160">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f66bb-160">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f66bb-161">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f66bb-161">-WhatIf</span></span>
<span data-ttu-id="f66bb-162">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="f66bb-162">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f66bb-163">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f66bb-163">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f66bb-164">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f66bb-164">CommonParameters</span></span>
<span data-ttu-id="f66bb-165">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f66bb-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f66bb-166">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f66bb-166">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f66bb-167">入力</span><span class="sxs-lookup"><span data-stu-id="f66bb-167">INPUTS</span></span>

### <span data-ttu-id="f66bb-168">ScheduledJobDefinition (Microsoft PowerShell)</span><span class="sxs-lookup"><span data-stu-id="f66bb-168">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="f66bb-169">パイプを使用して、スケジュールされたジョブを **Disable-ScheduledJob** に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="f66bb-169">You can pipe a scheduled job to **Disable-ScheduledJob** .</span></span>

## <span data-ttu-id="f66bb-170">出力</span><span class="sxs-lookup"><span data-stu-id="f66bb-170">OUTPUTS</span></span>

### <span data-ttu-id="f66bb-171">[なし] または [ScheduledJobDefinition]</span><span class="sxs-lookup"><span data-stu-id="f66bb-171">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="f66bb-172">**Passthru** パラメーターを使用すると、 **Disable-ScheduledJob** は無効にしたスケジュールされたジョブを返します。</span><span class="sxs-lookup"><span data-stu-id="f66bb-172">If you use the **Passthru** parameter, **Disable-ScheduledJob** returns the scheduled job that was disabled.</span></span>
<span data-ttu-id="f66bb-173">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="f66bb-173">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f66bb-174">注</span><span class="sxs-lookup"><span data-stu-id="f66bb-174">NOTES</span></span>

* <span data-ttu-id="f66bb-175">**無効-ScheduledJob** を使用して、既に無効になっているスケジュールされたジョブを無効にすると、警告やエラーは生成されません。</span><span class="sxs-lookup"><span data-stu-id="f66bb-175">**Disable-ScheduledJob** does not generate warnings or errors if you use it to disable a scheduled job that is already disabled.</span></span>

## <span data-ttu-id="f66bb-176">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f66bb-176">RELATED LINKS</span></span>

[<span data-ttu-id="f66bb-177">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f66bb-177">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="f66bb-178">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f66bb-178">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="f66bb-179">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f66bb-179">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="f66bb-180">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f66bb-180">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="f66bb-181">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f66bb-181">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="f66bb-182">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f66bb-182">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="f66bb-183">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f66bb-183">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="f66bb-184">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f66bb-184">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="f66bb-185">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f66bb-185">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="f66bb-186">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f66bb-186">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="f66bb-187">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f66bb-187">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="f66bb-188">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f66bb-188">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="f66bb-189">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f66bb-189">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="f66bb-190">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f66bb-190">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="f66bb-191">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f66bb-191">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="f66bb-192">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f66bb-192">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
