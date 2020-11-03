---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/start-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Job
ms.openlocfilehash: 116e007cc28a91e3c97fd980cc27461932390b7c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212736"
---
# <span data-ttu-id="ab632-103">Start-Job</span><span class="sxs-lookup"><span data-stu-id="ab632-103">Start-Job</span></span>

## <span data-ttu-id="ab632-104">概要</span><span class="sxs-lookup"><span data-stu-id="ab632-104">SYNOPSIS</span></span>
<span data-ttu-id="ab632-105">PowerShell バックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="ab632-105">Starts a PowerShell background job.</span></span>

## <span data-ttu-id="ab632-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ab632-106">SYNTAX</span></span>

### <span data-ttu-id="ab632-107">ComputerName (既定値)</span><span class="sxs-lookup"><span data-stu-id="ab632-107">ComputerName (Default)</span></span>

```
Start-Job [-Name <String>] [-ScriptBlock] <ScriptBlock> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="ab632-108">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="ab632-108">DefinitionName</span></span>

```
Start-Job [-DefinitionName] <String> [[-DefinitionPath] <String>] [[-Type] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="ab632-109">FilePathComputerName</span><span class="sxs-lookup"><span data-stu-id="ab632-109">FilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] [-FilePath] <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="ab632-110">LiteralFilePathComputerName</span><span class="sxs-lookup"><span data-stu-id="ab632-110">LiteralFilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] -LiteralPath <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="ab632-111">Description</span><span class="sxs-lookup"><span data-stu-id="ab632-111">DESCRIPTION</span></span>

<span data-ttu-id="ab632-112">コマンドレットにより、 `Start-Job` ローカルコンピューターで PowerShell バックグラウンドジョブが開始されます。</span><span class="sxs-lookup"><span data-stu-id="ab632-112">The `Start-Job` cmdlet starts a PowerShell background job on the local computer.</span></span>

<span data-ttu-id="ab632-113">PowerShell バックグラウンドジョブは、現在のセッションと対話せずにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab632-113">A PowerShell background job runs a command without interacting with the current session.</span></span> <span data-ttu-id="ab632-114">バックグラウンドジョブを開始すると、ジョブの完了に時間がかかる場合でも、ジョブオブジェクトは直ちに返されます。</span><span class="sxs-lookup"><span data-stu-id="ab632-114">When you start a background job, a job object returns immediately, even if the job takes an extended time to finish.</span></span> <span data-ttu-id="ab632-115">ジョブの実行中は、中断されることなく引き続きセッションで作業できます。</span><span class="sxs-lookup"><span data-stu-id="ab632-115">You can continue to work in the session without interruption while the job runs.</span></span>

