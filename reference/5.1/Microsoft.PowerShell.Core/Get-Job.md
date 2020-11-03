---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: 0b9c76ca1e26adaa244473366c2eabdaaa28452c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212032"
---
# <span data-ttu-id="a21bc-103">Get-Job</span><span class="sxs-lookup"><span data-stu-id="a21bc-103">Get-Job</span></span>

## <span data-ttu-id="a21bc-104">概要</span><span class="sxs-lookup"><span data-stu-id="a21bc-104">SYNOPSIS</span></span>
<span data-ttu-id="a21bc-105">現在のセッションで実行されている PowerShell バックグラウンドジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-105">Gets PowerShell background jobs that are running in the current session.</span></span>

## <span data-ttu-id="a21bc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a21bc-106">SYNTAX</span></span>

### <span data-ttu-id="a21bc-107">SessionIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="a21bc-107">SessionIdParameterSet (Default)</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="a21bc-108">CommandParameterSet</span><span class="sxs-lookup"><span data-stu-id="a21bc-108">CommandParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="a21bc-109">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="a21bc-109">InstanceIdParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="a21bc-110">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="a21bc-110">NameParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="a21bc-111">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="a21bc-111">StateParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="a21bc-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="a21bc-112">FilterParameterSet</span></span>

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="a21bc-113">Description</span><span class="sxs-lookup"><span data-stu-id="a21bc-113">DESCRIPTION</span></span>

<span data-ttu-id="a21bc-114">**Get-Job** コマンドレットは、現在のセッションで開始されたバックグラウンド ジョブを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-114">The **Get-Job** cmdlet gets objects that represent the background jobs that were started in the current session.</span></span>
<span data-ttu-id="a21bc-115">Start-Job コマンドレットを使用するか、任意のコマンドレットの *AsJob* パラメーターを使用して、開始されたジョブを **取得すること** ができます。</span><span class="sxs-lookup"><span data-stu-id="a21bc-115">You can use **Get-Job** to get jobs that were started by using the Start-Job cmdlet, or by using the *AsJob* parameter of any cmdlet.</span></span>

<span data-ttu-id="a21bc-116">パラメーターを指定しない場合、 **Get Job** コマンドは、現在のセッション内のすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-116">Without parameters, a **Get-Job** command gets all jobs in the current session.</span></span>
<span data-ttu-id="a21bc-117">**Get-Job** のパラメーターを使用すると、特定のジョブを取得できます。</span><span class="sxs-lookup"><span data-stu-id="a21bc-117">You can use the parameters of **Get-Job** to get particular jobs.</span></span>

<span data-ttu-id="a21bc-118">**Get-Job** から返されるジョブ オブジェクトには、ジョブに関する有用な情報が含まれていますが、ジョブの結果は含まれません。</span><span class="sxs-lookup"><span data-stu-id="a21bc-118">The job object that **Get-Job** returns contains useful information about the job, but it does not contain the job results.</span></span>
<span data-ttu-id="a21bc-119">結果を取得するには、Receive-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-119">To get the results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="a21bc-120">Windows PowerShell のバックグラウンドジョブは、現在のセッションと対話せずにバックグラウンドで実行されるコマンドです。</span><span class="sxs-lookup"><span data-stu-id="a21bc-120">A Windows PowerShell background job is a command that runs in the background without interacting with the current session.</span></span>
<span data-ttu-id="a21bc-121">通常は、バックグラウンドジョブを使用して、完了までに時間がかかる複雑なコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-121">Typically, you use a background job to run a complex command that takes a long time to finish.</span></span>
<span data-ttu-id="a21bc-122">Windows PowerShell のバックグラウンド ジョブの詳細については、「about_Jobs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21bc-122">For more information about background jobs in Windows PowerShell, see about_Jobs.</span></span>

<span data-ttu-id="a21bc-123">Windows PowerShell 3.0 以降では、 **Get-Job** コマンドレットを使用して、ワークフロー ジョブ、スケジュールされたジョブのインスタンスなどのカスタムのジョブの種類を取得できます。</span><span class="sxs-lookup"><span data-stu-id="a21bc-123">Beginning in Windows PowerShell 3.0, the **Get-Job** cmdlet also gets custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="a21bc-124">ジョブの種類を調べるには、ジョブの **PSJobTypeName** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-124">To find the job type of a job, use the **PSJobTypeName** property of the job.</span></span>

