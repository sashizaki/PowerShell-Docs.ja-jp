---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: 8a92e07746e86d4b0b84049f1f479a82c85e5e6f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217712"
---
# <span data-ttu-id="dd1b4-103">Get-Job</span><span class="sxs-lookup"><span data-stu-id="dd1b4-103">Get-Job</span></span>

## <span data-ttu-id="dd1b4-104">概要</span><span class="sxs-lookup"><span data-stu-id="dd1b4-104">SYNOPSIS</span></span>
<span data-ttu-id="dd1b4-105">現在のセッションで実行されている PowerShell バックグラウンドジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-105">Gets PowerShell background jobs that are running in the current session.</span></span>

## <span data-ttu-id="dd1b4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dd1b4-106">SYNTAX</span></span>

### <span data-ttu-id="dd1b4-107">SessionIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="dd1b4-107">SessionIdParameterSet (Default)</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="dd1b4-108">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="dd1b4-108">InstanceIdParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="dd1b4-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="dd1b4-109">NameParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="dd1b4-110">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="dd1b4-110">StateParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="dd1b4-111">CommandParameterSet</span><span class="sxs-lookup"><span data-stu-id="dd1b4-111">CommandParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="dd1b4-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="dd1b4-112">FilterParameterSet</span></span>

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="dd1b4-113">Description</span><span class="sxs-lookup"><span data-stu-id="dd1b4-113">DESCRIPTION</span></span>

<span data-ttu-id="dd1b4-114">**Get-Job** コマンドレットは、現在のセッションで開始されたバックグラウンド ジョブを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-114">The **Get-Job** cmdlet gets objects that represent the background jobs that were started in the current session.</span></span> <span data-ttu-id="dd1b4-115">Start-Job コマンドレットを使用するか、任意のコマンドレットの *AsJob* パラメーターを使用して、開始されたジョブを **取得すること** ができます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-115">You can use **Get-Job** to get jobs that were started by using the Start-Job cmdlet, or by using the *AsJob* parameter of any cmdlet.</span></span>

<span data-ttu-id="dd1b4-116">パラメーターを指定しない場合、 **Get Job** コマンドは、現在のセッション内のすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-116">Without parameters, a **Get-Job** command gets all jobs in the current session.</span></span>
<span data-ttu-id="dd1b4-117">**Get-Job** のパラメーターを使用すると、特定のジョブを取得できます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-117">You can use the parameters of **Get-Job** to get particular jobs.</span></span>

<span data-ttu-id="dd1b4-118">**Get-Job** から返されるジョブ オブジェクトには、ジョブに関する有用な情報が含まれていますが、ジョブの結果は含まれません。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-118">The job object that **Get-Job** returns contains useful information about the job, but it does not contain the job results.</span></span> <span data-ttu-id="dd1b4-119">結果を取得するには、Receive-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-119">To get the results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="dd1b4-120">PowerShell バックグラウンドジョブは、現在のセッションと対話せずにバックグラウンドで実行されるコマンドです。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-120">A PowerShell background job is a command that runs in the background without interacting with the current session.</span></span> <span data-ttu-id="dd1b4-121">通常は、バックグラウンドジョブを使用して、完了までに時間がかかる複雑なコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-121">Typically, you use a background job to run a complex command that takes a long time to finish.</span></span> <span data-ttu-id="dd1b4-122">PowerShell のバックグラウンドジョブの詳細については、「about_Jobs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-122">For more information about background jobs in PowerShell, see about_Jobs.</span></span>

<span data-ttu-id="dd1b4-123">Windows PowerShell 3.0 以降では、 **Get-Job** コマンドレットを使用して、ワークフロー ジョブ、スケジュールされたジョブのインスタンスなどのカスタムのジョブの種類を取得できます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-123">Beginning in Windows PowerShell 3.0, the **Get-Job** cmdlet also gets custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="dd1b4-124">ジョブの種類を調べるには、ジョブの **PSJobTypeName** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-124">To find the job type of a job, use the **PSJobTypeName** property of the job.</span></span>

<span data-ttu-id="dd1b4-125">カスタムジョブの種類を **取得できるようにするに** は、カスタムジョブの種類をサポートするモジュールをセッションにインポートしてから、 **Import-Module コマンドレット** を使用するか、またはモジュールのコマンドレットを使用または取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-125">To enable **Get-Job** to get a custom job type, import the module that supports the custom job type into the session before you run a **Get-Job** command, either by using the Import-Module cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="dd1b4-126">特定のカスタム ジョブの種類については、カスタムのジョブの種類機能のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-126">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="dd1b4-127">例</span><span class="sxs-lookup"><span data-stu-id="dd1b4-127">EXAMPLES</span></span>

### <span data-ttu-id="dd1b4-128">例 1: 現在のセッションで開始されているすべてのバックグラウンドジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="dd1b4-128">Example 1: Get all background jobs started in the current session</span></span>

```powershell
Get-Job
```

<span data-ttu-id="dd1b4-129">このコマンドは、現在のセッションで開始されたすべてのバックグラウンド ジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-129">This command gets all background jobs started in the current session.</span></span>
<span data-ttu-id="dd1b4-130">ローカル コンピューター上でジョブが実行される場合でも、他のセッションで作成されたジョブは含まれません。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-130">It does not include jobs created in other sessions, even if the jobs run on the local computer.</span></span>

### <span data-ttu-id="dd1b4-131">例 2: インスタンス ID を使用してジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="dd1b4-131">Example 2: Stop a job by using an instance ID</span></span>

