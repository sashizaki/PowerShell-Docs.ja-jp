---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/trace-command?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Trace-Command
ms.openlocfilehash: c26e1c46db8f7c6eeeb5c970bc17921622cd023e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211747"
---
# <span data-ttu-id="95779-103">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="95779-103">Trace-Command</span></span>

## <span data-ttu-id="95779-104">概要</span><span class="sxs-lookup"><span data-stu-id="95779-104">SYNOPSIS</span></span>
<span data-ttu-id="95779-105">指定された式またはコマンドのトレースを構成し、開始します。</span><span class="sxs-lookup"><span data-stu-id="95779-105">Configures and starts a trace of the specified expression or command.</span></span>

## <span data-ttu-id="95779-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="95779-106">SYNTAX</span></span>

### <span data-ttu-id="95779-107">式セット (既定値)</span><span class="sxs-lookup"><span data-stu-id="95779-107">expressionSet (Default)</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Expression] <ScriptBlock> [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force] [-Debugger]
 [-PSHost] [<CommonParameters>]
```

### <span data-ttu-id="95779-108">commandSet</span><span class="sxs-lookup"><span data-stu-id="95779-108">commandSet</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Command] <String> [-ArgumentList <Object[]>] [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force]
 [-Debugger] [-PSHost] [<CommonParameters>]
```

## <span data-ttu-id="95779-109">Description</span><span class="sxs-lookup"><span data-stu-id="95779-109">DESCRIPTION</span></span>
<span data-ttu-id="95779-110">`Trace-Command`コマンドレットは、指定された式またはコマンドのトレースを構成し、開始します。</span><span class="sxs-lookup"><span data-stu-id="95779-110">The `Trace-Command` cmdlet configures and starts a trace of the specified expression or command.</span></span>
<span data-ttu-id="95779-111">Set-TraceSource と同様に機能しますが、指定されたコマンドにのみ適用される点が異なります。</span><span class="sxs-lookup"><span data-stu-id="95779-111">It works like Set-TraceSource, except that it applies only to the specified command.</span></span>

## <span data-ttu-id="95779-112">例</span><span class="sxs-lookup"><span data-stu-id="95779-112">EXAMPLES</span></span>

### <span data-ttu-id="95779-113">例 1: メタデータの処理、パラメーターのバインド、および式をトレースする</span><span class="sxs-lookup"><span data-stu-id="95779-113">Example 1: Trace metadata processing, parameter binding, and an expression</span></span>

<span data-ttu-id="95779-114">この例では、メタデータの処理、パラメーターのバインド、およびコマンドレットの作成と式の破棄のトレースを開始し `Get-Process Notepad` ます。</span><span class="sxs-lookup"><span data-stu-id="95779-114">This example starts a trace of metadata processing, parameter binding, and cmdlet creation and destruction of the `Get-Process Notepad` expression.</span></span>

```powershell
Trace-Command -Name metadata,parameterbinding,cmdlet -Expression {Get-Process Notepad} -PSHost
```

<span data-ttu-id="95779-115">**Name** パラメーターを使用してトレースソースを指定し、 **Expression** パラメーターでコマンドを指定し、 **PSHost** パラメーターを使用して出力をコンソールに送信します。</span><span class="sxs-lookup"><span data-stu-id="95779-115">It uses the **Name** parameter to specify the trace sources, the **Expression** parameter to specify the command, and the **PSHost** parameter to send the output to the console.</span></span> <span data-ttu-id="95779-116">トレースオプションまたはリスナーオプションは指定されていないため、コマンドは既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="95779-116">Because it does not specify any tracing options or listener options, the command uses the defaults:</span></span>

- <span data-ttu-id="95779-117">トレースオプションのすべて</span><span class="sxs-lookup"><span data-stu-id="95779-117">All for the tracing options</span></span>
- <span data-ttu-id="95779-118">リスナーオプションの場合は None</span><span class="sxs-lookup"><span data-stu-id="95779-118">None for the listener options</span></span>

