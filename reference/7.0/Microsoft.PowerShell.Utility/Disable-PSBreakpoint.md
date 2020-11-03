---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-psbreakpoint?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSBreakpoint
ms.openlocfilehash: 80d0c77e4c54dbc7e501339f5550c87f5f1ddbed
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210731"
---
# <span data-ttu-id="ebb4e-103">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ebb4e-103">Disable-PSBreakpoint</span></span>

## <span data-ttu-id="ebb4e-104">概要</span><span class="sxs-lookup"><span data-stu-id="ebb4e-104">SYNOPSIS</span></span>
<span data-ttu-id="ebb4e-105">現在のコンソール内のブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-105">Disables the breakpoints in the current console.</span></span>

## <span data-ttu-id="ebb4e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ebb4e-106">SYNTAX</span></span>

### <span data-ttu-id="ebb4e-107">ブレークポイント (既定値)</span><span class="sxs-lookup"><span data-stu-id="ebb4e-107">Breakpoint (Default)</span></span>

```
Disable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ebb4e-108">Id</span><span class="sxs-lookup"><span data-stu-id="ebb4e-108">Id</span></span>

```
Disable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ebb4e-109">Description</span><span class="sxs-lookup"><span data-stu-id="ebb4e-109">DESCRIPTION</span></span>

<span data-ttu-id="ebb4e-110">**-PSBreakpoint** ポイントコマンドレットは、ブレークポイントを無効にします。これにより、スクリプトの実行時にヒットしないことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-110">The **Disable-PSBreakpoint** cmdlet disables breakpoints, which assures that they are not hit when the script runs.</span></span>
<span data-ttu-id="ebb4e-111">これを使用してすべてのブレークポイントを無効にするか、ブレークポイント オブジェクト ID またはブレークポイント ID を送信してブレークポイントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-111">You can use it to disable all breakpoints, or you can specify breakpoints by submitting breakpoint objects or breakpoint IDs.</span></span>

<span data-ttu-id="ebb4e-112">技術的には、このコマンドレットを使用して、ブレークポイントのオブジェクトの Enabled プロパティの値を False に変更します。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-112">Technically, this cmdlet changes the value of the Enabled property of a breakpoint object to False.</span></span>
<span data-ttu-id="ebb4e-113">ブレークポイントを再び有効にするには、Enable-PSBreakpoint コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-113">To re-enable a breakpoint, use the Enable-PSBreakpoint cmdlet.</span></span>
<span data-ttu-id="ebb4e-114">ブレークポイントは、Set-PSBreakpoint コマンドレットを使用して作成したときに既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-114">Breakpoints are enabled by default when you create them by using the Set-PSBreakpoint cmdlet.</span></span>

<span data-ttu-id="ebb4e-115">ブレークポイントは、スクリプト内の指示を調べることができるように、実行を一時的に停止するスクリプト内のポイントです。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-115">A breakpoint is a point in a script where execution stops temporarily so that you can examine the instructions in the script.</span></span>
<span data-ttu-id="ebb4e-116">**Disable-PSBreakpoint ポイントは、** PowerShell スクリプトのデバッグ用に設計されたいくつかのコマンドレットの1つです。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-116">**Disable-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="ebb4e-117">PowerShell デバッガーの詳細については、「about_Debuggers」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-117">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="ebb4e-118">例</span><span class="sxs-lookup"><span data-stu-id="ebb4e-118">EXAMPLES</span></span>

