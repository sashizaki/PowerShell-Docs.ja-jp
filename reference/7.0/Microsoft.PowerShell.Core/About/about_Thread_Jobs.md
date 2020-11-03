---
description: PowerShell スレッドベースのジョブに関する情報を提供します。 スレッドジョブは、現在のセッションプロセス内の別のスレッドでコマンドまたは式を実行するバックグラウンドジョブの一種です。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 10/16/2020
online version: 1.0.0
schema: 2.0.0
title: about_Thread_Jobs
ms.openlocfilehash: 973d0ddf18b63cd7462817cf68f7c5d7466f4724
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "93224643"
---
# <a name="about-thread-jobs"></a><span data-ttu-id="bc1ec-105">スレッドジョブについて</span><span class="sxs-lookup"><span data-stu-id="bc1ec-105">About Thread Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="bc1ec-106">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="bc1ec-106">Short description</span></span>

<span data-ttu-id="bc1ec-107">PowerShell スレッドベースのジョブに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-107">Provides information about PowerShell thread-based jobs.</span></span> <span data-ttu-id="bc1ec-108">スレッドジョブは、現在のセッションプロセス内の別のスレッドでコマンドまたは式を実行するバックグラウンドジョブの一種です。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-108">A thread job is a type of background job that runs a command or expression in a separate thread within the current session process.</span></span>

## <a name="long-description"></a><span data-ttu-id="bc1ec-109">長い説明</span><span class="sxs-lookup"><span data-stu-id="bc1ec-109">Long description</span></span>

