---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-tracesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TraceSource
ms.openlocfilehash: 6e7fd1c6eb3551906b4dd9d947b5e551cd05d30a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602027"
---
# <span data-ttu-id="2ce3d-102">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="2ce3d-102">Set-TraceSource</span></span>

## <span data-ttu-id="2ce3d-103">概要</span><span class="sxs-lookup"><span data-stu-id="2ce3d-103">SYNOPSIS</span></span>
<span data-ttu-id="2ce3d-104">PowerShell コンポーネントのトレースを構成、開始、および停止します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-104">Configures, starts, and stops a trace of PowerShell components.</span></span>

## <span data-ttu-id="2ce3d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2ce3d-105">SYNTAX</span></span>

### <span data-ttu-id="2ce3d-106">オプションセット (既定)</span><span class="sxs-lookup"><span data-stu-id="2ce3d-106">optionsSet (Default)</span></span>

```
Set-TraceSource [-Name] <String[]> [[-Option] <PSTraceSourceOptions>] [-ListenerOption <TraceOptions>]
 [-FilePath <String>] [-Force] [-Debugger] [-PSHost] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="2ce3d-107">removeAllListenersSet</span><span class="sxs-lookup"><span data-stu-id="2ce3d-107">removeAllListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveListener <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="2ce3d-108">Removefilelisten/Set</span><span class="sxs-lookup"><span data-stu-id="2ce3d-108">removeFileListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveFileListener <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="2ce3d-109">Description</span><span class="sxs-lookup"><span data-stu-id="2ce3d-109">DESCRIPTION</span></span>

<span data-ttu-id="2ce3d-110">**Set TraceSource** コマンドレットは、PowerShell コンポーネントのトレースを構成、開始、および停止します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-110">The **Set-TraceSource** cmdlet configures, starts, and stops a trace of a PowerShell component.</span></span>
<span data-ttu-id="2ce3d-111">これを使用して、トレースするコンポーネントと、トレース出力の送信先を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-111">You can use it to specify which components will be traced and where the tracing output is sent.</span></span>

## <span data-ttu-id="2ce3d-112">例</span><span class="sxs-lookup"><span data-stu-id="2ce3d-112">EXAMPLES</span></span>

### <span data-ttu-id="2ce3d-113">例 1: ParameterBinding コンポーネントをトレースする</span><span class="sxs-lookup"><span data-stu-id="2ce3d-113">Example 1: Trace the ParameterBinding component</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -Option ExecutionFlow -PSHost -ListenerOption "ProcessId,TimeStamp"
```

<span data-ttu-id="2ce3d-114">このコマンドは、PowerShell の ParameterBinding コンポーネントのトレースを開始します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-114">This command starts tracing for the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="2ce3d-115">*Name* パラメーターを使用してトレースソースを指定し、 *Option* パラメーターを使用して executionflow トレースイベントを選択します。また、 *PSHost* パラメーターを使用して、出力をコンソールに送信する PowerShell ホストリスナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-115">It uses the *Name* parameter to specify the trace source, the *Option* parameter to select the ExecutionFlow trace events, and the *PSHost* parameter to select the PowerShell host listener, which sends the output to the console.</span></span>
<span data-ttu-id="2ce3d-116">*ListenerOption* パラメーターを指定すると、ProcessID と TimeStamp の値がトレースメッセージのプレフィックスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-116">The *ListenerOption* parameter adds the ProcessID and TimeStamp values to the trace message prefix.</span></span>