<span data-ttu-id="dd1b4-132">ジョブのインスタンス ID を取得し、それを使用してジョブを停止する方法を次のコマンドに示します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-132">These commands show how to get the instance ID of a job and then use it to stop a job.</span></span>
<span data-ttu-id="dd1b4-133">一意ではないジョブ名とは異なり、インスタンス ID は一意です。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-133">Unlike the name of a job, which is not unique, the instance ID is unique.</span></span>

```powershell
$j = Get-Job -Name Job1
$ID = $j.InstanceID
$ID
```

```Output
Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55
```

```powershell
Stop-Job -InstanceId $ID
```

<span data-ttu-id="dd1b4-134">最初のコマンドは、 **Get-Job** コマンドレットを使用して、ジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-134">The first command uses the **Get-Job** cmdlet to get a job.</span></span> <span data-ttu-id="dd1b4-135">この例では、 *Name* パラメーターを使用してジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-135">It uses the *Name* parameter to identify the job.</span></span> <span data-ttu-id="dd1b4-136">このコマンドは、 **Get-Job** から返されたジョブ オブジェクトを $j 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-136">The command stores the job object that **Get-Job** returns in the $j variable.</span></span> <span data-ttu-id="dd1b4-137">この例では、指定された名前のジョブが 1 つだけあります。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-137">In this example, there is only one job with the specified name.</span></span>

<span data-ttu-id="dd1b4-138">2 番目のコマンドは、$j 変数内のオブジェクトの **InstanceId** プロパティを取得して、$ID 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-138">The second command gets the **InstanceId** property of the object in the $j variable and stores it in the $ID variable.</span></span>

<span data-ttu-id="dd1b4-139">3 番目のコマンドは、$ID 変数の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-139">The third command displays the value of the $ID variable.</span></span>

<span data-ttu-id="dd1b4-140">4番目のコマンドは、Stop-Job コマンドレットを使用してジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-140">The fourth command uses Stop-Job cmdlet to stop the job.</span></span> <span data-ttu-id="dd1b4-141">*InstanceId* パラメーターを使用してジョブを識別し、$ID 変数を使用してインスタンス ID を表しています。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-141">It uses the *InstanceId* parameter to identify the job and $ID variable to represent the instance ID of the job.</span></span>

### <span data-ttu-id="dd1b4-142">例 3: 特定のコマンドを含むジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="dd1b4-142">Example 3: Get jobs that include a specific command</span></span>

```powershell
Get-Job -Command "*get-process*"
```

<span data-ttu-id="dd1b4-143">このコマンドは、Get-Process コマンドを含むシステム上のジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-143">This command gets the jobs on the system that include a Get-Process command.</span></span> <span data-ttu-id="dd1b4-144">このコマンドは、 *Get-Job* の **Command** パラメーターを使用して取得するジョブを制限します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-144">The command uses the *Command* parameter of **Get-Job** to limit the jobs retrieved.</span></span> <span data-ttu-id="dd1b4-145">コマンドは、ワイルドカード文字 (\*) を使用して、コマンド文字列内の任意の場所にある **Get Process** コマンドを含むジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-145">The command uses wildcard characters (\*) to get jobs that include a **Get-Process** command anywhere in the command string.</span></span>

### <span data-ttu-id="dd1b4-146">例 4: パイプラインを使用して特定のコマンドを含むジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="dd1b4-146">Example 4: Get jobs that include a specific command by using the pipeline</span></span>

```powershell
"*get-process*" | Get-Job
```

<span data-ttu-id="dd1b4-147">前の例のコマンドと同様に、このコマンドは、 **Get Process** コマンドを含むシステム上のジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-147">Like the command in the previous example, this command gets the jobs on the system that include a **Get-Process** command.</span></span> <span data-ttu-id="dd1b4-148">このコマンドは、パイプライン演算子 (|) を使用して、文字列を引用符で囲んだ **後、コマンドレットに** 送信します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-148">The command uses a pipeline operator (|) to send a string, in quotation marks, to the **Get-Job** cmdlet.</span></span> <span data-ttu-id="dd1b4-149">これは、前のコマンドと同等です。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-149">It is the equivalent of the previous command.</span></span>

### <span data-ttu-id="dd1b4-150">例 5: 開始されていないジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="dd1b4-150">Example 5: Get jobs that have not been started</span></span>

```powershell
Get-Job -State NotStarted
```

<span data-ttu-id="dd1b4-151">このコマンドは、作成されている一方でまだ開始されていないジョブのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-151">This command gets only those jobs that have been created but have not yet been started.</span></span>
<span data-ttu-id="dd1b4-152">これには、後で実行するようにスケジュール設定されているジョブとまだスケジュール設定されていないジョブが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-152">This includes jobs that are scheduled to run in the future and those not yet scheduled.</span></span>

### <span data-ttu-id="dd1b4-153">例 6: 名前が割り当てられていないジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="dd1b4-153">Example 6: Get jobs that have not been assigned a name</span></span>

```powershell
Get-Job -Name Job*
```

<span data-ttu-id="dd1b4-154">このコマンドは、job で始まるジョブ名を持つすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-154">This command gets all jobs that have job names that begin with job.</span></span>
<span data-ttu-id="dd1b4-155">Job \<number\> はジョブの既定の名前であるため、このコマンドは、明示的に名前が割り当てられていないすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-155">Because job\<number\> is the default name for a job, this command gets all jobs that do not have an explicitly assigned name.</span></span>

### <span data-ttu-id="dd1b4-156">例 7: ジョブオブジェクトを使用してコマンド内のジョブを表す</span><span class="sxs-lookup"><span data-stu-id="dd1b4-156">Example 7: Use a job object to represent the job in a command</span></span>