<span data-ttu-id="bc1ec-110">この記事では、ローカルコンピューター上の PowerShell でスレッドジョブを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-110">This article explains how to run thread jobs in PowerShell on a local computer.</span></span>
<span data-ttu-id="bc1ec-111">ローカルコンピューターでのバックグラウンドジョブの実行の詳細については、「 [about_Jobs](about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-111">For information about running background jobs on a local computer, see [about_Jobs](about_Jobs.md).</span></span>

<span data-ttu-id="bc1ec-112">コマンドレットを使用して、スレッドジョブを開始し `Start-ThreadJob` ます。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-112">Start a thread job by using the `Start-ThreadJob` cmdlet.</span></span> <span data-ttu-id="bc1ec-113">このコマンドレットは、PowerShell に付属している **Threadjob** モジュールで使用できます。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-113">This cmdlet is available in the **ThreadJob** module that ships with PowerShell.</span></span>
<span data-ttu-id="bc1ec-114">`Start-ThreadJob` 実行中のコマンドまたはスクリプトをカプセル化し、コマンドレットを操作するすべての PowerShell ジョブで使用できる単一のジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-114">`Start-ThreadJob` returns a single job object that encapsulates the running command or script, and can be used with all PowerShell job manipulating cmdlets.</span></span>

## <a name="the-job-cmdlets"></a><span data-ttu-id="bc1ec-115">ジョブのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="bc1ec-115">The job cmdlets</span></span>

|<span data-ttu-id="bc1ec-116">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="bc1ec-116">Cmdlet</span></span>           |<span data-ttu-id="bc1ec-117">説明</span><span class="sxs-lookup"><span data-stu-id="bc1ec-117">Description</span></span>                                            |
|-----------------|-------------------------------------------------------|
|`Start-ThreadJob`|<span data-ttu-id="bc1ec-118">ローカルコンピューター上でスレッドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-118">Starts a thread job on a local computer.</span></span>               |
|`Get-Job`        |<span data-ttu-id="bc1ec-119">現在のセッションで開始されたジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-119">Gets the jobs that were started in the current session.</span></span>|
|`Receive-Job`    |<span data-ttu-id="bc1ec-120">ジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-120">Gets the results of jobs.</span></span>                              |
|`Stop-Job`       |<span data-ttu-id="bc1ec-121">実行中のジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-121">Stops a running job.</span></span>                                   |
|`Wait-Job`       |<span data-ttu-id="bc1ec-122">1つまたはすべてのジョブが完了するまで、コマンドプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-122">Suppresses the command prompt until one or all jobs are</span></span>|
|                 |<span data-ttu-id="bc1ec-123">完了.</span><span class="sxs-lookup"><span data-stu-id="bc1ec-123">complete.</span></span>                                              |
|`Remove-Job`     |<span data-ttu-id="bc1ec-124">ジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-124">Deletes a job.</span></span>                                         |

## <a name="how-to-start-a-thread-job-on-the-local-computer"></a><span data-ttu-id="bc1ec-125">ローカルコンピューターでスレッドジョブを開始する方法</span><span class="sxs-lookup"><span data-stu-id="bc1ec-125">How to start a thread job on the local computer</span></span>

<span data-ttu-id="bc1ec-126">ローカルコンピューターでスレッドジョブを開始するには、コマンドレットを使用し `Start-ThreadJob` ます。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-126">To start a thread job on the local computer, use the `Start-ThreadJob` cmdlet.</span></span>

<span data-ttu-id="bc1ec-127">コマンドを記述するに `Start-ThreadJob` は、コマンドを囲むか、ジョブの実行を中かっこ () で囲み `{ }` ます。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-127">To write a `Start-ThreadJob` command, enclose the command or script the job runs in curly braces (`{ }`).</span></span>

<span data-ttu-id="bc1ec-128">次のコマンドは、 `Get-Process` ローカルコンピューター上でコマンドを実行するスレッドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-128">The following command starts a thread job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process }
```

<span data-ttu-id="bc1ec-129">コマンドは、 `Start-ThreadJob` `ThreadJob` 実行中のジョブを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-129">The `Start-ThreadJob` command returns a `ThreadJob` object that represents the running job.</span></span> <span data-ttu-id="bc1ec-130">Job オブジェクトには、現在実行中の状態を含む、ジョブに関する有用な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-130">The job object contains useful information about the job including its current running status.</span></span> <span data-ttu-id="bc1ec-131">結果が生成されると、ジョブの結果が収集されます。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-131">It collects the results of the job as the results are being generated.</span></span>

<span data-ttu-id="bc1ec-132">コマンドを記述するには `ForEach-Object -Parallel` 、パイプでデータをコマンドに渡し、コマンドまたはスクリプトを囲みます。ジョブは中かっこ () で実行し `{}` ます。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-132">To write a `ForEach-Object -Parallel` command, pipe data to the command and enclose the command or script the job runs in curly braces(`{}`).</span></span> <span data-ttu-id="bc1ec-133">パラメータースイッチを使用し `-AsJob` て、ジョブオブジェクトが返されるようにします。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-133">Use the `-AsJob` parameter switch so that a job object is returned.</span></span>

<span data-ttu-id="bc1ec-134">次のコマンドは、コマンドにパイプを使用して、各入力値の子ジョブを含むジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-134">The following command starts a job that contains child jobs for each input value piped to the command.</span></span> <span data-ttu-id="bc1ec-135">各子ジョブは、 `Write-Output` パイプを使用した入力値を引数としてコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-135">Each child job runs the `Write-Output` command with a piped input value as the argument.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob
```

<span data-ttu-id="bc1ec-136">このコマンドは、パイプ処理された `ForEach-Object -Parallel` `PSTaskJob` 各入力値の子ジョブを含むオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-136">The `ForEach-Object -Parallel` command returns a `PSTaskJob` object that contains child jobs for each piped input value.</span></span> <span data-ttu-id="bc1ec-137">Job オブジェクトには、実行状態の子ジョブに関する有用な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-137">The job object contains useful information about the child jobs running status.</span></span> <span data-ttu-id="bc1ec-138">結果が生成されるときに子ジョブの結果を収集します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-138">It collects the results of the child jobs as the results are being generated.</span></span>

## <a name="how-to-wait-for-a-job-to-complete-and-retrieve-job-results"></a><span data-ttu-id="bc1ec-139">ジョブの完了を待機してジョブの結果を取得する方法</span><span class="sxs-lookup"><span data-stu-id="bc1ec-139">How to wait for a job to complete and retrieve job results</span></span>

<span data-ttu-id="bc1ec-140">やなどの PowerShell ジョブコマンドレットを使用して、 `Wait-Job` `Receive-Job` ジョブが完了するのを待ってから、ジョブによって生成されたすべての結果を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-140">You can use PowerShell job cmdlets, such as `Wait-Job` and `Receive-Job` to wait for a job to complete and then return all results generated by the job.</span></span>

<span data-ttu-id="bc1ec-141">次のコマンドは、コマンドを実行するスレッドジョブを開始し、 `Get-Process` コマンドが完了するまで待機します。最後に、コマンドによって生成されたすべてのデータ結果を返します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-141">The following command starts a thread job that runs a `Get-Process` command, then waits for the command to complete, and finally returns all data results generated by the command.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process } | Wait-Job | Receive-Job
```

<span data-ttu-id="bc1ec-142">次のコマンドは、パイプ処理された `Write-Output` 各入力に対してコマンドを実行し、すべての子ジョブが完了するまで待機して、最後に子ジョブによって生成されるすべてのデータ結果を返すジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-142">The following command starts a job that runs a `Write-Output` command for each piped input, then waits for all child jobs to complete, and finally returns all data results generated by the child jobs.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job
```

<span data-ttu-id="bc1ec-143">`Receive-Job`コマンドレットは、子ジョブの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-143">The `Receive-Job` cmdlet returns the results of the child jobs.</span></span>

```powershell
1
3
2
4
5
```

<span data-ttu-id="bc1ec-144">各子ジョブは並行して実行されるため、生成される結果の順序は保証されません。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-144">Because each child job runs parallel, the order of the generated results is not guaranteed.</span></span>

## <a name="powershell-concurrency-and-jobs"></a><span data-ttu-id="bc1ec-145">PowerShell の同時実行とジョブ</span><span class="sxs-lookup"><span data-stu-id="bc1ec-145">PowerShell concurrency and jobs</span></span>

<span data-ttu-id="bc1ec-146">PowerShell では、コマンドを同時に実行してジョブをスクリプト化します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-146">PowerShell concurrently runs commands and script through jobs.</span></span> <span data-ttu-id="bc1ec-147">同時実行をサポートするために PowerShell によって提供される3つのジョブベースのソリューションがあります。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-147">There are three jobs-based solutions provided by PowerShell to support concurrency.</span></span>

|<span data-ttu-id="bc1ec-148">ジョブ</span><span class="sxs-lookup"><span data-stu-id="bc1ec-148">Job</span></span>            |<span data-ttu-id="bc1ec-149">説明</span><span class="sxs-lookup"><span data-stu-id="bc1ec-149">Description</span></span>                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |<span data-ttu-id="bc1ec-150">コマンドとスクリプトをリモートコンピューターで実行します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-150">Command and script run on a remote computer.</span></span>                 |
|`BackgroundJob`|<span data-ttu-id="bc1ec-151">コマンドとスクリプトがローカルの別のプロセスで実行される</span><span class="sxs-lookup"><span data-stu-id="bc1ec-151">Command and script run in a separate process on the local</span></span>    |
|               |<span data-ttu-id="bc1ec-152">割り当てます。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-152">machine.</span></span>                                                     |
|`ThreadJob`    |<span data-ttu-id="bc1ec-153">コマンドとスクリプトが同じ内の別のスレッドで実行される</span><span class="sxs-lookup"><span data-stu-id="bc1ec-153">Command and script run in a separate thread within the same</span></span>  |
|               |<span data-ttu-id="bc1ec-154">ローカルコンピューターでプロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-154">process on the local machine.</span></span>                                |

<span data-ttu-id="bc1ec-155">各種類のジョブには、利点と欠点があります。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-155">Each type of job has benefits and drawbacks.</span></span> <span data-ttu-id="bc1ec-156">別のコンピューターまたは別のプロセスでスクリプトをリモートで実行すると、優れた分離ができます。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-156">Running script remotely on a separate machine or in a separate process has great isolation.</span></span> <span data-ttu-id="bc1ec-157">エラーが発生しても、他の実行中のジョブや、ジョブを開始したクライアントには影響しません。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-157">Any errors won't affect other running jobs or the client that started the job.</span></span> <span data-ttu-id="bc1ec-158">ただし、リモート処理層では、オブジェクトのシリアル化などのオーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-158">But the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="bc1ec-159">リモートセッションとの間でやり取りされるすべてのオブジェクトをシリアル化してから、クライアントとターゲットセッション間でやり取りするときに逆シリアル化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-159">All objects passed to and from the remote session must be serialized and then deserialized as it passes between the client and the target session.</span></span> <span data-ttu-id="bc1ec-160">シリアル化操作では、大規模な複雑なデータオブジェクトに対して多くのコンピューティングリソースとメモリリソースを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-160">The serialization operation can use many compute and memory resources for large complex data objects.</span></span>

## <a name="powershell-thread-based-jobs"></a><span data-ttu-id="bc1ec-161">PowerShell スレッドベースのジョブ</span><span class="sxs-lookup"><span data-stu-id="bc1ec-161">PowerShell thread based jobs</span></span>

<span data-ttu-id="bc1ec-162">スレッドベースのジョブは、異なるスレッドで同じプロセスで実行されるため、リモートジョブやバックグラウンドジョブほど堅牢ではありません。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-162">Thread based jobs are not as robust as Remote and Background jobs, because they run in the same process on different threads.</span></span> <span data-ttu-id="bc1ec-163">あるジョブで、プロセスをクラッシュさせる重大なエラーが発生している場合は、プロセス内の他のすべてのジョブも失敗します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-163">If one job has a critical error that crashes the process, then all other jobs in the process will also fail.</span></span>

<span data-ttu-id="bc1ec-164">ただし、スレッドベースのジョブのオーバーヘッドはかなり少なくなります。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-164">However, thread-based jobs have much less overhead.</span></span> <span data-ttu-id="bc1ec-165">リモート処理レイヤーまたはシリアル化を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-165">They don't need to use the remoting layer or serialization.</span></span> <span data-ttu-id="bc1ec-166">その結果、スレッドベースのジョブの実行速度が大幅に向上し、他の種類のジョブよりもはるかに少ないリソースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-166">The result is that thread-based jobs tend to run much faster and use far less resources than the other job types.</span></span>

## <a name="thread-job-performance"></a><span data-ttu-id="bc1ec-167">スレッドジョブのパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="bc1ec-167">Thread job performance</span></span>

<span data-ttu-id="bc1ec-168">スレッドジョブは、他の種類のジョブよりも高速で軽量です。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-168">Thread jobs are faster and lighter weight than other types of jobs.</span></span> <span data-ttu-id="bc1ec-169">ただし、ジョブが行っている作業と比べると、大きなオーバーヘッドが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-169">But they still have overhead that can be large when compared to work the job is doing.</span></span>

<span data-ttu-id="bc1ec-170">PowerShell は、セッションでコマンドとスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-170">PowerShell runs commands and script in a session.</span></span> <span data-ttu-id="bc1ec-171">セッションで一度に実行できるコマンドまたはスクリプトは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-171">Only one command or script can run at a time in a session.</span></span> <span data-ttu-id="bc1ec-172">そのため、複数のジョブを実行する場合、各ジョブは個別のセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-172">So when running multiple jobs, each job runs in a separate session.</span></span> <span data-ttu-id="bc1ec-173">各セッションは、オーバーヘッドに寄与します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-173">Each session contributes to the overhead.</span></span>

<span data-ttu-id="bc1ec-174">スレッドジョブは、実行する作業がジョブの実行に使用されるセッションのオーバーヘッドよりも大きい場合に最適なパフォーマンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-174">Thread jobs provide the best performance when the work they perform is greater than the overhead of the session used to run the job.</span></span> <span data-ttu-id="bc1ec-175">この条件を満たすには、2つのケースがあります。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-175">There are two cases for that meet this criteria.</span></span>

- <span data-ttu-id="bc1ec-176">作業は多くのコンピューティング処理を必要とします。複数のスレッドジョブでスクリプトを実行すると、複数のプロセッサコアを利用し、より高速に完了できます。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-176">Work is compute intensive - Running a script on multiple thread jobs can take advantage of multiple processor cores and complete faster.</span></span>

- <span data-ttu-id="bc1ec-177">作業は、i/o またはリモート呼び出しの結果を待機する時間を費やすスクリプトで構成されています。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-177">Work consists of significant waiting - A script that spends time waiting for I/O or remote call results.</span></span> <span data-ttu-id="bc1ec-178">並列実行は通常、連続して実行した場合よりも短時間で完了します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-178">Running in parallel usually completes quicker than if run sequentially.</span></span>

```powershell
(Measure-Command {
    1..1000 | ForEach { Start-ThreadJob { Write-Output "Hello $using:_" } } | Receive-Job -Wait
}).TotalMilliseconds
10457.962


(Measure-Command {
    1..1000 | ForEach-Object { "Hello: $_" }
}).TotalMilliseconds
24.9277
```

<span data-ttu-id="bc1ec-179">上の最初の例は、単純な文字列の書き込みを行うために1000のスレッドジョブを作成する foreach ループを示しています。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-179">The first example above shows a foreach loop that creates 1000 thread jobs to do a simple string write.</span></span> <span data-ttu-id="bc1ec-180">ジョブのオーバーヘッドが原因で、完了までに33秒以上かかります。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-180">Due to job overhead, it takes over 33 seconds to complete.</span></span>

<span data-ttu-id="bc1ec-181">2番目の例では、 `ForEach` コマンドレットを実行して同じ1000操作を実行します。また、各文字列の書き込みは、ジョブのオーバーヘッドなしで順番に実行されます。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-181">The second example runs the `ForEach` cmdlet to do the same 1000 operations and each string write is executed sequentially without any job overhead.</span></span> <span data-ttu-id="bc1ec-182">わずか25ミリ秒で完了します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-182">It completes in a mere 25 milliseconds.</span></span>

```powershell
$logNames.count
10

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

<span data-ttu-id="bc1ec-183">上の例では、10個の個別のシステムログに対して最大5000のエントリが収集されます。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-183">In the above example, up to 5000 entries are collected for 10 separate system logs.</span></span> <span data-ttu-id="bc1ec-184">このスクリプトには多数のログが含まれているため、操作を並行して実行するのが理にかなっています。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-184">Since the script involves reading a number of logs, it makes sense to do the operations in parallel.</span></span> <span data-ttu-id="bc1ec-185">また、ジョブは、スクリプトが順番に実行されるのと同じ速さで完了します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-185">And the job completes over twice as fast as when the script is run sequentially.</span></span>

```powershell
Measure-Command {
    $logs = $logNames | ForEach-Object {
        Get-WinEvent -LogName $_ -MaxEvents 5000 2>$null
    }
}

TotalMilliseconds : 252398.4321 (4 minutes 12 seconds)
$logs.Count
50000
```

## <a name="thread-jobs-and-variables"></a><span data-ttu-id="bc1ec-186">スレッドジョブと変数</span><span class="sxs-lookup"><span data-stu-id="bc1ec-186">Thread jobs and variables</span></span>

<span data-ttu-id="bc1ec-187">変数は、さまざまな方法でスレッドジョブに渡されます。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-187">Variables are passed into thread jobs in various ways.</span></span>

<span data-ttu-id="bc1ec-188">`Start-ThreadJob`は、コマンドレットにパイプ処理されるか、キーワードを使用してスクリプトブロックに渡されるか、ArgumentList パラメーターを介して渡される変数を受け入れることができ `$using` ます。 **ArgumentList**</span><span class="sxs-lookup"><span data-stu-id="bc1ec-188">`Start-ThreadJob` can accept variables that are piped to the cmdlet, passed in to the script block via the `$using` keyword, or passed in via the **ArgumentList** parameter.</span></span>

```powershell
$msg = "Hello"

$msg | Start-ThreadJob { $input | Write-Output } | Wait-Job | Receive-Job

Start-ThreadJob { Write-Output $using:msg } | Wait-Job | Receive-Job

Start-ThreadJob { param ([string] $message) Write-Output $message } -ArgumentList @($msg) |
  Wait-Job | Receive-Job

`ForEach-Object -Parallel` accepts piped in variables, and variables passed
directly to the script block via the `$using` keyword.

```powershell
$msg = "Hello"

$msg | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job

1..1 | ForEach-Object -Parallel { Write-Output $using:msg } -AsJob | Wait-Job | Receive-Job
```

<span data-ttu-id="bc1ec-189">スレッドジョブは同じプロセスで実行されるため、ジョブに渡される変数参照型は慎重に扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-189">Since thread jobs run in the same process, any variable reference type passed into the job has to be treated carefully.</span></span> <span data-ttu-id="bc1ec-190">スレッドセーフなオブジェクトでない場合は、に割り当てられないようにし、メソッドとプロパティを呼び出さないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-190">If it is not a thread safe object, then it should never be assigned to, and method and properties should never be invoked on it.</span></span>

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

<span data-ttu-id="bc1ec-191">上の例では、スレッドセーフな dotNet `ConcurrentDictionary` オブジェクトをすべての子ジョブに渡して、一意の名前を付けた process オブジェクトを収集します。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-191">The above example passes a thread safe dotNet `ConcurrentDictionary` object to all child jobs to collect uniquely named process objects.</span></span> <span data-ttu-id="bc1ec-192">スレッドセーフなオブジェクトであるため、ジョブがプロセス内で同時に実行されている間に安全に使用できます。</span><span class="sxs-lookup"><span data-stu-id="bc1ec-192">Since it is a thread safe object, it can be safely used while the jobs run concurrently in the process.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc1ec-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc1ec-193">See also</span></span>

- [<span data-ttu-id="bc1ec-194">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="bc1ec-194">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="bc1ec-195">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="bc1ec-195">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="bc1ec-196">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="bc1ec-196">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="bc1ec-197">about_Remote</span><span class="sxs-lookup"><span data-stu-id="bc1ec-197">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="bc1ec-198">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="bc1ec-198">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="bc1ec-199">Start-Job</span><span class="sxs-lookup"><span data-stu-id="bc1ec-199">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="bc1ec-200">Get-Job</span><span class="sxs-lookup"><span data-stu-id="bc1ec-200">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="bc1ec-201">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="bc1ec-201">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="bc1ec-202">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="bc1ec-202">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="bc1ec-203">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="bc1ec-203">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="bc1ec-204">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="bc1ec-204">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