### <span data-ttu-id="2ce3d-117">例 2: トレースを停止する</span><span class="sxs-lookup"><span data-stu-id="2ce3d-117">Example 2: Stop a trace</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -RemoveListener "Host"
```

<span data-ttu-id="2ce3d-118">このコマンドは、PowerShell の ParameterBinding コンポーネントのトレースを停止します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-118">This command stops the trace of the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="2ce3d-119">この例では、 *Name* パラメーターを使用して、トレース対象のコンポーネントを識別し、 *removelistener* パラメーターを使用してトレースリスナーを識別します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-119">It uses the *Name* parameter to identify the component that was being traced and the *RemoveListener* parameter to identify the trace listener.</span></span>

## <span data-ttu-id="2ce3d-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2ce3d-120">PARAMETERS</span></span>

### <span data-ttu-id="2ce3d-121">-デバッガー</span><span class="sxs-lookup"><span data-stu-id="2ce3d-121">-Debugger</span></span>

<span data-ttu-id="2ce3d-122">コマンドレットがトレース出力をデバッガーに送信することを示します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-122">Indicates that the cmdlet sends the trace output to the debugger.</span></span>
<span data-ttu-id="2ce3d-123">ユーザー モードまたはカーネル モードのデバッガー、あるいは Microsoft Visual Studio で出力を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-123">You can view the output in any user-mode or kernel mode debugger or in Microsoft Visual Studio.</span></span>
<span data-ttu-id="2ce3d-124">このパラメーターは、既定のトレース リスナーも選択します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-124">This parameter also selects the default trace listener.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ce3d-125">-FilePath</span><span class="sxs-lookup"><span data-stu-id="2ce3d-125">-FilePath</span></span>

<span data-ttu-id="2ce3d-126">このコマンドレットがトレース出力を送信するファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-126">Specifies a file that this cmdlet sends the trace output to.</span></span>
<span data-ttu-id="2ce3d-127">このパラメーターは、ファイル トレース リスナーも選択します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-127">This parameter also selects the file trace listener.</span></span>
<span data-ttu-id="2ce3d-128">このパラメーターを使用してトレースを開始する場合は、 *Removefilelistener* パラメーターを使用してトレースを停止します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-128">If you use this parameter to start the trace, use the *RemoveFileListener* parameter to stop the trace.</span></span>

```yaml
Type: System.String
Parameter Sets: optionsSet
Aliases: PSPath, Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ce3d-129">-Force</span><span class="sxs-lookup"><span data-stu-id="2ce3d-129">-Force</span></span>

<span data-ttu-id="2ce3d-130">コマンドレットが読み取り専用ファイルを上書きすることを示します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-130">Indicates that the cmdlet overwrites a read-only file.</span></span>
<span data-ttu-id="2ce3d-131">*FilePath* パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-131">Use with the *FilePath* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ce3d-132">-ListenerOption</span><span class="sxs-lookup"><span data-stu-id="2ce3d-132">-ListenerOption</span></span>

<span data-ttu-id="2ce3d-133">出力の各トレースメッセージのプレフィックスにオプションのデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-133">Specifies optional data to the prefix of each trace message in the output.</span></span>
<span data-ttu-id="2ce3d-134">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-134">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2ce3d-135">なし</span><span class="sxs-lookup"><span data-stu-id="2ce3d-135">None</span></span>
- <span data-ttu-id="2ce3d-136">LogicalOperationStack</span><span class="sxs-lookup"><span data-stu-id="2ce3d-136">LogicalOperationStack</span></span>
- <span data-ttu-id="2ce3d-137">DateTime</span><span class="sxs-lookup"><span data-stu-id="2ce3d-137">DateTime</span></span>
- <span data-ttu-id="2ce3d-138">Timestamp</span><span class="sxs-lookup"><span data-stu-id="2ce3d-138">Timestamp</span></span>
- <span data-ttu-id="2ce3d-139">ProcessId</span><span class="sxs-lookup"><span data-stu-id="2ce3d-139">ProcessId</span></span>
- <span data-ttu-id="2ce3d-140">スレッド Id</span><span class="sxs-lookup"><span data-stu-id="2ce3d-140">ThreadId</span></span>
- <span data-ttu-id="2ce3d-141">呼び出し履歴</span><span class="sxs-lookup"><span data-stu-id="2ce3d-141">Callstack</span></span>

<span data-ttu-id="2ce3d-142">[なし] が既定値です。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-142">None is the default.</span></span>

<span data-ttu-id="2ce3d-143">複数のオプションを指定するには、スペースなしで、コンマで区切り、"ProcessID,ThreadID" のように引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-143">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "ProcessID,ThreadID".</span></span>

