---
description: PowerShell デバッガーについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 08/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_debuggers?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Debuggers
ms.openlocfilehash: d3353a9c684091b17f496e15f1553c860d26e973
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223539"
---
# <a name="about-debuggers"></a><span data-ttu-id="f7b96-104">デバッガーについて</span><span class="sxs-lookup"><span data-stu-id="f7b96-104">About Debuggers</span></span>

## <a name="short-description"></a><span data-ttu-id="f7b96-105">概要</span><span class="sxs-lookup"><span data-stu-id="f7b96-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="f7b96-106">PowerShell デバッガーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-106">Describes the PowerShell debugger.</span></span>

## <a name="long-description"></a><span data-ttu-id="f7b96-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="f7b96-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="f7b96-108">デバッグは、スクリプトの実行中にスクリプトを調べて、スクリプトの指示に従ってエラーを特定して修正するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="f7b96-108">Debugging is the process of examining a script while it is running to identify and correct errors in the script instructions.</span></span> <span data-ttu-id="f7b96-109">PowerShell デバッガーを使用すると、スクリプト、関数、コマンド、PowerShell ワークフロー、PowerShell Desired State Configuration (DSC) 構成、または式のエラーや非効率性を確認し、識別することができます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-109">The PowerShell debugger can help you examine and identify errors and inefficiencies in your scripts, functions, commands, PowerShell workflows, PowerShell Desired State Configuration (DSC) configurations, or expressions.</span></span>

<span data-ttu-id="f7b96-110">PowerShell 5.0 以降では、PowerShell デバッガーが更新され、スクリプト、関数、ワークフロー、コマンド、構成、またはリモートコンピューター上の Windows PowerShell ISE のいずれかで実行されている式がデバッグされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f7b96-110">Starting in PowerShell 5.0, the PowerShell debugger has been updated to debug scripts, functions, workflows, commands, configurations, or expressions that are running in either the console or Windows PowerShell ISE on remote computers.</span></span> <span data-ttu-id="f7b96-111">を実行すると、 `Enter-PSSession` リモートコンピューター上でブレークポイントを設定したり、スクリプトファイルやコマンドをデバッグしたりできる対話型リモート PowerShell セッションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-111">You can run `Enter-PSSession` to start an interactive remote PowerShell session in which you can set breakpoints and debug script files and commands on the remote computer.</span></span> <span data-ttu-id="f7b96-112">`Enter-PSSession` リモートコンピューターでスクリプトまたはコマンドを実行している切断されたセッションに再接続して入力できるように、機能が更新されました。</span><span class="sxs-lookup"><span data-stu-id="f7b96-112">`Enter-PSSession` functionality has been updated to let you reconnect to and enter a disconnected session that is running a script or command on a remote computer.</span></span> <span data-ttu-id="f7b96-113">実行中のスクリプトがブレークポイントにヒットすると、クライアントセッションによってデバッガーが自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-113">If the running script hits a breakpoint, your client session automatically starts the debugger.</span></span> <span data-ttu-id="f7b96-114">スクリプトを実行している切断されたセッションが既にブレークポイントにヒットし、ブレークポイントで停止した場合、は `Enter-PSSession` セッションに再接続した後、コマンドラインデバッガーを自動的に開始します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-114">If the disconnected session that is running a script has already hit a breakpoint, and is stopped at the breakpoint, `Enter-PSSession` automatically starts the command-line debugger, after you reconnect to the session.</span></span>

<span data-ttu-id="f7b96-115">Powershell デバッガーは、powershell コンソールまたは Windows PowerShell ISE で powershell ワークフローをデバッグするためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-115">The PowerShell debugger can also be used to debug PowerShell workflows, in either the PowerShell console, or in Windows PowerShell ISE.</span></span> <span data-ttu-id="f7b96-116">PowerShell 5.0 以降では、実行中のジョブまたはプロセス内で、ローカルまたはリモートでデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-116">Starting in PowerShell 5.0, you can debug within running jobs or processes, either locally or remotely.</span></span>

<span data-ttu-id="f7b96-117">Powershell デバッガーの機能を使用して、PowerShell スクリプト、関数、コマンド、ワークフロー、または式が実行中であるかどうかを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-117">You can use the features of the PowerShell debugger to examine a PowerShell script, function, command, workflow, or expression while it is running.</span></span> <span data-ttu-id="f7b96-118">PowerShell デバッガーには、ブレークポイントの設定、ブレークポイントの管理、および呼び出し履歴の表示を行うためのコマンドレットのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7b96-118">The PowerShell debugger includes a set of cmdlets that let you set breakpoints, manage breakpoints, and view the call stack.</span></span>

## <a name="debugger-cmdlets"></a><span data-ttu-id="f7b96-119">デバッガーのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="f7b96-119">Debugger Cmdlets</span></span>

<span data-ttu-id="f7b96-120">PowerShell デバッガーには、次の一連のコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7b96-120">The PowerShell debugger includes the following set of cmdlets:</span></span>

- <span data-ttu-id="f7b96-121">`Set-PSBreakpoint`: 行、変数、およびコマンドにブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-121">`Set-PSBreakpoint`: Sets breakpoints on lines, variables, and commands.</span></span>
- <span data-ttu-id="f7b96-122">`Get-PSBreakpoint`: 現在のセッションのブレークポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-122">`Get-PSBreakpoint`: Gets breakpoints in the current session.</span></span>
- <span data-ttu-id="f7b96-123">`Disable-PSBreakpoint`: 現在のセッションのブレークポイントをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f7b96-123">`Disable-PSBreakpoint`: Turns off breakpoints in the current session.</span></span>
- <span data-ttu-id="f7b96-124">`Enable-PSBreakpoint`: 現在のセッションのブレークポイントを再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="f7b96-124">`Enable-PSBreakpoint`: Re-enables breakpoints in the current session.</span></span>
- <span data-ttu-id="f7b96-125">`Remove-PSBreakpoint`: 現在のセッションからブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-125">`Remove-PSBreakpoint`: Deletes breakpoints from the current session.</span></span>
- <span data-ttu-id="f7b96-126">`Get-PSCallStack`: 現在の呼び出し履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-126">`Get-PSCallStack`: Displays the current call stack.</span></span>

## <a name="starting-and-stopping-the-debugger"></a><span data-ttu-id="f7b96-127">デバッガーの起動と停止</span><span class="sxs-lookup"><span data-stu-id="f7b96-127">Starting and Stopping the Debugger</span></span>

<span data-ttu-id="f7b96-128">デバッガーを起動するには、1つまたは複数のブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-128">To start the debugger, set one or more breakpoints.</span></span> <span data-ttu-id="f7b96-129">次に、デバッグするスクリプト、コマンド、または関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-129">Then, run the script, command, or function that you want to debug.</span></span>

<span data-ttu-id="f7b96-130">ブレークポイントに到着すると、実行が停止し、制御がデバッガーに対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="f7b96-130">When you reach a breakpoint, execution stops, and control is turned over to the debugger.</span></span>

