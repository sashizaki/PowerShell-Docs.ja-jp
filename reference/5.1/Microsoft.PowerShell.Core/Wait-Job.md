---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/28/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/wait-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Job
ms.openlocfilehash: 1f6df33e995ad717e1451c047fec072a280b4a54
ms.sourcegitcommit: 81558c2adb9d109946a027e5b96e4d24b3b13747
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2021
ms.locfileid: "99098683"
---
# <span data-ttu-id="b2da2-103">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="b2da2-103">Wait-Job</span></span>

## <span data-ttu-id="b2da2-104">概要</span><span class="sxs-lookup"><span data-stu-id="b2da2-104">SYNOPSIS</span></span>
<span data-ttu-id="b2da2-105">セッションで実行されている PowerShell ジョブの1つまたはすべてが終了状態になるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-105">Waits until one or all of the PowerShell jobs running in the session are in a terminating state.</span></span>

## <span data-ttu-id="b2da2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b2da2-106">SYNTAX</span></span>

### <span data-ttu-id="b2da2-107">SessionIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="b2da2-107">SessionIdParameterSet (Default)</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="b2da2-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="b2da2-108">JobParameterSet</span></span>

```
Wait-Job [-Job] <Job[]> [-Any] [-Timeout <Int32>] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="b2da2-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="b2da2-109">NameParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="b2da2-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="b2da2-110">InstanceIdParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="b2da2-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="b2da2-111">StateParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="b2da2-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="b2da2-112">FilterParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="b2da2-113">Description</span><span class="sxs-lookup"><span data-stu-id="b2da2-113">DESCRIPTION</span></span>

<span data-ttu-id="b2da2-114">`Wait-Job`コマンドレットは、ジョブが終了状態になるまで待機してから、実行を継続します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-114">The `Wait-Job` cmdlet waits for a job to be in a terminating state before continuing execution.</span></span>
<span data-ttu-id="b2da2-115">終了状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b2da2-115">The terminating states are:</span></span>

- <span data-ttu-id="b2da2-116">完了</span><span class="sxs-lookup"><span data-stu-id="b2da2-116">Completed</span></span>
- <span data-ttu-id="b2da2-117">失敗</span><span class="sxs-lookup"><span data-stu-id="b2da2-117">Failed</span></span>
- <span data-ttu-id="b2da2-118">停止済み</span><span class="sxs-lookup"><span data-stu-id="b2da2-118">Stopped</span></span>
- <span data-ttu-id="b2da2-119">Suspended</span><span class="sxs-lookup"><span data-stu-id="b2da2-119">Suspended</span></span>
- <span data-ttu-id="b2da2-120">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="b2da2-120">Disconnected</span></span>

<span data-ttu-id="b2da2-121">指定されたジョブまたはすべてのジョブが終了状態になるまで待つことができます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-121">You can wait until a specified job, or all jobs are in a terminating state.</span></span> <span data-ttu-id="b2da2-122">また、 **Timeout** パラメーターを使用してジョブの最大待機時間を設定することも、 **Force** パラメーターを使用してまたは状態のジョブを待機することもでき `Suspended` `Disconnected` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-122">You can also set a maximum wait time for the job using the **Timeout** parameter, or use the **Force** parameter to wait for a job in the `Suspended` or `Disconnected` states.</span></span>

<span data-ttu-id="b2da2-123">ジョブのコマンドが完了すると、は `Wait-Job` ジョブオブジェクトを返し、実行を継続します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-123">When the commands in the job are complete, `Wait-Job` returns a job object and continues execution.</span></span>

<span data-ttu-id="b2da2-124">コマンドレットを使用すると、コマンドレット `Wait-Job` `Start-Job` またはコマンドレットの **AsJob** パラメーターを使用して、開始されたジョブを待機でき `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-124">You can use the `Wait-Job` cmdlet to wait for jobs started by using the `Start-Job` cmdlet or the **AsJob** parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="b2da2-125">ジョブの詳細については、「 [about_Jobs](./about/about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2da2-125">For more information about jobs, see [about_Jobs](./about/about_Jobs.md).</span></span>

