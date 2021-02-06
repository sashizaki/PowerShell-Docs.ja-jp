---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/28/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/wait-job?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Job
ms.openlocfilehash: ffcd0fba9fae9ed49e7f20fa5a971e6e50fc445f
ms.sourcegitcommit: 81558c2adb9d109946a027e5b96e4d24b3b13747
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2021
ms.locfileid: "99599707"
---
# <span data-ttu-id="0ece0-102">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="0ece0-102">Wait-Job</span></span>

## <span data-ttu-id="0ece0-103">概要</span><span class="sxs-lookup"><span data-stu-id="0ece0-103">SYNOPSIS</span></span>
<span data-ttu-id="0ece0-104">セッションで実行されている PowerShell ジョブの1つまたはすべてが終了状態になるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-104">Waits until one or all of the PowerShell jobs running in the session are in a terminating state.</span></span>

## <span data-ttu-id="0ece0-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0ece0-105">SYNTAX</span></span>

### <span data-ttu-id="0ece0-106">SessionIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="0ece0-106">SessionIdParameterSet (Default)</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="0ece0-107">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="0ece0-107">JobParameterSet</span></span>

```
Wait-Job [-Job] <Job[]> [-Any] [-Timeout <Int32>] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="0ece0-108">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="0ece0-108">NameParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="0ece0-109">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="0ece0-109">InstanceIdParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="0ece0-110">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="0ece0-110">StateParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="0ece0-111">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="0ece0-111">FilterParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="0ece0-112">Description</span><span class="sxs-lookup"><span data-stu-id="0ece0-112">DESCRIPTION</span></span>

<span data-ttu-id="0ece0-113">`Wait-Job`コマンドレットは、ジョブが終了状態になるまで待機してから、実行を継続します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-113">The `Wait-Job` cmdlet waits for a job to be in a terminating state before continuing execution.</span></span>
<span data-ttu-id="0ece0-114">終了状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0ece0-114">The terminating states are:</span></span>

- <span data-ttu-id="0ece0-115">完了</span><span class="sxs-lookup"><span data-stu-id="0ece0-115">Completed</span></span>
- <span data-ttu-id="0ece0-116">失敗</span><span class="sxs-lookup"><span data-stu-id="0ece0-116">Failed</span></span>
- <span data-ttu-id="0ece0-117">停止済み</span><span class="sxs-lookup"><span data-stu-id="0ece0-117">Stopped</span></span>
- <span data-ttu-id="0ece0-118">Suspended</span><span class="sxs-lookup"><span data-stu-id="0ece0-118">Suspended</span></span>
- <span data-ttu-id="0ece0-119">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="0ece0-119">Disconnected</span></span>

<span data-ttu-id="0ece0-120">指定されたジョブまたはすべてのジョブが終了状態になるまで待つことができます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-120">You can wait until a specified job, or all jobs are in a terminating state.</span></span> <span data-ttu-id="0ece0-121">また、 **Timeout** パラメーターを使用してジョブの最大待機時間を設定することも、 **Force** パラメーターを使用してまたは状態のジョブを待機することもでき `Suspended` `Disconnected` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-121">You can also set a maximum wait time for the job using the **Timeout** parameter, or use the **Force** parameter to wait for a job in the `Suspended` or `Disconnected` states.</span></span>

<span data-ttu-id="0ece0-122">ジョブのコマンドが完了すると、は `Wait-Job` ジョブオブジェクトを返し、実行を継続します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-122">When the commands in the job are complete, `Wait-Job` returns a job object and continues execution.</span></span>

<span data-ttu-id="0ece0-123">コマンドレットを使用すると、コマンドレット `Wait-Job` `Start-Job` またはコマンドレットの **AsJob** パラメーターを使用して、開始されたジョブを待機でき `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-123">You can use the `Wait-Job` cmdlet to wait for jobs started by using the `Start-Job` cmdlet or the **AsJob** parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="0ece0-124">ジョブの詳細については、「 [about_Jobs](./about/about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ece0-124">For more information about jobs, see [about_Jobs](./about/about_Jobs.md).</span></span>

