---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: 167f56964bbdb675c2dd85e2803fdee2d308ee4f
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389574"
---
# <span data-ttu-id="8570e-103">Get-Job</span><span class="sxs-lookup"><span data-stu-id="8570e-103">Get-Job</span></span>

## <span data-ttu-id="8570e-104">概要</span><span class="sxs-lookup"><span data-stu-id="8570e-104">SYNOPSIS</span></span>
<span data-ttu-id="8570e-105">現在のセッションで実行されている PowerShell バックグラウンドジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-105">Gets PowerShell background jobs that are running in the current session.</span></span>

## <span data-ttu-id="8570e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8570e-106">SYNTAX</span></span>

### <span data-ttu-id="8570e-107">SessionIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="8570e-107">SessionIdParameterSet (Default)</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="8570e-108">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="8570e-108">InstanceIdParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="8570e-109">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="8570e-109">NameParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="8570e-110">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="8570e-110">StateParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="8570e-111">CommandParameterSet</span><span class="sxs-lookup"><span data-stu-id="8570e-111">CommandParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="8570e-112">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="8570e-112">FilterParameterSet</span></span>

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="8570e-113">Description</span><span class="sxs-lookup"><span data-stu-id="8570e-113">DESCRIPTION</span></span>

<span data-ttu-id="8570e-114">`Get-Job`コマンドレットは、現在のセッションで開始されたバックグラウンドジョブを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-114">The `Get-Job` cmdlet gets objects that represent the background jobs that were started in the current session.</span></span> <span data-ttu-id="8570e-115">を使用すると、 `Get-Job` コマンドレットを使用するか、 `Start-Job` 任意のコマンドレットの **AsJob** パラメーターを使用して開始されたジョブを取得できます。</span><span class="sxs-lookup"><span data-stu-id="8570e-115">You can use `Get-Job` to get jobs that were started by using the `Start-Job` cmdlet, or by using the **AsJob** parameter of any cmdlet.</span></span>

<span data-ttu-id="8570e-116">パラメーターを指定しない場合、 `Get-Job` コマンドは現在のセッション内のすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-116">Without parameters, a `Get-Job` command gets all jobs in the current session.</span></span> <span data-ttu-id="8570e-117">のパラメーターを使用して、 `Get-Job` 特定のジョブを取得できます。</span><span class="sxs-lookup"><span data-stu-id="8570e-117">You can use the parameters of `Get-Job` to get particular jobs.</span></span>

<span data-ttu-id="8570e-118">が返すジョブオブジェクトには、 `Get-Job` ジョブに関する有用な情報が含まれていますが、ジョブの結果は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="8570e-118">The job object that `Get-Job` returns contains useful information about the job, but it does not contain the job results.</span></span> <span data-ttu-id="8570e-119">結果を取得するには、 `Receive-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8570e-119">To get the results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="8570e-120">Windows PowerShell のバックグラウンドジョブは、現在のセッションと対話せずにバックグラウンドで実行されるコマンドです。</span><span class="sxs-lookup"><span data-stu-id="8570e-120">A Windows PowerShell background job is a command that runs in the background without interacting with the current session.</span></span> <span data-ttu-id="8570e-121">通常は、バックグラウンドジョブを使用して、完了までに時間がかかる複雑なコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8570e-121">Typically, you use a background job to run a complex command that takes a long time to finish.</span></span> <span data-ttu-id="8570e-122">Windows PowerShell のバックグラウンド ジョブの詳細については、「[about_Jobs](./about/about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8570e-122">For more information about background jobs in Windows PowerShell, see [about_Jobs](./about/about_Jobs.md).</span></span>

<span data-ttu-id="8570e-123">Windows PowerShell 3.0 以降では、 `Get-Job` コマンドレットは、ワークフロージョブやスケジュールされたジョブのインスタンスなどのカスタムジョブの種類も取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-123">Beginning in Windows PowerShell 3.0, the `Get-Job` cmdlet also gets custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="8570e-124">ジョブの種類を調べるには、ジョブの **PSJobTypeName** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="8570e-124">To find the job type of a job, use the **PSJobTypeName** property of the job.</span></span>

<span data-ttu-id="8570e-125">でカスタムのジョブの種類を取得できるようにするには、 `Get-Job` コマンドを実行する前に、コマンドを実行する前に、カスタムジョブの種類をサポートするモジュールをセッションにインポートし `Get-Job` ます。これには、コマンドレットを使用するか、 `Import-Module` を使用するか、またはモジュールのコマンドレットを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-125">To enable `Get-Job` to get a custom job type, import the module that supports the custom job type into the session before you run a `Get-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="8570e-126">特定のカスタム ジョブの種類については、カスタムのジョブの種類機能のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8570e-126">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="8570e-127">例</span><span class="sxs-lookup"><span data-stu-id="8570e-127">EXAMPLES</span></span>

### <span data-ttu-id="8570e-128">例 1: 現在のセッションで開始されているすべてのバックグラウンドジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="8570e-128">Example 1: Get all background jobs started in the current session</span></span>

<span data-ttu-id="8570e-129">このコマンドは、現在のセッションで開始されたすべてのバックグラウンド ジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-129">This command gets all background jobs started in the current session.</span></span> <span data-ttu-id="8570e-130">ローカル コンピューター上でジョブが実行される場合でも、他のセッションで作成されたジョブは含まれません。</span><span class="sxs-lookup"><span data-stu-id="8570e-130">It does not include jobs created in other sessions, even if the jobs run on the local computer.</span></span>

```
PS C:\> Get-Job
```

### <span data-ttu-id="8570e-131">例 2: インスタンス ID を使用してジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="8570e-131">Example 2: Stop a job by using an instance ID</span></span>

