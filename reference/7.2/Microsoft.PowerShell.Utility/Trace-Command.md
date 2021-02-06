---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/trace-command?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Trace-Command
ms.openlocfilehash: afc08b263d75f8a728ce6d64cc7ede0a639df196
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601410"
---
# <span data-ttu-id="1e1ee-102">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="1e1ee-102">Trace-Command</span></span>

## <span data-ttu-id="1e1ee-103">概要</span><span class="sxs-lookup"><span data-stu-id="1e1ee-103">SYNOPSIS</span></span>
<span data-ttu-id="1e1ee-104">指定された式またはコマンドのトレースを構成し、開始します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-104">Configures and starts a trace of the specified expression or command.</span></span>

## <span data-ttu-id="1e1ee-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1e1ee-105">SYNTAX</span></span>

### <span data-ttu-id="1e1ee-106">式セット (既定値)</span><span class="sxs-lookup"><span data-stu-id="1e1ee-106">expressionSet (Default)</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Expression] <ScriptBlock> [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force] [-Debugger]
 [-PSHost] [<CommonParameters>]
```

### <span data-ttu-id="1e1ee-107">commandSet</span><span class="sxs-lookup"><span data-stu-id="1e1ee-107">commandSet</span></span>

```
Trace-Command [-InputObject <PSObject>] [-Name] <String[]> [[-Option] <PSTraceSourceOptions>]
 [-Command] <String> [-ArgumentList <Object[]>] [-ListenerOption <TraceOptions>] [-FilePath <String>] [-Force]
 [-Debugger] [-PSHost] [<CommonParameters>]
```

## <span data-ttu-id="1e1ee-108">Description</span><span class="sxs-lookup"><span data-stu-id="1e1ee-108">DESCRIPTION</span></span>
<span data-ttu-id="1e1ee-109">`Trace-Command`コマンドレットは、指定された式またはコマンドのトレースを構成し、開始します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-109">The `Trace-Command` cmdlet configures and starts a trace of the specified expression or command.</span></span>
<span data-ttu-id="1e1ee-110">Set-TraceSource と同様に機能しますが、指定されたコマンドにのみ適用される点が異なります。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-110">It works like Set-TraceSource, except that it applies only to the specified command.</span></span>

## <span data-ttu-id="1e1ee-111">例</span><span class="sxs-lookup"><span data-stu-id="1e1ee-111">EXAMPLES</span></span>

### <span data-ttu-id="1e1ee-112">例 1: メタデータの処理、パラメーターのバインド、および式をトレースする</span><span class="sxs-lookup"><span data-stu-id="1e1ee-112">Example 1: Trace metadata processing, parameter binding, and an expression</span></span>

<span data-ttu-id="1e1ee-113">この例では、メタデータの処理、パラメーターのバインド、およびコマンドレットの作成と式の破棄のトレースを開始し `Get-Process Notepad` ます。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-113">This example starts a trace of metadata processing, parameter binding, and cmdlet creation and destruction of the `Get-Process Notepad` expression.</span></span>

```powershell
Trace-Command -Name metadata,parameterbinding,cmdlet -Expression {Get-Process Notepad} -PSHost
```

<span data-ttu-id="1e1ee-114">**Name** パラメーターを使用してトレースソースを指定し、 **Expression** パラメーターでコマンドを指定し、 **PSHost** パラメーターを使用して出力をコンソールに送信します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-114">It uses the **Name** parameter to specify the trace sources, the **Expression** parameter to specify the command, and the **PSHost** parameter to send the output to the console.</span></span> <span data-ttu-id="1e1ee-115">トレースオプションまたはリスナーオプションは指定されていないため、コマンドは既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-115">Because it does not specify any tracing options or listener options, the command uses the defaults:</span></span>

- <span data-ttu-id="1e1ee-116">トレースオプションのすべて</span><span class="sxs-lookup"><span data-stu-id="1e1ee-116">All for the tracing options</span></span>
- <span data-ttu-id="1e1ee-117">リスナーオプションの場合は None</span><span class="sxs-lookup"><span data-stu-id="1e1ee-117">None for the listener options</span></span>

### <span data-ttu-id="1e1ee-118">例 2: ParameterBinding 操作のアクションをトレースする</span><span class="sxs-lookup"><span data-stu-id="1e1ee-118">Example 2: Trace the actions of ParameterBinding operations</span></span>

<span data-ttu-id="1e1ee-119">この例では、パイプラインからの入力を受け取る式を処理するときに、PowerShell の **Parameterbinding** 操作のアクションをトレース `Get-Alias` します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-119">This example traces the actions of the **ParameterBinding** operations of PowerShell while it processes a `Get-Alias` expression that takes input from the pipeline.</span></span>

```powershell
$A = "i*"
Trace-Command ParameterBinding {Get-Alias $Input} -PSHost -InputObject $A
```

<span data-ttu-id="1e1ee-120">では `Trace-Command` 、 **InputObject** パラメーターは、トレース中に処理される式にオブジェクトを渡します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-120">In `Trace-Command`, the **InputObject** parameter passes an object to the expression that is being processed during the trace.</span></span>

<span data-ttu-id="1e1ee-121">最初のコマンドは、変数に文字列を格納し `i*` `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-121">The first command stores the string `i*` in the `$A` variable.</span></span> <span data-ttu-id="1e1ee-122">2番目のコマンドは、 `Trace-Command` ParameterBinding トレースソースと共にコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-122">The second command uses the `Trace-Command` cmdlet with the ParameterBinding trace source.</span></span> <span data-ttu-id="1e1ee-123">**PSHost** パラメーターを指定すると、出力がコンソールに送信されます。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-123">The **PSHost** parameter sends the output to the console.</span></span>

