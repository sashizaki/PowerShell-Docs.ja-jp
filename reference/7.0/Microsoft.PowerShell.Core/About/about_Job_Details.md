---
description: ローカルコンピューターとリモートコンピューターのバックグラウンドジョブの詳細について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 10/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_job_details?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Job_Details
ms.openlocfilehash: 0d85cd242c8e79281fa8be153b0e140660f16c1a
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "93224635"
---
# <a name="about-job-details"></a><span data-ttu-id="d048f-104">ジョブの詳細について</span><span class="sxs-lookup"><span data-stu-id="d048f-104">About Job Details</span></span>

## <a name="short-description"></a><span data-ttu-id="d048f-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="d048f-105">Short description</span></span>
<span data-ttu-id="d048f-106">ローカルコンピューターとリモートコンピューターのバックグラウンドジョブの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="d048f-106">Provides details about background jobs on local and remote computers.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="d048f-107">詳しい説明</span><span class="sxs-lookup"><span data-stu-id="d048f-107">Detailed description</span></span>

<span data-ttu-id="d048f-108">このトピックでは、バックグラウンドジョブの概念について説明し、PowerShell でのバックグラウンドジョブの動作に関する技術情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d048f-108">This topic explains the concept of a background job and provides technical information about how background jobs work in PowerShell.</span></span>

<span data-ttu-id="d048f-109">このトピックでは、 [about_Jobs](about_Jobs.md)、 [about_Thread_Jobs](about_Thread_Jobs.md)、および [about_Remote_Jobs](about_Remote_Jobs.md) に関するトピックを補足します。</span><span class="sxs-lookup"><span data-stu-id="d048f-109">This topic is a supplement to the [about_Jobs](about_Jobs.md), [about_Thread_Jobs](about_Thread_Jobs.md), and [about_Remote_Jobs](about_Remote_Jobs.md) topics.</span></span>

### <a name="about-background-jobs"></a><span data-ttu-id="d048f-110">バックグラウンドジョブについて</span><span class="sxs-lookup"><span data-stu-id="d048f-110">About background jobs</span></span>

<span data-ttu-id="d048f-111">バックグラウンドジョブは、コマンドまたは式を非同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="d048f-111">A background job runs a command or expression asynchronously.</span></span> <span data-ttu-id="d048f-112">コマンドレット、関数、スクリプト、またはその他のコマンドベースのタスクが実行されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d048f-112">It might run a cmdlet, a function, a script, or any other command-based task.</span></span> <span data-ttu-id="d048f-113">これは、長い時間を要するコマンドを実行するように設計されていますが、バックグラウンドで任意のコマンドを実行するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d048f-113">It is designed to run commands that take an extended period of time, but you can use it to run any command in the background.</span></span>

<span data-ttu-id="d048f-114">同期コマンドを実行すると、コマンドが完了するまで PowerShell コマンドプロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="d048f-114">When a synchronous command runs, the PowerShell command prompt is suppressed until the command is complete.</span></span> <span data-ttu-id="d048f-115">ただし、バックグラウンドジョブでは PowerShell プロンプトは抑制されません。</span><span class="sxs-lookup"><span data-stu-id="d048f-115">But a background job does not suppress the PowerShell prompt.</span></span> <span data-ttu-id="d048f-116">バックグラウンドジョブを開始するコマンドは、ジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="d048f-116">A command to start a background job returns a job object.</span></span>
<span data-ttu-id="d048f-117">プロンプトはすぐに返されるので、バックグラウンドジョブの実行中に他のタスクを操作できます。</span><span class="sxs-lookup"><span data-stu-id="d048f-117">The prompt returns immediately so you can work on other tasks while the background job runs.</span></span>

