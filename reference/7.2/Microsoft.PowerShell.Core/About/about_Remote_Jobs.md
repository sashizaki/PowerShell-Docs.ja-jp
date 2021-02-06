---
description: リモートコンピューターでジョブを実行する方法について説明します。
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_jobs?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Jobs
ms.openlocfilehash: 93e1d3aba1f4037cc3c5c18386488bf321fc2a64
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599903"
---
# <a name="about-remote-jobs"></a><span data-ttu-id="eace8-103">リモートジョブについて</span><span class="sxs-lookup"><span data-stu-id="eace8-103">About Remote Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="eace8-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="eace8-104">Short Description</span></span>
<span data-ttu-id="eace8-105">リモートコンピューターでバックグラウンドジョブを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eace8-105">Describes how to run background jobs on remote computers.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="eace8-106">詳しい説明</span><span class="sxs-lookup"><span data-stu-id="eace8-106">Detailed Description</span></span>

<span data-ttu-id="eace8-107">PowerShell は、ジョブを使用してコマンドとスクリプトを同時に実行します。</span><span class="sxs-lookup"><span data-stu-id="eace8-107">PowerShell concurrently runs commands and scripts through jobs.</span></span> <span data-ttu-id="eace8-108">同時実行をサポートするために PowerShell によって提供されるジョブの種類は3つあります。</span><span class="sxs-lookup"><span data-stu-id="eace8-108">There are three jobs types provided by PowerShell to support concurrency.</span></span>

