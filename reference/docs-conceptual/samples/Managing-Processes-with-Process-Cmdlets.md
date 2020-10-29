---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: Process コマンドレットによるプロセスの管理
description: PowerShell には、ローカル コンピューター上およびリモート コンピューター上のプロセスを管理するのに役立つコマンドレットがいくつか用意されています。
ms.openlocfilehash: 977a3459eeac22536341753ccd59357d718745f2
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500438"
---
# <a name="managing-processes-with-process-cmdlets"></a><span data-ttu-id="7d8db-104">Process コマンドレットによるプロセスの管理</span><span class="sxs-lookup"><span data-stu-id="7d8db-104">Managing Processes with Process Cmdlets</span></span>

<span data-ttu-id="7d8db-105">Windows PowerShell で Process コマンドレットを使用して、Windows PowerShell のローカル プロセスおよびリモート プロセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="7d8db-105">You can use the Process cmdlets in Windows PowerShell to manage local and remote processes in Windows PowerShell.</span></span>

## <a name="getting-processes-get-process"></a><span data-ttu-id="7d8db-106">プロセスの取得 (Get-Process)</span><span class="sxs-lookup"><span data-stu-id="7d8db-106">Getting Processes (Get-Process)</span></span>

<span data-ttu-id="7d8db-107">ローカル コンピューターで実行されているプロセスを取得するには、パラメーターを指定せずに **Get-Process** を実行します。</span><span class="sxs-lookup"><span data-stu-id="7d8db-107">To get the processes running on the local computer, run a **Get-Process** with no parameters.</span></span>

<span data-ttu-id="7d8db-108">特定のプロセスを取得するには、プロセス名またはプロセス ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="7d8db-108">You can get particular processes by specifying their process names or process IDs.</span></span> <span data-ttu-id="7d8db-109">次のコマンドを実行すると、アイドル状態のプロセスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="7d8db-109">The following command gets the Idle process:</span></span>

```
PS> Get-Process -id 0

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
      0       0        0         16     0               0 Idle
```

<span data-ttu-id="7d8db-110">場合によっては、コマンドレットからデータが返されないこともあります。しかし、 **Get-Process** で ProcessId を使用してプロセスを指定した場合は、通常、実行中の既知のプロセスを取得することが目的であるため、一致するプロセスが見つからないときはエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="7d8db-110">Although it is normal for cmdlets to return no data in some situations, when you specify a process by its ProcessId, **Get-Process** generates an error if it finds no matches, because the usual intent is to retrieve a known running process.</span></span> <span data-ttu-id="7d8db-111">指定された ID と一致するプロセスが存在しない場合、その ID が間違っているか、プロセスが既に終了している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d8db-111">If there is no process with that Id, it is likely that the Id is incorrect or that the process of interest has already exited:</span></span>

```
PS> Get-Process -Id 99

Get-Process : No process with process ID 99 was found.
At line:1 char:12
+ Get-Process  <<<< -Id 99
```

<span data-ttu-id="7d8db-112">Get-Process コマンドレットの Name パラメーターを使用すると、プロセスのサブセットをプロセス名で指定できます。</span><span class="sxs-lookup"><span data-stu-id="7d8db-112">You can use the Name parameter of the Get-Process cmdlet to specify a subset of processes based on the process name.</span></span> <span data-ttu-id="7d8db-113">Name パラメーターでは、コンマ区切り一覧を使用して複数の名前を指定できます。また、ワイルドカードを使用できるため、名前のパターンを入力できます。</span><span class="sxs-lookup"><span data-stu-id="7d8db-113">The Name parameter can take multiple names in a comma-separated list and it supports the use of wildcards, so you can type name patterns.</span></span>

<span data-ttu-id="7d8db-114">たとえば、次のコマンドでは、名前が "ex" で始まるプロセスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="7d8db-114">For example, the following command gets process whose names begin with "ex."</span></span>

```
PS> Get-Process -Name ex*

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    234       7     5572      12484   134     2.98   1684 EXCEL
    555      15    34500      12384   134   105.25    728 explorer
```

<span data-ttu-id="7d8db-115">.NET System.Diagnostics.Process クラスは、Windows PowerShell のプロセスの基礎となるクラスです。そのため、Windows PowerShell のプロセスには、System.Diagnostics.Process の表記規則の一部が使用されています。</span><span class="sxs-lookup"><span data-stu-id="7d8db-115">Because the .NET System.Diagnostics.Process class is the foundation for Windows PowerShell processes, it follows some of the conventions used by System.Diagnostics.Process.</span></span> <span data-ttu-id="7d8db-116">これらの規則の 1 つとして、実行可能ファイルのプロセス名の最後に ".exe" は付きません。</span><span class="sxs-lookup"><span data-stu-id="7d8db-116">One of those conventions is that the process name for an executable never includes the ".exe" at the end of the executable name.</span></span>

