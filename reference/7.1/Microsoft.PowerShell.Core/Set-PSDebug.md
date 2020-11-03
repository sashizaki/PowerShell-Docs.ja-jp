---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-psdebug?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSDebug
ms.openlocfilehash: a0b5d7e86f9d63b487bc093feb18ecc7a4496999
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217003"
---
# <span data-ttu-id="69987-103">Set-PSDebug</span><span class="sxs-lookup"><span data-stu-id="69987-103">Set-PSDebug</span></span>

## <span data-ttu-id="69987-104">概要</span><span class="sxs-lookup"><span data-stu-id="69987-104">SYNOPSIS</span></span>
<span data-ttu-id="69987-105">スクリプトのデバッグ機能のオン/オフの切り替え、トレース レベルの設定、厳格モードの切り替えを行います。</span><span class="sxs-lookup"><span data-stu-id="69987-105">Turns script debugging features on and off, sets the trace level, and toggles strict mode.</span></span>

## <span data-ttu-id="69987-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="69987-106">SYNTAX</span></span>

### <span data-ttu-id="69987-107">on</span><span class="sxs-lookup"><span data-stu-id="69987-107">on</span></span>

```
Set-PSDebug [-Trace <Int32>] [-Step] [-Strict] [<CommonParameters>]
```

### <span data-ttu-id="69987-108">オフ</span><span class="sxs-lookup"><span data-stu-id="69987-108">off</span></span>

```
Set-PSDebug [-Off] [<CommonParameters>]
```

## <span data-ttu-id="69987-109">Description</span><span class="sxs-lookup"><span data-stu-id="69987-109">DESCRIPTION</span></span>

<span data-ttu-id="69987-110">`Set-PSDebug`コマンドレットは、スクリプトのデバッグ機能のオンとオフの切り替え、トレースレベルの設定、厳格モードの切り替えを行います。</span><span class="sxs-lookup"><span data-stu-id="69987-110">The `Set-PSDebug` cmdlet turns script debugging features on and off, sets the trace level, and toggles strict mode.</span></span> <span data-ttu-id="69987-111">既定では、PowerShell デバッグ機能はオフになっています。</span><span class="sxs-lookup"><span data-stu-id="69987-111">By default, the PowerShell debug features are off.</span></span>

<span data-ttu-id="69987-112">**Trace** パラメーターの値がの場合 `1` 、スクリプトの各行は実行時にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="69987-112">When the **Trace** parameter has a value of `1`, each line of script is traced as it runs.</span></span> <span data-ttu-id="69987-113">パラメーターの値がの場合 `2` 、変数の代入、関数の呼び出し、およびスクリプトの呼び出しもトレースされます。</span><span class="sxs-lookup"><span data-stu-id="69987-113">When the parameter has a value of `2`, variable assignments, function calls, and script calls are also traced.</span></span> <span data-ttu-id="69987-114">**Step** パラメーターを指定した場合は、スクリプトの各行が実行される前にプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69987-114">If the **Step** parameter is specified, you're prompted before each line of the script runs.</span></span>

## <span data-ttu-id="69987-115">例</span><span class="sxs-lookup"><span data-stu-id="69987-115">EXAMPLES</span></span>

### <span data-ttu-id="69987-116">例 1: トレースレベルを設定する</span><span class="sxs-lookup"><span data-stu-id="69987-116">Example 1: Set the trace level</span></span>

<span data-ttu-id="69987-117">この例では、トレースレベルをに設定し、 `2` 1、2、およびの数値を表示するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="69987-117">This example sets the trace level to `2`, and then runs a script that displays the numbers 1, 2, and</span></span>
3.

```powershell
Set-PSDebug -Trace 2; foreach ($i in 1..3) {$i}
```

```Output
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in  >>>> 1..3) {$i}
DEBUG:     ! SET $foreach = 'IEnumerator'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '1'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
1
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '2'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
2
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $i = '3'.
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ($i in 1..3) { >>>> $i}
3
DEBUG:    1+ Set-PSDebug -Trace 2; foreach ( >>>> $i in 1..3) {$i}
DEBUG:     ! SET $foreach = ''.
```

