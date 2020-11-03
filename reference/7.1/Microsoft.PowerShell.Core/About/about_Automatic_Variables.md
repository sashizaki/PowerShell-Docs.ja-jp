---
description: PowerShell の状態情報を格納する変数について説明します。 これらの変数は、PowerShell によって作成および管理されます。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 08/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_automatic_variables?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Automatic_Variables
ms.openlocfilehash: 5ce9e61113da2c781f5774866e827663a7c7ced4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93224160"
---
# <a name="about-automatic-variables"></a><span data-ttu-id="0e35c-105">自動変数について</span><span class="sxs-lookup"><span data-stu-id="0e35c-105">About Automatic Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="0e35c-106">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="0e35c-106">Short description</span></span>

<span data-ttu-id="0e35c-107">PowerShell の状態情報を格納する変数について説明します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-107">Describes variables that store state information for PowerShell.</span></span> <span data-ttu-id="0e35c-108">これらの変数は、PowerShell によって作成および管理されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-108">These variables are created and maintained by PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="0e35c-109">長い説明</span><span class="sxs-lookup"><span data-stu-id="0e35c-109">Long description</span></span>

<span data-ttu-id="0e35c-110">概念的には、これらの変数は読み取り専用と見なされます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-110">Conceptually, these variables are considered to be read-only.</span></span> <span data-ttu-id="0e35c-111">これらをに書き込む **ことはできますが** 、旧バージョンとの互換性のために書き込ま **ない** でください。</span><span class="sxs-lookup"><span data-stu-id="0e35c-111">Even though they **can** be written to, for backward compatibility they **should not** be written to.</span></span>

<span data-ttu-id="0e35c-112">PowerShell の自動変数の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-112">Here is a list of the automatic variables in PowerShell:</span></span>

### <a name=""></a>$$

<span data-ttu-id="0e35c-113">セッションによって受信された最後の行の最後のトークンを格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-113">Contains the last token in the last line received by the session.</span></span>

### <a name=""></a><span data-ttu-id="0e35c-114">$?</span><span class="sxs-lookup"><span data-stu-id="0e35c-114">$?</span></span>

<span data-ttu-id="0e35c-115">最後のコマンドの実行状態を格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-115">Contains the execution status of the last command.</span></span> <span data-ttu-id="0e35c-116">最後のコマンドが成功した場合は **True** 、失敗した場合は **False** が格納されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-116">It contains **True** if the last command succeeded and **False** if it failed.</span></span>

<span data-ttu-id="0e35c-117">パイプライン内の複数の段階で実行されるコマンドレットおよび拡張関数の場合 (およびブロックの両方で) は、とのように、またはの各ポイントでを `process` `end` 呼び出すと、 `this.WriteError()` `$PSCmdlet.WriteError()` `$?` **False** に設定され `this.ThrowTerminatingError()` `$PSCmdlet.ThrowTerminatingError()` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-117">For cmdlets and advanced functions that are run at multiple stages in a pipeline, for example in both `process` and `end` blocks, calling `this.WriteError()` or `$PSCmdlet.WriteError()` respectively at any point will set `$?` to **False** , as will `this.ThrowTerminatingError()` and `$PSCmdlet.ThrowTerminatingError()`.</span></span>

<span data-ttu-id="0e35c-118">`Write-Error`コマンドレットは、 `$?` 実行された直後に **false** に設定されますが、 `$?` それを呼び出す関数の場合は **false** に設定されません。</span><span class="sxs-lookup"><span data-stu-id="0e35c-118">The `Write-Error` cmdlet always sets `$?` to **False** immediately after it is executed, but will not set `$?` to **False** for a function calling it:</span></span>

```powershell
function Test-WriteError
{
    Write-Error "Bad"
    $? # $false
}

Test-WriteError
$? # $true
```

<span data-ttu-id="0e35c-119">後者の場合は、 `$PSCmdlet.WriteError()` 代わりにを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e35c-119">For the latter purpose, `$PSCmdlet.WriteError()` should be used instead.</span></span>

<span data-ttu-id="0e35c-120">ネイティブコマンド (実行可能ファイル) の場合、が `$?` 0 の場合は **True** に設定され、 `$LASTEXITCODE` が他の値の場合は **False** に設定され `$LASTEXITCODE` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-120">For native commands (executables), `$?` is set to **True** when `$LASTEXITCODE` is 0, and set to **False** when `$LASTEXITCODE` is any other value.</span></span>

> [!NOTE]
> <span data-ttu-id="0e35c-121">PowerShell 7 までは、かっこ内にステートメントが含ま `(...)` れている限り、部分式構文 `$(...)` または配列式は常に true にリセットされるので、は `@(...)` `$?` true になり **True** `(Write-Error)` `$?` ます。 **True**</span><span class="sxs-lookup"><span data-stu-id="0e35c-121">Until PowerShell 7, containing a statement within parentheses `(...)`, subexpression syntax `$(...)` or array expression `@(...)` always reset `$?` to **True** , so that `(Write-Error)` shows `$?` as **True**.</span></span>
> <span data-ttu-id="0e35c-122">これは PowerShell 7 で変更されているため、 `$?` は常に、これらの式で最後に実行されたコマンドの実際の成功を反映します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-122">This has been changed in PowerShell 7, so that `$?` will always reflect the actual success of the last command run in these expressions.</span></span>

### <a name=""></a>$^

<span data-ttu-id="0e35c-123">セッションによって受信された最後の行の最初のトークンを格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-123">Contains the first token in the last line received by the session.</span></span>

### <a name="_"></a><span data-ttu-id="0e35c-124">$_</span><span class="sxs-lookup"><span data-stu-id="0e35c-124">$_</span></span>

<span data-ttu-id="0e35c-125">`$PSItem` と同じ。</span><span class="sxs-lookup"><span data-stu-id="0e35c-125">Same as `$PSItem`.</span></span> <span data-ttu-id="0e35c-126">パイプラインオブジェクトの現在のオブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-126">Contains the current object in the pipeline object.</span></span> <span data-ttu-id="0e35c-127">この変数は、パイプライン内のすべてのオブジェクトまたは選択したオブジェクトに対してアクションを実行するコマンドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-127">You can use this variable in commands that perform an action on every object or on selected objects in a pipeline.</span></span>

### <a name="args"></a><span data-ttu-id="0e35c-128">$args</span><span class="sxs-lookup"><span data-stu-id="0e35c-128">$args</span></span>

<span data-ttu-id="0e35c-129">関数、スクリプト、またはスクリプトブロックに渡される、宣言されていないパラメーターの値の配列を格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-129">Contains an array of values for undeclared parameters that are passed to a function, script, or script block.</span></span> <span data-ttu-id="0e35c-130">関数を作成するときに、キーワードを使用する `param` か、関数名の後にパラメーターのコンマ区切りリストをかっこで追加することによって、パラメーターを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-130">When you create a function, you can declare the parameters by using the `param` keyword or by adding a comma-separated list of parameters in parentheses after the function name.</span></span>