### <span data-ttu-id="95779-119">例 2: ParameterBinding 操作のアクションをトレースする</span><span class="sxs-lookup"><span data-stu-id="95779-119">Example 2: Trace the actions of ParameterBinding operations</span></span>

<span data-ttu-id="95779-120">この例では、パイプラインからの入力を受け取る式を処理するときに、PowerShell の **Parameterbinding** 操作のアクションをトレース `Get-Alias` します。</span><span class="sxs-lookup"><span data-stu-id="95779-120">This example traces the actions of the **ParameterBinding** operations of PowerShell while it processes a `Get-Alias` expression that takes input from the pipeline.</span></span>

```powershell
$A = "i*"
Trace-Command ParameterBinding {Get-Alias $Input} -PSHost -InputObject $A
```

<span data-ttu-id="95779-121">では `Trace-Command` 、 **InputObject** パラメーターは、トレース中に処理される式にオブジェクトを渡します。</span><span class="sxs-lookup"><span data-stu-id="95779-121">In `Trace-Command`, the **InputObject** parameter passes an object to the expression that is being processed during the trace.</span></span>

<span data-ttu-id="95779-122">最初のコマンドは、変数に文字列を格納し `i*` `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="95779-122">The first command stores the string `i*` in the `$A` variable.</span></span> <span data-ttu-id="95779-123">2番目のコマンドは、 `Trace-Command` ParameterBinding トレースソースと共にコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="95779-123">The second command uses the `Trace-Command` cmdlet with the ParameterBinding trace source.</span></span> <span data-ttu-id="95779-124">**PSHost** パラメーターを指定すると、出力がコンソールに送信されます。</span><span class="sxs-lookup"><span data-stu-id="95779-124">The **PSHost** parameter sends the output to the console.</span></span>

<span data-ttu-id="95779-125">処理される式はです `Get-Alias $Input` 。ここで、 `$Input` 変数は **InputObject** パラメーターに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="95779-125">The expression being processed is `Get-Alias $Input`, where the `$Input` variable is associated with the **InputObject** parameter.</span></span> <span data-ttu-id="95779-126">**InputObject** パラメーターは、変数 `$A` を式に渡します。</span><span class="sxs-lookup"><span data-stu-id="95779-126">The **InputObject** parameter passes the variable `$A` to the expression.</span></span> <span data-ttu-id="95779-127">実際には、トレース中に処理されるコマンドは `Get-Alias -InputObject $A" or "$A | Get-Alias` です。</span><span class="sxs-lookup"><span data-stu-id="95779-127">In effect, the command being processed during the trace is `Get-Alias -InputObject $A" or "$A | Get-Alias`.</span></span>

## <span data-ttu-id="95779-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="95779-128">PARAMETERS</span></span>

### <span data-ttu-id="95779-129">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="95779-129">-ArgumentList</span></span>

<span data-ttu-id="95779-130">トレースするコマンドのパラメーターとパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="95779-130">Specifies the parameters and parameter values for the command being traced.</span></span> <span data-ttu-id="95779-131">**ArgumentList** のエイリアスは、 **Args** です。</span><span class="sxs-lookup"><span data-stu-id="95779-131">The alias for **ArgumentList** is **Args** .</span></span> <span data-ttu-id="95779-132">この機能は、動的パラメーターをデバッグする場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="95779-132">This feature is especially useful for debugging dynamic parameters.</span></span>

<span data-ttu-id="95779-133">**ArgumentList** の動作の詳細については、「 [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95779-133">For more information about the behavior of **ArgumentList** , see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: commandSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95779-134">-Command</span><span class="sxs-lookup"><span data-stu-id="95779-134">-Command</span></span>

<span data-ttu-id="95779-135">トレース中に処理するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="95779-135">Specifies a command that is being processed during the trace.</span></span>

```yaml
Type: System.String
Parameter Sets: commandSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95779-136">-デバッガー</span><span class="sxs-lookup"><span data-stu-id="95779-136">-Debugger</span></span>