<span data-ttu-id="b2da2-126">Windows PowerShell 3.0 以降では、 `Wait-Job` コマンドレットは、ワークフロージョブやスケジュールされたジョブのインスタンスなどのカスタムジョブの種類も待機します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-126">Starting in Windows PowerShell 3.0, the `Wait-Job` cmdlet also waits for custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="b2da2-127">が特定の種類のジョブを待機できるようにするには、コマンドレットを実行する前に、コマンドレットを使用するか、 `Wait-Job` `Get-Job` `Import-Module` またはモジュールのコマンドレットを使用して、カスタムジョブの種類をサポートするモジュールをセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="b2da2-127">To enable `Wait-Job` to wait for jobs of a particular type, import the module that supports the custom job type into the session before you run the `Get-Job` cmdlet, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="b2da2-128">特定のカスタム ジョブの種類については、カスタムのジョブの種類機能のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2da2-128">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="b2da2-129">例</span><span class="sxs-lookup"><span data-stu-id="b2da2-129">EXAMPLES</span></span>

### <span data-ttu-id="b2da2-130">例 1: すべてのジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="b2da2-130">Example 1: Wait for all jobs</span></span>

```powershell
Get-Job | Wait-Job
```

<span data-ttu-id="b2da2-131">このコマンドは、セッションで実行されているすべてのジョブが完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-131">This command waits for all of the jobs running in the session to finish.</span></span>

