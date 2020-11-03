---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: 905f3522a071fdd3f59d020b734c689a59e68a63
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217680"
---
# <span data-ttu-id="5ae35-103">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="5ae35-103">Debug-Process</span></span>

## <span data-ttu-id="5ae35-104">概要</span><span class="sxs-lookup"><span data-stu-id="5ae35-104">SYNOPSIS</span></span>
<span data-ttu-id="5ae35-105">ローカル コンピューター上で実行中の 1 つ以上のプロセスをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="5ae35-105">Debugs one or more processes running on the local computer.</span></span>

## <span data-ttu-id="5ae35-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5ae35-106">SYNTAX</span></span>

### <span data-ttu-id="5ae35-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="5ae35-107">Name (Default)</span></span>

```
Debug-Process [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5ae35-108">Id</span><span class="sxs-lookup"><span data-stu-id="5ae35-108">Id</span></span>

```
Debug-Process [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5ae35-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="5ae35-109">InputObject</span></span>

```
Debug-Process -InputObject <Process[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5ae35-110">Description</span><span class="sxs-lookup"><span data-stu-id="5ae35-110">DESCRIPTION</span></span>

<span data-ttu-id="5ae35-111">**Debug Process** コマンドレットは、ローカルコンピューター上で実行中の1つ以上のプロセスにデバッガーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="5ae35-111">The **Debug-Process** cmdlet attaches a debugger to one or more running processes on a local computer.</span></span>
<span data-ttu-id="5ae35-112">プロセスは、プロセス名またはプロセス ID (PID) で指定することも、パイプを使用してこのコマンドレットに処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="5ae35-112">You can specify the processes by their process name or process ID (PID), or you can pipe process objects to this cmdlet.</span></span>

<span data-ttu-id="5ae35-113">このコマンドレットは、プロセスに対して現在登録されているデバッガーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="5ae35-113">This cmdlet attaches the debugger that is currently registered for the process.</span></span>
<span data-ttu-id="5ae35-114">このコマンドレットを使用する前に、デバッガーがダウンロードされていて適切に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-114">Before using this cmdlet, verify that a debugger is downloaded and correctly configured.</span></span>

## <span data-ttu-id="5ae35-115">例</span><span class="sxs-lookup"><span data-stu-id="5ae35-115">EXAMPLES</span></span>

### <span data-ttu-id="5ae35-116">例 1: コンピューター上のプロセスにデバッガーをアタッチする</span><span class="sxs-lookup"><span data-stu-id="5ae35-116">Example 1: Attach a debugger to a process on the computer</span></span>

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

<span data-ttu-id="5ae35-117">このコマンドは、コンピューターの PowerShell プロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-117">This command attaches a debugger to the PowerShell process on the computer.</span></span>

### <span data-ttu-id="5ae35-118">例 2: 指定した文字列で始まるすべてのプロセスにデバッガーをアタッチする</span><span class="sxs-lookup"><span data-stu-id="5ae35-118">Example 2: Attach a debugger to all processes that begin with the specified string</span></span>

```
PS C:\> Debug-Process -Name "SQL*"
```

<span data-ttu-id="5ae35-119">このコマンドは、名前が SQL で始まるすべてのプロセスにデバッガーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="5ae35-119">This command attaches a debugger to all processes that have names that begin with SQL.</span></span>

### <span data-ttu-id="5ae35-120">例 3: デバッガーを複数のプロセスにアタッチする</span><span class="sxs-lookup"><span data-stu-id="5ae35-120">Example 3: Attach a debugger to multiple processes</span></span>

```
PS C:\> Debug-Process "Winlogon", "Explorer", "Outlook"
```

<span data-ttu-id="5ae35-121">このコマンドは、Winlogon、Explorer、Outlook の各プロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-121">This command attaches a debugger to the Winlogon, Explorer, and Outlook processes.</span></span>

### <span data-ttu-id="5ae35-122">例 4: デバッガーを複数のプロセス Id にアタッチする</span><span class="sxs-lookup"><span data-stu-id="5ae35-122">Example 4: Attach a debugger to multiple process IDs</span></span>

```
PS C:\> Debug-Process -Id 1132, 2028
```

<span data-ttu-id="5ae35-123">このコマンドは、プロセス ID 1132 および 2028 のプロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-123">This command attaches a debugger to the processes that have process IDs 1132 and 2028.</span></span>

### <span data-ttu-id="5ae35-124">例 5: Get-Process を使用してプロセスを取得し、デバッガーをアタッチする</span><span class="sxs-lookup"><span data-stu-id="5ae35-124">Example 5: Use Get-Process to get a process then attach a debugger to it</span></span>

```
PS C:\> Get-Process "Windows PowerShell" | Debug-Process
```

<span data-ttu-id="5ae35-125">このコマンドは、コンピューターの PowerShell プロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-125">This command attaches a debugger to the PowerShell processes on the computer.</span></span>
<span data-ttu-id="5ae35-126">このコマンドは、 **Get process** コマンドレットを使用してコンピューター上の PowerShell プロセスを取得し、パイプライン演算子 (|) を使用してプロセスを **デバッグプロセス** コマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-126">It uses the **Get-Process** cmdlet to get the PowerShell processes on the computer, and it uses a pipeline operator (|) to send the processes to the **Debug-Process** cmdlet.</span></span>

<span data-ttu-id="5ae35-127">特定の PowerShell プロセスを指定するには、 **Get process** の ID パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-127">To specify a particular PowerShell process, use the ID parameter of **Get-Process**.</span></span>

### <span data-ttu-id="5ae35-128">例 6: ローカルコンピューター上の現在のプロセスにデバッガーをアタッチする</span><span class="sxs-lookup"><span data-stu-id="5ae35-128">Example 6: Attach a debugger to a current process on the local computer</span></span>

```
PS C:\> $PID | Debug-Process
```

<span data-ttu-id="5ae35-129">このコマンドは、コンピューターの現在の PowerShell プロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-129">This command attaches a debugger to the current PowerShell processes on the computer.</span></span>

<span data-ttu-id="5ae35-130">このコマンドは、現在の PowerShell プロセスのプロセス ID を含む $PID 自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-130">The command uses the $PID automatic variable, which contains the process ID of the current PowerShell process.</span></span>
<span data-ttu-id="5ae35-131">次に、パイプライン演算子 (|) を使用してプロセス ID を **デバッグプロセス** のコマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-131">Then, it uses a pipeline operator (|) to send the process ID to the **Debug-Process** cmdlet.</span></span>

<span data-ttu-id="5ae35-132">$PID 自動変数の詳細については、「about_Automatic_Variables」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ae35-132">For more information about the $PID automatic variable, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="5ae35-133">例 7: InputObject パラメーターを使用するプロセスにデバッガーをアタッチする</span><span class="sxs-lookup"><span data-stu-id="5ae35-133">Example 7: Attach a debugger to a process that uses the InputObject parameter</span></span>

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

<span data-ttu-id="5ae35-134">このコマンドは、ローカル コンピューターの PowerShell プロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-134">This command attaches a debugger to the PowerShell processes on the local computer.</span></span>

<span data-ttu-id="5ae35-135">最初のコマンドは、 **Get Process** コマンドレットを使用して、コンピューター上の PowerShell プロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-135">The first command uses the **Get-Process** cmdlet to get the PowerShell processes on the computer.</span></span>
<span data-ttu-id="5ae35-136">これにより、結果として得られるプロセスオブジェクトが $P という名前の変数に保存されます。</span><span class="sxs-lookup"><span data-stu-id="5ae35-136">It saves the resulting process object in the variable named $P.</span></span>

<span data-ttu-id="5ae35-137">2番目のコマンドは、 **Debug process** コマンドレットの *InputObject* パラメーターを使用して、$P 変数にプロセスオブジェクトを送信します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-137">The second command uses the *InputObject* parameter of the **Debug-Process** cmdlet to submit the process object in the $P variable.</span></span>

## <span data-ttu-id="5ae35-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5ae35-138">PARAMETERS</span></span>

### <span data-ttu-id="5ae35-139">-Id</span><span class="sxs-lookup"><span data-stu-id="5ae35-139">-Id</span></span>

<span data-ttu-id="5ae35-140">デバッグするプロセスのプロセス ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-140">Specifies the process IDs of the processes to be debugged.</span></span>
<span data-ttu-id="5ae35-141">*Id* パラメーター名は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5ae35-141">The *Id* parameter name is optional.</span></span>

<span data-ttu-id="5ae35-142">プロセスのプロセス ID を検索するには、「」と入力 `Get-Process` します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-142">To find the process ID of a process, type `Get-Process`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases: PID, ProcessId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5ae35-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5ae35-143">-InputObject</span></span>

<span data-ttu-id="5ae35-144">デバッグするプロセスを表すプロセス オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-144">Specifies the process objects that represent processes to be debugged.</span></span>
<span data-ttu-id="5ae35-145">プロセスオブジェクトを含む変数、または Get-Process コマンドレットなどのプロセスオブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-145">Enter a variable that contains the process objects or a command that gets the process objects, such as the Get-Process cmdlet.</span></span>
<span data-ttu-id="5ae35-146">パイプを使用してプロセスオブジェクトをこのコマンドレットに送ることもできます。</span><span class="sxs-lookup"><span data-stu-id="5ae35-146">You can also pipe process objects to this cmdlet.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5ae35-147">-Name</span><span class="sxs-lookup"><span data-stu-id="5ae35-147">-Name</span></span>

<span data-ttu-id="5ae35-148">デバッグするプロセスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-148">Specifies the names of the processes to be debugged.</span></span>
<span data-ttu-id="5ae35-149">同じ名前のプロセスが複数ある場合、このコマンドレットは、その名前を持つすべてのプロセスにデバッガーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="5ae35-149">If there is more than one process with the same name, this cmdlet attaches a debugger to all processes with that name.</span></span>
<span data-ttu-id="5ae35-150">*Name* パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5ae35-150">The *Name* parameter is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5ae35-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5ae35-151">-Confirm</span></span>

<span data-ttu-id="5ae35-152">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ae35-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5ae35-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5ae35-153">-WhatIf</span></span>

<span data-ttu-id="5ae35-154">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="5ae35-155">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="5ae35-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5ae35-156">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5ae35-156">CommonParameters</span></span>

<span data-ttu-id="5ae35-157">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5ae35-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5ae35-158">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ae35-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5ae35-159">入力</span><span class="sxs-lookup"><span data-stu-id="5ae35-159">INPUTS</span></span>

### <span data-ttu-id="5ae35-160">System.string, System.string, System.string, System.string,</span><span class="sxs-lookup"><span data-stu-id="5ae35-160">System.Int32, System.Diagnostics.Process, System.String</span></span>

<span data-ttu-id="5ae35-161">パイプを使用して、プロセス ID (Int32)、プロセスオブジェクト (システム診断プロセス)、またはプロセス名 (文字列) をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-161">You can pipe a process ID (Int32), a process object (System.Diagnostics.Process), or a process name (String) to this cmdlet.</span></span>

## <span data-ttu-id="5ae35-162">出力</span><span class="sxs-lookup"><span data-stu-id="5ae35-162">OUTPUTS</span></span>

### <span data-ttu-id="5ae35-163">なし</span><span class="sxs-lookup"><span data-stu-id="5ae35-163">None</span></span>

<span data-ttu-id="5ae35-164">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="5ae35-164">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5ae35-165">注</span><span class="sxs-lookup"><span data-stu-id="5ae35-165">NOTES</span></span>

* <span data-ttu-id="5ae35-166">このコマンドレットは、Windows Management Instrumentation (WMI) Win32_Process クラスの AttachDebugger メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ae35-166">This cmdlet uses the AttachDebugger method of the Windows Management Instrumentation (WMI) Win32_Process class.</span></span> <span data-ttu-id="5ae35-167">このメソッドの詳細については、MSDN ライブラリの「 [Attachdebugger メソッド](https://go.microsoft.com/fwlink/?LinkId=143640) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ae35-167">For more information about this method, see [AttachDebugger method](https://go.microsoft.com/fwlink/?LinkId=143640) in the MSDN library.</span></span>

## <span data-ttu-id="5ae35-168">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5ae35-168">RELATED LINKS</span></span>

[<span data-ttu-id="5ae35-169">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="5ae35-169">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="5ae35-170">Get-Process</span><span class="sxs-lookup"><span data-stu-id="5ae35-170">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="5ae35-171">Start-Process</span><span class="sxs-lookup"><span data-stu-id="5ae35-171">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="5ae35-172">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="5ae35-172">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="5ae35-173">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="5ae35-173">Wait-Process</span></span>](Wait-Process.md)

