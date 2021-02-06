---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: 7df3375d547b696d67c44462142d592e6047ac63
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603028"
---
# <span data-ttu-id="7c24c-102">Get-Job</span><span class="sxs-lookup"><span data-stu-id="7c24c-102">Get-Job</span></span>

## <span data-ttu-id="7c24c-103">概要</span><span class="sxs-lookup"><span data-stu-id="7c24c-103">SYNOPSIS</span></span>
<span data-ttu-id="7c24c-104">現在のセッションで実行されている PowerShell バックグラウンドジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-104">Gets PowerShell background jobs that are running in the current session.</span></span>

## <span data-ttu-id="7c24c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7c24c-105">SYNTAX</span></span>

### <span data-ttu-id="7c24c-106">SessionIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="7c24c-106">SessionIdParameterSet (Default)</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="7c24c-107">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="7c24c-107">InstanceIdParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="7c24c-108">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="7c24c-108">NameParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="7c24c-109">StateParameterSet</span><span class="sxs-lookup"><span data-stu-id="7c24c-109">StateParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="7c24c-110">CommandParameterSet</span><span class="sxs-lookup"><span data-stu-id="7c24c-110">CommandParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="7c24c-111">FilterParameterSet</span><span class="sxs-lookup"><span data-stu-id="7c24c-111">FilterParameterSet</span></span>

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="7c24c-112">Description</span><span class="sxs-lookup"><span data-stu-id="7c24c-112">DESCRIPTION</span></span>

<span data-ttu-id="7c24c-113">`Get-Job`コマンドレットは、現在のセッションで開始されたバックグラウンドジョブを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-113">The `Get-Job` cmdlet gets objects that represent the background jobs that were started in the current session.</span></span> <span data-ttu-id="7c24c-114">を使用すると、 `Get-Job` コマンドレットを使用するか、 `Start-Job` 任意のコマンドレットの **AsJob** パラメーターを使用して開始されたジョブを取得できます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-114">You can use `Get-Job` to get jobs that were started by using the `Start-Job` cmdlet, or by using the **AsJob** parameter of any cmdlet.</span></span>

<span data-ttu-id="7c24c-115">パラメーターを指定しない場合、 `Get-Job` コマンドは現在のセッション内のすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-115">Without parameters, a `Get-Job` command gets all jobs in the current session.</span></span> <span data-ttu-id="7c24c-116">のパラメーターを使用して、 `Get-Job` 特定のジョブを取得できます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-116">You can use the parameters of `Get-Job` to get particular jobs.</span></span>

<span data-ttu-id="7c24c-117">が返すジョブオブジェクトには、 `Get-Job` ジョブに関する有用な情報が含まれていますが、ジョブの結果は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="7c24c-117">The job object that `Get-Job` returns contains useful information about the job, but it does not contain the job results.</span></span> <span data-ttu-id="7c24c-118">結果を取得するには、 `Receive-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-118">To get the results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="7c24c-119">Windows PowerShell のバックグラウンドジョブは、現在のセッションと対話せずにバックグラウンドで実行されるコマンドです。</span><span class="sxs-lookup"><span data-stu-id="7c24c-119">A Windows PowerShell background job is a command that runs in the background without interacting with the current session.</span></span> <span data-ttu-id="7c24c-120">通常は、バックグラウンドジョブを使用して、完了までに時間がかかる複雑なコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-120">Typically, you use a background job to run a complex command that takes a long time to finish.</span></span> <span data-ttu-id="7c24c-121">Windows PowerShell のバックグラウンド ジョブの詳細については、「[about_Jobs](./about/about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c24c-121">For more information about background jobs in Windows PowerShell, see [about_Jobs](./about/about_Jobs.md).</span></span>

<span data-ttu-id="7c24c-122">Windows PowerShell 3.0 以降では、 `Get-Job` コマンドレットは、ワークフロージョブやスケジュールされたジョブのインスタンスなどのカスタムジョブの種類も取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-122">Beginning in Windows PowerShell 3.0, the `Get-Job` cmdlet also gets custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="7c24c-123">ジョブの種類を調べるには、ジョブの **PSJobTypeName** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-123">To find the job type of a job, use the **PSJobTypeName** property of the job.</span></span>

<span data-ttu-id="7c24c-124">でカスタムのジョブの種類を取得できるようにするには、 `Get-Job` コマンドを実行する前に、コマンドを実行する前に、カスタムジョブの種類をサポートするモジュールをセッションにインポートし `Get-Job` ます。これには、コマンドレットを使用するか、 `Import-Module` を使用するか、またはモジュールのコマンドレットを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-124">To enable `Get-Job` to get a custom job type, import the module that supports the custom job type into the session before you run a `Get-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="7c24c-125">特定のカスタム ジョブの種類については、カスタムのジョブの種類機能のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c24c-125">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="7c24c-126">例</span><span class="sxs-lookup"><span data-stu-id="7c24c-126">EXAMPLES</span></span>

### <span data-ttu-id="7c24c-127">例 1: 現在のセッションで開始されているすべてのバックグラウンドジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="7c24c-127">Example 1: Get all background jobs started in the current session</span></span>

<span data-ttu-id="7c24c-128">このコマンドは、現在のセッションで開始されたすべてのバックグラウンド ジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-128">This command gets all background jobs started in the current session.</span></span> <span data-ttu-id="7c24c-129">ローカル コンピューター上でジョブが実行される場合でも、他のセッションで作成されたジョブは含まれません。</span><span class="sxs-lookup"><span data-stu-id="7c24c-129">It does not include jobs created in other sessions, even if the jobs run on the local computer.</span></span>

```
PS C:\> Get-Job
```