<span data-ttu-id="a21bc-125">カスタムジョブの種類を **取得できるようにするに** は、カスタムジョブの種類をサポートするモジュールをセッションにインポートしてから、 **Import-Module コマンドレット** を使用するか、またはモジュールのコマンドレットを使用または取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-125">To enable **Get-Job** to get a custom job type, import the module that supports the custom job type into the session before you run a **Get-Job** command, either by using the Import-Module cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="a21bc-126">特定のカスタム ジョブの種類については、カスタムのジョブの種類機能のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21bc-126">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="a21bc-127">例</span><span class="sxs-lookup"><span data-stu-id="a21bc-127">EXAMPLES</span></span>

### <span data-ttu-id="a21bc-128">例 1: 現在のセッションで開始されているすべてのバックグラウンドジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="a21bc-128">Example 1: Get all background jobs started in the current session</span></span>

```
PS C:\> Get-Job
```

<span data-ttu-id="a21bc-129">このコマンドは、現在のセッションで開始されたすべてのバックグラウンド ジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-129">This command gets all background jobs started in the current session.</span></span>
<span data-ttu-id="a21bc-130">ローカル コンピューター上でジョブが実行される場合でも、他のセッションで作成されたジョブは含まれません。</span><span class="sxs-lookup"><span data-stu-id="a21bc-130">It does not include jobs created in other sessions, even if the jobs run on the local computer.</span></span>

### <span data-ttu-id="a21bc-131">例 2: インスタンス ID を使用してジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="a21bc-131">Example 2: Stop a job by using an instance ID</span></span>

```
The first command uses the **Get-Job** cmdlet to get a job. It uses the *Name* parameter to identify the job. The command stores the job object that **Get-Job** returns in the $j variable. In this example, there is only one job with the specified name.
PS C:\> $j = Get-Job -Name Job1

The second command gets the **InstanceId** property of the object in the $j variable and stores it in the $ID variable.
PS C:\> $ID = $j.InstanceID

The third command displays the value of the $ID variable.
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

The fourth command uses Stop-Job cmdlet to stop the job. It uses the *InstanceId* parameter to identify the job and $ID variable to represent the instance ID of the job.
PS C:\> Stop-Job -InstanceId $ID
```

<span data-ttu-id="a21bc-132">ジョブのインスタンス ID を取得し、それを使用してジョブを停止する方法を次のコマンドに示します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-132">These commands show how to get the instance ID of a job and then use it to stop a job.</span></span>
<span data-ttu-id="a21bc-133">一意ではないジョブ名とは異なり、インスタンス ID は一意です。</span><span class="sxs-lookup"><span data-stu-id="a21bc-133">Unlike the name of a job, which is not unique, the instance ID is unique.</span></span>

### <span data-ttu-id="a21bc-134">例 3: 特定のコマンドを含むジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="a21bc-134">Example 3: Get jobs that include a specific command</span></span>

```
PS C:\> Get-Job -Command "*get-process*"
```

<span data-ttu-id="a21bc-135">このコマンドは、Get-Process コマンドを含むシステム上のジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-135">This command gets the jobs on the system that include a Get-Process command.</span></span>
<span data-ttu-id="a21bc-136">このコマンドは、 *Get-Job* の **Command** パラメーターを使用して取得するジョブを制限します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-136">The command uses the *Command* parameter of **Get-Job** to limit the jobs retrieved.</span></span>
<span data-ttu-id="a21bc-137">コマンドは、ワイルドカード文字 (\*) を使用して、コマンド文字列内の任意の場所にある **Get Process** コマンドを含むジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-137">The command uses wildcard characters (\*) to get jobs that include a **Get-Process** command anywhere in the command string.</span></span>

### <span data-ttu-id="a21bc-138">例 4: パイプラインを使用して特定のコマンドを含むジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="a21bc-138">Example 4: Get jobs that include a specific command by using the pipeline</span></span>

```
PS C:\> "*get-process*" | Get-Job
```

<span data-ttu-id="a21bc-139">前の例のコマンドと同様に、このコマンドは、 **Get Process** コマンドを含むシステム上のジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-139">Like the command in the previous example, this command gets the jobs on the system that include a **Get-Process** command.</span></span>
<span data-ttu-id="a21bc-140">このコマンドは、パイプライン演算子 (|) を使用して、文字列を引用符で囲んだ **後、コマンドレットに** 送信します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-140">The command uses a pipeline operator (|) to send a string, in quotation marks, to the **Get-Job** cmdlet.</span></span>
<span data-ttu-id="a21bc-141">これは、前のコマンドと同等です。</span><span class="sxs-lookup"><span data-stu-id="a21bc-141">It is the equivalent of the previous command.</span></span>

### <span data-ttu-id="a21bc-142">例 5: 開始されていないジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="a21bc-142">Example 5: Get jobs that have not been started</span></span>

```
PS C:\> Get-Job -State NotStarted
```