```yaml
Type: System.Diagnostics.TraceOptions
Parameter Sets: optionsSet
Aliases:
Accepted values: None, LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ce3d-144">-Name</span><span class="sxs-lookup"><span data-stu-id="2ce3d-144">-Name</span></span>

<span data-ttu-id="2ce3d-145">トレースするコンポーネントを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-145">Specifies which components are traced.</span></span>
<span data-ttu-id="2ce3d-146">各コンポーネントのトレース ソースの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-146">Enter the name of the trace source of each component.</span></span>
<span data-ttu-id="2ce3d-147">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-147">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="2ce3d-148">-Option</span><span class="sxs-lookup"><span data-stu-id="2ce3d-148">-Option</span></span>

<span data-ttu-id="2ce3d-149">トレースされるイベントの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-149">Specifies the type of events that are traced.</span></span>
<span data-ttu-id="2ce3d-150">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-150">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="2ce3d-151">なし</span><span class="sxs-lookup"><span data-stu-id="2ce3d-151">None</span></span>
- <span data-ttu-id="2ce3d-152">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="2ce3d-152">Constructor</span></span>
- <span data-ttu-id="2ce3d-153">Dispose</span><span class="sxs-lookup"><span data-stu-id="2ce3d-153">Dispose</span></span>
- <span data-ttu-id="2ce3d-154">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="2ce3d-154">Finalizer</span></span>
- <span data-ttu-id="2ce3d-155">メソッド</span><span class="sxs-lookup"><span data-stu-id="2ce3d-155">Method</span></span>
- <span data-ttu-id="2ce3d-156">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2ce3d-156">Property</span></span>
- <span data-ttu-id="2ce3d-157">デリゲート</span><span class="sxs-lookup"><span data-stu-id="2ce3d-157">Delegates</span></span>
- <span data-ttu-id="2ce3d-158">イベント</span><span class="sxs-lookup"><span data-stu-id="2ce3d-158">Events</span></span>
- <span data-ttu-id="2ce3d-159">例外</span><span class="sxs-lookup"><span data-stu-id="2ce3d-159">Exception</span></span>
- <span data-ttu-id="2ce3d-160">ロック</span><span class="sxs-lookup"><span data-stu-id="2ce3d-160">Lock</span></span>
- <span data-ttu-id="2ce3d-161">エラー</span><span class="sxs-lookup"><span data-stu-id="2ce3d-161">Error</span></span>
- <span data-ttu-id="2ce3d-162">エラー</span><span class="sxs-lookup"><span data-stu-id="2ce3d-162">Errors</span></span>
- <span data-ttu-id="2ce3d-163">警告</span><span class="sxs-lookup"><span data-stu-id="2ce3d-163">Warning</span></span>
- <span data-ttu-id="2ce3d-164">"詳細"</span><span class="sxs-lookup"><span data-stu-id="2ce3d-164">Verbose</span></span>
- <span data-ttu-id="2ce3d-165">WriteLine</span><span class="sxs-lookup"><span data-stu-id="2ce3d-165">WriteLine</span></span>
- <span data-ttu-id="2ce3d-166">データ</span><span class="sxs-lookup"><span data-stu-id="2ce3d-166">Data</span></span>
- <span data-ttu-id="2ce3d-167">Scope</span><span class="sxs-lookup"><span data-stu-id="2ce3d-167">Scope</span></span>
- <span data-ttu-id="2ce3d-168">ExecutionFlow</span><span class="sxs-lookup"><span data-stu-id="2ce3d-168">ExecutionFlow</span></span>
- <span data-ttu-id="2ce3d-169">Assert</span><span class="sxs-lookup"><span data-stu-id="2ce3d-169">Assert</span></span>
- <span data-ttu-id="2ce3d-170">すべて</span><span class="sxs-lookup"><span data-stu-id="2ce3d-170">All</span></span>

<span data-ttu-id="2ce3d-171">ALL が既定値です。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-171">All is the default.</span></span>

<span data-ttu-id="2ce3d-172">次の値はその他の値の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-172">The following values are combinations of other values:</span></span>

- <span data-ttu-id="2ce3d-173">ExecutionFlow: (コンストラクター、Dispose、ファイナライザー、メソッド、デリゲート、イベント、およびスコープ)</span><span class="sxs-lookup"><span data-stu-id="2ce3d-173">ExecutionFlow: (Constructor, Dispose, Finalizer, Method, Delegates, Events, and Scope)</span></span>
- <span data-ttu-id="2ce3d-174">データ: (コンストラクター、Dispose、ファイナライザー、プロパティ、Verbose、および WriteLine)</span><span class="sxs-lookup"><span data-stu-id="2ce3d-174">Data: (Constructor, Dispose, Finalizer, Property, Verbose, and WriteLine)</span></span>
- <span data-ttu-id="2ce3d-175">エラー: (エラーと例外)。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-175">Errors: (Error and Exception).</span></span>

<span data-ttu-id="2ce3d-176">複数のオプションを指定するには、スペースなしで、コンマで区切り、"Constructor,Dispose" のように引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-176">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "Constructor,Dispose".</span></span>

```yaml
Type: System.Management.Automation.PSTraceSourceOptions
Parameter Sets: optionsSet
Aliases:
Accepted values: None, Constructor, Dispose, Finalizer, Method, Property, Delegates, Events, Exception, Lock, Error, Errors, Warning, Verbose, WriteLine, Data, Scope, ExecutionFlow, Assert, All

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2ce3d-177">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2ce3d-177">-PassThru</span></span>

