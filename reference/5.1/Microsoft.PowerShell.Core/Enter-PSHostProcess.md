---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pshostprocess?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSHostProcess
ms.openlocfilehash: 56b8cef1911d1365f9568483921bfb49fbc32451
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212072"
---
# <span data-ttu-id="488e2-103">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="488e2-103">Enter-PSHostProcess</span></span>

## <span data-ttu-id="488e2-104">概要</span><span class="sxs-lookup"><span data-stu-id="488e2-104">SYNOPSIS</span></span>
<span data-ttu-id="488e2-105">ローカルプロセスを使用して、対話型セッションに接続して入力します。</span><span class="sxs-lookup"><span data-stu-id="488e2-105">Connects to and enters into an interactive session with a local process.</span></span>

## <span data-ttu-id="488e2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="488e2-106">SYNTAX</span></span>

### <span data-ttu-id="488e2-107">ProcessIdParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="488e2-107">ProcessIdParameterSet (Default)</span></span>

```
Enter-PSHostProcess [-Id] <Int32> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="488e2-108">ProcessParameterSet</span><span class="sxs-lookup"><span data-stu-id="488e2-108">ProcessParameterSet</span></span>

```
Enter-PSHostProcess [-Process] <Process> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="488e2-109">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="488e2-109">ProcessNameParameterSet</span></span>

```
Enter-PSHostProcess [-Name] <String> [[-AppDomainName] <String>] [<CommonParameters>]
```

### <span data-ttu-id="488e2-110">PSHostProcessInfoParameterSet</span><span class="sxs-lookup"><span data-stu-id="488e2-110">PSHostProcessInfoParameterSet</span></span>