<span data-ttu-id="dd1b4-157">この例は、 **Get-Job** を使用してジョブ オブジェクトを取得した後、そのジョブ オブジェクトを使用してコマンド内のジョブを表す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-157">This example shows how to use **Get-Job** to get a job object, and then it shows how to use the job object to represent the job in a command.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process} -Name MyJob
$j = Get-Job -Name MyJob
$j
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process
```

```powershell
Receive-Job -Job $j
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```

<span data-ttu-id="dd1b4-158">最初のコマンドは、 **開始ジョブ** コマンドレットを使用して、ローカルコンピューターで **Get Process** コマンドを実行するバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-158">The first command uses the **Start-Job** cmdlet to start a background job that runs a **Get-Process** command on the local computer.</span></span> <span data-ttu-id="dd1b4-159">このコマンドでは、 *Start-Job* の **Name** パラメーターを使用して、ジョブにフレンドリ名を割り当てています。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-159">The command uses the *Name* parameter of **Start-Job** to assign a friendly name to the job.</span></span>

<span data-ttu-id="dd1b4-160">2 番目のコマンドは、Get-Job を使用してジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-160">The second command uses Get-Job to get the job.</span></span> <span data-ttu-id="dd1b4-161">ジョブを識別するために *Get-Job* の **Name** パラメーターが使用されています。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-161">It uses the *Name* parameter of **Get-Job** to identify the job.</span></span> <span data-ttu-id="dd1b4-162">このコマンドは、結果のジョブ オブジェクトを $j 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-162">The command saves the resulting job object in the $j variable.</span></span>

<span data-ttu-id="dd1b4-163">3 番目のコマンドは、$j 変数内のジョブ オブジェクトの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-163">The third command displays the value of the job object in the $j variable.</span></span> <span data-ttu-id="dd1b4-164">**State** プロパティの値は、ジョブが完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-164">The value of the **State** property shows that the job is completed.</span></span> <span data-ttu-id="dd1b4-165">**HasMoreData** プロパティの値は、このジョブに関してまだ取得されていない結果があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-165">The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.</span></span>

<span data-ttu-id="dd1b4-166">4番目のコマンドは **、job コマンドレットを** 使用して、ジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-166">The fourth command uses the **Receive-Job** cmdlet to get the results of the job.</span></span> <span data-ttu-id="dd1b4-167">ジョブを表すために、$j 変数内のジョブ オブジェクトが使用されています。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-167">It uses the job object in the $j variable to represent the job.</span></span> <span data-ttu-id="dd1b4-168">パイプライン演算子を使用して、ジョブオブジェクトを **受信ジョブ** に送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-168">You can also use a pipeline operator to send a job object to **Receive-Job**.</span></span>

### <span data-ttu-id="dd1b4-169">例 8: 別の方法で開始されたジョブを含むすべてのジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="dd1b4-169">Example 8: Get all jobs including jobs started by a different method</span></span>

<span data-ttu-id="dd1b4-170">この例では、別の方法を使用して開始された場合でも、 **Get Job** コマンドレットを使用して、現在のセッションで開始されたすべてのジョブを取得できることを示します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-170">This example demonstrates that the **Get-Job** cmdlet can get all of the jobs that were started in the current session, even if they were started by using different methods.</span></span>

```powershell
Start-Job -ScriptBlock {Get-EventLog System}
Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob
Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Get-Job
```

```Output
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System
```

```powershell
Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
```

```Output
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

<span data-ttu-id="dd1b4-171">最初のコマンドは、 **Start ジョブ** コマンドレットを使用して、ローカルコンピューター上でジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-171">The first command uses the **Start-Job** cmdlet to start a job on the local computer.</span></span>

<span data-ttu-id="dd1b4-172">2番目のコマンドは、 **コマンド** レットの *AsJob* パラメーターを使用して、S1 コンピューターでジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-172">The second command uses the *AsJob* parameter of the **Invoke-Command** cmdlet to start a job on the S1 computer.</span></span> <span data-ttu-id="dd1b4-173">ジョブに含まれるコマンドがリモート コンピューター上で実行される場合でもジョブ オブジェクトがローカル コンピューターに作成されるため、ローカル コマンドを使用してジョブを管理します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-173">Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.</span></span>

<span data-ttu-id="dd1b4-174">3 番目のコマンドは、 **Invoke-Command** コマンドレットを使用して、S2 コンピューター上で **Start-Job** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-174">The third command uses the **Invoke-Command** cmdlet to run a **Start-Job** command on the S2 computer.</span></span> <span data-ttu-id="dd1b4-175">この方法を使用すると、ジョブオブジェクトがリモートコンピューター上に作成されるため、リモートコマンドを使用してジョブを管理します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-175">By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.</span></span>

<span data-ttu-id="dd1b4-176">4 番目のコマンドは、 **Get-Job** を使用して、ローカル コンピューター上に格納されているジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-176">The fourth command uses **Get-Job** to get the jobs stored on the local computer.</span></span> <span data-ttu-id="dd1b4-177">Windows PowerShell 3.0 で導入されたジョブの **PSJobTypeName** プロパティには、 **開始ジョブ** コマンドレットを使用して開始したローカルジョブがバックグラウンドジョブであり、 **Invoke コマンド** レットを使用してリモートセッションで開始されたジョブがリモートジョブであることが示されています。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-177">The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the **Start-Job** cmdlet is a background job and the job started in a remote session by using the **Invoke-Command** cmdlet is a remote job.</span></span>

<span data-ttu-id="dd1b4-178">5番目のコマンドは、 **コマンド** を使用して、S2 コンピューター上で **Get ジョブ** コマンドを実行します。サンプル出力には、Get-Job コマンドの結果が示されています。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-178">The fifth command uses **Invoke-Command** to run a **Get-Job** command on the S2 computer.The sample output shows the results of the Get-Job command.</span></span> <span data-ttu-id="dd1b4-179">S2 コンピューター上では、ジョブはローカル ジョブとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-179">On the S2 computer, the job appears to be a local job.</span></span> <span data-ttu-id="dd1b4-180">コンピューター名は localhost で、ジョブの種類はバックグラウンドジョブです。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-180">The computer name is localhost and the job type is a background job.</span></span>