<span data-ttu-id="0e35c-131">イベントアクションでは、変数には、 `$Args` 処理中のイベントのイベント引数を表すオブジェクトが格納されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-131">In an event action, the `$Args` variable contains objects that represent the event arguments of the event that is being processed.</span></span> <span data-ttu-id="0e35c-132">この変数は、 `Action` イベント登録コマンドのブロック内でのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-132">This variable is populated only within the `Action` block of an event registration command.</span></span>
<span data-ttu-id="0e35c-133">この変数の値は、を返す **PSEventArgs** オブジェクトの **sourceargs** プロパティにもあり `Get-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-133">The value of this variable can also be found in the **SourceArgs** property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="consolefilename"></a><span data-ttu-id="0e35c-134">$ConsoleFileName</span><span class="sxs-lookup"><span data-stu-id="0e35c-134">$ConsoleFileName</span></span>

<span data-ttu-id="0e35c-135">セッションで最近使用されたコンソールファイル () のパスを格納し `.psc1` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-135">Contains the path of the console file (`.psc1`) that was most recently used in the session.</span></span> <span data-ttu-id="0e35c-136">この変数は、 **Psconsolefile** パラメーターを使用して PowerShell を起動したとき、またはコマンドレットを使用して `Export-Console` スナップイン名をコンソールファイルにエクスポートしたときに設定されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-136">This variable is populated when you start PowerShell with the **PSConsoleFile** parameter or when you use the `Export-Console` cmdlet to export snap-in names to a console file.</span></span>

<span data-ttu-id="0e35c-137">`Export-Console`パラメーターを指定せずにコマンドレットを使用すると、セッションで最後に使用されたコンソールファイルが自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-137">When you use the `Export-Console` cmdlet without parameters, it automatically updates the console file that was most recently used in the session.</span></span> <span data-ttu-id="0e35c-138">この自動変数を使用すると、どのファイルを更新するかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-138">You can use this automatic variable to determine which file will be updated.</span></span>

### <a name="error"></a><span data-ttu-id="0e35c-139">$Error</span><span class="sxs-lookup"><span data-stu-id="0e35c-139">$Error</span></span>

<span data-ttu-id="0e35c-140">最新のエラーを表すエラーオブジェクトの配列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e35c-140">Contains an array of error objects that represent the most recent errors.</span></span>
<span data-ttu-id="0e35c-141">最新のエラーは、配列内の最初のエラーオブジェクトです `$Error[0]` 。</span><span class="sxs-lookup"><span data-stu-id="0e35c-141">The most recent error is the first error object in the array `$Error[0]`.</span></span>

<span data-ttu-id="0e35c-142">エラーが配列に追加されないようにするには `$Error` 、 **erroraction** 共通パラメーターに値 **Ignore** を指定します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-142">To prevent an error from being added to the `$Error` array, use the **ErrorAction** common parameter with a value of **Ignore**.</span></span> <span data-ttu-id="0e35c-143">詳細については、「[about_CommonParameters](about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e35c-143">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

### <a name="event"></a><span data-ttu-id="0e35c-144">$Event</span><span class="sxs-lookup"><span data-stu-id="0e35c-144">$Event</span></span>

<span data-ttu-id="0e35c-145">処理中のイベントを表す **PSEventArgs** オブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-145">Contains a **PSEventArgs** object that represents the event that is being processed.</span></span> <span data-ttu-id="0e35c-146">この変数は、などの `Action` イベント登録コマンドのブロック内でのみ設定され `Register-ObjectEvent` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-146">This variable is populated only within the `Action` block of an event registration command, such as `Register-ObjectEvent`.</span></span> <span data-ttu-id="0e35c-147">この変数の値は、コマンドレットが返すオブジェクトと同じです `Get-Event` 。</span><span class="sxs-lookup"><span data-stu-id="0e35c-147">The value of this variable is the same object that the `Get-Event` cmdlet returns.</span></span> <span data-ttu-id="0e35c-148">そのため、などの変数のプロパティを `Event` `$Event.TimeGenerated` スクリプトブロックで使用でき `Action` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-148">Therefore, you can use the properties of the `Event` variable, such as `$Event.TimeGenerated`, in an `Action` script block.</span></span>

### <a name="eventargs"></a><span data-ttu-id="0e35c-149">$EventArgs</span><span class="sxs-lookup"><span data-stu-id="0e35c-149">$EventArgs</span></span>

<span data-ttu-id="0e35c-150">処理中のイベントの **EventArgs** から派生した最初のイベント引数を表すオブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-150">Contains an object that represents the first event argument that derives from **EventArgs** of the event that is being processed.</span></span> <span data-ttu-id="0e35c-151">この変数は、 `Action` イベント登録コマンドのブロック内でのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-151">This variable is populated only within the `Action` block of an event registration command.</span></span>
<span data-ttu-id="0e35c-152">この変数の値は、を返す **PSEventArgs** オブジェクトの **sourceeventargs** プロパティにもあり `Get-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-152">The value of this variable can also be found in the **SourceEventArgs** property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="eventsubscriber"></a><span data-ttu-id="0e35c-153">$EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="0e35c-153">$EventSubscriber</span></span>

<span data-ttu-id="0e35c-154">処理中のイベントのイベントサブスクライバーを表す **PSEventSubscriber** オブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-154">Contains a **PSEventSubscriber** object that represents the event subscriber of the event that is being processed.</span></span> <span data-ttu-id="0e35c-155">この変数は、 `Action` イベント登録コマンドのブロック内でのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-155">This variable is populated only within the `Action` block of an event registration command.</span></span> <span data-ttu-id="0e35c-156">この変数の値は、コマンドレットが返すオブジェクトと同じです `Get-EventSubscriber` 。</span><span class="sxs-lookup"><span data-stu-id="0e35c-156">The value of this variable is the same object that the `Get-EventSubscriber` cmdlet returns.</span></span>

### <a name="executioncontext"></a><span data-ttu-id="0e35c-157">$ExecutionContext</span><span class="sxs-lookup"><span data-stu-id="0e35c-157">$ExecutionContext</span></span>

<span data-ttu-id="0e35c-158">PowerShell ホストの実行コンテキストを表す **EngineIntrinsics** オブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-158">Contains an **EngineIntrinsics** object that represents the execution context of the PowerShell host.</span></span> <span data-ttu-id="0e35c-159">この変数を使用すると、コマンドレットで使用できる実行オブジェクトを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-159">You can use this variable to find the execution objects that are available to cmdlets.</span></span>

### <a name="false"></a><span data-ttu-id="0e35c-160">$false</span><span class="sxs-lookup"><span data-stu-id="0e35c-160">$false</span></span>

<span data-ttu-id="0e35c-161">**False** が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e35c-161">Contains **False**.</span></span> <span data-ttu-id="0e35c-162">この変数を使用すると、文字列 "false" を使用する代わりに、コマンドとスクリプトで **false** を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-162">You can use this variable to represent **False** in commands and scripts instead of using the string "false".</span></span> <span data-ttu-id="0e35c-163">文字列は、空でない文字列または0以外の整数に変換される場合、 **True** として解釈できます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-163">The string can be interpreted as **True** if it's converted to a non-empty string or to a non-zero integer.</span></span>

### <a name="foreach"></a><span data-ttu-id="0e35c-164">$foreach</span><span class="sxs-lookup"><span data-stu-id="0e35c-164">$foreach</span></span>

<span data-ttu-id="0e35c-165">[ForEach](about_ForEach.md)ループの列挙子 (結果の値ではない) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-165">Contains the enumerator (not the resulting values) of a [ForEach](about_ForEach.md) loop.</span></span> <span data-ttu-id="0e35c-166">変数は、 `$ForEach` ループの実行中にのみ存在します。ループ `ForEach` が完了すると削除されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-166">The `$ForEach` variable exists only while the `ForEach` loop is running; it's deleted after the loop is completed.</span></span>

<span data-ttu-id="0e35c-167">列挙子には、ループ値を取得したり、現在のループの反復を変更したりするために使用できるプロパティとメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e35c-167">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="0e35c-168">詳細については、「 [列挙子の使用](#using-enumerators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e35c-168">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="home"></a><span data-ttu-id="0e35c-169">$HOME</span><span class="sxs-lookup"><span data-stu-id="0e35c-169">$HOME</span></span>

<span data-ttu-id="0e35c-170">ユーザーのホームディレクトリの完全なパスを含みます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-170">Contains the full path of the user's home directory.</span></span> <span data-ttu-id="0e35c-171">この変数は、 `"$env:homedrive$env:homepath"` 通常、Windows 環境変数に相当し `C:\Users\<UserName>` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-171">This variable is the equivalent of the `"$env:homedrive$env:homepath"` Windows environment variables, typically `C:\Users\<UserName>`.</span></span>

### <a name="host"></a><span data-ttu-id="0e35c-172">$Host</span><span class="sxs-lookup"><span data-stu-id="0e35c-172">$Host</span></span>

<span data-ttu-id="0e35c-173">PowerShell の現在のホストアプリケーションを表すオブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-173">Contains an object that represents the current host application for PowerShell.</span></span> <span data-ttu-id="0e35c-174">この変数を使用すると、コマンドで現在のホストを表すことや、ホストのプロパティを表示または変更することができ `$Host.version` ます。たとえば、やなど `$Host.CurrentCulture` `$host.ui.rawui.setbackgroundcolor("Red")` です。</span><span class="sxs-lookup"><span data-stu-id="0e35c-174">You can use this variable to represent the current host in commands or to display or change the properties of the host, such as `$Host.version` or `$Host.CurrentCulture`, or `$host.ui.rawui.setbackgroundcolor("Red")`.</span></span>

### <a name="input"></a><span data-ttu-id="0e35c-175">$input</span><span class="sxs-lookup"><span data-stu-id="0e35c-175">$input</span></span>

<span data-ttu-id="0e35c-176">関数に渡されるすべての入力を列挙する列挙子を格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-176">Contains an enumerator that enumerates all input that is passed to a function.</span></span> <span data-ttu-id="0e35c-177">変数は、 `$input` 関数とスクリプトブロック (名前のない関数) でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-177">The `$input` variable is available only to functions and script blocks (which are unnamed functions).</span></span>

- <span data-ttu-id="0e35c-178">、、またはブロックのない関数では、 `Begin` `Process` `End` 変数は、 `$input` 関数へのすべての入力のコレクションを列挙します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-178">In a function without a `Begin`, `Process`, or `End` block, the `$input` variable enumerates the collection of all input to the function.</span></span>

- <span data-ttu-id="0e35c-179">ブロックでは、 `Begin` `$input` 変数にデータが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="0e35c-179">In the `Begin` block, the `$input` variable contains no data.</span></span>

- <span data-ttu-id="0e35c-180">ブロック内の変数には、 `Process` `$input` 現在パイプライン内にあるオブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e35c-180">In the `Process` block, the `$input` variable contains the object that is currently in the pipeline.</span></span>

- <span data-ttu-id="0e35c-181">ブロックでは、 `End` 変数は、 `$input` 関数へのすべての入力のコレクションを列挙します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-181">In the `End` block, the `$input` variable enumerates the collection of all input to the function.</span></span>

  > [!NOTE]
  > <span data-ttu-id="0e35c-182">`$input`同じ関数またはスクリプトブロックの中で、プロセスブロックと End ブロックの両方で変数を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0e35c-182">You cannot use the `$input` variable inside both the Process block and the End block in the same function or script block.</span></span>

