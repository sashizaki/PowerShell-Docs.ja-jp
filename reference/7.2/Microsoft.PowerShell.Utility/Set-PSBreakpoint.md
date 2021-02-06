---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-psbreakpoint?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSBreakpoint
ms.openlocfilehash: 5e2bdf435bf7cb9da3f31712c346beff29a11baf
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600411"
---
# <span data-ttu-id="29031-102">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="29031-102">Set-PSBreakpoint</span></span>

## <span data-ttu-id="29031-103">概要</span><span class="sxs-lookup"><span data-stu-id="29031-103">SYNOPSIS</span></span>
<span data-ttu-id="29031-104">行、コマンド、または変数にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="29031-104">Sets a breakpoint on a line, command, or variable.</span></span>

## <span data-ttu-id="29031-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="29031-105">SYNTAX</span></span>

### <span data-ttu-id="29031-106">Line (既定値)</span><span class="sxs-lookup"><span data-stu-id="29031-106">Line (Default)</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Column] <Int32>] [-Line] <Int32[]> [-Script] <String[]>
 [<CommonParameters>]
```

### <span data-ttu-id="29031-107">コマンド</span><span class="sxs-lookup"><span data-stu-id="29031-107">Command</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] -Command <String[]> [[-Script] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="29031-108">変数</span><span class="sxs-lookup"><span data-stu-id="29031-108">Variable</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Script] <String[]>] -Variable <String[]>
 [-Mode <VariableAccessMode>] [<CommonParameters>]
```

## <span data-ttu-id="29031-109">Description</span><span class="sxs-lookup"><span data-stu-id="29031-109">DESCRIPTION</span></span>

<span data-ttu-id="29031-110">`Set-PSBreakpoint`コマンドレットは、現在のセッションで実行されているスクリプトまたは任意のコマンドでブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="29031-110">The `Set-PSBreakpoint` cmdlet sets a breakpoint in a script or in any command run in the current session.</span></span> <span data-ttu-id="29031-111">を使用すると、 `Set-PSBreakpoint` 別のブレークポイントで停止したときに、スクリプトを実行したり、コマンドを実行したり、デバッグ中にブレークポイントを設定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="29031-111">You can use `Set-PSBreakpoint` to set a breakpoint before executing a script or running a command, or during debugging, when stopped at another breakpoint.</span></span>

<span data-ttu-id="29031-112">`Set-PSBreakpoint` リモートコンピューターにブレークポイントを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="29031-112">`Set-PSBreakpoint` cannot set a breakpoint on a remote computer.</span></span> <span data-ttu-id="29031-113">リモート コンピューターでスクリプトをデバッグするには、スクリプトをローカル コンピューターにコピーしてからローカルでデバッグします。</span><span class="sxs-lookup"><span data-stu-id="29031-113">To debug a script on a remote computer, copy the script to the local computer and then debug it locally.</span></span>

<span data-ttu-id="29031-114">各 `Set-PSBreakpoint` コマンドは、次の3種類のブレークポイントのいずれかを作成します。</span><span class="sxs-lookup"><span data-stu-id="29031-114">Each `Set-PSBreakpoint` command creates one of the following three types of breakpoints:</span></span>

- <span data-ttu-id="29031-115">行のブレークポイント-特定の行と列の座標にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="29031-115">Line breakpoint - Sets breakpoints at particular line and column coordinates.</span></span>
- <span data-ttu-id="29031-116">コマンドのブレークポイント-コマンドおよび関数にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="29031-116">Command breakpoint - Sets breakpoints on commands and functions.</span></span>
- <span data-ttu-id="29031-117">変数のブレークポイント-変数にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="29031-117">Variable breakpoint - Sets breakpoints on variables.</span></span>

<span data-ttu-id="29031-118">1つのコマンドで複数の行、コマンド、または変数にブレークポイントを設定でき `Set-PSBreakpoint` ますが、各 `Set-PSBreakpoint` コマンドで設定できるブレークポイントの種類は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="29031-118">You can set a breakpoint on multiple lines, commands, or variables in a single `Set-PSBreakpoint` command, but each `Set-PSBreakpoint` command sets only one type of breakpoint.</span></span>

