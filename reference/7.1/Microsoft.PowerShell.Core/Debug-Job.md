---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/debug-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Job
ms.openlocfilehash: 8ff583fbf0ebf453a5194deecbc1eb42a51242d4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217779"
---
# <span data-ttu-id="e16e6-103">Debug-Job</span><span class="sxs-lookup"><span data-stu-id="e16e6-103">Debug-Job</span></span>

## <span data-ttu-id="e16e6-104">概要</span><span class="sxs-lookup"><span data-stu-id="e16e6-104">SYNOPSIS</span></span>
<span data-ttu-id="e16e6-105">実行中のバックグラウンド、リモート、または PowerShell ワークフロージョブをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="e16e6-105">Debugs a running background, remote, or PowerShell Workflow job.</span></span>

## <span data-ttu-id="e16e6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e16e6-106">SYNTAX</span></span>

### <span data-ttu-id="e16e6-107">JobParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="e16e6-107">JobParameterSet (Default)</span></span>

```
Debug-Job [-Job] <Job> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e16e6-108">JobNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="e16e6-108">JobNameParameterSet</span></span>

```
Debug-Job [-Name] <String> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e16e6-109">JobIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="e16e6-109">JobIdParameterSet</span></span>

```
Debug-Job [-Id] <Int32> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e16e6-110">JobInstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="e16e6-110">JobInstanceIdParameterSet</span></span>

```
Debug-Job [-InstanceId] <Guid> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e16e6-111">Description</span><span class="sxs-lookup"><span data-stu-id="e16e6-111">DESCRIPTION</span></span>
<span data-ttu-id="e16e6-112">**Job** コマンドレットを使用すると、ジョブ内で実行されているスクリプトをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="e16e6-112">The **Debug-Job** cmdlet lets you debug scripts that are running within jobs.</span></span>
<span data-ttu-id="e16e6-113">コマンドレットは、PowerShell ワークフロージョブ、バックグラウンドジョブ、およびリモートセッションで実行されているジョブをデバッグするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="e16e6-113">The cmdlet is designed to debug PowerShell Workflow jobs, background jobs, and jobs running in remote sessions.</span></span>
<span data-ttu-id="e16e6-114">**Debug-ジョブ** は、実行中のジョブオブジェクト、名前、id、またはインスタンス id を入力として受け取り、実行中のスクリプトでデバッグセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="e16e6-114">**Debug-Job** accepts a running job object, name, ID, or instance ID as input, and starts a debugging session on the script it is running.</span></span>
<span data-ttu-id="e16e6-115">デバッガーの **quit** コマンドは、ジョブを停止し、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="e16e6-115">The debugger **quit** command stops the job and running script.</span></span>
<span data-ttu-id="e16e6-116">Windows PowerShell 5.0 以降では、 **exit** コマンドによってデバッガーがデタッチされ、ジョブの実行を継続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e16e6-116">Starting in Windows PowerShell 5.0, the **exit** command detaches the debugger, and allows the job to continue to run.</span></span>

## <span data-ttu-id="e16e6-117">例</span><span class="sxs-lookup"><span data-stu-id="e16e6-117">EXAMPLES</span></span>

### <span data-ttu-id="e16e6-118">例 1: ジョブ ID でジョブをデバッグする</span><span class="sxs-lookup"><span data-stu-id="e16e6-118">Example 1: Debug a job by job ID</span></span>

```
PS C:\> Debug-Job -ID 3
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
3      Job3            RemoteJob       Running       True            PowerShellIx         TestWFDemo1.ps1
          Entering debug mode. Use h or ? for help.

          Hit Line breakpoint on 'C:\TestWFDemo1.ps1:8'

          At C:\TestWFDemo1.ps1:8 char:5
          +     Write-Output -InputObject "Now writing output:"
          +     ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
          [DBG:PowerShellIx]: PS C:\> > list

              3:
              4:  workflow SampleWorkflowTest
              5:  {
              6:      param ($MyOutput)
              7:
              8:*     Write-Output -InputObject "Now writing output:"
              9:      Write-Output -Input $MyOutput
             10:
             11:      Write-Output -InputObject "Get PowerShell process:"
             12:      Get-Process -Name powershell
             13:
             14:      Write-Output -InputObject "Workflow function complete."
             15:  }
             16:
             17:  # Call workflow function
             18:  SampleWorkflowTest -MyOutput "Hello"
```

<span data-ttu-id="e16e6-119">このコマンドは、ID が3の実行中のジョブに分割されます。</span><span class="sxs-lookup"><span data-stu-id="e16e6-119">This command breaks into a running job with an ID of 3.</span></span>

## <span data-ttu-id="e16e6-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e16e6-120">PARAMETERS</span></span>