<span data-ttu-id="0ece0-125">Windows PowerShell 3.0 以降では、 `Wait-Job` コマンドレットは、ワークフロージョブやスケジュールされたジョブのインスタンスなどのカスタムジョブの種類も待機します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-125">Starting in Windows PowerShell 3.0, the `Wait-Job` cmdlet also waits for custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="0ece0-126">が特定の種類のジョブを待機できるようにするには、コマンドレットを実行する前に、コマンドレットを使用するか、 `Wait-Job` `Get-Job` `Import-Module` またはモジュールのコマンドレットを使用して、カスタムジョブの種類をサポートするモジュールをセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="0ece0-126">To enable `Wait-Job` to wait for jobs of a particular type, import the module that supports the custom job type into the session before you run the `Get-Job` cmdlet, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="0ece0-127">特定のカスタム ジョブの種類については、カスタムのジョブの種類機能のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ece0-127">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="0ece0-128">例</span><span class="sxs-lookup"><span data-stu-id="0ece0-128">EXAMPLES</span></span>

### <span data-ttu-id="0ece0-129">例 1: すべてのジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="0ece0-129">Example 1: Wait for all jobs</span></span>

```powershell
Get-Job | Wait-Job
```

<span data-ttu-id="0ece0-130">このコマンドは、セッションで実行されているすべてのジョブが完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-130">This command waits for all of the jobs running in the session to finish.</span></span>

