---
description: PowerShell の状態情報を格納する変数について説明します。 これらの変数は、PowerShell によって作成および管理されます。
Locale: en-US
ms.date: 12/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_automatic_variables?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Automatic_Variables
ms.openlocfilehash: 8a2410dd2adcc1679ab203293b4c4e712b960278
ms.sourcegitcommit: 3a1d80e27438976101f216b8c3d623c61b868db8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "99975143"
---
# <a name="about-automatic-variables"></a><span data-ttu-id="99754-104">自動変数について</span><span class="sxs-lookup"><span data-stu-id="99754-104">About Automatic Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="99754-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="99754-105">Short description</span></span>

<span data-ttu-id="99754-106">PowerShell の状態情報を格納する変数について説明します。</span><span class="sxs-lookup"><span data-stu-id="99754-106">Describes variables that store state information for PowerShell.</span></span> <span data-ttu-id="99754-107">これらの変数は、PowerShell によって作成および管理されます。</span><span class="sxs-lookup"><span data-stu-id="99754-107">These variables are created and maintained by PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="99754-108">長い説明</span><span class="sxs-lookup"><span data-stu-id="99754-108">Long description</span></span>

<span data-ttu-id="99754-109">概念的には、これらの変数は読み取り専用と見なされます。</span><span class="sxs-lookup"><span data-stu-id="99754-109">Conceptually, these variables are considered to be read-only.</span></span> <span data-ttu-id="99754-110">これらをに書き込む **ことはできますが** 、旧バージョンとの互換性のために書き込ま **ない** でください。</span><span class="sxs-lookup"><span data-stu-id="99754-110">Even though they **can** be written to, for backward compatibility they **should not** be written to.</span></span>

<span data-ttu-id="99754-111">PowerShell の自動変数の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="99754-111">Here is a list of the automatic variables in PowerShell:</span></span>

### <a name=""></a>$$

<span data-ttu-id="99754-112">セッションによって受信された最後の行の最後のトークンを格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-112">Contains the last token in the last line received by the session.</span></span>

### <a name=""></a><span data-ttu-id="99754-113">$?</span><span class="sxs-lookup"><span data-stu-id="99754-113">$?</span></span>

<span data-ttu-id="99754-114">最後のコマンドの実行状態を格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-114">Contains the execution status of the last command.</span></span> <span data-ttu-id="99754-115">最後のコマンドが成功した場合は **True** 、失敗した場合は **False** が格納されます。</span><span class="sxs-lookup"><span data-stu-id="99754-115">It contains **True** if the last command succeeded and **False** if it failed.</span></span>

<span data-ttu-id="99754-116">パイプライン内の複数の段階で実行されるコマンドレットおよび拡張関数の場合 (およびブロックの両方で) は、とのように、またはの各ポイントでを `process` `end` 呼び出すと、 `this.WriteError()` `$PSCmdlet.WriteError()` `$?` **False** に設定され `this.ThrowTerminatingError()` `$PSCmdlet.ThrowTerminatingError()` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-116">For cmdlets and advanced functions that are run at multiple stages in a pipeline, for example in both `process` and `end` blocks, calling `this.WriteError()` or `$PSCmdlet.WriteError()` respectively at any point will set `$?` to **False**, as will `this.ThrowTerminatingError()` and `$PSCmdlet.ThrowTerminatingError()`.</span></span>

<span data-ttu-id="99754-117">`Write-Error`コマンドレットは、 `$?` 実行された直後に **false** に設定されますが、 `$?` それを呼び出す関数の場合は **false** に設定されません。</span><span class="sxs-lookup"><span data-stu-id="99754-117">The `Write-Error` cmdlet always sets `$?` to **False** immediately after it is executed, but will not set `$?` to **False** for a function calling it:</span></span>

```powershell
function Test-WriteError
{
    Write-Error "Bad"
    $? # $false
}

Test-WriteError
$? # $true
```

<span data-ttu-id="99754-118">後者の場合は、 `$PSCmdlet.WriteError()` 代わりにを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99754-118">For the latter purpose, `$PSCmdlet.WriteError()` should be used instead.</span></span>

<span data-ttu-id="99754-119">ネイティブコマンド (実行可能ファイル) の場合、が `$?` 0 の場合は **True** に設定され、 `$LASTEXITCODE` が他の値の場合は **False** に設定され `$LASTEXITCODE` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-119">For native commands (executables), `$?` is set to **True** when `$LASTEXITCODE` is 0, and set to **False** when `$LASTEXITCODE` is any other value.</span></span>

> [!NOTE]
> <span data-ttu-id="99754-120">PowerShell 7 までは、かっこ内にステートメントが含ま `(...)` れている限り、部分式構文 `$(...)` または配列式は常に true にリセットされるので、は `@(...)` `$?` true になり `(Write-Error)` `$?` ます。 </span><span class="sxs-lookup"><span data-stu-id="99754-120">Until PowerShell 7, containing a statement within parentheses `(...)`, subexpression syntax `$(...)` or array expression `@(...)` always reset `$?` to **True**, so that `(Write-Error)` shows `$?` as **True**.</span></span>
> <span data-ttu-id="99754-121">これは PowerShell 7 で変更されているため、 `$?` は常に、これらの式で最後に実行されたコマンドの実際の成功を反映します。</span><span class="sxs-lookup"><span data-stu-id="99754-121">This has been changed in PowerShell 7, so that `$?` will always reflect the actual success of the last command run in these expressions.</span></span>

### <a name=""></a>$^

<span data-ttu-id="99754-122">セッションによって受信された最後の行の最初のトークンを格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-122">Contains the first token in the last line received by the session.</span></span>

### <a name="_"></a><span data-ttu-id="99754-123">$_</span><span class="sxs-lookup"><span data-stu-id="99754-123">$_</span></span>

<span data-ttu-id="99754-124">`$PSItem` と同じ。</span><span class="sxs-lookup"><span data-stu-id="99754-124">Same as `$PSItem`.</span></span> <span data-ttu-id="99754-125">パイプラインオブジェクトの現在のオブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-125">Contains the current object in the pipeline object.</span></span> <span data-ttu-id="99754-126">この変数は、パイプライン内のすべてのオブジェクトまたは選択したオブジェクトに対してアクションを実行するコマンドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="99754-126">You can use this variable in commands that perform an action on every object or on selected objects in a pipeline.</span></span>

### <a name="args"></a><span data-ttu-id="99754-127">$args</span><span class="sxs-lookup"><span data-stu-id="99754-127">$args</span></span>

<span data-ttu-id="99754-128">関数、スクリプト、またはスクリプトブロックに渡される、宣言されていないパラメーターの値の配列を格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-128">Contains an array of values for undeclared parameters that are passed to a function, script, or script block.</span></span> <span data-ttu-id="99754-129">関数を作成するときに、キーワードを使用する `param` か、関数名の後にパラメーターのコンマ区切りリストをかっこで追加することによって、パラメーターを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="99754-129">When you create a function, you can declare the parameters by using the `param` keyword or by adding a comma-separated list of parameters in parentheses after the function name.</span></span>