### <span data-ttu-id="e16e6-121">-Id</span><span class="sxs-lookup"><span data-stu-id="e16e6-121">-Id</span></span>
<span data-ttu-id="e16e6-122">実行中のジョブの ID 番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="e16e6-122">Specifies the ID number of a running job.</span></span>
<span data-ttu-id="e16e6-123">ジョブの ID 番号を取得するには、Get-Job コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e16e6-123">To get the ID number of a job, run the Get-Job cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: JobIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e16e6-124">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="e16e6-124">-InstanceId</span></span>
<span data-ttu-id="e16e6-125">実行中のジョブのインスタンス ID GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="e16e6-125">Specifies the instance ID GUID of a running job.</span></span>
<span data-ttu-id="e16e6-126">ジョブの *InstanceId* を取得するには、次の例に示すように、 **get-help** コマンドレットを実行し、結果を **形式-** \* コマンドレットにパイプ処理します。</span><span class="sxs-lookup"><span data-stu-id="e16e6-126">To get the *InstanceId* of a job, run the **Get-Job** cmdlet, piping the results into a **Format-** \* cmdlet, as shown in the following example:</span></span>

`Get-Job | Format-List -Property Id,Name,InstanceId,State`

```yaml
Type: System.Guid
Parameter Sets: JobInstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e16e6-127">-ジョブ</span><span class="sxs-lookup"><span data-stu-id="e16e6-127">-Job</span></span>
<span data-ttu-id="e16e6-128">実行中のジョブオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e16e6-128">Specifies a running job object.</span></span>
<span data-ttu-id="e16e6-129">このパラメーターを使用する最も簡単な方法は、変数でデバッグする実行中のジョブを返す **Get job** コマンドの結果を保存し、このパラメーターの値として変数を指定することです。</span><span class="sxs-lookup"><span data-stu-id="e16e6-129">The simplest way to use this parameter is to save the results of a **Get-Job** command that returns the running job that you want to debug in a variable, and then specify the variable as the value of this parameter.</span></span>

```yaml
Type: System.Management.Automation.Job
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e16e6-130">-Name</span><span class="sxs-lookup"><span data-stu-id="e16e6-130">-Name</span></span>
<span data-ttu-id="e16e6-131">ジョブのフレンドリ名でジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="e16e6-131">Specifies a job by the friendly name of the job.</span></span>
<span data-ttu-id="e16e6-132">ジョブを開始するときに、 *JobName* パラメーターを追加することによってジョブ名を指定できます。このコマンドレットには、Invoke-Command や開始ジョブなどがあります。</span><span class="sxs-lookup"><span data-stu-id="e16e6-132">When you start a job, you can specify a job name by adding the *JobName* parameter, in cmdlets such as Invoke-Command and Start-Job.</span></span>

```yaml
Type: System.String
Parameter Sets: JobNameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e16e6-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e16e6-133">-Confirm</span></span>
<span data-ttu-id="e16e6-134">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e16e6-134">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e16e6-135">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e16e6-135">-WhatIf</span></span>
<span data-ttu-id="e16e6-136">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="e16e6-136">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e16e6-137">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e16e6-137">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e16e6-138">-BreakAll</span><span class="sxs-lookup"><span data-stu-id="e16e6-138">-BreakAll</span></span>

<span data-ttu-id="e16e6-139">{{BreakAll の説明を入力}}</span><span class="sxs-lookup"><span data-stu-id="e16e6-139">{{ Fill BreakAll Description }}</span></span>

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

### <span data-ttu-id="e16e6-140">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e16e6-140">CommonParameters</span></span>
<span data-ttu-id="e16e6-141">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e16e6-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e16e6-142">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e16e6-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e16e6-143">入力</span><span class="sxs-lookup"><span data-stu-id="e16e6-143">INPUTS</span></span>

### <span data-ttu-id="e16e6-144">System. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="e16e6-144">System.Management.Automation.RemotingJob</span></span>

## <span data-ttu-id="e16e6-145">出力</span><span class="sxs-lookup"><span data-stu-id="e16e6-145">OUTPUTS</span></span>

## <span data-ttu-id="e16e6-146">注</span><span class="sxs-lookup"><span data-stu-id="e16e6-146">NOTES</span></span>

## <span data-ttu-id="e16e6-147">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e16e6-147">RELATED LINKS</span></span>

[<span data-ttu-id="e16e6-148">Get-Job</span><span class="sxs-lookup"><span data-stu-id="e16e6-148">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="e16e6-149">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="e16e6-149">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="e16e6-150">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="e16e6-150">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="e16e6-151">Start-Job</span><span class="sxs-lookup"><span data-stu-id="e16e6-151">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="e16e6-152">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="e16e6-152">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="e16e6-153">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="e16e6-153">Wait-Job</span></span>](Wait-Job.md)