<span data-ttu-id="a21bc-143">このコマンドは、作成されている一方でまだ開始されていないジョブのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-143">This command gets only those jobs that have been created but have not yet been started.</span></span>
<span data-ttu-id="a21bc-144">これには、後で実行するようにスケジュール設定されているジョブとまだスケジュール設定されていないジョブが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a21bc-144">This includes jobs that are scheduled to run in the future and those not yet scheduled.</span></span>

### <span data-ttu-id="a21bc-145">例 6: 名前が割り当てられていないジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="a21bc-145">Example 6: Get jobs that have not been assigned a name</span></span>

```
PS C:\> Get-Job -Name Job*
```

<span data-ttu-id="a21bc-146">このコマンドは、job で始まるジョブ名を持つすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-146">This command gets all jobs that have job names that begin with job.</span></span>
<span data-ttu-id="a21bc-147">Job \<number\> はジョブの既定の名前であるため、このコマンドは、明示的に名前が割り当てられていないすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-147">Because job\<number\> is the default name for a job, this command gets all jobs that do not have an explicitly assigned name.</span></span>

### <span data-ttu-id="a21bc-148">例 7: ジョブオブジェクトを使用してコマンド内のジョブを表す</span><span class="sxs-lookup"><span data-stu-id="a21bc-148">Example 7: Use a job object to represent the job in a command</span></span>

```
The first command uses the **Start-Job** cmdlet to start a background job that runs a **Get-Process** command on the local computer. The command uses the *Name* parameter of **Start-Job** to assign a friendly name to the job.
PS C:\> Start-Job -ScriptBlock {Get-Process} -Name MyJob

The second command uses Get-Job to get the job. It uses the *Name* parameter of **Get-Job** to identify the job. The command saves the resulting job object in the $j variable.
PS C:\> $j = Get-Job -Name MyJob

The third command displays the value of the job object in the $j variable. The value of the **State** property shows that the job is completed. The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.
PS C:\> $j
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process

The fourth command uses the **Receive-Job** cmdlet to get the results of the job. It uses the job object in the $j variable to represent the job. You can also use a pipeline operator to send a job object to **Receive-Job**.
PS C:\> Receive-Job -Job $j
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```

<span data-ttu-id="a21bc-149">この例は、 **Get-Job** を使用してジョブ オブジェクトを取得した後、そのジョブ オブジェクトを使用してコマンド内のジョブを表す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a21bc-149">This example shows how to use **Get-Job** to get a job object, and then it shows how to use the job object to represent the job in a command.</span></span>

### <span data-ttu-id="a21bc-150">例 8: 別の方法で開始されたジョブを含むすべてのジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="a21bc-150">Example 8: Get all jobs including jobs started by a different method</span></span>

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer.
PS C:\> Start-Job -ScriptBlock {Get-EventLog System}

The second command uses the *AsJob* parameter of the **Invoke-Command** cmdlet to start a job on the S1 computer. Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.
PS C:\> Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob

The third command uses the **Invoke-Command** cmdlet to run a **Start-Job** command on the S2 computer. By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}

The fourth command uses **Get-Job** to get the jobs stored on the local computer. The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the **Start-Job** cmdlet is a background job and the job started in a remote session by using the **Invoke-Command** cmdlet is a remote job.
PS C:\> Get-Job
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System

The fifth command uses **Invoke-Command** to run a **Get-Job** command on the S2 computer.The sample output shows the results of the Get-Job command. On the S2 computer, the job appears to be a local job. The computer name is localhost and the job type is a background job.For more information about how to run background jobs on remote computers, see about_Remote_Jobs.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

<span data-ttu-id="a21bc-151">この例では、別の方法を使用して開始された場合でも、 **Get Job** コマンドレットを使用して、現在のセッションで開始されたすべてのジョブを取得できることを示します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-151">This example demonstrates that the **Get-Job** cmdlet can get all of the jobs that were started in the current session, even if they were started by using different methods.</span></span>

### <span data-ttu-id="a21bc-152">例 9: 失敗したジョブを調査する</span><span class="sxs-lookup"><span data-stu-id="a21bc-152">Example 9: Investigate a failed job</span></span>

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer. The job object that **Start-Job** returns shows that the job failed. The value of the **State** property is Failed.
PS C:\> Start-Job -ScriptBlock {Get-Process}
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process

The second command uses the **Get-Job** cmdlet to get the job. The command uses the dot method to get the value of the **JobStateInfo** property of the object. It uses a pipeline operator to send the object in the **JobStateInfo** property to the Format-List cmdlet, which formats all of the properties of the object (*) in a list.The result of the **Format-List** command shows that the value of the **Reason** property of the job is blank.
PS C:\> (Get-Job).JobStateInfo | Format-List -Property *
State  : Failed
Reason :