### <span data-ttu-id="b2da2-132">例 2: Start-Job を使用してリモートコンピューターで開始されたジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="b2da2-132">Example 2: Wait for jobs started on remote computers by using Start-Job</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
Invoke-Command -Session $s -ScriptBlock {Start-Job -Name Date1 -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -Command {Wait-Job -Name Date1}
$done.Count
```

```Output
3
```

<span data-ttu-id="b2da2-133">この例では、コマンドレットを使用して、 `Wait-Job` リモートコンピューターで開始されたジョブと共にコマンドレットを使用する方法を示し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-133">This example shows how to use the `Wait-Job` cmdlet with jobs started on remote computers by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="b2da2-134">コマンド `Start-Job` レットを使用して、コマンドとコマンドの両方を `Wait-Job` リモートコンピューターに送信し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-134">Both `Start-Job` and `Wait-Job` commands are submitted to the remote computer by using the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="b2da2-135">この例では、を使用し `Wait-Job` `Get-Date` て、3台の異なるコンピューターでジョブとして実行されているコマンドが終了したかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-135">This example uses `Wait-Job` to determine whether a `Get-Date` command running as a job on three different computers is finished.</span></span>

<span data-ttu-id="b2da2-136">最初のコマンドは、3台のリモートコンピューターそれぞれに Windows PowerShell セッション (**PSSession**) を作成し、それらを変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-136">The first command creates a Windows PowerShell session (**PSSession**) on each of the three remote computers and stores them in the `$s` variable.</span></span>

<span data-ttu-id="b2da2-137">2番目のコマンドは、を使用して `Invoke-Command` `Start-Job` 、の3つの各セッションでを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-137">The second command uses `Invoke-Command` to run `Start-Job` in each of the three sessions in `$s`.</span></span>
<span data-ttu-id="b2da2-138">すべてのジョブには、Date1 という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-138">All of the jobs are named Date1.</span></span>

<span data-ttu-id="b2da2-139">3番目のコマンドは、を使用して `Invoke-Command` を実行し `Wait-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-139">The third command uses `Invoke-Command` to run `Wait-Job`.</span></span> <span data-ttu-id="b2da2-140">このコマンドは、 `Date1` 各コンピューター上のジョブが完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-140">This command waits for the `Date1` jobs on each computer to finish.</span></span> <span data-ttu-id="b2da2-141">これにより、**ジョブ** オブジェクトの結果のコレクション (**配列**) が変数に格納され `$done` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-141">It stores the resulting collection (**array**) of **job** objects in the `$done` variable.</span></span>

<span data-ttu-id="b2da2-142">4番目のコマンドは、変数内のジョブオブジェクトの配列の **Count** プロパティを使用して `$done` 、完了したジョブの数を確認します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-142">The fourth command uses the **Count** property of the array of job objects in the `$done` variable to determine how many of the jobs are finished.</span></span>

### <span data-ttu-id="b2da2-143">例 3: 最初のジョブが完了したことを確認する</span><span class="sxs-lookup"><span data-stu-id="b2da2-143">Example 3: Determine when the first job finishes</span></span>

```powershell
$s = New-PSSession (Get-Content Machines.txt)
$c = 'Get-EventLog -LogName System | where {$_.EntryType -eq "error" --and $_.Source -eq "LSASRV"} | Out-File Errors.txt'
Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$Using:c}
Invoke-Command -Session $s -ScriptBlock {Wait-Job -Any}
```

<span data-ttu-id="b2da2-144">この例では、の **Any** パラメーターを使用して、 `Wait-Job` 現在のセッションで実行されている多くのジョブのうち、最初のジョブが終了状態にある時点を確認します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-144">This example uses the **Any** parameter of `Wait-Job` to determine when the first of many jobs running in the current session are in a terminating state.</span></span> <span data-ttu-id="b2da2-145">また、コマンドレットを使用して `Wait-Job` リモートジョブの完了を待機する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-145">It also shows how to use the `Wait-Job` cmdlet to wait for remote jobs to finish.</span></span>

<span data-ttu-id="b2da2-146">最初のコマンドは、Machines.txt ファイルに一覧表示されている各コンピューター上に **pssession** を作成し、その **pssession** オブジェクトを変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-146">The first command creates a **PSSession** on each of the computers listed in the Machines.txt file and stores the **PSSession** objects in the `$s` variable.</span></span> <span data-ttu-id="b2da2-147">このコマンドは、コマンドレットを使用して、 `Get-Content` ファイルの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-147">The command uses the `Get-Content` cmdlet to get the contents of the file.</span></span> <span data-ttu-id="b2da2-148">コマンドは、 `Get-Content` コマンドの前に実行されるように、かっこで囲まれてい `New-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-148">The `Get-Content` command is enclosed in parentheses to make sure that it runs before the `New-PSSession` command.</span></span>

<span data-ttu-id="b2da2-149">2番目のコマンドは、 `Get-EventLog` コマンド文字列を引用符で囲んで変数に格納し `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-149">The second command stores a `Get-EventLog` command string, in quotation marks, in the `$c` variable.</span></span>

<span data-ttu-id="b2da2-150">3番目のコマンドは、 `Invoke-Command` コマンドレットを使用して `Start-Job` 、の各セッションでを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-150">The third command uses `Invoke-Command` cmdlet to run `Start-Job` in each of the sessions in `$s`.</span></span>
<span data-ttu-id="b2da2-151">コマンドは、 `Start-Job` 変数でコマンドを実行するジョブを開始し `Get-EventLog` `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-151">The `Start-Job` command starts a job that runs the `Get-EventLog` command in the `$c` variable.</span></span>

<span data-ttu-id="b2da2-152">このコマンドは、 **Using** スコープ修飾子を使用して、 `$c` 変数がローカルコンピューター上で定義されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-152">The command uses the **Using** scope modifier to indicate that the `$c` variable was defined on the local computer.</span></span> <span data-ttu-id="b2da2-153">**Using** スコープ修飾子は、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b2da2-153">The **Using** scope modifier is introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="b2da2-154">スコープ修飾子の **使用** の詳細については、「 [about_Remote_Variables](./about/about_Remote_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2da2-154">For more information about the **Using** scope modifier, see [about_Remote_Variables](./about/about_Remote_Variables.md).</span></span>

<span data-ttu-id="b2da2-155">4番目のコマンドは、を使用し `Invoke-Command` `Wait-Job` て、セッションでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-155">The fourth command uses `Invoke-Command` to run a `Wait-Job` command in the sessions.</span></span> <span data-ttu-id="b2da2-156">また、 **Any** パラメーターを使用して、リモートコンピューター上の最初のジョブが終了状態になるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-156">It uses the **Any** parameter to wait until the first job on the remote computers is terminating state.</span></span>

### <span data-ttu-id="b2da2-157">例 4: リモートコンピューター上のジョブの待機時間を設定する</span><span class="sxs-lookup"><span data-stu-id="b2da2-157">Example 4: Set a wait time for jobs on remote computers</span></span>

```powershell
PS> $s = New-PSSession Server01, Server02, Server03
PS> $jobs = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-Date}}
PS> $done = Invoke-Command -Session $s -ScriptBlock {Wait-Job -Timeout 30}
PS>
```

<span data-ttu-id="b2da2-158">この例では、の **Timeout** パラメーターを使用して、 `Wait-Job` リモートコンピューターで実行されているジョブの最大待機時間を設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-158">This example shows how to use the **Timeout** parameter of `Wait-Job` to set a maximum wait time for the jobs running on remote computers.</span></span>

<span data-ttu-id="b2da2-159">最初のコマンドは、3台のリモートコンピューター (Server01、Server02、および Server03) のそれぞれに **pssession** を作成し、その後、 **pssession** オブジェクトを変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-159">The first command creates a **PSSession** on each of three remote computers (Server01, Server02, and Server03), and then stores the **PSSession** objects in the `$s` variable.</span></span>

<span data-ttu-id="b2da2-160">2番目のコマンドは、を使用して、の `Invoke-Command` `Start-Job` 各 **PSSession** オブジェクトでを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-160">The second command uses `Invoke-Command` to run `Start-Job` in each of the **PSSession** objects in `$s`.</span></span> <span data-ttu-id="b2da2-161">結果として得られるジョブオブジェクトが変数に格納され `$jobs` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-161">It stores the resulting job objects in the `$jobs` variable.</span></span>

<span data-ttu-id="b2da2-162">3番目のコマンドは、を使用して `Invoke-Command` `Wait-Job` 、の各セッションでを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-162">The third command uses `Invoke-Command` to run `Wait-Job` in each of the sessions in `$s`.</span></span> <span data-ttu-id="b2da2-163">`Wait-Job`コマンドは、すべてのコマンドが30秒以内に完了したかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-163">The `Wait-Job` command determines whether all of the commands have completed within 30 seconds.</span></span> <span data-ttu-id="b2da2-164">**タイムアウト** パラメーターを30に設定して最大待機時間を設定し、コマンドの結果を変数に格納し `$done` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-164">It uses the **Timeout** parameter with a value of 30 to establish the maximum wait time, and then stores the results of the command in the `$done` variable.</span></span>

<span data-ttu-id="b2da2-165">この場合に、30 秒後に Server02 コンピューター上のコマンドのみが完了しました。</span><span class="sxs-lookup"><span data-stu-id="b2da2-165">In this case, after 30 seconds, only the command on the Server02 computer has completed.</span></span> <span data-ttu-id="b2da2-166">`Wait-Job` 待機を終了し、完了したジョブを表すオブジェクトを返し、コマンドプロンプトを表示します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-166">`Wait-Job` ends the wait, returns the object that represents the job that was completed, and displays the command prompt.</span></span>

<span data-ttu-id="b2da2-167">変数には、 `$done` Server02 で実行されたジョブを表す job オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b2da2-167">The `$done` variable contains a job object that represents the job that ran on Server02.</span></span>

### <span data-ttu-id="b2da2-168">例 5: 複数のジョブのいずれかが完了するまで待機する</span><span class="sxs-lookup"><span data-stu-id="b2da2-168">Example 5: Wait until one of several jobs finishes</span></span>

```powershell
Wait-Job -id 1,2,5 -Any
```

<span data-ttu-id="b2da2-169">このコマンドは、3つのジョブを Id で識別し、いずれかのジョブが終了状態になるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-169">This command identifies three jobs by their IDs and waits until any one of them are in a terminating state.</span></span> <span data-ttu-id="b2da2-170">最初のジョブが完了すると、実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-170">Execution continues when the first job finishes.</span></span>

### <span data-ttu-id="b2da2-171">例 6: 期間を待機してから、ジョブをバックグラウンドで続行することを許可する</span><span class="sxs-lookup"><span data-stu-id="b2da2-171">Example 6: Wait for a period, then allow job to continue in background</span></span>

```powershell
Wait-Job -Name "DailyLog" -Timeout 120
```

<span data-ttu-id="b2da2-172">このコマンドは、DailyLog ジョブが完了するまで120秒 (2 分) 待機します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-172">This command waits 120 seconds (two minutes) for the DailyLog job to finish.</span></span> <span data-ttu-id="b2da2-173">ジョブが次の2分以内に完了しない場合、実行は続行され、ジョブはバックグラウンドで実行され続けます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-173">If the job does not finish in the next two minutes, execution continues, and the job continues to run in the background.</span></span>

### <span data-ttu-id="b2da2-174">例 7: 名前でジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="b2da2-174">Example 7: Wait for a job by name</span></span>

```powershell
Wait-Job -Name "Job3"
```

<span data-ttu-id="b2da2-175">このコマンドは、ジョブ名を使用して、待機するジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-175">This command uses the job name to identify the job for which to wait.</span></span>

### <span data-ttu-id="b2da2-176">例 8: Start-Job で開始されたローカルコンピューター上のジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="b2da2-176">Example 8: Wait for jobs on local computer started with Start-Job</span></span>

```powershell
$j = Start-Job -ScriptBlock {Get-ChildItem *.ps1| where {$_.lastwritetime -gt ((Get-Date) - (New-TimeSpan -Days 7))}}
$j | Wait-Job
```

<span data-ttu-id="b2da2-177">この例では、を使用して、 `Wait-Job` ローカルコンピューターで開始されたジョブと共にコマンドレットを使用する方法を示し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-177">This example shows how to use the `Wait-Job` cmdlet with jobs started on the local computer by using `Start-Job`.</span></span>

<span data-ttu-id="b2da2-178">これらのコマンドは、過去 1 週間に追加または更新された Windows PowerShell スクリプト ファイルを取得するジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-178">These commands start a job that gets the Windows PowerShell script files that were added or updated in the last week.</span></span>

<span data-ttu-id="b2da2-179">最初のコマンドは、を使用して `Start-Job` ローカルコンピューター上でジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-179">The first command uses `Start-Job` to start a job on the local computer.</span></span> <span data-ttu-id="b2da2-180">このジョブは、 `Get-ChildItem` 過去1週間に追加または更新されたファイル名拡張子が ps1 のすべてのファイルを取得するコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-180">The job runs a `Get-ChildItem` command that gets all of the files that have a .ps1 file name extension that were added or updated in the last week.</span></span>

<span data-ttu-id="b2da2-181">3番目のコマンドは、を使用して `Wait-Job` 、ジョブが終了状態になるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-181">The third command uses `Wait-Job` to wait until the job is in a terminating state.</span></span> <span data-ttu-id="b2da2-182">ジョブが完了すると、ジョブに関する情報を含むジョブオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-182">When the job finishes, the command displays the job object, which contains information about the job.</span></span>

### <span data-ttu-id="b2da2-183">例 9: Invoke-Command を使用してリモートコンピューターで開始されたジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="b2da2-183">Example 9: Wait for jobs started on remote computers by using Invoke-Command</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
$j = Invoke-Command -Session $s -ScriptBlock {Get-Process} -AsJob
$j | Wait-Job
```

