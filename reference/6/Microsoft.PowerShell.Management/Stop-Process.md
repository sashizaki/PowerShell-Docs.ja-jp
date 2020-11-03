---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-process?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Process
ms.openlocfilehash: a2f340f0119823ddc0876d86fc38e49edc51fe5d
ms.sourcegitcommit: 11abf355ac545531c2b04217a08ebe6be609c0bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "93220000"
---
# <span data-ttu-id="ffe73-103">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="ffe73-103">Stop-Process</span></span>

## <span data-ttu-id="ffe73-104">概要</span><span class="sxs-lookup"><span data-stu-id="ffe73-104">SYNOPSIS</span></span>
<span data-ttu-id="ffe73-105">実行中のプロセスを 1 つ以上停止します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-105">Stops one or more running processes.</span></span>

## <span data-ttu-id="ffe73-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ffe73-106">SYNTAX</span></span>

### <span data-ttu-id="ffe73-107">Id (既定値)</span><span class="sxs-lookup"><span data-stu-id="ffe73-107">Id (Default)</span></span>

```
Stop-Process [-Id] <Int32[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ffe73-108">Name</span><span class="sxs-lookup"><span data-stu-id="ffe73-108">Name</span></span>

```
Stop-Process -Name <String[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ffe73-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="ffe73-109">InputObject</span></span>

```
Stop-Process [-InputObject] <Process[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ffe73-110">Description</span><span class="sxs-lookup"><span data-stu-id="ffe73-110">DESCRIPTION</span></span>

<span data-ttu-id="ffe73-111">**Stop Process** コマンドレットは、実行中の1つ以上のプロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-111">The **Stop-Process** cmdlet stops one or more running processes.</span></span>
<span data-ttu-id="ffe73-112">プロセスは、プロセス名またはプロセス ID (PID) で指定することも、プロセスオブジェクトを **停止プロセス** に渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="ffe73-112">You can specify a process by process name or process ID (PID), or pass a process object to **Stop-Process**.</span></span>
<span data-ttu-id="ffe73-113">**停止プロセス** は、ローカルコンピューター上で実行されているプロセスでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-113">**Stop-Process** works only on processes running on the local computer.</span></span>

<span data-ttu-id="ffe73-114">Windows Vista 以降のバージョンの Windows オペレーティングシステムでは、現在のユーザーが所有していないプロセスを停止するには、[管理者として実行] オプションを使用して PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffe73-114">On Windows Vista and later versions of the Windows operating system, to stop a process that is not owned by the current user, you must start PowerShell by using the Run as administrator option.</span></span>
<span data-ttu-id="ffe73-115">また、 *Confirm* パラメーターを指定しない限り、確認のプロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="ffe73-115">Also, you are not prompted for confirmation unless you specify the *Confirm* parameter.</span></span>

## <span data-ttu-id="ffe73-116">例</span><span class="sxs-lookup"><span data-stu-id="ffe73-116">EXAMPLES</span></span>

### <span data-ttu-id="ffe73-117">例 1: プロセスのすべてのインスタンスを停止する</span><span class="sxs-lookup"><span data-stu-id="ffe73-117">Example 1: Stop all instances of a process</span></span>

```
PS C:\> Stop-Process -Name "notepad"
```

<span data-ttu-id="ffe73-118">このコマンドを実行すると、コンピューター上の Notepad プロセスのインスタンスがすべて停止されます。</span><span class="sxs-lookup"><span data-stu-id="ffe73-118">This command stops all instances of the Notepad process on the computer.</span></span>
<span data-ttu-id="ffe73-119">メモ帳の各インスタンスは、独自のプロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="ffe73-119">Each instance of Notepad runs in its own process.</span></span>
<span data-ttu-id="ffe73-120">*Name* パラメーターを使用してプロセスを指定し、そのすべてが同じ名前を持っています。</span><span class="sxs-lookup"><span data-stu-id="ffe73-120">It uses the *Name* parameter to specify the processes, all of which have the same name.</span></span>
<span data-ttu-id="ffe73-121">*Id* パラメーターを使用して同じプロセスを停止する場合は、メモ帳の各インスタンスのプロセス id を一覧表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffe73-121">If you were to use the *Id* parameter to stop the same processes, you would have to list the process IDs of each instance of Notepad.</span></span>

### <span data-ttu-id="ffe73-122">例 2: プロセスの特定のインスタンスを停止する</span><span class="sxs-lookup"><span data-stu-id="ffe73-122">Example 2: Stop a specific instance of a process</span></span>

```
PS C:\> Stop-Process -Id 3952 -Confirm -PassThru
Confirm
Are you sure you want to perform this action?
Performing operation "Stop-Process" on Target "notepad (3952)".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):y
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
41       2      996       3212    31            3952 notepad
```

<span data-ttu-id="ffe73-123">このコマンドを実行すると、Notepad プロセスの特定のインスタンスが停止されます。</span><span class="sxs-lookup"><span data-stu-id="ffe73-123">This command stops a particular instance of the Notepad process.</span></span>
<span data-ttu-id="ffe73-124">プロセス ID 3952 を使用してプロセスを識別しています。</span><span class="sxs-lookup"><span data-stu-id="ffe73-124">It uses the process ID, 3952, to identify the process.</span></span>
<span data-ttu-id="ffe73-125">*Confirm* パラメーターは、プロセスを停止する前にプロンプトを表示するように PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-125">The *Confirm* parameter directs PowerShell to prompt you before it stops the process.</span></span>
<span data-ttu-id="ffe73-126">このプロンプトには ID に加えてプロセス名が含まれているため、これがベストプラクティスです。</span><span class="sxs-lookup"><span data-stu-id="ffe73-126">Because the prompt includes the process namein addition to its ID, this is best practice.</span></span>
<span data-ttu-id="ffe73-127">*PassThru* パラメーターは、プロセスオブジェクトを表示用のフォーマッタに渡します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-127">The *PassThru* parameter passes the process object to the formatter for display.</span></span>
<span data-ttu-id="ffe73-128">このパラメーターを指定しないと、 **プロセスの停止** コマンドの後に表示されません。</span><span class="sxs-lookup"><span data-stu-id="ffe73-128">Without this parameter, there would be no display after a **Stop-Process** command.</span></span>

### <span data-ttu-id="ffe73-129">例 3: プロセスを停止し、停止したことを検出する</span><span class="sxs-lookup"><span data-stu-id="ffe73-129">Example 3: Stop a process and detect that it has stopped</span></span>

```
PS C:\> calc
PS C:\> $p = Get-Process -Name "calc"
PS C:\> Stop-Process -InputObject $p
PS C:\> Get-Process | Where-Object {$_.HasExited}
```

<span data-ttu-id="ffe73-130">この一連のコマンドは、Calc プロセスを開始および停止し、停止したプロセスを検出します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-130">This series of commands starts and stops the Calc process, and then detects processes that have stopped.</span></span>

<span data-ttu-id="ffe73-131">最初のコマンドは、電卓のインスタンスを起動します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-131">The first command starts an instance of the calculator.</span></span>

<span data-ttu-id="ffe73-132">2番目のコマンドは、[ **取得プロセス** ] を使用して、Calc プロセスを表すオブジェクトを取得し、$p 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-132">The second command uses **Get-Process** gets an object that represents the Calc process, and then stores it in the $p variable.</span></span>

<span data-ttu-id="ffe73-133">3番目のコマンドは、Calc 処理を停止します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-133">The third command stops the Calc process.</span></span>
<span data-ttu-id="ffe73-134">*InputObject* パラメーターを使用して、オブジェクトを **停止プロセス** に渡します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-134">It uses the *InputObject* parameter to pass the object to **Stop-Process**.</span></span>

<span data-ttu-id="ffe73-135">最後のコマンドは、コンピューター上の、以前は実行中で現在は停止しているすべてのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-135">The last command gets all of the processes on the computer that were running but that are now stopped.</span></span>
<span data-ttu-id="ffe73-136">コンピューター上のすべてのプロセスを取得するには、 **Get Process** を使用します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-136">It uses **Get-Process** to get all of the processes on the computer.</span></span>
<span data-ttu-id="ffe73-137">パイプライン演算子 (|) は、Where-Object コマンドレットに結果を渡します。このコマンドレットは、 **Hasexited** $True プロパティの値が指定されているものを選択します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-137">The pipeline operator (|) passes the results to the Where-Object cmdlet, which selects the ones where the value of the **HasExited** property is $True.</span></span>
<span data-ttu-id="ffe73-138">**Hasexited** 、プロセスオブジェクトの1つのプロパティにすぎません。</span><span class="sxs-lookup"><span data-stu-id="ffe73-138">**HasExited** is just one property of process objects.</span></span>
<span data-ttu-id="ffe73-139">すべてのプロパティを検索するには、「」と入力 `Get-Process | Get-Member` します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-139">To find all the properties, type `Get-Process | Get-Member`.</span></span>

### <span data-ttu-id="ffe73-140">例 4: 現在のユーザーが所有していないプロセスを停止する</span><span class="sxs-lookup"><span data-stu-id="ffe73-140">Example 4: Stop a process not owned by the current user</span></span>

```
PS C:\> Get-Process -Name "lsass" | Stop-Process