<span data-ttu-id="95779-137">コマンドレットがトレース出力をデバッガーに送信することを示します。</span><span class="sxs-lookup"><span data-stu-id="95779-137">Indicates that the cmdlet sends the trace output to the debugger.</span></span> <span data-ttu-id="95779-138">出力はユーザー モードまたはカーネル モードのデバッガーや、Visual Studio で表示することができます。</span><span class="sxs-lookup"><span data-stu-id="95779-138">You can view the output in any user-mode or kernel mode debugger or in Visual Studio.</span></span> <span data-ttu-id="95779-139">このパラメーターは、既定のトレース リスナーも選択します。</span><span class="sxs-lookup"><span data-stu-id="95779-139">This parameter also selects the default trace listener.</span></span>

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

### <span data-ttu-id="95779-140">-式</span><span class="sxs-lookup"><span data-stu-id="95779-140">-Expression</span></span>

<span data-ttu-id="95779-141">トレース中に処理する式を指定します。</span><span class="sxs-lookup"><span data-stu-id="95779-141">Specifies the expression that is being processed during the trace.</span></span> <span data-ttu-id="95779-142">式を中かっこ () で囲み `{}` ます。</span><span class="sxs-lookup"><span data-stu-id="95779-142">Enclose the expression in braces (`{}`).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: expressionSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95779-143">-FilePath</span><span class="sxs-lookup"><span data-stu-id="95779-143">-FilePath</span></span>

<span data-ttu-id="95779-144">コマンドレットがトレース出力を送信するファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="95779-144">Specifies a file that the cmdlet sends the trace output to.</span></span> <span data-ttu-id="95779-145">このパラメーターは、ファイル トレース リスナーも選択します。</span><span class="sxs-lookup"><span data-stu-id="95779-145">This parameter also selects the file trace listener.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95779-146">-Force</span><span class="sxs-lookup"><span data-stu-id="95779-146">-Force</span></span>

<span data-ttu-id="95779-147">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="95779-147">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="95779-148">**FilePath** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="95779-148">Used with the **FilePath** parameter.</span></span> <span data-ttu-id="95779-149">**Force** パラメーターを使用しても、コマンドレットはセキュリティ制限を上書きできません。</span><span class="sxs-lookup"><span data-stu-id="95779-149">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="95779-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="95779-150">-InputObject</span></span>

<span data-ttu-id="95779-151">トレース中に処理される式への入力を指定します。</span><span class="sxs-lookup"><span data-stu-id="95779-151">Specifies input to the expression that is being processed during the trace.</span></span> <span data-ttu-id="95779-152">式が受け取る入力を表した変数を入力するか、パイプラインを通じてオブジェクトを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="95779-152">You can enter a variable that represents the input that the expression accepts, or pass an object through the pipeline.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="95779-153">-ListenerOption</span><span class="sxs-lookup"><span data-stu-id="95779-153">-ListenerOption</span></span>

<span data-ttu-id="95779-154">出力の各トレースメッセージのプレフィックスにオプションのデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="95779-154">Specifies optional data to the prefix of each trace message in the output.</span></span> <span data-ttu-id="95779-155">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="95779-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="95779-156">なし</span><span class="sxs-lookup"><span data-stu-id="95779-156">None</span></span>
- <span data-ttu-id="95779-157">LogicalOperationStack</span><span class="sxs-lookup"><span data-stu-id="95779-157">LogicalOperationStack</span></span>
- <span data-ttu-id="95779-158">DateTime</span><span class="sxs-lookup"><span data-stu-id="95779-158">DateTime</span></span>
- <span data-ttu-id="95779-159">Timestamp</span><span class="sxs-lookup"><span data-stu-id="95779-159">Timestamp</span></span>
- <span data-ttu-id="95779-160">ProcessId</span><span class="sxs-lookup"><span data-stu-id="95779-160">ProcessId</span></span>
- <span data-ttu-id="95779-161">スレッド Id</span><span class="sxs-lookup"><span data-stu-id="95779-161">ThreadId</span></span>
- <span data-ttu-id="95779-162">呼び出し履歴</span><span class="sxs-lookup"><span data-stu-id="95779-162">Callstack</span></span>

