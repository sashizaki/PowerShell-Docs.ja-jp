---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-process?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Process
ms.openlocfilehash: 8c9e520f1f19444fd538fabee99a48ec08c69992
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602200"
---
# <span data-ttu-id="9939e-102">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="9939e-102">Stop-Process</span></span>

## <span data-ttu-id="9939e-103">概要</span><span class="sxs-lookup"><span data-stu-id="9939e-103">SYNOPSIS</span></span>
<span data-ttu-id="9939e-104">実行中のプロセスを 1 つ以上停止します。</span><span class="sxs-lookup"><span data-stu-id="9939e-104">Stops one or more running processes.</span></span>

## <span data-ttu-id="9939e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9939e-105">SYNTAX</span></span>

### <span data-ttu-id="9939e-106">Id (既定値)</span><span class="sxs-lookup"><span data-stu-id="9939e-106">Id (Default)</span></span>

```
Stop-Process [-Id] <Int32[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9939e-107">名前</span><span class="sxs-lookup"><span data-stu-id="9939e-107">Name</span></span>

```
Stop-Process -Name <String[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9939e-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="9939e-108">InputObject</span></span>

```
Stop-Process [-InputObject] <Process[]> [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9939e-109">Description</span><span class="sxs-lookup"><span data-stu-id="9939e-109">DESCRIPTION</span></span>

<span data-ttu-id="9939e-110">**Stop Process** コマンドレットは、実行中の1つ以上のプロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="9939e-110">The **Stop-Process** cmdlet stops one or more running processes.</span></span>
<span data-ttu-id="9939e-111">プロセスは、プロセス名またはプロセス ID (PID) で指定することも、プロセスオブジェクトを **停止プロセス** に渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="9939e-111">You can specify a process by process name or process ID (PID), or pass a process object to **Stop-Process**.</span></span>
<span data-ttu-id="9939e-112">**停止プロセス** は、ローカルコンピューター上で実行されているプロセスでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="9939e-112">**Stop-Process** works only on processes running on the local computer.</span></span>

<span data-ttu-id="9939e-113">Windows Vista 以降のバージョンの Windows オペレーティングシステムでは、現在のユーザーが所有していないプロセスを停止するには、[管理者として実行] オプションを使用して PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9939e-113">On Windows Vista and later versions of the Windows operating system, to stop a process that is not owned by the current user, you must start PowerShell by using the Run as administrator option.</span></span>
<span data-ttu-id="9939e-114">また、 *Confirm* パラメーターを指定しない限り、確認のプロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="9939e-114">Also, you are not prompted for confirmation unless you specify the *Confirm* parameter.</span></span>

## <span data-ttu-id="9939e-115">例</span><span class="sxs-lookup"><span data-stu-id="9939e-115">EXAMPLES</span></span>

### <span data-ttu-id="9939e-116">例 1: プロセスのすべてのインスタンスを停止する</span><span class="sxs-lookup"><span data-stu-id="9939e-116">Example 1: Stop all instances of a process</span></span>

```
PS C:\> Stop-Process -Name "notepad"
```

<span data-ttu-id="9939e-117">このコマンドを実行すると、コンピューター上の Notepad プロセスのインスタンスがすべて停止されます。</span><span class="sxs-lookup"><span data-stu-id="9939e-117">This command stops all instances of the Notepad process on the computer.</span></span>
<span data-ttu-id="9939e-118">メモ帳の各インスタンスは、独自のプロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="9939e-118">Each instance of Notepad runs in its own process.</span></span>
<span data-ttu-id="9939e-119">*Name* パラメーターを使用してプロセスを指定し、そのすべてが同じ名前を持っています。</span><span class="sxs-lookup"><span data-stu-id="9939e-119">It uses the *Name* parameter to specify the processes, all of which have the same name.</span></span>
<span data-ttu-id="9939e-120">*Id* パラメーターを使用して同じプロセスを停止する場合は、メモ帳の各インスタンスのプロセス id を一覧表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9939e-120">If you were to use the *Id* parameter to stop the same processes, you would have to list the process IDs of each instance of Notepad.</span></span>

### <span data-ttu-id="9939e-121">例 2: プロセスの特定のインスタンスを停止する</span><span class="sxs-lookup"><span data-stu-id="9939e-121">Example 2: Stop a specific instance of a process</span></span>

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

<span data-ttu-id="9939e-122">このコマンドを実行すると、Notepad プロセスの特定のインスタンスが停止されます。</span><span class="sxs-lookup"><span data-stu-id="9939e-122">This command stops a particular instance of the Notepad process.</span></span>
<span data-ttu-id="9939e-123">プロセス ID 3952 を使用してプロセスを識別しています。</span><span class="sxs-lookup"><span data-stu-id="9939e-123">It uses the process ID, 3952, to identify the process.</span></span>
<span data-ttu-id="9939e-124">*Confirm* パラメーターは、プロセスを停止する前にプロンプトを表示するように PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="9939e-124">The *Confirm* parameter directs PowerShell to prompt you before it stops the process.</span></span>
<span data-ttu-id="9939e-125">このプロンプトには ID に加えてプロセス名が含まれているため、これがベストプラクティスです。</span><span class="sxs-lookup"><span data-stu-id="9939e-125">Because the prompt includes the process namein addition to its ID, this is best practice.</span></span>
<span data-ttu-id="9939e-126">*PassThru* パラメーターは、プロセスオブジェクトを表示用のフォーマッタに渡します。</span><span class="sxs-lookup"><span data-stu-id="9939e-126">The *PassThru* parameter passes the process object to the formatter for display.</span></span>
<span data-ttu-id="9939e-127">このパラメーターを指定しないと、 **プロセスの停止** コマンドの後に表示されません。</span><span class="sxs-lookup"><span data-stu-id="9939e-127">Without this parameter, there would be no display after a **Stop-Process** command.</span></span>

### <span data-ttu-id="9939e-128">例 3: プロセスを停止し、停止したことを検出する</span><span class="sxs-lookup"><span data-stu-id="9939e-128">Example 3: Stop a process and detect that it has stopped</span></span>

```
PS C:\> calc
PS C:\> $p = Get-Process -Name "calc"
PS C:\> Stop-Process -InputObject $p
PS C:\> Get-Process | Where-Object {$_.HasExited}
```

<span data-ttu-id="9939e-129">この一連のコマンドは、Calc プロセスを開始および停止し、停止したプロセスを検出します。</span><span class="sxs-lookup"><span data-stu-id="9939e-129">This series of commands starts and stops the Calc process, and then detects processes that have stopped.</span></span>

<span data-ttu-id="9939e-130">最初のコマンドは、電卓のインスタンスを起動します。</span><span class="sxs-lookup"><span data-stu-id="9939e-130">The first command starts an instance of the calculator.</span></span>

<span data-ttu-id="9939e-131">2番目のコマンドは、[ **取得プロセス** ] を使用して、Calc プロセスを表すオブジェクトを取得し、$p 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="9939e-131">The second command uses **Get-Process** gets an object that represents the Calc process, and then stores it in the $p variable.</span></span>

<span data-ttu-id="9939e-132">3番目のコマンドは、Calc 処理を停止します。</span><span class="sxs-lookup"><span data-stu-id="9939e-132">The third command stops the Calc process.</span></span>
<span data-ttu-id="9939e-133">*InputObject* パラメーターを使用して、オブジェクトを **停止プロセス** に渡します。</span><span class="sxs-lookup"><span data-stu-id="9939e-133">It uses the *InputObject* parameter to pass the object to **Stop-Process**.</span></span>

<span data-ttu-id="9939e-134">最後のコマンドは、コンピューター上の、以前は実行中で現在は停止しているすべてのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9939e-134">The last command gets all of the processes on the computer that were running but that are now stopped.</span></span>
<span data-ttu-id="9939e-135">コンピューター上のすべてのプロセスを取得するには、 **Get Process** を使用します。</span><span class="sxs-lookup"><span data-stu-id="9939e-135">It uses **Get-Process** to get all of the processes on the computer.</span></span>
<span data-ttu-id="9939e-136">パイプライン演算子 (|) は、Where-Object コマンドレットに結果を渡します。このコマンドレットは、 **Hasexited** $True プロパティの値が指定されているものを選択します。</span><span class="sxs-lookup"><span data-stu-id="9939e-136">The pipeline operator (|) passes the results to the Where-Object cmdlet, which selects the ones where the value of the **HasExited** property is $True.</span></span>
<span data-ttu-id="9939e-137">**Hasexited** 、プロセスオブジェクトの1つのプロパティにすぎません。</span><span class="sxs-lookup"><span data-stu-id="9939e-137">**HasExited** is just one property of process objects.</span></span>
<span data-ttu-id="9939e-138">すべてのプロパティを検索するには、「」と入力 `Get-Process | Get-Member` します。</span><span class="sxs-lookup"><span data-stu-id="9939e-138">To find all the properties, type `Get-Process | Get-Member`.</span></span>

### <span data-ttu-id="9939e-139">例 4: 現在のユーザーが所有していないプロセスを停止する</span><span class="sxs-lookup"><span data-stu-id="9939e-139">Example 4: Stop a process not owned by the current user</span></span>

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

<span data-ttu-id="9939e-140">これらのコマンドは、 *Force* を使用して、ユーザーが所有していないプロセスを停止した場合の影響を示します。</span><span class="sxs-lookup"><span data-stu-id="9939e-140">These commands show the effect of using *Force* to stop a process that is not owned by the user.</span></span>

<span data-ttu-id="9939e-141">最初のコマンドは、 **Get process** を使用して Lsass プロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9939e-141">The first command uses **Get-Process** to get the Lsass process.</span></span>
<span data-ttu-id="9939e-142">パイプライン演算子は、プロセスを停止 **プロセス** に送信して停止します。</span><span class="sxs-lookup"><span data-stu-id="9939e-142">A pipeline operator sends the process to **Stop-Process** to stop it.</span></span>
<span data-ttu-id="9939e-143">サンプル出力に示されているように、最初のコマンドはアクセス拒否メッセージで失敗します。このプロセスは、コンピューターの Administrator グループのメンバーによってのみ停止される可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="9939e-143">As shown in the sample output, the first command fails with an Access denied message, because this process can be stopped only by a member of the Administrator group on the computer.</span></span>

<span data-ttu-id="9939e-144">[管理者として実行] オプションを使用して PowerShell を開き、コマンドを繰り返すと、確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9939e-144">When PowerShell is opened by using the Run as administrator option, and the command is repeated, PowerShell prompts you for confirmation.</span></span>

<span data-ttu-id="9939e-145">2番目のコマンドは、プロンプトを抑制する *Force* を指定します。</span><span class="sxs-lookup"><span data-stu-id="9939e-145">The second command specifies *Force* to suppress the prompt.</span></span>
<span data-ttu-id="9939e-146">その結果、プロセスは確認なしで停止されます。</span><span class="sxs-lookup"><span data-stu-id="9939e-146">As a result, the process is stopped without confirmation.</span></span>

## <span data-ttu-id="9939e-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9939e-147">PARAMETERS</span></span>

### <span data-ttu-id="9939e-148">-Force</span><span class="sxs-lookup"><span data-stu-id="9939e-148">-Force</span></span>

<span data-ttu-id="9939e-149">確認メッセージを表示せずに、指定されたプロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="9939e-149">Stops the specified processes without prompting for confirmation.</span></span>
<span data-ttu-id="9939e-150">既定では、現在のユーザーが所有していないプロセスを停止する前に、 **停止処理** によって確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9939e-150">By default, **Stop-Process** prompts for confirmation before stopping any process that is not owned by the current user.</span></span>

<span data-ttu-id="9939e-151">プロセスの所有者を見つけるには、コマンドレットを使用して、 `Get-CimInstance` プロセスを表す **Win32_Process** オブジェクトを取得し、オブジェクトの **GetOwner** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9939e-151">To find the owner of a process, use the `Get-CimInstance` cmdlet to get a **Win32_Process** object that represents the process, and then use the **GetOwner** method of the object.</span></span>

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

### <span data-ttu-id="9939e-152">-Id</span><span class="sxs-lookup"><span data-stu-id="9939e-152">-Id</span></span>

<span data-ttu-id="9939e-153">停止するプロセスのプロセス Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="9939e-153">Specifies the process IDs of the processes to stop.</span></span>
<span data-ttu-id="9939e-154">複数の ID を指定するには、ID をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="9939e-154">To specify multiple IDs, use commas to separate the IDs.</span></span>
<span data-ttu-id="9939e-155">プロセスの PID を検索するには、「」と入力 `Get-Process` します。</span><span class="sxs-lookup"><span data-stu-id="9939e-155">To find the PID of a process, type `Get-Process`.</span></span>

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

### <span data-ttu-id="9939e-156">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9939e-156">-InputObject</span></span>

<span data-ttu-id="9939e-157">停止するプロセスオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="9939e-157">Specifies the process objects to stop.</span></span>
<span data-ttu-id="9939e-158">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="9939e-158">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="9939e-159">-Name</span><span class="sxs-lookup"><span data-stu-id="9939e-159">-Name</span></span>

<span data-ttu-id="9939e-160">停止するプロセスのプロセス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="9939e-160">Specifies the process names of the processes to stop.</span></span>
<span data-ttu-id="9939e-161">複数のプロセス名をコンマで区切って入力することも、ワイルドカード文字を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9939e-161">You can type multiple process names, separated by commas, or use wildcard characters.</span></span>

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

### <span data-ttu-id="9939e-162">-PassThru</span><span class="sxs-lookup"><span data-stu-id="9939e-162">-PassThru</span></span>

<span data-ttu-id="9939e-163">プロセスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="9939e-163">Returns an object that represents the process.</span></span>
<span data-ttu-id="9939e-164">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="9939e-164">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="9939e-165">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9939e-165">-Confirm</span></span>

<span data-ttu-id="9939e-166">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9939e-166">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9939e-167">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9939e-167">-WhatIf</span></span>

<span data-ttu-id="9939e-168">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="9939e-168">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="9939e-169">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="9939e-169">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9939e-170">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9939e-170">CommonParameters</span></span>
<span data-ttu-id="9939e-171">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="9939e-171">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9939e-172">詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9939e-172">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9939e-173">入力</span><span class="sxs-lookup"><span data-stu-id="9939e-173">INPUTS</span></span>

### <span data-ttu-id="9939e-174">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="9939e-174">System.Diagnostics.Process</span></span>

<span data-ttu-id="9939e-175">パイプを使用してプロセスオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="9939e-175">You can pipe a process object to this cmdlet.</span></span>

## <span data-ttu-id="9939e-176">出力</span><span class="sxs-lookup"><span data-stu-id="9939e-176">OUTPUTS</span></span>

### <span data-ttu-id="9939e-177">なし、システム。診断プロセス</span><span class="sxs-lookup"><span data-stu-id="9939e-177">None, System.Diagnostics.Process</span></span>

<span data-ttu-id="9939e-178">このコマンドレットは、 *PassThru* パラメーターを指定した場合に、停止されたプロセスを表す **system.string オブジェクトを返します。**</span><span class="sxs-lookup"><span data-stu-id="9939e-178">This cmdlet returns a **System.Diagnostics.Process** object that represents the stopped process, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="9939e-179">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="9939e-179">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9939e-180">注</span><span class="sxs-lookup"><span data-stu-id="9939e-180">NOTES</span></span>

* <span data-ttu-id="9939e-181">また、組み込みエイリアスである **kill** と **spps** を使用して、**停止プロセス** を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="9939e-181">You can also refer to **Stop-Process** by its built-in aliases, **kill** and **spps**.</span></span> <span data-ttu-id="9939e-182">詳細については、「about_Aliases」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9939e-182">For more information, see about_Aliases.</span></span>

  <span data-ttu-id="9939e-183">Windows PowerShell では、Windows Management Instrumentation (WMI) **Win32_Process** オブジェクトのプロパティとメソッドを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9939e-183">You can also use the properties and methods of the Windows Management Instrumentation (WMI) **Win32_Process** object in Windows PowerShell.</span></span>
<span data-ttu-id="9939e-184">詳細については、「」および「WMI SDK」を参照してください `Get-CimInstance` 。</span><span class="sxs-lookup"><span data-stu-id="9939e-184">For more information, see `Get-CimInstance` and the WMI SDK.</span></span>

* <span data-ttu-id="9939e-185">プロセスを停止すると、プロセスに依存するプロセスやサービスが停止する可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9939e-185">When stopping processes, realize that stopping a process can stop process and services that depend on the process.</span></span>
<span data-ttu-id="9939e-186">場合によっては、プロセスを停止したとき、Windows が停止する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="9939e-186">In an extreme case, stopping a process can stop Windows.</span></span>

## <span data-ttu-id="9939e-187">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9939e-187">RELATED LINKS</span></span>

[<span data-ttu-id="9939e-188">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="9939e-188">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="9939e-189">Get-Process</span><span class="sxs-lookup"><span data-stu-id="9939e-189">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="9939e-190">Start-Process</span><span class="sxs-lookup"><span data-stu-id="9939e-190">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="9939e-191">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="9939e-191">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="9939e-192">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="9939e-192">Wait-Process</span></span>](Wait-Process.md)

