---
description: PowerShell スレッドベースのジョブに関する情報を提供します。 スレッドジョブは、現在のセッションプロセス内の別のスレッドでコマンドまたは式を実行するバックグラウンドジョブの一種です。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 11/11/2020
online version: 1.0.0
schema: 2.0.0
title: about_Thread_Jobs
ms.openlocfilehash: ba6251a195d3efdebd427b3f705386336b069211
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524843"
---
# <a name="about-thread-jobs"></a><span data-ttu-id="fa5dc-105">スレッドジョブについて</span><span class="sxs-lookup"><span data-stu-id="fa5dc-105">About Thread Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="fa5dc-106">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="fa5dc-106">Short description</span></span>

<span data-ttu-id="fa5dc-107">PowerShell スレッドベースのジョブに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-107">Provides information about PowerShell thread-based jobs.</span></span> <span data-ttu-id="fa5dc-108">スレッドジョブは、現在のセッションプロセス内の別のスレッドでコマンドまたは式を実行するバックグラウンドジョブの一種です。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-108">A thread job is a type of background job that runs a command or expression in a separate thread within the current session process.</span></span>

## <a name="long-description"></a><span data-ttu-id="fa5dc-109">長い説明</span><span class="sxs-lookup"><span data-stu-id="fa5dc-109">Long description</span></span>

<span data-ttu-id="fa5dc-110">PowerShell は、ジョブを使用してコマンドとスクリプトを同時に実行します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-110">PowerShell concurrently runs commands and scripts through jobs.</span></span> <span data-ttu-id="fa5dc-111">同時実行をサポートするために PowerShell によって提供されるジョブの種類は3つあります。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-111">There are three jobs types provided by PowerShell to support concurrency.</span></span>

- <span data-ttu-id="fa5dc-112">`RemoteJob` -コマンドとスクリプトはリモートセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-112">`RemoteJob` - Commands and scripts run in a remote session.</span></span> <span data-ttu-id="fa5dc-113">詳細については、「 [about_Remote_Jobs](about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-113">For information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
- <span data-ttu-id="fa5dc-114">`BackgroundJob` -コマンドとスクリプトは、ローカルコンピューター上で個別のプロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-114">`BackgroundJob` - Commands and scripts run in a separate process on the local machine.</span></span> <span data-ttu-id="fa5dc-115">詳細については、「[about_Jobs](about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-115">For more information, see [about_Jobs](about_Jobs.md).</span></span>
- <span data-ttu-id="fa5dc-116">`PSTaskJob` または `ThreadJob` -コマンドとスクリプトは、ローカルコンピューター上の同じプロセス内の別のスレッドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-116">`PSTaskJob` or `ThreadJob` - Commands and scripts run in a separate thread within the same process on the local machine.</span></span>

<span data-ttu-id="fa5dc-117">スレッドベースのジョブは、異なるスレッドで同じプロセスで実行されるため、リモートジョブやバックグラウンドジョブほど堅牢ではありません。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-117">Thread-based jobs are not as robust as remote and background jobs, because they run in the same process on different threads.</span></span> <span data-ttu-id="fa5dc-118">あるジョブで、プロセスをクラッシュさせる重大なエラーが発生している場合は、プロセス内の他のすべてのジョブが終了します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-118">If one job has a critical error that crashes the process, then all other jobs in the process are terminated.</span></span>

<span data-ttu-id="fa5dc-119">ただし、スレッドベースのジョブではオーバーヘッドが少なくなります。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-119">However, thread-based jobs require less overhead.</span></span> <span data-ttu-id="fa5dc-120">これらは、リモート処理レイヤーまたはシリアル化を使用しません。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-120">They don't use the remoting layer or serialization.</span></span> <span data-ttu-id="fa5dc-121">結果オブジェクトは、現在のセッションのライブオブジェクトへの参照として返されます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-121">The result objects are returned as references to live objects in the current session.</span></span> <span data-ttu-id="fa5dc-122">このオーバーヘッドがないと、スレッドベースのジョブはより高速に実行され、他の種類のジョブよりも使用されるリソースが少なくなります。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-122">Without this overhead, thread-based jobs run faster and use fewer resources than the other job types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa5dc-123">ジョブを作成した親セッションもジョブの状態を監視し、パイプラインデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-123">The parent session that created the job also monitors the job status and collects pipeline data.</span></span> <span data-ttu-id="fa5dc-124">ジョブが完了状態になると、親プロセスによってジョブの子プロセスが終了します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-124">The job child process is terminated by the parent process once the job reaches a finished state.</span></span> <span data-ttu-id="fa5dc-125">親セッションが終了すると、実行中のすべての子ジョブが子プロセスと共に終了します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-125">If the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span>

