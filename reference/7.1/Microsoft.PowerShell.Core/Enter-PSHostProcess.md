---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pshostprocess?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSHostProcess
ms.openlocfilehash: 14f6173e318c6abd223ddff85a3694cfaac75c93
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "93218968"
---
# <span data-ttu-id="ec408-103">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="ec408-103">Enter-PSHostProcess</span></span>

## <span data-ttu-id="ec408-104">概要</span><span class="sxs-lookup"><span data-stu-id="ec408-104">SYNOPSIS</span></span>
<span data-ttu-id="ec408-105">ローカルプロセスを使用して、対話型セッションに接続して入力します。</span><span class="sxs-lookup"><span data-stu-id="ec408-105">Connects to and enters into an interactive session with a local process.</span></span>

## <span data-ttu-id="ec408-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ec408-106">SYNTAX</span></span>

### <span data-ttu-id="ec408-107">ProcessIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="ec408-107">ProcessIdParameterSet (Default)</span></span>

```
Enter-PSHostProcess [-Id] <Int32> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="ec408-108">ProcessParameterSet</span><span class="sxs-lookup"><span data-stu-id="ec408-108">ProcessParameterSet</span></span>

```
Enter-PSHostProcess [-Process] <Process> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="ec408-109">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="ec408-109">ProcessNameParameterSet</span></span>