<span data-ttu-id="95779-163">既定値は **None** です。</span><span class="sxs-lookup"><span data-stu-id="95779-163">**None** is the default.</span></span>

<span data-ttu-id="95779-164">複数のオプションを指定するには、スペースなしで、コンマで区切り、"ProcessID,ThreadID" のように引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="95779-164">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "ProcessID,ThreadID".</span></span>

```yaml
Type: System.Diagnostics.TraceOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95779-165">-Name</span><span class="sxs-lookup"><span data-stu-id="95779-165">-Name</span></span>

<span data-ttu-id="95779-166">トレースされる PowerShell コンポーネントの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="95779-166">Specifies an array of PowerShell components that are traced.</span></span> <span data-ttu-id="95779-167">各コンポーネントのトレース ソースの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="95779-167">Enter the name of the trace source of each component.</span></span> <span data-ttu-id="95779-168">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="95779-168">Wildcards are permitted.</span></span> <span data-ttu-id="95779-169">コンピューター上のトレースソースを検索するには、「」と入力 `Get-TraceSource` します。</span><span class="sxs-lookup"><span data-stu-id="95779-169">To find the trace sources on your computer, type `Get-TraceSource`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95779-170">-Option</span><span class="sxs-lookup"><span data-stu-id="95779-170">-Option</span></span>

<span data-ttu-id="95779-171">トレース対象のイベントの種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="95779-171">Determines the type of events that are traced.</span></span> <span data-ttu-id="95779-172">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="95779-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="95779-173">なし</span><span class="sxs-lookup"><span data-stu-id="95779-173">None</span></span>
- <span data-ttu-id="95779-174">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="95779-174">Constructor</span></span>
- <span data-ttu-id="95779-175">Dispose</span><span class="sxs-lookup"><span data-stu-id="95779-175">Dispose</span></span>
- <span data-ttu-id="95779-176">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="95779-176">Finalizer</span></span>
- <span data-ttu-id="95779-177">Method</span><span class="sxs-lookup"><span data-stu-id="95779-177">Method</span></span>
- <span data-ttu-id="95779-178">プロパティ</span><span class="sxs-lookup"><span data-stu-id="95779-178">Property</span></span>
- <span data-ttu-id="95779-179">デリゲート</span><span class="sxs-lookup"><span data-stu-id="95779-179">Delegates</span></span>
- <span data-ttu-id="95779-180">イベント</span><span class="sxs-lookup"><span data-stu-id="95779-180">Events</span></span>
- <span data-ttu-id="95779-181">例外</span><span class="sxs-lookup"><span data-stu-id="95779-181">Exception</span></span>
- <span data-ttu-id="95779-182">ロック</span><span class="sxs-lookup"><span data-stu-id="95779-182">Lock</span></span>
- <span data-ttu-id="95779-183">エラー</span><span class="sxs-lookup"><span data-stu-id="95779-183">Error</span></span>
- <span data-ttu-id="95779-184">エラー</span><span class="sxs-lookup"><span data-stu-id="95779-184">Errors</span></span>
- <span data-ttu-id="95779-185">警告</span><span class="sxs-lookup"><span data-stu-id="95779-185">Warning</span></span>
- <span data-ttu-id="95779-186">"詳細"</span><span class="sxs-lookup"><span data-stu-id="95779-186">Verbose</span></span>
- <span data-ttu-id="95779-187">WriteLine</span><span class="sxs-lookup"><span data-stu-id="95779-187">WriteLine</span></span>
- <span data-ttu-id="95779-188">Data</span><span class="sxs-lookup"><span data-stu-id="95779-188">Data</span></span>
- <span data-ttu-id="95779-189">Scope</span><span class="sxs-lookup"><span data-stu-id="95779-189">Scope</span></span>
- <span data-ttu-id="95779-190">ExecutionFlow</span><span class="sxs-lookup"><span data-stu-id="95779-190">ExecutionFlow</span></span>
- <span data-ttu-id="95779-191">Assert</span><span class="sxs-lookup"><span data-stu-id="95779-191">Assert</span></span>
- <span data-ttu-id="95779-192">All</span><span class="sxs-lookup"><span data-stu-id="95779-192">All</span></span>

<span data-ttu-id="95779-193">ALL が既定値です。</span><span class="sxs-lookup"><span data-stu-id="95779-193">All is the default.</span></span>

<span data-ttu-id="95779-194">次の値はその他の値の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="95779-194">The following values are combinations of other values:</span></span>

- <span data-ttu-id="95779-195">ExecutionFlow: (コンストラクター、Dispose、ファイナライザー、メソッド、デリゲート、イベント、およびスコープ)</span><span class="sxs-lookup"><span data-stu-id="95779-195">ExecutionFlow: (Constructor, Dispose, Finalizer, Method, Delegates, Events, and Scope)</span></span>
- <span data-ttu-id="95779-196">データ: (コンストラクター、Dispose、ファイナライザー、プロパティ、Verbose、および WriteLine)</span><span class="sxs-lookup"><span data-stu-id="95779-196">Data: (Constructor, Dispose, Finalizer, Property, Verbose, and WriteLine)</span></span>
- <span data-ttu-id="95779-197">エラー: (エラーと例外)。</span><span class="sxs-lookup"><span data-stu-id="95779-197">Errors: (Error and Exception).</span></span>

<span data-ttu-id="95779-198">複数のオプションを指定するには、スペースなしで、コンマで区切り、"Constructor,Dispose" のように引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="95779-198">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "Constructor,Dispose".</span></span>

```yaml
Type: System.Management.Automation.PSTraceSourceOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, Constructor, Dispose, Finalizer, Method, Property, Delegates, Events, Exception, Lock, Error, Errors, Warning, Verbose, WriteLine, Data, Scope, ExecutionFlow, Assert, All

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="95779-199">-PSHost</span><span class="sxs-lookup"><span data-stu-id="95779-199">-PSHost</span></span>

