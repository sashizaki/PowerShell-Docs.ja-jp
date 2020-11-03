---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/debug-runspace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Runspace
ms.openlocfilehash: 1f347afe89ed63d64e8a8156b7259509800d5d24
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210088"
---
# <span data-ttu-id="5aa74-103">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="5aa74-103">Debug-Runspace</span></span>

## <span data-ttu-id="5aa74-104">概要</span><span class="sxs-lookup"><span data-stu-id="5aa74-104">SYNOPSIS</span></span>
<span data-ttu-id="5aa74-105">実行空間を使用して、対話型デバッグセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="5aa74-105">Starts an interactive debugging session with a runspace.</span></span>

## <span data-ttu-id="5aa74-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5aa74-106">SYNTAX</span></span>

### <span data-ttu-id="5aa74-107">RunspaceParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="5aa74-107">RunspaceParameterSet (Default)</span></span>

```
Debug-Runspace [-Runspace] <Runspace> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5aa74-108">NameParameterSet</span><span class="sxs-lookup"><span data-stu-id="5aa74-108">NameParameterSet</span></span>

```
Debug-Runspace [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5aa74-109">IdParameterSet</span><span class="sxs-lookup"><span data-stu-id="5aa74-109">IdParameterSet</span></span>

```
Debug-Runspace [-Id] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5aa74-110">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="5aa74-110">InstanceIdParameterSet</span></span>

```
Debug-Runspace [-InstanceId] <Guid> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5aa74-111">Description</span><span class="sxs-lookup"><span data-stu-id="5aa74-111">DESCRIPTION</span></span>

<span data-ttu-id="5aa74-112">`Debug-Runspace`コマンドレットは、ローカルまたはリモートのアクティブな実行空間を使用して、対話型デバッグセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="5aa74-112">The `Debug-Runspace` cmdlet starts an interactive debugging session with a local or remote active runspace.</span></span> <span data-ttu-id="5aa74-113">最初にを実行してデバッグする実行空間を見つけて、 `Get-Process` powershell に関連付けられているプロセスを見つけ、そのプロセス `Enter-PSHostProcess` にアタッチする **id** パラメーターで指定されたプロセス ID を使用して、 `Get-Runspace` powershell ホストプロセス内の実行空間を一覧表示することができます。</span><span class="sxs-lookup"><span data-stu-id="5aa74-113">You can find a runspace that you want to debug by first running `Get-Process` to find processes associated with PowerShell, then `Enter-PSHostProcess` with the process ID specified in the **Id** parameter to attach to the process, and then `Get-Runspace` to list runspaces within the PowerShell host process.</span></span>

<span data-ttu-id="5aa74-114">デバッグする実行空間を選択すると、実行空間で現在コマンドまたはスクリプトが実行されている場合、またはスクリプトがブレークポイントで停止した場合、PowerShell は実行空間に対してリモートデバッガーセッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="5aa74-114">After you have selected a runspace to debug, if the runspace is currently running a command or script, or if the script has stopped at a breakpoint, PowerShell opens a remote debugger session for the runspace.</span></span> <span data-ttu-id="5aa74-115">リモートセッションスクリプトがデバッグされるのと同じ方法で実行空間スクリプトをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="5aa74-115">You can debug the runspace script in the same way remote session scripts are debugged.</span></span>

<span data-ttu-id="5aa74-116">PowerShell ホストプロセスにアタッチできるのは、そのプロセスを実行しているコンピューターの管理者である場合、またはデバッグするスクリプトを実行している場合のみです。</span><span class="sxs-lookup"><span data-stu-id="5aa74-116">You can only attach to a PowerShell host process if you are an administrator on the computer that is running the process, or you are running the script that you want to debug.</span></span> <span data-ttu-id="5aa74-117">また、現在の PowerShell セッションを実行しているホストプロセスを入力することはできません。</span><span class="sxs-lookup"><span data-stu-id="5aa74-117">Also, you cannot enter the host process that is running the current PowerShell session.</span></span> <span data-ttu-id="5aa74-118">別の PowerShell セッションを実行しているホストプロセスのみを入力できます。</span><span class="sxs-lookup"><span data-stu-id="5aa74-118">You can only enter a host process that is running a different PowerShell session.</span></span>

## <span data-ttu-id="5aa74-119">例</span><span class="sxs-lookup"><span data-stu-id="5aa74-119">EXAMPLES</span></span>

### <span data-ttu-id="5aa74-120">例 1: リモートの実行空間をデバッグする</span><span class="sxs-lookup"><span data-stu-id="5aa74-120">Example 1: Debug a remote runspace</span></span>

```
PS C:\> Get-Process -ComputerName "WS10TestServer" -Name "*powershell*"

Handles      WS(K)   VM(M)      CPU(s)    Id  ProcessName
-------      -----   -----      ------    --  -----------
    377      69912     63     2.09      2420  powershell
    399     123396    829     4.48      1152  powershell_ise

PS C:\> Enter-PSSession -ComputerName "WS10TestServer"
[WS10TestServer]:PS C:\> Enter-PSHostProcess -Id 1152
[WS10TestServer:][Process:1152]: PS C:\Users\Test\Documents> Get-Runspace

Id Name            ComputerName    Type          State         Availability
-- ----            ------------    ----          -----         ------------
 1 Runspace1       WS10TestServer  Remote        Opened        Available
 2 RemoteHost      WS10TestServer  Remote        Opened        Busy

PS C:\> [WS10TestServer][Process:1152]: PS C:\Users\Test\Documents> Debug-Runspace -Id 2

Hit Line breakpoint on 'C:\TestWFVar1.ps1:83'
At C:\TestWFVar1.ps1:83 char:1
+ $scriptVar = "Script Variable"
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[Process:1152]: [RSDBG: 2]: PS C:\> >
```

<span data-ttu-id="5aa74-121">この例では、リモートコンピューターで開いている実行空間 WS10TestServer をデバッグします。</span><span class="sxs-lookup"><span data-stu-id="5aa74-121">In this example, you debug a runspace that is open on a remote computer, WS10TestServer.</span></span> <span data-ttu-id="5aa74-122">コマンドの最初の行で、リモートコンピューターでを実行し、 `Get-Process` Windows PowerShell ホストプロセスをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5aa74-122">In the first line of the command, you run `Get-Process` on the remote computer, and filter for Windows PowerShell host processes.</span></span> <span data-ttu-id="5aa74-123">この例では、プロセス ID 1152、Windows PowerShell ISE ホストプロセスをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="5aa74-123">In this example, you want to debug process ID 1152, the Windows PowerShell ISE host process.</span></span>

<span data-ttu-id="5aa74-124">2番目のコマンドでは、を実行し `Enter-PSSession` て、WS10TestServer でリモートセッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="5aa74-124">In the second command, you run `Enter-PSSession` to open a remote session on WS10TestServer.</span></span> <span data-ttu-id="5aa74-125">3番目のコマンドでは、を実行し、 `Enter-PSHostProcess` 最初のコマンド1152で取得したホストプロセスの ID を指定して、リモートサーバー上で実行されている Windows PowerShell ISE ホストプロセスにアタッチします。</span><span class="sxs-lookup"><span data-stu-id="5aa74-125">In the third command, you attach to the Windows PowerShell ISE host process running on the remote server by running `Enter-PSHostProcess`, and specifying the ID of the host process that you obtained in the first command, 1152.</span></span>

<span data-ttu-id="5aa74-126">4番目のコマンドでは、を実行して、プロセス ID 1152 の使用可能な実行空間を一覧表示し `Get-Runspace` ます。</span><span class="sxs-lookup"><span data-stu-id="5aa74-126">In the fourth command, you list available runspaces for process ID 1152 by running `Get-Runspace`.</span></span>
<span data-ttu-id="5aa74-127">ビジー状態の実行空間の ID 番号をメモしておきます。デバッグするスクリプトを実行しています。</span><span class="sxs-lookup"><span data-stu-id="5aa74-127">You note the ID number of the Busy runspace; it is running a script that you want to debug.</span></span>

<span data-ttu-id="5aa74-128">最後のコマンドでは、スクリプトを実行している開いている実行空間のデバッグ TestWFVar1.ps1 を開始し、を実行して、id パラメーターを追加することによって、実行 `Debug-Runspace` 空間を id (2) で識別します。 **Id**</span><span class="sxs-lookup"><span data-stu-id="5aa74-128">In the last command, you start debugging an opened runspace that is running a script, TestWFVar1.ps1, by running `Debug-Runspace`, and identifying the runspace by its ID, 2, by adding the **Id** parameter.</span></span> <span data-ttu-id="5aa74-129">スクリプトにブレークポイントがあるため、デバッガーが開きます。</span><span class="sxs-lookup"><span data-stu-id="5aa74-129">Because there's a breakpoint in the script, the debugger opens.</span></span>

## <span data-ttu-id="5aa74-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5aa74-130">PARAMETERS</span></span>

### <span data-ttu-id="5aa74-131">-Id</span><span class="sxs-lookup"><span data-stu-id="5aa74-131">-Id</span></span>

<span data-ttu-id="5aa74-132">実行空間の ID 番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="5aa74-132">Specifies the ID number of a runspace.</span></span> <span data-ttu-id="5aa74-133">実行 `Get-Runspace` 空間 id を表示するには、を実行します。</span><span class="sxs-lookup"><span data-stu-id="5aa74-133">You can run `Get-Runspace` to show runspace IDs.</span></span>

```yaml
Type: System.Int32
Parameter Sets: IdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5aa74-134">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="5aa74-134">-InstanceId</span></span>

<span data-ttu-id="5aa74-135">実行空間をインスタンス ID で指定します。この GUID は、を実行して表示でき `Get-Runspace` ます。</span><span class="sxs-lookup"><span data-stu-id="5aa74-135">Specifies a runspace by its instance ID, a GUID that you can show by running `Get-Runspace`.</span></span>

```yaml
Type: System.Guid
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5aa74-136">-Name</span><span class="sxs-lookup"><span data-stu-id="5aa74-136">-Name</span></span>

<span data-ttu-id="5aa74-137">実行空間を名前で指定します。</span><span class="sxs-lookup"><span data-stu-id="5aa74-137">Specifies a runspace by its name.</span></span> <span data-ttu-id="5aa74-138">実行 `Get-Runspace` 空間の名前を表示するには、を実行します。</span><span class="sxs-lookup"><span data-stu-id="5aa74-138">You can run `Get-Runspace` to show the names of runspaces.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5aa74-139">-実行空間</span><span class="sxs-lookup"><span data-stu-id="5aa74-139">-Runspace</span></span>

<span data-ttu-id="5aa74-140">実行空間オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="5aa74-140">Specifies a runspace object.</span></span> <span data-ttu-id="5aa74-141">このパラメーターに値を指定する最も簡単な方法は、フィルター処理されたコマンドの結果を含む変数を指定することです `Get-Runspace` 。</span><span class="sxs-lookup"><span data-stu-id="5aa74-141">The simplest way to provide a value for this parameter is to specify a variable that contains the results of a filtered `Get-Runspace` command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.Runspace
Parameter Sets: RunspaceParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5aa74-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5aa74-142">-Confirm</span></span>

<span data-ttu-id="5aa74-143">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5aa74-143">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5aa74-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5aa74-144">-WhatIf</span></span>

<span data-ttu-id="5aa74-145">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="5aa74-145">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="5aa74-146">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="5aa74-146">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5aa74-147">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5aa74-147">CommonParameters</span></span>

<span data-ttu-id="5aa74-148">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5aa74-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5aa74-149">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5aa74-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5aa74-150">入力</span><span class="sxs-lookup"><span data-stu-id="5aa74-150">INPUTS</span></span>

### <span data-ttu-id="5aa74-151">システム管理. 実行空間</span><span class="sxs-lookup"><span data-stu-id="5aa74-151">System.Management.Automation.Runspaces.Runspace</span></span>

<span data-ttu-id="5aa74-152">パイプを使用してコマンドの結果をデバッグすることができ `Get-Runspace` **ます。**</span><span class="sxs-lookup"><span data-stu-id="5aa74-152">You can pipe the results of a `Get-Runspace` command to **Debug-Runspace.**</span></span>

## <span data-ttu-id="5aa74-153">出力</span><span class="sxs-lookup"><span data-stu-id="5aa74-153">OUTPUTS</span></span>

## <span data-ttu-id="5aa74-154">注</span><span class="sxs-lookup"><span data-stu-id="5aa74-154">NOTES</span></span>

<span data-ttu-id="5aa74-155">`Debug-Runspace` Opened 状態の実行空間で機能します。</span><span class="sxs-lookup"><span data-stu-id="5aa74-155">`Debug-Runspace` works on runspaces that are in the Opened state.</span></span> <span data-ttu-id="5aa74-156">実行空間の状態が opened から別の状態に変わった場合、実行空間は実行中の一覧から自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="5aa74-156">If a runspace state changes from Opened to another state, that runspace is automatically removed from the running list.</span></span> <span data-ttu-id="5aa74-157">実行空間は、次の条件を満たしている場合にのみ、実行中の一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="5aa74-157">A runspace is added to the running list only if it meets the following criteria.</span></span>

- <span data-ttu-id="5aa74-158">呼び出し元である場合は、つまり、GUID ID があり `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="5aa74-158">If it is coming from Invoke-Command; that is, it has an `Invoke-Command` GUID ID.</span></span>
- <span data-ttu-id="5aa74-159">から送信されている場合は。 `Debug-Runspace` GUID ID を持つ場合は `Debug-Runspace` 。</span><span class="sxs-lookup"><span data-stu-id="5aa74-159">If it is coming from `Debug-Runspace`; that is, it has a `Debug-Runspace` GUID ID.</span></span>
- <span data-ttu-id="5aa74-160">PowerShell ワークフローから送信され、そのワークフロージョブ ID が現在のアクティブデバッガーワークフロージョブ ID と同じである場合。</span><span class="sxs-lookup"><span data-stu-id="5aa74-160">If it is coming from a PowerShell workflow, and its workflow job ID is the same as the current active debugger workflow job ID.</span></span>

## <span data-ttu-id="5aa74-161">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5aa74-161">RELATED LINKS</span></span>

[<span data-ttu-id="5aa74-162">about_Debuggers</span><span class="sxs-lookup"><span data-stu-id="5aa74-162">about_Debuggers</span></span>](../Microsoft.PowerShell.Core/About/about_Debuggers.md)

[<span data-ttu-id="5aa74-163">Debug-Job</span><span class="sxs-lookup"><span data-stu-id="5aa74-163">Debug-Job</span></span>](../Microsoft.PowerShell.Core/Debug-Job.md)

[<span data-ttu-id="5aa74-164">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="5aa74-164">Get-Runspace</span></span>](Get-Runspace.md)

[<span data-ttu-id="5aa74-165">Get-Process</span><span class="sxs-lookup"><span data-stu-id="5aa74-165">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)

[<span data-ttu-id="5aa74-166">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="5aa74-166">Enter-PSHostProcess</span></span>](../Microsoft.PowerShell.Core/Enter-PSHostProcess.md)

[<span data-ttu-id="5aa74-167">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="5aa74-167">Enter-PSSession</span></span>](../Microsoft.PowerShell.Core/Enter-PSSession.md)
