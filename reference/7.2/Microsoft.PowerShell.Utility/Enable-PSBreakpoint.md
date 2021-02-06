---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-psbreakpoint?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSBreakpoint
ms.openlocfilehash: 28cda7a2fa4435092b647e43a250222a852114b0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602195"
---
# <span data-ttu-id="2eeab-102">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2eeab-102">Enable-PSBreakpoint</span></span>

## <span data-ttu-id="2eeab-103">概要</span><span class="sxs-lookup"><span data-stu-id="2eeab-103">SYNOPSIS</span></span>
<span data-ttu-id="2eeab-104">現在のコンソール内のブレークポイントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2eeab-104">Enables the breakpoints in the current console.</span></span>

## <span data-ttu-id="2eeab-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2eeab-105">SYNTAX</span></span>

### <span data-ttu-id="2eeab-106">Id (既定値)</span><span class="sxs-lookup"><span data-stu-id="2eeab-106">Id (Default)</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2eeab-107">ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="2eeab-107">Breakpoint</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="2eeab-108">Description</span><span class="sxs-lookup"><span data-stu-id="2eeab-108">DESCRIPTION</span></span>

<span data-ttu-id="2eeab-109">コマンドレットでは、 `Enable-PSBreakpoint` 無効になっているブレークポイントを再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="2eeab-109">The `Enable-PSBreakpoint` cmdlet re-enables disabled breakpoints.</span></span> <span data-ttu-id="2eeab-110">これを使用すると、ブレークポイントオブジェクトまたは Id を指定することによって、すべてのブレークポイントまたは特定のブレークポイントを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="2eeab-110">You can use it to enable all breakpoints, or specific breakpoints by providing breakpoint objects or IDs.</span></span>

<span data-ttu-id="2eeab-111">ブレークポイントは、スクリプトの状態を確認できるように、実行が一時的に停止するスクリプト内のポイントです。</span><span class="sxs-lookup"><span data-stu-id="2eeab-111">A breakpoint is a point in a script where execution stops temporarily so that you can examine the state of the script.</span></span> <span data-ttu-id="2eeab-112">新しく作成されたブレークポイントは自動的に有効になりますが、を使用して無効にすることができ `Disable-PSBreakpoint` ます。</span><span class="sxs-lookup"><span data-stu-id="2eeab-112">Newly created breakpoints are automatically enabled, but can be disabled using `Disable-PSBreakpoint`.</span></span>

<span data-ttu-id="2eeab-113">技術的には、このコマンドレットは、ブレークポイントオブジェクトの **Enabled** プロパティの値を **True** に変更します。</span><span class="sxs-lookup"><span data-stu-id="2eeab-113">Technically, this cmdlet changes the value of the **Enabled** property of a breakpoint object to **True**.</span></span>