### <span data-ttu-id="0ece0-131">例 2: Start-Job を使用してリモートコンピューターで開始されたジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="0ece0-131">Example 2: Wait for jobs started on remote computers by using Start-Job</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
Invoke-Command -Session $s -ScriptBlock {Start-Job -Name Date1 -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -Command {Wait-Job -Name Date1}
$done.Count
```

```Output
3
```

<span data-ttu-id="0ece0-132">この例では、コマンドレットを使用して、 `Wait-Job` リモートコンピューターで開始されたジョブと共にコマンドレットを使用する方法を示し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-132">This example shows how to use the `Wait-Job` cmdlet with jobs started on remote computers by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="0ece0-133">コマンド `Start-Job` レットを使用して、コマンドとコマンドの両方を `Wait-Job` リモートコンピューターに送信し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-133">Both `Start-Job` and `Wait-Job` commands are submitted to the remote computer by using the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="0ece0-134">この例では、を使用し `Wait-Job` `Get-Date` て、3台の異なるコンピューターでジョブとして実行されているコマンドが終了したかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-134">This example uses `Wait-Job` to determine whether a `Get-Date` command running as a job on three different computers is finished.</span></span>

<span data-ttu-id="0ece0-135">最初のコマンドは、3台のリモートコンピューターそれぞれに Windows PowerShell セッション (**PSSession**) を作成し、それらを変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-135">The first command creates a Windows PowerShell session (**PSSession**) on each of the three remote computers and stores them in the `$s` variable.</span></span>

<span data-ttu-id="0ece0-136">2番目のコマンドは、を使用して `Invoke-Command` `Start-Job` 、の3つの各セッションでを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-136">The second command uses `Invoke-Command` to run `Start-Job` in each of the three sessions in `$s`.</span></span>
<span data-ttu-id="0ece0-137">すべてのジョブには、Date1 という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-137">All of the jobs are named Date1.</span></span>

<span data-ttu-id="0ece0-138">3番目のコマンドは、を使用して `Invoke-Command` を実行し `Wait-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-138">The third command uses `Invoke-Command` to run `Wait-Job`.</span></span> <span data-ttu-id="0ece0-139">このコマンドは、 `Date1` 各コンピューター上のジョブが完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-139">This command waits for the `Date1` jobs on each computer to finish.</span></span> <span data-ttu-id="0ece0-140">これにより、**ジョブ** オブジェクトの結果のコレクション (**配列**) が変数に格納され `$done` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-140">It stores the resulting collection (**array**) of **job** objects in the `$done` variable.</span></span>

<span data-ttu-id="0ece0-141">4番目のコマンドは、変数内のジョブオブジェクトの配列の **Count** プロパティを使用して `$done` 、完了したジョブの数を確認します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-141">The fourth command uses the **Count** property of the array of job objects in the `$done` variable to determine how many of the jobs are finished.</span></span>

### <span data-ttu-id="0ece0-142">例 3: 最初のジョブが完了したことを確認する</span><span class="sxs-lookup"><span data-stu-id="0ece0-142">Example 3: Determine when the first job finishes</span></span>

```powershell
$s = New-PSSession (Get-Content Machines.txt)
$c = 'Get-EventLog -LogName System | where {$_.EntryType -eq "error" --and $_.Source -eq "LSASRV"} | Out-File Errors.txt'
Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$Using:c}
Invoke-Command -Session $s -ScriptBlock {Wait-Job -Any}
```

<span data-ttu-id="0ece0-143">この例では、の **Any** パラメーターを使用して、 `Wait-Job` 現在のセッションで実行されている多くのジョブのうち、最初のジョブが終了状態にある時点を確認します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-143">This example uses the **Any** parameter of `Wait-Job` to determine when the first of many jobs running in the current session are in a terminating state.</span></span> <span data-ttu-id="0ece0-144">また、コマンドレットを使用して `Wait-Job` リモートジョブの完了を待機する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-144">It also shows how to use the `Wait-Job` cmdlet to wait for remote jobs to finish.</span></span>

<span data-ttu-id="0ece0-145">最初のコマンドは、Machines.txt ファイルに一覧表示されている各コンピューター上に **pssession** を作成し、その **pssession** オブジェクトを変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-145">The first command creates a **PSSession** on each of the computers listed in the Machines.txt file and stores the **PSSession** objects in the `$s` variable.</span></span> <span data-ttu-id="0ece0-146">このコマンドは、コマンドレットを使用して、 `Get-Content` ファイルの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-146">The command uses the `Get-Content` cmdlet to get the contents of the file.</span></span> <span data-ttu-id="0ece0-147">コマンドは、 `Get-Content` コマンドの前に実行されるように、かっこで囲まれてい `New-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-147">The `Get-Content` command is enclosed in parentheses to make sure that it runs before the `New-PSSession` command.</span></span>

<span data-ttu-id="0ece0-148">2番目のコマンドは、 `Get-EventLog` コマンド文字列を引用符で囲んで変数に格納し `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-148">The second command stores a `Get-EventLog` command string, in quotation marks, in the `$c` variable.</span></span>

<span data-ttu-id="0ece0-149">3番目のコマンドは、 `Invoke-Command` コマンドレットを使用して `Start-Job` 、の各セッションでを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-149">The third command uses `Invoke-Command` cmdlet to run `Start-Job` in each of the sessions in `$s`.</span></span>
<span data-ttu-id="0ece0-150">コマンドは、 `Start-Job` 変数でコマンドを実行するジョブを開始し `Get-EventLog` `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-150">The `Start-Job` command starts a job that runs the `Get-EventLog` command in the `$c` variable.</span></span>

<span data-ttu-id="0ece0-151">このコマンドは、 **Using** スコープ修飾子を使用して、 `$c` 変数がローカルコンピューター上で定義されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-151">The command uses the **Using** scope modifier to indicate that the `$c` variable was defined on the local computer.</span></span> <span data-ttu-id="0ece0-152">**Using** スコープ修飾子は、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0ece0-152">The **Using** scope modifier is introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="0ece0-153">スコープ修飾子の **使用** の詳細については、「 [about_Remote_Variables](./about/about_Remote_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ece0-153">For more information about the **Using** scope modifier, see [about_Remote_Variables](./about/about_Remote_Variables.md).</span></span>

<span data-ttu-id="0ece0-154">4番目のコマンドは、を使用し `Invoke-Command` `Wait-Job` て、セッションでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-154">The fourth command uses `Invoke-Command` to run a `Wait-Job` command in the sessions.</span></span> <span data-ttu-id="0ece0-155">また、 **Any** パラメーターを使用して、リモートコンピューター上の最初のジョブが終了状態になるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-155">It uses the **Any** parameter to wait until the first job on the remote computers is terminating state.</span></span>

### <span data-ttu-id="0ece0-156">例 4: リモートコンピューター上のジョブの待機時間を設定する</span><span class="sxs-lookup"><span data-stu-id="0ece0-156">Example 4: Set a wait time for jobs on remote computers</span></span>

```powershell
PS> $s = New-PSSession Server01, Server02, Server03
PS> $jobs = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-Date}}
PS> $done = Invoke-Command -Session $s -ScriptBlock {Wait-Job -Timeout 30}
PS>
```

<span data-ttu-id="0ece0-157">この例では、の **Timeout** パラメーターを使用して、 `Wait-Job` リモートコンピューターで実行されているジョブの最大待機時間を設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-157">This example shows how to use the **Timeout** parameter of `Wait-Job` to set a maximum wait time for the jobs running on remote computers.</span></span>

<span data-ttu-id="0ece0-158">最初のコマンドは、3台のリモートコンピューター (Server01、Server02、および Server03) のそれぞれに **pssession** を作成し、その後、 **pssession** オブジェクトを変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-158">The first command creates a **PSSession** on each of three remote computers (Server01, Server02, and Server03), and then stores the **PSSession** objects in the `$s` variable.</span></span>

<span data-ttu-id="0ece0-159">2番目のコマンドは、を使用して、の `Invoke-Command` `Start-Job` 各 **PSSession** オブジェクトでを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-159">The second command uses `Invoke-Command` to run `Start-Job` in each of the **PSSession** objects in `$s`.</span></span> <span data-ttu-id="0ece0-160">結果として得られるジョブオブジェクトが変数に格納され `$jobs` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-160">It stores the resulting job objects in the `$jobs` variable.</span></span>

<span data-ttu-id="0ece0-161">3番目のコマンドは、を使用して `Invoke-Command` `Wait-Job` 、の各セッションでを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-161">The third command uses `Invoke-Command` to run `Wait-Job` in each of the sessions in `$s`.</span></span> <span data-ttu-id="0ece0-162">`Wait-Job`コマンドは、すべてのコマンドが30秒以内に完了したかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-162">The `Wait-Job` command determines whether all of the commands have completed within 30 seconds.</span></span> <span data-ttu-id="0ece0-163">**タイムアウト** パラメーターを30に設定して最大待機時間を設定し、コマンドの結果を変数に格納し `$done` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-163">It uses the **Timeout** parameter with a value of 30 to establish the maximum wait time, and then stores the results of the command in the `$done` variable.</span></span>

<span data-ttu-id="0ece0-164">この場合に、30 秒後に Server02 コンピューター上のコマンドのみが完了しました。</span><span class="sxs-lookup"><span data-stu-id="0ece0-164">In this case, after 30 seconds, only the command on the Server02 computer has completed.</span></span> <span data-ttu-id="0ece0-165">`Wait-Job` 待機を終了し、完了したジョブを表すオブジェクトを返し、コマンドプロンプトを表示します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-165">`Wait-Job` ends the wait, returns the object that represents the job that was completed, and displays the command prompt.</span></span>

<span data-ttu-id="0ece0-166">変数には、 `$done` Server02 で実行されたジョブを表す job オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0ece0-166">The `$done` variable contains a job object that represents the job that ran on Server02.</span></span>

### <span data-ttu-id="0ece0-167">例 5: 複数のジョブのいずれかが完了するまで待機する</span><span class="sxs-lookup"><span data-stu-id="0ece0-167">Example 5: Wait until one of several jobs finishes</span></span>

```powershell
Wait-Job -id 1,2,5 -Any
```

<span data-ttu-id="0ece0-168">このコマンドは、3つのジョブを Id で識別し、いずれかのジョブが終了状態になるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-168">This command identifies three jobs by their IDs and waits until any one of them are in a terminating state.</span></span> <span data-ttu-id="0ece0-169">最初のジョブが完了すると、実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-169">Execution continues when the first job finishes.</span></span>

### <span data-ttu-id="0ece0-170">例 6: 期間を待機してから、ジョブをバックグラウンドで続行することを許可する</span><span class="sxs-lookup"><span data-stu-id="0ece0-170">Example 6: Wait for a period, then allow job to continue in background</span></span>

```powershell
Wait-Job -Name "DailyLog" -Timeout 120
```

<span data-ttu-id="0ece0-171">このコマンドは、DailyLog ジョブが完了するまで120秒 (2 分) 待機します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-171">This command waits 120 seconds (two minutes) for the DailyLog job to finish.</span></span> <span data-ttu-id="0ece0-172">ジョブが次の2分以内に完了しない場合、実行は続行され、ジョブはバックグラウンドで実行され続けます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-172">If the job does not finish in the next two minutes, execution continues, and the job continues to run in the background.</span></span>

### <span data-ttu-id="0ece0-173">例 7: 名前でジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="0ece0-173">Example 7: Wait for a job by name</span></span>

```powershell
Wait-Job -Name "Job3"
```

<span data-ttu-id="0ece0-174">このコマンドは、ジョブ名を使用して、待機するジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-174">This command uses the job name to identify the job for which to wait.</span></span>

### <span data-ttu-id="0ece0-175">例 8: Start-Job で開始されたローカルコンピューター上のジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="0ece0-175">Example 8: Wait for jobs on local computer started with Start-Job</span></span>

```powershell
$j = Start-Job -ScriptBlock {Get-ChildItem *.ps1| where {$_.lastwritetime -gt ((Get-Date) - (New-TimeSpan -Days 7))}}
$j | Wait-Job
```

<span data-ttu-id="0ece0-176">この例では、を使用して、 `Wait-Job` ローカルコンピューターで開始されたジョブと共にコマンドレットを使用する方法を示し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-176">This example shows how to use the `Wait-Job` cmdlet with jobs started on the local computer by using `Start-Job`.</span></span>

<span data-ttu-id="0ece0-177">これらのコマンドは、過去 1 週間に追加または更新された Windows PowerShell スクリプト ファイルを取得するジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-177">These commands start a job that gets the Windows PowerShell script files that were added or updated in the last week.</span></span>

<span data-ttu-id="0ece0-178">最初のコマンドは、を使用して `Start-Job` ローカルコンピューター上でジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-178">The first command uses `Start-Job` to start a job on the local computer.</span></span> <span data-ttu-id="0ece0-179">このジョブは、 `Get-ChildItem` 過去1週間に追加または更新されたファイル名拡張子が ps1 のすべてのファイルを取得するコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-179">The job runs a `Get-ChildItem` command that gets all of the files that have a .ps1 file name extension that were added or updated in the last week.</span></span>

<span data-ttu-id="0ece0-180">3番目のコマンドは、を使用して `Wait-Job` 、ジョブが終了状態になるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-180">The third command uses `Wait-Job` to wait until the job is in a terminating state.</span></span> <span data-ttu-id="0ece0-181">ジョブが完了すると、ジョブに関する情報を含むジョブオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-181">When the job finishes, the command displays the job object, which contains information about the job.</span></span>

### <span data-ttu-id="0ece0-182">例 9: Invoke-Command を使用してリモートコンピューターで開始されたジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="0ece0-182">Example 9: Wait for jobs started on remote computers by using Invoke-Command</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
$j = Invoke-Command -Session $s -ScriptBlock {Get-Process} -AsJob
$j | Wait-Job
```

