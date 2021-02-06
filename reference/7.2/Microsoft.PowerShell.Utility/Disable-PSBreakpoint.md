---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-psbreakpoint?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSBreakpoint
ms.openlocfilehash: 2bd1a48d2075950cdb337063a100bf31534ac6fe
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602627"
---
# <span data-ttu-id="d5f27-102">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="d5f27-102">Disable-PSBreakpoint</span></span>

## <span data-ttu-id="d5f27-103">概要</span><span class="sxs-lookup"><span data-stu-id="d5f27-103">SYNOPSIS</span></span>
<span data-ttu-id="d5f27-104">現在のコンソール内のブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d5f27-104">Disables the breakpoints in the current console.</span></span>

## <span data-ttu-id="d5f27-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d5f27-105">SYNTAX</span></span>

### <span data-ttu-id="d5f27-106">ブレークポイント (既定値)</span><span class="sxs-lookup"><span data-stu-id="d5f27-106">Breakpoint (Default)</span></span>

```
Disable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d5f27-107">Id</span><span class="sxs-lookup"><span data-stu-id="d5f27-107">Id</span></span>

```
Disable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d5f27-108">Description</span><span class="sxs-lookup"><span data-stu-id="d5f27-108">DESCRIPTION</span></span>

<span data-ttu-id="d5f27-109">**-PSBreakpoint** ポイントコマンドレットは、ブレークポイントを無効にします。これにより、スクリプトの実行時にヒットしないことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="d5f27-109">The **Disable-PSBreakpoint** cmdlet disables breakpoints, which assures that they are not hit when the script runs.</span></span>
<span data-ttu-id="d5f27-110">これを使用してすべてのブレークポイントを無効にするか、ブレークポイント オブジェクト ID またはブレークポイント ID を送信してブレークポイントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="d5f27-110">You can use it to disable all breakpoints, or you can specify breakpoints by submitting breakpoint objects or breakpoint IDs.</span></span>

<span data-ttu-id="d5f27-111">技術的には、このコマンドレットを使用して、ブレークポイントのオブジェクトの Enabled プロパティの値を False に変更します。</span><span class="sxs-lookup"><span data-stu-id="d5f27-111">Technically, this cmdlet changes the value of the Enabled property of a breakpoint object to False.</span></span>
<span data-ttu-id="d5f27-112">ブレークポイントを再び有効にするには、Enable-PSBreakpoint コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5f27-112">To re-enable a breakpoint, use the Enable-PSBreakpoint cmdlet.</span></span>
<span data-ttu-id="d5f27-113">ブレークポイントは、Set-PSBreakpoint コマンドレットを使用して作成したときに既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="d5f27-113">Breakpoints are enabled by default when you create them by using the Set-PSBreakpoint cmdlet.</span></span>

<span data-ttu-id="d5f27-114">ブレークポイントは、スクリプト内の指示を調べることができるように、実行を一時的に停止するスクリプト内のポイントです。</span><span class="sxs-lookup"><span data-stu-id="d5f27-114">A breakpoint is a point in a script where execution stops temporarily so that you can examine the instructions in the script.</span></span>
<span data-ttu-id="d5f27-115">**Disable-PSBreakpoint ポイントは、** PowerShell スクリプトのデバッグ用に設計されたいくつかのコマンドレットの1つです。</span><span class="sxs-lookup"><span data-stu-id="d5f27-115">**Disable-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="d5f27-116">PowerShell デバッガーの詳細については、「about_Debuggers」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5f27-116">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="d5f27-117">例</span><span class="sxs-lookup"><span data-stu-id="d5f27-117">EXAMPLES</span></span>

