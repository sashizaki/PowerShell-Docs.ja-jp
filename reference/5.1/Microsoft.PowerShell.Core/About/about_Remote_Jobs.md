---
description: リモートコンピューターでバックグラウンドジョブを実行する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_jobs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Jobs
ms.openlocfilehash: 5e74de2684d65a66025c4f2c815e9130dfe57e05
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223288"
---
# <a name="about-remote-jobs"></a><span data-ttu-id="6eab2-104">リモートジョブについて</span><span class="sxs-lookup"><span data-stu-id="6eab2-104">About Remote Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="6eab2-105">概要</span><span class="sxs-lookup"><span data-stu-id="6eab2-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="6eab2-106">リモートコンピューターでバックグラウンドジョブを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-106">Describes how to run background jobs on remote computers.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="6eab2-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="6eab2-107">DETAILED DESCRIPTION</span></span>

<span data-ttu-id="6eab2-108">バックグラウンドジョブは、現在のセッションと対話せずに非同期的に実行されるコマンドです。</span><span class="sxs-lookup"><span data-stu-id="6eab2-108">A background job is a command that runs asynchronously without interacting with the current session.</span></span> <span data-ttu-id="6eab2-109">コマンドプロンプトはすぐに返され、ジョブの実行中に引き続きセッションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-109">The command prompt returns immediately, and you can continue to use the session while the job runs.</span></span>

<span data-ttu-id="6eab2-110">既定では、バックグラウンドジョブはローカルコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-110">By default, background jobs run on the local computer.</span></span> <span data-ttu-id="6eab2-111">ただし、リモートコンピューターでバックグラウンドジョブを実行するには、いくつかの異なる手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-111">However, you can use several different procedures to run background jobs on remote computers.</span></span>

