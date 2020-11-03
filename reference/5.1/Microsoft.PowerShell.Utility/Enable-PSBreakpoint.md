---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-psbreakpoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSBreakpoint
ms.openlocfilehash: 9530e3bc15360245de334a6f45ff35883181a41e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214080"
---
# <span data-ttu-id="e4cf8-103">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e4cf8-103">Enable-PSBreakpoint</span></span>

## <span data-ttu-id="e4cf8-104">概要</span><span class="sxs-lookup"><span data-stu-id="e4cf8-104">SYNOPSIS</span></span>
<span data-ttu-id="e4cf8-105">現在のコンソール内のブレークポイントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-105">Enables the breakpoints in the current console.</span></span>

## <span data-ttu-id="e4cf8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e4cf8-106">SYNTAX</span></span>

### <span data-ttu-id="e4cf8-107">Id (既定値)</span><span class="sxs-lookup"><span data-stu-id="e4cf8-107">Id (Default)</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e4cf8-108">ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="e4cf8-108">Breakpoint</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="e4cf8-109">Description</span><span class="sxs-lookup"><span data-stu-id="e4cf8-109">DESCRIPTION</span></span>

<span data-ttu-id="e4cf8-110">コマンドレットでは、 `Enable-PSBreakpoint` 無効になっているブレークポイントを再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-110">The `Enable-PSBreakpoint` cmdlet re-enables disabled breakpoints.</span></span> <span data-ttu-id="e4cf8-111">これを使用すると、ブレークポイントオブジェクトまたは Id を指定することによって、すべてのブレークポイントまたは特定のブレークポイントを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-111">You can use it to enable all breakpoints, or specific breakpoints by providing breakpoint objects or IDs.</span></span>

<span data-ttu-id="e4cf8-112">ブレークポイントは、スクリプトの状態を確認できるように、実行が一時的に停止するスクリプト内のポイントです。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-112">A breakpoint is a point in a script where execution stops temporarily so that you can examine the state of the script.</span></span> <span data-ttu-id="e4cf8-113">新しく作成されたブレークポイントは自動的に有効になりますが、を使用して無効にすることができ `Disable-PSBreakpoint` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-113">Newly created breakpoints are automatically enabled, but can be disabled using `Disable-PSBreakpoint`.</span></span>

<span data-ttu-id="e4cf8-114">技術的には、このコマンドレットは、ブレークポイントオブジェクトの **Enabled** プロパティの値を **True** に変更します。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-114">Technically, this cmdlet changes the value of the **Enabled** property of a breakpoint object to **True** .</span></span>

