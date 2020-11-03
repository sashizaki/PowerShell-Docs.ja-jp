---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-psbreakpoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSBreakpoint
ms.openlocfilehash: 5968c51f04199d59d3514cdc85ba3f15d02475a4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213704"
---
# <span data-ttu-id="23471-103">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="23471-103">Set-PSBreakpoint</span></span>

## <span data-ttu-id="23471-104">概要</span><span class="sxs-lookup"><span data-stu-id="23471-104">SYNOPSIS</span></span>
<span data-ttu-id="23471-105">行、コマンド、または変数にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="23471-105">Sets a breakpoint on a line, command, or variable.</span></span>

## <span data-ttu-id="23471-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="23471-106">SYNTAX</span></span>

### <span data-ttu-id="23471-107">Line (既定値)</span><span class="sxs-lookup"><span data-stu-id="23471-107">Line (Default)</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Column] <Int32>] [-Line] <Int32[]> [-Script] <String[]>
 [<CommonParameters>]
```

### <span data-ttu-id="23471-108">コマンド</span><span class="sxs-lookup"><span data-stu-id="23471-108">Command</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] -Command <String[]> [[-Script] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="23471-109">変数</span><span class="sxs-lookup"><span data-stu-id="23471-109">Variable</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Script] <String[]>] -Variable <String[]>
 [-Mode <VariableAccessMode>] [<CommonParameters>]
```

## <span data-ttu-id="23471-110">Description</span><span class="sxs-lookup"><span data-stu-id="23471-110">DESCRIPTION</span></span>

<span data-ttu-id="23471-111">`Set-PSBreakpoint`コマンドレットは、現在のセッションで実行されているスクリプトまたは任意のコマンドでブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="23471-111">The `Set-PSBreakpoint` cmdlet sets a breakpoint in a script or in any command run in the current session.</span></span> <span data-ttu-id="23471-112">を使用すると、 `Set-PSBreakpoint` 別のブレークポイントで停止したときに、スクリプトを実行したり、コマンドを実行したり、デバッグ中にブレークポイントを設定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="23471-112">You can use `Set-PSBreakpoint` to set a breakpoint before executing a script or running a command, or during debugging, when stopped at another breakpoint.</span></span>

<span data-ttu-id="23471-113">`Set-PSBreakpoint` リモートコンピューターにブレークポイントを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="23471-113">`Set-PSBreakpoint` cannot set a breakpoint on a remote computer.</span></span> <span data-ttu-id="23471-114">リモート コンピューターでスクリプトをデバッグするには、スクリプトをローカル コンピューターにコピーしてからローカルでデバッグします。</span><span class="sxs-lookup"><span data-stu-id="23471-114">To debug a script on a remote computer, copy the script to the local computer and then debug it locally.</span></span>

<span data-ttu-id="23471-115">各 `Set-PSBreakpoint` コマンドは、次の3種類のブレークポイントのいずれかを作成します。</span><span class="sxs-lookup"><span data-stu-id="23471-115">Each `Set-PSBreakpoint` command creates one of the following three types of breakpoints:</span></span>

- <span data-ttu-id="23471-116">行のブレークポイント-特定の行と列の座標にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="23471-116">Line breakpoint - Sets breakpoints at particular line and column coordinates.</span></span>
- <span data-ttu-id="23471-117">コマンドのブレークポイント-コマンドおよび関数にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="23471-117">Command breakpoint - Sets breakpoints on commands and functions.</span></span>
- <span data-ttu-id="23471-118">変数のブレークポイント-変数にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="23471-118">Variable breakpoint - Sets breakpoints on variables.</span></span>

<span data-ttu-id="23471-119">1つのコマンドで複数の行、コマンド、または変数にブレークポイントを設定でき `Set-PSBreakpoint` ますが、各 `Set-PSBreakpoint` コマンドで設定できるブレークポイントの種類は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="23471-119">You can set a breakpoint on multiple lines, commands, or variables in a single `Set-PSBreakpoint` command, but each `Set-PSBreakpoint` command sets only one type of breakpoint.</span></span>