<span data-ttu-id="8570e-132">ジョブのインスタンス ID を取得し、それを使用してジョブを停止する方法を次のコマンドに示します。</span><span class="sxs-lookup"><span data-stu-id="8570e-132">These commands show how to get the instance ID of a job and then use it to stop a job.</span></span> <span data-ttu-id="8570e-133">一意ではないジョブ名とは異なり、インスタンス ID は一意です。</span><span class="sxs-lookup"><span data-stu-id="8570e-133">Unlike the name of a job, which is not unique, the instance ID is unique.</span></span>

<span data-ttu-id="8570e-134">最初のコマンドは、 `Get-Job` コマンドレットを使用してジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-134">The first command uses the `Get-Job` cmdlet to get a job.</span></span> <span data-ttu-id="8570e-135">この例では、 **Name** パラメーターを使用してジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="8570e-135">It uses the **Name** parameter to identify the job.</span></span> <span data-ttu-id="8570e-136">このコマンドは、を返すジョブオブジェクトを `Get-Job` 変数に格納し `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-136">The command stores the job object that `Get-Job` returns in the `$j` variable.</span></span> <span data-ttu-id="8570e-137">この例では、指定された名前のジョブが 1 つだけあります。</span><span class="sxs-lookup"><span data-stu-id="8570e-137">In this example, there is only one job with the specified name.</span></span> <span data-ttu-id="8570e-138">2番目のコマンドは、変数内のオブジェクトの **InstanceId** プロパティを取得 `$j` し、変数に格納し `$ID` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-138">The second command gets the **InstanceId** property of the object in the `$j` variable and stores it in the `$ID` variable.</span></span> <span data-ttu-id="8570e-139">3番目のコマンドは、変数の値を表示し `$ID` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-139">The third command displays the value of the `$ID` variable.</span></span> <span data-ttu-id="8570e-140">4番目のコマンドは、 `Stop-Job` コマンドレットを使用してジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="8570e-140">The fourth command uses `Stop-Job` cmdlet to stop the job.</span></span>
<span data-ttu-id="8570e-141">**InstanceId** パラメーターを使用してジョブと変数を識別し、 `$ID` ジョブのインスタンス ID を表します。</span><span class="sxs-lookup"><span data-stu-id="8570e-141">It uses the **InstanceId** parameter to identify the job and `$ID` variable to represent the instance ID of the job.</span></span>

```
PS C:\> $j = Get-Job -Name Job1
PS C:\> $ID = $j.InstanceID
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

PS C:\> Stop-Job -InstanceId $ID
```

### <span data-ttu-id="8570e-142">例 3: 特定のコマンドを含むジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="8570e-142">Example 3: Get jobs that include a specific command</span></span>

<span data-ttu-id="8570e-143">このコマンドは、コマンドを含むシステム上のジョブを取得し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-143">This command gets the jobs on the system that include a `Get-Process` command.</span></span> <span data-ttu-id="8570e-144">コマンドは、の **コマンド** パラメーターを使用して `Get-Job` 、取得するジョブを制限します。</span><span class="sxs-lookup"><span data-stu-id="8570e-144">The command uses the **Command** parameter of `Get-Job` to limit the jobs retrieved.</span></span> <span data-ttu-id="8570e-145">コマンドは、ワイルドカード文字 () を使用して `*` 、コマンド文字列内の任意の場所にコマンドを含むジョブを取得し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-145">The command uses wildcard characters (`*`) to get jobs that include a `Get-Process` command anywhere in the command string.</span></span>

```
PS C:\> Get-Job -Command "*get-process*"
```

### <span data-ttu-id="8570e-146">例 4: パイプラインを使用して特定のコマンドを含むジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="8570e-146">Example 4: Get jobs that include a specific command by using the pipeline</span></span>

<span data-ttu-id="8570e-147">前の例のコマンドと同様に、このコマンドは、コマンドを含むシステム上のジョブを取得し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-147">Like the command in the previous example, this command gets the jobs on the system that include a `Get-Process` command.</span></span> <span data-ttu-id="8570e-148">このコマンドは、パイプライン演算子 () を使用し `|` て、文字列を引用符で囲んで `Get-Job` コマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="8570e-148">The command uses a pipeline operator (`|`) to send a string, in quotation marks, to the `Get-Job` cmdlet.</span></span> <span data-ttu-id="8570e-149">これは、前のコマンドと同等です。</span><span class="sxs-lookup"><span data-stu-id="8570e-149">It is the equivalent of the previous command.</span></span>

```
PS C:\> "*get-process*" | Get-Job
```

### <span data-ttu-id="8570e-150">例 5: 開始されていないジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="8570e-150">Example 5: Get jobs that have not been started</span></span>

<span data-ttu-id="8570e-151">このコマンドは、作成されている一方でまだ開始されていないジョブのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-151">This command gets only those jobs that have been created but have not yet been started.</span></span> <span data-ttu-id="8570e-152">これには、後で実行するようにスケジュール設定されているジョブとまだスケジュール設定されていないジョブが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8570e-152">This includes jobs that are scheduled to run in the future and those not yet scheduled.</span></span>

```
PS C:\> Get-Job -State NotStarted
```

### <span data-ttu-id="8570e-153">例 6: 名前が割り当てられていないジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="8570e-153">Example 6: Get jobs that have not been assigned a name</span></span>

<span data-ttu-id="8570e-154">このコマンドは、job で始まるジョブ名を持つすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-154">This command gets all jobs that have job names that begin with job.</span></span> <span data-ttu-id="8570e-155">`job<number>`はジョブの既定の名前であるため、このコマンドは、明示的に名前が割り当てられていないすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-155">Because `job<number>` is the default name for a job, this command gets all jobs that do not have an explicitly assigned name.</span></span>

```
PS C:\> Get-Job -Name Job*
```

### <span data-ttu-id="8570e-156">例 7: ジョブオブジェクトを使用してコマンド内のジョブを表す</span><span class="sxs-lookup"><span data-stu-id="8570e-156">Example 7: Use a job object to represent the job in a command</span></span>