<span data-ttu-id="1e1ee-124">処理される式はです `Get-Alias $Input` 。ここで、 `$Input` 変数は **InputObject** パラメーターに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-124">The expression being processed is `Get-Alias $Input`, where the `$Input` variable is associated with the **InputObject** parameter.</span></span> <span data-ttu-id="1e1ee-125">**InputObject** パラメーターは、変数 `$A` を式に渡します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-125">The **InputObject** parameter passes the variable `$A` to the expression.</span></span> <span data-ttu-id="1e1ee-126">実際には、トレース中に処理されるコマンドは `Get-Alias -InputObject $A" or "$A | Get-Alias` です。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-126">In effect, the command being processed during the trace is `Get-Alias -InputObject $A" or "$A | Get-Alias`.</span></span>

## <span data-ttu-id="1e1ee-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1e1ee-127">PARAMETERS</span></span>

### <span data-ttu-id="1e1ee-128">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="1e1ee-128">-ArgumentList</span></span>

<span data-ttu-id="1e1ee-129">トレースするコマンドのパラメーターとパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-129">Specifies the parameters and parameter values for the command being traced.</span></span> <span data-ttu-id="1e1ee-130">**ArgumentList** のエイリアスは、**Args** です。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-130">The alias for **ArgumentList** is **Args**.</span></span> <span data-ttu-id="1e1ee-131">この機能は、動的パラメーターをデバッグする場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-131">This feature is especially useful for debugging dynamic parameters.</span></span>