- <span data-ttu-id="eace8-109">`RemoteJob` -コマンドとスクリプトはリモートセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="eace8-109">`RemoteJob` - Commands and scripts run in a remote session.</span></span>
- <span data-ttu-id="eace8-110">`BackgroundJob` -コマンドとスクリプトは、ローカルコンピューター上で個別のプロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="eace8-110">`BackgroundJob` - Commands and scripts run in a separate process on the local machine.</span></span> <span data-ttu-id="eace8-111">詳細については、「[about_Jobs](about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eace8-111">For more information, see [about_Jobs](about_Jobs.md).</span></span>
- <span data-ttu-id="eace8-112">`PSTaskJob` または `ThreadJob` -コマンドとスクリプトは、ローカルコンピューター上の同じプロセス内の別のスレッドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="eace8-112">`PSTaskJob` or `ThreadJob` - Commands and scripts run in a separate thread within the same process on the local machine.</span></span> <span data-ttu-id="eace8-113">詳細については、「 [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eace8-113">For more information, see [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).</span></span>

<span data-ttu-id="eace8-114">別のコンピューターまたは別のプロセスでスクリプトをリモートで実行すると、優れた分離が実現します。</span><span class="sxs-lookup"><span data-stu-id="eace8-114">Running scripts remotely, on a separate machine or in a separate process, provide great isolation.</span></span> <span data-ttu-id="eace8-115">リモートジョブで発生したエラーは、他の実行中のジョブ、またはジョブを開始した親セッションには影響しません。</span><span class="sxs-lookup"><span data-stu-id="eace8-115">Any errors that occur in the remote job do not affect other running jobs or the parent session that started the job.</span></span> <span data-ttu-id="eace8-116">ただし、リモート処理層では、オブジェクトのシリアル化などのオーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="eace8-116">However, the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="eace8-117">すべてのオブジェクトは、親セッションとリモート (ジョブ) セッションの間で渡されるときにシリアル化および逆シリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="eace8-117">All objects are serialized and deserialized as they are passed between the parent session and the remote (job) session.</span></span> <span data-ttu-id="eace8-118">大きな複雑なデータオブジェクトのシリアル化は、大量のコンピューティングリソースとメモリリソースを消費し、ネットワーク経由で大量のデータを転送することがあります。</span><span class="sxs-lookup"><span data-stu-id="eace8-118">Serialization of large complex data objects can consume large amounts of compute and memory resources and transfer large amounts of data across the network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eace8-119">ジョブを作成した親セッションもジョブの状態を監視し、パイプラインデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="eace8-119">The parent session that created the job also monitors the job status and collects pipeline data.</span></span> <span data-ttu-id="eace8-120">ジョブが完了状態になると、親プロセスによってジョブの子プロセスが終了します。</span><span class="sxs-lookup"><span data-stu-id="eace8-120">The job child process is terminated by the parent process once the job reaches a finished state.</span></span> <span data-ttu-id="eace8-121">親セッションが終了すると、実行中のすべての子ジョブが子プロセスと共に終了します。</span><span class="sxs-lookup"><span data-stu-id="eace8-121">If the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span>

<span data-ttu-id="eace8-122">この状況に対処するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="eace8-122">There are two ways work around this situation:</span></span>

1. <span data-ttu-id="eace8-123">`Invoke-Command`切断されたセッションで実行されるジョブを作成するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="eace8-123">Use `Invoke-Command` to create jobs that run in disconnected sessions.</span></span> <span data-ttu-id="eace8-124">この記事の「デタッチされた [プロセス](#how-to-run-as-a-detached-process) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eace8-124">See the [detached processes](#how-to-run-as-a-detached-process) section of this article.</span></span>
1. <span data-ttu-id="eace8-125">`Start-Process`ジョブではなく新しいプロセスを作成するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="eace8-125">Use `Start-Process` to create a new process rather than a job.</span></span> <span data-ttu-id="eace8-126">詳細については、「 [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eace8-126">For more information, see [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span></span>

## <a name="remote-jobs"></a><span data-ttu-id="eace8-127">リモートジョブ</span><span class="sxs-lookup"><span data-stu-id="eace8-127">Remote Jobs</span></span>

<span data-ttu-id="eace8-128">3種類の方法を使用して、リモートコンピューターでジョブを実行できます。</span><span class="sxs-lookup"><span data-stu-id="eace8-128">You can run jobs on remote computers by using three different methods.</span></span>

- <span data-ttu-id="eace8-129">リモートコンピューターで対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="eace8-129">Start an interactive session on a remote computer.</span></span> <span data-ttu-id="eace8-130">次に、対話型セッションでジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="eace8-130">Then start a job in the interactive session.</span></span> <span data-ttu-id="eace8-131">これらの手順はローカルジョブを実行するのと同じですが、すべての操作はリモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="eace8-131">The procedures are the same as running a local job, although all actions are performed on the remote computer.</span></span>

- <span data-ttu-id="eace8-132">結果をローカルコンピューターに返すリモートコンピューターでジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="eace8-132">Run a job on a remote computer that returns its results to the local computer.</span></span> <span data-ttu-id="eace8-133">ジョブの結果を収集し、ローカルコンピューター上の中央の場所に保持する場合は、この方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="eace8-133">Use this method when you want to collect the results of jobs and maintain them in a central location on the local computer.</span></span>

- <span data-ttu-id="eace8-134">リモートコンピューター上で結果が保持されているリモートコンピューターでジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="eace8-134">Run a job on a remote computer that maintains its results on the remote computer.</span></span> <span data-ttu-id="eace8-135">この方法は、ジョブデータを元のコンピューターでより安全に維持する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="eace8-135">Use this method when the job data is more securely maintained on the originating computer.</span></span>

### <a name="start-a-job-in-an-interactive-session"></a><span data-ttu-id="eace8-136">対話型セッションでジョブを開始する</span><span class="sxs-lookup"><span data-stu-id="eace8-136">Start a job in an interactive session</span></span>

<span data-ttu-id="eace8-137">リモートコンピューターで対話型セッションを開始し、対話型セッション中にジョブを開始することができます。</span><span class="sxs-lookup"><span data-stu-id="eace8-137">You can start an interactive session with a remote computer and then start a job during the interactive session.</span></span> <span data-ttu-id="eace8-138">対話型セッションの詳細については、「about_Remote」および「」を参照してください `Enter-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="eace8-138">For more information about interactive sessions, see about_Remote, and see `Enter-PSSession`.</span></span>

<span data-ttu-id="eace8-139">対話型セッションでジョブを開始する手順は、ローカルコンピューターでバックグラウンドジョブを開始する手順とほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="eace8-139">The procedure for starting a job in an interactive session is almost identical to the procedure for starting a background job on the local computer.</span></span> <span data-ttu-id="eace8-140">ただし、すべての操作は、ローカルコンピューターではなく、リモートコンピューター上で行われます。</span><span class="sxs-lookup"><span data-stu-id="eace8-140">However, all of the operations occur on the remote computer, not the local computer.</span></span>

1. <span data-ttu-id="eace8-141">`Enter-PSSession`コマンドレットを使用して、リモートコンピューターとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="eace8-141">Use the `Enter-PSSession` cmdlet to start an interactive session with a remote computer.</span></span> <span data-ttu-id="eace8-142">の ComputerName パラメーターを使用して、 `Enter-PSSession` 対話型セッションの一時的な接続を確立できます。</span><span class="sxs-lookup"><span data-stu-id="eace8-142">You can use the ComputerName parameter of `Enter-PSSession` to establish a temporary connection for the interactive session.</span></span> <span data-ttu-id="eace8-143">または、Session パラメーターを使用して、PowerShell セッション (PSSession) で対話型セッションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="eace8-143">Or, you can use the Session parameter to run the interactive session in a PowerShell session (PSSession).</span></span>

   <span data-ttu-id="eace8-144">次のコマンドは、Server01 コンピューター上で対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="eace8-144">The following command starts an interactive session on the Server01 computer.</span></span>

   ```powershell
   C:\PS> Enter-PSSession -computername Server01
   ```

   <span data-ttu-id="eace8-145">Server01 コンピューターに接続されていることを示すために、コマンドプロンプトが変更されます。</span><span class="sxs-lookup"><span data-stu-id="eace8-145">The command prompt changes to show that you are now connected to the Server01 computer.</span></span>

   ```
   Server01\C:>
   ```

1. <span data-ttu-id="eace8-146">セッションでリモートジョブを開始するには、コマンドレットを使用し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="eace8-146">To start a remote job in the session, use the `Start-Job` cmdlet.</span></span> <span data-ttu-id="eace8-147">次のコマンドは、Server01 コンピューター上の Windows PowerShell イベントログに含まれるイベントを取得するリモートジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="eace8-147">The following command runs a remote job that gets the events in the Windows PowerShell event log on the Server01 computer.</span></span> <span data-ttu-id="eace8-148">`Start-Job`コマンドレットは、ジョブを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="eace8-148">The `Start-Job` cmdlet returns an object that represents the job.</span></span>

   <span data-ttu-id="eace8-149">このコマンドは、ジョブオブジェクトを変数に保存し `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="eace8-149">This command saves the job object in the `$job` variable.</span></span>

   ```powershell
   Server01\C:> $job = Start-Job -scriptblock {
     Get-Eventlog "Windows PowerShell"
   }
   ```

   <span data-ttu-id="eace8-150">ジョブの実行中に、対話型セッションを使用して他のコマンド (他のジョブを含む) を実行できます。</span><span class="sxs-lookup"><span data-stu-id="eace8-150">While the job runs, you can use the interactive session to run other commands, including other jobs.</span></span> <span data-ttu-id="eace8-151">ただし、ジョブが完了するまで、対話型セッションを開いたままにしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="eace8-151">However, you must keep the interactive session open until the job is completed.</span></span> <span data-ttu-id="eace8-152">セッションを終了すると、ジョブは中断され、結果は失われます。</span><span class="sxs-lookup"><span data-stu-id="eace8-152">If you end the session, the job is interrupted, and the results are lost.</span></span>

1. <span data-ttu-id="eace8-153">ジョブが完了したかどうかを確認するには、変数の値を表示する `$job` か、コマンドレットを使用してジョブを取得し `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="eace8-153">To find out if the job is complete, display the value of the `$job` variable, or use the `Get-Job` cmdlet to get the job.</span></span> <span data-ttu-id="eace8-154">次のコマンドでは、 `Get-Job` コマンドレットを使用してジョブを表示します。</span><span class="sxs-lookup"><span data-stu-id="eace8-154">The following command uses the `Get-Job` cmdlet to display the job.</span></span>

   ```powershell
   Server01\C:> Get-Job $job

   SessionId  Name  State      HasMoreData  Location   Command
   ---------  ----  -----      -----------  --------   -------
   1          Job1  Complete   True         localhost  Get-Eventlog "Windows...
   ```

   <span data-ttu-id="eace8-155">この出力は、ジョブ `Get-Job` が "localhost" コンピューター上で実行されていることを示しています。これは、ジョブがで開始され、同じコンピューター (この場合は Server01) で実行されているためです。</span><span class="sxs-lookup"><span data-stu-id="eace8-155">The `Get-Job` output shows that job is running on the "localhost" computer because the job was started on and is running on the same computer (in this case, Server01).</span></span>

1. <span data-ttu-id="eace8-156">ジョブの結果を取得するには、コマンドレットを使用し `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="eace8-156">To get the results of the job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="eace8-157">対話型セッションで結果を表示したり、リモートコンピューター上のファイルに結果を保存したりできます。</span><span class="sxs-lookup"><span data-stu-id="eace8-157">You can display the results in the interactive session or save them to a file on the remote computer.</span></span> <span data-ttu-id="eace8-158">次のコマンドは、$job 変数内のジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="eace8-158">The following command gets the results of the job in the $job variable.</span></span> <span data-ttu-id="eace8-159">このコマンドは、リダイレクト演算子 () を使用して、 `>` ジョブの結果を Server01 コンピューターの PsLog.txt ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="eace8-159">The command uses the redirection operator (`>`) to save the results of the job in the PsLog.txt file on the Server01 computer.</span></span>

   ```powershell
   Server01\C:> Receive-Job $job > c:\logs\PsLog.txt
   ```

1. <span data-ttu-id="eace8-160">対話型セッションを終了するには、 `Exit-PSSession` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="eace8-160">To end the interactive session, use the `Exit-PSSession` cmdlet.</span></span> <span data-ttu-id="eace8-161">コマンドプロンプトが変更され、ローカルコンピューターの元のセッションに戻ったことが示されます。</span><span class="sxs-lookup"><span data-stu-id="eace8-161">The command prompt changes to show that you are back in the original session on the local computer.</span></span>

   ```powershell
   Server01\C:> Exit-PSSession
   C:\PS>
   ```

1. <span data-ttu-id="eace8-162">Server01 コンピューター上のファイルの内容をいつでも表示するに `PsLog.txt` は、別の対話型セッションを開始するか、リモートコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="eace8-162">To view the contents of the `PsLog.txt` file on the Server01 computer at any time, start another interactive session, or run a remote command.</span></span> <span data-ttu-id="eace8-163">この種類のコマンドは、複数のコマンドを使用してファイル内のデータを調査および管理する場合に、PSSession (固定接続) で実行することをお勧めし `PsLog.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="eace8-163">This type of command is best run in a PSSession (a persistent connection) in case you want to use several commands to investigate and manage the data in the `PsLog.txt` file.</span></span> <span data-ttu-id="eace8-164">PSSessions の詳細については、「 [about_PSSessions](about_PSSessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eace8-164">For more information about PSSessions, see [about_PSSessions](about_PSSessions.md).</span></span>

   <span data-ttu-id="eace8-165">次のコマンドは、コマンドレットを使用して、 `New-PSSession` Server01 コンピューターに接続されている **pssession** を作成し、コマンドレットを使用して `Invoke-Command` pssession 内のコマンドを実行し、 `Get-Content` ファイルの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="eace8-165">The following commands use the `New-PSSession` cmdlet to create a **PSSession** that is connected to the Server01 computer, and they use the `Invoke-Command` cmdlet to run a `Get-Content` command in the PSSession to view the contents of the file.</span></span>

   ```powershell
   $s = New-PSSession -computername Server01
   Invoke-Command -session $s -scriptblock {
     Get-Content c:\logs\pslog.txt}
   ```

### <a name="start-a-remote-job-that-returns-the-results-to-the-local-computer-asjob"></a><span data-ttu-id="eace8-166">結果をローカルコンピューター (AsJob) に返すリモートジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="eace8-166">Start a remote job that returns the results to the local computer (AsJob)</span></span>

<span data-ttu-id="eace8-167">コマンドの結果をローカルコンピューターに返すリモートコンピューターでジョブを開始するには、コマンドレットなどのコマンドレットの **AsJob** パラメーターを使用し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="eace8-167">To start a job on a remote computer that returns the command results to the local computer, use the **AsJob** parameter of a cmdlet such as the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="eace8-168">**AsJob** パラメーターを使用すると、ジョブがリモートコンピューター上で実行されている場合でも、ジョブオブジェクトは実際にはローカルコンピューター上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="eace8-168">When you use the **AsJob** parameter, the job object is actually created on the local computer even though the job runs on the remote computer.</span></span> <span data-ttu-id="eace8-169">ジョブが完了すると、結果がローカルコンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="eace8-169">When the job is completed, the results are returned to the local computer.</span></span>

<span data-ttu-id="eace8-170">ジョブの名詞を含むコマンドレット (Job コマンドレット) を使用して、任意のコマンドレットによって作成されたすべてのジョブを管理できます。</span><span class="sxs-lookup"><span data-stu-id="eace8-170">You can use the cmdlets that contain the Job noun (the Job cmdlets) to manage any job created by any cmdlet.</span></span> <span data-ttu-id="eace8-171">**AsJob** パラメーターを持つコマンドレットの多くは、PowerShell リモート処理を使用しないので、リモート処理用に構成されておらず、リモート処理の要件を満たしていないコンピューターでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="eace8-171">Many of the cmdlets that have **AsJob** parameters do not use PowerShell remoting, so you can use them even on computers that are not configured for remoting and that do not meet the requirements for remoting.</span></span>

1. <span data-ttu-id="eace8-172">次のコマンドでは、の **AsJob** パラメーターを使用して `Invoke-Command` 、Server01 コンピューター上でジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="eace8-172">The following command uses the **AsJob** parameter of `Invoke-Command` to start a job on the Server01 computer.</span></span> <span data-ttu-id="eace8-173">このジョブは、 `Get-Eventlog` システムログ内のイベントを取得するコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="eace8-173">The job runs a `Get-Eventlog` command that gets the events in the System log.</span></span> <span data-ttu-id="eace8-174">JobName パラメーターを使用して、ジョブに表示名を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="eace8-174">You can use the JobName parameter to assign a display name to the job.</span></span>

   ```powershell
   Invoke-Command -computername Server01 -scriptblock {
     Get-Eventlog system} -AsJob
   ```

   <span data-ttu-id="eace8-175">コマンドの結果は、次のサンプル出力のようになります。</span><span class="sxs-lookup"><span data-stu-id="eace8-175">The results of the command resemble the following sample output.</span></span>

   ```Output
   SessionId   Name   State    HasMoreData   Location   Command
   ---------   ----   -----    -----------   --------   -------
   1           Job1   Running  True          Server01   Get-Eventlog system
   ```

   <span data-ttu-id="eace8-176">**AsJob** パラメーターが使用されている場合、はを `Invoke-Command` 返すのと同じ種類のジョブオブジェクトを返し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="eace8-176">When the **AsJob** parameter is used, `Invoke-Command` returns the same type of job object that `Start-Job` returns.</span></span> <span data-ttu-id="eace8-177">ジョブオブジェクトを変数に保存することも、コマンドを使用してジョブを取得することもでき `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="eace8-177">You can save the job object in a variable, or you can use a `Get-Job` command to get the job.</span></span>

   <span data-ttu-id="eace8-178">Location プロパティの値は、Server01 コンピューターでジョブが実行されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="eace8-178">Note that the value of the Location property shows that the job ran on the Server01 computer.</span></span>

1. <span data-ttu-id="eace8-179">コマンドレットの **AsJob** パラメーターを使用して開始されたジョブを管理するには `Invoke-Command` 、job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="eace8-179">To manage a job started by using the **AsJob** parameter of the `Invoke-Command` cmdlet, use the Job cmdlets.</span></span> <span data-ttu-id="eace8-180">リモートジョブを表すジョブオブジェクトはローカルコンピューター上にあるため、リモートコマンドを実行してジョブを管理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="eace8-180">Because the job object that represents the remote job is on the local computer, you do not need to run remote commands to manage the job.</span></span>

   <span data-ttu-id="eace8-181">ジョブが完了したかどうかを確認するには、コマンドを使用し `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="eace8-181">To determine whether the job is complete, use a `Get-Job` command.</span></span> <span data-ttu-id="eace8-182">次のコマンドは、現在のセッションで開始されたすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="eace8-182">The following command gets all of the jobs that were started in the current session.</span></span>

   ```powershell
   Get-Job
   ```

   <span data-ttu-id="eace8-183">リモートジョブが現在のセッションで開始されたため、ローカル `Get-Job` コマンドはジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="eace8-183">Because the remote job was started in the current session, a local `Get-Job` command gets the job.</span></span> <span data-ttu-id="eace8-184">ジョブオブジェクトの State プロパティは、コマンドが正常に完了したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="eace8-184">The State property of the job object shows that the command was completed successfully.</span></span>

   ```Output
   SessionId   Name   State      HasMoreData   Location   Command
   ---------   ----   -----      -----------   --------   -------
   1           Job1   Completed  True          Server01   Get-Eventlog system
   ```

1. <span data-ttu-id="eace8-185">ジョブの結果を取得するには、コマンドレットを使用し `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="eace8-185">To get the results of the job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="eace8-186">ジョブの結果は、ジョブオブジェクトが存在するコンピューターに自動的に返されるため、ローカルコマンドを使用して結果を取得でき `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="eace8-186">Because the job results are automatically returned to the computer where the job object resides, you can get the results with a local `Receive-Job` command.</span></span>

   <span data-ttu-id="eace8-187">次のコマンドでは、 `Receive-Job` コマンドレットを使用してジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="eace8-187">The following command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="eace8-188">セッション ID を使用してジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="eace8-188">It uses the session ID to identify the job.</span></span> <span data-ttu-id="eace8-189">このコマンドは、ジョブの結果を $results 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="eace8-189">This command saves the job results in the $results variable.</span></span> <span data-ttu-id="eace8-190">また、結果をファイルにリダイレクトすることもできます。</span><span class="sxs-lookup"><span data-stu-id="eace8-190">You can also redirect the results to a file.</span></span>

   ```powershell
   $results = Receive-Job -id 1
   ```

### <a name="start-a-remote-job-that-keeps-the-results-on-the-remote-computer"></a><span data-ttu-id="eace8-191">リモートコンピューターで結果を保持するリモートジョブを開始する</span><span class="sxs-lookup"><span data-stu-id="eace8-191">Start a remote job that keeps the results on the remote computer</span></span>

<span data-ttu-id="eace8-192">リモートコンピューターでコマンドの結果を保持するジョブをリモートコンピューター上で開始するには、コマンドレットを使用して `Invoke-Command` リモートコンピューターでコマンドを実行し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="eace8-192">To start a job on a remote computer that keeps the command results on the remote computer, use the `Invoke-Command` cmdlet to run a `Start-Job` command on a remote computer.</span></span> <span data-ttu-id="eace8-193">この方法を使用すると、複数のコンピューターでジョブを実行できます。</span><span class="sxs-lookup"><span data-stu-id="eace8-193">You can use this method to run jobs on multiple computers.</span></span>

<span data-ttu-id="eace8-194">コマンドをリモートで実行すると、 `Start-Job` ジョブオブジェクトがリモートコンピューター上に作成され、ジョブの結果がリモートコンピューターに保持されます。</span><span class="sxs-lookup"><span data-stu-id="eace8-194">When you run a `Start-Job` command remotely, the job object is created on the remote computer, and the job results are maintained on the remote computer.</span></span>
<span data-ttu-id="eace8-195">ジョブの観点から見ると、すべての操作はローカルです。</span><span class="sxs-lookup"><span data-stu-id="eace8-195">From the perspective of the job, all operations are local.</span></span> <span data-ttu-id="eace8-196">リモートコンピューター上のローカルジョブを管理するために、コマンドをリモートで実行しているだけです。</span><span class="sxs-lookup"><span data-stu-id="eace8-196">You are just running commands remotely to manage a local job on the remote computer.</span></span>

1. <span data-ttu-id="eace8-197">コマンドレットを使用して、 `Invoke-Command` `Start-Job` リモートコンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="eace8-197">Use the `Invoke-Command` cmdlet to run a `Start-Job` command on a remote computer.</span></span>

   <span data-ttu-id="eace8-198">このコマンドには PSSession (永続的な接続) が必要です。</span><span class="sxs-lookup"><span data-stu-id="eace8-198">This command requires a PSSession (a persistent connection).</span></span> <span data-ttu-id="eace8-199">の ComputerName パラメーターを使用して `Invoke-Command` 一時的な接続を確立すると、 `Invoke-Command` ジョブオブジェクトが返されたときにコマンドは完了したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="eace8-199">If you use the ComputerName parameter of `Invoke-Command` to establish a temporary connection, the `Invoke-Command` command is considered to be complete when the job object is returned.</span></span> <span data-ttu-id="eace8-200">その結果、一時的な接続は閉じられ、ジョブは取り消されます。</span><span class="sxs-lookup"><span data-stu-id="eace8-200">As a result, the temporary connection is closed, and the job is canceled.</span></span>

   <span data-ttu-id="eace8-201">次のコマンドでは、コマンドレットを使用して、 `New-PSSession` Server01 コンピューターに接続されている PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="eace8-201">The following command uses the `New-PSSession` cmdlet to create a PSSession that is connected to the Server01 computer.</span></span> <span data-ttu-id="eace8-202">このコマンドは、PSSession を変数に保存し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="eace8-202">The command saves the PSSession in the `$s` variable.</span></span>

   ```powershell
   $s = New-PSSession -computername Server01
   ```

   <span data-ttu-id="eace8-203">次のコマンドは、コマンドレットを使用して `Invoke-Command` `Start-Job` PSSession 内のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="eace8-203">The next command uses the `Invoke-Command` cmdlet to run a `Start-Job` command in the PSSession.</span></span> <span data-ttu-id="eace8-204">`Start-Job`コマンドとコマンドは、 `Get-Eventlog` 中かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="eace8-204">The `Start-Job` command and the `Get-Eventlog` command are enclosed in braces.</span></span>

   ```powershell
   Invoke-Command -session $s -scriptblock {
     Start-Job -scriptblock {Get-Eventlog system}}
   ```

   <span data-ttu-id="eace8-205">結果は次のサンプル出力のようになります。</span><span class="sxs-lookup"><span data-stu-id="eace8-205">The results resemble the following sample output.</span></span>

   ```Output
   Id       Name    State      HasMoreData     Location   Command
   --       ----    -----      -----------     --------   -------
   2        Job2    Running    True            Localhost  Get-Eventlog system
   ```

   <span data-ttu-id="eace8-206">コマンドをリモートで実行すると `Start-Job` 、に `Invoke-Command` よって返されるのと同じ種類のジョブオブジェクトが返さ `Start-Job` れます。</span><span class="sxs-lookup"><span data-stu-id="eace8-206">When you run a `Start-Job` command remotely, `Invoke-Command` returns the same type of job object that `Start-Job` returns.</span></span> <span data-ttu-id="eace8-207">ジョブオブジェクトを変数に保存することも、コマンドを使用してジョブを取得することもでき `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="eace8-207">You can save the job object in a variable, or you can use a `Get-Job` command to get the job.</span></span>

   <span data-ttu-id="eace8-208">**Location** プロパティの値は、ジョブが Server01 コンピューター上で実行された場合でも、ローカルコンピューター上でジョブが実行されたことを示しています。これは、"LocalHost" と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="eace8-208">Note that the value of the **Location** property shows that the job ran on the local computer, known as "LocalHost", even though the job ran on the Server01 computer.</span></span> <span data-ttu-id="eace8-209">ジョブオブジェクトは Server01 コンピューター上に作成され、ジョブは同じコンピューター上で実行されるため、ローカルのバックグラウンドジョブと見なされます。</span><span class="sxs-lookup"><span data-stu-id="eace8-209">Because the job object is created on the Server01 computer and the job runs on the same computer, it is considered to be a local background job.</span></span>

1. <span data-ttu-id="eace8-210">リモートジョブを管理するには、 **job** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="eace8-210">To manage a remote job, use the **Job** cmdlets.</span></span> <span data-ttu-id="eace8-211">ジョブオブジェクトはリモートコンピューター上にあるため、リモートコマンドを実行して、ジョブの結果を取得、停止、待機、または取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eace8-211">Because the job object is on the remote computer, you need to run remote commands to get, stop, wait for, or retrieve the job results.</span></span>

   <span data-ttu-id="eace8-212">ジョブが完了したかどうかを確認するには、コマンドを使用して、 `Invoke-Command` `Get-Job` Server01 コンピューターに接続されている PSSession でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="eace8-212">To see if the job is complete, use an `Invoke-Command` command to run a `Get-Job` command in the PSSession that is connected to the Server01 computer.</span></span>

   ```powershell
   Invoke-Command -session $s -scriptblock {Get-Job}
   ```

   <span data-ttu-id="eace8-213">このコマンドによって返されるのは、ジョブ オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="eace8-213">The command returns a job object.</span></span> <span data-ttu-id="eace8-214">ジョブオブジェクトの **State** プロパティは、コマンドが正常に完了したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="eace8-214">The **State** property of the job object shows that the command was completed successfully.</span></span>

   ```Output
   SessionId   Name  State      HasMoreData   Location   Command
   ---------   ----  -----      -----------   --------   -------
   2           Job2  Completed  True          LocalHost   Get-Eventlog system
   ```

1. <span data-ttu-id="eace8-215">ジョブの結果を取得するには、コマンドレットを使用して、 `Invoke-Command` `Receive-Job` Server01 コンピューターに接続されている PSSession でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="eace8-215">To get the results of the job, use the `Invoke-Command` cmdlet to run a `Receive-Job` command in the PSSession that is connected to the Server01 computer.</span></span>

   <span data-ttu-id="eace8-216">次のコマンドでは、 `Receive-Job` コマンドレットを使用してジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="eace8-216">The following command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="eace8-217">セッション ID を使用してジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="eace8-217">It uses the session ID to identify the job.</span></span> <span data-ttu-id="eace8-218">このコマンドは、ジョブの結果を変数に保存し `$results` ます。</span><span class="sxs-lookup"><span data-stu-id="eace8-218">This command saves the job results in the `$results` variable.</span></span> <span data-ttu-id="eace8-219">この例では、の Keep パラメーターを使用して、 `Receive-Job` リモートコンピューター上のジョブキャッシュに結果を保持します。</span><span class="sxs-lookup"><span data-stu-id="eace8-219">It uses the Keep parameter of `Receive-Job` to keep the result in the job cache on the remote computer.</span></span>

   ```powershell
   $results = Invoke-Command -session $s -scriptblock {
     Receive-Job -SessionId 2 -Keep
   }
   ```

   <span data-ttu-id="eace8-220">また、ローカルコンピューターまたはリモートコンピューター上のファイルに結果をリダイレクトすることもできます。</span><span class="sxs-lookup"><span data-stu-id="eace8-220">You can also redirect the results to a file on the local or remote computer.</span></span>
   <span data-ttu-id="eace8-221">次のコマンドは、リダイレクト演算子を使用して、Server01 コンピューター上のファイルに結果を保存します。</span><span class="sxs-lookup"><span data-stu-id="eace8-221">The following command uses a redirection operator to save the results in a file on the Server01 computer.</span></span>

   ```powershell
   Invoke-Command -session $s -command {
     Receive-Job -SessionId 2 > c:\logs\pslog.txt
   }
   ```

## <a name="how-to-run-as-a-detached-process"></a><span data-ttu-id="eace8-222">デタッチされたプロセスとして実行する方法</span><span class="sxs-lookup"><span data-stu-id="eace8-222">How to run as a detached process</span></span>

<span data-ttu-id="eace8-223">既に説明したように、親セッションが終了すると、実行中のすべての子ジョブが子プロセスと共に終了します。</span><span class="sxs-lookup"><span data-stu-id="eace8-223">As previously mentioned, when the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span> <span data-ttu-id="eace8-224">ローカルコンピューターでリモート処理を使用して、現在の PowerShell セッションにアタッチされていないジョブを実行できます。</span><span class="sxs-lookup"><span data-stu-id="eace8-224">You can use remoting on the local machine to run jobs that are not attached to the current PowerShell session.</span></span>

<span data-ttu-id="eace8-225">ローカルコンピューターで新しい PowerShell セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="eace8-225">Create a new PowerShell session on the local machine.</span></span> <span data-ttu-id="eace8-226">`Invoke-Command`このセッションでジョブを開始するために使用する。</span><span class="sxs-lookup"><span data-stu-id="eace8-226">The use `Invoke-Command` to start a job in this session.</span></span> <span data-ttu-id="eace8-227">`Invoke-Command` リモートセッションを切断し、親セッションを終了することができます。</span><span class="sxs-lookup"><span data-stu-id="eace8-227">`Invoke-Command` allows you to disconnect a remote session and terminate the parent session.</span></span> <span data-ttu-id="eace8-228">後で、新しい PowerShell セッションを開始し、以前に切断されたセッションに接続して、ジョブの監視を再開できます。</span><span class="sxs-lookup"><span data-stu-id="eace8-228">Later, you can start a new PowerShell session and connect to the previously disconnected session to resume monitoring the job.</span></span> <span data-ttu-id="eace8-229">ただし、元の PowerShell セッションに返されたデータは、そのセッションが終了したときに失われます。</span><span class="sxs-lookup"><span data-stu-id="eace8-229">However, any data that was returned to the original PowerShell session is lost when that session is terminated.</span></span> <span data-ttu-id="eace8-230">再接続時に返されるのは、切断後に生成される新しいデータオブジェクトだけです。</span><span class="sxs-lookup"><span data-stu-id="eace8-230">Only new data objects generated after the disconnect are returned when re-connected.</span></span>

```powershell
# Create remote session on local machine
PS> $session = New-PSSession -cn localhost

# Start remote job
PS> $job = Invoke-Command -Session $session -ScriptBlock { 1..60 | % { sleep 1; "Output $_" } } -AsJob
PS> $job

Id     Name     PSJobTypeName   State         HasMoreData     Location      Command
--     ----     -------------   -----         -----------     --------      -------
1      Job1     RemoteJob       Running       True            localhost     1..60 | % { sleep 1; ...

# Disconnect the job session
PS> Disconnect-PSSession $session

Id Name         Transport ComputerName    ComputerType    State         ConfigurationName     Availability
-- ----         --------- ------------    ------------    -----         -----------------     ------------
1 Runspace1     WSMan     localhost       RemoteMachine   Disconnected  Microsoft.PowerShell          None

PS> $job

Id     Name     PSJobTypeName   State         HasMoreData     Location      Command
--     ----     -------------   -----         -----------     --------      -------
1      Job1     RemoteJob       Disconnected  True            localhost     1..60 | % { sleep 1;

# Reconnect the session to a new job object
PS> $jobNew = Receive-PSSession -Session $session -OutTarget Job
PS> $job | Wait-Job | Receive-Job
Output 9
Output 10
Output 11
...
```

<span data-ttu-id="eace8-231">この例では、ジョブは引き続き親 PowerShell セッションにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="eace8-231">For this example, the jobs are still attached to a parent PowerShell session.</span></span>
<span data-ttu-id="eace8-232">ただし、親セッションは、が実行された元の PowerShell セッションではありません `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="eace8-232">However, the parent session is not the original PowerShell session where `Invoke-Command` was run.</span></span>

## <a name="see-also"></a><span data-ttu-id="eace8-233">関連項目</span><span class="sxs-lookup"><span data-stu-id="eace8-233">See also</span></span>

- [<span data-ttu-id="eace8-234">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="eace8-234">about_Jobs</span></span>](about_Jobs.md)
- [<span data-ttu-id="eace8-235">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="eace8-235">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="eace8-236">about_Remote</span><span class="sxs-lookup"><span data-stu-id="eace8-236">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="eace8-237">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="eace8-237">about_Remote_Variables</span></span>](about_Remote_Variables.md)
- [<span data-ttu-id="eace8-238">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="eace8-238">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
- [<span data-ttu-id="eace8-239">Start-Job</span><span class="sxs-lookup"><span data-stu-id="eace8-239">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="eace8-240">Get-Job</span><span class="sxs-lookup"><span data-stu-id="eace8-240">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="eace8-241">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="eace8-241">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="eace8-242">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="eace8-242">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="eace8-243">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="eace8-243">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="eace8-244">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="eace8-244">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
- [<span data-ttu-id="eace8-245">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="eace8-245">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)
- [<span data-ttu-id="eace8-246">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="eace8-246">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)