```
Enter-PSHostProcess [-HostProcessInfo] <PSHostProcessInfo> [[-AppDomainName] <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="488e2-111">Description</span><span class="sxs-lookup"><span data-stu-id="488e2-111">DESCRIPTION</span></span>

<span data-ttu-id="488e2-112">`Enter-PSHostProcess`コマンドレットは、ローカルプロセスを使用して対話型セッションに接続し、それに入力します。</span><span class="sxs-lookup"><span data-stu-id="488e2-112">The `Enter-PSHostProcess` cmdlet connects to and enters into an interactive session with a local process.</span></span>

<span data-ttu-id="488e2-113">PowerShell をホストする新しいプロセスを作成し、リモートセッションを実行する代わりに、既に PowerShell を実行している既存のプロセスで、リモートの対話型セッションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="488e2-113">Instead of creating a new process to host PowerShell and run a remote session, the remote, interactive session is run in an existing process that is already running PowerShell.</span></span> <span data-ttu-id="488e2-114">指定されたプロセスでリモートセッションを操作する場合は、実行中の実行空間を列挙し、またはのいずれかを実行してデバッグする実行空間を選択でき `Debug-Runspace` `Enable-RunspaceDebug` ます。</span><span class="sxs-lookup"><span data-stu-id="488e2-114">When you are interacting with a remote session on a specified process, you can enumerate running runspaces, and then select a runspace to debug by running either `Debug-Runspace` or `Enable-RunspaceDebug`.</span></span>

<span data-ttu-id="488e2-115">入力するプロセスは、PowerShell (System.Management.Automation.dll) をホストしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="488e2-115">The process that you want to enter must be hosting PowerShell (System.Management.Automation.dll).</span></span>
<span data-ttu-id="488e2-116">プロセスが検出されたコンピューターの Administrators グループのメンバーであるか、またはプロセスを開始したスクリプトを実行しているユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="488e2-116">You must be either a member of the Administrators group on the computer on which the process is found, or you must be the user who is running the script that started the process.</span></span>

<span data-ttu-id="488e2-117">デバッグする実行空間を選択すると、現在コマンドを実行しているか、デバッガーで停止している場合、リモートデバッグセッションが実行空間に対して開かれます。</span><span class="sxs-lookup"><span data-stu-id="488e2-117">After you have selected a runspace to debug, a remote debug session is opened for the runspace if it is either currently running a command or is stopped in the debugger.</span></span> <span data-ttu-id="488e2-118">その後、他のリモートセッションスクリプトをデバッグする場合と同じ方法で、実行空間スクリプトをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="488e2-118">You can then debug the runspace script in the same way you would debug other remote session scripts.</span></span>

<span data-ttu-id="488e2-119">デバッグセッションからデタッチした後、プロセスとの対話型セッションを終了するには、exit を2回実行します。または、既存のデバッガーの quit コマンドを実行して、スクリプトの実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="488e2-119">Detach from a debugging session, and then the interactive session with the process, by running exit twice, or stop script execution by running the existing debugger quit command.</span></span>

<span data-ttu-id="488e2-120">**Name** パラメーターを使用してプロセスを指定し、指定した名前のプロセスが1つだけ見つかった場合は、プロセスが入力されます。</span><span class="sxs-lookup"><span data-stu-id="488e2-120">If you specify a process by using the **Name** parameter, and there is only one process found with the specified name, the process is entered.</span></span> <span data-ttu-id="488e2-121">指定された名前を持つ複数のプロセスが見つかった場合、PowerShell はエラーを返し、指定された名前を持つすべてのプロセスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="488e2-121">If more than one process with the specified name is found, PowerShell returns an error, and lists all processes found with the specified name.</span></span>

<span data-ttu-id="488e2-122">リモートコンピューター上のプロセスへのアタッチをサポートするために、 `Enter-PSHostProcess` 指定したリモートコンピューターでコマンドレットが有効になります。これにより、リモート PowerShell セッション内のローカルプロセスにアタッチできるようになります。</span><span class="sxs-lookup"><span data-stu-id="488e2-122">To support attaching to processes on remote computers, the `Enter-PSHostProcess` cmdlet is enabled in a specified remote computer, so that you can attach to a local process within a remote PowerShell session.</span></span>

## <span data-ttu-id="488e2-123">例</span><span class="sxs-lookup"><span data-stu-id="488e2-123">EXAMPLES</span></span>

### <span data-ttu-id="488e2-124">例 1: PowerShell ISE プロセス内の実行空間のデバッグを開始する</span><span class="sxs-lookup"><span data-stu-id="488e2-124">Example 1: Start debugging a runspace within the PowerShell ISE process</span></span>

<span data-ttu-id="488e2-125">この例では、 `Enter-PSHostProcess` powershell コンソール内からを実行して、POWERSHELL ISE プロセスに入ります。</span><span class="sxs-lookup"><span data-stu-id="488e2-125">In this example, you run `Enter-PSHostProcess` from within the PowerShell console to enter the PowerShell ISE process.</span></span> <span data-ttu-id="488e2-126">生成された対話型セッションでは、を実行してデバッグする実行空間を見つけて、実行 `Get-Runspace` 空間をデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="488e2-126">In the resulting interactive session, you can find a runspace that you want to debug by running `Get-Runspace`, and then debug the runspace.</span></span>

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

## <span data-ttu-id="488e2-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="488e2-127">PARAMETERS</span></span>

### <span data-ttu-id="488e2-128">-AppDomainName</span><span class="sxs-lookup"><span data-stu-id="488e2-128">-AppDomainName</span></span>

<span data-ttu-id="488e2-129">省略した場合に接続するアプリケーションドメイン名を指定します。 **Defaultappdomain** を使用します。</span><span class="sxs-lookup"><span data-stu-id="488e2-129">Specifies an application domain name to connect to if omitted, uses **DefaultAppDomain** .</span></span> <span data-ttu-id="488e2-130">`Get-PSHostProcessInfo`アプリケーションドメイン名を表示するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="488e2-130">Use `Get-PSHostProcessInfo` to display the application domain names.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: DefaultAppDomain
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="488e2-131">-HostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="488e2-131">-HostProcessInfo</span></span>

<span data-ttu-id="488e2-132">PowerShell を使用して接続できる **get-pshostprocessinfo** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="488e2-132">Specifies a **PSHostProcessInfo** object that can be connected to with PowerShell.</span></span> <span data-ttu-id="488e2-133">`Get-PSHostProcessInfo`オブジェクトを取得するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="488e2-133">Use `Get-PSHostProcessInfo` to get the object.</span></span>

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

### <span data-ttu-id="488e2-134">-Id</span><span class="sxs-lookup"><span data-stu-id="488e2-134">-Id</span></span>

<span data-ttu-id="488e2-135">プロセス ID を指定してプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="488e2-135">Specifies a process by the process ID.</span></span> <span data-ttu-id="488e2-136">プロセス ID を取得するには、 `Get-Process` コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="488e2-136">To get a process ID, run the `Get-Process` cmdlet.</span></span>

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

### <span data-ttu-id="488e2-137">-Name</span><span class="sxs-lookup"><span data-stu-id="488e2-137">-Name</span></span>

<span data-ttu-id="488e2-138">プロセス名でプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="488e2-138">Specifies a process by the process name.</span></span> <span data-ttu-id="488e2-139">プロセス名を取得するには、 `Get-Process` コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="488e2-139">To get a process name, run the `Get-Process` cmdlet.</span></span> <span data-ttu-id="488e2-140">また、タスクマネージャーでプロセスの [プロパティ] ダイアログボックスからプロセス名を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="488e2-140">You can also get process names from the Properties dialog box of a process in Task Manager.</span></span>

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

### <span data-ttu-id="488e2-141">-Process</span><span class="sxs-lookup"><span data-stu-id="488e2-141">-Process</span></span>

<span data-ttu-id="488e2-142">プロセスオブジェクトによってプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="488e2-142">Specifies a process by the process object.</span></span> <span data-ttu-id="488e2-143">このパラメーターを使用する最も簡単な方法は、 `Get-Process` 変数に入力するプロセスを返すコマンドの結果を保存し、その変数をこのパラメーターの値として指定することです。</span><span class="sxs-lookup"><span data-stu-id="488e2-143">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

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

### <span data-ttu-id="488e2-144">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="488e2-144">CommonParameters</span></span>

<span data-ttu-id="488e2-145">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="488e2-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="488e2-146">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="488e2-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="488e2-147">入力</span><span class="sxs-lookup"><span data-stu-id="488e2-147">INPUTS</span></span>

### <span data-ttu-id="488e2-148">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="488e2-148">System.Diagnostics.Process</span></span>

## <span data-ttu-id="488e2-149">出力</span><span class="sxs-lookup"><span data-stu-id="488e2-149">OUTPUTS</span></span>

## <span data-ttu-id="488e2-150">注</span><span class="sxs-lookup"><span data-stu-id="488e2-150">NOTES</span></span>

<span data-ttu-id="488e2-151">`Enter-PSHostProcess` コマンドを実行している PowerShell セッションのプロセスを入力できません。</span><span class="sxs-lookup"><span data-stu-id="488e2-151">`Enter-PSHostProcess` cannot enter the process of the PowerShell session in which you are running the command.</span></span> <span data-ttu-id="488e2-152">ただし、別の PowerShell セッションのプロセスや、を実行しているセッションと同時に実行されている PowerShell ISE セッションを入力することができ `Enter-PSHostProcess` ます。</span><span class="sxs-lookup"><span data-stu-id="488e2-152">You can, however, enter the process of another PowerShell session, or a PowerShell ISE session that is running at the same time as the session in which you are running `Enter-PSHostProcess`.</span></span>

<span data-ttu-id="488e2-153">`Enter-PSHostProcess` PowerShell をホストしているプロセスのみを入力できます。</span><span class="sxs-lookup"><span data-stu-id="488e2-153">`Enter-PSHostProcess` can enter only those processes that are hosting PowerShell.</span></span> <span data-ttu-id="488e2-154">つまり、PowerShell エンジンが読み込まれています。</span><span class="sxs-lookup"><span data-stu-id="488e2-154">That is, they have loaded the PowerShell engine.</span></span>

<span data-ttu-id="488e2-155">プロセス内からプロセスを終了するには、「 **exit** 」と入力し <kbd>、enter キーを押します。</kbd></span><span class="sxs-lookup"><span data-stu-id="488e2-155">To exit a process from within the process, type **exit** , and then press <kbd>Enter</kbd>.</span></span>

## <span data-ttu-id="488e2-156">関連リンク</span><span class="sxs-lookup"><span data-stu-id="488e2-156">RELATED LINKS</span></span>

[<span data-ttu-id="488e2-157">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="488e2-157">Exit-PSHostProcess</span></span>](Exit-PSHostProcess.md)

[<span data-ttu-id="488e2-158">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="488e2-158">Get-PSHostProcessInfo</span></span>](Get-PSHostProcessInfo.md)