<span data-ttu-id="f7b96-131">デバッガーを停止するには、スクリプト、コマンド、または関数を完了するまで実行します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-131">To stop the debugger, run the script, command, or function until it is complete.</span></span> <span data-ttu-id="f7b96-132">または、 `stop` またはと入力 `t` します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-132">Or, type `stop` or `t`.</span></span>

### <a name="debugger-commands"></a><span data-ttu-id="f7b96-133">デバッガー コマンド</span><span class="sxs-lookup"><span data-stu-id="f7b96-133">Debugger Commands</span></span>

<span data-ttu-id="f7b96-134">PowerShell コンソールでデバッガーを使用する場合は、次のコマンドを使用して実行を制御します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-134">When you use the debugger in the PowerShell console, use the following commands to control the execution.</span></span> <span data-ttu-id="f7b96-135">Windows PowerShell ISE では、[デバッグ] メニューのコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-135">In Windows PowerShell ISE, use commands on the Debug menu.</span></span>

<span data-ttu-id="f7b96-136">注: 他のホストアプリケーションでデバッガーを使用する方法については、ホストアプリケーションのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7b96-136">Note: For information about how to use the debugger in other host applications, see the host application documentation.</span></span>

- <span data-ttu-id="f7b96-137">`s`、 `StepInto` : 次のステートメントを実行してから停止します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-137">`s`, `StepInto`: Executes the next statement and then stops.</span></span>

- <span data-ttu-id="f7b96-138">`v`、 `StepOver` : 次のステートメントを実行しますが、関数と呼び出しをスキップします。</span><span class="sxs-lookup"><span data-stu-id="f7b96-138">`v`, `StepOver`: Executes the next statement, but skips functions and invocations.</span></span> <span data-ttu-id="f7b96-139">スキップしたステートメントは実行されますが、ステップ スルーされることはありません。</span><span class="sxs-lookup"><span data-stu-id="f7b96-139">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="f7b96-140">`Ctrl+Break`: (ISE 内のすべてを中断) は、PowerShell コンソールまたは Windows PowerShell ISE 内で実行中のスクリプトに分割されます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-140">`Ctrl+Break`: (Break All in ISE) Breaks into a running script within either the PowerShell console, or Windows PowerShell ISE.</span></span> <span data-ttu-id="f7b96-141"><kbd>Ctrl</kbd> + Windows PowerShell 2.0、3.0、および4.0 で Ctrl<kbd>Break</kbd>を押すと、プログラムが閉じられることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f7b96-141">Note that <kbd>Ctrl</kbd>+<kbd>Break</kbd> in Windows PowerShell 2.0, 3.0, and 4.0 closes the program.</span></span> <span data-ttu-id="f7b96-142">Break All は、ローカルとリモートの対話形式で実行されるスクリプトの両方で機能します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-142">Break All works on both local and remote interactively-running scripts.</span></span>

- <span data-ttu-id="f7b96-143">`o`、 `StepOut` : 現在の関数からステップアウトします。入れ子になっている場合は、1つ上のレベルになります。</span><span class="sxs-lookup"><span data-stu-id="f7b96-143">`o`, `StepOut`: Steps out of the current function; up one level if nested.</span></span> <span data-ttu-id="f7b96-144">メインボディの場合は、最後または次のブレークポイントに進みます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-144">If in the main body, it continues to the end or the next breakpoint.</span></span> <span data-ttu-id="f7b96-145">スキップしたステートメントは実行されますが、ステップ スルーされることはありません。</span><span class="sxs-lookup"><span data-stu-id="f7b96-145">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="f7b96-146">`c`、 `Continue` : スクリプトが完了するまで、または次のブレークポイントに到達するまで実行を続けます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-146">`c`, `Continue`: Continues to run until the script is complete or until the next breakpoint is reached.</span></span> <span data-ttu-id="f7b96-147">スキップしたステートメントは実行されますが、ステップ スルーされることはありません。</span><span class="sxs-lookup"><span data-stu-id="f7b96-147">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="f7b96-148">`l`、 `List` : 実行中のスクリプトの一部を表示します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-148">`l`, `List`: Displays the part of the script that is executing.</span></span> <span data-ttu-id="f7b96-149">既定では、現在の行、前の5行、および10個の後続の行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-149">By default, it displays the current line, five previous lines, and 10 subsequent lines.</span></span>
  <span data-ttu-id="f7b96-150">スクリプトの一覧を表示するには、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-150">To continue listing the script, press ENTER.</span></span>

- <span data-ttu-id="f7b96-151">`l <m>`、 `List` : によって指定された行番号で始まる16行のスクリプトが表示されます `<m>` 。</span><span class="sxs-lookup"><span data-stu-id="f7b96-151">`l <m>`, `List`: Displays 16 lines of the script beginning with the line number specified by `<m>`.</span></span>

- <span data-ttu-id="f7b96-152">`l <m> <n>`、 `List` : `<n>` によって指定された行番号で始まるスクリプトの行を表示 `<m>` します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-152">`l <m> <n>`, `List`: Displays `<n>` lines of the script, beginning with the line number specified by `<m>`.</span></span>

- <span data-ttu-id="f7b96-153">`q`、 `Stop` 、 `Exit` : スクリプトの実行を停止し、デバッガーを終了します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-153">`q`, `Stop`, `Exit`: Stops executing the script, and exits the debugger.</span></span> <span data-ttu-id="f7b96-154">コマンドレットを実行してジョブをデバッグしている場合は、コマンドによって `Debug-Job` `Exit` デバッガーがデタッチされ、ジョブの実行を継続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f7b96-154">If you are debugging a job by running the `Debug-Job` cmdlet, the `Exit` command detaches the debugger, and allows the job to continue running.</span></span>

- <span data-ttu-id="f7b96-155">`k`、 `Get-PsCallStack` : 現在の呼び出し履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-155">`k`, `Get-PsCallStack`: Displays the current call stack.</span></span>

- <span data-ttu-id="f7b96-156">`<Enter>`: 最後のコマンドがステップ、Xy ピッチ (v)、またはリスト (l) である場合、それを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-156">`<Enter>`: Repeats the last command if it was Step (s), StepOver (v), or List (l).</span></span> <span data-ttu-id="f7b96-157">それ以外の場合は、送信アクションを表します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-157">Otherwise, represents a submit action.</span></span>

- <span data-ttu-id="f7b96-158">`?`、 `h` : デバッガーコマンドのヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-158">`?`, `h`: Displays the debugger command Help.</span></span>

<span data-ttu-id="f7b96-159">デバッガーを終了するには、Stop (q) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-159">To exit the debugger, you can use Stop (q).</span></span>

<span data-ttu-id="f7b96-160">PowerShell 5.0 以降では、Exit コマンドを実行して、またはのいずれかを実行して開始した入れ子になったデバッグセッションを終了でき `Debug-Job` `Debug-Runspace` ます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-160">Starting in PowerShell 5.0, you can run the Exit command to exit a nested debugging session that you started by running either `Debug-Job` or `Debug-Runspace`.</span></span>

