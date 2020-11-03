---
description: 属性を指定する関数 `CmdletBinding` が、コンパイルされたコマンドレットで使用できるメソッドとプロパティを使用する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced_methods?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced_Methods
ms.openlocfilehash: 862c57d326049096ada28353b74485f8519f46da
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93224056"
---
# <a name="about-functions-advanced-methods"></a><span data-ttu-id="9eaa0-104">Functions の詳細なメソッドについて</span><span class="sxs-lookup"><span data-stu-id="9eaa0-104">About Functions Advanced Methods</span></span>

## <a name="short-description"></a><span data-ttu-id="9eaa0-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="9eaa0-105">Short description</span></span>

<span data-ttu-id="9eaa0-106">属性を指定する関数 `CmdletBinding` が、コンパイルされたコマンドレットで使用できるメソッドとプロパティを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-106">Describes how functions that specify the `CmdletBinding` attribute can use the methods and properties that are available to compiled cmdlets.</span></span>

## <a name="long-description"></a><span data-ttu-id="9eaa0-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="9eaa0-107">Long description</span></span>

<span data-ttu-id="9eaa0-108">属性を指定する関数 `CmdletBinding` は、変数を通じて多数のメソッドとプロパティにアクセスでき `$PSCmdlet` ます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-108">Functions that specify the `CmdletBinding` attribute can access a number of methods and properties through the `$PSCmdlet` variable.</span></span> <span data-ttu-id="9eaa0-109">これらのメソッドには、次のメソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-109">These methods include the following methods:</span></span>

- <span data-ttu-id="9eaa0-110">コンパイルされたコマンドレットが作業を行うために使用する入力処理メソッド。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-110">Input-processing methods that compiled cmdlets use to do their work.</span></span>
- <span data-ttu-id="9eaa0-111">`ShouldProcess` `ShouldContinue` アクションが実行される前にユーザーフィードバックを取得するために使用されるメソッドとメソッド。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-111">The `ShouldProcess` and `ShouldContinue` methods that are used to get user feedback before an action is performed.</span></span>
- <span data-ttu-id="9eaa0-112">`ThrowTerminatingError`エラーレコードを生成するメソッド。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-112">The `ThrowTerminatingError` method for generating error records.</span></span>
- <span data-ttu-id="9eaa0-113">`Write`さまざまな種類の出力を返すメソッドがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-113">Several `Write` methods that return different types of output.</span></span>

