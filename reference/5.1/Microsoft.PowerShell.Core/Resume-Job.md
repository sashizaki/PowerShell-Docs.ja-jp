---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/resume-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Job
ms.openlocfilehash: 6d08d9053e100cb53d37a6e4931d118f90c35a6a
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388537"
---
# <span data-ttu-id="b6832-103">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="b6832-103">Resume-Job</span></span>

## <span data-ttu-id="b6832-104">概要</span><span class="sxs-lookup"><span data-stu-id="b6832-104">SYNOPSIS</span></span>
<span data-ttu-id="b6832-105">中断されたジョブを再開します。</span><span class="sxs-lookup"><span data-stu-id="b6832-105">Restarts a suspended job.</span></span>

## <span data-ttu-id="b6832-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b6832-106">SYNTAX</span></span>

### <span data-ttu-id="b6832-107">SessionIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="b6832-107">SessionIdParameterSet (Default)</span></span>

```
Resume-Job [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b6832-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="b6832-108">JobParameterSet</span></span>

```
Resume-Job [-Job] <Job[]> [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b6832-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="b6832-109">NameParameterSet</span></span>

```
Resume-Job [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b6832-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="b6832-110">InstanceIdParameterSet</span></span>

```
Resume-Job [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b6832-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="b6832-111">StateParameterSet</span></span>

```
Resume-Job [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b6832-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="b6832-112">FilterParameterSet</span></span>

```
Resume-Job [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b6832-113">Description</span><span class="sxs-lookup"><span data-stu-id="b6832-113">DESCRIPTION</span></span>

<span data-ttu-id="b6832-114">コマンドレット `Resume-Job` `Suspend-Job` は、コマンドレットや [about_Suspend ワークフロー](../PSWorkflow/about/about_Suspend-Workflow.md) アクティビティなどを使用して、中断されたワークフロージョブを再開します。</span><span class="sxs-lookup"><span data-stu-id="b6832-114">The `Resume-Job` cmdlet resumes a workflow job that was suspended, such as by using the `Suspend-Job` cmdlet or the [about_Suspend-Workflow](../PSWorkflow/about/about_Suspend-Workflow.md) activity.</span></span> <span data-ttu-id="b6832-115">ワークフロージョブが再開されると、ジョブエンジンによって、状態、メタデータ、および保存されたリソース (チェックポイントなど) からの出力が再構築されます。</span><span class="sxs-lookup"><span data-stu-id="b6832-115">When a workflow job resumes, the job engine reconstructs the state, metadata, and output from saved resources, such as checkpoints.</span></span> <span data-ttu-id="b6832-116">ジョブは、状態またはデータを失うことなく再開されます。</span><span class="sxs-lookup"><span data-stu-id="b6832-116">The job is restarted without any loss of state or data.</span></span>
<span data-ttu-id="b6832-117">ジョブの状態は、 **Suspended** から **Running** に変更されます。</span><span class="sxs-lookup"><span data-stu-id="b6832-117">The job state is changed from **Suspended** to **Running**.</span></span>

<span data-ttu-id="b6832-118">のパラメーターを使用し `Resume-Job` て、名前、ID、インスタンス ID、またはパイプを使用してジョブを選択し `Get-Job` ます (コマンドレットによって返されるものなど) `Resume-Job` 。</span><span class="sxs-lookup"><span data-stu-id="b6832-118">Use the parameters of `Resume-Job` to select jobs by name, ID, instance ID or pipe a job object, such as one returned by the `Get-Job` cmdlet, to `Resume-Job`.</span></span> <span data-ttu-id="b6832-119">プロパティ フィルターを使用して再開するジョブを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="b6832-119">You can also use a property filter to select a job to be resumed.</span></span>

<span data-ttu-id="b6832-120">既定では、 `Resume-Job` すべてのジョブがまだ再開されていない場合でも、は直ちにを返します。</span><span class="sxs-lookup"><span data-stu-id="b6832-120">By default, `Resume-Job` returns immediately, even though all jobs might not yet be resumed.</span></span> <span data-ttu-id="b6832-121">指定したすべてのジョブが再開されるまでコマンド プロンプトが表示されないようにするには、 **Wait** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b6832-121">To suppress the command prompt until all specified jobs are resumed, use the **Wait** parameter.</span></span>

<span data-ttu-id="b6832-122">`Resume-Job`コマンドレットは、ワークフロージョブなど、カスタムのジョブの種類でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="b6832-122">The `Resume-Job` cmdlet works only on custom job types, such as workflow jobs.</span></span> <span data-ttu-id="b6832-123">コマンドレットを使用して開始されたものなど、標準のバックグラウンドジョブでは機能しません `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="b6832-123">It does not work on standard background jobs, such as those that are started by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="b6832-124">サポートされていない種類のジョブを送信すると、は `Resume-Job` 終了エラーを生成し、実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="b6832-124">If you submit a job of an unsupported type, `Resume-Job` generates a terminating error and stops running.</span></span>

<span data-ttu-id="b6832-125">ワークフロー ジョブを識別するには、ジョブの **PSJobTypeName** プロパティで **PSWorkflowJob** の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="b6832-125">To identify a workflow job, look for a value of **PSWorkflowJob** in the **PSJobTypeName** property of the job.</span></span> <span data-ttu-id="b6832-126">特定のカスタムジョブの種類がコマンドレットをサポートしているかどうかを判断するには、 `Resume-Job` カスタムジョブの種類のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6832-126">To determine whether a particular custom job type supports the `Resume-Job` cmdlet, see the help topics for the custom job type.</span></span>

<span data-ttu-id="b6832-127">カスタムのジョブの種類で Job コマンドレットを使用する前に、カスタムのジョブの種類をサポートするモジュールをインポートします。そのためには、コマンドレットを使用するか、 `Import-Module` モジュールのコマンドレットを取得または使用します。</span><span class="sxs-lookup"><span data-stu-id="b6832-127">Before using a Job cmdlet on a custom job type, import the module that supports the custom job type, either by using the `Import-Module` cmdlet or getting or using a cmdlet in the module.</span></span>

<span data-ttu-id="b6832-128">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b6832-128">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="b6832-129">例</span><span class="sxs-lookup"><span data-stu-id="b6832-129">EXAMPLES</span></span>

### <span data-ttu-id="b6832-130">例 1: ID でジョブを再開する</span><span class="sxs-lookup"><span data-stu-id="b6832-130">Example 1: Resume a job by ID</span></span>

<span data-ttu-id="b6832-131">この例のコマンドは、ジョブが中断状態のワークフロー ジョブであることを確認した後、このジョブを再開します。</span><span class="sxs-lookup"><span data-stu-id="b6832-131">The commands in this example verify that the job is a suspended workflow job and then resume the job.</span></span> <span data-ttu-id="b6832-132">最初のコマンドは、 `Get-Job` コマンドレットを使用してジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="b6832-132">The first command uses the `Get-Job` cmdlet to get the job.</span></span> <span data-ttu-id="b6832-133">出力に、ジョブが中断状態のワークフロー ジョブであることが示されています。</span><span class="sxs-lookup"><span data-stu-id="b6832-133">The output shows that the job is a suspended workflow job.</span></span> <span data-ttu-id="b6832-134">2番目のコマンドは、コマンドレットの **id** パラメーターを使用して `Resume-Job` 、 **id** 値が4のジョブを再開します。</span><span class="sxs-lookup"><span data-stu-id="b6832-134">The second command uses the **Id** parameter of the `Resume-Job` cmdlet to resume the job with an **Id** value of 4.</span></span>

```
PS C:\> Get-Job EventJob
Id     Name            PSJobTypeName   State         HasMoreData     Location   Command
--     ----            -------------   -----         -----------     --------   -------
4      EventJob        PSWorkflowJob   Suspended     True            Server01   \\Script\Share\Event.ps1

PS C:\> Resume-Job -Id 4
```

### <span data-ttu-id="b6832-135">例 2: 名前を指定してジョブを再開する</span><span class="sxs-lookup"><span data-stu-id="b6832-135">Example 2: Resume a job by name</span></span>

<span data-ttu-id="b6832-136">このコマンドは、 **Name** パラメーターを使用して、ローカル コンピューター上の複数のワークフロー ジョブを再開します。</span><span class="sxs-lookup"><span data-stu-id="b6832-136">This command uses the **Name** parameter to resume several workflow jobs on the local computer.</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest*
```

### <span data-ttu-id="b6832-137">例 3: カスタムプロパティ値を使用する</span><span class="sxs-lookup"><span data-stu-id="b6832-137">Example 3: Use custom property values</span></span>

<span data-ttu-id="b6832-138">このコマンドは、カスタム プロパティ値を使用して、再開するワークフロー ジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="b6832-138">This command uses the value of a custom property to identify the workflow job to resume.</span></span> <span data-ttu-id="b6832-139">このコマンドは、 **Filter** パラメーターを使用して、 **CustomID** プロパティでワークフロー ジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="b6832-139">It uses the **Filter** parameter to identify the workflow job by its **CustomID** property.</span></span> <span data-ttu-id="b6832-140">さらに、 **State** パラメーターを使用して、再開操作を開始する前に、ワークフロー ジョブが中断状態にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6832-140">It also uses the **State** parameter to verify that the workflow job is suspended, before it tries to resume it.</span></span>

```
PS C:\> Resume-Job -Filter @{CustomID="T091291"} -State Suspended
```

### <span data-ttu-id="b6832-141">例 4: リモートコンピューター上のすべての中断されたジョブを再開する</span><span class="sxs-lookup"><span data-stu-id="b6832-141">Example 4: Resume all suspended jobs on a remote computer</span></span>

<span data-ttu-id="b6832-142">このコマンドは、Srv01 リモート コンピューター上のすべての中断されているジョブを再開します。</span><span class="sxs-lookup"><span data-stu-id="b6832-142">This command resumes all suspended jobs on the Srv01 remote computer.</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01 -ScriptBlock {Get-Job -State Suspended | Resume-Job}
```

<span data-ttu-id="b6832-143">このコマンドは、コマンドレットを使用して、 `Invoke-Command` Srv01 コンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b6832-143">The command uses the `Invoke-Command` cmdlet to run a command on the Srv01 computer.</span></span> <span data-ttu-id="b6832-144">Remote コマンドは、コマンドレットの **State** パラメーターを使用して `Get-Job` 、コンピューター上のすべての中断されたジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="b6832-144">The remote command uses the **State** parameter of the `Get-Job` cmdlet to get all suspended jobs on the computer.</span></span> <span data-ttu-id="b6832-145">パイプライン演算子 () は、中断された `|` ジョブをコマンドレットに送信し `Resume-Job` ます。これにより、ジョブが再開されます。</span><span class="sxs-lookup"><span data-stu-id="b6832-145">A pipeline operator (`|`) sends the suspended jobs to the `Resume-Job` cmdlet, which resumes them.</span></span>

### <span data-ttu-id="b6832-146">例 5: ジョブが再開されるまで待機する</span><span class="sxs-lookup"><span data-stu-id="b6832-146">Example 5: Wait for jobs to resume</span></span>

<span data-ttu-id="b6832-147">このコマンドは、 **Wait** `Resume-Job` 指定されたすべてのジョブが再開された後にのみ、Wait パラメーターを使用してを返すように指示します。</span><span class="sxs-lookup"><span data-stu-id="b6832-147">This command uses the **Wait** parameter to direct `Resume-Job` to return only after all specified jobs are resumed.</span></span> <span data-ttu-id="b6832-148">**Wait** パラメーターは、ジョブが再開された後でスクリプトが続行されることを前提としているスクリプトで特に便利です。</span><span class="sxs-lookup"><span data-stu-id="b6832-148">The **Wait** parameter is especially useful in scripts that assume that jobs are resumed before the script continues.</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest* -Wait
```

### <span data-ttu-id="b6832-149">例 6: 自身を中断するワークフローを再開する</span><span class="sxs-lookup"><span data-stu-id="b6832-149">Example 6: Resume a workflow that suspends itself</span></span>

<span data-ttu-id="b6832-150">このコードサンプルは、 `Suspend-Workflow` ワークフロー内のアクティビティを示しています。</span><span class="sxs-lookup"><span data-stu-id="b6832-150">This code sample shows the `Suspend-Workflow` activity in a workflow.</span></span>

<span data-ttu-id="b6832-151">`Test-Suspend`Server01 コンピューター上のワークフロー。</span><span class="sxs-lookup"><span data-stu-id="b6832-151">The `Test-Suspend` workflow on the Server01 computer.</span></span> <span data-ttu-id="b6832-152">ワークフローを実行すると、ワークフローはアクティビティを実行 `Get-Date` し、結果を変数に格納し `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="b6832-152">When you run the workflow, the workflow runs the `Get-Date` activity and stores the result in the `$a` variable.</span></span> <span data-ttu-id="b6832-153">次に、アクティビティを実行し `Suspend-Workflow` ます。</span><span class="sxs-lookup"><span data-stu-id="b6832-153">Then it runs the `Suspend-Workflow` activity.</span></span> <span data-ttu-id="b6832-154">このアクティビティは、チェックポイントを取得し、ワークフローを中断した後、ワークフロー ジョブ オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="b6832-154">In response, it takes a checkpoint, suspends the workflow, and returns a workflow job object.</span></span> <span data-ttu-id="b6832-155">`Suspend-Workflow` ワークフローがジョブとして明示的に実行されていない場合でも、ワークフロージョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="b6832-155">`Suspend-Workflow` returns a workflow job object even if the workflow is not explicitly run as a job.</span></span>

<span data-ttu-id="b6832-156">`Resume-Job``Test-Suspend`Job8 のワークフローを再開します。</span><span class="sxs-lookup"><span data-stu-id="b6832-156">`Resume-Job` resumes the `Test-Suspend` workflow in Job8.</span></span> <span data-ttu-id="b6832-157">ここでは、 **Wait** パラメーターを使用して、ジョブが再開されるまでコマンド プロンプトを保持しています。</span><span class="sxs-lookup"><span data-stu-id="b6832-157">It uses the **Wait** parameter to hold the command prompt until the job is resumed.</span></span>

<span data-ttu-id="b6832-158">コマンドレットでは、 `Receive-Job` ワークフローの結果を取得し `Test-Suspend` ます。</span><span class="sxs-lookup"><span data-stu-id="b6832-158">The `Receive-Job` cmdlet gets the results of the `Test-Suspend` workflow.</span></span> <span data-ttu-id="b6832-159">ワークフローの最後のコマンドは、現在の日付と時刻の間の経過時間と、ワークフローが中断される前に変数に保存された日時を表す **TimeSpan** オブジェクトを返し `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="b6832-159">The final command in the workflow returns a **TimeSpan** object that represents the elapsed time between the current date and time and the date and time that was saved in the `$a` variable before the workflow was suspended.</span></span>

```
#SampleWorkflow
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

PS C:\> Test-Suspend -PSComputerName Server01
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Suspended     True            Server01             Test-Suspend

PS C:\> Resume-Job -Name "Job8" -Wait
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Running       True            Server01             Test-Suspend

PS C:\> Receive-Job -Name Job8
        Days              : 0
        Hours             : 0
        Minutes           : 0
        Seconds           : 19
        Milliseconds      : 823
        Ticks             : 198230041
        TotalDays         : 0.000229432917824074
        TotalHours        : 0.00550639002777778
        TotalMinutes      : 0.330383401666667
        TotalSeconds      : 19.8230041
        TotalMilliseconds : 19823.0041
        PSComputerName    : Server01
```

<span data-ttu-id="b6832-160">`Resume-Job`コマンドレットを使用すると、アクティビティを使用して中断されたワークフロージョブを再開でき `Suspend-Workflow` ます。</span><span class="sxs-lookup"><span data-stu-id="b6832-160">The `Resume-Job` cmdlet lets you resume a workflow job that was suspend by using the `Suspend-Workflow` activity.</span></span> <span data-ttu-id="b6832-161">このアクティビティは、ワークフロー内からワークフローを中断します。</span><span class="sxs-lookup"><span data-stu-id="b6832-161">This activity suspends a workflow from within a workflow.</span></span> <span data-ttu-id="b6832-162">ワークフローでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="b6832-162">It is valid only in workflows.</span></span>

<span data-ttu-id="b6832-163">の詳細については `Suspend-Workflow` 、「about_Suspend」 (.) を参照してください。/Psworkflow/about_Suspend/)。</span><span class="sxs-lookup"><span data-stu-id="b6832-163">For information about the `Suspend-Workflow`, see about_Suspend-Workflow](../PSWorkflow/about/about_Suspend-Workflow.md).</span></span>

## <span data-ttu-id="b6832-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b6832-164">PARAMETERS</span></span>

### <span data-ttu-id="b6832-165">-Filter</span><span class="sxs-lookup"><span data-stu-id="b6832-165">-Filter</span></span>

<span data-ttu-id="b6832-166">条件のハッシュテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b6832-166">Specifies a hash table of conditions.</span></span> <span data-ttu-id="b6832-167">このコマンドレットは、ハッシュテーブル内のすべての条件に適合するジョブを再開します。</span><span class="sxs-lookup"><span data-stu-id="b6832-167">This cmdlet resumes jobs that satisfy all of the conditions in the hash table.</span></span> <span data-ttu-id="b6832-168">ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="b6832-168">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

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

### <span data-ttu-id="b6832-169">-Id</span><span class="sxs-lookup"><span data-stu-id="b6832-169">-Id</span></span>

<span data-ttu-id="b6832-170">このコマンドレットが再開するジョブの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b6832-170">Specifies an array of IDs for jobs that this cmdlet resumes.</span></span>

<span data-ttu-id="b6832-171">ID は、現在のセッションでジョブを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="b6832-171">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="b6832-172">インスタンス ID よりも覚えやすく、入力する方が簡単ですが、現在のセッションでのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="b6832-172">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="b6832-173">1つ以上の Id をコンマで区切って入力できます。</span><span class="sxs-lookup"><span data-stu-id="b6832-173">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="b6832-174">ジョブの ID を検索するには、を実行 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="b6832-174">To find the ID of a job, run `Get-Job`.</span></span>

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

### <span data-ttu-id="b6832-175">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="b6832-175">-InstanceId</span></span>

<span data-ttu-id="b6832-176">このコマンドレットによって再開されるジョブのインスタンス Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b6832-176">Specifies an array of instance IDs of jobs that this cmdlet resumes.</span></span> <span data-ttu-id="b6832-177">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="b6832-177">The default is all jobs.</span></span>

<span data-ttu-id="b6832-178">インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="b6832-178">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="b6832-179">ジョブのインスタンス ID を検索するには、を実行 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="b6832-179">To find the instance ID of a job, run `Get-Job`.</span></span>

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

### <span data-ttu-id="b6832-180">-ジョブ</span><span class="sxs-lookup"><span data-stu-id="b6832-180">-Job</span></span>

<span data-ttu-id="b6832-181">再開するジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="b6832-181">Specifies the jobs to be resumed.</span></span> <span data-ttu-id="b6832-182">ジョブが格納されている変数、またはジョブを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b6832-182">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="b6832-183">パイプを使用してジョブをコマンドレットに送ることもでき `Resume-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="b6832-183">You can also pipe jobs to the `Resume-Job` cmdlet.</span></span>

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

### <span data-ttu-id="b6832-184">-Name</span><span class="sxs-lookup"><span data-stu-id="b6832-184">-Name</span></span>

<span data-ttu-id="b6832-185">このコマンドレットによって再開されるジョブのフレンドリ名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b6832-185">Specifies an array of friendly names of jobs that this cmdlet resumes.</span></span> <span data-ttu-id="b6832-186">1 つまたは複数のジョブ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="b6832-186">Enter one or more job names.</span></span>
<span data-ttu-id="b6832-187">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6832-187">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="b6832-188">-状態</span><span class="sxs-lookup"><span data-stu-id="b6832-188">-State</span></span>

<span data-ttu-id="b6832-189">再開するジョブの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="b6832-189">Specifies the state of jobs to resume.</span></span> <span data-ttu-id="b6832-190">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b6832-190">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b6832-191">NotStarted</span><span class="sxs-lookup"><span data-stu-id="b6832-191">NotStarted</span></span>
- <span data-ttu-id="b6832-192">実行中</span><span class="sxs-lookup"><span data-stu-id="b6832-192">Running</span></span>
- <span data-ttu-id="b6832-193">完了</span><span class="sxs-lookup"><span data-stu-id="b6832-193">Completed</span></span>
- <span data-ttu-id="b6832-194">失敗</span><span class="sxs-lookup"><span data-stu-id="b6832-194">Failed</span></span>
- <span data-ttu-id="b6832-195">停止済み</span><span class="sxs-lookup"><span data-stu-id="b6832-195">Stopped</span></span>
- <span data-ttu-id="b6832-196">［ブロック済み］</span><span class="sxs-lookup"><span data-stu-id="b6832-196">Blocked</span></span>
- <span data-ttu-id="b6832-197">Suspended</span><span class="sxs-lookup"><span data-stu-id="b6832-197">Suspended</span></span>
- <span data-ttu-id="b6832-198">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="b6832-198">Disconnected</span></span>
- <span data-ttu-id="b6832-199">中断中</span><span class="sxs-lookup"><span data-stu-id="b6832-199">Suspending</span></span>
- <span data-ttu-id="b6832-200">停止中</span><span class="sxs-lookup"><span data-stu-id="b6832-200">Stopping</span></span>

<span data-ttu-id="b6832-201">このコマンドレットは、 **中断** 状態のジョブのみを再開します。</span><span class="sxs-lookup"><span data-stu-id="b6832-201">This cmdlet resumes only jobs in the **Suspended** state.</span></span>

<span data-ttu-id="b6832-202">ジョブの状態の詳細については、「 [Jobstate 列挙型](/dotnet/api/system.management.automation.jobstate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6832-202">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

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

### <span data-ttu-id="b6832-203">-Wait</span><span class="sxs-lookup"><span data-stu-id="b6832-203">-Wait</span></span>

<span data-ttu-id="b6832-204">すべてのジョブの結果が再起動されるまで、このコマンドレットによってコマンドプロンプトが抑制されることを示します。</span><span class="sxs-lookup"><span data-stu-id="b6832-204">Indicates that this cmdlet suppresses the command prompt until all job results are restarted.</span></span> <span data-ttu-id="b6832-205">既定では、このコマンドレットは使用可能な結果を直ちに返します。</span><span class="sxs-lookup"><span data-stu-id="b6832-205">By default, this cmdlet immediately returns the available results.</span></span>

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

### <span data-ttu-id="b6832-206">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b6832-206">-Confirm</span></span>

<span data-ttu-id="b6832-207">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6832-207">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b6832-208">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b6832-208">-WhatIf</span></span>

<span data-ttu-id="b6832-209">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="b6832-209">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b6832-210">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="b6832-210">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b6832-211">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b6832-211">CommonParameters</span></span>

<span data-ttu-id="b6832-212">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b6832-212">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b6832-213">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6832-213">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b6832-214">入力</span><span class="sxs-lookup"><span data-stu-id="b6832-214">INPUTS</span></span>

### <span data-ttu-id="b6832-215">システム管理. ジョブ</span><span class="sxs-lookup"><span data-stu-id="b6832-215">System.Management.Automation.Job</span></span>

<span data-ttu-id="b6832-216">このコマンドレットには、すべての種類のジョブをパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6832-216">You can pipe all types of jobs to this cmdlet.</span></span> <span data-ttu-id="b6832-217">が `Resume-Job` サポートされていない種類のジョブを取得すると、終了エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="b6832-217">If `Resume-Job` gets a job of an unsupported type, it returns a terminating error.</span></span>

## <span data-ttu-id="b6832-218">出力</span><span class="sxs-lookup"><span data-stu-id="b6832-218">OUTPUTS</span></span>

### <span data-ttu-id="b6832-219">なし、システム管理. ジョブ</span><span class="sxs-lookup"><span data-stu-id="b6832-219">None, System.Management.Automation.Job</span></span>

<span data-ttu-id="b6832-220">このコマンドレットは、 **PassThru** パラメーターを使用する場合に、再開しようとしたジョブを返します。</span><span class="sxs-lookup"><span data-stu-id="b6832-220">This cmdlet returns the jobs that it tries to resume, if you use the **PassThru** parameter.</span></span>
<span data-ttu-id="b6832-221">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="b6832-221">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b6832-222">注</span><span class="sxs-lookup"><span data-stu-id="b6832-222">NOTES</span></span>

- <span data-ttu-id="b6832-223">`Resume-Job` では、中断されているジョブのみを再開できます。</span><span class="sxs-lookup"><span data-stu-id="b6832-223">`Resume-Job` can only resume jobs that are suspended.</span></span> <span data-ttu-id="b6832-224">ジョブを別の状態で送信すると、によってジョブの再開操作が実行されますが、ジョブを再開できなかった `Resume-Job` ことを通知する警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="b6832-224">If you submit a job in a different state, `Resume-Job` runs the resume operation on the job, but generates a warning to notify you that the job could not be resumed.</span></span> <span data-ttu-id="b6832-225">警告を抑制するには、値が SilentlyContinue の **Warnings action** 共通パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b6832-225">To suppress the warning, use the **WarningAction** common parameter with a value of SilentlyContinue.</span></span>
- <span data-ttu-id="b6832-226">ジョブがワークフロージョブ ( **Psworkflowjob** ) などの再開をサポートする種類ではない場合、は `Resume-Job` 終了エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="b6832-226">If a job is not of a type that supports resuming, such as a workflow job ( **PSWorkflowJob** ), `Resume-Job` returns a terminating error.</span></span>
- <span data-ttu-id="b6832-227">中断されているジョブを保存するメカニズムと保存先の場所は、ジョブの種類によって異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b6832-227">The mechanism and location for saving a suspended job might vary depending on the job type.</span></span> <span data-ttu-id="b6832-228">たとえば、中断されているワークフロー ジョブは、既定でフラット ファイル ストアに保存されますが、SQL データベースに保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="b6832-228">For example, suspended workflow jobs are saved in a flat file store by default, but can also be saved in a SQL database.</span></span>
- <span data-ttu-id="b6832-229">ジョブを再開すると、ジョブの状態が **Suspended** から **Running** に変更されます。</span><span class="sxs-lookup"><span data-stu-id="b6832-229">When you resume a job, the job state changes from **Suspended** to **Running**.</span></span> <span data-ttu-id="b6832-230">このコマンドレットによって再開されたジョブを含め、実行中のジョブを検索するには、コマンドレットの **state** パラメーターを使用し `Get-Job` **て、実行中** の状態のジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="b6832-230">To find the jobs that are running, including those that were resumed by this cmdlet, use the **State** parameter of the `Get-Job` cmdlet to get jobs in the **Running** state.</span></span>
- <span data-ttu-id="b6832-231">一部のジョブの種類には、Windows PowerShell によるジョブの中断が許可されないオプションまたはプロパティを持つもあります。</span><span class="sxs-lookup"><span data-stu-id="b6832-231">Some job types have options or properties that prevent Windows PowerShell from suspending the job.</span></span>
  <span data-ttu-id="b6832-232">ジョブを中断する試みが失敗した場合は、ジョブのオプションとプロパティで中断が許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6832-232">If attempts to suspend the job fail, verify that the job options and properties allow for suspending.</span></span>

## <span data-ttu-id="b6832-233">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b6832-233">RELATED LINKS</span></span>

[<span data-ttu-id="b6832-234">Get-Job</span><span class="sxs-lookup"><span data-stu-id="b6832-234">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="b6832-235">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="b6832-235">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="b6832-236">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="b6832-236">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="b6832-237">Start-Job</span><span class="sxs-lookup"><span data-stu-id="b6832-237">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="b6832-238">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="b6832-238">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="b6832-239">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="b6832-239">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="b6832-240">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="b6832-240">Wait-Job</span></span>](Wait-Job.md)
