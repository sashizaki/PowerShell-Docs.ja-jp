---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/wait-job?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Job
ms.openlocfilehash: 93673fe82ebb87f160fc0a20acdc5c766a446445
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387177"
---
# <span data-ttu-id="4484b-103">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="4484b-103">Wait-Job</span></span>

## <span data-ttu-id="4484b-104">概要</span><span class="sxs-lookup"><span data-stu-id="4484b-104">SYNOPSIS</span></span>
<span data-ttu-id="4484b-105">セッションで実行されている PowerShell バックグラウンドジョブの1つまたはすべてが完了するまで、コマンドプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="4484b-105">Suppresses the command prompt until one or all of the PowerShell background jobs running in the session are completed.</span></span>

## <span data-ttu-id="4484b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4484b-106">SYNTAX</span></span>

### <span data-ttu-id="4484b-107">SessionIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="4484b-107">SessionIdParameterSet (Default)</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="4484b-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="4484b-108">JobParameterSet</span></span>

```
Wait-Job [-Job] <Job[]> [-Any] [-Timeout <Int32>] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="4484b-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="4484b-109">NameParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="4484b-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="4484b-110">InstanceIdParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="4484b-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="4484b-111">StateParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="4484b-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="4484b-112">FilterParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="4484b-113">Description</span><span class="sxs-lookup"><span data-stu-id="4484b-113">DESCRIPTION</span></span>

<span data-ttu-id="4484b-114">`Wait-Job`コマンドレットは、PowerShell のバックグラウンドジョブが完了するのを待ってから、コマンドプロンプトを表示します。</span><span class="sxs-lookup"><span data-stu-id="4484b-114">The `Wait-Job` cmdlet waits for PowerShell background jobs to finish before it displays the command prompt.</span></span> <span data-ttu-id="4484b-115">任意のバックグラウンド ジョブまたはすべてのバックグラウンド ジョブが完了まで待機できます。さらに、ジョブの最大待機時間を設定できます。</span><span class="sxs-lookup"><span data-stu-id="4484b-115">You can wait until any background job is complete, or until all background jobs are complete, and you can set a maximum wait time for the job.</span></span>

<span data-ttu-id="4484b-116">ジョブのコマンドが完了すると、によって `Wait-Job` コマンドプロンプトが表示され、別のコマンドにパイプできるようにジョブオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="4484b-116">When the commands in the job are complete, `Wait-Job` displays the command prompt and returns a job object so that you can pipe it to another command.</span></span>

<span data-ttu-id="4484b-117">コマンドレットまたはコマンドレット `Wait-Job` の AsJob パラメーターを使用して開始されたジョブなど、バックグラウンドジョブを待機するには、コマンドレットを使用し `Start-Job` **AsJob** `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-117">You can use `Wait-Job` cmdlet to wait for background jobs, such as those that were started by using the `Start-Job` cmdlet or the **AsJob** parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="4484b-118">Windows PowerShell のバックグラウンド ジョブの詳細については、「[about_Jobs](./about/about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4484b-118">For more information about Windows PowerShell background jobs, see [about_Jobs](./about/about_Jobs.md).</span></span>

<span data-ttu-id="4484b-119">Windows PowerShell 3.0 以降では、 `Wait-Job` コマンドレットは、ワークフロージョブやスケジュールされたジョブのインスタンスなどのカスタムジョブの種類も待機します。</span><span class="sxs-lookup"><span data-stu-id="4484b-119">Starting in Windows PowerShell 3.0, the `Wait-Job` cmdlet also waits for custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="4484b-120">が特定の種類のジョブを待機できるようにするには、コマンドレットを実行する前に、コマンドレットを使用するか、 `Wait-Job` `Get-Job` `Import-Module` またはモジュールのコマンドレットを使用して、カスタムジョブの種類をサポートするモジュールをセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="4484b-120">To enable `Wait-Job` to wait for jobs of a particular type, import the module that supports the custom job type into the session before you run the `Get-Job` cmdlet, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="4484b-121">特定のカスタム ジョブの種類については、カスタムのジョブの種類機能のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4484b-121">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="4484b-122">例</span><span class="sxs-lookup"><span data-stu-id="4484b-122">EXAMPLES</span></span>

### <span data-ttu-id="4484b-123">例 1: すべてのジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="4484b-123">Example 1: Wait for all jobs</span></span>