<span data-ttu-id="dd1b4-181">リモートコンピューターでバックグラウンドジョブを実行する方法の詳細については、「about_Remote_Jobs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-181">For more information about how to run background jobs on remote computers, see about_Remote_Jobs.</span></span>

### <span data-ttu-id="dd1b4-182">例 9: 失敗したジョブを調査する</span><span class="sxs-lookup"><span data-stu-id="dd1b4-182">Example 9: Investigate a failed job</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process}
```

```Output
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process
```

```powershell
(Get-Job).JobStateInfo | Format-List -Property *
```

```Output
State  : Failed
Reason :
```

```powershell
Get-Job | Format-List -Property *
```

```Output
HasMoreData   : False
StatusMessage :
Location      : localhost
Command       : get-process
JobStateInfo  : Failed
Finished      : System.Threading.ManualReset
EventInstanceId    : fb792295-1318-4f5d-8ac8-8a89c5261507
Id            : 1
Name          : Job1
ChildJobs     : {Job2}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :
```

```powershell
(Get-Job -Name job2).JobStateInfo.Reason
```

```Output
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the following error message: Access is denied.

For information about requirements for remoting in PowerShell, see about_Remote_Requirements. For
troubleshooting tips, see about_Remote_Troubleshooting.
```

<span data-ttu-id="dd1b4-183">このコマンドは、job が返すジョブオブジェクトを使用 **して、** ジョブが失敗した原因を調査する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-183">This command shows how to use the job object that **Get-Job** returns to investigate why a job failed.</span></span>
<span data-ttu-id="dd1b4-184">また、各ジョブの子ジョブを取得する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-184">It also shows how to get the child jobs of each job.</span></span>

<span data-ttu-id="dd1b4-185">最初のコマンドは、 **Start ジョブ** コマンドレットを使用して、ローカルコンピューター上でジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-185">The first command uses the **Start-Job** cmdlet to start a job on the local computer.</span></span> <span data-ttu-id="dd1b4-186">**Start-Job** から返されるジョブ オブジェクトは、ジョブが失敗したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-186">The job object that **Start-Job** returns shows that the job failed.</span></span> <span data-ttu-id="dd1b4-187">**State** プロパティの値が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-187">The value of the **State** property is Failed.</span></span>

<span data-ttu-id="dd1b4-188">2 番目のコマンドは、 **Get-Job** コマンドレットを使用して、ジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-188">The second command uses the **Get-Job** cmdlet to get the job.</span></span> <span data-ttu-id="dd1b4-189">ここでは、ドット表記を使用してオブジェクトの **JobStateInfo** プロパティの値を取得しています。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-189">The command uses the dot method to get the value of the **JobStateInfo** property of the object.</span></span> <span data-ttu-id="dd1b4-190">パイプライン演算子を使用して、 **Jobstateinfo** プロパティのオブジェクトを Format-List コマンドレットに送信します。これにより、オブジェクト (\*) のすべてのプロパティが一覧表示されます。 **形式一覧** コマンドの結果は、ジョブの **Reason** プロパティの値が空白であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-190">It uses a pipeline operator to send the object in the **JobStateInfo** property to the Format-List cmdlet, which formats all of the properties of the object (\*) in a list.The result of the **Format-List** command shows that the value of the **Reason** property of the job is blank.</span></span>

<span data-ttu-id="dd1b4-191">3番目のコマンドは、詳細を調査します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-191">The third command investigates more.</span></span> <span data-ttu-id="dd1b4-192">このコマンドは、ジョブを取得するために、 **Get job** コマンドを使用します。次に、パイプライン演算子を使用して、ジョブオブジェクト全体を一覧表示します。このコマンドレットに **より** 、ジョブのすべてのプロパティがリストに表示されます。Job オブジェクトのすべてのプロパティの表示は、そのジョブに Job2 という名前の子ジョブが含まれていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-192">It uses a **Get-Job** command to get the job and then uses a pipeline operator to send the whole job object to the **Format-List** cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.</span></span>

<span data-ttu-id="dd1b4-193">4 番目のコマンドは、 **Get-Job** を使用して、Job2 子ジョブを表すジョブ オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-193">The fourth command uses **Get-Job** to get the job object that represents the Job2 child job.</span></span> <span data-ttu-id="dd1b4-194">これは、コマンドが実際に実行されたジョブです。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-194">This is the job in which the command actually ran.</span></span> <span data-ttu-id="dd1b4-195">ここでは、ドットメソッドを使用して、 **Jobstateinfo** プロパティの **Reason** プロパティを取得します。結果には、アクセス拒否エラーによってジョブが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-195">It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error.</span></span> <span data-ttu-id="dd1b4-196">この場合、ユーザーは PowerShell の起動時に [管理者として実行] オプションを使用していません。バックグラウンドジョブは、PowerShell のリモート処理機能を使用するため、ローカルコンピューターでジョブが実行されている場合でも、ジョブを実行するリモート処理用にコンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-196">In this case, the user forgot to use the Run as administrator option when starting PowerShell.Because background jobs use the remoting features of PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.</span></span>

### <span data-ttu-id="dd1b4-197">例 10: フィルター処理された結果を取得する</span><span class="sxs-lookup"><span data-stu-id="dd1b4-197">Example 10: Get filtered results</span></span>

<span data-ttu-id="dd1b4-198">この例では、 *Filter* パラメーターを使用してワークフロー ジョブを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-198">This example shows how to use the *Filter* parameter to get a workflow job.</span></span>
<span data-ttu-id="dd1b4-199">Windows PowerShell 3.0 で導入された *Filter* パラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-199">The *Filter* parameter, introduced in Windows PowerShell 3.0 is valid only on custom job types, such as workflow jobs and scheduled jobs.</span></span>

```powershell
Workflow WFProcess {Get-Process}
WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}
Get-Job -Filter @{MyCustomId = 92107}
```

```Output
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

