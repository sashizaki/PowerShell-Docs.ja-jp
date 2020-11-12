---
description: リモートコンピューターでジョブを実行する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_jobs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Jobs
ms.openlocfilehash: 389db08a2b6528d14ff5f79cd4d369c23ed0c737
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524537"
---
# <a name="about-remote-jobs"></a><span data-ttu-id="20c31-104">リモートジョブについて</span><span class="sxs-lookup"><span data-stu-id="20c31-104">About Remote Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="20c31-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="20c31-105">Short Description</span></span>
<span data-ttu-id="20c31-106">リモートコンピューターでジョブを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="20c31-106">Describes how to run jobs on remote computers.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="20c31-107">詳しい説明</span><span class="sxs-lookup"><span data-stu-id="20c31-107">Detailed Description</span></span>

<span data-ttu-id="20c31-108">PowerShell は、ジョブを使用してコマンドとスクリプトを同時に実行します。</span><span class="sxs-lookup"><span data-stu-id="20c31-108">PowerShell concurrently runs commands and scripts through jobs.</span></span> <span data-ttu-id="20c31-109">同時実行をサポートするために PowerShell によって提供されるジョブの種類は3つあります。</span><span class="sxs-lookup"><span data-stu-id="20c31-109">There are three jobs types provided by PowerShell to support concurrency.</span></span>

