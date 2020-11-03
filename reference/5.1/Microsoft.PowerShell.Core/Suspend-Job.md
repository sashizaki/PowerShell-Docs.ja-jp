---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/suspend-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Job
ms.openlocfilehash: 6ab50342e963832d89b3dfc4128a22fc16405926
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212723"
---
# <span data-ttu-id="97184-103">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="97184-103">Suspend-Job</span></span>

## <span data-ttu-id="97184-104">概要</span><span class="sxs-lookup"><span data-stu-id="97184-104">SYNOPSIS</span></span>
<span data-ttu-id="97184-105">ワークフロー ジョブを一時的に停止します。</span><span class="sxs-lookup"><span data-stu-id="97184-105">Temporarily stops workflow jobs.</span></span>

## <span data-ttu-id="97184-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="97184-106">SYNTAX</span></span>

### <span data-ttu-id="97184-107">SessionIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="97184-107">SessionIdParameterSet (Default)</span></span>

```
Suspend-Job [-Force] [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="97184-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="97184-108">JobParameterSet</span></span>

```
Suspend-Job [-Job] <Job[]> [-Force] [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="97184-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="97184-109">NameParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="97184-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="97184-110">InstanceIdParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="97184-111">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="97184-111">FilterParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="97184-112">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="97184-112">StateParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="97184-113">Description</span><span class="sxs-lookup"><span data-stu-id="97184-113">DESCRIPTION</span></span>
<span data-ttu-id="97184-114">**Suspend ジョブ** コマンドレットは、ワークフロージョブを中断します。</span><span class="sxs-lookup"><span data-stu-id="97184-114">The **Suspend-Job** cmdlet suspends workflow jobs.</span></span>
<span data-ttu-id="97184-115">中断とは、一時的にワークフロージョブを中断または一時停止することを意味します。</span><span class="sxs-lookup"><span data-stu-id="97184-115">Suspend means to temporarily interrupt or pause a workflow job.</span></span>
<span data-ttu-id="97184-116">ワークフローを実行しているユーザーは、このコマンドレットを使用してワークフローを中断できます。</span><span class="sxs-lookup"><span data-stu-id="97184-116">This cmdlet allows users who are running workflows to suspend the workflow.</span></span>
<span data-ttu-id="97184-117">ワークフローを中断するワークフロー内のコマンドである、中断ワークフローアクティビティを補完し https://go.microsoft.com/fwlink/?LinkId=267141 ます。</span><span class="sxs-lookup"><span data-stu-id="97184-117">It complements the Suspend-Workflowhttps://go.microsoft.com/fwlink/?LinkId=267141 activity, which is a command in the workflow that suspends the workflow.</span></span>

<span data-ttu-id="97184-118">**Suspend-Job** コマンドレットは、ワークフロー ジョブでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="97184-118">The **Suspend-Job** cmdlet works only on workflow jobs.</span></span>
<span data-ttu-id="97184-119">これは、Start-Job コマンドレットを使用して開始されたものなど、標準のバックグラウンドジョブでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="97184-119">It does not work on standard background jobs, such as those that are started by using the Start-Job cmdlet.</span></span>

<span data-ttu-id="97184-120">ワークフロー ジョブを識別するには、ジョブの PSJobTypeName プロパティで **PSWorkflowJob** の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="97184-120">To identify a workflow job, look for a value of PSWorkflowJob in the **PSJobTypeName** property of the job.</span></span>
<span data-ttu-id="97184-121">特定のカスタム ジョブの種類で **Suspend-Job** コマンドレットがサポートされているかどうかを確認する方法については、カスタムのジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="97184-121">To determine whether a particular custom job type supports the **Suspend-Job** cmdlet, see the help topics for the custom job type.</span></span>

<span data-ttu-id="97184-122">ワークフロー ジョブを中断すると、ワークフロー ジョブは次のチェックポイントまで実行された後で中断されます。その後、ワークフロー ジョブ オブジェクトが直ちに返されます。</span><span class="sxs-lookup"><span data-stu-id="97184-122">When you suspend a workflow job, the workflow job runs to the next checkpoint, suspends, and immediately returns a workflow job object.</span></span>
<span data-ttu-id="97184-123">ジョブを取得する前に中断が完了するまで待機するには、 **Suspend ジョブ** または Wait-Job コマンドレットの *wait* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="97184-123">To wait for the suspension to complete before getting the job, use the *Wait* parameter of **Suspend-Job** or the Wait-Job cmdlet.</span></span>
<span data-ttu-id="97184-124">ワークフロージョブが中断されている場合、ジョブの **State** プロパティの値は中断されます。</span><span class="sxs-lookup"><span data-stu-id="97184-124">When the workflow job is suspended, the value of the **State** property of the job is Suspended.</span></span>

<span data-ttu-id="97184-125">正しく中断できるかどうかはチェックポイントに依存します。</span><span class="sxs-lookup"><span data-stu-id="97184-125">Suspending correctly relies on checkpoints.</span></span>
<span data-ttu-id="97184-126">現在のジョブの状態、メタデータ、および出力がチェックポイントに保存されるため、状態やデータを失うことなくワークフロージョブを再開できます。</span><span class="sxs-lookup"><span data-stu-id="97184-126">The current job state, metadata, and output are saved in the checkpoint so the workflow job can be resumed without loss of state or data.</span></span>
<span data-ttu-id="97184-127">ワークフロージョブにチェックポイントがない場合、正常に中断することはできません。</span><span class="sxs-lookup"><span data-stu-id="97184-127">If the workflow job does not have checkpoints, it cannot be suspended correctly.</span></span>
<span data-ttu-id="97184-128">実行中のワークフローにチェックポイントを追加するには、 *PSPersist* ワークフロー共通パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="97184-128">To add checkpoints to a workflow that you are running, use the *PSPersist* workflow common parameter.</span></span>
<span data-ttu-id="97184-129">*Force* パラメーターを使用すると、ワークフロージョブを即座に中断し、チェックポイントのないワークフロージョブを中断できますが、操作によって状態とデータが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97184-129">You can use the *Force* parameter to suspend any workflow job immediately and to suspend a workflow job that does not have checkpoints, but the action could cause loss of state and data.</span></span>

<span data-ttu-id="97184-130">ワークフロージョブ ( **Psworkflowjob** ) などのカスタムジョブの種類で job コマンドレットを使用する前に、カスタムジョブの種類をサポートするモジュールをインポートします。そのためには、Import-Module コマンドレットを使用するか、またはモジュールのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="97184-130">Before you use a Job cmdlet on a custom job type, such as a workflow job ( **PSWorkflowJob** ) import the module that supports the custom job type, either by using the Import-Module cmdlet or using or using a cmdlet in the module.</span></span>

<span data-ttu-id="97184-131">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="97184-131">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="97184-132">例</span><span class="sxs-lookup"><span data-stu-id="97184-132">EXAMPLES</span></span>

### <span data-ttu-id="97184-133">例 1: 名前を指定してワークフロージョブを中断する</span><span class="sxs-lookup"><span data-stu-id="97184-133">Example 1: Suspend a workflow job by name</span></span>

```
The first command creates the Get-SystemLog workflow. The workflow uses the CheckPoint-Workflow activity to define a checkpoint in the workflow.
#Sample WorkflowWorkflow Get-SystemLog
{
    $Events = Get-WinEvent -LogName System
    CheckPoint-Workflow
    InlineScript {\\Server01\Scripts\Analyze-SystemEvents.ps1 -Events $Events}
}

The second command uses the *AsJob* parameter that is common to all workflows to run the Get-SystemLog workflow as a background job. The command uses the *JobName* workflow common parameter to specify a friendly name for the workflow job.
PS C:\> Get-SystemLog -AsJob -JobName "Get-SystemLogJob"

The third command uses the **Get-Job** cmdlet to get the Get-SystemLogJob workflow job. The output shows that the value of the **PSJobTypeName** property is PSWorkflowJob.
PS C:\> Get-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Running     True            localhost   Get-SystemLog

The fourth command uses the **Suspend-Job** cmdlet to suspend the Get-SystemLogJob job. The job runs to the checkpoint and then suspends.
PS C:\> Suspend-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Suspended   True            localhost   Get-SystemLog
```

<span data-ttu-id="97184-134">この例では、ワークフロー ジョブを中断する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="97184-134">This example shows how to suspend a workflow job.</span></span>

### <span data-ttu-id="97184-135">例 2: ワークフロージョブを中断および再開する</span><span class="sxs-lookup"><span data-stu-id="97184-135">Example 2: Suspend and resume a workflow job</span></span>

```
The first command suspends the LogWorkflowJob job.The command returns immediately. The output shows that the workflow job is still running, even though it is being suspended.
PS C:\> Suspend-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow

The second command uses the **Get-Job** cmdlet to get the LogWorkflowJob job. The output shows that the workflow job suspended successfully.
PS C:\> Get-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Suspended     True            localhost            LogWorkflow

The third command uses the **Get-Job** cmdlet to get the LogWorkflowJob job and the Resume-Job cmdlet to resume it. The output shows that the workflow job resumed successfully and is now running.
PS C:\> Get-Job -Name LogWorkflowJob | Resume-Job
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow
```

<span data-ttu-id="97184-136">この例では、ワークフロー ジョブを中断し、再開する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="97184-136">This example shows how to suspend and resume a workflow job.</span></span>

### <span data-ttu-id="97184-137">例 3: リモートコンピューター上のワークフロージョブを中断する</span><span class="sxs-lookup"><span data-stu-id="97184-137">Example 3: Suspend a workflow job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01 -Scriptblock {Suspend-Job -Filter @{CustomID="031589"}
```

<span data-ttu-id="97184-138">このコマンドは、Invoke-Command コマンドレットを使用して、Srv01 リモートコンピューター上のワークフロージョブを中断します。</span><span class="sxs-lookup"><span data-stu-id="97184-138">This command uses the Invoke-Command cmdlet to suspend a workflow job on the Srv01 remote computer.</span></span>
<span data-ttu-id="97184-139">*Filter* パラメーターの値は、customid 値を指定するハッシュテーブルです。</span><span class="sxs-lookup"><span data-stu-id="97184-139">The value of the *Filter* parameter is a hash table that specifies a CustomID value.</span></span>
<span data-ttu-id="97184-140">この **CustomID** は、ジョブのメタデータ ( **PSPrivateMetadata** ) です。</span><span class="sxs-lookup"><span data-stu-id="97184-140">This **CustomID** is job metadata ( **PSPrivateMetadata** ).</span></span>

### <span data-ttu-id="97184-141">例 4: ワークフロージョブが中断されるまで待機する</span><span class="sxs-lookup"><span data-stu-id="97184-141">Example 4: Wait for the workflow job to suspend</span></span>

```
PS C:\> Suspend-Job VersionCheck -Wait
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
 5     VersionCheck  PSWorkflowJob      Suspended     True            localhost            LogWorkflow
```

<span data-ttu-id="97184-142">このコマンドは、VersionCheck ワークフロー ジョブを中断します。</span><span class="sxs-lookup"><span data-stu-id="97184-142">This command suspends the VersionCheck workflow job.</span></span>
<span data-ttu-id="97184-143">このコマンドでは、 *Wait* パラメーターを使用して、ワークフロー ジョブが中断されるのを待機しています。</span><span class="sxs-lookup"><span data-stu-id="97184-143">The command uses the *Wait* parameter to wait until the workflow job is suspended.</span></span>
<span data-ttu-id="97184-144">ワークフロージョブが次のチェックポイントまで実行され、中断されると、コマンドが完了し、ジョブオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="97184-144">When the workflow job runs to the next checkpoint and is suspended, the command finishes and returns the job object.</span></span>

### <span data-ttu-id="97184-145">例 5: ワークフロージョブを強制的に中断する</span><span class="sxs-lookup"><span data-stu-id="97184-145">Example 5: Force a workflow job to suspend</span></span>

```
PS C:\> Suspend-Job Maintenance -Force
```

<span data-ttu-id="97184-146">このコマンドは、強制的に Maintenance ワークフロー ジョブを中断します。</span><span class="sxs-lookup"><span data-stu-id="97184-146">This command suspends the Maintenance workflow job forcibly.</span></span>
<span data-ttu-id="97184-147">メンテナンスジョブにチェックポイントがありません。</span><span class="sxs-lookup"><span data-stu-id="97184-147">The Maintenance job does not have checkpoints.</span></span>
<span data-ttu-id="97184-148">正しく中断することができず、正常に再開されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97184-148">It cannot be suspended correctly and might not resume correctly.</span></span>

## <span data-ttu-id="97184-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="97184-149">PARAMETERS</span></span>

### <span data-ttu-id="97184-150">-Filter</span><span class="sxs-lookup"><span data-stu-id="97184-150">-Filter</span></span>
<span data-ttu-id="97184-151">条件のハッシュテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="97184-151">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="97184-152">このコマンドレットは、すべての条件に適合するジョブを中断します。</span><span class="sxs-lookup"><span data-stu-id="97184-152">This cmdlet suspends jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="97184-153">ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="97184-153">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

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

### <span data-ttu-id="97184-154">-Force</span><span class="sxs-lookup"><span data-stu-id="97184-154">-Force</span></span>
<span data-ttu-id="97184-155">ワークフロー ジョブを即座に中断します。</span><span class="sxs-lookup"><span data-stu-id="97184-155">Suspends the workflow job immediately.</span></span>
<span data-ttu-id="97184-156">この操作により、状態とデータが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97184-156">This action could cause a loss of state and data.</span></span>

<span data-ttu-id="97184-157">既定では、 **Suspend-Job** は、ワークフロー ジョブを次のチェックポイントまで実行した後で中断します。</span><span class="sxs-lookup"><span data-stu-id="97184-157">By default, **Suspend-Job** lets the workflow job run until the next checkpoint and then suspends it.</span></span>
<span data-ttu-id="97184-158">このパラメーターを使用すると、チェックポイントがないワークフロー ジョブも中断できます。</span><span class="sxs-lookup"><span data-stu-id="97184-158">You can also use this parameter to suspend workflow jobs that do not have checkpoints.</span></span>

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

### <span data-ttu-id="97184-159">-Id</span><span class="sxs-lookup"><span data-stu-id="97184-159">-Id</span></span>
<span data-ttu-id="97184-160">このコマンドレットが中断するジョブの Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="97184-160">Specifies the IDs of jobs that this cmdlet suspends.</span></span>

<span data-ttu-id="97184-161">ID は、現在のセッションでジョブを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="97184-161">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="97184-162">インスタンス ID よりも覚えやすく、入力する方が簡単ですが、現在のセッションでのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="97184-162">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="97184-163">1つ以上の Id をコンマで区切って入力できます。</span><span class="sxs-lookup"><span data-stu-id="97184-163">You can type one or more IDs, separated by commas.</span></span>
<span data-ttu-id="97184-164">ジョブの ID を検索するには、Get-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="97184-164">To find the ID of a job, use the Get-Job cmdlet.</span></span>

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

### <span data-ttu-id="97184-165">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="97184-165">-InstanceId</span></span>
<span data-ttu-id="97184-166">このコマンドレットが中断するジョブのインスタンス Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="97184-166">Specifies the instance IDs of jobs that this cmdlet suspends.</span></span>
<span data-ttu-id="97184-167">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="97184-167">The default is all jobs.</span></span>

<span data-ttu-id="97184-168">インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="97184-168">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="97184-169">ジョブのインスタンス ID を調べるには、 **Get-Job** を使用します。</span><span class="sxs-lookup"><span data-stu-id="97184-169">To find the instance ID of a job, use **Get-Job** .</span></span>

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

### <span data-ttu-id="97184-170">-ジョブ</span><span class="sxs-lookup"><span data-stu-id="97184-170">-Job</span></span>
<span data-ttu-id="97184-171">このコマンドレットが停止するワークフロージョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="97184-171">Specifies the workflow jobs that this cmdlet stops.</span></span>
<span data-ttu-id="97184-172">ワークフロー ジョブが格納されている変数、またはワークフロー ジョブを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="97184-172">Enter a variable that contains the workflow jobs or a command that gets the workflow jobs.</span></span>
<span data-ttu-id="97184-173">パイプを使用してワークフロー ジョブを **Suspend-Job** コマンドレットに渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="97184-173">You can also pipe workflow jobs to the **Suspend-Job** cmdlet.</span></span>

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

### <span data-ttu-id="97184-174">-Name</span><span class="sxs-lookup"><span data-stu-id="97184-174">-Name</span></span>
<span data-ttu-id="97184-175">このコマンドレットが中断するジョブのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="97184-175">Specifies friendly names of jobs that this cmdlet suspends.</span></span>
<span data-ttu-id="97184-176">1 つまたは複数のワークフロー ジョブ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="97184-176">Enter one or more workflow job names.</span></span>
<span data-ttu-id="97184-177">ワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="97184-177">Wildcard characters are supported.</span></span>

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

### <span data-ttu-id="97184-178">-状態</span><span class="sxs-lookup"><span data-stu-id="97184-178">-State</span></span>
<span data-ttu-id="97184-179">ジョブの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="97184-179">Specifies a job state.</span></span>
<span data-ttu-id="97184-180">このコマンドレットは、指定された状態のジョブのみを停止します。</span><span class="sxs-lookup"><span data-stu-id="97184-180">This cmdlet stops only jobs in the specified state.</span></span>
<span data-ttu-id="97184-181">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="97184-181">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="97184-182">NotStarted</span><span class="sxs-lookup"><span data-stu-id="97184-182">NotStarted</span></span>
- <span data-ttu-id="97184-183">実行中</span><span class="sxs-lookup"><span data-stu-id="97184-183">Running</span></span>
- <span data-ttu-id="97184-184">完了</span><span class="sxs-lookup"><span data-stu-id="97184-184">Completed</span></span>
- <span data-ttu-id="97184-185">失敗</span><span class="sxs-lookup"><span data-stu-id="97184-185">Failed</span></span>
- <span data-ttu-id="97184-186">停止済み</span><span class="sxs-lookup"><span data-stu-id="97184-186">Stopped</span></span>
- <span data-ttu-id="97184-187">Blocked</span><span class="sxs-lookup"><span data-stu-id="97184-187">Blocked</span></span>
- <span data-ttu-id="97184-188">Suspended</span><span class="sxs-lookup"><span data-stu-id="97184-188">Suspended</span></span>
- <span data-ttu-id="97184-189">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="97184-189">Disconnected</span></span>
- <span data-ttu-id="97184-190">中断中</span><span class="sxs-lookup"><span data-stu-id="97184-190">Suspending</span></span>
- <span data-ttu-id="97184-191">停止中</span><span class="sxs-lookup"><span data-stu-id="97184-191">Stopping</span></span>

<span data-ttu-id="97184-192">**Suspend-ジョブ** は、 **実行** 状態のワークフロージョブのみを中断します。</span><span class="sxs-lookup"><span data-stu-id="97184-192">**Suspend-Job** suspends only workflow jobs in the **Running** state.</span></span>

<span data-ttu-id="97184-193">ジョブの状態の詳細については、MSDN ライブラリの「 [Jobstate 列挙型](https://msdn.microsoft.com/library/system.management.automation.jobstate) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97184-193">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

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

### <span data-ttu-id="97184-194">-Wait</span><span class="sxs-lookup"><span data-stu-id="97184-194">-Wait</span></span>
<span data-ttu-id="97184-195">ワークフロージョブが中断状態になるまで、このコマンドレットによってコマンドプロンプトが抑制されることを示します。</span><span class="sxs-lookup"><span data-stu-id="97184-195">Indicates that this cmdlet suppresses the command prompt until the workflow job is in the suspended state.</span></span>
<span data-ttu-id="97184-196">既定では、 **中断ジョブ** は、ワークフロージョブがまだ中断状態になっていない場合でも、直ちに返されます。</span><span class="sxs-lookup"><span data-stu-id="97184-196">By default, **Suspend-Job** returns immediately, even if the workflow job is not yet in the suspended state.</span></span>

<span data-ttu-id="97184-197">*Wait* パラメーターは、 **Suspend ジョブ** を実行する **コマンドレットに** 渡します。</span><span class="sxs-lookup"><span data-stu-id="97184-197">The *Wait* parameter is equivalent to piping a **Suspend-Job** command to the **Wait-Job** cmdlet.</span></span>

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

### <span data-ttu-id="97184-198">-Confirm</span><span class="sxs-lookup"><span data-stu-id="97184-198">-Confirm</span></span>
<span data-ttu-id="97184-199">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97184-199">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="97184-200">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="97184-200">-WhatIf</span></span>
<span data-ttu-id="97184-201">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="97184-201">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="97184-202">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="97184-202">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="97184-203">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="97184-203">CommonParameters</span></span>
<span data-ttu-id="97184-204">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="97184-204">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="97184-205">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97184-205">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="97184-206">入力</span><span class="sxs-lookup"><span data-stu-id="97184-206">INPUTS</span></span>

### <span data-ttu-id="97184-207">システム管理. ジョブ</span><span class="sxs-lookup"><span data-stu-id="97184-207">System.Management.Automation.Job</span></span>
<span data-ttu-id="97184-208">このコマンドレットには、すべての種類のジョブをパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="97184-208">You can pipe all types of jobs to this cmdlet.</span></span>
<span data-ttu-id="97184-209">ただし、 **中断ジョブ** がサポートされていない種類のジョブを取得すると、終了エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="97184-209">However, if **Suspend-Job** gets a job of an unsupported type, it returns a terminating error.</span></span>

## <span data-ttu-id="97184-210">出力</span><span class="sxs-lookup"><span data-stu-id="97184-210">OUTPUTS</span></span>

### <span data-ttu-id="97184-211">システム管理. ジョブ</span><span class="sxs-lookup"><span data-stu-id="97184-211">System.Management.Automation.Job</span></span>
<span data-ttu-id="97184-212">このコマンドレットは、中断されたジョブを返します。</span><span class="sxs-lookup"><span data-stu-id="97184-212">This cmdlet returns the jobs that it suspended.</span></span>

## <span data-ttu-id="97184-213">注</span><span class="sxs-lookup"><span data-stu-id="97184-213">NOTES</span></span>

* <span data-ttu-id="97184-214">中断されているジョブを保存するメカニズムと保存先の場所は、ジョブの種類によって異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97184-214">The mechanism and location for saving a suspended job might vary depending on the job type.</span></span> <span data-ttu-id="97184-215">たとえば、中断されているワークフロー ジョブは、既定でフラット ファイル ストアに保存されますが、データベースに保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="97184-215">For example, suspended workflow jobs are saved in a flat file store by default, but can also be saved in a database.</span></span>
* <span data-ttu-id="97184-216">Running 状態にないワークフロー ジョブを送信すると、 **Suspend-Job** は警告メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="97184-216">If you submit a workflow job that is not in the Running state, **Suspend-Job** displays a warning message.</span></span> <span data-ttu-id="97184-217">警告を抑制するには、値が SilentlyContinue の *Warnings action* 共通パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="97184-217">To suppress the warning, use the *WarningAction* common parameter with a value of SilentlyContinue.</span></span>

  <span data-ttu-id="97184-218">ジョブが中断をサポートする種類ではない場合、 **中断ジョブ** は終了エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="97184-218">If a job is not of a type that supports suspending, **Suspend-Job** returns a terminating error.</span></span>

* <span data-ttu-id="97184-219">中断されているワークフロージョブ (このコマンドレットによって中断されたジョブを含む) を検索するには、 **get-help** コマンドレットの *state* パラメーターを使用して、中断状態のワークフロージョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="97184-219">To find the workflow jobs that are suspended, including those that were suspended by this cmdlet, use the *State* parameter of the **Get-Job** cmdlet to get workflow jobs in the Suspended state.</span></span>
* <span data-ttu-id="97184-220">一部のジョブの種類には、Windows PowerShell によるジョブの中断が許可されないオプションまたはプロパティを持つもあります。</span><span class="sxs-lookup"><span data-stu-id="97184-220">Some job types have options or properties that prevent Windows PowerShell from suspending the job.</span></span> <span data-ttu-id="97184-221">ジョブを中断する試みが失敗した場合は、ジョブのオプションとプロパティで中断が許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="97184-221">If attempts to suspend the job fail, verify that the job options and properties allow for suspending.</span></span>

## <span data-ttu-id="97184-222">関連リンク</span><span class="sxs-lookup"><span data-stu-id="97184-222">RELATED LINKS</span></span>

[<span data-ttu-id="97184-223">Get-Job</span><span class="sxs-lookup"><span data-stu-id="97184-223">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="97184-224">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="97184-224">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="97184-225">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="97184-225">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="97184-226">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="97184-226">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="97184-227">Start-Job</span><span class="sxs-lookup"><span data-stu-id="97184-227">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="97184-228">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="97184-228">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="97184-229">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="97184-229">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="97184-230">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="97184-230">Wait-Job</span></span>](Wait-Job.md)