<span data-ttu-id="2ce3d-178">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-178">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="2ce3d-179">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-179">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ce3d-180">-PSHost</span><span class="sxs-lookup"><span data-stu-id="2ce3d-180">-PSHost</span></span>

<span data-ttu-id="2ce3d-181">ndicates は、このコマンドレットがトレース出力を PowerShell ホストに送信することを通知します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-181">ndicates that this cmdlet sends the trace output to the PowerShell host.</span></span>
<span data-ttu-id="2ce3d-182">このパラメーターは、PSHost トレース リスナーも選択します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-182">This parameter also selects the PSHost trace listener.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: optionsSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ce3d-183">-RemoveFileListener</span><span class="sxs-lookup"><span data-stu-id="2ce3d-183">-RemoveFileListener</span></span>

<span data-ttu-id="2ce3d-184">指定したファイルに関連付けられているファイル トレース リスナーを削除することで、トレースを停止します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-184">Stops the trace by removing the file trace listener associated with the specified file.</span></span>
<span data-ttu-id="2ce3d-185">トレース出力ファイルのパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-185">Enter the path and file name of the trace output file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: removeFileListenersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ce3d-186">-RemoveListener</span><span class="sxs-lookup"><span data-stu-id="2ce3d-186">-RemoveListener</span></span>

<span data-ttu-id="2ce3d-187">トレース リスナーを削除することで、トレースを停止します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-187">Stops the trace by removing the trace listener.</span></span>

<span data-ttu-id="2ce3d-188">*Removelistener* には次の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-188">Use the following values with *RemoveListener*:</span></span>

- <span data-ttu-id="2ce3d-189">PSHost (コンソール) を削除するには、「」と入力 `Host` します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-189">To remove PSHost (console), type `Host`.</span></span>
- <span data-ttu-id="2ce3d-190">デバッガーを削除するには、「」と入力 `Debug` します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-190">To remove Debugger, type `Debug`.</span></span>
- <span data-ttu-id="2ce3d-191">すべてのトレースリスナーを削除するには、「」と入力 `*` します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-191">To remove all trace listeners, type `*`.</span></span>

<span data-ttu-id="2ce3d-192">ファイルトレースリスナーを削除するには、 *Removefilelistener* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-192">To remove the file trace listener, use the *RemoveFileListener* parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: removeAllListenersSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ce3d-193">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2ce3d-193">CommonParameters</span></span>

<span data-ttu-id="2ce3d-194">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-194">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2ce3d-195">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-195">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2ce3d-196">入力</span><span class="sxs-lookup"><span data-stu-id="2ce3d-196">INPUTS</span></span>

### <span data-ttu-id="2ce3d-197">System.String</span><span class="sxs-lookup"><span data-stu-id="2ce3d-197">System.String</span></span>

<span data-ttu-id="2ce3d-198">パイプを使用して、名前を含む文字列を **設定-TraceSource** にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-198">You can pipe a string that contains a name to **Set-TraceSource**.</span></span>

## <span data-ttu-id="2ce3d-199">出力</span><span class="sxs-lookup"><span data-stu-id="2ce3d-199">OUTPUTS</span></span>

### <span data-ttu-id="2ce3d-200">None または System.management.automation.pstracesource。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-200">None or System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="2ce3d-201">*PassThru* パラメーターを使用すると、 **system.management.automation.pstracesource** オブジェクトがトレースセッションを表すように **設定** されます。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-201">When you use the *PassThru* parameter, **Set-TraceSource** generates a **System.Management.Automation.PSTraceSource** object representing the trace session.</span></span>
<span data-ttu-id="2ce3d-202">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-202">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2ce3d-203">注</span><span class="sxs-lookup"><span data-stu-id="2ce3d-203">NOTES</span></span>