<span data-ttu-id="7d8db-117">**Get-Process** の Name パラメーターには、複数の値を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="7d8db-117">**Get-Process** also accepts multiple values for the Name parameter.</span></span>

```
PS> Get-Process -Name exp*,power*

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    540      15    35172      48148   141    88.44    408 explorer
    605       9    30668      29800   155     7.11   3052 powershell
```

<span data-ttu-id="7d8db-118">Get-Process の ComputerName パラメーターを使用すると、リモート コンピューター上のプロセスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="7d8db-118">You can use the ComputerName parameter of Get-Process to get processes on remote computers.</span></span> <span data-ttu-id="7d8db-119">たとえば、次のコマンドでは、ローカル コンピューター ("localhost" で表す) と 2 台のリモート コンピューターの PowerShell プロセスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="7d8db-119">For example, the following command gets the PowerShell processes on the local computer (represented by "localhost") and on two remote computers.</span></span>

```
PS> Get-Process -Name PowerShell -ComputerName localhost, Server01, Server02

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    258       8    29772      38636   130            3700 powershell
    398      24    75988      76800   572            5816 powershell
    605       9    30668      29800   155     7.11   3052 powershell
```

<span data-ttu-id="7d8db-120">ここではコンピューターの名前は表示されませんが、Get-Process から返されたプロセス オブジェクトの MachineName プロパティに格納されています。</span><span class="sxs-lookup"><span data-stu-id="7d8db-120">The computer names are not evident in this display, but they are stored in the MachineName property of the process objects that Get-Process returns.</span></span> <span data-ttu-id="7d8db-121">次のコマンドでは、Format-Table コマンドレットを使用して、プロセス オブジェクトのプロセス ID、ProcessName、および MachineName (ComputerName) の各プロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="7d8db-121">The following command uses the Format-Table cmdlet to display the process ID, ProcessName and MachineName (ComputerName) properties of the process objects.</span></span>

```
PS> Get-Process -Name PowerShell -ComputerName localhost, Server01, Server01 |
  Format-Table -Property ID, ProcessName, MachineName

  Id ProcessName MachineName
  -- ----------- -----------
3700 powershell  Server01
3052 powershell  Server02
5816 powershell  localhost
```

<span data-ttu-id="7d8db-122">より複雑なこのコマンドは、Get-Process の標準の表示に MachineName プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="7d8db-122">This more complex command adds the MachineName property to the standard Get-Process display.</span></span>

```
PS> Get-Process powershell -ComputerName localhost, Server01, Server02 |
    Format-Table -Property Handles,
        @{Label="NPM(K)";Expression={[int]($_.NPM/1024)}},
        @{Label="PM(K)";Expression={[int]($_.PM/1024)}},
        @{Label="WS(K)";Expression={[int]($_.WS/1024)}},
        @{Label="VM(M)";Expression={[int]($_.VM/1MB)}},
        @{Label="CPU(s)";Expression={if ($_.CPU -ne $()){$_.CPU.ToString("N")}}},
        Id, ProcessName, MachineName -auto

Handles  NPM(K)  PM(K) WS(K) VM(M) CPU(s)  Id ProcessName  MachineName
-------  ------  ----- ----- ----- ------  -- -----------  -----------
    258       8  29772 38636   130         3700 powershell Server01
    398      24  75988 76800   572         5816 powershell localhost
    605       9  30668 29800   155 7.11    3052 powershell Server02
```

## <a name="stopping-processes-stop-process"></a><span data-ttu-id="7d8db-123">プロセスの停止 (Stop-Process)</span><span class="sxs-lookup"><span data-stu-id="7d8db-123">Stopping Processes (Stop-Process)</span></span>

<span data-ttu-id="7d8db-124">Windows PowerShell では、さまざまな方法でプロセスを一覧表示できますが、プロセスの停止についてはどうでしょうか。</span><span class="sxs-lookup"><span data-stu-id="7d8db-124">Windows PowerShell gives you flexibility for listing processes, but what about stopping a process?</span></span>

<span data-ttu-id="7d8db-125">**Stop-Process** コマンドレットでは、停止するプロセスを Name または Id で指定できます。</span><span class="sxs-lookup"><span data-stu-id="7d8db-125">The **Stop-Process** cmdlet takes a Name or Id to specify a process you want to stop.</span></span> <span data-ttu-id="7d8db-126">プロセスを停止できるかどうかは、ユーザーのアクセス許可によって異なります。</span><span class="sxs-lookup"><span data-stu-id="7d8db-126">Your ability to stop processes depends on your permissions.</span></span> <span data-ttu-id="7d8db-127">停止することのできないプロセスもあります。</span><span class="sxs-lookup"><span data-stu-id="7d8db-127">Some processes cannot be stopped.</span></span> <span data-ttu-id="7d8db-128">たとえば、アイドル状態のプロセスを停止しようとすると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="7d8db-128">For example, if you try to stop the idle process, you get an error:</span></span>