<span data-ttu-id="d048f-118">ただし、バックグラウンドジョブを開始すると、ジョブが非常に短時間で実行された場合でも、すぐに結果を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="d048f-118">However, when you start a background job, you do not get the results immediately even if the job runs very quickly.</span></span> <span data-ttu-id="d048f-119">返されるジョブオブジェクトには、ジョブに関する有用な情報が含まれていますが、ジョブの結果は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d048f-119">The job object that is returned contains useful information about the job, but it does not contain the job results.</span></span> <span data-ttu-id="d048f-120">ジョブの結果を取得するには、別のコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d048f-120">You must run a separate command to get the job results.</span></span> <span data-ttu-id="d048f-121">また、コマンドを実行してジョブを停止し、ジョブが完了するまで待機して、ジョブを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="d048f-121">You can also run commands to stop the job, to wait for the job to be completed, and to delete the job.</span></span>

<span data-ttu-id="d048f-122">バックグラウンドジョブのタイミングを他のコマンドから独立させるには、各バックグラウンドジョブが独自の PowerShell セッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="d048f-122">To make the timing of a background job independent of other commands, each background job runs in its own PowerShell session.</span></span> <span data-ttu-id="d048f-123">ただし、これは、ジョブを実行するためだけに作成され、その後破棄される一時的な接続である場合もあれば、複数の関連ジョブやコマンドを実行するために使用できる永続的な **PSSession** である場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d048f-123">However, this can be a temporary connection that is created only to run the job and is then destroyed, or it can be a persistent **PSSession** that you can use to run several related jobs or commands.</span></span>

### <a name="using-the-job-cmdlets"></a><span data-ttu-id="d048f-124">Job コマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="d048f-124">Using the job cmdlets</span></span>

<span data-ttu-id="d048f-125">コマンドを使用し `Start-Job` て、ローカルコンピューター上でバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="d048f-125">Use a `Start-Job` command to start a background job on a local computer.</span></span>
<span data-ttu-id="d048f-126">`Start-Job` ジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="d048f-126">`Start-Job` returns a job object.</span></span> <span data-ttu-id="d048f-127">コマンドレットを使用して、ローカルコンピューターで開始されたジョブを表すオブジェクトを取得することもでき `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="d048f-127">You can also get objects representing the jobs that were started on the local computer using the `Get-Job` cmdlet.</span></span>

<span data-ttu-id="d048f-128">ジョブの結果を取得するには、コマンドを使用し `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="d048f-128">To get the job results, use a `Receive-Job` command.</span></span> <span data-ttu-id="d048f-129">ジョブが完了していない場合は、 `Receive-Job` 部分的な結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="d048f-129">If the job is not complete, `Receive-Job` returns partial results.</span></span> <span data-ttu-id="d048f-130">また、コマンドレットを使用して、 `Wait-Job` セッションで開始された1つまたはすべてのジョブが完了するまで、コマンドプロンプトを表示しないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d048f-130">You can also use the `Wait-Job` cmdlet to suppress the command prompt until one or all of the jobs that were started in the session are complete.</span></span>

<span data-ttu-id="d048f-131">バックグラウンドジョブを停止するには、 `Stop-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d048f-131">To stop a background job, use the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="d048f-132">ジョブを削除するには、 `Remove-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d048f-132">To delete a job, use the `Remove-Job` cmdlet.</span></span>