### <span data-ttu-id="7c24c-130">例 2: インスタンス ID を使用してジョブを停止する</span><span class="sxs-lookup"><span data-stu-id="7c24c-130">Example 2: Stop a job by using an instance ID</span></span>

<span data-ttu-id="7c24c-131">ジョブのインスタンス ID を取得し、それを使用してジョブを停止する方法を次のコマンドに示します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-131">These commands show how to get the instance ID of a job and then use it to stop a job.</span></span> <span data-ttu-id="7c24c-132">一意ではないジョブ名とは異なり、インスタンス ID は一意です。</span><span class="sxs-lookup"><span data-stu-id="7c24c-132">Unlike the name of a job, which is not unique, the instance ID is unique.</span></span>

<span data-ttu-id="7c24c-133">最初のコマンドは、 `Get-Job` コマンドレットを使用してジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-133">The first command uses the `Get-Job` cmdlet to get a job.</span></span> <span data-ttu-id="7c24c-134">この例では、 **Name** パラメーターを使用してジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-134">It uses the **Name** parameter to identify the job.</span></span> <span data-ttu-id="7c24c-135">このコマンドは、を返すジョブオブジェクトを `Get-Job` 変数に格納し `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-135">The command stores the job object that `Get-Job` returns in the `$j` variable.</span></span> <span data-ttu-id="7c24c-136">この例では、指定された名前のジョブが 1 つだけあります。</span><span class="sxs-lookup"><span data-stu-id="7c24c-136">In this example, there is only one job with the specified name.</span></span> <span data-ttu-id="7c24c-137">2番目のコマンドは、変数内のオブジェクトの **InstanceId** プロパティを取得 `$j` し、変数に格納し `$ID` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-137">The second command gets the **InstanceId** property of the object in the `$j` variable and stores it in the `$ID` variable.</span></span> <span data-ttu-id="7c24c-138">3番目のコマンドは、変数の値を表示し `$ID` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-138">The third command displays the value of the `$ID` variable.</span></span> <span data-ttu-id="7c24c-139">4番目のコマンドは、 `Stop-Job` コマンドレットを使用してジョブを停止します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-139">The fourth command uses `Stop-Job` cmdlet to stop the job.</span></span>
<span data-ttu-id="7c24c-140">**InstanceId** パラメーターを使用してジョブと変数を識別し、 `$ID` ジョブのインスタンス ID を表します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-140">It uses the **InstanceId** parameter to identify the job and `$ID` variable to represent the instance ID of the job.</span></span>

```
PS C:\> $j = Get-Job -Name Job1
PS C:\> $ID = $j.InstanceID
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

PS C:\> Stop-Job -InstanceId $ID
```

### <span data-ttu-id="7c24c-141">例 3: 特定のコマンドを含むジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="7c24c-141">Example 3: Get jobs that include a specific command</span></span>

<span data-ttu-id="7c24c-142">このコマンドは、コマンドを含むシステム上のジョブを取得し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-142">This command gets the jobs on the system that include a `Get-Process` command.</span></span> <span data-ttu-id="7c24c-143">コマンドは、の **コマンド** パラメーターを使用して `Get-Job` 、取得するジョブを制限します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-143">The command uses the **Command** parameter of `Get-Job` to limit the jobs retrieved.</span></span> <span data-ttu-id="7c24c-144">コマンドは、ワイルドカード文字 () を使用して `*` 、コマンド文字列内の任意の場所にコマンドを含むジョブを取得し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-144">The command uses wildcard characters (`*`) to get jobs that include a `Get-Process` command anywhere in the command string.</span></span>

```
PS C:\> Get-Job -Command "*get-process*"
```

### <span data-ttu-id="7c24c-145">例 4: パイプラインを使用して特定のコマンドを含むジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="7c24c-145">Example 4: Get jobs that include a specific command by using the pipeline</span></span>

<span data-ttu-id="7c24c-146">前の例のコマンドと同様に、このコマンドは、コマンドを含むシステム上のジョブを取得し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-146">Like the command in the previous example, this command gets the jobs on the system that include a `Get-Process` command.</span></span> <span data-ttu-id="7c24c-147">このコマンドは、パイプライン演算子 () を使用し `|` て、文字列を引用符で囲んで `Get-Job` コマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-147">The command uses a pipeline operator (`|`) to send a string, in quotation marks, to the `Get-Job` cmdlet.</span></span> <span data-ttu-id="7c24c-148">これは、前のコマンドと同等です。</span><span class="sxs-lookup"><span data-stu-id="7c24c-148">It is the equivalent of the previous command.</span></span>

```
PS C:\> "*get-process*" | Get-Job
```

### <span data-ttu-id="7c24c-149">例 5: 開始されていないジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="7c24c-149">Example 5: Get jobs that have not been started</span></span>

<span data-ttu-id="7c24c-150">このコマンドは、作成されている一方でまだ開始されていないジョブのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-150">This command gets only those jobs that have been created but have not yet been started.</span></span> <span data-ttu-id="7c24c-151">これには、後で実行するようにスケジュール設定されているジョブとまだスケジュール設定されていないジョブが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-151">This includes jobs that are scheduled to run in the future and those not yet scheduled.</span></span>

```
PS C:\> Get-Job -State NotStarted
```

### <span data-ttu-id="7c24c-152">例 6: 名前が割り当てられていないジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="7c24c-152">Example 6: Get jobs that have not been assigned a name</span></span>

<span data-ttu-id="7c24c-153">このコマンドは、job で始まるジョブ名を持つすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-153">This command gets all jobs that have job names that begin with job.</span></span> <span data-ttu-id="7c24c-154">`job<number>`はジョブの既定の名前であるため、このコマンドは、明示的に名前が割り当てられていないすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-154">Because `job<number>` is the default name for a job, this command gets all jobs that do not have an explicitly assigned name.</span></span>

```
PS C:\> Get-Job -Name Job*
```

### <span data-ttu-id="7c24c-155">例 7: ジョブオブジェクトを使用してコマンド内のジョブを表す</span><span class="sxs-lookup"><span data-stu-id="7c24c-155">Example 7: Use a job object to represent the job in a command</span></span>

<span data-ttu-id="7c24c-156">この例では、を使用して `Get-Job` ジョブオブジェクトを取得し、そのジョブオブジェクトを使用してコマンド内のジョブを表す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-156">This example shows how to use `Get-Job` to get a job object, and then it shows how to use the job object to represent the job in a command.</span></span>

<span data-ttu-id="7c24c-157">最初のコマンドは、コマンドレットを使用して、 `Start-Job` `Get-Process` ローカルコンピューター上でコマンドを実行するバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-157">The first command uses the `Start-Job` cmdlet to start a background job that runs a `Get-Process` command on the local computer.</span></span> <span data-ttu-id="7c24c-158">このコマンドは、の **name** パラメーターを使用して `Start-Job` 、ジョブにフレンドリ名を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-158">The command uses the **Name** parameter of `Start-Job` to assign a friendly name to the job.</span></span> <span data-ttu-id="7c24c-159">2番目のコマンドは、を使用し `Get-Job` てジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-159">The second command uses `Get-Job` to get the job.</span></span> <span data-ttu-id="7c24c-160">この例では、の **Name** パラメーターを使用して `Get-Job` ジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-160">It uses the **Name** parameter of `Get-Job` to identify the job.</span></span> <span data-ttu-id="7c24c-161">このコマンドは、結果として得られるジョブオブジェクトを変数に保存し `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-161">The command saves the resulting job object in the `$j` variable.</span></span> <span data-ttu-id="7c24c-162">3番目のコマンドは、変数内の job オブジェクトの値を表示し `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-162">The third command displays the value of the job object in the `$j` variable.</span></span> <span data-ttu-id="7c24c-163">**State** プロパティの値は、ジョブが完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-163">The value of the **State** property shows that the job is completed.</span></span> <span data-ttu-id="7c24c-164">**HasMoreData** プロパティの値は、このジョブに関してまだ取得されていない結果があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="7c24c-164">The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.</span></span> <span data-ttu-id="7c24c-165">4番目のコマンドは、 `Receive-Job` コマンドレットを使用してジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-165">The fourth command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="7c24c-166">ジョブを表すために、変数内の job オブジェクトを使用し `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-166">It uses the job object in the `$j` variable to represent the job.</span></span> <span data-ttu-id="7c24c-167">また、パイプライン演算子を使用して、ジョブオブジェクトをに送信することもでき `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-167">You can also use a pipeline operator to send a job object to `Receive-Job`.</span></span>

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