<span data-ttu-id="29031-119">ブレークポイントでは、PowerShell は一時的に実行を停止し、デバッガーに制御を与えます。</span><span class="sxs-lookup"><span data-stu-id="29031-119">At a breakpoint, PowerShell temporarily stops executing and gives control to the debugger.</span></span> <span data-ttu-id="29031-120">コマンドプロンプトがに変わり、 `DBG\>` 一連のデバッガーコマンドを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="29031-120">The command prompt changes to `DBG\>`, and a set of debugger commands become available for use.</span></span> <span data-ttu-id="29031-121">ただし、 **Action** パラメーターを使用して、ブレークポイントの条件、ログ記録や診断などの追加のタスクを実行する命令などの代替応答を指定できます。</span><span class="sxs-lookup"><span data-stu-id="29031-121">However, you can use the **Action** parameter to specify an alternate response, such as conditions for the breakpoint or instructions to perform additional tasks such as logging or diagnostics.</span></span>

<span data-ttu-id="29031-122">`Set-PSBreakpoint`コマンドレットは、PowerShell スクリプトのデバッグ用に設計されたいくつかのコマンドレットの1つです。</span><span class="sxs-lookup"><span data-stu-id="29031-122">The `Set-PSBreakpoint` cmdlet is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="29031-123">PowerShell デバッガーの詳細については、「 [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29031-123">For more information about the PowerShell debugger, see [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span></span>

## <span data-ttu-id="29031-124">例</span><span class="sxs-lookup"><span data-stu-id="29031-124">EXAMPLES</span></span>

### <span data-ttu-id="29031-125">例 1: 行にブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="29031-125">Example 1: Set a breakpoint on a line</span></span>

<span data-ttu-id="29031-126">この例では、Sample.ps1 スクリプトの5行目にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="29031-126">This example sets a breakpoint at line 5 in the Sample.ps1 script.</span></span> <span data-ttu-id="29031-127">スクリプトを実行すると、5行目が実行される直前に実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="29031-127">When the script runs, execution stops immediately before line 5 would execute.</span></span>

```powershell
Set-PSBreakpoint -Script "sample.ps1" -Line 5
```

```output
Column     : 0
Line       : 5
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="29031-128">新しいブレークポイントを行番号で設定すると、コマンドレットによって、 `Set-PSBreakpoint` ブレークポイント ID とヒットカウントを含む行ブレークポイントオブジェクト (system.string) が生成さ **れます**。</span><span class="sxs-lookup"><span data-stu-id="29031-128">When you set a new breakpoint by line number, the `Set-PSBreakpoint` cmdlet generates a line breakpoint object (**System.Management.Automation.LineBreakpoint**) that includes the breakpoint ID and hit count.</span></span>

### <span data-ttu-id="29031-129">例 2: 関数にブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="29031-129">Example 2: Set a breakpoint on a function</span></span>

<span data-ttu-id="29031-130">この例では、Sample.ps1 コマンドレットの関数にコマンドのブレークポイントを作成し `Increment` ます。</span><span class="sxs-lookup"><span data-stu-id="29031-130">This example creates a command breakpoint on the `Increment` function in the Sample.ps1 cmdlet.</span></span> <span data-ttu-id="29031-131">スクリプトは、指定した関数を呼び出すたびに、直前に実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="29031-131">The script stops executing immediately before each call to the specified function.</span></span>

```powershell
Set-PSBreakpoint -Command "Increment" -Script "sample.ps1"
```

```Output
Command    : Increment
Action     :
Enabled    : True
HitCount   : 0
Id         : 1
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="29031-132">結果として、コマンドのブレークポイント オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="29031-132">The result is a command breakpoint object.</span></span> <span data-ttu-id="29031-133">スクリプトを実行する前に、 **ヒットカウント** プロパティの値は0です。</span><span class="sxs-lookup"><span data-stu-id="29031-133">Before the script runs, the value of the **HitCount** property is 0.</span></span>

### <span data-ttu-id="29031-134">例 3: 変数にブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="29031-134">Example 3: Set a breakpoint on a variable</span></span>

<span data-ttu-id="29031-135">この例では、Sample.ps1 スクリプトの **サーバー** 変数にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="29031-135">This example sets a breakpoint on the **Server** variable in the Sample.ps1 script.</span></span> <span data-ttu-id="29031-136">この例では、 **Mode** パラメーターを **ReadWrite** の値と共に使用して、変数の値が読み取られたときと値が変更される直前に実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="29031-136">It uses the **Mode** parameter with a value of **ReadWrite** to stop execution when the value of the variable is read and just before the value changes.</span></span>

```powershell
Set-PSBreakpoint -Script "sample.ps1" -Variable "Server" -Mode ReadWrite
```

### <span data-ttu-id="29031-137">例 4: 指定したテキストで始まるすべてのコマンドにブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="29031-137">Example 4: Set a breakpoint on every command that begins with specified text</span></span>

<span data-ttu-id="29031-138">この例では、"write" で始まる Sample.ps1 スクリプト内のすべてのコマンドにブレークポイントを設定します (など) `Write-Host` 。</span><span class="sxs-lookup"><span data-stu-id="29031-138">This example sets a breakpoint on every command in the Sample.ps1 script that begins with "write", such as `Write-Host`.</span></span>

```powershell
Set-PSBreakpoint -Script Sample.ps1 -Command "write*"
```

### <span data-ttu-id="29031-139">例 5: 変数の値に応じてブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="29031-139">Example 5: Set a breakpoint depending on the value of a variable</span></span>

<span data-ttu-id="29031-140">この例 `DiskTest` では、変数の値が2より大きい場合にのみ、Test.ps1 スクリプトの関数で実行を停止し `$Disk` ます。</span><span class="sxs-lookup"><span data-stu-id="29031-140">This example stops execution at the `DiskTest` function in the Test.ps1 script only when the value of the `$Disk` variable is greater than 2.</span></span>

```powershell
Set-PSBreakpoint -Script "test.ps1" -Command "DiskTest" -Action { if ($Disk -gt 2) { break } }
```

<span data-ttu-id="29031-141">**アクション** の値は、関数内の変数の値をテストするスクリプトブロックです `$Disk` 。</span><span class="sxs-lookup"><span data-stu-id="29031-141">The value of the **Action** is a script block that tests the value of the `$Disk` variable in the function.</span></span>

<span data-ttu-id="29031-142">アクションは、 `break` 条件が満たされた場合に、キーワードを使用して実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="29031-142">The action uses the `break` keyword to stop execution if the condition is met.</span></span> <span data-ttu-id="29031-143">代替 (および既定値) は **続行** されます。</span><span class="sxs-lookup"><span data-stu-id="29031-143">The alternative (and the default) is **Continue**.</span></span>

### <span data-ttu-id="29031-144">例 6: 関数にブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="29031-144">Example 6: Set a breakpoint on a function</span></span>

<span data-ttu-id="29031-145">この例では、関数にブレークポイントを設定 `CheckLog` します。</span><span class="sxs-lookup"><span data-stu-id="29031-145">This example sets a breakpoint on the `CheckLog` function.</span></span> <span data-ttu-id="29031-146">このコマンドにはスクリプトが指定されていないため、現在のセッションで実行されているすべてにブレークポイントが設定されます。</span><span class="sxs-lookup"><span data-stu-id="29031-146">Because the command does not specify a script, the breakpoint is set on anything that runs in the current session.</span></span> <span data-ttu-id="29031-147">デバッガーは、関数が宣言されているときではなく、呼び出されたときに中断します。</span><span class="sxs-lookup"><span data-stu-id="29031-147">The debugger breaks when the function is called, not when it is declared.</span></span>

```
PS> Set-PSBreakpoint -Command "checklog"
Id       : 0
Command  : checklog
Enabled  : True
HitCount : 0
Action   :

function CheckLog {
>> get-eventlog -log Application |
>> where {($_.source -like "TestApp") -and ($_.Message -like "*failed*")}
>>}
>>
PS> Checklog
DEBUG: Hit breakpoint(s)
DEBUG:  Function breakpoint on 'prompt:Checklog'
```

### <span data-ttu-id="29031-148">例 7: 複数行にブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="29031-148">Example 7: Set breakpoints on multiple lines</span></span>

<span data-ttu-id="29031-149">この例では、Sample.ps1 スクリプトに3つの行のブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="29031-149">This example sets three line breakpoints in the Sample.ps1 script.</span></span> <span data-ttu-id="29031-150">スクリプトで指定した各行の列 2 にブレークポイントが 1 つ設定されます。</span><span class="sxs-lookup"><span data-stu-id="29031-150">It sets one breakpoint at column 2 on each of the lines specified in the script.</span></span> <span data-ttu-id="29031-151">**Action** パラメーターで指定されたアクションは、すべてのブレークポイントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="29031-151">The action specified in the **Action** parameter applies to all breakpoints.</span></span>

```powershell
PS C:\> Set-PSBreakpoint -Script "sample.ps1" -Line 1, 14, 19 -Column 2 -Action {&(log.ps1)}
```

```Output
Column     : 2
Line       : 1
Action     :
Enabled    : True
HitCount   : 0
Id         : 6
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1


Column     : 2
Line       : 14
Action     :
Enabled    : True
HitCount   : 0
Id         : 7
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1


Column     : 2
Line       : 19
Action     :
Enabled    : True
HitCount   : 0
Id         : 8
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

## <span data-ttu-id="29031-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="29031-152">PARAMETERS</span></span>

### <span data-ttu-id="29031-153">-Action</span><span class="sxs-lookup"><span data-stu-id="29031-153">-Action</span></span>

<span data-ttu-id="29031-154">中断するのではなく、各ブレークポイントで実行するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="29031-154">Specifies commands that run at each breakpoint instead of breaking.</span></span> <span data-ttu-id="29031-155">コマンドを含むスクリプト ブロックを入力します。</span><span class="sxs-lookup"><span data-stu-id="29031-155">Enter a script block that contains the commands.</span></span> <span data-ttu-id="29031-156">このパラメーターを使用して、条件付きブレークポイントを設定することや、テストやログの記録など、他のタスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="29031-156">You can use this parameter to set conditional breakpoints or to perform other tasks, such as testing or logging.</span></span>

<span data-ttu-id="29031-157">このパラメーターを省略し、アクションを指定しない場合、ブレークポイントに達すると実行が停止し、デバッガーが開始されます。</span><span class="sxs-lookup"><span data-stu-id="29031-157">If this parameter is omitted, or no action is specified, execution stops at the breakpoint, and the debugger starts.</span></span>

<span data-ttu-id="29031-158">**Action** パラメーターを使用すると、アクションスクリプトブロックが各ブレークポイントで実行されます。</span><span class="sxs-lookup"><span data-stu-id="29031-158">When the **Action** parameter is used, the Action script block runs at each breakpoint.</span></span> <span data-ttu-id="29031-159">スクリプト ブロックに Break キーワードが含まれない場合、実行は停止しません。</span><span class="sxs-lookup"><span data-stu-id="29031-159">Execution does not stop unless the script block includes the Break keyword.</span></span> <span data-ttu-id="29031-160">スクリプト ブロックに Continue キーワードを使用した場合、次のブレークポイントに達する前に実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="29031-160">If you use the Continue keyword in the script block, execution resumes until the next breakpoint.</span></span>

<span data-ttu-id="29031-161">詳細については、「 [about_Script_Blocks](../Microsoft.PowerShell.Core/About/about_Script_Blocks.md)、 [about_Break](../Microsoft.PowerShell.Core/About/about_Break.md)、および [about_Continue](../Microsoft.PowerShell.Core/About/about_Continue.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29031-161">For more information, see [about_Script_Blocks](../Microsoft.PowerShell.Core/About/about_Script_Blocks.md), [about_Break](../Microsoft.PowerShell.Core/About/about_Break.md), and [about_Continue](../Microsoft.PowerShell.Core/About/about_Continue.md).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29031-162">-列</span><span class="sxs-lookup"><span data-stu-id="29031-162">-Column</span></span>

<span data-ttu-id="29031-163">実行を停止するスクリプト ファイル内の列の列番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="29031-163">Specifies the column number of the column in the script file on which execution stops.</span></span> <span data-ttu-id="29031-164">列番号を 1 つのみ入力します。</span><span class="sxs-lookup"><span data-stu-id="29031-164">Enter only one column number.</span></span> <span data-ttu-id="29031-165">既定値は 列 1 です。</span><span class="sxs-lookup"><span data-stu-id="29031-165">The default is column 1.</span></span>

<span data-ttu-id="29031-166">列の値は、ブレークポイントを指定するために **Line** パラメーターの値と共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="29031-166">The Column value is used with the value of the **Line** parameter to specify the breakpoint.</span></span> <span data-ttu-id="29031-167">**Line** パラメーターに複数の行が指定されている場合、 **column** パラメーターは、指定した各行の指定された列にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="29031-167">If the **Line** parameter specifies multiple lines, the **Column** parameter sets a breakpoint at the specified column on each of the specified lines.</span></span> <span data-ttu-id="29031-168">PowerShell は、指定された行と列の位置にある文字を含むステートメントまたは式の前に実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="29031-168">PowerShell stops executing before the statement or expression that includes the character at the specified line and column position.</span></span>

<span data-ttu-id="29031-169">列は、最上位の左余白の先頭が列番号 1 でカウントされます (0 ではありません)。</span><span class="sxs-lookup"><span data-stu-id="29031-169">Columns are counted from the top left margin beginning with column number 1 (not 0).</span></span> <span data-ttu-id="29031-170">スクリプトに存在しない列を指定した場合、エラーにはなりませんが、ブレークポイントが実行されることはありません。</span><span class="sxs-lookup"><span data-stu-id="29031-170">If you specify a column that does not exist in the script, an error is not declared, but the breakpoint is never executed.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Line
Aliases:

Required: False
Position: 2
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29031-171">-Command</span><span class="sxs-lookup"><span data-stu-id="29031-171">-Command</span></span>

<span data-ttu-id="29031-172">コマンドのブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="29031-172">Sets a command breakpoint.</span></span> <span data-ttu-id="29031-173">コマンドレット名 (など) `Get-Process` 、または関数名を入力します。</span><span class="sxs-lookup"><span data-stu-id="29031-173">Enter cmdlet names, such as `Get-Process`, or function names.</span></span> <span data-ttu-id="29031-174">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="29031-174">Wildcards are permitted.</span></span>

<span data-ttu-id="29031-175">各コマンドの各インスタンスが実行される直前に、実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="29031-175">Execution stops just before each instance of each command is executed.</span></span> <span data-ttu-id="29031-176">コマンドが関数の場合、関数が呼び出されるたびに、BEGIN、PROCESS、および END セクションごとに実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="29031-176">If the command is a function, execution stops each time the function is called and at each BEGIN, PROCESS, and END section.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Command
Aliases: C

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="29031-177">-Line</span><span class="sxs-lookup"><span data-stu-id="29031-177">-Line</span></span>

<span data-ttu-id="29031-178">スクリプトに行のブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="29031-178">Sets a line breakpoint in a script.</span></span> <span data-ttu-id="29031-179">コンマで区切って 1 つまたは複数の行番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="29031-179">Enter one or more line numbers, separated by commas.</span></span> <span data-ttu-id="29031-180">PowerShell は、指定された各行で始まるステートメントを実行する直前に停止します。</span><span class="sxs-lookup"><span data-stu-id="29031-180">PowerShell stops immediately before executing the statement that begins on each of the specified lines.</span></span>

<span data-ttu-id="29031-181">行は、スクリプト ファイルの最上位の左余白の先頭が行番号 1 でカウントされます (0 ではありません)。</span><span class="sxs-lookup"><span data-stu-id="29031-181">Lines are counted from the top left margin of the script file beginning with line number 1 (not 0).</span></span>
<span data-ttu-id="29031-182">空白行を指定した場合、次の空白でない行の前で実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="29031-182">If you specify a blank line, execution stops before the next non-blank line.</span></span> <span data-ttu-id="29031-183">行が範囲外にある場合、ブレークポイントがヒットすることはありません。</span><span class="sxs-lookup"><span data-stu-id="29031-183">If the line is out of range, the breakpoint is never hit.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Line
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29031-184">-Mode</span><span class="sxs-lookup"><span data-stu-id="29031-184">-Mode</span></span>

<span data-ttu-id="29031-185">変数のブレークポイントをトリガーするアクセスモードを指定します。</span><span class="sxs-lookup"><span data-stu-id="29031-185">Specifies the mode of access that triggers variable breakpoints.</span></span> <span data-ttu-id="29031-186">既定値は **Write** です。</span><span class="sxs-lookup"><span data-stu-id="29031-186">The default is **Write**.</span></span>

<span data-ttu-id="29031-187">このパラメーターは、 **Variable** パラメーターがコマンドで使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="29031-187">This parameter is valid only when the **Variable** parameter is used in the command.</span></span> <span data-ttu-id="29031-188">このモードは、コマンドに設定されたブレークポイントすべてに適用されます。</span><span class="sxs-lookup"><span data-stu-id="29031-188">The mode applies to all breakpoints set in the command.</span></span> <span data-ttu-id="29031-189">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29031-189">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="29031-190">**書き込み** -新しい値が変数に書き込まれる直前に実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="29031-190">**Write** - Stops execution immediately before a new value is written to the variable.</span></span>
- <span data-ttu-id="29031-191">**読み取り** -変数が読み取られたとき、つまり、割り当て、表示、または使用されるときに、変数の値にアクセスしたときに実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="29031-191">**Read** - Stops execution when the variable is read, that is, when its value is accessed, either to be assigned, displayed, or used.</span></span> <span data-ttu-id="29031-192">Read モードでは、変数の値が変更されたときは実行を停止しません。</span><span class="sxs-lookup"><span data-stu-id="29031-192">In read mode, execution does not stop when the value of the variable changes.</span></span>
- <span data-ttu-id="29031-193">**ReadWrite** -変数の読み取りまたは書き込み時に実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="29031-193">**ReadWrite** - Stops execution when the variable is read or written.</span></span>

```yaml
Type: System.Management.Automation.VariableAccessMode
Parameter Sets: Variable
Aliases:
Accepted values: Read, Write, ReadWrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29031-194">-スクリプト</span><span class="sxs-lookup"><span data-stu-id="29031-194">-Script</span></span>

<span data-ttu-id="29031-195">このコマンドレットによってブレークポイントが設定されるスクリプトファイルの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="29031-195">Specifies an array of script files that this cmdlet sets a breakpoint in.</span></span> <span data-ttu-id="29031-196">1 つまたは複数のスクリプト ファイルのパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="29031-196">Enter the paths and file names of one or more script files.</span></span> <span data-ttu-id="29031-197">ファイルが現在のディレクトリにある場合、パスを省略することができます。</span><span class="sxs-lookup"><span data-stu-id="29031-197">If the files are in the current directory, you can omit the path.</span></span>
<span data-ttu-id="29031-198">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="29031-198">Wildcards are permitted.</span></span>

<span data-ttu-id="29031-199">既定では、変数のブレークポイントとコマンドのブレークポイントは、現在のセッションで実行されているコマンドに設定されます。</span><span class="sxs-lookup"><span data-stu-id="29031-199">By default, variable breakpoints and command breakpoints are set on any command that runs in the current session.</span></span> <span data-ttu-id="29031-200">このパラメーターは、行のブレークポイントを設定するときにのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="29031-200">This parameter is required only when setting a line breakpoint.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Line, Command, Variable
Aliases:

Required: True (Line), False (Command, Variable)
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29031-201">-Variable</span><span class="sxs-lookup"><span data-stu-id="29031-201">-Variable</span></span>

<span data-ttu-id="29031-202">このコマンドレットでブレークポイントを設定する変数の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="29031-202">Specifies an array of variables that this cmdlet sets breakpoints on.</span></span> <span data-ttu-id="29031-203">ドル記号を付けずに変数のコンマ区切りリストを入力し `$` ます ()。</span><span class="sxs-lookup"><span data-stu-id="29031-203">Enter a comma-separated list of variables without dollar signs (`$`).</span></span>

<span data-ttu-id="29031-204">**Mode** パラメーターを使用して、ブレークポイントをトリガーするアクセスモードを決定します。</span><span class="sxs-lookup"><span data-stu-id="29031-204">Use the **Mode** parameter to determine the mode of access that triggers the breakpoints.</span></span> <span data-ttu-id="29031-205">既定のモードは Write であり、新しい値が変数に書き込まれる直前に実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="29031-205">The default mode, Write, stops execution just before a new value is written to the variable.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Variable
Aliases: V

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29031-206">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="29031-206">CommonParameters</span></span>

<span data-ttu-id="29031-207">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="29031-207">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="29031-208">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29031-208">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="29031-209">入力</span><span class="sxs-lookup"><span data-stu-id="29031-209">INPUTS</span></span>

### <span data-ttu-id="29031-210">なし</span><span class="sxs-lookup"><span data-stu-id="29031-210">None</span></span>
<span data-ttu-id="29031-211">入力をにパイプすることはできません `Set-PSBreakpoint` 。</span><span class="sxs-lookup"><span data-stu-id="29031-211">You cannot pipe input to `Set-PSBreakpoint`.</span></span>

## <span data-ttu-id="29031-212">出力</span><span class="sxs-lookup"><span data-stu-id="29031-212">OUTPUTS</span></span>

### <span data-ttu-id="29031-213">ブレークポイントオブジェクト (system.string、system......................... CommandBreakpoint ポイント、</span><span class="sxs-lookup"><span data-stu-id="29031-213">Breakpoint object (System.Management.Automation.LineBreakpoint, System.Management.Automation.VariableBreakpoint, System.Management.Automation.CommandBreakpoint)</span></span>

<span data-ttu-id="29031-214">`Set-PSBreakpoint` 設定されている各ブレークポイントを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="29031-214">`Set-PSBreakpoint` returns an object that represents each breakpoint that it sets.</span></span>

## <span data-ttu-id="29031-215">注</span><span class="sxs-lookup"><span data-stu-id="29031-215">NOTES</span></span>

- <span data-ttu-id="29031-216">`Set-PSBreakpoint` リモートコンピューターにブレークポイントを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="29031-216">`Set-PSBreakpoint` cannot set a breakpoint on a remote computer.</span></span> <span data-ttu-id="29031-217">リモート コンピューターでスクリプトをデバッグするには、スクリプトをローカル コンピューターにコピーしてからローカルでデバッグします。</span><span class="sxs-lookup"><span data-stu-id="29031-217">To debug a script on a remote computer, copy the script to the local computer and then debug it locally.</span></span>
- <span data-ttu-id="29031-218">複数の行、コマンド、または変数にブレークポイントを設定すると、によっ `Set-PSBreakpoint` て各エントリのブレークポイントオブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="29031-218">When you set a breakpoint on more than one line, command, or variable, `Set-PSBreakpoint` generates a breakpoint object for each entry.</span></span>
- <span data-ttu-id="29031-219">コマンド プロンプトで関数または変数にブレークポイントを設定すると、関数または変数を作成する前または後に、ブレークポイントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="29031-219">When setting a breakpoint on a function or variable at the command prompt, you can set the breakpoint before or after you create the function or variable.</span></span>

## <span data-ttu-id="29031-220">関連リンク</span><span class="sxs-lookup"><span data-stu-id="29031-220">RELATED LINKS</span></span>

[<span data-ttu-id="29031-221">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="29031-221">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="29031-222">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="29031-222">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="29031-223">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="29031-223">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="29031-224">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="29031-224">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="29031-225">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="29031-225">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