The third command investigates more. It uses a **Get-Job** command to get the job and then uses a pipeline operator to send the whole job object to the **Format-List** cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.
PS C:\> Get-Job | Format-List -Property *
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

The fourth command uses **Get-Job** to get the job object that represents the Job2 child job. This is the job in which the command actually ran. It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error. In this case, the user forgot to use the Run as administrator option when starting Windows PowerShell.Because background jobs use the remoting features of Windows PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.For information about requirements for remoting in Windows PowerShell, see about_Remote_Requirements. For troubleshooting tips, see about_Remote_Troubleshooting.
PS C:\> (Get-Job -Name job2).JobStateInfo.Reason
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the following error message: Access is denied.
```

<span data-ttu-id="a21bc-153">このコマンドは、job が返すジョブオブジェクトを使用 **して、** ジョブが失敗した原因を調査する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-153">This command shows how to use the job object that **Get-Job** returns to investigate why a job failed.</span></span>
<span data-ttu-id="a21bc-154">また、各ジョブの子ジョブを取得する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-154">It also shows how to get the child jobs of each job.</span></span>

### <span data-ttu-id="a21bc-155">例 10: フィルター処理された結果を取得する</span><span class="sxs-lookup"><span data-stu-id="a21bc-155">Example 10: Get filtered results</span></span>

```
The first command uses the **Workflow** keyword to create the WFProcess workflow.
PS C:\> Workflow WFProcess {Get-Process}

The second command uses the *AsJob* parameter of the WFProcess workflow to run the workflow as a background job. It uses the *JobName* parameter of the workflow to specify a name for the job, and the *PSPrivateMetadata* parameter of the workflow to specify a custom ID.
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}

The third command uses the *Filter* parameter of **Get-Job** to get the job by custom ID that was specified in the *PSPrivateMetadata* parameter.
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

<span data-ttu-id="a21bc-156">この例では、 *Filter* パラメーターを使用してワークフロー ジョブを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-156">This example shows how to use the *Filter* parameter to get a workflow job.</span></span>
<span data-ttu-id="a21bc-157">Windows PowerShell 3.0 で導入された *Filter* パラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="a21bc-157">The *Filter* parameter, introduced in Windows PowerShell 3.0 is valid only on custom job types, such as workflow jobs and scheduled jobs.</span></span>

### <span data-ttu-id="a21bc-158">例 11: 子ジョブに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="a21bc-158">Example 11: Get information about child jobs</span></span>

```
The first command gets the jobs in the current session. The output includes a background job, a remote job and several instances of a scheduled job. The remote job, Job4, appears to have failed.
PS C:\> Get-Job
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The second command uses the *IncludeChildJob* parameter of **Get-Job**. The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.
PS C:\> Get-Job -IncludeChildJob
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

The third command uses the *ChildJobState* parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.
PS C:\> Get-Job -Name Job4 -ChildJobState Failed
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The fifth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.
PS C:\> (Get-Job -Name Job5).JobStateInfo.Reason
Connecting to remote server Server01 failed with the following error message:
Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
```

<span data-ttu-id="a21bc-159">この例は、 *Get-Job* コマンドレットの *IncludeChildJob* パラメーターと **ChildJobState** パラメーターを使用した場合の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="a21bc-159">This example shows the effect of using the *IncludeChildJob* and *ChildJobState* parameters of the **Get-Job** cmdlet.</span></span>

## <span data-ttu-id="a21bc-160">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a21bc-160">PARAMETERS</span></span>

### <span data-ttu-id="a21bc-161">-After</span><span class="sxs-lookup"><span data-stu-id="a21bc-161">-After</span></span>

<span data-ttu-id="a21bc-162">指定された日時以降に終了した完了済みのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-162">Gets completed jobs that ended after the specified date and time.</span></span>
<span data-ttu-id="a21bc-163">**Datetime** オブジェクトを入力します。たとえば、Get-Date コマンドレットによって返されるオブジェクトや、 **datetime** オブジェクトに変換できる文字列 (やなど) を入力し `Dec 1, 2012 2:00 AM` `11/06` ます。</span><span class="sxs-lookup"><span data-stu-id="a21bc-163">Enter a **DateTime** object, such as one returned by the Get-Date cmdlet or a string that can be converted to a **DateTime** object, such as `Dec 1, 2012 2:00 AM` or `11/06`.</span></span>