<span data-ttu-id="dd1b4-200">最初のコマンドは、 **workflow** キーワードを使用して、ワークフローのワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-200">The first command uses the **Workflow** keyword to create the WFProcess workflow.</span></span>

<span data-ttu-id="dd1b4-201">2番目のコマンドは、ワークフローをバックグラウンドジョブとして実行するために、処理されたプロセスワークフローの *AsJob* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-201">The second command uses the *AsJob* parameter of the WFProcess workflow to run the workflow as a background job.</span></span> <span data-ttu-id="dd1b4-202">ここでは、ワークフローの *JobName* パラメーターを使用してジョブの名前を指定し、ワークフローの *PSPrivateMetadata* パラメーターを使用してカスタム ID を指定しています。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-202">It uses the *JobName* parameter of the workflow to specify a name for the job, and the *PSPrivateMetadata* parameter of the workflow to specify a custom ID.</span></span>

<span data-ttu-id="dd1b4-203">3 番目のコマンドでは、 *Get-Job* の **Filter** パラメーターを使用して、 *PSPrivateMetadata* パラメーターで指定されたカスタム ID でジョブを取得しています。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-203">The third command uses the *Filter* parameter of **Get-Job** to get the job by custom ID that was specified in the *PSPrivateMetadata* parameter.</span></span>

### <span data-ttu-id="dd1b4-204">例 11: 子ジョブに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="dd1b4-204">Example 11: Get information about child jobs</span></span>

<span data-ttu-id="dd1b4-205">この例は、 *Get-Job* コマンドレットの *IncludeChildJob* パラメーターと **ChildJobState** パラメーターを使用した場合の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-205">This example shows the effect of using the *IncludeChildJob* and *ChildJobState* parameters of the **Get-Job** cmdlet.</span></span>

```powershell
Get-Job
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
```

```powershell
Get-Job -IncludeChildJob
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
3      Job3                            Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
6      Job6                            Completed     True            Server02            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
```

```powershell
Get-Job -Name Job4 -ChildJobState Failed
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
```

```powershell
(Get-Job -Name Job5).JobStateInfo.Reason
```

```Output
Connecting to remote server Server01 failed with the following error message:
Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
```

<span data-ttu-id="dd1b4-206">最初のコマンドは、現在のセッション内のジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-206">The first command gets the jobs in the current session.</span></span> <span data-ttu-id="dd1b4-207">出力には、バックグラウンド ジョブ、リモート ジョブ、およびスケジュールされたジョブのいくつかのインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-207">The output includes a background job, a remote job and several instances of a scheduled job.</span></span> <span data-ttu-id="dd1b4-208">リモート ジョブ Job4 については、失敗したことが示されています。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-208">The remote job, Job4, appears to have failed.</span></span>

<span data-ttu-id="dd1b4-209">2 番目のコマンドは、 *Get-Job* の **IncludeChildJob** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-209">The second command uses the *IncludeChildJob* parameter of **Get-Job**.</span></span> <span data-ttu-id="dd1b4-210">出力には、子ジョブを持つすべてのジョブの子ジョブが追加されます。この場合、変更後の出力には、Job4 の Job5 子ジョブのみが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-210">The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.</span></span>

<span data-ttu-id="dd1b4-211">3番目のコマンドは、 *Childjobstate* パラメーターを使用して、値が failed であることを示します。出力には、すべての親ジョブと、失敗した子ジョブのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-211">The third command uses the *ChildJobState* parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.</span></span>

<span data-ttu-id="dd1b4-212">4番目のコマンドは、jobs の **Jobstateinfo** プロパティと **Reason** プロパティを使用して、Job5 が失敗した理由を検出します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-212">The fourth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.</span></span>

## <span data-ttu-id="dd1b4-213">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dd1b4-213">PARAMETERS</span></span>

### <span data-ttu-id="dd1b4-214">-After</span><span class="sxs-lookup"><span data-stu-id="dd1b4-214">-After</span></span>

<span data-ttu-id="dd1b4-215">指定された日時以降に終了した完了済みのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-215">Gets completed jobs that ended after the specified date and time.</span></span> <span data-ttu-id="dd1b4-216">**Datetime** オブジェクトを入力します。たとえば、Get-Date コマンドレットによって返されるオブジェクトや、 **datetime** オブジェクトに変換できる文字列 (やなど) を入力し `Dec 1, 2012 2:00 AM` `11/06` ます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-216">Enter a **DateTime** object, such as one returned by the Get-Date cmdlet or a string that can be converted to a **DateTime** object, such as `Dec 1, 2012 2:00 AM` or `11/06`.</span></span>

<span data-ttu-id="dd1b4-217">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、 **EndTime** プロパティを持つカスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-217">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="dd1b4-218">これは、 **開始ジョブ** コマンドレットを使用して作成されたジョブなど、標準のバックグラウンドジョブでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-218">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span> <span data-ttu-id="dd1b4-219">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-219">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="dd1b4-220">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-220">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd1b4-221">-Before</span><span class="sxs-lookup"><span data-stu-id="dd1b4-221">-Before</span></span>