<span data-ttu-id="9eaa0-114">**PSCmdlet** クラスのすべてのメソッドとプロパティは、高度な関数で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-114">All the methods and properties of the **PSCmdlet** class are available to advanced functions.</span></span> <span data-ttu-id="9eaa0-115">詳細については、「 [PSCmdlet](/dotnet/api/system.management.automation.pscmdlet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-115">For more information, see [System.Management.Automation.PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span></span>

<span data-ttu-id="9eaa0-116">属性の詳細については `CmdletBinding` 、「 [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-116">For more information about the `CmdletBinding` attribute, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>
<span data-ttu-id="9eaa0-117">[コマンド](/dotnet/api/system.management.automation.cmdletbindingattribute)レット **bindingattribute** クラスについては、「system.string」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-117">For the **CmdletBindingAttribute** class, see [System.Management.Automation.Cmdlet.CmdletBindingAttribute](/dotnet/api/system.management.automation.cmdletbindingattribute).</span></span>

### <a name="input-processing-methods"></a><span data-ttu-id="9eaa0-118">入力処理メソッド</span><span class="sxs-lookup"><span data-stu-id="9eaa0-118">Input processing methods</span></span>

<span data-ttu-id="9eaa0-119">このセクションで説明するメソッドは、入力処理メソッドと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-119">The methods described in this section are referred to as the input processing methods.</span></span> <span data-ttu-id="9eaa0-120">関数の場合、これら3つのメソッドは `Begin` 、 `Process` 関数の、、およびの各ブロックによって表され `End` ます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-120">For functions, these three methods are represented by the `Begin`, `Process`, and `End` blocks of the function.</span></span> <span data-ttu-id="9eaa0-121">関数でこれらのブロックを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-121">You aren't required to use any of these blocks in your functions.</span></span>

> [!NOTE]
> <span data-ttu-id="9eaa0-122">これらのブロックは、属性を使用しない関数でも使用でき `CmdletBinding` ます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-122">These blocks are also available to functions that don't use the `CmdletBinding` attribute.</span></span>

#### <a name="begin"></a><span data-ttu-id="9eaa0-123">開始</span><span class="sxs-lookup"><span data-stu-id="9eaa0-123">Begin</span></span>

<span data-ttu-id="9eaa0-124">このブロックは、関数に対してオプションの1回限りの前処理を行うために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-124">This block is used to provide optional one-time preprocessing for the function.</span></span>
<span data-ttu-id="9eaa0-125">PowerShell ランタイムは、パイプライン内の関数の各インスタンスに対して、このブロック内のコードを1回使用します。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-125">The PowerShell runtime uses the code in this block once for each instance of the function in the pipeline.</span></span>

#### <a name="process"></a><span data-ttu-id="9eaa0-126">プロセス</span><span class="sxs-lookup"><span data-stu-id="9eaa0-126">Process</span></span>

<span data-ttu-id="9eaa0-127">このブロックは、関数のレコードごとの処理を提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-127">This block is used to provide record-by-record processing for the function.</span></span> <span data-ttu-id="9eaa0-128">`Process`ブロックは、他のブロックを定義することなく使用できます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-128">You can use a `Process` block without defining the other blocks.</span></span> <span data-ttu-id="9eaa0-129">ブロックの実行回数は、 `Process` 関数の使用方法と、関数が受け取る入力によって異なります。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-129">The number of `Process` block executions depends on how you use the function and what input the function receives.</span></span>

<span data-ttu-id="9eaa0-130">自動変数 `$_` またはは、 `$PSItem` ブロックで使用するために、パイプライン内の現在のオブジェクトを格納し `Process` ます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-130">The automatic variable `$_` or `$PSItem` contains the current object in the pipeline for use in the `Process` block.</span></span> <span data-ttu-id="9eaa0-131">自動変数には、 `$input` 関数とスクリプトブロックでのみ使用できる列挙子が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-131">The `$input` automatic variable contains an enumerator that's only available to functions and script blocks.</span></span>
<span data-ttu-id="9eaa0-132">詳細については、「 [about_Automatic_Variables](about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-132">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

- <span data-ttu-id="9eaa0-133">パイプラインの先頭または外部で関数を呼び出すと、ブロックが `Process` 1 回実行されます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-133">Calling the function at the beginning, or outside of a pipeline, executes the `Process` block once.</span></span>
- <span data-ttu-id="9eaa0-134">パイプライン内では、 `Process` ブロックは、関数に到達した入力オブジェクトごとに1回実行されます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-134">Within a pipeline, the `Process` block executes once for each input object that reaches the function.</span></span>
- <span data-ttu-id="9eaa0-135">関数に到達したパイプライン入力が空の場合、 `Process` ブロックは実行 **されません** 。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-135">If the pipeline input that reaches the function is empty, the `Process` block **does not** execute.</span></span>
  - <span data-ttu-id="9eaa0-136">`Begin`ブロックとブロックは依然として `End` 実行されます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-136">The `Begin` and `End` blocks still execute.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9eaa0-137">関数パラメーターがパイプライン入力を受け入れるように設定されていて、ブロックが定義されていない場合 `Process` 、レコードごとの処理は失敗します。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-137">If a function parameter is set to accept pipeline input, and a `Process` block isn't defined, record-by-record processing will fail.</span></span> <span data-ttu-id="9eaa0-138">この場合、関数は、入力に関係なく、1回だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-138">In this case, your function will only execute once, regardless of the input.</span></span>

#### <a name="end"></a><span data-ttu-id="9eaa0-139">End</span><span class="sxs-lookup"><span data-stu-id="9eaa0-139">End</span></span>

<span data-ttu-id="9eaa0-140">このブロックは、関数に対して省略可能な1回限りの後処理を提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-140">This block is used to provide optional one-time post-processing for the function.</span></span>

<span data-ttu-id="9eaa0-141">次の例は、 `Begin` 1 回限りの前処理のブロック、 `Process` 複数のレコード処理のブロック、および1回限りの後処理のブロックを含む関数の概要を示してい `End` ます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-141">The following example shows the outline of a function that contains a `Begin` block for one-time preprocessing, a `Process` block for multiple record processing, and an `End` block for one-time post-processing.</span></span>

```powershell
Function Test-ScriptCmdlet
{
[CmdletBinding(SupportsShouldProcess=$True)]
    Param ($Parameter1)
    Begin{}
    Process{}
    End{}
}
```

> [!NOTE]
> <span data-ttu-id="9eaa0-142">またはブロックのいずれかを使用する `Begin` には、 `End` 3 つのブロックをすべて定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-142">Using either a `Begin` or `End` block requires that you define all three blocks.</span></span> <span data-ttu-id="9eaa0-143">3つすべてのブロックを使用する場合は、すべての PowerShell コードがいずれかのブロックに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-143">When using all three blocks, all PowerShell code must be inside one of the blocks.</span></span>

### <a name="confirmation-methods"></a><span data-ttu-id="9eaa0-144">確認方法</span><span class="sxs-lookup"><span data-stu-id="9eaa0-144">Confirmation methods</span></span>

#### <a name="shouldprocess"></a><span data-ttu-id="9eaa0-145">ShouldProcess</span><span class="sxs-lookup"><span data-stu-id="9eaa0-145">ShouldProcess</span></span>

<span data-ttu-id="9eaa0-146">このメソッドは、システムを変更するアクションを実行する前に、ユーザーからの確認を要求するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-146">This method is called to request confirmation from the user before the function performs an action that would change the system.</span></span> <span data-ttu-id="9eaa0-147">関数は、メソッドによって返されるブール値に基づいて続行できます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-147">The function can continue based on the Boolean value returned by the method.</span></span> <span data-ttu-id="9eaa0-148">このメソッドを呼び出すことができるのは `Process{}` 、関数のブロック内からだけです。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-148">This method can only be called only from within the `Process{}` block of the function.</span></span> <span data-ttu-id="9eaa0-149">また、属性は、 `CmdletBinding` 関数が (前の例で示したように) をサポートすることも宣言する必要があり `ShouldProcess` ます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-149">The `CmdletBinding` attribute must also declare that the function supports `ShouldProcess` (as shown in the previous example).</span></span>

<span data-ttu-id="9eaa0-150">このメソッドの詳細については、「 [システムの管理](/dotnet/api/system.management.automation.cmdlet.shouldprocess)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-150">For more information about this method, see [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/system.management.automation.cmdlet.shouldprocess).</span></span>

<span data-ttu-id="9eaa0-151">確認を要求する方法の詳細については、「 [確認](/powershell/scripting/developer/cmdlet/requesting-confirmation)の要求」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-151">For more information about how to request confirmation, see [Requesting Confirmation](/powershell/scripting/developer/cmdlet/requesting-confirmation).</span></span>

#### <a name="shouldcontinue"></a><span data-ttu-id="9eaa0-152">ShouldContinue</span><span class="sxs-lookup"><span data-stu-id="9eaa0-152">ShouldContinue</span></span>

<span data-ttu-id="9eaa0-153">このメソッドは、2番目の確認メッセージを要求するために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-153">This method is called to request a second confirmation message.</span></span> <span data-ttu-id="9eaa0-154">メソッドから制御が戻ったときに呼び出す必要があり `ShouldProcess` `$true` ます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-154">It should be called when the `ShouldProcess` method returns `$true`.</span></span> <span data-ttu-id="9eaa0-155">このメソッドの詳細については、「 [システムの管理](/dotnet/api/system.management.automation.cmdlet.shouldcontinue)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-155">For more information about this method, see [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/system.management.automation.cmdlet.shouldcontinue).</span></span>

### <a name="error-methods"></a><span data-ttu-id="9eaa0-156">エラーメソッド</span><span class="sxs-lookup"><span data-stu-id="9eaa0-156">Error methods</span></span>

<span data-ttu-id="9eaa0-157">関数は、エラーが発生したときに2つの異なるメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-157">Functions can call two different methods when errors occur.</span></span> <span data-ttu-id="9eaa0-158">終了しないエラーが発生した場合、関数はメソッドを呼び出す必要があり `WriteError` ます。これについては、 `Write` 「メソッド」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-158">When a non-terminating error occurs, the function should call the `WriteError` method, which is described in the `Write` methods section.</span></span> <span data-ttu-id="9eaa0-159">終了エラーが発生し、関数を続行できない場合は、メソッドを呼び出す必要があり `ThrowTerminatingError` ます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-159">When a terminating error occurs and the function can't continue, it should call the `ThrowTerminatingError` method.</span></span> <span data-ttu-id="9eaa0-160">また、ステートメントを使用して `Throw` エラーを終了し、 [書き込みエラー](xref:Microsoft.PowerShell.Utility.Write-Error) コマンドレットを使用して、終了しないエラーを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-160">You can also use the `Throw` statement for terminating errors and the [Write-Error](xref:Microsoft.PowerShell.Utility.Write-Error) cmdlet for non-terminating errors.</span></span>

<span data-ttu-id="9eaa0-161">詳細については、「 [ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-161">For more information, see [System.Management.Automation.Cmdlet.ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror).</span></span>

### <a name="write-methods"></a><span data-ttu-id="9eaa0-162">メソッドの書き込み</span><span class="sxs-lookup"><span data-stu-id="9eaa0-162">Write methods</span></span>

<span data-ttu-id="9eaa0-163">関数は、次のメソッドを呼び出して、異なる種類の出力を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-163">A function can call the following methods to return different types of output.</span></span>
<span data-ttu-id="9eaa0-164">すべての出力がパイプラインの次のコマンドに送られているわけではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-164">Notice that not all the output goes to the next command in the pipeline.</span></span> <span data-ttu-id="9eaa0-165">などのさまざまなコマンドレットを使用することもでき `Write` `Write-Error` ます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-165">You can also use the various `Write` cmdlets, such as `Write-Error`.</span></span>

#### <a name="writecommanddetail"></a><span data-ttu-id="9eaa0-166">WriteCommandDetail</span><span class="sxs-lookup"><span data-stu-id="9eaa0-166">WriteCommandDetail</span></span>

<span data-ttu-id="9eaa0-167">メソッドの詳細については `WriteCommandDetails` 、「 [WriteCommandDetail](/dotnet/api/system.management.automation.cmdlet.writecommanddetail)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-167">For information about the `WriteCommandDetails` method, see [System.Management.Automation.Cmdlet.WriteCommandDetail](/dotnet/api/system.management.automation.cmdlet.writecommanddetail).</span></span>

#### <a name="writedebug"></a><span data-ttu-id="9eaa0-168">WriteDebug</span><span class="sxs-lookup"><span data-stu-id="9eaa0-168">WriteDebug</span></span>

<span data-ttu-id="9eaa0-169">関数のトラブルシューティングに使用できる情報を提供するには、関数がメソッドを呼び出すようにし `WriteDebug` ます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-169">To provide information that can be used to troubleshoot a function, make the function call the `WriteDebug` method.</span></span> <span data-ttu-id="9eaa0-170">メソッドは、 `WriteDebug` ユーザーにデバッグメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-170">The `WriteDebug` method displays debug messages to the user.</span></span> <span data-ttu-id="9eaa0-171">詳細については [、「system.string](/dotnet/api/system.management.automation.cmdlet.writedebug)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-171">For more information, see [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/system.management.automation.cmdlet.writedebug).</span></span>

#### <a name="writeerror"></a><span data-ttu-id="9eaa0-172">WriteError</span><span class="sxs-lookup"><span data-stu-id="9eaa0-172">WriteError</span></span>

<span data-ttu-id="9eaa0-173">関数は、終了しないエラーが発生し、関数がレコードの処理を続行するように設計されている場合に、このメソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-173">Functions should call this method when non-terminating errors occur and the function is designed to continue processing records.</span></span> <span data-ttu-id="9eaa0-174">詳細については、「 [WriteError](/dotnet/api/system.management.automation.cmdlet.writeerror)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-174">For more information, see [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/system.management.automation.cmdlet.writeerror).</span></span>

> [!NOTE]
> <span data-ttu-id="9eaa0-175">終了エラーが発生した場合、関数は [ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror) メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-175">If a terminating error occurs, the function should call the [ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror) method.</span></span>

#### <a name="writeobject"></a><span data-ttu-id="9eaa0-176">WriteObject</span><span class="sxs-lookup"><span data-stu-id="9eaa0-176">WriteObject</span></span>

<span data-ttu-id="9eaa0-177">`WriteObject`メソッドを使用すると、関数は、パイプラインの次のコマンドにオブジェクトを送信できます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-177">The `WriteObject` method allows the function to send an object to the next command in the pipeline.</span></span> <span data-ttu-id="9eaa0-178">ほとんどの場合、 `WriteObject` は、関数がデータを返すときに使用するメソッドです。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-178">In most cases, `WriteObject` is the method to use when the function returns data.</span></span> <span data-ttu-id="9eaa0-179">詳細については、「 [PSCmdlet. WriteObject](/dotnet/api/system.management.automation.cmdlet.writeobject)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-179">For more information, see [System.Management.Automation.PSCmdlet.WriteObject](/dotnet/api/system.management.automation.cmdlet.writeobject).</span></span>

#### <a name="writeprogress"></a><span data-ttu-id="9eaa0-180">WriteProgress</span><span class="sxs-lookup"><span data-stu-id="9eaa0-180">WriteProgress</span></span>

<span data-ttu-id="9eaa0-181">完了に時間がかかるアクションを含む関数の場合、このメソッドは、 `WriteProgress` 進行状況の情報が表示されるように、関数がメソッドを呼び出すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-181">For functions with actions that take a long time to complete, this method allows the function to call the `WriteProgress` method so that progress information is displayed.</span></span> <span data-ttu-id="9eaa0-182">たとえば、完了した割合を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-182">For example, you can display the percent completed.</span></span>
<span data-ttu-id="9eaa0-183">詳細については、「 [PSCmdlet](/dotnet/api/system.management.automation.cmdlet.writeprogress)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-183">For more information, see [System.Management.Automation.PSCmdlet.WriteProgress](/dotnet/api/system.management.automation.cmdlet.writeprogress).</span></span>

#### <a name="writeverbose"></a><span data-ttu-id="9eaa0-184">WriteVerbose</span><span class="sxs-lookup"><span data-stu-id="9eaa0-184">WriteVerbose</span></span>

<span data-ttu-id="9eaa0-185">関数の動作に関する詳細情報を提供するには、メソッドを呼び出して、 `WriteVerbose` ユーザーに詳細メッセージを表示するようにします。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-185">To provide detailed information about what the function is doing, make the function call the `WriteVerbose` method to display verbose messages to the user.</span></span> <span data-ttu-id="9eaa0-186">既定では、詳細メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-186">By default, verbose messages aren't displayed.</span></span> <span data-ttu-id="9eaa0-187">詳細については、「 [PSCmdlet](/dotnet/api/system.management.automation.cmdlet.writeverbose)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-187">For more information, see [System.Management.Automation.PSCmdlet.WriteVerbose](/dotnet/api/system.management.automation.cmdlet.writeverbose).</span></span>

#### <a name="writewarning"></a><span data-ttu-id="9eaa0-188">WriteWarning</span><span class="sxs-lookup"><span data-stu-id="9eaa0-188">WriteWarning</span></span>

<span data-ttu-id="9eaa0-189">予期しない結果になる可能性のある条件に関する情報を提供するには、関数が WriteWarning メソッドを呼び出して、警告メッセージをユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-189">To provide information about conditions that may cause unexpected results, make the function call the WriteWarning method to display warning messages to the user.</span></span> <span data-ttu-id="9eaa0-190">既定では、警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-190">By default, warning messages are displayed.</span></span> <span data-ttu-id="9eaa0-191">詳細については、「 [PSCmdlet](/dotnet/api/system.management.automation.cmdlet.writewarning)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-191">For more information, see [System.Management.Automation.PSCmdlet.WriteWarning](/dotnet/api/system.management.automation.cmdlet.writewarning).</span></span>

> [!NOTE]
> <span data-ttu-id="9eaa0-192">また、変数を構成する `$WarningPreference` か、 `Verbose` およびコマンドラインオプションを使用して、警告メッセージを表示することもでき `Debug` ます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-192">You can also display warning messages by configuring the `$WarningPreference` variable or by using the `Verbose` and `Debug` command-line options.</span></span> <span data-ttu-id="9eaa0-193">変数の詳細については `$WarningPreference` 、「 [about_Preference_Variables](about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-193">for more information about the `$WarningPreference` variable, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

### <a name="other-methods-and-properties"></a><span data-ttu-id="9eaa0-194">その他のメソッドとプロパティ</span><span class="sxs-lookup"><span data-stu-id="9eaa0-194">Other methods and properties</span></span>

<span data-ttu-id="9eaa0-195">変数を使用してアクセスできるその他のメソッドとプロパティの詳細については `$PSCmdlet` 、「 [PSCmdlet](/dotnet/api/system.management.automation.pscmdlet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-195">For information about the other methods and properties that can be accessed through the `$PSCmdlet` variable, see [System.Management.Automation.PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).</span></span>

<span data-ttu-id="9eaa0-196">たとえば、 [ParameterSetName](/dotnet/api/system.management.automation.pscmdlet.parametersetname) プロパティを使用すると、使用されているパラメーターセットを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-196">For example, the [ParameterSetName](/dotnet/api/system.management.automation.pscmdlet.parametersetname) property allows you to see the parameter set that is being used.</span></span> <span data-ttu-id="9eaa0-197">パラメーターセットを使用すると、関数の実行時に指定されたパラメーターに基づいてさまざまなタスクを実行する関数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="9eaa0-197">Parameter sets allow you to create a function that performs different tasks based on the parameters that are specified when the function is run.</span></span>

## <a name="see-also"></a><span data-ttu-id="9eaa0-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="9eaa0-198">See also</span></span>

[<span data-ttu-id="9eaa0-199">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="9eaa0-199">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="9eaa0-200">about_Functions</span><span class="sxs-lookup"><span data-stu-id="9eaa0-200">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="9eaa0-201">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="9eaa0-201">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="9eaa0-202">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="9eaa0-202">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="9eaa0-203">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="9eaa0-203">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="9eaa0-204">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="9eaa0-204">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="9eaa0-205">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="9eaa0-205">about_Preference_Variables</span></span>](about_Preference_Variables.md)