<span data-ttu-id="fa5dc-126">この状況に対処するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-126">There are two ways work around this situation:</span></span>

1. <span data-ttu-id="fa5dc-127">`Invoke-Command`切断されたセッションで実行されるジョブを作成するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-127">Use `Invoke-Command` to create jobs that run in disconnected sessions.</span></span> <span data-ttu-id="fa5dc-128">詳細については、「 [about_Remote_Jobs](about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-128">For more information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
1. <span data-ttu-id="fa5dc-129">`Start-Process`ジョブではなく新しいプロセスを作成するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-129">Use `Start-Process` to create a new process rather than a job.</span></span> <span data-ttu-id="fa5dc-130">詳細については、「 [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-130">For more information, see [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span></span>

## <a name="how-to-start-and-manage-thread-based-jobs"></a><span data-ttu-id="fa5dc-131">スレッドベースのジョブを開始および管理する方法</span><span class="sxs-lookup"><span data-stu-id="fa5dc-131">How to start and manage thread-based jobs</span></span>

<span data-ttu-id="fa5dc-132">スレッドベースのジョブを開始するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-132">There are two ways to start thread-based jobs:</span></span>

- <span data-ttu-id="fa5dc-133">`Start-ThreadJob` - **Threadjob** モジュールから</span><span class="sxs-lookup"><span data-stu-id="fa5dc-133">`Start-ThreadJob` - from the **ThreadJob** module</span></span>
- <span data-ttu-id="fa5dc-134">`ForEach-Object -Parallel -AsJob` -並列機能は PowerShell 7.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-134">`ForEach-Object -Parallel -AsJob` - the parallel feature was added in PowerShell 7.0</span></span>

<span data-ttu-id="fa5dc-135">[About_Jobs](about_Jobs.md)に記載されているのと同じ **ジョブ** コマンドレットを使用して、スレッドベースのジョブを管理します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-135">Use the same **Job** cmdlets described in [about_Jobs](about_Jobs.md) to manage thread-based jobs.</span></span>

### <a name="using-start-threadjob"></a><span data-ttu-id="fa5dc-136">`Start-ThreadJob` の使用</span><span class="sxs-lookup"><span data-stu-id="fa5dc-136">Using `Start-ThreadJob`</span></span>

<span data-ttu-id="fa5dc-137">**Threadjob** モジュールは、最初に PowerShell 6 に付属しています。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-137">The **ThreadJob** module first shipped with PowerShell 6.</span></span> <span data-ttu-id="fa5dc-138">また、Windows PowerShell 5.1 の PowerShell ギャラリーからインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-138">It can also be installed from the PowerShell Gallery for Windows PowerShell 5.1.</span></span>

<span data-ttu-id="fa5dc-139">ローカルコンピューターでスレッドジョブを開始するに `Start-ThreadJob` は、コマンドレットを、中かっこ () で囲まれたコマンドまたはスクリプトと共に使用し `{ }` ます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-139">To start a thread job on the local computer, use the `Start-ThreadJob` cmdlet with a command or script enclosed in curly braces (`{ }`).</span></span>

<span data-ttu-id="fa5dc-140">次の例では、ローカルコンピューターでコマンドを実行するスレッドジョブを開始し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-140">The following example starts a thread job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process }
```

<span data-ttu-id="fa5dc-141">コマンドは、 `Start-ThreadJob` `ThreadJob` 実行中のジョブを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-141">The `Start-ThreadJob` command returns a `ThreadJob` object that represents the running job.</span></span> <span data-ttu-id="fa5dc-142">Job オブジェクトには、現在実行中の状態を含む、ジョブに関する有用な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-142">The job object contains useful information about the job including its current running status.</span></span> <span data-ttu-id="fa5dc-143">結果が生成されると、ジョブの結果が収集されます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-143">It collects the results of the job as the results are being generated.</span></span>

### <a name="using-foreach-object--parallel--asjob"></a><span data-ttu-id="fa5dc-144">`ForEach-Object -Parallel -AsJob` の使用</span><span class="sxs-lookup"><span data-stu-id="fa5dc-144">Using `ForEach-Object -Parallel -AsJob`</span></span>

<span data-ttu-id="fa5dc-145">PowerShell 7.0 によって、コマンドレットに新しいパラメーターが設定されました `ForEach-Object` 。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-145">PowerShell 7.0 added a new parameter set to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="fa5dc-146">新しいパラメーターを使用すると、スクリプトブロックを PowerShell ジョブとして並列スレッドで実行できます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-146">The new parameters allow you to run script blocks in parallel threads as PowerShell jobs.</span></span>

<span data-ttu-id="fa5dc-147">パイプを使用してデータをにパイプすることができ `ForEach-Object -Parallel` ます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-147">You can pipe data to `ForEach-Object -Parallel`.</span></span> <span data-ttu-id="fa5dc-148">データは、並列で実行されるスクリプトブロックに渡されます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-148">The data is passed to the script block that is run in parallel.</span></span> <span data-ttu-id="fa5dc-149">パラメーターは、 `-AsJob` 並列スレッドごとにジョブオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-149">The `-AsJob` parameter creates jobs objects for each of the parallel threads.</span></span>

<span data-ttu-id="fa5dc-150">次のコマンドは、コマンドにパイプを使用して、各入力値の子ジョブを含むジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-150">The following command starts a job that contains child jobs for each input value piped to the command.</span></span> <span data-ttu-id="fa5dc-151">各子ジョブは、 `Write-Output` パイプを使用した入力値を引数としてコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-151">Each child job runs the `Write-Output` command with a piped input value as the argument.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob
```

<span data-ttu-id="fa5dc-152">このコマンドは、パイプ処理された `ForEach-Object -Parallel` `PSTaskJob` 各入力値の子ジョブを含むオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-152">The `ForEach-Object -Parallel` command returns a `PSTaskJob` object that contains child jobs for each piped input value.</span></span> <span data-ttu-id="fa5dc-153">Job オブジェクトには、実行状態の子ジョブに関する有用な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-153">The job object contains useful information about the child jobs running status.</span></span> <span data-ttu-id="fa5dc-154">結果が生成されるときに子ジョブの結果を収集します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-154">It collects the results of the child jobs as the results are being generated.</span></span>

## <a name="how-to-wait-for-a-job-to-complete-and-retrieve-job-results"></a><span data-ttu-id="fa5dc-155">ジョブの完了を待機してジョブの結果を取得する方法</span><span class="sxs-lookup"><span data-stu-id="fa5dc-155">How to wait for a job to complete and retrieve job results</span></span>

<span data-ttu-id="fa5dc-156">やなどの PowerShell ジョブコマンドレットを使用して、 `Wait-Job` `Receive-Job` ジョブが完了するのを待ってから、ジョブによって生成されたすべての結果を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-156">You can use PowerShell job cmdlets, such as `Wait-Job` and `Receive-Job` to wait for a job to complete and then return all results generated by the job.</span></span>

<span data-ttu-id="fa5dc-157">次のコマンドは、コマンドを実行するスレッドジョブを開始し、 `Get-Process` コマンドが完了するまで待機します。最後に、コマンドによって生成されたすべてのデータ結果を返します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-157">The following command starts a thread job that runs a `Get-Process` command, then waits for the command to complete, and finally returns all data results generated by the command.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process } | Wait-Job | Receive-Job
```

<span data-ttu-id="fa5dc-158">次のコマンドは、パイプ処理された `Write-Output` 各入力に対してコマンドを実行し、すべての子ジョブが完了するまで待機して、最後に子ジョブによって生成されるすべてのデータ結果を返すジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-158">The following command starts a job that runs a `Write-Output` command for each piped input, then waits for all child jobs to complete, and finally returns all data results generated by the child jobs.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job
```

<span data-ttu-id="fa5dc-159">`Receive-Job`コマンドレットは、子ジョブの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-159">The `Receive-Job` cmdlet returns the results of the child jobs.</span></span>

```powershell
1
3
2
4
5
```

<span data-ttu-id="fa5dc-160">各子ジョブは並行して実行されるため、生成される結果の順序は保証されません。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-160">Because each child job runs parallel, the order of the generated results is not guaranteed.</span></span>

## <a name="thread-job-performance"></a><span data-ttu-id="fa5dc-161">スレッドジョブのパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="fa5dc-161">Thread job performance</span></span>

<span data-ttu-id="fa5dc-162">スレッドジョブは、他の種類のジョブよりも高速で軽量です。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-162">Thread jobs are faster and lighter weight than other types of jobs.</span></span> <span data-ttu-id="fa5dc-163">ただし、ジョブが行っている作業と比べると、大きなオーバーヘッドが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-163">But they still have overhead that can be large when compared to work the job is doing.</span></span>

<span data-ttu-id="fa5dc-164">PowerShell は、セッションでコマンドとスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-164">PowerShell runs commands and script in a session.</span></span> <span data-ttu-id="fa5dc-165">セッションで一度に実行できるコマンドまたはスクリプトは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-165">Only one command or script can run at a time in a session.</span></span> <span data-ttu-id="fa5dc-166">そのため、複数のジョブを実行する場合、各ジョブは個別のセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-166">So when running multiple jobs, each job runs in a separate session.</span></span> <span data-ttu-id="fa5dc-167">各セッションは、オーバーヘッドに寄与します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-167">Each session contributes to the overhead.</span></span>

<span data-ttu-id="fa5dc-168">スレッドジョブは、実行する作業がジョブの実行に使用されるセッションのオーバーヘッドよりも大きい場合に最適なパフォーマンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-168">Thread jobs provide the best performance when the work they perform is greater than the overhead of the session used to run the job.</span></span> <span data-ttu-id="fa5dc-169">この条件を満たすには、2つのケースがあります。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-169">There are two cases for that meet this criteria.</span></span>

- <span data-ttu-id="fa5dc-170">作業は多くのコンピューティング処理を必要とします。複数のスレッドジョブでスクリプトを実行すると、複数のプロセッサコアを利用し、より高速に完了できます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-170">Work is compute intensive - Running a script on multiple thread jobs can take advantage of multiple processor cores and complete faster.</span></span>

- <span data-ttu-id="fa5dc-171">作業は、i/o またはリモート呼び出しの結果を待機する時間を費やすスクリプトで構成されています。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-171">Work consists of significant waiting - A script that spends time waiting for I/O or remote call results.</span></span> <span data-ttu-id="fa5dc-172">並列実行は通常、連続して実行した場合よりも短時間で完了します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-172">Running in parallel usually completes quicker than if run sequentially.</span></span>

```powershell
(Measure-Command {
    1..1000 | ForEach { Start-ThreadJob { Write-Output "Hello $using:_" } } | Receive-Job -Wait
}).TotalMilliseconds
36860.8226

(Measure-Command {
    1..1000 | ForEach-Object { "Hello: $_" }
}).TotalMilliseconds
7.1975
```

<span data-ttu-id="fa5dc-173">上の最初の例は、単純な文字列の書き込みを行うために1000のスレッドジョブを作成する foreach ループを示しています。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-173">The first example above shows a foreach loop that creates 1000 thread jobs to do a simple string write.</span></span> <span data-ttu-id="fa5dc-174">ジョブのオーバーヘッドが原因で、完了までに36秒以上かかります。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-174">Due to job overhead, it takes over 36 seconds to complete.</span></span>

<span data-ttu-id="fa5dc-175">2番目の例では、 `ForEach` 同じ1000操作を実行するためにコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-175">The second example runs the `ForEach` cmdlet to do the same 1000 operations.</span></span>
<span data-ttu-id="fa5dc-176">この時間は、ジョブのオーバーヘッドを発生させる `ForEach-Object` ことなく、1つのスレッドで順番に実行されます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-176">This time, `ForEach-Object` runs sequentially, on a single thread, without any job overhead.</span></span> <span data-ttu-id="fa5dc-177">わずか7ミリ秒で完了します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-177">It completes in a mere 7 milliseconds.</span></span>

<span data-ttu-id="fa5dc-178">次の例では、10個の個別のシステムログについて最大5000のエントリが収集されます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-178">In the following example, up to 5000 entries are collected for 10 separate system logs.</span></span> <span data-ttu-id="fa5dc-179">このスクリプトには多数のログが含まれているため、操作を並行して実行するのが理にかなっています。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-179">Since the script involves reading a number of logs, it makes sense to do the operations in parallel.</span></span>

```powershell
$logNames.count
10

Measure-Command {
    $logs = $logNames | ForEach-Object {
        Get-WinEvent -LogName $_ -MaxEvents 5000 2>$null
    }
}

TotalMilliseconds : 252398.4321 (4 minutes 12 seconds)
$logs.Count
50000
```

<span data-ttu-id="fa5dc-180">このスクリプトは、ジョブが並列で実行される半分の時間に完了します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-180">The script completes in half the time when the jobs are run in parallel.</span></span>

```powershell
Measure-Command {
    $logs = $logNames | ForEach {
        Start-ThreadJob {
            Get-WinEvent -LogName $using:_ -MaxEvents 5000 2>$null
        } -ThrottleLimit 10
    } | Wait-Job | Receive-Job
}

TotalMilliseconds : 115994.3 (1 minute 56 seconds)
$logs.Count
50000
```

## <a name="thread-jobs-and-variables"></a><span data-ttu-id="fa5dc-181">スレッドジョブと変数</span><span class="sxs-lookup"><span data-stu-id="fa5dc-181">Thread jobs and variables</span></span>

<span data-ttu-id="fa5dc-182">スレッドベースのジョブには、複数の方法で値を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-182">There are multiple ways to pass values into the thread-based jobs.</span></span>

<span data-ttu-id="fa5dc-183">`Start-ThreadJob`は、コマンドレットにパイプ処理されるか、キーワードを使用してスクリプトブロックに渡されるか、ArgumentList パラメーターを介して渡される変数を受け入れることができ `$using` ます。 **ArgumentList**</span><span class="sxs-lookup"><span data-stu-id="fa5dc-183">`Start-ThreadJob` can accept variables that are piped to the cmdlet, passed in to the script block via the `$using` keyword, or passed in via the **ArgumentList** parameter.</span></span>

```powershell
$msg = "Hello"

$msg | Start-ThreadJob { $input | Write-Output } | Wait-Job | Receive-Job

Start-ThreadJob { Write-Output $using:msg } | Wait-Job | Receive-Job

Start-ThreadJob { param ([string] $message) Write-Output $message } -ArgumentList @($msg) |
  Wait-Job | Receive-Job
```

<span data-ttu-id="fa5dc-184">`ForEach-Object -Parallel` 変数でパイプを受け取り、キーワードを使用してスクリプトブロックに直接渡された変数を受け入れ `$using` ます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-184">`ForEach-Object -Parallel` accepts piped in variables, and variables passed directly to the script block via the `$using` keyword.</span></span>

```powershell
$msg = "Hello"

$msg | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job

1..1 | ForEach-Object -Parallel { Write-Output $using:msg } -AsJob | Wait-Job | Receive-Job
```

<span data-ttu-id="fa5dc-185">スレッドジョブは同じプロセスで実行されるため、ジョブに渡される変数参照型は慎重に扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-185">Since thread jobs run in the same process, any variable reference type passed into the job has to be treated carefully.</span></span> <span data-ttu-id="fa5dc-186">スレッドセーフなオブジェクトでない場合は、に割り当てられないようにし、メソッドとプロパティを呼び出さないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-186">If it is not a thread safe object, then it should never be assigned to, and method and properties should never be invoked on it.</span></span>

<span data-ttu-id="fa5dc-187">次の例では、スレッドセーフな .NET `ConcurrentDictionary` オブジェクトをすべての子ジョブに渡して、一意の名前付きプロセスオブジェクトを収集します。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-187">The following example passes a thread-safe .NET `ConcurrentDictionary` object to all child jobs to collect uniquely named process objects.</span></span> <span data-ttu-id="fa5dc-188">スレッドセーフなオブジェクトであるため、ジョブがプロセス内で同時に実行されている間に安全に使用できます。</span><span class="sxs-lookup"><span data-stu-id="fa5dc-188">Since it is a thread safe object, it can be safely used while the jobs run concurrently in the process.</span></span>

```powershell
$threadSafeDictionary = [System.Collections.Concurrent.ConcurrentDictionary[string,object]]::new()
$jobs = Get-Process | ForEach {
    Start-ThreadJob {
        $proc = $using:_
        $dict = $using:threadSafeDictionary
        $dict.TryAdd($proc.ProcessName, $proc)
    }
}
$jobs | Wait-Job | Receive-Job

$threadSafeDictionary.Count
96

$threadSafeDictionary["pwsh"]

NPM(K)  PM(M)   WS(M) CPU(s)    Id SI ProcessName
------  -----   ----- ------    -- -- -----------
  112  108.25  124.43  69.75 16272  1 pwsh
```

## <a name="see-also"></a><span data-ttu-id="fa5dc-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa5dc-189">See also</span></span>

- [<span data-ttu-id="fa5dc-190">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="fa5dc-190">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="fa5dc-191">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="fa5dc-191">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="fa5dc-192">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="fa5dc-192">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="fa5dc-193">about_Remote</span><span class="sxs-lookup"><span data-stu-id="fa5dc-193">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="fa5dc-194">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="fa5dc-194">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="fa5dc-195">Start-Job</span><span class="sxs-lookup"><span data-stu-id="fa5dc-195">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="fa5dc-196">Get-Job</span><span class="sxs-lookup"><span data-stu-id="fa5dc-196">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="fa5dc-197">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="fa5dc-197">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="fa5dc-198">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="fa5dc-198">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="fa5dc-199">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="fa5dc-199">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="fa5dc-200">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="fa5dc-200">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