<span data-ttu-id="f7b96-161">これらのデバッガーコマンドを使用して、スクリプトを実行し、問題点について停止し、変数の値とシステムの状態を調べて、問題が特定されるまでスクリプトの実行を続行することができます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-161">By using these debugger commands, you can run a script, stop on a point of concern, examine the values of variables and the state of the system, and continue running the script until you have identified a problem.</span></span>

<span data-ttu-id="f7b96-162">注: リダイレクト演算子 (">" など) を使用してステートメントにステップインすると、PowerShell デバッガーはスクリプト内の残りのすべてのステートメントをステップオーバーします。</span><span class="sxs-lookup"><span data-stu-id="f7b96-162">NOTE: If you step into a statement with a redirection operator, such as ">", the PowerShell debugger steps over all remaining statements in the script.</span></span>

<span data-ttu-id="f7b96-163">スクリプト変数の値の表示</span><span class="sxs-lookup"><span data-stu-id="f7b96-163">Displaying the Values of script Variables</span></span>

<span data-ttu-id="f7b96-164">デバッガーでは、コマンドを入力したり、変数の値を表示したり、コマンドレットを使用したり、コマンドラインでスクリプトを実行したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-164">While you are in the debugger, you can also enter commands, display the value of variables, use cmdlets, and run scripts at the command line.</span></span>

<span data-ttu-id="f7b96-165">次の自動変数を除き、デバッグ対象のスクリプト内のすべての変数の現在の値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-165">You can display the current value of all variables in the script that is being debugged, except for the following automatic variables:</span></span>

```powershell
$_
$Args
$Input
$MyInvocation
$PSBoundParameters
```

<span data-ttu-id="f7b96-166">これらの変数のいずれかの値を表示しようとする場合は、スクリプト内の変数の値ではなく、デバッガーが使う内部パイプラインでその変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-166">If you try to display the value of any of these variables, you get the value of that variable for in an internal pipeline the debugger uses, not the value of the variable in the script.</span></span>

<span data-ttu-id="f7b96-167">デバッグされているスクリプトのこれらの変数の値を表示するには、スクリプトで自動変数の値を新しい変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-167">To display the value these variables for the script that is being debugged, in the script, assign the value of the automatic variable to a new variable.</span></span> <span data-ttu-id="f7b96-168">その後、新しい変数の値を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-168">Then you can display the value of the new variable.</span></span>

<span data-ttu-id="f7b96-169">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-169">For example,</span></span>

```powershell
$scriptArgs = $Args
$scriptArgs
```

<span data-ttu-id="f7b96-170">このトピックの例では、変数の値が次のように再 `$MyInvocation` 割り当てされます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-170">In the example in this topic, the value of the `$MyInvocation` variable is reassigned as follows:</span></span>

```powershell
$scriptname = $MyInvocation.MyCommand.Path
```

## <a name="the-debugger-environment"></a><span data-ttu-id="f7b96-171">デバッガー環境</span><span class="sxs-lookup"><span data-stu-id="f7b96-171">The Debugger Environment</span></span>

<span data-ttu-id="f7b96-172">ブレークポイントにヒットしたら、デバッガー環境に入ります。</span><span class="sxs-lookup"><span data-stu-id="f7b96-172">When you reach a breakpoint, you enter the debugger environment.</span></span> <span data-ttu-id="f7b96-173">コマンドプロンプトが "[DBG]:" で始まるように変更されます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-173">The command prompt changes so that it begins with "[DBG]:".</span></span> <span data-ttu-id="f7b96-174">ワークフローをデバッグしている場合、プロンプトは "[作成されたユーザー名]" になります。</span><span class="sxs-lookup"><span data-stu-id="f7b96-174">If you are debugging a workflow, the prompt is "[WFDBG]".</span></span> <span data-ttu-id="f7b96-175">プロンプトはカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-175">You can customize the prompt.</span></span>