<span data-ttu-id="0e35c-183">`$input`は列挙子であるため、そのプロパティのいずれかにアクセスすると、が使用できなくなり `$input` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-183">Since `$input` is an enumerator, accessing any of it's properties causes `$input` to no longer be available.</span></span> <span data-ttu-id="0e35c-184">`$input`別の変数に格納して、プロパティを再利用することができ `$input` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-184">You can store `$input` in another variable to reuse the `$input` properties.</span></span>

<span data-ttu-id="0e35c-185">列挙子には、ループ値を取得したり、現在のループの反復を変更したりするために使用できるプロパティとメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e35c-185">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="0e35c-186">詳細については、「 [列挙子の使用](#using-enumerators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e35c-186">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="iscoreclr"></a><span data-ttu-id="0e35c-187">$IsCoreCLR</span><span class="sxs-lookup"><span data-stu-id="0e35c-187">$IsCoreCLR</span></span>

<span data-ttu-id="0e35c-188">`$True`現在のセッションが .Net Core ランタイム (CoreCLR) で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-188">Contains `$True` if the current session is running on the .NET Core Runtime (CoreCLR).</span></span> <span data-ttu-id="0e35c-189">それ以外 `$False` の場合は。</span><span class="sxs-lookup"><span data-stu-id="0e35c-189">Otherwise contains `$False`.</span></span>

### <a name="islinux"></a><span data-ttu-id="0e35c-190">$IsLinux</span><span class="sxs-lookup"><span data-stu-id="0e35c-190">$IsLinux</span></span>

<span data-ttu-id="0e35c-191">`$True`現在のセッションが Linux オペレーティングシステムで実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-191">Contains `$True` if the current session is running on a Linux operating system.</span></span>
<span data-ttu-id="0e35c-192">それ以外 `$False` の場合は。</span><span class="sxs-lookup"><span data-stu-id="0e35c-192">Otherwise contains `$False`.</span></span>

### <a name="ismacos"></a><span data-ttu-id="0e35c-193">$IsMacOS</span><span class="sxs-lookup"><span data-stu-id="0e35c-193">$IsMacOS</span></span>

<span data-ttu-id="0e35c-194">`$True`現在のセッションが MacOS オペレーティングシステムで実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-194">Contains `$True` if the current session is running on a MacOS operating system.</span></span>
<span data-ttu-id="0e35c-195">それ以外 `$False` の場合は。</span><span class="sxs-lookup"><span data-stu-id="0e35c-195">Otherwise contains `$False`.</span></span>

### <a name="iswindows"></a><span data-ttu-id="0e35c-196">$IsWindows</span><span class="sxs-lookup"><span data-stu-id="0e35c-196">$IsWindows</span></span>

<span data-ttu-id="0e35c-197">`$TRUE`現在のセッションが Windows オペレーティングシステムで実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-197">Contains `$TRUE` if the current session is running on a Windows operating system.</span></span> <span data-ttu-id="0e35c-198">それ以外 `$FALSE` の場合は。</span><span class="sxs-lookup"><span data-stu-id="0e35c-198">Otherwise contains `$FALSE`.</span></span>

### <a name="lastexitcode"></a><span data-ttu-id="0e35c-199">$LastExitCode</span><span class="sxs-lookup"><span data-stu-id="0e35c-199">$LastExitCode</span></span>

<span data-ttu-id="0e35c-200">最後に実行された Windows ベースのプログラムの終了コードを格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-200">Contains the exit code of the last Windows-based program that was run.</span></span>

### <a name="matches"></a><span data-ttu-id="0e35c-201">$Matches</span><span class="sxs-lookup"><span data-stu-id="0e35c-201">$Matches</span></span>

<span data-ttu-id="0e35c-202">変数は、 `Matches` `-match` 演算子と演算子と連携し `-notmatch` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-202">The `Matches` variable works with the `-match` and `-notmatch` operators.</span></span>
<span data-ttu-id="0e35c-203">スカラー入力を or 演算子に送信 `-match` `-notmatch` し、一方が一致を検出した場合は、ブール値を返し、 `$Matches` 一致した文字列値のハッシュテーブルで自動変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-203">When you submit scalar input to the `-match` or `-notmatch` operator, and either one detects a match, they return a Boolean value and populate the `$Matches` automatic variable with a hash table of any string values that were matched.</span></span> <span data-ttu-id="0e35c-204">`$Matches`演算子で正規表現を使用する場合、ハッシュテーブルにキャプチャを設定することもでき `-match` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-204">The `$Matches` hash table can also be populated with captures when you use regular expressions with the `-match` operator.</span></span>

