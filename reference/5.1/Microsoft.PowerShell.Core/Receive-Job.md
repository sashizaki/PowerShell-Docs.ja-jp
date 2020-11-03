---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/receive-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-Job
ms.openlocfilehash: 7b872c2a28943ee3d2b9ab27459ddb87722cc954
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212840"
---
# <span data-ttu-id="b7196-103">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="b7196-103">Receive-Job</span></span>

## <span data-ttu-id="b7196-104">概要</span><span class="sxs-lookup"><span data-stu-id="b7196-104">SYNOPSIS</span></span>
<span data-ttu-id="b7196-105">現在のセッションの PowerShell バックグラウンドジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="b7196-105">Gets the results of the PowerShell background jobs in the current session.</span></span>

## <span data-ttu-id="b7196-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b7196-106">SYNTAX</span></span>

### <span data-ttu-id="b7196-107">Location (既定値)</span><span class="sxs-lookup"><span data-stu-id="b7196-107">Location (Default)</span></span>

```
Receive-Job [-Job] <Job[]> [[-Location] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="b7196-108">Session</span><span class="sxs-lookup"><span data-stu-id="b7196-108">Session</span></span>

```
Receive-Job [-Job] <Job[]> [[-Session] <PSSession[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="b7196-109">[ComputerName]</span><span class="sxs-lookup"><span data-stu-id="b7196-109">ComputerName</span></span>

```
Receive-Job [-Job] <Job[]> [[-ComputerName] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="b7196-110">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="b7196-110">NameParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="b7196-111">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="b7196-111">InstanceIdParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="b7196-112">SessionIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="b7196-112">SessionIdParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="b7196-113">Description</span><span class="sxs-lookup"><span data-stu-id="b7196-113">DESCRIPTION</span></span>

<span data-ttu-id="b7196-114">コマンドレットは、コマンド `Receive-Job` `Start-Job` レットまたは任意のコマンドレットの **AsJob** パラメーターを使用して開始されたジョブなど、PowerShell のバックグラウンドジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="b7196-114">The `Receive-Job` cmdlet gets the results of PowerShell background jobs, such as those started by using the `Start-Job` cmdlet or the **AsJob** parameter of any cmdlet.</span></span>
<span data-ttu-id="b7196-115">すべてのジョブの結果の取得、名前、ID、インスタンス ID、コンピューター名、場所、セッションによる指定、ジョブ オブジェクトの送信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b7196-115">You can get the results of all jobs or identify jobs by their name, ID, instance ID, computer name, location, or session, or by submitting a job object.</span></span>

<span data-ttu-id="b7196-116">PowerShell バックグラウンドジョブを開始すると、ジョブが開始されますが、結果はすぐには表示されません。</span><span class="sxs-lookup"><span data-stu-id="b7196-116">When you start a PowerShell background job, the job starts, but the results do not appear immediately.</span></span> <span data-ttu-id="b7196-117">代わりに、バックグラウンド ジョブを表すオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="b7196-117">Instead, the command returns an object that represents the background job.</span></span>
<span data-ttu-id="b7196-118">このジョブ オブジェクトには、ジョブに関する有用な情報が含まれていますが、結果は含まれません。</span><span class="sxs-lookup"><span data-stu-id="b7196-118">The job object contains useful information about the job, but it does not contain the results.</span></span>
<span data-ttu-id="b7196-119">このメソッドを使用すると、ジョブの実行中にセッションで作業を続行できます。</span><span class="sxs-lookup"><span data-stu-id="b7196-119">This method lets you continue to work in the session while the job runs.</span></span>
<span data-ttu-id="b7196-120">PowerShell のバックグラウンドジョブの詳細については、「 [about_Jobs](./About/about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7196-120">For more information about background jobs in PowerShell, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="b7196-121">`Receive-Job`コマンドレットは、コマンドの送信時に生成された結果を取得し `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="b7196-121">The `Receive-Job` cmdlet gets the results that have been generated by the time that the `Receive-Job` command is submitted.</span></span>
<span data-ttu-id="b7196-122">結果がまだ完了していない場合は、追加 `Receive-Job` のコマンドを実行して残りの結果を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b7196-122">If the results are not yet complete, you can run additional `Receive-Job` commands to get the remaining results.</span></span>

<span data-ttu-id="b7196-123">既定では、ジョブの結果は受信時にシステムから削除されますが、再度受信できるように **Keep** パラメーターを使用して結果を保存することができます。</span><span class="sxs-lookup"><span data-stu-id="b7196-123">By default, job results are deleted from the system when you receive them, but you can use the **Keep** parameter to save the results so that you can receive them again.</span></span>
<span data-ttu-id="b7196-124">ジョブの結果を削除するには、 `Receive-Job` **Keep** パラメーターを指定せずにコマンドを再度実行するか、セッションを閉じるか、コマンドレットを使用して `Remove-Job` セッションからジョブを削除します。</span><span class="sxs-lookup"><span data-stu-id="b7196-124">To delete the job results, run the `Receive-Job` command again without the **Keep** parameter, close the session, or use the `Remove-Job` cmdlet to delete the job from the session.</span></span>

<span data-ttu-id="b7196-125">Windows PowerShell 3.0 以降では、 `Receive-Job` ワークフロージョブやスケジュールされたジョブのインスタンスなどのカスタムジョブの種類の結果も取得します。</span><span class="sxs-lookup"><span data-stu-id="b7196-125">Starting in Windows PowerShell 3.0, `Receive-Job` also gets the results of custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="b7196-126">がカスタムのジョブの種類の結果を取得できるようにするには `Receive-Job` 、コマンドを実行する前に、コマンドを実行する前に、カスタムジョブの種類をサポートするモジュールをセッションにインポートします。そのためには、 `Receive-Job` コマンドレットを使用するか、 `Import-Module` またはモジュールのコマンドレットを取得します。</span><span class="sxs-lookup"><span data-stu-id="b7196-126">To enable `Receive-Job` to get the results a custom job type, import the module that supports the custom job type into the session before it runs a `Receive-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="b7196-127">特定のカスタム ジョブの種類については、カスタムのジョブの種類機能のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7196-127">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="b7196-128">例</span><span class="sxs-lookup"><span data-stu-id="b7196-128">EXAMPLES</span></span>

### <span data-ttu-id="b7196-129">例 1: 特定のジョブの結果を取得する</span><span class="sxs-lookup"><span data-stu-id="b7196-129">Example 1: Get results for a particular job</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
Receive-Job -Job $job
```

<span data-ttu-id="b7196-130">これらのコマンドは、の **job** パラメーターを使用して、 `Receive-Job` 特定のジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="b7196-130">These commands use the **Job** parameter of `Receive-Job` to get the results of a particular job.</span></span>

<span data-ttu-id="b7196-131">最初のコマンドは、を使用してジョブを開始し、その `Start-Job` ジョブオブジェクトを変数に格納し `$job` ます。</span><span class="sxs-lookup"><span data-stu-id="b7196-131">The first command starts a job with `Start-Job` and stores the job object in the `$job` variable.</span></span>

<span data-ttu-id="b7196-132">2番目のコマンドは、 `Receive-Job` コマンドレットを使用してジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="b7196-132">The second command uses the `Receive-Job` cmdlet to get the results of the job.</span></span>
<span data-ttu-id="b7196-133">**Job** パラメーターを使用して、ジョブを指定しています。</span><span class="sxs-lookup"><span data-stu-id="b7196-133">It uses the **Job** parameter to specify the job.</span></span>

### <span data-ttu-id="b7196-134">例 2: Keep パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="b7196-134">Example 2: Use the Keep parameter</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Service dhcp, fakeservice}
$job | Receive-Job -Keep
```

```Output
Cannot find any service with service name 'fakeservice'.
    + CategoryInfo          : ObjectNotFound: (fakeservice:String) [Get-Service], ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.GetServiceCommand
    + PSComputerName        : localhost

Status   Name               DisplayName
------   ----               -----------
Running  dhcp               DHCP Client
```

```powershell
$job | Receive-Job -Keep
```

```output
Cannot find any service with service name 'fakeservice'.
    + CategoryInfo          : ObjectNotFound: (fakeservice:String) [Get-Service], ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.GetServiceCommand
    + PSComputerName        : localhost

Status   Name               DisplayName
------   ----               -----------
Running  dhcp               DHCP Client
```

<span data-ttu-id="b7196-135">この例では、ジョブを変数に格納し、その `$job` ジョブを `Receive-Job` コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="b7196-135">This example stores a job in the `$job` variable, and pipes the job to the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="b7196-136">`-Keep`パラメーターは、最初のビューの後にすべての集計ストリームデータを再度取得できるようにするためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="b7196-136">The `-Keep` parameter is also used to allow all aggregated stream data to be retrieved again after first view.</span></span>

### <span data-ttu-id="b7196-137">例 3: いくつかのバックグラウンドジョブの結果を取得する</span><span class="sxs-lookup"><span data-stu-id="b7196-137">Example 3: Get results of several background jobs</span></span>

<span data-ttu-id="b7196-138">の **AsJob** パラメーターを使用して `Invoke-Command` ジョブを開始すると、ジョブがリモートコンピューター上で実行されている場合でも、ジョブオブジェクトがローカルコンピューター上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="b7196-138">When you use the **AsJob** parameter of `Invoke-Command` to start a job, the job object is created on the local computer, even though the job runs on the remote computers.</span></span>
<span data-ttu-id="b7196-139">その結果、ジョブを管理するには、ローカルのコマンドを使用することになります。</span><span class="sxs-lookup"><span data-stu-id="b7196-139">As a result, you use local commands to manage the job.</span></span>

<span data-ttu-id="b7196-140">また、 **AsJob** を使用すると、PowerShell は、開始された各ジョブの子ジョブを含む1つのジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="b7196-140">Also, when you use **AsJob** , PowerShell returns one job object that contains a child job for each job that was started.</span></span> <span data-ttu-id="b7196-141">この例では、ジョブ オブジェクトには、各リモート コンピューターのジョブに 1 つずつ、合計 3 つの子ジョブが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b7196-141">In this case, the job object contains three child jobs, one for each job on each remote computer.</span></span>

```powershell
# Use the Invoke-Command cmdlet with the -AsJob parameter to start a background job that runs a Get-Service command on three remote computers.
# Store the resulting job object in the $j variable
$j = Invoke-Command -ComputerName Server01, Server02, Server03 -ScriptBlock {Get-Service} -AsJob
# Display the value of the **ChildJobs** property of the job object in $j.
# The display shows that the command created three child jobs, one for the job on each remote computer.
# You could also use the -IncludeChildJobs parameter of the Get-Job cmdlet.
$j.ChildJobs
```

```Output
Id   Name     State      HasMoreData   Location       Command
--   ----     -----      -----------   --------       -------
2    Job2     Completed  True          Server01       Get-Service
3    Job3     Completed  True          Server02       Get-Service
4    Job4     Completed  True          Server03       Get-Service
```

```powershell
# Use the Receive-Job cmdlet to get the results of just the Job3 child job that ran on the Server02 computer.
# Use the *Keep* parameter to allow you to view the aggregated stream data more than once.
Receive-Job -Name Job3 -Keep
```

```Output
Status  Name        DisplayName                        PSComputerName
------  ----------- -----------                        --------------
Running AeLookupSvc Application Experience             Server02
Stopped ALG         Application Layer Gateway Service  Server02
Running Appinfo     Application Information            Server02
Running AppMgmt     Application Management             Server02
```

### <span data-ttu-id="b7196-142">例 4: 複数のリモートコンピューターでバックグラウンドジョブの結果を取得する</span><span class="sxs-lookup"><span data-stu-id="b7196-142">Example 4: Get results of background jobs on multiple remote computers</span></span>

```powershell
# Use the New-PSSession cmdlet to create three user-managed PSSessions on three servers, and save the sessions in the $s variable.
$s = New-PSSession -ComputerName Server01, Server02, Server03
# Use Invoke-Command run a Start-Job command in each of the PSSessions in the $s variable.
# The job outputs the ComputerName of each server.
# Save the job objects in the $j variable.
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$env:COMPUTERNAME}}
# To confirm that these job objects are from the remote machines, run Get-Job to show no local jobs running.
Get-Job
```

```Output