```
Enter-PSHostProcess [-Name] <String> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="ec408-110">PSHostProcessInfoParameterSet</span><span class="sxs-lookup"><span data-stu-id="ec408-110">PSHostProcessInfoParameterSet</span></span>

```
Enter-PSHostProcess [-HostProcessInfo] <PSHostProcessInfo> [[-AppDomainName] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="ec408-111">PipeNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="ec408-111">PipeNameParameterSet</span></span>

```
Enter-PSHostProcess -CustomPipeName <String> [<CommonParameters>]
```

## <span data-ttu-id="ec408-112">Description</span><span class="sxs-lookup"><span data-stu-id="ec408-112">DESCRIPTION</span></span>

<span data-ttu-id="ec408-113">`Enter-PSHostProcess`コマンドレットは、ローカルプロセスを使用して対話型セッションに接続し、それに入力します。</span><span class="sxs-lookup"><span data-stu-id="ec408-113">The `Enter-PSHostProcess` cmdlet connects to and enters into an interactive session with a local process.</span></span> <span data-ttu-id="ec408-114">PowerShell 6.2 以降では、このコマンドレットは Windows 以外のプラットフォームでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ec408-114">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

<span data-ttu-id="ec408-115">PowerShell をホストする新しいプロセスを作成し、リモートセッションを実行する代わりに、既に PowerShell を実行している既存のプロセスで、リモートの対話型セッションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="ec408-115">Instead of creating a new process to host PowerShell and run a remote session, the remote, interactive session is run in an existing process that is already running PowerShell.</span></span> <span data-ttu-id="ec408-116">指定されたプロセスでリモートセッションを操作する場合は、実行中の実行空間を列挙し、またはのいずれかを実行してデバッグする実行空間を選択でき `Debug-Runspace` `Enable-RunspaceDebug` ます。</span><span class="sxs-lookup"><span data-stu-id="ec408-116">When you are interacting with a remote session on a specified process, you can enumerate running runspaces, and then select a runspace to debug by running either `Debug-Runspace` or `Enable-RunspaceDebug`.</span></span>

<span data-ttu-id="ec408-117">入力するプロセスは、PowerShell (System.Management.Automation.dll) をホストしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec408-117">The process that you want to enter must be hosting PowerShell (System.Management.Automation.dll).</span></span>
<span data-ttu-id="ec408-118">プロセスが検出されたコンピューターの Administrators グループのメンバーであるか、またはプロセスを開始したスクリプトを実行しているユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec408-118">You must be either a member of the Administrators group on the computer on which the process is found, or you must be the user who is running the script that started the process.</span></span>

<span data-ttu-id="ec408-119">デバッグする実行空間を選択すると、現在コマンドを実行しているか、デバッガーで停止している場合、リモートデバッグセッションが実行空間に対して開かれます。</span><span class="sxs-lookup"><span data-stu-id="ec408-119">After you have selected a runspace to debug, a remote debug session is opened for the runspace if it is either currently running a command or is stopped in the debugger.</span></span> <span data-ttu-id="ec408-120">その後、他のリモートセッションスクリプトをデバッグする場合と同じ方法で、実行空間スクリプトをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="ec408-120">You can then debug the runspace script in the same way you would debug other remote session scripts.</span></span>

<span data-ttu-id="ec408-121">デバッグセッションからデタッチした後、プロセスとの対話型セッションを終了するには、exit を2回実行します。または、既存のデバッガーの quit コマンドを実行して、スクリプトの実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="ec408-121">Detach from a debugging session, and then the interactive session with the process, by running exit twice, or stop script execution by running the existing debugger quit command.</span></span>

<span data-ttu-id="ec408-122">**Name** パラメーターを使用してプロセスを指定し、指定した名前のプロセスが1つだけ見つかった場合は、プロセスが入力されます。</span><span class="sxs-lookup"><span data-stu-id="ec408-122">If you specify a process by using the **Name** parameter, and there is only one process found with the specified name, the process is entered.</span></span> <span data-ttu-id="ec408-123">指定された名前を持つ複数のプロセスが見つかった場合、PowerShell はエラーを返し、指定された名前を持つすべてのプロセスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ec408-123">If more than one process with the specified name is found, PowerShell returns an error, and lists all processes found with the specified name.</span></span>

<span data-ttu-id="ec408-124">リモートコンピューター上のプロセスへのアタッチをサポートするために、 `Enter-PSHostProcess` 指定したリモートコンピューターでコマンドレットが有効になります。これにより、リモート PowerShell セッション内のローカルプロセスにアタッチできるようになります。</span><span class="sxs-lookup"><span data-stu-id="ec408-124">To support attaching to processes on remote computers, the `Enter-PSHostProcess` cmdlet is enabled in a specified remote computer, so that you can attach to a local process within a remote PowerShell session.</span></span>

## <span data-ttu-id="ec408-125">例</span><span class="sxs-lookup"><span data-stu-id="ec408-125">EXAMPLES</span></span>

### <span data-ttu-id="ec408-126">例 1: PowerShell ISE プロセス内の実行空間のデバッグを開始する</span><span class="sxs-lookup"><span data-stu-id="ec408-126">Example 1: Start debugging a runspace within the PowerShell ISE process</span></span>

<span data-ttu-id="ec408-127">この例では、 `Enter-PSHostProcess` powershell コンソール内からを実行して、POWERSHELL ISE プロセスに入ります。</span><span class="sxs-lookup"><span data-stu-id="ec408-127">In this example, you run `Enter-PSHostProcess` from within the PowerShell console to enter the PowerShell ISE process.</span></span> <span data-ttu-id="ec408-128">生成された対話型セッションでは、を実行してデバッグする実行空間を見つけて、実行 `Get-Runspace` 空間をデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="ec408-128">In the resulting interactive session, you can find a runspace that you want to debug by running `Get-Runspace`, and then debug the runspace.</span></span>

```
PS C:\> Enter-PSHostProcess -Name powershell_ise
[Process:1520]: PS C:\Test\Documents>

Next, get available runspaces within the process you have entered.
PS C:\> [Process:1520]: PS C:\>  Get-Runspace
Id    Name          InstanceId                               State           Availability
--    -------       -----------                              ------          -------------
1     Runspace1     2d91211d-9cce-42f0-ab0e-71ac258b32b5     Opened          Available
2     Runspace2     a3855043-cb16-424a-a616-685360c3763b     Opened          RemoteDebug
3     MyLocalRS     2236dbd8-2105-4dec-a15a-a27d0bfaacb5     Opened          LocalDebug
4     MyRunspace    771356e9-8c44-4b70-9de5-dd17cb41e48e     Opened          Busy
5     Runspace8     3e517382-a97a-49ba-9c3c-fd21f6664288     Broken          None

The runspace objects returned by Get-Runspace also have a NoteProperty called ScriptStackTrace of
the running command stack, if available.Next, debug runspace ID 4, that is running another user's
long-running script. From the list returned from Get-Runspace, note that the runspace state is
Opened, and Availability is Busy, meaning that the runspace is still running the long-running
script.

PS C:\> [Process:1520]: PS C:\>  (Get-Runspace -Id 4).ScriptStackTrace
Command                    Arguments                           Location
-------                    ---------                           --------
MyModuleWorkflowF1         {}                                  TestNoFile3.psm1: line 6
WFTest1                    {}                                  TestNoFile2.ps1: line 14
TestNoFile2.ps1            {}                                  TestNoFile2.ps1: line 22
<ScriptBlock>              {}                                  <No file>

Start an interactive debugging session with this runspace by running the Debug-Runspace cmdlet.

PS C:\> [Process: 1520]: PS C:\>  Debug-Runspace -Id 4
Hit Line breakpoint on 'C:\TestWFVar1.ps1:83'

At C:\TestWFVar1.ps1:83 char:1
+ $scriptVar = "Script Variable"
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

[Process: 1520]: [RSDBG: 4]: PS C:\> >

After you are finished debugging, allow the script to continue running without the debugger attached
by running the exit debugger command. Alternatively, you can quit the debugger with the q or Stop
commands.

PS C:\> [Process:346]: [RSDBG: 3]: PS C:\> > exit
[Process:1520]: PS C:\>

When you are finished working in the process, exit the process by running the Exit-PSHostProcess
cmdlet. This returns you to the PS C:\> prompt.

PS C:\> [Process:1520]: PS C:\>  Exit-PSHostProcess
PS C:\>
```

## <span data-ttu-id="ec408-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ec408-129">PARAMETERS</span></span>

### <span data-ttu-id="ec408-130">-AppDomainName</span><span class="sxs-lookup"><span data-stu-id="ec408-130">-AppDomainName</span></span>

<span data-ttu-id="ec408-131">省略した場合に接続するアプリケーションドメイン名を指定します。 **Defaultappdomain** を使用します。</span><span class="sxs-lookup"><span data-stu-id="ec408-131">Specifies an application domain name to connect to if omitted, uses **DefaultAppDomain**.</span></span> <span data-ttu-id="ec408-132">`Get-PSHostProcessInfo`アプリケーションドメイン名を表示するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="ec408-132">Use `Get-PSHostProcessInfo` to display the application domain names.</span></span>

```yaml
Type: System.String
Parameter Sets: ProcessIdParameterSet, ProcessParameterSet, ProcessNameParameterSet, PSHostProcessInfoParameterSet
Aliases:

Required: False
Position: 1
Default value: DefaultAppDomain
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ec408-133">-HostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="ec408-133">-HostProcessInfo</span></span>

<span data-ttu-id="ec408-134">PowerShell を使用して接続できる **get-pshostprocessinfo** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec408-134">Specifies a **PSHostProcessInfo** object that can be connected to with PowerShell.</span></span> <span data-ttu-id="ec408-135">`Get-PSHostProcessInfo`オブジェクトを取得するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="ec408-135">Use `Get-PSHostProcessInfo` to get the object.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.PSHostProcessInfo
Parameter Sets: PSHostProcessInfoParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ec408-136">-Id</span><span class="sxs-lookup"><span data-stu-id="ec408-136">-Id</span></span>

<span data-ttu-id="ec408-137">プロセス ID を指定してプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec408-137">Specifies a process by the process ID.</span></span> <span data-ttu-id="ec408-138">プロセス ID を取得するには、 `Get-Process` コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ec408-138">To get a process ID, run the `Get-Process` cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ProcessIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ec408-139">-Name</span><span class="sxs-lookup"><span data-stu-id="ec408-139">-Name</span></span>

<span data-ttu-id="ec408-140">プロセス名でプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec408-140">Specifies a process by the process name.</span></span> <span data-ttu-id="ec408-141">プロセス名を取得するには、 `Get-Process` コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ec408-141">To get a process name, run the `Get-Process` cmdlet.</span></span> <span data-ttu-id="ec408-142">また、タスクマネージャーでプロセスの [プロパティ] ダイアログボックスからプロセス名を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="ec408-142">You can also get process names from the Properties dialog box of a process in Task Manager.</span></span>

```yaml
Type: System.String
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ec408-143">-Process</span><span class="sxs-lookup"><span data-stu-id="ec408-143">-Process</span></span>

<span data-ttu-id="ec408-144">プロセスオブジェクトによってプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec408-144">Specifies a process by the process object.</span></span> <span data-ttu-id="ec408-145">このパラメーターを使用する最も簡単な方法は、 `Get-Process` 変数に入力するプロセスを返すコマンドの結果を保存し、その変数をこのパラメーターの値として指定することです。</span><span class="sxs-lookup"><span data-stu-id="ec408-145">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

```yaml
Type: System.Diagnostics.Process
Parameter Sets: ProcessParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ec408-146">-CustomPipeName</span><span class="sxs-lookup"><span data-stu-id="ec408-146">-CustomPipeName</span></span>

<span data-ttu-id="ec408-147">接続先のカスタム名前付きパイプ名を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="ec408-147">Gets or sets the custom named pipe name to connect to.</span></span> <span data-ttu-id="ec408-148">これは通常、と組み合わせて使用され `pwsh -CustomPipeName` ます。</span><span class="sxs-lookup"><span data-stu-id="ec408-148">This is usually used in conjunction with `pwsh -CustomPipeName`.</span></span>

<span data-ttu-id="ec408-149">このパラメーターは、PowerShell 6.2 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ec408-149">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.String
Parameter Sets: PipeNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ec408-150">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ec408-150">CommonParameters</span></span>

<span data-ttu-id="ec408-151">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ec408-151">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ec408-152">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec408-152">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ec408-153">入力</span><span class="sxs-lookup"><span data-stu-id="ec408-153">INPUTS</span></span>

### <span data-ttu-id="ec408-154">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="ec408-154">System.Diagnostics.Process</span></span>

## <span data-ttu-id="ec408-155">出力</span><span class="sxs-lookup"><span data-stu-id="ec408-155">OUTPUTS</span></span>

## <span data-ttu-id="ec408-156">注</span><span class="sxs-lookup"><span data-stu-id="ec408-156">NOTES</span></span>

<span data-ttu-id="ec408-157">`Enter-PSHostProcess` コマンドを実行している PowerShell セッションのプロセスを入力できません。</span><span class="sxs-lookup"><span data-stu-id="ec408-157">`Enter-PSHostProcess` cannot enter the process of the PowerShell session in which you are running the command.</span></span> <span data-ttu-id="ec408-158">ただし、別の PowerShell セッションのプロセスや、を実行しているセッションと同時に実行されている PowerShell ISE セッションを入力することができ `Enter-PSHostProcess` ます。</span><span class="sxs-lookup"><span data-stu-id="ec408-158">You can, however, enter the process of another PowerShell session, or a PowerShell ISE session that is running at the same time as the session in which you are running `Enter-PSHostProcess`.</span></span>

<span data-ttu-id="ec408-159">`Enter-PSHostProcess` PowerShell をホストしているプロセスのみを入力できます。</span><span class="sxs-lookup"><span data-stu-id="ec408-159">`Enter-PSHostProcess` can enter only those processes that are hosting PowerShell.</span></span> <span data-ttu-id="ec408-160">つまり、PowerShell エンジンが読み込まれています。</span><span class="sxs-lookup"><span data-stu-id="ec408-160">That is, they have loaded the PowerShell engine.</span></span>

<span data-ttu-id="ec408-161">プロセス内からプロセスを終了するには、「 **exit** 」と入力し <kbd>、enter キーを押します。</kbd></span><span class="sxs-lookup"><span data-stu-id="ec408-161">To exit a process from within the process, type **exit** , and then press <kbd>Enter</kbd>.</span></span>

<span data-ttu-id="ec408-162">PowerShell 7.1 より前では、SSH 経由のリモート処理は、次ホップのリモート セッションをサポートしていませんでした。</span><span class="sxs-lookup"><span data-stu-id="ec408-162">Prior to PowerShell 7.1, remoting over SSH did not support second-hop remote sessions.</span></span> <span data-ttu-id="ec408-163">この機能は、WinRM を使用したセッションに限定されていました。</span><span class="sxs-lookup"><span data-stu-id="ec408-163">This capability was limited to sessions using WinRM.</span></span> <span data-ttu-id="ec408-164">PowerShell 7.1 を使用すると、任意の対話型リモート セッション内で `Enter-PSSession` と `Enter-PSHostProcess` が機能します。</span><span class="sxs-lookup"><span data-stu-id="ec408-164">PowerShell 7.1 allows `Enter-PSSession` and `Enter-PSHostProcess` to work from within any interactive remote session.</span></span>

## <span data-ttu-id="ec408-165">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ec408-165">RELATED LINKS</span></span>

[<span data-ttu-id="ec408-166">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="ec408-166">Exit-PSHostProcess</span></span>](Exit-PSHostProcess.md)

[<span data-ttu-id="ec408-167">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="ec408-167">Get-PSHostProcessInfo</span></span>](Get-PSHostProcessInfo.md)

