---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 08/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-psdebug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSDebug
ms.openlocfilehash: 45764b09bfa1f632fe5c36ca76b32b4a1b54874c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600993"
---
# <span data-ttu-id="dbb9c-102">Set-PSDebug</span><span class="sxs-lookup"><span data-stu-id="dbb9c-102">Set-PSDebug</span></span>

## <span data-ttu-id="dbb9c-103">概要</span><span class="sxs-lookup"><span data-stu-id="dbb9c-103">SYNOPSIS</span></span>
<span data-ttu-id="dbb9c-104">スクリプトのデバッグ機能のオン/オフの切り替え、トレース レベルの設定、厳格モードの切り替えを行います。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-104">Turns script debugging features on and off, sets the trace level, and toggles strict mode.</span></span>

## <span data-ttu-id="dbb9c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dbb9c-105">SYNTAX</span></span>

### <span data-ttu-id="dbb9c-106">on</span><span class="sxs-lookup"><span data-stu-id="dbb9c-106">on</span></span>

```
Set-PSDebug [-Trace <Int32>] [-Step] [-Strict] [<CommonParameters>]
```

### <span data-ttu-id="dbb9c-107">オフ</span><span class="sxs-lookup"><span data-stu-id="dbb9c-107">off</span></span>

```
Set-PSDebug [-Off] [<CommonParameters>]
```

## <span data-ttu-id="dbb9c-108">Description</span><span class="sxs-lookup"><span data-stu-id="dbb9c-108">DESCRIPTION</span></span>

<span data-ttu-id="dbb9c-109">`Set-PSDebug`コマンドレットは、スクリプトのデバッグ機能のオンとオフの切り替え、トレースレベルの設定、厳格モードの切り替えを行います。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-109">The `Set-PSDebug` cmdlet turns script debugging features on and off, sets the trace level, and toggles strict mode.</span></span> <span data-ttu-id="dbb9c-110">既定では、PowerShell デバッグ機能はオフになっています。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-110">By default, the PowerShell debug features are off.</span></span>

<span data-ttu-id="dbb9c-111">**Trace** パラメーターの値がの場合 `1` 、スクリプトの各行は実行時にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-111">When the **Trace** parameter has a value of `1`, each line of script is traced as it runs.</span></span> <span data-ttu-id="dbb9c-112">パラメーターの値がの場合 `2` 、変数の代入、関数の呼び出し、およびスクリプトの呼び出しもトレースされます。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-112">When the parameter has a value of `2`, variable assignments, function calls, and script calls are also traced.</span></span> <span data-ttu-id="dbb9c-113">**Step** パラメーターを指定した場合は、スクリプトの各行が実行される前にプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-113">If the **Step** parameter is specified, you're prompted before each line of the script runs.</span></span>

## <span data-ttu-id="dbb9c-114">例</span><span class="sxs-lookup"><span data-stu-id="dbb9c-114">EXAMPLES</span></span>

### <span data-ttu-id="dbb9c-115">例 1: トレースレベルを設定する</span><span class="sxs-lookup"><span data-stu-id="dbb9c-115">Example 1: Set the trace level</span></span>

<span data-ttu-id="dbb9c-116">この例では、トレースレベルをに設定し、 `2` 1、2、およびの数値を表示するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-116">This example sets the trace level to `2`, and then runs a script that displays the numbers 1, 2, and</span></span>
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

### <span data-ttu-id="dbb9c-117">例 2: ステップ実行を有効にする</span><span class="sxs-lookup"><span data-stu-id="dbb9c-117">Example 2: Turn on stepping</span></span>

<span data-ttu-id="dbb9c-118">この例では、ステップ実行をオンにして、1、2、および3の番号を表示するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-118">This example turns on stepping, and then runs a script that displays the numbers 1, 2, and 3.</span></span>

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

### <span data-ttu-id="dbb9c-119">例 3: strict モードを使用する</span><span class="sxs-lookup"><span data-stu-id="dbb9c-119">Example 3: Use strict mode</span></span>

<span data-ttu-id="dbb9c-120">この例では、PowerShell を厳格モードで配置し、値が割り当てられていない変数にアクセスしようとします。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-120">This example puts PowerShell in strict mode and attempts to access a variable that doesn't have an assigned value.</span></span>

```powershell
Set-PSDebug -Strict; $NewVar
```

```Output
The variable '$NewVar' cannot be retrieved because it has not been set.
At line:1 char:22
+ Set-PSDebug -Strict; $NewVar
```

### <span data-ttu-id="dbb9c-121">例 4: デバッグ機能を無効にする</span><span class="sxs-lookup"><span data-stu-id="dbb9c-121">Example 4: Turn off debug features</span></span>

<span data-ttu-id="dbb9c-122">この例では、すべてのデバッグ機能をオフにしてから、1、2、および3の番号を表示するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-122">This example turns off all debugging features, and then runs a script that displays the numbers 1, 2, and 3.</span></span>

```powershell
Set-PSDebug -Off; foreach ($i in 1..3) {$i}
```

```Output
1
2
3
```

## <span data-ttu-id="dbb9c-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dbb9c-123">PARAMETERS</span></span>

### <span data-ttu-id="dbb9c-124">-Off</span><span class="sxs-lookup"><span data-stu-id="dbb9c-124">-Off</span></span>

