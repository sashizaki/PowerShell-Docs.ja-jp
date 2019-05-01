---
ms.date: 08/14/2018
keywords: PowerShell, コマンドレット
title: PowerShell.exe コマンドラインのヘルプ
ms.assetid: 1ab7b93b-6785-42c6-a1c9-35ff686a958f
ms.openlocfilehash: 0a11ebb11d29adf5853c232b3aa10bc72f92bf0c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058515"
---
# <a name="powershellexe-command-line-help"></a><span data-ttu-id="3cb60-103">PowerShell.exe コマンドラインのヘルプ</span><span class="sxs-lookup"><span data-stu-id="3cb60-103">PowerShell.exe Command-Line Help</span></span>

<span data-ttu-id="3cb60-104">PowerShell.exe を使用して、Cmd.exe などの別のツールのコマンド ラインから PowerShell セッションを起動したり、PowerShell.exe を PowerShell コマンド ラインで使用して、新しいセッションを開始したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3cb60-104">You can use PowerShell.exe to start a PowerShell session from the command line of another tool, such as Cmd.exe, or use it at the PowerShell command line to start a new session.</span></span> <span data-ttu-id="3cb60-105">パラメーターを使用して、セッションをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="3cb60-105">Use the parameters to customize the session.</span></span>

## <a name="syntax"></a><span data-ttu-id="3cb60-106">構文</span><span class="sxs-lookup"><span data-stu-id="3cb60-106">Syntax</span></span>

```syntax
PowerShell[.exe]
       [-Command { - | <script-block> [-args <arg-array>]
                     | <string> [<CommandParameters>] } ]
       [-EncodedCommand <Base64EncodedCommand>]
       [-ExecutionPolicy <ExecutionPolicy>]
       [-File <FilePath> [<Args>]]
       [-InputFormat {Text | XML}]
       [-Mta]
       [-NoExit]
       [-NoLogo]
       [-NonInteractive]
       [-NoProfile]
       [-OutputFormat {Text | XML}]
       [-PSConsoleFile <FilePath> | -Version <PowerShell version>]
       [-Sta]
       [-WindowStyle <style>]

PowerShell[.exe] -Help | -? | /?
```

## <a name="parameters"></a><span data-ttu-id="3cb60-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3cb60-107">Parameters</span></span>

### <a name="-encodedcommand-base64encodedcommand"></a><span data-ttu-id="3cb60-108">-EncodedCommand <Base64EncodedCommand></span><span class="sxs-lookup"><span data-stu-id="3cb60-108">-EncodedCommand <Base64EncodedCommand></span></span>

<span data-ttu-id="3cb60-109">Base 64 エンコード文字列版のコマンドを許可します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-109">Accepts a base-64-encoded string version of a command.</span></span> <span data-ttu-id="3cb60-110">複雑な引用符や中かっこを必要とするコマンドを PowerShell に渡す場合にこのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-110">Use this parameter to submit commands to PowerShell that require complex quotation marks or curly braces.</span></span>

### <a name="-executionpolicy-executionpolicy"></a><span data-ttu-id="3cb60-111">-ExecutionPolicy <ExecutionPolicy></span><span class="sxs-lookup"><span data-stu-id="3cb60-111">-ExecutionPolicy <ExecutionPolicy></span></span>