Stop-Process : Cannot stop process 'lsass (596)' because of the following error: Access is denied
At line:1 char:34
+ Get-Process -Name "lsass" | Stop-Process <<<<

[ADMIN]: PS C:\> Get-Process -Name "lsass" | Stop-Process

Warning!
Are you sure you want to perform this action?
Performing operation 'Stop-Process' on Target 'lsass(596)'
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
[ADMIN]: PS C:\> Get-Process -Name "lsass" | Stop-Process -Force
[ADMIN]: PS C:\>
```

<span data-ttu-id="ffe73-141">これらのコマンドは、 *Force* を使用して、ユーザーが所有していないプロセスを停止した場合の影響を示します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-141">These commands show the effect of using *Force* to stop a process that is not owned by the user.</span></span>

<span data-ttu-id="ffe73-142">最初のコマンドは、 **Get process** を使用して Lsass プロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-142">The first command uses **Get-Process** to get the Lsass process.</span></span>
<span data-ttu-id="ffe73-143">パイプライン演算子は、プロセスを停止 **プロセス** に送信して停止します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-143">A pipeline operator sends the process to **Stop-Process** to stop it.</span></span>
<span data-ttu-id="ffe73-144">サンプル出力に示されているように、最初のコマンドはアクセス拒否メッセージで失敗します。このプロセスは、コンピューターの Administrator グループのメンバーによってのみ停止される可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="ffe73-144">As shown in the sample output, the first command fails with an Access denied message, because this process can be stopped only by a member of the Administrator group on the computer.</span></span>

<span data-ttu-id="ffe73-145">[管理者として実行] オプションを使用して PowerShell を開き、コマンドを繰り返すと、確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffe73-145">When PowerShell is opened by using the Run as administrator option, and the command is repeated, PowerShell prompts you for confirmation.</span></span>

<span data-ttu-id="ffe73-146">2番目のコマンドは、プロンプトを抑制する *Force* を指定します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-146">The second command specifies *Force* to suppress the prompt.</span></span>
<span data-ttu-id="ffe73-147">その結果、プロセスは確認なしで停止されます。</span><span class="sxs-lookup"><span data-stu-id="ffe73-147">As a result, the process is stopped without confirmation.</span></span>

## <span data-ttu-id="ffe73-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ffe73-148">PARAMETERS</span></span>

### <span data-ttu-id="ffe73-149">-Force</span><span class="sxs-lookup"><span data-stu-id="ffe73-149">-Force</span></span>

<span data-ttu-id="ffe73-150">確認メッセージを表示せずに、指定されたプロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-150">Stops the specified processes without prompting for confirmation.</span></span>
<span data-ttu-id="ffe73-151">既定では、現在のユーザーが所有していないプロセスを停止する前に、 **停止処理** によって確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffe73-151">By default, **Stop-Process** prompts for confirmation before stopping any process that is not owned by the current user.</span></span>

<span data-ttu-id="ffe73-152">プロセスの所有者を見つけるには、コマンドレットを使用して、 `Get-CimInstance` プロセスを表す **Win32_Process** オブジェクトを取得し、オブジェクトの **GetOwner** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-152">To find the owner of a process, use the `Get-CimInstance` cmdlet to get a **Win32_Process** object that represents the process, and then use the **GetOwner** method of the object.</span></span>

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

### <span data-ttu-id="ffe73-153">-Id</span><span class="sxs-lookup"><span data-stu-id="ffe73-153">-Id</span></span>

<span data-ttu-id="ffe73-154">停止するプロセスのプロセス Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-154">Specifies the process IDs of the processes to stop.</span></span>
<span data-ttu-id="ffe73-155">複数の ID を指定するには、ID をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="ffe73-155">To specify multiple IDs, use commas to separate the IDs.</span></span>
<span data-ttu-id="ffe73-156">プロセスの PID を検索するには、「」と入力 `Get-Process` します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-156">To find the PID of a process, type `Get-Process`.</span></span>

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

### <span data-ttu-id="ffe73-157">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ffe73-157">-InputObject</span></span>

<span data-ttu-id="ffe73-158">停止するプロセスオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-158">Specifies the process objects to stop.</span></span>
<span data-ttu-id="ffe73-159">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-159">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ffe73-160">-Name</span><span class="sxs-lookup"><span data-stu-id="ffe73-160">-Name</span></span>

<span data-ttu-id="ffe73-161">停止するプロセスのプロセス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-161">Specifies the process names of the processes to stop.</span></span>
<span data-ttu-id="ffe73-162">複数のプロセス名をコンマで区切って入力することも、ワイルドカード文字を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ffe73-162">You can type multiple process names, separated by commas, or use wildcard characters.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="ffe73-163">-PassThru</span><span class="sxs-lookup"><span data-stu-id="ffe73-163">-PassThru</span></span>

<span data-ttu-id="ffe73-164">プロセスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-164">Returns an object that represents the process.</span></span>
<span data-ttu-id="ffe73-165">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="ffe73-165">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="ffe73-166">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ffe73-166">-Confirm</span></span>

<span data-ttu-id="ffe73-167">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffe73-167">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ffe73-168">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ffe73-168">-WhatIf</span></span>

<span data-ttu-id="ffe73-169">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-169">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ffe73-170">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="ffe73-170">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ffe73-171">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ffe73-171">CommonParameters</span></span>

<span data-ttu-id="ffe73-172">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ffe73-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ffe73-173">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffe73-173">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ffe73-174">入力</span><span class="sxs-lookup"><span data-stu-id="ffe73-174">INPUTS</span></span>

### <span data-ttu-id="ffe73-175">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="ffe73-175">System.Diagnostics.Process</span></span>

<span data-ttu-id="ffe73-176">パイプを使用してプロセスオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="ffe73-176">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="ffe73-177">出力</span><span class="sxs-lookup"><span data-stu-id="ffe73-177">OUTPUTS</span></span>

### <span data-ttu-id="ffe73-178">なし、システム。診断プロセス</span><span class="sxs-lookup"><span data-stu-id="ffe73-178">None, System.Diagnostics.Process</span></span>

<span data-ttu-id="ffe73-179">このコマンドレットは、 *PassThru* パラメーターを指定した場合に、停止されたプロセスを表す **system.string オブジェクトを返します。**</span><span class="sxs-lookup"><span data-stu-id="ffe73-179">This cmdlet returns a **System.Diagnostics.Process** object that represents the stopped process, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="ffe73-180">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="ffe73-180">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ffe73-181">注</span><span class="sxs-lookup"><span data-stu-id="ffe73-181">NOTES</span></span>

* <span data-ttu-id="ffe73-182">また、組み込みエイリアスである **kill** と **spps** を使用して、 **停止プロセス** を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="ffe73-182">You can also refer to **Stop-Process** by its built-in aliases, **kill** and **spps**.</span></span> <span data-ttu-id="ffe73-183">詳細については、「about_Aliases」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffe73-183">For more information, see about_Aliases.</span></span>

  <span data-ttu-id="ffe73-184">Windows PowerShell では、Windows Management Instrumentation (WMI) **Win32_Process** オブジェクトのプロパティとメソッドを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ffe73-184">You can also use the properties and methods of the Windows Management Instrumentation (WMI) **Win32_Process** object in Windows PowerShell.</span></span>
<span data-ttu-id="ffe73-185">詳細については、「」および「WMI SDK」を参照してください `Get-CimInstance` 。</span><span class="sxs-lookup"><span data-stu-id="ffe73-185">For more information, see `Get-CimInstance` and the WMI SDK.</span></span>

* <span data-ttu-id="ffe73-186">プロセスを停止すると、プロセスに依存するプロセスやサービスが停止する可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ffe73-186">When stopping processes, realize that stopping a process can stop process and services that depend on the process.</span></span>
<span data-ttu-id="ffe73-187">場合によっては、プロセスを停止したとき、Windows が停止する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ffe73-187">In an extreme case, stopping a process can stop Windows.</span></span>

## <span data-ttu-id="ffe73-188">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ffe73-188">RELATED LINKS</span></span>

[<span data-ttu-id="ffe73-189">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="ffe73-189">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="ffe73-190">Get-Process</span><span class="sxs-lookup"><span data-stu-id="ffe73-190">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="ffe73-191">Start-Process</span><span class="sxs-lookup"><span data-stu-id="ffe73-191">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="ffe73-192">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="ffe73-192">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="ffe73-193">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="ffe73-193">Wait-Process</span></span>](Wait-Process.md)