<span data-ttu-id="b2da2-184">この例では `Wait-Job` 、の **AsJob** パラメーターを使用して、リモートコンピューターで開始されたジョブと共にを使用する方法を示し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-184">This example shows how to use `Wait-Job` with jobs started on remote computers by using the **AsJob** parameter of `Invoke-Command`.</span></span> <span data-ttu-id="b2da2-185">**AsJob** を使用する場合、ジョブはローカルコンピューター上に作成され、そのジョブがリモートコンピューター上で実行されている場合でも、結果はローカルコンピューターに自動的に返されます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-185">When using **AsJob**, the job is created on the local computer and the results are automatically returned to the local computer, even though the job runs on the remote computers.</span></span>

<span data-ttu-id="b2da2-186">この例では、を使用して、 `Wait-Job` `Get-Process` 3 台のリモートコンピューター上のセッションで実行されているコマンドが終了状態であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-186">This example uses `Wait-Job` to determine whether a `Get-Process` command running in the sessions on three remote computers is in a terminating state.</span></span>

<span data-ttu-id="b2da2-187">最初のコマンドは、3台のコンピューター上に **PSSession** オブジェクトを作成し、それらを変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-187">The first command creates **PSSession** objects on three computers and stores them in the `$s` variable.</span></span>

<span data-ttu-id="b2da2-188">2番目のコマンドは、を使用して `Invoke-Command` `Get-Process` 、の3つの各セッションでを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-188">The second command uses `Invoke-Command` to run `Get-Process` in each of the three sessions in `$s`.</span></span>
<span data-ttu-id="b2da2-189">このコマンドは、 **AsJob** パラメーターを使用して、コマンドをジョブとして非同期に実行します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-189">The command uses the **AsJob** parameter to run the command asynchronously as a job.</span></span> <span data-ttu-id="b2da2-190">コマンドは、を使用して開始されたジョブと同様に、ジョブオブジェクトを返し、 `Start-Job` ジョブオブジェクトは変数に格納され `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-190">The command returns a job object, just like the jobs started by using `Start-Job`, and the job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="b2da2-191">3番目のコマンドは、パイプライン演算子 () を使用して、 `|` のジョブオブジェクトを `$j` コマンドレットに送信し `Wait-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-191">The third command uses a pipeline operator (`|`) to send the job object in `$j` to the `Wait-Job` cmdlet.</span></span> <span data-ttu-id="b2da2-192">`Invoke-Command`この場合、ジョブはローカルコンピューター上に存在するため、コマンドは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b2da2-192">An `Invoke-Command` command is not required in this case, because the job resides on the local computer.</span></span>

### <span data-ttu-id="b2da2-193">例 10: ID を持つジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="b2da2-193">Example 10: Wait for a job that has an ID</span></span>

```powershell
Get-Job
```

```Output
Id   Name     State      HasMoreData     Location             Command
--   ----     -----      -----------     --------             -------
1    Job1     Completed  True            localhost,Server01.. get-service
4    Job4     Completed  True            localhost            dir | where
```

```powershell
Wait-Job -Id 1
```

<span data-ttu-id="b2da2-194">このコマンドは、ID 値が 1 であるジョブを待機します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-194">This command waits for the job with an ID value of 1.</span></span>

## <span data-ttu-id="b2da2-195">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b2da2-195">PARAMETERS</span></span>

### <span data-ttu-id="b2da2-196">-任意</span><span class="sxs-lookup"><span data-stu-id="b2da2-196">-Any</span></span>

<span data-ttu-id="b2da2-197">このコマンドレットがジョブオブジェクトを返し、任意のジョブが終了したときに実行を継続することを示します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-197">Indicates that this cmdlet returns the job object and continues execution when any job finishes.</span></span> <span data-ttu-id="b2da2-198">既定では、は、 `Wait-Job` 指定されたすべてのジョブが完了するまで待機してから、プロンプトを表示します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-198">By default, `Wait-Job` waits until all of the specified jobs are complete before it displays the prompt.</span></span>

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

### <span data-ttu-id="b2da2-199">-Filter</span><span class="sxs-lookup"><span data-stu-id="b2da2-199">-Filter</span></span>

<span data-ttu-id="b2da2-200">条件のハッシュテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-200">Specifies a hash table of conditions.</span></span> <span data-ttu-id="b2da2-201">このコマンドレットは、ハッシュテーブル内のすべての条件を満たすジョブを待機します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-201">This cmdlet waits for jobs that satisfy all of the conditions in the hash table.</span></span> <span data-ttu-id="b2da2-202">ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-202">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="b2da2-203">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-203">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="b2da2-204">コマンドレットを使用して作成されたジョブなど、標準ジョブでは機能しません `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="b2da2-204">It does not work on standard jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="b2da2-205">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2da2-205">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="b2da2-206">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b2da2-206">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="b2da2-207">-Force</span><span class="sxs-lookup"><span data-stu-id="b2da2-207">-Force</span></span>