<span data-ttu-id="dbb9c-125">すべてのスクリプト デバッグ機能をオフにします。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-125">Turns off all script debugging features.</span></span>

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

### <span data-ttu-id="dbb9c-126">-ステップ</span><span class="sxs-lookup"><span data-stu-id="dbb9c-126">-Step</span></span>

<span data-ttu-id="dbb9c-127">スクリプトのステップ実行をオンにします。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-127">Turns on script stepping.</span></span> <span data-ttu-id="dbb9c-128">各行が実行される前に、PowerShell は、スクリプトの状態を検査するために、停止するか、続行するか、新しいインタープリターレベルを入力するように求めます。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-128">Before each line runs, PowerShell prompts you to stop, continue, or enter a new interpreter level to inspect the state of the script.</span></span>

<span data-ttu-id="dbb9c-129">**Step** パラメーターを指定すると、のトレースレベルが自動的に設定さ `1` れます。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-129">Specifying the **Step** parameter automatically sets a trace level of `1`.</span></span>

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

### <span data-ttu-id="dbb9c-130">-Strict</span><span class="sxs-lookup"><span data-stu-id="dbb9c-130">-Strict</span></span>

<span data-ttu-id="dbb9c-131">スクリプトで参照される前に、変数に値を代入する必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-131">Specifies that variables must be assigned a value before being referenced in a script.</span></span> <span data-ttu-id="dbb9c-132">値が割り当てられる前に変数が参照されている場合、PowerShell は例外エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-132">If a variable is referenced before a value is assigned, PowerShell returns an exception error.</span></span> <span data-ttu-id="dbb9c-133">これは、`Set-StrictMode -Version 1` と同じです。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-133">This is equivalent to `Set-StrictMode -Version 1`.</span></span> <span data-ttu-id="dbb9c-134">詳細については、「 [set-strictmode](Set-StrictMode.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-134">For more information, see [Set-StrictMode](Set-StrictMode.md).</span></span>

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

### <span data-ttu-id="dbb9c-135">-トレース</span><span class="sxs-lookup"><span data-stu-id="dbb9c-135">-Trace</span></span>

<span data-ttu-id="dbb9c-136">スクリプトの各行のトレースレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-136">Specifies the trace level for each line in a script.</span></span> <span data-ttu-id="dbb9c-137">各行は実行時にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-137">Each line is traced as it's run.</span></span>

<span data-ttu-id="dbb9c-138">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-138">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="dbb9c-139">0: スクリプトのトレースをオフにします。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-139">0: Turn script tracing off.</span></span>
- <span data-ttu-id="dbb9c-140">1: 実行時にスクリプト行をトレースします。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-140">1: Trace script lines as they run.</span></span>
- <span data-ttu-id="dbb9c-141">2: スクリプト行、変数の代入、関数呼び出し、およびスクリプトをトレースします。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-141">2: Trace script lines, variable assignments, function calls, and scripts.</span></span>

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

### <span data-ttu-id="dbb9c-142">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="dbb9c-142">CommonParameters</span></span>

<span data-ttu-id="dbb9c-143">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dbb9c-144">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dbb9c-145">入力</span><span class="sxs-lookup"><span data-stu-id="dbb9c-145">INPUTS</span></span>

### <span data-ttu-id="dbb9c-146">なし</span><span class="sxs-lookup"><span data-stu-id="dbb9c-146">None</span></span>

<span data-ttu-id="dbb9c-147">このコマンドレットに入力をパイプラインすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-147">You can't pipeline input to this cmdlet.</span></span>

## <span data-ttu-id="dbb9c-148">出力</span><span class="sxs-lookup"><span data-stu-id="dbb9c-148">OUTPUTS</span></span>

### <span data-ttu-id="dbb9c-149">なし</span><span class="sxs-lookup"><span data-stu-id="dbb9c-149">None</span></span>

<span data-ttu-id="dbb9c-150">このコマンドレットは出力を返しません。</span><span class="sxs-lookup"><span data-stu-id="dbb9c-150">This cmdlet doesn't return any output.</span></span>

## <span data-ttu-id="dbb9c-151">注</span><span class="sxs-lookup"><span data-stu-id="dbb9c-151">NOTES</span></span>

## <span data-ttu-id="dbb9c-152">関連リンク</span><span class="sxs-lookup"><span data-stu-id="dbb9c-152">RELATED LINKS</span></span>

[<span data-ttu-id="dbb9c-153">about_Debuggers</span><span class="sxs-lookup"><span data-stu-id="dbb9c-153">about_Debuggers</span></span>](./About/about_Debuggers.md)

[<span data-ttu-id="dbb9c-154">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="dbb9c-154">Debug-Process</span></span>](../Microsoft.PowerShell.Management/Debug-Process.md)

[<span data-ttu-id="dbb9c-155">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="dbb9c-155">Set-PSBreakpoint</span></span>](../Microsoft.PowerShell.Utility/Set-PSBreakpoint.md)

[<span data-ttu-id="dbb9c-156">Set-StrictMode</span><span class="sxs-lookup"><span data-stu-id="dbb9c-156">Set-StrictMode</span></span>](Set-StrictMode.md)

[<span data-ttu-id="dbb9c-157">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="dbb9c-157">Write-Debug</span></span>](../Microsoft.PowerShell.Utility/Write-Debug.md)