<span data-ttu-id="0ece0-183">この例では `Wait-Job` 、の **AsJob** パラメーターを使用して、リモートコンピューターで開始されたジョブと共にを使用する方法を示し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-183">This example shows how to use `Wait-Job` with jobs started on remote computers by using the **AsJob** parameter of `Invoke-Command`.</span></span> <span data-ttu-id="0ece0-184">**AsJob** を使用する場合、ジョブはローカルコンピューター上に作成され、そのジョブがリモートコンピューター上で実行されている場合でも、結果はローカルコンピューターに自動的に返されます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-184">When using **AsJob**, the job is created on the local computer and the results are automatically returned to the local computer, even though the job runs on the remote computers.</span></span>

<span data-ttu-id="0ece0-185">この例では、を使用して、 `Wait-Job` `Get-Process` 3 台のリモートコンピューター上のセッションで実行されているコマンドが終了状態であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-185">This example uses `Wait-Job` to determine whether a `Get-Process` command running in the sessions on three remote computers is in a terminating state.</span></span>

<span data-ttu-id="0ece0-186">最初のコマンドは、3台のコンピューター上に **PSSession** オブジェクトを作成し、それらを変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-186">The first command creates **PSSession** objects on three computers and stores them in the `$s` variable.</span></span>

<span data-ttu-id="0ece0-187">2番目のコマンドは、を使用して `Invoke-Command` `Get-Process` 、の3つの各セッションでを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-187">The second command uses `Invoke-Command` to run `Get-Process` in each of the three sessions in `$s`.</span></span>
<span data-ttu-id="0ece0-188">このコマンドは、 **AsJob** パラメーターを使用して、コマンドをジョブとして非同期に実行します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-188">The command uses the **AsJob** parameter to run the command asynchronously as a job.</span></span> <span data-ttu-id="0ece0-189">コマンドは、を使用して開始されたジョブと同様に、ジョブオブジェクトを返し、 `Start-Job` ジョブオブジェクトは変数に格納され `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-189">The command returns a job object, just like the jobs started by using `Start-Job`, and the job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="0ece0-190">3番目のコマンドは、パイプライン演算子 () を使用して、 `|` のジョブオブジェクトを `$j` コマンドレットに送信し `Wait-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-190">The third command uses a pipeline operator (`|`) to send the job object in `$j` to the `Wait-Job` cmdlet.</span></span> <span data-ttu-id="0ece0-191">`Invoke-Command`この場合、ジョブはローカルコンピューター上に存在するため、コマンドは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0ece0-191">An `Invoke-Command` command is not required in this case, because the job resides on the local computer.</span></span>

### <span data-ttu-id="0ece0-192">例 10: ID を持つジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="0ece0-192">Example 10: Wait for a job that has an ID</span></span>

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

<span data-ttu-id="0ece0-193">このコマンドは、ID 値が 1 であるジョブを待機します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-193">This command waits for the job with an ID value of 1.</span></span>

## <span data-ttu-id="0ece0-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0ece0-194">PARAMETERS</span></span>

### <span data-ttu-id="0ece0-195">-任意</span><span class="sxs-lookup"><span data-stu-id="0ece0-195">-Any</span></span>

<span data-ttu-id="0ece0-196">このコマンドレットがジョブオブジェクトを返し、任意のジョブが終了したときに実行を継続することを示します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-196">Indicates that this cmdlet returns the job object and continues execution when any job finishes.</span></span> <span data-ttu-id="0ece0-197">既定では、は、 `Wait-Job` 指定されたすべてのジョブが完了するまで待機してから、プロンプトを表示します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-197">By default, `Wait-Job` waits until all of the specified jobs are complete before it displays the prompt.</span></span>

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

### <span data-ttu-id="0ece0-198">-Filter</span><span class="sxs-lookup"><span data-stu-id="0ece0-198">-Filter</span></span>

<span data-ttu-id="0ece0-199">条件のハッシュテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-199">Specifies a hash table of conditions.</span></span> <span data-ttu-id="0ece0-200">このコマンドレットは、ハッシュテーブル内のすべての条件を満たすジョブを待機します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-200">This cmdlet waits for jobs that satisfy all of the conditions in the hash table.</span></span> <span data-ttu-id="0ece0-201">ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-201">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="0ece0-202">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-202">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="0ece0-203">コマンドレットを使用して作成されたジョブなど、標準ジョブでは機能しません `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="0ece0-203">It does not work on standard jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="0ece0-204">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ece0-204">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="0ece0-205">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0ece0-205">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0ece0-206">-Force</span><span class="sxs-lookup"><span data-stu-id="0ece0-206">-Force</span></span>