### <span data-ttu-id="7c24c-168">例 8: 別の方法で開始されたジョブを含むすべてのジョブを取得する</span><span class="sxs-lookup"><span data-stu-id="7c24c-168">Example 8: Get all jobs including jobs started by a different method</span></span>

<span data-ttu-id="7c24c-169">この例では、 `Get-Job` コマンドレットが、別の方法を使用して起動された場合でも、現在のセッションで開始されたすべてのジョブを取得できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="7c24c-169">This example demonstrates that the `Get-Job` cmdlet can get all of the jobs that were started in the current session, even if they were started by using different methods.</span></span>

<span data-ttu-id="7c24c-170">最初のコマンドは、 `Start-Job` コマンドレットを使用して、ローカルコンピューター上でジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-170">The first command uses the `Start-Job` cmdlet to start a job on the local computer.</span></span> <span data-ttu-id="7c24c-171">2番目のコマンドは、コマンドレットの **AsJob** パラメーターを使用して、 `Invoke-Command` S1 コンピューターでジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-171">The second command uses the **AsJob** parameter of the `Invoke-Command` cmdlet to start a job on the S1 computer.</span></span> <span data-ttu-id="7c24c-172">ジョブに含まれるコマンドがリモート コンピューター上で実行される場合でもジョブ オブジェクトがローカル コンピューターに作成されるため、ローカル コマンドを使用してジョブを管理します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-172">Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.</span></span> <span data-ttu-id="7c24c-173">3番目のコマンドは、コマンドレットを使用して、 `Invoke-Command` `Start-Job` S2 コンピューター上でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-173">The third command uses the `Invoke-Command` cmdlet to run a `Start-Job` command on the S2 computer.</span></span> <span data-ttu-id="7c24c-174">この方法を使用すると、ジョブオブジェクトがリモートコンピューター上に作成されるため、リモートコマンドを使用してジョブを管理します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-174">By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.</span></span> <span data-ttu-id="7c24c-175">4番目のコマンドは、を使用して、 `Get-Job` ローカルコンピューターに格納されているジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-175">The fourth command uses `Get-Job` to get the jobs stored on the local computer.</span></span> <span data-ttu-id="7c24c-176">Windows PowerShell 3.0 で導入されたジョブの **PSJobTypeName** プロパティには、コマンドレットを使用して開始したローカルジョブ `Start-Job` がバックグラウンドジョブであり、コマンドレットを使用してリモートセッションで開始されたジョブがリモートジョブであることが示されてい `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-176">The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the `Start-Job` cmdlet is a background job and the job started in a remote session by using the `Invoke-Command` cmdlet is a remote job.</span></span> <span data-ttu-id="7c24c-177">5番目のコマンドは、を使用して `Invoke-Command` `Get-Job` S2 コンピューターでコマンドを実行します。このサンプル出力は、コマンドの結果を示して `Get-Job` います。</span><span class="sxs-lookup"><span data-stu-id="7c24c-177">The fifth command uses `Invoke-Command` to run a `Get-Job` command on the S2 computer.The sample output shows the results of the `Get-Job` command.</span></span> <span data-ttu-id="7c24c-178">S2 コンピューター上では、ジョブはローカル ジョブとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-178">On the S2 computer, the job appears to be a local job.</span></span> <span data-ttu-id="7c24c-179">コンピューター名は localhost で、ジョブの種類はバックグラウンドジョブです。リモートコンピューターでバックグラウンドジョブを実行する方法の詳細については、「 [about_Remote_Jobs](./about/about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c24c-179">The computer name is localhost and the job type is a background job.For more information about how to run background jobs on remote computers, see [about_Remote_Jobs](./about/about_Remote_Jobs.md).</span></span>

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

### <span data-ttu-id="7c24c-180">例 9: 失敗したジョブを調査する</span><span class="sxs-lookup"><span data-stu-id="7c24c-180">Example 9: Investigate a failed job</span></span>

<span data-ttu-id="7c24c-181">このコマンドは、が返すジョブオブジェクトを使用して `Get-Job` 、ジョブが失敗した原因を調査する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-181">This command shows how to use the job object that `Get-Job` returns to investigate why a job failed.</span></span>
<span data-ttu-id="7c24c-182">また、各ジョブの子ジョブを取得する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-182">It also shows how to get the child jobs of each job.</span></span>

<span data-ttu-id="7c24c-183">最初のコマンドは、 `Start-Job` コマンドレットを使用して、ローカルコンピューター上でジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-183">The first command uses the `Start-Job` cmdlet to start a job on the local computer.</span></span> <span data-ttu-id="7c24c-184">が返すジョブオブジェクトは、 `Start-Job` ジョブが失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-184">The job object that `Start-Job` returns shows that the job failed.</span></span> <span data-ttu-id="7c24c-185">**State** プロパティの値が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="7c24c-185">The value of the **State** property is Failed.</span></span>

<span data-ttu-id="7c24c-186">2番目のコマンドは、 `Get-Job` コマンドレットを使用してジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-186">The second command uses the `Get-Job` cmdlet to get the job.</span></span> <span data-ttu-id="7c24c-187">ここでは、ドット表記を使用してオブジェクトの **JobStateInfo** プロパティの値を取得しています。</span><span class="sxs-lookup"><span data-stu-id="7c24c-187">The command uses the dot method to get the value of the **JobStateInfo** property of the object.</span></span> <span data-ttu-id="7c24c-188">パイプライン演算子を使用して、 **Jobstateinfo** プロパティのオブジェクトをコマンドレットに送信し `Format-List` ます。これにより、オブジェクトのすべてのプロパティ () の書式 `*` がリストに設定されます。コマンドの結果は、 `Format-List` ジョブの **Reason** プロパティの値が空白であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="7c24c-188">It uses a pipeline operator to send the object in the **JobStateInfo** property to the `Format-List` cmdlet, which formats all of the properties of the object (`*`) in a list.The result of the `Format-List` command shows that the value of the **Reason** property of the job is blank.</span></span>

<span data-ttu-id="7c24c-189">3番目のコマンドは、詳細を調査します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-189">The third command investigates more.</span></span> <span data-ttu-id="7c24c-190">コマンドを使用して `Get-Job` ジョブを取得し、パイプライン演算子を使用してジョブオブジェクト全体をコマンドレットに送信します。これにより、ジョブ `Format-List` のすべてのプロパティが一覧に表示されます。Job オブジェクトのすべてのプロパティの表示は、そのジョブに Job2 という名前の子ジョブが含まれていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="7c24c-190">It uses a `Get-Job` command to get the job and then uses a pipeline operator to send the whole job object to the `Format-List` cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.</span></span>

<span data-ttu-id="7c24c-191">4番目のコマンドは、を使用して、 `Get-Job` Job2 子ジョブを表すジョブオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-191">The fourth command uses `Get-Job` to get the job object that represents the Job2 child job.</span></span> <span data-ttu-id="7c24c-192">これは、コマンドが実際に実行されたジョブです。</span><span class="sxs-lookup"><span data-stu-id="7c24c-192">This is the job in which the command actually ran.</span></span> <span data-ttu-id="7c24c-193">ここでは、ドットメソッドを使用して、 **Jobstateinfo** プロパティの **Reason** プロパティを取得します。結果には、アクセス拒否エラーによってジョブが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-193">It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error.</span></span> <span data-ttu-id="7c24c-194">この場合、ユーザーは Windows PowerShell を起動するときに [管理者として実行] オプションを使用していません。バックグラウンドジョブは、Windows PowerShell のリモート処理機能を使用するため、ローカルコンピューター上でジョブが実行されている場合でも、ジョブを実行するリモート処理用にコンピューターを構成する必要があります。Windows PowerShell でのリモート処理の要件の詳細については、「 [about_Remote_Requirements](./about/about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c24c-194">In this case, the user forgot to use the Run as administrator option when starting Windows PowerShell.Because background jobs use the remoting features of Windows PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.For information about requirements for remoting in Windows PowerShell, see [about_Remote_Requirements](./about/about_Remote_Requirements.md).</span></span> <span data-ttu-id="7c24c-195">トラブルシューティングのヒントについては、「[about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c24c-195">For troubleshooting tips, see [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md).</span></span>

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

### <span data-ttu-id="7c24c-196">例 10: フィルター処理された結果を取得する</span><span class="sxs-lookup"><span data-stu-id="7c24c-196">Example 10: Get filtered results</span></span>

<span data-ttu-id="7c24c-197">この例では、**Filter** パラメーターを使用してワークフロー ジョブを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-197">This example shows how to use the **Filter** parameter to get a workflow job.</span></span> <span data-ttu-id="7c24c-198">Windows PowerShell 3.0 で導入された **Filter** パラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="7c24c-198">The **Filter** parameter, introduced in Windows PowerShell 3.0 is valid only on custom job types, such as workflow jobs and scheduled jobs.</span></span>

<span data-ttu-id="7c24c-199">最初のコマンドは、 **workflow** キーワードを使用して、ワークフローのワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-199">The first command uses the **Workflow** keyword to create the WFProcess workflow.</span></span> <span data-ttu-id="7c24c-200">2番目のコマンドは、ワークフローをバックグラウンドジョブとして実行するために、処理されたプロセスワークフローの **AsJob** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-200">The second command uses the **AsJob** parameter of the WFProcess workflow to run the workflow as a background job.</span></span> <span data-ttu-id="7c24c-201">ここでは、ワークフローの **JobName** パラメーターを使用してジョブの名前を指定し、ワークフローの **PSPrivateMetadata** パラメーターを使用してカスタム ID を指定しています。</span><span class="sxs-lookup"><span data-stu-id="7c24c-201">It uses the **JobName** parameter of the workflow to specify a name for the job, and the **PSPrivateMetadata** parameter of the workflow to specify a custom ID.</span></span> <span data-ttu-id="7c24c-202">3番目のコマンドは、の **Filter** パラメーターを使用し `Get-Job` て、 **PSPrivateMetadata** パラメーターで指定されたカスタム ID でジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-202">The third command uses the **Filter** parameter of `Get-Job` to get the job by custom ID that was specified in the **PSPrivateMetadata** parameter.</span></span>

```
PS C:\> Workflow WFProcess {Get-Process}
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

