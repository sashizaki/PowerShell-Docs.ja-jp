---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-psbreakpoint?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSBreakpoint
ms.openlocfilehash: a56b9041c0ae70def7df619f2a4d265cb631fe7b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600784"
---
# <span data-ttu-id="318ac-102">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="318ac-102">Remove-PSBreakpoint</span></span>

## <span data-ttu-id="318ac-103">概要</span><span class="sxs-lookup"><span data-stu-id="318ac-103">SYNOPSIS</span></span>
<span data-ttu-id="318ac-104">現在のコンソールからブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="318ac-104">Deletes breakpoints from the current console.</span></span>

## <span data-ttu-id="318ac-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="318ac-105">SYNTAX</span></span>

### <span data-ttu-id="318ac-106">ブレークポイント (既定値)</span><span class="sxs-lookup"><span data-stu-id="318ac-106">Breakpoint (Default)</span></span>

```
Remove-PSBreakpoint [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="318ac-107">Id</span><span class="sxs-lookup"><span data-stu-id="318ac-107">Id</span></span>

```
Remove-PSBreakpoint [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="318ac-108">Description</span><span class="sxs-lookup"><span data-stu-id="318ac-108">DESCRIPTION</span></span>
<span data-ttu-id="318ac-109">Delete **PSBreakpoint** ポイントコマンドレットは、ブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="318ac-109">The **Remove-PSBreakpoint** cmdlet deletes a breakpoint.</span></span>
<span data-ttu-id="318ac-110">ブレークポイント　オブジェクトまたはブレークポイント ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="318ac-110">Enter a breakpoint object or a breakpoint ID.</span></span>

<span data-ttu-id="318ac-111">ブレークポイントを削除すると、ブレークポイント オブジェクトは使用できないか、機能不能となります。</span><span class="sxs-lookup"><span data-stu-id="318ac-111">When you remove a breakpoint, the breakpoint object is no longer available or functional.</span></span>
<span data-ttu-id="318ac-112">ブレークポイント オブジェクトを変数を保存した場合、参照は存続するが、ブレークポイントは機能しません。</span><span class="sxs-lookup"><span data-stu-id="318ac-112">If you have saved a breakpoint object in a variable, the reference still exists, but the breakpoint does not function.</span></span>

<span data-ttu-id="318ac-113">**削除-PSBreakpoint ポイントは、** PowerShell スクリプトのデバッグ用に設計されたいくつかのコマンドレットの1つです。</span><span class="sxs-lookup"><span data-stu-id="318ac-113">**Remove-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="318ac-114">PowerShell デバッガーの詳細については、「about_Debuggers」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="318ac-114">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="318ac-115">例</span><span class="sxs-lookup"><span data-stu-id="318ac-115">EXAMPLES</span></span>

### <span data-ttu-id="318ac-116">例 1: すべてのブレークポイントを削除する</span><span class="sxs-lookup"><span data-stu-id="318ac-116">Example 1: Remove all breakpoints</span></span>

```
PS C:\> Get-PSBreakpoint | Remove-PSBreakpoint
```

<span data-ttu-id="318ac-117">このコマンドは、現在のコンソール内のすべてのブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="318ac-117">This command deletes all of the breakpoints in the current console.</span></span>

### <span data-ttu-id="318ac-118">例 2: 指定したブレークポイントを削除する</span><span class="sxs-lookup"><span data-stu-id="318ac-118">Example 2: Remove a specified breakpoint</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "Name"
PS C:\> $B | Remove-PSBreakpoint
```

<span data-ttu-id="318ac-119">このコマンドは、ブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="318ac-119">This command deletes a breakpoint.</span></span>

<span data-ttu-id="318ac-120">最初のコマンドでは、Set-PSBreakpoint コマンドレットを使用して、Sample.ps1 スクリプトの Name 変数にブレークポイントを作成しています。</span><span class="sxs-lookup"><span data-stu-id="318ac-120">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the Name variable in the Sample.ps1 script.</span></span>
<span data-ttu-id="318ac-121">次に、ブレークポイントオブジェクトを $B 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="318ac-121">Then, it saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="318ac-122">2番目のコマンドは、 **削除 PSBreakpoint ポイント** コマンドレットを使用して、新しいブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="318ac-122">The second command uses the **Remove-PSBreakpoint** cmdlet to delete the new breakpoint.</span></span>
<span data-ttu-id="318ac-123">パイプライン演算子 (|) を使用して、$B 変数内のブレークポイントオブジェクトを、 **削除 PSBreakpoint ポイント** コマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="318ac-123">It uses a pipeline operator (|) to send the breakpoint object in the $B variable to the **Remove-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="318ac-124">このコマンドの結果、スクリプトを実行した場合、停止することなく完了するまで実行されます。</span><span class="sxs-lookup"><span data-stu-id="318ac-124">As a result of this command, if you run the script, it runs to completion without stopping.</span></span>
<span data-ttu-id="318ac-125">また、 **Get PSBreakpoint ポイント** コマンドレットは、このブレークポイントを返しません。</span><span class="sxs-lookup"><span data-stu-id="318ac-125">Also, the **Get-PSBreakpoint** cmdlet does not return this breakpoint.</span></span>

### <span data-ttu-id="318ac-126">例 3: ID によってブレークポイントを削除する</span><span class="sxs-lookup"><span data-stu-id="318ac-126">Example 3: Remove a breakpoint by ID</span></span>

```
PS C:\> Remove-PSBreakpoint -Id 2
```

<span data-ttu-id="318ac-127">このコマンドは、ブレークポイント ID が 2 のブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="318ac-127">This command deletes the breakpoint with breakpoint ID 2.</span></span>

### <span data-ttu-id="318ac-128">例 4: 関数を使用してすべてのブレークポイントを削除する</span><span class="sxs-lookup"><span data-stu-id="318ac-128">Example 4: Use a function to remove all breakpoints</span></span>

```
PS C:\> function del-psb { get-psbreakpoint | remove-psbreakpoint }
```

<span data-ttu-id="318ac-129">この単純な関数は、現在のコンソール内のすべてのブレークポイントを削除します。</span><span class="sxs-lookup"><span data-stu-id="318ac-129">This simple function deletes all of the breakpoints in the current console.</span></span>
<span data-ttu-id="318ac-130">Get-PSBreakpoint コマンドレットを使用してブレークポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="318ac-130">It uses the Get-PSBreakpoint cmdlet to get the breakpoints.</span></span>
<span data-ttu-id="318ac-131">次に、パイプライン演算子 (|) を使用して、ブレークポイントを **削除する、PSBreakpoint ポイント** コマンドレットにブレークポイントを送信します。</span><span class="sxs-lookup"><span data-stu-id="318ac-131">Then, it uses a pipeline operator (|) to send the breakpoints to the **Remove-PSBreakpoint** cmdlet, which deletes them.</span></span>

<span data-ttu-id="318ac-132">そのため、 `del-psb` 長いコマンドの代わりにを入力できます。</span><span class="sxs-lookup"><span data-stu-id="318ac-132">As a result, you can type `del-psb` instead of the longer command.</span></span>

<span data-ttu-id="318ac-133">関数を保存するには、PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="318ac-133">To save the function, add it to your PowerShell profile.</span></span>

## <span data-ttu-id="318ac-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="318ac-134">PARAMETERS</span></span>

### <span data-ttu-id="318ac-135">-ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="318ac-135">-Breakpoint</span></span>
<span data-ttu-id="318ac-136">削除するブレークポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="318ac-136">Specifies the breakpoints to delete.</span></span>
<span data-ttu-id="318ac-137">ブレークポイントオブジェクトを含む変数、または、ブレークポイントオブジェクトを取得するコマンド ( **Get PSBreakpoint** ポイントコマンドなど) を入力します。</span><span class="sxs-lookup"><span data-stu-id="318ac-137">Enter a variable that contains breakpoint objects or a command that gets breakpoint objects, such as a **Get-PSBreakpoint** command.</span></span>
<span data-ttu-id="318ac-138">パイプを使用して、ブレークポイントオブジェクトを **削除** することもできます。</span><span class="sxs-lookup"><span data-stu-id="318ac-138">You can also pipe breakpoint objects to **Remove-PSBreakpoint**.</span></span>

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

### <span data-ttu-id="318ac-139">-Id</span><span class="sxs-lookup"><span data-stu-id="318ac-139">-Id</span></span>
<span data-ttu-id="318ac-140">このコマンドレットがブレークポイントを削除するブレークポイント Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="318ac-140">Specifies breakpoint IDs for which this cmdlet deletes breakpoints.</span></span>

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

### <span data-ttu-id="318ac-141">-Confirm</span><span class="sxs-lookup"><span data-stu-id="318ac-141">-Confirm</span></span>
<span data-ttu-id="318ac-142">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="318ac-142">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="318ac-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="318ac-143">-WhatIf</span></span>
<span data-ttu-id="318ac-144">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="318ac-144">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="318ac-145">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="318ac-145">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="318ac-146">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="318ac-146">CommonParameters</span></span>
<span data-ttu-id="318ac-147">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="318ac-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="318ac-148">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="318ac-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="318ac-149">入力</span><span class="sxs-lookup"><span data-stu-id="318ac-149">INPUTS</span></span>

### <span data-ttu-id="318ac-150">システム.... ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="318ac-150">System.Management.Automation.Breakpoint</span></span>
<span data-ttu-id="318ac-151">パイプを使用してブレークポイントオブジェクトを **削除し、-PSBreakpoint ポイントを削除** できます。</span><span class="sxs-lookup"><span data-stu-id="318ac-151">You can pipe breakpoint objects to **Remove-PSBreakpoint**.</span></span>

## <span data-ttu-id="318ac-152">出力</span><span class="sxs-lookup"><span data-stu-id="318ac-152">OUTPUTS</span></span>

### <span data-ttu-id="318ac-153">なし</span><span class="sxs-lookup"><span data-stu-id="318ac-153">None</span></span>
<span data-ttu-id="318ac-154">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="318ac-154">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="318ac-155">注</span><span class="sxs-lookup"><span data-stu-id="318ac-155">NOTES</span></span>

## <span data-ttu-id="318ac-156">関連リンク</span><span class="sxs-lookup"><span data-stu-id="318ac-156">RELATED LINKS</span></span>

[<span data-ttu-id="318ac-157">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="318ac-157">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="318ac-158">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="318ac-158">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="318ac-159">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="318ac-159">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="318ac-160">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="318ac-160">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="318ac-161">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="318ac-161">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