<span data-ttu-id="b2da2-208">このコマンドレットが中断または切断状態のジョブを引き続き待機することを示します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-208">Indicates that this cmdlet continues to wait for jobs in the Suspended or Disconnected state.</span></span> <span data-ttu-id="b2da2-209">既定では、 `Wait-Job` ジョブが次のいずれかの状態にある場合、は待機を返すか、または終了します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-209">By default, `Wait-Job` returns, or ends the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="b2da2-210">完了</span><span class="sxs-lookup"><span data-stu-id="b2da2-210">Completed</span></span>
- <span data-ttu-id="b2da2-211">失敗</span><span class="sxs-lookup"><span data-stu-id="b2da2-211">Failed</span></span>
- <span data-ttu-id="b2da2-212">停止済み</span><span class="sxs-lookup"><span data-stu-id="b2da2-212">Stopped</span></span>
- <span data-ttu-id="b2da2-213">Suspended</span><span class="sxs-lookup"><span data-stu-id="b2da2-213">Suspended</span></span>
- <span data-ttu-id="b2da2-214">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="b2da2-214">Disconnected</span></span>

<span data-ttu-id="b2da2-215">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b2da2-215">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="b2da2-216">-Id</span><span class="sxs-lookup"><span data-stu-id="b2da2-216">-Id</span></span>