<span data-ttu-id="95779-200">コマンドレットがトレース出力を PowerShell ホストに送信することを示します。</span><span class="sxs-lookup"><span data-stu-id="95779-200">Indicates that the cmdlet sends the trace output to the PowerShell host.</span></span> <span data-ttu-id="95779-201">このパラメーターは、PSHost トレース リスナーも選択します。</span><span class="sxs-lookup"><span data-stu-id="95779-201">This parameter also selects the PSHost trace listener.</span></span>

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

### <span data-ttu-id="95779-202">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="95779-202">CommonParameters</span></span>

<span data-ttu-id="95779-203">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="95779-203">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="95779-204">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95779-204">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="95779-205">入力</span><span class="sxs-lookup"><span data-stu-id="95779-205">INPUTS</span></span>

### <span data-ttu-id="95779-206">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="95779-206">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="95779-207">パイプを使用して、入力を表すオブジェクトをに渡し `Trace-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="95779-207">You can pipe objects that represent input to the expression to `Trace-Command`.</span></span>

## <span data-ttu-id="95779-208">出力</span><span class="sxs-lookup"><span data-stu-id="95779-208">OUTPUTS</span></span>

### <span data-ttu-id="95779-209">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="95779-209">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="95779-210">デバッグ ストリーム内にコマンド トレースを返します。</span><span class="sxs-lookup"><span data-stu-id="95779-210">Returns the command trace in the debug stream.</span></span>

## <span data-ttu-id="95779-211">注</span><span class="sxs-lookup"><span data-stu-id="95779-211">NOTES</span></span>