<span data-ttu-id="0e35c-205">オペレーターの詳細については `-match` 、「 [about_Comparison_Operators](about_comparison_operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e35c-205">For more information about the `-match` operator, see [about_Comparison_Operators](about_comparison_operators.md).</span></span> <span data-ttu-id="0e35c-206">正規表現の詳細については、「 [about_Regular_Expressions](about_Regular_Expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e35c-206">For more information on regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

### <a name="myinvocation"></a><span data-ttu-id="0e35c-207">$MyInvocation</span><span class="sxs-lookup"><span data-stu-id="0e35c-207">$MyInvocation</span></span>

<span data-ttu-id="0e35c-208">現在のコマンドに関する情報 (名前、パラメーター、パラメーター値など)、コマンドの開始、呼び出し、または呼び出しの方法 (現在のコマンドを呼び出したスクリプトの名前など) に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-208">Contains information about the current command, such as the name, parameters, parameter values, and information about how the command was started, called, or invoked, such as the name of the script that called the current command.</span></span>

<span data-ttu-id="0e35c-209">`$MyInvocation` は、スクリプト、関数、およびスクリプトブロックに対してのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-209">`$MyInvocation` is populated only for scripts, function, and script blocks.</span></span> <span data-ttu-id="0e35c-210">現在のスクリプトの **System.Management.Automation.InvocationInfo** `$MyInvocation` パスとファイル名 ( `$MyInvocation.MyCommand.Path` )、または関数の名前 () を使用して現在のコマンドを `$MyInvocation.MyCommand.Name` 識別することで、InvocationInfo オブジェクトの情報を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-210">You can use the information in the **System.Management.Automation.InvocationInfo** object that `$MyInvocation` returns in the current script, such as the path and file name of the script (`$MyInvocation.MyCommand.Path`) or the name of a function (`$MyInvocation.MyCommand.Name`) to identify the current command.</span></span> <span data-ttu-id="0e35c-211">これは、現在のスクリプトの名前を検索する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="0e35c-211">This is particularly useful for finding the name of the current script.</span></span>

<span data-ttu-id="0e35c-212">PowerShell 3.0 以降では、に `MyInvocation` 次の新しいプロパティが追加されています。</span><span class="sxs-lookup"><span data-stu-id="0e35c-212">Beginning in PowerShell 3.0, `MyInvocation` has the following new properties.</span></span>

| <span data-ttu-id="0e35c-213">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0e35c-213">Property</span></span>      | <span data-ttu-id="0e35c-214">説明</span><span class="sxs-lookup"><span data-stu-id="0e35c-214">Description</span></span>                                         |
| ------------- | --------------------------------------------------- |
| <span data-ttu-id="0e35c-215">**PSScriptRoot**</span><span class="sxs-lookup"><span data-stu-id="0e35c-215">**PSScriptRoot**</span></span>  | <span data-ttu-id="0e35c-216">呼び出されたスクリプトへの完全なパスを格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-216">Contains the full path to the script that invoked</span></span>   |
|               | <span data-ttu-id="0e35c-217">現在のコマンド。</span><span class="sxs-lookup"><span data-stu-id="0e35c-217">the current command.</span></span> <span data-ttu-id="0e35c-218">このプロパティの値は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0e35c-218">The value of this property is</span></span>  |
|               | <span data-ttu-id="0e35c-219">呼び出し元がスクリプトの場合にのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-219">populated only when the caller is a script.</span></span>         |
| <span data-ttu-id="0e35c-220">**PSCommandPath**</span><span class="sxs-lookup"><span data-stu-id="0e35c-220">**PSCommandPath**</span></span> | <span data-ttu-id="0e35c-221">スクリプトの完全なパスとファイル名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-221">Contains the full path and file name of the script</span></span>  |
|               | <span data-ttu-id="0e35c-222">現在のコマンドを呼び出した。</span><span class="sxs-lookup"><span data-stu-id="0e35c-222">that invoked the current command.</span></span> <span data-ttu-id="0e35c-223">このの値</span><span class="sxs-lookup"><span data-stu-id="0e35c-223">The value of this</span></span> |
|               | <span data-ttu-id="0e35c-224">プロパティは、呼び出し元がである場合にのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-224">property is populated only when the caller is a</span></span>     |
|               | <span data-ttu-id="0e35c-225"> スクリプトを入手してください。</span><span class="sxs-lookup"><span data-stu-id="0e35c-225">script.</span></span>                                             |

<span data-ttu-id="0e35c-226">`$PSScriptRoot`および自動変数とは異なり `$PSCommandPath` 、自動変数の **psscriptroot** および **psscriptroot** プロパティには、現在のスクリプトでは `$MyInvocation` なく、呼び出し元または呼び出し元のスクリプトに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-226">Unlike the `$PSScriptRoot` and `$PSCommandPath` automatic variables, the **PSScriptRoot** and **PSCommandPath** properties of the `$MyInvocation` automatic variable contain information about the invoker or calling script, not the current script.</span></span>

### <a name="nestedpromptlevel"></a><span data-ttu-id="0e35c-227">$NestedPromptLevel</span><span class="sxs-lookup"><span data-stu-id="0e35c-227">$NestedPromptLevel</span></span>

<span data-ttu-id="0e35c-228">現在のプロンプトレベルを格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-228">Contains the current prompt level.</span></span> <span data-ttu-id="0e35c-229">値が0の場合は、元のプロンプトレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-229">A value of 0 indicates the original prompt level.</span></span> <span data-ttu-id="0e35c-230">この値は、入れ子になったレベルを入力するとインクリメントされ、終了時にはデクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-230">The value is incremented when you enter a nested level and decremented when you exit it.</span></span>

<span data-ttu-id="0e35c-231">たとえば、PowerShell では、メソッドを使用すると、入れ子になったコマンドプロンプトが表示さ `$Host.EnterNestedPrompt` れます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-231">For example, PowerShell presents a nested command prompt when you use the `$Host.EnterNestedPrompt` method.</span></span> <span data-ttu-id="0e35c-232">Powershell デバッガーでブレークポイントに到着すると、入れ子になったコマンドプロンプトも表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-232">PowerShell also presents a nested command prompt when you reach a breakpoint in the PowerShell debugger.</span></span>

<span data-ttu-id="0e35c-233">入れ子になったプロンプトを入力すると、PowerShell は現在のコマンドを一時停止し、実行コンテキストを保存して、変数の値をインクリメントし `$NestedPromptLevel` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-233">When you enter a nested prompt, PowerShell pauses the current command, saves the execution context, and increments the value of the `$NestedPromptLevel` variable.</span></span> <span data-ttu-id="0e35c-234">入れ子になったコマンドプロンプト (最大128レベル) を作成するか、元のコマンドプロンプトに戻るには、コマンドを実行するか、「」と入力 `exit` します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-234">To create additional nested command prompts (up to 128 levels) or to return to the original command prompt, complete the command, or type `exit`.</span></span>

<span data-ttu-id="0e35c-235">変数は、 `$NestedPromptLevel` プロンプトレベルを追跡するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-235">The `$NestedPromptLevel` variable helps you track the prompt level.</span></span> <span data-ttu-id="0e35c-236">この値を含む別の PowerShell コマンドプロンプトを作成して、常に表示されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-236">You can create an alternative PowerShell command prompt that includes this value so that it's always visible.</span></span>

### <a name="null"></a><span data-ttu-id="0e35c-237">$null</span><span class="sxs-lookup"><span data-stu-id="0e35c-237">$null</span></span>

<span data-ttu-id="0e35c-238">`$null`**null** または空の値を含む自動変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-238">`$null` is an automatic variable that contains a **null** or empty value.</span></span> <span data-ttu-id="0e35c-239">この変数を使用すると、コマンドやスクリプトに存在しない値または未定義の値を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-239">You can use this variable to represent an absent or undefined value in commands and scripts.</span></span>

<span data-ttu-id="0e35c-240">PowerShell `$null` は、値を持つオブジェクト (つまり、明示的なプレースホルダー) としてを処理します。これにより、を使用して `$null` 一連の値で空の値を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-240">PowerShell treats `$null` as an object with a value, that is, as an explicit placeholder, so you can use `$null` to represent an empty value in a series of values.</span></span>

<span data-ttu-id="0e35c-241">たとえば、 `$null` コレクションにが含まれている場合、オブジェクトの1つとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-241">For example, when `$null` is included in a collection, it's counted as one of the objects.</span></span>

```powershell
$a = "one", $null, "three"
$a.count
```

```Output
3
```

<span data-ttu-id="0e35c-242">パイプを使用して変数をコマンドレットに渡した場合、 `$null` 他の `ForEach-Object` `$null` オブジェクトの場合と同様に、の値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-242">If you pipe the `$null` variable to the `ForEach-Object` cmdlet, it generates a value for `$null`, just as it does for the other objects</span></span>

```powershell
"one", $null, "three" | ForEach-Object { "Hello " + $_}
```

```Output
Hello one
Hello
Hello three
```

<span data-ttu-id="0e35c-243">このため、を使用して `$null` **パラメーター値を指定** することはできません。</span><span class="sxs-lookup"><span data-stu-id="0e35c-243">As a result, you can't use `$null` to mean **no parameter value**.</span></span> <span data-ttu-id="0e35c-244">パラメーター値がの場合、 `$null` 既定のパラメーター値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-244">A parameter value of `$null` overrides the default parameter value.</span></span>

<span data-ttu-id="0e35c-245">ただし、PowerShell では `$null` 変数がプレースホルダーとして扱われるため、次のようなスクリプトで使用できます。これは、が無視された場合には機能し `$null` ません。</span><span class="sxs-lookup"><span data-stu-id="0e35c-245">However, because PowerShell treats the `$null` variable as a placeholder, you can use it in scripts like the following one, which wouldn't work if `$null` were ignored.</span></span>

```powershell
$calendar = @($null, $null, "Meeting", $null, $null, "Team Lunch", $null)
$days = "Sunday","Monday","Tuesday","Wednesday","Thursday",
        "Friday","Saturday"
$currentDay = 0
foreach($day in $calendar)
{
    if($day -ne $null)
    {
        "Appointment on $($days[$currentDay]): $day"
    }

    $currentDay++
}
```

```Output
Appointment on Tuesday: Meeting
Appointment on Friday: Team lunch
```

### <a name="pid"></a><span data-ttu-id="0e35c-246">$PID</span><span class="sxs-lookup"><span data-stu-id="0e35c-246">$PID</span></span>

<span data-ttu-id="0e35c-247">現在の PowerShell セッションをホストしているプロセスのプロセス識別子 (PID) を格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-247">Contains the process identifier (PID) of the process that is hosting the current PowerShell session.</span></span>

### <a name="profile"></a><span data-ttu-id="0e35c-248">$PROFILE</span><span class="sxs-lookup"><span data-stu-id="0e35c-248">$PROFILE</span></span>

<span data-ttu-id="0e35c-249">現在のユーザーと現在のホストアプリケーションの PowerShell プロファイルの完全パスを含みます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-249">Contains the full path of the PowerShell profile for the current user and the current host application.</span></span> <span data-ttu-id="0e35c-250">この変数を使用すると、コマンドでプロファイルを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-250">You can use this variable to represent the profile in commands.</span></span> <span data-ttu-id="0e35c-251">たとえば、コマンドで使用して、プロファイルが作成されているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-251">For example, you can use it in a command to determine whether a profile has been created:</span></span>

```powershell
Test-Path $PROFILE
```

<span data-ttu-id="0e35c-252">または、コマンドで使用してプロファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-252">Or, you can use it in a command to create a profile:</span></span>

```powershell
New-Item -ItemType file -Path $PROFILE -Force
```

<span data-ttu-id="0e35c-253">これをコマンドで使用すると、 **notepad.exe** でプロファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-253">You can use it in a command to open the profile in **notepad.exe** :</span></span>

```powershell
notepad.exe $PROFILE
```

### <a name="psboundparameters"></a><span data-ttu-id="0e35c-254">$PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="0e35c-254">$PSBoundParameters</span></span>

<span data-ttu-id="0e35c-255">スクリプトまたは関数に渡されるパラメーターのディクショナリと、その現在の値を格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-255">Contains a dictionary of the parameters that are passed to a script or function and their current values.</span></span> <span data-ttu-id="0e35c-256">この変数の値は、スクリプトや関数など、パラメーターが宣言されているスコープ内にのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-256">This variable has a value only in a scope where parameters are declared, such as a script or function.</span></span> <span data-ttu-id="0e35c-257">これを使用すると、パラメーターの現在の値を表示または変更したり、別のスクリプトまたは関数にパラメーター値を渡したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-257">You can use it to display or change the current values of parameters or to pass parameter values to another script or function.</span></span>

<span data-ttu-id="0e35c-258">この例では、 **Test2** 関数はを `$PSBoundParameters` **Test1** 関数に渡します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-258">In this example, the **Test2** function passes the `$PSBoundParameters` to the **Test1** function.</span></span> <span data-ttu-id="0e35c-259">は、 `$PSBoundParameters` **キー** と **値** の形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-259">The `$PSBoundParameters` are displayed in the format of **Key** and **Value**.</span></span>

```powershell
function Test1 {
   param($a, $b)

   # Display the parameters in dictionary format.
   $PSBoundParameters
}

function Test2 {
   param($a, $b)

   # Run the Test1 function with $a and $b.
   Test1 @PSBoundParameters
}
```

```powershell
Test2 -a Power -b Shell
```

```Output
Key   Value
---   -----
a     Power
b     Shell
```

### <a name="pscmdlet"></a><span data-ttu-id="0e35c-260">$PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="0e35c-260">$PSCmdlet</span></span>

<span data-ttu-id="0e35c-261">実行されているコマンドレットまたは高度な関数を表すオブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-261">Contains an object that represents the cmdlet or advanced function that's being run.</span></span>

<span data-ttu-id="0e35c-262">コマンドレットまたは関数コードでオブジェクトのプロパティとメソッドを使用して、使用条件に応答できます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-262">You can use the properties and methods of the object in your cmdlet or function code to respond to the conditions of use.</span></span> <span data-ttu-id="0e35c-263">たとえば、 **ParameterSetName** プロパティには、使用されているパラメーターセットの名前が含まれます **。このメソッドは** 、 **WhatIf** および **Confirm** パラメーターをコマンドレットに動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-263">For example, the **ParameterSetName** property contains the name of the parameter set that's being used, and the **ShouldProcess** method adds the **WhatIf** and **Confirm** parameters to the cmdlet dynamically.</span></span>

<span data-ttu-id="0e35c-264">自動変数の詳細については `$PSCmdlet` 、「 [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) 」および「 [about_Functions_Advanced](about_Functions_Advanced.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e35c-264">For more information about the `$PSCmdlet` automatic variable, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) and [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

### <a name="pscommandpath"></a><span data-ttu-id="0e35c-265">$PSCommandPath</span><span class="sxs-lookup"><span data-stu-id="0e35c-265">$PSCommandPath</span></span>

<span data-ttu-id="0e35c-266">実行されているスクリプトの完全なパスとファイル名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-266">Contains the full path and file name of the script that's being run.</span></span> <span data-ttu-id="0e35c-267">この変数は、すべてのスクリプトで有効です。</span><span class="sxs-lookup"><span data-stu-id="0e35c-267">This variable is valid in all scripts.</span></span>

### <a name="psculture"></a><span data-ttu-id="0e35c-268">$PSCulture</span><span class="sxs-lookup"><span data-stu-id="0e35c-268">$PSCulture</span></span>

<span data-ttu-id="0e35c-269">PowerShell 7 以降では、は `$PSCulture` 現在の powershell 実行空間 (セッション) のカルチャを反映しています。</span><span class="sxs-lookup"><span data-stu-id="0e35c-269">Beginning in PowerShell 7, `$PSCulture` reflects the culture of the current PowerShell runspace (session).</span></span> <span data-ttu-id="0e35c-270">PowerShell 実行空間でカルチャが変更された場合、 `$PSCulture` その実行空間の値が更新されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-270">If the culture is changed in a PowerShell runspace, the `$PSCulture` value for that runspace is updated.</span></span>

<span data-ttu-id="0e35c-271">カルチャによって、数値、通貨、日付などの項目の表示形式が決定され、 **システムの CultureInfo** オブジェクトに格納されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-271">The culture determines the display format of items such as numbers, currency, and dates, and is stored in a **System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="0e35c-272">`Get-Culture`コンピューターのカルチャを表示するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-272">Use `Get-Culture` to display the computer's culture.</span></span> <span data-ttu-id="0e35c-273">`$PSCulture`**Name** プロパティの値を格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-273">`$PSCulture` contains the **Name** property's value.</span></span>

### <a name="psdebugcontext"></a><span data-ttu-id="0e35c-274">$PSDebugContext</span><span class="sxs-lookup"><span data-stu-id="0e35c-274">$PSDebugContext</span></span>

<span data-ttu-id="0e35c-275">デバッグ中に、この変数にはデバッグ環境に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-275">While debugging, this variable contains information about the debugging environment.</span></span> <span data-ttu-id="0e35c-276">それ以外の場合は、 **null** 値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-276">Otherwise, it contains a **null** value.</span></span> <span data-ttu-id="0e35c-277">その結果、デバッガーにコントロールがあるかどうかを示すために使用できます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-277">As a result, you can use it to indicate whether the debugger has control.</span></span> <span data-ttu-id="0e35c-278">値が設定されると、 **ブレークポイント** と **InvocationInfo** プロパティを持つ **psdebugcontext** オブジェクトが格納されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-278">When populated, it contains a **PsDebugContext** object that has **Breakpoints** and **InvocationInfo** properties.</span></span> <span data-ttu-id="0e35c-279">**InvocationInfo** プロパティには、 **Location** プロパティなど、いくつかの便利なプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="0e35c-279">The **InvocationInfo** property has several useful properties, including the **Location** property.</span></span> <span data-ttu-id="0e35c-280">**Location** プロパティは、デバッグされているスクリプトのパスを示します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-280">The **Location** property indicates the path of the script that is being debugged.</span></span>

### <a name="pshome"></a><span data-ttu-id="0e35c-281">$PSHOME</span><span class="sxs-lookup"><span data-stu-id="0e35c-281">$PSHOME</span></span>

<span data-ttu-id="0e35c-282">PowerShell のインストールディレクトリ (通常は Windows システム) の完全なパスが含まれ `$env:windir\System32\PowerShell\v1.0` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-282">Contains the full path of the installation directory for PowerShell, typically, `$env:windir\System32\PowerShell\v1.0` in Windows systems.</span></span> <span data-ttu-id="0e35c-283">この変数は、PowerShell ファイルのパスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-283">You can use this variable in the paths of PowerShell files.</span></span> <span data-ttu-id="0e35c-284">たとえば、次のコマンドは、概念説明ヘルプトピックで word **変数** を検索します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-284">For example, the following command searches the conceptual Help topics for the word **variable** :</span></span>

```powershell
Select-String -Pattern Variable -Path $pshome\*.txt
```

### <a name="psitem"></a><span data-ttu-id="0e35c-285">$PSItem</span><span class="sxs-lookup"><span data-stu-id="0e35c-285">$PSItem</span></span>

<span data-ttu-id="0e35c-286">`$_` と同じ。</span><span class="sxs-lookup"><span data-stu-id="0e35c-286">Same as `$_`.</span></span> <span data-ttu-id="0e35c-287">パイプラインオブジェクトの現在のオブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-287">Contains the current object in the pipeline object.</span></span> <span data-ttu-id="0e35c-288">この変数は、パイプライン内のすべてのオブジェクトまたは選択したオブジェクトに対してアクションを実行するコマンドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-288">You can use this variable in commands that perform an action on every object or on selected objects in a pipeline.</span></span>

### <a name="psscriptroot"></a><span data-ttu-id="0e35c-289">$PSScriptRoot</span><span class="sxs-lookup"><span data-stu-id="0e35c-289">$PSScriptRoot</span></span>

<span data-ttu-id="0e35c-290">スクリプトの実行元のディレクトリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-290">Contains the directory from which a script is being run.</span></span>

<span data-ttu-id="0e35c-291">PowerShell 2.0 では、この変数はスクリプトモジュール () でのみ有効です `.psm1` 。</span><span class="sxs-lookup"><span data-stu-id="0e35c-291">In PowerShell 2.0, this variable is valid only in script modules (`.psm1`).</span></span>
<span data-ttu-id="0e35c-292">PowerShell 3.0 以降、すべてのスクリプトで有効になります。</span><span class="sxs-lookup"><span data-stu-id="0e35c-292">Beginning in PowerShell 3.0, it's valid in all scripts.</span></span>

### <a name="pssenderinfo"></a><span data-ttu-id="0e35c-293">$PSSenderInfo</span><span class="sxs-lookup"><span data-stu-id="0e35c-293">$PSSenderInfo</span></span>

<span data-ttu-id="0e35c-294">PSSession を開始したユーザーに関する情報が含まれます。これには、元のコンピューターのユーザー id とタイムゾーンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-294">Contains information about the user who started the PSSession, including the user identity and the time zone of the originating computer.</span></span> <span data-ttu-id="0e35c-295">この変数は、PSSessions でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-295">This variable is available only in PSSessions.</span></span>

<span data-ttu-id="0e35c-296">変数には、 `$PSSenderInfo` ユーザーが構成できるプロパティ **applicationarguments** が含まれています。既定では、元のセッションからのみが含まれ `$PSVersionTable` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-296">The `$PSSenderInfo` variable includes a user-configurable property, **ApplicationArguments** , that by default, contains only the `$PSVersionTable` from the originating session.</span></span> <span data-ttu-id="0e35c-297">**Applicationarguments** プロパティにデータを追加するには、コマンドレットの **applicationarguments** パラメーターを使用し `New-PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-297">To add data to the **ApplicationArguments** property, use the **ApplicationArguments** parameter of the `New-PSSessionOption` cmdlet.</span></span>

### <a name="psuiculture"></a><span data-ttu-id="0e35c-298">$PSUICulture</span><span class="sxs-lookup"><span data-stu-id="0e35c-298">$PSUICulture</span></span>

<span data-ttu-id="0e35c-299">オペレーティングシステムで現在使用されているユーザーインターフェイス (UI) カルチャの名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-299">Contains the name of the user interface (UI) culture that's currently in use in the operating system.</span></span> <span data-ttu-id="0e35c-300">UI カルチャは、どのテキスト文字列がメニューやメッセージなどのユーザー インターフェイス要素に使用されるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-300">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span> <span data-ttu-id="0e35c-301">これは、システムの **System.Globalization.CultureInfo.CurrentUICulture.Name** プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="0e35c-301">This is the value of the **System.Globalization.CultureInfo.CurrentUICulture.Name** property of the system.</span></span> <span data-ttu-id="0e35c-302">システムの **システムのグローバリゼーション** オブジェクトを取得するには、コマンドレットを使用し `Get-UICulture` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-302">To get the **System.Globalization.CultureInfo** object for the system, use the `Get-UICulture` cmdlet.</span></span>

### <a name="psversiontable"></a><span data-ttu-id="0e35c-303">$PSVersionTable</span><span class="sxs-lookup"><span data-stu-id="0e35c-303">$PSVersionTable</span></span>

<span data-ttu-id="0e35c-304">現在のセッションで実行されている PowerShell のバージョンに関する詳細を表示する読み取り専用のハッシュテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e35c-304">Contains a read-only hash table that displays details about the version of PowerShell that is running in the current session.</span></span> <span data-ttu-id="0e35c-305">この表には、次の項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e35c-305">The table includes the following items:</span></span>

| <span data-ttu-id="0e35c-306">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0e35c-306">Property</span></span>                  | <span data-ttu-id="0e35c-307">説明</span><span class="sxs-lookup"><span data-stu-id="0e35c-307">Description</span></span>                                   |
| ------------------------- | --------------------------------------------- |
| <span data-ttu-id="0e35c-308">**PSVersion**</span><span class="sxs-lookup"><span data-stu-id="0e35c-308">**PSVersion**</span></span>             | <span data-ttu-id="0e35c-309">PowerShell のバージョン番号</span><span class="sxs-lookup"><span data-stu-id="0e35c-309">The PowerShell version number</span></span>                 |
| <span data-ttu-id="0e35c-310">**PSEdition**</span><span class="sxs-lookup"><span data-stu-id="0e35c-310">**PSEdition**</span></span>             | <span data-ttu-id="0e35c-311">このプロパティの値は、</span><span class="sxs-lookup"><span data-stu-id="0e35c-311">This property has the value of 'Desktop' for</span></span>  |
|                           | <span data-ttu-id="0e35c-312">Powershell 4 以降、PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e35c-312">PowerShell 4 and below as well as PowerShell</span></span>  |
|                           | <span data-ttu-id="0e35c-313">5.1 は、すべての機能を備えた Windows エディションに対応しています。</span><span class="sxs-lookup"><span data-stu-id="0e35c-313">5.1 on full-featured Windows editions.</span></span>        |
|                           | <span data-ttu-id="0e35c-314">このプロパティの値は、</span><span class="sxs-lookup"><span data-stu-id="0e35c-314">This property has the value of 'Core' for</span></span>     |
|                           | <span data-ttu-id="0e35c-315">Powershell と powershell 6 以降</span><span class="sxs-lookup"><span data-stu-id="0e35c-315">PowerShell 6 and above as well as PowerShell</span></span>  |
|                           | <span data-ttu-id="0e35c-316">フットプリントが縮小されたエディションでの PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="0e35c-316">PowerShell 5.1 on reduced-footprint editions</span></span>  |
|                           | <span data-ttu-id="0e35c-317">Windows Nano Server や Windows IoT と同様です。</span><span class="sxs-lookup"><span data-stu-id="0e35c-317">like Windows Nano Server or Windows IoT.</span></span>      |
| <span data-ttu-id="0e35c-318">**GitCommitId**</span><span class="sxs-lookup"><span data-stu-id="0e35c-318">**GitCommitId**</span></span>           | <span data-ttu-id="0e35c-319">ソースファイルのコミット Id (GitHub)</span><span class="sxs-lookup"><span data-stu-id="0e35c-319">The commit Id of the source files, in GitHub,</span></span> |
| <span data-ttu-id="0e35c-320">**OS**</span><span class="sxs-lookup"><span data-stu-id="0e35c-320">**OS**</span></span>                    | <span data-ttu-id="0e35c-321">オペレーティングシステムの説明</span><span class="sxs-lookup"><span data-stu-id="0e35c-321">Description of the operating system that</span></span>      |
|                           | <span data-ttu-id="0e35c-322">PowerShell はで実行されています。</span><span class="sxs-lookup"><span data-stu-id="0e35c-322">PowerShell is running on.</span></span>                     |
| <span data-ttu-id="0e35c-323">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="0e35c-323">**Platform**</span></span>              | <span data-ttu-id="0e35c-324">オペレーティングシステムが実行されているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="0e35c-324">Platform that the operating system is running</span></span> |
|                           | <span data-ttu-id="0e35c-325">。</span><span class="sxs-lookup"><span data-stu-id="0e35c-325">on.</span></span> <span data-ttu-id="0e35c-326">Linux と macOS の値は **Unix** です。</span><span class="sxs-lookup"><span data-stu-id="0e35c-326">The value on Linux and macOS is **Unix**.</span></span> |
|                           | <span data-ttu-id="0e35c-327">`$IsMacOs` と `$IsLinux` を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e35c-327">See `$IsMacOs` and `$IsLinux`.</span></span>                |
| <span data-ttu-id="0e35c-328">**Ps互換バージョン**</span><span class="sxs-lookup"><span data-stu-id="0e35c-328">**PSCompatibleVersions**</span></span>  | <span data-ttu-id="0e35c-329">互換性のある PowerShell のバージョン</span><span class="sxs-lookup"><span data-stu-id="0e35c-329">Versions of PowerShell that are compatible</span></span>    |
|                           | <span data-ttu-id="0e35c-330">現在のバージョンで</span><span class="sxs-lookup"><span data-stu-id="0e35c-330">with the current version</span></span>                      |
| <span data-ttu-id="0e35c-331">**PSRemotingProtocolVersion**</span><span class="sxs-lookup"><span data-stu-id="0e35c-331">**PSRemotingProtocolVersion**</span></span> | <span data-ttu-id="0e35c-332">PowerShell リモートのバージョン</span><span class="sxs-lookup"><span data-stu-id="0e35c-332">The version of the PowerShell remote</span></span>      |
|                           | <span data-ttu-id="0e35c-333">管理プロトコル。</span><span class="sxs-lookup"><span data-stu-id="0e35c-333">management protocol.</span></span>                          |
| <span data-ttu-id="0e35c-334">**SerializationVersion**</span><span class="sxs-lookup"><span data-stu-id="0e35c-334">**SerializationVersion**</span></span>  | <span data-ttu-id="0e35c-335">シリアル化メソッドのバージョン</span><span class="sxs-lookup"><span data-stu-id="0e35c-335">The version of the serialization method</span></span>       |
| <span data-ttu-id="0e35c-336">**WSManStackVersion**</span><span class="sxs-lookup"><span data-stu-id="0e35c-336">**WSManStackVersion**</span></span>     | <span data-ttu-id="0e35c-337">WS-Management スタックのバージョン番号</span><span class="sxs-lookup"><span data-stu-id="0e35c-337">The version number of the WS-Management stack</span></span> |

### <a name="pwd"></a><span data-ttu-id="0e35c-338">$PWD</span><span class="sxs-lookup"><span data-stu-id="0e35c-338">$PWD</span></span>

<span data-ttu-id="0e35c-339">現在のディレクトリの完全パスを表す path オブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-339">Contains a path object that represents the full path of the current directory.</span></span>

### <a name="sender"></a><span data-ttu-id="0e35c-340">$Sender</span><span class="sxs-lookup"><span data-stu-id="0e35c-340">$Sender</span></span>

<span data-ttu-id="0e35c-341">このイベントを生成したオブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-341">Contains the object that generated this event.</span></span> <span data-ttu-id="0e35c-342">この変数は、イベント登録コマンドのアクションブロック内でのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-342">This variable is populated only within the Action block of an event registration command.</span></span> <span data-ttu-id="0e35c-343">この変数の値は、を返す **PSEventArgs** オブジェクトの Sender プロパティにもあり `Get-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-343">The value of this variable can also be found in the Sender property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="shellid"></a><span data-ttu-id="0e35c-344">$ShellId</span><span class="sxs-lookup"><span data-stu-id="0e35c-344">$ShellId</span></span>

<span data-ttu-id="0e35c-345">現在のシェルの識別子を格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-345">Contains the identifier of the current shell.</span></span>

### <a name="stacktrace"></a><span data-ttu-id="0e35c-346">$StackTrace</span><span class="sxs-lookup"><span data-stu-id="0e35c-346">$StackTrace</span></span>

<span data-ttu-id="0e35c-347">最新のエラーのスタックトレースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e35c-347">Contains a stack trace for the most recent error.</span></span>

### <a name="switch"></a><span data-ttu-id="0e35c-348">$switch</span><span class="sxs-lookup"><span data-stu-id="0e35c-348">$switch</span></span>

<span data-ttu-id="0e35c-349">ステートメントの結果の値ではない列挙子を格納し `Switch` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-349">Contains the enumerator not the resulting values of a `Switch` statement.</span></span> <span data-ttu-id="0e35c-350">変数は、 `$switch` ステートメントの実行中にのみ存在し、 `Switch` ステートメントの実行が完了すると削除され `switch` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-350">The `$switch` variable exists only while the `Switch` statement is running; it's deleted when the `switch` statement completes execution.</span></span> <span data-ttu-id="0e35c-351">詳細については、「 [about_Switch](about_Switch.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e35c-351">For more information, see [about_Switch](about_Switch.md).</span></span>

<span data-ttu-id="0e35c-352">列挙子には、ループ値を取得したり、現在のループの反復を変更したりするために使用できるプロパティとメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e35c-352">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="0e35c-353">詳細については、「 [列挙子の使用](#using-enumerators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e35c-353">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="this"></a><span data-ttu-id="0e35c-354">$this</span><span class="sxs-lookup"><span data-stu-id="0e35c-354">$this</span></span>

<span data-ttu-id="0e35c-355">スクリプトプロパティまたはスクリプトメソッドを定義するスクリプトブロックでは、 `$this` 変数は拡張されるオブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-355">In a script block that defines a script property or script method, the `$this` variable refers to the object that is being extended.</span></span>

<span data-ttu-id="0e35c-356">カスタムクラスでは、変数はクラス `$this` オブジェクト自体を参照し、クラスで定義されているプロパティとメソッドにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="0e35c-356">In a custom class, the `$this` variable refers to the class object itself allowing access to properties and methods defined in the class.</span></span>

### <a name="true"></a><span data-ttu-id="0e35c-357">$true</span><span class="sxs-lookup"><span data-stu-id="0e35c-357">$true</span></span>

<span data-ttu-id="0e35c-358">**True** を格納します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-358">Contains **True**.</span></span> <span data-ttu-id="0e35c-359">この変数を使用すると、コマンドとスクリプトで **True** を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-359">You can use this variable to represent **True** in commands and scripts.</span></span>

## <a name="using-enumerators"></a><span data-ttu-id="0e35c-360">列挙子の使用</span><span class="sxs-lookup"><span data-stu-id="0e35c-360">Using Enumerators</span></span>

<span data-ttu-id="0e35c-361">`$input`、 `$foreach` 、およびの `$switch` 各変数は、含まれているコードブロックによって処理される値を反復処理するために使用されるすべての列挙子です。</span><span class="sxs-lookup"><span data-stu-id="0e35c-361">The `$input`, `$foreach`, and `$switch` variables are all enumerators used to iterate through the values processed by their containing code block.</span></span>

<span data-ttu-id="0e35c-362">列挙子には、反復処理やイテレーション値の取得に使用できるプロパティとメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e35c-362">An enumerator contains properties and methods you can use to advance or reset iteration, or retrieve iteration values.</span></span> <span data-ttu-id="0e35c-363">列挙子を直接操作することは、ベストプラクティスとは見なされません。</span><span class="sxs-lookup"><span data-stu-id="0e35c-363">Directly manipulating enumerators isn't considered best practice.</span></span>

- <span data-ttu-id="0e35c-364">ループ内では、フロー制御キーワード [break](about_Break.md) と [continue](about_Continue.md) を優先する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e35c-364">Within loops, flow control keywords [break](about_Break.md) and [continue](about_Continue.md) should be preferred.</span></span>
- <span data-ttu-id="0e35c-365">パイプライン入力を受け入れる関数内では、 **Valuefrompipeline** 属性または **Valuefrompipelinebypropertyname** 属性でパラメーターを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0e35c-365">Within functions that accept pipeline input, it's best practice to use Parameters with the **ValueFromPipeline** or **ValueFromPipelineByPropertyName** attributes.</span></span>

  <span data-ttu-id="0e35c-366">詳細については、「 [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e35c-366">For more information, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="movenext"></a><span data-ttu-id="0e35c-367">MoveNext</span><span class="sxs-lookup"><span data-stu-id="0e35c-367">MoveNext</span></span>

<span data-ttu-id="0e35c-368">[MoveNext](/dotnet/api/system.collections.ienumerator.movenext)メソッドは、列挙子をコレクションの次の要素に進めます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-368">The [MoveNext](/dotnet/api/system.collections.ienumerator.movenext) method advances the enumerator to the next element of the collection.</span></span> <span data-ttu-id="0e35c-369">列挙子が正常に拡張された場合、 **MoveNext** は **True** を返します。列挙子がコレクションの末尾を越えた場合は **False** を返します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-369">**MoveNext** returns **True** if the enumerator was successfully advanced, **False** if the enumerator has passed the end of the collection.</span></span>

> [!NOTE]
> <span data-ttu-id="0e35c-370">返さ **れた戻り値は** 、出力ストリームに **送信され** ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-370">The **Boolean** value returned my **MoveNext** is sent to the output stream.</span></span>
> <span data-ttu-id="0e35c-371">出力を抑制するには、出力を typecasting する `[void]` か、 [Out-Null](xref:Microsoft.PowerShell.Core.Out-Null)にパイプします。</span><span class="sxs-lookup"><span data-stu-id="0e35c-371">You can suppress the output by typecasting it to `[void]` or piping it to [Out-Null](xref:Microsoft.PowerShell.Core.Out-Null).</span></span>
>
> ```powershell
> $input.MoveNext() | Out-Null
> ```
>
> ```powershell
> [void]$input.MoveNext()
> ```

### <a name="reset"></a><span data-ttu-id="0e35c-372">Reset</span><span class="sxs-lookup"><span data-stu-id="0e35c-372">Reset</span></span>

<span data-ttu-id="0e35c-373">[Reset](/dotnet/api/system.collections.ienumerator.reset)メソッドは、列挙子を初期位置、つまりコレクション内の最初の要素の **前** に設定します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-373">The [Reset](/dotnet/api/system.collections.ienumerator.reset) method sets the enumerator to its initial position, which is **before** the first element in the collection.</span></span>

### <a name="current"></a><span data-ttu-id="0e35c-374">Current</span><span class="sxs-lookup"><span data-stu-id="0e35c-374">Current</span></span>

<span data-ttu-id="0e35c-375">[現在](/dotnet/api/system.collections.ienumerator.current)のプロパティは、列挙子の現在位置にある、コレクションまたはパイプライン内の要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-375">The [Current](/dotnet/api/system.collections.ienumerator.current) property gets the element in the collection, or pipeline, at the current position of the enumerator.</span></span>

<span data-ttu-id="0e35c-376">**現在** のプロパティは、 **MoveNext** が呼び出されるまで、同じプロパティを返し続けます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-376">The **Current** property continues to return the same property until **MoveNext** is called.</span></span>

## <a name="examples"></a><span data-ttu-id="0e35c-377">例</span><span class="sxs-lookup"><span data-stu-id="0e35c-377">Examples</span></span>

### <a name="example-1-using-the-input-variable"></a><span data-ttu-id="0e35c-378">例 1: $input 変数の使用</span><span class="sxs-lookup"><span data-stu-id="0e35c-378">Example 1: Using the $input variable</span></span>

<span data-ttu-id="0e35c-379">次の例では、変数にアクセスすると、 `$input` 次にプロセスブロックが実行されるまで変数がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-379">In the following example, accessing the `$input` variable clears the variable until the next time the process block executes.</span></span> <span data-ttu-id="0e35c-380">**Reset** メソッドを使用すると、 `$input` 変数が現在のパイプライン値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-380">Using the **Reset** method resets the `$input` variable to the current pipeline value.</span></span>

```powershell
function Test
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        "`tInput: $input"
        "`tAccess Again: $input"
        $input.Reset()
        "`tAfter Reset: $input"
    }
}

