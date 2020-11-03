---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-tracesource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TraceSource
ms.openlocfilehash: cef166404af546c35ccc3b0ffed4174515f74c15
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213691"
---
# <span data-ttu-id="1de77-103">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="1de77-103">Set-TraceSource</span></span>

## <span data-ttu-id="1de77-104">概要</span><span class="sxs-lookup"><span data-stu-id="1de77-104">SYNOPSIS</span></span>
<span data-ttu-id="1de77-105">PowerShell コンポーネントのトレースを構成、開始、および停止します。</span><span class="sxs-lookup"><span data-stu-id="1de77-105">Configures, starts, and stops a trace of PowerShell components.</span></span>

## <span data-ttu-id="1de77-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1de77-106">SYNTAX</span></span>

### <span data-ttu-id="1de77-107">オプションセット (既定)</span><span class="sxs-lookup"><span data-stu-id="1de77-107">optionsSet (Default)</span></span>

```
Set-TraceSource [-Name] <String[]> [[-Option] <PSTraceSourceOptions>] [-ListenerOption <TraceOptions>]
 [-FilePath <String>] [-Force] [-Debugger] [-PSHost] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="1de77-108">removeAllListenersSet</span><span class="sxs-lookup"><span data-stu-id="1de77-108">removeAllListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveListener <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="1de77-109">Removefilelisten/Set</span><span class="sxs-lookup"><span data-stu-id="1de77-109">removeFileListenersSet</span></span>

```
Set-TraceSource [-Name] <String[]> [-RemoveFileListener <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="1de77-110">Description</span><span class="sxs-lookup"><span data-stu-id="1de77-110">DESCRIPTION</span></span>

<span data-ttu-id="1de77-111">**Set TraceSource** コマンドレットは、PowerShell コンポーネントのトレースを構成、開始、および停止します。</span><span class="sxs-lookup"><span data-stu-id="1de77-111">The **Set-TraceSource** cmdlet configures, starts, and stops a trace of a PowerShell component.</span></span>
<span data-ttu-id="1de77-112">これを使用して、トレースするコンポーネントと、トレース出力の送信先を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1de77-112">You can use it to specify which components will be traced and where the tracing output is sent.</span></span>

## <span data-ttu-id="1de77-113">例</span><span class="sxs-lookup"><span data-stu-id="1de77-113">EXAMPLES</span></span>

### <span data-ttu-id="1de77-114">例 1: ParameterBinding コンポーネントをトレースする</span><span class="sxs-lookup"><span data-stu-id="1de77-114">Example 1: Trace the ParameterBinding component</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -Option ExecutionFlow -PSHost -ListenerOption "ProcessId,TimeStamp"
```

<span data-ttu-id="1de77-115">このコマンドは、PowerShell の ParameterBinding コンポーネントのトレースを開始します。</span><span class="sxs-lookup"><span data-stu-id="1de77-115">This command starts tracing for the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="1de77-116">*Name* パラメーターを使用してトレースソースを指定し、 *Option* パラメーターを使用して executionflow トレースイベントを選択します。また、 *PSHost* パラメーターを使用して、出力をコンソールに送信する PowerShell ホストリスナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1de77-116">It uses the *Name* parameter to specify the trace source, the *Option* parameter to select the ExecutionFlow trace events, and the *PSHost* parameter to select the PowerShell host listener, which sends the output to the console.</span></span>
<span data-ttu-id="1de77-117">*ListenerOption* パラメーターを指定すると、ProcessID と TimeStamp の値がトレースメッセージのプレフィックスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="1de77-117">The *ListenerOption* parameter adds the ProcessID and TimeStamp values to the trace message prefix.</span></span>

### <span data-ttu-id="1de77-118">例 2: トレースを停止する</span><span class="sxs-lookup"><span data-stu-id="1de77-118">Example 2: Stop a trace</span></span>

```
PS C:\> Set-TraceSource -Name "ParameterBinding" -RemoveListener "Host"
```

<span data-ttu-id="1de77-119">このコマンドは、PowerShell の ParameterBinding コンポーネントのトレースを停止します。</span><span class="sxs-lookup"><span data-stu-id="1de77-119">This command stops the trace of the ParameterBinding component of PowerShell.</span></span>
<span data-ttu-id="1de77-120">この例では、 *Name* パラメーターを使用して、トレース対象のコンポーネントを識別し、 *removelistener* パラメーターを使用してトレースリスナーを識別します。</span><span class="sxs-lookup"><span data-stu-id="1de77-120">It uses the *Name* parameter to identify the component that was being traced and the *RemoveListener* parameter to identify the trace listener.</span></span>

## <span data-ttu-id="1de77-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1de77-121">PARAMETERS</span></span>

### <span data-ttu-id="1de77-122">-デバッガー</span><span class="sxs-lookup"><span data-stu-id="1de77-122">-Debugger</span></span>

<span data-ttu-id="1de77-123">コマンドレットがトレース出力をデバッガーに送信することを示します。</span><span class="sxs-lookup"><span data-stu-id="1de77-123">Indicates that the cmdlet sends the trace output to the debugger.</span></span>
<span data-ttu-id="1de77-124">ユーザー モードまたはカーネル モードのデバッガー、あるいは Microsoft Visual Studio で出力を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="1de77-124">You can view the output in any user-mode or kernel mode debugger or in Microsoft Visual Studio.</span></span>
<span data-ttu-id="1de77-125">このパラメーターは、既定のトレース リスナーも選択します。</span><span class="sxs-lookup"><span data-stu-id="1de77-125">This parameter also selects the default trace listener.</span></span>

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

### <span data-ttu-id="1de77-126">-FilePath</span><span class="sxs-lookup"><span data-stu-id="1de77-126">-FilePath</span></span>

<span data-ttu-id="1de77-127">このコマンドレットがトレース出力を送信するファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="1de77-127">Specifies a file that this cmdlet sends the trace output to.</span></span>
<span data-ttu-id="1de77-128">このパラメーターは、ファイル トレース リスナーも選択します。</span><span class="sxs-lookup"><span data-stu-id="1de77-128">This parameter also selects the file trace listener.</span></span>
<span data-ttu-id="1de77-129">このパラメーターを使用してトレースを開始する場合は、 *Removefilelistener* パラメーターを使用してトレースを停止します。</span><span class="sxs-lookup"><span data-stu-id="1de77-129">If you use this parameter to start the trace, use the *RemoveFileListener* parameter to stop the trace.</span></span>

```yaml
Type: System.String
Parameter Sets: optionsSet
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1de77-130">-Force</span><span class="sxs-lookup"><span data-stu-id="1de77-130">-Force</span></span>

<span data-ttu-id="1de77-131">コマンドレットが読み取り専用ファイルを上書きすることを示します。</span><span class="sxs-lookup"><span data-stu-id="1de77-131">Indicates that the cmdlet overwrites a read-only file.</span></span>
<span data-ttu-id="1de77-132">*FilePath* パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="1de77-132">Use with the *FilePath* parameter.</span></span>

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

### <span data-ttu-id="1de77-133">-ListenerOption</span><span class="sxs-lookup"><span data-stu-id="1de77-133">-ListenerOption</span></span>

<span data-ttu-id="1de77-134">出力の各トレースメッセージのプレフィックスにオプションのデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="1de77-134">Specifies optional data to the prefix of each trace message in the output.</span></span>
<span data-ttu-id="1de77-135">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1de77-135">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1de77-136">なし</span><span class="sxs-lookup"><span data-stu-id="1de77-136">None</span></span>
- <span data-ttu-id="1de77-137">LogicalOperationStack</span><span class="sxs-lookup"><span data-stu-id="1de77-137">LogicalOperationStack</span></span>
- <span data-ttu-id="1de77-138">DateTime</span><span class="sxs-lookup"><span data-stu-id="1de77-138">DateTime</span></span>
- <span data-ttu-id="1de77-139">Timestamp</span><span class="sxs-lookup"><span data-stu-id="1de77-139">Timestamp</span></span>
- <span data-ttu-id="1de77-140">ProcessId</span><span class="sxs-lookup"><span data-stu-id="1de77-140">ProcessId</span></span>
- <span data-ttu-id="1de77-141">スレッド Id</span><span class="sxs-lookup"><span data-stu-id="1de77-141">ThreadId</span></span>
- <span data-ttu-id="1de77-142">呼び出し履歴</span><span class="sxs-lookup"><span data-stu-id="1de77-142">Callstack</span></span>

<span data-ttu-id="1de77-143">既定値は None です。</span><span class="sxs-lookup"><span data-stu-id="1de77-143">None is the default.</span></span>

<span data-ttu-id="1de77-144">複数のオプションを指定するには、スペースなしで、コンマで区切り、"ProcessID,ThreadID" のように引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="1de77-144">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "ProcessID,ThreadID".</span></span>

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

### <span data-ttu-id="1de77-145">-Name</span><span class="sxs-lookup"><span data-stu-id="1de77-145">-Name</span></span>

<span data-ttu-id="1de77-146">トレースするコンポーネントを指定します。</span><span class="sxs-lookup"><span data-stu-id="1de77-146">Specifies which components are traced.</span></span>
<span data-ttu-id="1de77-147">各コンポーネントのトレース ソースの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1de77-147">Enter the name of the trace source of each component.</span></span>
<span data-ttu-id="1de77-148">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1de77-148">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="1de77-149">-Option</span><span class="sxs-lookup"><span data-stu-id="1de77-149">-Option</span></span>

<span data-ttu-id="1de77-150">トレースされるイベントの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="1de77-150">Specifies the type of events that are traced.</span></span>
<span data-ttu-id="1de77-151">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1de77-151">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1de77-152">なし</span><span class="sxs-lookup"><span data-stu-id="1de77-152">None</span></span>
- <span data-ttu-id="1de77-153">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="1de77-153">Constructor</span></span>
- <span data-ttu-id="1de77-154">Dispose</span><span class="sxs-lookup"><span data-stu-id="1de77-154">Dispose</span></span>
- <span data-ttu-id="1de77-155">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="1de77-155">Finalizer</span></span>
- <span data-ttu-id="1de77-156">Method</span><span class="sxs-lookup"><span data-stu-id="1de77-156">Method</span></span>
- <span data-ttu-id="1de77-157">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1de77-157">Property</span></span>
- <span data-ttu-id="1de77-158">デリゲート</span><span class="sxs-lookup"><span data-stu-id="1de77-158">Delegates</span></span>
- <span data-ttu-id="1de77-159">イベント</span><span class="sxs-lookup"><span data-stu-id="1de77-159">Events</span></span>
- <span data-ttu-id="1de77-160">例外</span><span class="sxs-lookup"><span data-stu-id="1de77-160">Exception</span></span>
- <span data-ttu-id="1de77-161">ロック</span><span class="sxs-lookup"><span data-stu-id="1de77-161">Lock</span></span>
- <span data-ttu-id="1de77-162">エラー</span><span class="sxs-lookup"><span data-stu-id="1de77-162">Error</span></span>
- <span data-ttu-id="1de77-163">エラー</span><span class="sxs-lookup"><span data-stu-id="1de77-163">Errors</span></span>
- <span data-ttu-id="1de77-164">警告</span><span class="sxs-lookup"><span data-stu-id="1de77-164">Warning</span></span>
- <span data-ttu-id="1de77-165">"詳細"</span><span class="sxs-lookup"><span data-stu-id="1de77-165">Verbose</span></span>
- <span data-ttu-id="1de77-166">WriteLine</span><span class="sxs-lookup"><span data-stu-id="1de77-166">WriteLine</span></span>
- <span data-ttu-id="1de77-167">Data</span><span class="sxs-lookup"><span data-stu-id="1de77-167">Data</span></span>
- <span data-ttu-id="1de77-168">Scope</span><span class="sxs-lookup"><span data-stu-id="1de77-168">Scope</span></span>
- <span data-ttu-id="1de77-169">ExecutionFlow</span><span class="sxs-lookup"><span data-stu-id="1de77-169">ExecutionFlow</span></span>
- <span data-ttu-id="1de77-170">Assert</span><span class="sxs-lookup"><span data-stu-id="1de77-170">Assert</span></span>
- <span data-ttu-id="1de77-171">All</span><span class="sxs-lookup"><span data-stu-id="1de77-171">All</span></span>

<span data-ttu-id="1de77-172">ALL が既定値です。</span><span class="sxs-lookup"><span data-stu-id="1de77-172">All is the default.</span></span>

<span data-ttu-id="1de77-173">次の値はその他の値の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="1de77-173">The following values are combinations of other values:</span></span>

- <span data-ttu-id="1de77-174">ExecutionFlow: (コンストラクター、Dispose、ファイナライザー、メソッド、デリゲート、イベント、およびスコープ)</span><span class="sxs-lookup"><span data-stu-id="1de77-174">ExecutionFlow: (Constructor, Dispose, Finalizer, Method, Delegates, Events, and Scope)</span></span>
- <span data-ttu-id="1de77-175">データ: (コンストラクター、Dispose、ファイナライザー、プロパティ、Verbose、および WriteLine)</span><span class="sxs-lookup"><span data-stu-id="1de77-175">Data: (Constructor, Dispose, Finalizer, Property, Verbose, and WriteLine)</span></span>
- <span data-ttu-id="1de77-176">エラー: (エラーと例外)。</span><span class="sxs-lookup"><span data-stu-id="1de77-176">Errors: (Error and Exception).</span></span>

<span data-ttu-id="1de77-177">複数のオプションを指定するには、スペースなしで、コンマで区切り、"Constructor,Dispose" のように引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="1de77-177">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "Constructor,Dispose".</span></span>

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

### <span data-ttu-id="1de77-178">-PassThru</span><span class="sxs-lookup"><span data-stu-id="1de77-178">-PassThru</span></span>

<span data-ttu-id="1de77-179">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="1de77-179">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="1de77-180">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="1de77-180">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="1de77-181">-PSHost</span><span class="sxs-lookup"><span data-stu-id="1de77-181">-PSHost</span></span>

<span data-ttu-id="1de77-182">ndicates は、このコマンドレットがトレース出力を PowerShell ホストに送信することを通知します。</span><span class="sxs-lookup"><span data-stu-id="1de77-182">ndicates that this cmdlet sends the trace output to the PowerShell host.</span></span>
<span data-ttu-id="1de77-183">このパラメーターは、PSHost トレース リスナーも選択します。</span><span class="sxs-lookup"><span data-stu-id="1de77-183">This parameter also selects the PSHost trace listener.</span></span>

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

### <span data-ttu-id="1de77-184">-RemoveFileListener</span><span class="sxs-lookup"><span data-stu-id="1de77-184">-RemoveFileListener</span></span>

<span data-ttu-id="1de77-185">指定したファイルに関連付けられているファイル トレース リスナーを削除することで、トレースを停止します。</span><span class="sxs-lookup"><span data-stu-id="1de77-185">Stops the trace by removing the file trace listener associated with the specified file.</span></span>
<span data-ttu-id="1de77-186">トレース出力ファイルのパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="1de77-186">Enter the path and file name of the trace output file.</span></span>

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

### <span data-ttu-id="1de77-187">-RemoveListener</span><span class="sxs-lookup"><span data-stu-id="1de77-187">-RemoveListener</span></span>

<span data-ttu-id="1de77-188">トレース リスナーを削除することで、トレースを停止します。</span><span class="sxs-lookup"><span data-stu-id="1de77-188">Stops the trace by removing the trace listener.</span></span>

<span data-ttu-id="1de77-189">*Removelistener* には次の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="1de77-189">Use the following values with *RemoveListener* :</span></span>

- <span data-ttu-id="1de77-190">PSHost (コンソール) を削除するには、「」と入力 `Host` します。</span><span class="sxs-lookup"><span data-stu-id="1de77-190">To remove PSHost (console), type `Host`.</span></span>
- <span data-ttu-id="1de77-191">デバッガーを削除するには、「」と入力 `Debug` します。</span><span class="sxs-lookup"><span data-stu-id="1de77-191">To remove Debugger, type `Debug`.</span></span>
- <span data-ttu-id="1de77-192">すべてのトレースリスナーを削除するには、「」と入力 `*` します。</span><span class="sxs-lookup"><span data-stu-id="1de77-192">To remove all trace listeners, type `*`.</span></span>

<span data-ttu-id="1de77-193">ファイルトレースリスナーを削除するには、 *Removefilelistener* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1de77-193">To remove the file trace listener, use the *RemoveFileListener* parameter.</span></span>

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

### <span data-ttu-id="1de77-194">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1de77-194">CommonParameters</span></span>

<span data-ttu-id="1de77-195">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="1de77-195">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1de77-196">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de77-196">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1de77-197">入力</span><span class="sxs-lookup"><span data-stu-id="1de77-197">INPUTS</span></span>

### <span data-ttu-id="1de77-198">System.String</span><span class="sxs-lookup"><span data-stu-id="1de77-198">System.String</span></span>

<span data-ttu-id="1de77-199">パイプを使用して、名前を含む文字列を **設定-TraceSource** にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1de77-199">You can pipe a string that contains a name to **Set-TraceSource** .</span></span>

## <span data-ttu-id="1de77-200">出力</span><span class="sxs-lookup"><span data-stu-id="1de77-200">OUTPUTS</span></span>

### <span data-ttu-id="1de77-201">None または System.management.automation.pstracesource。</span><span class="sxs-lookup"><span data-stu-id="1de77-201">None or System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="1de77-202">*PassThru* パラメーターを使用すると、 **system.management.automation.pstracesource** オブジェクトがトレースセッションを表すように **設定** されます。</span><span class="sxs-lookup"><span data-stu-id="1de77-202">When you use the *PassThru* parameter, **Set-TraceSource** generates a **System.Management.Automation.PSTraceSource** object representing the trace session.</span></span>
<span data-ttu-id="1de77-203">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="1de77-203">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="1de77-204">注</span><span class="sxs-lookup"><span data-stu-id="1de77-204">NOTES</span></span>

* <span data-ttu-id="1de77-205">トレースは、開発者がプログラムをデバッグし、調整するために使用するメソッドです。</span><span class="sxs-lookup"><span data-stu-id="1de77-205">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="1de77-206">トレース時に、プログラムは、内部処理の各手順について詳細なメッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="1de77-206">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

  <span data-ttu-id="1de77-207">PowerShell トレースコマンドレットは、PowerShell 開発者を支援するように設計されていますが、すべてのユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="1de77-207">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span>
<span data-ttu-id="1de77-208">これらを使用すると、PowerShell の機能のほぼすべての側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="1de77-208">They let you monitor nearly every aspect of the functionality of PowerShell.</span></span>

  <span data-ttu-id="1de77-209">トレースソースは、トレースを管理し、コンポーネントのトレースメッセージを生成する各 PowerShell コンポーネントの一部です。</span><span class="sxs-lookup"><span data-stu-id="1de77-209">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span>
<span data-ttu-id="1de77-210">コンポーネントをトレースするには、トレース ソースを特定します。</span><span class="sxs-lookup"><span data-stu-id="1de77-210">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="1de77-211">トレースリスナーは、トレースの出力を受信し、ユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="1de77-211">A trace listener receives the output of the trace and displays it to the user.</span></span>
<span data-ttu-id="1de77-212">トレースデータは、ユーザーモードまたはカーネルモードのデバッガー、コンソール、ファイル、または **TraceListener** クラスから派生したカスタムリスナーに送信することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1de77-212">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

* <span data-ttu-id="1de77-213">トレースを開始するには、 *Name* パラメーターを使用してトレースソースを指定し、 *FilePath* 、 *Debugger* 、または *PSHost* パラメーターを使用してリスナー (出力先) を指定します。</span><span class="sxs-lookup"><span data-stu-id="1de77-213">To start a trace, use the *Name* parameter to specify a trace source and the *FilePath* , *Debugger* , or *PSHost* parameters to specify a listener (a destination for the output).</span></span> <span data-ttu-id="1de77-214">*Options* パラメーターを使用して、トレースされるイベントの種類を決定し、 *ListenerOption* パラメーターを使用してトレース出力を構成します。</span><span class="sxs-lookup"><span data-stu-id="1de77-214">Use the *Options* parameter to determine the types of events that are traced and the *ListenerOption* parameter to configure the trace output.</span></span>
* <span data-ttu-id="1de77-215">トレースの構成を変更するには、トレースを開始するときと同じように、 **Set TraceSource** コマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="1de77-215">To change the configuration of a trace, enter a **Set-TraceSource** command as you would to start a trace.</span></span> <span data-ttu-id="1de77-216">PowerShell は、トレースソースが既にトレースされていることを認識します。</span><span class="sxs-lookup"><span data-stu-id="1de77-216">PowerShell recognizes that the trace source is already being traced.</span></span> <span data-ttu-id="1de77-217">トレースを停止し、新しい構成を追加して、トレースを開始または再開します。</span><span class="sxs-lookup"><span data-stu-id="1de77-217">It stops the trace, adds the new configuration, and starts or restarts the trace.</span></span>
* <span data-ttu-id="1de77-218">トレースを停止するには、 *Removelistener* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1de77-218">To stop a trace, use the *RemoveListener* parameter.</span></span> <span data-ttu-id="1de77-219">ファイルリスナーを使用するトレース ( *FilePath* パラメーターを使用して開始されたトレース) を停止するには、 *removefilelistener* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1de77-219">To stop a trace that uses the file listener (a trace started by using the *FilePath* parameter), use the *RemoveFileListener* parameter.</span></span> <span data-ttu-id="1de77-220">リスナーを削除すると、トレースは停止します。</span><span class="sxs-lookup"><span data-stu-id="1de77-220">When you remove the listener, the trace stops.</span></span>
* <span data-ttu-id="1de77-221">トレース可能なコンポーネントを判別するには、Get TraceSource を使用します。</span><span class="sxs-lookup"><span data-stu-id="1de77-221">To determine which components can be traced, use Get-TraceSource.</span></span> <span data-ttu-id="1de77-222">各モジュールのトレースソースは、コンポーネントが使用されているときに自動的に読み込まれ、 **Get TraceSource** の出力に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1de77-222">The trace sources for each module are loaded automatically when the component is in use, and they appear in the output of **Get-TraceSource** .</span></span>

## <span data-ttu-id="1de77-223">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1de77-223">RELATED LINKS</span></span>

[<span data-ttu-id="1de77-224">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="1de77-224">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="1de77-225">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="1de77-225">Trace-Command</span></span>](Trace-Command.md)