### <span data-ttu-id="69987-118">例 2: ステップ実行を有効にする</span><span class="sxs-lookup"><span data-stu-id="69987-118">Example 2: Turn on stepping</span></span>

<span data-ttu-id="69987-119">この例では、ステップ実行をオンにして、1、2、および3の番号を表示するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="69987-119">This example turns on stepping, and then runs a script that displays the numbers 1, 2, and 3.</span></span>

```powershell
Set-PSDebug -Step; foreach ($i in 1..3) {$i}
```

```Output
Continue with this operation?
   1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): A
DEBUG:    1+ Set-PSDebug -Step; foreach ($i in  >>>> 1..3) {$i}
1
2
3
```

### <span data-ttu-id="69987-120">例 3: strict モードを使用する</span><span class="sxs-lookup"><span data-stu-id="69987-120">Example 3: Use strict mode</span></span>

<span data-ttu-id="69987-121">この例では、PowerShell を厳格モードで配置し、値が割り当てられていない変数にアクセスしようとします。</span><span class="sxs-lookup"><span data-stu-id="69987-121">This example puts PowerShell in strict mode and attempts to access a variable that doesn't have an assigned value.</span></span>

```powershell
Set-PSDebug -Strict; $NewVar
```

```Output
The variable '$NewVar' cannot be retrieved because it has not been set.
At line:1 char:22
+ Set-PSDebug -Strict; $NewVar
```

### <span data-ttu-id="69987-122">例 4: デバッグ機能を無効にする</span><span class="sxs-lookup"><span data-stu-id="69987-122">Example 4: Turn off debug features</span></span>

<span data-ttu-id="69987-123">この例では、すべてのデバッグ機能をオフにしてから、1、2、および3の番号を表示するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="69987-123">This example turns off all debugging features, and then runs a script that displays the numbers 1, 2, and 3.</span></span>

```powershell
Set-PSDebug -Off; foreach ($i in 1..3) {$i}
```

```Output
1
2
3
```

## <span data-ttu-id="69987-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="69987-124">PARAMETERS</span></span>

### <span data-ttu-id="69987-125">-Off</span><span class="sxs-lookup"><span data-stu-id="69987-125">-Off</span></span>

<span data-ttu-id="69987-126">すべてのスクリプト デバッグ機能をオフにします。</span><span class="sxs-lookup"><span data-stu-id="69987-126">Turns off all script debugging features.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: off
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69987-127">-ステップ</span><span class="sxs-lookup"><span data-stu-id="69987-127">-Step</span></span>

<span data-ttu-id="69987-128">スクリプトのステップ実行をオンにします。</span><span class="sxs-lookup"><span data-stu-id="69987-128">Turns on script stepping.</span></span> <span data-ttu-id="69987-129">各行が実行される前に、PowerShell は、スクリプトの状態を検査するために、停止するか、続行するか、新しいインタープリターレベルを入力するように求めます。</span><span class="sxs-lookup"><span data-stu-id="69987-129">Before each line runs, PowerShell prompts you to stop, continue, or enter a new interpreter level to inspect the state of the script.</span></span>

<span data-ttu-id="69987-130">**Step** パラメーターを指定すると、のトレースレベルが自動的に設定さ `1` れます。</span><span class="sxs-lookup"><span data-stu-id="69987-130">Specifying the **Step** parameter automatically sets a trace level of `1`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69987-131">-Strict</span><span class="sxs-lookup"><span data-stu-id="69987-131">-Strict</span></span>