* <span data-ttu-id="2ce3d-204">トレースは、開発者がプログラムをデバッグし、調整するために使用するメソッドです。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-204">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="2ce3d-205">トレース時に、プログラムは、内部処理の各手順について詳細なメッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-205">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

  <span data-ttu-id="2ce3d-206">PowerShell トレースコマンドレットは、PowerShell 開発者を支援するように設計されていますが、すべてのユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-206">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span>
<span data-ttu-id="2ce3d-207">これらを使用すると、PowerShell の機能のほぼすべての側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-207">They let you monitor nearly every aspect of the functionality of PowerShell.</span></span>

  <span data-ttu-id="2ce3d-208">トレースソースは、トレースを管理し、コンポーネントのトレースメッセージを生成する各 PowerShell コンポーネントの一部です。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-208">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span>
<span data-ttu-id="2ce3d-209">コンポーネントをトレースするには、トレース ソースを特定します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-209">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="2ce3d-210">トレースリスナーは、トレースの出力を受信し、ユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-210">A trace listener receives the output of the trace and displays it to the user.</span></span>
<span data-ttu-id="2ce3d-211">トレースデータは、ユーザーモードまたはカーネルモードのデバッガー、コンソール、ファイル、または **TraceListener** クラスから派生したカスタムリスナーに送信することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-211">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

* <span data-ttu-id="2ce3d-212">トレースを開始するには、 *Name* パラメーターを使用してトレースソースを指定し、 *FilePath*、 *Debugger*、または *PSHost* パラメーターを使用してリスナー (出力先) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-212">To start a trace, use the *Name* parameter to specify a trace source and the *FilePath*, *Debugger*, or *PSHost* parameters to specify a listener (a destination for the output).</span></span> <span data-ttu-id="2ce3d-213">*Options* パラメーターを使用して、トレースされるイベントの種類を決定し、 *ListenerOption* パラメーターを使用してトレース出力を構成します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-213">Use the *Options* parameter to determine the types of events that are traced and the *ListenerOption* parameter to configure the trace output.</span></span>
* <span data-ttu-id="2ce3d-214">トレースの構成を変更するには、トレースを開始するときと同じように、 **Set TraceSource** コマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-214">To change the configuration of a trace, enter a **Set-TraceSource** command as you would to start a trace.</span></span> <span data-ttu-id="2ce3d-215">PowerShell は、トレースソースが既にトレースされていることを認識します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-215">PowerShell recognizes that the trace source is already being traced.</span></span> <span data-ttu-id="2ce3d-216">トレースを停止し、新しい構成を追加して、トレースを開始または再開します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-216">It stops the trace, adds the new configuration, and starts or restarts the trace.</span></span>
* <span data-ttu-id="2ce3d-217">トレースを停止するには、 *Removelistener* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-217">To stop a trace, use the *RemoveListener* parameter.</span></span> <span data-ttu-id="2ce3d-218">ファイルリスナーを使用するトレース ( *FilePath* パラメーターを使用して開始されたトレース) を停止するには、 *removefilelistener* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-218">To stop a trace that uses the file listener (a trace started by using the *FilePath* parameter), use the *RemoveFileListener* parameter.</span></span> <span data-ttu-id="2ce3d-219">リスナーを削除すると、トレースは停止します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-219">When you remove the listener, the trace stops.</span></span>
* <span data-ttu-id="2ce3d-220">トレース可能なコンポーネントを判別するには、Get TraceSource を使用します。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-220">To determine which components can be traced, use Get-TraceSource.</span></span> <span data-ttu-id="2ce3d-221">各モジュールのトレースソースは、コンポーネントが使用されているときに自動的に読み込まれ、 **Get TraceSource** の出力に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ce3d-221">The trace sources for each module are loaded automatically when the component is in use, and they appear in the output of **Get-TraceSource**.</span></span>

## <span data-ttu-id="2ce3d-222">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2ce3d-222">RELATED LINKS</span></span>

[<span data-ttu-id="2ce3d-223">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="2ce3d-223">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="2ce3d-224">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="2ce3d-224">Trace-Command</span></span>](Trace-Command.md)

