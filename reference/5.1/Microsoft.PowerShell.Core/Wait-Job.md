---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/wait-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Job
ms.openlocfilehash: acf01415c9722b6da95e70a8db1b558c3e14662b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212712"
---
# <span data-ttu-id="bbe5f-103">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="bbe5f-103">Wait-Job</span></span>

## <span data-ttu-id="bbe5f-104">概要</span><span class="sxs-lookup"><span data-stu-id="bbe5f-104">SYNOPSIS</span></span>
<span data-ttu-id="bbe5f-105">セッションで実行されている Windows PowerShell のバックグラウンドジョブの1つまたはすべてが完了するまで、コマンドプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-105">Suppresses the command prompt until one or all of the Windows PowerShell background jobs running in the session are completed.</span></span>

## <span data-ttu-id="bbe5f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bbe5f-106">SYNTAX</span></span>

### <span data-ttu-id="bbe5f-107">SessionIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="bbe5f-107">SessionIdParameterSet (Default)</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="bbe5f-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="bbe5f-108">JobParameterSet</span></span>

```
Wait-Job [-Job] <Job[]> [-Any] [-Timeout <Int32>] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="bbe5f-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="bbe5f-109">NameParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="bbe5f-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="bbe5f-110">InstanceIdParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="bbe5f-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="bbe5f-111">StateParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="bbe5f-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="bbe5f-112">FilterParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="bbe5f-113">Description</span><span class="sxs-lookup"><span data-stu-id="bbe5f-113">DESCRIPTION</span></span>
<span data-ttu-id="bbe5f-114">**Wait ジョブ** コマンドレットは、Windows PowerShell のバックグラウンドジョブが完了するのを待ってから、コマンドプロンプトを表示します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-114">The **Wait-Job** cmdlet waits for Windows PowerShell background jobs to finish before it displays the command prompt.</span></span>
<span data-ttu-id="bbe5f-115">任意のバックグラウンド ジョブまたはすべてのバックグラウンド ジョブが完了まで待機できます。さらに、ジョブの最大待機時間を設定できます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-115">You can wait until any background job is complete, or until all background jobs are complete, and you can set a maximum wait time for the job.</span></span>

<span data-ttu-id="bbe5f-116">ジョブ内のコマンドが完了すると、 **Wait-Job** はコマンド プロンプトを表示し、ジョブ オブジェクトを返します。そのため、パイプを使用して別のコマンドにジョブ オブジェクトを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-116">When the commands in the job are complete, **Wait-Job** displays the command prompt and returns a job object so that you can pipe it to another command.</span></span>

<span data-ttu-id="bbe5f-117">Start-Job コマンドレットまたは Invoke-Command コマンドレットの *AsJob* パラメーターを使用して開始されたジョブなど、バックグラウンドジョブを待機するには、 **wait-Job** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-117">You can use **Wait-Job** cmdlet to wait for background jobs, such as those that were started by using the Start-Job cmdlet or the *AsJob* parameter of the Invoke-Command cmdlet.</span></span>
<span data-ttu-id="bbe5f-118">Windows PowerShell のバックグラウンド ジョブの詳細については、「about_Jobs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-118">For more information about Windows PowerShell background jobs, see about_Jobs.</span></span>

<span data-ttu-id="bbe5f-119">Windows PowerShell 3.0 以降では、 **待機ジョブ** コマンドレットは、ワークフロージョブやスケジュールされたジョブのインスタンスなどのカスタムジョブの種類も待機します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-119">Starting in Windows PowerShell 3.0, the **Wait-Job** cmdlet also waits for custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="bbe5f-120">**待機ジョブ** が特定の種類のジョブを待機できるようにするには、Get-Job コマンドレットを実行する前に、カスタムジョブの種類をサポートするモジュールをセッションにインポートします。そのためには、Import-Module コマンドレットを使用するか、またはモジュールのコマンドレットを使用または取得します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-120">To enable **Wait-Job** to wait for jobs of a particular type, import the module that supports the custom job type into the session before you run the Get-Job cmdlet, either by using the Import-Module cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="bbe5f-121">特定のカスタム ジョブの種類については、カスタムのジョブの種類機能のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-121">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="bbe5f-122">例</span><span class="sxs-lookup"><span data-stu-id="bbe5f-122">EXAMPLES</span></span>

### <span data-ttu-id="bbe5f-123">例 1: すべてのジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="bbe5f-123">Example 1: Wait for all jobs</span></span>

```
PS C:\> Get-Job | Wait-Job
```

<span data-ttu-id="bbe5f-124">このコマンドは、セッションで実行されているすべてのバックグラウンドジョブが完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-124">This command waits for all of the background jobs running in the session to finish.</span></span>

### <span data-ttu-id="bbe5f-125">例 2: Start-Job を使用してリモートコンピューターで開始されたジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="bbe5f-125">Example 2: Wait for jobs started on remote computers by using Start-Job</span></span>

```
PS C:\> $s = New-PSSession Server01, Server02, Server03
PS C:\> Invoke-Command -Session $s -ScriptBlock {Start-Job -Name Date1 -ScriptBlock {Get-Date}}
PS C:\> $done = Invoke-Command -Session $s -Command {Wait-Job -Name Date1}
PS C:\> $done.Count
3
```

<span data-ttu-id="bbe5f-126">この例では、 **Start ジョブ** コマンドレットを使用して、リモートコンピューターで開始されたジョブで、 **Wait-job** コマンドレットを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-126">This example shows how to use the **Wait-Job** cmdlet with jobs started on remote computers by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="bbe5f-127">**開始ジョブ** と **待機ジョブ** の両方のコマンドをリモートコンピューターに送信するには、 **コマンド** レットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-127">Both **Start-Job** and **Wait-Job** commands are submitted to the remote computer by using the **Invoke-Command** cmdlet.</span></span>

<span data-ttu-id="bbe5f-128">この例では、 **待機ジョブ** を使用して、3台の異なるコンピューター上でバックグラウンドジョブとして実行されている Get-Date コマンドが終了しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-128">This example uses **Wait-Job** to determine whether a Get-Date command running as a background job on three different computers is finished.</span></span>

<span data-ttu-id="bbe5f-129">最初のコマンドは、3台のリモートコンピューターそれぞれに Windows PowerShell セッション ( **PSSession** ) を作成し、それらを $s 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-129">The first command creates a Windows PowerShell session ( **PSSession** ) on each of the three remote computers and stores them in the $s variable.</span></span>

<span data-ttu-id="bbe5f-130">2番目のコマンドは、 **Invoke コマンド** を使用して、$s 内の3つの各セッションで **Start ジョブ** を実行します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-130">The second command uses **Invoke-Command** to run **Start-Job** in each of the three sessions in $s.</span></span>
<span data-ttu-id="bbe5f-131">すべてのジョブには、Date1 という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-131">All of the jobs are named Date1.</span></span>

<span data-ttu-id="bbe5f-132">3番目のコマンドは、 **Invoke コマンド** を使用して **待機ジョブ** を実行します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-132">The third command uses **Invoke-Command** to run **Wait-Job** .</span></span>
<span data-ttu-id="bbe5f-133">このコマンドは、各コンピューター上の Date1 ジョブが完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-133">This command waits for the Date1 jobs on each computer to finish.</span></span>
<span data-ttu-id="bbe5f-134">このコマンドは、ジョブ オブジェクトの結果のコレクション (配列) を $done 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-134">It stores the resulting collection (array) of job objects in the $done variable.</span></span>

<span data-ttu-id="bbe5f-135">4番目のコマンドは、$done 変数内のジョブオブジェクトの配列の **Count** プロパティを使用して、完了したジョブの数を確認します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-135">The fourth command uses the **Count** property of the array of job objects in the $done variable to determine how many of the jobs are finished.</span></span>

### <span data-ttu-id="bbe5f-136">例 3: 最初のバックグラウンドジョブがいつ終了するかを判断する</span><span class="sxs-lookup"><span data-stu-id="bbe5f-136">Example 3: Determine when the first background job finishes</span></span>

```
PS C:\> $s = New-PSSession (Get-Content Machines.txt)
PS C:\> $c = 'Get-EventLog -LogName System | where {$_.EntryType -eq "error" --and $_.Source -eq "LSASRV"} | Out-File Errors.txt'
PS C:\> Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$Using:c}
PS C:\> Invoke-Command -Session $s -ScriptBlock {Wait-Job -Any}
```

<span data-ttu-id="bbe5f-137">この例では、 **Wait-Job** の *任意* のパラメーターを使用して、現在のセッションで実行されている多くのバックグラウンドジョブが完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-137">This example uses the *Any* parameter of **Wait-Job** to determine when the first of many background jobs running in the current session are completed.</span></span>
<span data-ttu-id="bbe5f-138">また、 **wait-Job** コマンドレットを使用して、リモートジョブが終了するのを待機する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-138">It also shows how to use the **Wait-Job** cmdlet to wait for remote jobs to finish.</span></span>

<span data-ttu-id="bbe5f-139">最初のコマンドは、Machines.txt ファイルに一覧表示されている各コンピューター上に **pssession** を作成し、$s 変数に **pssession** オブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-139">The first command creates a **PSSession** on each of the computers listed in the Machines.txt file and stores the **PSSession** objects in the $s variable.</span></span>
<span data-ttu-id="bbe5f-140">このコマンドは、Get-Content コマンドレットを使用して、ファイルの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-140">The command uses the Get-Content cmdlet to get the contents of the file.</span></span>
<span data-ttu-id="bbe5f-141">**Get Content** コマンドは、New-PSSession コマンドの前に実行されるように、かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-141">The **Get-Content** command is enclosed in parentheses to make sure that it runs before the New-PSSession command.</span></span>

<span data-ttu-id="bbe5f-142">2番目のコマンドは、 **Get EventLog** コマンド文字列を $c 変数に引用符で囲んで格納します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-142">The second command stores a **Get-EventLog** command string, in quotation marks, in the $c variable.</span></span>

<span data-ttu-id="bbe5f-143">3番目のコマンドは、Invoke-Command コマンドレットを使用して、$s 内の各セッションで **Start ジョブ** を実行します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-143">The third command uses Invoke-Command cmdlet to run **Start-Job** in each of the sessions in $s.</span></span>
<span data-ttu-id="bbe5f-144">**Start ジョブ** コマンドを実行すると、$c 変数で **Get EventLog** コマンドを実行するバックグラウンドジョブが開始されます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-144">The **Start-Job** command starts a background job that runs the **Get-EventLog** command in the $c variable.</span></span>

<span data-ttu-id="bbe5f-145">このコマンドは、 **Using** スコープ修飾子を使用して、$c 変数がローカル コンピューター上で定義されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-145">The command uses the **Using** scope modifier to indicate that the $c variable was defined on the local computer.</span></span>
<span data-ttu-id="bbe5f-146">**Using** スコープ修飾子は、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-146">The **Using** scope modifier is introduced in Windows PowerShell 3.0.</span></span>
<span data-ttu-id="bbe5f-147">スコープ修飾子の **使用** の詳細については、「about_Remote_Variables (」を参照してください https://go.microsoft.com/fwlink/?LinkID=252653) 。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-147">For more information about the **Using** scope modifier, see about_Remote_Variables (https://go.microsoft.com/fwlink/?LinkID=252653).</span></span>

<span data-ttu-id="bbe5f-148">4番目のコマンドは、 **Invoke コマンド** を使用して、セッションで **待機ジョブ** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-148">The fourth command uses **Invoke-Command** to run a **Wait-Job** command in the sessions.</span></span>
<span data-ttu-id="bbe5f-149">また、 *Any* パラメーターを使用して、リモートコンピューター上の最初のジョブが完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-149">It uses the *Any* parameter to wait until the first job on the remote computers is completed.</span></span>

### <span data-ttu-id="bbe5f-150">例 4: リモートコンピューター上のジョブの待機時間を設定する</span><span class="sxs-lookup"><span data-stu-id="bbe5f-150">Example 4: Set a wait time for jobs on remote computers</span></span>

```
PS C:\> $s = New-PSSession Server01, Server02, Server03
PS C:\> $jobs = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-Date}}
PS C:\> $done = Invoke-Command -Session $s -ScriptBlock {Wait-Job -Timeout 30}
```

<span data-ttu-id="bbe5f-151">この例では、 **Wait ジョブ** の *Timeout* パラメーターを使用して、リモートコンピューターで実行されているジョブの最大待機時間を設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-151">This example shows how to use the *Timeout* parameter of **Wait-Job** to set a maximum wait time for the jobs running on remote computers.</span></span>

<span data-ttu-id="bbe5f-152">最初のコマンドは、3台のリモートコンピューター (Server01、Server02、および Server03) のそれぞれに **pssession** を作成し、 **pssession** オブジェクトを $s 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-152">The first command creates a **PSSession** on each of three remote computers (Server01, Server02, and Server03), and then stores the **PSSession** objects in the $s variable.</span></span>

<span data-ttu-id="bbe5f-153">2番目のコマンドは、 **Invoke コマンド** を使用して、$s 内の各 **PSSession** オブジェクトで **Start ジョブ** を実行します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-153">The second command uses **Invoke-Command** to run **Start-Job** in each of the **PSSession** objects in $s.</span></span>
<span data-ttu-id="bbe5f-154">結果として得られるジョブオブジェクトが $jobs 変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-154">It stores the resulting job objects in the $jobs variable.</span></span>

<span data-ttu-id="bbe5f-155">3番目のコマンドは、$s 内の各セッションで、 **Invoke コマンド** を使用して **待機ジョブ** を実行します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-155">The third command uses **Invoke-Command** to run **Wait-Job** in each of the sessions in $s.</span></span>
<span data-ttu-id="bbe5f-156">**Wait ジョブ** コマンドは、すべてのコマンドが30秒以内に完了したかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-156">The **Wait-Job** command determines whether all of the commands have completed within 30 seconds.</span></span>
<span data-ttu-id="bbe5f-157">*タイムアウト* パラメーターを30に設定して最大待機時間を設定し、コマンドの結果を $done 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-157">It uses the *Timeout* parameter with a value of 30 to establish the maximum wait time, and then stores the results of the command in the $done variable.</span></span>

<span data-ttu-id="bbe5f-158">この場合に、30 秒後に Server02 コンピューター上のコマンドのみが完了しました。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-158">In this case, after 30 seconds, only the command on the Server02 computer has completed.</span></span>
<span data-ttu-id="bbe5f-159">**Wait-job** は待機を終了し、コマンドプロンプトを表示して、完了したジョブを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-159">**Wait-Job** ends the wait, displays the command prompt, and returns the object that represents the job that was completed.</span></span>

<span data-ttu-id="bbe5f-160">$done 変数には、Server02 上で実行されたジョブを表すジョブ オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-160">The $done variable contains a job object that represents the job that ran on Server02.</span></span>

### <span data-ttu-id="bbe5f-161">例 5: 複数のジョブのいずれかが完了するまで待機する</span><span class="sxs-lookup"><span data-stu-id="bbe5f-161">Example 5: Wait until one of several jobs finishes</span></span>

```
PS C:\> Wait-Job -id 1,2,5 -Any
```

<span data-ttu-id="bbe5f-162">このコマンドは、3つのジョブを Id で識別し、いずれかのジョブが完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-162">This command identifies three jobs by their IDs and waits until any one of them are completed.</span></span>
<span data-ttu-id="bbe5f-163">最初のジョブが完了すると、コマンドプロンプトが返されます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-163">The command prompt returns when the first job finishes.</span></span>

### <span data-ttu-id="bbe5f-164">例 6: 期間を待機してから、ジョブをバックグラウンドで続行することを許可する</span><span class="sxs-lookup"><span data-stu-id="bbe5f-164">Example 6: Wait for a period, then allow job to continue in background</span></span>

```
PS C:\> Wait-Job -Name "DailyLog" -Timeout 120
```

<span data-ttu-id="bbe5f-165">このコマンドは、DailyLog ジョブが完了するまで120秒 (2 分) 待機します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-165">This command waits 120 seconds (two minutes) for the DailyLog job to finish.</span></span>
<span data-ttu-id="bbe5f-166">ジョブが次の2分以内に完了しなかった場合は、コマンドプロンプトが返され、ジョブはバックグラウンドで実行され続けます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-166">If the job does not finish in the next two minutes, the command prompt returns anyway, and the job continues to run in the background.</span></span>

### <span data-ttu-id="bbe5f-167">例 7: 名前でジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="bbe5f-167">Example 7: Wait for a job by name</span></span>

```
PS C:\> Wait-Job -Name "Job3"
```

<span data-ttu-id="bbe5f-168">このコマンドは、ジョブ名を使用して、待機するジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-168">This command uses the job name to identify the job for which to wait.</span></span>

### <span data-ttu-id="bbe5f-169">例 8: Start-Job で開始されたローカルコンピューター上のジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="bbe5f-169">Example 8: Wait for jobs on local computer started with Start-Job</span></span>

```
PS C:\> $j = Start-Job -ScriptBlock {Get-ChildItem *.ps1| where {$_lastwritetime -gt ((Get-Date) - (New-TimeSpan -Days 7))}}
PS C:\> $j | Wait-Job
```

<span data-ttu-id="bbe5f-170">この例では、 **Start ジョブ** を使用してローカルコンピューターで開始されたジョブで、 **Wait-job** コマンドレットを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-170">This example shows how to use the **Wait-Job** cmdlet with jobs started on the local computer by using **Start-Job** .</span></span>

<span data-ttu-id="bbe5f-171">これらのコマンドは、過去 1 週間に追加または更新された Windows PowerShell スクリプト ファイルを取得するジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-171">These commands start a job that gets the Windows PowerShell script files that were added or updated in the last week.</span></span>

<span data-ttu-id="bbe5f-172">最初のコマンドは、 **開始ジョブ** を使用して、ローカルコンピューター上でバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-172">The first command uses **Start-Job** to start a background job on the local computer.</span></span>
<span data-ttu-id="bbe5f-173">このジョブは、過去1週間に追加または更新されたファイル名拡張子が ps1 のすべてのファイルを取得する Get-ChildItem コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-173">The job runs a Get-ChildItem command that gets all of the files that have a .ps1 file name extension that were added or updated in the last week.</span></span>

<span data-ttu-id="bbe5f-174">3番目のコマンドは、ジョブが完了するまで待機するために、 **Wait ジョブ** を使用します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-174">The third command uses **Wait-Job** to wait until the job is completed.</span></span>
<span data-ttu-id="bbe5f-175">ジョブが完了すると、ジョブに関する情報を含むジョブオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-175">When the job finishes, the command displays the job object, which contains information about the job.</span></span>

### <span data-ttu-id="bbe5f-176">例 9: Invoke-Command を使用してリモートコンピューターで開始されたジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="bbe5f-176">Example 9: Wait for jobs started on remote computers by using Invoke-Command</span></span>

```
PS C:\> $s = New-PSSession Server01, Server02, Server03
PS C:\> $j = Invoke-Command -Session $s -ScriptBlock {Get-Process} -AsJob
PS C:\> $j | Wait-Job
```

<span data-ttu-id="bbe5f-177">この例では、リモートコンピューターで開始されたジョブに対して、 **Invoke コマンド** の *AsJob* パラメーターを使用して、 **待機ジョブ** を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-177">This example shows how to use **Wait-Job** with jobs started on remote computers by using the *AsJob* parameter of **Invoke-Command** .</span></span>
<span data-ttu-id="bbe5f-178">*AsJob* を使用する場合、ジョブはローカルコンピューター上に作成され、そのジョブがリモートコンピューター上で実行されている場合でも、結果はローカルコンピューターに自動的に返されます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-178">When using *AsJob* , the job is created on the local computer and the results are automatically returned to the local computer, even though the job runs on the remote computers.</span></span>

<span data-ttu-id="bbe5f-179">この例では、 **待機ジョブ** を使用して、3台のリモートコンピューター上のセッションで実行されている **Get Process** コマンドが完了しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-179">This example uses **Wait-Job** to determine whether a **Get-Process** command running in the sessions on three remote computers is completed.</span></span>

<span data-ttu-id="bbe5f-180">最初のコマンドは、3台のコンピューター上に **PSSession** オブジェクトを作成し、それらを $s 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-180">The first command creates **PSSession** objects on three computers and stores them in the $s variable.</span></span>

<span data-ttu-id="bbe5f-181">2番目のコマンドは、 **Invoke コマンド** を使用して、$s 内の3つの各セッションで **Get Process** を実行します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-181">The second command uses **Invoke-Command** to run **Get-Process** in each of the three sessions in $s.</span></span>
<span data-ttu-id="bbe5f-182">このコマンドは、 *AsJob* パラメーターを使用して、バックグラウンドジョブとしてコマンドを非同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-182">The command uses the *AsJob* parameter to run the command asynchronously as a background job.</span></span>
<span data-ttu-id="bbe5f-183">このコマンドは、 **Start ジョブ** を使用して開始されたジョブと同様に、ジョブオブジェクトを返します。ジョブオブジェクトは $j 変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-183">The command returns a job object, just like the jobs started by using **Start-Job** , and the job object is stored in the $j variable.</span></span>

<span data-ttu-id="bbe5f-184">3番目のコマンドは、パイプライン演算子 (|) を使用して、$j 内のジョブオブジェクトを、 **Wait ジョブ** コマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-184">The third command uses a pipeline operator (|) to send the job object in $j to the **Wait-Job** cmdlet.</span></span>
<span data-ttu-id="bbe5f-185">この場合、ジョブはローカルコンピューター上に存在するので、 **コマンドの呼び出し** は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-185">An **Invoke-Command** command is not required in this case, because the job resides on the local computer.</span></span>

### <span data-ttu-id="bbe5f-186">例 10: ID を持つジョブを待機する</span><span class="sxs-lookup"><span data-stu-id="bbe5f-186">Example 10: Wait for a job that has an ID</span></span>

```
PS C:\> Get-Job