<span data-ttu-id="23471-120">ブレークポイントでは、PowerShell は一時的に実行を停止し、デバッガーに制御を与えます。</span><span class="sxs-lookup"><span data-stu-id="23471-120">At a breakpoint, PowerShell temporarily stops executing and gives control to the debugger.</span></span> <span data-ttu-id="23471-121">コマンドプロンプトがに変わり、 `DBG\>` 一連のデバッガーコマンドを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="23471-121">The command prompt changes to `DBG\>`, and a set of debugger commands become available for use.</span></span> <span data-ttu-id="23471-122">ただし、 **Action** パラメーターを使用して、ブレークポイントの条件、ログ記録や診断などの追加のタスクを実行する命令などの代替応答を指定できます。</span><span class="sxs-lookup"><span data-stu-id="23471-122">However, you can use the **Action** parameter to specify an alternate response, such as conditions for the breakpoint or instructions to perform additional tasks such as logging or diagnostics.</span></span>

<span data-ttu-id="23471-123">`Set-PSBreakpoint`コマンドレットは、PowerShell スクリプトのデバッグ用に設計されたいくつかのコマンドレットの1つです。</span><span class="sxs-lookup"><span data-stu-id="23471-123">The `Set-PSBreakpoint` cmdlet is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="23471-124">PowerShell デバッガーの詳細については、「 [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23471-124">For more information about the PowerShell debugger, see [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span></span>

## <span data-ttu-id="23471-125">例</span><span class="sxs-lookup"><span data-stu-id="23471-125">EXAMPLES</span></span>

### <span data-ttu-id="23471-126">例 1: 行にブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="23471-126">Example 1: Set a breakpoint on a line</span></span>

<span data-ttu-id="23471-127">この例では、Sample.ps1 スクリプトの5行目にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="23471-127">This example sets a breakpoint at line 5 in the Sample.ps1 script.</span></span> <span data-ttu-id="23471-128">スクリプトを実行すると、5行目が実行される直前に実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="23471-128">When the script runs, execution stops immediately before line 5 would execute.</span></span>

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

<span data-ttu-id="23471-129">新しいブレークポイントを行番号で設定すると、コマンドレットによって、 `Set-PSBreakpoint` ブレークポイント ID とヒットカウントを含む行ブレークポイントオブジェクト (system.string) が生成さ **れます** 。</span><span class="sxs-lookup"><span data-stu-id="23471-129">When you set a new breakpoint by line number, the `Set-PSBreakpoint` cmdlet generates a line breakpoint object ( **System.Management.Automation.LineBreakpoint** ) that includes the breakpoint ID and hit count.</span></span>

### <span data-ttu-id="23471-130">例 2: 関数にブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="23471-130">Example 2: Set a breakpoint on a function</span></span>

<span data-ttu-id="23471-131">この例では、Sample.ps1 コマンドレットの関数にコマンドのブレークポイントを作成し `Increment` ます。</span><span class="sxs-lookup"><span data-stu-id="23471-131">This example creates a command breakpoint on the `Increment` function in the Sample.ps1 cmdlet.</span></span> <span data-ttu-id="23471-132">スクリプトは、指定した関数を呼び出すたびに、直前に実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="23471-132">The script stops executing immediately before each call to the specified function.</span></span>

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

<span data-ttu-id="23471-133">結果として、コマンドのブレークポイント オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="23471-133">The result is a command breakpoint object.</span></span> <span data-ttu-id="23471-134">スクリプトを実行する前に、 **ヒットカウント** プロパティの値は0です。</span><span class="sxs-lookup"><span data-stu-id="23471-134">Before the script runs, the value of the **HitCount** property is 0.</span></span>

### <span data-ttu-id="23471-135">例 3: 変数にブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="23471-135">Example 3: Set a breakpoint on a variable</span></span>

<span data-ttu-id="23471-136">この例では、Sample.ps1 スクリプトの **サーバー** 変数にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="23471-136">This example sets a breakpoint on the **Server** variable in the Sample.ps1 script.</span></span> <span data-ttu-id="23471-137">この例では、 **Mode** パラメーターを **ReadWrite** の値と共に使用して、変数の値が読み取られたときと値が変更される直前に実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="23471-137">It uses the **Mode** parameter with a value of **ReadWrite** to stop execution when the value of the variable is read and just before the value changes.</span></span>

```powershell
Set-PSBreakpoint -Script "sample.ps1" -Variable "Server" -Mode ReadWrite
```

### <span data-ttu-id="23471-138">例 4: 指定したテキストで始まるすべてのコマンドにブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="23471-138">Example 4: Set a breakpoint on every command that begins with specified text</span></span>

<span data-ttu-id="23471-139">この例では、"write" で始まる Sample.ps1 スクリプト内のすべてのコマンドにブレークポイントを設定します (など) `Write-Host` 。</span><span class="sxs-lookup"><span data-stu-id="23471-139">This example sets a breakpoint on every command in the Sample.ps1 script that begins with "write", such as `Write-Host`.</span></span>

```powershell
Set-PSBreakpoint -Script Sample.ps1 -Command "write*"
```

### <span data-ttu-id="23471-140">例 5: 変数の値に応じてブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="23471-140">Example 5: Set a breakpoint depending on the value of a variable</span></span>

<span data-ttu-id="23471-141">この例 `DiskTest` では、変数の値が2より大きい場合にのみ、Test.ps1 スクリプトの関数で実行を停止し `$Disk` ます。</span><span class="sxs-lookup"><span data-stu-id="23471-141">This example stops execution at the `DiskTest` function in the Test.ps1 script only when the value of the `$Disk` variable is greater than 2.</span></span>

```powershell
Set-PSBreakpoint -Script "test.ps1" -Command "DiskTest" -Action { if ($Disk -gt 2) { break } }
```

<span data-ttu-id="23471-142">**アクション** の値は、関数内の変数の値をテストするスクリプトブロックです `$Disk` 。</span><span class="sxs-lookup"><span data-stu-id="23471-142">The value of the **Action** is a script block that tests the value of the `$Disk` variable in the function.</span></span>

<span data-ttu-id="23471-143">アクションは、 `break` 条件が満たされた場合に、キーワードを使用して実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="23471-143">The action uses the `break` keyword to stop execution if the condition is met.</span></span> <span data-ttu-id="23471-144">代替 (および既定値) は **続行** されます。</span><span class="sxs-lookup"><span data-stu-id="23471-144">The alternative (and the default) is **Continue** .</span></span>

### <span data-ttu-id="23471-145">例 6: 関数にブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="23471-145">Example 6: Set a breakpoint on a function</span></span>

<span data-ttu-id="23471-146">この例では、関数にブレークポイントを設定 `CheckLog` します。</span><span class="sxs-lookup"><span data-stu-id="23471-146">This example sets a breakpoint on the `CheckLog` function.</span></span> <span data-ttu-id="23471-147">このコマンドにはスクリプトが指定されていないため、現在のセッションで実行されているすべてにブレークポイントが設定されます。</span><span class="sxs-lookup"><span data-stu-id="23471-147">Because the command does not specify a script, the breakpoint is set on anything that runs in the current session.</span></span> <span data-ttu-id="23471-148">デバッガーは、関数が宣言されているときではなく、呼び出されたときに中断します。</span><span class="sxs-lookup"><span data-stu-id="23471-148">The debugger breaks when the function is called, not when it is declared.</span></span>

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

### <span data-ttu-id="23471-149">例 7: 複数行にブレークポイントを設定する</span><span class="sxs-lookup"><span data-stu-id="23471-149">Example 7: Set breakpoints on multiple lines</span></span>

<span data-ttu-id="23471-150">この例では、Sample.ps1 スクリプトに3つの行のブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="23471-150">This example sets three line breakpoints in the Sample.ps1 script.</span></span> <span data-ttu-id="23471-151">スクリプトで指定した各行の列 2 にブレークポイントが 1 つ設定されます。</span><span class="sxs-lookup"><span data-stu-id="23471-151">It sets one breakpoint at column 2 on each of the lines specified in the script.</span></span> <span data-ttu-id="23471-152">**Action** パラメーターで指定されたアクションは、すべてのブレークポイントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="23471-152">The action specified in the **Action** parameter applies to all breakpoints.</span></span>

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

## <span data-ttu-id="23471-153">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="23471-153">PARAMETERS</span></span>

### <span data-ttu-id="23471-154">-Action</span><span class="sxs-lookup"><span data-stu-id="23471-154">-Action</span></span>

<span data-ttu-id="23471-155">中断するのではなく、各ブレークポイントで実行するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="23471-155">Specifies commands that run at each breakpoint instead of breaking.</span></span> <span data-ttu-id="23471-156">コマンドを含むスクリプト ブロックを入力します。</span><span class="sxs-lookup"><span data-stu-id="23471-156">Enter a script block that contains the commands.</span></span> <span data-ttu-id="23471-157">このパラメーターを使用して、条件付きブレークポイントを設定することや、テストやログの記録など、他のタスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="23471-157">You can use this parameter to set conditional breakpoints or to perform other tasks, such as testing or logging.</span></span>

<span data-ttu-id="23471-158">このパラメーターを省略し、アクションを指定しない場合、ブレークポイントに達すると実行が停止し、デバッガーが開始されます。</span><span class="sxs-lookup"><span data-stu-id="23471-158">If this parameter is omitted, or no action is specified, execution stops at the breakpoint, and the debugger starts.</span></span>

<span data-ttu-id="23471-159">**Action** パラメーターを使用すると、アクションスクリプトブロックが各ブレークポイントで実行されます。</span><span class="sxs-lookup"><span data-stu-id="23471-159">When the **Action** parameter is used, the Action script block runs at each breakpoint.</span></span> <span data-ttu-id="23471-160">スクリプト ブロックに Break キーワードが含まれない場合、実行は停止しません。</span><span class="sxs-lookup"><span data-stu-id="23471-160">Execution does not stop unless the script block includes the Break keyword.</span></span> <span data-ttu-id="23471-161">スクリプト ブロックに Continue キーワードを使用した場合、次のブレークポイントに達する前に実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="23471-161">If you use the Continue keyword in the script block, execution resumes until the next breakpoint.</span></span>

<span data-ttu-id="23471-162">詳細については、「 [about_Script_Blocks](../Microsoft.PowerShell.Core/About/about_Script_Blocks.md)、 [about_Break](../Microsoft.PowerShell.Core/About/about_Break.md)、および [about_Continue](../Microsoft.PowerShell.Core/About/about_Continue.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23471-162">For more information, see [about_Script_Blocks](../Microsoft.PowerShell.Core/About/about_Script_Blocks.md), [about_Break](../Microsoft.PowerShell.Core/About/about_Break.md), and [about_Continue](../Microsoft.PowerShell.Core/About/about_Continue.md).</span></span>

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

### <span data-ttu-id="23471-163">-列</span><span class="sxs-lookup"><span data-stu-id="23471-163">-Column</span></span>

<span data-ttu-id="23471-164">実行を停止するスクリプト ファイル内の列の列番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="23471-164">Specifies the column number of the column in the script file on which execution stops.</span></span> <span data-ttu-id="23471-165">列番号を 1 つのみ入力します。</span><span class="sxs-lookup"><span data-stu-id="23471-165">Enter only one column number.</span></span> <span data-ttu-id="23471-166">既定値は 列 1 です。</span><span class="sxs-lookup"><span data-stu-id="23471-166">The default is column 1.</span></span>

<span data-ttu-id="23471-167">列の値は、ブレークポイントを指定するために **Line** パラメーターの値と共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="23471-167">The Column value is used with the value of the **Line** parameter to specify the breakpoint.</span></span> <span data-ttu-id="23471-168">**Line** パラメーターに複数の行が指定されている場合、 **column** パラメーターは、指定した各行の指定された列にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="23471-168">If the **Line** parameter specifies multiple lines, the **Column** parameter sets a breakpoint at the specified column on each of the specified lines.</span></span> <span data-ttu-id="23471-169">PowerShell は、指定された行と列の位置にある文字を含むステートメントまたは式の前に実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="23471-169">PowerShell stops executing before the statement or expression that includes the character at the specified line and column position.</span></span>

<span data-ttu-id="23471-170">列は、最上位の左余白の先頭が列番号 1 でカウントされます (0 ではありません)。</span><span class="sxs-lookup"><span data-stu-id="23471-170">Columns are counted from the top left margin beginning with column number 1 (not 0).</span></span> <span data-ttu-id="23471-171">スクリプトに存在しない列を指定した場合、エラーにはなりませんが、ブレークポイントが実行されることはありません。</span><span class="sxs-lookup"><span data-stu-id="23471-171">If you specify a column that does not exist in the script, an error is not declared, but the breakpoint is never executed.</span></span>

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

### <span data-ttu-id="23471-172">-Command</span><span class="sxs-lookup"><span data-stu-id="23471-172">-Command</span></span>

<span data-ttu-id="23471-173">コマンドのブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="23471-173">Sets a command breakpoint.</span></span> <span data-ttu-id="23471-174">コマンドレット名 (など) `Get-Process` 、または関数名を入力します。</span><span class="sxs-lookup"><span data-stu-id="23471-174">Enter cmdlet names, such as `Get-Process`, or function names.</span></span> <span data-ttu-id="23471-175">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="23471-175">Wildcards are permitted.</span></span>

<span data-ttu-id="23471-176">各コマンドの各インスタンスが実行される直前に、実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="23471-176">Execution stops just before each instance of each command is executed.</span></span> <span data-ttu-id="23471-177">コマンドが関数の場合、関数が呼び出されるたびに、BEGIN、PROCESS、および END セクションごとに実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="23471-177">If the command is a function, execution stops each time the function is called and at each BEGIN, PROCESS, and END section.</span></span>

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

### <span data-ttu-id="23471-178">-Line</span><span class="sxs-lookup"><span data-stu-id="23471-178">-Line</span></span>

<span data-ttu-id="23471-179">スクリプトに行のブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="23471-179">Sets a line breakpoint in a script.</span></span> <span data-ttu-id="23471-180">コンマで区切って 1 つまたは複数の行番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="23471-180">Enter one or more line numbers, separated by commas.</span></span> <span data-ttu-id="23471-181">PowerShell は、指定された各行で始まるステートメントを実行する直前に停止します。</span><span class="sxs-lookup"><span data-stu-id="23471-181">PowerShell stops immediately before executing the statement that begins on each of the specified lines.</span></span>

<span data-ttu-id="23471-182">行は、スクリプト ファイルの最上位の左余白の先頭が行番号 1 でカウントされます (0 ではありません)。</span><span class="sxs-lookup"><span data-stu-id="23471-182">Lines are counted from the top left margin of the script file beginning with line number 1 (not 0).</span></span>
<span data-ttu-id="23471-183">空白行を指定した場合、次の空白でない行の前で実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="23471-183">If you specify a blank line, execution stops before the next non-blank line.</span></span> <span data-ttu-id="23471-184">行が範囲外にある場合、ブレークポイントがヒットすることはありません。</span><span class="sxs-lookup"><span data-stu-id="23471-184">If the line is out of range, the breakpoint is never hit.</span></span>

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

### <span data-ttu-id="23471-185">-Mode</span><span class="sxs-lookup"><span data-stu-id="23471-185">-Mode</span></span>

<span data-ttu-id="23471-186">変数のブレークポイントをトリガーするアクセスモードを指定します。</span><span class="sxs-lookup"><span data-stu-id="23471-186">Specifies the mode of access that triggers variable breakpoints.</span></span> <span data-ttu-id="23471-187">既定値は **Write** です。</span><span class="sxs-lookup"><span data-stu-id="23471-187">The default is **Write** .</span></span>

<span data-ttu-id="23471-188">このパラメーターは、 **Variable** パラメーターがコマンドで使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="23471-188">This parameter is valid only when the **Variable** parameter is used in the command.</span></span> <span data-ttu-id="23471-189">このモードは、コマンドに設定されたブレークポイントすべてに適用されます。</span><span class="sxs-lookup"><span data-stu-id="23471-189">The mode applies to all breakpoints set in the command.</span></span> <span data-ttu-id="23471-190">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="23471-190">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="23471-191">**書き込み** -新しい値が変数に書き込まれる直前に実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="23471-191">**Write** - Stops execution immediately before a new value is written to the variable.</span></span>
- <span data-ttu-id="23471-192">**読み取り** -変数が読み取られたとき、つまり、割り当て、表示、または使用されるときに、変数の値にアクセスしたときに実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="23471-192">**Read** - Stops execution when the variable is read, that is, when its value is accessed, either to be assigned, displayed, or used.</span></span> <span data-ttu-id="23471-193">Read モードでは、変数の値が変更されたときは実行を停止しません。</span><span class="sxs-lookup"><span data-stu-id="23471-193">In read mode, execution does not stop when the value of the variable changes.</span></span>
- <span data-ttu-id="23471-194">**ReadWrite** -変数の読み取りまたは書き込み時に実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="23471-194">**ReadWrite** - Stops execution when the variable is read or written.</span></span>

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

### <span data-ttu-id="23471-195">-スクリプト</span><span class="sxs-lookup"><span data-stu-id="23471-195">-Script</span></span>

<span data-ttu-id="23471-196">このコマンドレットによってブレークポイントが設定されるスクリプトファイルの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="23471-196">Specifies an array of script files that this cmdlet sets a breakpoint in.</span></span> <span data-ttu-id="23471-197">1 つまたは複数のスクリプト ファイルのパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="23471-197">Enter the paths and file names of one or more script files.</span></span> <span data-ttu-id="23471-198">ファイルが現在のディレクトリにある場合、パスを省略することができます。</span><span class="sxs-lookup"><span data-stu-id="23471-198">If the files are in the current directory, you can omit the path.</span></span>
<span data-ttu-id="23471-199">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="23471-199">Wildcards are permitted.</span></span>

<span data-ttu-id="23471-200">既定では、変数のブレークポイントとコマンドのブレークポイントは、現在のセッションで実行されているコマンドに設定されます。</span><span class="sxs-lookup"><span data-stu-id="23471-200">By default, variable breakpoints and command breakpoints are set on any command that runs in the current session.</span></span> <span data-ttu-id="23471-201">このパラメーターは、行のブレークポイントを設定するときにのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="23471-201">This parameter is required only when setting a line breakpoint.</span></span>

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

### <span data-ttu-id="23471-202">-Variable</span><span class="sxs-lookup"><span data-stu-id="23471-202">-Variable</span></span>

<span data-ttu-id="23471-203">このコマンドレットでブレークポイントを設定する変数の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="23471-203">Specifies an array of variables that this cmdlet sets breakpoints on.</span></span> <span data-ttu-id="23471-204">ドル記号を付けずに変数のコンマ区切りリストを入力し `$` ます ()。</span><span class="sxs-lookup"><span data-stu-id="23471-204">Enter a comma-separated list of variables without dollar signs (`$`).</span></span>

<span data-ttu-id="23471-205">**Mode** パラメーターを使用して、ブレークポイントをトリガーするアクセスモードを決定します。</span><span class="sxs-lookup"><span data-stu-id="23471-205">Use the **Mode** parameter to determine the mode of access that triggers the breakpoints.</span></span> <span data-ttu-id="23471-206">既定のモードは Write であり、新しい値が変数に書き込まれる直前に実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="23471-206">The default mode, Write, stops execution just before a new value is written to the variable.</span></span>

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

### <span data-ttu-id="23471-207">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="23471-207">CommonParameters</span></span>

<span data-ttu-id="23471-208">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="23471-208">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="23471-209">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23471-209">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="23471-210">入力</span><span class="sxs-lookup"><span data-stu-id="23471-210">INPUTS</span></span>

### <span data-ttu-id="23471-211">なし</span><span class="sxs-lookup"><span data-stu-id="23471-211">None</span></span>
<span data-ttu-id="23471-212">入力をにパイプすることはできません `Set-PSBreakpoint` 。</span><span class="sxs-lookup"><span data-stu-id="23471-212">You cannot pipe input to `Set-PSBreakpoint`.</span></span>

## <span data-ttu-id="23471-213">出力</span><span class="sxs-lookup"><span data-stu-id="23471-213">OUTPUTS</span></span>

### <span data-ttu-id="23471-214">ブレークポイントオブジェクト (system.string、system......................... CommandBreakpoint ポイント、</span><span class="sxs-lookup"><span data-stu-id="23471-214">Breakpoint object (System.Management.Automation.LineBreakpoint, System.Management.Automation.VariableBreakpoint, System.Management.Automation.CommandBreakpoint)</span></span>

<span data-ttu-id="23471-215">`Set-PSBreakpoint` 設定されている各ブレークポイントを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="23471-215">`Set-PSBreakpoint` returns an object that represents each breakpoint that it sets.</span></span>

## <span data-ttu-id="23471-216">注</span><span class="sxs-lookup"><span data-stu-id="23471-216">NOTES</span></span>

- <span data-ttu-id="23471-217">`Set-PSBreakpoint` リモートコンピューターにブレークポイントを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="23471-217">`Set-PSBreakpoint` cannot set a breakpoint on a remote computer.</span></span> <span data-ttu-id="23471-218">リモート コンピューターでスクリプトをデバッグするには、スクリプトをローカル コンピューターにコピーしてからローカルでデバッグします。</span><span class="sxs-lookup"><span data-stu-id="23471-218">To debug a script on a remote computer, copy the script to the local computer and then debug it locally.</span></span>
- <span data-ttu-id="23471-219">複数の行、コマンド、または変数にブレークポイントを設定すると、によっ `Set-PSBreakpoint` て各エントリのブレークポイントオブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="23471-219">When you set a breakpoint on more than one line, command, or variable, `Set-PSBreakpoint` generates a breakpoint object for each entry.</span></span>
- <span data-ttu-id="23471-220">コマンド プロンプトで関数または変数にブレークポイントを設定すると、関数または変数を作成する前または後に、ブレークポイントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="23471-220">When setting a breakpoint on a function or variable at the command prompt, you can set the breakpoint before or after you create the function or variable.</span></span>

## <span data-ttu-id="23471-221">関連リンク</span><span class="sxs-lookup"><span data-stu-id="23471-221">RELATED LINKS</span></span>

[<span data-ttu-id="23471-222">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="23471-222">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="23471-223">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="23471-223">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="23471-224">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="23471-224">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="23471-225">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="23471-225">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="23471-226">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="23471-226">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)