<span data-ttu-id="b2da2-217">このコマンドレットが待機するジョブの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-217">Specifies an array of IDs of jobs for which this cmdlet waits.</span></span>

<span data-ttu-id="b2da2-218">ID は、現在のセッションでジョブを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="b2da2-218">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="b2da2-219">インスタンス ID よりも覚えやすく、入力も簡単ですが、現在のセッションでのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="b2da2-219">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="b2da2-220">1つ以上の Id をコンマで区切って入力できます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-220">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="b2da2-221">ジョブの ID を検索するには、「」と入力 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-221">To find the ID of a job, type `Get-Job`.</span></span>

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

### <span data-ttu-id="b2da2-222">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="b2da2-222">-InstanceId</span></span>

<span data-ttu-id="b2da2-223">このコマンドレットが待機するジョブのインスタンス Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-223">Specifies an array of instance IDs of jobs for which this cmdlet waits.</span></span> <span data-ttu-id="b2da2-224">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="b2da2-224">The default is all jobs.</span></span>

<span data-ttu-id="b2da2-225">インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="b2da2-225">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="b2da2-226">ジョブのインスタンス ID を検索するには、を使用 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-226">To find the instance ID of a job, use `Get-Job`.</span></span>

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

### <span data-ttu-id="b2da2-227">-ジョブ</span><span class="sxs-lookup"><span data-stu-id="b2da2-227">-Job</span></span>