<span data-ttu-id="dd1b4-222">指定された日時以前に終了した完了済みのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-222">Gets completed jobs that ended before the specified date and time.</span></span>
<span data-ttu-id="dd1b4-223">**DateTime** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-223">Enter a **DateTime** object.</span></span>

<span data-ttu-id="dd1b4-224">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、 **EndTime** プロパティを持つカスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-224">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="dd1b4-225">これは、 **開始ジョブ** コマンドレットを使用して作成されたジョブなど、標準のバックグラウンドジョブでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-225">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span> <span data-ttu-id="dd1b4-226">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-226">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="dd1b4-227">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-227">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd1b4-228">-ChildJobState</span><span class="sxs-lookup"><span data-stu-id="dd1b4-228">-ChildJobState</span></span>

<span data-ttu-id="dd1b4-229">指定された状態を持つ子ジョブのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-229">Gets only the child jobs that have the specified state.</span></span>
<span data-ttu-id="dd1b4-230">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-230">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="dd1b4-231">NotStarted</span><span class="sxs-lookup"><span data-stu-id="dd1b4-231">NotStarted</span></span>
- <span data-ttu-id="dd1b4-232">実行中</span><span class="sxs-lookup"><span data-stu-id="dd1b4-232">Running</span></span>
- <span data-ttu-id="dd1b4-233">完了</span><span class="sxs-lookup"><span data-stu-id="dd1b4-233">Completed</span></span>
- <span data-ttu-id="dd1b4-234">失敗</span><span class="sxs-lookup"><span data-stu-id="dd1b4-234">Failed</span></span>
- <span data-ttu-id="dd1b4-235">停止済み</span><span class="sxs-lookup"><span data-stu-id="dd1b4-235">Stopped</span></span>
- <span data-ttu-id="dd1b4-236">Blocked</span><span class="sxs-lookup"><span data-stu-id="dd1b4-236">Blocked</span></span>
- <span data-ttu-id="dd1b4-237">Suspended</span><span class="sxs-lookup"><span data-stu-id="dd1b4-237">Suspended</span></span>
- <span data-ttu-id="dd1b4-238">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="dd1b4-238">Disconnected</span></span>
- <span data-ttu-id="dd1b4-239">中断中</span><span class="sxs-lookup"><span data-stu-id="dd1b4-239">Suspending</span></span>
- <span data-ttu-id="dd1b4-240">停止中</span><span class="sxs-lookup"><span data-stu-id="dd1b4-240">Stopping</span></span>

<span data-ttu-id="dd1b4-241">既定では、 **Get-Job** は子ジョブを取得しません。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-241">By default, **Get-Job** does not get child jobs.</span></span>
<span data-ttu-id="dd1b4-242">*IncludeChildJob* パラメーターを使用すると **、すべて** の子ジョブが取得されます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-242">By using the *IncludeChildJob* parameter, **Get-Job** gets all child jobs.</span></span>
<span data-ttu-id="dd1b4-243">*ChildJobState* パラメーターを使用した場合、 *IncludeChildJob* パラメーターは効果を持ちません。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-243">If you use the *ChildJobState* parameter, the *IncludeChildJob* parameter has no effect.</span></span>

<span data-ttu-id="dd1b4-244">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-244">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd1b4-245">-Command</span><span class="sxs-lookup"><span data-stu-id="dd1b4-245">-Command</span></span>

<span data-ttu-id="dd1b4-246">コマンドの配列を文字列として指定します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-246">Specifies an array of commands as strings.</span></span>
<span data-ttu-id="dd1b4-247">このコマンドレットは、指定されたコマンドを含むジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-247">This cmdlet gets the jobs that include the specified commands.</span></span>
<span data-ttu-id="dd1b4-248">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-248">The default is all jobs.</span></span>
<span data-ttu-id="dd1b4-249">ワイルドカード文字を使用すると、コマンドパターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-249">You can use wildcard characters to specify a command pattern.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="dd1b4-250">-Filter</span><span class="sxs-lookup"><span data-stu-id="dd1b4-250">-Filter</span></span>

<span data-ttu-id="dd1b4-251">条件のハッシュテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-251">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="dd1b4-252">このコマンドレットは、すべての条件に適合するジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-252">This cmdlet gets jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="dd1b4-253">ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-253">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="dd1b4-254">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-254">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span>
<span data-ttu-id="dd1b4-255">これは、 **開始ジョブ** コマンドレットを使用して作成されたジョブなど、標準のバックグラウンドジョブでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-255">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="dd1b4-256">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-256">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="dd1b4-257">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-257">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dd1b4-258">-Hasdata</span><span class="sxs-lookup"><span data-stu-id="dd1b4-258">-HasMoreData</span></span>

<span data-ttu-id="dd1b4-259">このコマンドレットが、指定された **hasを持つデータ** プロパティ値を持つジョブのみを取得するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-259">Indicates whether this cmdlet gets only jobs that have the specified **HasMoreData** property value.</span></span>
<span data-ttu-id="dd1b4-260">**HasMoreData** プロパティは、すべてのジョブの結果が現在のセッションで受け取られたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-260">The **HasMoreData** property indicates whether all job results have been received in the current session.</span></span>
<span data-ttu-id="dd1b4-261">より多くの結果を持つジョブを取得するには、$True の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-261">To get jobs that have more results, specify a value of $True.</span></span>
<span data-ttu-id="dd1b4-262">より多くの結果が得られないジョブを取得するには、$False の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-262">To get jobs that do not have more results, specify a value of $False.</span></span>