<span data-ttu-id="ab632-116">ジョブオブジェクトには、ジョブに関する有用な情報が含まれていますが、ジョブの結果は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="ab632-116">The job object contains useful information about the job, but it doesn't contain the job results.</span></span>
<span data-ttu-id="ab632-117">ジョブが完了したら、コマンドレットを使用して `Receive-Job` ジョブの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="ab632-117">When the job finishes, use the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="ab632-118">バックグラウンド ジョブの詳細については、「[about_Jobs](./About/about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab632-118">For more information about background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="ab632-119">リモートコンピューターでバックグラウンドジョブを実行するには、多くのコマンドレットで使用できる **AsJob** パラメーターを使用するか、コマンドレットを使用して `Invoke-Command` `Start-Job` リモートコンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab632-119">To run a background job on a remote computer, use the **AsJob** parameter that is available on many cmdlets, or use the `Invoke-Command` cmdlet to run a `Start-Job` command on the remote computer.</span></span> <span data-ttu-id="ab632-120">詳細については、「 [about_Remote_Jobs](./About/about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab632-120">For more information, see [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span></span>

<span data-ttu-id="ab632-121">PowerShell 3.0 以降では、 `Start-Job` スケジュールされたジョブなど、カスタムのジョブの種類のインスタンスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="ab632-121">Starting in PowerShell 3.0, `Start-Job` can start instances of custom job types, such as scheduled jobs.</span></span> <span data-ttu-id="ab632-122">を使用してカスタム型のジョブを開始する方法の詳細については、 `Start-Job` ジョブの種類の機能に関するヘルプドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab632-122">For information about how to use `Start-Job` to start jobs with custom types, see the help documents for the job type feature.</span></span>

<span data-ttu-id="ab632-123">ジョブの既定の作業ディレクトリはハードコーディングされています。</span><span class="sxs-lookup"><span data-stu-id="ab632-123">The default working directory for jobs is hardcoded.</span></span> <span data-ttu-id="ab632-124">Windows の既定値はで、 `$HOME\Documents` Linux または macOS では既定値は `$HOME` です。</span><span class="sxs-lookup"><span data-stu-id="ab632-124">The Windows default is `$HOME\Documents` and on Linux or macOS the default is `$HOME`.</span></span> <span data-ttu-id="ab632-125">バックグラウンドジョブで実行されているスクリプトコードでは、必要に応じて作業ディレクトリを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab632-125">The script code running in the background job needs to manage the working directory as needed.</span></span>

## <span data-ttu-id="ab632-126">例</span><span class="sxs-lookup"><span data-stu-id="ab632-126">EXAMPLES</span></span>

### <span data-ttu-id="ab632-127">例 1: バックグラウンドジョブを開始する</span><span class="sxs-lookup"><span data-stu-id="ab632-127">Example 1: Start a background job</span></span>

<span data-ttu-id="ab632-128">この例では、ローカルコンピューターで実行されるバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="ab632-128">This example starts a background job that runs on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name powershell }
```

```Output
Id  Name   PSJobTypeName   State     HasMoreData   Location    Command
--  ----   -------------   -----     -----------   --------    -------
1   Job1   BackgroundJob   Running   True          localhost   Get-Process -Name powershell
```

<span data-ttu-id="ab632-129">`Start-Job`**ScriptBlock** パラメーターを使用し `Get-Process` て、バックグラウンドジョブとして実行します。</span><span class="sxs-lookup"><span data-stu-id="ab632-129">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Process` as a background job.</span></span> <span data-ttu-id="ab632-130">**Name** パラメーターは、PowerShell プロセスを検索するように指定し `powershell` ます。</span><span class="sxs-lookup"><span data-stu-id="ab632-130">The **Name** parameter specifies to find PowerShell processes, `powershell`.</span></span> <span data-ttu-id="ab632-131">ジョブ情報が表示され、ジョブがバックグラウンドで実行されている間、PowerShell がプロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="ab632-131">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="ab632-132">ジョブの出力を表示するには、 `Receive-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab632-132">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="ab632-133">たとえば、「 `Receive-Job -Id 1` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ab632-133">For example, `Receive-Job -Id 1`.</span></span>

### <span data-ttu-id="ab632-134">例 2: Invoke-Command を使用してジョブを開始する</span><span class="sxs-lookup"><span data-stu-id="ab632-134">Example 2: Start a job using Invoke-Command</span></span>

<span data-ttu-id="ab632-135">この例では、複数のコンピューターでジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab632-135">This example runs a job on multiple computers.</span></span> <span data-ttu-id="ab632-136">ジョブは変数に格納され、PowerShell コマンドラインで変数名を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="ab632-136">The job is stored in a variable and is executed by using the variable name on the PowerShell command line.</span></span>

```powershell
$jobWRM = Invoke-Command -ComputerName (Get-Content -Path C:\Servers.txt) -ScriptBlock {
   Get-Service -Name WinRM } -JobName WinRM -ThrottleLimit 16 -AsJob
```

<span data-ttu-id="ab632-137">を使用するジョブ `Invoke-Command` が作成され、変数に格納され `$jobWRM` ます。</span><span class="sxs-lookup"><span data-stu-id="ab632-137">A job that uses `Invoke-Command` is created and stored in the `$jobWRM` variable.</span></span> <span data-ttu-id="ab632-138">`Invoke-Command`**ComputerName** パラメーターを使用して、ジョブを実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-138">`Invoke-Command` uses the **ComputerName** parameter to specify the computers where the job runs.</span></span> <span data-ttu-id="ab632-139">`Get-Content` ファイルからサーバー名を取得し `C:\Servers.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="ab632-139">`Get-Content` gets the server names from the `C:\Servers.txt` file.</span></span>

<span data-ttu-id="ab632-140">**ScriptBlock** パラメーターは、WinRM サービスを取得するコマンドを指定し `Get-Service` ます。 **WinRM**</span><span class="sxs-lookup"><span data-stu-id="ab632-140">The **ScriptBlock** parameter specifies a command that `Get-Service` gets the **WinRM** service.</span></span> <span data-ttu-id="ab632-141">**JobName** パラメーターは、ジョブのフレンドリ名を指定します ( **WinRM** )。</span><span class="sxs-lookup"><span data-stu-id="ab632-141">The **JobName** parameter specifies a friendly name for the job, **WinRM** .</span></span> <span data-ttu-id="ab632-142">**ThrottleLimit** パラメーターは、同時実行コマンドの数を16に制限します。</span><span class="sxs-lookup"><span data-stu-id="ab632-142">The **ThrottleLimit** parameter limits the number of concurrent commands to 16.</span></span> <span data-ttu-id="ab632-143">**AsJob** パラメーターは、サーバーでコマンドを実行するバックグラウンドジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="ab632-143">The **AsJob** parameter starts a background job that runs the command on the servers.</span></span>

### <span data-ttu-id="ab632-144">例 3: ジョブ情報を取得する</span><span class="sxs-lookup"><span data-stu-id="ab632-144">Example 3: Get job information</span></span>

<span data-ttu-id="ab632-145">この例では、ジョブに関する情報を取得し、ローカルコンピューターで実行された完了したジョブの結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="ab632-145">This example gets information about a job and displays the results of a completed job that was run on the local computer.</span></span>

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

<span data-ttu-id="ab632-146">`Start-Job`**ScriptBlock** パラメーターを使用して、 `Get-WinEvent` **システム** ログを取得するように指定したコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab632-146">`Start-Job` uses the **ScriptBlock** parameter to run a command that specifies `Get-WinEvent` to get the **System** log.</span></span> <span data-ttu-id="ab632-147">**Credential** パラメーターには、コンピューター上でジョブを実行するアクセス許可を持つドメインユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-147">The **Credential** parameter specifies a domain user account with permission to run the job on the computer.</span></span> <span data-ttu-id="ab632-148">ジョブオブジェクトは変数に格納され `$j` ます。</span><span class="sxs-lookup"><span data-stu-id="ab632-148">The job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="ab632-149">変数内のオブジェクト `$j` は、パイプラインの下にに送信され `Select-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="ab632-149">The object in the `$j` variable is sent down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="ab632-150">**Property** パラメーターは、 `*` すべてのジョブオブジェクトのプロパティを表示するアスタリスク () を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-150">The **Property** parameter specifies an asterisk (`*`) to display all the job object's properties.</span></span>

### <span data-ttu-id="ab632-151">例 4: バックグラウンドジョブとしてスクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="ab632-151">Example 4: Run a script as a background job</span></span>

<span data-ttu-id="ab632-152">この例では、ローカルコンピューター上のスクリプトがバックグラウンドジョブとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="ab632-152">In this example, a script on the local computer is run as a background job.</span></span>

```powershell
Start-Job -FilePath C:\Scripts\Sample.ps1
```

<span data-ttu-id="ab632-153">`Start-Job`**FilePath** パラメーターを使用して、ローカルコンピューターに格納されているスクリプトファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-153">`Start-Job` uses the **FilePath** parameter to specify a script file that's stored on the local computer.</span></span>

### <span data-ttu-id="ab632-154">例 5: バックグラウンドジョブを使用してプロセスを取得する</span><span class="sxs-lookup"><span data-stu-id="ab632-154">Example 5: Get a process using a background job</span></span>

<span data-ttu-id="ab632-155">この例では、バックグラウンドジョブを使用して、指定されたプロセスを名前で取得します。</span><span class="sxs-lookup"><span data-stu-id="ab632-155">This example uses a background job to get a specified process by name.</span></span>

```powershell
Start-Job -Name PShellJob -ScriptBlock { Get-Process -Name PowerShell }
```

<span data-ttu-id="ab632-156">`Start-Job`**Name** パラメーターを使用して、わかりやすいジョブ名 **pshelljob** を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-156">`Start-Job` uses the **Name** parameter to specify a friendly job name, **PShellJob** .</span></span> <span data-ttu-id="ab632-157">**ScriptBlock** パラメーターは、 `Get-Process` **PowerShell** という名前のプロセスを取得するように指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-157">The **ScriptBlock** parameter specifies `Get-Process` to get processes with the name **PowerShell** .</span></span>

### <span data-ttu-id="ab632-158">例 6: バックグラウンドジョブを使用してデータを収集して保存する</span><span class="sxs-lookup"><span data-stu-id="ab632-158">Example 6: Collect and save data by using a background job</span></span>

<span data-ttu-id="ab632-159">この例では、大量のマップデータを収集してファイルに保存するジョブを開始し `.tif` ます。</span><span class="sxs-lookup"><span data-stu-id="ab632-159">This example starts a job that collects a large amount of map data and then saves it in a `.tif` file.</span></span>

```powershell
Start-Job -Name GetMappingFiles -InitializationScript {Import-Module MapFunctions} -ScriptBlock {
   Get-Map -Name * | Set-Content -Path D:\Maps.tif } -RunAs32
```

<span data-ttu-id="ab632-160">`Start-Job`**Name** パラメーターを使用して、わかりやすいジョブ名である **getmappingfiles** を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-160">`Start-Job` uses the **Name** parameter to specify a friendly job name, **GetMappingFiles** .</span></span> <span data-ttu-id="ab632-161">**InitializationScript** パラメーターは、 **mapfunctions** モジュールをインポートするスクリプトブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab632-161">The **InitializationScript** parameter runs a script block that imports the **MapFunctions** module.</span></span> <span data-ttu-id="ab632-162">**ScriptBlock** パラメーターは、 `Get-Map` `Set-Content` **Path** パラメーターによって指定された場所にデータを実行して保存します。</span><span class="sxs-lookup"><span data-stu-id="ab632-162">The **ScriptBlock** parameter runs `Get-Map` and `Set-Content` saves the data in the location specified by the **Path** parameter.</span></span> <span data-ttu-id="ab632-163">**RunAs32** パラメーターは、64ビットオペレーティングシステムであっても、32ビットとしてプロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab632-163">The **RunAs32** parameter runs the process as 32-bit, even on a 64-bit operating system.</span></span>

### <span data-ttu-id="ab632-164">例 7: バックグラウンドジョブに入力を渡す</span><span class="sxs-lookup"><span data-stu-id="ab632-164">Example 7: Pass input to a background job</span></span>

<span data-ttu-id="ab632-165">この例では、 `$input` 自動変数を使用して入力オブジェクトを処理します。</span><span class="sxs-lookup"><span data-stu-id="ab632-165">This example uses the `$input` automatic variable to process an input object.</span></span> <span data-ttu-id="ab632-166">`Receive-Job`ジョブの出力を表示するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="ab632-166">Use `Receive-Job` to view the job's output.</span></span>

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

<span data-ttu-id="ab632-167">`Start-Job`**ScriptBlock** パラメーターを使用し `Get-Content` て、自動変数を指定して実行し `$input` ます。</span><span class="sxs-lookup"><span data-stu-id="ab632-167">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Content` with the `$input` automatic variable.</span></span> <span data-ttu-id="ab632-168">`$input`変数は **InputObject** パラメーターからオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="ab632-168">The `$input` variable gets objects from the **InputObject** parameter.</span></span> <span data-ttu-id="ab632-169">`Receive-Job`**Name** パラメーターを使用してジョブを指定し、結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="ab632-169">`Receive-Job` uses the **Name** parameter to specify the job and outputs the results.</span></span> <span data-ttu-id="ab632-170">**Keep** パラメーターを指定すると、ジョブの出力が保存され、PowerShell セッション中に再度表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ab632-170">The **Keep** parameter saves the job output so it can be viewed again during the PowerShell session.</span></span>

### <span data-ttu-id="ab632-171">例 8: ArgumentList パラメーターを使用して配列を指定する</span><span class="sxs-lookup"><span data-stu-id="ab632-171">Example 8: Use the ArgumentList parameter to specify an array</span></span>

<span data-ttu-id="ab632-172">この例では、 **ArgumentList** パラメーターを使用して、引数の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-172">This example uses the **ArgumentList** parameter to specify an array of arguments.</span></span> <span data-ttu-id="ab632-173">配列は、プロセス名のコンマ区切りのリストです。</span><span class="sxs-lookup"><span data-stu-id="ab632-173">The array is a comma-separated list of process names.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name $args } -ArgumentList powershell, pwsh, notepad
```

```Output
Id     Name      PSJobTypeName   State       HasMoreData     Location     Command
--     ----      -------------   -----       -----------     --------     -------
1      Job1      BackgroundJob   Running     True            localhost    Get-Process -Name $args
```

<span data-ttu-id="ab632-174">コマンドレットでは、 `Start-Job` **ScriptBlock** パラメーターを使用してコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab632-174">The `Start-Job` cmdlet uses the **ScriptBlock** parameter to run a command.</span></span> <span data-ttu-id="ab632-175">`Get-Process`**Name** パラメーターを使用して、自動変数を指定し `$args` ます。</span><span class="sxs-lookup"><span data-stu-id="ab632-175">`Get-Process` uses the **Name** parameter to specify the automatic variable `$args`.</span></span> <span data-ttu-id="ab632-176">**ArgumentList** パラメーターは、プロセス名の配列をに渡し `$args` ます。</span><span class="sxs-lookup"><span data-stu-id="ab632-176">The **ArgumentList** parameter passes the array of process names to `$args`.</span></span> <span data-ttu-id="ab632-177">このプロセス名は、ローカルコンピューター上で実行されているプロセスです。</span><span class="sxs-lookup"><span data-stu-id="ab632-177">The process names powershell, pwsh, and notepad are processes running on the local computer.</span></span>

<span data-ttu-id="ab632-178">ジョブの出力を表示するには、 `Receive-Job` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab632-178">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="ab632-179">たとえば、「 `Receive-Job -Id 1` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ab632-179">For example, `Receive-Job -Id 1`.</span></span>

## <span data-ttu-id="ab632-180">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ab632-180">PARAMETERS</span></span>

### <span data-ttu-id="ab632-181">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="ab632-181">-ArgumentList</span></span>

<span data-ttu-id="ab632-182">**FilePath** パラメーターで指定されたスクリプト、または **ScriptBlock** パラメーターで指定されたコマンドで指定されたスクリプトの引数またはパラメーター値の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-182">Specifies an array of arguments, or parameter values, for the script that is specified by the **FilePath** parameter or a command specified with the **ScriptBlock** parameter.</span></span>

<span data-ttu-id="ab632-183">引数は、1次元の配列引数として **ArgumentList** に渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab632-183">Arguments must be passed to **ArgumentList** as single-dimension array argument.</span></span> <span data-ttu-id="ab632-184">たとえば、コンマ区切りのリストです。</span><span class="sxs-lookup"><span data-stu-id="ab632-184">For example, a comma-separated list.</span></span> <span data-ttu-id="ab632-185">**ArgumentList** の動作の詳細については、「 [about_Splatting](about/about_Splatting.md#splatting-with-arrays)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab632-185">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab632-186">-認証</span><span class="sxs-lookup"><span data-stu-id="ab632-186">-Authentication</span></span>

<span data-ttu-id="ab632-187">ユーザー資格情報の認証に使用するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-187">Specifies the mechanism that is used to authenticate user credentials.</span></span>

<span data-ttu-id="ab632-188">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ab632-188">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="ab632-189">Default</span><span class="sxs-lookup"><span data-stu-id="ab632-189">Default</span></span>
- <span data-ttu-id="ab632-190">Basic</span><span class="sxs-lookup"><span data-stu-id="ab632-190">Basic</span></span>
- <span data-ttu-id="ab632-191">Credssp</span><span class="sxs-lookup"><span data-stu-id="ab632-191">Credssp</span></span>
- <span data-ttu-id="ab632-192">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="ab632-192">Digest</span></span>
- <span data-ttu-id="ab632-193">Kerberos</span><span class="sxs-lookup"><span data-stu-id="ab632-193">Kerberos</span></span>
- <span data-ttu-id="ab632-194">ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="ab632-194">Negotiate</span></span>
- <span data-ttu-id="ab632-195">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="ab632-195">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="ab632-196">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="ab632-196">The default value is Default.</span></span>

<span data-ttu-id="ab632-197">CredSSP 認証は、windows Vista、Windows Server 2008、およびそれ以降のバージョンの Windows オペレーティングシステムでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ab632-197">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="ab632-198">このパラメーターの値の詳細については、「 [Authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab632-198">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="ab632-199">ユーザーの資格情報が認証対象のリモート コンピューターに渡される Credential Security Support Provider (CredSSP) 認証は、リモート ネットワーク共有にアクセスする場合など、複数のリソースの認証を必要とするコマンドを対象としています。</span><span class="sxs-lookup"><span data-stu-id="ab632-199">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="ab632-200">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="ab632-200">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="ab632-201">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ab632-201">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab632-202">-Credential</span><span class="sxs-lookup"><span data-stu-id="ab632-202">-Credential</span></span>

<span data-ttu-id="ab632-203">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-203">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="ab632-204">**Credential** パラメーターが指定されていない場合、コマンドは現在のユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="ab632-204">If the **Credential** parameter isn't specified, the command uses the current user's credentials.</span></span>

<span data-ttu-id="ab632-205">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="ab632-205">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="ab632-206">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="ab632-206">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="ab632-207">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="ab632-207">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="ab632-208">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab632-208">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab632-209">-DefinitionName</span><span class="sxs-lookup"><span data-stu-id="ab632-209">-DefinitionName</span></span>

<span data-ttu-id="ab632-210">このコマンドレットが開始するジョブの定義名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-210">Specifies the definition name of the job that this cmdlet starts.</span></span> <span data-ttu-id="ab632-211">このパラメーターは、スケジュールされたジョブのように定義名を持つカスタムのジョブを開始するために使用します。</span><span class="sxs-lookup"><span data-stu-id="ab632-211">Use this parameter to start custom job types that have a definition name, such as scheduled jobs.</span></span>

<span data-ttu-id="ab632-212">を使用し `Start-Job` てスケジュールされたジョブのインスタンスを開始すると、ジョブトリガーやジョブオプションに関係なく、ジョブは直ちに開始されます。</span><span class="sxs-lookup"><span data-stu-id="ab632-212">When you use `Start-Job` to start an instance of a scheduled job, the job starts immediately, regardless of job triggers or job options.</span></span> <span data-ttu-id="ab632-213">結果のジョブインスタンスはスケジュールされたジョブですが、スケジュールされたジョブのトリガーなどのディスクには保存されません。</span><span class="sxs-lookup"><span data-stu-id="ab632-213">The resulting job instance is a scheduled job, but it isn't saved to disk like triggered scheduled jobs.</span></span> <span data-ttu-id="ab632-214">の **ArgumentList** パラメーターを使用して、 `Start-Job` スケジュールされたジョブで実行されるスクリプトのパラメーターの値を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab632-214">You can't use the **ArgumentList** parameter of `Start-Job` to provide values for parameters of scripts that run in a scheduled job.</span></span> <span data-ttu-id="ab632-215">詳細については、「 [about_Scheduled_Jobs](../PSScheduledJob/About/about_Scheduled_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab632-215">For more information, see [about_Scheduled_Jobs](../PSScheduledJob/About/about_Scheduled_Jobs.md).</span></span>

<span data-ttu-id="ab632-216">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ab632-216">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ab632-217">-DefinitionPath</span><span class="sxs-lookup"><span data-stu-id="ab632-217">-DefinitionPath</span></span>

<span data-ttu-id="ab632-218">このコマンドレットが開始するジョブの定義のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-218">Specifies path of the definition for the job that this cmdlet starts.</span></span> <span data-ttu-id="ab632-219">定義のパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ab632-219">Enter the definition path.</span></span> <span data-ttu-id="ab632-220">**Definitionpath** パラメーターと **definitionpath** パラメーターの値を連結したものは、ジョブ定義の完全修飾パスです。</span><span class="sxs-lookup"><span data-stu-id="ab632-220">The concatenation of the values of the **DefinitionPath** and **DefinitionName** parameters is the fully qualified path of the job definition.</span></span> <span data-ttu-id="ab632-221">このパラメーターは、スケジュールされたジョブのように定義パスを持つカスタムのジョブを開始するために使用します。</span><span class="sxs-lookup"><span data-stu-id="ab632-221">Use this parameter to start custom job types that have a definition path, such as scheduled jobs.</span></span>

<span data-ttu-id="ab632-222">スケジュールされたジョブの場合、 **Definitionpath** パラメーターの値は `$home\AppData\Local\Windows\PowerShell\ScheduledJob` です。</span><span class="sxs-lookup"><span data-stu-id="ab632-222">For scheduled jobs, the value of the **DefinitionPath** parameter is `$home\AppData\Local\Windows\PowerShell\ScheduledJob`.</span></span>

<span data-ttu-id="ab632-223">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ab632-223">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ab632-224">-FilePath</span><span class="sxs-lookup"><span data-stu-id="ab632-224">-FilePath</span></span>

<span data-ttu-id="ab632-225">`Start-Job`バックグラウンドジョブとして実行するローカルスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-225">Specifies a local script that `Start-Job` runs as a background job.</span></span> <span data-ttu-id="ab632-226">スクリプトのパスとファイル名を入力するか、パイプラインを使用してスクリプトパスを送信 `Start-Job` します。</span><span class="sxs-lookup"><span data-stu-id="ab632-226">Enter the path and file name of the script or use the pipeline to send a script path to `Start-Job`.</span></span> <span data-ttu-id="ab632-227">スクリプトは、ローカルコンピューター上、またはローカルコンピューターがアクセスできるフォルダー内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab632-227">The script must be on the local computer or in a folder that the local computer can access.</span></span>

<span data-ttu-id="ab632-228">このパラメーターを使用すると、PowerShell によって、指定したスクリプトファイルの内容がスクリプトブロックに変換され、バックグラウンドジョブとしてスクリプトブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="ab632-228">When you use this parameter, PowerShell converts the contents of the specified script file to a script block and runs the script block as a background job.</span></span>

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

### <span data-ttu-id="ab632-229">-InitializationScript</span><span class="sxs-lookup"><span data-stu-id="ab632-229">-InitializationScript</span></span>

<span data-ttu-id="ab632-230">ジョブの開始前に実行するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-230">Specifies commands that run before the job starts.</span></span> <span data-ttu-id="ab632-231">スクリプトブロックを作成するには、コマンドを中かっこ ( `{}` ) で囲みます。</span><span class="sxs-lookup"><span data-stu-id="ab632-231">To create a script block, enclose the commands in curly braces (`{}`).</span></span>

<span data-ttu-id="ab632-232">このパラメーターは、ジョブを実行するセッションを準備するために使用します。</span><span class="sxs-lookup"><span data-stu-id="ab632-232">Use this parameter to prepare the session in which the job runs.</span></span> <span data-ttu-id="ab632-233">たとえば、このパラメーターを使用して、関数、スナップイン、モジュールをセッションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="ab632-233">For example, you can use it to add functions, snap-ins, and modules to the session.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab632-234">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ab632-234">-InputObject</span></span>

<span data-ttu-id="ab632-235">コマンドへの入力を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-235">Specifies input to the command.</span></span> <span data-ttu-id="ab632-236">オブジェクトが格納されている変数を入力するか、オブジェクトを生成するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="ab632-236">Enter a variable that contains the objects, or type a command or expression that generates the objects.</span></span>

<span data-ttu-id="ab632-237">**ScriptBlock** パラメーターの値で、自動変数を使用して `$input` 入力オブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="ab632-237">In the value of the **ScriptBlock** parameter, use the `$input` automatic variable to represent the input objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ab632-238">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ab632-238">-LiteralPath</span></span>

<span data-ttu-id="ab632-239">このコマンドレットをバックグラウンドジョブとして実行するローカルスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-239">Specifies a local script that this cmdlet runs as a background job.</span></span> <span data-ttu-id="ab632-240">ローカルコンピューター上のスクリプトのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ab632-240">Enter the path of a script on the local computer.</span></span>

<span data-ttu-id="ab632-241">`Start-Job`**LiteralPath** パラメーターの値を、型指定されたとおりに使用します。</span><span class="sxs-lookup"><span data-stu-id="ab632-241">`Start-Job` uses the value of the **LiteralPath** parameter exactly as it's typed.</span></span> <span data-ttu-id="ab632-242">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="ab632-242">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="ab632-243">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="ab632-243">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="ab632-244">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="ab632-244">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralFilePathComputerName
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab632-245">-Name</span><span class="sxs-lookup"><span data-stu-id="ab632-245">-Name</span></span>

<span data-ttu-id="ab632-246">新しいジョブのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-246">Specifies a friendly name for the new job.</span></span> <span data-ttu-id="ab632-247">この名前を使用して、コマンドレットなど、他のジョブコマンドレットに対してジョブを識別でき `Stop-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="ab632-247">You can use the name to identify the job to other job cmdlets, such as the `Stop-Job` cmdlet.</span></span>

<span data-ttu-id="ab632-248">既定の表示名はです `Job#` 。ここで、 `#` は、ジョブごとに増分される序数です。</span><span class="sxs-lookup"><span data-stu-id="ab632-248">The default friendly name is `Job#`, where `#` is an ordinal number that is incremented for each job.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ab632-249">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="ab632-249">-PSVersion</span></span>

<span data-ttu-id="ab632-250">バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-250">Specifies a version.</span></span> <span data-ttu-id="ab632-251">`Start-Job` PowerShell のバージョンでジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab632-251">`Start-Job` runs the job with the version of PowerShell.</span></span> <span data-ttu-id="ab632-252">このパラメーターに指定できる値は、 `2.0` と `3.0` です。</span><span class="sxs-lookup"><span data-stu-id="ab632-252">The acceptable values for this parameter are: `2.0` and `3.0`.</span></span>

<span data-ttu-id="ab632-253">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ab632-253">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab632-254">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="ab632-254">-RunAs32</span></span>

<span data-ttu-id="ab632-255">が `Start-Job` 32 ビットプロセスでジョブを実行することを示します。</span><span class="sxs-lookup"><span data-stu-id="ab632-255">Indicates that `Start-Job` runs the job in a 32-bit process.</span></span> <span data-ttu-id="ab632-256">**RunAs32** は、64ビットオペレーティングシステム上でも、32ビットプロセスでジョブを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="ab632-256">**RunAs32** forces the job to run in a 32-bit process, even on a 64-bit operating system.</span></span>

<span data-ttu-id="ab632-257">Windows 7 と Windows Server 2008 R2 の64ビットバージョンでは、コマンドに `Start-Job` **RunAs32** パラメーターが含まれている場合、 **Credential** パラメーターを使用して別のユーザーの資格情報を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab632-257">On 64-bit versions of Windows 7 and Windows Server 2008 R2, when the `Start-Job` command includes the **RunAs32** parameter, you can't use the **Credential** parameter to specify the credentials of another user.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, LiteralFilePathComputerName, FilePathComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab632-258">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="ab632-258">-ScriptBlock</span></span>

<span data-ttu-id="ab632-259">バックグラウンド ジョブで実行するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab632-259">Specifies the commands to run in the background job.</span></span> <span data-ttu-id="ab632-260">スクリプトブロックを作成するには、コマンドを中かっこ ( `{}` ) で囲みます。</span><span class="sxs-lookup"><span data-stu-id="ab632-260">To create a script block, enclose the commands in curly braces (`{}`).</span></span> <span data-ttu-id="ab632-261">`$input` **InputObject** パラメーターの値にアクセスするには、自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="ab632-261">Use the `$input` automatic variable to access the value of the **InputObject** parameter.</span></span> <span data-ttu-id="ab632-262">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="ab632-262">This parameter is required.</span></span>

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

### <span data-ttu-id="ab632-263">-Type</span><span class="sxs-lookup"><span data-stu-id="ab632-263">-Type</span></span>

<span data-ttu-id="ab632-264">によって開始されるジョブのカスタムの種類を指定し `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="ab632-264">Specifies the custom type for jobs started by `Start-Job`.</span></span> <span data-ttu-id="ab632-265">カスタムのジョブの種類の名前を入力します (スケジュールされたジョブの場合は PSScheduledJob、ワークフロー ジョブの場合は PSWorkflowJob)。</span><span class="sxs-lookup"><span data-stu-id="ab632-265">Enter a custom job type name, such as PSScheduledJob for scheduled jobs or PSWorkflowJob for workflows jobs.</span></span> <span data-ttu-id="ab632-266">このパラメーターは、標準のバックグラウンドジョブでは無効です。</span><span class="sxs-lookup"><span data-stu-id="ab632-266">This parameter isn't valid for standard background jobs.</span></span>

<span data-ttu-id="ab632-267">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ab632-267">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ab632-268">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ab632-268">CommonParameters</span></span>

<span data-ttu-id="ab632-269">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ab632-269">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ab632-270">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab632-270">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ab632-271">入力</span><span class="sxs-lookup"><span data-stu-id="ab632-271">INPUTS</span></span>

### <span data-ttu-id="ab632-272">System.String</span><span class="sxs-lookup"><span data-stu-id="ab632-272">System.String</span></span>

<span data-ttu-id="ab632-273">パイプラインを使用し **て、name プロパティを** 持つオブジェクトを **name** パラメーターに送信できます。</span><span class="sxs-lookup"><span data-stu-id="ab632-273">You can use the pipeline to send an object with the **Name** property to the **Name** parameter.</span></span> <span data-ttu-id="ab632-274">たとえば、 **FileInfo** オブジェクトをからにパイプラインでき `Get-ChildItem` `Start-Job` ます。</span><span class="sxs-lookup"><span data-stu-id="ab632-274">For example, you can pipeline a **FileInfo** object from `Get-ChildItem` to `Start-Job`.</span></span>

## <span data-ttu-id="ab632-275">出力</span><span class="sxs-lookup"><span data-stu-id="ab632-275">OUTPUTS</span></span>

### <span data-ttu-id="ab632-276">システムの管理. PSRemotingJob</span><span class="sxs-lookup"><span data-stu-id="ab632-276">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="ab632-277">`Start-Job` 開始したジョブを表す **Psremotingjob** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="ab632-277">`Start-Job` returns a **PSRemotingJob** object that represents the job that it started.</span></span>

## <span data-ttu-id="ab632-278">注</span><span class="sxs-lookup"><span data-stu-id="ab632-278">NOTES</span></span>

<span data-ttu-id="ab632-279">バックグラウンドでを実行するために、は、 `Start-Job` 現在のセッションで独自のセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="ab632-279">To run in the background, `Start-Job` runs in its own session in the current session.</span></span> <span data-ttu-id="ab632-280">コマンドレットを使用して `Invoke-Command` `Start-Job` リモートコンピューター上のセッションでコマンドを実行すると、は `Start-Job` リモートセッションのセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="ab632-280">When you use the `Invoke-Command` cmdlet to run a `Start-Job` command in a session on a remote computer, `Start-Job` runs in a session in the remote session.</span></span>

## <span data-ttu-id="ab632-281">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ab632-281">RELATED LINKS</span></span>

[<span data-ttu-id="ab632-282">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="ab632-282">about_Arrays</span></span>](./about/about_arrays.md)

[<span data-ttu-id="ab632-283">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="ab632-283">about_Automatic_Variables</span></span>](./about/about_automatic_variables.md)

[<span data-ttu-id="ab632-284">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="ab632-284">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="ab632-285">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="ab632-285">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="ab632-286">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="ab632-286">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="ab632-287">Get-Job</span><span class="sxs-lookup"><span data-stu-id="ab632-287">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="ab632-288">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="ab632-288">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="ab632-289">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="ab632-289">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="ab632-290">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="ab632-290">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="ab632-291">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="ab632-291">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="ab632-292">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="ab632-292">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="ab632-293">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="ab632-293">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="ab632-294">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="ab632-294">Wait-Job</span></span>](Wait-Job.md)