<span data-ttu-id="6eab2-112">このトピックでは、リモートコンピューターでバックグラウンドジョブを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-112">This topic explains how to run a background job on a remote computer.</span></span> <span data-ttu-id="6eab2-113">ローカルコンピューターでバックグラウンドジョブを実行する方法の詳細については、「 [about_Jobs](about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6eab2-113">For information about how to run background jobs on a local computer, see [about_Jobs](about_Jobs.md).</span></span> <span data-ttu-id="6eab2-114">バックグラウンドジョブの詳細については、「 [about_Job_Details](about_Job_Details.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6eab2-114">For more information about background jobs, see [about_Job_Details](about_Job_Details.md).</span></span>

## <a name="remote-background-jobs"></a><span data-ttu-id="6eab2-115">リモートバックグラウンドジョブ</span><span class="sxs-lookup"><span data-stu-id="6eab2-115">REMOTE BACKGROUND JOBS</span></span>

<span data-ttu-id="6eab2-116">リモートコンピューターでは、3つの異なる方法を使用してバックグラウンドジョブを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-116">You can run background jobs on remote computers by using three different methods.</span></span>

- <span data-ttu-id="6eab2-117">リモートコンピューターとの対話型セッションを開始し、対話型セッションでジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-117">Start an interactive session with a remote computer, and start a job in the interactive session.</span></span> <span data-ttu-id="6eab2-118">これらの手順はローカルジョブを実行するのと同じですが、すべての操作はリモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-118">The procedures are the same as running a local job, although all actions are performed on the remote computer.</span></span>

- <span data-ttu-id="6eab2-119">リモートコンピューターでバックグラウンドジョブを実行し、その結果をローカルコンピューターに返します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-119">Run a background job on a remote computer that returns its results to the local computer.</span></span> <span data-ttu-id="6eab2-120">この方法は、バックグラウンドジョブの結果を収集し、ローカルコンピューター上の中央の場所に保持する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-120">Use this method when you want to collect the results of background jobs and maintain them in a central location on the local computer.</span></span>

- <span data-ttu-id="6eab2-121">リモートコンピューター上で結果が保持されているリモートコンピューターでバックグラウンドジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-121">Run a background job on a remote computer that maintains its results on the remote computer.</span></span> <span data-ttu-id="6eab2-122">この方法は、ジョブデータを元のコンピューターでより安全に維持する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-122">Use this method when the job data is more securely maintained on the originating computer.</span></span>

### <a name="start-a-background-job-in-an-interactive-session"></a><span data-ttu-id="6eab2-123">対話型セッションでバックグラウンドジョブを開始する</span><span class="sxs-lookup"><span data-stu-id="6eab2-123">START A BACKGROUND JOB IN AN INTERACTIVE SESSION</span></span>

<span data-ttu-id="6eab2-124">リモートコンピューターで対話型セッションを開始し、対話型セッション中にバックグラウンドジョブを開始することができます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-124">You can start an interactive session with a remote computer and then start a background job during the interactive session.</span></span> <span data-ttu-id="6eab2-125">対話型セッションの詳細については、「about_Remote」および「Enter-PSSession」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6eab2-125">For more information about interactive sessions, see about_Remote, and see Enter-PSSession.</span></span>

<span data-ttu-id="6eab2-126">対話型セッションでバックグラウンドジョブを開始する手順は、ローカルコンピューターでバックグラウンドジョブを開始する手順とほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="6eab2-126">The procedure for starting a background job in an interactive session is almost identical to the procedure for starting a background job on the local computer.</span></span> <span data-ttu-id="6eab2-127">ただし、すべての操作は、ローカルコンピューターではなく、リモートコンピューター上で行われます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-127">However, all of the operations occur on the remote computer, not the local computer.</span></span>

#### <a name="step-1-enter-pssession"></a><span data-ttu-id="6eab2-128">手順 1:-PSSESSION を入力する</span><span class="sxs-lookup"><span data-stu-id="6eab2-128">STEP 1: ENTER-PSSESSION</span></span>

<span data-ttu-id="6eab2-129">リモートコンピューターとの対話型セッションを開始するには、Enter-PSSession コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-129">Use the Enter-PSSession cmdlet to start an interactive session with a remote computer.</span></span> <span data-ttu-id="6eab2-130">Enter-PSSession の ComputerName パラメーターを使用して、対話型セッションの一時的な接続を確立できます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-130">You can use the ComputerName parameter of Enter-PSSession to establish a temporary connection for the interactive session.</span></span> <span data-ttu-id="6eab2-131">または、セッションパラメーターを使用して、Windows PowerShell セッション (PSSession) で対話型セッションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-131">Or, you can use the Session parameter to run the interactive session in a Windows PowerShell session (PSSession).</span></span>

<span data-ttu-id="6eab2-132">次のコマンドは、Server01 コンピューター上で対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-132">The following command starts an interactive session on the Server01 computer.</span></span>

```powershell
C:\PS> Enter-PSSession -computername Server01
```

<span data-ttu-id="6eab2-133">Server01 コンピューターに接続されていることを示すために、コマンドプロンプトが変更されます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-133">The command prompt changes to show that you are now connected to the Server01 computer.</span></span>

```
Server01\C:>
```

#### <a name="step-2-start-job"></a><span data-ttu-id="6eab2-134">手順 2: ジョブの開始</span><span class="sxs-lookup"><span data-stu-id="6eab2-134">STEP 2: START-JOB</span></span>

<span data-ttu-id="6eab2-135">セッションでバックグラウンドジョブを開始するには、Start-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-135">To start a background job in the session, use the Start-Job cmdlet.</span></span>

<span data-ttu-id="6eab2-136">次のコマンドは、Server01 コンピューター上の Windows PowerShell イベントログ内のイベントを取得するバックグラウンドジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-136">The following command runs a background job that gets the events in the Windows PowerShell event log on the Server01 computer.</span></span> <span data-ttu-id="6eab2-137">Start-Job コマンドレットは、ジョブを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-137">The Start-Job cmdlet returns an object that represents the job.</span></span>

<span data-ttu-id="6eab2-138">このコマンドは、ジョブオブジェクトをジョブ変数に保存し \$ ます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-138">This command saves the job object in the \$job variable.</span></span>

```powershell
Server01\C:> $job = start-job -scriptblock {
  get-eventlog "Windows PowerShell"
}
```

<span data-ttu-id="6eab2-139">ジョブの実行中に、対話型セッションを使用して他のコマンド (他のバックグラウンドジョブなど) を実行できます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-139">While the job runs, you can use the interactive session to run other commands, including other background jobs.</span></span> <span data-ttu-id="6eab2-140">ただし、ジョブが完了するまで、対話型セッションを開いたままにしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="6eab2-140">However, you must keep the interactive session open until the job is completed.</span></span> <span data-ttu-id="6eab2-141">セッションを終了すると、ジョブは中断され、結果は失われます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-141">If you end the session, the job is interrupted, and the results are lost.</span></span>

#### <a name="step-3-get-job"></a><span data-ttu-id="6eab2-142">手順 3: ジョブの取得</span><span class="sxs-lookup"><span data-stu-id="6eab2-142">STEP 3: GET-JOB</span></span>

<span data-ttu-id="6eab2-143">ジョブが完了したかどうかを確認するには、ジョブ変数の値を表示する \$ か、Get-Job コマンドレットを使用してジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-143">To find out if the job is complete, display the value of the \$job variable, or use the Get-Job cmdlet to get the job.</span></span> <span data-ttu-id="6eab2-144">次のコマンドでは、Get-Job コマンドレットを使用してジョブを表示します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-144">The following command uses the Get-Job cmdlet to display the job.</span></span>

```powershell
Server01\C:> get-job $job

SessionId  Name  State      HasMoreData  Location   Command
---------  ----  -----      -----------  --------   -------
1          Job1  Complete   True         localhost  get-eventlog "Windows...
```

<span data-ttu-id="6eab2-145">Get-Job 出力は、ジョブが "localhost" コンピューター上で実行されていることを示しています。これは、ジョブがで開始され、同じコンピューター (この場合は Server01) で実行されているためです。</span><span class="sxs-lookup"><span data-stu-id="6eab2-145">The Get-Job output shows that job is running on the "localhost" computer because the job was started on and is running on the same computer (in this case, Server01).</span></span>

#### <a name="step-4-receive-job"></a><span data-ttu-id="6eab2-146">手順 4: 受信-ジョブ</span><span class="sxs-lookup"><span data-stu-id="6eab2-146">STEP 4: RECEIVE-JOB</span></span>

<span data-ttu-id="6eab2-147">ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-147">To get the results of the job, use the Receive-Job cmdlet.</span></span> <span data-ttu-id="6eab2-148">対話型セッションで結果を表示したり、リモートコンピューター上のファイルに結果を保存したりできます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-148">You can display the results in the interactive session or save them to a file on the remote computer.</span></span> <span data-ttu-id="6eab2-149">次のコマンドは、$job 変数内のジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-149">The following command gets the results of the job in the $job variable.</span></span> <span data-ttu-id="6eab2-150">このコマンドは、リダイレクト演算子 (>) を使用して、ジョブの結果を Server01 コンピューター上の PsLog.txt ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-150">The command uses the redirection operator (>) to save the results of the job in the PsLog.txt file on the Server01 computer.</span></span>

```powershell
Server01\C:> receive-job $job > c:\logs\PsLog.txt
```

#### <a name="step-5-exit-pssession"></a><span data-ttu-id="6eab2-151">手順 5: PSSESSION を終了する</span><span class="sxs-lookup"><span data-stu-id="6eab2-151">STEP 5: EXIT-PSSESSION</span></span>

<span data-ttu-id="6eab2-152">対話型セッションを終了するには、Exit-PSSession コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-152">To end the interactive session, use the Exit-PSSession cmdlet.</span></span> <span data-ttu-id="6eab2-153">コマンドプロンプトが変更され、ローカルコンピューターの元のセッションに戻ったことが示されます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-153">The command prompt changes to show that you are back in the original session on the local computer.</span></span>

```powershell
Server01\C:> Exit-PSSession
C:\PS>
```

#### <a name="step-6-invoke-command-get-content"></a><span data-ttu-id="6eab2-154">手順 6: INVOKE コマンド: GET CONTENT</span><span class="sxs-lookup"><span data-stu-id="6eab2-154">STEP 6: INVOKE-COMMAND: GET-CONTENT</span></span>

<span data-ttu-id="6eab2-155">Server01 コンピューター上の PsLog.txt ファイルの内容をいつでも表示するには、別の対話型セッションを開始するか、リモートコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-155">To view the contents of the PsLog.txt file on the Server01 computer at any time, start another interactive session, or run a remote command.</span></span> <span data-ttu-id="6eab2-156">この種類のコマンドは、複数のコマンドを使用して PsLog.txt ファイル内のデータを調査および管理する場合に、PSSession (固定接続) で実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6eab2-156">This type of command is best run in a PSSession (a persistent connection) in case you want to use several commands to investigate and manage the data in the PsLog.txt file.</span></span> <span data-ttu-id="6eab2-157">PSSessions の詳細については、「about_PSSessions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6eab2-157">For more information about PSSessions, see about_PSSessions.</span></span>

<span data-ttu-id="6eab2-158">次のコマンドは、New-PSSession コマンドレットを使用して、Server01 コンピューターに接続されている PSSession を作成し、Invoke-Command コマンドレットを使用して PSSession の Get-Content コマンドを実行し、ファイルの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-158">The following commands use the New-PSSession cmdlet to create a PSSession that is connected to the Server01 computer, and they use the Invoke-Command cmdlet to run a Get-Content command in the PSSession to view the contents of the file.</span></span>

```powershell
$s = new-pssession -computername Server01
invoke-command -session $s -scriptblock {
  get-content c:\logs\pslog.txt}
```

### <a name="start-a-remote-job-that-returns-the-results-to-the-local-computer-asjob"></a><span data-ttu-id="6eab2-159">結果をローカルコンピューター ASJOB に返すリモートジョブを開始します。 \(\)</span><span class="sxs-lookup"><span data-stu-id="6eab2-159">START A REMOTE JOB THAT RETURNS THE RESULTS TO THE LOCAL COMPUTER \(ASJOB\)</span></span>

<span data-ttu-id="6eab2-160">コマンドの結果をローカルコンピューターに返すリモートコンピューターでバックグラウンドジョブを開始するには、Invoke-Command コマンドレットなどのコマンドレットの AsJob パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-160">To start a background job on a remote computer that returns the command results to the local computer, use the AsJob parameter of a cmdlet such as the Invoke-Command cmdlet.</span></span>

<span data-ttu-id="6eab2-161">AsJob パラメーターを使用すると、ジョブがリモートコンピューター上で実行されている場合でも、ジョブオブジェクトは実際にはローカルコンピューター上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-161">When you use the AsJob parameter, the job object is actually created on the local computer even though the job runs on the remote computer.</span></span> <span data-ttu-id="6eab2-162">ジョブが完了すると、結果がローカルコンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-162">When the job is completed, the results are returned to the local computer.</span></span>

<span data-ttu-id="6eab2-163">ジョブの名詞を含むコマンドレット (Job コマンドレット) を使用して、任意のコマンドレットによって作成されたすべてのジョブを管理できます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-163">You can use the cmdlets that contain the Job noun (the Job cmdlets) to manage any job created by any cmdlet.</span></span> <span data-ttu-id="6eab2-164">AsJob パラメーターを持つコマンドレットの多くは、Windows PowerShell リモート処理を使用しないので、リモート処理用に構成されておらず、リモート処理の要件を満たしていないコンピューターでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-164">Many of the cmdlets that have AsJob parameters do not use Windows PowerShell remoting, so you can use them even on computers that are not configured for remoting and that do not meet the requirements for remoting.</span></span>

#### <a name="step-1-invoke-command--asjob"></a><span data-ttu-id="6eab2-165">手順 1: INVOKE-コマンド-ASJOB</span><span class="sxs-lookup"><span data-stu-id="6eab2-165">STEP 1: INVOKE-COMMAND -ASJOB</span></span>

<span data-ttu-id="6eab2-166">次のコマンドでは、Invoke-Command の AsJob パラメーターを使用して、Server01 コンピューター上でバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-166">The following command uses the AsJob parameter of Invoke-Command to start a background job on the Server01 computer.</span></span> <span data-ttu-id="6eab2-167">このジョブは、システム ログのイベントを取得する Get-Eventlog コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-167">The job runs a Get-Eventlog command that gets the events in the System log.</span></span> <span data-ttu-id="6eab2-168">JobName パラメーターを使用して、ジョブに表示名を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-168">You can use the JobName parameter to assign a display name to the job.</span></span>

```powershell
invoke-command -computername Server01 -scriptblock {
  get-eventlog system} -asjob
```

<span data-ttu-id="6eab2-169">コマンドの結果は、次のサンプル出力のようになります。</span><span class="sxs-lookup"><span data-stu-id="6eab2-169">The results of the command resemble the following sample output.</span></span>

```Output
SessionId   Name   State    HasMoreData   Location   Command
---------   ----   -----    -----------   --------   -------
1           Job1   Running  True          Server01   get-eventlog system
```

<span data-ttu-id="6eab2-170">AsJob パラメーターを使用すると、Invoke-Command は、Start-Job が返すのと同じ種類のジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-170">When the AsJob parameter is used, Invoke-Command returns the same type of job object that Start-Job returns.</span></span> <span data-ttu-id="6eab2-171">ジョブオブジェクトを変数に保存することも、Get-Job コマンドを使用してジョブを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-171">You can save the job object in a variable, or you can use a Get-Job command to get the job.</span></span>

<span data-ttu-id="6eab2-172">Location プロパティの値は、Server01 コンピューターでジョブが実行されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="6eab2-172">Note that the value of the Location property shows that the job ran on the Server01 computer.</span></span>

#### <a name="step-2-get-job"></a><span data-ttu-id="6eab2-173">手順 2: ジョブの取得</span><span class="sxs-lookup"><span data-stu-id="6eab2-173">STEP 2: GET-JOB</span></span>

<span data-ttu-id="6eab2-174">Invoke-Command コマンドレットの AsJob パラメーターを使用して開始されたジョブを管理するには、Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-174">To manage a job started by using the AsJob parameter of the Invoke-Command cmdlet, use the Job cmdlets.</span></span> <span data-ttu-id="6eab2-175">リモートジョブを表すジョブオブジェクトはローカルコンピューター上にあるため、リモートコマンドを実行してジョブを管理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6eab2-175">Because the job object that represents the remote job is on the local computer, you do not need to run remote commands to manage the job.</span></span>

<span data-ttu-id="6eab2-176">ジョブが完了したかどうかを確認するには、Get-Job コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-176">To determine whether the job is complete, use a Get-Job command.</span></span> <span data-ttu-id="6eab2-177">次のコマンドは、現在のセッションで開始されたすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-177">The following command gets all of the jobs that were started in the current session.</span></span>

```powershell
get-job
```

<span data-ttu-id="6eab2-178">リモートジョブが現在のセッションで開始されたため、ローカル Get-Job コマンドはジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-178">Because the remote job was started in the current session, a local Get-Job command gets the job.</span></span> <span data-ttu-id="6eab2-179">ジョブオブジェクトの State プロパティは、コマンドが正常に完了したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="6eab2-179">The State property of the job object shows that the command was completed successfully.</span></span>

```Output
SessionId   Name   State      HasMoreData   Location   Command
---------   ----   -----      -----------   --------   -------
1           Job1   Completed  True          Server01   get-eventlog system
```

#### <a name="step-3-receive-job"></a><span data-ttu-id="6eab2-180">手順 3: 受信-ジョブ</span><span class="sxs-lookup"><span data-stu-id="6eab2-180">STEP 3: RECEIVE-JOB</span></span>

<span data-ttu-id="6eab2-181">ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-181">To get the results of the job, use the Receive-Job cmdlet.</span></span> <span data-ttu-id="6eab2-182">ジョブの結果は、ジョブオブジェクトが存在するコンピュータに自動的に返されるため、ローカルの Receive-Job コマンドを使用して結果を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-182">Because the job results are automatically returned to the computer where the job object resides, you can get the results with a local Receive-Job command.</span></span>

<span data-ttu-id="6eab2-183">次のコマンドでは、Receive-Job コマンドレットを使用して、ジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-183">The following command uses the Receive-Job cmdlet to get the results of the job.</span></span> <span data-ttu-id="6eab2-184">セッション ID を使用してジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-184">It uses the session ID to identify the job.</span></span> <span data-ttu-id="6eab2-185">このコマンドは、ジョブの結果を $results 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-185">This command saves the job results in the $results variable.</span></span> <span data-ttu-id="6eab2-186">また、結果をファイルにリダイレクトすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-186">You can also redirect the results to a file.</span></span>

```powershell
$results = receive-job -id 1
```

### <a name="start-a-remote-job-that-keeps-the-results-on-the-remote-computer"></a><span data-ttu-id="6eab2-187">リモートコンピューターで結果を保持するリモートジョブを開始する</span><span class="sxs-lookup"><span data-stu-id="6eab2-187">START A REMOTE JOB THAT KEEPS THE RESULTS ON THE REMOTE COMPUTER</span></span>

<span data-ttu-id="6eab2-188">リモートコンピューターでコマンドの結果を保持するバックグラウンドジョブをリモートコンピューターで開始するには、Invoke-Command コマンドレットを使用して、リモートコンピューターで Start-Job コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-188">To start a background job on a remote computer that keeps the command results on the remote computer, use the Invoke-Command cmdlet to run a Start-Job command on a remote computer.</span></span> <span data-ttu-id="6eab2-189">この方法を使用すると、複数のコンピューターでバックグラウンドジョブを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-189">You can use this method to run background jobs on multiple computers.</span></span>

<span data-ttu-id="6eab2-190">Start-Job コマンドをリモートで実行すると、ジョブオブジェクトがリモートコンピューター上に作成され、ジョブの結果がリモートコンピューターに保持されます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-190">When you run a Start-Job command remotely, the job object is created on the remote computer, and the job results are maintained on the remote computer.</span></span>
<span data-ttu-id="6eab2-191">ジョブの観点から見ると、すべての操作はローカルです。</span><span class="sxs-lookup"><span data-stu-id="6eab2-191">From the perspective of the job, all operations are local.</span></span> <span data-ttu-id="6eab2-192">リモートコンピューター上のローカルジョブを管理するために、コマンドをリモートで実行しているだけです。</span><span class="sxs-lookup"><span data-stu-id="6eab2-192">You are just running commands remotely to manage a local job on the remote computer.</span></span>

#### <a name="step-1-invoke-command-start-job"></a><span data-ttu-id="6eab2-193">手順 1: コマンドの起動-ジョブ</span><span class="sxs-lookup"><span data-stu-id="6eab2-193">STEP 1: INVOKE-COMMAND START-JOB</span></span>

<span data-ttu-id="6eab2-194">Invoke-Command コマンドレットを使用して、リモートコンピューターで Start-Job コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-194">Use the Invoke-Command cmdlet to run a Start-Job command on a remote computer.</span></span>

<span data-ttu-id="6eab2-195">このコマンドには PSSession (永続的な接続) が必要です。</span><span class="sxs-lookup"><span data-stu-id="6eab2-195">This command requires a PSSession (a persistent connection).</span></span> <span data-ttu-id="6eab2-196">Invoke-Command の ComputerName パラメーターを使用して一時的な接続を確立した場合、ジョブオブジェクトが返されると、Invoke-Command コマンドは完了したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-196">If you use the ComputerName parameter of Invoke-Command to establish a temporary connection, the Invoke-Command command is considered to be complete when the job object is returned.</span></span> <span data-ttu-id="6eab2-197">その結果、一時的な接続は閉じられ、ジョブは取り消されます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-197">As a result, the temporary connection is closed, and the job is canceled.</span></span>

<span data-ttu-id="6eab2-198">次のコマンドは、New-PSSession コマンドレットを使用して、Server01 コンピューターに接続されている PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-198">The following command uses the New-PSSession cmdlet to create a PSSession that is connected to the Server01 computer.</span></span> <span data-ttu-id="6eab2-199">このコマンドは、PSSession を s 変数に保存し \$ ます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-199">The command saves the PSSession in the \$s variable.</span></span>

```powershell
$s = new-pssession -computername Server01
```

<span data-ttu-id="6eab2-200">次のコマンドは、Invoke-Command コマンドレットを使用して、PSSession で Start-Job コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-200">The next command uses the Invoke-Command cmdlet to run a Start-Job command in the PSSession.</span></span> <span data-ttu-id="6eab2-201">Start-Job コマンドと Get-Eventlog コマンドは、中かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="6eab2-201">The Start-Job command and the Get-Eventlog command are enclosed in braces.</span></span>

```powershell
invoke-command -session $s -scriptblock {
  start-job -scriptblock {get-eventlog system}}
```

<span data-ttu-id="6eab2-202">結果は次のサンプル出力のようになります。</span><span class="sxs-lookup"><span data-stu-id="6eab2-202">The results resemble the following sample output.</span></span>

```Output
Id       Name    State      HasMoreData     Location   Command
--       ----    -----      -----------     --------   -------
2        Job2    Running    True            Localhost  get-eventlog system
```

<span data-ttu-id="6eab2-203">Start-Job コマンドをリモートで実行すると、Invoke-Command によっ Start-Job て返されるのと同じ種類のジョブオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-203">When you run a Start-Job command remotely, Invoke-Command returns the same type of job object that Start-Job returns.</span></span> <span data-ttu-id="6eab2-204">ジョブオブジェクトを変数に保存することも、Get-Job コマンドを使用してジョブを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-204">You can save the job object in a variable, or you can use a Get-Job command to get the job.</span></span>

<span data-ttu-id="6eab2-205">Location プロパティの値は、ジョブが Server01 コンピューター上で実行された場合でも、ローカルコンピューター上でジョブが実行されたことを示しています。これは、"LocalHost" と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="6eab2-205">Note that the value of the Location property shows that the job ran on the local computer, known as "LocalHost", even though the job ran on the Server01 computer.</span></span> <span data-ttu-id="6eab2-206">ジョブオブジェクトは Server01 コンピューター上に作成され、ジョブは同じコンピューター上で実行されるため、ローカルのバックグラウンドジョブと見なされます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-206">Because the job object is created on the Server01 computer and the job runs on the same computer, it is considered to be a local background job.</span></span>

#### <a name="step-2-invoke-command-get-job"></a><span data-ttu-id="6eab2-207">手順 2: コマンドの取得-ジョブ</span><span class="sxs-lookup"><span data-stu-id="6eab2-207">STEP 2: INVOKE-COMMAND GET-JOB</span></span>

<span data-ttu-id="6eab2-208">リモートのバックグラウンドジョブを管理するには、Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-208">To manage a remote background job, use the Job cmdlets.</span></span> <span data-ttu-id="6eab2-209">ジョブオブジェクトはリモートコンピューター上にあるため、リモートコマンドを実行して、ジョブの結果を取得、停止、待機、または取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6eab2-209">Because the job object is on the remote computer, you need to run remote commands to get, stop, wait for, or retrieve the job results.</span></span>

<span data-ttu-id="6eab2-210">ジョブが完了したかどうかを確認するには、Invoke-Command コマンドを使用して、Server01 コンピューターに接続されている PSSession で Get-Job コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-210">To see if the job is complete, use an Invoke-Command command to run a Get-Job command in the PSSession that is connected to the Server01 computer.</span></span>

```powershell
invoke-command -session $s -scriptblock {get-job}
```

<span data-ttu-id="6eab2-211">このコマンドによって返されるのは、ジョブ オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="6eab2-211">The command returns a job object.</span></span> <span data-ttu-id="6eab2-212">ジョブオブジェクトの State プロパティは、コマンドが正常に完了したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="6eab2-212">The State property of the job object shows that the command was completed successfully.</span></span>

```Output
SessionId   Name  State      HasMoreData   Location   Command
---------   ----  -----      -----------   --------   -------
2           Job2  Completed  True          LocalHost   get-eventlog system
```

#### <a name="step-3-invoke-command-receive-job"></a><span data-ttu-id="6eab2-213">手順 3: コマンドの受信-ジョブ</span><span class="sxs-lookup"><span data-stu-id="6eab2-213">STEP 3: INVOKE-COMMAND RECEIVE-JOB</span></span>

<span data-ttu-id="6eab2-214">ジョブの結果を取得するには、Invoke-Command コマンドレットを使用して、Server01 コンピューターに接続されている PSSession で Receive-Job コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-214">To get the results of the job, use the Invoke-Command cmdlet to run a Receive-Job command in the PSSession that is connected to the Server01 computer.</span></span>

<span data-ttu-id="6eab2-215">次のコマンドでは、Receive-Job コマンドレットを使用して、ジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-215">The following command uses the Receive-Job cmdlet to get the results of the job.</span></span> <span data-ttu-id="6eab2-216">セッション ID を使用してジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-216">It uses the session ID to identify the job.</span></span> <span data-ttu-id="6eab2-217">このコマンドは、結果変数にジョブの結果を保存し \$ ます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-217">This command saves the job results in the \$results variable.</span></span> <span data-ttu-id="6eab2-218">Receive-Job の Keep パラメーターを使用して、リモートコンピューター上のジョブキャッシュに結果を保持します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-218">It uses the Keep parameter of Receive-Job to keep the result in the job cache on the remote computer.</span></span>

```powershell
$results = invoke-command -session $s -scriptblock {
  receive-job -sessionid 2 -keep}
```

<span data-ttu-id="6eab2-219">また、ローカルコンピューターまたはリモートコンピューター上のファイルに結果をリダイレクトすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6eab2-219">You can also redirect the results to a file on the local or remote computer.</span></span>
<span data-ttu-id="6eab2-220">次のコマンドは、リダイレクト演算子を使用して、Server01 コンピューター上のファイルに結果を保存します。</span><span class="sxs-lookup"><span data-stu-id="6eab2-220">The following command uses a redirection operator to save the results in a file on the Server01 computer.</span></span>

```powershell
invoke-command -session $s -command {
  receive-job -sessionid 2 > c:\logs\pslog.txt}
```

## <a name="see-also"></a><span data-ttu-id="6eab2-221">関連項目</span><span class="sxs-lookup"><span data-stu-id="6eab2-221">SEE ALSO</span></span>

[<span data-ttu-id="6eab2-222">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="6eab2-222">about_Jobs</span></span>](about_Jobs.md)

[<span data-ttu-id="6eab2-223">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="6eab2-223">about_Job_Details</span></span>](about_Job_Details.md)

[<span data-ttu-id="6eab2-224">about_Remote</span><span class="sxs-lookup"><span data-stu-id="6eab2-224">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="6eab2-225">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="6eab2-225">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="6eab2-226">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="6eab2-226">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="6eab2-227">Start-Job</span><span class="sxs-lookup"><span data-stu-id="6eab2-227">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)

[<span data-ttu-id="6eab2-228">Get-Job</span><span class="sxs-lookup"><span data-stu-id="6eab2-228">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)

[<span data-ttu-id="6eab2-229">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="6eab2-229">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)

[<span data-ttu-id="6eab2-230">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="6eab2-230">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)

[<span data-ttu-id="6eab2-231">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="6eab2-231">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)

[<span data-ttu-id="6eab2-232">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="6eab2-232">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="6eab2-233">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="6eab2-233">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="6eab2-234">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="6eab2-234">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)
