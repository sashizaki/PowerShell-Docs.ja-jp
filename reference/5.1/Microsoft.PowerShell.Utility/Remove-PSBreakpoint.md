---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-psbreakpoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSBreakpoint
ms.openlocfilehash: b12913cd10c2c505322c1f922a05ecc98987e830
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213755"
---
# <span data-ttu-id="6b1d0-103">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6b1d0-103">Remove-PSBreakpoint</span></span>

## <span data-ttu-id="6b1d0-104">概要</span><span class="sxs-lookup"><span data-stu-id="6b1d0-104">SYNOPSIS</span></span>
<span data-ttu-id="6b1d0-105">現在のコンソールからブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-105">Deletes breakpoints from the current console.</span></span>

## <span data-ttu-id="6b1d0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6b1d0-106">SYNTAX</span></span>

### <span data-ttu-id="6b1d0-107">ブレークポイント (既定値)</span><span class="sxs-lookup"><span data-stu-id="6b1d0-107">Breakpoint (Default)</span></span>

```
Remove-PSBreakpoint [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6b1d0-108">Id</span><span class="sxs-lookup"><span data-stu-id="6b1d0-108">Id</span></span>

```
Remove-PSBreakpoint [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6b1d0-109">Description</span><span class="sxs-lookup"><span data-stu-id="6b1d0-109">DESCRIPTION</span></span>
<span data-ttu-id="6b1d0-110">Delete **PSBreakpoint** ポイントコマンドレットは、ブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-110">The **Remove-PSBreakpoint** cmdlet deletes a breakpoint.</span></span>
<span data-ttu-id="6b1d0-111">ブレークポイント　オブジェクトまたはブレークポイント ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-111">Enter a breakpoint object or a breakpoint ID.</span></span>

<span data-ttu-id="6b1d0-112">ブレークポイントを削除すると、ブレークポイント オブジェクトは使用できないか、機能不能となります。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-112">When you remove a breakpoint, the breakpoint object is no longer available or functional.</span></span>
<span data-ttu-id="6b1d0-113">ブレークポイント オブジェクトを変数を保存した場合、参照は存続するが、ブレークポイントは機能しません。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-113">If you have saved a breakpoint object in a variable, the reference still exists, but the breakpoint does not function.</span></span>

<span data-ttu-id="6b1d0-114">**削除-PSBreakpoint ポイントは、** Windows PowerShell スクリプトのデバッグ用に設計されたいくつかのコマンドレットの1つです。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-114">**Remove-PSBreakpoint** is one of several cmdlets designed for debugging Windows PowerShell scripts.</span></span>
<span data-ttu-id="6b1d0-115">Windows PowerShell のデバッガーの詳細については、「about_Debuggers」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-115">For more information about the Windows PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="6b1d0-116">例</span><span class="sxs-lookup"><span data-stu-id="6b1d0-116">EXAMPLES</span></span>

### <span data-ttu-id="6b1d0-117">例 1: すべてのブレークポイントを削除する</span><span class="sxs-lookup"><span data-stu-id="6b1d0-117">Example 1: Remove all breakpoints</span></span>

```
PS C:\> Get-PSBreakpoint | Remove-PSBreakpoint
```

<span data-ttu-id="6b1d0-118">このコマンドは、現在のコンソール内のすべてのブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-118">This command deletes all of the breakpoints in the current console.</span></span>

### <span data-ttu-id="6b1d0-119">例 2: 指定したブレークポイントを削除する</span><span class="sxs-lookup"><span data-stu-id="6b1d0-119">Example 2: Remove a specified breakpoint</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "Name"
PS C:\> $B | Remove-PSBreakpoint
```

<span data-ttu-id="6b1d0-120">このコマンドは、ブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-120">This command deletes a breakpoint.</span></span>

<span data-ttu-id="6b1d0-121">最初のコマンドでは、Set-PSBreakpoint コマンドレットを使用して、Sample.ps1 スクリプトの Name 変数にブレークポイントを作成しています。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-121">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the Name variable in the Sample.ps1 script.</span></span>
<span data-ttu-id="6b1d0-122">次に、ブレークポイントオブジェクトを $B 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-122">Then, it saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="6b1d0-123">2番目のコマンドは、 **削除 PSBreakpoint ポイント** コマンドレットを使用して、新しいブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-123">The second command uses the **Remove-PSBreakpoint** cmdlet to delete the new breakpoint.</span></span>
<span data-ttu-id="6b1d0-124">パイプライン演算子 (|) を使用して、$B 変数内のブレークポイントオブジェクトを、 **削除 PSBreakpoint ポイント** コマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-124">It uses a pipeline operator (|) to send the breakpoint object in the $B variable to the **Remove-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="6b1d0-125">このコマンドの結果、スクリプトを実行した場合、停止することなく完了するまで実行されます。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-125">As a result of this command, if you run the script, it runs to completion without stopping.</span></span>
<span data-ttu-id="6b1d0-126">また、 **Get PSBreakpoint ポイント** コマンドレットは、このブレークポイントを返しません。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-126">Also, the **Get-PSBreakpoint** cmdlet does not return this breakpoint.</span></span>

### <span data-ttu-id="6b1d0-127">例 3: ID によってブレークポイントを削除する</span><span class="sxs-lookup"><span data-stu-id="6b1d0-127">Example 3: Remove a breakpoint by ID</span></span>

```
PS C:\> Remove-PSBreakpoint -Id 2
```

<span data-ttu-id="6b1d0-128">このコマンドは、ブレークポイント ID が 2 のブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-128">This command deletes the breakpoint with breakpoint ID 2.</span></span>

### <span data-ttu-id="6b1d0-129">例 4: 関数を使用してすべてのブレークポイントを削除する</span><span class="sxs-lookup"><span data-stu-id="6b1d0-129">Example 4: Use a function to remove all breakpoints</span></span>

```
PS C:\> function del-psb { get-psbreakpoint | remove-psbreakpoint }
```

<span data-ttu-id="6b1d0-130">この単純な関数は、現在のコンソール内のすべてのブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-130">This simple function deletes all of the breakpoints in the current console.</span></span>
<span data-ttu-id="6b1d0-131">Get-PSBreakpoint コマンドレットを使用してブレークポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-131">It uses the Get-PSBreakpoint cmdlet to get the breakpoints.</span></span>
<span data-ttu-id="6b1d0-132">次に、パイプライン演算子 (|) を使用して、ブレークポイントを **削除する、PSBreakpoint ポイント** コマンドレットにブレークポイントを送信します。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-132">Then, it uses a pipeline operator (|) to send the breakpoints to the **Remove-PSBreakpoint** cmdlet, which deletes them.</span></span>

<span data-ttu-id="6b1d0-133">そのため、 `del-psb` 長いコマンドの代わりにを入力できます。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-133">As a result, you can type `del-psb` instead of the longer command.</span></span>

<span data-ttu-id="6b1d0-134">関数を保存するには、それを indows PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-134">To save the function, add it to your Windows PowerShell profile.</span></span>

## <span data-ttu-id="6b1d0-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6b1d0-135">PARAMETERS</span></span>

### <span data-ttu-id="6b1d0-136">-ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="6b1d0-136">-Breakpoint</span></span>
<span data-ttu-id="6b1d0-137">削除するブレークポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-137">Specifies the breakpoints to delete.</span></span>
<span data-ttu-id="6b1d0-138">ブレークポイントオブジェクトを含む変数、または、ブレークポイントオブジェクトを取得するコマンド ( **Get PSBreakpoint** ポイントコマンドなど) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-138">Enter a variable that contains breakpoint objects or a command that gets breakpoint objects, such as a **Get-PSBreakpoint** command.</span></span>
<span data-ttu-id="6b1d0-139">パイプを使用して、ブレークポイントオブジェクトを **削除** することもできます。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-139">You can also pipe breakpoint objects to **Remove-PSBreakpoint** .</span></span>

```yaml
Type: System.Management.Automation.Breakpoint[]
Parameter Sets: Breakpoint
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6b1d0-140">-Id</span><span class="sxs-lookup"><span data-stu-id="6b1d0-140">-Id</span></span>
<span data-ttu-id="6b1d0-141">このコマンドレットがブレークポイントを削除するブレークポイント Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-141">Specifies breakpoint IDs for which this cmdlet deletes breakpoints.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6b1d0-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6b1d0-142">-Confirm</span></span>
<span data-ttu-id="6b1d0-143">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-143">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6b1d0-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6b1d0-144">-WhatIf</span></span>
<span data-ttu-id="6b1d0-145">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-145">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="6b1d0-146">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-146">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6b1d0-147">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b1d0-147">CommonParameters</span></span>
<span data-ttu-id="6b1d0-148">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6b1d0-149">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6b1d0-150">入力</span><span class="sxs-lookup"><span data-stu-id="6b1d0-150">INPUTS</span></span>

### <span data-ttu-id="6b1d0-151">システム.... ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="6b1d0-151">System.Management.Automation.Breakpoint</span></span>
<span data-ttu-id="6b1d0-152">パイプを使用してブレークポイントオブジェクトを **削除し、-PSBreakpoint ポイントを削除** できます。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-152">You can pipe breakpoint objects to **Remove-PSBreakpoint** .</span></span>

## <span data-ttu-id="6b1d0-153">出力</span><span class="sxs-lookup"><span data-stu-id="6b1d0-153">OUTPUTS</span></span>

### <span data-ttu-id="6b1d0-154">なし</span><span class="sxs-lookup"><span data-stu-id="6b1d0-154">None</span></span>
<span data-ttu-id="6b1d0-155">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="6b1d0-155">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="6b1d0-156">注</span><span class="sxs-lookup"><span data-stu-id="6b1d0-156">NOTES</span></span>

## <span data-ttu-id="6b1d0-157">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6b1d0-157">RELATED LINKS</span></span>

[<span data-ttu-id="6b1d0-158">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6b1d0-158">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="6b1d0-159">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6b1d0-159">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="6b1d0-160">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6b1d0-160">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="6b1d0-161">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="6b1d0-161">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="6b1d0-162">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6b1d0-162">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)