<span data-ttu-id="99754-130">イベントアクションでは、変数には、 `$args` 処理中のイベントのイベント引数を表すオブジェクトが格納されます。</span><span class="sxs-lookup"><span data-stu-id="99754-130">In an event action, the `$args` variable contains objects that represent the event arguments of the event that is being processed.</span></span> <span data-ttu-id="99754-131">この変数は、 `Action` イベント登録コマンドのブロック内でのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="99754-131">This variable is populated only within the `Action` block of an event registration command.</span></span>
<span data-ttu-id="99754-132">この変数の値は、を返す **PSEventArgs** オブジェクトの **sourceargs** プロパティにもあり `Get-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-132">The value of this variable can also be found in the **SourceArgs** property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="consolefilename"></a><span data-ttu-id="99754-133">$ConsoleFileName</span><span class="sxs-lookup"><span data-stu-id="99754-133">$ConsoleFileName</span></span>

<span data-ttu-id="99754-134">セッションで最近使用されたコンソールファイル () のパスを格納し `.psc1` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-134">Contains the path of the console file (`.psc1`) that was most recently used in the session.</span></span> <span data-ttu-id="99754-135">この変数は、 **Psconsolefile** パラメーターを使用して PowerShell を起動したとき、またはコマンドレットを使用して `Export-Console` スナップイン名をコンソールファイルにエクスポートしたときに設定されます。</span><span class="sxs-lookup"><span data-stu-id="99754-135">This variable is populated when you start PowerShell with the **PSConsoleFile** parameter or when you use the `Export-Console` cmdlet to export snap-in names to a console file.</span></span>

<span data-ttu-id="99754-136">`Export-Console`パラメーターを指定せずにコマンドレットを使用すると、セッションで最後に使用されたコンソールファイルが自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="99754-136">When you use the `Export-Console` cmdlet without parameters, it automatically updates the console file that was most recently used in the session.</span></span> <span data-ttu-id="99754-137">この自動変数を使用すると、どのファイルを更新するかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="99754-137">You can use this automatic variable to determine which file will be updated.</span></span>

### <a name="error"></a><span data-ttu-id="99754-138">$Error</span><span class="sxs-lookup"><span data-stu-id="99754-138">$Error</span></span>

<span data-ttu-id="99754-139">最新のエラーを表すエラーオブジェクトの配列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="99754-139">Contains an array of error objects that represent the most recent errors.</span></span>
<span data-ttu-id="99754-140">最新のエラーは、配列内の最初のエラーオブジェクトです `$Error[0]` 。</span><span class="sxs-lookup"><span data-stu-id="99754-140">The most recent error is the first error object in the array `$Error[0]`.</span></span>

<span data-ttu-id="99754-141">エラーが配列に追加されないようにするには `$Error` 、 **erroraction** 共通パラメーターに値 **Ignore** を指定します。</span><span class="sxs-lookup"><span data-stu-id="99754-141">To prevent an error from being added to the `$Error` array, use the **ErrorAction** common parameter with a value of **Ignore**.</span></span> <span data-ttu-id="99754-142">詳細については、「[about_CommonParameters](about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99754-142">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

### <a name="event"></a><span data-ttu-id="99754-143">$Event</span><span class="sxs-lookup"><span data-stu-id="99754-143">$Event</span></span>

<span data-ttu-id="99754-144">処理中のイベントを表す **PSEventArgs** オブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-144">Contains a **PSEventArgs** object that represents the event that is being processed.</span></span> <span data-ttu-id="99754-145">この変数は、などの `Action` イベント登録コマンドのブロック内でのみ設定され `Register-ObjectEvent` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-145">This variable is populated only within the `Action` block of an event registration command, such as `Register-ObjectEvent`.</span></span> <span data-ttu-id="99754-146">この変数の値は、コマンドレットが返すオブジェクトと同じです `Get-Event` 。</span><span class="sxs-lookup"><span data-stu-id="99754-146">The value of this variable is the same object that the `Get-Event` cmdlet returns.</span></span> <span data-ttu-id="99754-147">そのため、などの変数のプロパティを `Event` `$Event.TimeGenerated` スクリプトブロックで使用でき `Action` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-147">Therefore, you can use the properties of the `Event` variable, such as `$Event.TimeGenerated`, in an `Action` script block.</span></span>

### <a name="eventargs"></a><span data-ttu-id="99754-148">$EventArgs</span><span class="sxs-lookup"><span data-stu-id="99754-148">$EventArgs</span></span>

<span data-ttu-id="99754-149">処理中のイベントの **EventArgs** から派生した最初のイベント引数を表すオブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-149">Contains an object that represents the first event argument that derives from **EventArgs** of the event that is being processed.</span></span> <span data-ttu-id="99754-150">この変数は、 `Action` イベント登録コマンドのブロック内でのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="99754-150">This variable is populated only within the `Action` block of an event registration command.</span></span>
<span data-ttu-id="99754-151">この変数の値は、を返す **PSEventArgs** オブジェクトの **sourceeventargs** プロパティにもあり `Get-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-151">The value of this variable can also be found in the **SourceEventArgs** property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="eventsubscriber"></a><span data-ttu-id="99754-152">$EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="99754-152">$EventSubscriber</span></span>

<span data-ttu-id="99754-153">処理中のイベントのイベントサブスクライバーを表す **PSEventSubscriber** オブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-153">Contains a **PSEventSubscriber** object that represents the event subscriber of the event that is being processed.</span></span> <span data-ttu-id="99754-154">この変数は、 `Action` イベント登録コマンドのブロック内でのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="99754-154">This variable is populated only within the `Action` block of an event registration command.</span></span> <span data-ttu-id="99754-155">この変数の値は、コマンドレットが返すオブジェクトと同じです `Get-EventSubscriber` 。</span><span class="sxs-lookup"><span data-stu-id="99754-155">The value of this variable is the same object that the `Get-EventSubscriber` cmdlet returns.</span></span>

### <a name="executioncontext"></a><span data-ttu-id="99754-156">$ExecutionContext</span><span class="sxs-lookup"><span data-stu-id="99754-156">$ExecutionContext</span></span>

<span data-ttu-id="99754-157">PowerShell ホストの実行コンテキストを表す **EngineIntrinsics** オブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-157">Contains an **EngineIntrinsics** object that represents the execution context of the PowerShell host.</span></span> <span data-ttu-id="99754-158">この変数を使用すると、コマンドレットで使用できる実行オブジェクトを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="99754-158">You can use this variable to find the execution objects that are available to cmdlets.</span></span>

### <a name="false"></a><span data-ttu-id="99754-159">$false</span><span class="sxs-lookup"><span data-stu-id="99754-159">$false</span></span>

<span data-ttu-id="99754-160">**False** が含まれています。</span><span class="sxs-lookup"><span data-stu-id="99754-160">Contains **False**.</span></span> <span data-ttu-id="99754-161">この変数を使用すると、文字列 "false" を使用する代わりに、コマンドとスクリプトで **false** を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="99754-161">You can use this variable to represent **False** in commands and scripts instead of using the string "false".</span></span> <span data-ttu-id="99754-162">文字列は、空でない文字列または0以外の整数に変換される場合、 **True** として解釈できます。</span><span class="sxs-lookup"><span data-stu-id="99754-162">The string can be interpreted as **True** if it's converted to a non-empty string or to a non-zero integer.</span></span>

### <a name="foreach"></a><span data-ttu-id="99754-163">$foreach</span><span class="sxs-lookup"><span data-stu-id="99754-163">$foreach</span></span>

<span data-ttu-id="99754-164">[ForEach](about_ForEach.md)ループの列挙子 (結果の値ではない) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="99754-164">Contains the enumerator (not the resulting values) of a [ForEach](about_ForEach.md) loop.</span></span> <span data-ttu-id="99754-165">変数は、 `$ForEach` ループの実行中にのみ存在します。ループ `ForEach` が完了すると削除されます。</span><span class="sxs-lookup"><span data-stu-id="99754-165">The `$ForEach` variable exists only while the `ForEach` loop is running; it's deleted after the loop is completed.</span></span>

