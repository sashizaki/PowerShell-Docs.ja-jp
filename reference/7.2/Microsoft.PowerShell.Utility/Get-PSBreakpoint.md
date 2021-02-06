---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-psbreakpoint?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSBreakpoint
ms.openlocfilehash: 78691b806fe68aaa8d9e502d28e6f3967867f95b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600980"
---
# <span data-ttu-id="8dddd-102">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8dddd-102">Get-PSBreakpoint</span></span>

## <span data-ttu-id="8dddd-103">概要</span><span class="sxs-lookup"><span data-stu-id="8dddd-103">SYNOPSIS</span></span>
<span data-ttu-id="8dddd-104">現在のセッションで設定されたブレークポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-104">Gets the breakpoints that are set in the current session.</span></span>

## <span data-ttu-id="8dddd-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8dddd-105">SYNTAX</span></span>

### <span data-ttu-id="8dddd-106">スクリプト (既定値)</span><span class="sxs-lookup"><span data-stu-id="8dddd-106">Script (Default)</span></span>

```
Get-PSBreakpoint [-Script <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="8dddd-107">変数</span><span class="sxs-lookup"><span data-stu-id="8dddd-107">Variable</span></span>

```
Get-PSBreakpoint [-Script <String[]>] -Variable <String[]> [<CommonParameters>]
```

### <span data-ttu-id="8dddd-108">コマンド</span><span class="sxs-lookup"><span data-stu-id="8dddd-108">Command</span></span>

```
Get-PSBreakpoint [-Script <String[]>] -Command <String[]> [<CommonParameters>]
```

### <span data-ttu-id="8dddd-109">型</span><span class="sxs-lookup"><span data-stu-id="8dddd-109">Type</span></span>

```
Get-PSBreakpoint [-Script <String[]>] [-Type] <BreakpointType[]> [<CommonParameters>]
```

### <span data-ttu-id="8dddd-110">Id</span><span class="sxs-lookup"><span data-stu-id="8dddd-110">Id</span></span>

```
Get-PSBreakpoint [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="8dddd-111">Description</span><span class="sxs-lookup"><span data-stu-id="8dddd-111">DESCRIPTION</span></span>

<span data-ttu-id="8dddd-112">**Get PSBreakPoint ポイント** コマンドレットは、現在のセッションで設定されているブレークポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-112">The **Get-PSBreakPoint** cmdlet gets the breakpoints that are set in the current session.</span></span>
<span data-ttu-id="8dddd-113">コマンドレットのパラメーターを使用して、特定のブレークポイントを取得できます。</span><span class="sxs-lookup"><span data-stu-id="8dddd-113">You can use the cmdlet parameters to get particular breakpoints.</span></span>

<span data-ttu-id="8dddd-114">ブレークポイントとは、実行を一時的に停止して命令を調べることができるようにするための、コマンドまたはスクリプト内のポイントです。</span><span class="sxs-lookup"><span data-stu-id="8dddd-114">A breakpoint is a point in a command or script where execution stops temporarily so that you can examine the instructions.</span></span>
<span data-ttu-id="8dddd-115">**Get-PSBreakpoint ポイント** は、PowerShell スクリプトとコマンドのデバッグ用に設計されたいくつかのコマンドレットの1つです。</span><span class="sxs-lookup"><span data-stu-id="8dddd-115">**Get-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts and commands.</span></span> <span data-ttu-id="8dddd-116">PowerShell デバッガーの詳細については、「about_Debuggers」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8dddd-116">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="8dddd-117">例</span><span class="sxs-lookup"><span data-stu-id="8dddd-117">EXAMPLES</span></span>

### <span data-ttu-id="8dddd-118">例 1: すべてのスクリプトおよび関数のすべてのブレークポイントを取得する</span><span class="sxs-lookup"><span data-stu-id="8dddd-118">Example 1: Get all breakpoints for all scripts and functions</span></span>

```
PS C:\> Get-PSBreakpoint
```

<span data-ttu-id="8dddd-119">このコマンドは、現在のセッション内のすべてのスクリプトおよび関数に設定されているすべてのブレークポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-119">This command gets all breakpoints set on all scripts and functions in the current session.</span></span>

### <span data-ttu-id="8dddd-120">例 2: ID によってブレークポイントを取得する</span><span class="sxs-lookup"><span data-stu-id="8dddd-120">Example 2: Get breakpoints by ID</span></span>

```
PS C:\> Get-PSBreakpoint -Id 2
Function   :
IncrementAction     :
Enabled    :
TrueHitCount   : 0
Id         : 2
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="8dddd-121">このコマンドは、ブレークポイント ID が 2 のブレークポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-121">This command gets the breakpoint with breakpoint ID 2.</span></span>

### <span data-ttu-id="8dddd-122">例 3: パイプを使用して ID を Get-PSBreakpoint にする</span><span class="sxs-lookup"><span data-stu-id="8dddd-122">Example 3: Pipe an ID to Get-PSBreakpoint</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Command "Increment"
PS C:\> $B.Id | Get-PSBreakpoint
```

<span data-ttu-id="8dddd-123">これらのコマンドは、ブレークポイント ID をパイプを使ってブレークポイントを取得する方法を示し **ています**。</span><span class="sxs-lookup"><span data-stu-id="8dddd-123">These commands show how to get a breakpoint by piping a breakpoint ID to **Get-PSBreakpoint**.</span></span>

<span data-ttu-id="8dddd-124">最初のコマンドは、Set-PSBreakpoint コマンドレットを使用して、Sample.ps1 スクリプトの Increment 関数にブレークポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-124">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the Increment function in the Sample.ps1 script.</span></span> <span data-ttu-id="8dddd-125">ブレークポイントオブジェクトを $B 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-125">It saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="8dddd-126">2番目のコマンドは、ドット演算子 (.) を使用して、$B 変数内のブレークポイントオブジェクトの Id プロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-126">The second command uses the dot operator (.) to get the Id property of the breakpoint object in the $B variable.</span></span> <span data-ttu-id="8dddd-127">パイプライン演算子 (|) を使用して、ID を **Get PSBreakpoint ポイント** コマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-127">It uses a pipeline operator (|) to send the ID to the **Get-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="8dddd-128">結果として **、指定** した ID のブレークポイントが取得されます。</span><span class="sxs-lookup"><span data-stu-id="8dddd-128">As a result, **Get-PSBreakpoint** gets the breakpoint with the specified ID.</span></span>

### <span data-ttu-id="8dddd-129">例 4: 指定したスクリプトファイル内のブレークポイントを取得する</span><span class="sxs-lookup"><span data-stu-id="8dddd-129">Example 4: Get breakpoints in specified script files</span></span>

```
PS C:\> Get-PSBreakpoint -Script "Sample.ps1, SupportScript.ps1"
```

<span data-ttu-id="8dddd-130">このコマンドは、Sample.ps1 ファイルと SupportScript.ps1 ファイル内のすべてのブレークポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-130">This command gets all of the breakpoints in the Sample.ps1 and SupportScript.ps1 files.</span></span>

<span data-ttu-id="8dddd-131">このコマンドは、他のスクリプトまたはセッションの関数で設定されている可能性のある他のブレークポイントを取得しません。</span><span class="sxs-lookup"><span data-stu-id="8dddd-131">This command does not get other breakpoints that might be set in other scripts or on functions in the session.</span></span>

### <span data-ttu-id="8dddd-132">例 5: 指定したコマンドレットのブレークポイントを取得する</span><span class="sxs-lookup"><span data-stu-id="8dddd-132">Example 5: Get breakpoints in specified cmdlets</span></span>

```
PS C:\> Get-PSBreakpoint -Command "Read-Host, Write-Host" -Script "Sample.ps1"
```

<span data-ttu-id="8dddd-133">このコマンドは、Sample.ps1 ファイル内の Read-Host コマンドまたは Write-Host コマンドに設定されているすべてのコマンド ブレークポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-133">This command gets all Command breakpoints that are set on Read-Host or Write-Host commands in the Sample.ps1 file.</span></span>

### <span data-ttu-id="8dddd-134">例 6: 指定したファイル内のコマンドのブレークポイントを取得する</span><span class="sxs-lookup"><span data-stu-id="8dddd-134">Example 6: Get Command breakpoints in a specified file</span></span>

```
PS C:\> Get-PSBreakpoint -Type Command -Script "Sample.ps1"
```

<span data-ttu-id="8dddd-135">このコマンドは、Sample.ps1 ファイル内のすべてのコマンド ブレークポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-135">This command gets all Command breakpoints in the Sample.ps1 file.</span></span>

### <span data-ttu-id="8dddd-136">例 7: 変数によってブレークポイントを取得する</span><span class="sxs-lookup"><span data-stu-id="8dddd-136">Example 7: Get breakpoints by variable</span></span>

```
PS C:\> Get-PSBreakpoint -Variable "Index, Swap"
```

<span data-ttu-id="8dddd-137">このコマンドは、現在のセッションの $Index と $Swap 変数に設定されているブレークポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-137">This command gets breakpoints that are set on the $Index and $Swap variables in the current session.</span></span>

### <span data-ttu-id="8dddd-138">例 8: ファイル内のすべての行と変数のブレークポイントを取得する</span><span class="sxs-lookup"><span data-stu-id="8dddd-138">Example 8: Get all Line and Variable breakpoints in a file</span></span>

```
PS C:\> Get-PSBreakpoint -Type Line, Variable -Script "Sample.ps1"
```

<span data-ttu-id="8dddd-139">このコマンドは、Sample.ps1 スクリプト内のすべての行ブレークポイントと変数ブレークポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-139">This command gets all line and variable breakpoints in the Sample.ps1 script.</span></span>

## <span data-ttu-id="8dddd-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8dddd-140">PARAMETERS</span></span>

### <span data-ttu-id="8dddd-141">-Command</span><span class="sxs-lookup"><span data-stu-id="8dddd-141">-Command</span></span>

<span data-ttu-id="8dddd-142">指定したコマンド名に設定されているコマンドのブレークポイントの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-142">Specifies an array of command breakpoints that are set on the specified command names.</span></span>
<span data-ttu-id="8dddd-143">コマンドレットや関数の名前などのコマンド名を入力します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-143">Enter the command names, such as the name of a cmdlet or function.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Command
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8dddd-144">-Id</span><span class="sxs-lookup"><span data-stu-id="8dddd-144">-Id</span></span>

<span data-ttu-id="8dddd-145">このコマンドレットが取得するブレークポイント Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-145">Specifies the breakpoint IDs that this cmdlet gets.</span></span>
<span data-ttu-id="8dddd-146">ID をコンマ区切りリスト形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-146">Enter the IDs in a comma-separated list.</span></span>
<span data-ttu-id="8dddd-147">パイプを使用してブレークポイント Id を **取得** することもできます。</span><span class="sxs-lookup"><span data-stu-id="8dddd-147">You can also pipe breakpoint IDs to **Get-PSBreakpoint**.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8dddd-148">-スクリプト</span><span class="sxs-lookup"><span data-stu-id="8dddd-148">-Script</span></span>

<span data-ttu-id="8dddd-149">ブレークポイントを含むスクリプトの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-149">Specifies an array of scripts that contain the breakpoints.</span></span>
<span data-ttu-id="8dddd-150">1つまたは複数のスクリプトファイルのパス (省略可能) と名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-150">Enter the path (optional) and names of one or more script files.</span></span>
<span data-ttu-id="8dddd-151">パスを省略した場合、現在のディレクトリが既定の場所になります。</span><span class="sxs-lookup"><span data-stu-id="8dddd-151">If you omit the path, the default location is the current directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Script, Variable, Command, Type
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8dddd-152">-Type</span><span class="sxs-lookup"><span data-stu-id="8dddd-152">-Type</span></span>

<span data-ttu-id="8dddd-153">このコマンドレットが取得するブレークポイントの型の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-153">Specifies an array of breakpoint types that this cmdlet gets.</span></span>
<span data-ttu-id="8dddd-154">1 つまたは複数の型を入力します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-154">Enter one or more types.</span></span>
<span data-ttu-id="8dddd-155">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8dddd-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8dddd-156">行</span><span class="sxs-lookup"><span data-stu-id="8dddd-156">Line</span></span>
- <span data-ttu-id="8dddd-157">コマンド</span><span class="sxs-lookup"><span data-stu-id="8dddd-157">Command</span></span>
- <span data-ttu-id="8dddd-158">変数</span><span class="sxs-lookup"><span data-stu-id="8dddd-158">Variable</span></span>

<span data-ttu-id="8dddd-159">パイプを使用してブレークポイント **の** 種類を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="8dddd-159">You can also pipe breakpoint types to **Get-PSBreakPoint**.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.BreakpointType[]
Parameter Sets: Type
Aliases:
Accepted values: Line, Variable, Command

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8dddd-160">-Variable</span><span class="sxs-lookup"><span data-stu-id="8dddd-160">-Variable</span></span>

<span data-ttu-id="8dddd-161">指定した変数名に設定されている変数のブレークポイントの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-161">Specifies an array of variable breakpoints that are set on the specified variable names.</span></span>
<span data-ttu-id="8dddd-162">ドル記号を付けずに変数名を入力します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-162">Enter the variable names without dollar signs.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Variable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8dddd-163">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8dddd-163">CommonParameters</span></span>

<span data-ttu-id="8dddd-164">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8dddd-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8dddd-165">詳細については、「about_CommonParameters」 (https://go.microsoft.com/fwlink/?LinkID=113216) ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8dddd-165">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8dddd-166">入力</span><span class="sxs-lookup"><span data-stu-id="8dddd-166">INPUTS</span></span>

### <span data-ttu-id="8dddd-167">System.string、Microsoft. PowerShell. BreakpointType</span><span class="sxs-lookup"><span data-stu-id="8dddd-167">System.Int32, Microsoft.PowerShell.Commands.BreakpointType</span></span>

<span data-ttu-id="8dddd-168">パイプを使用して、ブレークポイントの Id とブレークポイントの種類を **取得** することができます。</span><span class="sxs-lookup"><span data-stu-id="8dddd-168">You can pipe breakpoint IDs and breakpoint types to **Get-PSBreakPoint**.</span></span>

## <span data-ttu-id="8dddd-169">出力</span><span class="sxs-lookup"><span data-stu-id="8dddd-169">OUTPUTS</span></span>

### <span data-ttu-id="8dddd-170">システム.... ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="8dddd-170">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="8dddd-171">**Get-PSBreakPoint ポイント** は、セッション内のブレークポイントを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="8dddd-171">**Get-PSBreakPoint** returns objects that represent the breakpoints in the session.</span></span>

## <span data-ttu-id="8dddd-172">注</span><span class="sxs-lookup"><span data-stu-id="8dddd-172">NOTES</span></span>

* <span data-ttu-id="8dddd-173">使用することができます、 **取得-PSBreakpoint ポイント** またはそのエイリアス "gbp" です。</span><span class="sxs-lookup"><span data-stu-id="8dddd-173">You can use **Get-PSBreakpoint** or its alias, "gbp".</span></span>

## <span data-ttu-id="8dddd-174">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8dddd-174">RELATED LINKS</span></span>

[<span data-ttu-id="8dddd-175">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8dddd-175">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="8dddd-176">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8dddd-176">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="8dddd-177">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="8dddd-177">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="8dddd-178">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8dddd-178">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="8dddd-179">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8dddd-179">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