<span data-ttu-id="e4cf8-115">`Enable-PSBreakpoint` は、PowerShell スクリプトのデバッグ用に設計されたいくつかのコマンドレットの1つです。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-115">`Enable-PSBreakpoint` is one of several cmdlets designed for debugging PowerShell scripts.</span></span> <span data-ttu-id="e4cf8-116">PowerShell デバッガーの詳細については、「 [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-116">For more information about the PowerShell debugger, see [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span></span>

## <span data-ttu-id="e4cf8-117">例</span><span class="sxs-lookup"><span data-stu-id="e4cf8-117">EXAMPLES</span></span>

### <span data-ttu-id="e4cf8-118">例 1: すべてのブレークポイントを有効にする</span><span class="sxs-lookup"><span data-stu-id="e4cf8-118">Example 1: Enable all breakpoints</span></span>

<span data-ttu-id="e4cf8-119">この例では、現在のセッションのすべてのブレークポイントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-119">This example enables all breakpoints in the current session.</span></span>

```powershell
Get-PSBreakpoint | Enable-PSBreakpoint
```

<span data-ttu-id="e4cf8-120">エイリアスを使用して、この例をとして省略でき `gbp | ebp` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-120">Using aliases, this example can be abbreviated as `gbp | ebp`.</span></span>

### <span data-ttu-id="e4cf8-121">例 2: ID によってブレークポイントを有効にする</span><span class="sxs-lookup"><span data-stu-id="e4cf8-121">Example 2: Enable breakpoints by ID</span></span>

<span data-ttu-id="e4cf8-122">この例では、ブレークポイント Id を使用して複数のブレークポイントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-122">This example enables multiple breakpoints using their breakpoint IDs.</span></span>

```powershell
Enable-PSBreakpoint -Id 0, 1, 5
```

### <span data-ttu-id="e4cf8-123">例 3: 無効になっているブレークポイントを有効にする</span><span class="sxs-lookup"><span data-stu-id="e4cf8-123">Example 3: Enable a disabled breakpoint</span></span>

<span data-ttu-id="e4cf8-124">この例では、無効になっているブレークポイントを再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-124">This example re-enables a breakpoint that has been disabled.</span></span>

```powershell
$B = Set-PSBreakpoint -Script "sample.ps1" -Variable Name -PassThru
$B | Enable-PSBreakpoint -PassThru
```

```Output
AccessMode : Write
Variable   : Name
Action     :
Enabled    : False
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1

AccessMode : Write
Variable   : Name
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="e4cf8-125">`Set-PSBreakpoint` スクリプト内の **名前** 変数にブレークポイントを作成し、 `Sample.ps1` 変数内のブレークポイントオブジェクトを保存し `$B` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-125">`Set-PSBreakpoint` creates a breakpoint on the **Name** variable in the `Sample.ps1` script saving the breakpoint object in the `$B` variable.</span></span> <span data-ttu-id="e4cf8-126">**PassThru** パラメーターは、ブレークポイントの **Enabled** プロパティの値が **False** であることを示します。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-126">The **PassThru** parameter displays the value of the **Enabled** property of the breakpoint is **False** .</span></span>

<span data-ttu-id="e4cf8-127">`Enable-PSBreakpoint` ブレークポイントを再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-127">`Enable-PSBreakpoint` re-enables the breakpoint.</span></span> <span data-ttu-id="e4cf8-128">ここでも、 **PassThru** パラメーターを使用すると、 **Enabled** プロパティの値が **True** であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-128">Again, using the **PassThru** parameter we see that the value of the **Enabled** property is **True** .</span></span>

### <span data-ttu-id="e4cf8-129">例 4: 変数を使用してブレークポイントを有効にする</span><span class="sxs-lookup"><span data-stu-id="e4cf8-129">Example 4: Enable breakpoints using a variable</span></span>

<span data-ttu-id="e4cf8-130">この例では、ブレークポイントオブジェクトを使用して、一連のブレークポイントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-130">This example enables a set of breakpoints using the breakpoint objects.</span></span>

```powershell
$B = Get-PSBreakpoint -Id 3, 5
Enable-PSBreakpoint -Breakpoint $B
```

<span data-ttu-id="e4cf8-131">`Get-PSBreakpoint` ブレークポイントを取得し、変数に保存し `$B` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-131">`Get-PSBreakpoint` gets the breakpoints and saves them in the `$B` variable.</span></span> <span data-ttu-id="e4cf8-132">**ブレーク** ポイントパラメーターを使用すると、 `Enable-PSBreakpoint` ブレークポイントを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-132">Using the **Breakpoint** parameter, `Enable-PSBreakpoint` enables the breakpoints.</span></span>

<span data-ttu-id="e4cf8-133">この例は、を実行することと同じです `Enable-PSBreakpoint -Id 3, 5` 。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-133">This example is equivalent to running `Enable-PSBreakpoint -Id 3, 5`.</span></span>

## <span data-ttu-id="e4cf8-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e4cf8-134">PARAMETERS</span></span>

### <span data-ttu-id="e4cf8-135">-ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="e4cf8-135">-Breakpoint</span></span>

<span data-ttu-id="e4cf8-136">有効にするブレークポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-136">Specifies the breakpoints to enable.</span></span> <span data-ttu-id="e4cf8-137">ブレークポイントを含む変数、またはブレークポイントオブジェクトを取得するコマンド (など) を指定し `Get-PSBreakpoint` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-137">Provide a variable containing breakpoints or a command that gets breakpoint objects, such as `Get-PSBreakpoint`.</span></span> <span data-ttu-id="e4cf8-138">パイプを使用して、ブレークポイントオブジェクトをにパイプすることもでき `Enable-PSBreakpoint` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-138">You can also pipe breakpoint objects to `Enable-PSBreakpoint`.</span></span>

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

### <span data-ttu-id="e4cf8-139">-Id</span><span class="sxs-lookup"><span data-stu-id="e4cf8-139">-Id</span></span>

<span data-ttu-id="e4cf8-140">有効にするブレークポイントの **Id** 番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-140">Specifies the **Id** numbers of the breakpoints to enable.</span></span> <span data-ttu-id="e4cf8-141">既定値はすべてのブレークポイントです。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-141">The default value is all breakpoints.</span></span>
<span data-ttu-id="e4cf8-142">**Id** を数値または変数で指定します。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-142">Provide the **Id** by number or in a variable.</span></span> <span data-ttu-id="e4cf8-143">**Id** 番号をにパイプすることはできません `Enable-PSBreakpoint` 。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-143">You can't pipe **Id** numbers to `Enable-PSBreakpoint`.</span></span> <span data-ttu-id="e4cf8-144">ブレークポイントの **Id** を確認するには、 `Get-PSBreakpoint` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-144">To find the **Id** of a breakpoint, use the `Get-PSBreakpoint` cmdlet.</span></span>

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

### <span data-ttu-id="e4cf8-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e4cf8-145">-PassThru</span></span>

<span data-ttu-id="e4cf8-146">有効になっているブレークポイントを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-146">Returns an object representing the breakpoint being enabled.</span></span> <span data-ttu-id="e4cf8-147">既定では、このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-147">By default, this cmdlet doesn't generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4cf8-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e4cf8-148">-Confirm</span></span>

<span data-ttu-id="e4cf8-149">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e4cf8-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e4cf8-150">-WhatIf</span></span>

<span data-ttu-id="e4cf8-151">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-151">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e4cf8-152">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-152">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="e4cf8-153">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e4cf8-153">CommonParameters</span></span>

<span data-ttu-id="e4cf8-154">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e4cf8-155">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e4cf8-156">入力</span><span class="sxs-lookup"><span data-stu-id="e4cf8-156">INPUTS</span></span>

### <span data-ttu-id="e4cf8-157">システム.... ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="e4cf8-157">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="e4cf8-158">パイプを使用して、ブレークポイントオブジェクトをに渡し `Enable-PSBreakpoint` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-158">You can pipe a breakpoint object to `Enable-PSBreakpoint`.</span></span>

## <span data-ttu-id="e4cf8-159">出力</span><span class="sxs-lookup"><span data-stu-id="e4cf8-159">OUTPUTS</span></span>

### <span data-ttu-id="e4cf8-160">None または system.string。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-160">None or System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="e4cf8-161">**PassThru** パラメーターを使用すると、 `Enable-PSBreakpoint` 有効にされたブレークポイントを表すブレークポイントオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-161">When you use the **PassThru** parameter, `Enable-PSBreakpoint` returns a breakpoint object that represents that breakpoint that was enabled.</span></span> <span data-ttu-id="e4cf8-162">それ以外の場合、このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-162">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="e4cf8-163">注</span><span class="sxs-lookup"><span data-stu-id="e4cf8-163">NOTES</span></span>

- <span data-ttu-id="e4cf8-164">既に有効になっている `Enable-PSBreakpoint` ブレークポイントを有効にしようとすると、コマンドレットはエラーを生成しません。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-164">The `Enable-PSBreakpoint` cmdlet doesn't generate an error if you try to enable a breakpoint that is already enabled.</span></span> <span data-ttu-id="e4cf8-165">そのため、一部のブレークポイントのみが無効な場合でも、エラーを生成せずにすべてのブレークポイントを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-165">As such, you can enable all breakpoints without error, even when only a few are disabled.</span></span>

- <span data-ttu-id="e4cf8-166">ブレークポイントは、コマンドレットを使用して作成するときに有効になり `Set-PSBreakpoint` ます。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-166">Breakpoints are enabled when you create them by using the `Set-PSBreakpoint` cmdlet.</span></span> <span data-ttu-id="e4cf8-167">新しく作成されたブレークポイントを有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e4cf8-167">You don't need to enable newly created breakpoints.</span></span>

## <span data-ttu-id="e4cf8-168">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e4cf8-168">RELATED LINKS</span></span>

[<span data-ttu-id="e4cf8-169">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e4cf8-169">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="e4cf8-170">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e4cf8-170">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="e4cf8-171">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="e4cf8-171">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="e4cf8-172">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e4cf8-172">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="e4cf8-173">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e4cf8-173">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
