---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/resume-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Job
ms.openlocfilehash: 85cbfad2a4866bf18e69fb99afb8698e233c4c80
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212776"
---
# <span data-ttu-id="edb7b-103">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="edb7b-103">Resume-Job</span></span>

## <span data-ttu-id="edb7b-104">概要</span><span class="sxs-lookup"><span data-stu-id="edb7b-104">SYNOPSIS</span></span>
<span data-ttu-id="edb7b-105">中断されたジョブを再開します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-105">Restarts a suspended job.</span></span>

## <span data-ttu-id="edb7b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="edb7b-106">SYNTAX</span></span>

### <span data-ttu-id="edb7b-107">SessionIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="edb7b-107">SessionIdParameterSet (Default)</span></span>

```
Resume-Job [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="edb7b-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="edb7b-108">JobParameterSet</span></span>

```
Resume-Job [-Job] <Job[]> [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="edb7b-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="edb7b-109">NameParameterSet</span></span>

```
Resume-Job [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="edb7b-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="edb7b-110">InstanceIdParameterSet</span></span>

```
Resume-Job [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="edb7b-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="edb7b-111">StateParameterSet</span></span>

```
Resume-Job [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="edb7b-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="edb7b-112">FilterParameterSet</span></span>

```
Resume-Job [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="edb7b-113">Description</span><span class="sxs-lookup"><span data-stu-id="edb7b-113">DESCRIPTION</span></span>
<span data-ttu-id="edb7b-114">**Resume ジョブ** コマンドレットは、Suspend-Job コマンドレットや about_Suspend workflow アクティビティなどを使用して、中断されたワークフロージョブを再開します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-114">The **Resume-Job** cmdlet resumes a workflow job that was suspended, such as by using the Suspend-Job cmdlet or the about_Suspend-Workflow activity.</span></span>
<span data-ttu-id="edb7b-115">ワークフロージョブが再開されると、ジョブエンジンによって、状態、メタデータ、および保存されたリソース (チェックポイントなど) からの出力が再構築されます。</span><span class="sxs-lookup"><span data-stu-id="edb7b-115">When a workflow job resumes, the job engine reconstructs the state, metadata, and output from saved resources, such as checkpoints.</span></span>
<span data-ttu-id="edb7b-116">ジョブは、状態またはデータを失うことなく再開されます。</span><span class="sxs-lookup"><span data-stu-id="edb7b-116">The job is restarted without any loss of state or data.</span></span>
<span data-ttu-id="edb7b-117">ジョブの状態は、 **Suspended** から **Running** に変更されます。</span><span class="sxs-lookup"><span data-stu-id="edb7b-117">The job state is changed from **Suspended** to **Running** .</span></span>

<span data-ttu-id="edb7b-118">**再開** ジョブのパラメーターを使用して、名前、ID、インスタンス ID、またはパイプを使用してジョブを選択します。たとえば、Get-Job コマンドレットによって返されるジョブオブジェクトは、 **ジョブを再開** します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-118">Use the parameters of **Resume-Job** to select jobs by name, ID, instance ID or pipe a job object, such as one returned by the Get-Job cmdlet, to **Resume-Job** .</span></span>
<span data-ttu-id="edb7b-119">プロパティ フィルターを使用して再開するジョブを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="edb7b-119">You can also use a property filter to select a job to be resumed.</span></span>

<span data-ttu-id="edb7b-120">既定では、 **Resume-Job** は、すべてのジョブがまだ再開されていない状態であっても即座に制御を返します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-120">By default, **Resume-Job** returns immediately, even though all jobs might not yet be resumed.</span></span>
<span data-ttu-id="edb7b-121">指定したすべてのジョブが再開されるまでコマンド プロンプトが表示されないようにするには、 *Wait* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-121">To suppress the command prompt until all specified jobs are resumed, use the *Wait* parameter.</span></span>

<span data-ttu-id="edb7b-122">**Resume-Job** コマンドレットは、ワークフロー ジョブなどのカスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-122">The **Resume-Job** cmdlet works only on custom job types, such as workflow jobs.</span></span>
<span data-ttu-id="edb7b-123">これは、Start-Job コマンドレットを使用して開始されたものなど、標準のバックグラウンドジョブでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="edb7b-123">It does not work on standard background jobs, such as those that are started by using the Start-Job cmdlet.</span></span>
<span data-ttu-id="edb7b-124">サポートされない種類のジョブを送信した場合、 **Resume-Job** は、終了エラーを生成し、実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-124">If you submit a job of an unsupported type, **Resume-Job** generates a terminating error and stops running.</span></span>

<span data-ttu-id="edb7b-125">ワークフロー ジョブを識別するには、ジョブの **PSJobTypeName** プロパティで **PSWorkflowJob** の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-125">To identify a workflow job, look for a value of **PSWorkflowJob** in the **PSJobTypeName** property of the job.</span></span>
<span data-ttu-id="edb7b-126">特定のカスタムジョブの種類で **Resume ジョブ** のコマンドレットがサポートされているかどうかを確認するには、カスタムジョブの種類のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="edb7b-126">To determine whether a particular custom job type supports the **Resume-Job** cmdlet, see the help topics for the custom job type.</span></span>

<span data-ttu-id="edb7b-127">カスタムのジョブの種類で Job コマンドレットを使用する前に、カスタムのジョブの種類をサポートするモジュールをインポートします。そのためには、Import-Module コマンドレットを使用するか、モジュールのコマンドレットを取得または使用します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-127">Before using a Job cmdlet on a custom job type, import the module that supports the custom job type, either by using the Import-Module cmdlet or getting or using a cmdlet in the module.</span></span>

<span data-ttu-id="edb7b-128">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="edb7b-128">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="edb7b-129">例</span><span class="sxs-lookup"><span data-stu-id="edb7b-129">EXAMPLES</span></span>

### <span data-ttu-id="edb7b-130">例 1: ID でジョブを再開する</span><span class="sxs-lookup"><span data-stu-id="edb7b-130">Example 1: Resume a job by ID</span></span>

```
The first command uses the **Get-Job** cmdlet to get the job. The output shows that the job is a suspended workflow job.
PS C:\> Get-Job EventJob
Id     Name            PSJobTypeName   State         HasMoreData     Location   Command
--     ----            -------------   -----         -----------     --------   -------
4      EventJob        PSWorkflowJob   Suspended     True            Server01   \\Script\Share\Event.ps1

The second command uses the *Id* parameter of the **Resume-Job** cmdlet to resume the job with an *Id* value of 4.
PS C:\> Resume-Job -Id 4
```

<span data-ttu-id="edb7b-131">この例のコマンドは、ジョブが中断状態のワークフロー ジョブであることを確認した後、このジョブを再開します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-131">The commands in this example verify that the job is a suspended workflow job and then resume the job.</span></span>

### <span data-ttu-id="edb7b-132">例 2: 名前を指定してジョブを再開する</span><span class="sxs-lookup"><span data-stu-id="edb7b-132">Example 2: Resume a job by name</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest*
```

<span data-ttu-id="edb7b-133">このコマンドは、 *Name* パラメーターを使用して、ローカル コンピューター上の複数のワークフロー ジョブを再開します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-133">This command uses the *Name* parameter to resume several workflow jobs on the local computer.</span></span>

### <span data-ttu-id="edb7b-134">例 3: カスタムプロパティ値を使用する</span><span class="sxs-lookup"><span data-stu-id="edb7b-134">Example 3: Use custom property values</span></span>

```
PS C:\> Resume-Job -Filter @{CustomID="T091291"} -State Suspended
```

<span data-ttu-id="edb7b-135">このコマンドは、カスタム プロパティ値を使用して、再開するワークフロー ジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-135">This command uses the value of a custom property to identify the workflow job to resume.</span></span>
<span data-ttu-id="edb7b-136">このコマンドは、 *Filter* パラメーターを使用して、 **CustomID** プロパティでワークフロー ジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-136">It uses the *Filter* parameter to identify the workflow job by its **CustomID** property.</span></span>
<span data-ttu-id="edb7b-137">さらに、 *State* パラメーターを使用して、再開操作を開始する前に、ワークフロー ジョブが中断状態にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-137">It also uses the *State* parameter to verify that the workflow job is suspended, before it tries to resume it.</span></span>

### <span data-ttu-id="edb7b-138">例 4: リモートコンピューター上のすべての中断されたジョブを再開する</span><span class="sxs-lookup"><span data-stu-id="edb7b-138">Example 4: Resume all suspended jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01 -ScriptBlock {Get-Job -State Suspended | Resume-Job}
```

<span data-ttu-id="edb7b-139">このコマンドは、Srv01 リモート コンピューター上のすべての中断されているジョブを再開します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-139">This command resumes all suspended jobs on the Srv01 remote computer.</span></span>

<span data-ttu-id="edb7b-140">このコマンドは、Invoke-Command コマンドレットを使用して、Srv01 コンピューター上でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-140">The command uses the Invoke-Command cmdlet to run a command on the Srv01 computer.</span></span>
<span data-ttu-id="edb7b-141">Remote コマンドは、 **Job** コマンドレットの *State* パラメーターを使用して、コンピューター上のすべての中断されたジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-141">The remote command uses the *State* parameter of the **Get-Job** cmdlet to get all suspended jobs on the computer.</span></span>
<span data-ttu-id="edb7b-142">パイプライン演算子 (|) により、中断されているジョブが **Resume-Job** コマンドレットに送信され、このコマンドレットによって再開されます。</span><span class="sxs-lookup"><span data-stu-id="edb7b-142">A pipeline operator (|) sends the suspended jobs to the **Resume-Job** cmdlet, which resumes them.</span></span>

### <span data-ttu-id="edb7b-143">例 5: ジョブが再開されるまで待機する</span><span class="sxs-lookup"><span data-stu-id="edb7b-143">Example 5: Wait for jobs to resume</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest* -Wait
```

<span data-ttu-id="edb7b-144">このコマンドは、 *Wait* パラメーターを使用して、指定したすべてのジョブが再開された後にのみを返すように **Resume ジョブ** に指示します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-144">This command uses the *Wait* parameter to direct **Resume-Job** to return only after all specified jobs are resumed.</span></span>
<span data-ttu-id="edb7b-145">*Wait* パラメーターは、ジョブが再開された後でスクリプトが続行されることを前提としているスクリプトで特に便利です。</span><span class="sxs-lookup"><span data-stu-id="edb7b-145">The *Wait* parameter is especially useful in scripts that assume that jobs are resumed before the script continues.</span></span>

### <span data-ttu-id="edb7b-146">例 6: 自身を中断するワークフローを再開する</span><span class="sxs-lookup"><span data-stu-id="edb7b-146">Example 6: Resume a workflow that suspends itself</span></span>

```
This code sample shows the **Suspend-Workflow** activity in a workflow.
#SampleWorkflow
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

The following command runs the Test-Suspend workflow on the Server01 computer.When you run the workflow, the workflow runs the Get-Date activity and stores the result in the $a variable. Then it runs the Suspend-Workflow activity. In response, it takes a checkpoint, suspends the workflow, and returns a workflow job object.  Suspend-Workflow returns a workflow job object even if the workflow is not explicitly run as a job.
PS C:\> Test-Suspend -PSComputerName Server01
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Suspended     True            Server01             Test-Suspend

The following command resumes the Test-Suspend workflow in Job8. It uses the *Wait* parameter to hold the command prompt until the job is resumed.
PS C:\> Resume-Job -Name "Job8" -Wait
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command

--     ----            -------------   -----         -----------     --------             -------

8      Job8            PSWorkflowJob   Running       True            Server01             Test-Suspend

This command uses the **Receive-Job** cmdlet to get the results of the Test-Suspend workflow. The final command in the workflow returns a **TimeSpan** object that represents the elapsed time between the current date and time and the date and time that was saved in the $a variable before the workflow was suspended.
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

<span data-ttu-id="edb7b-147">**Resume ジョブ** コマンドレットを使用すると、中断 **ワークフロー** アクティビティを使用して中断されたワークフロージョブを再開できます。</span><span class="sxs-lookup"><span data-stu-id="edb7b-147">The **Resume-Job** cmdlet lets you resume a workflow job that was suspend by using the **Suspend-Workflow** activity.</span></span>
<span data-ttu-id="edb7b-148">このアクティビティは、ワークフロー内からワークフローを中断します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-148">This activity suspends a workflow from within a workflow.</span></span>
<span data-ttu-id="edb7b-149">ワークフローでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="edb7b-149">It is valid only in workflows.</span></span>

<span data-ttu-id="edb7b-150">Suspend-Workflow の詳細については、「about_Suspend-Workflow」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edb7b-150">For information about the Suspend-Workflow, see about_Suspend-Workflow.</span></span>

## <span data-ttu-id="edb7b-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="edb7b-151">PARAMETERS</span></span>

### <span data-ttu-id="edb7b-152">-Filter</span><span class="sxs-lookup"><span data-stu-id="edb7b-152">-Filter</span></span>
<span data-ttu-id="edb7b-153">条件のハッシュテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-153">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="edb7b-154">このコマンドレットは、ハッシュテーブル内のすべての条件に適合するジョブを再開します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-154">This cmdlet resumes jobs that satisfy all of the conditions in the hash table.</span></span>
<span data-ttu-id="edb7b-155">ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-155">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

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

### <span data-ttu-id="edb7b-156">-Id</span><span class="sxs-lookup"><span data-stu-id="edb7b-156">-Id</span></span>
<span data-ttu-id="edb7b-157">このコマンドレットが再開するジョブの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-157">Specifies an array of IDs for jobs that this cmdlet resumes.</span></span>

<span data-ttu-id="edb7b-158">ID は、現在のセッションでジョブを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="edb7b-158">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="edb7b-159">インスタンス ID よりも覚えやすく、入力する方が簡単ですが、現在のセッションでのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="edb7b-159">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="edb7b-160">1つ以上の Id をコンマで区切って入力できます。</span><span class="sxs-lookup"><span data-stu-id="edb7b-160">You can type one or more IDs, separated by commas.</span></span>
<span data-ttu-id="edb7b-161">ジョブの ID を検索するには、 **Get job** を実行します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-161">To find the ID of a job, run **Get-Job** .</span></span>

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

### <span data-ttu-id="edb7b-162">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="edb7b-162">-InstanceId</span></span>
<span data-ttu-id="edb7b-163">このコマンドレットによって再開されるジョブのインスタンス Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-163">Specifies an array of instance IDs of jobs that this cmdlet resumes.</span></span>
<span data-ttu-id="edb7b-164">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="edb7b-164">The default is all jobs.</span></span>

<span data-ttu-id="edb7b-165">インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="edb7b-165">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="edb7b-166">ジョブのインスタンス ID を検索するには、 **Get job** を実行します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-166">To find the instance ID of a job, run **Get-Job** .</span></span>

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

### <span data-ttu-id="edb7b-167">-ジョブ</span><span class="sxs-lookup"><span data-stu-id="edb7b-167">-Job</span></span>
<span data-ttu-id="edb7b-168">再開するジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-168">Specifies the jobs to be resumed.</span></span>
<span data-ttu-id="edb7b-169">ジョブが格納されている変数、またはジョブを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-169">Enter a variable that contains the jobs or a command that gets the jobs.</span></span>
<span data-ttu-id="edb7b-170">パイプを使用してジョブを **Resume-Job** コマンドレットに渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="edb7b-170">You can also pipe jobs to the **Resume-Job** cmdlet.</span></span>

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

### <span data-ttu-id="edb7b-171">-Name</span><span class="sxs-lookup"><span data-stu-id="edb7b-171">-Name</span></span>
<span data-ttu-id="edb7b-172">このコマンドレットによって再開されるジョブのフレンドリ名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-172">Specifies an array of friendly names of jobs that this cmdlet resumes.</span></span>
<span data-ttu-id="edb7b-173">1 つまたは複数のジョブ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-173">Enter one or more job names.</span></span>
<span data-ttu-id="edb7b-174">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="edb7b-174">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="edb7b-175">-状態</span><span class="sxs-lookup"><span data-stu-id="edb7b-175">-State</span></span>
<span data-ttu-id="edb7b-176">再開するジョブの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-176">Specifies the state of jobs to resume.</span></span>
<span data-ttu-id="edb7b-177">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="edb7b-177">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="edb7b-178">NotStarted</span><span class="sxs-lookup"><span data-stu-id="edb7b-178">NotStarted</span></span>
- <span data-ttu-id="edb7b-179">実行中</span><span class="sxs-lookup"><span data-stu-id="edb7b-179">Running</span></span>
- <span data-ttu-id="edb7b-180">完了</span><span class="sxs-lookup"><span data-stu-id="edb7b-180">Completed</span></span>
- <span data-ttu-id="edb7b-181">失敗</span><span class="sxs-lookup"><span data-stu-id="edb7b-181">Failed</span></span>
- <span data-ttu-id="edb7b-182">停止済み</span><span class="sxs-lookup"><span data-stu-id="edb7b-182">Stopped</span></span>
- <span data-ttu-id="edb7b-183">Blocked</span><span class="sxs-lookup"><span data-stu-id="edb7b-183">Blocked</span></span>
- <span data-ttu-id="edb7b-184">Suspended</span><span class="sxs-lookup"><span data-stu-id="edb7b-184">Suspended</span></span>
- <span data-ttu-id="edb7b-185">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="edb7b-185">Disconnected</span></span>
- <span data-ttu-id="edb7b-186">中断中</span><span class="sxs-lookup"><span data-stu-id="edb7b-186">Suspending</span></span>
- <span data-ttu-id="edb7b-187">停止中</span><span class="sxs-lookup"><span data-stu-id="edb7b-187">Stopping</span></span>

<span data-ttu-id="edb7b-188">このコマンドレットは、 **中断** 状態のジョブのみを再開します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-188">This cmdlet resumes only jobs in the **Suspended** state.</span></span>

<span data-ttu-id="edb7b-189">ジョブの状態の詳細については、MSDN ライブラリの「 [Jobstate 列挙型](https://msdn.microsoft.com/library/system.management.automation.jobstate) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edb7b-189">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

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

### <span data-ttu-id="edb7b-190">-Wait</span><span class="sxs-lookup"><span data-stu-id="edb7b-190">-Wait</span></span>
<span data-ttu-id="edb7b-191">すべてのジョブの結果が再起動されるまで、このコマンドレットによってコマンドプロンプトが抑制されることを示します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-191">Indicates that this cmdlet suppresses the command prompt until all job results are restarted.</span></span>
<span data-ttu-id="edb7b-192">既定では、このコマンドレットは使用可能な結果を直ちに返します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-192">By default, this cmdlet immediately returns the available results.</span></span>

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

### <span data-ttu-id="edb7b-193">-Confirm</span><span class="sxs-lookup"><span data-stu-id="edb7b-193">-Confirm</span></span>
<span data-ttu-id="edb7b-194">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="edb7b-194">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="edb7b-195">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="edb7b-195">-WhatIf</span></span>
<span data-ttu-id="edb7b-196">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-196">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="edb7b-197">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="edb7b-197">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="edb7b-198">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="edb7b-198">CommonParameters</span></span>
<span data-ttu-id="edb7b-199">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="edb7b-199">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="edb7b-200">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edb7b-200">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="edb7b-201">入力</span><span class="sxs-lookup"><span data-stu-id="edb7b-201">INPUTS</span></span>

### <span data-ttu-id="edb7b-202">システム管理. ジョブ</span><span class="sxs-lookup"><span data-stu-id="edb7b-202">System.Management.Automation.Job</span></span>
<span data-ttu-id="edb7b-203">このコマンドレットには、すべての種類のジョブをパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="edb7b-203">You can pipe all types of jobs to this cmdlet.</span></span>
<span data-ttu-id="edb7b-204">**Resume ジョブ** がサポートされていない種類のジョブを取得すると、終了エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="edb7b-204">If **Resume-Job** gets a job of an unsupported type, it returns a terminating error.</span></span>

## <span data-ttu-id="edb7b-205">出力</span><span class="sxs-lookup"><span data-stu-id="edb7b-205">OUTPUTS</span></span>

### <span data-ttu-id="edb7b-206">なし、システム管理. ジョブ</span><span class="sxs-lookup"><span data-stu-id="edb7b-206">None, System.Management.Automation.Job</span></span>
<span data-ttu-id="edb7b-207">このコマンドレットは、 *PassThru* パラメーターを使用する場合に、再開しようとしたジョブを返します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-207">This cmdlet returns the jobs that it tries to resume, if you use the *PassThru* parameter.</span></span>
<span data-ttu-id="edb7b-208">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="edb7b-208">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="edb7b-209">注</span><span class="sxs-lookup"><span data-stu-id="edb7b-209">NOTES</span></span>

* <span data-ttu-id="edb7b-210">**Resume-ジョブ** は、中断されているジョブのみを再開できます。</span><span class="sxs-lookup"><span data-stu-id="edb7b-210">**Resume-Job** can only resume jobs that are suspended.</span></span> <span data-ttu-id="edb7b-211">それ以外の状態のジョブを送信した場合、 **Resume-Job** は、ジョブに対して再開操作を実行しますが、ジョブを再開できなかったことを通知する警告を生成します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-211">If you submit a job in a different state, **Resume-Job** runs the resume operation on the job, but generates a warning to notify you that the job could not be resumed.</span></span> <span data-ttu-id="edb7b-212">警告を抑制するには、値が SilentlyContinue の *Warnings action* 共通パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-212">To suppress the warning, use the *WarningAction* common parameter with a value of SilentlyContinue.</span></span>
* <span data-ttu-id="edb7b-213">ジョブがワークフロージョブ ( **Psworkflowjob** ) などの再開をサポートする種類ではない場合、 **Resume ジョブ** は終了エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-213">If a job is not of a type that supports resuming, such as a workflow job ( **PSWorkflowJob** ), **Resume-Job** returns a terminating error.</span></span>
* <span data-ttu-id="edb7b-214">中断されているジョブを保存するメカニズムと保存先の場所は、ジョブの種類によって異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="edb7b-214">The mechanism and location for saving a suspended job might vary depending on the job type.</span></span> <span data-ttu-id="edb7b-215">たとえば、中断されているワークフロー ジョブは、既定でフラット ファイル ストアに保存されますが、SQL データベースに保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="edb7b-215">For example, suspended workflow jobs are saved in a flat file store by default, but can also be saved in a SQL database.</span></span>
* <span data-ttu-id="edb7b-216">ジョブを再開すると、ジョブの状態が **Suspended** から **Running** に変更されます。</span><span class="sxs-lookup"><span data-stu-id="edb7b-216">When you resume a job, the job state changes from **Suspended** to **Running** .</span></span> <span data-ttu-id="edb7b-217">このコマンドレットによって再開されたジョブを含め、実行中のジョブを検索するには、 **get-help** コマンドレットの *state* パラメーターを使用し **て、running** 状態のジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-217">To find the jobs that are running, including those that were resumed by this cmdlet, use the *State* parameter of the **Get-Job** cmdlet to get jobs in the **Running** state.</span></span>
* <span data-ttu-id="edb7b-218">一部のジョブの種類には、Windows PowerShell によるジョブの中断が許可されないオプションまたはプロパティを持つもあります。</span><span class="sxs-lookup"><span data-stu-id="edb7b-218">Some job types have options or properties that prevent Windows PowerShell from suspending the job.</span></span> <span data-ttu-id="edb7b-219">ジョブを中断する試みが失敗した場合は、ジョブのオプションとプロパティで中断が許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="edb7b-219">If attempts to suspend the job fail, verify that the job options and properties allow for suspending.</span></span>

## <span data-ttu-id="edb7b-220">関連リンク</span><span class="sxs-lookup"><span data-stu-id="edb7b-220">RELATED LINKS</span></span>

[<span data-ttu-id="edb7b-221">Get-Job</span><span class="sxs-lookup"><span data-stu-id="edb7b-221">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="edb7b-222">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="edb7b-222">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="edb7b-223">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="edb7b-223">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="edb7b-224">Start-Job</span><span class="sxs-lookup"><span data-stu-id="edb7b-224">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="edb7b-225">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="edb7b-225">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="edb7b-226">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="edb7b-226">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="edb7b-227">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="edb7b-227">Wait-Job</span></span>](Wait-Job.md)