```

```powershell
# Display the three job objects in $j.
# Note that the Localhost location is not the local computer, but instead localhost as it relates to the job on each Server.
$j
```

```Output
Id   Name     State      HasMoreData   Location   Command
--   ----     -----      -----------   --------   -------
1    Job1     Completed  True          Localhost  $env:COMPUTERNAME
2    Job2     Completed  True          Localhost  $env:COMPUTERNAME
3    Job3     Completed  True          Localhost  $env:COMPUTERNAME
```

```powershell
# Use Invoke-Command to run a Receive-Job command in each of the sessions in the $s variable and save the results in the $Results variable.
# The Receive-Job command must be run in each session because the jobs were run locally on each server.
$results = Invoke-Command -Session $s -ScriptBlock {Receive-Job -Job $Using:j}
```

```Output
Server01
Server02
Server03
```

<span data-ttu-id="b7196-143">この例は、3 つのリモート コンピューター上で実行されるバックグラウンド ジョブの結果を取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b7196-143">This example shows how to get the results of background jobs run on three remote computers.</span></span>
<span data-ttu-id="b7196-144">前の例とは異なり、を使用して `Invoke-Command` コマンドを実行すると、 `Start-Job` 3 台のコンピューターそれぞれに対して3つの独立したジョブが実際に開始されます。</span><span class="sxs-lookup"><span data-stu-id="b7196-144">Unlike the previous example, using `Invoke-Command` to run the `Start-Job` command actually started three independent jobs on each of the three computers.</span></span> <span data-ttu-id="b7196-145">結果として、このコマンドは、3 つの異なるコンピューターでローカルに実行される 3 つのジョブを表す 3 つのジョブ オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="b7196-145">As a result, the command returned three job objects representing three jobs run locally on three different computers.</span></span>

> [!NOTE]
> <span data-ttu-id="b7196-146">最後のコマンドでは、 `$j` がローカル変数であるため、スクリプトブロックは **Using** スコープ修飾子を使用して変数を識別し `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="b7196-146">In the last command, because `$j` is a local variable, the script block uses the **Using** scope modifier to identify the `$j` variable.</span></span> <span data-ttu-id="b7196-147">スコープ修飾子の **使用** の詳細については、「 [about_Remote_Variables](./About/about_Remote_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7196-147">For more information about the **Using** scope modifier, see [about_Remote_Variables](./About/about_Remote_Variables.md).</span></span>

### <span data-ttu-id="b7196-148">例 5: 子ジョブにアクセスする</span><span class="sxs-lookup"><span data-stu-id="b7196-148">Example 5: Access child jobs</span></span>

<span data-ttu-id="b7196-149">パラメーターは、 `-Keep` ジョブの集計されたストリームの状態を保持して、再び表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b7196-149">The `-Keep` parameter preserves the state of the aggregated streams of a job so that it can be viewed again.</span></span> <span data-ttu-id="b7196-150">このパラメーターを指定しないと、ジョブの受信時にすべての集計ストリームデータが消去されます。</span><span class="sxs-lookup"><span data-stu-id="b7196-150">Without this parameter all aggregated stream data is erased when the job is received.</span></span> <span data-ttu-id="b7196-151">詳細については、「」を参照してください [about_Job_Details](About/about_Job_Details.md#child-jobs)</span><span class="sxs-lookup"><span data-stu-id="b7196-151">For more information, see [about_Job_Details](About/about_Job_Details.md#child-jobs)</span></span>

> [!NOTE]
> <span data-ttu-id="b7196-152">集計されたストリームには、すべての子ジョブのストリームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b7196-152">The aggregated streams include the streams of all child jobs.</span></span> <span data-ttu-id="b7196-153">引き続き、ジョブオブジェクトと子ジョブオブジェクトを使用して、個々のデータストリームに接続できます。</span><span class="sxs-lookup"><span data-stu-id="b7196-153">You can still reach the individual streams of data through the job object and child job objects.</span></span>

```powershell
Start-Job -Name TestJob -ScriptBlock {dir C:\, Z:\}
# Without the Keep parameter, aggregated child job data is displayed once.
# Then destroyed.
Receive-Job -Name TestJob
```

```output
    Directory: C:\

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-r---        1/24/2019   7:11 AM                Program Files
d-r---        2/13/2019   8:32 AM                Program Files (x86)
d-r---        10/3/2018  11:47 AM                Users
d-----         2/7/2019   1:52 AM                Windows
Cannot find drive. A drive with the name 'Z' does not exist.
    + CategoryInfo          : ObjectNotFound: (Z:String) [Get-ChildItem], DriveNotFoundException
    + FullyQualifiedErrorId : DriveNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
    + PSComputerName        : localhost
```

```powershell
# It would seem that the child job data is gone.
Receive-Job -Name TestJob
```

```output

```

```powershell
# Using the object model, you can still retrieve child job data and streams.
$job = Get-Job -Name TestJob
$job.ChildJobs[0].Error
```

```output
Cannot find drive. A drive with the name 'Z' does not exist.
    + CategoryInfo          : ObjectNotFound: (Z:String) [Get-ChildItem], DriveNotFoundException
    + FullyQualifiedErrorId : DriveNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
    + PSComputerName        : localhost
```

## <span data-ttu-id="b7196-154">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b7196-154">PARAMETERS</span></span>

### <span data-ttu-id="b7196-155">-AutoRemoveJob</span><span class="sxs-lookup"><span data-stu-id="b7196-155">-AutoRemoveJob</span></span>

<span data-ttu-id="b7196-156">このコマンドレットがジョブの結果を返した後にジョブを削除することを示します。</span><span class="sxs-lookup"><span data-stu-id="b7196-156">Indicates that this cmdlet deletes the job after it returns the job results.</span></span>
<span data-ttu-id="b7196-157">ジョブの結果が増えると、ジョブは削除されますが、 `Receive-Job` メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7196-157">If the job has more results, the job is still deleted, but `Receive-Job` displays a message.</span></span>

<span data-ttu-id="b7196-158">このパラメーターは、カスタムのジョブの種類に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="b7196-158">This parameter works only on custom job types.</span></span>
<span data-ttu-id="b7196-159">スケジュールされたジョブのインスタンスなど、ジョブやセッションの外部の種類を保存するジョブのインスタンス用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="b7196-159">It is designed for instances of job types that save the job or the type outside of the session, such as instances of scheduled jobs.</span></span>

<span data-ttu-id="b7196-160">このパラメーターは、 **Wait** パラメーターなしでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="b7196-160">This parameter cannot be used without the **Wait** parameter.</span></span>

<span data-ttu-id="b7196-161">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b7196-161">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="b7196-162">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="b7196-162">-ComputerName</span></span>

<span data-ttu-id="b7196-163">コンピューターの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7196-163">Specifies an array of names of computers.</span></span>

<span data-ttu-id="b7196-164">このパラメーターは、ローカル コンピューターに格納されているジョブの結果の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="b7196-164">This parameter selects from among the job results that are stored on the local computer.</span></span>
<span data-ttu-id="b7196-165">リモートコンピューターで実行されるジョブのデータは取得されません。</span><span class="sxs-lookup"><span data-stu-id="b7196-165">It does not get data for jobs run on remote computers.</span></span>
<span data-ttu-id="b7196-166">リモートコンピューターに格納されているジョブの結果を取得するには、 `Invoke-Command` コマンドレットを使用して `Receive-Job` コマンドをリモートで実行します。</span><span class="sxs-lookup"><span data-stu-id="b7196-166">To get job results that are stored on remote computers, use the `Invoke-Command` cmdlet to run a `Receive-Job` command remotely.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: False
Position: 1
Default value: All computers available
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="b7196-167">-Force</span><span class="sxs-lookup"><span data-stu-id="b7196-167">-Force</span></span>

<span data-ttu-id="b7196-168">ジョブが **中断** 状態または **切断** 状態の場合、このコマンドレットは待機を続行することを示します。</span><span class="sxs-lookup"><span data-stu-id="b7196-168">Indicates that this cmdlet continues waiting if jobs are in the **Suspended** or **Disconnected** state.</span></span> <span data-ttu-id="b7196-169">既定では、の **wait** パラメーターは、 `Receive-Job` ジョブが次のいずれかの状態にある場合に、待機を返します。</span><span class="sxs-lookup"><span data-stu-id="b7196-169">By default, the **Wait** parameter of `Receive-Job` returns, or terminates the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="b7196-170">完了</span><span class="sxs-lookup"><span data-stu-id="b7196-170">Completed</span></span>
- <span data-ttu-id="b7196-171">失敗</span><span class="sxs-lookup"><span data-stu-id="b7196-171">Failed</span></span>
- <span data-ttu-id="b7196-172">停止済み</span><span class="sxs-lookup"><span data-stu-id="b7196-172">Stopped</span></span>
- <span data-ttu-id="b7196-173">Suspended</span><span class="sxs-lookup"><span data-stu-id="b7196-173">Suspended</span></span>
- <span data-ttu-id="b7196-174">[接続解除されました。]</span><span class="sxs-lookup"><span data-stu-id="b7196-174">Disconnected.</span></span>

<span data-ttu-id="b7196-175">**Force** パラメーターは、このコマンドで **Wait** パラメーターも使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="b7196-175">The **Force** parameter is valid only when the **Wait** parameter is also used in the command.</span></span>

<span data-ttu-id="b7196-176">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b7196-176">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="b7196-177">-Id</span><span class="sxs-lookup"><span data-stu-id="b7196-177">-Id</span></span>

<span data-ttu-id="b7196-178">ID の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7196-178">Specifies an array of IDs.</span></span>
<span data-ttu-id="b7196-179">このコマンドレットは、指定された Id を持つジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="b7196-179">This cmdlet gets the results of jobs with the specified IDs.</span></span>

<span data-ttu-id="b7196-180">ID は、現在のセッションでジョブを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="b7196-180">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="b7196-181">インスタンス ID よりも覚えやすく、入力も簡単ですが、現在のセッションでのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="b7196-181">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="b7196-182">1つ以上の Id をコンマで区切って入力できます。</span><span class="sxs-lookup"><span data-stu-id="b7196-182">You can type one or more IDs separated by commas.</span></span>
<span data-ttu-id="b7196-183">ジョブの ID を検索するには、を使用 `Get-Job` します。</span><span class="sxs-lookup"><span data-stu-id="b7196-183">To find the ID of a job, use `Get-Job`.</span></span>

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

### <span data-ttu-id="b7196-184">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="b7196-184">-InstanceId</span></span>

<span data-ttu-id="b7196-185">インスタンス Id の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7196-185">Specifies an array of instance IDs.</span></span>
<span data-ttu-id="b7196-186">このコマンドレットは、指定されたインスタンス Id を持つジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="b7196-186">This cmdlet gets the results of jobs with the specified instance IDs.</span></span>

<span data-ttu-id="b7196-187">インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="b7196-187">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="b7196-188">ジョブのインスタンス ID を検索するには、コマンドレットを使用し `Get-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="b7196-188">To find the instance ID of a job, use the `Get-Job` cmdlet.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All instances
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b7196-189">-ジョブ</span><span class="sxs-lookup"><span data-stu-id="b7196-189">-Job</span></span>

<span data-ttu-id="b7196-190">結果を取得するジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="b7196-190">Specifies the job for which results are being retrieved.</span></span>

<span data-ttu-id="b7196-191">ジョブまたはジョブを取得するコマンドを含む変数を入力します。</span><span class="sxs-lookup"><span data-stu-id="b7196-191">Enter a variable that contains the job or a command that gets the job.</span></span>
<span data-ttu-id="b7196-192">パイプを使用してジョブオブジェクトをにパイプすることもでき `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="b7196-192">You can also pipe a job object to `Receive-Job`.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: Location, Session, ComputerName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b7196-193">-保持</span><span class="sxs-lookup"><span data-stu-id="b7196-193">-Keep</span></span>

<span data-ttu-id="b7196-194">このコマンドレットが、集計されたストリームデータを受け取った後でもシステムに保存することを示します。</span><span class="sxs-lookup"><span data-stu-id="b7196-194">Indicates that this cmdlet saves the aggregated stream data in the system, even after you have received them.</span></span> <span data-ttu-id="b7196-195">既定では、を使用して表示した後、集計ストリームデータは消去され `Receive-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="b7196-195">By default, aggregated stream data is erased after viewed with `Receive-Job`.</span></span>

<span data-ttu-id="b7196-196">セッションを閉じるか、コマンドレットを使用してジョブを削除すると、 `Remove-Job` 集計されたストリームデータも削除されます。</span><span class="sxs-lookup"><span data-stu-id="b7196-196">Closing the session, or removing the job with the `Remove-Job` cmdlet also deletes aggregated stream data.</span></span>

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

### <span data-ttu-id="b7196-197">-Location</span><span class="sxs-lookup"><span data-stu-id="b7196-197">-Location</span></span>

<span data-ttu-id="b7196-198">場所の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7196-198">Specifies an array of locations.</span></span>
<span data-ttu-id="b7196-199">このコマンドレットは、指定された場所にあるジョブの結果のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="b7196-199">This cmdlet gets only the results of jobs in the specified locations.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: 1
Default value: All locations
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b7196-200">-Name</span><span class="sxs-lookup"><span data-stu-id="b7196-200">-Name</span></span>

<span data-ttu-id="b7196-201">フレンドリ名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7196-201">Specifies an array of friendly names.</span></span>
<span data-ttu-id="b7196-202">このコマンドレットは、指定された名前を持つジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="b7196-202">This cmdlet gets the results of jobs that have the specified names.</span></span>
<span data-ttu-id="b7196-203">ワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b7196-203">Wildcard characters are supported.</span></span>

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

### <span data-ttu-id="b7196-204">-NoRecurse</span><span class="sxs-lookup"><span data-stu-id="b7196-204">-NoRecurse</span></span>

<span data-ttu-id="b7196-205">このコマンドレットが、指定されたジョブからのみ結果を取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="b7196-205">Indicates that this cmdlet gets results only from the specified job.</span></span>
<span data-ttu-id="b7196-206">既定では、は、 `Receive-Job` 指定されたジョブのすべての子ジョブの結果も取得します。</span><span class="sxs-lookup"><span data-stu-id="b7196-206">By default, `Receive-Job` also gets the results of all child jobs of the specified job.</span></span>

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

### <span data-ttu-id="b7196-207">-セッション</span><span class="sxs-lookup"><span data-stu-id="b7196-207">-Session</span></span>

<span data-ttu-id="b7196-208">セッションの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7196-208">Specifies an array of sessions.</span></span>
<span data-ttu-id="b7196-209">このコマンドレットは、指定された PowerShell セッション ( **PSSession** ) で実行されたジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="b7196-209">This cmdlet gets the results of jobs that were run in the specified PowerShell session ( **PSSession** ).</span></span>
<span data-ttu-id="b7196-210">**Pssession** を含む変数、またはコマンドなどの **pssession** を取得するコマンドを入力し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="b7196-210">Enter a variable that contains the **PSSession** or a command that gets the **PSSession** , such as a `Get-PSSession` command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: False
Position: 1
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b7196-211">-Wait</span><span class="sxs-lookup"><span data-stu-id="b7196-211">-Wait</span></span>

<span data-ttu-id="b7196-212">すべてのジョブの結果を受信するまでコマンドプロンプトが表示されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="b7196-212">Indicates that this cmdlet suppresses the command prompt until all job results are received.</span></span>
<span data-ttu-id="b7196-213">既定では、は `Receive-Job` 使用可能な結果を直ちに返します。</span><span class="sxs-lookup"><span data-stu-id="b7196-213">By default, `Receive-Job` immediately returns the available results.</span></span>

<span data-ttu-id="b7196-214">既定では、 **Wait** パラメーターは、ジョブが次のいずれかの状態になるまで待機します:</span><span class="sxs-lookup"><span data-stu-id="b7196-214">By default, the **Wait** parameter waits until the job is in one of the following states:</span></span>

- <span data-ttu-id="b7196-215">完了</span><span class="sxs-lookup"><span data-stu-id="b7196-215">Completed</span></span>
- <span data-ttu-id="b7196-216">失敗</span><span class="sxs-lookup"><span data-stu-id="b7196-216">Failed</span></span>
- <span data-ttu-id="b7196-217">停止済み</span><span class="sxs-lookup"><span data-stu-id="b7196-217">Stopped</span></span>
- <span data-ttu-id="b7196-218">Suspended</span><span class="sxs-lookup"><span data-stu-id="b7196-218">Suspended</span></span>
- <span data-ttu-id="b7196-219">[接続解除されました。]</span><span class="sxs-lookup"><span data-stu-id="b7196-219">Disconnected.</span></span>

<span data-ttu-id="b7196-220">ジョブの状態が中断または切断された場合に待機するように **待機** パラメーターを指定するには、 **wait** パラメーターと共に **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b7196-220">To direct the **Wait** parameter to continue waiting if the job state is Suspended or Disconnected, use the **Force** parameter together with the **Wait** parameter.</span></span>

<span data-ttu-id="b7196-221">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b7196-221">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="b7196-222">-WriteEvents</span><span class="sxs-lookup"><span data-stu-id="b7196-222">-WriteEvents</span></span>

<span data-ttu-id="b7196-223">このコマンドレットがジョブの完了を待機している間に、ジョブの状態の変化を報告することを示します。</span><span class="sxs-lookup"><span data-stu-id="b7196-223">Indicates that this cmdlet reports changes in the job state while it waits for the job to finish.</span></span>

<span data-ttu-id="b7196-224">このパラメーターは、 **Wait** パラメーターがこのコマンドで使用され、 **Keep** パラメーターが省略される場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="b7196-224">This parameter is valid only when the **Wait** parameter is used in the command and the **Keep** parameter is omitted.</span></span>

<span data-ttu-id="b7196-225">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b7196-225">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="b7196-226">-WriteJobInResults</span><span class="sxs-lookup"><span data-stu-id="b7196-226">-WriteJobInResults</span></span>

<span data-ttu-id="b7196-227">このコマンドレットによってジョブオブジェクトが返され、その後に結果が返されることを示します。</span><span class="sxs-lookup"><span data-stu-id="b7196-227">Indicates that this cmdlet returns the job object followed by the results.</span></span>

<span data-ttu-id="b7196-228">このパラメーターは、 **Wait** パラメーターがこのコマンドで使用され、 **Keep** パラメーターが省略される場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="b7196-228">This parameter is valid only when the **Wait** parameter is used in the command and the **Keep** parameter is omitted.</span></span>

<span data-ttu-id="b7196-229">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b7196-229">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="b7196-230">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b7196-230">CommonParameters</span></span>

<span data-ttu-id="b7196-231">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b7196-231">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b7196-232">詳細については、「[about_CommonParameters](./About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7196-232">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b7196-233">入力</span><span class="sxs-lookup"><span data-stu-id="b7196-233">INPUTS</span></span>

### <span data-ttu-id="b7196-234">システム管理. ジョブ</span><span class="sxs-lookup"><span data-stu-id="b7196-234">System.Management.Automation.Job</span></span>

<span data-ttu-id="b7196-235">パイプを使用してジョブオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="b7196-235">You can pipe job objects to this cmdlet.</span></span>

## <span data-ttu-id="b7196-236">出力</span><span class="sxs-lookup"><span data-stu-id="b7196-236">OUTPUTS</span></span>

### <span data-ttu-id="b7196-237">PSObject</span><span class="sxs-lookup"><span data-stu-id="b7196-237">PSObject</span></span>

<span data-ttu-id="b7196-238">このコマンドレットは、ジョブのコマンドの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="b7196-238">This cmdlet returns the results of the commands in the job.</span></span>

## <span data-ttu-id="b7196-239">注</span><span class="sxs-lookup"><span data-stu-id="b7196-239">NOTES</span></span>

## <span data-ttu-id="b7196-240">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b7196-240">RELATED LINKS</span></span>

[<span data-ttu-id="b7196-241">Get-Job</span><span class="sxs-lookup"><span data-stu-id="b7196-241">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="b7196-242">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="b7196-242">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="b7196-243">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="b7196-243">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="b7196-244">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="b7196-244">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="b7196-245">Start-Job</span><span class="sxs-lookup"><span data-stu-id="b7196-245">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="b7196-246">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="b7196-246">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="b7196-247">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="b7196-247">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="b7196-248">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="b7196-248">Wait-Job</span></span>](Wait-Job.md)
