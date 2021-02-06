---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pshostprocess?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSHostProcess
ms.openlocfilehash: 85cbc9d012781873dddaf2a7d220a0e478dcbda2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602619"
---
# <span data-ttu-id="c5cd7-102">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="c5cd7-102">Enter-PSHostProcess</span></span>

## <span data-ttu-id="c5cd7-103">概要</span><span class="sxs-lookup"><span data-stu-id="c5cd7-103">SYNOPSIS</span></span>
<span data-ttu-id="c5cd7-104">ローカルプロセスを使用して、対話型セッションに接続して入力します。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-104">Connects to and enters into an interactive session with a local process.</span></span>

## <span data-ttu-id="c5cd7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c5cd7-105">SYNTAX</span></span>

### <span data-ttu-id="c5cd7-106">ProcessIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="c5cd7-106">ProcessIdParameterSet (Default)</span></span>

```
Enter-PSHostProcess [-Id] <Int32> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="c5cd7-107">ProcessParameterSet</span><span class="sxs-lookup"><span data-stu-id="c5cd7-107">ProcessParameterSet</span></span>

```
Enter-PSHostProcess [-Process] <Process> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="c5cd7-108">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="c5cd7-108">ProcessNameParameterSet</span></span>

```
Enter-PSHostProcess [-Name] <String> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="c5cd7-109">PSHostProcessInfoParameterSet</span><span class="sxs-lookup"><span data-stu-id="c5cd7-109">PSHostProcessInfoParameterSet</span></span>

```
Enter-PSHostProcess [-HostProcessInfo] <PSHostProcessInfo> [[-AppDomainName] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="c5cd7-110">PipeNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="c5cd7-110">PipeNameParameterSet</span></span>

```
Enter-PSHostProcess -CustomPipeName <String> [<CommonParameters>]
```

## <span data-ttu-id="c5cd7-111">Description</span><span class="sxs-lookup"><span data-stu-id="c5cd7-111">DESCRIPTION</span></span>

<span data-ttu-id="c5cd7-112">`Enter-PSHostProcess`コマンドレットは、ローカルプロセスを使用して対話型セッションに接続し、それに入力します。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-112">The `Enter-PSHostProcess` cmdlet connects to and enters into an interactive session with a local process.</span></span> <span data-ttu-id="c5cd7-113">PowerShell 6.2 以降では、このコマンドレットは Windows 以外のプラットフォームでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-113">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

<span data-ttu-id="c5cd7-114">PowerShell をホストする新しいプロセスを作成し、リモートセッションを実行する代わりに、既に PowerShell を実行している既存のプロセスで、リモートの対話型セッションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-114">Instead of creating a new process to host PowerShell and run a remote session, the remote, interactive session is run in an existing process that is already running PowerShell.</span></span> <span data-ttu-id="c5cd7-115">指定されたプロセスでリモートセッションを操作する場合は、実行中の実行空間を列挙し、またはのいずれかを実行してデバッグする実行空間を選択でき `Debug-Runspace` `Enable-RunspaceDebug` ます。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-115">When you are interacting with a remote session on a specified process, you can enumerate running runspaces, and then select a runspace to debug by running either `Debug-Runspace` or `Enable-RunspaceDebug`.</span></span>

<span data-ttu-id="c5cd7-116">入力するプロセスは、PowerShell (System.Management.Automation.dll) をホストしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-116">The process that you want to enter must be hosting PowerShell (System.Management.Automation.dll).</span></span>
<span data-ttu-id="c5cd7-117">プロセスが検出されたコンピューターの Administrators グループのメンバーであるか、またはプロセスを開始したスクリプトを実行しているユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-117">You must be either a member of the Administrators group on the computer on which the process is found, or you must be the user who is running the script that started the process.</span></span>

<span data-ttu-id="c5cd7-118">デバッグする実行空間を選択すると、現在コマンドを実行しているか、デバッガーで停止している場合、リモートデバッグセッションが実行空間に対して開かれます。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-118">After you have selected a runspace to debug, a remote debug session is opened for the runspace if it is either currently running a command or is stopped in the debugger.</span></span> <span data-ttu-id="c5cd7-119">その後、他のリモートセッションスクリプトをデバッグする場合と同じ方法で、実行空間スクリプトをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-119">You can then debug the runspace script in the same way you would debug other remote session scripts.</span></span>

<span data-ttu-id="c5cd7-120">デバッグセッションからデタッチした後、プロセスとの対話型セッションを終了するには、exit を2回実行します。または、既存のデバッガーの quit コマンドを実行して、スクリプトの実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-120">Detach from a debugging session, and then the interactive session with the process, by running exit twice, or stop script execution by running the existing debugger quit command.</span></span>

<span data-ttu-id="c5cd7-121">**Name** パラメーターを使用してプロセスを指定し、指定した名前のプロセスが1つだけ見つかった場合は、プロセスが入力されます。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-121">If you specify a process by using the **Name** parameter, and there is only one process found with the specified name, the process is entered.</span></span> <span data-ttu-id="c5cd7-122">指定された名前を持つ複数のプロセスが見つかった場合、PowerShell はエラーを返し、指定された名前を持つすべてのプロセスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-122">If more than one process with the specified name is found, PowerShell returns an error, and lists all processes found with the specified name.</span></span>

<span data-ttu-id="c5cd7-123">リモートコンピューター上のプロセスへのアタッチをサポートするために、 `Enter-PSHostProcess` 指定したリモートコンピューターでコマンドレットが有効になります。これにより、リモート PowerShell セッション内のローカルプロセスにアタッチできるようになります。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-123">To support attaching to processes on remote computers, the `Enter-PSHostProcess` cmdlet is enabled in a specified remote computer, so that you can attach to a local process within a remote PowerShell session.</span></span>

## <span data-ttu-id="c5cd7-124">例</span><span class="sxs-lookup"><span data-stu-id="c5cd7-124">EXAMPLES</span></span>

### <span data-ttu-id="c5cd7-125">例 1: PowerShell ISE プロセス内の実行空間のデバッグを開始する</span><span class="sxs-lookup"><span data-stu-id="c5cd7-125">Example 1: Start debugging a runspace within the PowerShell ISE process</span></span>

<span data-ttu-id="c5cd7-126">この例では、 `Enter-PSHostProcess` powershell コンソール内からを実行して、POWERSHELL ISE プロセスに入ります。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-126">In this example, you run `Enter-PSHostProcess` from within the PowerShell console to enter the PowerShell ISE process.</span></span> <span data-ttu-id="c5cd7-127">生成された対話型セッションでは、を実行してデバッグする実行空間を見つけて、実行 `Get-Runspace` 空間をデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-127">In the resulting interactive session, you can find a runspace that you want to debug by running `Get-Runspace`, and then debug the runspace.</span></span>

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

## <span data-ttu-id="c5cd7-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c5cd7-128">PARAMETERS</span></span>

### <span data-ttu-id="c5cd7-129">-AppDomainName</span><span class="sxs-lookup"><span data-stu-id="c5cd7-129">-AppDomainName</span></span>

<span data-ttu-id="c5cd7-130">省略した場合に接続するアプリケーションドメイン名を指定します。 **Defaultappdomain** を使用します。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-130">Specifies an application domain name to connect to if omitted, uses **DefaultAppDomain**.</span></span> <span data-ttu-id="c5cd7-131">`Get-PSHostProcessInfo`アプリケーションドメイン名を表示するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-131">Use `Get-PSHostProcessInfo` to display the application domain names.</span></span>

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

### <span data-ttu-id="c5cd7-132">-HostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="c5cd7-132">-HostProcessInfo</span></span>

<span data-ttu-id="c5cd7-133">PowerShell を使用して接続できる **get-pshostprocessinfo** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-133">Specifies a **PSHostProcessInfo** object that can be connected to with PowerShell.</span></span> <span data-ttu-id="c5cd7-134">`Get-PSHostProcessInfo`オブジェクトを取得するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-134">Use `Get-PSHostProcessInfo` to get the object.</span></span>

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

### <span data-ttu-id="c5cd7-135">-Id</span><span class="sxs-lookup"><span data-stu-id="c5cd7-135">-Id</span></span>

<span data-ttu-id="c5cd7-136">プロセス ID を指定してプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-136">Specifies a process by the process ID.</span></span> <span data-ttu-id="c5cd7-137">プロセス ID を取得するには、 `Get-Process` コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-137">To get a process ID, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="c5cd7-138">-Name</span><span class="sxs-lookup"><span data-stu-id="c5cd7-138">-Name</span></span>

<span data-ttu-id="c5cd7-139">プロセス名でプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-139">Specifies a process by the process name.</span></span> <span data-ttu-id="c5cd7-140">プロセス名を取得するには、 `Get-Process` コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-140">To get a process name, run the `Get-Process` cmdlet.</span></span> <span data-ttu-id="c5cd7-141">また、タスクマネージャーでプロセスの [プロパティ] ダイアログボックスからプロセス名を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-141">You can also get process names from the Properties dialog box of a process in Task Manager.</span></span>

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

### <span data-ttu-id="c5cd7-142">-Process</span><span class="sxs-lookup"><span data-stu-id="c5cd7-142">-Process</span></span>

<span data-ttu-id="c5cd7-143">プロセスオブジェクトによってプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-143">Specifies a process by the process object.</span></span> <span data-ttu-id="c5cd7-144">このパラメーターを使用する最も簡単な方法は、 `Get-Process` 変数に入力するプロセスを返すコマンドの結果を保存し、その変数をこのパラメーターの値として指定することです。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-144">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

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

### <span data-ttu-id="c5cd7-145">-CustomPipeName</span><span class="sxs-lookup"><span data-stu-id="c5cd7-145">-CustomPipeName</span></span>

<span data-ttu-id="c5cd7-146">接続先のカスタム名前付きパイプ名を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-146">Gets or sets the custom named pipe name to connect to.</span></span> <span data-ttu-id="c5cd7-147">これは通常、と組み合わせて使用され `pwsh -CustomPipeName` ます。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-147">This is usually used in conjunction with `pwsh -CustomPipeName`.</span></span>

<span data-ttu-id="c5cd7-148">このパラメーターは、PowerShell 6.2 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-148">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="c5cd7-149">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c5cd7-149">CommonParameters</span></span>

<span data-ttu-id="c5cd7-150">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c5cd7-151">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-151">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c5cd7-152">入力</span><span class="sxs-lookup"><span data-stu-id="c5cd7-152">INPUTS</span></span>

### <span data-ttu-id="c5cd7-153">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="c5cd7-153">System.Diagnostics.Process</span></span>

## <span data-ttu-id="c5cd7-154">出力</span><span class="sxs-lookup"><span data-stu-id="c5cd7-154">OUTPUTS</span></span>

## <span data-ttu-id="c5cd7-155">注</span><span class="sxs-lookup"><span data-stu-id="c5cd7-155">NOTES</span></span>

<span data-ttu-id="c5cd7-156">`Enter-PSHostProcess` コマンドを実行している PowerShell セッションのプロセスを入力できません。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-156">`Enter-PSHostProcess` cannot enter the process of the PowerShell session in which you are running the command.</span></span> <span data-ttu-id="c5cd7-157">ただし、別の PowerShell セッションのプロセスや、を実行しているセッションと同時に実行されている PowerShell ISE セッションを入力することができ `Enter-PSHostProcess` ます。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-157">You can, however, enter the process of another PowerShell session, or a PowerShell ISE session that is running at the same time as the session in which you are running `Enter-PSHostProcess`.</span></span>

<span data-ttu-id="c5cd7-158">`Enter-PSHostProcess` PowerShell をホストしているプロセスのみを入力できます。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-158">`Enter-PSHostProcess` can enter only those processes that are hosting PowerShell.</span></span> <span data-ttu-id="c5cd7-159">つまり、PowerShell エンジンが読み込まれています。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-159">That is, they have loaded the PowerShell engine.</span></span>

<span data-ttu-id="c5cd7-160">プロセス内からプロセスを終了するには、「 **exit**」と入力し <kbd>、enter キーを押します。</kbd></span><span class="sxs-lookup"><span data-stu-id="c5cd7-160">To exit a process from within the process, type **exit**, and then press <kbd>Enter</kbd>.</span></span>

<span data-ttu-id="c5cd7-161">PowerShell 7.1 より前では、SSH 経由のリモート処理は、次ホップのリモート セッションをサポートしていませんでした。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-161">Prior to PowerShell 7.1, remoting over SSH did not support second-hop remote sessions.</span></span> <span data-ttu-id="c5cd7-162">この機能は、WinRM を使用したセッションに限定されていました。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-162">This capability was limited to sessions using WinRM.</span></span> <span data-ttu-id="c5cd7-163">PowerShell 7.1 を使用すると、任意の対話型リモート セッション内で `Enter-PSSession` と `Enter-PSHostProcess` が機能します。</span><span class="sxs-lookup"><span data-stu-id="c5cd7-163">PowerShell 7.1 allows `Enter-PSSession` and `Enter-PSHostProcess` to work from within any interactive remote session.</span></span>

## <span data-ttu-id="c5cd7-164">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c5cd7-164">RELATED LINKS</span></span>

[<span data-ttu-id="c5cd7-165">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="c5cd7-165">Exit-PSHostProcess</span></span>](Exit-PSHostProcess.md)

[<span data-ttu-id="c5cd7-166">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="c5cd7-166">Get-PSHostProcessInfo</span></span>](Get-PSHostProcessInfo.md)