<span data-ttu-id="99754-166">列挙子には、ループ値を取得したり、現在のループの反復を変更したりするために使用できるプロパティとメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="99754-166">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="99754-167">詳細については、「 [列挙子の使用](#using-enumerators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99754-167">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="home"></a><span data-ttu-id="99754-168">$HOME</span><span class="sxs-lookup"><span data-stu-id="99754-168">$HOME</span></span>

<span data-ttu-id="99754-169">ユーザーのホームディレクトリの完全なパスを含みます。</span><span class="sxs-lookup"><span data-stu-id="99754-169">Contains the full path of the user's home directory.</span></span> <span data-ttu-id="99754-170">この変数は、 `"$env:homedrive$env:homepath"` 通常、Windows 環境変数に相当し `C:\Users\<UserName>` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-170">This variable is the equivalent of the `"$env:homedrive$env:homepath"` Windows environment variables, typically `C:\Users\<UserName>`.</span></span>

### <a name="host"></a><span data-ttu-id="99754-171">$Host</span><span class="sxs-lookup"><span data-stu-id="99754-171">$Host</span></span>

<span data-ttu-id="99754-172">PowerShell の現在のホストアプリケーションを表すオブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-172">Contains an object that represents the current host application for PowerShell.</span></span> <span data-ttu-id="99754-173">この変数を使用すると、コマンドで現在のホストを表すことや、ホストのプロパティを表示または変更することができ `$Host.version` ます。たとえば、やなど `$Host.CurrentCulture` `$host.ui.rawui.setbackgroundcolor("Red")` です。</span><span class="sxs-lookup"><span data-stu-id="99754-173">You can use this variable to represent the current host in commands or to display or change the properties of the host, such as `$Host.version` or `$Host.CurrentCulture`, or `$host.ui.rawui.setbackgroundcolor("Red")`.</span></span>

### <a name="input"></a><span data-ttu-id="99754-174">$input</span><span class="sxs-lookup"><span data-stu-id="99754-174">$input</span></span>

<span data-ttu-id="99754-175">関数に渡されるすべての入力を列挙する列挙子を格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-175">Contains an enumerator that enumerates all input that is passed to a function.</span></span> <span data-ttu-id="99754-176">変数は、 `$input` 関数とスクリプトブロック (名前のない関数) でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="99754-176">The `$input` variable is available only to functions and script blocks (which are unnamed functions).</span></span>

- <span data-ttu-id="99754-177">、、またはブロックのない関数では、 `Begin` `Process` `End` 変数は、 `$input` 関数へのすべての入力のコレクションを列挙します。</span><span class="sxs-lookup"><span data-stu-id="99754-177">In a function without a `Begin`, `Process`, or `End` block, the `$input` variable enumerates the collection of all input to the function.</span></span>

- <span data-ttu-id="99754-178">ブロックでは、 `Begin` `$input` 変数にデータが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="99754-178">In the `Begin` block, the `$input` variable contains no data.</span></span>

- <span data-ttu-id="99754-179">ブロック内の変数には、 `Process` `$input` 現在パイプライン内にあるオブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="99754-179">In the `Process` block, the `$input` variable contains the object that is currently in the pipeline.</span></span>

- <span data-ttu-id="99754-180">ブロックでは、 `End` 変数は、 `$input` 関数へのすべての入力のコレクションを列挙します。</span><span class="sxs-lookup"><span data-stu-id="99754-180">In the `End` block, the `$input` variable enumerates the collection of all input to the function.</span></span>

  > [!NOTE]
  > <span data-ttu-id="99754-181">`$input`同じ関数またはスクリプトブロックの中で、プロセスブロックと End ブロックの両方で変数を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="99754-181">You cannot use the `$input` variable inside both the Process block and the End block in the same function or script block.</span></span>

<span data-ttu-id="99754-182">`$input`は列挙子であるため、そのプロパティのいずれかにアクセスすると、が使用できなくなり `$input` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-182">Since `$input` is an enumerator, accessing any of it's properties causes `$input` to no longer be available.</span></span> <span data-ttu-id="99754-183">`$input`別の変数に格納して、プロパティを再利用することができ `$input` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-183">You can store `$input` in another variable to reuse the `$input` properties.</span></span>

<span data-ttu-id="99754-184">列挙子には、ループ値を取得したり、現在のループの反復を変更したりするために使用できるプロパティとメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="99754-184">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="99754-185">詳細については、「 [列挙子の使用](#using-enumerators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99754-185">For more information, see [Using Enumerators](#using-enumerators).</span></span>

<span data-ttu-id="99754-186">変数は、 `$input` `-Command` `pwsh` コマンドラインから呼び出されたときに、のパラメーターで指定したコマンドにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="99754-186">The `$input` variable is also available to the command specified by the `-Command` parameter of `pwsh` when invoked from the command line.</span></span> <span data-ttu-id="99754-187">次の例は、Windows コマンドシェルから実行されます。</span><span class="sxs-lookup"><span data-stu-id="99754-187">The following example is run from the Windows Command shell.</span></span>

```CMD
echo Hello | pwsh -Command """$input World!"""
```

### <a name="iscoreclr"></a><span data-ttu-id="99754-188">$IsCoreCLR</span><span class="sxs-lookup"><span data-stu-id="99754-188">$IsCoreCLR</span></span>

<span data-ttu-id="99754-189">`$True`現在のセッションが .Net Core ランタイム (CoreCLR) で実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="99754-189">Contains `$True` if the current session is running on the .NET Core Runtime (CoreCLR).</span></span> <span data-ttu-id="99754-190">それ以外 `$False` の場合は。</span><span class="sxs-lookup"><span data-stu-id="99754-190">Otherwise contains `$False`.</span></span>

### <a name="islinux"></a><span data-ttu-id="99754-191">$IsLinux</span><span class="sxs-lookup"><span data-stu-id="99754-191">$IsLinux</span></span>

<span data-ttu-id="99754-192">`$True`現在のセッションが Linux オペレーティングシステムで実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="99754-192">Contains `$True` if the current session is running on a Linux operating system.</span></span>
<span data-ttu-id="99754-193">それ以外 `$False` の場合は。</span><span class="sxs-lookup"><span data-stu-id="99754-193">Otherwise contains `$False`.</span></span>

### <a name="ismacos"></a><span data-ttu-id="99754-194">$IsMacOS</span><span class="sxs-lookup"><span data-stu-id="99754-194">$IsMacOS</span></span>

<span data-ttu-id="99754-195">`$True`現在のセッションが MacOS オペレーティングシステムで実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="99754-195">Contains `$True` if the current session is running on a MacOS operating system.</span></span>
<span data-ttu-id="99754-196">それ以外 `$False` の場合は。</span><span class="sxs-lookup"><span data-stu-id="99754-196">Otherwise contains `$False`.</span></span>

### <a name="iswindows"></a><span data-ttu-id="99754-197">$IsWindows</span><span class="sxs-lookup"><span data-stu-id="99754-197">$IsWindows</span></span>

<span data-ttu-id="99754-198">`$TRUE`現在のセッションが Windows オペレーティングシステムで実行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="99754-198">Contains `$TRUE` if the current session is running on a Windows operating system.</span></span> <span data-ttu-id="99754-199">それ以外 `$FALSE` の場合は。</span><span class="sxs-lookup"><span data-stu-id="99754-199">Otherwise contains `$FALSE`.</span></span>

### <a name="lastexitcode"></a><span data-ttu-id="99754-200">$LastExitCode</span><span class="sxs-lookup"><span data-stu-id="99754-200">$LastExitCode</span></span>

<span data-ttu-id="99754-201">最後に実行された Windows ベースのプログラムの終了コードを格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-201">Contains the exit code of the last Windows-based program that was run.</span></span>

### <a name="matches"></a><span data-ttu-id="99754-202">$Matches</span><span class="sxs-lookup"><span data-stu-id="99754-202">$Matches</span></span>

<span data-ttu-id="99754-203">変数は、 `Matches` `-match` 演算子と演算子と連携し `-notmatch` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-203">The `Matches` variable works with the `-match` and `-notmatch` operators.</span></span>
<span data-ttu-id="99754-204">スカラー入力を or 演算子に送信 `-match` `-notmatch` し、一方が一致を検出した場合は、ブール値を返し、 `$Matches` 一致した文字列値のハッシュテーブルで自動変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="99754-204">When you submit scalar input to the `-match` or `-notmatch` operator, and either one detects a match, they return a Boolean value and populate the `$Matches` automatic variable with a hash table of any string values that were matched.</span></span> <span data-ttu-id="99754-205">`$Matches`演算子で正規表現を使用する場合、ハッシュテーブルにキャプチャを設定することもでき `-match` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-205">The `$Matches` hash table can also be populated with captures when you use regular expressions with the `-match` operator.</span></span>

<span data-ttu-id="99754-206">オペレーターの詳細については `-match` 、「 [about_Comparison_Operators](about_comparison_operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99754-206">For more information about the `-match` operator, see [about_Comparison_Operators](about_comparison_operators.md).</span></span> <span data-ttu-id="99754-207">正規表現の詳細については、「 [about_Regular_Expressions](about_Regular_Expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99754-207">For more information on regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

### <a name="myinvocation"></a><span data-ttu-id="99754-208">$MyInvocation</span><span class="sxs-lookup"><span data-stu-id="99754-208">$MyInvocation</span></span>

<span data-ttu-id="99754-209">現在のコマンドに関する情報 (名前、パラメーター、パラメーター値など)、コマンドの開始、呼び出し、または呼び出しの方法 (現在のコマンドを呼び出したスクリプトの名前など) に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-209">Contains information about the current command, such as the name, parameters, parameter values, and information about how the command was started, called, or invoked, such as the name of the script that called the current command.</span></span>

<span data-ttu-id="99754-210">`$MyInvocation` は、スクリプト、関数、およびスクリプトブロックに対してのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="99754-210">`$MyInvocation` is populated only for scripts, function, and script blocks.</span></span> <span data-ttu-id="99754-211">現在のスクリプトの `$MyInvocation` パスとファイル名 ( `$MyInvocation.MyCommand.Path` )、または関数の名前 () を使用して現在のコマンドを `$MyInvocation.MyCommand.Name` 識別することで、InvocationInfo オブジェクトの情報を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="99754-211">You can use the information in the **System.Management.Automation.InvocationInfo** object that `$MyInvocation` returns in the current script, such as the path and file name of the script (`$MyInvocation.MyCommand.Path`) or the name of a function (`$MyInvocation.MyCommand.Name`) to identify the current command.</span></span> <span data-ttu-id="99754-212">これは、現在のスクリプトの名前を検索する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="99754-212">This is particularly useful for finding the name of the current script.</span></span>

<span data-ttu-id="99754-213">PowerShell 3.0 以降では、に `MyInvocation` 次の新しいプロパティが追加されています。</span><span class="sxs-lookup"><span data-stu-id="99754-213">Beginning in PowerShell 3.0, `MyInvocation` has the following new properties.</span></span>

| <span data-ttu-id="99754-214">プロパティ</span><span class="sxs-lookup"><span data-stu-id="99754-214">Property</span></span>      | <span data-ttu-id="99754-215">Description</span><span class="sxs-lookup"><span data-stu-id="99754-215">Description</span></span>                                         |
| ------------- | --------------------------------------------------- |
| <span data-ttu-id="99754-216">**PSScriptRoot**</span><span class="sxs-lookup"><span data-stu-id="99754-216">**PSScriptRoot**</span></span>  | <span data-ttu-id="99754-217">呼び出されたスクリプトへの完全なパスを格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-217">Contains the full path to the script that invoked</span></span>   |
|               | <span data-ttu-id="99754-218">現在のコマンド。</span><span class="sxs-lookup"><span data-stu-id="99754-218">the current command.</span></span> <span data-ttu-id="99754-219">このプロパティの値は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="99754-219">The value of this property is</span></span>  |
|               | <span data-ttu-id="99754-220">呼び出し元がスクリプトの場合にのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="99754-220">populated only when the caller is a script.</span></span>         |
| <span data-ttu-id="99754-221">**PSCommandPath**</span><span class="sxs-lookup"><span data-stu-id="99754-221">**PSCommandPath**</span></span> | <span data-ttu-id="99754-222">スクリプトの完全なパスとファイル名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="99754-222">Contains the full path and file name of the script</span></span>  |
|               | <span data-ttu-id="99754-223">現在のコマンドを呼び出した。</span><span class="sxs-lookup"><span data-stu-id="99754-223">that invoked the current command.</span></span> <span data-ttu-id="99754-224">このの値</span><span class="sxs-lookup"><span data-stu-id="99754-224">The value of this</span></span> |
|               | <span data-ttu-id="99754-225">プロパティは、呼び出し元がである場合にのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="99754-225">property is populated only when the caller is a</span></span>     |
|               | <span data-ttu-id="99754-226"> スクリプトを入手してください。</span><span class="sxs-lookup"><span data-stu-id="99754-226">script.</span></span>                                             |

<span data-ttu-id="99754-227">`$PSScriptRoot`および自動変数とは異なり `$PSCommandPath` 、自動変数の **psscriptroot** および **psscriptroot** プロパティには、現在のスクリプトでは `$MyInvocation` なく、呼び出し元または呼び出し元のスクリプトに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="99754-227">Unlike the `$PSScriptRoot` and `$PSCommandPath` automatic variables, the **PSScriptRoot** and **PSCommandPath** properties of the `$MyInvocation` automatic variable contain information about the invoker or calling script, not the current script.</span></span>

### <a name="nestedpromptlevel"></a><span data-ttu-id="99754-228">$NestedPromptLevel</span><span class="sxs-lookup"><span data-stu-id="99754-228">$NestedPromptLevel</span></span>

<span data-ttu-id="99754-229">現在のプロンプトレベルを格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-229">Contains the current prompt level.</span></span> <span data-ttu-id="99754-230">値が0の場合は、元のプロンプトレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="99754-230">A value of 0 indicates the original prompt level.</span></span> <span data-ttu-id="99754-231">この値は、入れ子になったレベルを入力するとインクリメントされ、終了時にはデクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="99754-231">The value is incremented when you enter a nested level and decremented when you exit it.</span></span>

<span data-ttu-id="99754-232">たとえば、PowerShell では、メソッドを使用すると、入れ子になったコマンドプロンプトが表示さ `$Host.EnterNestedPrompt` れます。</span><span class="sxs-lookup"><span data-stu-id="99754-232">For example, PowerShell presents a nested command prompt when you use the `$Host.EnterNestedPrompt` method.</span></span> <span data-ttu-id="99754-233">Powershell デバッガーでブレークポイントに到着すると、入れ子になったコマンドプロンプトも表示されます。</span><span class="sxs-lookup"><span data-stu-id="99754-233">PowerShell also presents a nested command prompt when you reach a breakpoint in the PowerShell debugger.</span></span>

<span data-ttu-id="99754-234">入れ子になったプロンプトを入力すると、PowerShell は現在のコマンドを一時停止し、実行コンテキストを保存して、変数の値をインクリメントし `$NestedPromptLevel` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-234">When you enter a nested prompt, PowerShell pauses the current command, saves the execution context, and increments the value of the `$NestedPromptLevel` variable.</span></span> <span data-ttu-id="99754-235">入れ子になったコマンドプロンプト (最大128レベル) を作成するか、元のコマンドプロンプトに戻るには、コマンドを実行するか、「」と入力 `exit` します。</span><span class="sxs-lookup"><span data-stu-id="99754-235">To create additional nested command prompts (up to 128 levels) or to return to the original command prompt, complete the command, or type `exit`.</span></span>

<span data-ttu-id="99754-236">変数は、 `$NestedPromptLevel` プロンプトレベルを追跡するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="99754-236">The `$NestedPromptLevel` variable helps you track the prompt level.</span></span> <span data-ttu-id="99754-237">この値を含む別の PowerShell コマンドプロンプトを作成して、常に表示されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="99754-237">You can create an alternative PowerShell command prompt that includes this value so that it's always visible.</span></span>

### <a name="null"></a><span data-ttu-id="99754-238">$null</span><span class="sxs-lookup"><span data-stu-id="99754-238">$null</span></span>

<span data-ttu-id="99754-239">`$null`**null** または空の値を含む自動変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="99754-239">`$null` is an automatic variable that contains a **null** or empty value.</span></span> <span data-ttu-id="99754-240">この変数を使用すると、コマンドやスクリプトに存在しない値または未定義の値を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="99754-240">You can use this variable to represent an absent or undefined value in commands and scripts.</span></span>

<span data-ttu-id="99754-241">PowerShell `$null` は、値を持つオブジェクト (つまり、明示的なプレースホルダー) としてを処理します。これにより、を使用して `$null` 一連の値で空の値を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="99754-241">PowerShell treats `$null` as an object with a value, that is, as an explicit placeholder, so you can use `$null` to represent an empty value in a series of values.</span></span>

<span data-ttu-id="99754-242">たとえば、 `$null` コレクションにが含まれている場合、オブジェクトの1つとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="99754-242">For example, when `$null` is included in a collection, it's counted as one of the objects.</span></span>

```powershell
$a = "one", $null, "three"
$a.count
```

```Output
3
```

<span data-ttu-id="99754-243">パイプを使用して変数をコマンドレットに渡した場合、 `$null` 他の `ForEach-Object` `$null` オブジェクトの場合と同様に、の値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="99754-243">If you pipe the `$null` variable to the `ForEach-Object` cmdlet, it generates a value for `$null`, just as it does for the other objects</span></span>

```powershell
"one", $null, "three" | ForEach-Object { "Hello " + $_}
```

```Output
Hello one
Hello
Hello three
```

<span data-ttu-id="99754-244">このため、を使用して `$null` **パラメーター値を指定** することはできません。</span><span class="sxs-lookup"><span data-stu-id="99754-244">As a result, you can't use `$null` to mean **no parameter value**.</span></span> <span data-ttu-id="99754-245">パラメーター値がの場合、 `$null` 既定のパラメーター値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="99754-245">A parameter value of `$null` overrides the default parameter value.</span></span>

<span data-ttu-id="99754-246">ただし、PowerShell では `$null` 変数がプレースホルダーとして扱われるため、次のようなスクリプトで使用できます。これは、が無視された場合には機能し `$null` ません。</span><span class="sxs-lookup"><span data-stu-id="99754-246">However, because PowerShell treats the `$null` variable as a placeholder, you can use it in scripts like the following one, which wouldn't work if `$null` were ignored.</span></span>

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

### <a name="pid"></a><span data-ttu-id="99754-247">$PID</span><span class="sxs-lookup"><span data-stu-id="99754-247">$PID</span></span>

<span data-ttu-id="99754-248">現在の PowerShell セッションをホストしているプロセスのプロセス識別子 (PID) を格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-248">Contains the process identifier (PID) of the process that is hosting the current PowerShell session.</span></span>

### <a name="profile"></a><span data-ttu-id="99754-249">$PROFILE</span><span class="sxs-lookup"><span data-stu-id="99754-249">$PROFILE</span></span>

<span data-ttu-id="99754-250">現在のユーザーと現在のホストアプリケーションの PowerShell プロファイルの完全パスを含みます。</span><span class="sxs-lookup"><span data-stu-id="99754-250">Contains the full path of the PowerShell profile for the current user and the current host application.</span></span> <span data-ttu-id="99754-251">この変数を使用すると、コマンドでプロファイルを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="99754-251">You can use this variable to represent the profile in commands.</span></span> <span data-ttu-id="99754-252">たとえば、コマンドで使用して、プロファイルが作成されているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="99754-252">For example, you can use it in a command to determine whether a profile has been created:</span></span>

```powershell
Test-Path $PROFILE
```

<span data-ttu-id="99754-253">または、コマンドで使用してプロファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="99754-253">Or, you can use it in a command to create a profile:</span></span>

```powershell
New-Item -ItemType file -Path $PROFILE -Force
```

<span data-ttu-id="99754-254">これをコマンドで使用すると、 **notepad.exe** でプロファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="99754-254">You can use it in a command to open the profile in **notepad.exe**:</span></span>

```powershell
notepad.exe $PROFILE
```

### <a name="psboundparameters"></a><span data-ttu-id="99754-255">$PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="99754-255">$PSBoundParameters</span></span>

<span data-ttu-id="99754-256">スクリプトまたは関数に渡されるパラメーターのディクショナリと、その現在の値を格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-256">Contains a dictionary of the parameters that are passed to a script or function and their current values.</span></span> <span data-ttu-id="99754-257">この変数の値は、スクリプトや関数など、パラメーターが宣言されているスコープ内にのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="99754-257">This variable has a value only in a scope where parameters are declared, such as a script or function.</span></span> <span data-ttu-id="99754-258">これを使用すると、パラメーターの現在の値を表示または変更したり、別のスクリプトまたは関数にパラメーター値を渡したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="99754-258">You can use it to display or change the current values of parameters or to pass parameter values to another script or function.</span></span>

<span data-ttu-id="99754-259">この例では、 **Test2** 関数はを `$PSBoundParameters` **Test1** 関数に渡します。</span><span class="sxs-lookup"><span data-stu-id="99754-259">In this example, the **Test2** function passes the `$PSBoundParameters` to the **Test1** function.</span></span> <span data-ttu-id="99754-260">は、 `$PSBoundParameters` **キー** と **値** の形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="99754-260">The `$PSBoundParameters` are displayed in the format of **Key** and **Value**.</span></span>

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

### <a name="pscmdlet"></a><span data-ttu-id="99754-261">$PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="99754-261">$PSCmdlet</span></span>

<span data-ttu-id="99754-262">実行されているコマンドレットまたは高度な関数を表すオブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-262">Contains an object that represents the cmdlet or advanced function that's being run.</span></span>

<span data-ttu-id="99754-263">コマンドレットまたは関数コードでオブジェクトのプロパティとメソッドを使用して、使用条件に応答できます。</span><span class="sxs-lookup"><span data-stu-id="99754-263">You can use the properties and methods of the object in your cmdlet or function code to respond to the conditions of use.</span></span> <span data-ttu-id="99754-264">たとえば、 **ParameterSetName** プロパティには、使用されているパラメーターセットの名前が含まれます **。このメソッドは** 、 **WhatIf** および **Confirm** パラメーターをコマンドレットに動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="99754-264">For example, the **ParameterSetName** property contains the name of the parameter set that's being used, and the **ShouldProcess** method adds the **WhatIf** and **Confirm** parameters to the cmdlet dynamically.</span></span>

<span data-ttu-id="99754-265">自動変数の詳細については `$PSCmdlet` 、「 [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) 」および「 [about_Functions_Advanced](about_Functions_Advanced.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99754-265">For more information about the `$PSCmdlet` automatic variable, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) and [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

### <a name="pscommandpath"></a><span data-ttu-id="99754-266">$PSCommandPath</span><span class="sxs-lookup"><span data-stu-id="99754-266">$PSCommandPath</span></span>

<span data-ttu-id="99754-267">実行されているスクリプトの完全なパスとファイル名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="99754-267">Contains the full path and file name of the script that's being run.</span></span> <span data-ttu-id="99754-268">この変数は、すべてのスクリプトで有効です。</span><span class="sxs-lookup"><span data-stu-id="99754-268">This variable is valid in all scripts.</span></span>

### <a name="psculture"></a><span data-ttu-id="99754-269">$PSCulture</span><span class="sxs-lookup"><span data-stu-id="99754-269">$PSCulture</span></span>

<span data-ttu-id="99754-270">PowerShell 7 以降では、は `$PSCulture` 現在の powershell 実行空間 (セッション) のカルチャを反映しています。</span><span class="sxs-lookup"><span data-stu-id="99754-270">Beginning in PowerShell 7, `$PSCulture` reflects the culture of the current PowerShell runspace (session).</span></span> <span data-ttu-id="99754-271">PowerShell 実行空間でカルチャが変更された場合、 `$PSCulture` その実行空間の値が更新されます。</span><span class="sxs-lookup"><span data-stu-id="99754-271">If the culture is changed in a PowerShell runspace, the `$PSCulture` value for that runspace is updated.</span></span>

<span data-ttu-id="99754-272">カルチャによって、数値、通貨、日付などの項目の表示形式が決定され、 **システムの CultureInfo** オブジェクトに格納されます。</span><span class="sxs-lookup"><span data-stu-id="99754-272">The culture determines the display format of items such as numbers, currency, and dates, and is stored in a **System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="99754-273">`Get-Culture`コンピューターのカルチャを表示するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="99754-273">Use `Get-Culture` to display the computer's culture.</span></span> <span data-ttu-id="99754-274">`$PSCulture`**Name** プロパティの値を格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-274">`$PSCulture` contains the **Name** property's value.</span></span>

### <a name="psdebugcontext"></a><span data-ttu-id="99754-275">$PSDebugContext</span><span class="sxs-lookup"><span data-stu-id="99754-275">$PSDebugContext</span></span>

<span data-ttu-id="99754-276">デバッグ中に、この変数にはデバッグ環境に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="99754-276">While debugging, this variable contains information about the debugging environment.</span></span> <span data-ttu-id="99754-277">それ以外の場合は、 **null** 値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="99754-277">Otherwise, it contains a **null** value.</span></span> <span data-ttu-id="99754-278">その結果、デバッガーにコントロールがあるかどうかを示すために使用できます。</span><span class="sxs-lookup"><span data-stu-id="99754-278">As a result, you can use it to indicate whether the debugger has control.</span></span> <span data-ttu-id="99754-279">値が設定されると、**ブレークポイント** と **InvocationInfo** プロパティを持つ **psdebugcontext** オブジェクトが格納されます。</span><span class="sxs-lookup"><span data-stu-id="99754-279">When populated, it contains a **PsDebugContext** object that has **Breakpoints** and **InvocationInfo** properties.</span></span> <span data-ttu-id="99754-280">**InvocationInfo** プロパティには、 **Location** プロパティなど、いくつかの便利なプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="99754-280">The **InvocationInfo** property has several useful properties, including the **Location** property.</span></span> <span data-ttu-id="99754-281">**Location** プロパティは、デバッグされているスクリプトのパスを示します。</span><span class="sxs-lookup"><span data-stu-id="99754-281">The **Location** property indicates the path of the script that is being debugged.</span></span>

### <a name="pshome"></a><span data-ttu-id="99754-282">$PSHOME</span><span class="sxs-lookup"><span data-stu-id="99754-282">$PSHOME</span></span>

<span data-ttu-id="99754-283">PowerShell のインストールディレクトリ (通常は Windows システム) の完全なパスが含まれ `$env:windir\System32\PowerShell\v1.0` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-283">Contains the full path of the installation directory for PowerShell, typically, `$env:windir\System32\PowerShell\v1.0` in Windows systems.</span></span> <span data-ttu-id="99754-284">この変数は、PowerShell ファイルのパスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="99754-284">You can use this variable in the paths of PowerShell files.</span></span> <span data-ttu-id="99754-285">たとえば、次のコマンドは、概念説明ヘルプトピックで word **変数** を検索します。</span><span class="sxs-lookup"><span data-stu-id="99754-285">For example, the following command searches the conceptual Help topics for the word **variable**:</span></span>

```powershell
Select-String -Pattern Variable -Path $pshome\*.txt
```

### <a name="psitem"></a><span data-ttu-id="99754-286">$PSItem</span><span class="sxs-lookup"><span data-stu-id="99754-286">$PSItem</span></span>

<span data-ttu-id="99754-287">`$_` と同じ。</span><span class="sxs-lookup"><span data-stu-id="99754-287">Same as `$_`.</span></span> <span data-ttu-id="99754-288">パイプラインオブジェクトの現在のオブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-288">Contains the current object in the pipeline object.</span></span> <span data-ttu-id="99754-289">この変数は、パイプライン内のすべてのオブジェクトまたは選択したオブジェクトに対してアクションを実行するコマンドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="99754-289">You can use this variable in commands that perform an action on every object or on selected objects in a pipeline.</span></span>

### <a name="psscriptroot"></a><span data-ttu-id="99754-290">$PSScriptRoot</span><span class="sxs-lookup"><span data-stu-id="99754-290">$PSScriptRoot</span></span>

<span data-ttu-id="99754-291">スクリプトの実行元のディレクトリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="99754-291">Contains the directory from which a script is being run.</span></span>

<span data-ttu-id="99754-292">PowerShell 2.0 では、この変数はスクリプトモジュール () でのみ有効です `.psm1` 。</span><span class="sxs-lookup"><span data-stu-id="99754-292">In PowerShell 2.0, this variable is valid only in script modules (`.psm1`).</span></span>
<span data-ttu-id="99754-293">PowerShell 3.0 以降、すべてのスクリプトで有効になります。</span><span class="sxs-lookup"><span data-stu-id="99754-293">Beginning in PowerShell 3.0, it's valid in all scripts.</span></span>

### <a name="pssenderinfo"></a><span data-ttu-id="99754-294">$PSSenderInfo</span><span class="sxs-lookup"><span data-stu-id="99754-294">$PSSenderInfo</span></span>

<span data-ttu-id="99754-295">PSSession を開始したユーザーに関する情報が含まれます。これには、元のコンピューターのユーザー id とタイムゾーンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="99754-295">Contains information about the user who started the PSSession, including the user identity and the time zone of the originating computer.</span></span> <span data-ttu-id="99754-296">この変数は、PSSessions でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="99754-296">This variable is available only in PSSessions.</span></span>

<span data-ttu-id="99754-297">変数には、 `$PSSenderInfo` ユーザーが構成できるプロパティ **applicationarguments** が含まれています。既定では、元のセッションからのみが含まれ `$PSVersionTable` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-297">The `$PSSenderInfo` variable includes a user-configurable property, **ApplicationArguments**, that by default, contains only the `$PSVersionTable` from the originating session.</span></span> <span data-ttu-id="99754-298">**Applicationarguments** プロパティにデータを追加するには、コマンドレットの **applicationarguments** パラメーターを使用し `New-PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-298">To add data to the **ApplicationArguments** property, use the **ApplicationArguments** parameter of the `New-PSSessionOption` cmdlet.</span></span>

### <a name="psuiculture"></a><span data-ttu-id="99754-299">$PSUICulture</span><span class="sxs-lookup"><span data-stu-id="99754-299">$PSUICulture</span></span>

<span data-ttu-id="99754-300">オペレーティングシステムで現在使用されているユーザーインターフェイス (UI) カルチャの名前を格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-300">Contains the name of the user interface (UI) culture that's currently in use in the operating system.</span></span> <span data-ttu-id="99754-301">UI カルチャは、どのテキスト文字列がメニューやメッセージなどのユーザー インターフェイス要素に使用されるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="99754-301">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span> <span data-ttu-id="99754-302">これは、システムの **System.Globalization.CultureInfo.CurrentUICulture.Name** プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="99754-302">This is the value of the **System.Globalization.CultureInfo.CurrentUICulture.Name** property of the system.</span></span> <span data-ttu-id="99754-303">システムの **システムのグローバリゼーション** オブジェクトを取得するには、コマンドレットを使用し `Get-UICulture` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-303">To get the **System.Globalization.CultureInfo** object for the system, use the `Get-UICulture` cmdlet.</span></span>

### <a name="psversiontable"></a><span data-ttu-id="99754-304">$PSVersionTable</span><span class="sxs-lookup"><span data-stu-id="99754-304">$PSVersionTable</span></span>

<span data-ttu-id="99754-305">現在のセッションで実行されている PowerShell のバージョンに関する詳細を表示する読み取り専用のハッシュテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="99754-305">Contains a read-only hash table that displays details about the version of PowerShell that is running in the current session.</span></span> <span data-ttu-id="99754-306">この表には、次の項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="99754-306">The table includes the following items:</span></span>

| <span data-ttu-id="99754-307">プロパティ</span><span class="sxs-lookup"><span data-stu-id="99754-307">Property</span></span>                  | <span data-ttu-id="99754-308">Description</span><span class="sxs-lookup"><span data-stu-id="99754-308">Description</span></span>                                   |
| ------------------------- | --------------------------------------------- |
| <span data-ttu-id="99754-309">**PSVersion**</span><span class="sxs-lookup"><span data-stu-id="99754-309">**PSVersion**</span></span>             | <span data-ttu-id="99754-310">PowerShell のバージョン番号</span><span class="sxs-lookup"><span data-stu-id="99754-310">The PowerShell version number</span></span>                 |
| <span data-ttu-id="99754-311">**PSEdition**</span><span class="sxs-lookup"><span data-stu-id="99754-311">**PSEdition**</span></span>             | <span data-ttu-id="99754-312">このプロパティの値は、</span><span class="sxs-lookup"><span data-stu-id="99754-312">This property has the value of 'Desktop' for</span></span>  |
|                           | <span data-ttu-id="99754-313">Powershell 4 以降、PowerShell</span><span class="sxs-lookup"><span data-stu-id="99754-313">PowerShell 4 and below as well as PowerShell</span></span>  |
|                           | <span data-ttu-id="99754-314">5.1 は、すべての機能を備えた Windows エディションに対応しています。</span><span class="sxs-lookup"><span data-stu-id="99754-314">5.1 on full-featured Windows editions.</span></span>        |
|                           | <span data-ttu-id="99754-315">このプロパティの値は、</span><span class="sxs-lookup"><span data-stu-id="99754-315">This property has the value of 'Core' for</span></span>     |
|                           | <span data-ttu-id="99754-316">Powershell と powershell 6 以降</span><span class="sxs-lookup"><span data-stu-id="99754-316">PowerShell 6 and above as well as PowerShell</span></span>  |
|                           | <span data-ttu-id="99754-317">フットプリントが縮小されたエディションでの PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="99754-317">PowerShell 5.1 on reduced-footprint editions</span></span>  |
|                           | <span data-ttu-id="99754-318">Windows Nano Server や Windows IoT と同様です。</span><span class="sxs-lookup"><span data-stu-id="99754-318">like Windows Nano Server or Windows IoT.</span></span>      |
| <span data-ttu-id="99754-319">**GitCommitId**</span><span class="sxs-lookup"><span data-stu-id="99754-319">**GitCommitId**</span></span>           | <span data-ttu-id="99754-320">ソースファイルのコミット Id (GitHub)</span><span class="sxs-lookup"><span data-stu-id="99754-320">The commit Id of the source files, in GitHub,</span></span> |
| <span data-ttu-id="99754-321">**OS**</span><span class="sxs-lookup"><span data-stu-id="99754-321">**OS**</span></span>                    | <span data-ttu-id="99754-322">オペレーティングシステムの説明</span><span class="sxs-lookup"><span data-stu-id="99754-322">Description of the operating system that</span></span>      |
|                           | <span data-ttu-id="99754-323">PowerShell はで実行されています。</span><span class="sxs-lookup"><span data-stu-id="99754-323">PowerShell is running on.</span></span>                     |
| <span data-ttu-id="99754-324">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="99754-324">**Platform**</span></span>              | <span data-ttu-id="99754-325">オペレーティングシステムが実行されているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="99754-325">Platform that the operating system is running</span></span> |
|                           | <span data-ttu-id="99754-326">。</span><span class="sxs-lookup"><span data-stu-id="99754-326">on.</span></span> <span data-ttu-id="99754-327">Linux と macOS の値は **Unix** です。</span><span class="sxs-lookup"><span data-stu-id="99754-327">The value on Linux and macOS is **Unix**.</span></span> |
|                           | <span data-ttu-id="99754-328">`$IsMacOs` と `$IsLinux` を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99754-328">See `$IsMacOs` and `$IsLinux`.</span></span>                |
| <span data-ttu-id="99754-329">**Ps互換バージョン**</span><span class="sxs-lookup"><span data-stu-id="99754-329">**PSCompatibleVersions**</span></span>  | <span data-ttu-id="99754-330">互換性のある PowerShell のバージョン</span><span class="sxs-lookup"><span data-stu-id="99754-330">Versions of PowerShell that are compatible</span></span>    |
|                           | <span data-ttu-id="99754-331">現在のバージョンで</span><span class="sxs-lookup"><span data-stu-id="99754-331">with the current version</span></span>                      |
| <span data-ttu-id="99754-332">**PSRemotingProtocolVersion**</span><span class="sxs-lookup"><span data-stu-id="99754-332">**PSRemotingProtocolVersion**</span></span> | <span data-ttu-id="99754-333">PowerShell リモートのバージョン</span><span class="sxs-lookup"><span data-stu-id="99754-333">The version of the PowerShell remote</span></span>      |
|                           | <span data-ttu-id="99754-334">管理プロトコル。</span><span class="sxs-lookup"><span data-stu-id="99754-334">management protocol.</span></span>                          |
| <span data-ttu-id="99754-335">**SerializationVersion**</span><span class="sxs-lookup"><span data-stu-id="99754-335">**SerializationVersion**</span></span>  | <span data-ttu-id="99754-336">シリアル化メソッドのバージョン</span><span class="sxs-lookup"><span data-stu-id="99754-336">The version of the serialization method</span></span>       |
| <span data-ttu-id="99754-337">**WSManStackVersion**</span><span class="sxs-lookup"><span data-stu-id="99754-337">**WSManStackVersion**</span></span>     | <span data-ttu-id="99754-338">WS-Management スタックのバージョン番号</span><span class="sxs-lookup"><span data-stu-id="99754-338">The version number of the WS-Management stack</span></span> |

### <a name="pwd"></a><span data-ttu-id="99754-339">$PWD</span><span class="sxs-lookup"><span data-stu-id="99754-339">$PWD</span></span>

<span data-ttu-id="99754-340">現在のディレクトリの完全パスを表す path オブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-340">Contains a path object that represents the full path of the current directory.</span></span>

### <a name="sender"></a><span data-ttu-id="99754-341">$Sender</span><span class="sxs-lookup"><span data-stu-id="99754-341">$Sender</span></span>

<span data-ttu-id="99754-342">このイベントを生成したオブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-342">Contains the object that generated this event.</span></span> <span data-ttu-id="99754-343">この変数は、イベント登録コマンドのアクションブロック内でのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="99754-343">This variable is populated only within the Action block of an event registration command.</span></span> <span data-ttu-id="99754-344">この変数の値は、を返す **PSEventArgs** オブジェクトの Sender プロパティにもあり `Get-Event` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-344">The value of this variable can also be found in the Sender property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="shellid"></a><span data-ttu-id="99754-345">$ShellId</span><span class="sxs-lookup"><span data-stu-id="99754-345">$ShellId</span></span>

<span data-ttu-id="99754-346">現在のシェルの識別子を格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-346">Contains the identifier of the current shell.</span></span>

### <a name="stacktrace"></a><span data-ttu-id="99754-347">$StackTrace</span><span class="sxs-lookup"><span data-stu-id="99754-347">$StackTrace</span></span>

<span data-ttu-id="99754-348">最新のエラーのスタックトレースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="99754-348">Contains a stack trace for the most recent error.</span></span>

### <a name="switch"></a><span data-ttu-id="99754-349">$switch</span><span class="sxs-lookup"><span data-stu-id="99754-349">$switch</span></span>

<span data-ttu-id="99754-350">ステートメントの結果の値ではない列挙子を格納し `Switch` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-350">Contains the enumerator not the resulting values of a `Switch` statement.</span></span> <span data-ttu-id="99754-351">変数は、 `$switch` ステートメントの実行中にのみ存在し、 `Switch` ステートメントの実行が完了すると削除され `switch` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-351">The `$switch` variable exists only while the `Switch` statement is running; it's deleted when the `switch` statement completes execution.</span></span> <span data-ttu-id="99754-352">詳細については、「 [about_Switch](about_Switch.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99754-352">For more information, see [about_Switch](about_Switch.md).</span></span>

<span data-ttu-id="99754-353">列挙子には、ループ値を取得したり、現在のループの反復を変更したりするために使用できるプロパティとメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="99754-353">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="99754-354">詳細については、「 [列挙子の使用](#using-enumerators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99754-354">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="this"></a><span data-ttu-id="99754-355">$this</span><span class="sxs-lookup"><span data-stu-id="99754-355">$this</span></span>

<span data-ttu-id="99754-356">スクリプトプロパティまたはスクリプトメソッドを定義するスクリプトブロックでは、 `$this` 変数は拡張されるオブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="99754-356">In a script block that defines a script property or script method, the `$this` variable refers to the object that is being extended.</span></span>

<span data-ttu-id="99754-357">カスタムクラスでは、変数はクラス `$this` オブジェクト自体を参照し、クラスで定義されているプロパティとメソッドにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="99754-357">In a custom class, the `$this` variable refers to the class object itself allowing access to properties and methods defined in the class.</span></span>

### <a name="true"></a><span data-ttu-id="99754-358">$true</span><span class="sxs-lookup"><span data-stu-id="99754-358">$true</span></span>

<span data-ttu-id="99754-359">**True** を格納します。</span><span class="sxs-lookup"><span data-stu-id="99754-359">Contains **True**.</span></span> <span data-ttu-id="99754-360">この変数を使用すると、コマンドとスクリプトで **True** を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="99754-360">You can use this variable to represent **True** in commands and scripts.</span></span>

## <a name="using-enumerators"></a><span data-ttu-id="99754-361">列挙子の使用</span><span class="sxs-lookup"><span data-stu-id="99754-361">Using Enumerators</span></span>

<span data-ttu-id="99754-362">`$input`、 `$foreach` 、およびの `$switch` 各変数は、含まれているコードブロックによって処理される値を反復処理するために使用されるすべての列挙子です。</span><span class="sxs-lookup"><span data-stu-id="99754-362">The `$input`, `$foreach`, and `$switch` variables are all enumerators used to iterate through the values processed by their containing code block.</span></span>

<span data-ttu-id="99754-363">列挙子には、反復処理やイテレーション値の取得に使用できるプロパティとメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="99754-363">An enumerator contains properties and methods you can use to advance or reset iteration, or retrieve iteration values.</span></span> <span data-ttu-id="99754-364">列挙子を直接操作することは、ベストプラクティスとは見なされません。</span><span class="sxs-lookup"><span data-stu-id="99754-364">Directly manipulating enumerators isn't considered best practice.</span></span>

- <span data-ttu-id="99754-365">ループ内では、フロー制御キーワード [break](about_Break.md) と [continue](about_Continue.md) を優先する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99754-365">Within loops, flow control keywords [break](about_Break.md) and [continue](about_Continue.md) should be preferred.</span></span>
- <span data-ttu-id="99754-366">パイプライン入力を受け入れる関数内では、 **Valuefrompipeline** 属性または **Valuefrompipelinebypropertyname** 属性でパラメーターを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="99754-366">Within functions that accept pipeline input, it's best practice to use Parameters with the **ValueFromPipeline** or **ValueFromPipelineByPropertyName** attributes.</span></span>

  <span data-ttu-id="99754-367">詳細については、「 [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99754-367">For more information, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="movenext"></a><span data-ttu-id="99754-368">MoveNext</span><span class="sxs-lookup"><span data-stu-id="99754-368">MoveNext</span></span>

<span data-ttu-id="99754-369">[MoveNext](/dotnet/api/system.collections.ienumerator.movenext)メソッドは、列挙子をコレクションの次の要素に進めます。</span><span class="sxs-lookup"><span data-stu-id="99754-369">The [MoveNext](/dotnet/api/system.collections.ienumerator.movenext) method advances the enumerator to the next element of the collection.</span></span> <span data-ttu-id="99754-370">列挙子が正常に拡張された場合、 **MoveNext** は **True** を返します。列挙子がコレクションの末尾を越えた場合は **False** を返します。</span><span class="sxs-lookup"><span data-stu-id="99754-370">**MoveNext** returns **True** if the enumerator was successfully advanced, **False** if the enumerator has passed the end of the collection.</span></span>

> [!NOTE]
> <span data-ttu-id="99754-371">返さ **れた戻り値は** 、出力ストリームに **送信され** ます。</span><span class="sxs-lookup"><span data-stu-id="99754-371">The **Boolean** value returned my **MoveNext** is sent to the output stream.</span></span>
> <span data-ttu-id="99754-372">出力を抑制するには、出力を typecasting する `[void]` か、 [Out-Null](xref:Microsoft.PowerShell.Core.Out-Null)にパイプします。</span><span class="sxs-lookup"><span data-stu-id="99754-372">You can suppress the output by typecasting it to `[void]` or piping it to [Out-Null](xref:Microsoft.PowerShell.Core.Out-Null).</span></span>
>
> ```powershell
> $input.MoveNext() | Out-Null
> ```
>
> ```powershell
> [void]$input.MoveNext()
> ```

### <a name="reset"></a><span data-ttu-id="99754-373">Reset</span><span class="sxs-lookup"><span data-stu-id="99754-373">Reset</span></span>

<span data-ttu-id="99754-374">[Reset](/dotnet/api/system.collections.ienumerator.reset)メソッドは、列挙子を初期位置、つまりコレクション内の最初の要素の **前** に設定します。</span><span class="sxs-lookup"><span data-stu-id="99754-374">The [Reset](/dotnet/api/system.collections.ienumerator.reset) method sets the enumerator to its initial position, which is **before** the first element in the collection.</span></span>

### <a name="current"></a><span data-ttu-id="99754-375">Current</span><span class="sxs-lookup"><span data-stu-id="99754-375">Current</span></span>

<span data-ttu-id="99754-376">[現在](/dotnet/api/system.collections.ienumerator.current)のプロパティは、列挙子の現在位置にある、コレクションまたはパイプライン内の要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="99754-376">The [Current](/dotnet/api/system.collections.ienumerator.current) property gets the element in the collection, or pipeline, at the current position of the enumerator.</span></span>

<span data-ttu-id="99754-377">**現在** のプロパティは、 **MoveNext** が呼び出されるまで、同じプロパティを返し続けます。</span><span class="sxs-lookup"><span data-stu-id="99754-377">The **Current** property continues to return the same property until **MoveNext** is called.</span></span>

## <a name="examples"></a><span data-ttu-id="99754-378">例</span><span class="sxs-lookup"><span data-stu-id="99754-378">Examples</span></span>

### <a name="example-1-using-the-input-variable"></a><span data-ttu-id="99754-379">例 1: $input 変数の使用</span><span class="sxs-lookup"><span data-stu-id="99754-379">Example 1: Using the $input variable</span></span>

<span data-ttu-id="99754-380">次の例では、変数にアクセスすると、 `$input` 次にプロセスブロックが実行されるまで変数がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="99754-380">In the following example, accessing the `$input` variable clears the variable until the next time the process block executes.</span></span> <span data-ttu-id="99754-381">**Reset** メソッドを使用すると、 `$input` 変数が現在のパイプライン値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="99754-381">Using the **Reset** method resets the `$input` variable to the current pipeline value.</span></span>

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

<span data-ttu-id="99754-382">プロセスブロックは、 `$input` アクセスしない場合でも変数を自動的に進めます。</span><span class="sxs-lookup"><span data-stu-id="99754-382">The process block automatically advances the `$input` variable even if you don't access it.</span></span>

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

### <a name="example-2-using-input-outside-the-process-block"></a><span data-ttu-id="99754-383">例 2: プロセスブロックの外部での $input の使用</span><span class="sxs-lookup"><span data-stu-id="99754-383">Example 2: Using $input outside the process block</span></span>

<span data-ttu-id="99754-384">プロセスブロックの外部では、 `$input` 変数は関数にパイプされたすべての値を表します。</span><span class="sxs-lookup"><span data-stu-id="99754-384">Outside of the process block the `$input` variable represents all the values piped into the function.</span></span>

- <span data-ttu-id="99754-385">変数にアクセスすると、 `$input` すべての値がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="99754-385">Accessing the `$input` variable clears all values.</span></span>
- <span data-ttu-id="99754-386">**Reset** メソッドは、コレクション全体をリセットします。</span><span class="sxs-lookup"><span data-stu-id="99754-386">The **Reset** method resets the entire collection.</span></span>
- <span data-ttu-id="99754-387">**現在** のプロパティは設定されません。</span><span class="sxs-lookup"><span data-stu-id="99754-387">The **Current** property is never populated.</span></span>
- <span data-ttu-id="99754-388">コレクションを高度にすることはできないため、 **MoveNext** メソッドは false を返します。</span><span class="sxs-lookup"><span data-stu-id="99754-388">The **MoveNext** method returns false because the collection can't be advanced.</span></span>
  - <span data-ttu-id="99754-389">**MoveNext** を呼び出すと、変数がクリアさ `$input` れます。</span><span class="sxs-lookup"><span data-stu-id="99754-389">Calling **MoveNext** clears out the `$input` variable.</span></span>

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

### <a name="example-3-using-the-inputcurrent-property"></a><span data-ttu-id="99754-390">例 3: $input の使用現在のプロパティ</span><span class="sxs-lookup"><span data-stu-id="99754-390">Example 3: Using the $input.Current property</span></span>

<span data-ttu-id="99754-391">**現在** のプロパティを使用して、 **Reset** メソッドを使用せずに、現在のパイプライン値に複数回アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="99754-391">By using the **Current** property, the current pipeline value can be accessed multiple times without using the **Reset** method.</span></span> <span data-ttu-id="99754-392">プロセスブロックは自動的に **MoveNext** メソッドを呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="99754-392">The process block doesn't automatically call the **MoveNext** method.</span></span>

<span data-ttu-id="99754-393">明示的に **MoveNext** を呼び出さない限り、**現在** のプロパティには値が設定されません。</span><span class="sxs-lookup"><span data-stu-id="99754-393">The **Current** property will never be populated unless you explicitly call **MoveNext**.</span></span> <span data-ttu-id="99754-394">**現在** のプロパティには、その値をクリアせずに、プロセスブロック内で複数回アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="99754-394">The **Current** property can be accessed multiple times inside the process block without clearing its value.</span></span>

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

### <a name="example-4-using-the-foreach-variable"></a><span data-ttu-id="99754-395">例 4: $foreach 変数の使用</span><span class="sxs-lookup"><span data-stu-id="99754-395">Example 4: Using the $foreach variable</span></span>

<span data-ttu-id="99754-396">変数とは異なり、 `$input` 変数は、 `$foreach` 直接アクセスされるときに常にコレクション内のすべての項目を表します。</span><span class="sxs-lookup"><span data-stu-id="99754-396">Unlike the `$input` variable, the `$foreach` variable always represents all items in the collection when accessed directly.</span></span> <span data-ttu-id="99754-397">**現在のプロパティを** 使用して現在のコレクション要素にアクセスし、 **Reset** メソッドと **MoveNext** メソッドを使用してその値を変更します。</span><span class="sxs-lookup"><span data-stu-id="99754-397">Use the **Current** property to access the current collection element, and the **Reset** and **MoveNext** methods to change its value.</span></span>

> [!NOTE]
> <span data-ttu-id="99754-398">ループの各反復処理で `foreach` は、 **MoveNext** メソッドが自動的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="99754-398">Each iteration of the `foreach` loop will automatically call the **MoveNext** method.</span></span>

<span data-ttu-id="99754-399">次のループは2回だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="99754-399">The following loop only executes twice.</span></span> <span data-ttu-id="99754-400">2番目の反復処理では、反復処理が完了する前にコレクションが3番目の要素に移動されます。</span><span class="sxs-lookup"><span data-stu-id="99754-400">In the second iteration, the collection is moved to the third element before the iteration is complete.</span></span> <span data-ttu-id="99754-401">2番目の反復処理の後、反復処理する値がなくなり、ループが終了します。</span><span class="sxs-lookup"><span data-stu-id="99754-401">After the second iteration, there are now no more values to iterate, and the loop terminates.</span></span>

<span data-ttu-id="99754-402">**MoveNext** プロパティは、コレクション () を反復処理するために選択された変数には影響しません `$Num` 。</span><span class="sxs-lookup"><span data-stu-id="99754-402">The **MoveNext** property doesn't affect the variable chosen to iterate through the collection (`$Num`).</span></span>

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

<span data-ttu-id="99754-403">**Reset** メソッドを使用すると、コレクション内の現在の要素がリセットされます。</span><span class="sxs-lookup"><span data-stu-id="99754-403">Using the **Reset** method resets the current element in the collection.</span></span> <span data-ttu-id="99754-404">次の例では、 **Reset** メソッドが呼び出されるため、最初の2つの要素を **2 回** ループします。</span><span class="sxs-lookup"><span data-stu-id="99754-404">The following example loops through the first two elements **twice** because the **Reset** method is called.</span></span> <span data-ttu-id="99754-405">最初の2つのループの後、 `if` ステートメントは失敗し、ループは3つのすべての要素を通常どおり反復処理します。</span><span class="sxs-lookup"><span data-stu-id="99754-405">After the first two loops, the `if` statement fails and the loop iterates through all three elements normally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99754-406">これにより、無限ループが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="99754-406">This could result in an infinite loop.</span></span>

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

### <a name="example-5-using-the-switch-variable"></a><span data-ttu-id="99754-407">例 5: $switch 変数を使用する</span><span class="sxs-lookup"><span data-stu-id="99754-407">Example 5: Using the $switch variable</span></span>

<span data-ttu-id="99754-408">変数には、 `$switch` 変数とまったく同じ規則があり `$foreach` ます。</span><span class="sxs-lookup"><span data-stu-id="99754-408">The `$switch` variable has the exact same rules as the `$foreach` variable.</span></span>
<span data-ttu-id="99754-409">次の例は、すべての列挙子の概念を示しています。</span><span class="sxs-lookup"><span data-stu-id="99754-409">The following example demonstrates all the enumerator concepts.</span></span>

> [!NOTE]
> <span data-ttu-id="99754-410">MoveNext メソッドの後にステートメントが存在しない場合でも、Note のよう **な大文字** と小文字の区別が実行されないことに注意して `break` ください。 </span><span class="sxs-lookup"><span data-stu-id="99754-410">Note how the **NotEvaluated** case is never executed, even though there's no `break` statement after the **MoveNext** method.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="99754-411">関連項目</span><span class="sxs-lookup"><span data-stu-id="99754-411">See also</span></span>

[<span data-ttu-id="99754-412">about_Functions</span><span class="sxs-lookup"><span data-stu-id="99754-412">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="99754-413">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="99754-413">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="99754-414">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="99754-414">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="99754-415">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="99754-415">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="99754-416">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="99754-416">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="99754-417">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="99754-417">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="99754-418">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="99754-418">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="99754-419">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="99754-419">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="99754-420">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="99754-420">about_Splatting</span></span>](about_Splatting.md)

[<span data-ttu-id="99754-421">about_Variables</span><span class="sxs-lookup"><span data-stu-id="99754-421">about_Variables</span></span>](about_Variables.md)