<span data-ttu-id="0ece0-207">このコマンドレットが中断または切断状態のジョブを引き続き待機することを示します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-207">Indicates that this cmdlet continues to wait for jobs in the Suspended or Disconnected state.</span></span> <span data-ttu-id="0ece0-208">既定では、 `Wait-Job` ジョブが次のいずれかの状態にある場合、は待機を返すか、または終了します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-208">By default, `Wait-Job` returns, or ends the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="0ece0-209">完了</span><span class="sxs-lookup"><span data-stu-id="0ece0-209">Completed</span></span>
- <span data-ttu-id="0ece0-210">失敗</span><span class="sxs-lookup"><span data-stu-id="0ece0-210">Failed</span></span>
- <span data-ttu-id="0ece0-211">停止済み</span><span class="sxs-lookup"><span data-stu-id="0ece0-211">Stopped</span></span>
- <span data-ttu-id="0ece0-212">Suspended</span><span class="sxs-lookup"><span data-stu-id="0ece0-212">Suspended</span></span>
- <span data-ttu-id="0ece0-213">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="0ece0-213">Disconnected</span></span>

<span data-ttu-id="0ece0-214">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0ece0-214">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0ece0-215">-Id</span><span class="sxs-lookup"><span data-stu-id="0ece0-215">-Id</span></span>