- <span data-ttu-id="95779-212">トレースは、開発者がプログラムをデバッグし、調整するために使用するメソッドです。</span><span class="sxs-lookup"><span data-stu-id="95779-212">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="95779-213">トレース時に、プログラムは、内部処理の各手順について詳細なメッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="95779-213">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

- <span data-ttu-id="95779-214">PowerShell トレースコマンドレットは、PowerShell 開発者を支援するように設計されていますが、すべてのユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="95779-214">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span> <span data-ttu-id="95779-215">シェルの機能のほとんどすべての側面を監視します。</span><span class="sxs-lookup"><span data-stu-id="95779-215">They let you monitor nearly every aspect of the functionality of the shell.</span></span>

- <span data-ttu-id="95779-216">トレースが有効になっている PowerShell コンポーネントを検索するには、「」と入力 `Get-Help Get-TraceSource` します。</span><span class="sxs-lookup"><span data-stu-id="95779-216">To find the PowerShell components that are enabled for tracing, type `Get-Help Get-TraceSource`.</span></span>

  <span data-ttu-id="95779-217">トレースソースは、トレースを管理し、コンポーネントのトレースメッセージを生成する各 PowerShell コンポーネントの一部です。</span><span class="sxs-lookup"><span data-stu-id="95779-217">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span> <span data-ttu-id="95779-218">コンポーネントをトレースするには、トレース ソースを特定します。</span><span class="sxs-lookup"><span data-stu-id="95779-218">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="95779-219">トレースリスナーは、トレースの出力を受信し、ユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="95779-219">A trace listener receives the output of the trace and displays it to the user.</span></span> <span data-ttu-id="95779-220">トレースデータは、ユーザーモードまたはカーネルモードのデバッガー、ホストまたはコンソール、ファイル、または **TraceListener** クラスから派生したカスタムリスナーに送信することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="95779-220">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the host or console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

- <span data-ttu-id="95779-221">CommandSet パラメーターセットを使用すると、PowerShell はパイプラインで処理されるのと同じようにコマンドを処理します。</span><span class="sxs-lookup"><span data-stu-id="95779-221">When you use the commandSet parameter set, PowerShell processes the command just as it would be processed in a pipeline.</span></span> <span data-ttu-id="95779-222">たとえば、コマンドの検出は、受信した各オブジェクトごとに繰り返されません。</span><span class="sxs-lookup"><span data-stu-id="95779-222">For example, command discovery is not repeated for each incoming object.</span></span>

- <span data-ttu-id="95779-223">**Name** 、 **Expression** 、 **Option** 、および **Command** パラメーターの名前は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="95779-223">The names of the **Name** , **Expression** , **Option** , and **Command** parameters are optional.</span></span> <span data-ttu-id="95779-224">パラメーター名を省略した場合、 **名前** 、 **式** 、 **オプション** 、または **名前** 、 **コマンド** 、 **オプション** の順に名前のないパラメーター値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="95779-224">If you omit the parameter names, the unnamed parameter values must appear in this order: **Name** , **Expression** , **Option** or **Name** , **Command** , **Option** .</span></span> <span data-ttu-id="95779-225">パラメーター名を指定する場合は、パラメーターの順序に決まりはありません。</span><span class="sxs-lookup"><span data-stu-id="95779-225">If you include the parameter names, the parameters can appear in any order.</span></span>

## <span data-ttu-id="95779-226">関連リンク</span><span class="sxs-lookup"><span data-stu-id="95779-226">RELATED LINKS</span></span>

[<span data-ttu-id="95779-227">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="95779-227">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="95779-228">Measure-Command</span><span class="sxs-lookup"><span data-stu-id="95779-228">Measure-Command</span></span>](Measure-Command.md)

[<span data-ttu-id="95779-229">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="95779-229">Set-TraceSource</span></span>](Set-TraceSource.md)

