---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/suspend-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Job
ms.openlocfilehash: 9b18782fae77fa0776aa2cfaa39b74a2292099d9
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388469"
---
# <span data-ttu-id="79d7c-103">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="79d7c-103">Suspend-Job</span></span>

## <span data-ttu-id="79d7c-104">概要</span><span class="sxs-lookup"><span data-stu-id="79d7c-104">SYNOPSIS</span></span>
<span data-ttu-id="79d7c-105">ワークフロー ジョブを一時的に停止します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-105">Temporarily stops workflow jobs.</span></span>

## <span data-ttu-id="79d7c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="79d7c-106">SYNTAX</span></span>

### <span data-ttu-id="79d7c-107">SessionIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="79d7c-107">SessionIdParameterSet (Default)</span></span>

```
Suspend-Job [-Force] [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="79d7c-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="79d7c-108">JobParameterSet</span></span>

```
Suspend-Job [-Job] <Job[]> [-Force] [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="79d7c-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="79d7c-109">NameParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="79d7c-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="79d7c-110">InstanceIdParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="79d7c-111">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="79d7c-111">FilterParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="79d7c-112">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="79d7c-112">StateParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="79d7c-113">Description</span><span class="sxs-lookup"><span data-stu-id="79d7c-113">DESCRIPTION</span></span>

<span data-ttu-id="79d7c-114">コマンドレットでは、 `Suspend-Job` ワークフロージョブを中断します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-114">The `Suspend-Job` cmdlet suspends workflow jobs.</span></span> <span data-ttu-id="79d7c-115">中断とは、一時的にワークフロージョブを中断または一時停止することを意味します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-115">Suspend means to temporarily interrupt or pause a workflow job.</span></span> <span data-ttu-id="79d7c-116">ワークフローを実行しているユーザーは、このコマンドレットを使用してワークフローを中断できます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-116">This cmdlet allows users who are running workflows to suspend the workflow.</span></span> <span data-ttu-id="79d7c-117">ワークフローを中断するワークフロー内のコマンドである、中断ワークフローアクティビティを補完し https://go.microsoft.com/fwlink/?LinkId=267141 ます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-117">It complements the Suspend-Workflowhttps://go.microsoft.com/fwlink/?LinkId=267141 activity, which is a command in the workflow that suspends the workflow.</span></span>

<span data-ttu-id="79d7c-118">`Suspend-Job`コマンドレットは、ワークフロージョブに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-118">The `Suspend-Job` cmdlet works only on workflow jobs.</span></span> <span data-ttu-id="79d7c-119">コマンドレットを使用して開始されたものなど、標準のバックグラウンドジョブでは機能しません `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="79d7c-119">It does not work on standard background jobs, such as those that are started by using the `Start-Job` cmdlet.</span></span>

<span data-ttu-id="79d7c-120">ワークフロー ジョブを識別するには、ジョブの PSJobTypeName プロパティで **PSWorkflowJob** の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-120">To identify a workflow job, look for a value of PSWorkflowJob in the **PSJobTypeName** property of the job.</span></span> <span data-ttu-id="79d7c-121">特定のカスタムジョブの種類がコマンドレットをサポートしているかどうかを判断するには、 `Suspend-Job` カスタムジョブの種類のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="79d7c-121">To determine whether a particular custom job type supports the `Suspend-Job` cmdlet, see the help topics for the custom job type.</span></span>

<span data-ttu-id="79d7c-122">ワークフロー ジョブを中断すると、ワークフロー ジョブは次のチェックポイントまで実行された後で中断されます。その後、ワークフロー ジョブ オブジェクトが直ちに返されます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-122">When you suspend a workflow job, the workflow job runs to the next checkpoint, suspends, and immediately returns a workflow job object.</span></span> <span data-ttu-id="79d7c-123">ジョブを取得する前に中断が完了するまで待機するに **Wait** `Suspend-Job` は、またはコマンドレットの wait パラメーターを使用し `Wait-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-123">To wait for the suspension to complete before getting the job, use the **Wait** parameter of `Suspend-Job` or the `Wait-Job` cmdlet.</span></span> <span data-ttu-id="79d7c-124">ワークフロージョブが中断されている場合、ジョブの **State** プロパティの値は中断されます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-124">When the workflow job is suspended, the value of the **State** property of the job is Suspended.</span></span>

<span data-ttu-id="79d7c-125">正しく中断できるかどうかはチェックポイントに依存します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-125">Suspending correctly relies on checkpoints.</span></span> <span data-ttu-id="79d7c-126">現在のジョブの状態、メタデータ、および出力がチェックポイントに保存されるため、状態やデータを失うことなくワークフロージョブを再開できます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-126">The current job state, metadata, and output are saved in the checkpoint so the workflow job can be resumed without loss of state or data.</span></span> <span data-ttu-id="79d7c-127">ワークフロージョブにチェックポイントがない場合、正常に中断することはできません。</span><span class="sxs-lookup"><span data-stu-id="79d7c-127">If the workflow job does not have checkpoints, it cannot be suspended correctly.</span></span> <span data-ttu-id="79d7c-128">実行中のワークフローにチェックポイントを追加するには、 **PSPersist** ワークフロー共通パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-128">To add checkpoints to a workflow that you are running, use the **PSPersist** workflow common parameter.</span></span> <span data-ttu-id="79d7c-129">**Force** パラメーターを使用すると、ワークフロージョブを即座に中断し、チェックポイントのないワークフロージョブを中断できますが、操作によって状態とデータが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="79d7c-129">You can use the **Force** parameter to suspend any workflow job immediately and to suspend a workflow job that does not have checkpoints, but the action could cause loss of state and data.</span></span>

<span data-ttu-id="79d7c-130">ワークフロージョブ ( **Psworkflowjob** ) などのカスタムジョブの種類で job コマンドレットを使用する前に、カスタムジョブの種類をサポートするモジュールをインポートします。そのためには、コマンドレットを使用するか、 `Import-Module` またはモジュールのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-130">Before you use a Job cmdlet on a custom job type, such as a workflow job ( **PSWorkflowJob** ) import the module that supports the custom job type, either by using the `Import-Module` cmdlet or using or using a cmdlet in the module.</span></span>

<span data-ttu-id="79d7c-131">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="79d7c-131">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="79d7c-132">例</span><span class="sxs-lookup"><span data-stu-id="79d7c-132">EXAMPLES</span></span>

### <span data-ttu-id="79d7c-133">例 1: 名前を指定してワークフロージョブを中断する</span><span class="sxs-lookup"><span data-stu-id="79d7c-133">Example 1: Suspend a workflow job by name</span></span>

<span data-ttu-id="79d7c-134">この例では、ワークフロー ジョブを中断する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-134">This example shows how to suspend a workflow job.</span></span>

<span data-ttu-id="79d7c-135">最初のコマンドは、ワークフローを作成し `Get-SystemLog` ます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-135">The first command creates the `Get-SystemLog` workflow.</span></span> <span data-ttu-id="79d7c-136">ワークフローは、アクティビティを使用して `CheckPoint-Workflow` ワークフローのチェックポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-136">The workflow uses the `CheckPoint-Workflow` activity to define a checkpoint in the workflow.</span></span>

<span data-ttu-id="79d7c-137">2番目のコマンドは、すべてのワークフローに共通の **AsJob** パラメーターを使用し `Get-SystemLog` て、ワークフローをバックグラウンドジョブとして実行します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-137">The second command uses the **AsJob** parameter that is common to all workflows to run the `Get-SystemLog` workflow as a background job.</span></span> <span data-ttu-id="79d7c-138">このコマンドは、 **JobName** ワークフロー共通パラメーターを使用して、ワークフロー ジョブのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-138">The command uses the **JobName** workflow common parameter to specify a friendly name for the workflow job.</span></span>

<span data-ttu-id="79d7c-139">3番目のコマンドは、 `Get-Job` コマンドレットを使用してワークフロージョブを取得し `Get-SystemLogJob` ます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-139">The third command uses the `Get-Job` cmdlet to get the `Get-SystemLogJob` workflow job.</span></span> <span data-ttu-id="79d7c-140">出力には、 **PSJobTypeName** プロパティの値が PSWorkflowJob であることが示されています。</span><span class="sxs-lookup"><span data-stu-id="79d7c-140">The output shows that the value of the **PSJobTypeName** property is PSWorkflowJob.</span></span>

<span data-ttu-id="79d7c-141">4番目のコマンドは、 `Suspend-Job` コマンドレットを使用してジョブを中断し `Get-SystemLogJob` ます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-141">The fourth command uses the `Suspend-Job` cmdlet to suspend the `Get-SystemLogJob` job.</span></span> <span data-ttu-id="79d7c-142">ジョブはチェックポイントまで実行された後、中断されます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-142">The job runs to the checkpoint and then suspends.</span></span>

```
#Sample WorkflowWorkflow Get-SystemLog
{
    $Events = Get-WinEvent -LogName System
    CheckPoint-Workflow
    InlineScript {\\Server01\Scripts\Analyze-SystemEvents.ps1 -Events $Events}
}

PS C:\> Get-SystemLog -AsJob -JobName "Get-SystemLogJob"

PS C:\> Get-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Running     True            localhost   Get-SystemLog

PS C:\> Suspend-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Suspended   True            localhost   Get-SystemLog
```


### <span data-ttu-id="79d7c-143">例 2: ワークフロージョブを中断および再開する</span><span class="sxs-lookup"><span data-stu-id="79d7c-143">Example 2: Suspend and resume a workflow job</span></span>

<span data-ttu-id="79d7c-144">この例では、ワークフロー ジョブを中断し、再開する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-144">This example shows how to suspend and resume a workflow job.</span></span>

<span data-ttu-id="79d7c-145">最初のコマンドは、LogWorkflowJob ジョブを中断します。コマンドは直ちに返されます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-145">The first command suspends the LogWorkflowJob job.The command returns immediately.</span></span> <span data-ttu-id="79d7c-146">出力は、中断されている場合でも、ワークフロージョブがまだ実行中であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="79d7c-146">The output shows that the workflow job is still running, even though it is being suspended.</span></span>

<span data-ttu-id="79d7c-147">2番目のコマンドは、 `Get-Job` コマンドレットを使用して LogWorkflowJob ジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-147">The second command uses the `Get-Job` cmdlet to get the LogWorkflowJob job.</span></span> <span data-ttu-id="79d7c-148">出力には、ジョブが正常に完了したことが示されています。</span><span class="sxs-lookup"><span data-stu-id="79d7c-148">The output shows that the workflow job suspended successfully.</span></span>

<span data-ttu-id="79d7c-149">3番目のコマンドは、コマンドレットを使用して `Get-Job` LogWorkflowJob ジョブを取得し、コマンドレットを使用してジョブを `Resume-Job` 再開します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-149">The third command uses the `Get-Job` cmdlet to get the LogWorkflowJob job and the `Resume-Job` cmdlet to resume it.</span></span> <span data-ttu-id="79d7c-150">出力には、ワークフロー ジョブが正常に再開され、現在実行中であることが示されています。</span><span class="sxs-lookup"><span data-stu-id="79d7c-150">The output shows that the workflow job resumed successfully and is now running.</span></span>

```
PS C:\> Suspend-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow

PS C:\> Get-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Suspended     True            localhost            LogWorkflow

PS C:\> Get-Job -Name LogWorkflowJob | Resume-Job
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow
```


### <span data-ttu-id="79d7c-151">例 3: リモートコンピューター上のワークフロージョブを中断する</span><span class="sxs-lookup"><span data-stu-id="79d7c-151">Example 3: Suspend a workflow job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01 -Scriptblock {Suspend-Job -Filter @{CustomID="031589"}
```

<span data-ttu-id="79d7c-152">このコマンドは、 `Invoke-Command` コマンドレットを使用して、Srv01 リモートコンピューター上のワークフロージョブを中断します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-152">This command uses the `Invoke-Command` cmdlet to suspend a workflow job on the Srv01 remote computer.</span></span> <span data-ttu-id="79d7c-153">**Filter** パラメーターの値は、customid 値を指定するハッシュテーブルです。</span><span class="sxs-lookup"><span data-stu-id="79d7c-153">The value of the **Filter** parameter is a hash table that specifies a CustomID value.</span></span>
<span data-ttu-id="79d7c-154">この **CustomID** は、ジョブのメタデータ ( **PSPrivateMetadata** ) です。</span><span class="sxs-lookup"><span data-stu-id="79d7c-154">This **CustomID** is job metadata ( **PSPrivateMetadata** ).</span></span>

### <span data-ttu-id="79d7c-155">例 4: ワークフロージョブが中断されるまで待機する</span><span class="sxs-lookup"><span data-stu-id="79d7c-155">Example 4: Wait for the workflow job to suspend</span></span>

```
PS C:\> Suspend-Job VersionCheck -Wait
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
 5     VersionCheck  PSWorkflowJob      Suspended     True            localhost            LogWorkflow
```

<span data-ttu-id="79d7c-156">このコマンドは、VersionCheck ワークフロー ジョブを中断します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-156">This command suspends the VersionCheck workflow job.</span></span> <span data-ttu-id="79d7c-157">このコマンドでは、 **Wait** パラメーターを使用して、ワークフロー ジョブが中断されるのを待機しています。</span><span class="sxs-lookup"><span data-stu-id="79d7c-157">The command uses the **Wait** parameter to wait until the workflow job is suspended.</span></span> <span data-ttu-id="79d7c-158">ワークフロージョブが次のチェックポイントまで実行され、中断されると、コマンドが完了し、ジョブオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-158">When the workflow job runs to the next checkpoint and is suspended, the command finishes and returns the job object.</span></span>

### <span data-ttu-id="79d7c-159">例 5: ワークフロージョブを強制的に中断する</span><span class="sxs-lookup"><span data-stu-id="79d7c-159">Example 5: Force a workflow job to suspend</span></span>

```
PS C:\> Suspend-Job Maintenance -Force
```

<span data-ttu-id="79d7c-160">このコマンドは、強制的に Maintenance ワークフロー ジョブを中断します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-160">This command suspends the Maintenance workflow job forcibly.</span></span> <span data-ttu-id="79d7c-161">メンテナンスジョブにチェックポイントがありません。</span><span class="sxs-lookup"><span data-stu-id="79d7c-161">The Maintenance job does not have checkpoints.</span></span> <span data-ttu-id="79d7c-162">正しく中断することができず、正常に再開されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="79d7c-162">It cannot be suspended correctly and might not resume correctly.</span></span>

## <span data-ttu-id="79d7c-163">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="79d7c-163">PARAMETERS</span></span>

### <span data-ttu-id="79d7c-164">-Filter</span><span class="sxs-lookup"><span data-stu-id="79d7c-164">-Filter</span></span>

<span data-ttu-id="79d7c-165">条件のハッシュテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-165">Specifies a hash table of conditions.</span></span> <span data-ttu-id="79d7c-166">このコマンドレットは、すべての条件に適合するジョブを中断します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-166">This cmdlet suspends jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="79d7c-167">ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-167">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="79d7c-168">-Force</span><span class="sxs-lookup"><span data-stu-id="79d7c-168">-Force</span></span>

<span data-ttu-id="79d7c-169">ワークフロー ジョブを即座に中断します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-169">Suspends the workflow job immediately.</span></span> <span data-ttu-id="79d7c-170">この操作により、状態とデータが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="79d7c-170">This action could cause a loss of state and data.</span></span>

<span data-ttu-id="79d7c-171">既定では、 `Suspend-Job` ワークフロージョブは次のチェックポイントまで実行され、その後中断されます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-171">By default, `Suspend-Job` lets the workflow job run until the next checkpoint and then suspends it.</span></span>
<span data-ttu-id="79d7c-172">このパラメーターを使用すると、チェックポイントがないワークフロー ジョブも中断できます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-172">You can also use this parameter to suspend workflow jobs that do not have checkpoints.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: F

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79d7c-173">-Id</span><span class="sxs-lookup"><span data-stu-id="79d7c-173">-Id</span></span>

<span data-ttu-id="79d7c-174">このコマンドレットが中断するジョブの Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-174">Specifies the IDs of jobs that this cmdlet suspends.</span></span>

<span data-ttu-id="79d7c-175">ID は、現在のセッションでジョブを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="79d7c-175">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="79d7c-176">インスタンス ID よりも覚えやすく、入力する方が簡単ですが、現在のセッションでのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="79d7c-176">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="79d7c-177">1つ以上の Id をコンマで区切って入力できます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-177">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="79d7c-178">ジョブの ID を検索するには、コマンドレットを使用し `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-178">To find the ID of a job, use the `Get-Job` cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="79d7c-179">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="79d7c-179">-InstanceId</span></span>

<span data-ttu-id="79d7c-180">このコマンドレットが中断するジョブのインスタンス Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-180">Specifies the instance IDs of jobs that this cmdlet suspends.</span></span> <span data-ttu-id="79d7c-181">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="79d7c-181">The default is all jobs.</span></span>

<span data-ttu-id="79d7c-182">インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="79d7c-182">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="79d7c-183">ジョブのインスタンス ID を検索するには、を使用 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-183">To find the instance ID of a job, use `Get-Job`.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="79d7c-184">-ジョブ</span><span class="sxs-lookup"><span data-stu-id="79d7c-184">-Job</span></span>

<span data-ttu-id="79d7c-185">このコマンドレットが停止するワークフロージョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-185">Specifies the workflow jobs that this cmdlet stops.</span></span> <span data-ttu-id="79d7c-186">ワークフロー ジョブが格納されている変数、またはワークフロー ジョブを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-186">Enter a variable that contains the workflow jobs or a command that gets the workflow jobs.</span></span> <span data-ttu-id="79d7c-187">ワークフロージョブをコマンドレットにパイプ処理することもでき `Suspend-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-187">You can also pipe workflow jobs to the `Suspend-Job` cmdlet.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="79d7c-188">-Name</span><span class="sxs-lookup"><span data-stu-id="79d7c-188">-Name</span></span>

<span data-ttu-id="79d7c-189">このコマンドレットが中断するジョブのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-189">Specifies friendly names of jobs that this cmdlet suspends.</span></span> <span data-ttu-id="79d7c-190">1 つまたは複数のワークフロー ジョブ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-190">Enter one or more workflow job names.</span></span>
<span data-ttu-id="79d7c-191">ワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="79d7c-191">Wildcard characters are supported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="79d7c-192">-状態</span><span class="sxs-lookup"><span data-stu-id="79d7c-192">-State</span></span>

<span data-ttu-id="79d7c-193">ジョブの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-193">Specifies a job state.</span></span> <span data-ttu-id="79d7c-194">このコマンドレットは、指定された状態のジョブのみを停止します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-194">This cmdlet stops only jobs in the specified state.</span></span> <span data-ttu-id="79d7c-195">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="79d7c-195">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="79d7c-196">NotStarted</span><span class="sxs-lookup"><span data-stu-id="79d7c-196">NotStarted</span></span>
- <span data-ttu-id="79d7c-197">実行中</span><span class="sxs-lookup"><span data-stu-id="79d7c-197">Running</span></span>
- <span data-ttu-id="79d7c-198">完了</span><span class="sxs-lookup"><span data-stu-id="79d7c-198">Completed</span></span>
- <span data-ttu-id="79d7c-199">失敗</span><span class="sxs-lookup"><span data-stu-id="79d7c-199">Failed</span></span>
- <span data-ttu-id="79d7c-200">停止済み</span><span class="sxs-lookup"><span data-stu-id="79d7c-200">Stopped</span></span>
- <span data-ttu-id="79d7c-201">［ブロック済み］</span><span class="sxs-lookup"><span data-stu-id="79d7c-201">Blocked</span></span>
- <span data-ttu-id="79d7c-202">Suspended</span><span class="sxs-lookup"><span data-stu-id="79d7c-202">Suspended</span></span>
- <span data-ttu-id="79d7c-203">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="79d7c-203">Disconnected</span></span>
- <span data-ttu-id="79d7c-204">中断中</span><span class="sxs-lookup"><span data-stu-id="79d7c-204">Suspending</span></span>
- <span data-ttu-id="79d7c-205">停止中</span><span class="sxs-lookup"><span data-stu-id="79d7c-205">Stopping</span></span>

<span data-ttu-id="79d7c-206">`Suspend-Job`**実行中** の状態のワークフロージョブのみを中断します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-206">`Suspend-Job` suspends only workflow jobs in the **Running** state.</span></span>

<span data-ttu-id="79d7c-207">ジョブの状態の詳細については、「 [Jobstate 列挙型](/dotnet/api/system.management.automation.jobstate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79d7c-207">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="79d7c-208">-Wait</span><span class="sxs-lookup"><span data-stu-id="79d7c-208">-Wait</span></span>

<span data-ttu-id="79d7c-209">ワークフロージョブが中断状態になるまで、このコマンドレットによってコマンドプロンプトが抑制されることを示します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-209">Indicates that this cmdlet suppresses the command prompt until the workflow job is in the suspended state.</span></span> <span data-ttu-id="79d7c-210">既定では、 `Suspend-Job` ワークフロージョブがまだ中断状態になっていない場合でも、は直ちにを返します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-210">By default, `Suspend-Job` returns immediately, even if the workflow job is not yet in the suspended state.</span></span>

<span data-ttu-id="79d7c-211">**Wait** パラメーターは、 `Suspend-Job` コマンドをコマンドレットにパイプ処理することと同じです `Wait-Job` 。</span><span class="sxs-lookup"><span data-stu-id="79d7c-211">The **Wait** parameter is equivalent to piping a `Suspend-Job` command to the `Wait-Job` cmdlet.</span></span>

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

### <span data-ttu-id="79d7c-212">-Confirm</span><span class="sxs-lookup"><span data-stu-id="79d7c-212">-Confirm</span></span>

<span data-ttu-id="79d7c-213">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-213">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="79d7c-214">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="79d7c-214">-WhatIf</span></span>

<span data-ttu-id="79d7c-215">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-215">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="79d7c-216">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="79d7c-216">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="79d7c-217">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="79d7c-217">CommonParameters</span></span>

<span data-ttu-id="79d7c-218">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="79d7c-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="79d7c-219">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79d7c-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="79d7c-220">入力</span><span class="sxs-lookup"><span data-stu-id="79d7c-220">INPUTS</span></span>

### <span data-ttu-id="79d7c-221">システム管理. ジョブ</span><span class="sxs-lookup"><span data-stu-id="79d7c-221">System.Management.Automation.Job</span></span>

<span data-ttu-id="79d7c-222">このコマンドレットには、すべての種類のジョブをパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-222">You can pipe all types of jobs to this cmdlet.</span></span> <span data-ttu-id="79d7c-223">ただし、が `Suspend-Job` サポートされていない種類のジョブを取得すると、終了エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-223">However, if `Suspend-Job` gets a job of an unsupported type, it returns a terminating error.</span></span>

## <span data-ttu-id="79d7c-224">出力</span><span class="sxs-lookup"><span data-stu-id="79d7c-224">OUTPUTS</span></span>

### <span data-ttu-id="79d7c-225">システム管理. ジョブ</span><span class="sxs-lookup"><span data-stu-id="79d7c-225">System.Management.Automation.Job</span></span>
<span data-ttu-id="79d7c-226">このコマンドレットは、中断されたジョブを返します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-226">This cmdlet returns the jobs that it suspended.</span></span>

## <span data-ttu-id="79d7c-227">注</span><span class="sxs-lookup"><span data-stu-id="79d7c-227">NOTES</span></span>

- <span data-ttu-id="79d7c-228">中断されているジョブを保存するメカニズムと保存先の場所は、ジョブの種類によって異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="79d7c-228">The mechanism and location for saving a suspended job might vary depending on the job type.</span></span> <span data-ttu-id="79d7c-229">たとえば、中断されているワークフロー ジョブは、既定でフラット ファイル ストアに保存されますが、データベースに保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-229">For example, suspended workflow jobs are saved in a flat file store by default, but can also be saved in a database.</span></span>
- <span data-ttu-id="79d7c-230">実行状態ではないワークフロージョブを送信すると、に `Suspend-Job` 警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="79d7c-230">If you submit a workflow job that is not in the Running state, `Suspend-Job` displays a warning message.</span></span> <span data-ttu-id="79d7c-231">警告を抑制するには、値が SilentlyContinue の **Warnings action** 共通パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-231">To suppress the warning, use the **WarningAction** common parameter with a value of SilentlyContinue.</span></span>

  <span data-ttu-id="79d7c-232">ジョブが中断をサポートする種類ではない場合、は `Suspend-Job` 終了エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-232">If a job is not of a type that supports suspending, `Suspend-Job` returns a terminating error.</span></span>

- <span data-ttu-id="79d7c-233">中断されているワークフロージョブ (このコマンドレットによって中断されたジョブを含む) を検索するには、コマンドレットの **state** パラメーターを使用して `Get-Job` 、中断状態のワークフロージョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-233">To find the workflow jobs that are suspended, including those that were suspended by this cmdlet, use the **State** parameter of the `Get-Job` cmdlet to get workflow jobs in the Suspended state.</span></span>
- <span data-ttu-id="79d7c-234">一部のジョブの種類には、Windows PowerShell によるジョブの中断が許可されないオプションまたはプロパティを持つもあります。</span><span class="sxs-lookup"><span data-stu-id="79d7c-234">Some job types have options or properties that prevent Windows PowerShell from suspending the job.</span></span>
  <span data-ttu-id="79d7c-235">ジョブを中断する試みが失敗した場合は、ジョブのオプションとプロパティで中断が許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="79d7c-235">If attempts to suspend the job fail, verify that the job options and properties allow for suspending.</span></span>

## <span data-ttu-id="79d7c-236">関連リンク</span><span class="sxs-lookup"><span data-stu-id="79d7c-236">RELATED LINKS</span></span>

[<span data-ttu-id="79d7c-237">Get-Job</span><span class="sxs-lookup"><span data-stu-id="79d7c-237">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="79d7c-238">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="79d7c-238">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="79d7c-239">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="79d7c-239">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="79d7c-240">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="79d7c-240">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="79d7c-241">Start-Job</span><span class="sxs-lookup"><span data-stu-id="79d7c-241">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="79d7c-242">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="79d7c-242">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="79d7c-243">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="79d7c-243">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="79d7c-244">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="79d7c-244">Wait-Job</span></span>](Wait-Job.md)