<span data-ttu-id="dd1b4-263">ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-263">To get the results of a job, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="dd1b4-264">**Receive-Job** コマンドレットを使用すると、メモリ内のセッション固有のストレージから、返された結果が削除されます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-264">When you use the **Receive-Job** cmdlet, it deletes from its in-memory, session-specific storage the results that it returned.</span></span> <span data-ttu-id="dd1b4-265">現在のセッションでジョブのすべての結果が返された場合は、ジョブの **Hasmore data** プロパティの値を $False) に設定して、現在のセッションにジョブの結果がなくなったことを示します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-265">When it has returned all results of the job in the current session, it sets the value of the **HasMoreData** property of the job to $False) to indicate that it has no more results for the job in the current session.</span></span> <span data-ttu-id="dd1b4-266">*Receive-Job* が結果を削除して **HasMoreData** プロパティの値を変更しないようにするには、 **Receive-Job** の **Keep** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-266">Use the *Keep* parameter of **Receive-Job** to prevent **Receive-Job** from deleting results and changing the value of the **HasMoreData** property.</span></span> <span data-ttu-id="dd1b4-267">詳細を表示するには「`Get-Help Receive-Job`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-267">For more information, type `Get-Help Receive-Job`.</span></span>

<span data-ttu-id="dd1b4-268">**HasMoreData** プロパティは、現在のセッションに固有です。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-268">The **HasMoreData** property is specific to the current session.</span></span> <span data-ttu-id="dd1b4-269">ジョブの結果をディスクに保存するスケジュールされたジョブの種類など、カスタムジョブの種類の結果がセッションの外部に保存される場合は、 **Hasdata** の値が $False 場合でも、別のセッションで **Receive-job** コマンドレットを使用して、ジョブの結果を再度取得できます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-269">If results for a custom job type are saved outside of the session, such as the scheduled job type, which saves job results on disk, you can use the **Receive-Job** cmdlet in a different session to get the job results again, even if the value of **HasMoreData** is $False.</span></span> <span data-ttu-id="dd1b4-270">詳細については、カスタムのジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-270">For more information, see the help topics for the custom job type.</span></span>

<span data-ttu-id="dd1b4-271">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-271">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd1b4-272">-Id</span><span class="sxs-lookup"><span data-stu-id="dd1b4-272">-Id</span></span>

<span data-ttu-id="dd1b4-273">このコマンドレットが取得するジョブの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-273">Specifies an array of IDs of jobs that this cmdlet gets.</span></span>

<span data-ttu-id="dd1b4-274">ID は、現在のセッションでジョブを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-274">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="dd1b4-275">インスタンス ID よりも覚えやすく、入力する方が簡単ですが、現在のセッションでのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-275">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="dd1b4-276">1つ以上の Id をコンマで区切って入力できます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-276">You can type one or more IDs separated by commas.</span></span>
<span data-ttu-id="dd1b4-277">ジョブの ID を検索するには、パラメーターを指定せずに「」と入力 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-277">To find the ID of a job, type `Get-Job` without parameters.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="dd1b4-278">-IncludeChildJob</span><span class="sxs-lookup"><span data-stu-id="dd1b4-278">-IncludeChildJob</span></span>

<span data-ttu-id="dd1b4-279">このコマンドレットが親ジョブに加えて子ジョブも返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-279">Indicates that this cmdlet returns child jobs, in addition to parent jobs.</span></span>

<span data-ttu-id="dd1b4-280">このパラメーターは、エラーの原因が子ジョブのプロパティに保存されているので、ワークフロージョブを調査する場合に特に便利です。この場合、ジョブの親ジョブとジョブの失敗 **が返され** ます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-280">This parameter is especially useful for investigating workflow jobs, for which **Get-Job** returns a container parent job, and job failures, because the reason for the failure is saved in a property of the child job.</span></span>

<span data-ttu-id="dd1b4-281">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-281">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd1b4-282">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="dd1b4-282">-InstanceId</span></span>

<span data-ttu-id="dd1b4-283">このコマンドレットが取得するジョブのインスタンス Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-283">Specifies an array of instance IDs of jobs that this cmdlet gets.</span></span>
<span data-ttu-id="dd1b4-284">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-284">The default is all jobs.</span></span>

<span data-ttu-id="dd1b4-285">インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-285">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="dd1b4-286">ジョブのインスタンス ID を調べるには、 **Get-Job** を使用します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-286">To find the instance ID of a job, use **Get-Job**.</span></span>

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

### <span data-ttu-id="dd1b4-287">-Name</span><span class="sxs-lookup"><span data-stu-id="dd1b4-287">-Name</span></span>

<span data-ttu-id="dd1b4-288">このコマンドレットが取得するジョブのインスタンスフレンドリ名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-288">Specifies an array of instance friendly names of jobs that this cmdlet gets.</span></span>
<span data-ttu-id="dd1b4-289">ジョブの名前を入力するか、またはワイルドカード文字を使用してジョブ名のパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-289">Enter a job name, or use wildcard characters to enter a job name pattern.</span></span>
<span data-ttu-id="dd1b4-290">既定では、 **Get-Job** は、現在のセッション内のすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-290">By default, **Get-Job** gets all jobs in the current session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="dd1b4-291">-最新</span><span class="sxs-lookup"><span data-stu-id="dd1b4-291">-Newest</span></span>

<span data-ttu-id="dd1b4-292">取得するジョブの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-292">Specifies a number of jobs to get.</span></span>
<span data-ttu-id="dd1b4-293">このコマンドレットは、最後に終了したジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-293">This cmdlet gets the jobs that ended most recently.</span></span>

<span data-ttu-id="dd1b4-294">*Newest* パラメーターは、並べ替えを行わずに、終了時刻の順で最も新しいジョブを返します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-294">The *Newest* parameter does not sort or return the newest jobs in end-time order.</span></span>
<span data-ttu-id="dd1b4-295">出力を並べ替えるには、Sort-Object コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-295">To sort the output, use the Sort-Object cmdlet.</span></span>