<span data-ttu-id="0ece0-216">このコマンドレットが待機するジョブの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-216">Specifies an array of IDs of jobs for which this cmdlet waits.</span></span>

<span data-ttu-id="0ece0-217">ID は、現在のセッションでジョブを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="0ece0-217">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="0ece0-218">インスタンス ID よりも覚えやすく、入力も簡単ですが、現在のセッションでのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="0ece0-218">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="0ece0-219">1つ以上の Id をコンマで区切って入力できます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-219">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="0ece0-220">ジョブの ID を検索するには、「」と入力 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-220">To find the ID of a job, type `Get-Job`.</span></span>

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

### <span data-ttu-id="0ece0-221">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="0ece0-221">-InstanceId</span></span>

<span data-ttu-id="0ece0-222">このコマンドレットが待機するジョブのインスタンス Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-222">Specifies an array of instance IDs of jobs for which this cmdlet waits.</span></span> <span data-ttu-id="0ece0-223">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="0ece0-223">The default is all jobs.</span></span>

<span data-ttu-id="0ece0-224">インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="0ece0-224">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="0ece0-225">ジョブのインスタンス ID を検索するには、を使用 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-225">To find the instance ID of a job, use `Get-Job`.</span></span>

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

### <span data-ttu-id="0ece0-226">-ジョブ</span><span class="sxs-lookup"><span data-stu-id="0ece0-226">-Job</span></span>