<span data-ttu-id="8570e-157">この例では、を使用して `Get-Job` ジョブオブジェクトを取得し、そのジョブオブジェクトを使用してコマンド内のジョブを表す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8570e-157">This example shows how to use `Get-Job` to get a job object, and then it shows how to use the job object to represent the job in a command.</span></span>

<span data-ttu-id="8570e-158">最初のコマンドは、コマンドレットを使用して、 `Start-Job` `Get-Process` ローカルコンピューター上でコマンドを実行するバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="8570e-158">The first command uses the `Start-Job` cmdlet to start a background job that runs a `Get-Process` command on the local computer.</span></span> <span data-ttu-id="8570e-159">このコマンドは、の **name** パラメーターを使用して `Start-Job` 、ジョブにフレンドリ名を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8570e-159">The command uses the **Name** parameter of `Start-Job` to assign a friendly name to the job.</span></span> <span data-ttu-id="8570e-160">2番目のコマンドは、を使用し `Get-Job` てジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-160">The second command uses `Get-Job` to get the job.</span></span> <span data-ttu-id="8570e-161">この例では、の **Name** パラメーターを使用して `Get-Job` ジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="8570e-161">It uses the **Name** parameter of `Get-Job` to identify the job.</span></span> <span data-ttu-id="8570e-162">このコマンドは、結果として得られるジョブオブジェクトを変数に保存し `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-162">The command saves the resulting job object in the `$j` variable.</span></span> <span data-ttu-id="8570e-163">3番目のコマンドは、変数内の job オブジェクトの値を表示し `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-163">The third command displays the value of the job object in the `$j` variable.</span></span> <span data-ttu-id="8570e-164">**State** プロパティの値は、ジョブが完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="8570e-164">The value of the **State** property shows that the job is completed.</span></span> <span data-ttu-id="8570e-165">**HasMoreData** プロパティの値は、このジョブに関してまだ取得されていない結果があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="8570e-165">The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.</span></span> <span data-ttu-id="8570e-166">4番目のコマンドは、 `Receive-Job` コマンドレットを使用してジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-166">The fourth command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="8570e-167">ジョブを表すために、変数内の job オブジェクトを使用し `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-167">It uses the job object in the `$j` variable to represent the job.</span></span> <span data-ttu-id="8570e-168">また、パイプライン演算子を使用して、ジョブオブジェクトをに送信することもでき `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-168">You can also use a pipeline operator to send a job object to `Receive-Job`.</span></span>

```
PS C:\> Start-Job -ScriptBlock {Get-Process} -Name MyJob
PS C:\> $j = Get-Job -Name MyJob
PS C:\> $j
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process

PS C:\> Receive-Job -Job $j
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```


### <span data-ttu-id="8570e-169">例 8: 別の方法で開始されたジョブを含むすべてのジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="8570e-169">Example 8: Get all jobs including jobs started by a different method</span></span>

<span data-ttu-id="8570e-170">この例では、 `Get-Job` コマンドレットが、別の方法を使用して起動された場合でも、現在のセッションで開始されたすべてのジョブを取得できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="8570e-170">This example demonstrates that the `Get-Job` cmdlet can get all of the jobs that were started in the current session, even if they were started by using different methods.</span></span>

<span data-ttu-id="8570e-171">最初のコマンドは、 `Start-Job` コマンドレットを使用して、ローカルコンピューター上でジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="8570e-171">The first command uses the `Start-Job` cmdlet to start a job on the local computer.</span></span> <span data-ttu-id="8570e-172">2番目のコマンドは、コマンドレットの **AsJob** パラメーターを使用して、 `Invoke-Command` S1 コンピューターでジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="8570e-172">The second command uses the **AsJob** parameter of the `Invoke-Command` cmdlet to start a job on the S1 computer.</span></span> <span data-ttu-id="8570e-173">ジョブに含まれるコマンドがリモート コンピューター上で実行される場合でもジョブ オブジェクトがローカル コンピューターに作成されるため、ローカル コマンドを使用してジョブを管理します。</span><span class="sxs-lookup"><span data-stu-id="8570e-173">Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.</span></span> <span data-ttu-id="8570e-174">3番目のコマンドは、コマンドレットを使用して、 `Invoke-Command` `Start-Job` S2 コンピューター上でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8570e-174">The third command uses the `Invoke-Command` cmdlet to run a `Start-Job` command on the S2 computer.</span></span> <span data-ttu-id="8570e-175">この方法を使用すると、ジョブオブジェクトがリモートコンピューター上に作成されるため、リモートコマンドを使用してジョブを管理します。</span><span class="sxs-lookup"><span data-stu-id="8570e-175">By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.</span></span> <span data-ttu-id="8570e-176">4番目のコマンドは、を使用して、 `Get-Job` ローカルコンピューターに格納されているジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-176">The fourth command uses `Get-Job` to get the jobs stored on the local computer.</span></span> <span data-ttu-id="8570e-177">Windows PowerShell 3.0 で導入されたジョブの **PSJobTypeName** プロパティには、コマンドレットを使用して開始したローカルジョブ `Start-Job` がバックグラウンドジョブであり、コマンドレットを使用してリモートセッションで開始されたジョブがリモートジョブであることが示されてい `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-177">The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the `Start-Job` cmdlet is a background job and the job started in a remote session by using the `Invoke-Command` cmdlet is a remote job.</span></span> <span data-ttu-id="8570e-178">5番目のコマンドは、を使用して `Invoke-Command` `Get-Job` S2 コンピューターでコマンドを実行します。このサンプル出力は、コマンドの結果を示して `Get-Job` います。</span><span class="sxs-lookup"><span data-stu-id="8570e-178">The fifth command uses `Invoke-Command` to run a `Get-Job` command on the S2 computer.The sample output shows the results of the `Get-Job` command.</span></span> <span data-ttu-id="8570e-179">S2 コンピューター上では、ジョブはローカル ジョブとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="8570e-179">On the S2 computer, the job appears to be a local job.</span></span> <span data-ttu-id="8570e-180">コンピューター名は localhost で、ジョブの種類はバックグラウンドジョブです。リモートコンピューターでバックグラウンドジョブを実行する方法の詳細については、「 [about_Remote_Jobs](./about/about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8570e-180">The computer name is localhost and the job type is a background job.For more information about how to run background jobs on remote computers, see [about_Remote_Jobs](./about/about_Remote_Jobs.md).</span></span>

```
PS C:\> Start-Job -ScriptBlock {Get-EventLog System}
PS C:\> Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
PS C:\> Get-Job
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System

PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

### <span data-ttu-id="8570e-181">例 9: 失敗したジョブを調査する</span><span class="sxs-lookup"><span data-stu-id="8570e-181">Example 9: Investigate a failed job</span></span>

<span data-ttu-id="8570e-182">このコマンドは、が返すジョブオブジェクトを使用して `Get-Job` 、ジョブが失敗した原因を調査する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8570e-182">This command shows how to use the job object that `Get-Job` returns to investigate why a job failed.</span></span>
<span data-ttu-id="8570e-183">また、各ジョブの子ジョブを取得する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="8570e-183">It also shows how to get the child jobs of each job.</span></span>

<span data-ttu-id="8570e-184">最初のコマンドは、 `Start-Job` コマンドレットを使用して、ローカルコンピューター上でジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="8570e-184">The first command uses the `Start-Job` cmdlet to start a job on the local computer.</span></span> <span data-ttu-id="8570e-185">が返すジョブオブジェクトは、 `Start-Job` ジョブが失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="8570e-185">The job object that `Start-Job` returns shows that the job failed.</span></span> <span data-ttu-id="8570e-186">**State** プロパティの値が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="8570e-186">The value of the **State** property is Failed.</span></span>

<span data-ttu-id="8570e-187">2番目のコマンドは、 `Get-Job` コマンドレットを使用してジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-187">The second command uses the `Get-Job` cmdlet to get the job.</span></span> <span data-ttu-id="8570e-188">ここでは、ドット表記を使用してオブジェクトの **JobStateInfo** プロパティの値を取得しています。</span><span class="sxs-lookup"><span data-stu-id="8570e-188">The command uses the dot method to get the value of the **JobStateInfo** property of the object.</span></span> <span data-ttu-id="8570e-189">パイプライン演算子を使用して、 **Jobstateinfo** プロパティのオブジェクトをコマンドレットに送信し `Format-List` ます。これにより、オブジェクトのすべてのプロパティ () の書式 `*` がリストに設定されます。コマンドの結果は、 `Format-List` ジョブの **Reason** プロパティの値が空白であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="8570e-189">It uses a pipeline operator to send the object in the **JobStateInfo** property to the `Format-List` cmdlet, which formats all of the properties of the object (`*`) in a list.The result of the `Format-List` command shows that the value of the **Reason** property of the job is blank.</span></span>

<span data-ttu-id="8570e-190">3番目のコマンドは、詳細を調査します。</span><span class="sxs-lookup"><span data-stu-id="8570e-190">The third command investigates more.</span></span> <span data-ttu-id="8570e-191">コマンドを使用して `Get-Job` ジョブを取得し、パイプライン演算子を使用してジョブオブジェクト全体をコマンドレットに送信します。これにより、ジョブ `Format-List` のすべてのプロパティが一覧に表示されます。Job オブジェクトのすべてのプロパティの表示は、そのジョブに Job2 という名前の子ジョブが含まれていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="8570e-191">It uses a `Get-Job` command to get the job and then uses a pipeline operator to send the whole job object to the `Format-List` cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.</span></span>