```
PS> Stop-Process -Name Idle
Stop-Process : Process 'Idle (0)' cannot be stopped due to the following error:
 Access is denied
At line:1 char:13
+ Stop-Process  <<<< -Name Idle
```

<span data-ttu-id="7d8db-129">**Confirm** パラメーターを使用して、確認メッセージを強制的に表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="7d8db-129">You can also force prompting with the **Confirm** parameter.</span></span> <span data-ttu-id="7d8db-130">ワイルドカードを使ってプロセス名を指定する場合、停止する必要のないプロセスに誤って一致する可能性があるため、このパラメーターは特に便利です。</span><span class="sxs-lookup"><span data-stu-id="7d8db-130">This parameter is particularly useful if you use a wildcard when specifying the process name, because you may accidentally match some processes you do not want to stop:</span></span>

```
PS> Stop-Process -Name t*,e* -Confirm
Confirm
Are you sure you want to perform this action?
Performing operation "Stop-Process" on Target "explorer (408)".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):n
Confirm
Are you sure you want to perform this action?
Performing operation "Stop-Process" on Target "taskmgr (4072)".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):n
```

<span data-ttu-id="7d8db-131">オブジェクトのフィルター処理コマンドレットを使用すれば、複雑なプロセス操作を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="7d8db-131">Complex process manipulation is possible by using some of the object filtering cmdlets.</span></span> <span data-ttu-id="7d8db-132">Process オブジェクトには、応答がない場合に True を返す Responding プロパティがあります。したがって、次のコマンドを使用すると、応答のないアプリケーションをすべて停止できます。</span><span class="sxs-lookup"><span data-stu-id="7d8db-132">Because a Process object has a Responding property that is true when it is no longer responding, you can stop all nonresponsive applications with the following command:</span></span>

```powershell
Get-Process | Where-Object -FilterScript {$_.Responding -eq $false} | Stop-Process
```

<span data-ttu-id="7d8db-133">他の状況でも、これと同じアプローチを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d8db-133">You can use the same approach in other situations.</span></span> <span data-ttu-id="7d8db-134">たとえば、あるアプリケーションを起動すると、補助的なアプリケーションが自動的に実行され、通知領域に表示されるとします。</span><span class="sxs-lookup"><span data-stu-id="7d8db-134">For example, suppose a secondary notification area application automatically runs when users start another application.</span></span> <span data-ttu-id="7d8db-135">このとき、ターミナル サービスのセッションで補助的なアプリケーションが正しく起動しないことがわかりました。しかし、物理的なコンピューター コンソールで実行されているセッションでは起動したままにしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d8db-135">You may find that this does not work correctly in Terminal Services sessions, but you still want to keep it in sessions that run on the physical computer console.</span></span> <span data-ttu-id="7d8db-136">物理的なコンピューター デスクトップに関連付けられたセッションには、常にセッション ID として 0 が割り当てられます。したがって、 **Where-Object** およびプロセスの **SessionId** を使用することで、その他のセッションに属するプロセスのすべてのインスタンスを停止できます。</span><span class="sxs-lookup"><span data-stu-id="7d8db-136">Sessions connected to the physical computer desktop always have a session ID of 0, so you can stop all instances of the process that are in other sessions by using **Where-Object** and the process, **SessionId** :</span></span>

```powershell
Get-Process -Name BadApp | Where-Object -FilterScript {$_.SessionId -neq 0} | Stop-Process
```

<span data-ttu-id="7d8db-137">Stop-Process コマンドレットには、ComputerName パラメーターがありません。</span><span class="sxs-lookup"><span data-stu-id="7d8db-137">The Stop-Process cmdlet does not have a ComputerName parameter.</span></span> <span data-ttu-id="7d8db-138">そのため、リモート コンピューター上でプロセスを停止するコマンドを実行するには、Invoke-Command コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d8db-138">Therefore, to run a stop process command on a remote computer, you need to use the Invoke-Command cmdlet.</span></span> <span data-ttu-id="7d8db-139">たとえば、リモート コンピューター Server01 上で PowerShell プロセスを停止するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7d8db-139">For example, to stop the PowerShell process on the Server01 remote computer, type:</span></span>