<span data-ttu-id="2eeab-114">`Enable-PSBreakpoint` は、PowerShell スクリプトのデバッグ用に設計されたいくつかのコマンドレットの1つです。</span><span class="sxs-lookup"><span data-stu-id="2eeab-114">`Enable-PSBreakpoint` is one of several cmdlets designed for debugging PowerShell scripts.</span></span> <span data-ttu-id="2eeab-115">PowerShell デバッガーの詳細については、「 [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2eeab-115">For more information about the PowerShell debugger, see [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span></span>

## <span data-ttu-id="2eeab-116">例</span><span class="sxs-lookup"><span data-stu-id="2eeab-116">EXAMPLES</span></span>

### <span data-ttu-id="2eeab-117">例 1: すべてのブレークポイントを有効にする</span><span class="sxs-lookup"><span data-stu-id="2eeab-117">Example 1: Enable all breakpoints</span></span>

<span data-ttu-id="2eeab-118">この例では、現在のセッションのすべてのブレークポイントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2eeab-118">This example enables all breakpoints in the current session.</span></span>

```powershell
Get-PSBreakpoint | Enable-PSBreakpoint
```

<span data-ttu-id="2eeab-119">エイリアスを使用して、この例をとして省略でき `gbp | ebp` ます。</span><span class="sxs-lookup"><span data-stu-id="2eeab-119">Using aliases, this example can be abbreviated as `gbp | ebp`.</span></span>

### <span data-ttu-id="2eeab-120">例 2: ID によってブレークポイントを有効にする</span><span class="sxs-lookup"><span data-stu-id="2eeab-120">Example 2: Enable breakpoints by ID</span></span>

<span data-ttu-id="2eeab-121">この例では、ブレークポイント Id を使用して複数のブレークポイントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2eeab-121">This example enables multiple breakpoints using their breakpoint IDs.</span></span>

```powershell
Enable-PSBreakpoint -Id 0, 1, 5
```

### <span data-ttu-id="2eeab-122">例 3: 無効になっているブレークポイントを有効にする</span><span class="sxs-lookup"><span data-stu-id="2eeab-122">Example 3: Enable a disabled breakpoint</span></span>

<span data-ttu-id="2eeab-123">この例では、無効になっているブレークポイントを再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="2eeab-123">This example re-enables a breakpoint that has been disabled.</span></span>

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

<span data-ttu-id="2eeab-124">`Set-PSBreakpoint` スクリプト内の **名前** 変数にブレークポイントを作成し、 `Sample.ps1` 変数内のブレークポイントオブジェクトを保存し `$B` ます。</span><span class="sxs-lookup"><span data-stu-id="2eeab-124">`Set-PSBreakpoint` creates a breakpoint on the **Name** variable in the `Sample.ps1` script saving the breakpoint object in the `$B` variable.</span></span> <span data-ttu-id="2eeab-125">**PassThru** パラメーターは、ブレークポイントの **Enabled** プロパティの値が **False** であることを示します。</span><span class="sxs-lookup"><span data-stu-id="2eeab-125">The **PassThru** parameter displays the value of the **Enabled** property of the breakpoint is **False**.</span></span>

<span data-ttu-id="2eeab-126">`Enable-PSBreakpoint` ブレークポイントを再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="2eeab-126">`Enable-PSBreakpoint` re-enables the breakpoint.</span></span> <span data-ttu-id="2eeab-127">ここでも、 **PassThru** パラメーターを使用すると、 **Enabled** プロパティの値が **True** であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="2eeab-127">Again, using the **PassThru** parameter we see that the value of the **Enabled** property is **True**.</span></span>

### <span data-ttu-id="2eeab-128">例 4: 変数を使用してブレークポイントを有効にする</span><span class="sxs-lookup"><span data-stu-id="2eeab-128">Example 4: Enable breakpoints using a variable</span></span>

<span data-ttu-id="2eeab-129">この例では、ブレークポイントオブジェクトを使用して、一連のブレークポイントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2eeab-129">This example enables a set of breakpoints using the breakpoint objects.</span></span>

```powershell
$B = Get-PSBreakpoint -Id 3, 5
Enable-PSBreakpoint -Breakpoint $B
```

<span data-ttu-id="2eeab-130">`Get-PSBreakpoint` ブレークポイントを取得し、変数に保存し `$B` ます。</span><span class="sxs-lookup"><span data-stu-id="2eeab-130">`Get-PSBreakpoint` gets the breakpoints and saves them in the `$B` variable.</span></span> <span data-ttu-id="2eeab-131">**ブレーク** ポイントパラメーターを使用すると、 `Enable-PSBreakpoint` ブレークポイントを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="2eeab-131">Using the **Breakpoint** parameter, `Enable-PSBreakpoint` enables the breakpoints.</span></span>

<span data-ttu-id="2eeab-132">この例は、を実行することと同じです `Enable-PSBreakpoint -Id 3, 5` 。</span><span class="sxs-lookup"><span data-stu-id="2eeab-132">This example is equivalent to running `Enable-PSBreakpoint -Id 3, 5`.</span></span>

## <span data-ttu-id="2eeab-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2eeab-133">PARAMETERS</span></span>

### <span data-ttu-id="2eeab-134">-ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="2eeab-134">-Breakpoint</span></span>

<span data-ttu-id="2eeab-135">有効にするブレークポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="2eeab-135">Specifies the breakpoints to enable.</span></span> <span data-ttu-id="2eeab-136">ブレークポイントを含む変数、またはブレークポイントオブジェクトを取得するコマンド (など) を指定し `Get-PSBreakpoint` ます。</span><span class="sxs-lookup"><span data-stu-id="2eeab-136">Provide a variable containing breakpoints or a command that gets breakpoint objects, such as `Get-PSBreakpoint`.</span></span> <span data-ttu-id="2eeab-137">パイプを使用して、ブレークポイントオブジェクトをにパイプすることもでき `Enable-PSBreakpoint` ます。</span><span class="sxs-lookup"><span data-stu-id="2eeab-137">You can also pipe breakpoint objects to `Enable-PSBreakpoint`.</span></span>

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

### <span data-ttu-id="2eeab-138">-Id</span><span class="sxs-lookup"><span data-stu-id="2eeab-138">-Id</span></span>

<span data-ttu-id="2eeab-139">有効にするブレークポイントの **Id** 番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="2eeab-139">Specifies the **Id** numbers of the breakpoints to enable.</span></span> <span data-ttu-id="2eeab-140">既定値はすべてのブレークポイントです。</span><span class="sxs-lookup"><span data-stu-id="2eeab-140">The default value is all breakpoints.</span></span>
<span data-ttu-id="2eeab-141">**Id** を数値または変数で指定します。</span><span class="sxs-lookup"><span data-stu-id="2eeab-141">Provide the **Id** by number or in a variable.</span></span> <span data-ttu-id="2eeab-142">**Id** 番号をにパイプすることはできません `Enable-PSBreakpoint` 。</span><span class="sxs-lookup"><span data-stu-id="2eeab-142">You can't pipe **Id** numbers to `Enable-PSBreakpoint`.</span></span> <span data-ttu-id="2eeab-143">ブレークポイントの **Id** を確認するには、 `Get-PSBreakpoint` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2eeab-143">To find the **Id** of a breakpoint, use the `Get-PSBreakpoint` cmdlet.</span></span>

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

### <span data-ttu-id="2eeab-144">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2eeab-144">-PassThru</span></span>

<span data-ttu-id="2eeab-145">有効になっているブレークポイントを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2eeab-145">Returns an object representing the breakpoint being enabled.</span></span> <span data-ttu-id="2eeab-146">既定では、このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="2eeab-146">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="2eeab-147">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2eeab-147">-Confirm</span></span>

<span data-ttu-id="2eeab-148">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2eeab-148">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2eeab-149">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2eeab-149">-WhatIf</span></span>

<span data-ttu-id="2eeab-150">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="2eeab-150">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2eeab-151">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2eeab-151">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="2eeab-152">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2eeab-152">CommonParameters</span></span>

<span data-ttu-id="2eeab-153">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2eeab-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2eeab-154">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2eeab-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2eeab-155">入力</span><span class="sxs-lookup"><span data-stu-id="2eeab-155">INPUTS</span></span>

### <span data-ttu-id="2eeab-156">システム.... ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="2eeab-156">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="2eeab-157">パイプを使用して、ブレークポイントオブジェクトをに渡し `Enable-PSBreakpoint` ます。</span><span class="sxs-lookup"><span data-stu-id="2eeab-157">You can pipe a breakpoint object to `Enable-PSBreakpoint`.</span></span>

## <span data-ttu-id="2eeab-158">出力</span><span class="sxs-lookup"><span data-stu-id="2eeab-158">OUTPUTS</span></span>

### <span data-ttu-id="2eeab-159">None または system.string。</span><span class="sxs-lookup"><span data-stu-id="2eeab-159">None or System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="2eeab-160">**PassThru** パラメーターを使用すると、 `Enable-PSBreakpoint` 有効にされたブレークポイントを表すブレークポイントオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="2eeab-160">When you use the **PassThru** parameter, `Enable-PSBreakpoint` returns a breakpoint object that represents that breakpoint that was enabled.</span></span> <span data-ttu-id="2eeab-161">それ以外の場合、このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="2eeab-161">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="2eeab-162">注</span><span class="sxs-lookup"><span data-stu-id="2eeab-162">NOTES</span></span>

- <span data-ttu-id="2eeab-163">既に有効になっている `Enable-PSBreakpoint` ブレークポイントを有効にしようとすると、コマンドレットはエラーを生成しません。</span><span class="sxs-lookup"><span data-stu-id="2eeab-163">The `Enable-PSBreakpoint` cmdlet doesn't generate an error if you try to enable a breakpoint that is already enabled.</span></span> <span data-ttu-id="2eeab-164">そのため、一部のブレークポイントのみが無効な場合でも、エラーを生成せずにすべてのブレークポイントを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="2eeab-164">As such, you can enable all breakpoints without error, even when only a few are disabled.</span></span>

- <span data-ttu-id="2eeab-165">ブレークポイントは、コマンドレットを使用して作成するときに有効になり `Set-PSBreakpoint` ます。</span><span class="sxs-lookup"><span data-stu-id="2eeab-165">Breakpoints are enabled when you create them by using the `Set-PSBreakpoint` cmdlet.</span></span> <span data-ttu-id="2eeab-166">新しく作成されたブレークポイントを有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2eeab-166">You don't need to enable newly created breakpoints.</span></span>

## <span data-ttu-id="2eeab-167">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2eeab-167">RELATED LINKS</span></span>

[<span data-ttu-id="2eeab-168">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2eeab-168">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="2eeab-169">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2eeab-169">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="2eeab-170">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="2eeab-170">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="2eeab-171">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2eeab-171">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="2eeab-172">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2eeab-172">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