<span data-ttu-id="8570e-192">4番目のコマンドは、を使用して、 `Get-Job` Job2 子ジョブを表すジョブオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-192">The fourth command uses `Get-Job` to get the job object that represents the Job2 child job.</span></span> <span data-ttu-id="8570e-193">これは、コマンドが実際に実行されたジョブです。</span><span class="sxs-lookup"><span data-stu-id="8570e-193">This is the job in which the command actually ran.</span></span> <span data-ttu-id="8570e-194">ここでは、ドットメソッドを使用して、 **Jobstateinfo** プロパティの **Reason** プロパティを取得します。結果には、アクセス拒否エラーによってジョブが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="8570e-194">It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error.</span></span> <span data-ttu-id="8570e-195">この場合、ユーザーは Windows PowerShell を起動するときに [管理者として実行] オプションを使用していません。バックグラウンドジョブは、Windows PowerShell のリモート処理機能を使用するため、ローカルコンピューター上でジョブが実行されている場合でも、ジョブを実行するリモート処理用にコンピューターを構成する必要があります。Windows PowerShell でのリモート処理の要件の詳細については、「 [about_Remote_Requirements](./about/about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8570e-195">In this case, the user forgot to use the Run as administrator option when starting Windows PowerShell.Because background jobs use the remoting features of Windows PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.For information about requirements for remoting in Windows PowerShell, see [about_Remote_Requirements](./about/about_Remote_Requirements.md).</span></span> <span data-ttu-id="8570e-196">トラブルシューティングのヒントについては、「[about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8570e-196">For troubleshooting tips, see [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md).</span></span>

```
PS C:\> Start-Job -ScriptBlock {Get-Process}
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process

PS C:\> (Get-Job).JobStateInfo | Format-List -Property *
State  : Failed
Reason :

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

PS C:\> (Get-Job -Name job2).JobStateInfo.Reason
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the
following error message: Access is denied.
```

### <span data-ttu-id="8570e-197">例 10: フィルター処理された結果を取得する</span><span class="sxs-lookup"><span data-stu-id="8570e-197">Example 10: Get filtered results</span></span>

<span data-ttu-id="8570e-198">この例では、 **Filter** パラメーターを使用してワークフロー ジョブを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8570e-198">This example shows how to use the **Filter** parameter to get a workflow job.</span></span> <span data-ttu-id="8570e-199">Windows PowerShell 3.0 で導入された **Filter** パラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="8570e-199">The **Filter** parameter, introduced in Windows PowerShell 3.0 is valid only on custom job types, such as workflow jobs and scheduled jobs.</span></span>

<span data-ttu-id="8570e-200">最初のコマンドは、 **workflow** キーワードを使用して、ワークフローのワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="8570e-200">The first command uses the **Workflow** keyword to create the WFProcess workflow.</span></span> <span data-ttu-id="8570e-201">2番目のコマンドは、ワークフローをバックグラウンドジョブとして実行するために、処理されたプロセスワークフローの **AsJob** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8570e-201">The second command uses the **AsJob** parameter of the WFProcess workflow to run the workflow as a background job.</span></span> <span data-ttu-id="8570e-202">ここでは、ワークフローの **JobName** パラメーターを使用してジョブの名前を指定し、ワークフローの **PSPrivateMetadata** パラメーターを使用してカスタム ID を指定しています。</span><span class="sxs-lookup"><span data-stu-id="8570e-202">It uses the **JobName** parameter of the workflow to specify a name for the job, and the **PSPrivateMetadata** parameter of the workflow to specify a custom ID.</span></span> <span data-ttu-id="8570e-203">3番目のコマンドは、の **Filter** パラメーターを使用し `Get-Job` て、 **PSPrivateMetadata** パラメーターで指定されたカスタム ID でジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-203">The third command uses the **Filter** parameter of `Get-Job` to get the job by custom ID that was specified in the **PSPrivateMetadata** parameter.</span></span>

```
PS C:\> Workflow WFProcess {Get-Process}
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

### <span data-ttu-id="8570e-204">例 11: 子ジョブに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="8570e-204">Example 11: Get information about child jobs</span></span>

<span data-ttu-id="8570e-205">この例は、コマンドレットの **IncludeChildJob** パラメーターと **childjobstate** パラメーターを使用した場合の効果を示して `Get-Job` います。</span><span class="sxs-lookup"><span data-stu-id="8570e-205">This example shows the effect of using the **IncludeChildJob** and **ChildJobState** parameters of the `Get-Job` cmdlet.</span></span>

<span data-ttu-id="8570e-206">最初のコマンドは、現在のセッション内のジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-206">The first command gets the jobs in the current session.</span></span> <span data-ttu-id="8570e-207">出力には、バックグラウンド ジョブ、リモート ジョブ、およびスケジュールされたジョブのいくつかのインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8570e-207">The output includes a background job, a remote job and several instances of a scheduled job.</span></span> <span data-ttu-id="8570e-208">リモート ジョブ Job4 については、失敗したことが示されています。</span><span class="sxs-lookup"><span data-stu-id="8570e-208">The remote job, Job4, appears to have failed.</span></span>
<span data-ttu-id="8570e-209">2番目のコマンドは、の **IncludeChildJob** パラメーターを使用し `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-209">The second command uses the **IncludeChildJob** parameter of `Get-Job`.</span></span> <span data-ttu-id="8570e-210">出力には、子ジョブを持つすべてのジョブの子ジョブが追加されます。この場合、変更後の出力には、Job4 の Job5 子ジョブのみが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="8570e-210">The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.</span></span> <span data-ttu-id="8570e-211">3番目のコマンドは、 **Childjobstate** パラメーターを使用して、値が failed であることを示します。出力には、すべての親ジョブと、失敗した子ジョブのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8570e-211">The third command uses the **ChildJobState** parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.</span></span> <span data-ttu-id="8570e-212">5番目のコマンドは、jobs の **Jobstateinfo** プロパティと **Reason** プロパティを使用して、Job5 が失敗した理由を検出します。</span><span class="sxs-lookup"><span data-stu-id="8570e-212">The fifth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.</span></span>

```
PS C:\> Get-Job
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

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

PS C:\> (Get-Job -Name Job5).JobStateInfo.Reason
Connecting to remote server Server01 failed with the following error message:
Access is denied.
```

<span data-ttu-id="8570e-213">詳細については、 [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md) のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8570e-213">For more information, see the [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md) Help topic.</span></span>

## <span data-ttu-id="8570e-214">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8570e-214">PARAMETERS</span></span>

### <span data-ttu-id="8570e-215">-After</span><span class="sxs-lookup"><span data-stu-id="8570e-215">-After</span></span>

<span data-ttu-id="8570e-216">指定された日時以降に終了した完了済みのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-216">Gets completed jobs that ended after the specified date and time.</span></span> <span data-ttu-id="8570e-217">**Datetime** オブジェクトを入力します。たとえば、コマンドレットによって返されるオブジェクト `Get-Date` や、 **datetime** オブジェクトに変換できる文字列 (やなど) を入力し `Dec 1, 2012 2:00 AM` `11/06` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-217">Enter a **DateTime** object, such as one returned by the `Get-Date` cmdlet or a string that can be converted to a **DateTime** object, such as `Dec 1, 2012 2:00 AM` or `11/06`.</span></span>

<span data-ttu-id="8570e-218">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、 **EndTime** プロパティを持つカスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="8570e-218">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="8570e-219">コマンドレットを使用して作成されたものなど、標準のバックグラウンドジョブでは機能しません `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="8570e-219">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="8570e-220">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8570e-220">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="8570e-221">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8570e-221">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="8570e-222">-Before</span><span class="sxs-lookup"><span data-stu-id="8570e-222">-Before</span></span>

<span data-ttu-id="8570e-223">指定された日時以前に終了した完了済みのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-223">Gets completed jobs that ended before the specified date and time.</span></span> <span data-ttu-id="8570e-224">**DateTime** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="8570e-224">Enter a **DateTime** object.</span></span>

<span data-ttu-id="8570e-225">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、 **EndTime** プロパティを持つカスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="8570e-225">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="8570e-226">コマンドレットを使用して作成されたものなど、標準のバックグラウンドジョブでは機能しません `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="8570e-226">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="8570e-227">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8570e-227">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="8570e-228">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8570e-228">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="8570e-229">-ChildJobState</span><span class="sxs-lookup"><span data-stu-id="8570e-229">-ChildJobState</span></span>

<span data-ttu-id="8570e-230">指定された状態を持つ子ジョブのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-230">Gets only the child jobs that have the specified state.</span></span> <span data-ttu-id="8570e-231">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8570e-231">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8570e-232">NotStarted</span><span class="sxs-lookup"><span data-stu-id="8570e-232">NotStarted</span></span>
- <span data-ttu-id="8570e-233">実行中</span><span class="sxs-lookup"><span data-stu-id="8570e-233">Running</span></span>
- <span data-ttu-id="8570e-234">完了</span><span class="sxs-lookup"><span data-stu-id="8570e-234">Completed</span></span>
- <span data-ttu-id="8570e-235">失敗</span><span class="sxs-lookup"><span data-stu-id="8570e-235">Failed</span></span>
- <span data-ttu-id="8570e-236">停止済み</span><span class="sxs-lookup"><span data-stu-id="8570e-236">Stopped</span></span>
- <span data-ttu-id="8570e-237">［ブロック済み］</span><span class="sxs-lookup"><span data-stu-id="8570e-237">Blocked</span></span>
- <span data-ttu-id="8570e-238">Suspended</span><span class="sxs-lookup"><span data-stu-id="8570e-238">Suspended</span></span>
- <span data-ttu-id="8570e-239">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="8570e-239">Disconnected</span></span>
- <span data-ttu-id="8570e-240">中断中</span><span class="sxs-lookup"><span data-stu-id="8570e-240">Suspending</span></span>
- <span data-ttu-id="8570e-241">停止中</span><span class="sxs-lookup"><span data-stu-id="8570e-241">Stopping</span></span>

<span data-ttu-id="8570e-242">既定で `Get-Job` は、は子ジョブを取得しません。</span><span class="sxs-lookup"><span data-stu-id="8570e-242">By default, `Get-Job` does not get child jobs.</span></span> <span data-ttu-id="8570e-243">**IncludeChildJob** パラメーターを使用して、 `Get-Job` すべての子ジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-243">By using the **IncludeChildJob** parameter, `Get-Job` gets all child jobs.</span></span> <span data-ttu-id="8570e-244">**ChildJobState** パラメーターを使用した場合、 **IncludeChildJob** パラメーターは効果を持ちません。</span><span class="sxs-lookup"><span data-stu-id="8570e-244">If you use the **ChildJobState** parameter, the **IncludeChildJob** parameter has no effect.</span></span>

<span data-ttu-id="8570e-245">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8570e-245">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="8570e-246">-Command</span><span class="sxs-lookup"><span data-stu-id="8570e-246">-Command</span></span>

<span data-ttu-id="8570e-247">コマンドの配列を文字列として指定します。</span><span class="sxs-lookup"><span data-stu-id="8570e-247">Specifies an array of commands as strings.</span></span> <span data-ttu-id="8570e-248">このコマンドレットは、指定されたコマンドを含むジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-248">This cmdlet gets the jobs that include the specified commands.</span></span> <span data-ttu-id="8570e-249">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="8570e-249">The default is all jobs.</span></span> <span data-ttu-id="8570e-250">ワイルドカード文字を使用すると、コマンドパターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8570e-250">You can use wildcard characters to specify a command pattern.</span></span>

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

### <span data-ttu-id="8570e-251">-Filter</span><span class="sxs-lookup"><span data-stu-id="8570e-251">-Filter</span></span>

<span data-ttu-id="8570e-252">条件のハッシュテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="8570e-252">Specifies a hash table of conditions.</span></span> <span data-ttu-id="8570e-253">このコマンドレットは、すべての条件に適合するジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-253">This cmdlet gets jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="8570e-254">ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="8570e-254">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="8570e-255">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="8570e-255">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="8570e-256">コマンドレットを使用して作成されたものなど、標準のバックグラウンドジョブでは機能しません `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="8570e-256">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="8570e-257">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8570e-257">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="8570e-258">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8570e-258">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="8570e-259">-Hasdata</span><span class="sxs-lookup"><span data-stu-id="8570e-259">-HasMoreData</span></span>

<span data-ttu-id="8570e-260">このコマンドレットが、指定された **hasを持つデータ** プロパティ値を持つジョブのみを取得するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="8570e-260">Indicates whether this cmdlet gets only jobs that have the specified **HasMoreData** property value.</span></span>
<span data-ttu-id="8570e-261">**HasMoreData** プロパティは、すべてのジョブの結果が現在のセッションで受け取られたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="8570e-261">The **HasMoreData** property indicates whether all job results have been received in the current session.</span></span> <span data-ttu-id="8570e-262">より多くの結果を持つジョブを取得するには、の値を指定し `$True` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-262">To get jobs that have more results, specify a value of `$True`.</span></span> <span data-ttu-id="8570e-263">より多くの結果が得られないジョブを取得するには、の値を指定し `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-263">To get jobs that do not have more results, specify a value of `$False`.</span></span>

<span data-ttu-id="8570e-264">ジョブの結果を取得するには、コマンドレットを使用し `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-264">To get the results of a job, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="8570e-265">コマンドレットを使用すると、 `Receive-Job` メモリ内のセッション固有のストレージから、返された結果が削除されます。</span><span class="sxs-lookup"><span data-stu-id="8570e-265">When you use the `Receive-Job` cmdlet, it deletes from its in-memory, session-specific storage the results that it returned.</span></span> <span data-ttu-id="8570e-266">現在のセッションでジョブのすべての結果が返されると、ジョブの **Hasmore data** プロパティの値がに設定され、 `$False` 現在のセッションにジョブの結果がなくなったことが示されます。</span><span class="sxs-lookup"><span data-stu-id="8570e-266">When it has returned all results of the job in the current session, it sets the value of the **HasMoreData** property of the job to `$False`) to indicate that it has no more results for the job in the current session.</span></span> <span data-ttu-id="8570e-267">が **Keep** `Receive-Job` `Receive-Job` 結果を削除して、 **hasdata** プロパティの値を変更しないようにするには、の Keep パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8570e-267">Use the **Keep** parameter of `Receive-Job` to prevent `Receive-Job` from deleting results and changing the value of the **HasMoreData** property.</span></span>
<span data-ttu-id="8570e-268">詳細を表示するには「`Get-Help Receive-Job`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="8570e-268">For more information, type `Get-Help Receive-Job`.</span></span>

<span data-ttu-id="8570e-269">**HasMoreData** プロパティは、現在のセッションに固有です。</span><span class="sxs-lookup"><span data-stu-id="8570e-269">The **HasMoreData** property is specific to the current session.</span></span> <span data-ttu-id="8570e-270">ジョブの結果をディスクに保存するスケジュールされたジョブの種類など、カスタムジョブの種類の結果がセッションの外部に保存される場合は、 `Receive-Job` 別のセッションでコマンドレットを使用して、 **hasdata** の値がの場合でも、ジョブの結果を再び取得でき `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-270">If results for a custom job type are saved outside of the session, such as the scheduled job type, which saves job results on disk, you can use the `Receive-Job` cmdlet in a different session to get the job results again, even if the value of **HasMoreData** is `$False`.</span></span> <span data-ttu-id="8570e-271">詳細については、カスタムのジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8570e-271">For more information, see the help topics for the custom job type.</span></span>

<span data-ttu-id="8570e-272">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8570e-272">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="8570e-273">-Id</span><span class="sxs-lookup"><span data-stu-id="8570e-273">-Id</span></span>

<span data-ttu-id="8570e-274">このコマンドレットが取得するジョブの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="8570e-274">Specifies an array of IDs of jobs that this cmdlet gets.</span></span>

<span data-ttu-id="8570e-275">ID は、現在のセッションでジョブを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="8570e-275">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="8570e-276">インスタンス ID よりも覚えやすく、入力する方が簡単ですが、現在のセッションでのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="8570e-276">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="8570e-277">1つ以上の Id をコンマで区切って入力できます。</span><span class="sxs-lookup"><span data-stu-id="8570e-277">You can type one or more IDs separated by commas.</span></span> <span data-ttu-id="8570e-278">ジョブの ID を検索するには、パラメーターを指定せずに「」と入力 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="8570e-278">To find the ID of a job, type `Get-Job` without parameters.</span></span>

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

### <span data-ttu-id="8570e-279">-IncludeChildJob</span><span class="sxs-lookup"><span data-stu-id="8570e-279">-IncludeChildJob</span></span>

<span data-ttu-id="8570e-280">このコマンドレットが親ジョブに加えて子ジョブも返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="8570e-280">Indicates that this cmdlet returns child jobs, in addition to parent jobs.</span></span>

<span data-ttu-id="8570e-281">このパラメーターは、 `Get-Job` エラーの原因が子ジョブのプロパティに保存されるため、がコンテナーの親ジョブとジョブの失敗を返すワークフロージョブを調査する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="8570e-281">This parameter is especially useful for investigating workflow jobs, for which `Get-Job` returns a container parent job, and job failures, because the reason for the failure is saved in a property of the child job.</span></span>

<span data-ttu-id="8570e-282">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8570e-282">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="8570e-283">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="8570e-283">-InstanceId</span></span>

<span data-ttu-id="8570e-284">このコマンドレットが取得するジョブのインスタンス Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="8570e-284">Specifies an array of instance IDs of jobs that this cmdlet gets.</span></span> <span data-ttu-id="8570e-285">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="8570e-285">The default is all jobs.</span></span>

<span data-ttu-id="8570e-286">インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="8570e-286">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="8570e-287">ジョブのインスタンス ID を検索するには、を使用 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="8570e-287">To find the instance ID of a job, use `Get-Job`.</span></span>

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

### <span data-ttu-id="8570e-288">-Name</span><span class="sxs-lookup"><span data-stu-id="8570e-288">-Name</span></span>

<span data-ttu-id="8570e-289">このコマンドレットが取得するジョブのインスタンスフレンドリ名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="8570e-289">Specifies an array of instance friendly names of jobs that this cmdlet gets.</span></span> <span data-ttu-id="8570e-290">ジョブの名前を入力するか、またはワイルドカード文字を使用してジョブ名のパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="8570e-290">Enter a job name, or use wildcard characters to enter a job name pattern.</span></span> <span data-ttu-id="8570e-291">既定では、は、 `Get-Job` 現在のセッション内のすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-291">By default, `Get-Job` gets all jobs in the current session.</span></span>

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

### <span data-ttu-id="8570e-292">-最新</span><span class="sxs-lookup"><span data-stu-id="8570e-292">-Newest</span></span>

<span data-ttu-id="8570e-293">取得するジョブの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="8570e-293">Specifies a number of jobs to get.</span></span> <span data-ttu-id="8570e-294">このコマンドレットは、最後に終了したジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-294">This cmdlet gets the jobs that ended most recently.</span></span>

<span data-ttu-id="8570e-295">**Newest** パラメーターは、並べ替えを行わずに、終了時刻の順で最も新しいジョブを返します。</span><span class="sxs-lookup"><span data-stu-id="8570e-295">The **Newest** parameter does not sort or return the newest jobs in end-time order.</span></span> <span data-ttu-id="8570e-296">出力を並べ替えるには、コマンドレットを使用し `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="8570e-296">To sort the output, use the `Sort-Object` cmdlet.</span></span>

<span data-ttu-id="8570e-297">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8570e-297">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="8570e-298">-状態</span><span class="sxs-lookup"><span data-stu-id="8570e-298">-State</span></span>

<span data-ttu-id="8570e-299">ジョブの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="8570e-299">Specifies a job state.</span></span> <span data-ttu-id="8570e-300">このコマンドレットは、指定された状態のジョブのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-300">This cmdlet gets only jobs in the specified state.</span></span> <span data-ttu-id="8570e-301">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8570e-301">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8570e-302">NotStarted</span><span class="sxs-lookup"><span data-stu-id="8570e-302">NotStarted</span></span>
- <span data-ttu-id="8570e-303">実行中</span><span class="sxs-lookup"><span data-stu-id="8570e-303">Running</span></span>
- <span data-ttu-id="8570e-304">完了</span><span class="sxs-lookup"><span data-stu-id="8570e-304">Completed</span></span>
- <span data-ttu-id="8570e-305">失敗</span><span class="sxs-lookup"><span data-stu-id="8570e-305">Failed</span></span>
- <span data-ttu-id="8570e-306">停止済み</span><span class="sxs-lookup"><span data-stu-id="8570e-306">Stopped</span></span>
- <span data-ttu-id="8570e-307">［ブロック済み］</span><span class="sxs-lookup"><span data-stu-id="8570e-307">Blocked</span></span>
- <span data-ttu-id="8570e-308">Suspended</span><span class="sxs-lookup"><span data-stu-id="8570e-308">Suspended</span></span>
- <span data-ttu-id="8570e-309">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="8570e-309">Disconnected</span></span>
- <span data-ttu-id="8570e-310">中断中</span><span class="sxs-lookup"><span data-stu-id="8570e-310">Suspending</span></span>
- <span data-ttu-id="8570e-311">停止中</span><span class="sxs-lookup"><span data-stu-id="8570e-311">Stopping</span></span>

<span data-ttu-id="8570e-312">既定では、は、 `Get-Job` 現在のセッション内のすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="8570e-312">By default, `Get-Job` gets all the jobs in the current session.</span></span>

<span data-ttu-id="8570e-313">ジョブの状態の詳細については、「 [Jobstate 列挙型](/dotnet/api/system.management.automation.jobstate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8570e-313">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

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

### <span data-ttu-id="8570e-314">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8570e-314">CommonParameters</span></span>

<span data-ttu-id="8570e-315">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8570e-315">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8570e-316">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8570e-316">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8570e-317">入力</span><span class="sxs-lookup"><span data-stu-id="8570e-317">INPUTS</span></span>

### <span data-ttu-id="8570e-318">なし</span><span class="sxs-lookup"><span data-stu-id="8570e-318">None</span></span>

<span data-ttu-id="8570e-319">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="8570e-319">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="8570e-320">出力</span><span class="sxs-lookup"><span data-stu-id="8570e-320">OUTPUTS</span></span>

### <span data-ttu-id="8570e-321">System. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="8570e-321">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="8570e-322">このコマンドレットは、セッション内のジョブを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="8570e-322">This cmdlet returns objects that represent the jobs in the session.</span></span>

## <span data-ttu-id="8570e-323">注</span><span class="sxs-lookup"><span data-stu-id="8570e-323">NOTES</span></span>

<span data-ttu-id="8570e-324">ジョブの **PSJobTypeName** プロパティは、ジョブの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="8570e-324">The **PSJobTypeName** property of jobs indicates the job type of the job.</span></span> <span data-ttu-id="8570e-325">プロパティ値は、ジョブの種類の作成者によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="8570e-325">The property value is determined by the job type author.</span></span> <span data-ttu-id="8570e-326">次の一覧に、一般的なジョブの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="8570e-326">The following list shows common job types.</span></span>

- <span data-ttu-id="8570e-327">**Backgroundjob** 。</span><span class="sxs-lookup"><span data-stu-id="8570e-327">**BackgroundJob**.</span></span> <span data-ttu-id="8570e-328">ローカルジョブは、を使用して開始されました `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="8570e-328">Local job started by using `Start-Job`.</span></span>
- <span data-ttu-id="8570e-329">**Remotejob** 。</span><span class="sxs-lookup"><span data-stu-id="8570e-329">**RemoteJob**.</span></span> <span data-ttu-id="8570e-330">コマンドレットの **AsJob** パラメーターを使用して、 **PSSession** でジョブが開始されました `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="8570e-330">Job started in a **PSSession** by using the **AsJob** parameter of the `Invoke-Command` cmdlet.</span></span>
- <span data-ttu-id="8570e-331">**Psworkflowjob** 。</span><span class="sxs-lookup"><span data-stu-id="8570e-331">**PSWorkflowJob**.</span></span> <span data-ttu-id="8570e-332">ワークフローの **AsJob** 共通パラメーターを使用して開始されたジョブ。</span><span class="sxs-lookup"><span data-stu-id="8570e-332">Job started by using the **AsJob** common parameter of workflows.</span></span>

## <span data-ttu-id="8570e-333">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8570e-333">RELATED LINKS</span></span>

[<span data-ttu-id="8570e-334">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="8570e-334">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="8570e-335">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="8570e-335">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="8570e-336">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="8570e-336">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="8570e-337">Start-Job</span><span class="sxs-lookup"><span data-stu-id="8570e-337">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="8570e-338">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="8570e-338">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="8570e-339">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="8570e-339">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="8570e-340">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="8570e-340">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="8570e-341">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="8570e-341">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="8570e-342">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="8570e-342">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)