### <span data-ttu-id="7c24c-203">例 11: 子ジョブに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="7c24c-203">Example 11: Get information about child jobs</span></span>

<span data-ttu-id="7c24c-204">この例は、コマンドレットの **IncludeChildJob** パラメーターと **childjobstate** パラメーターを使用した場合の効果を示して `Get-Job` います。</span><span class="sxs-lookup"><span data-stu-id="7c24c-204">This example shows the effect of using the **IncludeChildJob** and **ChildJobState** parameters of the `Get-Job` cmdlet.</span></span>

<span data-ttu-id="7c24c-205">最初のコマンドは、現在のセッション内のジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-205">The first command gets the jobs in the current session.</span></span> <span data-ttu-id="7c24c-206">出力には、バックグラウンド ジョブ、リモート ジョブ、およびスケジュールされたジョブのいくつかのインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-206">The output includes a background job, a remote job and several instances of a scheduled job.</span></span> <span data-ttu-id="7c24c-207">リモート ジョブ Job4 については、失敗したことが示されています。</span><span class="sxs-lookup"><span data-stu-id="7c24c-207">The remote job, Job4, appears to have failed.</span></span>
<span data-ttu-id="7c24c-208">2番目のコマンドは、の **IncludeChildJob** パラメーターを使用し `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-208">The second command uses the **IncludeChildJob** parameter of `Get-Job`.</span></span> <span data-ttu-id="7c24c-209">出力には、子ジョブを持つすべてのジョブの子ジョブが追加されます。この場合、変更後の出力には、Job4 の Job5 子ジョブのみが失敗したことが示されます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-209">The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.</span></span> <span data-ttu-id="7c24c-210">3番目のコマンドは、 **Childjobstate** パラメーターを使用して、値が failed であることを示します。出力には、すべての親ジョブと、失敗した子ジョブのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-210">The third command uses the **ChildJobState** parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.</span></span> <span data-ttu-id="7c24c-211">5番目のコマンドは、jobs の **Jobstateinfo** プロパティと **Reason** プロパティを使用して、Job5 が失敗した理由を検出します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-211">The fifth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.</span></span>

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

<span data-ttu-id="7c24c-212">詳細については、 [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md) のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c24c-212">For more information, see the [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md) Help topic.</span></span>

## <span data-ttu-id="7c24c-213">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7c24c-213">PARAMETERS</span></span>

### <span data-ttu-id="7c24c-214">-After</span><span class="sxs-lookup"><span data-stu-id="7c24c-214">-After</span></span>

<span data-ttu-id="7c24c-215">指定された日時以降に終了した完了済みのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-215">Gets completed jobs that ended after the specified date and time.</span></span> <span data-ttu-id="7c24c-216">**Datetime** オブジェクトを入力します。たとえば、コマンドレットによって返されるオブジェクト `Get-Date` や、 **datetime** オブジェクトに変換できる文字列 (やなど) を入力し `Dec 1, 2012 2:00 AM` `11/06` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-216">Enter a **DateTime** object, such as one returned by the `Get-Date` cmdlet or a string that can be converted to a **DateTime** object, such as `Dec 1, 2012 2:00 AM` or `11/06`.</span></span>

<span data-ttu-id="7c24c-217">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、**EndTime** プロパティを持つカスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-217">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="7c24c-218">コマンドレットを使用して作成されたものなど、標準のバックグラウンドジョブでは機能しません `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="7c24c-218">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="7c24c-219">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c24c-219">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="7c24c-220">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7c24c-220">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="7c24c-221">-Before</span><span class="sxs-lookup"><span data-stu-id="7c24c-221">-Before</span></span>

