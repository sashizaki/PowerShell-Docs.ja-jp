---
description: PowerShell バックグラウンドジョブが、現在のセッションと対話せずにバックグラウンドでコマンドまたは式を実行する方法について説明します。
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_jobs?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Jobs
ms.openlocfilehash: 862fbf54b927bb70c68e4b3cc43c564f178f9db5
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599700"
---
# <a name="about-jobs"></a><span data-ttu-id="c119d-103">ジョブについて</span><span class="sxs-lookup"><span data-stu-id="c119d-103">About Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="c119d-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="c119d-104">Short description</span></span>
<span data-ttu-id="c119d-105">PowerShell バックグラウンドジョブが、現在のセッションと対話せずにバックグラウンドでコマンドまたは式を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c119d-105">Provides information about how PowerShell background jobs run a command or expression in the background without interacting with the current session.</span></span>

## <a name="long-description"></a><span data-ttu-id="c119d-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="c119d-106">Long description</span></span>

<span data-ttu-id="c119d-107">PowerShell は、ジョブを使用してコマンドとスクリプトを同時に実行します。</span><span class="sxs-lookup"><span data-stu-id="c119d-107">PowerShell concurrently runs commands and scripts through jobs.</span></span> <span data-ttu-id="c119d-108">同時実行をサポートするために PowerShell によって提供されるジョブの種類は3つあります。</span><span class="sxs-lookup"><span data-stu-id="c119d-108">There are three jobs types provided by PowerShell to support concurrency.</span></span>