<span data-ttu-id="3cb60-112">現在のセッションの既定の実行ポリシーを設定し、$env:PSExecutionPolicyPreference 環境変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-112">Sets the default execution policy for the current session and saves it in the $env:PSExecutionPolicyPreference environment variable.</span></span> <span data-ttu-id="3cb60-113">このパラメーターは、レジストリに設定された PowerShell 実行ポリシーを変更しません。</span><span class="sxs-lookup"><span data-stu-id="3cb60-113">This parameter doesn't change the PowerShell execution policy that is set in the registry.</span></span> <span data-ttu-id="3cb60-114">有効な値の一覧など、PowerShell 実行ポリシーについては、「[about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cb60-114">For information about PowerShell execution policies, including a list of valid values, see [about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>

### <a name="-file-filepath-parameters"></a><span data-ttu-id="3cb60-115">-File <FilePath> \[<Parameters>]</span><span class="sxs-lookup"><span data-stu-id="3cb60-115">-File <FilePath> \[<Parameters>]</span></span>

<span data-ttu-id="3cb60-116">スクリプトで作成される関数と変数を現在のセッションで使用できるように、指定したスクリプトをローカル スコープ ("ドット ソース形式") で実行します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-116">Runs the specified script in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="3cb60-117">スクリプト ファイルのパスと (存在する場合) パラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-117">Enter the script file path and any parameters.</span></span> <span data-ttu-id="3cb60-118">**File** は、コマンド内の最後のパラメーターにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cb60-118">**File** must be the last parameter in the command.</span></span> <span data-ttu-id="3cb60-119">**-File** パラメーターの後に入力されたすべての値は、スクリプト ファイルのパスとそのスクリプトに渡されるパラメーターとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="3cb60-119">All values typed after the **-File** parameter are interpreted as the script file path and parameters passed to that script.</span></span>

<span data-ttu-id="3cb60-120">スクリプトに渡されるパラメーターは、(現在のシェルによる解釈の後で) リテラル文字列として渡されます。</span><span class="sxs-lookup"><span data-stu-id="3cb60-120">Parameters passed to the script are passed as literal strings, after interpretation by the current shell.</span></span> <span data-ttu-id="3cb60-121">たとえば、cmd.exe で環境変数値を渡す場合は、cmd.exe 構文 `powershell.exe -File .\test.ps1 -TestParam %windir%` を使用します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-121">For example, if you are in cmd.exe and want to pass an environment variable value, you would use the cmd.exe syntax: `powershell.exe -File .\test.ps1 -TestParam %windir%`</span></span>

<span data-ttu-id="3cb60-122">対照的に、cmd.exe で `powershell.exe -File .\test.ps1 -TestParam $env:windir` を実行すると、スクリプトはリテラル文字列 `$env:windir` を受け取ります。これは、現在の cmd.exe シェルには特別な意味がないためです。</span><span class="sxs-lookup"><span data-stu-id="3cb60-122">In contrast, running `powershell.exe -File .\test.ps1 -TestParam $env:windir` in cmd.exe results in the script receiving the literal string `$env:windir` because it has no special meaning to the current cmd.exe shell.</span></span>
<span data-ttu-id="3cb60-123">`$env:windir` スタイルの環境変数参照は、PowerShell コードとして解釈されるため、`-Command` パラメーター内で "_使用できます_"。</span><span class="sxs-lookup"><span data-stu-id="3cb60-123">The `$env:windir` style of environment variable reference _can_ be used inside a `-Command` parameter, since there it will be interpreted as PowerShell code.</span></span>

### <a name="-inputformat-text--xml"></a><span data-ttu-id="3cb60-124">\-InputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="3cb60-124">\-InputFormat {Text | XML}</span></span>

<span data-ttu-id="3cb60-125">PowerShell に送信されるデータの形式を記述します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-125">Describes the format of data sent to PowerShell.</span></span> <span data-ttu-id="3cb60-126">使用できる値は、"Text" (テキスト文字列) と "XML" (シリアル化された CLIXML 形式) です。</span><span class="sxs-lookup"><span data-stu-id="3cb60-126">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-mta"></a><span data-ttu-id="3cb60-127">-Mta</span><span class="sxs-lookup"><span data-stu-id="3cb60-127">-Mta</span></span>

<span data-ttu-id="3cb60-128">マルチスレッド アパートメントを使用して、PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-128">Starts PowerShell using a multi-threaded apartment.</span></span> <span data-ttu-id="3cb60-129">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3cb60-129">This parameter is introduced in PowerShell 3.0.</span></span> <span data-ttu-id="3cb60-130">PowerShell 3.0 では、シングルスレッド アパートメント (STA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="3cb60-130">In PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span> <span data-ttu-id="3cb60-131">PowerShell 2.0 では、マルチスレッド アパートメント (MTA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="3cb60-131">In PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span>

### <a name="-noexit"></a><span data-ttu-id="3cb60-132">-NoExit</span><span class="sxs-lookup"><span data-stu-id="3cb60-132">-NoExit</span></span>

<span data-ttu-id="3cb60-133">スタートアップ コマンドを実行後、終了しません。</span><span class="sxs-lookup"><span data-stu-id="3cb60-133">Doesn't exit after running startup commands.</span></span>

### <a name="-nologo"></a><span data-ttu-id="3cb60-134">-NoLogo</span><span class="sxs-lookup"><span data-stu-id="3cb60-134">-NoLogo</span></span>

<span data-ttu-id="3cb60-135">スタートアップ時に著作権の見出しを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="3cb60-135">Hides the copyright banner at startup.</span></span>

### <a name="-noninteractive"></a><span data-ttu-id="3cb60-136">-NonInteractive</span><span class="sxs-lookup"><span data-stu-id="3cb60-136">-NonInteractive</span></span>

<span data-ttu-id="3cb60-137">ユーザーに対話的なプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="3cb60-137">Doesn't present an interactive prompt to the user.</span></span>

### <a name="-noprofile"></a><span data-ttu-id="3cb60-138">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="3cb60-138">-NoProfile</span></span>

<span data-ttu-id="3cb60-139">PowerShell プロファイルを読み込みません。</span><span class="sxs-lookup"><span data-stu-id="3cb60-139">Doesn't load the PowerShell profile.</span></span>

### <a name="-outputformat-text--xml"></a><span data-ttu-id="3cb60-140">-OutputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="3cb60-140">-OutputFormat {Text | XML}</span></span>

<span data-ttu-id="3cb60-141">PowerShell からの出力の形式を決定します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-141">Determines how output from PowerShell is formatted.</span></span> <span data-ttu-id="3cb60-142">使用できる値は、"Text" (テキスト文字列) と "XML" (シリアル化された CLIXML 形式) です。</span><span class="sxs-lookup"><span data-stu-id="3cb60-142">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-psconsolefile-filepath"></a><span data-ttu-id="3cb60-143">-PSConsoleFile <FilePath></span><span class="sxs-lookup"><span data-stu-id="3cb60-143">-PSConsoleFile <FilePath></span></span>

<span data-ttu-id="3cb60-144">指定された PowerShell コンソール ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="3cb60-144">Loads the specified PowerShell console file.</span></span> <span data-ttu-id="3cb60-145">コンソール ファイルの名前とパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-145">Enter the path and name of the console file.</span></span> <span data-ttu-id="3cb60-146">コンソール ファイルを作成するには、PowerShell で [`Export-Console`](/powershell/module/Microsoft.PowerShell.Core/Export-Console) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-146">To create a console file, use the [`Export-Console`](/powershell/module/Microsoft.PowerShell.Core/Export-Console) cmdlet in PowerShell.</span></span>

### <a name="-sta"></a><span data-ttu-id="3cb60-147">-Sta</span><span class="sxs-lookup"><span data-stu-id="3cb60-147">-Sta</span></span>

<span data-ttu-id="3cb60-148">シングルスレッド アパートメントを使用して、PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-148">Starts PowerShell using a single-threaded apartment.</span></span> <span data-ttu-id="3cb60-149">PowerShell 3.0 では、シングルスレッド アパートメント (STA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="3cb60-149">In PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span> <span data-ttu-id="3cb60-150">PowerShell 2.0 では、マルチスレッド アパートメント (MTA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="3cb60-150">In PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span>

### <a name="-version-powershell-version"></a><span data-ttu-id="3cb60-151">-Version <PowerShell Version></span><span class="sxs-lookup"><span data-stu-id="3cb60-151">-Version <PowerShell Version></span></span>

<span data-ttu-id="3cb60-152">指定したバージョンの PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-152">Starts the specified version of PowerShell.</span></span> <span data-ttu-id="3cb60-153">指定するバージョンがシステムにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cb60-153">The version that you specify must be installed on the system.</span></span> <span data-ttu-id="3cb60-154">PowerShell 3.0 がコンピューターにインストールされている場合、有効な値は "2.0" と "3.0" です。</span><span class="sxs-lookup"><span data-stu-id="3cb60-154">If PowerShell 3.0 is installed on the computer, valid values are "2.0" and "3.0".</span></span> <span data-ttu-id="3cb60-155">既定値は "3.0" です。</span><span class="sxs-lookup"><span data-stu-id="3cb60-155">The default value is "3.0".</span></span>

<span data-ttu-id="3cb60-156">PowerShell 3.0 がインストールされていない場合、有効な値は "2.0" のみです。</span><span class="sxs-lookup"><span data-stu-id="3cb60-156">If PowerShell 3.0 isn't installed, the only valid value is "2.0".</span></span> <span data-ttu-id="3cb60-157">他の値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="3cb60-157">Other values are ignored.</span></span>

<span data-ttu-id="3cb60-158">詳しくは、「[Windows PowerShell のインストール](../../setup/installing-windows-powershell.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3cb60-158">For more information, see [Installing Windows PowerShell](../../setup/installing-windows-powershell.md).</span></span>

### <a name="-windowstyle-window-style"></a><span data-ttu-id="3cb60-159">-WindowStyle <Window style></span><span class="sxs-lookup"><span data-stu-id="3cb60-159">-WindowStyle <Window style></span></span>

<span data-ttu-id="3cb60-160">セッションのウィンドウ スタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-160">Sets the window style for the session.</span></span> <span data-ttu-id="3cb60-161">使用できる値は、Normal、Minimized、Maximized、および Hidden です。</span><span class="sxs-lookup"><span data-stu-id="3cb60-161">Valid values are Normal, Minimized, Maximized, and Hidden.</span></span>

### <a name="-command"></a><span data-ttu-id="3cb60-162">-Command</span><span class="sxs-lookup"><span data-stu-id="3cb60-162">-Command</span></span>

<span data-ttu-id="3cb60-163">PowerShell のコマンド プロンプトに入力された場合と同様に、指定されたコマンド (任意のパラメーターを付与する) を実行します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-163">Executes the specified commands (with any parameters) as though they were typed at the PowerShell command prompt.</span></span>
<span data-ttu-id="3cb60-164">実行後は、**NoExit** パラメーターが指定されていない限り、PowerShell は終了します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-164">After execution, PowerShell exits unless the **NoExit** parameter is specified.</span></span>
<span data-ttu-id="3cb60-165">`-Command` の後にある任意のテキストは、単一のコマンド ラインとして PowerShell に送信されます。</span><span class="sxs-lookup"><span data-stu-id="3cb60-165">Any text after `-Command` is sent as a single command line to PowerShell.</span></span>
<span data-ttu-id="3cb60-166">これは、`-File` がスクリプトに送信されたパラメーターを処理する方法とは異なります。</span><span class="sxs-lookup"><span data-stu-id="3cb60-166">This is different from how `-File` handles parameters sent to a script.</span></span>

<span data-ttu-id="3cb60-167">`-Command` の値には、"-"、文字列、またはスクリプト ブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3cb60-167">The value of `-Command` can be "-", a string, or a script block.</span></span>
<span data-ttu-id="3cb60-168">コマンドの結果は、ライブ オブジェクトとしてではなく、逆シリアル化された XML オブジェクトとして親シェルに返されます。</span><span class="sxs-lookup"><span data-stu-id="3cb60-168">The results of the command are returned to the parent shell as deserialized XML objects, not live objects.</span></span>

<span data-ttu-id="3cb60-169">`-Command` の値が "-" の場合、コマンド テキストは標準入力から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="3cb60-169">If the value of `-Command` is "-", the command text is read from standard input.</span></span>

<span data-ttu-id="3cb60-170">`-Command` の値が文字列の場合、**Command** は指定する最後のパラメーターにする "_必要があります_"。コマンドの後に入力された文字は、コマンド引数として解釈されるためです。</span><span class="sxs-lookup"><span data-stu-id="3cb60-170">When the value of `-Command` is a string, **Command** _must_ be the last parameter specified because any characters typed after the command are interpreted as the command arguments.</span></span>

<span data-ttu-id="3cb60-171">**Command** パラメーターは、`-Command` に渡された値を ScriptBlock 型として認識できる場合にのみ、スクリプト ブロックを実行用に受け付けます。</span><span class="sxs-lookup"><span data-stu-id="3cb60-171">The **Command** parameter only accepts a script block for execution when it can recognize the value passed to `-Command` as a ScriptBlock type.</span></span>
<span data-ttu-id="3cb60-172">これが可能なのは、別の PowerShell ホストから PowerShell.exe を実行している場合 "_のみ_" です。</span><span class="sxs-lookup"><span data-stu-id="3cb60-172">This is _only_ possible when running PowerShell.exe from another PowerShell host.</span></span>
<span data-ttu-id="3cb60-173">ScriptBlock 型は、PowerShell.exe に渡される前に、既存の変数に含まれているか、式から返されるか、中かっこ `{}` で囲まれたリテラル スクリプト ブロックとして PowerShell ホストによって解析されることがあります。</span><span class="sxs-lookup"><span data-stu-id="3cb60-173">The ScriptBlock type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces `{}`, before being passed to PowerShell.exe.</span></span>

<span data-ttu-id="3cb60-174">cmd.exe では、スクリプト ブロック (または ScriptBlock 型) とは異なり、**Command** に渡される値は "_常に_" 文字列になります。</span><span class="sxs-lookup"><span data-stu-id="3cb60-174">In cmd.exe, there is no such thing as a script block (or ScriptBlock type), so the value passed to **Command** will _always_ be a string.</span></span>
<span data-ttu-id="3cb60-175">文字列の中にスクリプト ブロックを記述することはできますが、実行されるのではなく、通常の PowerShell プロンプトで入力した場合とまったく同じように動作し、スクリプト ブロックの内容が出力されます。</span><span class="sxs-lookup"><span data-stu-id="3cb60-175">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="3cb60-176">`-Command` に渡された文字列は PowerShell として実行されます。そのため、cmd.exe から実行する場合、スクリプト ブロックの中かっこがそもそも必要ないことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="3cb60-176">A string passed to `-Command` will still be executed as PowerShell, so the script block curly braces are often not required in the first place when running from cmd.exe.</span></span>
<span data-ttu-id="3cb60-177">文字列内で定義されているインライン スクリプト ブロックを実行するには、次の[呼び出し演算子](/powershell/module/microsoft.powershell.core/about/about_operators#call-operator-) `&` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cb60-177">To execute an inline script block defined inside a string, the [call operator](/powershell/module/microsoft.powershell.core/about/about_operators#call-operator-) `&` can be used:</span></span>

```console
"& {<command>}"
```

### <a name="-help---"></a><span data-ttu-id="3cb60-178">-Help、-?、/?</span><span class="sxs-lookup"><span data-stu-id="3cb60-178">-Help, -?, /?</span></span>

<span data-ttu-id="3cb60-179">Powershell.exe の構文を示します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-179">Shows the syntax of powershell.exe.</span></span> <span data-ttu-id="3cb60-180">PowerShell で PowerShell.exe のコマンドを入力している場合、コマンド パラメーターの前にスラッシュ (/) ではなくハイフン (-) を入力してください。</span><span class="sxs-lookup"><span data-stu-id="3cb60-180">If you are typing a PowerShell.exe command in PowerShell, prepend the command parameters with a hyphen (-), not a forward slash (/).</span></span> <span data-ttu-id="3cb60-181">Cmd.exe では、ハイフンとスラッシュのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cb60-181">You can use either a hyphen or forward slash in Cmd.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="3cb60-182">トラブルシューティング上の注意:PowerShell 2.0 では、一部のプログラムを Windows PowerShell コンソールで開始すると、LastExitCode 0xc0000142 で失敗します。</span><span class="sxs-lookup"><span data-stu-id="3cb60-182">Troubleshooting Note: In PowerShell 2.0, starting some programs in the Windows PowerShell console fails with a LastExitCode of 0xc0000142.</span></span>

## <a name="examples"></a><span data-ttu-id="3cb60-183">例</span><span class="sxs-lookup"><span data-stu-id="3cb60-183">EXAMPLES</span></span>

```powershell
# Create a new PowerShell session and load a saved console file
PowerShell -PSConsoleFile sqlsnapin.psc1

# Create a new PowerShell V2 session with text input, XML output, and no logo
PowerShell -Version 2.0 -NoLogo -InputFormat text -OutputFormat XML

# Execute a PowerShell Command in a session
PowerShell -Command "Get-EventLog -LogName security"

# Run a script block in a session
PowerShell -Command {Get-EventLog -LogName security}

# An alternate way to run a command in a new session
PowerShell -Command "& {Get-EventLog -LogName security}"

# To use the -EncodedCommand parameter:
$command = "dir 'c:\program files' "
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
powershell.exe -encodedCommand $encodedCommand
```