```powershell
Get-Job | Wait-Job
```

<span data-ttu-id="4484b-124">このコマンドは、セッションで実行されているすべてのバックグラウンドジョブが完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="4484b-124">This command waits for all of the background jobs running in the session to finish.</span></span>

### <span data-ttu-id="4484b-125">例 2: Start-Job を使用してリモートコンピューターで開始されたジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="4484b-125">Example 2: Wait for jobs started on remote computers by using Start-Job</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
Invoke-Command -Session $s -ScriptBlock {Start-Job -Name Date1 -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -Command {Wait-Job -Name Date1}
$done.Count
```

```Output
3
```

<span data-ttu-id="4484b-126">この例では、コマンドレットを使用して、 `Wait-Job` リモートコンピューターで開始されたジョブと共にコマンドレットを使用する方法を示し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-126">This example shows how to use the `Wait-Job` cmdlet with jobs started on remote computers by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="4484b-127">コマンド `Start-Job` レットを使用して、コマンドとコマンドの両方を `Wait-Job` リモートコンピューターに送信し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-127">Both `Start-Job` and `Wait-Job` commands are submitted to the remote computer by using the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="4484b-128">この例では `Wait-Job` 、を使用し `Get-Date` て、3台の異なるコンピューターでバックグラウンドジョブとして実行されているコマンドが終了しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="4484b-128">This example uses `Wait-Job` to determine whether a `Get-Date` command running as a background job on three different computers is finished.</span></span>

<span data-ttu-id="4484b-129">最初のコマンドは、3台のリモートコンピューターそれぞれに Windows PowerShell セッション ( **PSSession** ) を作成し、それらを変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-129">The first command creates a Windows PowerShell session ( **PSSession** ) on each of the three remote computers and stores them in the `$s` variable.</span></span>

<span data-ttu-id="4484b-130">2番目のコマンドは、を使用して `Invoke-Command` `Start-Job` 、の3つの各セッションでを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-130">The second command uses `Invoke-Command` to run `Start-Job` in each of the three sessions in `$s`.</span></span>
<span data-ttu-id="4484b-131">すべてのジョブには、Date1 という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="4484b-131">All of the jobs are named Date1.</span></span>

<span data-ttu-id="4484b-132">3番目のコマンドは、を使用して `Invoke-Command` を実行し `Wait-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-132">The third command uses `Invoke-Command` to run `Wait-Job`.</span></span> <span data-ttu-id="4484b-133">このコマンドは、各コンピューター上の Date1 ジョブが完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="4484b-133">This command waits for the Date1 jobs on each computer to finish.</span></span> <span data-ttu-id="4484b-134">これにより、ジョブオブジェクトの結果のコレクション (配列) が変数に格納され `$done` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-134">It stores the resulting collection (array) of job objects in the `$done` variable.</span></span>

<span data-ttu-id="4484b-135">4番目のコマンドは、変数内のジョブオブジェクトの配列の **Count** プロパティを使用して `$done` 、完了したジョブの数を確認します。</span><span class="sxs-lookup"><span data-stu-id="4484b-135">The fourth command uses the **Count** property of the array of job objects in the `$done` variable to determine how many of the jobs are finished.</span></span>

### <span data-ttu-id="4484b-136">例 3: 最初のバックグラウンドジョブがいつ終了するかを判断する</span><span class="sxs-lookup"><span data-stu-id="4484b-136">Example 3: Determine when the first background job finishes</span></span>

```powershell
$s = New-PSSession (Get-Content Machines.txt)
$c = 'Get-EventLog -LogName System | where {$_.EntryType -eq "error" --and $_.Source -eq "LSASRV"} | Out-File Errors.txt'
Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$Using:c}
Invoke-Command -Session $s -ScriptBlock {Wait-Job -Any}
```

<span data-ttu-id="4484b-137">この例では、の **任意** のパラメーターを使用して、 `Wait-Job` 現在のセッションで実行されている多くのバックグラウンドジョブが完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4484b-137">This example uses the **Any** parameter of `Wait-Job` to determine when the first of many background jobs running in the current session are completed.</span></span> <span data-ttu-id="4484b-138">また、コマンドレットを使用して `Wait-Job` リモートジョブの完了を待機する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="4484b-138">It also shows how to use the `Wait-Job` cmdlet to wait for remote jobs to finish.</span></span>

<span data-ttu-id="4484b-139">最初のコマンドは、Machines.txt ファイルに一覧表示されている各コンピューター上に **pssession** を作成し、その **pssession** オブジェクトを変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-139">The first command creates a **PSSession** on each of the computers listed in the Machines.txt file and stores the **PSSession** objects in the `$s` variable.</span></span> <span data-ttu-id="4484b-140">このコマンドは、コマンドレットを使用して、 `Get-Content` ファイルの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="4484b-140">The command uses the `Get-Content` cmdlet to get the contents of the file.</span></span> <span data-ttu-id="4484b-141">コマンドは、 `Get-Content` コマンドの前に実行されるように、かっこで囲まれてい `New-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-141">The `Get-Content` command is enclosed in parentheses to make sure that it runs before the `New-PSSession` command.</span></span>

<span data-ttu-id="4484b-142">2番目のコマンドは、 `Get-EventLog` コマンド文字列を引用符で囲んで変数に格納し `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-142">The second command stores a `Get-EventLog` command string, in quotation marks, in the `$c` variable.</span></span>

<span data-ttu-id="4484b-143">3番目のコマンドは、 `Invoke-Command` コマンドレットを使用して `Start-Job` 、の各セッションでを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-143">The third command uses `Invoke-Command` cmdlet to run `Start-Job` in each of the sessions in `$s`.</span></span>
<span data-ttu-id="4484b-144">コマンドは、 `Start-Job` 変数でコマンドを実行するバックグラウンドジョブを開始し `Get-EventLog` `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-144">The `Start-Job` command starts a background job that runs the `Get-EventLog` command in the `$c` variable.</span></span>

<span data-ttu-id="4484b-145">このコマンドは、 **Using** スコープ修飾子を使用して、 `$c` 変数がローカルコンピューター上で定義されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="4484b-145">The command uses the **Using** scope modifier to indicate that the `$c` variable was defined on the local computer.</span></span> <span data-ttu-id="4484b-146">**Using** スコープ修飾子は、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4484b-146">The **Using** scope modifier is introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="4484b-147">スコープ修飾子の **使用** の詳細については、「 [about_Remote_Variables](./about/about_Remote_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4484b-147">For more information about the **Using** scope modifier, see [about_Remote_Variables](./about/about_Remote_Variables.md).</span></span>

<span data-ttu-id="4484b-148">4番目のコマンドは、を使用し `Invoke-Command` `Wait-Job` て、セッションでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4484b-148">The fourth command uses `Invoke-Command` to run a `Wait-Job` command in the sessions.</span></span> <span data-ttu-id="4484b-149">また、 **Any** パラメーターを使用して、リモートコンピューター上の最初のジョブが完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="4484b-149">It uses the **Any** parameter to wait until the first job on the remote computers is completed.</span></span>

### <span data-ttu-id="4484b-150">例 4: リモートコンピューター上のジョブの待機時間を設定する</span><span class="sxs-lookup"><span data-stu-id="4484b-150">Example 4: Set a wait time for jobs on remote computers</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
$jobs = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -ScriptBlock {Wait-Job -Timeout 30}
```

<span data-ttu-id="4484b-151">この例では、の **Timeout** パラメーターを使用して、 `Wait-Job` リモートコンピューターで実行されているジョブの最大待機時間を設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4484b-151">This example shows how to use the **Timeout** parameter of `Wait-Job` to set a maximum wait time for the jobs running on remote computers.</span></span>

<span data-ttu-id="4484b-152">最初のコマンドは、3台のリモートコンピューター (Server01、Server02、および Server03) のそれぞれに **pssession** を作成し、その後、 **pssession** オブジェクトを変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-152">The first command creates a **PSSession** on each of three remote computers (Server01, Server02, and Server03), and then stores the **PSSession** objects in the `$s` variable.</span></span>

<span data-ttu-id="4484b-153">2番目のコマンドは、を使用して、の `Invoke-Command` `Start-Job` 各 **PSSession** オブジェクトでを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-153">The second command uses `Invoke-Command` to run `Start-Job` in each of the **PSSession** objects in `$s`.</span></span> <span data-ttu-id="4484b-154">結果として得られるジョブオブジェクトが変数に格納され `$jobs` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-154">It stores the resulting job objects in the `$jobs` variable.</span></span>

<span data-ttu-id="4484b-155">3番目のコマンドは、を使用して `Invoke-Command` `Wait-Job` 、の各セッションでを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-155">The third command uses `Invoke-Command` to run `Wait-Job` in each of the sessions in `$s`.</span></span> <span data-ttu-id="4484b-156">`Wait-Job`コマンドは、すべてのコマンドが30秒以内に完了したかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="4484b-156">The `Wait-Job` command determines whether all of the commands have completed within 30 seconds.</span></span> <span data-ttu-id="4484b-157">**タイムアウト** パラメーターを30に設定して最大待機時間を設定し、コマンドの結果を変数に格納し `$done` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-157">It uses the **Timeout** parameter with a value of 30 to establish the maximum wait time, and then stores the results of the command in the `$done` variable.</span></span>

<span data-ttu-id="4484b-158">この場合に、30 秒後に Server02 コンピューター上のコマンドのみが完了しました。</span><span class="sxs-lookup"><span data-stu-id="4484b-158">In this case, after 30 seconds, only the command on the Server02 computer has completed.</span></span> <span data-ttu-id="4484b-159">`Wait-Job` 待機を終了し、コマンドプロンプトを表示して、完了したジョブを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="4484b-159">`Wait-Job` ends the wait, displays the command prompt, and returns the object that represents the job that was completed.</span></span>

<span data-ttu-id="4484b-160">変数には、 `$done` Server02 で実行されたジョブを表す job オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4484b-160">The `$done` variable contains a job object that represents the job that ran on Server02.</span></span>

### <span data-ttu-id="4484b-161">例 5: 複数のジョブのいずれかが完了するまで待機する</span><span class="sxs-lookup"><span data-stu-id="4484b-161">Example 5: Wait until one of several jobs finishes</span></span>

```powershell
Wait-Job -id 1,2,5 -Any
```

<span data-ttu-id="4484b-162">このコマンドは、3つのジョブを Id で識別し、いずれかのジョブが完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="4484b-162">This command identifies three jobs by their IDs and waits until any one of them are completed.</span></span>
<span data-ttu-id="4484b-163">最初のジョブが完了すると、コマンドプロンプトが返されます。</span><span class="sxs-lookup"><span data-stu-id="4484b-163">The command prompt returns when the first job finishes.</span></span>

### <span data-ttu-id="4484b-164">例 6: 期間を待機してから、ジョブをバックグラウンドで続行することを許可する</span><span class="sxs-lookup"><span data-stu-id="4484b-164">Example 6: Wait for a period, then allow job to continue in background</span></span>

```powershell
Wait-Job -Name "DailyLog" -Timeout 120
```

<span data-ttu-id="4484b-165">このコマンドは、DailyLog ジョブが完了するまで120秒 (2 分) 待機します。</span><span class="sxs-lookup"><span data-stu-id="4484b-165">This command waits 120 seconds (two minutes) for the DailyLog job to finish.</span></span> <span data-ttu-id="4484b-166">ジョブが次の2分以内に完了しなかった場合は、コマンドプロンプトが返され、ジョブはバックグラウンドで実行され続けます。</span><span class="sxs-lookup"><span data-stu-id="4484b-166">If the job does not finish in the next two minutes, the command prompt returns anyway, and the job continues to run in the background.</span></span>

### <span data-ttu-id="4484b-167">例 7: 名前でジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="4484b-167">Example 7: Wait for a job by name</span></span>

```powershell
Wait-Job -Name "Job3"
```

<span data-ttu-id="4484b-168">このコマンドは、ジョブ名を使用して、待機するジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="4484b-168">This command uses the job name to identify the job for which to wait.</span></span>

### <span data-ttu-id="4484b-169">例 8: Start-Job で開始されたローカルコンピューター上のジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="4484b-169">Example 8: Wait for jobs on local computer started with Start-Job</span></span>

```powershell
$j = Start-Job -ScriptBlock {Get-ChildItem *.ps1| where {$_lastwritetime -gt ((Get-Date) - (New-TimeSpan -Days 7))}}
$j | Wait-Job
```

<span data-ttu-id="4484b-170">この例では、を使用して、 `Wait-Job` ローカルコンピューターで開始されたジョブと共にコマンドレットを使用する方法を示し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-170">This example shows how to use the `Wait-Job` cmdlet with jobs started on the local computer by using `Start-Job`.</span></span>

<span data-ttu-id="4484b-171">これらのコマンドは、過去 1 週間に追加または更新された Windows PowerShell スクリプト ファイルを取得するジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="4484b-171">These commands start a job that gets the Windows PowerShell script files that were added or updated in the last week.</span></span>

<span data-ttu-id="4484b-172">最初のコマンドは、を使用して、 `Start-Job` ローカルコンピューター上でバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="4484b-172">The first command uses `Start-Job` to start a background job on the local computer.</span></span> <span data-ttu-id="4484b-173">このジョブは、 `Get-ChildItem` 過去1週間に追加または更新されたファイル名拡張子が ps1 のすべてのファイルを取得するコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4484b-173">The job runs a `Get-ChildItem` command that gets all of the files that have a .ps1 file name extension that were added or updated in the last week.</span></span>

<span data-ttu-id="4484b-174">3番目のコマンドは、を使用して `Wait-Job` 、ジョブが完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="4484b-174">The third command uses `Wait-Job` to wait until the job is completed.</span></span> <span data-ttu-id="4484b-175">ジョブが完了すると、ジョブに関する情報を含むジョブオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4484b-175">When the job finishes, the command displays the job object, which contains information about the job.</span></span>

### <span data-ttu-id="4484b-176">例 9: Invoke-Command を使用してリモートコンピューターで開始されたジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="4484b-176">Example 9: Wait for jobs started on remote computers by using Invoke-Command</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
$j = Invoke-Command -Session $s -ScriptBlock {Get-Process} -AsJob
$j | Wait-Job
```

<span data-ttu-id="4484b-177">この例では `Wait-Job` 、の **AsJob** パラメーターを使用して、リモートコンピューターで開始されたジョブと共にを使用する方法を示し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-177">This example shows how to use `Wait-Job` with jobs started on remote computers by using the **AsJob** parameter of `Invoke-Command`.</span></span> <span data-ttu-id="4484b-178">**AsJob** を使用する場合、ジョブはローカルコンピューター上に作成され、そのジョブがリモートコンピューター上で実行されている場合でも、結果はローカルコンピューターに自動的に返されます。</span><span class="sxs-lookup"><span data-stu-id="4484b-178">When using **AsJob** , the job is created on the local computer and the results are automatically returned to the local computer, even though the job runs on the remote computers.</span></span>

<span data-ttu-id="4484b-179">この例では、を使用して `Wait-Job` `Get-Process` 、3台のリモートコンピューター上のセッションで実行されているコマンドが完了したかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="4484b-179">This example uses `Wait-Job` to determine whether a `Get-Process` command running in the sessions on three remote computers is completed.</span></span>

<span data-ttu-id="4484b-180">最初のコマンドは、3台のコンピューター上に **PSSession** オブジェクトを作成し、それらを変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-180">The first command creates **PSSession** objects on three computers and stores them in the `$s` variable.</span></span>

<span data-ttu-id="4484b-181">2番目のコマンドは、を使用して `Invoke-Command` `Get-Process` 、の3つの各セッションでを実行し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-181">The second command uses `Invoke-Command` to run `Get-Process` in each of the three sessions in `$s`.</span></span>
<span data-ttu-id="4484b-182">このコマンドは、 **AsJob** パラメーターを使用して、バックグラウンドジョブとしてコマンドを非同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="4484b-182">The command uses the **AsJob** parameter to run the command asynchronously as a background job.</span></span> <span data-ttu-id="4484b-183">コマンドは、を使用して開始されたジョブと同様に、ジョブオブジェクトを返し、 `Start-Job` ジョブオブジェクトは変数に格納され `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-183">The command returns a job object, just like the jobs started by using `Start-Job`, and the job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="4484b-184">3番目のコマンドは、パイプライン演算子 () を使用して、 `|` のジョブオブジェクトを `$j` コマンドレットに送信し `Wait-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-184">The third command uses a pipeline operator (`|`) to send the job object in `$j` to the `Wait-Job` cmdlet.</span></span> <span data-ttu-id="4484b-185">`Invoke-Command`この場合、ジョブはローカルコンピューター上に存在するため、コマンドは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4484b-185">An `Invoke-Command` command is not required in this case, because the job resides on the local computer.</span></span>

### <span data-ttu-id="4484b-186">例 10: ID を持つジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="4484b-186">Example 10: Wait for a job that has an ID</span></span>

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

<span data-ttu-id="4484b-187">このコマンドは、ID 値が 1 であるジョブを待機します。</span><span class="sxs-lookup"><span data-stu-id="4484b-187">This command waits for the job with an ID value of 1.</span></span>

## <span data-ttu-id="4484b-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4484b-188">PARAMETERS</span></span>

### <span data-ttu-id="4484b-189">-任意</span><span class="sxs-lookup"><span data-stu-id="4484b-189">-Any</span></span>

<span data-ttu-id="4484b-190">このコマンドレットによってコマンドプロンプトが表示され、ジョブの完了時にジョブオブジェクトが返されることを示します。</span><span class="sxs-lookup"><span data-stu-id="4484b-190">Indicates that this cmdlet displays the command prompt, and returns the job object, when any job finishes.</span></span> <span data-ttu-id="4484b-191">既定では、は、 `Wait-Job` 指定されたすべてのジョブが完了するまで待機してから、プロンプトを表示します。</span><span class="sxs-lookup"><span data-stu-id="4484b-191">By default, `Wait-Job` waits until all of the specified jobs are complete before it displays the prompt.</span></span>

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

### <span data-ttu-id="4484b-192">-Filter</span><span class="sxs-lookup"><span data-stu-id="4484b-192">-Filter</span></span>

<span data-ttu-id="4484b-193">条件のハッシュテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="4484b-193">Specifies a hash table of conditions.</span></span> <span data-ttu-id="4484b-194">このコマンドレットは、ハッシュテーブル内のすべての条件を満たすジョブを待機します。</span><span class="sxs-lookup"><span data-stu-id="4484b-194">This cmdlet waits for jobs that satisfy all of the conditions in the hash table.</span></span> <span data-ttu-id="4484b-195">ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="4484b-195">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="4484b-196">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="4484b-196">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="4484b-197">コマンドレットを使用して作成されたものなど、標準のバックグラウンドジョブでは機能しません `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="4484b-197">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="4484b-198">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4484b-198">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="4484b-199">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4484b-199">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4484b-200">-Force</span><span class="sxs-lookup"><span data-stu-id="4484b-200">-Force</span></span>

<span data-ttu-id="4484b-201">このコマンドレットが中断または切断状態のジョブを引き続き待機することを示します。</span><span class="sxs-lookup"><span data-stu-id="4484b-201">Indicates that this cmdlet continues to wait for jobs in the Suspended or Disconnected state.</span></span> <span data-ttu-id="4484b-202">既定では、 `Wait-Job` ジョブが次のいずれかの状態にある場合、は待機を返すか、または終了します。</span><span class="sxs-lookup"><span data-stu-id="4484b-202">By default, `Wait-Job` returns, or ends the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="4484b-203">完了</span><span class="sxs-lookup"><span data-stu-id="4484b-203">Completed</span></span>
- <span data-ttu-id="4484b-204">失敗</span><span class="sxs-lookup"><span data-stu-id="4484b-204">Failed</span></span>
- <span data-ttu-id="4484b-205">停止済み</span><span class="sxs-lookup"><span data-stu-id="4484b-205">Stopped</span></span>
- <span data-ttu-id="4484b-206">Suspended</span><span class="sxs-lookup"><span data-stu-id="4484b-206">Suspended</span></span>
- <span data-ttu-id="4484b-207">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="4484b-207">Disconnected</span></span>

<span data-ttu-id="4484b-208">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4484b-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4484b-209">-Id</span><span class="sxs-lookup"><span data-stu-id="4484b-209">-Id</span></span>

<span data-ttu-id="4484b-210">このコマンドレットが待機するジョブの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="4484b-210">Specifies an array of IDs of jobs for which this cmdlet waits.</span></span>

<span data-ttu-id="4484b-211">ID は、現在のセッションでジョブを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="4484b-211">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="4484b-212">インスタンス ID よりも覚えやすく、入力も簡単ですが、現在のセッションでのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="4484b-212">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="4484b-213">1つ以上の Id をコンマで区切って入力できます。</span><span class="sxs-lookup"><span data-stu-id="4484b-213">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="4484b-214">ジョブの ID を検索するには、「」と入力 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="4484b-214">To find the ID of a job, type `Get-Job`.</span></span>

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

### <span data-ttu-id="4484b-215">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="4484b-215">-InstanceId</span></span>

<span data-ttu-id="4484b-216">このコマンドレットが待機するジョブのインスタンス Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="4484b-216">Specifies an array of instance IDs of jobs for which this cmdlet waits.</span></span> <span data-ttu-id="4484b-217">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="4484b-217">The default is all jobs.</span></span>

<span data-ttu-id="4484b-218">インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="4484b-218">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="4484b-219">ジョブのインスタンス ID を検索するには、を使用 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="4484b-219">To find the instance ID of a job, use `Get-Job`.</span></span>

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

### <span data-ttu-id="4484b-220">-ジョブ</span><span class="sxs-lookup"><span data-stu-id="4484b-220">-Job</span></span>

<span data-ttu-id="4484b-221">このコマンドレットが待機するジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="4484b-221">Specifies the jobs for which this cmdlet waits.</span></span> <span data-ttu-id="4484b-222">ジョブ オブジェクトが格納されている変数、またはジョブ オブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="4484b-222">Enter a variable that contains the job objects or a command that gets the job objects.</span></span> <span data-ttu-id="4484b-223">パイプライン演算子を使用して、ジョブオブジェクトをコマンドレットに渡すこともでき `Wait-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-223">You can also use a pipeline operator to send job objects to the `Wait-Job` cmdlet.</span></span> <span data-ttu-id="4484b-224">既定では、は、 `Wait-Job` 現在のセッションで作成されたすべてのジョブを待機します。</span><span class="sxs-lookup"><span data-stu-id="4484b-224">By default, `Wait-Job` waits for all jobs created in the current session.</span></span>

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

### <span data-ttu-id="4484b-225">-Name</span><span class="sxs-lookup"><span data-stu-id="4484b-225">-Name</span></span>

<span data-ttu-id="4484b-226">このコマンドレットが待機するジョブのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4484b-226">Specifies friendly names of jobs for which this cmdlet waits.</span></span>

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

### <span data-ttu-id="4484b-227">-状態</span><span class="sxs-lookup"><span data-stu-id="4484b-227">-State</span></span>

<span data-ttu-id="4484b-228">ジョブの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="4484b-228">Specifies a job state.</span></span> <span data-ttu-id="4484b-229">このコマンドレットは、指定された状態のジョブのみを待機します。</span><span class="sxs-lookup"><span data-stu-id="4484b-229">This cmdlet waits only for jobs in the specified state.</span></span> <span data-ttu-id="4484b-230">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4484b-230">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="4484b-231">NotStarted</span><span class="sxs-lookup"><span data-stu-id="4484b-231">NotStarted</span></span>
- <span data-ttu-id="4484b-232">実行中</span><span class="sxs-lookup"><span data-stu-id="4484b-232">Running</span></span>
- <span data-ttu-id="4484b-233">完了</span><span class="sxs-lookup"><span data-stu-id="4484b-233">Completed</span></span>
- <span data-ttu-id="4484b-234">失敗</span><span class="sxs-lookup"><span data-stu-id="4484b-234">Failed</span></span>
- <span data-ttu-id="4484b-235">停止済み</span><span class="sxs-lookup"><span data-stu-id="4484b-235">Stopped</span></span>
- <span data-ttu-id="4484b-236">［ブロック済み］</span><span class="sxs-lookup"><span data-stu-id="4484b-236">Blocked</span></span>
- <span data-ttu-id="4484b-237">Suspended</span><span class="sxs-lookup"><span data-stu-id="4484b-237">Suspended</span></span>
- <span data-ttu-id="4484b-238">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="4484b-238">Disconnected</span></span>
- <span data-ttu-id="4484b-239">中断中</span><span class="sxs-lookup"><span data-stu-id="4484b-239">Suspending</span></span>
- <span data-ttu-id="4484b-240">停止中</span><span class="sxs-lookup"><span data-stu-id="4484b-240">Stopping</span></span>

<span data-ttu-id="4484b-241">ジョブの状態の詳細については、「 [Jobstate 列挙型](/dotnet/api/system.management.automation.jobstate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4484b-241">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

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

### <span data-ttu-id="4484b-242">-タイムアウト</span><span class="sxs-lookup"><span data-stu-id="4484b-242">-Timeout</span></span>

<span data-ttu-id="4484b-243">各バックグラウンドジョブの最大待機時間を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="4484b-243">Specifies the maximum wait time for each background job, in seconds.</span></span> <span data-ttu-id="4484b-244">既定値は-1 です。このコマンドレットは、ジョブが完了するまで待機することを示します。</span><span class="sxs-lookup"><span data-stu-id="4484b-244">The default value, -1, indicates that the cmdlet waits until the job finishes.</span></span> <span data-ttu-id="4484b-245">コマンドではなくコマンドを送信すると、タイミングが開始 `Wait-Job` され `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="4484b-245">The timing starts when you submit the `Wait-Job` command, not the `Start-Job` command.</span></span>

<span data-ttu-id="4484b-246">この時間を超えた場合、ジョブがまだ実行中でも、待機が終了し、コマンド プロンプトが返されます。</span><span class="sxs-lookup"><span data-stu-id="4484b-246">If this time is exceeded, the wait ends and the command prompt returns, even if the job is still running.</span></span> <span data-ttu-id="4484b-247">このコマンドでは、エラーメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="4484b-247">The command does not display any error message.</span></span>

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

### <span data-ttu-id="4484b-248">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4484b-248">CommonParameters</span></span>

<span data-ttu-id="4484b-249">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="4484b-249">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4484b-250">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4484b-250">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4484b-251">入力</span><span class="sxs-lookup"><span data-stu-id="4484b-251">INPUTS</span></span>

### <span data-ttu-id="4484b-252">System. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="4484b-252">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="4484b-253">パイプを使用してジョブオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="4484b-253">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="4484b-254">出力</span><span class="sxs-lookup"><span data-stu-id="4484b-254">OUTPUTS</span></span>

### <span data-ttu-id="4484b-255">システムの管理. PSRemotingJob</span><span class="sxs-lookup"><span data-stu-id="4484b-255">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="4484b-256">このコマンドレットは、完了したジョブを表すジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="4484b-256">This cmdlet returns job objects that represent the completed jobs.</span></span> <span data-ttu-id="4484b-257">**Timeout** パラメーターの値を超えたことが原因で待機が終了した場合、 `Wait-Job` はオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="4484b-257">If the wait ends because the value of the **Timeout** parameter is exceeded, `Wait-Job` does not return any objects.</span></span>

## <span data-ttu-id="4484b-258">注</span><span class="sxs-lookup"><span data-stu-id="4484b-258">NOTES</span></span>

<span data-ttu-id="4484b-259">既定では、 `Wait-Job` ジョブが次のいずれかの状態にある場合、は待機を返すか、または終了します。</span><span class="sxs-lookup"><span data-stu-id="4484b-259">By default, `Wait-Job` returns, or ends the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="4484b-260">完了</span><span class="sxs-lookup"><span data-stu-id="4484b-260">Completed</span></span>
- <span data-ttu-id="4484b-261">失敗</span><span class="sxs-lookup"><span data-stu-id="4484b-261">Failed</span></span>
- <span data-ttu-id="4484b-262">停止済み</span><span class="sxs-lookup"><span data-stu-id="4484b-262">Stopped</span></span>
- <span data-ttu-id="4484b-263">Suspended</span><span class="sxs-lookup"><span data-stu-id="4484b-263">Suspended</span></span>
- <span data-ttu-id="4484b-264">`Wait-Job`中断されたジョブと切断されたジョブを引き続き待機するために切断された場合は、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="4484b-264">Disconnected To direct `Wait-Job` to continue to wait for Suspended and Disconnected jobs, use the **Force** parameter.</span></span>

## <span data-ttu-id="4484b-265">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4484b-265">RELATED LINKS</span></span>

[<span data-ttu-id="4484b-266">Get-Job</span><span class="sxs-lookup"><span data-stu-id="4484b-266">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="4484b-267">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="4484b-267">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="4484b-268">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="4484b-268">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="4484b-269">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="4484b-269">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="4484b-270">Start-Job</span><span class="sxs-lookup"><span data-stu-id="4484b-270">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="4484b-271">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="4484b-271">Stop-Job</span></span>](Stop-Job.md)