- <span data-ttu-id="c119d-109">`RemoteJob` -コマンドとスクリプトは、リモートセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="c119d-109">`RemoteJob` - Commands and scripts run on a remote session.</span></span> <span data-ttu-id="c119d-110">詳細については、「 [about_Remote_Jobs](about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c119d-110">For information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
- <span data-ttu-id="c119d-111">`BackgroundJob` -コマンドとスクリプトは、ローカルコンピューター上で個別のプロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="c119d-111">`BackgroundJob` - Commands and scripts run in a separate process on the local machine.</span></span>
- <span data-ttu-id="c119d-112">`PSTaskJob` または `ThreadJob` -コマンドとスクリプトは、ローカルコンピューター上の同じプロセス内の別のスレッドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="c119d-112">`PSTaskJob` or `ThreadJob` - Commands and scripts run in a separate thread within the same process on the local machine.</span></span> <span data-ttu-id="c119d-113">詳細については、「 [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c119d-113">For more information, see [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).</span></span>

<span data-ttu-id="c119d-114">別のコンピューターまたは別のプロセスでスクリプトをリモートで実行すると、優れた分離が実現します。</span><span class="sxs-lookup"><span data-stu-id="c119d-114">Running scripts remotely, on a separate machine or in a separate process, provides great isolation.</span></span> <span data-ttu-id="c119d-115">リモートジョブで発生したエラーは、他の実行中のジョブ、またはジョブを開始した親セッションには影響しません。</span><span class="sxs-lookup"><span data-stu-id="c119d-115">Any errors that occur in the remote job do not affect other running jobs or the parent session that started the job.</span></span> <span data-ttu-id="c119d-116">ただし、リモート処理層では、オブジェクトのシリアル化などのオーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="c119d-116">However, the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="c119d-117">すべてのオブジェクトは、親セッションとリモート (ジョブ) セッションの間で渡されるときにシリアル化および逆シリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="c119d-117">All objects are serialized and deserialized as they are passed between the parent session and the remote (job) session.</span></span> <span data-ttu-id="c119d-118">大きな複雑なデータオブジェクトのシリアル化は、大量のコンピューティングリソースとメモリリソースを消費し、ネットワーク経由で大量のデータを転送することがあります。</span><span class="sxs-lookup"><span data-stu-id="c119d-118">Serialization of large complex data objects can consume large amounts of compute and memory resources and transfer large amounts of data across the network.</span></span>

<span data-ttu-id="c119d-119">スレッドベースのジョブは、異なるスレッドで同じプロセスで実行されるため、リモートジョブやバックグラウンドジョブほど堅牢ではありません。</span><span class="sxs-lookup"><span data-stu-id="c119d-119">Thread-based jobs are not as robust as remote and background jobs, because they run in the same process on different threads.</span></span> <span data-ttu-id="c119d-120">あるジョブで、プロセスをクラッシュさせる重大なエラーが発生している場合は、プロセス内の他のすべてのジョブが終了します。</span><span class="sxs-lookup"><span data-stu-id="c119d-120">If one job has a critical error that crashes the process, then all other jobs in the process are terminated.</span></span>

<span data-ttu-id="c119d-121">ただし、スレッドベースのジョブではオーバーヘッドが少なくなります。</span><span class="sxs-lookup"><span data-stu-id="c119d-121">However, thread-based jobs require less overhead.</span></span> <span data-ttu-id="c119d-122">これらは、リモート処理レイヤーまたはシリアル化を使用しません。</span><span class="sxs-lookup"><span data-stu-id="c119d-122">They don't use the remoting layer or serialization.</span></span> <span data-ttu-id="c119d-123">結果オブジェクトは、現在のセッションのライブオブジェクトへの参照として返されます。</span><span class="sxs-lookup"><span data-stu-id="c119d-123">The result objects are returned as references to live objects in the current session.</span></span> <span data-ttu-id="c119d-124">このオーバーヘッドがないと、スレッドベースのジョブはより高速に実行され、他の種類のジョブよりも使用されるリソースが少なくなります。</span><span class="sxs-lookup"><span data-stu-id="c119d-124">Without this overhead, thread-based jobs run faster and use fewer resources than the other job types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c119d-125">ジョブを作成した親セッションもジョブの状態を監視し、パイプラインデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="c119d-125">The parent session that created the job also monitors the job status and collects pipeline data.</span></span> <span data-ttu-id="c119d-126">ジョブが完了状態になると、親プロセスによってジョブの子プロセスが終了します。</span><span class="sxs-lookup"><span data-stu-id="c119d-126">The job child process is terminated by the parent process once the job reaches a finished state.</span></span> <span data-ttu-id="c119d-127">親セッションが終了すると、実行中のすべての子ジョブが子プロセスと共に終了します。</span><span class="sxs-lookup"><span data-stu-id="c119d-127">If the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span>

<span data-ttu-id="c119d-128">この状況に対処するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="c119d-128">There are two ways work around this situation:</span></span>

1. <span data-ttu-id="c119d-129">`Invoke-Command`切断されたセッションで実行されるジョブを作成するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="c119d-129">Use `Invoke-Command` to create jobs that run in disconnected sessions.</span></span> <span data-ttu-id="c119d-130">詳細については、「 [about_Remote_Jobs](about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c119d-130">For more information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
1. <span data-ttu-id="c119d-131">`Start-Process`ジョブではなく新しいプロセスを作成するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="c119d-131">Use `Start-Process` to create a new process rather than a job.</span></span> <span data-ttu-id="c119d-132">詳細については、「 [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c119d-132">For more information, see [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span></span>

## <a name="the-job-cmdlets"></a><span data-ttu-id="c119d-133">ジョブのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="c119d-133">The job cmdlets</span></span>

|<span data-ttu-id="c119d-134">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c119d-134">Cmdlet</span></span>          |<span data-ttu-id="c119d-135">説明</span><span class="sxs-lookup"><span data-stu-id="c119d-135">Description</span></span>                                            |
|----------------|-------------------------------------------------------|
|`Start-Job`     |<span data-ttu-id="c119d-136">ローカルコンピューターでバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="c119d-136">Starts a background job on a local computer.</span></span>           |
|`Get-Job`       |<span data-ttu-id="c119d-137">で開始されたバックグラウンドジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="c119d-137">Gets the background jobs that were started in the</span></span>      |
|                |<span data-ttu-id="c119d-138">現在のセッション。</span><span class="sxs-lookup"><span data-stu-id="c119d-138">current session.</span></span>                                       |
|`Receive-Job`   |<span data-ttu-id="c119d-139">バックグラウンドジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="c119d-139">Gets the results of background jobs.</span></span>                   |
|`Stop-Job`      |<span data-ttu-id="c119d-140">バックグラウンドジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="c119d-140">Stops a background job.</span></span>                                |
|`Wait-Job`      |<span data-ttu-id="c119d-141">1つまたはすべてのジョブが完了するまで、コマンドプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="c119d-141">Suppresses the command prompt until one or all jobs are</span></span>|
|                |<span data-ttu-id="c119d-142">完了.</span><span class="sxs-lookup"><span data-stu-id="c119d-142">complete.</span></span>                                              |
|`Remove-Job`    |<span data-ttu-id="c119d-143">バックグラウンドジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="c119d-143">Deletes a background job.</span></span>                              |
|`Invoke-Command`|<span data-ttu-id="c119d-144">**AsJob** パラメーターは、に対してバックグラウンドジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="c119d-144">The **AsJob** parameter creates a background job on a</span></span>  |
|                |<span data-ttu-id="c119d-145">リモートコンピューター。</span><span class="sxs-lookup"><span data-stu-id="c119d-145">remote computer.</span></span> <span data-ttu-id="c119d-146">を使用して、 `Invoke-Command`</span><span class="sxs-lookup"><span data-stu-id="c119d-146">You can use `Invoke-Command` to run</span></span>   |
|                |<span data-ttu-id="c119d-147">を含め、任意のジョブコマンドをリモートで実行 `Start-Job` します。</span><span class="sxs-lookup"><span data-stu-id="c119d-147">any job command remotely, including `Start-Job`.</span></span>       |

## <a name="how-to-start-a-job-on-the-local-computer"></a><span data-ttu-id="c119d-148">ローカルコンピューターでジョブを開始する方法</span><span class="sxs-lookup"><span data-stu-id="c119d-148">How to start a job on the local computer</span></span>

<span data-ttu-id="c119d-149">ローカルコンピューターでバックグラウンドジョブを開始するには、コマンドレットを使用し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="c119d-149">To start a background job on the local computer, use the `Start-Job` cmdlet.</span></span>

<span data-ttu-id="c119d-150">コマンドを記述するには、 `Start-Job` ジョブを実行するコマンドを中かっこ ( `{}` ) で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c119d-150">To write a `Start-Job` command, enclose the command that the job runs in curly braces (`{}`).</span></span> <span data-ttu-id="c119d-151">**ScriptBlock** パラメーターを使用して、コマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="c119d-151">Use the **ScriptBlock** parameter to specify the command.</span></span>

<span data-ttu-id="c119d-152">次のコマンドは、ローカルコンピューターでコマンドを実行するバックグラウンドジョブを開始し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="c119d-152">The following command starts a background job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="c119d-153">バックグラウンドジョブを開始すると、ジョブが完了するまでに時間がかかる場合でも、コマンドプロンプトがすぐに返されます。</span><span class="sxs-lookup"><span data-stu-id="c119d-153">When you start a background job, the command prompt returns immediately, even if the job takes an extended time to complete.</span></span> <span data-ttu-id="c119d-154">ジョブの実行中は、中断されることなく引き続きセッションで作業できます。</span><span class="sxs-lookup"><span data-stu-id="c119d-154">You can continue to work in the session without interruption while the job runs.</span></span>

<span data-ttu-id="c119d-155">この `Start-Job` コマンドは、ジョブを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c119d-155">The `Start-Job` command returns an object that represents the job.</span></span> <span data-ttu-id="c119d-156">ジョブ オブジェクトには、ジョブに関する有用な情報が含まれていますが、ジョブの結果は含まれません。</span><span class="sxs-lookup"><span data-stu-id="c119d-156">The job object contains useful information about the job, but it does not contain the job results.</span></span>

<span data-ttu-id="c119d-157">ジョブオブジェクトを変数に保存し、他の **ジョブ** コマンドレットと共に使用してバックグラウンドジョブを管理できます。</span><span class="sxs-lookup"><span data-stu-id="c119d-157">You can save the job object in a variable and then use it with the other **Job** cmdlets to manage the background job.</span></span> <span data-ttu-id="c119d-158">次のコマンドは、ジョブオブジェクトを開始し、結果として生成されたジョブオブジェクトを変数に保存し `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="c119d-158">The following command starts a job object and saves the resulting job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="c119d-159">PowerShell 6.0 以降では、パイプラインの最後にバックグラウンド演算子 () を使用して、 `&` バックグラウンドジョブを開始できます。</span><span class="sxs-lookup"><span data-stu-id="c119d-159">Beginning in PowerShell 6.0, you can use the background operator (`&`) at the end of a pipeline to start a background job.</span></span> <span data-ttu-id="c119d-160">詳細については、「 [background operator](about_Operators.md#background-operator-)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c119d-160">For more information, see [background operator](about_Operators.md#background-operator-).</span></span>

<span data-ttu-id="c119d-161">Background 演算子を使用することは、前の例のコマンドレットを使用するのと機能的には同じです `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="c119d-161">Using the background operator is functionally equivalent to using the `Start-Job` cmdlet in the previous example.</span></span>

```powershell
$job = Get-Process &
```

## <a name="getting-job-objects"></a><span data-ttu-id="c119d-162">ジョブオブジェクトの取得</span><span class="sxs-lookup"><span data-stu-id="c119d-162">Getting job objects</span></span>

<span data-ttu-id="c119d-163">`Get-Job`コマンドレットは、現在のセッションで開始されたバックグラウンドジョブを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c119d-163">The `Get-Job` cmdlet returns objects that represent the background jobs that were started in the current session.</span></span> <span data-ttu-id="c119d-164">パラメーターを指定しない場合は、 `Get-Job` 現在のセッションで開始されたすべてのジョブが返されます。</span><span class="sxs-lookup"><span data-stu-id="c119d-164">Without parameters, `Get-Job` returns all of the jobs that were started in the current session.</span></span>

```powershell
Get-Job
```

<span data-ttu-id="c119d-165">ジョブオブジェクトには、ジョブが完了したかどうかを示すジョブの状態が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c119d-165">The job object contains the state of the job, which indicates whether the job has finished.</span></span> <span data-ttu-id="c119d-166">完了したジョブの状態が " **完了** " または " **失敗**" になっています。</span><span class="sxs-lookup"><span data-stu-id="c119d-166">A finished job has a state of **Complete** or **Failed**.</span></span> <span data-ttu-id="c119d-167">ジョブも **ブロック** されているか、実行され **ている** 可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c119d-167">A job might also be **Blocked** or **Running**.</span></span>

```Output
Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Complete   True         localhost  Get-Process
```

<span data-ttu-id="c119d-168">ジョブオブジェクトを変数に保存し、それを使用して後のコマンドでジョブを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="c119d-168">You can save the job object in a variable and use it to represent the job in a later command.</span></span> <span data-ttu-id="c119d-169">次のコマンドは、ID が1のジョブを取得し、変数に保存し `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="c119d-169">The following command gets the job with ID 1 and saves it in the `$job` variable.</span></span>

```powershell
$job = Get-Job -Id 1
```

## <a name="getting-the-results-of-a-job"></a><span data-ttu-id="c119d-170">ジョブの結果を取得する</span><span class="sxs-lookup"><span data-stu-id="c119d-170">Getting the results of a job</span></span>

<span data-ttu-id="c119d-171">バックグラウンドジョブを実行しても、結果はすぐには表示されません。</span><span class="sxs-lookup"><span data-stu-id="c119d-171">When you run a background job, the results do not appear immediately.</span></span> <span data-ttu-id="c119d-172">バックグラウンドジョブの結果を取得するには、コマンドレットを使用し `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="c119d-172">To get the results of a background job, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="c119d-173">次の例では、 `Receive-Job` コマンドレットは、変数内の job オブジェクトを使用してジョブの結果を取得し `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="c119d-173">The following example, the `Receive-Job` cmdlet gets the results of the job using job object in the `$job` variable.</span></span>

```powershell
Receive-Job -Job $job
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
    103       4    11328       9692    56           1176 audiodg
    804      14    12228      14108   100   101.74  1740 CcmExec
    668       7     2672       6168   104    32.26   488 csrss
...
```

<span data-ttu-id="c119d-174">ジョブの結果を変数に保存できます。</span><span class="sxs-lookup"><span data-stu-id="c119d-174">You can save the results of a job in a variable.</span></span> <span data-ttu-id="c119d-175">次のコマンドは、変数内のジョブの結果を `$job` 変数に保存し `$results` ます。</span><span class="sxs-lookup"><span data-stu-id="c119d-175">The following command saves the results of the job in the `$job` variable to the `$results` variable.</span></span>

```powershell
$results = Receive-Job -Job $job
```

### <a name="getting-and-keeping-partial-job-results"></a><span data-ttu-id="c119d-176">部分的なジョブ結果の取得と保持</span><span class="sxs-lookup"><span data-stu-id="c119d-176">Getting and keeping partial job results</span></span>

<span data-ttu-id="c119d-177">コマンドレットでは、 `Receive-Job` バックグラウンドジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="c119d-177">The `Receive-Job` cmdlet gets the results of a background job.</span></span> <span data-ttu-id="c119d-178">ジョブが完了すると、は `Receive-Job` すべてのジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="c119d-178">If the job is complete, `Receive-Job` gets all job results.</span></span> <span data-ttu-id="c119d-179">ジョブがまだ実行中の場合は、 `Receive-Job` これまでに生成された結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="c119d-179">If the job is still running, `Receive-Job` gets the results that have been generated thus far.</span></span> <span data-ttu-id="c119d-180">`Receive-Job`コマンドをもう一度実行して、残りの結果を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="c119d-180">You can run `Receive-Job` commands again to get the remaining results.</span></span>

<span data-ttu-id="c119d-181">既定では、は、 `Receive-Job` ジョブの結果が格納されているキャッシュから結果を削除します。</span><span class="sxs-lookup"><span data-stu-id="c119d-181">By default, `Receive-Job` deletes the results from the cache where job results are stored.</span></span> <span data-ttu-id="c119d-182">もう一度を実行すると `Receive-Job` 、最初の実行後に到着した新しい結果だけが取得されます。</span><span class="sxs-lookup"><span data-stu-id="c119d-182">When you run `Receive-Job` again, you get only the new results that arrived after the first run.</span></span>

<span data-ttu-id="c119d-183">次のコマンドは、 `Receive-Job` ジョブが完了する前に実行されたコマンドの結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="c119d-183">The following commands show the results of `Receive-Job` commands run before the job is complete.</span></span>

```powershell
C:\PS> Receive-Job -Job $job

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec

C:\PS> Receive-Job -Job $job

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    68       3     2632        664    29     0.36   1388 ccmsetup
   749      22    21468      19940   203   122.13   3644 communicator
   905       7     2980       2628    34   197.97    424 csrss
  1121      25    28408      32940   174   430.14   3048 explorer
```

<span data-ttu-id="c119d-184">返され `Receive-Job` たジョブの結果がから削除されないようにするには、Keep パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c119d-184">Use the **Keep** parameter to prevent `Receive-Job` from deleting the job results that are returned.</span></span> <span data-ttu-id="c119d-185">次のコマンドは、まだ完了していないジョブで **Keep** パラメーターを使用した場合の影響を示しています。</span><span class="sxs-lookup"><span data-stu-id="c119d-185">The following commands show the effect of using the **Keep** parameter on a job that is not yet complete.</span></span>

```powershell
C:\PS> Receive-Job -Job $job -Keep

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec

C:\PS> Receive-Job -Job $job -Keep

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec
     68       3     2632        664    29     0.36   1388 ccmsetup
    749      22    21468      19940   203   122.13   3644 communicator
    905       7     2980       2628    34   197.97    424 csrss
   1121      25    28408      32940   174   430.14   3048 explorer
```

### <a name="waiting-for-the-results"></a><span data-ttu-id="c119d-186">結果を待機しています</span><span class="sxs-lookup"><span data-stu-id="c119d-186">Waiting for the results</span></span>

<span data-ttu-id="c119d-187">完了までに時間がかかるコマンドを実行する場合は、ジョブオブジェクトのプロパティを使用して、ジョブがいつ完了したかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="c119d-187">If you run a command that takes a long time to complete, you can use the properties of the job object to determine when the job is complete.</span></span> <span data-ttu-id="c119d-188">次のコマンドでは、オブジェクトを使用して、 `Get-Job` 現在のセッションのすべてのバックグラウンドジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="c119d-188">The following command uses the `Get-Job` object to get all of the background jobs in the current session.</span></span>

```powershell
Get-Job
```

<span data-ttu-id="c119d-189">結果はテーブルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c119d-189">The results appear in a table.</span></span> <span data-ttu-id="c119d-190">ジョブの状態が [ **状態** 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c119d-190">The status of the job appears in the **State** column.</span></span>

```Output
Id Name  PSJobTypeName State    HasMoreData Location  Command
-- ----  ------------- -----    ----------- --------  -------
1  Job1  BackgroundJob Complete True        localhost Get-Process
2  Job2  BackgroundJob Running  True        localhost Get-EventLog -Log ...
3  Job3  BackgroundJob Complete True        localhost dir -Path C:\* -Re...
```

<span data-ttu-id="c119d-191">この場合、 **State** プロパティは、ジョブ2がまだ実行されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="c119d-191">In this case, the **State** property reveals that Job 2 is still running.</span></span> <span data-ttu-id="c119d-192">コマンドレットを使用して `Receive-Job` ジョブの結果を取得した場合、結果は不完全になります。</span><span class="sxs-lookup"><span data-stu-id="c119d-192">If you were to use the `Receive-Job` cmdlet to get the job results now, the results would be incomplete.</span></span> <span data-ttu-id="c119d-193">`Receive-Job`コマンドレットを繰り返し使用して、すべての結果を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="c119d-193">You can use the `Receive-Job` cmdlet repeatedly to get all of the results.</span></span> <span data-ttu-id="c119d-194">**State** プロパティを使用して、ジョブがいつ完了したかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c119d-194">Use the **State** property to determine when the job is complete.</span></span>

<span data-ttu-id="c119d-195">コマンドレットの **Wait** パラメーターを使用することもでき `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="c119d-195">You can also use the **Wait** parameter of the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="c119d-196">使用時にこのパラメーターを使用すると、コマンドレットは、ジョブが完了し、すべての結果を使用できるようになるまで、コマンドプロンプトを返しません。</span><span class="sxs-lookup"><span data-stu-id="c119d-196">When use use this parameter, the cmdlet does not return the command prompt until the job is completed and all results are available.</span></span>

<span data-ttu-id="c119d-197">また、コマンドレットを使用して、 `Wait-Job` ジョブの結果のいずれかまたはすべてを待機することもできます。</span><span class="sxs-lookup"><span data-stu-id="c119d-197">You can also use the `Wait-Job` cmdlet to wait for any or all of the results of the job.</span></span> <span data-ttu-id="c119d-198">`Wait-Job` 1つ以上の特定のジョブまたはすべてのジョブを待機できます。</span><span class="sxs-lookup"><span data-stu-id="c119d-198">`Wait-Job` lets you wait for one or more specific job or for all jobs.</span></span>
<span data-ttu-id="c119d-199">次のコマンドは、 `Wait-Job` コマンドレットを使用して、 **ID** を持つジョブを待機します。</span><span class="sxs-lookup"><span data-stu-id="c119d-199">The following command uses the `Wait-Job` cmdlet to wait for a job with **ID**</span></span>
10.

```powershell
Wait-Job -ID 10
```

<span data-ttu-id="c119d-200">その結果、ジョブが完了するまで PowerShell プロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="c119d-200">As a result, the PowerShell prompt is suppressed until the job is completed.</span></span>

<span data-ttu-id="c119d-201">事前に定義した時間が経過するまで待機することもできます。</span><span class="sxs-lookup"><span data-stu-id="c119d-201">You can also wait for a predetermined period of time.</span></span> <span data-ttu-id="c119d-202">このコマンドでは、 **Timeout** パラメーターを使用して、待機時間を120秒に制限します。</span><span class="sxs-lookup"><span data-stu-id="c119d-202">This command uses the **Timeout** parameter to limit the wait to 120 seconds.</span></span> <span data-ttu-id="c119d-203">時間が経過すると、コマンドプロンプトは返されますが、ジョブはバックグラウンドで実行され続けます。</span><span class="sxs-lookup"><span data-stu-id="c119d-203">When the time expires, the command prompt returns, but the job continues to run in the background.</span></span>

```powershell
Wait-Job -ID 10 -Timeout 120
```

## <a name="stopping-a-job"></a><span data-ttu-id="c119d-204">ジョブの停止</span><span class="sxs-lookup"><span data-stu-id="c119d-204">Stopping a job</span></span>

<span data-ttu-id="c119d-205">バックグラウンドジョブを停止するには、 `Stop-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c119d-205">To stop a background job, use the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="c119d-206">次のコマンドは、システムイベントログ内のすべてのエントリを取得するジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="c119d-206">The following command starts a job to get every entry in the System event log.</span></span> <span data-ttu-id="c119d-207">ジョブオブジェクトは変数に保存され `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="c119d-207">It saves the job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-EventLog -Log System}
```

<span data-ttu-id="c119d-208">次のコマンドは、ジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="c119d-208">The following command stops the job.</span></span> <span data-ttu-id="c119d-209">パイプライン演算子 () を使用して `|` 、変数内のジョブをに送信し `$job` `Stop-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="c119d-209">It uses a pipeline operator (`|`) to send the job in the `$job` variable to `Stop-Job`.</span></span>

```powershell
$job | Stop-Job
```

## <a name="deleting-a-job"></a><span data-ttu-id="c119d-210">ジョブの削除</span><span class="sxs-lookup"><span data-stu-id="c119d-210">Deleting a job</span></span>

<span data-ttu-id="c119d-211">バックグラウンドジョブを削除するには、 `Remove-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c119d-211">To delete a background job, use the `Remove-Job` cmdlet.</span></span> <span data-ttu-id="c119d-212">次のコマンドは、変数内のジョブを削除し `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="c119d-212">The following command deletes the job in the `$job` variable.</span></span>

```powershell
Remove-Job -Job $job
```

## <a name="investigating-a-failed-job"></a><span data-ttu-id="c119d-213">失敗したジョブの調査</span><span class="sxs-lookup"><span data-stu-id="c119d-213">Investigating a failed job</span></span>

<span data-ttu-id="c119d-214">ジョブは、さまざまな理由で失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c119d-214">Jobs can fail for many reasons.</span></span> <span data-ttu-id="c119d-215">job オブジェクトには、失敗の原因に関する情報を含む **Reason** プロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c119d-215">the job object contains a **Reason** property that contains information about the cause of the failure.</span></span>

<span data-ttu-id="c119d-216">次の例では、必要な資格情報を使用せずにジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="c119d-216">The following example starts a job without the required credentials.</span></span>

```powershell
$job = Start-Job -ScriptBlock {New-Item -Path HKLM:\Software\MyCompany}
Get-Job $job

Id Name  PSJobTypeName State  HasMoreData  Location  Command
-- ----  ------------- -----  -----------  --------  -------
1  Job1  BackgroundJob Failed False        localhost New-Item -Path HKLM:...
```

<span data-ttu-id="c119d-217">**Reason** プロパティを調べて、ジョブが失敗する原因となったエラーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="c119d-217">Inspect the **Reason** property to find the error that caused the job to fail.</span></span>

```powershell
$job.ChildJobs[0].JobStateInfo.Reason
```

<span data-ttu-id="c119d-218">この場合、リモートコンピューターでコマンドを実行するための明示的な資格情報が必要であったため、ジョブが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="c119d-218">In this case, the job failed because the remote computer required explicit credentials to run the command.</span></span> <span data-ttu-id="c119d-219">**Reason** プロパティには、次のメッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c119d-219">The **Reason** property contains the following message:</span></span>

> <span data-ttu-id="c119d-220">リモートサーバーに接続できませんでした。次のエラーメッセージが表示されました: "アクセスが拒否されました。"</span><span class="sxs-lookup"><span data-stu-id="c119d-220">Connecting to remote server failed with the following error message: "Access is denied".</span></span>

## <a name="see-also"></a><span data-ttu-id="c119d-221">関連項目</span><span class="sxs-lookup"><span data-stu-id="c119d-221">See also</span></span>

- [<span data-ttu-id="c119d-222">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="c119d-222">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="c119d-223">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="c119d-223">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="c119d-224">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="c119d-224">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="c119d-225">about_Remote</span><span class="sxs-lookup"><span data-stu-id="c119d-225">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="c119d-226">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="c119d-226">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="c119d-227">Start-Job</span><span class="sxs-lookup"><span data-stu-id="c119d-227">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="c119d-228">Get-Job</span><span class="sxs-lookup"><span data-stu-id="c119d-228">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="c119d-229">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="c119d-229">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="c119d-230">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="c119d-230">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="c119d-231">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="c119d-231">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="c119d-232">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="c119d-232">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="c119d-233">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="c119d-233">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