Id   Name     State      HasMoreData     Location             Command
--   ----     -----      -----------     --------             -------
1    Job1     Completed  True            localhost,Server01.. get-service
4    Job4     Completed  True            localhost            dir | where

PS C:\> Wait-Job -Id 1
```

<span data-ttu-id="bbe5f-187">このコマンドは、ID 値が 1 であるジョブを待機します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-187">This command waits for the job with an ID value of 1.</span></span>

## <span data-ttu-id="bbe5f-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bbe5f-188">PARAMETERS</span></span>

### <span data-ttu-id="bbe5f-189">-任意</span><span class="sxs-lookup"><span data-stu-id="bbe5f-189">-Any</span></span>
<span data-ttu-id="bbe5f-190">このコマンドレットによってコマンドプロンプトが表示され、ジョブの完了時にジョブオブジェクトが返されることを示します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-190">Indicates that this cmdlet displays the command prompt, and returns the job object, when any job finishes.</span></span>
<span data-ttu-id="bbe5f-191">既定では、指定されたすべてのジョブが完了する **まで待機し** てから、プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-191">By default, **Wait-Job** waits until all of the specified jobs are complete before it displays the prompt.</span></span>

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

### <span data-ttu-id="bbe5f-192">-Filter</span><span class="sxs-lookup"><span data-stu-id="bbe5f-192">-Filter</span></span>
<span data-ttu-id="bbe5f-193">条件のハッシュテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-193">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="bbe5f-194">このコマンドレットは、ハッシュテーブル内のすべての条件を満たすジョブを待機します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-194">This cmdlet waits for jobs that satisfy all of the conditions in the hash table.</span></span>
<span data-ttu-id="bbe5f-195">ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-195">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="bbe5f-196">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-196">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span>
<span data-ttu-id="bbe5f-197">これは、 **開始ジョブ** コマンドレットを使用して作成されたジョブなど、標準のバックグラウンドジョブでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-197">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="bbe5f-198">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-198">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="bbe5f-199">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-199">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="bbe5f-200">-Force</span><span class="sxs-lookup"><span data-stu-id="bbe5f-200">-Force</span></span>
<span data-ttu-id="bbe5f-201">このコマンドレットが中断または切断状態のジョブを引き続き待機することを示します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-201">Indicates that this cmdlet continues to wait for jobs in the Suspended or Disconnected state.</span></span>
<span data-ttu-id="bbe5f-202">既定では、ジョブが次のいずれかの状態にある場合は、 **待機時間** が返されるか、待機が終了します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-202">By default, **Wait-Job** returns, or ends  the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="bbe5f-203">完了</span><span class="sxs-lookup"><span data-stu-id="bbe5f-203">Completed</span></span>
- <span data-ttu-id="bbe5f-204">失敗</span><span class="sxs-lookup"><span data-stu-id="bbe5f-204">Failed</span></span>
- <span data-ttu-id="bbe5f-205">停止済み</span><span class="sxs-lookup"><span data-stu-id="bbe5f-205">Stopped</span></span>
- <span data-ttu-id="bbe5f-206">Suspended</span><span class="sxs-lookup"><span data-stu-id="bbe5f-206">Suspended</span></span>
- <span data-ttu-id="bbe5f-207">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="bbe5f-207">Disconnected</span></span>

<span data-ttu-id="bbe5f-208">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="bbe5f-209">-Id</span><span class="sxs-lookup"><span data-stu-id="bbe5f-209">-Id</span></span>
<span data-ttu-id="bbe5f-210">このコマンドレットが待機するジョブの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-210">Specifies an array of IDs of jobs for which this cmdlet waits.</span></span>

<span data-ttu-id="bbe5f-211">ID は、現在のセッションでジョブを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-211">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="bbe5f-212">インスタンス ID よりも覚えやすく、入力も簡単ですが、現在のセッションでのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-212">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="bbe5f-213">1つ以上の Id をコンマで区切って入力できます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-213">You can type one or more IDs, separated by commas.</span></span>
<span data-ttu-id="bbe5f-214">ジョブの ID を検索するには、「」と入力 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-214">To find the ID of a job, type `Get-Job`.</span></span>

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

### <span data-ttu-id="bbe5f-215">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="bbe5f-215">-InstanceId</span></span>
<span data-ttu-id="bbe5f-216">このコマンドレットが待機するジョブのインスタンス Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-216">Specifies an array of instance IDs of jobs for which this cmdlet waits.</span></span>
<span data-ttu-id="bbe5f-217">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-217">The default is all jobs.</span></span>

<span data-ttu-id="bbe5f-218">インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-218">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="bbe5f-219">ジョブのインスタンス ID を調べるには、 **Get-Job** を使用します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-219">To find the instance ID of a job, use **Get-Job** .</span></span>

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

### <span data-ttu-id="bbe5f-220">-ジョブ</span><span class="sxs-lookup"><span data-stu-id="bbe5f-220">-Job</span></span>
<span data-ttu-id="bbe5f-221">このコマンドレットが待機するジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-221">Specifies the jobs for which this cmdlet waits.</span></span>
<span data-ttu-id="bbe5f-222">ジョブ オブジェクトが格納されている変数、またはジョブ オブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-222">Enter a variable that contains the job objects or a command that gets the job objects.</span></span>
<span data-ttu-id="bbe5f-223">また、パイプライン演算子を使用して、ジョブオブジェクトを **Wait** コマンドレットに送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-223">You can also use a pipeline operator to send job objects to the **Wait-Job** cmdlet.</span></span>
<span data-ttu-id="bbe5f-224">既定では、 **Wait** は、現在のセッションで作成されたすべてのジョブを待機します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-224">By default, **Wait-Job** waits for all jobs created in the current session.</span></span>

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

### <span data-ttu-id="bbe5f-225">-Name</span><span class="sxs-lookup"><span data-stu-id="bbe5f-225">-Name</span></span>
<span data-ttu-id="bbe5f-226">このコマンドレットが待機するジョブのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-226">Specifies friendly names of jobs for which this cmdlet waits.</span></span>

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

### <span data-ttu-id="bbe5f-227">-状態</span><span class="sxs-lookup"><span data-stu-id="bbe5f-227">-State</span></span>
<span data-ttu-id="bbe5f-228">ジョブの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-228">Specifies a job state.</span></span>
<span data-ttu-id="bbe5f-229">このコマンドレットは、指定された状態のジョブのみを待機します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-229">This cmdlet waits only for jobs in the specified state.</span></span>
<span data-ttu-id="bbe5f-230">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-230">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bbe5f-231">NotStarted</span><span class="sxs-lookup"><span data-stu-id="bbe5f-231">NotStarted</span></span>
- <span data-ttu-id="bbe5f-232">実行中</span><span class="sxs-lookup"><span data-stu-id="bbe5f-232">Running</span></span>
- <span data-ttu-id="bbe5f-233">完了</span><span class="sxs-lookup"><span data-stu-id="bbe5f-233">Completed</span></span>
- <span data-ttu-id="bbe5f-234">失敗</span><span class="sxs-lookup"><span data-stu-id="bbe5f-234">Failed</span></span>
- <span data-ttu-id="bbe5f-235">停止済み</span><span class="sxs-lookup"><span data-stu-id="bbe5f-235">Stopped</span></span>
- <span data-ttu-id="bbe5f-236">Blocked</span><span class="sxs-lookup"><span data-stu-id="bbe5f-236">Blocked</span></span>
- <span data-ttu-id="bbe5f-237">Suspended</span><span class="sxs-lookup"><span data-stu-id="bbe5f-237">Suspended</span></span>
- <span data-ttu-id="bbe5f-238">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="bbe5f-238">Disconnected</span></span>
- <span data-ttu-id="bbe5f-239">中断中</span><span class="sxs-lookup"><span data-stu-id="bbe5f-239">Suspending</span></span>
- <span data-ttu-id="bbe5f-240">停止中</span><span class="sxs-lookup"><span data-stu-id="bbe5f-240">Stopping</span></span>

<span data-ttu-id="bbe5f-241">ジョブの状態の詳細については、MSDN ライブラリの「 [Jobstate 列挙型](https://msdn.microsoft.com/library/system.management.automation.jobstate) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-241">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

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

### <span data-ttu-id="bbe5f-242">-タイムアウト</span><span class="sxs-lookup"><span data-stu-id="bbe5f-242">-Timeout</span></span>
<span data-ttu-id="bbe5f-243">各バックグラウンドジョブの最大待機時間を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-243">Specifies the maximum wait time for each background job, in seconds.</span></span>
<span data-ttu-id="bbe5f-244">既定値は-1 です。このコマンドレットは、ジョブが完了するまで待機することを示します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-244">The default value, -1, indicates that the cmdlet waits until the job finishes.</span></span>
<span data-ttu-id="bbe5f-245">タイミングは、 **開始ジョブ** コマンドではなく、 **Wait ジョブ** コマンドを送信すると開始されます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-245">The timing starts when you submit the **Wait-Job** command, not the **Start-Job** command.</span></span>

<span data-ttu-id="bbe5f-246">この時間を超えた場合、ジョブがまだ実行中でも、待機が終了し、コマンド プロンプトが返されます。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-246">If this time is exceeded, the wait ends and the command prompt returns, even if the job is still running.</span></span>
<span data-ttu-id="bbe5f-247">このコマンドでは、エラーメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-247">The command does not display any error message.</span></span>

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

### <span data-ttu-id="bbe5f-248">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="bbe5f-248">CommonParameters</span></span>
<span data-ttu-id="bbe5f-249">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-249">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bbe5f-250">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-250">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bbe5f-251">入力</span><span class="sxs-lookup"><span data-stu-id="bbe5f-251">INPUTS</span></span>

### <span data-ttu-id="bbe5f-252">System. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="bbe5f-252">System.Management.Automation.RemotingJob</span></span>
<span data-ttu-id="bbe5f-253">パイプを使用してジョブオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-253">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="bbe5f-254">出力</span><span class="sxs-lookup"><span data-stu-id="bbe5f-254">OUTPUTS</span></span>

### <span data-ttu-id="bbe5f-255">システムの管理. PSRemotingJob</span><span class="sxs-lookup"><span data-stu-id="bbe5f-255">System.Management.Automation.PSRemotingJob</span></span>
<span data-ttu-id="bbe5f-256">このコマンドレットは、完了したジョブを表すジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-256">This cmdlet returns job objects that represent the completed jobs.</span></span>
<span data-ttu-id="bbe5f-257">*Timeout* パラメーターの値を超えたために待機が終了した場合、 **待機** 時間はオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-257">If the wait ends because the value of the *Timeout* parameter is exceeded, **Wait-Job** does not return any objects.</span></span>

## <span data-ttu-id="bbe5f-258">注</span><span class="sxs-lookup"><span data-stu-id="bbe5f-258">NOTES</span></span>

* <span data-ttu-id="bbe5f-259">既定では、ジョブが次のいずれかの状態にある場合は、 **待機時間** が返されるか、待機が終了します。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-259">By default, **Wait-Job** returns, or ends the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="bbe5f-260">完了</span><span class="sxs-lookup"><span data-stu-id="bbe5f-260">Completed</span></span>
- <span data-ttu-id="bbe5f-261">失敗</span><span class="sxs-lookup"><span data-stu-id="bbe5f-261">Failed</span></span>
- <span data-ttu-id="bbe5f-262">停止済み</span><span class="sxs-lookup"><span data-stu-id="bbe5f-262">Stopped</span></span>
- <span data-ttu-id="bbe5f-263">Suspended</span><span class="sxs-lookup"><span data-stu-id="bbe5f-263">Suspended</span></span>
- <span data-ttu-id="bbe5f-264">中断されたジョブと切断されたジョブの待機を続けるために、direct **Wait ジョブ** が切断されました。 *Force* パラメーターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="bbe5f-264">Disconnected To direct **Wait-Job** to continue to wait for Suspended and Disconnected jobs, use the *Force* parameter.</span></span>

## <span data-ttu-id="bbe5f-265">関連リンク</span><span class="sxs-lookup"><span data-stu-id="bbe5f-265">RELATED LINKS</span></span>

[<span data-ttu-id="bbe5f-266">Get-Job</span><span class="sxs-lookup"><span data-stu-id="bbe5f-266">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="bbe5f-267">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="bbe5f-267">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="bbe5f-268">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="bbe5f-268">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="bbe5f-269">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="bbe5f-269">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="bbe5f-270">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="bbe5f-270">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="bbe5f-271">Start-Job</span><span class="sxs-lookup"><span data-stu-id="bbe5f-271">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="bbe5f-272">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="bbe5f-272">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="bbe5f-273">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="bbe5f-273">Suspend-Job</span></span>](Suspend-Job.md)