<span data-ttu-id="d048f-133">コマンドレットの動作の詳細については、各コマンドレットのヘルプトピックを参照し、 [about_Jobs](about_Jobs.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d048f-133">For more information about how the cmdlets work, see the Help topic for each cmdlet, and see [about_Jobs](about_Jobs.md).</span></span>

### <a name="starting-background-jobs-on-remote-computers"></a><span data-ttu-id="d048f-134">リモートコンピューターでバックグラウンドジョブを開始しています</span><span class="sxs-lookup"><span data-stu-id="d048f-134">Starting background jobs on remote computers</span></span>

<span data-ttu-id="d048f-135">ローカルコンピューターまたはリモートコンピューターでバックグラウンドジョブを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="d048f-135">You can create and manage background jobs on a local or remote computer.</span></span> <span data-ttu-id="d048f-136">バックグラウンドジョブをリモートで実行するには、コマンドレットの **AsJob** パラメーター (など) を使用する `Invoke-Command` か、 `Invoke-Command` コマンドレットを使用して `Start-Job` コマンドをリモートで実行します。</span><span class="sxs-lookup"><span data-stu-id="d048f-136">To run a background job remotely, use the **AsJob** parameter of a cmdlet such as `Invoke-Command`, or use the `Invoke-Command` cmdlet to run a `Start-Job` command remotely.</span></span> <span data-ttu-id="d048f-137">対話型セッションでバックグラウンドジョブを開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="d048f-137">You can also start a background job in an interactive session.</span></span>

<span data-ttu-id="d048f-138">リモートバックグラウンドジョブの詳細については、「 [about_Remote_Jobs](about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d048f-138">For more information about remote background jobs, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>

### <a name="child-jobs"></a><span data-ttu-id="d048f-139">子ジョブ</span><span class="sxs-lookup"><span data-stu-id="d048f-139">Child jobs</span></span>

<span data-ttu-id="d048f-140">各バックグラウンドジョブは、親ジョブと1つ以上の子ジョブで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d048f-140">Each background job consists of a parent job and one or more child jobs.</span></span> <span data-ttu-id="d048f-141">またはの AsJob パラメーターを使用して開始されたジョブでは、 `Start-Job` **AsJob** `Invoke-Command` 親ジョブは役員です。</span><span class="sxs-lookup"><span data-stu-id="d048f-141">In jobs started using `Start-Job` or the **AsJob** parameter of `Invoke-Command`, the parent job is an executive.</span></span> <span data-ttu-id="d048f-142">コマンドを実行したり、結果を返したりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="d048f-142">It does not run any commands or return any results.</span></span> <span data-ttu-id="d048f-143">コマンドは、実際には子ジョブによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="d048f-143">The commands are actually run by the child jobs.</span></span> <span data-ttu-id="d048f-144">他のコマンドレットを使用して開始されたジョブの動作が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d048f-144">Jobs started using other cmdlets might work differently.</span></span>

<span data-ttu-id="d048f-145">子ジョブは親ジョブオブジェクトの **childjobs** プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="d048f-145">The child jobs are stored in the **ChildJobs** property of the parent job object.</span></span> <span data-ttu-id="d048f-146">**Childjobs** プロパティには、1つまたは複数の子ジョブオブジェクトを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d048f-146">The **ChildJobs** property can contain one or many child job objects.</span></span>
<span data-ttu-id="d048f-147">子ジョブオブジェクトの **名前** 、 **ID** 、および **InstanceId** は親ジョブとは異なるので、親ジョブと子ジョブを個別に、または1つの単位として管理できます。</span><span class="sxs-lookup"><span data-stu-id="d048f-147">The child job objects have a **Name** , **ID** , and **InstanceId** that differ from the parent job so that you can manage the parent and child jobs individually or as a unit.</span></span>

<span data-ttu-id="d048f-148">ジョブの親ジョブと子ジョブを取得するには、コマンドレットの **IncludeChildJobs** パラメーターを使用し `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="d048f-148">To get the parent and child jobs of a job, use the **IncludeChildJobs** parameter of the `Get-Job` cmdlet.</span></span> <span data-ttu-id="d048f-149">**IncludeChildJob** パラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d048f-149">The **IncludeChildJob** parameter was introduced in Windows PowerShell 3.0.</span></span>

```powershell
PS> Get-Job -IncludeChildJob

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
1  Job1   RemoteJob     Failed     True          localhost   Get-Process
2  Job2                 Completed  True          Server01    Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

<span data-ttu-id="d048f-150">親ジョブと特定の **状態** 値を持つ子ジョブのみを取得するには、コマンドレットの **childjobstate** パラメーターを使用し `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="d048f-150">To get the parent job and only the child jobs with a particular **State** value, use the **ChildJobState** parameter of the `Get-Job` cmdlet.</span></span> <span data-ttu-id="d048f-151">**Childjobstate** パラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d048f-151">The **ChildJobState** parameter was introduced in Windows PowerShell 3.0.</span></span>

```powershell
PS> Get-Job -ChildJobState Failed

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
1  Job1   RemoteJob     Failed     True          localhost   Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

<span data-ttu-id="d048f-152">すべてのバージョンの PowerShell でジョブの子ジョブを取得するには、親ジョブの **childjob** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="d048f-152">To get the child jobs of a job on all versions of PowerShell, use the **ChildJob** property of the parent job.</span></span>

```powershell
PS> (Get-Job Job1).ChildJobs

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
2  Job2                 Completed  True          Server01    Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

<span data-ttu-id="d048f-153">`Get-Job`次のコマンドに示すように、子ジョブでコマンドを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d048f-153">You can also use a `Get-Job` command on the child job, as shown in the following command:</span></span>

```powershell
PS> Get-Job Job3

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
3  Job3                 Failed     False         localhost   Get-Process
```

<span data-ttu-id="d048f-154">子ジョブの構成は、ジョブを開始するために使用するコマンドによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d048f-154">The configuration of the child job depends on the command that you use to start the job.</span></span>

- <span data-ttu-id="d048f-155">を使用し `Start-Job` てローカルコンピューターでジョブを開始すると、ジョブは、コマンドを実行する executive 親ジョブと子ジョブで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d048f-155">When you use `Start-Job` to start a job on a local computer, the job consists of an executive parent job and a child job that runs the command.</span></span>

- <span data-ttu-id="d048f-156">の **AsJob** パラメーターを使用して `Invoke-Command` 1 つまたは複数のコンピューターでジョブを開始すると、ジョブは、各コンピューターで実行される各ジョブの役員親ジョブと子ジョブで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d048f-156">When you use the **AsJob** parameter of `Invoke-Command` to start a job on one or more computers, the job consists of an executive parent job and a child job for each job run on each computer.</span></span>

- <span data-ttu-id="d048f-157">を使用して `Invoke-Command` 1 台以上のリモートコンピューターでコマンドを実行すると、 `Start-Job` 各リモートコンピューターで実行されるローカルコマンドと同じ結果になります。</span><span class="sxs-lookup"><span data-stu-id="d048f-157">When you use `Invoke-Command` to run a `Start-Job` command on one or more remote computers, the result is the same as a local command run on each remote computer.</span></span> <span data-ttu-id="d048f-158">このコマンドは、各コンピューターのジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="d048f-158">The command returns a job object for each computer.</span></span> <span data-ttu-id="d048f-159">ジョブオブジェクトは、コマンドを実行する役員親ジョブと1つの子ジョブで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d048f-159">The job object consists of an executive parent job and one child job that runs the command.</span></span>

<span data-ttu-id="d048f-160">親ジョブは、すべての子ジョブを表します。</span><span class="sxs-lookup"><span data-stu-id="d048f-160">The parent job represents all of the child jobs.</span></span> <span data-ttu-id="d048f-161">親ジョブを管理する場合は、関連付けられている子ジョブも管理します。</span><span class="sxs-lookup"><span data-stu-id="d048f-161">When you manage a parent job, you also manage the associated child jobs.</span></span> <span data-ttu-id="d048f-162">たとえば、親ジョブを停止すると、すべての子ジョブが停止します。</span><span class="sxs-lookup"><span data-stu-id="d048f-162">For example, if you stop a parent job, all child jobs are stopped.</span></span> <span data-ttu-id="d048f-163">親ジョブの結果を取得すると、すべての子ジョブの結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="d048f-163">If you get the results of a parent job, you get the results of all child jobs.</span></span>

<span data-ttu-id="d048f-164">ただし、子ジョブを個別に管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="d048f-164">However, you can also manage child jobs individually.</span></span> <span data-ttu-id="d048f-165">これは、ジョブに関する問題を調査する場合や、の **AsJob** パラメーターを使用して開始された複数の子ジョブの結果を取得する場合に最も役立ち `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="d048f-165">This is most useful when you want to investigate a problem with a job or get the results of only one of a number of child jobs started using the **AsJob** parameter of `Invoke-Command`.</span></span>

<span data-ttu-id="d048f-166">次のコマンドでは、の **AsJob** パラメーターを使用して、 `Invoke-Command` ローカルコンピューターと2台のリモートコンピューターでバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="d048f-166">The following command uses the **AsJob** parameter of `Invoke-Command` to start background jobs on the local computer and two remote computers.</span></span> <span data-ttu-id="d048f-167">このコマンドは、ジョブを変数に保存し `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="d048f-167">The command saves the job in the `$j` variable.</span></span>

```powershell
PS> $j = Invoke-Command -ComputerName localhost, Server01, Server02 `
-Command {Get-Date} -AsJob
```

<span data-ttu-id="d048f-168">でジョブの Name および **childjob** プロパティを表示すると `$j` 、このコマンドによって、3つの子ジョブ (コンピューターごとに1つ) のジョブオブジェクトが返されたことが示されます。</span><span class="sxs-lookup"><span data-stu-id="d048f-168">When you display the Name and **ChildJob** properties of the job in `$j`, it shows that the command returned a job object with three child jobs, one for each computer.</span></span>

```powershell
PS> $j | Format-List Name, ChildJobs

Name      : Job3
ChildJobs : {Job4, Job5, Job6}
```

<span data-ttu-id="d048f-169">親ジョブを表示すると、ジョブが失敗したことが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d048f-169">When you display the parent job, it shows that the job failed.</span></span>

```powershell
PS> $j

Id Name   PSJobTypeName State      HasMoreData   Location
-- ----   ------------- -----      -----------   --------
3  Job3   RemotingJob   Failed     False         localhost,Server...
```

<span data-ttu-id="d048f-170">ただし、 `Get-Job` 子ジョブを取得するコマンドを実行すると、1つの子ジョブが失敗したことが出力に示されます。</span><span class="sxs-lookup"><span data-stu-id="d048f-170">But when you run a `Get-Job` command that gets the child jobs, the output shows that only one child job failed.</span></span>

```powershell
PS> Get-Job -IncludeChildJobs

Id  Name   PSJobTypeName State      HasMoreData   Location    Command
--  ----   ------------- -----      -----------   --------    -------
3   Job3   RemotingJob   Failed     False         localhost,Server...
4   Job4                 Completed  True          localhost   Get-Date
5   Job5                 Failed     False         Server01    Get-Date
6   Job6                 Completed  True          Server02    Get-Date
```

<span data-ttu-id="d048f-171">すべての子ジョブの結果を取得するには、コマンドレットを使用して `Receive-Job` 親ジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="d048f-171">To get the results of all child jobs, use the `Receive-Job` cmdlet to get the results of the parent job.</span></span> <span data-ttu-id="d048f-172">ただし、次のコマンドに示すように、特定の子ジョブの結果を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="d048f-172">But you can also get the results of a particular child job, as shown in the following command.</span></span>

```powershell
PS> Receive-Job -Name Job6 -Keep | Format-Table ComputerName,
>> DateTime -AutoSize
ComputerName DateTime
------------ --------
Server02     Thursday, March 13, 2008 4:16:03 PM
```

<span data-ttu-id="d048f-173">PowerShell のバックグラウンドジョブの子ジョブ機能を使用すると、実行するジョブをより細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="d048f-173">The child jobs feature of PowerShell background jobs gives you more control over the jobs that you run.</span></span>

### <a name="job-types"></a><span data-ttu-id="d048f-174">ジョブの種類</span><span class="sxs-lookup"><span data-stu-id="d048f-174">Job types</span></span>

<span data-ttu-id="d048f-175">PowerShell では、タスクごとに異なる種類のジョブをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d048f-175">PowerShell supports different types of jobs for different tasks.</span></span> <span data-ttu-id="d048f-176">Windows PowerShell 3.0 以降では、開発者は、新しいジョブの種類を PowerShell に追加する "ジョブソースアダプター" を作成し、モジュールにジョブソースアダプターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d048f-176">Beginning in Windows PowerShell 3.0, developers can write "job source adapters" that add new job types to PowerShell and include the job source adapters in modules.</span></span>
<span data-ttu-id="d048f-177">モジュールをインポートするときに、セッションで新しいジョブの種類を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d048f-177">When you import the module, you can use the new job type in your session.</span></span>

<span data-ttu-id="d048f-178">たとえば、PSScheduledJob モジュールによってスケジュールされたジョブが追加され、PSWorkflow モジュールによってワークフロージョブが追加されます。</span><span class="sxs-lookup"><span data-stu-id="d048f-178">For example, the PSScheduledJob module adds scheduled jobs and the PSWorkflow module adds workflow jobs.</span></span>

<span data-ttu-id="d048f-179">カスタムジョブの種類は、標準の PowerShell バックグラウンドジョブとは大きく異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d048f-179">Custom jobs types might differ significantly from standard PowerShell background jobs.</span></span> <span data-ttu-id="d048f-180">たとえば、スケジュールされたジョブはディスクに保存されます。これらは、特定のセッションにのみ存在しません。</span><span class="sxs-lookup"><span data-stu-id="d048f-180">For example, scheduled jobs are saved on disk; they do not exist only in a particular session.</span></span> <span data-ttu-id="d048f-181">ワークフロージョブは、中断して再開することができます。</span><span class="sxs-lookup"><span data-stu-id="d048f-181">Workflow jobs can be suspended and resumed.</span></span>

<span data-ttu-id="d048f-182">カスタムジョブの管理に使用するコマンドレットは、ジョブの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d048f-182">The cmdlets that you use to manage custom jobs depend on the job type.</span></span> <span data-ttu-id="d048f-183">場合によっては、やなどの標準のジョブコマンドレットを使用し `Get-Job` `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="d048f-183">For some, you use the standard job cmdlets, such as `Get-Job` and `Start-Job`.</span></span> <span data-ttu-id="d048f-184">特定の種類のジョブのみを管理する特殊なコマンドレットが付属しています。</span><span class="sxs-lookup"><span data-stu-id="d048f-184">Others come with specialized cmdlets that manage only a particular type of job.</span></span> <span data-ttu-id="d048f-185">カスタムのジョブの種類の詳細については、ジョブの種類に関するヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d048f-185">For detailed information about custom job types, see the help topics about the job type.</span></span>

<span data-ttu-id="d048f-186">ジョブのジョブの種類を検索するには、 `Get-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d048f-186">To find the job type of a job, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="d048f-187">`Get-Job` さまざまな種類のジョブに対して異なるジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="d048f-187">`Get-Job` returns different job objects for different types of jobs.</span></span> <span data-ttu-id="d048f-188">が返すジョブオブジェクトの **PSJobTypeName** プロパティの値は、 `Get-Job` ジョブの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="d048f-188">The value of the **PSJobTypeName** property of the job objects that `Get-Job` returns indicates the job type.</span></span>

<span data-ttu-id="d048f-189">次の表に、PowerShell に付属するジョブの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="d048f-189">The following table lists the job types that come with PowerShell.</span></span>

|    <span data-ttu-id="d048f-190">ジョブの種類</span><span class="sxs-lookup"><span data-stu-id="d048f-190">Job Type</span></span>    |                       <span data-ttu-id="d048f-191">説明</span><span class="sxs-lookup"><span data-stu-id="d048f-191">Description</span></span>                        |
| -------------- | -------------------------------------------------------- |
| <span data-ttu-id="d048f-192">BackgroundJob</span><span class="sxs-lookup"><span data-stu-id="d048f-192">BackgroundJob</span></span>  | <span data-ttu-id="d048f-193">コマンドレットの使用を開始しました `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="d048f-193">Started using the `Start-Job` cmdlet.</span></span>                    |
| <span data-ttu-id="d048f-194">RemoteJob</span><span class="sxs-lookup"><span data-stu-id="d048f-194">RemoteJob</span></span>      | <span data-ttu-id="d048f-195">の **AsJob** パラメーターの使用を開始しました</span><span class="sxs-lookup"><span data-stu-id="d048f-195">Started using the **AsJob** parameter of the</span></span>             |
|                | <span data-ttu-id="d048f-196">`Invoke-Command` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d048f-196">`Invoke-Command` cmdlet.</span></span>                                 |
| <span data-ttu-id="d048f-197">PSWorkflowJob</span><span class="sxs-lookup"><span data-stu-id="d048f-197">PSWorkflowJob</span></span>  | <span data-ttu-id="d048f-198">ワークフローの **AsJob** パラメーターの使用を開始しました。</span><span class="sxs-lookup"><span data-stu-id="d048f-198">Started using the **AsJob** parameter of a workflow.</span></span>     |
| <span data-ttu-id="d048f-199">PSScheduledJob</span><span class="sxs-lookup"><span data-stu-id="d048f-199">PSScheduledJob</span></span> | <span data-ttu-id="d048f-200">ジョブトリガーによって開始されるスケジュールされたジョブのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="d048f-200">An instance of a scheduled job started by a job trigger.</span></span> |
| <span data-ttu-id="d048f-201">CIMJob</span><span class="sxs-lookup"><span data-stu-id="d048f-201">CIMJob</span></span>         | <span data-ttu-id="d048f-202">からコマンドレットの **AsJob** パラメーターの使用を開始しました</span><span class="sxs-lookup"><span data-stu-id="d048f-202">Started using the **AsJob** parameter of a cmdlet from a</span></span> |
|                | <span data-ttu-id="d048f-203">CDXML モジュール。</span><span class="sxs-lookup"><span data-stu-id="d048f-203">CDXML module.</span></span>                                            |
| <span data-ttu-id="d048f-204">Wmi ジョブ</span><span class="sxs-lookup"><span data-stu-id="d048f-204">WMIJob</span></span>         | <span data-ttu-id="d048f-205">からコマンドレットの **AsJob** パラメーターの使用を開始しました</span><span class="sxs-lookup"><span data-stu-id="d048f-205">Started using the **AsJob** parameter of a cmdlet from a</span></span> |
|                | <span data-ttu-id="d048f-206">WMI モジュール。</span><span class="sxs-lookup"><span data-stu-id="d048f-206">WMI module.</span></span>                                              |
| <span data-ttu-id="d048f-207">PSEventJob</span><span class="sxs-lookup"><span data-stu-id="d048f-207">PSEventJob</span></span>     | <span data-ttu-id="d048f-208">を使用してを作成 `Register-ObjectEvent` し、</span><span class="sxs-lookup"><span data-stu-id="d048f-208">Created using`Register-ObjectEvent` and specifying an</span></span>    |
|                | <span data-ttu-id="d048f-209">**action パラメーターを** 使用したアクション。</span><span class="sxs-lookup"><span data-stu-id="d048f-209">action with the **Action** parameter.</span></span>                    |

<span data-ttu-id="d048f-210">注: コマンドレットを使用して `Get-Job` 特定の種類のジョブを取得する前に、ジョブの種類を追加するモジュールが現在のセッションにインポートされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d048f-210">NOTE: Before using the `Get-Job` cmdlet to get jobs of a particular type, verify that the module that adds the job type is imported into the current session.</span></span>
<span data-ttu-id="d048f-211">それ以外の場合、 `Get-Job` はその種類のジョブを取得しません。</span><span class="sxs-lookup"><span data-stu-id="d048f-211">Otherwise, `Get-Job` does not get jobs of that type.</span></span>

## <a name="examples"></a><span data-ttu-id="d048f-212">例</span><span class="sxs-lookup"><span data-stu-id="d048f-212">Examples</span></span>

<span data-ttu-id="d048f-213">次のコマンドは、ローカルのバックグラウンドジョブ、リモートのバックグラウンドジョブ、ワークフロージョブ、およびスケジュールされたジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="d048f-213">The following commands create a local background job, a remote background job, a workflow job, and a scheduled job.</span></span> <span data-ttu-id="d048f-214">次に、コマンドレットを使用して `Get-Job` ジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="d048f-214">Then, it uses the `Get-Job` cmdlet to get the jobs.</span></span> <span data-ttu-id="d048f-215">`Get-Job` は、スケジュールされたジョブを取得しませんが、スケジュールされたジョブの開始インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d048f-215">`Get-Job` does not get the scheduled job, but it gets any started instances of the scheduled job.</span></span>

<span data-ttu-id="d048f-216">ローカルコンピューターでバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="d048f-216">Start a background job on the local computer.</span></span>

```powershell
PS> Start-Job -Name LocalData {Get-Process}

Id Name        PSJobTypeName   State   HasMoreData   Location   Command
-- ----        -------------   -----   -----------   --------   -------
2  LocalData   BackgroundJob   Running        True   localhost  Get-Process
```

<span data-ttu-id="d048f-217">リモートコンピューターで実行されるバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="d048f-217">Start a background job that runs on a remote computer.</span></span>

```powershell
PS> Invoke-Command -ComputerName Server01 {Get-Process} `
-AsJob -JobName RemoteData

Id  Name        PSJobTypeName  State   HasMoreData   Location   Command
--  ----        -------------  -----   -----------   --------   -------
2   RemoteData  RemoteJob      Running        True   Server01   Get-Process
```

<span data-ttu-id="d048f-218">スケジュールされたジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="d048f-218">Create a scheduled job</span></span>

```powershell
PS>  Register-ScheduledJob -Name ScheduledJob -ScriptBlock `
 {Get-Process} -Trigger (New-JobTrigger -Once -At "3 PM")

Id         Name            JobTriggers     Command       Enabled
--         ----            -----------     -------       -------
1          ScheduledJob    1               Get-Process   True
```

<span data-ttu-id="d048f-219">ワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="d048f-219">Create a workflow.</span></span>

```powershell
PS> workflow Test-Workflow {Get-Process}
```

<span data-ttu-id="d048f-220">ワークフローをジョブとして実行します。</span><span class="sxs-lookup"><span data-stu-id="d048f-220">Run the workflow as a job.</span></span>

```powershell

PS> Test-Workflow -AsJob -JobName TestWFJob

Id  Name       PSJobTypeName   State   HasMoreData   Location   Command
--  ----       -------------   -----   -----------   --------   -------
2   TestWFJob  PSWorkflowJob   NotStarted     True   localhost  Get-Process
```

<span data-ttu-id="d048f-221">ジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="d048f-221">Get the jobs.</span></span> <span data-ttu-id="d048f-222">このコマンドは、スケジュールされ `Get-Job` たジョブを取得しませんが、開始されたスケジュールされたジョブのインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d048f-222">The `Get-Job` command does not get scheduled jobs, but it gets instances of the scheduled job that are started.</span></span>

```powershell
PS> Get-Job

Id  Name         PSJobTypeName  State     HasMoreData  Location  Command
--  ----         -------------  -----     -----------  --------  -------
2   LocalData    BackgroundJob  Completed True         localhost Get-Process
4   RemoteData   RemoteJob      Completed True         Server01  Get-Process
6   TestWFJob    PSWorkflowJob  Completed True         localhost WorkflowJob
8   ScheduledJob PSScheduledJob Completed True         localhost Get-Process
```

<span data-ttu-id="d048f-223">スケジュールされたジョブを取得するには、コマンドレットを使用し `Get-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="d048f-223">To get scheduled jobs, use the `Get-ScheduledJob` cmdlet.</span></span>

```powershell
PS> Get-ScheduledJob

Id         Name            JobTriggers     Command       Enabled
--         ----            -----------     -------       -------
1          ScheduledJob    1               Get-Process   True
```

## <a name="see-also"></a><span data-ttu-id="d048f-224">関連項目</span><span class="sxs-lookup"><span data-stu-id="d048f-224">See also</span></span>

- [<span data-ttu-id="d048f-225">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="d048f-225">about_Jobs</span></span>](about_Jobs.md)
- [<span data-ttu-id="d048f-226">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="d048f-226">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="d048f-227">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="d048f-227">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="d048f-228">about_Remote</span><span class="sxs-lookup"><span data-stu-id="d048f-228">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="d048f-229">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="d048f-229">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
- [<span data-ttu-id="d048f-230">Start-Job</span><span class="sxs-lookup"><span data-stu-id="d048f-230">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="d048f-231">Get-Job</span><span class="sxs-lookup"><span data-stu-id="d048f-231">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="d048f-232">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="d048f-232">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="d048f-233">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="d048f-233">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="d048f-234">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="d048f-234">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="d048f-235">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="d048f-235">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
- [<span data-ttu-id="d048f-236">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="d048f-236">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)
- [<span data-ttu-id="d048f-237">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="d048f-237">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)
