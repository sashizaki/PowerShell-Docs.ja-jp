---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/stop-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Job
ms.openlocfilehash: 5d8fdd3b798caab4661b1b26641c4e534cbd99a5
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94390560"
---
# <span data-ttu-id="a62d3-103">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="a62d3-103">Stop-Job</span></span>

## <span data-ttu-id="a62d3-104">概要</span><span class="sxs-lookup"><span data-stu-id="a62d3-104">SYNOPSIS</span></span>
<span data-ttu-id="a62d3-105">PowerShell バックグラウンドジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-105">Stops a PowerShell background job.</span></span>

## <span data-ttu-id="a62d3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a62d3-106">SYNTAX</span></span>

### <span data-ttu-id="a62d3-107">SessionIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="a62d3-107">SessionIdParameterSet (Default)</span></span>

```
Stop-Job [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a62d3-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="a62d3-108">JobParameterSet</span></span>

```
Stop-Job [-Job] <Job[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a62d3-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="a62d3-109">NameParameterSet</span></span>

```
Stop-Job [-PassThru] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a62d3-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="a62d3-110">InstanceIdParameterSet</span></span>

```
Stop-Job [-PassThru] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a62d3-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="a62d3-111">StateParameterSet</span></span>

```
Stop-Job [-PassThru] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a62d3-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="a62d3-112">FilterParameterSet</span></span>

```
Stop-Job [-PassThru] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a62d3-113">Description</span><span class="sxs-lookup"><span data-stu-id="a62d3-113">DESCRIPTION</span></span>

<span data-ttu-id="a62d3-114">`Stop-Job`コマンドレットでは、進行中の PowerShell バックグラウンドジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-114">The `Stop-Job` cmdlet stops PowerShell background jobs that are in progress.</span></span> <span data-ttu-id="a62d3-115">このコマンドレットを使用すると、すべてのジョブを停止したり、名前、ID、インスタンス ID、または状態に基づいて選択したジョブを停止したり、ジョブオブジェクトをに渡したりすることができ `Stop-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="a62d3-115">You can use this cmdlet to stop all jobs or stop selected jobs based on their name, ID, instance ID, or state, or by passing a job object to `Stop-Job`.</span></span>

<span data-ttu-id="a62d3-116">を使用すると、 `Stop-Job` `Start-Job` コマンドレットまたは任意のコマンドレットの **AsJob** パラメーターを使用して開始されたジョブなど、バックグラウンドジョブを停止できます。</span><span class="sxs-lookup"><span data-stu-id="a62d3-116">You can use `Stop-Job` to stop background jobs, such as those that were started by using the `Start-Job` cmdlet or the **AsJob** parameter of any cmdlet.</span></span> <span data-ttu-id="a62d3-117">バックグラウンドジョブを停止すると、PowerShell はそのジョブキューで保留中のすべてのタスクを完了し、ジョブを終了します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-117">When you stop a background job, PowerShell completes all tasks that are pending in that job queue and then ends the job.</span></span> <span data-ttu-id="a62d3-118">このコマンドが送信された後、新しいタスクはキューに追加されません。</span><span class="sxs-lookup"><span data-stu-id="a62d3-118">No new tasks are added to the queue after this command is submitted.</span></span>

<span data-ttu-id="a62d3-119">このコマンドレットは、バックグラウンド ジョブを削除しません。</span><span class="sxs-lookup"><span data-stu-id="a62d3-119">This cmdlet does not delete background jobs.</span></span> <span data-ttu-id="a62d3-120">ジョブを削除するには、 `Remove-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-120">To delete a job, use the `Remove-Job` cmdlet.</span></span>

<span data-ttu-id="a62d3-121">Windows PowerShell 3.0 以降では、は、 `Stop-Job` ワークフロージョブやスケジュールされたジョブのインスタンスなどのカスタムジョブの種類も停止します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-121">Starting in Windows PowerShell 3.0, `Stop-Job` also stops custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="a62d3-122">カスタムジョブの種類を使用してジョブを停止できるようにするに `Stop-Job` は、コマンドを実行する前に、コマンドを実行する前に、カスタムジョブの種類をサポートするモジュールをセッションにインポートします。そのためには、 `Stop-Job` コマンドレットを使用するか、 `Import-Module` またはモジュールのコマンドレットを取得します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-122">To enable `Stop-Job` to stop a job with custom job type, import the module that supports the custom job type into the session before you run a `Stop-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="a62d3-123">特定のカスタム ジョブの種類については、カスタムのジョブの種類機能のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a62d3-123">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="a62d3-124">例</span><span class="sxs-lookup"><span data-stu-id="a62d3-124">EXAMPLES</span></span>

### <span data-ttu-id="a62d3-125">例 1: Invoke-Command を使用してリモートコンピューター上のジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="a62d3-125">Example 1: Stop a job on a remote computer by using Invoke-Command</span></span>

```powershell
$s = New-PSSession -ComputerName Server01 -Credential Domain01\Admin02
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Invoke-Command -Session $s -ScriptBlock { Stop-job -Job $Using:j }
```

<span data-ttu-id="a62d3-126">この例では、コマンドレットを使用して、 `Stop-Job` リモートコンピューター上で実行されているジョブを停止する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-126">This example shows how to use the `Stop-Job` cmdlet to stop a job that is running on a remote computer.</span></span>

<span data-ttu-id="a62d3-127">コマンドレットを使用してジョブをリモートで実行することによってジョブが開始されたため `Invoke-Command` `Start-Job` 、ジョブオブジェクトはリモートコンピューターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="a62d3-127">Because the job was started by using the `Invoke-Command` cmdlet to run a `Start-Job` command remotely, the job object is stored on the remote computer.</span></span> <span data-ttu-id="a62d3-128">`Invoke-Command`コマンドをリモートで実行するには、別のコマンドを使用する必要があり `Stop-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="a62d3-128">You must use another `Invoke-Command` command to run a `Stop-Job` command remotely.</span></span> <span data-ttu-id="a62d3-129">リモート バックグラウンド ジョブの詳細については、「about_Remote_Jobs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a62d3-129">For more information about remote background jobs, see about_Remote_Jobs.</span></span>

<span data-ttu-id="a62d3-130">最初のコマンドは、Server01 コンピューター上に PowerShell セッション ( **PSSession** ) を作成し、そのセッションオブジェクトを変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="a62d3-130">The first command creates a PowerShell session ( **PSSession** ) on the Server01 computer, and then stores the session object in the `$s` variable.</span></span> <span data-ttu-id="a62d3-131">このコマンドは、ドメイン管理者の資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-131">The command uses the credentials of a domain administrator.</span></span>

<span data-ttu-id="a62d3-132">2番目のコマンドは、コマンドレットを使用して、 `Invoke-Command` `Start-Job` セッションでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-132">The second command uses the `Invoke-Command` cmdlet to run a `Start-Job` command in the session.</span></span> <span data-ttu-id="a62d3-133">ジョブのコマンドは、システム イベント ログ内のすべてのイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-133">The command in the job gets all of the events in the System event log.</span></span> <span data-ttu-id="a62d3-134">結果として得られるジョブオブジェクトは変数に格納され `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="a62d3-134">The resulting job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="a62d3-135">3 番目のコマンドは、ジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-135">The third command stops the job.</span></span> <span data-ttu-id="a62d3-136">コマンドレットを使用して、 `Invoke-Command` `Stop-Job` Server01 上の **PSSession** でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-136">It uses the `Invoke-Command` cmdlet to run a `Stop-Job` command in the **PSSession** on Server01.</span></span> <span data-ttu-id="a62d3-137">ジョブオブジェクトはローカルコンピューター上の変数であるに格納されるので、このコマンドは、Using スコープ修飾子を使用して、 `$j` `$j` ローカル変数としてを識別します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-137">Because the job objects are stored in `$j`, which is a variable on the local computer, the command uses the Using scope modifier to identify `$j` as a local variable.</span></span>
<span data-ttu-id="a62d3-138">スコープ修飾子の使用の詳細については、「 [about_Remote_Variables](about/about_Remote_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a62d3-138">For more information about the Using scope modifier, see [about_Remote_Variables](about/about_Remote_Variables.md).</span></span>

<span data-ttu-id="a62d3-139">コマンドが完了すると、ジョブが停止し、の **PSSession** を `$s` 使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a62d3-139">When the command finishes, the job is stopped and the **PSSession** in `$s` is available for use.</span></span>

### <span data-ttu-id="a62d3-140">例 2: バックグラウンドジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="a62d3-140">Example 2: Stop a background job</span></span>

```powershell
Stop-Job -Name "Job1"
```

<span data-ttu-id="a62d3-141">このコマンドは、Job1 バックグラウンド ジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-141">This command stops the Job1 background job.</span></span>

### <span data-ttu-id="a62d3-142">例 3: いくつかのバックグラウンドジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="a62d3-142">Example 3: Stop several background jobs</span></span>

```powershell
Stop-Job -Id 1, 3, 4
```

<span data-ttu-id="a62d3-143">このコマンドは、3 つのジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-143">This command stops three jobs.</span></span>
<span data-ttu-id="a62d3-144">ID によって識別しています。</span><span class="sxs-lookup"><span data-stu-id="a62d3-144">It identifies them by their IDs.</span></span>

### <span data-ttu-id="a62d3-145">例 4: すべてのバックグラウンドジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="a62d3-145">Example 4: Stop all background jobs</span></span>

```powershell
Get-Job | Stop-Job
```

<span data-ttu-id="a62d3-146">このコマンドは、現在のセッションのすべてのバックグラウンド ジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-146">This command stops all of the background jobs in the current session.</span></span>

### <span data-ttu-id="a62d3-147">例 5: すべてのブロックされたバックグラウンドジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="a62d3-147">Example 5: Stop all blocked background jobs</span></span>

```powershell
Stop-Job -State Blocked
```

<span data-ttu-id="a62d3-148">このコマンドは、すべてのブロックされているジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-148">This command stops all the jobs that are blocked.</span></span>

### <span data-ttu-id="a62d3-149">例 6: インスタンス ID を使用してジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="a62d3-149">Example 6: Stop a job by using an instance ID</span></span>

```powershell
Get-Job | Format-Table ID, Name, Command, @{Label="State";Expression={$_.JobStateInfo.State}},
InstanceID -Auto
```

```Output
Id Name Command                 State  InstanceId
-- ---- -------                 -----  ----------
1 Job1 start-service schedule Running 05abb67a-2932-4bd5-b331-c0254b8d9146
3 Job3 start-service schedule Running c03cbd45-19f3-4558-ba94-ebe41b68ad03
5 Job5 get-service s*         Blocked e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

```powershell
Stop-Job -InstanceId e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

<span data-ttu-id="a62d3-150">これらのコマンドは、インスタンス ID に基づいてジョブを停止する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a62d3-150">These commands show how to stop a job based on its instance ID.</span></span>

<span data-ttu-id="a62d3-151">最初のコマンドは、 `Get-Job` コマンドレットを使用して、現在のセッションのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-151">The first command uses the `Get-Job` cmdlet to get the jobs in the current session.</span></span> <span data-ttu-id="a62d3-152">このコマンドは、パイプライン演算子 () を使用し `|` てコマンドにジョブを送信し `Format-Table` ます。これにより、各ジョブの指定されたプロパティのテーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a62d3-152">The command uses a pipeline operator (`|`) to send the jobs to a `Format-Table` command, which displays a table of the specified properties of each job.</span></span> <span data-ttu-id="a62d3-153">この表には各ジョブのインスタンス ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a62d3-153">The table includes the Instance ID of each job.</span></span> <span data-ttu-id="a62d3-154">ジョブの状態を表示するには、集計プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-154">It uses a calculated property to display the job state.</span></span>

<span data-ttu-id="a62d3-155">2番目のコマンドは、InstanceID パラメーターを持つコマンドを使用して、 `Stop-Job` 選択したジョブを停止します。 **InstanceID**</span><span class="sxs-lookup"><span data-stu-id="a62d3-155">The second command uses a `Stop-Job` command that has the **InstanceID** parameter to stop a selected job.</span></span>

### <span data-ttu-id="a62d3-156">例 7: リモートコンピューター上のジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="a62d3-156">Example 7: Stop a job on a remote computer</span></span>

```powershell
$j = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-EventLog System} -AsJob
$j | Stop-Job -PassThru
```

```Output
Id    Name    State      HasMoreData     Location         Command
--    ----    ----       -----------     --------         -------
5     Job5    Stopped    True            user01-tablet    get-eventlog system
```

<span data-ttu-id="a62d3-157">この例では、コマンドレットを使用して、 `Stop-Job` リモートコンピューター上で実行されているジョブを停止する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-157">This example shows how to use the `Stop-Job` cmdlet to stop a job that is running on a remote computer.</span></span>

<span data-ttu-id="a62d3-158">ジョブはコマンドレットの **AsJob** パラメーターを使用して開始されたため、ジョブが `Invoke-Command` リモートコンピューター上で実行されている場合でも、ジョブオブジェクトはローカルコンピューターに配置されます。</span><span class="sxs-lookup"><span data-stu-id="a62d3-158">Because the job was started by using the **AsJob** parameter of the `Invoke-Command` cmdlet, the job object is located on the local computer, even though the job runs on the remote computer.</span></span> <span data-ttu-id="a62d3-159">そのため、ローカルコマンドを使用してジョブを停止することができ `Stop-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="a62d3-159">Therefore, you can use a local `Stop-Job` command to stop the job.</span></span>

<span data-ttu-id="a62d3-160">最初のコマンドは、 `Invoke-Command` コマンドレットを使用して、Server01 コンピューター上でバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-160">The first command uses the `Invoke-Command` cmdlet to start a background job on the Server01 computer.</span></span> <span data-ttu-id="a62d3-161">このコマンドは、 **AsJob** パラメーターを使用して、バックグラウンド ジョブとしてリモート コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-161">The command uses the **AsJob** parameter to run the remote command as a background job.</span></span>

<span data-ttu-id="a62d3-162">このコマンドは、ジョブオブジェクトを返します。これは、コマンドレットから返されるものと同じジョブオブジェクトです `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="a62d3-162">This command returns a job object, which is the same job object that the `Start-Job` cmdlet returns.</span></span>
<span data-ttu-id="a62d3-163">このコマンドは、ジョブオブジェクトを変数に保存し `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="a62d3-163">The command saves the job object in the `$j` variable.</span></span>

<span data-ttu-id="a62d3-164">2番目のコマンドは、パイプライン演算子を使用して、変数内のジョブをに送信し `$j` `Stop-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="a62d3-164">The second command uses a pipeline operator to send the job in the `$j` variable to `Stop-Job`.</span></span> <span data-ttu-id="a62d3-165">このコマンドは、 **PassThru** パラメーターを使用して、 `Stop-Job` ジョブオブジェクトを返すように指示します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-165">The command uses the **PassThru** parameter to direct `Stop-Job` to return a job object.</span></span> <span data-ttu-id="a62d3-166">ジョブオブジェクトの表示では、ジョブの状態が Stopped であることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="a62d3-166">The job object display confirms that the state of the job is Stopped.</span></span>

<span data-ttu-id="a62d3-167">リモート バックグラウンド ジョブの詳細については、「about_Remote_Jobs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a62d3-167">For more information about remote background jobs, see about_Remote_Jobs.</span></span>

## <span data-ttu-id="a62d3-168">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a62d3-168">PARAMETERS</span></span>

### <span data-ttu-id="a62d3-169">-Filter</span><span class="sxs-lookup"><span data-stu-id="a62d3-169">-Filter</span></span>

<span data-ttu-id="a62d3-170">条件のハッシュテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-170">Specifies a hash table of conditions.</span></span> <span data-ttu-id="a62d3-171">このコマンドレットは、すべての条件に適合するジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-171">This cmdlet stops jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="a62d3-172">ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-172">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="a62d3-173">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-173">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="a62d3-174">コマンドレットを使用して作成されたものなど、標準のバックグラウンドジョブでは機能しません `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="a62d3-174">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="a62d3-175">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a62d3-175">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="a62d3-176">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a62d3-176">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a62d3-177">-Id</span><span class="sxs-lookup"><span data-stu-id="a62d3-177">-Id</span></span>

<span data-ttu-id="a62d3-178">このコマンドレットが停止するジョブの Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-178">Specifies the IDs of jobs that this cmdlet stops.</span></span> <span data-ttu-id="a62d3-179">既定は、現在のセッション内のすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="a62d3-179">The default is all jobs in the current session.</span></span>

<span data-ttu-id="a62d3-180">ID は、現在のセッションでジョブを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="a62d3-180">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="a62d3-181">インスタンス ID よりも覚えやすく、入力も簡単ですが、現在のセッションでのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="a62d3-181">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="a62d3-182">1つ以上の Id をコンマで区切って入力できます。</span><span class="sxs-lookup"><span data-stu-id="a62d3-182">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="a62d3-183">ジョブの ID を検索するには、「」と入力 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-183">To find the ID of a job, type `Get-Job`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a62d3-184">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="a62d3-184">-InstanceId</span></span>

<span data-ttu-id="a62d3-185">このコマンドレットが停止するジョブのインスタンス Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-185">Specifies the instance IDs of jobs that this cmdlet stops.</span></span> <span data-ttu-id="a62d3-186">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="a62d3-186">The default is all jobs.</span></span>

<span data-ttu-id="a62d3-187">インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="a62d3-187">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="a62d3-188">ジョブのインスタンス ID を検索するには、を使用 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-188">To find the instance ID of a job, use `Get-Job`.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a62d3-189">-ジョブ</span><span class="sxs-lookup"><span data-stu-id="a62d3-189">-Job</span></span>

<span data-ttu-id="a62d3-190">このコマンドレットが停止するジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-190">Specifies the jobs that this cmdlet stops.</span></span> <span data-ttu-id="a62d3-191">ジョブが格納されている変数、またはジョブを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-191">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="a62d3-192">パイプライン演算子を使用して、コマンドレットにジョブを送信することもでき `Stop-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="a62d3-192">You can also use a pipeline operator to submit jobs to the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="a62d3-193">既定では、は、 `Stop-Job` 現在のセッションで開始されたすべてのジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-193">By default, `Stop-Job` deletes all jobs that were started in the current session.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a62d3-194">-Name</span><span class="sxs-lookup"><span data-stu-id="a62d3-194">-Name</span></span>

<span data-ttu-id="a62d3-195">このコマンドレットが停止するジョブのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-195">Specifies friendly names of jobs that this cmdlet stops.</span></span> <span data-ttu-id="a62d3-196">コンマ区切りの一覧でジョブの名前を入力するか、ワイルドカード文字 (\*) を使用してジョブの名前パターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-196">Enter the job names in a comma-separated list or use wildcard characters (\*) to enter a job name pattern.</span></span> <span data-ttu-id="a62d3-197">既定では、は、 `Stop-Job` 現在のセッションで作成されたすべてのジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-197">By default, `Stop-Job` stops all jobs created in the current session.</span></span>

<span data-ttu-id="a62d3-198">フレンドリ名は一意であるとは限らないため、名前によってジョブを停止する場合は、 **WhatIf** パラメーターと **Confirm** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-198">Because the friendly name is not guaranteed to be unique, use the **WhatIf** and **Confirm** parameters when stopping jobs by name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="a62d3-199">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a62d3-199">-PassThru</span></span>

<span data-ttu-id="a62d3-200">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-200">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="a62d3-201">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="a62d3-201">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a62d3-202">-状態</span><span class="sxs-lookup"><span data-stu-id="a62d3-202">-State</span></span>

<span data-ttu-id="a62d3-203">ジョブの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-203">Specifies a job state.</span></span> <span data-ttu-id="a62d3-204">このコマンドレットは、指定された状態のジョブのみを停止します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-204">This cmdlet stops only jobs in the specified state.</span></span> <span data-ttu-id="a62d3-205">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a62d3-205">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a62d3-206">NotStarted</span><span class="sxs-lookup"><span data-stu-id="a62d3-206">NotStarted</span></span>
- <span data-ttu-id="a62d3-207">実行中</span><span class="sxs-lookup"><span data-stu-id="a62d3-207">Running</span></span>
- <span data-ttu-id="a62d3-208">完了</span><span class="sxs-lookup"><span data-stu-id="a62d3-208">Completed</span></span>
- <span data-ttu-id="a62d3-209">失敗</span><span class="sxs-lookup"><span data-stu-id="a62d3-209">Failed</span></span>
- <span data-ttu-id="a62d3-210">停止済み</span><span class="sxs-lookup"><span data-stu-id="a62d3-210">Stopped</span></span>
- <span data-ttu-id="a62d3-211">［ブロック済み］</span><span class="sxs-lookup"><span data-stu-id="a62d3-211">Blocked</span></span>
- <span data-ttu-id="a62d3-212">Suspended</span><span class="sxs-lookup"><span data-stu-id="a62d3-212">Suspended</span></span>
- <span data-ttu-id="a62d3-213">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="a62d3-213">Disconnected</span></span>
- <span data-ttu-id="a62d3-214">中断中</span><span class="sxs-lookup"><span data-stu-id="a62d3-214">Suspending</span></span>
- <span data-ttu-id="a62d3-215">停止中</span><span class="sxs-lookup"><span data-stu-id="a62d3-215">Stopping</span></span>

<span data-ttu-id="a62d3-216">ジョブの状態の詳細については、「 [Jobstate 列挙型](/dotnet/api/system.management.automation.jobstate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a62d3-216">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a62d3-217">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a62d3-217">-Confirm</span></span>

<span data-ttu-id="a62d3-218">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a62d3-218">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a62d3-219">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a62d3-219">-WhatIf</span></span>

<span data-ttu-id="a62d3-220">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-220">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a62d3-221">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a62d3-221">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a62d3-222">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a62d3-222">CommonParameters</span></span>

<span data-ttu-id="a62d3-223">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a62d3-223">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a62d3-224">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a62d3-224">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a62d3-225">入力</span><span class="sxs-lookup"><span data-stu-id="a62d3-225">INPUTS</span></span>

### <span data-ttu-id="a62d3-226">System. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="a62d3-226">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="a62d3-227">パイプを使用してジョブオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-227">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="a62d3-228">出力</span><span class="sxs-lookup"><span data-stu-id="a62d3-228">OUTPUTS</span></span>

### <span data-ttu-id="a62d3-229">なし、システムの管理. PSRemotingJob</span><span class="sxs-lookup"><span data-stu-id="a62d3-229">None, System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="a62d3-230">**PassThru** パラメーターを指定した場合、このコマンドレットはジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a62d3-230">This cmdlet returns a job object, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="a62d3-231">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="a62d3-231">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a62d3-232">注</span><span class="sxs-lookup"><span data-stu-id="a62d3-232">NOTES</span></span>

## <span data-ttu-id="a62d3-233">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a62d3-233">RELATED LINKS</span></span>

[<span data-ttu-id="a62d3-234">Get-Job</span><span class="sxs-lookup"><span data-stu-id="a62d3-234">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="a62d3-235">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="a62d3-235">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="a62d3-236">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="a62d3-236">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="a62d3-237">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="a62d3-237">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="a62d3-238">Start-Job</span><span class="sxs-lookup"><span data-stu-id="a62d3-238">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="a62d3-239">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="a62d3-239">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="a62d3-240">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="a62d3-240">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="a62d3-241">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="a62d3-241">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)

[<span data-ttu-id="a62d3-242">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="a62d3-242">about_Remote_Variables</span></span>](About/about_Remote_Variables.md)

[<span data-ttu-id="a62d3-243">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="a62d3-243">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="a62d3-244">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="a62d3-244">about_Scopes</span></span>](About/about_scopes.md)