<span data-ttu-id="a21bc-164">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、 **EndTime** プロパティを持つカスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-164">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span>
<span data-ttu-id="a21bc-165">これは、 **開始ジョブ** コマンドレットを使用して作成されたジョブなど、標準のバックグラウンドジョブでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="a21bc-165">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="a21bc-166">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21bc-166">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="a21bc-167">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a21bc-167">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a21bc-168">-Before</span><span class="sxs-lookup"><span data-stu-id="a21bc-168">-Before</span></span>

<span data-ttu-id="a21bc-169">指定された日時以前に終了した完了済みのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-169">Gets completed jobs that ended before the specified date and time.</span></span>
<span data-ttu-id="a21bc-170">**DateTime** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-170">Enter a **DateTime** object.</span></span>

<span data-ttu-id="a21bc-171">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、 **EndTime** プロパティを持つカスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-171">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span>
<span data-ttu-id="a21bc-172">これは、 **開始ジョブ** コマンドレットを使用して作成されたジョブなど、標準のバックグラウンドジョブでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="a21bc-172">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="a21bc-173">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21bc-173">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="a21bc-174">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a21bc-174">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a21bc-175">-ChildJobState</span><span class="sxs-lookup"><span data-stu-id="a21bc-175">-ChildJobState</span></span>

<span data-ttu-id="a21bc-176">指定された状態を持つ子ジョブのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-176">Gets only the child jobs that have the specified state.</span></span>
<span data-ttu-id="a21bc-177">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a21bc-177">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a21bc-178">NotStarted</span><span class="sxs-lookup"><span data-stu-id="a21bc-178">NotStarted</span></span>
- <span data-ttu-id="a21bc-179">実行中</span><span class="sxs-lookup"><span data-stu-id="a21bc-179">Running</span></span>
- <span data-ttu-id="a21bc-180">完了</span><span class="sxs-lookup"><span data-stu-id="a21bc-180">Completed</span></span>
- <span data-ttu-id="a21bc-181">失敗</span><span class="sxs-lookup"><span data-stu-id="a21bc-181">Failed</span></span>
- <span data-ttu-id="a21bc-182">停止済み</span><span class="sxs-lookup"><span data-stu-id="a21bc-182">Stopped</span></span>
- <span data-ttu-id="a21bc-183">Blocked</span><span class="sxs-lookup"><span data-stu-id="a21bc-183">Blocked</span></span>
- <span data-ttu-id="a21bc-184">Suspended</span><span class="sxs-lookup"><span data-stu-id="a21bc-184">Suspended</span></span>
- <span data-ttu-id="a21bc-185">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="a21bc-185">Disconnected</span></span>
- <span data-ttu-id="a21bc-186">中断中</span><span class="sxs-lookup"><span data-stu-id="a21bc-186">Suspending</span></span>
- <span data-ttu-id="a21bc-187">停止中</span><span class="sxs-lookup"><span data-stu-id="a21bc-187">Stopping</span></span>

<span data-ttu-id="a21bc-188">既定では、 **Get-Job** は子ジョブを取得しません。</span><span class="sxs-lookup"><span data-stu-id="a21bc-188">By default, **Get-Job** does not get child jobs.</span></span>
<span data-ttu-id="a21bc-189">*IncludeChildJob* パラメーターを使用すると **、すべて** の子ジョブが取得されます。</span><span class="sxs-lookup"><span data-stu-id="a21bc-189">By using the *IncludeChildJob* parameter, **Get-Job** gets all child jobs.</span></span>
<span data-ttu-id="a21bc-190">*ChildJobState* パラメーターを使用した場合、 *IncludeChildJob* パラメーターは効果を持ちません。</span><span class="sxs-lookup"><span data-stu-id="a21bc-190">If you use the *ChildJobState* parameter, the *IncludeChildJob* parameter has no effect.</span></span>

<span data-ttu-id="a21bc-191">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a21bc-191">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a21bc-192">-Command</span><span class="sxs-lookup"><span data-stu-id="a21bc-192">-Command</span></span>

<span data-ttu-id="a21bc-193">コマンドの配列を文字列として指定します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-193">Specifies an array of commands as strings.</span></span>
<span data-ttu-id="a21bc-194">このコマンドレットは、指定されたコマンドを含むジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-194">This cmdlet gets the jobs that include the specified commands.</span></span>
<span data-ttu-id="a21bc-195">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="a21bc-195">The default is all jobs.</span></span>
<span data-ttu-id="a21bc-196">ワイルドカード文字を使用すると、コマンドパターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a21bc-196">You can use wildcard characters to specify a command pattern.</span></span>

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

### <span data-ttu-id="a21bc-197">-Filter</span><span class="sxs-lookup"><span data-stu-id="a21bc-197">-Filter</span></span>