<span data-ttu-id="7c24c-222">指定された日時以前に終了した完了済みのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-222">Gets completed jobs that ended before the specified date and time.</span></span> <span data-ttu-id="7c24c-223">**DateTime** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-223">Enter a **DateTime** object.</span></span>

<span data-ttu-id="7c24c-224">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、**EndTime** プロパティを持つカスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-224">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="7c24c-225">コマンドレットを使用して作成されたものなど、標準のバックグラウンドジョブでは機能しません `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="7c24c-225">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="7c24c-226">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c24c-226">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="7c24c-227">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7c24c-227">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="7c24c-228">-ChildJobState</span><span class="sxs-lookup"><span data-stu-id="7c24c-228">-ChildJobState</span></span>

<span data-ttu-id="7c24c-229">指定された状態を持つ子ジョブのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-229">Gets only the child jobs that have the specified state.</span></span> <span data-ttu-id="7c24c-230">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7c24c-230">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7c24c-231">NotStarted</span><span class="sxs-lookup"><span data-stu-id="7c24c-231">NotStarted</span></span>
- <span data-ttu-id="7c24c-232">実行中</span><span class="sxs-lookup"><span data-stu-id="7c24c-232">Running</span></span>
- <span data-ttu-id="7c24c-233">完了</span><span class="sxs-lookup"><span data-stu-id="7c24c-233">Completed</span></span>
- <span data-ttu-id="7c24c-234">失敗</span><span class="sxs-lookup"><span data-stu-id="7c24c-234">Failed</span></span>
- <span data-ttu-id="7c24c-235">停止済み</span><span class="sxs-lookup"><span data-stu-id="7c24c-235">Stopped</span></span>
- <span data-ttu-id="7c24c-236">［ブロック済み］</span><span class="sxs-lookup"><span data-stu-id="7c24c-236">Blocked</span></span>
- <span data-ttu-id="7c24c-237">Suspended</span><span class="sxs-lookup"><span data-stu-id="7c24c-237">Suspended</span></span>
- <span data-ttu-id="7c24c-238">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="7c24c-238">Disconnected</span></span>
- <span data-ttu-id="7c24c-239">中断中</span><span class="sxs-lookup"><span data-stu-id="7c24c-239">Suspending</span></span>
- <span data-ttu-id="7c24c-240">停止中</span><span class="sxs-lookup"><span data-stu-id="7c24c-240">Stopping</span></span>