```powershell
Invoke-Command -ComputerName Server01 {Stop-Process Powershell}
```

## <a name="stopping-all-other-windows-powershell-sessions"></a><span data-ttu-id="7d8db-140">他のすべての Windows PowerShell セッションの停止</span><span class="sxs-lookup"><span data-stu-id="7d8db-140">Stopping All Other Windows PowerShell Sessions</span></span>

<span data-ttu-id="7d8db-141">現在のセッションを除いて、実行中のすべての Windows PowerShell セッションを停止できると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7d8db-141">It may occasionally be useful to be able to stop all running Windows PowerShell sessions other than the current session.</span></span> <span data-ttu-id="7d8db-142">特定のセッションで大量のリソースが消費されていたり、セッションがアクセスできない状態になっている場合 (リモートから実行されていたり、別のデスクトップ セッションで使用されている場合など)、そのプロセスを直接停止できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="7d8db-142">If a session is using too many resources or is inaccessible (it may be running remotely or in another desktop session), you may not be able to directly stop it.</span></span> <span data-ttu-id="7d8db-143">しかし、実行中のすべてのセッションを停止しようとすると、現在のセッションまで停止されてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d8db-143">If you try to stop all running sessions, however, the current session may be terminated instead.</span></span>

<span data-ttu-id="7d8db-144">Windows PowerShell の各セッションには、Windows PowerShell プロセスの ID を保持する環境変数 PID が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="7d8db-144">Each Windows PowerShell session has an environment variable PID that contains the Id of the Windows PowerShell process.</span></span> <span data-ttu-id="7d8db-145">$PID と各セッションの ID を照合することによって、異なる ID を持つ Windows PowerShell セッションだけを強制終了できます。これは、次のパイプライン コマンドで実現できます。また、 **PassThru** パラメーターを使用しているため、強制終了されたセッションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d8db-145">You can check the $PID against the Id of each session and terminate only Windows PowerShell sessions that have a different Id. The following pipeline command does this and returns the list of terminated sessions (because of the use of the **PassThru** parameter):</span></span>

```
PS> Get-Process -Name powershell | Where-Object -FilterScript {$_.Id -ne $PID} | Stop-Process -PassThru

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    334       9    23348      29136   143     1.03    388 powershell
    304       9    23152      29040   143     1.03    632 powershell
    302       9    20916      26804   143     1.03   1116 powershell
    335       9    25656      31412   143     1.09   3452 powershell
    303       9    23156      29044   143     1.05   3608 powershell
    287       9    21044      26928   143     1.02   3672 powershell
```

## <a name="starting-debugging-and-waiting-for-processes"></a><span data-ttu-id="7d8db-146">プロセスの開始、デバッグ、待機</span><span class="sxs-lookup"><span data-stu-id="7d8db-146">Starting, Debugging, and Waiting for Processes</span></span>

<span data-ttu-id="7d8db-147">Windows PowerShell には、プロセスを開始 (または再開) するためのコマンドレット、プロセスのデバッグ用コマンドレット、コマンドを実行する前にプロセスが完了するまで待機するためのコマンドレットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7d8db-147">Windows PowerShell also comes with cmdlets to start (or restart), debug a process, and wait for a process to complete before running a command.</span></span> <span data-ttu-id="7d8db-148">これらのコマンドレットについては、各コマンドレットのヘルプ トピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7d8db-148">For information about these cmdlets, see the cmdlet help topic for each cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d8db-149">参照</span><span class="sxs-lookup"><span data-stu-id="7d8db-149">See Also</span></span>

- [<span data-ttu-id="7d8db-150">Get-Process</span><span class="sxs-lookup"><span data-stu-id="7d8db-150">Get-Process</span></span>](/powershell/module/Microsoft.PowerShell.Management/Get-Process)
- [<span data-ttu-id="7d8db-151">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="7d8db-151">Stop-Process</span></span>](/powershell/module/Microsoft.PowerShell.Management/Stop-Process)
- [<span data-ttu-id="7d8db-152">Start-Process</span><span class="sxs-lookup"><span data-stu-id="7d8db-152">Start-Process</span></span>](/powershell/module/Microsoft.PowerShell.Management/Start-Process)
- [<span data-ttu-id="7d8db-153">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="7d8db-153">Wait-Process</span></span>](/powershell/module/Microsoft.PowerShell.Management/Wait-Process)
- [<span data-ttu-id="7d8db-154">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="7d8db-154">Debug-Process</span></span>](/powershell/module/Microsoft.PowerShell.Management/Debug-Process)
- [<span data-ttu-id="7d8db-155">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="7d8db-155">Invoke-Command</span></span>](/powershell/module/Microsoft.PowerShell.Core/Invoke-Command)
