---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: 660d2b4845df8091ff8b69b28c4e7695af557122
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602773"
---
# <span data-ttu-id="9f061-102">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="9f061-102">Debug-Process</span></span>

## <span data-ttu-id="9f061-103">概要</span><span class="sxs-lookup"><span data-stu-id="9f061-103">SYNOPSIS</span></span>
<span data-ttu-id="9f061-104">ローカル コンピューター上で実行中の 1 つ以上のプロセスをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="9f061-104">Debugs one or more processes running on the local computer.</span></span>

## <span data-ttu-id="9f061-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9f061-105">SYNTAX</span></span>

### <span data-ttu-id="9f061-106">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="9f061-106">Name (Default)</span></span>

```
Debug-Process [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9f061-107">Id</span><span class="sxs-lookup"><span data-stu-id="9f061-107">Id</span></span>

```
Debug-Process [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9f061-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="9f061-108">InputObject</span></span>

```
Debug-Process -InputObject <Process[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9f061-109">Description</span><span class="sxs-lookup"><span data-stu-id="9f061-109">DESCRIPTION</span></span>

<span data-ttu-id="9f061-110">`Debug-Process`コマンドレットは、ローカルコンピューター上で実行中の1つ以上のプロセスにデバッガーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="9f061-110">The `Debug-Process` cmdlet attaches a debugger to one or more running processes on a local computer.</span></span>
<span data-ttu-id="9f061-111">プロセスは、プロセス名またはプロセス ID (PID) で指定することも、パイプを使用してこのコマンドレットに処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="9f061-111">You can specify the processes by their process name or process ID (PID), or you can pipe process objects to this cmdlet.</span></span>

<span data-ttu-id="9f061-112">このコマンドレットは、プロセスに対して現在登録されているデバッガーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="9f061-112">This cmdlet attaches the debugger that is currently registered for the process.</span></span> <span data-ttu-id="9f061-113">このコマンドレットを使用する前に、デバッガーがダウンロードされていて適切に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9f061-113">Before using this cmdlet, verify that a debugger is downloaded and correctly configured.</span></span>

## <span data-ttu-id="9f061-114">例</span><span class="sxs-lookup"><span data-stu-id="9f061-114">EXAMPLES</span></span>

### <span data-ttu-id="9f061-115">例 1: コンピューター上のプロセスにデバッガーをアタッチする</span><span class="sxs-lookup"><span data-stu-id="9f061-115">Example 1: Attach a debugger to a process on the computer</span></span>

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

<span data-ttu-id="9f061-116">このコマンドは、コンピューターの PowerShell プロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="9f061-116">This command attaches a debugger to the PowerShell process on the computer.</span></span>

### <span data-ttu-id="9f061-117">例 2: 指定した文字列で始まるすべてのプロセスにデバッガーをアタッチする</span><span class="sxs-lookup"><span data-stu-id="9f061-117">Example 2: Attach a debugger to all processes that begin with the specified string</span></span>

```
PS C:\> Debug-Process -Name "SQL*"
```

<span data-ttu-id="9f061-118">このコマンドは、名前が SQL で始まるすべてのプロセスにデバッガーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="9f061-118">This command attaches a debugger to all processes that have names that begin with SQL.</span></span>

### <span data-ttu-id="9f061-119">例 3: デバッガーを複数のプロセスにアタッチする</span><span class="sxs-lookup"><span data-stu-id="9f061-119">Example 3: Attach a debugger to multiple processes</span></span>

```
PS C:\> Debug-Process "Winlogon", "Explorer", "Outlook"
```

<span data-ttu-id="9f061-120">このコマンドは、Winlogon、Explorer、Outlook の各プロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="9f061-120">This command attaches a debugger to the Winlogon, Explorer, and Outlook processes.</span></span>

### <span data-ttu-id="9f061-121">例 4: デバッガーを複数のプロセス Id にアタッチする</span><span class="sxs-lookup"><span data-stu-id="9f061-121">Example 4: Attach a debugger to multiple process IDs</span></span>

```
PS C:\> Debug-Process -Id 1132, 2028
```

<span data-ttu-id="9f061-122">このコマンドは、プロセス ID 1132 および 2028 のプロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="9f061-122">This command attaches a debugger to the processes that have process IDs 1132 and 2028.</span></span>

### <span data-ttu-id="9f061-123">例 5: Get-Process を使用してプロセスを取得し、デバッガーをアタッチする</span><span class="sxs-lookup"><span data-stu-id="9f061-123">Example 5: Use Get-Process to get a process then attach a debugger to it</span></span>

```
PS C:\> Get-Process "Windows PowerShell" | Debug-Process
```

<span data-ttu-id="9f061-124">このコマンドは、コンピューターの PowerShell プロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="9f061-124">This command attaches a debugger to the PowerShell processes on the computer.</span></span> <span data-ttu-id="9f061-125">コマンドレットを使用して `Get-Process` コンピューター上の PowerShell プロセスを取得し、パイプライン演算子 () を使用して `|` プロセスをコマンドレットに送信し `Debug-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="9f061-125">It uses the `Get-Process` cmdlet to get the PowerShell processes on the computer, and it uses a pipeline operator (`|`) to send the processes to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="9f061-126">特定の PowerShell プロセスを指定するには、の ID パラメーターを使用し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="9f061-126">To specify a particular PowerShell process, use the ID parameter of `Get-Process`.</span></span>

### <span data-ttu-id="9f061-127">例 6: ローカルコンピューター上の現在のプロセスにデバッガーをアタッチする</span><span class="sxs-lookup"><span data-stu-id="9f061-127">Example 6: Attach a debugger to a current process on the local computer</span></span>

```
PS C:\> $PID | Debug-Process
```

<span data-ttu-id="9f061-128">このコマンドは、コンピューターの現在の PowerShell プロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="9f061-128">This command attaches a debugger to the current PowerShell processes on the computer.</span></span>

<span data-ttu-id="9f061-129">このコマンドは、 `$PID` 現在の PowerShell プロセスのプロセス ID を含む自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="9f061-129">The command uses the `$PID` automatic variable, which contains the process ID of the current PowerShell process.</span></span> <span data-ttu-id="9f061-130">次に、パイプライン演算子 () を使用して、 `|` プロセス ID をコマンドレットに送信し `Debug-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="9f061-130">Then, it uses a pipeline operator (`|`) to send the process ID to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="9f061-131">自動変数の詳細については `$PID` 、「about_Automatic_Variables」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f061-131">For more information about the `$PID` automatic variable, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="9f061-132">例 7: InputObject パラメーターを使用するプロセスにデバッガーをアタッチする</span><span class="sxs-lookup"><span data-stu-id="9f061-132">Example 7: Attach a debugger to a process that uses the InputObject parameter</span></span>

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

<span data-ttu-id="9f061-133">このコマンドは、ローカル コンピューターの PowerShell プロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="9f061-133">This command attaches a debugger to the PowerShell processes on the local computer.</span></span>

<span data-ttu-id="9f061-134">最初のコマンドは、 `Get-Process` コマンドレットを使用して、コンピューター上の PowerShell プロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9f061-134">The first command uses the `Get-Process` cmdlet to get the PowerShell processes on the computer.</span></span> <span data-ttu-id="9f061-135">結果として得られるプロセスオブジェクトをという名前の変数に保存し `$P` ます。</span><span class="sxs-lookup"><span data-stu-id="9f061-135">It saves the resulting process object in the variable named `$P`.</span></span>

<span data-ttu-id="9f061-136">2番目のコマンドは、コマンドレットの **InputObject** パラメーターを使用して `Debug-Process` 、変数内のプロセスオブジェクトを送信し `$P` ます。</span><span class="sxs-lookup"><span data-stu-id="9f061-136">The second command uses the **InputObject** parameter of the `Debug-Process` cmdlet to submit the process object in the `$P` variable.</span></span>

## <span data-ttu-id="9f061-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9f061-137">PARAMETERS</span></span>

### <span data-ttu-id="9f061-138">-Id</span><span class="sxs-lookup"><span data-stu-id="9f061-138">-Id</span></span>

<span data-ttu-id="9f061-139">デバッグするプロセスのプロセス ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="9f061-139">Specifies the process IDs of the processes to be debugged.</span></span> <span data-ttu-id="9f061-140">**Id** パラメーター名は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9f061-140">The **Id** parameter name is optional.</span></span>

<span data-ttu-id="9f061-141">プロセスのプロセス ID を検索するには、「」と入力 `Get-Process` します。</span><span class="sxs-lookup"><span data-stu-id="9f061-141">To find the process ID of a process, type `Get-Process`.</span></span>

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

### <span data-ttu-id="9f061-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9f061-142">-InputObject</span></span>

<span data-ttu-id="9f061-143">デバッグするプロセスを表すプロセス オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f061-143">Specifies the process objects that represent processes to be debugged.</span></span> <span data-ttu-id="9f061-144">プロセスオブジェクトを含む変数、または、コマンドレットなどのプロセスオブジェクトを取得するコマンドを入力し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="9f061-144">Enter a variable that contains the process objects or a command that gets the process objects, such as the `Get-Process` cmdlet.</span></span> <span data-ttu-id="9f061-145">パイプを使用してプロセスオブジェクトをこのコマンドレットに送ることもできます。</span><span class="sxs-lookup"><span data-stu-id="9f061-145">You can also pipe process objects to this cmdlet.</span></span>

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

### <span data-ttu-id="9f061-146">-Name</span><span class="sxs-lookup"><span data-stu-id="9f061-146">-Name</span></span>

<span data-ttu-id="9f061-147">デバッグするプロセスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9f061-147">Specifies the names of the processes to be debugged.</span></span> <span data-ttu-id="9f061-148">同じ名前のプロセスが複数ある場合、このコマンドレットは、その名前を持つすべてのプロセスにデバッガーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="9f061-148">If there is more than one process with the same name, this cmdlet attaches a debugger to all processes with that name.</span></span> <span data-ttu-id="9f061-149">**Name** パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9f061-149">The **Name** parameter is optional.</span></span>

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

### <span data-ttu-id="9f061-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9f061-150">-Confirm</span></span>

<span data-ttu-id="9f061-151">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f061-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9f061-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9f061-152">-WhatIf</span></span>

<span data-ttu-id="9f061-153">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="9f061-153">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="9f061-154">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="9f061-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9f061-155">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9f061-155">CommonParameters</span></span>

<span data-ttu-id="9f061-156">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="9f061-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9f061-157">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f061-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9f061-158">入力</span><span class="sxs-lookup"><span data-stu-id="9f061-158">INPUTS</span></span>

### <span data-ttu-id="9f061-159">System.string, System.string, System.string, System.string,</span><span class="sxs-lookup"><span data-stu-id="9f061-159">System.Int32, System.Diagnostics.Process, System.String</span></span>

<span data-ttu-id="9f061-160">パイプを使用して、プロセス ID (Int32)、プロセスオブジェクト (システム診断プロセス)、またはプロセス名 (文字列) をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="9f061-160">You can pipe a process ID (Int32), a process object (System.Diagnostics.Process), or a process name (String) to this cmdlet.</span></span>

## <span data-ttu-id="9f061-161">出力</span><span class="sxs-lookup"><span data-stu-id="9f061-161">OUTPUTS</span></span>

### <span data-ttu-id="9f061-162">なし</span><span class="sxs-lookup"><span data-stu-id="9f061-162">None</span></span>

<span data-ttu-id="9f061-163">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="9f061-163">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9f061-164">注</span><span class="sxs-lookup"><span data-stu-id="9f061-164">NOTES</span></span>

<span data-ttu-id="9f061-165">このコマンドレットは、Windows Management Instrumentation (WMI) Win32_Process クラスの AttachDebugger メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9f061-165">This cmdlet uses the AttachDebugger method of the Windows Management Instrumentation (WMI) Win32_Process class.</span></span> <span data-ttu-id="9f061-166">このメソッドの詳細については、MSDN ライブラリの「 [Attachdebugger メソッド](https://go.microsoft.com/fwlink/?LinkId=143640) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f061-166">For more information about this method, see [AttachDebugger method](https://go.microsoft.com/fwlink/?LinkId=143640) in the MSDN library.</span></span>

## <span data-ttu-id="9f061-167">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9f061-167">RELATED LINKS</span></span>

[<span data-ttu-id="9f061-168">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="9f061-168">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="9f061-169">Get-Process</span><span class="sxs-lookup"><span data-stu-id="9f061-169">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="9f061-170">Start-Process</span><span class="sxs-lookup"><span data-stu-id="9f061-170">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="9f061-171">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="9f061-171">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="9f061-172">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="9f061-172">Wait-Process</span></span>](Wait-Process.md)
