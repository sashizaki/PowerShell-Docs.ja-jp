---
description: PowerShell バックグラウンドジョブが、現在のセッションと対話せずにバックグラウンドでコマンドまたは式を実行する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 10/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_jobs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Jobs
ms.openlocfilehash: a2fba9024f9b365c79ea5d59d6840a72ba1f8b21
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "93224568"
---
# <a name="about-jobs"></a><span data-ttu-id="f40f8-104">ジョブについて</span><span class="sxs-lookup"><span data-stu-id="f40f8-104">About Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="f40f8-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="f40f8-105">Short description</span></span>
<span data-ttu-id="f40f8-106">PowerShell バックグラウンドジョブが、現在のセッションと対話せずにバックグラウンドでコマンドまたは式を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-106">Provides information about how PowerShell background jobs run a command or expression in the background without interacting with the current session.</span></span>

## <a name="long-description"></a><span data-ttu-id="f40f8-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="f40f8-107">Long description</span></span>

<span data-ttu-id="f40f8-108">PowerShell では、コマンドを同時に実行してジョブをスクリプト化します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-108">PowerShell concurrently runs commands and script through jobs.</span></span> <span data-ttu-id="f40f8-109">同時実行をサポートするために PowerShell によって提供される3つのジョブベースのソリューションがあります。</span><span class="sxs-lookup"><span data-stu-id="f40f8-109">There are three jobs-based solutions provided by PowerShell to support concurrency.</span></span>

|<span data-ttu-id="f40f8-110">ジョブ</span><span class="sxs-lookup"><span data-stu-id="f40f8-110">Job</span></span>            |<span data-ttu-id="f40f8-111">説明</span><span class="sxs-lookup"><span data-stu-id="f40f8-111">Description</span></span>                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |<span data-ttu-id="f40f8-112">コマンドとスクリプトをリモートコンピューターで実行します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-112">Command and script run on a remote computer.</span></span>                 |
|`BackgroundJob`|<span data-ttu-id="f40f8-113">コマンドとスクリプトがローカルの別のプロセスで実行される</span><span class="sxs-lookup"><span data-stu-id="f40f8-113">Command and script run in a separate process on the local</span></span>    |
|               |<span data-ttu-id="f40f8-114">割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-114">machine.</span></span>                                                     |
|`ThreadJob`    |<span data-ttu-id="f40f8-115">コマンドとスクリプトが同じ内の別のスレッドで実行される</span><span class="sxs-lookup"><span data-stu-id="f40f8-115">Command and script run in a separate thread within the same</span></span>  |
|               |<span data-ttu-id="f40f8-116">ローカルコンピューターでプロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-116">process on the local machine.</span></span>                                |

<span data-ttu-id="f40f8-117">各種類のジョブには、利点と欠点があります。</span><span class="sxs-lookup"><span data-stu-id="f40f8-117">Each type of job has benefits and drawbacks.</span></span> <span data-ttu-id="f40f8-118">別のコンピューターまたは別のプロセスでスクリプトをリモートで実行すると、優れた分離ができます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-118">Running script remotely on a separate machine or in a separate process has great isolation.</span></span> <span data-ttu-id="f40f8-119">エラーが発生しても、他の実行中のジョブや、ジョブを開始したクライアントには影響しません。</span><span class="sxs-lookup"><span data-stu-id="f40f8-119">Any errors won't affect other running jobs or the client that started the job.</span></span> <span data-ttu-id="f40f8-120">ただし、リモート処理層では、オブジェクトのシリアル化などのオーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-120">But the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="f40f8-121">リモートセッションとの間でやり取りされるすべてのオブジェクトをシリアル化してから、クライアントとターゲットセッション間でやり取りするときに逆シリアル化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f40f8-121">All objects passed to and from the remote session must be serialized and then deserialized as it passes between the client and the target session.</span></span> <span data-ttu-id="f40f8-122">シリアル化操作では、大規模な複雑なデータオブジェクトに対して多くのコンピューティングリソースとメモリリソースを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-122">The serialization operation can use many compute and memory resources for large complex data objects.</span></span>