<span data-ttu-id="a21bc-198">条件のハッシュテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-198">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="a21bc-199">このコマンドレットは、すべての条件に適合するジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-199">This cmdlet gets jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="a21bc-200">ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-200">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="a21bc-201">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-201">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span>
<span data-ttu-id="a21bc-202">これは、 **開始ジョブ** コマンドレットを使用して作成されたジョブなど、標準のバックグラウンドジョブでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="a21bc-202">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="a21bc-203">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21bc-203">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="a21bc-204">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a21bc-204">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a21bc-205">-Hasdata</span><span class="sxs-lookup"><span data-stu-id="a21bc-205">-HasMoreData</span></span>

<span data-ttu-id="a21bc-206">このコマンドレットが、指定された **hasを持つデータ** プロパティ値を持つジョブのみを取得するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-206">Indicates whether this cmdlet gets only jobs that have the specified **HasMoreData** property value.</span></span>
<span data-ttu-id="a21bc-207">**HasMoreData** プロパティは、すべてのジョブの結果が現在のセッションで受け取られたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-207">The **HasMoreData** property indicates whether all job results have been received in the current session.</span></span>
<span data-ttu-id="a21bc-208">より多くの結果を持つジョブを取得するには、$True の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-208">To get jobs that have more results, specify a value of $True.</span></span>
<span data-ttu-id="a21bc-209">より多くの結果が得られないジョブを取得するには、$False の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-209">To get jobs that do not have more results, specify a value of $False.</span></span>

<span data-ttu-id="a21bc-210">ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-210">To get the results of a job, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="a21bc-211">**Receive-Job** コマンドレットを使用すると、メモリ内のセッション固有のストレージから、返された結果が削除されます。</span><span class="sxs-lookup"><span data-stu-id="a21bc-211">When you use the **Receive-Job** cmdlet, it deletes from its in-memory, session-specific storage the results that it returned.</span></span>
<span data-ttu-id="a21bc-212">現在のセッションでジョブのすべての結果が返された場合は、ジョブの **Hasmore data** プロパティの値を $False) に設定して、現在のセッションにジョブの結果がなくなったことを示します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-212">When it has returned all results of the job in the current session, it sets the value of the **HasMoreData** property of the job to $False) to indicate that it has no more results for the job in the current session.</span></span>
<span data-ttu-id="a21bc-213">*Receive-Job* が結果を削除して **HasMoreData** プロパティの値を変更しないようにするには、 **Receive-Job** の **Keep** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-213">Use the *Keep* parameter of **Receive-Job** to prevent **Receive-Job** from deleting results and changing the value of the **HasMoreData** property.</span></span>
<span data-ttu-id="a21bc-214">詳細を表示するには「`Get-Help Receive-Job`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-214">For more information, type `Get-Help Receive-Job`.</span></span>

<span data-ttu-id="a21bc-215">**HasMoreData** プロパティは、現在のセッションに固有です。</span><span class="sxs-lookup"><span data-stu-id="a21bc-215">The **HasMoreData** property is specific to the current session.</span></span>
<span data-ttu-id="a21bc-216">ジョブの結果をディスクに保存するスケジュールされたジョブの種類など、カスタムジョブの種類の結果がセッションの外部に保存される場合は、 **Hasdata** の値が $False 場合でも、別のセッションで **Receive-job** コマンドレットを使用して、ジョブの結果を再度取得できます。</span><span class="sxs-lookup"><span data-stu-id="a21bc-216">If results for a custom job type are saved outside of the session, such as the scheduled job type, which saves job results on disk, you can use the **Receive-Job** cmdlet in a different session to get the job results again, even if the value of **HasMoreData** is $False.</span></span>
<span data-ttu-id="a21bc-217">詳細については、カスタムのジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21bc-217">For more information, see the help topics for the custom job type.</span></span>

<span data-ttu-id="a21bc-218">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a21bc-218">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a21bc-219">-Id</span><span class="sxs-lookup"><span data-stu-id="a21bc-219">-Id</span></span>

<span data-ttu-id="a21bc-220">このコマンドレットが取得するジョブの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-220">Specifies an array of IDs of jobs that this cmdlet gets.</span></span>

<span data-ttu-id="a21bc-221">ID は、現在のセッションでジョブを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="a21bc-221">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="a21bc-222">インスタンス ID よりも覚えやすく、入力する方が簡単ですが、現在のセッションでのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="a21bc-222">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="a21bc-223">1つ以上の Id をコンマで区切って入力できます。</span><span class="sxs-lookup"><span data-stu-id="a21bc-223">You can type one or more IDs separated by commas.</span></span>
<span data-ttu-id="a21bc-224">ジョブの ID を検索するには、パラメーターを指定せずに「」と入力 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-224">To find the ID of a job, type `Get-Job` without parameters.</span></span>

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

