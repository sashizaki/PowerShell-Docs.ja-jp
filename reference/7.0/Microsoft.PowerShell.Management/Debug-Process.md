---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: 7a439cc3f15b319f5f56709260035ffa8fc03c12
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391376"
---
# <span data-ttu-id="60605-103">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="60605-103">Debug-Process</span></span>

## <span data-ttu-id="60605-104">概要</span><span class="sxs-lookup"><span data-stu-id="60605-104">SYNOPSIS</span></span>
<span data-ttu-id="60605-105">ローカル コンピューター上で実行中の 1 つ以上のプロセスをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="60605-105">Debugs one or more processes running on the local computer.</span></span>

## <span data-ttu-id="60605-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="60605-106">SYNTAX</span></span>

### <span data-ttu-id="60605-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="60605-107">Name (Default)</span></span>

```
Debug-Process [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="60605-108">Id</span><span class="sxs-lookup"><span data-stu-id="60605-108">Id</span></span>

```
Debug-Process [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="60605-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="60605-109">InputObject</span></span>

```
Debug-Process -InputObject <Process[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="60605-110">Description</span><span class="sxs-lookup"><span data-stu-id="60605-110">DESCRIPTION</span></span>

<span data-ttu-id="60605-111">`Debug-Process`コマンドレットは、ローカルコンピューター上で実行中の1つ以上のプロセスにデバッガーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="60605-111">The `Debug-Process` cmdlet attaches a debugger to one or more running processes on a local computer.</span></span>
<span data-ttu-id="60605-112">プロセスは、プロセス名またはプロセス ID (PID) で指定することも、パイプを使用してこのコマンドレットに処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="60605-112">You can specify the processes by their process name or process ID (PID), or you can pipe process objects to this cmdlet.</span></span>

<span data-ttu-id="60605-113">このコマンドレットは、プロセスに対して現在登録されているデバッガーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="60605-113">This cmdlet attaches the debugger that is currently registered for the process.</span></span> <span data-ttu-id="60605-114">このコマンドレットを使用する前に、デバッガーがダウンロードされていて適切に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="60605-114">Before using this cmdlet, verify that a debugger is downloaded and correctly configured.</span></span>

## <span data-ttu-id="60605-115">例</span><span class="sxs-lookup"><span data-stu-id="60605-115">EXAMPLES</span></span>

### <span data-ttu-id="60605-116">例 1: コンピューター上のプロセスにデバッガーをアタッチする</span><span class="sxs-lookup"><span data-stu-id="60605-116">Example 1: Attach a debugger to a process on the computer</span></span>

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

<span data-ttu-id="60605-117">このコマンドは、コンピューターの PowerShell プロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="60605-117">This command attaches a debugger to the PowerShell process on the computer.</span></span>

### <span data-ttu-id="60605-118">例 2: 指定した文字列で始まるすべてのプロセスにデバッガーをアタッチする</span><span class="sxs-lookup"><span data-stu-id="60605-118">Example 2: Attach a debugger to all processes that begin with the specified string</span></span>

```
PS C:\> Debug-Process -Name "SQL*"
```

<span data-ttu-id="60605-119">このコマンドは、名前が SQL で始まるすべてのプロセスにデバッガーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="60605-119">This command attaches a debugger to all processes that have names that begin with SQL.</span></span>

### <span data-ttu-id="60605-120">例 3: デバッガーを複数のプロセスにアタッチする</span><span class="sxs-lookup"><span data-stu-id="60605-120">Example 3: Attach a debugger to multiple processes</span></span>

```
PS C:\> Debug-Process "Winlogon", "Explorer", "Outlook"
```

<span data-ttu-id="60605-121">このコマンドは、Winlogon、Explorer、Outlook の各プロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="60605-121">This command attaches a debugger to the Winlogon, Explorer, and Outlook processes.</span></span>

### <span data-ttu-id="60605-122">例 4: デバッガーを複数のプロセス Id にアタッチする</span><span class="sxs-lookup"><span data-stu-id="60605-122">Example 4: Attach a debugger to multiple process IDs</span></span>

```
PS C:\> Debug-Process -Id 1132, 2028
```

<span data-ttu-id="60605-123">このコマンドは、プロセス ID 1132 および 2028 のプロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="60605-123">This command attaches a debugger to the processes that have process IDs 1132 and 2028.</span></span>

### <span data-ttu-id="60605-124">例 5: Get-Process を使用してプロセスを取得し、デバッガーをアタッチする</span><span class="sxs-lookup"><span data-stu-id="60605-124">Example 5: Use Get-Process to get a process then attach a debugger to it</span></span>

```
PS C:\> Get-Process "Windows PowerShell" | Debug-Process
```

<span data-ttu-id="60605-125">このコマンドは、コンピューターの PowerShell プロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="60605-125">This command attaches a debugger to the PowerShell processes on the computer.</span></span> <span data-ttu-id="60605-126">コマンドレットを使用して `Get-Process` コンピューター上の PowerShell プロセスを取得し、パイプライン演算子 () を使用して `|` プロセスをコマンドレットに送信し `Debug-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="60605-126">It uses the `Get-Process` cmdlet to get the PowerShell processes on the computer, and it uses a pipeline operator (`|`) to send the processes to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="60605-127">特定の PowerShell プロセスを指定するには、の ID パラメーターを使用し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="60605-127">To specify a particular PowerShell process, use the ID parameter of `Get-Process`.</span></span>

### <span data-ttu-id="60605-128">例 6: ローカルコンピューター上の現在のプロセスにデバッガーをアタッチする</span><span class="sxs-lookup"><span data-stu-id="60605-128">Example 6: Attach a debugger to a current process on the local computer</span></span>

```
PS C:\> $PID | Debug-Process
```

<span data-ttu-id="60605-129">このコマンドは、コンピューターの現在の PowerShell プロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="60605-129">This command attaches a debugger to the current PowerShell processes on the computer.</span></span>

<span data-ttu-id="60605-130">このコマンドは、 `$PID` 現在の PowerShell プロセスのプロセス ID を含む自動変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="60605-130">The command uses the `$PID` automatic variable, which contains the process ID of the current PowerShell process.</span></span> <span data-ttu-id="60605-131">次に、パイプライン演算子 () を使用して、 `|` プロセス ID をコマンドレットに送信し `Debug-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="60605-131">Then, it uses a pipeline operator (`|`) to send the process ID to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="60605-132">自動変数の詳細については `$PID` 、「about_Automatic_Variables」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60605-132">For more information about the `$PID` automatic variable, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="60605-133">例 7: InputObject パラメーターを使用するプロセスにデバッガーをアタッチする</span><span class="sxs-lookup"><span data-stu-id="60605-133">Example 7: Attach a debugger to a process that uses the InputObject parameter</span></span>

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

<span data-ttu-id="60605-134">このコマンドは、ローカル コンピューターの PowerShell プロセスにデバッガーを結合します。</span><span class="sxs-lookup"><span data-stu-id="60605-134">This command attaches a debugger to the PowerShell processes on the local computer.</span></span>

<span data-ttu-id="60605-135">最初のコマンドは、 `Get-Process` コマンドレットを使用して、コンピューター上の PowerShell プロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="60605-135">The first command uses the `Get-Process` cmdlet to get the PowerShell processes on the computer.</span></span> <span data-ttu-id="60605-136">結果として得られるプロセスオブジェクトをという名前の変数に保存し `$P` ます。</span><span class="sxs-lookup"><span data-stu-id="60605-136">It saves the resulting process object in the variable named `$P`.</span></span>

<span data-ttu-id="60605-137">2番目のコマンドは、コマンドレットの **InputObject** パラメーターを使用して `Debug-Process` 、変数内のプロセスオブジェクトを送信し `$P` ます。</span><span class="sxs-lookup"><span data-stu-id="60605-137">The second command uses the **InputObject** parameter of the `Debug-Process` cmdlet to submit the process object in the `$P` variable.</span></span>

## <span data-ttu-id="60605-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="60605-138">PARAMETERS</span></span>

### <span data-ttu-id="60605-139">-Id</span><span class="sxs-lookup"><span data-stu-id="60605-139">-Id</span></span>

<span data-ttu-id="60605-140">デバッグするプロセスのプロセス ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="60605-140">Specifies the process IDs of the processes to be debugged.</span></span> <span data-ttu-id="60605-141">**Id** パラメーター名は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="60605-141">The **Id** parameter name is optional.</span></span>

<span data-ttu-id="60605-142">プロセスのプロセス ID を検索するには、「」と入力 `Get-Process` します。</span><span class="sxs-lookup"><span data-stu-id="60605-142">To find the process ID of a process, type `Get-Process`.</span></span>

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

### <span data-ttu-id="60605-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="60605-143">-InputObject</span></span>

<span data-ttu-id="60605-144">デバッグするプロセスを表すプロセス オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="60605-144">Specifies the process objects that represent processes to be debugged.</span></span> <span data-ttu-id="60605-145">プロセスオブジェクトを含む変数、または、コマンドレットなどのプロセスオブジェクトを取得するコマンドを入力し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="60605-145">Enter a variable that contains the process objects or a command that gets the process objects, such as the `Get-Process` cmdlet.</span></span> <span data-ttu-id="60605-146">パイプを使用してプロセスオブジェクトをこのコマンドレットに送ることもできます。</span><span class="sxs-lookup"><span data-stu-id="60605-146">You can also pipe process objects to this cmdlet.</span></span>

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

### <span data-ttu-id="60605-147">-Name</span><span class="sxs-lookup"><span data-stu-id="60605-147">-Name</span></span>

<span data-ttu-id="60605-148">デバッグするプロセスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="60605-148">Specifies the names of the processes to be debugged.</span></span> <span data-ttu-id="60605-149">同じ名前のプロセスが複数ある場合、このコマンドレットは、その名前を持つすべてのプロセスにデバッガーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="60605-149">If there is more than one process with the same name, this cmdlet attaches a debugger to all processes with that name.</span></span> <span data-ttu-id="60605-150">**Name** パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="60605-150">The **Name** parameter is optional.</span></span>

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

### <span data-ttu-id="60605-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="60605-151">-Confirm</span></span>

<span data-ttu-id="60605-152">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60605-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="60605-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="60605-153">-WhatIf</span></span>

<span data-ttu-id="60605-154">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="60605-154">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="60605-155">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="60605-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="60605-156">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="60605-156">CommonParameters</span></span>

<span data-ttu-id="60605-157">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="60605-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="60605-158">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60605-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="60605-159">入力</span><span class="sxs-lookup"><span data-stu-id="60605-159">INPUTS</span></span>

### <span data-ttu-id="60605-160">System.string, System.string, System.string, System.string,</span><span class="sxs-lookup"><span data-stu-id="60605-160">System.Int32, System.Diagnostics.Process, System.String</span></span>

<span data-ttu-id="60605-161">パイプを使用して、プロセス ID (Int32)、プロセスオブジェクト (システム診断プロセス)、またはプロセス名 (文字列) をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="60605-161">You can pipe a process ID (Int32), a process object (System.Diagnostics.Process), or a process name (String) to this cmdlet.</span></span>

## <span data-ttu-id="60605-162">出力</span><span class="sxs-lookup"><span data-stu-id="60605-162">OUTPUTS</span></span>

### <span data-ttu-id="60605-163">なし</span><span class="sxs-lookup"><span data-stu-id="60605-163">None</span></span>

<span data-ttu-id="60605-164">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="60605-164">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="60605-165">注</span><span class="sxs-lookup"><span data-stu-id="60605-165">NOTES</span></span>

<span data-ttu-id="60605-166">このコマンドレットは、Windows Management Instrumentation (WMI) Win32_Process クラスの AttachDebugger メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="60605-166">This cmdlet uses the AttachDebugger method of the Windows Management Instrumentation (WMI) Win32_Process class.</span></span> <span data-ttu-id="60605-167">このメソッドの詳細については、MSDN ライブラリの「 [Attachdebugger メソッド](https://go.microsoft.com/fwlink/?LinkId=143640) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60605-167">For more information about this method, see [AttachDebugger method](https://go.microsoft.com/fwlink/?LinkId=143640) in the MSDN library.</span></span>

## <span data-ttu-id="60605-168">関連リンク</span><span class="sxs-lookup"><span data-stu-id="60605-168">RELATED LINKS</span></span>

[<span data-ttu-id="60605-169">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="60605-169">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="60605-170">Get-Process</span><span class="sxs-lookup"><span data-stu-id="60605-170">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="60605-171">Start-Process</span><span class="sxs-lookup"><span data-stu-id="60605-171">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="60605-172">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="60605-172">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="60605-173">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="60605-173">Wait-Process</span></span>](Wait-Process.md)