"one","two" | Test
```

```Output
Iteration: 0
    Input: one
    Access Again:
    After Reset: one
Iteration: 1
    Input: two
    Access Again:
    After Reset: two
```

<span data-ttu-id="0e35c-381">プロセスブロックは、 `$input` アクセスしない場合でも変数を自動的に進めます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-381">The process block automatically advances the `$input` variable even if you don't access it.</span></span>

```powershell
$skip = $true
function Skip
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        if ($skip)
        {
            "`tSkipping"
            $skip = $false
        }
        else
        {
            "`tInput: $input"
        }
    }
}

"one","two" | Skip
```

```Output
Iteration: 0
    Skipping
Iteration: 1
    Input: two
```

### <a name="example-2-using-input-outside-the-process-block"></a><span data-ttu-id="0e35c-382">例 2: プロセスブロックの外部での $input の使用</span><span class="sxs-lookup"><span data-stu-id="0e35c-382">Example 2: Using $input outside the process block</span></span>

<span data-ttu-id="0e35c-383">プロセスブロックの外部では、 `$input` 変数は関数にパイプされたすべての値を表します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-383">Outside of the process block the `$input` variable represents all the values piped into the function.</span></span>

- <span data-ttu-id="0e35c-384">変数にアクセスすると、 `$input` すべての値がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-384">Accessing the `$input` variable clears all values.</span></span>
- <span data-ttu-id="0e35c-385">**Reset** メソッドは、コレクション全体をリセットします。</span><span class="sxs-lookup"><span data-stu-id="0e35c-385">The **Reset** method resets the entire collection.</span></span>
- <span data-ttu-id="0e35c-386">**現在** のプロパティは設定されません。</span><span class="sxs-lookup"><span data-stu-id="0e35c-386">The **Current** property is never populated.</span></span>
- <span data-ttu-id="0e35c-387">コレクションを高度にすることはできないため、 **MoveNext** メソッドは false を返します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-387">The **MoveNext** method returns false because the collection can't be advanced.</span></span>
  - <span data-ttu-id="0e35c-388">**MoveNext** を呼び出すと、変数がクリアさ `$input` れます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-388">Calling **MoveNext** clears out the `$input` variable.</span></span>

```powershell
Function All
{
    "All Values: $input"
    "Access Again: $input"
    $input.Reset()
    "After Reset: $input"
    $input.MoveNext() | Out-Null
    "After MoveNext: $input"
}