<span data-ttu-id="0ece0-227">このコマンドレットが待機するジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-227">Specifies the jobs for which this cmdlet waits.</span></span> <span data-ttu-id="0ece0-228">ジョブ オブジェクトが格納されている変数、またはジョブ オブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-228">Enter a variable that contains the job objects or a command that gets the job objects.</span></span> <span data-ttu-id="0ece0-229">パイプライン演算子を使用して、ジョブオブジェクトをコマンドレットに渡すこともでき `Wait-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-229">You can also use a pipeline operator to send job objects to the `Wait-Job` cmdlet.</span></span> <span data-ttu-id="0ece0-230">既定では、は、 `Wait-Job` 現在のセッションで作成されたすべてのジョブを待機します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-230">By default, `Wait-Job` waits for all jobs created in the current session.</span></span>

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

### <span data-ttu-id="0ece0-231">-Name</span><span class="sxs-lookup"><span data-stu-id="0ece0-231">-Name</span></span>

<span data-ttu-id="0ece0-232">このコマンドレットが待機するジョブのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-232">Specifies friendly names of jobs for which this cmdlet waits.</span></span>

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

### <span data-ttu-id="0ece0-233">-状態</span><span class="sxs-lookup"><span data-stu-id="0ece0-233">-State</span></span>

<span data-ttu-id="0ece0-234">ジョブの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-234">Specifies a job state.</span></span> <span data-ttu-id="0ece0-235">このコマンドレットは、指定された状態のジョブのみを待機します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-235">This cmdlet waits only for jobs in the specified state.</span></span> <span data-ttu-id="0ece0-236">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0ece0-236">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0ece0-237">NotStarted</span><span class="sxs-lookup"><span data-stu-id="0ece0-237">NotStarted</span></span>
- <span data-ttu-id="0ece0-238">実行中</span><span class="sxs-lookup"><span data-stu-id="0ece0-238">Running</span></span>
- <span data-ttu-id="0ece0-239">完了</span><span class="sxs-lookup"><span data-stu-id="0ece0-239">Completed</span></span>
- <span data-ttu-id="0ece0-240">失敗</span><span class="sxs-lookup"><span data-stu-id="0ece0-240">Failed</span></span>
- <span data-ttu-id="0ece0-241">停止済み</span><span class="sxs-lookup"><span data-stu-id="0ece0-241">Stopped</span></span>
- <span data-ttu-id="0ece0-242">［ブロック済み］</span><span class="sxs-lookup"><span data-stu-id="0ece0-242">Blocked</span></span>
- <span data-ttu-id="0ece0-243">Suspended</span><span class="sxs-lookup"><span data-stu-id="0ece0-243">Suspended</span></span>
- <span data-ttu-id="0ece0-244">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="0ece0-244">Disconnected</span></span>
- <span data-ttu-id="0ece0-245">中断中</span><span class="sxs-lookup"><span data-stu-id="0ece0-245">Suspending</span></span>
- <span data-ttu-id="0ece0-246">停止中</span><span class="sxs-lookup"><span data-stu-id="0ece0-246">Stopping</span></span>

<span data-ttu-id="0ece0-247">ジョブの状態の詳細については、「 [Jobstate 列挙型](/dotnet/api/system.management.automation.jobstate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ece0-247">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

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

### <span data-ttu-id="0ece0-248">-タイムアウト</span><span class="sxs-lookup"><span data-stu-id="0ece0-248">-Timeout</span></span>

<span data-ttu-id="0ece0-249">各ジョブの最大待機時間を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-249">Specifies the maximum wait time for each job, in seconds.</span></span> <span data-ttu-id="0ece0-250">既定値は-1 です。このコマンドレットは、ジョブが完了するまで待機することを示します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-250">The default value, -1, indicates that the cmdlet waits until the job finishes.</span></span> <span data-ttu-id="0ece0-251">コマンドではなくコマンドを送信すると、タイミングが開始 `Wait-Job` され `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-251">The timing starts when you submit the `Wait-Job` command, not the `Start-Job` command.</span></span>