<span data-ttu-id="b2da2-228">このコマンドレットが待機するジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-228">Specifies the jobs for which this cmdlet waits.</span></span> <span data-ttu-id="b2da2-229">ジョブ オブジェクトが格納されている変数、またはジョブ オブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-229">Enter a variable that contains the job objects or a command that gets the job objects.</span></span> <span data-ttu-id="b2da2-230">パイプライン演算子を使用して、ジョブオブジェクトをコマンドレットに渡すこともでき `Wait-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-230">You can also use a pipeline operator to send job objects to the `Wait-Job` cmdlet.</span></span> <span data-ttu-id="b2da2-231">既定では、は、 `Wait-Job` 現在のセッションで作成されたすべてのジョブを待機します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-231">By default, `Wait-Job` waits for all jobs created in the current session.</span></span>

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

### <span data-ttu-id="b2da2-232">-Name</span><span class="sxs-lookup"><span data-stu-id="b2da2-232">-Name</span></span>

<span data-ttu-id="b2da2-233">このコマンドレットが待機するジョブのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-233">Specifies friendly names of jobs for which this cmdlet waits.</span></span>

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

### <span data-ttu-id="b2da2-234">-状態</span><span class="sxs-lookup"><span data-stu-id="b2da2-234">-State</span></span>

<span data-ttu-id="b2da2-235">ジョブの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-235">Specifies a job state.</span></span> <span data-ttu-id="b2da2-236">このコマンドレットは、指定された状態のジョブのみを待機します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-236">This cmdlet waits only for jobs in the specified state.</span></span> <span data-ttu-id="b2da2-237">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b2da2-237">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b2da2-238">NotStarted</span><span class="sxs-lookup"><span data-stu-id="b2da2-238">NotStarted</span></span>
- <span data-ttu-id="b2da2-239">実行中</span><span class="sxs-lookup"><span data-stu-id="b2da2-239">Running</span></span>
- <span data-ttu-id="b2da2-240">完了</span><span class="sxs-lookup"><span data-stu-id="b2da2-240">Completed</span></span>
- <span data-ttu-id="b2da2-241">失敗</span><span class="sxs-lookup"><span data-stu-id="b2da2-241">Failed</span></span>
- <span data-ttu-id="b2da2-242">停止済み</span><span class="sxs-lookup"><span data-stu-id="b2da2-242">Stopped</span></span>
- <span data-ttu-id="b2da2-243">［ブロック済み］</span><span class="sxs-lookup"><span data-stu-id="b2da2-243">Blocked</span></span>
- <span data-ttu-id="b2da2-244">Suspended</span><span class="sxs-lookup"><span data-stu-id="b2da2-244">Suspended</span></span>
- <span data-ttu-id="b2da2-245">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="b2da2-245">Disconnected</span></span>
- <span data-ttu-id="b2da2-246">中断中</span><span class="sxs-lookup"><span data-stu-id="b2da2-246">Suspending</span></span>
- <span data-ttu-id="b2da2-247">停止中</span><span class="sxs-lookup"><span data-stu-id="b2da2-247">Stopping</span></span>

<span data-ttu-id="b2da2-248">ジョブの状態の詳細については、「 [Jobstate 列挙型](/dotnet/api/system.management.automation.jobstate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2da2-248">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

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

### <span data-ttu-id="b2da2-249">-タイムアウト</span><span class="sxs-lookup"><span data-stu-id="b2da2-249">-Timeout</span></span>

<span data-ttu-id="b2da2-250">各ジョブの最大待機時間を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-250">Specifies the maximum wait time for each job, in seconds.</span></span> <span data-ttu-id="b2da2-251">既定値は-1 です。このコマンドレットは、ジョブが完了するまで待機することを示します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-251">The default value, -1, indicates that the cmdlet waits until the job finishes.</span></span> <span data-ttu-id="b2da2-252">コマンドではなくコマンドを送信すると、タイミングが開始 `Wait-Job` され `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-252">The timing starts when you submit the `Wait-Job` command, not the `Start-Job` command.</span></span>