<span data-ttu-id="69987-132">スクリプトで参照される前に、変数に値を代入する必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="69987-132">Specifies that variables must be assigned a value before being referenced in a script.</span></span> <span data-ttu-id="69987-133">値が割り当てられる前に変数が参照されている場合、PowerShell は例外エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="69987-133">If a variable is referenced before a value is assigned, PowerShell returns an exception error.</span></span> <span data-ttu-id="69987-134">これは、`Set-StrictMode -Version 1` と同じです。</span><span class="sxs-lookup"><span data-stu-id="69987-134">This is equivalent to `Set-StrictMode -Version 1`.</span></span> <span data-ttu-id="69987-135">詳細については、「 [set-strictmode](Set-StrictMode.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69987-135">For more information, see [Set-StrictMode](Set-StrictMode.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69987-136">-トレース</span><span class="sxs-lookup"><span data-stu-id="69987-136">-Trace</span></span>

<span data-ttu-id="69987-137">スクリプトの各行のトレースレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="69987-137">Specifies the trace level for each line in a script.</span></span> <span data-ttu-id="69987-138">各行は実行時にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="69987-138">Each line is traced as it's run.</span></span>

<span data-ttu-id="69987-139">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="69987-139">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="69987-140">0: スクリプトのトレースをオフにします。</span><span class="sxs-lookup"><span data-stu-id="69987-140">0: Turn script tracing off.</span></span>
- <span data-ttu-id="69987-141">1: 実行時にスクリプト行をトレースします。</span><span class="sxs-lookup"><span data-stu-id="69987-141">1: Trace script lines as they run.</span></span>
- <span data-ttu-id="69987-142">2: スクリプト行、変数の代入、関数呼び出し、およびスクリプトをトレースします。</span><span class="sxs-lookup"><span data-stu-id="69987-142">2: Trace script lines, variable assignments, function calls, and scripts.</span></span>

```yaml
Type: System.Int32
Parameter Sets: on
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="69987-143">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="69987-143">CommonParameters</span></span>

<span data-ttu-id="69987-144">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="69987-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="69987-145">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69987-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="69987-146">入力</span><span class="sxs-lookup"><span data-stu-id="69987-146">INPUTS</span></span>

### <span data-ttu-id="69987-147">なし</span><span class="sxs-lookup"><span data-stu-id="69987-147">None</span></span>

<span data-ttu-id="69987-148">このコマンドレットに入力をパイプラインすることはできません。</span><span class="sxs-lookup"><span data-stu-id="69987-148">You can't pipeline input to this cmdlet.</span></span>

## <span data-ttu-id="69987-149">出力</span><span class="sxs-lookup"><span data-stu-id="69987-149">OUTPUTS</span></span>

### <span data-ttu-id="69987-150">なし</span><span class="sxs-lookup"><span data-stu-id="69987-150">None</span></span>

<span data-ttu-id="69987-151">このコマンドレットは出力を返しません。</span><span class="sxs-lookup"><span data-stu-id="69987-151">This cmdlet doesn't return any output.</span></span>

## <span data-ttu-id="69987-152">注</span><span class="sxs-lookup"><span data-stu-id="69987-152">NOTES</span></span>

## <span data-ttu-id="69987-153">関連リンク</span><span class="sxs-lookup"><span data-stu-id="69987-153">RELATED LINKS</span></span>

[<span data-ttu-id="69987-154">about_Debuggers</span><span class="sxs-lookup"><span data-stu-id="69987-154">about_Debuggers</span></span>](./About/about_Debuggers.md)

[<span data-ttu-id="69987-155">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="69987-155">Debug-Process</span></span>](../Microsoft.PowerShell.Management/Debug-Process.md)

[<span data-ttu-id="69987-156">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="69987-156">Set-PSBreakpoint</span></span>](../Microsoft.PowerShell.Utility/Set-PSBreakpoint.md)

[<span data-ttu-id="69987-157">Set-StrictMode</span><span class="sxs-lookup"><span data-stu-id="69987-157">Set-StrictMode</span></span>](Set-StrictMode.md)

[<span data-ttu-id="69987-158">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="69987-158">Write-Debug</span></span>](../Microsoft.PowerShell.Utility/Write-Debug.md)
