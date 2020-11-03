---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/stop-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Job
ms.openlocfilehash: d6f1b3a719724073919930b1f1c0839250b5d2c8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216963"
---
# <span data-ttu-id="5a4cb-103">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="5a4cb-103">Stop-Job</span></span>

## <span data-ttu-id="5a4cb-104">概要</span><span class="sxs-lookup"><span data-stu-id="5a4cb-104">SYNOPSIS</span></span>
<span data-ttu-id="5a4cb-105">PowerShell バックグラウンドジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-105">Stops a PowerShell background job.</span></span>

## <span data-ttu-id="5a4cb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5a4cb-106">SYNTAX</span></span>

### <span data-ttu-id="5a4cb-107">SessionIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="5a4cb-107">SessionIdParameterSet (Default)</span></span>

```
Stop-Job [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5a4cb-108">JobParameterSet</span><span class="sxs-lookup"><span data-stu-id="5a4cb-108">JobParameterSet</span></span>

```
Stop-Job [-Job] <Job[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5a4cb-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="5a4cb-109">NameParameterSet</span></span>

```
Stop-Job [-PassThru] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5a4cb-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="5a4cb-110">InstanceIdParameterSet</span></span>

```
Stop-Job [-PassThru] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5a4cb-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="5a4cb-111">StateParameterSet</span></span>

```
Stop-Job [-PassThru] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5a4cb-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="5a4cb-112">FilterParameterSet</span></span>

```
Stop-Job [-PassThru] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5a4cb-113">Description</span><span class="sxs-lookup"><span data-stu-id="5a4cb-113">DESCRIPTION</span></span>

<span data-ttu-id="5a4cb-114">**停止ジョブ** コマンドレットは、進行中の PowerShell バックグラウンドジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-114">The **Stop-Job** cmdlet stops PowerShell background jobs that are in progress.</span></span>
<span data-ttu-id="5a4cb-115">このコマンドレットを使用すると、すべてのジョブを停止したり、名前、ID、インスタンス ID、または状態に基づいて選択したジョブを停止したり、ジョブオブジェクトを **停止ジョブ** に渡したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-115">You can use this cmdlet to stop all jobs or stop selected jobs based on their name, ID, instance ID, or state, or by passing a job object to **Stop-Job** .</span></span>

<span data-ttu-id="5a4cb-116">Start-Job コマンドレットまたは任意のコマンドレットの *AsJob* パラメーターを使用して開始されたジョブなど、バックグラウンドジョブを停止するには、[ **ジョブの停止** ] を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-116">You can use **Stop-Job** to stop background jobs, such as those that were started by using the Start-Job cmdlet or the *AsJob* parameter of any cmdlet.</span></span>
<span data-ttu-id="5a4cb-117">バックグラウンドジョブを停止すると、PowerShell はそのジョブキューで保留中のすべてのタスクを完了し、ジョブを終了します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-117">When you stop a background job, PowerShell completes all tasks that are pending in that job queue and then ends the job.</span></span>
<span data-ttu-id="5a4cb-118">このコマンドが送信された後、新しいタスクはキューに追加されません。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-118">No new tasks are added to the queue after this command is submitted.</span></span>

<span data-ttu-id="5a4cb-119">このコマンドレットは、バックグラウンド ジョブを削除しません。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-119">This cmdlet does not delete background jobs.</span></span>
<span data-ttu-id="5a4cb-120">ジョブを削除するには、Remove-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-120">To delete a job, use the Remove-Job cmdlet.</span></span>

<span data-ttu-id="5a4cb-121">Windows PowerShell 3.0 以降では、 **停止ジョブによっ** て、ワークフロージョブやスケジュールされたジョブのインスタンスなどのカスタムジョブの種類も停止します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-121">Starting in Windows PowerShell 3.0, **Stop-Job** also stops custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="5a4cb-122">カスタムジョブの種類を使用してジョブ **を停止することを有効に** するには、Import-Module コマンドレットを使用するか、またはモジュールのコマンドレットを使用して、ジョブの **停止** コマンドを実行する前に、そのカスタムジョブの種類をサポートするモジュールをセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-122">To enable **Stop-Job** to stop a job with custom job type, import the module that supports the custom job type into the session before you run a **Stop-Job** command, either by using the Import-Module cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="5a4cb-123">特定のカスタム ジョブの種類については、カスタムのジョブの種類機能のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-123">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="5a4cb-124">例</span><span class="sxs-lookup"><span data-stu-id="5a4cb-124">EXAMPLES</span></span>

### <span data-ttu-id="5a4cb-125">例 1: Invoke-Command を使用してリモートコンピューター上のジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="5a4cb-125">Example 1: Stop a job on a remote computer by using Invoke-Command</span></span>

```powershell
$s = New-PSSession -ComputerName Server01 -Credential Domain01\Admin02
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Invoke-Command -Session $s -ScriptBlock { Stop-job -Job $Using:j }
```

<span data-ttu-id="5a4cb-126">この例は、 **Stop-Job** コマンドレットを使用して、リモート コンピューターで実行中のジョブを停止する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-126">This example shows how to use the **Stop-Job** cmdlet to stop a job that is running on a remote computer.</span></span>

<span data-ttu-id="5a4cb-127">ジョブは、Invoke-Command コマンドレットを使用して **開始ジョブ** をリモートで実行することによって開始されたため、ジョブオブジェクトはリモートコンピューターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-127">Because the job was started by using the Invoke-Command cmdlet to run a **Start-Job** command remotely, the job object is stored on the remote computer.</span></span>
<span data-ttu-id="5a4cb-128">別の **呼び出しコマンド** コマンドを使用して、 **ジョブの停止** コマンドをリモートで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-128">You must use another **Invoke-Command** command to run a **Stop-Job** command remotely.</span></span>
<span data-ttu-id="5a4cb-129">リモート バックグラウンド ジョブの詳細については、「about_Remote_Jobs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-129">For more information about remote background jobs, see about_Remote_Jobs.</span></span>

<span data-ttu-id="5a4cb-130">最初のコマンドは、Server01 コンピューター上に PowerShell セッション ( **PSSession** ) を作成し、そのセッションオブジェクトを $s 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-130">The first command creates a PowerShell session ( **PSSession** ) on the Server01 computer, and then stores the session object in the $s variable.</span></span>
<span data-ttu-id="5a4cb-131">このコマンドは、ドメイン管理者の資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-131">The command uses the credentials of a domain administrator.</span></span>

<span data-ttu-id="5a4cb-132">2 番目のコマンドは、 **Invoke-Command** コマンドレットを使用して、セッションで **Start-Job** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-132">The second command uses the **Invoke-Command** cmdlet to run a **Start-Job** command in the session.</span></span>
<span data-ttu-id="5a4cb-133">ジョブのコマンドは、システム イベント ログ内のすべてのイベントを取得します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-133">The command in the job gets all of the events in the System event log.</span></span>
<span data-ttu-id="5a4cb-134">結果のジョブ オブジェクトは、$j 変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-134">The resulting job object is stored in the $j variable.</span></span>

<span data-ttu-id="5a4cb-135">3 番目のコマンドは、ジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-135">The third command stops the job.</span></span>
<span data-ttu-id="5a4cb-136">Server01 の **PSSession** で、 **コマンド** レットを使用して、 **ジョブの停止** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-136">It uses the **Invoke-Command** cmdlet to run a **Stop-Job** command in the **PSSession** on Server01.</span></span>
<span data-ttu-id="5a4cb-137">これは、ジョブ オブジェクトがローカル コンピューター上の変数である $j に格納されているためです。コマンドは、$j をローカル変数として識別するために、Using スコープ修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-137">Because the job objects are stored in $j, which is a variable on the local computer, the command uses the Using scope modifier to identify $j as a local variable.</span></span>
<span data-ttu-id="5a4cb-138">スコープ修飾子の使用の詳細については、「 [about_Remote_Variables](about/about_Remote_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-138">For more information about the Using scope modifier, see [about_Remote_Variables](about/about_Remote_Variables.md).</span></span>

<span data-ttu-id="5a4cb-139">コマンドが完了すると、ジョブが停止し、$s の **PSSession** を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-139">When the command finishes, the job is stopped and the **PSSession** in $s is available for use.</span></span>

### <span data-ttu-id="5a4cb-140">例 2: バックグラウンドジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="5a4cb-140">Example 2: Stop a background job</span></span>

```powershell
Stop-Job -Name "Job1"
```

<span data-ttu-id="5a4cb-141">このコマンドは、Job1 バックグラウンド ジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-141">This command stops the Job1 background job.</span></span>

### <span data-ttu-id="5a4cb-142">例 3: いくつかのバックグラウンドジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="5a4cb-142">Example 3: Stop several background jobs</span></span>

```powershell
Stop-Job -Id 1, 3, 4
```

<span data-ttu-id="5a4cb-143">このコマンドは、3 つのジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-143">This command stops three jobs.</span></span>
<span data-ttu-id="5a4cb-144">ID によって識別しています。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-144">It identifies them by their IDs.</span></span>

### <span data-ttu-id="5a4cb-145">例 4: すべてのバックグラウンドジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="5a4cb-145">Example 4: Stop all background jobs</span></span>

```powershell
Get-Job | Stop-Job
```

<span data-ttu-id="5a4cb-146">このコマンドは、現在のセッションのすべてのバックグラウンド ジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-146">This command stops all of the background jobs in the current session.</span></span>

### <span data-ttu-id="5a4cb-147">例 5: すべてのブロックされたバックグラウンドジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="5a4cb-147">Example 5: Stop all blocked background jobs</span></span>

```powershell
Stop-Job -State Blocked
```

<span data-ttu-id="5a4cb-148">このコマンドは、すべてのブロックされているジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-148">This command stops all the jobs that are blocked.</span></span>

### <span data-ttu-id="5a4cb-149">例 6: インスタンス ID を使用してジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="5a4cb-149">Example 6: Stop a job by using an instance ID</span></span>

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

<span data-ttu-id="5a4cb-150">これらのコマンドは、インスタンス ID に基づいてジョブを停止する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-150">These commands show how to stop a job based on its instance ID.</span></span>

<span data-ttu-id="5a4cb-151">最初のコマンドは、Get-Job コマンドレットを使用して、現在のセッションのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-151">The first command uses the Get-Job cmdlet to get the jobs in the current session.</span></span>
<span data-ttu-id="5a4cb-152">このコマンドは、パイプライン演算子 (|) を使用して Format-Table コマンドにジョブを送信します。これにより、各ジョブの指定されたプロパティのテーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-152">The command uses a pipeline operator (|) to send the jobs to a Format-Table command, which displays a table of the specified properties of each job.</span></span>
<span data-ttu-id="5a4cb-153">この表には各ジョブのインスタンス ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-153">The table includes the Instance ID of each job.</span></span>
<span data-ttu-id="5a4cb-154">ジョブの状態を表示するには、集計プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-154">It uses a calculated property to display the job state.</span></span>

<span data-ttu-id="5a4cb-155">2番目のコマンドは、 *InstanceID* パラメーターが指定された **ジョブの停止** コマンドを使用して、選択したジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-155">The second command uses a **Stop-Job** command that has the *InstanceID* parameter to stop a selected job.</span></span>

### <span data-ttu-id="5a4cb-156">例 7: リモートコンピューター上のジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="5a4cb-156">Example 7: Stop a job on a remote computer</span></span>

```powershell
$j = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-EventLog System} -AsJob
$j | Stop-Job -PassThru
```

```Output
Id    Name    State      HasMoreData     Location         Command
--    ----    ----       -----------     --------         -------
5     Job5    Stopped    True            user01-tablet    get-eventlog system
```

<span data-ttu-id="5a4cb-157">この例は、 **Stop-Job** コマンドレットを使用して、リモート コンピューターで実行中のジョブを停止する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-157">This example shows how to use the **Stop-Job** cmdlet to stop a job that is running on a remote computer.</span></span>

<span data-ttu-id="5a4cb-158">ジョブは、 **コマンド** レットの *AsJob* パラメーターを使用して開始されたため、ジョブがリモートコンピューター上で実行されている場合でも、ジョブオブジェクトはローカルコンピューターに配置されます。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-158">Because the job was started by using the *AsJob* parameter of the **Invoke-Command** cmdlet, the job object is located on the local computer, even though the job runs on the remote computer.</span></span>
<span data-ttu-id="5a4cb-159">そのため、ローカルのジョブ **停止** コマンドを使用してジョブを停止することができます。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-159">Therefore, you can use a local **Stop-Job** command to stop the job.</span></span>

<span data-ttu-id="5a4cb-160">最初のコマンドは、 **Invoke-Command** コマンドレットを使用して、Server01 コンピューターでバックグラウンド ジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-160">The first command uses the **Invoke-Command** cmdlet to start a background job on the Server01 computer.</span></span>
<span data-ttu-id="5a4cb-161">このコマンドは、 *AsJob* パラメーターを使用して、バックグラウンド ジョブとしてリモート コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-161">The command uses the *AsJob* parameter to run the remote command as a background job.</span></span>

<span data-ttu-id="5a4cb-162">このコマンドは、ジョブオブジェクトを返します。このオブジェクトは、 **開始ジョブ** コマンドレットから返されるものと同じジョブオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-162">This command returns a job object, which is the same job object that the **Start-Job** cmdlet returns.</span></span>
<span data-ttu-id="5a4cb-163">このコマンドは、ジョブ オブジェクトを $j 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-163">The command saves the job object in the $j variable.</span></span>

<span data-ttu-id="5a4cb-164">2 番目のコマンドは、パイプライン演算子を使用して $j 変数のジョブを Stop-Job に渡します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-164">The second command uses a pipeline operator to send the job in the $j variable to Stop-Job.</span></span>
<span data-ttu-id="5a4cb-165">このコマンドは、 *PassThru* パラメーターを使用して、 **Stop-Job** に対してジョブ オブジェクトを返すように指示します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-165">The command uses the *PassThru* parameter to direct **Stop-Job** to return a job object.</span></span>
<span data-ttu-id="5a4cb-166">ジョブオブジェクトの表示では、ジョブの状態が Stopped であることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-166">The job object display confirms that the state of the job is Stopped.</span></span>

<span data-ttu-id="5a4cb-167">リモート バックグラウンド ジョブの詳細については、「about_Remote_Jobs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-167">For more information about remote background jobs, see about_Remote_Jobs.</span></span>

## <span data-ttu-id="5a4cb-168">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5a4cb-168">PARAMETERS</span></span>

### <span data-ttu-id="5a4cb-169">-Filter</span><span class="sxs-lookup"><span data-stu-id="5a4cb-169">-Filter</span></span>

<span data-ttu-id="5a4cb-170">条件のハッシュテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-170">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="5a4cb-171">このコマンドレットは、すべての条件に適合するジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-171">This cmdlet stops jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="5a4cb-172">ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-172">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="5a4cb-173">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-173">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span>
<span data-ttu-id="5a4cb-174">これは、 **開始ジョブ** コマンドレットを使用して作成されたジョブなど、標準のバックグラウンドジョブでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-174">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="5a4cb-175">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-175">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="5a4cb-176">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-176">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5a4cb-177">-Id</span><span class="sxs-lookup"><span data-stu-id="5a4cb-177">-Id</span></span>

<span data-ttu-id="5a4cb-178">このコマンドレットが停止するジョブの Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-178">Specifies the IDs of jobs that this cmdlet stops.</span></span>
<span data-ttu-id="5a4cb-179">既定は、現在のセッション内のすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-179">The default is all jobs in the current session.</span></span>

<span data-ttu-id="5a4cb-180">ID は、現在のセッションでジョブを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-180">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="5a4cb-181">インスタンス ID よりも覚えやすく、入力も簡単ですが、現在のセッションでのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-181">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="5a4cb-182">1つ以上の Id をコンマで区切って入力できます。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-182">You can type one or more IDs, separated by commas.</span></span>
<span data-ttu-id="5a4cb-183">ジョブの ID を検索するには、「」と入力 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-183">To find the ID of a job, type `Get-Job`.</span></span>

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

### <span data-ttu-id="5a4cb-184">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="5a4cb-184">-InstanceId</span></span>

<span data-ttu-id="5a4cb-185">このコマンドレットが停止するジョブのインスタンス Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-185">Specifies the instance IDs of jobs that this cmdlet stops.</span></span>
<span data-ttu-id="5a4cb-186">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-186">The default is all jobs.</span></span>

<span data-ttu-id="5a4cb-187">インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-187">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="5a4cb-188">ジョブのインスタンス ID を調べるには、Get-Job を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-188">To find the instance ID of a job, use Get-Job.</span></span>

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

### <span data-ttu-id="5a4cb-189">-ジョブ</span><span class="sxs-lookup"><span data-stu-id="5a4cb-189">-Job</span></span>

<span data-ttu-id="5a4cb-190">このコマンドレットが停止するジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-190">Specifies the jobs that this cmdlet stops.</span></span>
<span data-ttu-id="5a4cb-191">ジョブが格納されている変数、またはジョブを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-191">Enter a variable that contains the jobs or a command that gets the jobs.</span></span>
<span data-ttu-id="5a4cb-192">また、パイプライン演算子を使用して、ジョブを **停止** コマンドレットに送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-192">You can also use a pipeline operator to submit jobs to the **Stop-Job** cmdlet.</span></span>
<span data-ttu-id="5a4cb-193">既定では、 **停止ジョブ** は、現在のセッションで開始されたすべてのジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-193">By default, **Stop-Job** deletes all jobs that were started in the current session.</span></span>

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

### <span data-ttu-id="5a4cb-194">-Name</span><span class="sxs-lookup"><span data-stu-id="5a4cb-194">-Name</span></span>

<span data-ttu-id="5a4cb-195">このコマンドレットが停止するジョブのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-195">Specifies friendly names of jobs that this cmdlet stops.</span></span>
<span data-ttu-id="5a4cb-196">コンマ区切りの一覧でジョブの名前を入力するか、ワイルドカード文字 (\*) を使用してジョブの名前パターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-196">Enter the job names in a comma-separated list or use wildcard characters (\*) to enter a job name pattern.</span></span>
<span data-ttu-id="5a4cb-197">既定では、 **停止ジョブ** は、現在のセッションで作成されたすべてのジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-197">By default, **Stop-Job** stops all jobs created in the current session.</span></span>

<span data-ttu-id="5a4cb-198">フレンドリ名は一意であるとは限らないため、名前によってジョブを停止する場合は、 *WhatIf* パラメーターと *Confirm* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-198">Because the friendly name is not guaranteed to be unique, use the *WhatIf* and *Confirm* parameters when stopping jobs by name.</span></span>

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

### <span data-ttu-id="5a4cb-199">-PassThru</span><span class="sxs-lookup"><span data-stu-id="5a4cb-199">-PassThru</span></span>

<span data-ttu-id="5a4cb-200">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-200">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="5a4cb-201">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-201">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="5a4cb-202">-状態</span><span class="sxs-lookup"><span data-stu-id="5a4cb-202">-State</span></span>

<span data-ttu-id="5a4cb-203">ジョブの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-203">Specifies a job state.</span></span>
<span data-ttu-id="5a4cb-204">このコマンドレットは、指定された状態のジョブのみを停止します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-204">This cmdlet stops only jobs in the specified state.</span></span>
<span data-ttu-id="5a4cb-205">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-205">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5a4cb-206">NotStarted</span><span class="sxs-lookup"><span data-stu-id="5a4cb-206">NotStarted</span></span>
- <span data-ttu-id="5a4cb-207">実行中</span><span class="sxs-lookup"><span data-stu-id="5a4cb-207">Running</span></span>
- <span data-ttu-id="5a4cb-208">完了</span><span class="sxs-lookup"><span data-stu-id="5a4cb-208">Completed</span></span>
- <span data-ttu-id="5a4cb-209">失敗</span><span class="sxs-lookup"><span data-stu-id="5a4cb-209">Failed</span></span>
- <span data-ttu-id="5a4cb-210">停止済み</span><span class="sxs-lookup"><span data-stu-id="5a4cb-210">Stopped</span></span>
- <span data-ttu-id="5a4cb-211">Blocked</span><span class="sxs-lookup"><span data-stu-id="5a4cb-211">Blocked</span></span>
- <span data-ttu-id="5a4cb-212">Suspended</span><span class="sxs-lookup"><span data-stu-id="5a4cb-212">Suspended</span></span>
- <span data-ttu-id="5a4cb-213">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="5a4cb-213">Disconnected</span></span>
- <span data-ttu-id="5a4cb-214">中断中</span><span class="sxs-lookup"><span data-stu-id="5a4cb-214">Suspending</span></span>
- <span data-ttu-id="5a4cb-215">停止中</span><span class="sxs-lookup"><span data-stu-id="5a4cb-215">Stopping</span></span>

<span data-ttu-id="5a4cb-216">ジョブの状態の詳細については、MSDN ライブラリの「 [Jobstate 列挙型](https://msdn.microsoft.com/library/system.management.automation.jobstate) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-216">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

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

### <span data-ttu-id="5a4cb-217">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5a4cb-217">-Confirm</span></span>

<span data-ttu-id="5a4cb-218">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-218">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5a4cb-219">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5a4cb-219">-WhatIf</span></span>

<span data-ttu-id="5a4cb-220">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-220">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="5a4cb-221">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-221">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5a4cb-222">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a4cb-222">CommonParameters</span></span>

<span data-ttu-id="5a4cb-223">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-223">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5a4cb-224">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-224">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5a4cb-225">入力</span><span class="sxs-lookup"><span data-stu-id="5a4cb-225">INPUTS</span></span>

### <span data-ttu-id="5a4cb-226">System. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="5a4cb-226">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="5a4cb-227">パイプを使用してジョブオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-227">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="5a4cb-228">出力</span><span class="sxs-lookup"><span data-stu-id="5a4cb-228">OUTPUTS</span></span>

### <span data-ttu-id="5a4cb-229">なし、システムの管理. PSRemotingJob</span><span class="sxs-lookup"><span data-stu-id="5a4cb-229">None, System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="5a4cb-230">*PassThru* パラメーターを指定した場合、このコマンドレットはジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-230">This cmdlet returns a job object, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="5a4cb-231">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="5a4cb-231">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5a4cb-232">注</span><span class="sxs-lookup"><span data-stu-id="5a4cb-232">NOTES</span></span>

## <span data-ttu-id="5a4cb-233">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5a4cb-233">RELATED LINKS</span></span>

[<span data-ttu-id="5a4cb-234">Get-Job</span><span class="sxs-lookup"><span data-stu-id="5a4cb-234">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="5a4cb-235">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="5a4cb-235">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="5a4cb-236">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="5a4cb-236">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="5a4cb-237">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="5a4cb-237">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="5a4cb-238">Start-Job</span><span class="sxs-lookup"><span data-stu-id="5a4cb-238">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="5a4cb-239">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="5a4cb-239">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="5a4cb-240">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="5a4cb-240">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="5a4cb-241">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="5a4cb-241">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)

[<span data-ttu-id="5a4cb-242">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="5a4cb-242">about_Remote_Variables</span></span>](About/about_Remote_Variables.md)

[<span data-ttu-id="5a4cb-243">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="5a4cb-243">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="5a4cb-244">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="5a4cb-244">about_Scopes</span></span>](About/about_scopes.md)