<span data-ttu-id="7c24c-241">既定で `Get-Job` は、は子ジョブを取得しません。</span><span class="sxs-lookup"><span data-stu-id="7c24c-241">By default, `Get-Job` does not get child jobs.</span></span> <span data-ttu-id="7c24c-242">**IncludeChildJob** パラメーターを使用して、 `Get-Job` すべての子ジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-242">By using the **IncludeChildJob** parameter, `Get-Job` gets all child jobs.</span></span> <span data-ttu-id="7c24c-243">**ChildJobState** パラメーターを使用した場合、**IncludeChildJob** パラメーターは効果を持ちません。</span><span class="sxs-lookup"><span data-stu-id="7c24c-243">If you use the **ChildJobState** parameter, the **IncludeChildJob** parameter has no effect.</span></span>

<span data-ttu-id="7c24c-244">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7c24c-244">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="7c24c-245">-Command</span><span class="sxs-lookup"><span data-stu-id="7c24c-245">-Command</span></span>

<span data-ttu-id="7c24c-246">コマンドの配列を文字列として指定します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-246">Specifies an array of commands as strings.</span></span> <span data-ttu-id="7c24c-247">このコマンドレットは、指定されたコマンドを含むジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-247">This cmdlet gets the jobs that include the specified commands.</span></span> <span data-ttu-id="7c24c-248">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="7c24c-248">The default is all jobs.</span></span> <span data-ttu-id="7c24c-249">ワイルドカード文字を使用すると、コマンドパターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-249">You can use wildcard characters to specify a command pattern.</span></span>

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

### <span data-ttu-id="7c24c-250">-Filter</span><span class="sxs-lookup"><span data-stu-id="7c24c-250">-Filter</span></span>

<span data-ttu-id="7c24c-251">条件のハッシュテーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-251">Specifies a hash table of conditions.</span></span> <span data-ttu-id="7c24c-252">このコマンドレットは、すべての条件に適合するジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-252">This cmdlet gets jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="7c24c-253">ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-253">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="7c24c-254">このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-254">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="7c24c-255">コマンドレットを使用して作成されたものなど、標準のバックグラウンドジョブでは機能しません `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="7c24c-255">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="7c24c-256">このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c24c-256">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="7c24c-257">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7c24c-257">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="7c24c-258">-Hasdata</span><span class="sxs-lookup"><span data-stu-id="7c24c-258">-HasMoreData</span></span>

<span data-ttu-id="7c24c-259">このコマンドレットが、指定された **hasを持つデータ** プロパティ値を持つジョブのみを取得するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-259">Indicates whether this cmdlet gets only jobs that have the specified **HasMoreData** property value.</span></span>
<span data-ttu-id="7c24c-260">**HasMoreData** プロパティは、すべてのジョブの結果が現在のセッションで受け取られたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-260">The **HasMoreData** property indicates whether all job results have been received in the current session.</span></span> <span data-ttu-id="7c24c-261">より多くの結果を持つジョブを取得するには、の値を指定し `$True` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-261">To get jobs that have more results, specify a value of `$True`.</span></span> <span data-ttu-id="7c24c-262">より多くの結果が得られないジョブを取得するには、の値を指定し `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-262">To get jobs that do not have more results, specify a value of `$False`.</span></span>