<span data-ttu-id="b2da2-253">この時間が経過すると、ジョブがまだ実行されている場合でも、待機が終了し、実行が継続されます。</span><span class="sxs-lookup"><span data-stu-id="b2da2-253">If this time is exceeded, the wait ends and execution continues, even if the job is still running.</span></span>
<span data-ttu-id="b2da2-254">このコマンドでは、エラーメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="b2da2-254">The command does not display any error message.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b2da2-255">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b2da2-255">CommonParameters</span></span>

<span data-ttu-id="b2da2-256">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b2da2-256">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b2da2-257">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2da2-257">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b2da2-258">入力</span><span class="sxs-lookup"><span data-stu-id="b2da2-258">INPUTS</span></span>

### <span data-ttu-id="b2da2-259">System. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="b2da2-259">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="b2da2-260">パイプを使用してジョブオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-260">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="b2da2-261">出力</span><span class="sxs-lookup"><span data-stu-id="b2da2-261">OUTPUTS</span></span>

### <span data-ttu-id="b2da2-262">システムの管理. PSRemotingJob</span><span class="sxs-lookup"><span data-stu-id="b2da2-262">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="b2da2-263">このコマンドレットは、終了状態のジョブを表すジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-263">This cmdlet returns job objects that represent the jobs in a terminating state.</span></span> <span data-ttu-id="b2da2-264">**Timeout** パラメーターの値を超えたことが原因で待機が終了した場合、 `Wait-Job` はオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="b2da2-264">If the wait ends because the value of the **Timeout** parameter is exceeded, `Wait-Job` does not return any objects.</span></span>

## <span data-ttu-id="b2da2-265">注</span><span class="sxs-lookup"><span data-stu-id="b2da2-265">NOTES</span></span>

<span data-ttu-id="b2da2-266">既定では、 `Wait-Job` ジョブが次のいずれかの状態にある場合、は待機を返すか、または終了します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-266">By default, `Wait-Job` returns, or ends the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="b2da2-267">完了</span><span class="sxs-lookup"><span data-stu-id="b2da2-267">Completed</span></span>
- <span data-ttu-id="b2da2-268">失敗</span><span class="sxs-lookup"><span data-stu-id="b2da2-268">Failed</span></span>
- <span data-ttu-id="b2da2-269">停止済み</span><span class="sxs-lookup"><span data-stu-id="b2da2-269">Stopped</span></span>
- <span data-ttu-id="b2da2-270">Suspended</span><span class="sxs-lookup"><span data-stu-id="b2da2-270">Suspended</span></span>
- <span data-ttu-id="b2da2-271">`Wait-Job`中断されたジョブと切断されたジョブを引き続き待機するために切断された場合は、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b2da2-271">Disconnected To direct `Wait-Job` to continue to wait for Suspended and Disconnected jobs, use the **Force** parameter.</span></span>

## <span data-ttu-id="b2da2-272">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b2da2-272">RELATED LINKS</span></span>

[<span data-ttu-id="b2da2-273">Get-Job</span><span class="sxs-lookup"><span data-stu-id="b2da2-273">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="b2da2-274">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="b2da2-274">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="b2da2-275">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="b2da2-275">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="b2da2-276">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="b2da2-276">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="b2da2-277">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="b2da2-277">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="b2da2-278">Start-Job</span><span class="sxs-lookup"><span data-stu-id="b2da2-278">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="b2da2-279">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="b2da2-279">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="b2da2-280">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="b2da2-280">Suspend-Job</span></span>](Suspend-Job.md)