<span data-ttu-id="f7b96-176">プロンプトのカスタマイズの詳細については、「 [about_Prompts](about_prompts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7b96-176">For more information about customizing the prompt, see [about_Prompts](about_prompts.md).</span></span>

<span data-ttu-id="f7b96-177">また、PowerShell コンソールなどの一部のホストアプリケーション (Windows PowerShell Integrated Scripting Environment [ISE] ではない) では、デバッグのために入れ子になったプロンプトが開きます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-177">Also, in some host applications, such as the PowerShell console, (but not in Windows PowerShell Integrated Scripting Environment [ISE]), a nested prompt opens for debugging.</span></span> <span data-ttu-id="f7b96-178">入れ子になったプロンプトを検出するには、コマンドプロンプトに表示される大なり記号 (ASCII 62) を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-178">You can detect the nested prompt by the repeating greater-than characters (ASCII 62) that appear at the command prompt.</span></span>

<span data-ttu-id="f7b96-179">たとえば、PowerShell コンソールの既定のデバッグプロンプトは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f7b96-179">For example, the following is the default debugging prompt in the PowerShell console:</span></span>

```
[DBG]: PS (get-location)>>>
```

<span data-ttu-id="f7b96-180">入れ子レベルは、自動変数を使用して見つけることができ `$NestedPromptLevel` ます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-180">You can find the nesting level by using the `$NestedPromptLevel` automatic variable.</span></span>

<span data-ttu-id="f7b96-181">また、自動変数は、 `$PSDebugContext` ローカルスコープで定義されます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-181">Additionally, an automatic variable, `$PSDebugContext`, is defined in the local scope.</span></span> <span data-ttu-id="f7b96-182">変数の存在を使用して、 `$PsDebugContext` デバッガーで実行されているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-182">You can use the presence of the `$PsDebugContext` variable to determine whether you are in the debugger.</span></span>

<span data-ttu-id="f7b96-183">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-183">For example:</span></span>

```powershell
if ($PSDebugContext) {"Debugging"} else {"Not Debugging"}
```

<span data-ttu-id="f7b96-184">デバッグで変数の値を使用でき `$PSDebugContext` ます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-184">You can use the value of the `$PSDebugContext` variable in your debugging.</span></span>

```
[DBG]: PS>>> $PSDebugContext.InvocationInfo

Name   CommandLineParameters  UnboundArguments  Location
----   ---------------------  ----------------  --------
=      {}                     {}                C:\ps-test\vote.ps1 (1)
```

## <a name="debugging-and-scope"></a><span data-ttu-id="f7b96-185">デバッグとスコープ</span><span class="sxs-lookup"><span data-stu-id="f7b96-185">Debugging and Scope</span></span>

<span data-ttu-id="f7b96-186">デバッガーを中断しても、操作中のスコープは変更されませんが、スクリプト内のブレークポイントに到着すると、スクリプトのスコープに移動します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-186">Breaking into the debugger does not change the scope in which you are operating, but when you reach a breakpoint in a script, you move into the script scope.</span></span> <span data-ttu-id="f7b96-187">スクリプトスコープは、デバッガーを実行したスコープの子です。</span><span class="sxs-lookup"><span data-stu-id="f7b96-187">The script scope is a child of the scope in which you ran the debugger.</span></span>

<span data-ttu-id="f7b96-188">スクリプトスコープで定義されている変数とエイリアスを検索するに `Get-Alias` は、またはコマンドレットの scope パラメーターを使用し `Get-Variable` ます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-188">To find the variables and aliases that are defined in the script scope, use the Scope parameter of the `Get-Alias` or `Get-Variable` cmdlets.</span></span>

<span data-ttu-id="f7b96-189">たとえば、次のコマンドは、ローカル (スクリプト) スコープ内の変数を取得します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-189">For example, the following command gets the variables in the local (script) scope:</span></span>

```powershell
Get-Variable -scope 0
```

<span data-ttu-id="f7b96-190">コマンドは次のように省略できます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-190">You can abbreviate the command as:</span></span>

```powershell
gv -s 0
```

<span data-ttu-id="f7b96-191">これは、スクリプトで定義した変数と、デバッグ中に定義した変数のみを表示するのに便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="f7b96-191">This is a useful way to see only the variables that you defined in the script and that you defined while debugging.</span></span>

<span data-ttu-id="f7b96-192">コマンドラインでのデバッグ</span><span class="sxs-lookup"><span data-stu-id="f7b96-192">Debugging at the Command Line</span></span>

<span data-ttu-id="f7b96-193">変数のブレークポイントまたはコマンドのブレークポイントを設定した場合は、スクリプトファイル内でのみブレークポイントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-193">When you set a variable breakpoint or a command breakpoint, you can set the breakpoint only in a script file.</span></span> <span data-ttu-id="f7b96-194">ただし、既定では、現在のセッションで実行されるすべてのものにブレークポイントが設定されます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-194">However, by default, the breakpoint is set on anything that runs in the current session.</span></span>

<span data-ttu-id="f7b96-195">たとえば、変数にブレークポイントを設定した場合、 `$name` デバッガーは、 `$name` ブレークポイントを無効にするか削除するまで実行する任意のスクリプト、コマンド、関数、スクリプトコマンドレット、または式で、任意の変数を中断します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-195">For example, if you set a breakpoint on the `$name` variable, the debugger breaks on any `$name` variable in any script, command, function, script cmdlet or expression that you run until you disable or remove the breakpoint.</span></span>

<span data-ttu-id="f7b96-196">これにより、セッションとユーザーのプロファイルの関数、変数、およびその他のスクリプトによって影響を受ける可能性のある、より現実的なコンテキストでスクリプトをデバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-196">This allows you to debug your scripts in a more realistic context in which they might be affected by functions, variables, and other scripts in the session and in the user's profile.</span></span>

<span data-ttu-id="f7b96-197">行のブレークポイントはスクリプトファイルに固有であるため、スクリプトファイルでのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-197">Line breakpoints are specific to script files, so they are set only in script files.</span></span>

## <a name="debugging-workflows"></a><span data-ttu-id="f7b96-198">デバッグのワークフロー</span><span class="sxs-lookup"><span data-stu-id="f7b96-198">Debugging Workflows</span></span>

<span data-ttu-id="f7b96-199">Powershell 4.0 デバッガーは、powershell コンソールまたは Windows PowerShell ISE で PowerShell ワークフローをデバッグするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-199">The PowerShell 4.0 debugger can be used to debug PowerShell workflows, either in the PowerShell console, or in Windows PowerShell ISE.</span></span> <span data-ttu-id="f7b96-200">PowerShell デバッガーを使用してワークフローをデバッグする場合、いくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="f7b96-200">There are some limitations with using the PowerShell debugger to debug workflows.</span></span>

- <span data-ttu-id="f7b96-201">デバッガーではワークフロー変数を表示できますが、デバッガー内からワークフロー変数を設定することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f7b96-201">You can view workflow variables while you are in the debugger, but setting workflow variables from within the debugger is not supported.</span></span>
- <span data-ttu-id="f7b96-202">ワークフローデバッガーで停止したときのタブ補完は使用できません。</span><span class="sxs-lookup"><span data-stu-id="f7b96-202">Tab completion when stopped in the workflow debugger is not available.</span></span>
- <span data-ttu-id="f7b96-203">ワークフローデバッグは、PowerShell スクリプトからワークフローを同期的に実行する場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-203">Workflow debugging works only with synchronous running of workflows from a PowerShell script.</span></span> <span data-ttu-id="f7b96-204">ワークフローが ( **AsJob** パラメーターを使用して) ジョブとして実行されている場合、ワークフローをデバッグすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f7b96-204">You cannot debug workflows if they are running as a job (with the **AsJob** parameter).</span></span>
- <span data-ttu-id="f7b96-205">別のワークフローを呼び出すワークフローやスクリプトを呼び出すワークフローなど、他の入れ子になったデバッグシナリオは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="f7b96-205">Other nested debugging scenarios, such as a workflow calling another workflow or a workflow calling a script, are not implemented.</span></span>

<span data-ttu-id="f7b96-206">次の例は、ワークフローのデバッグを示しています。</span><span class="sxs-lookup"><span data-stu-id="f7b96-206">The following example demonstrates debugging a workflow.</span></span> <span data-ttu-id="f7b96-207">デバッガーがワークフロー関数にステップインすると、デバッガープロンプトが "[変更あり]" に変わります。</span><span class="sxs-lookup"><span data-stu-id="f7b96-207">When the debugger steps into the workflow function, the debugger prompt changes to "[WFDBG]".</span></span>

```powershell
PS C:> Set-PSBreakpoint -Script C:\TestWFDemo1.ps1 -Line 8

ID Script           Line Command    Variable     Action
-- ------           ---- -------    --------     ------
0 TestWFDemo1.ps1   8

PS C:> C:\TestWFDemo1.ps1
Entering debug mode. Use h or ? for help.

Hit Line breakpoint on 'C:\TestWFDemo1.ps1:8'

At C:\TestWFDemo1.ps1:8 char:5
+     Write-Output -InputObject "Now writing output:"
# +!INCLUDE[]~~~~~

[WFDBG:localhost]: PS C:>> list

# 3:

4:  workflow SampleWorkflowTest
5:  {
6:      param ($MyOutput)
# 7:

8:*     Write-Output -InputObject "Now writing output:"
9:      Write-Output -Input $MyOutput
# 10:

11:      Write-Output -InputObject "Get PowerShell process:"
12:      Get-Process -Name powershell
# 13:

14:      Write-Output -InputObject "Workflow function complete."
15:  }
# 16:

17:  # Call workflow function
18:  SampleWorkflowTest -MyOutput "Hello"

[WFDBG:localhost]: PS C:>> $MyOutput
Hello
[WFDBG:localhost]: PS C:>> stepOver
Now writing output:
At C:\TestWFDemo1.ps1:9 char:5
+     Write-Output -Input $MyOutput
# +!INCLUDE[]~

[WFDBG:localhost]: PS C:>> list

4:  workflow SampleWorkflowTest
5:  {
6:      param ($MyOutput)
# 7:

8:      Write-Output -InputObject "Now writing output:"
9:*     Write-Output -Input $MyOutput
# 10:

11:      Write-Output -InputObject "Get PowerShell process:"
12:      Get-Process -Name powershell
# 13:

14:      Write-Output -InputObject "Workflow function complete."
15:  }
# 16:

17:  # Call workflow function
18:  SampleWorkflowTest -MyOutput "Hello"
# 19:


[WFDBG:localhost]: PS C:>> stepOver
Hello
At C:\TestWFDemo1.ps1:11 char:5
+     Write-Output -InputObject "Get PowerShell process:"
# +!INCLUDE[]~~~~~~~~~

[WFDBG:localhost]: PS C:>> stepOut
Get PowerShell process:

Handles  NPM(K)    PM(K)    WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----    ----- -----   ------     -- -----------
    433      35   106688   128392   726     2.67   7124 powershell
    499      44   134244   172096   787     2.79   7452 powershell

Workflow function complete.
```

## <a name="debugging-functions"></a><span data-ttu-id="f7b96-208">デバッグ関数</span><span class="sxs-lookup"><span data-stu-id="f7b96-208">Debugging Functions</span></span>

<span data-ttu-id="f7b96-209">、、およびの各セクションを含む関数にブレークポイントを設定すると、 `Begin` `Process` `End` デバッガーは各セクションの最初の行で中断します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-209">When you set a breakpoint on a function that has `Begin`, `Process`, and `End` sections, the debugger breaks at the first line of each section.</span></span>

<span data-ttu-id="f7b96-210">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-210">For example:</span></span>

```powershell
function test-cmdlet {
    begin {
        write-output "Begin"
    }
    process {
        write-output "Process"
    }
    end {
        write-output "End"
    }
}

C:\PS> Set-PSBreakpoint -command test-cmdlet

C:\PS> test-cmdlet

Begin
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

[DBG]: C:\PS> c
Process
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

[DBG]: C:\PS> c
End
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

# [DBG]: C:\PS>
```

## <a name="debugging-remote-scripts"></a><span data-ttu-id="f7b96-211">リモートスクリプトのデバッグ</span><span class="sxs-lookup"><span data-stu-id="f7b96-211">Debugging Remote Scripts</span></span>

<span data-ttu-id="f7b96-212">PowerShell 5.0 以降では、コンソールまたは Windows PowerShell ISE で、リモートセッションで PowerShell デバッガーを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-212">Starting in PowerShell 5.0, you can run the PowerShell debugger in a remote session, in either the console, or Windows PowerShell ISE.</span></span>
<span data-ttu-id="f7b96-213">`Enter-PSSession` リモートコンピューターで実行中の切断されたセッションに再接続して、現在スクリプトを実行できるように、機能が更新されました。</span><span class="sxs-lookup"><span data-stu-id="f7b96-213">`Enter-PSSession` functionality has been updated to let you reconnect to and enter a disconnected session that is running on a remote computer, and currently running a script.</span></span> <span data-ttu-id="f7b96-214">実行中のスクリプトがブレークポイントにヒットすると、クライアントセッションによってデバッガーが自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-214">If the running script hits a breakpoint, your client session automatically starts the debugger.</span></span>

<span data-ttu-id="f7b96-215">次に示すのは、行6、11、22、および25のスクリプトにブレークポイントを設定して、このしくみがどのように機能するかを示す例です。</span><span class="sxs-lookup"><span data-stu-id="f7b96-215">The following is an example that shows how this works, with breakpoints set in a script at lines 6, 11, 22, and 25.</span></span> <span data-ttu-id="f7b96-216">この例では、デバッガーの起動時に2つの識別プロンプトがあります。セッションが実行されているコンピューターの名前と、デバッグモードであることを知らせる DBG プロンプトがあります。</span><span class="sxs-lookup"><span data-stu-id="f7b96-216">Note that in the example, when the debugger starts, there are two identifying prompts: the name of the computer on which the session is running, and the DBG prompt that lets you know you are in debugging mode.</span></span>

```powershell
Enter-Pssession -Cn localhost
[localhost]: PS C:\psscripts> Set-PSBreakpoint .\ttest19.ps1 6,11,22,25

ID Script          Line     Command          Variable          Action
-- ------          ----     -------          --------          ------
0 ttest19.ps1          6
1 ttest19.ps1          11
2 ttest19.ps1          22
3 ttest19.ps1          25

[localhost]: PS C:\psscripts> .\ttest19.ps1
Hit Line breakpoint on 'C:\psscripts\ttest19.ps1:11'

At C:\psscripts\ttest19.ps1:11 char:1
+ $winRMName = "WinRM"
# + ~

[localhost]: [DBG]: PS C:\psscripts>> list

6:      1..5 | foreach { sleep 1; Write-Output "hello2day $_" }
7:  }
# 8:

9:  $count = 10
10:  $psName = "PowerShell"
11:* $winRMName = "WinRM"
12:  $myVar = 102
# 13:

14:  for ($i=0; $i -lt $count; $i++)
15:  {
16:      sleep 1
17:      Write-Output "Loop iteration is: $i"
18:      Write-Output "MyVar is $myVar"
# 19:

20:      hello2day
# 21:


[localhost]: [DBG]: PS C:\psscripts>> stepover
At C:\psscripts\ttest19.ps1:12 char:1
+ $myVar = 102
# + ~

[localhost]: [DBG]: PS C:\psscripts>> quit
[localhost]: PS C:\psscripts> Exit-PSSession
PS C:\psscripts>
```

## <a name="examples"></a><span data-ttu-id="f7b96-217">例</span><span class="sxs-lookup"><span data-stu-id="f7b96-217">Examples</span></span>

<span data-ttu-id="f7b96-218">このテストスクリプトは、オペレーティングシステムのバージョンを検出し、システムに適切なメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-218">This test script detects the version of the operating system and displays a system-appropriate message.</span></span> <span data-ttu-id="f7b96-219">これには、関数、関数呼び出し、および変数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-219">It includes a function, a function call, and a variable.</span></span>

<span data-ttu-id="f7b96-220">次のコマンドを実行すると、テストスクリプトファイルの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-220">The following command displays the contents of the test script file:</span></span>

```powershell
PS C:\PS-test>  Get-Content test.ps1

function psversion {
  "PowerShell " + $PSVersionTable.PSVersion
  if ($PSVersionTable.PSVersion.Major -lt 6) {
    "Upgrade to PowerShell 6.0!"
  }
  else {
    "Have you run a background job today (start-job)?"
  }
}

$scriptName = $MyInvocation.MyCommand.Path
psversion
"Done $scriptName."
```

<span data-ttu-id="f7b96-221">まず、行、コマンド、変数、関数など、スクリプト内の目的の位置にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-221">To start, set a breakpoint at a point of interest in the script, such as a line, command, variable, or function.</span></span>

<span data-ttu-id="f7b96-222">まず、現在のディレクトリの Test.ps1 スクリプトの最初の行に行のブレークポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-222">Start by creating a line breakpoint on the first line of the Test.ps1 script in the current directory.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -line 1 -script test.ps1
```

<span data-ttu-id="f7b96-223">このコマンドは、省略形</span><span class="sxs-lookup"><span data-stu-id="f7b96-223">You can abbreviate this command as:</span></span>

```powershell
PS C:\ps-test> spb 1 -s test.ps1
```

<span data-ttu-id="f7b96-224">このコマンドは、行ブレークポイントオブジェクト (system.string **ブレークポイント** ) を返します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-224">The command returns a line-breakpoint object ( **System.Management.Automation.LineBreakpoint** ).</span></span>

```
Column     : 0
Line       : 1
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\test.ps1
ScriptName : C:\ps-test\test.ps1
```

<span data-ttu-id="f7b96-225">次に、スクリプトを開始します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-225">Now, start the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
```

<span data-ttu-id="f7b96-226">スクリプトが最初のブレークポイントに到達すると、ブレークポイントメッセージはデバッガーがアクティブであることを示します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-226">When the script reaches the first breakpoint, the breakpoint message indicates that the debugger is active.</span></span> <span data-ttu-id="f7b96-227">ここでは、ブレークポイントについて説明し、関数宣言であるスクリプトの最初の行をプレビューします。</span><span class="sxs-lookup"><span data-stu-id="f7b96-227">It describes the breakpoint and previews the first line of the script, which is a function declaration.</span></span> <span data-ttu-id="f7b96-228">また、コマンドプロンプトは、デバッガーにコントロールがあることを示すためにも変更されます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-228">The command prompt also changes to indicate that the debugger has control.</span></span>

<span data-ttu-id="f7b96-229">プレビュー行には、プレビューされたコマンドのスクリプト名と行番号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7b96-229">The preview line includes the script name and the line number of the previewed command.</span></span>

```powershell
Entering debug mode. Use h or ? for help.

Hit Line breakpoint on 'C:\ps-test\test.ps1:1'

test.ps1:1   function psversion {
# DBG>
```

<span data-ttu-id="f7b96-230">ステップコマンドを使用して、スクリプト内の最初のステートメントを実行し、次のステートメントをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="f7b96-230">Use the Step command (s) to execute the first statement in the script and to preview the next statement.</span></span> <span data-ttu-id="f7b96-231">次のステートメントでは、自動変数を使用して、 `$MyInvocation` 変数の値を `$scriptName` スクリプトファイルのパスとファイル名に設定します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-231">The next statement uses the `$MyInvocation` automatic variable to set the value of the `$scriptName` variable to the path and file name of the script file.</span></span>

```powershell
DBG> s
test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
```

<span data-ttu-id="f7b96-232">この時点で、 `$scriptName` 変数には値が設定されませんが、変数の値を表示して変数の値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-232">At this point, the `$scriptName` variable is not populated, but you can verify the value of the variable by displaying its value.</span></span> <span data-ttu-id="f7b96-233">この場合、値は `$null` です。</span><span class="sxs-lookup"><span data-stu-id="f7b96-233">In this case, the value is `$null`.</span></span>

```powershell
DBG> $scriptname
# DBG>
```

<span data-ttu-id="f7b96-234">別のステップコマンドを使用して、現在のステートメントを実行し、スクリプト内の次のステートメントをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="f7b96-234">Use another Step command (s) to execute the current statement and to preview the next statement in the script.</span></span> <span data-ttu-id="f7b96-235">次のステートメントは、PsVersion 関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-235">The next statement calls the PsVersion function.</span></span>

```powershell
DBG> s
test.ps1:12  psversion
```

<span data-ttu-id="f7b96-236">この時点で、 `$scriptName` 変数に値が設定されていますが、変数の値を表示することによって変数の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-236">At this point, the `$scriptName` variable is populated, but you verify the value of the variable by displaying its value.</span></span> <span data-ttu-id="f7b96-237">この場合、値はスクリプトパスに設定されます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-237">In this case, the value is set to the script path.</span></span>

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```

<span data-ttu-id="f7b96-238">別のステップコマンドを使用して関数呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-238">Use another Step command to execute the function call.</span></span> <span data-ttu-id="f7b96-239">ENTER キーを押すか、ステップに「s」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-239">Press ENTER, or type "s" for Step.</span></span>

```powershell
DBG> s
test.ps1:2       "PowerShell " + $PSVersionTable.PSVersion
```

<span data-ttu-id="f7b96-240">デバッグメッセージには、関数内のステートメントのプレビューが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7b96-240">The debug message includes a preview of the statement in the function.</span></span> <span data-ttu-id="f7b96-241">このステートメントを実行し、関数の次のステートメントをプレビューするには、コマンドを使用し `Step` ます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-241">To execute this statement and to preview the next statement in the function, you can use a `Step` command.</span></span> <span data-ttu-id="f7b96-242">ただし、この場合は、StepOut コマンド (o) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-242">But, in this case, use a StepOut command (o).</span></span> <span data-ttu-id="f7b96-243">(ブレークポイントに到達しない限り) 関数の実行を完了し、スクリプト内の次のステートメントにステップインします。</span><span class="sxs-lookup"><span data-stu-id="f7b96-243">It completes the execution of the function (unless it reaches a breakpoint) and steps to the next statement in the script.</span></span>

```powershell
DBG> o
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

<span data-ttu-id="f7b96-244">スクリプトの最後のステートメントが実行されているので、Step、StepOut、Continue の各コマンドは同じ効果を持ちます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-244">Because we are on the last statement in the script, the Step, StepOut, and Continue commands have the same effect.</span></span> <span data-ttu-id="f7b96-245">この場合は、StepOut (o) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-245">In this case, use StepOut (o).</span></span>

```powershell
Done C:\ps-test\test.ps1
PS C:\ps-test>
```

<span data-ttu-id="f7b96-246">StepOut コマンドは、最後のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-246">The StepOut command executes the last command.</span></span> <span data-ttu-id="f7b96-247">標準のコマンドプロンプトは、デバッガーが終了し、コマンドプロセッサに制御を返したことを示します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-247">The standard command prompt indicates that the debugger has exited and returned control to the command processor.</span></span>

<span data-ttu-id="f7b96-248">次に、デバッガーを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-248">Now, run the debugger again.</span></span> <span data-ttu-id="f7b96-249">まず、現在のブレークポイントを削除するには、 `Get-PsBreakpoint` `Remove-PsBreakpoint` コマンドレットとコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-249">First, to delete the current breakpoint, use the `Get-PsBreakpoint` and `Remove-PsBreakpoint` cmdlets.</span></span> <span data-ttu-id="f7b96-250">(ブレークポイントを再利用する可能性があると思われる場合は、 `Disable-PsBreakpoint` の代わりにコマンドレットを使用 `Remove-PsBreakpoint` してください)。</span><span class="sxs-lookup"><span data-stu-id="f7b96-250">(If you think you might reuse the breakpoint, use the `Disable-PsBreakpoint` cmdlet instead of `Remove-PsBreakpoint`.)</span></span>

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

<span data-ttu-id="f7b96-251">このコマンドは、省略形</span><span class="sxs-lookup"><span data-stu-id="f7b96-251">You can abbreviate this command as:</span></span>

```powershell
PS C:\ps-test> gbp | rbp
```

<span data-ttu-id="f7b96-252">または、次のような関数を記述してコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-252">Or, run the command by writing a function, such as the following function:</span></span>

```powershell
function delbr { gbp | rbp }
```

<span data-ttu-id="f7b96-253">次に、変数にブレークポイントを作成し `$scriptname` ます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-253">Now, create a breakpoint on the `$scriptname` variable.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -variable scriptname -script test.ps1
```

<span data-ttu-id="f7b96-254">コマンドは次のように省略できます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-254">You can abbreviate the command as:</span></span>

```powershell
PS C:\ps-test> sbp -v scriptname -s test.ps1
```

<span data-ttu-id="f7b96-255">次に、スクリプトを開始します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-255">Now, start the script.</span></span> <span data-ttu-id="f7b96-256">スクリプトが変数のブレークポイントに到達します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-256">The script reaches the variable breakpoint.</span></span> <span data-ttu-id="f7b96-257">既定のモードは Write であるため、変数の値を変更するステートメントの直前に実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-257">The default mode is Write, so execution stops just before the statement that changes the value of the variable.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Variable breakpoint on 'C:\ps-test\test.ps1:$scriptName'
(Write access)

test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
# DBG>
```

<span data-ttu-id="f7b96-258">変数の現在の値を表示 `$scriptName` `$null` します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-258">Display the current value of the `$scriptName` variable, which is `$null`.</span></span>

```powershell
DBG> $scriptName
# DBG>
```

<span data-ttu-id="f7b96-259">ステップコマンドを使用して、変数を設定するステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-259">Use a Step command (s) to execute the statement that populates the variable.</span></span>
<span data-ttu-id="f7b96-260">次に、変数の新しい値を表示し `$scriptName` ます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-260">Then, display the new value of the `$scriptName` variable.</span></span>

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```powershell

Use a Step command (s) to preview the next statement in the script.

```powershell
DBG> s
test.ps1:12  psversion
```

<span data-ttu-id="f7b96-261">次のステートメントは、PsVersion 関数の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="f7b96-261">The next statement is a call to the PsVersion function.</span></span> <span data-ttu-id="f7b96-262">関数をスキップした後も実行するには、Xy ピッチコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-262">To skip the function but still execute it, use a StepOver command (v).</span></span> <span data-ttu-id="f7b96-263">ピッチを使用するときに関数を既に使用している場合は、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="f7b96-263">If you are already in the function when you use StepOver, it is not effective.</span></span> <span data-ttu-id="f7b96-264">関数呼び出しが表示されますが、実行されません。</span><span class="sxs-lookup"><span data-stu-id="f7b96-264">The function call is displayed, but it is not executed.</span></span>

```powershell
DBG> v
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

<span data-ttu-id="f7b96-265">Xy ピッチコマンドは関数を実行し、スクリプト内の次のステートメントをプレビューします。最後の行が出力されます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-265">The StepOver command executes the function, and it previews the next statement in the script, which prints the final line.</span></span>

<span data-ttu-id="f7b96-266">停止コマンド (t) を使用してデバッガーを終了します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-266">Use a Stop command (t) to exit the debugger.</span></span> <span data-ttu-id="f7b96-267">コマンドプロンプトが標準のコマンドプロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="f7b96-267">The command prompt reverts to the standard command prompt.</span></span>

```powershell
C:\ps-test>
```

<span data-ttu-id="f7b96-268">ブレークポイントを削除するには `Get-PsBreakpoint` 、 `Remove-PsBreakpoint` コマンドレットとコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-268">To delete the breakpoints, use the `Get-PsBreakpoint` and `Remove-PsBreakpoint` cmdlets.</span></span>

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

<span data-ttu-id="f7b96-269">PsVersion 関数に新しいコマンドのブレークポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-269">Create a new command breakpoint on the PsVersion function.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1
```

<span data-ttu-id="f7b96-270">このコマンドは、次のように省略できます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-270">You can abbreviate this command to:</span></span>

```powershell
PS C:\ps-test> sbp -c psversion -s test.ps1
```

<span data-ttu-id="f7b96-271">次に、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-271">Now, run the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
# DBG>
```

<span data-ttu-id="f7b96-272">スクリプトは、関数呼び出しのブレークポイントに到達します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-272">The script reaches the breakpoint at the function call.</span></span> <span data-ttu-id="f7b96-273">この時点で、関数はまだ呼び出されていません。</span><span class="sxs-lookup"><span data-stu-id="f7b96-273">At this point, the function has not yet been called.</span></span> <span data-ttu-id="f7b96-274">これにより、の Action パラメーターを使用して、 `Set-PSBreakpoint` ブレークポイントの実行条件を設定したり、ログの開始や診断やセキュリティスクリプトの呼び出しなどの準備タスクや診断タスクを実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-274">This gives you the opportunity to use the Action parameter of `Set-PSBreakpoint` to set conditions for the execution of the breakpoint or to perform preparatory or diagnostic tasks, such as starting a log or invoking a diagnostic or security script.</span></span>

<span data-ttu-id="f7b96-275">アクションを設定するには、Continue コマンド (c) を使用してスクリプトを終了し、コマンドを使用して `Remove-PsBreakpoint` 現在のブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-275">To set an action, use a Continue command (c) to exit the script, and a `Remove-PsBreakpoint` command to delete the current breakpoint.</span></span> <span data-ttu-id="f7b96-276">(ブレークポイントは読み取り専用であるため、現在のブレークポイントにアクションを追加することはできません)。</span><span class="sxs-lookup"><span data-stu-id="f7b96-276">(Breakpoints are read-only, so you cannot add an action to the current breakpoint.)</span></span>

```powershell
DBG> c
Windows PowerShell 2.0
Have you run a background job today (start-job)?
Done C:\ps-test\test.ps1

PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
PS C:\ps-test>
```

<span data-ttu-id="f7b96-277">ここで、アクションを使用して新しいコマンドブレークポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-277">Now, create a new command breakpoint with an action.</span></span> <span data-ttu-id="f7b96-278">次のコマンドは、 `$scriptName` 関数が呼び出されたときに変数の値をログに記録するアクションを使用して、コマンドのブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-278">The following command sets a command breakpoint with an action that logs the value of the `$scriptName` variable when the function is called.</span></span> <span data-ttu-id="f7b96-279">Break キーワードがアクションで使用されていないため、実行は停止されません。</span><span class="sxs-lookup"><span data-stu-id="f7b96-279">Because the Break keyword is not used in the action, execution does not stop.</span></span> <span data-ttu-id="f7b96-280">(バックティック (') は、行連結文字です)。</span><span class="sxs-lookup"><span data-stu-id="f7b96-280">(The backtick (\`) is the line-continuation character.)</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1  `
-action { add-content "The value of `$scriptName is $scriptName." `
-path action.log}
```

<span data-ttu-id="f7b96-281">また、ブレークポイントの条件を設定するアクションを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-281">You can also add actions that set conditions for the breakpoint.</span></span> <span data-ttu-id="f7b96-282">次のコマンドでは、実行ポリシーが RemoteSigned に設定されている場合にのみ、コマンドのブレークポイントが実行されます。これは、スクリプトの実行を許可する最も制限の厳しいポリシーです。</span><span class="sxs-lookup"><span data-stu-id="f7b96-282">In the following command, the command breakpoint is executed only if the execution policy is set to RemoteSigned, the most restrictive policy that still permits you to run scripts.</span></span> <span data-ttu-id="f7b96-283">(バックティック (') は継続文字です)。</span><span class="sxs-lookup"><span data-stu-id="f7b96-283">(The backtick (\`) is the continuation character.)</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -script test.ps1 -command psversion `
-action { if ((Get-ExecutionPolicy) -eq "RemoteSigned") { break }}
```

<span data-ttu-id="f7b96-284">アクションの Break キーワードは、ブレークポイントを実行するようにデバッガーに指示します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-284">The Break keyword in the action directs the debugger to execute the breakpoint.</span></span>
<span data-ttu-id="f7b96-285">Continue キーワードを使用して、デバッガーを中断せずに実行するように指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-285">You can also use the Continue keyword to direct the debugger to execute without breaking.</span></span> <span data-ttu-id="f7b96-286">Default キーワードは Continue であるため、実行を停止するには [中断] を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7b96-286">Because the default keyword is Continue, you must specify Break to stop execution.</span></span>

<span data-ttu-id="f7b96-287">次に、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-287">Now, run the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
```

<span data-ttu-id="f7b96-288">実行ポリシーは **RemoteSigned** に設定されているため、関数呼び出しで実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-288">Because the execution policy is set to **RemoteSigned** , execution stops at the function call.</span></span>

<span data-ttu-id="f7b96-289">この時点で、呼び出し履歴を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-289">At this point, you might want to check the call stack.</span></span> <span data-ttu-id="f7b96-290">コマンド `Get-PsCallStack` レットまたは `Get-PsCallStack` デバッガーコマンド (k) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-290">Use the `Get-PsCallStack` cmdlet or the `Get-PsCallStack` debugger command (k).</span></span> <span data-ttu-id="f7b96-291">次のコマンドは、現在の呼び出し履歴を取得します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-291">The following command gets the current call stack.</span></span>

```powershell
DBG> k
2: prompt
1: .\test.ps1: $args=[]
0: prompt: $args=[]
```

<span data-ttu-id="f7b96-292">この例では、PowerShell デバッガーを使用するさまざまな方法をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-292">This example demonstrates just a few of the many ways to use the PowerShell debugger.</span></span>

<span data-ttu-id="f7b96-293">デバッガーのコマンドレットの詳細については、次のコマンドを入力してください。</span><span class="sxs-lookup"><span data-stu-id="f7b96-293">For more information about the debugger cmdlets, type the following command:</span></span>

```powershell
help <cmdlet-name> -full
```

<span data-ttu-id="f7b96-294">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-294">For example, type:</span></span>

```powershell
help Set-PSBreakpoint -full
```

## <a name="other-debugging-features-in-powershell"></a><span data-ttu-id="f7b96-295">PowerShell のその他のデバッグ機能</span><span class="sxs-lookup"><span data-stu-id="f7b96-295">Other Debugging Features in PowerShell</span></span>

<span data-ttu-id="f7b96-296">Powershell デバッガーに加えて、PowerShell には、スクリプトや関数のデバッグに使用できる機能が他にもいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="f7b96-296">In addition to the PowerShell debugger, PowerShell includes several other features that you can use to debug scripts and functions.</span></span>

- <span data-ttu-id="f7b96-297">Windows PowerShell ISE には、対話型のグラフィカルデバッガーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7b96-297">Windows PowerShell ISE includes an interactive graphical debugger.</span></span> <span data-ttu-id="f7b96-298">詳細については、Windows PowerShell ISE を開始し、F1 キーを押してください。</span><span class="sxs-lookup"><span data-stu-id="f7b96-298">For more information, start Windows PowerShell ISE and press F1.</span></span>

- <span data-ttu-id="f7b96-299">`Set-PSDebug`コマンドレットには、ステップ実行やトレースなど、基本的なスクリプトデバッグ機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="f7b96-299">The `Set-PSDebug` cmdlet offers very basic script debugging features, including stepping and tracing.</span></span>

- <span data-ttu-id="f7b96-300">コマンドレットを使用して、初期化されて `Set-StrictMode` いない変数への参照、オブジェクトの存在しないプロパティへの参照、および無効な関数構文を検出します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-300">Use the `Set-StrictMode` cmdlet to detect references to uninitialized variables, to references to non-existent properties of an object, and to function syntax that is not valid.</span></span>

- <span data-ttu-id="f7b96-301">変数の値を表示するステートメント、コマンドラインから入力を読み取るステートメント、現在の命令を報告するステートメントなど、診断ステートメントをスクリプトに追加します。</span><span class="sxs-lookup"><span data-stu-id="f7b96-301">Add diagnostic statements to a script, such as statements that display the value of variables, statements that read input from the command line, or statements that report the current instruction.</span></span> <span data-ttu-id="f7b96-302">、、、など、このタスクの書き込み動詞を含むコマンドレットを使用し `Write-Host` `Write-Debug` `Write-Warning` `Write-Verbose` ます。</span><span class="sxs-lookup"><span data-stu-id="f7b96-302">Use the cmdlets that contain the Write verb for this task, such as `Write-Host`, `Write-Debug`, `Write-Warning`, and `Write-Verbose`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7b96-303">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7b96-303">SEE ALSO</span></span>

- [<span data-ttu-id="f7b96-304">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="f7b96-304">Disable-PSBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Disable-PSBreakpoint)
- [<span data-ttu-id="f7b96-305">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="f7b96-305">Enable-PSBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Enable-PSBreakpoint)
- [<span data-ttu-id="f7b96-306">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="f7b96-306">Get-PSBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Get-PSBreakpoint)
- [<span data-ttu-id="f7b96-307">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="f7b96-307">Get-PSCallStack</span></span>](xref:Microsoft.PowerShell.Utility.Get-PSCallStack)
- [<span data-ttu-id="f7b96-308">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="f7b96-308">Remove-PSBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Remove-PSBreakpoint)
- [<span data-ttu-id="f7b96-309">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="f7b96-309">Set-PSBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Set-PSBreakpoint)
- [<span data-ttu-id="f7b96-310">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="f7b96-310">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [<span data-ttu-id="f7b96-311">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="f7b96-311">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)