"one","two","three" | All
```

```Output
All Values: one two three
Access Again:
After Reset: one two three
After MoveNext:
```

### <a name="example-3-using-the-inputcurrent-property"></a><span data-ttu-id="0e35c-389">例 3: $input の使用現在のプロパティ</span><span class="sxs-lookup"><span data-stu-id="0e35c-389">Example 3: Using the $input.Current property</span></span>

<span data-ttu-id="0e35c-390">**現在** のプロパティを使用して、 **Reset** メソッドを使用せずに、現在のパイプライン値に複数回アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-390">By using the **Current** property, the current pipeline value can be accessed multiple times without using the **Reset** method.</span></span> <span data-ttu-id="0e35c-391">プロセスブロックは自動的に **MoveNext** メソッドを呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="0e35c-391">The process block doesn't automatically call the **MoveNext** method.</span></span>

<span data-ttu-id="0e35c-392">明示的に **MoveNext** を呼び出さない限り、 **現在** のプロパティには値が設定されません。</span><span class="sxs-lookup"><span data-stu-id="0e35c-392">The **Current** property will never be populated unless you explicitly call **MoveNext**.</span></span> <span data-ttu-id="0e35c-393">**現在** のプロパティには、その値をクリアせずに、プロセスブロック内で複数回アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-393">The **Current** property can be accessed multiple times inside the process block without clearing its value.</span></span>

```powershell
function Current
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        "`tBefore MoveNext: $($input.Current)"
        $input.MoveNext() | Out-Null
        "`tAfter MoveNext: $($input.Current)"
        "`tAccess Again: $($input.Current)"
    }
}