<span data-ttu-id="7c24c-263">ジョブの結果を取得するには、コマンドレットを使用し `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-263">To get the results of a job, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="7c24c-264">コマンドレットを使用すると、 `Receive-Job` メモリ内のセッション固有のストレージから、返された結果が削除されます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-264">When you use the `Receive-Job` cmdlet, it deletes from its in-memory, session-specific storage the results that it returned.</span></span> <span data-ttu-id="7c24c-265">現在のセッションでジョブのすべての結果が返されると、ジョブの **Hasmore data** プロパティの値がに設定され、 `$False` 現在のセッションにジョブの結果がなくなったことが示されます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-265">When it has returned all results of the job in the current session, it sets the value of the **HasMoreData** property of the job to `$False`) to indicate that it has no more results for the job in the current session.</span></span> <span data-ttu-id="7c24c-266">が `Receive-Job` `Receive-Job` 結果を削除して、 **hasdata** プロパティの値を変更しないようにするには、の Keep パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-266">Use the **Keep** parameter of `Receive-Job` to prevent `Receive-Job` from deleting results and changing the value of the **HasMoreData** property.</span></span>
<span data-ttu-id="7c24c-267">詳細を表示するには「`Get-Help Receive-Job`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-267">For more information, type `Get-Help Receive-Job`.</span></span>

<span data-ttu-id="7c24c-268">**HasMoreData** プロパティは、現在のセッションに固有です。</span><span class="sxs-lookup"><span data-stu-id="7c24c-268">The **HasMoreData** property is specific to the current session.</span></span> <span data-ttu-id="7c24c-269">ジョブの結果をディスクに保存するスケジュールされたジョブの種類など、カスタムジョブの種類の結果がセッションの外部に保存される場合は、 `Receive-Job` 別のセッションでコマンドレットを使用して、 **hasdata** の値がの場合でも、ジョブの結果を再び取得でき `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-269">If results for a custom job type are saved outside of the session, such as the scheduled job type, which saves job results on disk, you can use the `Receive-Job` cmdlet in a different session to get the job results again, even if the value of **HasMoreData** is `$False`.</span></span> <span data-ttu-id="7c24c-270">詳細については、カスタムのジョブの種類のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c24c-270">For more information, see the help topics for the custom job type.</span></span>

<span data-ttu-id="7c24c-271">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7c24c-271">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="7c24c-272">-Id</span><span class="sxs-lookup"><span data-stu-id="7c24c-272">-Id</span></span>

<span data-ttu-id="7c24c-273">このコマンドレットが取得するジョブの Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-273">Specifies an array of IDs of jobs that this cmdlet gets.</span></span>

<span data-ttu-id="7c24c-274">ID は、現在のセッションでジョブを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="7c24c-274">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="7c24c-275">インスタンス ID よりも覚えやすく、入力する方が簡単ですが、現在のセッションでのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="7c24c-275">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="7c24c-276">1つ以上の Id をコンマで区切って入力できます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-276">You can type one or more IDs separated by commas.</span></span> <span data-ttu-id="7c24c-277">ジョブの ID を検索するには、パラメーターを指定せずに「」と入力 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-277">To find the ID of a job, type `Get-Job` without parameters.</span></span>

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

### <span data-ttu-id="7c24c-278">-IncludeChildJob</span><span class="sxs-lookup"><span data-stu-id="7c24c-278">-IncludeChildJob</span></span>

<span data-ttu-id="7c24c-279">このコマンドレットが親ジョブに加えて子ジョブも返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-279">Indicates that this cmdlet returns child jobs, in addition to parent jobs.</span></span>

<span data-ttu-id="7c24c-280">このパラメーターは、 `Get-Job` エラーの原因が子ジョブのプロパティに保存されるため、がコンテナーの親ジョブとジョブの失敗を返すワークフロージョブを調査する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="7c24c-280">This parameter is especially useful for investigating workflow jobs, for which `Get-Job` returns a container parent job, and job failures, because the reason for the failure is saved in a property of the child job.</span></span>

<span data-ttu-id="7c24c-281">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7c24c-281">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="7c24c-282">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="7c24c-282">-InstanceId</span></span>

<span data-ttu-id="7c24c-283">このコマンドレットが取得するジョブのインスタンス Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-283">Specifies an array of instance IDs of jobs that this cmdlet gets.</span></span> <span data-ttu-id="7c24c-284">既定値はすべてのジョブです。</span><span class="sxs-lookup"><span data-stu-id="7c24c-284">The default is all jobs.</span></span>

<span data-ttu-id="7c24c-285">インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="7c24c-285">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="7c24c-286">ジョブのインスタンス ID を検索するには、を使用 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-286">To find the instance ID of a job, use `Get-Job`.</span></span>

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

### <span data-ttu-id="7c24c-287">-Name</span><span class="sxs-lookup"><span data-stu-id="7c24c-287">-Name</span></span>

<span data-ttu-id="7c24c-288">このコマンドレットが取得するジョブのインスタンスフレンドリ名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-288">Specifies an array of instance friendly names of jobs that this cmdlet gets.</span></span> <span data-ttu-id="7c24c-289">ジョブの名前を入力するか、またはワイルドカード文字を使用してジョブ名のパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-289">Enter a job name, or use wildcard characters to enter a job name pattern.</span></span> <span data-ttu-id="7c24c-290">既定では、は、 `Get-Job` 現在のセッション内のすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-290">By default, `Get-Job` gets all jobs in the current session.</span></span>

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

### <span data-ttu-id="7c24c-291">-最新</span><span class="sxs-lookup"><span data-stu-id="7c24c-291">-Newest</span></span>

<span data-ttu-id="7c24c-292">取得するジョブの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-292">Specifies a number of jobs to get.</span></span> <span data-ttu-id="7c24c-293">このコマンドレットは、最後に終了したジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-293">This cmdlet gets the jobs that ended most recently.</span></span>

<span data-ttu-id="7c24c-294">**Newest** パラメーターは、並べ替えを行わずに、終了時刻の順で最も新しいジョブを返します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-294">The **Newest** parameter does not sort or return the newest jobs in end-time order.</span></span> <span data-ttu-id="7c24c-295">出力を並べ替えるには、コマンドレットを使用し `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-295">To sort the output, use the `Sort-Object` cmdlet.</span></span>

<span data-ttu-id="7c24c-296">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7c24c-296">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="7c24c-297">-状態</span><span class="sxs-lookup"><span data-stu-id="7c24c-297">-State</span></span>