### <span data-ttu-id="d5f27-118">例 1: ブレークポイントを設定して無効にする</span><span class="sxs-lookup"><span data-stu-id="d5f27-118">Example 1: Set a breakpoint and disable it</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "name"
PS C:\> $B | Disable-PSBreakpoint
```

<span data-ttu-id="d5f27-119">これらのコマンドは、新しく作成したブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d5f27-119">These commands disable a newly-created breakpoint.</span></span>

<span data-ttu-id="d5f27-120">最初のコマンドは、Set-PSBreakpoint コマンドレットを使用して、Sample.ps1 スクリプト内の *Name* 変数にブレークポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="d5f27-120">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the *Name* variable in the Sample.ps1 script.</span></span>
<span data-ttu-id="d5f27-121">次に、ブレークポイントオブジェクトを $B 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="d5f27-121">Then, it saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="d5f27-122">2番目のコマンドは、 **disable-PSBreakpoint ポイント** コマンドレットを使用して、新しいブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d5f27-122">The second command uses the **Disable-PSBreakpoint** cmdlet to disable the new breakpoint.</span></span>
<span data-ttu-id="d5f27-123">パイプライン演算子 (|) を使用して、$B 内のブレークポイントオブジェクトを **無効-PSBreakpoint ポイント** コマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="d5f27-123">It uses a pipeline operator (|) to send the breakpoint object in $B to the **Disable-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="d5f27-124">このコマンドの結果として、$B 内のブレークポイントオブジェクトの Enabled プロパティの値は False になります。</span><span class="sxs-lookup"><span data-stu-id="d5f27-124">As a result of this command, the value of the Enabled property of the breakpoint object in $B is False.</span></span>

### <span data-ttu-id="d5f27-125">例 2: ブレークポイントを無効にする</span><span class="sxs-lookup"><span data-stu-id="d5f27-125">Example 2: Disable a breakpoint</span></span>

```
PS C:\> Disable-PSBreakpoint -Id 0
```

<span data-ttu-id="d5f27-126">このコマンドは、ブレークポイント ID が 0 のブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d5f27-126">This command disables the breakpoint with breakpoint ID 0.</span></span>

### <span data-ttu-id="d5f27-127">例 3: 無効になっているブレークポイントを作成する</span><span class="sxs-lookup"><span data-stu-id="d5f27-127">Example 3: Create a disabled breakpoint</span></span>

```
PS C:\> Disable-PSBreakpoint -Breakpoint ($B = Set-PSBreakpoint -Script "sample.ps1" -Line 5)
PS C:\> $B
```

<span data-ttu-id="d5f27-128">このコマンドは、有効に設定するまで無効である新しいブレークポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="d5f27-128">This command creates a new breakpoint that is disabled until you enable it.</span></span>

<span data-ttu-id="d5f27-129">このコマンドは、 **disable-PSBreakpoint** ポイントコマンドレットを使用して、ブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d5f27-129">It uses the **Disable-PSBreakpoint** cmdlet to disable the breakpoint.</span></span>
<span data-ttu-id="d5f27-130">*ブレークポイント* パラメーターの値は、新しいブレークポイントを設定し、ブレークポイントオブジェクトを生成し、そのオブジェクトを $B 変数に保存する Set-PSBreakpoint コマンドです。</span><span class="sxs-lookup"><span data-stu-id="d5f27-130">The value of the *Breakpoint* parameter is a Set-PSBreakpoint command that sets a new breakpoint, generates a breakpoint object, and saves the object in the $B variable.</span></span>

<span data-ttu-id="d5f27-131">オブジェクトを値として受け取るコマンドレットのパラメーターは、オブジェクトを含む変数や、オブジェクトを取得または生成するコマンドを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="d5f27-131">Cmdlet parameters that take objects as their values can accept a variable that contains the object or a command that gets or generates the object.</span></span>
<span data-ttu-id="d5f27-132">この場合、 **設定-PSBreakpoint** ポイントはブレークポイントオブジェクトを生成するため、 *ブレーク* ポイントパラメーターの値として使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5f27-132">In this case, because **Set-PSBreakpoint** generates a breakpoint object, it can be used as the value of the *Breakpoint* parameter.</span></span>

<span data-ttu-id="d5f27-133">2番目のコマンドは、$B 変数の値にブレークポイントオブジェクトを表示します。</span><span class="sxs-lookup"><span data-stu-id="d5f27-133">The second command displays the breakpoint object in the value of the $B variable.</span></span>

### <span data-ttu-id="d5f27-134">例 4: 現在のコンソールのすべてのブレークポイントを無効にする</span><span class="sxs-lookup"><span data-stu-id="d5f27-134">Example 4: Disable all breakpoints in the current console</span></span>

```
PS C:\> Get-PSBreakpoint | Disable-PSBreakpoint
```

<span data-ttu-id="d5f27-135">このコマンドは、現在のコンソールのすべてのブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d5f27-135">This command disables all breakpoints in the current console.</span></span>
<span data-ttu-id="d5f27-136">次のように、このコマンドを省略することができます。 "gbp |.dbp "。</span><span class="sxs-lookup"><span data-stu-id="d5f27-136">You can abbreviate this command as: "gbp | dbp".</span></span>

## <span data-ttu-id="d5f27-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d5f27-137">PARAMETERS</span></span>

### <span data-ttu-id="d5f27-138">-ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="d5f27-138">-Breakpoint</span></span>

<span data-ttu-id="d5f27-139">無効にするブレークポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="d5f27-139">Specifies the breakpoints to disable.</span></span>
<span data-ttu-id="d5f27-140">ブレークポイント オブジェクトを含んでいる変数または Get-PSBreakpoint コマンドのようなブレークポイント オブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="d5f27-140">Enter a variable that contains breakpoint objects or a command that gets breakpoint objects, such as a Get-PSBreakpoint command.</span></span>
<span data-ttu-id="d5f27-141">また、パイプを使用してブレークポイントオブジェクトを **無効** にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d5f27-141">You can also pipe breakpoint objects to the **Disable-PSBreakpoint** cmdlet.</span></span>

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

### <span data-ttu-id="d5f27-142">-Id</span><span class="sxs-lookup"><span data-stu-id="d5f27-142">-Id</span></span>

<span data-ttu-id="d5f27-143">指定したブレークポイント ID を持つブレークポイントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d5f27-143">Disables the breakpoints with the specified breakpoint IDs.</span></span>
<span data-ttu-id="d5f27-144">ID または ID が含まれる変数を入力します</span><span class="sxs-lookup"><span data-stu-id="d5f27-144">Enter the IDs or a variable that contains the IDs.</span></span>
<span data-ttu-id="d5f27-145">パイプを使用して Id を無効にすることはできません **-PSBreakpoint ポイント**。</span><span class="sxs-lookup"><span data-stu-id="d5f27-145">You cannot pipe IDs to **Disable-PSBreakpoint**.</span></span>

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

### <span data-ttu-id="d5f27-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d5f27-146">-PassThru</span></span>

<span data-ttu-id="d5f27-147">有効になっているブレークポイントを表すオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="d5f27-147">Returns an object representing the enabled breakpoints.</span></span>
<span data-ttu-id="d5f27-148">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="d5f27-148">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="d5f27-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d5f27-149">-Confirm</span></span>

<span data-ttu-id="d5f27-150">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5f27-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d5f27-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d5f27-151">-WhatIf</span></span>

<span data-ttu-id="d5f27-152">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="d5f27-152">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d5f27-153">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="d5f27-153">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d5f27-154">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d5f27-154">CommonParameters</span></span>

<span data-ttu-id="d5f27-155">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d5f27-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d5f27-156">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5f27-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d5f27-157">入力</span><span class="sxs-lookup"><span data-stu-id="d5f27-157">INPUTS</span></span>

### <span data-ttu-id="d5f27-158">システム.... ブレークポイント</span><span class="sxs-lookup"><span data-stu-id="d5f27-158">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="d5f27-159">パイプを使用して、ブレークポイントオブジェクトを無効にし、 **-PSBreakpoint ポイントを無効** にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d5f27-159">You can pipe a breakpoint object to **Disable-PSBreakpoint**.</span></span>

## <span data-ttu-id="d5f27-160">出力</span><span class="sxs-lookup"><span data-stu-id="d5f27-160">OUTPUTS</span></span>

### <span data-ttu-id="d5f27-161">None または system.string。</span><span class="sxs-lookup"><span data-stu-id="d5f27-161">None or System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="d5f27-162">*PassThru* パラメーターを使用すると、**無効** にしたブレークポイントを表すオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="d5f27-162">When you use the *PassThru* parameter, **Disable-PSBreakpoint** returns an object that represents the disabled breakpoint.</span></span>
<span data-ttu-id="d5f27-163">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="d5f27-163">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d5f27-164">注</span><span class="sxs-lookup"><span data-stu-id="d5f27-164">NOTES</span></span>

## <span data-ttu-id="d5f27-165">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d5f27-165">RELATED LINKS</span></span>

[<span data-ttu-id="d5f27-166">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="d5f27-166">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="d5f27-167">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="d5f27-167">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="d5f27-168">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="d5f27-168">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="d5f27-169">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="d5f27-169">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="d5f27-170">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="d5f27-170">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