"one","two" | Current
```

```Output
Iteration: 0
    Before MoveNext:
    After MoveNext: one
    Access Again: one
Iteration: 1
    Before MoveNext:
    After MoveNext: two
    Access Again: two
```

### <a name="example-4-using-the-foreach-variable"></a><span data-ttu-id="0e35c-394">例 4: $foreach 変数の使用</span><span class="sxs-lookup"><span data-stu-id="0e35c-394">Example 4: Using the $foreach variable</span></span>

<span data-ttu-id="0e35c-395">変数とは異なり、 `$input` 変数は、 `$foreach` 直接アクセスされるときに常にコレクション内のすべての項目を表します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-395">Unlike the `$input` variable, the `$foreach` variable always represents all items in the collection when accessed directly.</span></span> <span data-ttu-id="0e35c-396">**現在のプロパティを** 使用して現在のコレクション要素にアクセスし、 **Reset** メソッドと **MoveNext** メソッドを使用してその値を変更します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-396">Use the **Current** property to access the current collection element, and the **Reset** and **MoveNext** methods to change its value.</span></span>

> [!NOTE]
> <span data-ttu-id="0e35c-397">ループの各反復処理で `foreach` は、 **MoveNext** メソッドが自動的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-397">Each iteration of the `foreach` loop will automatically call the **MoveNext** method.</span></span>

<span data-ttu-id="0e35c-398">次のループは2回だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-398">The following loop only executes twice.</span></span> <span data-ttu-id="0e35c-399">2番目の反復処理では、反復処理が完了する前にコレクションが3番目の要素に移動されます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-399">In the second iteration, the collection is moved to the third element before the iteration is complete.</span></span> <span data-ttu-id="0e35c-400">2番目の反復処理の後、反復処理する値がなくなり、ループが終了します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-400">After the second iteration, there are now no more values to iterate, and the loop terminates.</span></span>

<span data-ttu-id="0e35c-401">**MoveNext** プロパティは、コレクション () を反復処理するために選択された変数には影響しません `$Num` 。</span><span class="sxs-lookup"><span data-stu-id="0e35c-401">The **MoveNext** property doesn't affect the variable chosen to iterate through the collection (`$Num`).</span></span>

```powershell
$i = 0
foreach ($num in ("one","two","three"))
{
    "Iteration: $i"
    $i++
    "`tNum: $num"
    "`tCurrent: $($foreach.Current)"

    if ($foreach.Current -eq "two")
    {
        "Before MoveNext (Current): $($foreach.Current)"
        $foreach.MoveNext() | Out-Null
        "After MoveNext (Current): $($foreach.Current)"
        "Num has not changed: $num"
    }
}
```

```Output
Iteration: 0
        Num: one
        Current: one
