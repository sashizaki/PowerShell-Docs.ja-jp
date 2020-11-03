---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/start-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Job
ms.openlocfilehash: 7875419bed68251628b072a35d6c220e75b78c24
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212472"
---
# <span data-ttu-id="93526-103">Start-Job</span><span class="sxs-lookup"><span data-stu-id="93526-103">Start-Job</span></span>

## <span data-ttu-id="93526-104">概要</span><span class="sxs-lookup"><span data-stu-id="93526-104">SYNOPSIS</span></span>
<span data-ttu-id="93526-105">PowerShell バックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="93526-105">Starts a PowerShell background job.</span></span>

## <span data-ttu-id="93526-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="93526-106">SYNTAX</span></span>

### <span data-ttu-id="93526-107">ComputerName (既定値)</span><span class="sxs-lookup"><span data-stu-id="93526-107">ComputerName (Default)</span></span>

```
Start-Job [-Name <String>] [-ScriptBlock] <ScriptBlock> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="93526-108">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="93526-108">DefinitionName</span></span>

```
Start-Job [-DefinitionName] <String> [[-DefinitionPath] <String>] [[-Type] <String>]
 [-WorkingDirectory <String>] [<CommonParameters>]
```

### <span data-ttu-id="93526-109">FilePathComputerName</span><span class="sxs-lookup"><span data-stu-id="93526-109">FilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] [-FilePath] <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="93526-110">LiteralFilePathComputerName</span><span class="sxs-lookup"><span data-stu-id="93526-110">LiteralFilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] -LiteralPath <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="93526-111">Description</span><span class="sxs-lookup"><span data-stu-id="93526-111">DESCRIPTION</span></span>

<span data-ttu-id="93526-112">コマンドレットにより、 `Start-Job` ローカルコンピューターで PowerShell バックグラウンドジョブが開始されます。</span><span class="sxs-lookup"><span data-stu-id="93526-112">The `Start-Job` cmdlet starts a PowerShell background job on the local computer.</span></span>

<span data-ttu-id="93526-113">PowerShell バックグラウンドジョブは、現在のセッションと対話せずにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="93526-113">A PowerShell background job runs a command without interacting with the current session.</span></span> <span data-ttu-id="93526-114">バックグラウンドジョブを開始すると、ジョブの完了に時間がかかる場合でも、ジョブオブジェクトは直ちに返されます。</span><span class="sxs-lookup"><span data-stu-id="93526-114">When you start a background job, a job object returns immediately, even if the job takes an extended time to finish.</span></span> <span data-ttu-id="93526-115">ジョブの実行中は、中断されることなく引き続きセッションで作業できます。</span><span class="sxs-lookup"><span data-stu-id="93526-115">You can continue to work in the session without interruption while the job runs.</span></span>

<span data-ttu-id="93526-116">ジョブオブジェクトには、ジョブに関する有用な情報が含まれていますが、ジョブの結果は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="93526-116">The job object contains useful information about the job, but it doesn't contain the job results.</span></span>
<span data-ttu-id="93526-117">ジョブが完了したら、コマンドレットを使用して `Receive-Job` ジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="93526-117">When the job finishes, use the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="93526-118">バックグラウンド ジョブの詳細については、「[about_Jobs](./About/about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93526-118">For more information about background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="93526-119">リモートコンピューターでバックグラウンドジョブを実行するには、多くのコマンドレットで使用できる **AsJob** パラメーターを使用するか、コマンドレットを使用して `Invoke-Command` `Start-Job` リモートコンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="93526-119">To run a background job on a remote computer, use the **AsJob** parameter that is available on many cmdlets, or use the `Invoke-Command` cmdlet to run a `Start-Job` command on the remote computer.</span></span> <span data-ttu-id="93526-120">詳細については、「 [about_Remote_Jobs](./About/about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93526-120">For more information, see [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span></span>

<span data-ttu-id="93526-121">PowerShell 3.0 以降では、 `Start-Job` スケジュールされたジョブなど、カスタムのジョブの種類のインスタンスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="93526-121">Starting in PowerShell 3.0, `Start-Job` can start instances of custom job types, such as scheduled jobs.</span></span> <span data-ttu-id="93526-122">を使用してカスタム型のジョブを開始する方法の詳細については、 `Start-Job` ジョブの種類の機能に関するヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="93526-122">For information about how to use `Start-Job` to start jobs with custom types, see the help documents for the job type feature.</span></span>

<span data-ttu-id="93526-123">PowerShell 6.0 以降では、アンパサンド () のバックグラウンド操作を使用してジョブを開始でき `&` ます。</span><span class="sxs-lookup"><span data-stu-id="93526-123">Beginning in PowerShell 6.0, you can start jobs using the ampersand (`&`) background operator.</span></span> <span data-ttu-id="93526-124">Background 演算子の機能は、に似てい `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="93526-124">The functionality of the background operator is similar to `Start-Job`.</span></span> <span data-ttu-id="93526-125">ジョブを開始する2つの方法では、 **Psremotingjob** ジョブオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="93526-125">Both methods to start a job create a **PSRemotingJob** job object.</span></span> <span data-ttu-id="93526-126">アンパサンド () の使用の詳細については `&` 、「 [about_Operators](./about/about_operators.md#background-operator-)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93526-126">For more information about using the ampersand (`&`), see [about_Operators](./about/about_operators.md#background-operator-).</span></span>

<span data-ttu-id="93526-127">PowerShell 7 では、バックグラウンドジョブの初期作業ディレクトリを指定する **WorkingDirectory** パラメーターが導入されました。</span><span class="sxs-lookup"><span data-stu-id="93526-127">PowerShell 7 introduced the **WorkingDirectory** parameter that specifies a background job's initial working directory.</span></span> <span data-ttu-id="93526-128">パラメーターを指定しない場合、既定では、 `Start-Job` ジョブを開始した呼び出し元の現在の作業ディレクトリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="93526-128">If the parameter isn't specified, `Start-Job` defaults to the current working directory of the caller that started the job.</span></span>

> [!NOTE]
> <span data-ttu-id="93526-129">Powershell Azure Functions など、powershell が他のアプリケーションでホストされているシナリオでは、を使用してアウトプロセスのバックグラウンドジョブを作成する `Start-Job` ことはできません。</span><span class="sxs-lookup"><span data-stu-id="93526-129">Creating an out-of-process background job with `Start-Job` is not supported in the scenario where PowerShell is being hosted in other applications, such as the PowerShell Azure Functions.</span></span>
>
> <span data-ttu-id="93526-130">これは仕様です。これは、 `Start-Job` `pwsh` プロセス外のバックグラウンドジョブを開始するために、で使用できる実行可能ファイルに依存して `$PSHOME` いますが、アプリケーションが powershell をホストしている場合は、powershell NuGet SDK パッケージを直接使用しており、配布されていないためです `pwsh` 。</span><span class="sxs-lookup"><span data-stu-id="93526-130">This is by design because `Start-Job` depends on the `pwsh` executable to be available under `$PSHOME` to start an out-of-process background job, but when an application is hosting PowerShell, it's directly using the PowerShell NuGet SDK packages and won't have `pwsh` shipped along.</span></span>
>
> <span data-ttu-id="93526-131">このシナリオでの代替は、 `Start-ThreadJob` モジュール **[threadjob](https://www.powershellgallery.com/packages/ThreadJob)** からのものです。</span><span class="sxs-lookup"><span data-stu-id="93526-131">The substitute in that scenario is `Start-ThreadJob` from the module **[ThreadJob](https://www.powershellgallery.com/packages/ThreadJob)** .</span></span>

## <span data-ttu-id="93526-132">例</span><span class="sxs-lookup"><span data-stu-id="93526-132">EXAMPLES</span></span>

### <span data-ttu-id="93526-133">例 1: バックグラウンドジョブを開始する</span><span class="sxs-lookup"><span data-stu-id="93526-133">Example 1: Start a background job</span></span>

<span data-ttu-id="93526-134">この例では、ローカルコンピューターで実行されるバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="93526-134">This example starts a background job that runs on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name pwsh }
```

```Output
Id  Name   PSJobTypeName   State     HasMoreData   Location    Command
--  ----   -------------   -----     -----------   --------    -------
1   Job1   BackgroundJob   Running   True          localhost   Get-Process -Name pwsh
```

<span data-ttu-id="93526-135">`Start-Job`**ScriptBlock** パラメーターを使用し `Get-Process` て、バックグラウンドジョブとして実行します。</span><span class="sxs-lookup"><span data-stu-id="93526-135">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Process` as a background job.</span></span> <span data-ttu-id="93526-136">**Name** パラメーターは、PowerShell プロセスを検索するように指定し `pwsh` ます。</span><span class="sxs-lookup"><span data-stu-id="93526-136">The **Name** parameter specifies to find PowerShell processes, `pwsh`.</span></span> <span data-ttu-id="93526-137">ジョブ情報が表示され、ジョブがバックグラウンドで実行されている間、PowerShell がプロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="93526-137">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="93526-138">ジョブの出力を表示するには、 `Receive-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="93526-138">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="93526-139">たとえば、「 `Receive-Job -Id 1` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="93526-139">For example, `Receive-Job -Id 1`.</span></span>

### <span data-ttu-id="93526-140">例 2: バックグラウンドオペレーターを使用してバックグラウンドジョブを開始する</span><span class="sxs-lookup"><span data-stu-id="93526-140">Example 2: Use the background operator to start a background job</span></span>

<span data-ttu-id="93526-141">この例では、アンパサンド ( `&` ) バックグラウンド演算子を使用して、ローカルコンピューター上でバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="93526-141">This example uses the ampersand (`&`) background operator to start a background job on the local computer.</span></span> <span data-ttu-id="93526-142">このジョブは、例1の場合と同じ結果を取得し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="93526-142">The job gets the same result as `Start-Job` in Example 1.</span></span>

```powershell
Get-Process -Name pwsh &
```

```Output
Id    Name   PSJobTypeName   State       HasMoreData     Location      Command
--    ----   -------------   -----       -----------     --------      -------
5     Job5   BackgroundJob   Running     True            localhost     Microsoft.PowerShell.Man...
```

<span data-ttu-id="93526-143">`Get-Process`**Name** パラメーターを使用して、PowerShell プロセスを指定し `pwsh` ます。</span><span class="sxs-lookup"><span data-stu-id="93526-143">`Get-Process` uses the **Name** parameter to specify PowerShell processes, `pwsh`.</span></span> <span data-ttu-id="93526-144">アンパサンド () は、 `&` バックグラウンドジョブとしてコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="93526-144">The ampersand (`&`) runs the command as a background job.</span></span> <span data-ttu-id="93526-145">ジョブ情報が表示され、ジョブがバックグラウンドで実行されている間、PowerShell がプロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="93526-145">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="93526-146">ジョブの出力を表示するには、 `Receive-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="93526-146">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="93526-147">たとえば、「 `Receive-Job -Id 5` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="93526-147">For example, `Receive-Job -Id 5`.</span></span>

### <span data-ttu-id="93526-148">例 3: Invoke-Command を使用してジョブを開始する</span><span class="sxs-lookup"><span data-stu-id="93526-148">Example 3: Start a job using Invoke-Command</span></span>

<span data-ttu-id="93526-149">この例では、複数のコンピューターでジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="93526-149">This example runs a job on multiple computers.</span></span> <span data-ttu-id="93526-150">ジョブは変数に格納され、PowerShell コマンドラインで変数名を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="93526-150">The job is stored in a variable and is executed by using the variable name on the PowerShell command line.</span></span>

```powershell
$jobWRM = Invoke-Command -ComputerName (Get-Content -Path C:\Servers.txt) -ScriptBlock {
   Get-Service -Name WinRM } -JobName WinRM -ThrottleLimit 16 -AsJob
```

<span data-ttu-id="93526-151">を使用するジョブ `Invoke-Command` が作成され、変数に格納され `$jobWRM` ます。</span><span class="sxs-lookup"><span data-stu-id="93526-151">A job that uses `Invoke-Command` is created and stored in the `$jobWRM` variable.</span></span> <span data-ttu-id="93526-152">`Invoke-Command`**ComputerName** パラメーターを使用して、ジョブを実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-152">`Invoke-Command` uses the **ComputerName** parameter to specify the computers where the job runs.</span></span> <span data-ttu-id="93526-153">`Get-Content` ファイルからサーバー名を取得し `C:\Servers.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="93526-153">`Get-Content` gets the server names from the `C:\Servers.txt` file.</span></span>

<span data-ttu-id="93526-154">**ScriptBlock** パラメーターは、WinRM サービスを取得するコマンドを指定し `Get-Service` ます。 **WinRM**</span><span class="sxs-lookup"><span data-stu-id="93526-154">The **ScriptBlock** parameter specifies a command that `Get-Service` gets the **WinRM** service.</span></span> <span data-ttu-id="93526-155">**JobName** パラメーターは、ジョブのフレンドリ名を指定します ( **WinRM** )。</span><span class="sxs-lookup"><span data-stu-id="93526-155">The **JobName** parameter specifies a friendly name for the job, **WinRM** .</span></span> <span data-ttu-id="93526-156">**ThrottleLimit** パラメーターは、同時実行コマンドの数を16に制限します。</span><span class="sxs-lookup"><span data-stu-id="93526-156">The **ThrottleLimit** parameter limits the number of concurrent commands to 16.</span></span> <span data-ttu-id="93526-157">**AsJob** パラメーターは、サーバーでコマンドを実行するバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="93526-157">The **AsJob** parameter starts a background job that runs the command on the servers.</span></span>

### <span data-ttu-id="93526-158">例 4: ジョブ情報を取得する</span><span class="sxs-lookup"><span data-stu-id="93526-158">Example 4: Get job information</span></span>

<span data-ttu-id="93526-159">この例では、ジョブに関する情報を取得し、ローカルコンピューターで実行された完了したジョブの結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="93526-159">This example gets information about a job and displays the results of a completed job that was run on the local computer.</span></span>

```powershell
$j = Start-Job -ScriptBlock { Get-WinEvent -Log System } -Credential Domain01\User01
$j | Select-Object -Property *
```

```Output
State         : Completed
HasMoreData   : True
StatusMessage :
Location      : localhost
Command       : Get-WinEvent -Log System
JobStateInfo  : Completed
Finished      : System.Threading.ManualResetEvent
InstanceId    : 27ce3fd9-40ed-488a-99e5-679cd91b9dd3
Id            : 18
Name          : Job18
ChildJobs     : {Job19}
PSBeginTime   : 8/8/2019 14:41:57
PSEndTime     : 8/8/2019 14:42:07
PSJobTypeName : BackgroundJob
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
```

<span data-ttu-id="93526-160">`Start-Job`**ScriptBlock** パラメーターを使用して、 `Get-WinEvent` **システム** ログを取得するように指定したコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="93526-160">`Start-Job` uses the **ScriptBlock** parameter to run a command that specifies `Get-WinEvent` to get the **System** log.</span></span> <span data-ttu-id="93526-161">**Credential** パラメーターには、コンピューター上でジョブを実行するアクセス許可を持つドメインユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-161">The **Credential** parameter specifies a domain user account with permission to run the job on the computer.</span></span> <span data-ttu-id="93526-162">ジョブオブジェクトは変数に格納され `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="93526-162">The job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="93526-163">変数内のオブジェクト `$j` は、パイプラインの下にに送信され `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="93526-163">The object in the `$j` variable is sent down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="93526-164">**Property** パラメーターは、 `*` すべてのジョブオブジェクトのプロパティを表示するアスタリスク () を指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-164">The **Property** parameter specifies an asterisk (`*`) to display all the job object's properties.</span></span>

### <span data-ttu-id="93526-165">例 5: バックグラウンドジョブとしてスクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="93526-165">Example 5: Run a script as a background job</span></span>

<span data-ttu-id="93526-166">この例では、ローカルコンピューター上のスクリプトがバックグラウンドジョブとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="93526-166">In this example, a script on the local computer is run as a background job.</span></span>

```powershell
Start-Job -FilePath C:\Scripts\Sample.ps1
```

<span data-ttu-id="93526-167">`Start-Job`**FilePath** パラメーターを使用して、ローカルコンピューターに格納されているスクリプトファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-167">`Start-Job` uses the **FilePath** parameter to specify a script file that's stored on the local computer.</span></span>

### <span data-ttu-id="93526-168">例 6: バックグラウンドジョブを使用してプロセスを取得する</span><span class="sxs-lookup"><span data-stu-id="93526-168">Example 6: Get a process using a background job</span></span>

<span data-ttu-id="93526-169">この例では、バックグラウンドジョブを使用して、指定されたプロセスを名前で取得します。</span><span class="sxs-lookup"><span data-stu-id="93526-169">This example uses a background job to get a specified process by name.</span></span>

```powershell
Start-Job -Name PShellJob -ScriptBlock { Get-Process -Name PowerShell }
```

<span data-ttu-id="93526-170">`Start-Job`**Name** パラメーターを使用して、わかりやすいジョブ名 **pshelljob** を指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-170">`Start-Job` uses the **Name** parameter to specify a friendly job name, **PShellJob** .</span></span> <span data-ttu-id="93526-171">**ScriptBlock** パラメーターは、 `Get-Process` **PowerShell** という名前のプロセスを取得するように指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-171">The **ScriptBlock** parameter specifies `Get-Process` to get processes with the name **PowerShell** .</span></span>

### <span data-ttu-id="93526-172">例 7: バックグラウンドジョブを使用してデータを収集して保存する</span><span class="sxs-lookup"><span data-stu-id="93526-172">Example 7: Collect and save data by using a background job</span></span>

<span data-ttu-id="93526-173">この例では、大量のマップデータを収集してファイルに保存するジョブを開始し `.tif` ます。</span><span class="sxs-lookup"><span data-stu-id="93526-173">This example starts a job that collects a large amount of map data and then saves it in a `.tif` file.</span></span>

```powershell
Start-Job -Name GetMappingFiles -InitializationScript {Import-Module MapFunctions} -ScriptBlock {
   Get-Map -Name * | Set-Content -Path D:\Maps.tif }
```

<span data-ttu-id="93526-174">`Start-Job`**Name** パラメーターを使用して、わかりやすいジョブ名である **getmappingfiles** を指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-174">`Start-Job` uses the **Name** parameter to specify a friendly job name, **GetMappingFiles** .</span></span> <span data-ttu-id="93526-175">**InitializationScript** パラメーターは、 **mapfunctions** モジュールをインポートするスクリプトブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="93526-175">The **InitializationScript** parameter runs a script block that imports the **MapFunctions** module.</span></span> <span data-ttu-id="93526-176">**ScriptBlock** パラメーターは、 `Get-Map` `Set-Content` **Path** パラメーターによって指定された場所にデータを実行して保存します。</span><span class="sxs-lookup"><span data-stu-id="93526-176">The **ScriptBlock** parameter runs `Get-Map` and `Set-Content` saves the data in the location specified by the **Path** parameter.</span></span>

### <span data-ttu-id="93526-177">例 8: バックグラウンドジョブに入力を渡す</span><span class="sxs-lookup"><span data-stu-id="93526-177">Example 8: Pass input to a background job</span></span>

<span data-ttu-id="93526-178">この例では、 `$input` 自動変数を使用して入力オブジェクトを処理します。</span><span class="sxs-lookup"><span data-stu-id="93526-178">This example uses the `$input` automatic variable to process an input object.</span></span> <span data-ttu-id="93526-179">`Receive-Job`ジョブの出力を表示するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="93526-179">Use `Receive-Job` to view the job's output.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Content $input } -InputObject "C:\Servers.txt"
Receive-Job -Name Job45 -Keep
```

```Output
Server01
Server02
Server03
Server04
```

<span data-ttu-id="93526-180">`Start-Job`**ScriptBlock** パラメーターを使用し `Get-Content` て、自動変数を指定して実行し `$input` ます。</span><span class="sxs-lookup"><span data-stu-id="93526-180">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Content` with the `$input` automatic variable.</span></span> <span data-ttu-id="93526-181">`$input`変数は **InputObject** パラメーターからオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="93526-181">The `$input` variable gets objects from the **InputObject** parameter.</span></span> <span data-ttu-id="93526-182">`Receive-Job`**Name** パラメーターを使用してジョブを指定し、結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="93526-182">`Receive-Job` uses the **Name** parameter to specify the job and outputs the results.</span></span> <span data-ttu-id="93526-183">**Keep** パラメーターを指定すると、ジョブの出力が保存され、PowerShell セッション中に再度表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="93526-183">The **Keep** parameter saves the job output so it can be viewed again during the PowerShell session.</span></span>

### <span data-ttu-id="93526-184">例 9: バックグラウンドジョブの作業ディレクトリを設定する</span><span class="sxs-lookup"><span data-stu-id="93526-184">Example 9: Set the working directory for a background job</span></span>

<span data-ttu-id="93526-185">**WorkingDirectory** を使用すると、スクリプトまたは開いているファイルを実行できるジョブの代替ディレクトリを指定できます。</span><span class="sxs-lookup"><span data-stu-id="93526-185">The **WorkingDirectory** allows you to specify an alternate directory for a job from which you can run scripts or open files.</span></span> <span data-ttu-id="93526-186">この例では、バックグラウンドジョブは、現在のディレクトリの場所とは異なる作業ディレクトリを指定しています。</span><span class="sxs-lookup"><span data-stu-id="93526-186">In this example, the background job specifies a working directory that's different than the current directory location.</span></span>

```
PS C:\Test> Start-Job -WorkingDirectory C:\Test\Scripts { $PWD } | Receive-Job -AutoRemoveJob -Wait

Path
----
C:\Test\Scripts
```

<span data-ttu-id="93526-187">この例の現在の作業ディレクトリは `C:\Test` です。</span><span class="sxs-lookup"><span data-stu-id="93526-187">This example's current working directory is `C:\Test`.</span></span> <span data-ttu-id="93526-188">`Start-Job`**WorkingDirectory** パラメーターを使用して、ジョブの作業ディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-188">`Start-Job` uses the **WorkingDirectory** parameter to specify the job's working directory.</span></span> <span data-ttu-id="93526-189">**ScriptBlock** パラメーターは、 `$PWD` を使用してジョブの作業ディレクトリを表示します。</span><span class="sxs-lookup"><span data-stu-id="93526-189">The **ScriptBlock** parameter uses `$PWD` to display the job's working directory.</span></span> <span data-ttu-id="93526-190">`Receive-Job` バックグラウンドジョブの出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="93526-190">`Receive-Job` displays the background job's output.</span></span>
<span data-ttu-id="93526-191">**AutoRemoveJob** はジョブを削除し、 **待機** すると、すべての結果が受信されるまでコマンドプロンプトが抑制されます。</span><span class="sxs-lookup"><span data-stu-id="93526-191">**AutoRemoveJob** deletes the job and **Wait** suppresses the command prompt until all results are received.</span></span>

### <span data-ttu-id="93526-192">例 10: ArgumentList パラメーターを使用して配列を指定する</span><span class="sxs-lookup"><span data-stu-id="93526-192">Example 10: Use the ArgumentList parameter to specify an array</span></span>

<span data-ttu-id="93526-193">この例では、 **ArgumentList** パラメーターを使用して、引数の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-193">This example uses the **ArgumentList** parameter to specify an array of arguments.</span></span> <span data-ttu-id="93526-194">配列は、プロセス名のコンマ区切りのリストです。</span><span class="sxs-lookup"><span data-stu-id="93526-194">The array is a comma-separated list of process names.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name $args } -ArgumentList powershell, pwsh, notepad
```

```Output
Id     Name      PSJobTypeName   State       HasMoreData     Location     Command
--     ----      -------------   -----       -----------     --------     -------
1      Job1      BackgroundJob   Running     True            localhost    Get-Process -Name $args
```

<span data-ttu-id="93526-195">コマンドレットでは、 `Start-Job` **ScriptBlock** パラメーターを使用してコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="93526-195">The `Start-Job` cmdlet uses the **ScriptBlock** parameter to run a command.</span></span> <span data-ttu-id="93526-196">`Get-Process`**Name** パラメーターを使用して、自動変数を指定し `$args` ます。</span><span class="sxs-lookup"><span data-stu-id="93526-196">`Get-Process` uses the **Name** parameter to specify the automatic variable `$args`.</span></span> <span data-ttu-id="93526-197">**ArgumentList** パラメーターは、プロセス名の配列をに渡し `$args` ます。</span><span class="sxs-lookup"><span data-stu-id="93526-197">The **ArgumentList** parameter passes the array of process names to `$args`.</span></span> <span data-ttu-id="93526-198">このプロセス名は、ローカルコンピューター上で実行されているプロセスです。</span><span class="sxs-lookup"><span data-stu-id="93526-198">The process names powershell, pwsh, and notepad are processes running on the local computer.</span></span>

<span data-ttu-id="93526-199">ジョブの出力を表示するには、 `Receive-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="93526-199">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="93526-200">たとえば、「 `Receive-Job -Id 1` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="93526-200">For example, `Receive-Job -Id 1`.</span></span>

### <span data-ttu-id="93526-201">例 11: Windows PowerShell 5.1 でジョブを実行する</span><span class="sxs-lookup"><span data-stu-id="93526-201">Example 11: Run job in a Windows PowerShell 5.1</span></span>

<span data-ttu-id="93526-202">この例では、値が **5.1** の **psversion** パラメーターを使用して、Windows PowerShell 5.1 セッションでジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="93526-202">This example uses the **PSVersion** parameter with value **5.1** to run job in a Windows PowerShell 5.1 session.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Patch  PreReleaseLabel BuildLabel
-----  -----  -----  --------------- ----------
7      0      0      rc.1
```

```powershell
$job = Start-Job { $PSVersionTable.PSVersion } -PSVersion 5.1
Receive-Job $job
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  3383
```

## <span data-ttu-id="93526-203">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="93526-203">PARAMETERS</span></span>

### <span data-ttu-id="93526-204">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="93526-204">-ArgumentList</span></span>

<span data-ttu-id="93526-205">**FilePath** パラメーターで指定されたスクリプト、または **ScriptBlock** パラメーターで指定されたコマンドで指定されたスクリプトの引数またはパラメーター値の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-205">Specifies an array of arguments, or parameter values, for the script that is specified by the **FilePath** parameter or a command specified with the **ScriptBlock** parameter.</span></span>

<span data-ttu-id="93526-206">引数は、1次元の配列引数として **ArgumentList** に渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="93526-206">Arguments must be passed to **ArgumentList** as single-dimension array argument.</span></span> <span data-ttu-id="93526-207">たとえば、コンマ区切りのリストです。</span><span class="sxs-lookup"><span data-stu-id="93526-207">For example, a comma-separated list.</span></span> <span data-ttu-id="93526-208">**ArgumentList** の動作の詳細については、「 [about_Splatting](about/about_Splatting.md#splatting-with-arrays)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93526-208">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93526-209">-認証</span><span class="sxs-lookup"><span data-stu-id="93526-209">-Authentication</span></span>

<span data-ttu-id="93526-210">ユーザー資格情報の認証に使用するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-210">Specifies the mechanism that is used to authenticate user credentials.</span></span>

<span data-ttu-id="93526-211">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="93526-211">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="93526-212">Default</span><span class="sxs-lookup"><span data-stu-id="93526-212">Default</span></span>
- <span data-ttu-id="93526-213">Basic</span><span class="sxs-lookup"><span data-stu-id="93526-213">Basic</span></span>
- <span data-ttu-id="93526-214">Credssp</span><span class="sxs-lookup"><span data-stu-id="93526-214">Credssp</span></span>
- <span data-ttu-id="93526-215">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="93526-215">Digest</span></span>
- <span data-ttu-id="93526-216">Kerberos</span><span class="sxs-lookup"><span data-stu-id="93526-216">Kerberos</span></span>
- <span data-ttu-id="93526-217">ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="93526-217">Negotiate</span></span>
- <span data-ttu-id="93526-218">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="93526-218">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="93526-219">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="93526-219">The default value is Default.</span></span>

<span data-ttu-id="93526-220">CredSSP 認証は、windows Vista、Windows Server 2008、およびそれ以降のバージョンの Windows オペレーティングシステムでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="93526-220">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="93526-221">このパラメーターの値の詳細については、「 [Authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93526-221">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="93526-222">ユーザーの資格情報が認証対象のリモート コンピューターに渡される Credential Security Support Provider (CredSSP) 認証は、リモート ネットワーク共有にアクセスする場合など、複数のリソースの認証を必要とするコマンドを対象としています。</span><span class="sxs-lookup"><span data-stu-id="93526-222">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="93526-223">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="93526-223">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="93526-224">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="93526-224">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93526-225">-Credential</span><span class="sxs-lookup"><span data-stu-id="93526-225">-Credential</span></span>

<span data-ttu-id="93526-226">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-226">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="93526-227">**Credential** パラメーターが指定されていない場合、コマンドは現在のユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="93526-227">If the **Credential** parameter isn't specified, the command uses the current user's credentials.</span></span>

<span data-ttu-id="93526-228">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="93526-228">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="93526-229">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="93526-229">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="93526-230">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="93526-230">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="93526-231">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93526-231">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93526-232">-DefinitionName</span><span class="sxs-lookup"><span data-stu-id="93526-232">-DefinitionName</span></span>

<span data-ttu-id="93526-233">このコマンドレットが開始するジョブの定義名を指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-233">Specifies the definition name of the job that this cmdlet starts.</span></span> <span data-ttu-id="93526-234">このパラメーターは、スケジュールされたジョブのように定義名を持つカスタムのジョブを開始するために使用します。</span><span class="sxs-lookup"><span data-stu-id="93526-234">Use this parameter to start custom job types that have a definition name, such as scheduled jobs.</span></span>

<span data-ttu-id="93526-235">を使用し `Start-Job` てスケジュールされたジョブのインスタンスを開始すると、ジョブトリガーやジョブオプションに関係なく、ジョブは直ちに開始されます。</span><span class="sxs-lookup"><span data-stu-id="93526-235">When you use `Start-Job` to start an instance of a scheduled job, the job starts immediately, regardless of job triggers or job options.</span></span> <span data-ttu-id="93526-236">結果のジョブインスタンスはスケジュールされたジョブですが、スケジュールされたジョブのトリガーなどのディスクには保存されません。</span><span class="sxs-lookup"><span data-stu-id="93526-236">The resulting job instance is a scheduled job, but it isn't saved to disk like triggered scheduled jobs.</span></span> <span data-ttu-id="93526-237">の **ArgumentList** パラメーターを使用して、 `Start-Job` スケジュールされたジョブで実行されるスクリプトのパラメーターの値を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="93526-237">You can't use the **ArgumentList** parameter of `Start-Job` to provide values for parameters of scripts that run in a scheduled job.</span></span>

<span data-ttu-id="93526-238">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="93526-238">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93526-239">-DefinitionPath</span><span class="sxs-lookup"><span data-stu-id="93526-239">-DefinitionPath</span></span>

<span data-ttu-id="93526-240">このコマンドレットが開始するジョブの定義のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-240">Specifies path of the definition for the job that this cmdlet starts.</span></span> <span data-ttu-id="93526-241">定義のパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="93526-241">Enter the definition path.</span></span> <span data-ttu-id="93526-242">**Definitionpath** パラメーターと **definitionpath** パラメーターの値を連結したものは、ジョブ定義の完全修飾パスです。</span><span class="sxs-lookup"><span data-stu-id="93526-242">The concatenation of the values of the **DefinitionPath** and **DefinitionName** parameters is the fully qualified path of the job definition.</span></span> <span data-ttu-id="93526-243">このパラメーターは、スケジュールされたジョブのように定義パスを持つカスタムのジョブを開始するために使用します。</span><span class="sxs-lookup"><span data-stu-id="93526-243">Use this parameter to start custom job types that have a definition path, such as scheduled jobs.</span></span>

<span data-ttu-id="93526-244">スケジュールされたジョブの場合、 **Definitionpath** パラメーターの値は `$home\AppData\Local\Windows\PowerShell\ScheduledJob` です。</span><span class="sxs-lookup"><span data-stu-id="93526-244">For scheduled jobs, the value of the **DefinitionPath** parameter is `$home\AppData\Local\Windows\PowerShell\ScheduledJob`.</span></span>

<span data-ttu-id="93526-245">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="93526-245">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93526-246">-FilePath</span><span class="sxs-lookup"><span data-stu-id="93526-246">-FilePath</span></span>

<span data-ttu-id="93526-247">`Start-Job`バックグラウンドジョブとして実行するローカルスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-247">Specifies a local script that `Start-Job` runs as a background job.</span></span> <span data-ttu-id="93526-248">スクリプトのパスとファイル名を入力するか、パイプラインを使用してスクリプトパスを送信 `Start-Job` します。</span><span class="sxs-lookup"><span data-stu-id="93526-248">Enter the path and file name of the script or use the pipeline to send a script path to `Start-Job`.</span></span> <span data-ttu-id="93526-249">スクリプトは、ローカルコンピューター上、またはローカルコンピューターがアクセスできるフォルダー内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="93526-249">The script must be on the local computer or in a folder that the local computer can access.</span></span>

<span data-ttu-id="93526-250">このパラメーターを使用すると、PowerShell によって、指定したスクリプトファイルの内容がスクリプトブロックに変換され、バックグラウンドジョブとしてスクリプトブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="93526-250">When you use this parameter, PowerShell converts the contents of the specified script file to a script block and runs the script block as a background job.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathComputerName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93526-251">-InitializationScript</span><span class="sxs-lookup"><span data-stu-id="93526-251">-InitializationScript</span></span>

<span data-ttu-id="93526-252">ジョブの開始前に実行するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-252">Specifies commands that run before the job starts.</span></span> <span data-ttu-id="93526-253">スクリプトブロックを作成するには、コマンドを中かっこ ( `{}` ) で囲みます。</span><span class="sxs-lookup"><span data-stu-id="93526-253">To create a script block, enclose the commands in curly braces (`{}`).</span></span>

<span data-ttu-id="93526-254">このパラメーターは、ジョブを実行するセッションを準備するために使用します。</span><span class="sxs-lookup"><span data-stu-id="93526-254">Use this parameter to prepare the session in which the job runs.</span></span> <span data-ttu-id="93526-255">たとえば、このパラメーターを使用して、関数、スナップイン、モジュールをセッションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="93526-255">For example, you can use it to add functions, snap-ins, and modules to the session.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93526-256">-InputObject</span><span class="sxs-lookup"><span data-stu-id="93526-256">-InputObject</span></span>

<span data-ttu-id="93526-257">コマンドへの入力を指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-257">Specifies input to the command.</span></span> <span data-ttu-id="93526-258">オブジェクトが格納されている変数を入力するか、オブジェクトを生成するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="93526-258">Enter a variable that contains the objects, or type a command or expression that generates the objects.</span></span>

<span data-ttu-id="93526-259">**ScriptBlock** パラメーターの値で、自動変数を使用して `$input` 入力オブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="93526-259">In the value of the **ScriptBlock** parameter, use the `$input` automatic variable to represent the input objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="93526-260">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="93526-260">-LiteralPath</span></span>

<span data-ttu-id="93526-261">このコマンドレットをバックグラウンドジョブとして実行するローカルスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-261">Specifies a local script that this cmdlet runs as a background job.</span></span> <span data-ttu-id="93526-262">ローカルコンピューター上のスクリプトのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="93526-262">Enter the path of a script on the local computer.</span></span>

<span data-ttu-id="93526-263">`Start-Job`**LiteralPath** パラメーターの値を、型指定されたとおりに使用します。</span><span class="sxs-lookup"><span data-stu-id="93526-263">`Start-Job` uses the value of the **LiteralPath** parameter exactly as it's typed.</span></span> <span data-ttu-id="93526-264">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="93526-264">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="93526-265">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="93526-265">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="93526-266">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="93526-266">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralFilePathComputerName
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93526-267">-Name</span><span class="sxs-lookup"><span data-stu-id="93526-267">-Name</span></span>

<span data-ttu-id="93526-268">新しいジョブのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-268">Specifies a friendly name for the new job.</span></span> <span data-ttu-id="93526-269">この名前を使用して、コマンドレットなど、他のジョブコマンドレットに対してジョブを識別でき `Stop-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="93526-269">You can use the name to identify the job to other job cmdlets, such as the `Stop-Job` cmdlet.</span></span>

<span data-ttu-id="93526-270">既定の表示名はです `Job#` 。ここで、 `#` は、ジョブごとに増分される序数です。</span><span class="sxs-lookup"><span data-stu-id="93526-270">The default friendly name is `Job#`, where `#` is an ordinal number that is incremented for each job.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="93526-271">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="93526-271">-PSVersion</span></span>

<span data-ttu-id="93526-272">ジョブの実行に使用する PowerShell のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-272">Specifies a version of PowerShell to use for running the job.</span></span>
<span data-ttu-id="93526-273">**Psversion** の値が **5.1** の場合、ジョブは Windows PowerShell 5.1 セッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="93526-273">When the value of **PSVersion** is **5.1** The job is run in a Windows PowerShell 5.1 session.</span></span>
<span data-ttu-id="93526-274">その他の値については、現在のバージョンの PowerShell を使用してジョブが実行されます。</span><span class="sxs-lookup"><span data-stu-id="93526-274">For any other value, the job is run using the current version of PowerShell.</span></span>

<span data-ttu-id="93526-275">このパラメーターは、PowerShell 7 で追加され、Windows でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="93526-275">This parameter was added in PowerShell 7 and only works on Windows.</span></span>

```yaml
Type: System.Version
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93526-276">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="93526-276">-RunAs32</span></span>

<span data-ttu-id="93526-277">PowerShell 7 以降では、 **RunAs32** パラメーターは64ビットの powershell () では機能しません `pwsh` 。</span><span class="sxs-lookup"><span data-stu-id="93526-277">Beginning with PowerShell 7, the **RunAs32** parameter doesn't work on 64-bit PowerShell (`pwsh`).</span></span>
<span data-ttu-id="93526-278">64ビットの PowerShell で **RunAs32** が指定されている場合、は `Start-Job` 終了例外のエラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="93526-278">If **RunAs32** is specified in 64-bit PowerShell, `Start-Job` throws a terminating exception error.</span></span>
<span data-ttu-id="93526-279">RunAs32 で32ビットの PowerShell () プロセスを開始するには、 `pwsh` 32 ビットの powershell がインストールされている必要があります。 **RunAs32**</span><span class="sxs-lookup"><span data-stu-id="93526-279">To start a 32-bit PowerShell (`pwsh`) process with **RunAs32** , you need to have the 32-bit PowerShell installed.</span></span>

<span data-ttu-id="93526-280">32ビットの PowerShell では、 **RunAs32** は、64ビットのオペレーティングシステムであっても、32ビットプロセスでジョブを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="93526-280">In 32-bit PowerShell, **RunAs32** forces the job to run in a 32-bit process, even on a 64-bit operating system.</span></span>

<span data-ttu-id="93526-281">Windows 7 と Windows Server 2008 R2 の64ビットバージョンでは、コマンドに `Start-Job` **RunAs32** パラメーターが含まれている場合、 **Credential** パラメーターを使用して別のユーザーの資格情報を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="93526-281">On 64-bit versions of Windows 7 and Windows Server 2008 R2, when the `Start-Job` command includes the **RunAs32** parameter, you can't use the **Credential** parameter to specify the credentials of another user.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93526-282">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="93526-282">-ScriptBlock</span></span>

<span data-ttu-id="93526-283">バックグラウンド ジョブで実行するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-283">Specifies the commands to run in the background job.</span></span> <span data-ttu-id="93526-284">スクリプトブロックを作成するには、コマンドを中かっこ ( `{}` ) で囲みます。</span><span class="sxs-lookup"><span data-stu-id="93526-284">To create a script block, enclose the commands in curly braces (`{}`).</span></span> <span data-ttu-id="93526-285">`$input` **InputObject** パラメーターの値にアクセスするには、自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="93526-285">Use the `$input` automatic variable to access the value of the **InputObject** parameter.</span></span> <span data-ttu-id="93526-286">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="93526-286">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ComputerName
Aliases: Command

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93526-287">-Type</span><span class="sxs-lookup"><span data-stu-id="93526-287">-Type</span></span>

<span data-ttu-id="93526-288">によって開始されるジョブのカスタムの種類を指定し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="93526-288">Specifies the custom type for jobs started by `Start-Job`.</span></span> <span data-ttu-id="93526-289">カスタムのジョブの種類の名前を入力します (スケジュールされたジョブの場合は PSScheduledJob、ワークフロー ジョブの場合は PSWorkflowJob)。</span><span class="sxs-lookup"><span data-stu-id="93526-289">Enter a custom job type name, such as PSScheduledJob for scheduled jobs or PSWorkflowJob for workflows jobs.</span></span> <span data-ttu-id="93526-290">このパラメーターは、標準のバックグラウンドジョブでは無効です。</span><span class="sxs-lookup"><span data-stu-id="93526-290">This parameter isn't valid for standard background jobs.</span></span>

<span data-ttu-id="93526-291">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="93526-291">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93526-292">-WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="93526-292">-WorkingDirectory</span></span>

<span data-ttu-id="93526-293">バックグラウンドジョブの初期作業ディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="93526-293">Specifies the initial working directory of the background job.</span></span> <span data-ttu-id="93526-294">パラメーターが指定されていない場合、ジョブは既定の場所から実行されます。</span><span class="sxs-lookup"><span data-stu-id="93526-294">If the parameter isn't specified, the job runs from the default location.</span></span> <span data-ttu-id="93526-295">既定の場所は、ジョブを開始した呼び出し元の現在の作業ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="93526-295">The default location is the current working directory of the caller that started the job.</span></span>

<span data-ttu-id="93526-296">このパラメーターは、PowerShell 7 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="93526-296">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.String
Parameter Sets: All
Aliases:

Required: False
Position: Named
Default value: $HOME on Unix (macOS, Linux) and $HOME\Documents on Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="93526-297">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="93526-297">CommonParameters</span></span>

<span data-ttu-id="93526-298">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="93526-298">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="93526-299">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93526-299">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="93526-300">入力</span><span class="sxs-lookup"><span data-stu-id="93526-300">INPUTS</span></span>

### <span data-ttu-id="93526-301">System.String</span><span class="sxs-lookup"><span data-stu-id="93526-301">System.String</span></span>

<span data-ttu-id="93526-302">パイプラインを使用し **て、name プロパティを** 持つオブジェクトを **name** パラメーターに送信できます。</span><span class="sxs-lookup"><span data-stu-id="93526-302">You can use the pipeline to send an object with the **Name** property to the **Name** parameter.</span></span> <span data-ttu-id="93526-303">たとえば、 **FileInfo** オブジェクトをからにパイプラインでき `Get-ChildItem` `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="93526-303">For example, you can pipeline a **FileInfo** object from `Get-ChildItem` to `Start-Job`.</span></span>

## <span data-ttu-id="93526-304">出力</span><span class="sxs-lookup"><span data-stu-id="93526-304">OUTPUTS</span></span>

### <span data-ttu-id="93526-305">システムの管理. PSRemotingJob</span><span class="sxs-lookup"><span data-stu-id="93526-305">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="93526-306">`Start-Job` 開始したジョブを表す **Psremotingjob** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="93526-306">`Start-Job` returns a **PSRemotingJob** object that represents the job that it started.</span></span>

## <span data-ttu-id="93526-307">注</span><span class="sxs-lookup"><span data-stu-id="93526-307">NOTES</span></span>

<span data-ttu-id="93526-308">バックグラウンドでを実行するために、は、 `Start-Job` 現在のセッションで独自のセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="93526-308">To run in the background, `Start-Job` runs in its own session in the current session.</span></span> <span data-ttu-id="93526-309">コマンドレットを使用して `Invoke-Command` `Start-Job` リモートコンピューター上のセッションでコマンドを実行すると、は `Start-Job` リモートセッションのセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="93526-309">When you use the `Invoke-Command` cmdlet to run a `Start-Job` command in a session on a remote computer, `Start-Job` runs in a session in the remote session.</span></span>

## <span data-ttu-id="93526-310">関連リンク</span><span class="sxs-lookup"><span data-stu-id="93526-310">RELATED LINKS</span></span>

[<span data-ttu-id="93526-311">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="93526-311">about_Arrays</span></span>](./about/about_arrays.md)

[<span data-ttu-id="93526-312">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="93526-312">about_Automatic_Variables</span></span>](./about/about_automatic_variables.md)

[<span data-ttu-id="93526-313">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="93526-313">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="93526-314">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="93526-314">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="93526-315">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="93526-315">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="93526-316">Get-Job</span><span class="sxs-lookup"><span data-stu-id="93526-316">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="93526-317">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="93526-317">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="93526-318">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="93526-318">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="93526-319">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="93526-319">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="93526-320">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="93526-320">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="93526-321">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="93526-321">Wait-Job</span></span>](Wait-Job.md)