### <span data-ttu-id="ebb4e-119">例 1: ブレークポイントを設定して無効にする</span><span class="sxs-lookup"><span data-stu-id="ebb4e-119">Example 1: Set a breakpoint and disable it</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "name"
PS C:\> $B | Disable-PSBreakpoint
```

<span data-ttu-id="ebb4e-120">これらのコマンドは、新しく作成したブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-120">These commands disable a newly-created breakpoint.</span></span>

<span data-ttu-id="ebb4e-121">最初のコマンドは、Set-PSBreakpoint コマンドレットを使用して、Sample.ps1 スクリプト内の *Name* 変数にブレークポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-121">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the *Name* variable in the Sample.ps1 script.</span></span>
<span data-ttu-id="ebb4e-122">次に、ブレークポイントオブジェクトを $B 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-122">Then, it saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="ebb4e-123">2番目のコマンドは、 **disable-PSBreakpoint ポイント** コマンドレットを使用して、新しいブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-123">The second command uses the **Disable-PSBreakpoint** cmdlet to disable the new breakpoint.</span></span>
<span data-ttu-id="ebb4e-124">パイプライン演算子 (|) を使用して、$B 内のブレークポイントオブジェクトを **無効-PSBreakpoint ポイント** コマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-124">It uses a pipeline operator (|) to send the breakpoint object in $B to the **Disable-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="ebb4e-125">このコマンドの結果として、$B 内のブレークポイントオブジェクトの Enabled プロパティの値は False になります。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-125">As a result of this command, the value of the Enabled property of the breakpoint object in $B is False.</span></span>

### <span data-ttu-id="ebb4e-126">例 2: ブレークポイントを無効にする</span><span class="sxs-lookup"><span data-stu-id="ebb4e-126">Example 2: Disable a breakpoint</span></span>

```
PS C:\> Disable-PSBreakpoint -Id 0
```

<span data-ttu-id="ebb4e-127">このコマンドは、ブレークポイント ID が 0 のブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-127">This command disables the breakpoint with breakpoint ID 0.</span></span>

### <span data-ttu-id="ebb4e-128">例 3: 無効になっているブレークポイントを作成する</span><span class="sxs-lookup"><span data-stu-id="ebb4e-128">Example 3: Create a disabled breakpoint</span></span>

```
PS C:\> Disable-PSBreakpoint -Breakpoint ($B = Set-PSBreakpoint -Script "sample.ps1" -Line 5)
PS C:\> $B
```

<span data-ttu-id="ebb4e-129">このコマンドは、有効に設定するまで無効である新しいブレークポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-129">This command creates a new breakpoint that is disabled until you enable it.</span></span>

<span data-ttu-id="ebb4e-130">このコマンドは、 **disable-PSBreakpoint** ポイントコマンドレットを使用して、ブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-130">It uses the **Disable-PSBreakpoint** cmdlet to disable the breakpoint.</span></span>
<span data-ttu-id="ebb4e-131">*ブレークポイント* パラメーターの値は、新しいブレークポイントを設定し、ブレークポイントオブジェクトを生成し、そのオブジェクトを $B 変数に保存する Set-PSBreakpoint コマンドです。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-131">The value of the *Breakpoint* parameter is a Set-PSBreakpoint command that sets a new breakpoint, generates a breakpoint object, and saves the object in the $B variable.</span></span>

<span data-ttu-id="ebb4e-132">オブジェクトを値として受け取るコマンドレットのパラメーターは、オブジェクトを含む変数や、オブジェクトを取得または生成するコマンドを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-132">Cmdlet parameters that take objects as their values can accept a variable that contains the object or a command that gets or generates the object.</span></span>
<span data-ttu-id="ebb4e-133">この場合、 **設定-PSBreakpoint** ポイントはブレークポイントオブジェクトを生成するため、 *ブレーク* ポイントパラメーターの値として使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-133">In this case, because **Set-PSBreakpoint** generates a breakpoint object, it can be used as the value of the *Breakpoint* parameter.</span></span>

<span data-ttu-id="ebb4e-134">2番目のコマンドは、$B 変数の値にブレークポイントオブジェクトを表示します。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-134">The second command displays the breakpoint object in the value of the $B variable.</span></span>

### <span data-ttu-id="ebb4e-135">例 4: 現在のコンソールのすべてのブレークポイントを無効にする</span><span class="sxs-lookup"><span data-stu-id="ebb4e-135">Example 4: Disable all breakpoints in the current console</span></span>

```
PS C:\> Get-PSBreakpoint | Disable-PSBreakpoint
```

<span data-ttu-id="ebb4e-136">このコマンドは、現在のコンソールのすべてのブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-136">This command disables all breakpoints in the current console.</span></span>
<span data-ttu-id="ebb4e-137">次のように、このコマンドを省略することができます。 "gbp |.dbp "。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-137">You can abbreviate this command as: "gbp | dbp".</span></span>

## <span data-ttu-id="ebb4e-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ebb4e-138">PARAMETERS</span></span>

### <span data-ttu-id="ebb4e-139">-ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="ebb4e-139">-Breakpoint</span></span>

<span data-ttu-id="ebb4e-140">無効にするブレークポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-140">Specifies the breakpoints to disable.</span></span>
<span data-ttu-id="ebb4e-141">ブレークポイント オブジェクトを含んでいる変数または Get-PSBreakpoint コマンドのようなブレークポイント オブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-141">Enter a variable that contains breakpoint objects or a command that gets breakpoint objects, such as a Get-PSBreakpoint command.</span></span>
<span data-ttu-id="ebb4e-142">また、パイプを使用してブレークポイントオブジェクトを **無効** にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-142">You can also pipe breakpoint objects to the **Disable-PSBreakpoint** cmdlet.</span></span>

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

### <span data-ttu-id="ebb4e-143">-Id</span><span class="sxs-lookup"><span data-stu-id="ebb4e-143">-Id</span></span>

<span data-ttu-id="ebb4e-144">指定したブレークポイント ID を持つブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-144">Disables the breakpoints with the specified breakpoint IDs.</span></span>
<span data-ttu-id="ebb4e-145">ID または ID が含まれる変数を入力します</span><span class="sxs-lookup"><span data-stu-id="ebb4e-145">Enter the IDs or a variable that contains the IDs.</span></span>
<span data-ttu-id="ebb4e-146">パイプを使用して Id を無効にすることはできません **-PSBreakpoint ポイント** 。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-146">You cannot pipe IDs to **Disable-PSBreakpoint** .</span></span>

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

### <span data-ttu-id="ebb4e-147">-PassThru</span><span class="sxs-lookup"><span data-stu-id="ebb4e-147">-PassThru</span></span>

<span data-ttu-id="ebb4e-148">有効になっているブレークポイントを表すオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-148">Returns an object representing the enabled breakpoints.</span></span>
<span data-ttu-id="ebb4e-149">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-149">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="ebb4e-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ebb4e-150">-Confirm</span></span>

<span data-ttu-id="ebb4e-151">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ebb4e-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ebb4e-152">-WhatIf</span></span>

<span data-ttu-id="ebb4e-153">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-153">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ebb4e-154">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ebb4e-155">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ebb4e-155">CommonParameters</span></span>

<span data-ttu-id="ebb4e-156">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ebb4e-157">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ebb4e-158">入力</span><span class="sxs-lookup"><span data-stu-id="ebb4e-158">INPUTS</span></span>

### <span data-ttu-id="ebb4e-159">システム.... ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="ebb4e-159">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="ebb4e-160">パイプを使用して、ブレークポイントオブジェクトを無効にし、 **-PSBreakpoint ポイントを無効** にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-160">You can pipe a breakpoint object to **Disable-PSBreakpoint** .</span></span>

## <span data-ttu-id="ebb4e-161">出力</span><span class="sxs-lookup"><span data-stu-id="ebb4e-161">OUTPUTS</span></span>

### <span data-ttu-id="ebb4e-162">None または system.string。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-162">None or System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="ebb4e-163">*PassThru* パラメーターを使用すると、 **無効** にしたブレークポイントを表すオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-163">When you use the *PassThru* parameter, **Disable-PSBreakpoint** returns an object that represents the disabled breakpoint.</span></span>
<span data-ttu-id="ebb4e-164">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="ebb4e-164">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ebb4e-165">注</span><span class="sxs-lookup"><span data-stu-id="ebb4e-165">NOTES</span></span>

## <span data-ttu-id="ebb4e-166">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ebb4e-166">RELATED LINKS</span></span>

[<span data-ttu-id="ebb4e-167">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ebb4e-167">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="ebb4e-168">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ebb4e-168">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="ebb4e-169">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="ebb4e-169">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="ebb4e-170">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ebb4e-170">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="ebb4e-171">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ebb4e-171">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