Iteration: 1
        Num: two
        Current: two
Before MoveNext (Current): two
After MoveNext (Current): three
Num has not changed: two
```

<span data-ttu-id="0e35c-402">**Reset** メソッドを使用すると、コレクション内の現在の要素がリセットされます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-402">Using the **Reset** method resets the current element in the collection.</span></span> <span data-ttu-id="0e35c-403">次の例では、 **Reset** メソッドが呼び出されるため、最初の2つの要素を **2 回** ループします。</span><span class="sxs-lookup"><span data-stu-id="0e35c-403">The following example loops through the first two elements **twice** because the **Reset** method is called.</span></span> <span data-ttu-id="0e35c-404">最初の2つのループの後、 `if` ステートメントは失敗し、ループは3つのすべての要素を通常どおり反復処理します。</span><span class="sxs-lookup"><span data-stu-id="0e35c-404">After the first two loops, the `if` statement fails and the loop iterates through all three elements normally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e35c-405">これにより、無限ループが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e35c-405">This could result in an infinite loop.</span></span>

```powershell
$stopLoop = 0
foreach ($num in ("one","two", "three"))
{
    ("`t" * $stopLoop) + "Current: $($foreach.Current)"

    if ($num -eq "two" -and $stopLoop -lt 2)
    {
        $foreach.Reset() | Out-Null
        ("`t" * $stopLoop) + "Reset Loop: $stopLoop"
        $stopLoop++
    }
}
```

```Output
Current: one
Current: two
Reset Loop: 0
        Current: one
        Current: two
        Reset Loop: 1
                Current: one
                Current: two
                Current: three
```

### <a name="example-5-using-the-switch-variable"></a><span data-ttu-id="0e35c-406">例 5: $switch 変数を使用する</span><span class="sxs-lookup"><span data-stu-id="0e35c-406">Example 5: Using the $switch variable</span></span>

<span data-ttu-id="0e35c-407">変数には、 `$switch` 変数とまったく同じ規則があり `$foreach` ます。</span><span class="sxs-lookup"><span data-stu-id="0e35c-407">The `$switch` variable has the exact same rules as the `$foreach` variable.</span></span>
<span data-ttu-id="0e35c-408">次の例は、すべての列挙子の概念を示しています。</span><span class="sxs-lookup"><span data-stu-id="0e35c-408">The following example demonstrates all the enumerator concepts.</span></span>

> [!NOTE]
> <span data-ttu-id="0e35c-409">MoveNext メソッドの後にステートメントが存在しない場合でも、Note のよう **な大文字** と小文字の区別が実行されないことに注意して `break` ください。 **MoveNext**</span><span class="sxs-lookup"><span data-stu-id="0e35c-409">Note how the **NotEvaluated** case is never executed, even though there's no `break` statement after the **MoveNext** method.</span></span>

```powershell
$values = "Start", "MoveNext", "NotEvaluated", "Reset", "End"
$stopInfinite = $false
switch ($values)
{
    "MoveNext" {
        "`tMoveNext"
        $switch.MoveNext() | Out-Null
        "`tAfter MoveNext: $($switch.Current)"
    }
    # This case is never evaluated.
    "NotEvaluated" {
        "`tAfterMoveNext: $($switch.Current)"
    }

    "Reset" {
        if (!$stopInfinite)
        {
            "`tReset"
            $switch.Reset()
            $stopInfinite = $true
        }
    }

    default {
        "Default (Current): $($switch.Current)"
    }
}
```

```Output
Default (Current): Start
    MoveNext
    After MoveNext: NotEvaluated
    Reset
Default (Current): Start
    MoveNext
    After MoveNext: NotEvaluated
Default (Current): End
```

## <a name="see-also"></a><span data-ttu-id="0e35c-410">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e35c-410">See also</span></span>

[<span data-ttu-id="0e35c-411">about_Functions</span><span class="sxs-lookup"><span data-stu-id="0e35c-411">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="0e35c-412">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="0e35c-412">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="0e35c-413">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="0e35c-413">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="0e35c-414">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="0e35c-414">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="0e35c-415">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="0e35c-415">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="0e35c-416">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="0e35c-416">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="0e35c-417">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="0e35c-417">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="0e35c-418">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="0e35c-418">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="0e35c-419">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="0e35c-419">about_Splatting</span></span>](about_Splatting.md)

[<span data-ttu-id="0e35c-420">about_Variables</span><span class="sxs-lookup"><span data-stu-id="0e35c-420">about_Variables</span></span>](about_Variables.md)