<span data-ttu-id="f40f8-123">このトピックでは、ローカルコンピューター上の PowerShell でバックグラウンドジョブを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-123">This topic explains how to run background jobs in PowerShell on a local computer.</span></span> <span data-ttu-id="f40f8-124">リモートコンピューターでバックグラウンドジョブを実行する方法の詳細については、「 [about_Remote_Jobs](about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f40f8-124">For information about running background jobs on remote computers, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span> <span data-ttu-id="f40f8-125">スレッドジョブの詳細については、「 [about_Thread_Jobs](/powershell/module/microsoft.powershell.core/about/about_Thread_Jobs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f40f8-125">For more information about thread jobs, see [about_Thread_Jobs](/powershell/module/microsoft.powershell.core/about/about_Thread_Jobs).</span></span>

<span data-ttu-id="f40f8-126">バックグラウンドジョブを開始すると、ジョブが完了するまでに時間がかかる場合でも、コマンドプロンプトがすぐに返されます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-126">When you start a background job, the command prompt returns immediately, even if the job takes an extended time to complete.</span></span> <span data-ttu-id="f40f8-127">ジョブの実行中は、中断されることなく引き続きセッションで作業できます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-127">You can continue to work in the session without interruption while the job runs.</span></span>

## <a name="the-job-cmdlets"></a><span data-ttu-id="f40f8-128">ジョブのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="f40f8-128">The job cmdlets</span></span>

|<span data-ttu-id="f40f8-129">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f40f8-129">Cmdlet</span></span>          |<span data-ttu-id="f40f8-130">説明</span><span class="sxs-lookup"><span data-stu-id="f40f8-130">Description</span></span>                                            |
|----------------|-------------------------------------------------------|
|`Start-Job`     |<span data-ttu-id="f40f8-131">ローカルコンピューターでバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-131">Starts a background job on a local computer.</span></span>           |
|`Get-Job`       |<span data-ttu-id="f40f8-132">で開始されたバックグラウンドジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-132">Gets the background jobs that were started in the</span></span>      |
|                |<span data-ttu-id="f40f8-133">現在のセッション。</span><span class="sxs-lookup"><span data-stu-id="f40f8-133">current session.</span></span>                                       |
|`Receive-Job`   |<span data-ttu-id="f40f8-134">バックグラウンドジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-134">Gets the results of background jobs.</span></span>                   |
|`Stop-Job`      |<span data-ttu-id="f40f8-135">バックグラウンドジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-135">Stops a background job.</span></span>                                |
|`Wait-Job`      |<span data-ttu-id="f40f8-136">1つまたはすべてのジョブが完了するまで、コマンドプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="f40f8-136">Suppresses the command prompt until one or all jobs are</span></span>|
|                |<span data-ttu-id="f40f8-137">完了.</span><span class="sxs-lookup"><span data-stu-id="f40f8-137">complete.</span></span>                                              |
|`Remove-Job`    |<span data-ttu-id="f40f8-138">バックグラウンドジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-138">Deletes a background job.</span></span>                              |
|`Invoke-Command`|<span data-ttu-id="f40f8-139">**AsJob** パラメーターは、に対してバックグラウンドジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-139">The **AsJob** parameter creates a background job on a</span></span>  |
|                |<span data-ttu-id="f40f8-140">リモートコンピューター。</span><span class="sxs-lookup"><span data-stu-id="f40f8-140">remote computer.</span></span> <span data-ttu-id="f40f8-141">を使用して、 `Invoke-Command`</span><span class="sxs-lookup"><span data-stu-id="f40f8-141">You can use `Invoke-Command` to run</span></span>   |
|                |<span data-ttu-id="f40f8-142">を含め、任意のジョブコマンドをリモートで実行 `Start-Job` します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-142">any job command remotely, including `Start-Job`.</span></span>       |

## <a name="how-to-start-a-job-on-the-local-computer"></a><span data-ttu-id="f40f8-143">ローカルコンピューターでジョブを開始する方法</span><span class="sxs-lookup"><span data-stu-id="f40f8-143">How to start a job on the local computer</span></span>

<span data-ttu-id="f40f8-144">ローカルコンピューターでバックグラウンドジョブを開始するには、コマンドレットを使用し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-144">To start a background job on the local computer, use the `Start-Job` cmdlet.</span></span>

<span data-ttu-id="f40f8-145">コマンドを記述するには、 `Start-Job` ジョブを実行するコマンドを中かっこ ( `{}` ) で囲みます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-145">To write a `Start-Job` command, enclose the command that the job runs in curly braces (`{}`).</span></span> <span data-ttu-id="f40f8-146">**ScriptBlock** パラメーターを使用して、コマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-146">Use the **ScriptBlock** parameter to specify the command.</span></span>

<span data-ttu-id="f40f8-147">次のコマンドは、ローカルコンピューターでコマンドを実行するバックグラウンドジョブを開始し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-147">The following command starts a background job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="f40f8-148">この `Start-Job` コマンドは、ジョブを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-148">The `Start-Job` command returns an object that represents the job.</span></span> <span data-ttu-id="f40f8-149">ジョブ オブジェクトには、ジョブに関する有用な情報が含まれていますが、ジョブの結果は含まれません。</span><span class="sxs-lookup"><span data-stu-id="f40f8-149">The job object contains useful information about the job, but it does not contain the job results.</span></span>

<span data-ttu-id="f40f8-150">ジョブオブジェクトを変数に保存し、他のジョブコマンドレットと共に使用してバックグラウンドジョブを管理します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-150">Save the job object in a variable, and then use it with the other Job cmdlets to manage the background job.</span></span> <span data-ttu-id="f40f8-151">次のコマンドは、ジョブオブジェクトを開始し、結果として生成されたジョブオブジェクトを変数に保存し `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-151">The following command starts a job object and saves the resulting job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="f40f8-152">また、コマンドレットを使用して、 `Get-Job` 現在のセッションで開始されたジョブを表すオブジェクトを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-152">You can also use the `Get-Job` cmdlet to get objects that represent the jobs started in the current session.</span></span> <span data-ttu-id="f40f8-153">`Get-Job` を返す同じジョブオブジェクトを返し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-153">`Get-Job` returns the same job object that `Start-Job` returns.</span></span>

## <a name="getting-job-objects"></a><span data-ttu-id="f40f8-154">ジョブオブジェクトの取得</span><span class="sxs-lookup"><span data-stu-id="f40f8-154">Getting job objects</span></span>

<span data-ttu-id="f40f8-155">現在のセッションで開始されたバックグラウンドジョブを表すオブジェクトを取得するには、コマンドレットを使用し `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-155">To get object that represent the background jobs that were started in the current session, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="f40f8-156">パラメーターを指定しない場合は、 `Get-Job` 現在のセッションで開始されたすべてのジョブが返されます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-156">Without parameters, `Get-Job` returns all of the jobs that were started in the current session.</span></span>

<span data-ttu-id="f40f8-157">たとえば、次のコマンドは、現在のセッションのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-157">For example, the following command gets the jobs in the current session.</span></span>

```powershell
PS C:> Get-Job

Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Running    True         localhost  Get-Process
```

<span data-ttu-id="f40f8-158">また、ジョブオブジェクトを変数に保存し、後のコマンドでジョブを表すために使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-158">You can also save the job object in a variable and use it to represent the job in a later command.</span></span> <span data-ttu-id="f40f8-159">次のコマンドは、ID が1のジョブを取得し、変数に保存し `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-159">The following command gets the job with ID 1 and saves it in the `$job` variable.</span></span>

```powershell
$job = Get-Job -Id 1
```

<span data-ttu-id="f40f8-160">ジョブオブジェクトには、ジョブが完了したかどうかを示すジョブの状態が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f40f8-160">The job object contains the state of the job, which indicates whether the job has finished.</span></span> <span data-ttu-id="f40f8-161">完了したジョブの状態が " **完了** " または " **失敗** " になっています。</span><span class="sxs-lookup"><span data-stu-id="f40f8-161">A finished job has a state of **Complete** or **Failed**.</span></span> <span data-ttu-id="f40f8-162">ジョブも **ブロック** されているか、実行され **ている** 可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f40f8-162">A job might also be **blocked** or **running**.</span></span>

```powershell
Get-Job

Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Complete   True         localhost  Get-Process
```

## <a name="getting-the-results-of-a-job"></a><span data-ttu-id="f40f8-163">ジョブの結果を取得する</span><span class="sxs-lookup"><span data-stu-id="f40f8-163">Getting the results of a job</span></span>

<span data-ttu-id="f40f8-164">バックグラウンドジョブを実行しても、結果はすぐには表示されません。</span><span class="sxs-lookup"><span data-stu-id="f40f8-164">When you run a background job, the results do not appear immediately.</span></span> <span data-ttu-id="f40f8-165">代わりに、 `Start-Job` コマンドレットはジョブを表すジョブオブジェクトを返しますが、結果は含まれません。</span><span class="sxs-lookup"><span data-stu-id="f40f8-165">Instead, the `Start-Job` cmdlet returns a job object that represents the job, but it does not contain the results.</span></span> <span data-ttu-id="f40f8-166">バックグラウンドジョブの結果を取得するには、コマンドレットを使用し `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-166">To get the results of a background job, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="f40f8-167">次のコマンドでは、 `Receive-Job` コマンドレットを使用してジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-167">The following command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="f40f8-168">変数に保存されているジョブオブジェクトを使用して `$job` 、ジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-168">It uses a job object saved in the `$job` variable to identify the job.</span></span>

```powershell
Receive-Job -Job $job
```

<span data-ttu-id="f40f8-169">`Receive-Job`コマンドレットは、ジョブの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-169">The `Receive-Job` cmdlet returns the results of the job.</span></span>

```
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
    103       4    11328       9692    56           1176 audiodg
    804      14    12228      14108   100   101.74  1740 CcmExec
    668       7     2672       6168   104    32.26   488 csrss
# ...
```

<span data-ttu-id="f40f8-170">ジョブの結果を変数に保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-170">You can also save the results of a job in a variable.</span></span> <span data-ttu-id="f40f8-171">次のコマンドは、変数内のジョブの結果を `$job` 変数に保存し `$results` ます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-171">The following command saves the results of the job in the `$job` variable to the `$results` variable.</span></span>

```powershell
$results = Receive-Job -Job $job
```

<span data-ttu-id="f40f8-172">また、リダイレクト演算子 ( `>` ) またはコマンドレットを使用して、ジョブの結果をファイルに保存することもでき `Out-File` ます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-172">And, you can save the results of the job in a file by using the redirection operator (`>`) or the `Out-File` cmdlet.</span></span> <span data-ttu-id="f40f8-173">次のコマンドは、リダイレクト演算子を使用して、ジョブの結果を `$job` ファイル内の変数に保存し `Results.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-173">The following command uses the redirection operator to save the results of the job in the `$job` variable in the `Results.txt` file.</span></span>

```powershell
Receive-Job -Job $job > results.txt
```

## <a name="getting-and-keeping-partial-job-results"></a><span data-ttu-id="f40f8-174">部分的なジョブ結果の取得と保持</span><span class="sxs-lookup"><span data-stu-id="f40f8-174">Getting and keeping partial job results</span></span>

<span data-ttu-id="f40f8-175">コマンドレットでは、 `Receive-Job` バックグラウンドジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-175">The `Receive-Job` cmdlet gets the results of a background job.</span></span> <span data-ttu-id="f40f8-176">ジョブが完了すると、は `Receive-Job` すべてのジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-176">If the job is complete, `Receive-Job` gets all job results.</span></span> <span data-ttu-id="f40f8-177">ジョブがまだ実行中の場合は、 `Receive-Job` これまでに生成された結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-177">If the job is still running, `Receive-Job` gets the results that have been generated thus far.</span></span> <span data-ttu-id="f40f8-178">`Receive-Job`コマンドをもう一度実行して、残りの結果を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-178">You can run `Receive-Job` commands again to get the remaining results.</span></span>

<span data-ttu-id="f40f8-179">`Receive-Job`が結果を返す場合、既定では、ジョブの結果が格納されているキャッシュから結果が削除されます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-179">When `Receive-Job` returns results, by default, it deletes those results from the cache where job results are stored.</span></span> <span data-ttu-id="f40f8-180">別のコマンドを実行すると `Receive-Job` 、まだ受け取っていない結果だけが取得されます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-180">If you run another `Receive-Job` command, you get only the results that are not yet received.</span></span>

<span data-ttu-id="f40f8-181">次のコマンドは、 `Receive-Job` ジョブが完了する前に実行されたコマンドの結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="f40f8-181">The following commands show the results of `Receive-Job` commands run before the job is complete.</span></span>

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

<span data-ttu-id="f40f8-182">によって返されたジョブの結果が削除されないようにするには `Receive-Job` 、 **Keep** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-182">To prevent `Receive-Job` from deleting the job results that it has returned, use the **Keep** parameter.</span></span> <span data-ttu-id="f40f8-183">その結果、は、 `Receive-Job` その時点までに生成されたすべての結果を返します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-183">As a result, `Receive-Job` returns all of the results that have been generated until that time.</span></span>

<span data-ttu-id="f40f8-184">次のコマンドは、まだ完了していないジョブで **Keep** パラメーターを使用した場合の影響を示しています。</span><span class="sxs-lookup"><span data-stu-id="f40f8-184">The following commands show the effect of using the **Keep** parameter on a job that is not yet complete.</span></span>

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

## <a name="waiting-for-the-results"></a><span data-ttu-id="f40f8-185">結果を待機しています</span><span class="sxs-lookup"><span data-stu-id="f40f8-185">Waiting for the results</span></span>

<span data-ttu-id="f40f8-186">完了までに時間がかかるコマンドを実行する場合は、ジョブオブジェクトのプロパティを使用して、ジョブがいつ完了したかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-186">If you run a command that takes a long time to complete, you can use the properties of the job object to determine when the job is complete.</span></span> <span data-ttu-id="f40f8-187">次のコマンドでは、オブジェクトを使用して、 `Get-Job` 現在のセッションのすべてのバックグラウンドジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-187">The following command uses the `Get-Job` object to get all of the background jobs in the current session.</span></span>

```powershell
Get-Job
```

<span data-ttu-id="f40f8-188">結果はテーブルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-188">The results appear in a table.</span></span> <span data-ttu-id="f40f8-189">ジョブの状態が [ **状態** 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-189">The status of the job appears in the **State** column.</span></span>

```
Id Name  PSJobTypeName State    HasMoreData Location  Command
-- ----  ------------- -----    ----------- --------  -------
1  Job1  BackgroundJob Complete True        localhost Get-Process
2  Job2  BackgroundJob Running  True        localhost Get-EventLog -Log ...
3  Job3  BackgroundJob Complete True        localhost dir -Path C:\* -Re...
```

<span data-ttu-id="f40f8-190">この場合、State プロパティは、ジョブ2がまだ実行されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-190">In this case, the State property reveals that Job 2 is still running.</span></span> <span data-ttu-id="f40f8-191">コマンドレットを使用して `Receive-Job` ジョブの結果を取得した場合、結果は不完全になります。</span><span class="sxs-lookup"><span data-stu-id="f40f8-191">If you were to use the `Receive-Job` cmdlet to get the job results now, the results would be incomplete.</span></span> <span data-ttu-id="f40f8-192">`Receive-Job`コマンドレットを繰り返し使用して、すべての結果を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-192">You can use the `Receive-Job` cmdlet repeatedly to get all of the results.</span></span> <span data-ttu-id="f40f8-193">既定では、これを使用するたびに、まだ受け取っていない結果のみが取得されますが、コマンドレットの **Keep** パラメーターを使用すると、 `Receive-Job` 既に受信している場合でも結果を保持できます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-193">By default, each time you use it, you get only the results that were not already received, but you can use the **Keep** parameter of the `Receive-Job` cmdlet to retain the results, even though they were already received.</span></span>

<span data-ttu-id="f40f8-194">部分的な結果をファイルに書き込んでから、新しい結果を受け取るか、後でジョブの状態を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-194">You can write the partial results to a file and then append newer results as they arrive or you can wait and check the state of the job later.</span></span>

<span data-ttu-id="f40f8-195">コマンドレットの **Wait** パラメーターを使用できます `Receive-Job` 。これにより、ジョブが完了し、すべての結果が利用可能になるまで、コマンドプロンプトは返されません。</span><span class="sxs-lookup"><span data-stu-id="f40f8-195">You can use the **Wait** parameter of the `Receive-Job` cmdlet, which does not return the command prompt until the job is complete and all results are available.</span></span>

<span data-ttu-id="f40f8-196">また、コマンドレットを使用して、 `Wait-Job` ジョブの結果のいずれかまたはすべてを待機することもできます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-196">You can also use the `Wait-Job` cmdlet to wait for any or all of the results of the job.</span></span> <span data-ttu-id="f40f8-197">`Wait-Job` では、特定のジョブ、すべてのジョブ、またはいずれかのジョブが完了するまで待つことができます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-197">`Wait-Job` lets you wait for a particular job, for all jobs, or for any of the jobs to be completed.</span></span>

<span data-ttu-id="f40f8-198">次のコマンドは、 `Wait-Job` コマンドレットを使用して、 **ID** を持つジョブを待機します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-198">The following command uses the `Wait-Job` cmdlet to wait for a job with **ID**</span></span>
10.

```powershell
Wait-Job -ID 10
```

<span data-ttu-id="f40f8-199">その結果、ジョブが完了するまで PowerShell プロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="f40f8-199">As a result, the PowerShell prompt is suppressed until the job is completed.</span></span>

<span data-ttu-id="f40f8-200">事前に定義した時間が経過するまで待機することもできます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-200">You can also wait for a predetermined period of time.</span></span> <span data-ttu-id="f40f8-201">このコマンドでは、 **Timeout** パラメーターを使用して、待機時間を120秒に制限します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-201">This command uses the **Timeout** parameter to limit the wait to 120 seconds.</span></span> <span data-ttu-id="f40f8-202">時間が経過すると、コマンドプロンプトは返されますが、ジョブはバックグラウンドで実行され続けます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-202">When the time expires, the command prompt returns, but the job continues to run in the background.</span></span>

```powershell
Wait-Job -ID 10 -Timeout 120
```

## <a name="stopping-a-job"></a><span data-ttu-id="f40f8-203">ジョブの停止</span><span class="sxs-lookup"><span data-stu-id="f40f8-203">Stopping a job</span></span>

<span data-ttu-id="f40f8-204">バックグラウンドジョブを停止するには、 `Stop-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-204">To stop a background job, use the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="f40f8-205">次のコマンドは、システムイベントログ内のすべてのエントリを取得するジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-205">The following command starts a job to get every entry in the System event log.</span></span> <span data-ttu-id="f40f8-206">ジョブオブジェクトは変数に保存され `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-206">It saves the job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-EventLog -Log System}
```

<span data-ttu-id="f40f8-207">次のコマンドは、ジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-207">The following command stops the job.</span></span> <span data-ttu-id="f40f8-208">パイプライン演算子 () を使用して `|` 、変数内のジョブをに送信し `$job` `Stop-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-208">It uses a pipeline operator (`|`) to send the job in the `$job` variable to `Stop-Job`.</span></span>

```powershell
$job | Stop-Job
```

## <a name="deleting-a-job"></a><span data-ttu-id="f40f8-209">ジョブの削除</span><span class="sxs-lookup"><span data-stu-id="f40f8-209">Deleting a job</span></span>

<span data-ttu-id="f40f8-210">バックグラウンドジョブを削除するには、 `Remove-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-210">To delete a background job, use the `Remove-Job` cmdlet.</span></span> <span data-ttu-id="f40f8-211">次のコマンドは、変数内のジョブを削除し `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-211">The following command deletes the job in the `$job` variable.</span></span>

```powershell
Remove-Job -Job $job
```

## <a name="investigating-a-failed-job"></a><span data-ttu-id="f40f8-212">失敗したジョブの調査</span><span class="sxs-lookup"><span data-stu-id="f40f8-212">Investigating a failed job</span></span>

<span data-ttu-id="f40f8-213">ジョブが失敗した原因を調べるには、job オブジェクトの **Reason** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-213">To find out why a job failed, use the **Reason** property of the job object.</span></span>

<span data-ttu-id="f40f8-214">次のコマンドは、必要な資格情報を使用せずにジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="f40f8-214">The following command starts a job without the required credentials.</span></span> <span data-ttu-id="f40f8-215">ジョブオブジェクトは変数に保存され `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-215">It saves the job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {New-Item -Path HKLM:\Software\MyCompany}

Id Name  PSJobTypeName State  HasMoreData  Location  Command
-- ----  ------------- -----  -----------  --------  -------
1  Job1  BackgroundJob Failed False        localhost New-Item -Path HKLM:...
```

<span data-ttu-id="f40f8-216">次のコマンドでは、Reason プロパティを使用して、ジョブが失敗する原因となったエラーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="f40f8-216">The following command uses the Reason property to find the error that caused the job to fail.</span></span>

```powershell
$job.ChildJobs[0].JobStateInfo.Reason
```

<span data-ttu-id="f40f8-217">この場合、リモートコンピューターでコマンドを実行するための明示的な資格情報が必要であったため、ジョブが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="f40f8-217">In this case, the job failed because the remote computer required explicit credentials to run the command.</span></span> <span data-ttu-id="f40f8-218">**Reason** プロパティの値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f40f8-218">The value of the **Reason** property is:</span></span>

<span data-ttu-id="f40f8-219">リモートサーバーに接続できませんでした。次のエラーメッセージが表示されました: "アクセスが拒否されました。"</span><span class="sxs-lookup"><span data-stu-id="f40f8-219">Connecting to remote server failed with the following error message: "Access is denied".</span></span>

## <a name="see-also"></a><span data-ttu-id="f40f8-220">関連項目</span><span class="sxs-lookup"><span data-stu-id="f40f8-220">See also</span></span>

- [<span data-ttu-id="f40f8-221">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="f40f8-221">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="f40f8-222">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="f40f8-222">about_Thread_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_Thread_Jobs)
- [<span data-ttu-id="f40f8-223">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="f40f8-223">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="f40f8-224">about_Remote</span><span class="sxs-lookup"><span data-stu-id="f40f8-224">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="f40f8-225">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="f40f8-225">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="f40f8-226">Start-Job</span><span class="sxs-lookup"><span data-stu-id="f40f8-226">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="f40f8-227">Get-Job</span><span class="sxs-lookup"><span data-stu-id="f40f8-227">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="f40f8-228">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="f40f8-228">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="f40f8-229">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="f40f8-229">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="f40f8-230">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="f40f8-230">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="f40f8-231">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="f40f8-231">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="f40f8-232">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="f40f8-232">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