<span data-ttu-id="0ece0-252">この時間が経過すると、ジョブがまだ実行されている場合でも、待機が終了し、実行が継続されます。</span><span class="sxs-lookup"><span data-stu-id="0ece0-252">If this time is exceeded, the wait ends and execution continues, even if the job is still running.</span></span>
<span data-ttu-id="0ece0-253">このコマンドでは、エラーメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="0ece0-253">The command does not display any error message.</span></span>

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

### <span data-ttu-id="0ece0-254">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="0ece0-254">CommonParameters</span></span>

<span data-ttu-id="0ece0-255">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="0ece0-255">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0ece0-256">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ece0-256">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0ece0-257">入力</span><span class="sxs-lookup"><span data-stu-id="0ece0-257">INPUTS</span></span>

### <span data-ttu-id="0ece0-258">System. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="0ece0-258">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="0ece0-259">パイプを使用してジョブオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-259">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="0ece0-260">出力</span><span class="sxs-lookup"><span data-stu-id="0ece0-260">OUTPUTS</span></span>

### <span data-ttu-id="0ece0-261">システムの管理. PSRemotingJob</span><span class="sxs-lookup"><span data-stu-id="0ece0-261">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="0ece0-262">このコマンドレットは、終了状態のジョブを表すジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-262">This cmdlet returns job objects that represent the jobs in a terminating state.</span></span> <span data-ttu-id="0ece0-263">**Timeout** パラメーターの値を超えたことが原因で待機が終了した場合、 `Wait-Job` はオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="0ece0-263">If the wait ends because the value of the **Timeout** parameter is exceeded, `Wait-Job` does not return any objects.</span></span>

## <span data-ttu-id="0ece0-264">注</span><span class="sxs-lookup"><span data-stu-id="0ece0-264">NOTES</span></span>

<span data-ttu-id="0ece0-265">既定では、 `Wait-Job` ジョブが次のいずれかの状態にある場合、は待機を返すか、または終了します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-265">By default, `Wait-Job` returns, or ends the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="0ece0-266">完了</span><span class="sxs-lookup"><span data-stu-id="0ece0-266">Completed</span></span>
- <span data-ttu-id="0ece0-267">失敗</span><span class="sxs-lookup"><span data-stu-id="0ece0-267">Failed</span></span>
- <span data-ttu-id="0ece0-268">停止済み</span><span class="sxs-lookup"><span data-stu-id="0ece0-268">Stopped</span></span>
- <span data-ttu-id="0ece0-269">Suspended</span><span class="sxs-lookup"><span data-stu-id="0ece0-269">Suspended</span></span>
- <span data-ttu-id="0ece0-270">`Wait-Job`中断されたジョブと切断されたジョブを引き続き待機するために切断された場合は、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="0ece0-270">Disconnected To direct `Wait-Job` to continue to wait for Suspended and Disconnected jobs, use the **Force** parameter.</span></span>

## <span data-ttu-id="0ece0-271">関連リンク</span><span class="sxs-lookup"><span data-stu-id="0ece0-271">RELATED LINKS</span></span>

[<span data-ttu-id="0ece0-272">Get-Job</span><span class="sxs-lookup"><span data-stu-id="0ece0-272">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="0ece0-273">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="0ece0-273">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="0ece0-274">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="0ece0-274">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="0ece0-275">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="0ece0-275">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="0ece0-276">Start-Job</span><span class="sxs-lookup"><span data-stu-id="0ece0-276">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="0ece0-277">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="0ece0-277">Stop-Job</span></span>](Stop-Job.md)