### <span data-ttu-id="a21bc-225">-IncludeChildJob</span><span class="sxs-lookup"><span data-stu-id="a21bc-225">-IncludeChildJob</span></span>

<span data-ttu-id="a21bc-226">このコマンドレットが親ジョブに加えて子ジョブも返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-226">Indicates that this cmdlet returns child jobs, in addition to parent jobs.</span></span>

<span data-ttu-id="a21bc-227">このパラメーターは、エラーの原因が子ジョブのプロパティに保存されているので、ワークフロージョブを調査する場合に特に便利です。この場合、ジョブの親ジョブとジョブの失敗 **が返され** ます。</span><span class="sxs-lookup"><span data-stu-id="a21bc-227">This parameter is especially useful for investigating workflow jobs, for which **Get-Job** returns a container parent job, and job failures, because the reason for the failure is saved in a property of the child job.</span></span>

<span data-ttu-id="a21bc-228">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a21bc-228">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a21bc-229">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="a21bc-229">-InstanceId</span></span>

<span data-ttu-id="a21bc-230">このコマンドレットが取得するジョブのインスタンス Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-230">Specifies an array of instance IDs of jobs that this cmdlet gets.</span></span>
<span data-ttu-id="a21bc-231">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="a21bc-231">The default is all jobs.</span></span>

<span data-ttu-id="a21bc-232">インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="a21bc-232">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="a21bc-233">ジョブのインスタンス ID を調べるには、 **Get-Job** を使用します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-233">To find the instance ID of a job, use **Get-Job** .</span></span>

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

### <span data-ttu-id="a21bc-234">-Name</span><span class="sxs-lookup"><span data-stu-id="a21bc-234">-Name</span></span>

<span data-ttu-id="a21bc-235">このコマンドレットが取得するジョブのインスタンスフレンドリ名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-235">Specifies an array of instance friendly names of jobs that this cmdlet gets.</span></span>
<span data-ttu-id="a21bc-236">ジョブの名前を入力するか、またはワイルドカード文字を使用してジョブ名のパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-236">Enter a job name, or use wildcard characters to enter a job name pattern.</span></span>
<span data-ttu-id="a21bc-237">既定では、 **Get-Job** は、現在のセッション内のすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-237">By default, **Get-Job** gets all jobs in the current session.</span></span>

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

### <span data-ttu-id="a21bc-238">-最新</span><span class="sxs-lookup"><span data-stu-id="a21bc-238">-Newest</span></span>

<span data-ttu-id="a21bc-239">取得するジョブの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-239">Specifies a number of jobs to get.</span></span>
<span data-ttu-id="a21bc-240">このコマンドレットは、最後に終了したジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-240">This cmdlet gets the jobs that ended most recently.</span></span>

<span data-ttu-id="a21bc-241">*Newest* パラメーターは、並べ替えを行わずに、終了時刻の順で最も新しいジョブを返します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-241">The *Newest* parameter does not sort or return the newest jobs in end-time order.</span></span>
<span data-ttu-id="a21bc-242">出力を並べ替えるには、Sort-Object コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-242">To sort the output, use the Sort-Object cmdlet.</span></span>

<span data-ttu-id="a21bc-243">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a21bc-243">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a21bc-244">-状態</span><span class="sxs-lookup"><span data-stu-id="a21bc-244">-State</span></span>

<span data-ttu-id="a21bc-245">ジョブの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-245">Specifies a job state.</span></span>
<span data-ttu-id="a21bc-246">このコマンドレットは、指定された状態のジョブのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-246">This cmdlet gets only jobs in the specified state.</span></span>
<span data-ttu-id="a21bc-247">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a21bc-247">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a21bc-248">NotStarted</span><span class="sxs-lookup"><span data-stu-id="a21bc-248">NotStarted</span></span>
- <span data-ttu-id="a21bc-249">実行中</span><span class="sxs-lookup"><span data-stu-id="a21bc-249">Running</span></span>
- <span data-ttu-id="a21bc-250">完了</span><span class="sxs-lookup"><span data-stu-id="a21bc-250">Completed</span></span>
- <span data-ttu-id="a21bc-251">失敗</span><span class="sxs-lookup"><span data-stu-id="a21bc-251">Failed</span></span>
- <span data-ttu-id="a21bc-252">停止済み</span><span class="sxs-lookup"><span data-stu-id="a21bc-252">Stopped</span></span>
- <span data-ttu-id="a21bc-253">Blocked</span><span class="sxs-lookup"><span data-stu-id="a21bc-253">Blocked</span></span>
- <span data-ttu-id="a21bc-254">Suspended</span><span class="sxs-lookup"><span data-stu-id="a21bc-254">Suspended</span></span>
- <span data-ttu-id="a21bc-255">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="a21bc-255">Disconnected</span></span>
- <span data-ttu-id="a21bc-256">中断中</span><span class="sxs-lookup"><span data-stu-id="a21bc-256">Suspending</span></span>
- <span data-ttu-id="a21bc-257">停止中</span><span class="sxs-lookup"><span data-stu-id="a21bc-257">Stopping</span></span>