<span data-ttu-id="7c24c-298">ジョブの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-298">Specifies a job state.</span></span> <span data-ttu-id="7c24c-299">このコマンドレットは、指定された状態のジョブのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-299">This cmdlet gets only jobs in the specified state.</span></span> <span data-ttu-id="7c24c-300">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7c24c-300">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7c24c-301">NotStarted</span><span class="sxs-lookup"><span data-stu-id="7c24c-301">NotStarted</span></span>
- <span data-ttu-id="7c24c-302">実行中</span><span class="sxs-lookup"><span data-stu-id="7c24c-302">Running</span></span>
- <span data-ttu-id="7c24c-303">完了</span><span class="sxs-lookup"><span data-stu-id="7c24c-303">Completed</span></span>
- <span data-ttu-id="7c24c-304">失敗</span><span class="sxs-lookup"><span data-stu-id="7c24c-304">Failed</span></span>
- <span data-ttu-id="7c24c-305">停止済み</span><span class="sxs-lookup"><span data-stu-id="7c24c-305">Stopped</span></span>
- <span data-ttu-id="7c24c-306">［ブロック済み］</span><span class="sxs-lookup"><span data-stu-id="7c24c-306">Blocked</span></span>
- <span data-ttu-id="7c24c-307">Suspended</span><span class="sxs-lookup"><span data-stu-id="7c24c-307">Suspended</span></span>
- <span data-ttu-id="7c24c-308">[Disconnected]\(切断済み\)</span><span class="sxs-lookup"><span data-stu-id="7c24c-308">Disconnected</span></span>
- <span data-ttu-id="7c24c-309">中断中</span><span class="sxs-lookup"><span data-stu-id="7c24c-309">Suspending</span></span>
- <span data-ttu-id="7c24c-310">停止中</span><span class="sxs-lookup"><span data-stu-id="7c24c-310">Stopping</span></span>

<span data-ttu-id="7c24c-311">既定では、は、 `Get-Job` 現在のセッション内のすべてのジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-311">By default, `Get-Job` gets all the jobs in the current session.</span></span>

<span data-ttu-id="7c24c-312">ジョブの状態の詳細については、「 [Jobstate 列挙型](/dotnet/api/system.management.automation.jobstate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c24c-312">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

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

### <span data-ttu-id="7c24c-313">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7c24c-313">CommonParameters</span></span>

<span data-ttu-id="7c24c-314">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7c24c-314">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7c24c-315">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c24c-315">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7c24c-316">入力</span><span class="sxs-lookup"><span data-stu-id="7c24c-316">INPUTS</span></span>

### <span data-ttu-id="7c24c-317">なし</span><span class="sxs-lookup"><span data-stu-id="7c24c-317">None</span></span>

<span data-ttu-id="7c24c-318">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="7c24c-318">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="7c24c-319">出力</span><span class="sxs-lookup"><span data-stu-id="7c24c-319">OUTPUTS</span></span>

### <span data-ttu-id="7c24c-320">System. Automation. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="7c24c-320">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="7c24c-321">このコマンドレットは、セッション内のジョブを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-321">This cmdlet returns objects that represent the jobs in the session.</span></span>

## <span data-ttu-id="7c24c-322">注</span><span class="sxs-lookup"><span data-stu-id="7c24c-322">NOTES</span></span>

<span data-ttu-id="7c24c-323">ジョブの **PSJobTypeName** プロパティは、ジョブの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-323">The **PSJobTypeName** property of jobs indicates the job type of the job.</span></span> <span data-ttu-id="7c24c-324">プロパティ値は、ジョブの種類の作成者によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="7c24c-324">The property value is determined by the job type author.</span></span> <span data-ttu-id="7c24c-325">次の一覧に、一般的なジョブの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="7c24c-325">The following list shows common job types.</span></span>

- <span data-ttu-id="7c24c-326">**Backgroundjob**。</span><span class="sxs-lookup"><span data-stu-id="7c24c-326">**BackgroundJob**.</span></span> <span data-ttu-id="7c24c-327">ローカルジョブは、を使用して開始されました `Start-Job` 。</span><span class="sxs-lookup"><span data-stu-id="7c24c-327">Local job started by using `Start-Job`.</span></span>
- <span data-ttu-id="7c24c-328">**Remotejob**。</span><span class="sxs-lookup"><span data-stu-id="7c24c-328">**RemoteJob**.</span></span> <span data-ttu-id="7c24c-329">コマンドレットの **AsJob** パラメーターを使用して、 **PSSession** でジョブが開始されました `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="7c24c-329">Job started in a **PSSession** by using the **AsJob** parameter of the `Invoke-Command` cmdlet.</span></span>
- <span data-ttu-id="7c24c-330">**Psworkflowjob**。</span><span class="sxs-lookup"><span data-stu-id="7c24c-330">**PSWorkflowJob**.</span></span> <span data-ttu-id="7c24c-331">ワークフローの **AsJob** 共通パラメーターを使用して開始されたジョブ。</span><span class="sxs-lookup"><span data-stu-id="7c24c-331">Job started by using the **AsJob** common parameter of workflows.</span></span>

## <span data-ttu-id="7c24c-332">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7c24c-332">RELATED LINKS</span></span>

[<span data-ttu-id="7c24c-333">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="7c24c-333">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="7c24c-334">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="7c24c-334">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="7c24c-335">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="7c24c-335">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="7c24c-336">Start-Job</span><span class="sxs-lookup"><span data-stu-id="7c24c-336">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="7c24c-337">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="7c24c-337">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="7c24c-338">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="7c24c-338">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="7c24c-339">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="7c24c-339">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="7c24c-340">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="7c24c-340">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="7c24c-341">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="7c24c-341">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)