- <span data-ttu-id="20c31-110">`RemoteJob` -コマンドとスクリプトはリモートセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="20c31-110">`RemoteJob` - Commands and scripts run in a remote session.</span></span>
- <span data-ttu-id="20c31-111">`BackgroundJob` -コマンドとスクリプトは、ローカルコンピューター上で個別のプロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="20c31-111">`BackgroundJob` - Commands and scripts run in a separate process on the local machine.</span></span> <span data-ttu-id="20c31-112">詳細については、「[about_Jobs](about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c31-112">For more information, see [about_Jobs](about_Jobs.md).</span></span>
- <span data-ttu-id="20c31-113">`PSTaskJob` または `ThreadJob` -コマンドとスクリプトは、ローカルコンピューター上の同じプロセス内の別のスレッドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="20c31-113">`PSTaskJob` or `ThreadJob` - Commands and scripts run in a separate thread within the same process on the local machine.</span></span> <span data-ttu-id="20c31-114">詳細については、「 [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c31-114">For more information, see [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).</span></span>

<span data-ttu-id="20c31-115">別のコンピューターまたは別のプロセスでスクリプトをリモートで実行すると、優れた分離が実現します。</span><span class="sxs-lookup"><span data-stu-id="20c31-115">Running scripts remotely, on a separate machine or in a separate process, provide great isolation.</span></span> <span data-ttu-id="20c31-116">リモートジョブで発生したエラーは、他の実行中のジョブ、またはジョブを開始した親セッションには影響しません。</span><span class="sxs-lookup"><span data-stu-id="20c31-116">Any errors that occur in the remote job do not affect other running jobs or the parent session that started the job.</span></span> <span data-ttu-id="20c31-117">ただし、リモート処理層では、オブジェクトのシリアル化などのオーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="20c31-117">However, the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="20c31-118">すべてのオブジェクトは、親セッションとリモート (ジョブ) セッションの間で渡されるときにシリアル化および逆シリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="20c31-118">All objects are serialized and deserialized as they are passed between the parent session and the remote (job) session.</span></span> <span data-ttu-id="20c31-119">大きな複雑なデータオブジェクトのシリアル化は、大量のコンピューティングリソースとメモリリソースを消費し、ネットワーク経由で大量のデータを転送することがあります。</span><span class="sxs-lookup"><span data-stu-id="20c31-119">Serialization of large complex data objects can consume large amounts of compute and memory resources and transfer large amounts of data across the network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20c31-120">ジョブを作成した親セッションもジョブの状態を監視し、パイプラインデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="20c31-120">The parent session that created the job also monitors the job status and collects pipeline data.</span></span> <span data-ttu-id="20c31-121">ジョブが完了状態になると、親プロセスによってジョブの子プロセスが終了します。</span><span class="sxs-lookup"><span data-stu-id="20c31-121">The job child process is terminated by the parent process once the job reaches a finished state.</span></span> <span data-ttu-id="20c31-122">親セッションが終了すると、実行中のすべての子ジョブが子プロセスと共に終了します。</span><span class="sxs-lookup"><span data-stu-id="20c31-122">If the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span>

<span data-ttu-id="20c31-123">この状況に対処するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="20c31-123">There are two ways work around this situation:</span></span>

1. <span data-ttu-id="20c31-124">`Invoke-Command`切断されたセッションで実行されるジョブを作成するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="20c31-124">Use `Invoke-Command` to create jobs that run in disconnected sessions.</span></span> <span data-ttu-id="20c31-125">この記事の「デタッチされた [プロセス](#how-to-run-as-a-detached-process) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c31-125">See the [detached processes](#how-to-run-as-a-detached-process) section of this article.</span></span>
1. <span data-ttu-id="20c31-126">`Start-Process`ジョブではなく新しいプロセスを作成するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="20c31-126">Use `Start-Process` to create a new process rather than a job.</span></span> <span data-ttu-id="20c31-127">詳細については、「 [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c31-127">For more information, see [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span></span>

## <a name="remote-jobs"></a><span data-ttu-id="20c31-128">リモートジョブ</span><span class="sxs-lookup"><span data-stu-id="20c31-128">Remote Jobs</span></span>

<span data-ttu-id="20c31-129">3種類の方法を使用して、リモートコンピューターでジョブを実行できます。</span><span class="sxs-lookup"><span data-stu-id="20c31-129">You can run jobs on remote computers by using three different methods.</span></span>

- <span data-ttu-id="20c31-130">リモートコンピューターで対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="20c31-130">Start an interactive session on a remote computer.</span></span> <span data-ttu-id="20c31-131">次に、対話型セッションでジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="20c31-131">Then start a job in the interactive session.</span></span> <span data-ttu-id="20c31-132">これらの手順はローカルジョブを実行するのと同じですが、すべての操作はリモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="20c31-132">The procedures are the same as running a local job, although all actions are performed on the remote computer.</span></span>

- <span data-ttu-id="20c31-133">結果をローカルコンピューターに返すリモートコンピューターでジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="20c31-133">Run a job on a remote computer that returns its results to the local computer.</span></span> <span data-ttu-id="20c31-134">ジョブの結果を収集し、ローカルコンピューター上の中央の場所に保持する場合は、この方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="20c31-134">Use this method when you want to collect the results of jobs and maintain them in a central location on the local computer.</span></span>

- <span data-ttu-id="20c31-135">リモートコンピューター上で結果が保持されているリモートコンピューターでジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="20c31-135">Run a job on a remote computer that maintains its results on the remote computer.</span></span> <span data-ttu-id="20c31-136">この方法は、ジョブデータを元のコンピューターでより安全に維持する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="20c31-136">Use this method when the job data is more securely maintained on the originating computer.</span></span>

### <a name="start-a-job-in-an-interactive-session"></a><span data-ttu-id="20c31-137">対話型セッションでジョブを開始する</span><span class="sxs-lookup"><span data-stu-id="20c31-137">Start a job in an interactive session</span></span>

<span data-ttu-id="20c31-138">リモートコンピューターで対話型セッションを開始し、対話型セッション中にジョブを開始することができます。</span><span class="sxs-lookup"><span data-stu-id="20c31-138">You can start an interactive session with a remote computer and then start a job during the interactive session.</span></span> <span data-ttu-id="20c31-139">対話型セッションの詳細については、「about_Remote」および「」を参照してください `Enter-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="20c31-139">For more information about interactive sessions, see about_Remote, and see `Enter-PSSession`.</span></span>

<span data-ttu-id="20c31-140">対話型セッションでジョブを開始する手順は、ローカルコンピューターでバックグラウンドジョブを開始する手順とほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="20c31-140">The procedure for starting a job in an interactive session is almost identical to the procedure for starting a background job on the local computer.</span></span> <span data-ttu-id="20c31-141">ただし、すべての操作は、ローカルコンピューターではなく、リモートコンピューター上で行われます。</span><span class="sxs-lookup"><span data-stu-id="20c31-141">However, all of the operations occur on the remote computer, not the local computer.</span></span>

1. <span data-ttu-id="20c31-142">`Enter-PSSession`コマンドレットを使用して、リモートコンピューターとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="20c31-142">Use the `Enter-PSSession` cmdlet to start an interactive session with a remote computer.</span></span> <span data-ttu-id="20c31-143">の ComputerName パラメーターを使用して、 `Enter-PSSession` 対話型セッションの一時的な接続を確立できます。</span><span class="sxs-lookup"><span data-stu-id="20c31-143">You can use the ComputerName parameter of `Enter-PSSession` to establish a temporary connection for the interactive session.</span></span> <span data-ttu-id="20c31-144">または、Session パラメーターを使用して、PowerShell セッション (PSSession) で対話型セッションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="20c31-144">Or, you can use the Session parameter to run the interactive session in a PowerShell session (PSSession).</span></span>

   <span data-ttu-id="20c31-145">次のコマンドは、Server01 コンピューター上で対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="20c31-145">The following command starts an interactive session on the Server01 computer.</span></span>

   ```powershell
   C:\PS> Enter-PSSession -computername Server01
   ```

   <span data-ttu-id="20c31-146">Server01 コンピューターに接続されていることを示すために、コマンドプロンプトが変更されます。</span><span class="sxs-lookup"><span data-stu-id="20c31-146">The command prompt changes to show that you are now connected to the Server01 computer.</span></span>

   ```
   Server01\C:>
   ```

1. <span data-ttu-id="20c31-147">セッションでリモートジョブを開始するには、コマンドレットを使用し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="20c31-147">To start a remote job in the session, use the `Start-Job` cmdlet.</span></span> <span data-ttu-id="20c31-148">次のコマンドは、Server01 コンピューター上の Windows PowerShell イベントログに含まれるイベントを取得するリモートジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="20c31-148">The following command runs a remote job that gets the events in the Windows PowerShell event log on the Server01 computer.</span></span> <span data-ttu-id="20c31-149">`Start-Job`コマンドレットは、ジョブを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="20c31-149">The `Start-Job` cmdlet returns an object that represents the job.</span></span>

   <span data-ttu-id="20c31-150">このコマンドは、ジョブオブジェクトを変数に保存し `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="20c31-150">This command saves the job object in the `$job` variable.</span></span>

   ```powershell
   Server01\C:> $job = Start-Job -scriptblock {
     Get-Eventlog "Windows PowerShell"
   }
   ```

   <span data-ttu-id="20c31-151">ジョブの実行中に、対話型セッションを使用して他のコマンド (他のジョブを含む) を実行できます。</span><span class="sxs-lookup"><span data-stu-id="20c31-151">While the job runs, you can use the interactive session to run other commands, including other jobs.</span></span> <span data-ttu-id="20c31-152">ただし、ジョブが完了するまで、対話型セッションを開いたままにしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="20c31-152">However, you must keep the interactive session open until the job is completed.</span></span> <span data-ttu-id="20c31-153">セッションを終了すると、ジョブは中断され、結果は失われます。</span><span class="sxs-lookup"><span data-stu-id="20c31-153">If you end the session, the job is interrupted, and the results are lost.</span></span>

1. <span data-ttu-id="20c31-154">ジョブが完了したかどうかを確認するには、変数の値を表示する `$job` か、コマンドレットを使用してジョブを取得し `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="20c31-154">To find out if the job is complete, display the value of the `$job` variable, or use the `Get-Job` cmdlet to get the job.</span></span> <span data-ttu-id="20c31-155">次のコマンドでは、 `Get-Job` コマンドレットを使用してジョブを表示します。</span><span class="sxs-lookup"><span data-stu-id="20c31-155">The following command uses the `Get-Job` cmdlet to display the job.</span></span>

   ```powershell
   Server01\C:> Get-Job $job

   SessionId  Name  State      HasMoreData  Location   Command
   ---------  ----  -----      -----------  --------   -------
   1          Job1  Complete   True         localhost  Get-Eventlog "Windows...
   ```

   <span data-ttu-id="20c31-156">この出力は、ジョブ `Get-Job` が "localhost" コンピューター上で実行されていることを示しています。これは、ジョブがで開始され、同じコンピューター (この場合は Server01) で実行されているためです。</span><span class="sxs-lookup"><span data-stu-id="20c31-156">The `Get-Job` output shows that job is running on the "localhost" computer because the job was started on and is running on the same computer (in this case, Server01).</span></span>

1. <span data-ttu-id="20c31-157">ジョブの結果を取得するには、コマンドレットを使用し `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="20c31-157">To get the results of the job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="20c31-158">対話型セッションで結果を表示したり、リモートコンピューター上のファイルに結果を保存したりできます。</span><span class="sxs-lookup"><span data-stu-id="20c31-158">You can display the results in the interactive session or save them to a file on the remote computer.</span></span> <span data-ttu-id="20c31-159">次のコマンドは、$job 変数内のジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="20c31-159">The following command gets the results of the job in the $job variable.</span></span> <span data-ttu-id="20c31-160">このコマンドは、リダイレクト演算子 () を使用して、 `>` ジョブの結果を Server01 コンピューターの PsLog.txt ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="20c31-160">The command uses the redirection operator (`>`) to save the results of the job in the PsLog.txt file on the Server01 computer.</span></span>

   ```powershell
   Server01\C:> Receive-Job $job > c:\logs\PsLog.txt
   ```

1. <span data-ttu-id="20c31-161">対話型セッションを終了するには、 `Exit-PSSession` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="20c31-161">To end the interactive session, use the `Exit-PSSession` cmdlet.</span></span> <span data-ttu-id="20c31-162">コマンドプロンプトが変更され、ローカルコンピューターの元のセッションに戻ったことが示されます。</span><span class="sxs-lookup"><span data-stu-id="20c31-162">The command prompt changes to show that you are back in the original session on the local computer.</span></span>

   ```powershell
   Server01\C:> Exit-PSSession
   C:\PS>
   ```

1. <span data-ttu-id="20c31-163">Server01 コンピューター上のファイルの内容をいつでも表示するに `PsLog.txt` は、別の対話型セッションを開始するか、リモートコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20c31-163">To view the contents of the `PsLog.txt` file on the Server01 computer at any time, start another interactive session, or run a remote command.</span></span> <span data-ttu-id="20c31-164">この種類のコマンドは、複数のコマンドを使用してファイル内のデータを調査および管理する場合に、PSSession (固定接続) で実行することをお勧めし `PsLog.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="20c31-164">This type of command is best run in a PSSession (a persistent connection) in case you want to use several commands to investigate and manage the data in the `PsLog.txt` file.</span></span> <span data-ttu-id="20c31-165">PSSessions の詳細については、「 [about_PSSessions](about_PSSessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20c31-165">For more information about PSSessions, see [about_PSSessions](about_PSSessions.md).</span></span>

   <span data-ttu-id="20c31-166">次のコマンドは、コマンドレットを使用して、 `New-PSSession` Server01 コンピューターに接続されている **pssession** を作成し、コマンドレットを使用して `Invoke-Command` pssession 内のコマンドを実行し、 `Get-Content` ファイルの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="20c31-166">The following commands use the `New-PSSession` cmdlet to create a **PSSession** that is connected to the Server01 computer, and they use the `Invoke-Command` cmdlet to run a `Get-Content` command in the PSSession to view the contents of the file.</span></span>

   ```powershell
   $s = New-PSSession -computername Server01
   Invoke-Command -session $s -scriptblock {
     Get-Content c:\logs\pslog.txt}
   ```

### <a name="start-a-remote-job-that-returns-the-results-to-the-local-computer-asjob"></a><span data-ttu-id="20c31-167">結果をローカルコンピューター (AsJob) に返すリモートジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="20c31-167">Start a remote job that returns the results to the local computer (AsJob)</span></span>

<span data-ttu-id="20c31-168">コマンドの結果をローカルコンピューターに返すリモートコンピューターでジョブを開始するには、コマンドレットなどのコマンドレットの **AsJob** パラメーターを使用し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="20c31-168">To start a job on a remote computer that returns the command results to the local computer, use the **AsJob** parameter of a cmdlet such as the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="20c31-169">**AsJob** パラメーターを使用すると、ジョブがリモートコンピューター上で実行されている場合でも、ジョブオブジェクトは実際にはローカルコンピューター上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="20c31-169">When you use the **AsJob** parameter, the job object is actually created on the local computer even though the job runs on the remote computer.</span></span> <span data-ttu-id="20c31-170">ジョブが完了すると、結果がローカルコンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="20c31-170">When the job is completed, the results are returned to the local computer.</span></span>

<span data-ttu-id="20c31-171">ジョブの名詞を含むコマンドレット (Job コマンドレット) を使用して、任意のコマンドレットによって作成されたすべてのジョブを管理できます。</span><span class="sxs-lookup"><span data-stu-id="20c31-171">You can use the cmdlets that contain the Job noun (the Job cmdlets) to manage any job created by any cmdlet.</span></span> <span data-ttu-id="20c31-172">**AsJob** パラメーターを持つコマンドレットの多くは、PowerShell リモート処理を使用しないので、リモート処理用に構成されておらず、リモート処理の要件を満たしていないコンピューターでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="20c31-172">Many of the cmdlets that have **AsJob** parameters do not use PowerShell remoting, so you can use them even on computers that are not configured for remoting and that do not meet the requirements for remoting.</span></span>

1. <span data-ttu-id="20c31-173">次のコマンドでは、の **AsJob** パラメーターを使用して `Invoke-Command` 、Server01 コンピューター上でジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="20c31-173">The following command uses the **AsJob** parameter of `Invoke-Command` to start a job on the Server01 computer.</span></span> <span data-ttu-id="20c31-174">このジョブは、 `Get-Eventlog` システムログ内のイベントを取得するコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20c31-174">The job runs a `Get-Eventlog` command that gets the events in the System log.</span></span> <span data-ttu-id="20c31-175">JobName パラメーターを使用して、ジョブに表示名を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="20c31-175">You can use the JobName parameter to assign a display name to the job.</span></span>

   ```powershell
   Invoke-Command -computername Server01 -scriptblock {
     Get-Eventlog system} -AsJob
   ```

   <span data-ttu-id="20c31-176">コマンドの結果は、次のサンプル出力のようになります。</span><span class="sxs-lookup"><span data-stu-id="20c31-176">The results of the command resemble the following sample output.</span></span>

   ```Output
   SessionId   Name   State    HasMoreData   Location   Command
   ---------   ----   -----    -----------   --------   -------
   1           Job1   Running  True          Server01   Get-Eventlog system
   ```

   <span data-ttu-id="20c31-177">**AsJob** パラメーターが使用されている場合、はを `Invoke-Command` 返すのと同じ種類のジョブオブジェクトを返し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="20c31-177">When the **AsJob** parameter is used, `Invoke-Command` returns the same type of job object that `Start-Job` returns.</span></span> <span data-ttu-id="20c31-178">ジョブオブジェクトを変数に保存することも、コマンドを使用してジョブを取得することもでき `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="20c31-178">You can save the job object in a variable, or you can use a `Get-Job` command to get the job.</span></span>

   <span data-ttu-id="20c31-179">Location プロパティの値は、Server01 コンピューターでジョブが実行されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="20c31-179">Note that the value of the Location property shows that the job ran on the Server01 computer.</span></span>

1. <span data-ttu-id="20c31-180">コマンドレットの **AsJob** パラメーターを使用して開始されたジョブを管理するには `Invoke-Command` 、job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="20c31-180">To manage a job started by using the **AsJob** parameter of the `Invoke-Command` cmdlet, use the Job cmdlets.</span></span> <span data-ttu-id="20c31-181">リモートジョブを表すジョブオブジェクトはローカルコンピューター上にあるため、リモートコマンドを実行してジョブを管理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="20c31-181">Because the job object that represents the remote job is on the local computer, you do not need to run remote commands to manage the job.</span></span>

   <span data-ttu-id="20c31-182">ジョブが完了したかどうかを確認するには、コマンドを使用し `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="20c31-182">To determine whether the job is complete, use a `Get-Job` command.</span></span> <span data-ttu-id="20c31-183">次のコマンドは、現在のセッションで開始されたすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="20c31-183">The following command gets all of the jobs that were started in the current session.</span></span>

   ```powershell
   Get-Job
   ```

   <span data-ttu-id="20c31-184">リモートジョブが現在のセッションで開始されたため、ローカル `Get-Job` コマンドはジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="20c31-184">Because the remote job was started in the current session, a local `Get-Job` command gets the job.</span></span> <span data-ttu-id="20c31-185">ジョブオブジェクトの State プロパティは、コマンドが正常に完了したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="20c31-185">The State property of the job object shows that the command was completed successfully.</span></span>

   ```Output
   SessionId   Name   State      HasMoreData   Location   Command
   ---------   ----   -----      -----------   --------   -------
   1           Job1   Completed  True          Server01   Get-Eventlog system
   ```

1. <span data-ttu-id="20c31-186">ジョブの結果を取得するには、コマンドレットを使用し `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="20c31-186">To get the results of the job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="20c31-187">ジョブの結果は、ジョブオブジェクトが存在するコンピューターに自動的に返されるため、ローカルコマンドを使用して結果を取得でき `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="20c31-187">Because the job results are automatically returned to the computer where the job object resides, you can get the results with a local `Receive-Job` command.</span></span>

   <span data-ttu-id="20c31-188">次のコマンドでは、 `Receive-Job` コマンドレットを使用してジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="20c31-188">The following command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="20c31-189">セッション ID を使用してジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="20c31-189">It uses the session ID to identify the job.</span></span> <span data-ttu-id="20c31-190">このコマンドは、ジョブの結果を $results 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="20c31-190">This command saves the job results in the $results variable.</span></span> <span data-ttu-id="20c31-191">また、結果をファイルにリダイレクトすることもできます。</span><span class="sxs-lookup"><span data-stu-id="20c31-191">You can also redirect the results to a file.</span></span>

   ```powershell
   $results = Receive-Job -id 1
   ```

### <a name="start-a-remote-job-that-keeps-the-results-on-the-remote-computer"></a><span data-ttu-id="20c31-192">リモートコンピューターで結果を保持するリモートジョブを開始する</span><span class="sxs-lookup"><span data-stu-id="20c31-192">Start a remote job that keeps the results on the remote computer</span></span>

<span data-ttu-id="20c31-193">リモートコンピューターでコマンドの結果を保持するジョブをリモートコンピューター上で開始するには、コマンドレットを使用して `Invoke-Command` リモートコンピューターでコマンドを実行し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="20c31-193">To start a job on a remote computer that keeps the command results on the remote computer, use the `Invoke-Command` cmdlet to run a `Start-Job` command on a remote computer.</span></span> <span data-ttu-id="20c31-194">この方法を使用すると、複数のコンピューターでジョブを実行できます。</span><span class="sxs-lookup"><span data-stu-id="20c31-194">You can use this method to run jobs on multiple computers.</span></span>

<span data-ttu-id="20c31-195">コマンドをリモートで実行すると、 `Start-Job` ジョブオブジェクトがリモートコンピューター上に作成され、ジョブの結果がリモートコンピューターに保持されます。</span><span class="sxs-lookup"><span data-stu-id="20c31-195">When you run a `Start-Job` command remotely, the job object is created on the remote computer, and the job results are maintained on the remote computer.</span></span>
<span data-ttu-id="20c31-196">ジョブの観点から見ると、すべての操作はローカルです。</span><span class="sxs-lookup"><span data-stu-id="20c31-196">From the perspective of the job, all operations are local.</span></span> <span data-ttu-id="20c31-197">リモートコンピューター上のローカルジョブを管理するために、コマンドをリモートで実行しているだけです。</span><span class="sxs-lookup"><span data-stu-id="20c31-197">You are just running commands remotely to manage a local job on the remote computer.</span></span>

1. <span data-ttu-id="20c31-198">コマンドレットを使用して、 `Invoke-Command` `Start-Job` リモートコンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20c31-198">Use the `Invoke-Command` cmdlet to run a `Start-Job` command on a remote computer.</span></span>

   <span data-ttu-id="20c31-199">このコマンドには PSSession (永続的な接続) が必要です。</span><span class="sxs-lookup"><span data-stu-id="20c31-199">This command requires a PSSession (a persistent connection).</span></span> <span data-ttu-id="20c31-200">の ComputerName パラメーターを使用して `Invoke-Command` 一時的な接続を確立すると、 `Invoke-Command` ジョブオブジェクトが返されたときにコマンドは完了したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="20c31-200">If you use the ComputerName parameter of `Invoke-Command` to establish a temporary connection, the `Invoke-Command` command is considered to be complete when the job object is returned.</span></span> <span data-ttu-id="20c31-201">その結果、一時的な接続は閉じられ、ジョブは取り消されます。</span><span class="sxs-lookup"><span data-stu-id="20c31-201">As a result, the temporary connection is closed, and the job is canceled.</span></span>

   <span data-ttu-id="20c31-202">次のコマンドでは、コマンドレットを使用して、 `New-PSSession` Server01 コンピューターに接続されている PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="20c31-202">The following command uses the `New-PSSession` cmdlet to create a PSSession that is connected to the Server01 computer.</span></span> <span data-ttu-id="20c31-203">このコマンドは、PSSession を変数に保存し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="20c31-203">The command saves the PSSession in the `$s` variable.</span></span>

   ```powershell
   $s = New-PSSession -computername Server01
   ```

   <span data-ttu-id="20c31-204">次のコマンドは、コマンドレットを使用して `Invoke-Command` `Start-Job` PSSession 内のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20c31-204">The next command uses the `Invoke-Command` cmdlet to run a `Start-Job` command in the PSSession.</span></span> <span data-ttu-id="20c31-205">`Start-Job`コマンドとコマンドは、 `Get-Eventlog` 中かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="20c31-205">The `Start-Job` command and the `Get-Eventlog` command are enclosed in braces.</span></span>

   ```powershell
   Invoke-Command -session $s -scriptblock {
     Start-Job -scriptblock {Get-Eventlog system}}
   ```

   <span data-ttu-id="20c31-206">結果は次のサンプル出力のようになります。</span><span class="sxs-lookup"><span data-stu-id="20c31-206">The results resemble the following sample output.</span></span>

   ```Output
   Id       Name    State      HasMoreData     Location   Command
   --       ----    -----      -----------     --------   -------
   2        Job2    Running    True            Localhost  Get-Eventlog system
   ```

   <span data-ttu-id="20c31-207">コマンドをリモートで実行すると `Start-Job` 、に `Invoke-Command` よって返されるのと同じ種類のジョブオブジェクトが返さ `Start-Job` れます。</span><span class="sxs-lookup"><span data-stu-id="20c31-207">When you run a `Start-Job` command remotely, `Invoke-Command` returns the same type of job object that `Start-Job` returns.</span></span> <span data-ttu-id="20c31-208">ジョブオブジェクトを変数に保存することも、コマンドを使用してジョブを取得することもでき `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="20c31-208">You can save the job object in a variable, or you can use a `Get-Job` command to get the job.</span></span>

   <span data-ttu-id="20c31-209">**Location** プロパティの値は、ジョブが Server01 コンピューター上で実行された場合でも、ローカルコンピューター上でジョブが実行されたことを示しています。これは、"LocalHost" と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="20c31-209">Note that the value of the **Location** property shows that the job ran on the local computer, known as "LocalHost", even though the job ran on the Server01 computer.</span></span> <span data-ttu-id="20c31-210">ジョブオブジェクトは Server01 コンピューター上に作成され、ジョブは同じコンピューター上で実行されるため、ローカルのバックグラウンドジョブと見なされます。</span><span class="sxs-lookup"><span data-stu-id="20c31-210">Because the job object is created on the Server01 computer and the job runs on the same computer, it is considered to be a local background job.</span></span>

1. <span data-ttu-id="20c31-211">リモートジョブを管理するには、 **job** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="20c31-211">To manage a remote job, use the **Job** cmdlets.</span></span> <span data-ttu-id="20c31-212">ジョブオブジェクトはリモートコンピューター上にあるため、リモートコマンドを実行して、ジョブの結果を取得、停止、待機、または取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20c31-212">Because the job object is on the remote computer, you need to run remote commands to get, stop, wait for, or retrieve the job results.</span></span>

   <span data-ttu-id="20c31-213">ジョブが完了したかどうかを確認するには、コマンドを使用して、 `Invoke-Command` `Get-Job` Server01 コンピューターに接続されている PSSession でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20c31-213">To see if the job is complete, use an `Invoke-Command` command to run a `Get-Job` command in the PSSession that is connected to the Server01 computer.</span></span>

   ```powershell
   Invoke-Command -session $s -scriptblock {Get-Job}
   ```

   <span data-ttu-id="20c31-214">このコマンドによって返されるのは、ジョブ オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="20c31-214">The command returns a job object.</span></span> <span data-ttu-id="20c31-215">ジョブオブジェクトの **State** プロパティは、コマンドが正常に完了したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="20c31-215">The **State** property of the job object shows that the command was completed successfully.</span></span>

   ```Output
   SessionId   Name  State      HasMoreData   Location   Command
   ---------   ----  -----      -----------   --------   -------
   2           Job2  Completed  True          LocalHost   Get-Eventlog system
   ```

1. <span data-ttu-id="20c31-216">ジョブの結果を取得するには、コマンドレットを使用して、 `Invoke-Command` `Receive-Job` Server01 コンピューターに接続されている PSSession でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20c31-216">To get the results of the job, use the `Invoke-Command` cmdlet to run a `Receive-Job` command in the PSSession that is connected to the Server01 computer.</span></span>

   <span data-ttu-id="20c31-217">次のコマンドでは、 `Receive-Job` コマンドレットを使用してジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="20c31-217">The following command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="20c31-218">セッション ID を使用してジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="20c31-218">It uses the session ID to identify the job.</span></span> <span data-ttu-id="20c31-219">このコマンドは、ジョブの結果を変数に保存し `$results` ます。</span><span class="sxs-lookup"><span data-stu-id="20c31-219">This command saves the job results in the `$results` variable.</span></span> <span data-ttu-id="20c31-220">この例では、の Keep パラメーターを使用して、 `Receive-Job` リモートコンピューター上のジョブキャッシュに結果を保持します。</span><span class="sxs-lookup"><span data-stu-id="20c31-220">It uses the Keep parameter of `Receive-Job` to keep the result in the job cache on the remote computer.</span></span>

   ```powershell
   $results = Invoke-Command -session $s -scriptblock {
     Receive-Job -SessionId 2 -Keep
   }
   ```

   <span data-ttu-id="20c31-221">また、ローカルコンピューターまたはリモートコンピューター上のファイルに結果をリダイレクトすることもできます。</span><span class="sxs-lookup"><span data-stu-id="20c31-221">You can also redirect the results to a file on the local or remote computer.</span></span>
   <span data-ttu-id="20c31-222">次のコマンドは、リダイレクト演算子を使用して、Server01 コンピューター上のファイルに結果を保存します。</span><span class="sxs-lookup"><span data-stu-id="20c31-222">The following command uses a redirection operator to save the results in a file on the Server01 computer.</span></span>

   ```powershell
   Invoke-Command -session $s -command {
     Receive-Job -SessionId 2 > c:\logs\pslog.txt
   }
   ```

## <a name="how-to-run-as-a-detached-process"></a><span data-ttu-id="20c31-223">デタッチされたプロセスとして実行する方法</span><span class="sxs-lookup"><span data-stu-id="20c31-223">How to run as a detached process</span></span>

<span data-ttu-id="20c31-224">既に説明したように、親セッションが終了すると、実行中のすべての子ジョブが子プロセスと共に終了します。</span><span class="sxs-lookup"><span data-stu-id="20c31-224">As previously mentioned, when the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span> <span data-ttu-id="20c31-225">ローカルコンピューターでリモート処理を使用して、現在の PowerShell セッションにアタッチされていないジョブを実行できます。</span><span class="sxs-lookup"><span data-stu-id="20c31-225">You can use remoting on the local machine to run jobs that are not attached to the current PowerShell session.</span></span>

<span data-ttu-id="20c31-226">ローカルコンピューターで新しい PowerShell セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="20c31-226">Create a new PowerShell session on the local machine.</span></span> <span data-ttu-id="20c31-227">`Invoke-Command`このセッションでジョブを開始するために使用する。</span><span class="sxs-lookup"><span data-stu-id="20c31-227">The use `Invoke-Command` to start a job in this session.</span></span> <span data-ttu-id="20c31-228">`Invoke-Command` リモートセッションを切断し、親セッションを終了することができます。</span><span class="sxs-lookup"><span data-stu-id="20c31-228">`Invoke-Command` allows you to disconnect a remote session and terminate the parent session.</span></span> <span data-ttu-id="20c31-229">後で、新しい PowerShell セッションを開始し、以前に切断されたセッションに接続して、ジョブの監視を再開できます。</span><span class="sxs-lookup"><span data-stu-id="20c31-229">Later, you can start a new PowerShell session and connect to the previously disconnected session to resume monitoring the job.</span></span> <span data-ttu-id="20c31-230">ただし、元の PowerShell セッションに返されたデータは、そのセッションが終了したときに失われます。</span><span class="sxs-lookup"><span data-stu-id="20c31-230">However, any data that was returned to the original PowerShell session is lost when that session is terminated.</span></span> <span data-ttu-id="20c31-231">再接続時に返されるのは、切断後に生成される新しいデータオブジェクトだけです。</span><span class="sxs-lookup"><span data-stu-id="20c31-231">Only new data objects generated after the disconnect are returned when re-connected.</span></span>

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

<span data-ttu-id="20c31-232">この例では、ジョブは引き続き親 PowerShell セッションにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="20c31-232">For this example, the jobs are still attached to a parent PowerShell session.</span></span>
<span data-ttu-id="20c31-233">ただし、親セッションは、が実行された元の PowerShell セッションではありません `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="20c31-233">However, the parent session is not the original PowerShell session where `Invoke-Command` was run.</span></span>

## <a name="see-also"></a><span data-ttu-id="20c31-234">関連項目</span><span class="sxs-lookup"><span data-stu-id="20c31-234">See also</span></span>

- [<span data-ttu-id="20c31-235">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="20c31-235">about_Jobs</span></span>](about_Jobs.md)
- [<span data-ttu-id="20c31-236">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="20c31-236">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="20c31-237">about_Remote</span><span class="sxs-lookup"><span data-stu-id="20c31-237">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="20c31-238">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="20c31-238">about_Remote_Variables</span></span>](about_Remote_Variables.md)
- [<span data-ttu-id="20c31-239">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="20c31-239">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
- [<span data-ttu-id="20c31-240">Start-Job</span><span class="sxs-lookup"><span data-stu-id="20c31-240">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="20c31-241">Get-Job</span><span class="sxs-lookup"><span data-stu-id="20c31-241">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="20c31-242">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="20c31-242">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="20c31-243">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="20c31-243">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="20c31-244">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="20c31-244">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="20c31-245">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="20c31-245">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
- [<span data-ttu-id="20c31-246">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="20c31-246">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)
- [<span data-ttu-id="20c31-247">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="20c31-247">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)