<span data-ttu-id="a21bc-258">既定では、 **Get-Job** は、現在のセッション内のすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-258">By default, **Get-Job** gets all the jobs in the current session.</span></span>

<span data-ttu-id="a21bc-259">ジョブの状態の詳細については、MSDN ライブラリの「 [Jobstate 列挙型](https://msdn.microsoft.com/library/system.management.automation.jobstate) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21bc-259">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

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

### <span data-ttu-id="a21bc-260">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a21bc-260">CommonParameters</span></span>

<span data-ttu-id="a21bc-261">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a21bc-261">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a21bc-262">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21bc-262">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a21bc-263">入力</span><span class="sxs-lookup"><span data-stu-id="a21bc-263">INPUTS</span></span>

### <span data-ttu-id="a21bc-264">なし</span><span class="sxs-lookup"><span data-stu-id="a21bc-264">None</span></span>

<span data-ttu-id="a21bc-265">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="a21bc-265">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="a21bc-266">出力</span><span class="sxs-lookup"><span data-stu-id="a21bc-266">OUTPUTS</span></span>

### <span data-ttu-id="a21bc-267">System. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="a21bc-267">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="a21bc-268">このコマンドレットは、セッション内のジョブを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-268">This cmdlet returns objects that represent the jobs in the session.</span></span>

## <span data-ttu-id="a21bc-269">注</span><span class="sxs-lookup"><span data-stu-id="a21bc-269">NOTES</span></span>

* <span data-ttu-id="a21bc-270">ジョブの **PSJobTypeName** プロパティは、ジョブの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-270">The **PSJobTypeName** property of jobs indicates the job type of the job.</span></span> <span data-ttu-id="a21bc-271">プロパティ値は、ジョブの種類の作成者によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="a21bc-271">The property value is determined by the job type author.</span></span> <span data-ttu-id="a21bc-272">次の一覧に、一般的なジョブの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="a21bc-272">The following list shows common job types.</span></span>

  - <span data-ttu-id="a21bc-273">**Backgroundjob** 。</span><span class="sxs-lookup"><span data-stu-id="a21bc-273">**BackgroundJob** .</span></span>
<span data-ttu-id="a21bc-274">ローカルジョブは **、開始ジョブ** を使用して開始されました。</span><span class="sxs-lookup"><span data-stu-id="a21bc-274">Local job started by using **Start-Job** .</span></span>

  - <span data-ttu-id="a21bc-275">**Remotejob** 。</span><span class="sxs-lookup"><span data-stu-id="a21bc-275">**RemoteJob** .</span></span>
<span data-ttu-id="a21bc-276">Invoke-Command コマンドレットの *AsJob* パラメーターを使用して、 **PSSession** でジョブが開始されました。</span><span class="sxs-lookup"><span data-stu-id="a21bc-276">Job started in a **PSSession** by using the *AsJob* parameter of the Invoke-Command cmdlet.</span></span>

  - <span data-ttu-id="a21bc-277">**Psworkflowjob** 。</span><span class="sxs-lookup"><span data-stu-id="a21bc-277">**PSWorkflowJob** .</span></span>
<span data-ttu-id="a21bc-278">ワークフローの *AsJob* 共通パラメーターを使用して開始されたジョブ。</span><span class="sxs-lookup"><span data-stu-id="a21bc-278">Job started by using the *AsJob* common parameter of workflows.</span></span>

## <span data-ttu-id="a21bc-279">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a21bc-279">RELATED LINKS</span></span>

[<span data-ttu-id="a21bc-280">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="a21bc-280">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="a21bc-281">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="a21bc-281">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="a21bc-282">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="a21bc-282">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="a21bc-283">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="a21bc-283">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="a21bc-284">Start-Job</span><span class="sxs-lookup"><span data-stu-id="a21bc-284">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="a21bc-285">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="a21bc-285">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="a21bc-286">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="a21bc-286">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="a21bc-287">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="a21bc-287">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="a21bc-288">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="a21bc-288">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="a21bc-289">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="a21bc-289">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="a21bc-290">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="a21bc-290">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)

[<span data-ttu-id="a21bc-291">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="a21bc-291">about_Scheduled_Jobs</span></span>](../PSScheduledJob/About/about_Scheduled_Jobs.md)