<span data-ttu-id="dd1b4-296">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-296">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dd1b4-297">-状態</span><span class="sxs-lookup"><span data-stu-id="dd1b4-297">-State</span></span>

<span data-ttu-id="dd1b4-298">ジョブの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-298">Specifies a job state.</span></span>
<span data-ttu-id="dd1b4-299">このコマンドレットは、指定された状態のジョブのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-299">This cmdlet gets only jobs in the specified state.</span></span>
<span data-ttu-id="dd1b4-300">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-300">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="dd1b4-301">NotStarted</span><span class="sxs-lookup"><span data-stu-id="dd1b4-301">NotStarted</span></span>
- <span data-ttu-id="dd1b4-302">実行中</span><span class="sxs-lookup"><span data-stu-id="dd1b4-302">Running</span></span>
- <span data-ttu-id="dd1b4-303">完了</span><span class="sxs-lookup"><span data-stu-id="dd1b4-303">Completed</span></span>
- <span data-ttu-id="dd1b4-304">失敗</span><span class="sxs-lookup"><span data-stu-id="dd1b4-304">Failed</span></span>
- <span data-ttu-id="dd1b4-305">停止済み</span><span class="sxs-lookup"><span data-stu-id="dd1b4-305">Stopped</span></span>
- <span data-ttu-id="dd1b4-306">Blocked</span><span class="sxs-lookup"><span data-stu-id="dd1b4-306">Blocked</span></span>
- <span data-ttu-id="dd1b4-307">Suspended</span><span class="sxs-lookup"><span data-stu-id="dd1b4-307">Suspended</span></span>
- <span data-ttu-id="dd1b4-308">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="dd1b4-308">Disconnected</span></span>
- <span data-ttu-id="dd1b4-309">中断中</span><span class="sxs-lookup"><span data-stu-id="dd1b4-309">Suspending</span></span>
- <span data-ttu-id="dd1b4-310">停止中</span><span class="sxs-lookup"><span data-stu-id="dd1b4-310">Stopping</span></span>

<span data-ttu-id="dd1b4-311">既定では、 **Get-Job** は、現在のセッション内のすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-311">By default, **Get-Job** gets all the jobs in the current session.</span></span>

<span data-ttu-id="dd1b4-312">ジョブの状態の詳細については、MSDN ライブラリの「 [Jobstate 列挙型](https://msdn.microsoft.com/library/system.management.automation.jobstate) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-312">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

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

### <span data-ttu-id="dd1b4-313">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="dd1b4-313">CommonParameters</span></span>

<span data-ttu-id="dd1b4-314">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-314">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dd1b4-315">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-315">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dd1b4-316">入力</span><span class="sxs-lookup"><span data-stu-id="dd1b4-316">INPUTS</span></span>

### <span data-ttu-id="dd1b4-317">なし</span><span class="sxs-lookup"><span data-stu-id="dd1b4-317">None</span></span>

<span data-ttu-id="dd1b4-318">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-318">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="dd1b4-319">出力</span><span class="sxs-lookup"><span data-stu-id="dd1b4-319">OUTPUTS</span></span>

### <span data-ttu-id="dd1b4-320">System. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="dd1b4-320">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="dd1b4-321">このコマンドレットは、セッション内のジョブを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-321">This cmdlet returns objects that represent the jobs in the session.</span></span>

## <span data-ttu-id="dd1b4-322">注</span><span class="sxs-lookup"><span data-stu-id="dd1b4-322">NOTES</span></span>

* <span data-ttu-id="dd1b4-323">ジョブの **PSJobTypeName** プロパティは、ジョブの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-323">The **PSJobTypeName** property of jobs indicates the job type of the job.</span></span> <span data-ttu-id="dd1b4-324">プロパティ値は、ジョブの種類の作成者によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-324">The property value is determined by the job type author.</span></span> <span data-ttu-id="dd1b4-325">次の一覧に、一般的なジョブの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-325">The following list shows common job types.</span></span>

  - <span data-ttu-id="dd1b4-326">**Backgroundjob** 。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-326">**BackgroundJob**.</span></span>
<span data-ttu-id="dd1b4-327">ローカルジョブは **、開始ジョブ** を使用して開始されました。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-327">Local job started by using **Start-Job**.</span></span>

  - <span data-ttu-id="dd1b4-328">**Remotejob** 。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-328">**RemoteJob**.</span></span>
<span data-ttu-id="dd1b4-329">Invoke-Command コマンドレットの *AsJob* パラメーターを使用して、 **PSSession** でジョブが開始されました。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-329">Job started in a **PSSession** by using the *AsJob* parameter of the Invoke-Command cmdlet.</span></span>

  - <span data-ttu-id="dd1b4-330">**Psworkflowjob** 。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-330">**PSWorkflowJob**.</span></span>
<span data-ttu-id="dd1b4-331">ワークフローの *AsJob* 共通パラメーターを使用して開始されたジョブ。</span><span class="sxs-lookup"><span data-stu-id="dd1b4-331">Job started by using the *AsJob* common parameter of workflows.</span></span>

## <span data-ttu-id="dd1b4-332">関連リンク</span><span class="sxs-lookup"><span data-stu-id="dd1b4-332">RELATED LINKS</span></span>

[<span data-ttu-id="dd1b4-333">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="dd1b4-333">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="dd1b4-334">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="dd1b4-334">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="dd1b4-335">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="dd1b4-335">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="dd1b4-336">Start-Job</span><span class="sxs-lookup"><span data-stu-id="dd1b4-336">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="dd1b4-337">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="dd1b4-337">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="dd1b4-338">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="dd1b4-338">Wait-Job</span></span>](Wait-Job.md)