<span data-ttu-id="1e1ee-132">**ArgumentList** の動作の詳細については、「 [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-132">For more information about the behavior of **ArgumentList**, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span></span>

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

### <span data-ttu-id="1e1ee-133">-Command</span><span class="sxs-lookup"><span data-stu-id="1e1ee-133">-Command</span></span>

<span data-ttu-id="1e1ee-134">トレース中に処理するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-134">Specifies a command that is being processed during the trace.</span></span>

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

### <span data-ttu-id="1e1ee-135">-デバッガー</span><span class="sxs-lookup"><span data-stu-id="1e1ee-135">-Debugger</span></span>

<span data-ttu-id="1e1ee-136">コマンドレットがトレース出力をデバッガーに送信することを示します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-136">Indicates that the cmdlet sends the trace output to the debugger.</span></span> <span data-ttu-id="1e1ee-137">出力はユーザー モードまたはカーネル モードのデバッガーや、Visual Studio で表示することができます。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-137">You can view the output in any user-mode or kernel mode debugger or in Visual Studio.</span></span> <span data-ttu-id="1e1ee-138">このパラメーターは、既定のトレース リスナーも選択します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-138">This parameter also selects the default trace listener.</span></span>

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

### <span data-ttu-id="1e1ee-139">-式</span><span class="sxs-lookup"><span data-stu-id="1e1ee-139">-Expression</span></span>

<span data-ttu-id="1e1ee-140">トレース中に処理する式を指定します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-140">Specifies the expression that is being processed during the trace.</span></span> <span data-ttu-id="1e1ee-141">式を中かっこ () で囲み `{}` ます。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-141">Enclose the expression in braces (`{}`).</span></span>

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

### <span data-ttu-id="1e1ee-142">-FilePath</span><span class="sxs-lookup"><span data-stu-id="1e1ee-142">-FilePath</span></span>

<span data-ttu-id="1e1ee-143">コマンドレットがトレース出力を送信するファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-143">Specifies a file that the cmdlet sends the trace output to.</span></span> <span data-ttu-id="1e1ee-144">このパラメーターは、ファイル トレース リスナーも選択します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-144">This parameter also selects the file trace listener.</span></span>

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

### <span data-ttu-id="1e1ee-145">-Force</span><span class="sxs-lookup"><span data-stu-id="1e1ee-145">-Force</span></span>

<span data-ttu-id="1e1ee-146">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-146">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="1e1ee-147">**FilePath** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-147">Used with the **FilePath** parameter.</span></span> <span data-ttu-id="1e1ee-148">**Force** パラメーターを使用しても、コマンドレットはセキュリティ制限を上書きできません。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-148">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="1e1ee-149">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1e1ee-149">-InputObject</span></span>

<span data-ttu-id="1e1ee-150">トレース中に処理される式への入力を指定します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-150">Specifies input to the expression that is being processed during the trace.</span></span> <span data-ttu-id="1e1ee-151">式が受け取る入力を表した変数を入力するか、パイプラインを通じてオブジェクトを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-151">You can enter a variable that represents the input that the expression accepts, or pass an object through the pipeline.</span></span>

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

### <span data-ttu-id="1e1ee-152">-ListenerOption</span><span class="sxs-lookup"><span data-stu-id="1e1ee-152">-ListenerOption</span></span>

<span data-ttu-id="1e1ee-153">出力の各トレースメッセージのプレフィックスにオプションのデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-153">Specifies optional data to the prefix of each trace message in the output.</span></span> <span data-ttu-id="1e1ee-154">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-154">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1e1ee-155">なし</span><span class="sxs-lookup"><span data-stu-id="1e1ee-155">None</span></span>
- <span data-ttu-id="1e1ee-156">LogicalOperationStack</span><span class="sxs-lookup"><span data-stu-id="1e1ee-156">LogicalOperationStack</span></span>
- <span data-ttu-id="1e1ee-157">DateTime</span><span class="sxs-lookup"><span data-stu-id="1e1ee-157">DateTime</span></span>
- <span data-ttu-id="1e1ee-158">Timestamp</span><span class="sxs-lookup"><span data-stu-id="1e1ee-158">Timestamp</span></span>
- <span data-ttu-id="1e1ee-159">ProcessId</span><span class="sxs-lookup"><span data-stu-id="1e1ee-159">ProcessId</span></span>
- <span data-ttu-id="1e1ee-160">スレッド Id</span><span class="sxs-lookup"><span data-stu-id="1e1ee-160">ThreadId</span></span>
- <span data-ttu-id="1e1ee-161">呼び出し履歴</span><span class="sxs-lookup"><span data-stu-id="1e1ee-161">Callstack</span></span>

<span data-ttu-id="1e1ee-162">**[なし]** が既定値です。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-162">**None** is the default.</span></span>

<span data-ttu-id="1e1ee-163">複数のオプションを指定するには、スペースなしで、コンマで区切り、"ProcessID,ThreadID" のように引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-163">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "ProcessID,ThreadID".</span></span>

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

### <span data-ttu-id="1e1ee-164">-Name</span><span class="sxs-lookup"><span data-stu-id="1e1ee-164">-Name</span></span>

<span data-ttu-id="1e1ee-165">トレースされる PowerShell コンポーネントの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-165">Specifies an array of PowerShell components that are traced.</span></span> <span data-ttu-id="1e1ee-166">各コンポーネントのトレース ソースの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-166">Enter the name of the trace source of each component.</span></span> <span data-ttu-id="1e1ee-167">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-167">Wildcards are permitted.</span></span> <span data-ttu-id="1e1ee-168">コンピューター上のトレースソースを検索するには、「」と入力 `Get-TraceSource` します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-168">To find the trace sources on your computer, type `Get-TraceSource`.</span></span>

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

### <span data-ttu-id="1e1ee-169">-Option</span><span class="sxs-lookup"><span data-stu-id="1e1ee-169">-Option</span></span>

<span data-ttu-id="1e1ee-170">トレース対象のイベントの種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-170">Determines the type of events that are traced.</span></span> <span data-ttu-id="1e1ee-171">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-171">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1e1ee-172">なし</span><span class="sxs-lookup"><span data-stu-id="1e1ee-172">None</span></span>
- <span data-ttu-id="1e1ee-173">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="1e1ee-173">Constructor</span></span>
- <span data-ttu-id="1e1ee-174">Dispose</span><span class="sxs-lookup"><span data-stu-id="1e1ee-174">Dispose</span></span>
- <span data-ttu-id="1e1ee-175">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="1e1ee-175">Finalizer</span></span>
- <span data-ttu-id="1e1ee-176">メソッド</span><span class="sxs-lookup"><span data-stu-id="1e1ee-176">Method</span></span>
- <span data-ttu-id="1e1ee-177">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e1ee-177">Property</span></span>
- <span data-ttu-id="1e1ee-178">デリゲート</span><span class="sxs-lookup"><span data-stu-id="1e1ee-178">Delegates</span></span>
- <span data-ttu-id="1e1ee-179">イベント</span><span class="sxs-lookup"><span data-stu-id="1e1ee-179">Events</span></span>
- <span data-ttu-id="1e1ee-180">例外</span><span class="sxs-lookup"><span data-stu-id="1e1ee-180">Exception</span></span>
- <span data-ttu-id="1e1ee-181">ロック</span><span class="sxs-lookup"><span data-stu-id="1e1ee-181">Lock</span></span>
- <span data-ttu-id="1e1ee-182">エラー</span><span class="sxs-lookup"><span data-stu-id="1e1ee-182">Error</span></span>
- <span data-ttu-id="1e1ee-183">エラー</span><span class="sxs-lookup"><span data-stu-id="1e1ee-183">Errors</span></span>
- <span data-ttu-id="1e1ee-184">警告</span><span class="sxs-lookup"><span data-stu-id="1e1ee-184">Warning</span></span>
- <span data-ttu-id="1e1ee-185">"詳細"</span><span class="sxs-lookup"><span data-stu-id="1e1ee-185">Verbose</span></span>
- <span data-ttu-id="1e1ee-186">WriteLine</span><span class="sxs-lookup"><span data-stu-id="1e1ee-186">WriteLine</span></span>
- <span data-ttu-id="1e1ee-187">データ</span><span class="sxs-lookup"><span data-stu-id="1e1ee-187">Data</span></span>
- <span data-ttu-id="1e1ee-188">Scope</span><span class="sxs-lookup"><span data-stu-id="1e1ee-188">Scope</span></span>
- <span data-ttu-id="1e1ee-189">ExecutionFlow</span><span class="sxs-lookup"><span data-stu-id="1e1ee-189">ExecutionFlow</span></span>
- <span data-ttu-id="1e1ee-190">Assert</span><span class="sxs-lookup"><span data-stu-id="1e1ee-190">Assert</span></span>
- <span data-ttu-id="1e1ee-191">すべて</span><span class="sxs-lookup"><span data-stu-id="1e1ee-191">All</span></span>

<span data-ttu-id="1e1ee-192">ALL が既定値です。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-192">All is the default.</span></span>

<span data-ttu-id="1e1ee-193">次の値はその他の値の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-193">The following values are combinations of other values:</span></span>

- <span data-ttu-id="1e1ee-194">ExecutionFlow: (コンストラクター、Dispose、ファイナライザー、メソッド、デリゲート、イベント、およびスコープ)</span><span class="sxs-lookup"><span data-stu-id="1e1ee-194">ExecutionFlow: (Constructor, Dispose, Finalizer, Method, Delegates, Events, and Scope)</span></span>
- <span data-ttu-id="1e1ee-195">データ: (コンストラクター、Dispose、ファイナライザー、プロパティ、Verbose、および WriteLine)</span><span class="sxs-lookup"><span data-stu-id="1e1ee-195">Data: (Constructor, Dispose, Finalizer, Property, Verbose, and WriteLine)</span></span>
- <span data-ttu-id="1e1ee-196">エラー: (エラーと例外)。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-196">Errors: (Error and Exception).</span></span>

<span data-ttu-id="1e1ee-197">複数のオプションを指定するには、スペースなしで、コンマで区切り、"Constructor,Dispose" のように引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-197">To specify multiple options, separate them with commas, but with no spaces, and enclose them in quotation marks, such as "Constructor,Dispose".</span></span>

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

### <span data-ttu-id="1e1ee-198">-PSHost</span><span class="sxs-lookup"><span data-stu-id="1e1ee-198">-PSHost</span></span>

<span data-ttu-id="1e1ee-199">コマンドレットがトレース出力を PowerShell ホストに送信することを示します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-199">Indicates that the cmdlet sends the trace output to the PowerShell host.</span></span> <span data-ttu-id="1e1ee-200">このパラメーターは、PSHost トレース リスナーも選択します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-200">This parameter also selects the PSHost trace listener.</span></span>

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

### <span data-ttu-id="1e1ee-201">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e1ee-201">CommonParameters</span></span>

<span data-ttu-id="1e1ee-202">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-202">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1e1ee-203">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-203">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1e1ee-204">入力</span><span class="sxs-lookup"><span data-stu-id="1e1ee-204">INPUTS</span></span>

### <span data-ttu-id="1e1ee-205">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="1e1ee-205">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="1e1ee-206">パイプを使用して、入力を表すオブジェクトをに渡し `Trace-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-206">You can pipe objects that represent input to the expression to `Trace-Command`.</span></span>

## <span data-ttu-id="1e1ee-207">出力</span><span class="sxs-lookup"><span data-stu-id="1e1ee-207">OUTPUTS</span></span>

### <span data-ttu-id="1e1ee-208">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="1e1ee-208">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="1e1ee-209">デバッグ ストリーム内にコマンド トレースを返します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-209">Returns the command trace in the debug stream.</span></span>

## <span data-ttu-id="1e1ee-210">注</span><span class="sxs-lookup"><span data-stu-id="1e1ee-210">NOTES</span></span>

- <span data-ttu-id="1e1ee-211">トレースは、開発者がプログラムをデバッグし、調整するために使用するメソッドです。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-211">Tracing is a method that developers use to debug and refine programs.</span></span> <span data-ttu-id="1e1ee-212">トレース時に、プログラムは、内部処理の各手順について詳細なメッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-212">When tracing, the program generates detailed messages about each step in its internal processing.</span></span>

- <span data-ttu-id="1e1ee-213">PowerShell トレースコマンドレットは、PowerShell 開発者を支援するように設計されていますが、すべてのユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-213">The PowerShell tracing cmdlets are designed to help PowerShell developers, but they are available to all users.</span></span> <span data-ttu-id="1e1ee-214">シェルの機能のほとんどすべての側面を監視します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-214">They let you monitor nearly every aspect of the functionality of the shell.</span></span>

- <span data-ttu-id="1e1ee-215">トレースが有効になっている PowerShell コンポーネントを検索するには、「」と入力 `Get-Help Get-TraceSource` します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-215">To find the PowerShell components that are enabled for tracing, type `Get-Help Get-TraceSource`.</span></span>

  <span data-ttu-id="1e1ee-216">トレースソースは、トレースを管理し、コンポーネントのトレースメッセージを生成する各 PowerShell コンポーネントの一部です。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-216">A trace source is the part of each PowerShell component that manages tracing and generates trace messages for the component.</span></span> <span data-ttu-id="1e1ee-217">コンポーネントをトレースするには、トレース ソースを特定します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-217">To trace a component, you identify its trace source.</span></span>

  <span data-ttu-id="1e1ee-218">トレースリスナーは、トレースの出力を受信し、ユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-218">A trace listener receives the output of the trace and displays it to the user.</span></span> <span data-ttu-id="1e1ee-219">トレースデータは、ユーザーモードまたはカーネルモードのデバッガー、ホストまたはコンソール、ファイル、または **TraceListener** クラスから派生したカスタムリスナーに送信することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-219">You can elect to send the trace data to a user-mode or kernel-mode debugger, to the host or console, to a file, or to a custom listener derived from the **System.Diagnostics.TraceListener** class.</span></span>

- <span data-ttu-id="1e1ee-220">CommandSet パラメーターセットを使用すると、PowerShell はパイプラインで処理されるのと同じようにコマンドを処理します。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-220">When you use the commandSet parameter set, PowerShell processes the command just as it would be processed in a pipeline.</span></span> <span data-ttu-id="1e1ee-221">たとえば、コマンドの検出は、受信した各オブジェクトごとに繰り返されません。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-221">For example, command discovery is not repeated for each incoming object.</span></span>

- <span data-ttu-id="1e1ee-222">**Name**、 **Expression**、 **Option**、および **Command** パラメーターの名前は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-222">The names of the **Name**, **Expression**, **Option**, and **Command** parameters are optional.</span></span> <span data-ttu-id="1e1ee-223">パラメーター名を省略した場合、 **名前**、 **式**、 **オプション** 、または **名前**、 **コマンド**、 **オプション** の順に名前のないパラメーター値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-223">If you omit the parameter names, the unnamed parameter values must appear in this order: **Name**, **Expression**, **Option** or **Name**, **Command**, **Option**.</span></span> <span data-ttu-id="1e1ee-224">パラメーター名を指定する場合は、パラメーターの順序に決まりはありません。</span><span class="sxs-lookup"><span data-stu-id="1e1ee-224">If you include the parameter names, the parameters can appear in any order.</span></span>

## <span data-ttu-id="1e1ee-225">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1e1ee-225">RELATED LINKS</span></span>

[<span data-ttu-id="1e1ee-226">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="1e1ee-226">Get-TraceSource</span></span>](Get-TraceSource.md)

[<span data-ttu-id="1e1ee-227">Measure-Command</span><span class="sxs-lookup"><span data-stu-id="1e1ee-227">Measure-Command</span></span>](Measure-Command.md)

[<span data-ttu-id="1e1ee-228">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="1e1ee-228">Set-TraceSource</span></span>](Set-TraceSource.md)

