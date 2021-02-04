---
description: コマンドラインインターフェイスの使用方法について説明 `pwsh` します。 コマンドラインパラメーターを表示し、構文について説明します。
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pwsh?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Pwsh
ms.openlocfilehash: 6f6e7ea66aa04eaeea2b9da7c07864180210131c
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "97693001"
---
# <a name="about-pwsh"></a><span data-ttu-id="19203-104">Pwsh の概要</span><span class="sxs-lookup"><span data-stu-id="19203-104">About pwsh</span></span>

## <a name="short-description"></a><span data-ttu-id="19203-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="19203-105">Short Description</span></span>
<span data-ttu-id="19203-106">コマンドラインインターフェイスの使用方法について説明 `pwsh` します。</span><span class="sxs-lookup"><span data-stu-id="19203-106">Explains how to use the `pwsh` command-line interface.</span></span> <span data-ttu-id="19203-107">コマンドラインパラメーターを表示し、構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="19203-107">Displays the command-line parameters and describes the syntax.</span></span>

## <a name="long-description"></a><span data-ttu-id="19203-108">長い説明</span><span class="sxs-lookup"><span data-stu-id="19203-108">Long Description</span></span>

## <a name="syntax"></a><span data-ttu-id="19203-109">構文</span><span class="sxs-lookup"><span data-stu-id="19203-109">Syntax</span></span>

```
pwsh[.exe]
   [[-File] <filePath> [args]]
   [-Command { - | <script-block> [-args <arg-array>]
                 | <string> [<CommandParameters>] } ]
   [-ConfigurationName <string>]
   [-CustomPipeName <string>]
   [-EncodedCommand <Base64EncodedCommand>]
   [-ExecutionPolicy <ExecutionPolicy>]
   [-InputFormat {Text | XML}]
   [-Interactive]
   [-Login]
   [-MTA]
   [-NoExit]
   [-NoLogo]
   [-NonInteractive]
   [-NoProfile]
   [-OutputFormat {Text | XML}]
   [-SettingsFile <SettingsFilePath>]
   [-SSHServerMode]
   [-STA]
   [-Version]
   [-WindowStyle <style>]
   [-WorkingDirectory <directoryPath>]

pwsh[.exe] -h | -Help | -? | /?
```

## <a name="parameters"></a><span data-ttu-id="19203-110">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19203-110">Parameters</span></span>

<span data-ttu-id="19203-111">すべてのパラメーターで大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="19203-111">All parameters are case-insensitive.</span></span>

### <a name="-file---f"></a><span data-ttu-id="19203-112">-File |-f</span><span class="sxs-lookup"><span data-stu-id="19203-112">-File | -f</span></span>

<span data-ttu-id="19203-113">の値がの `File` 場合 `-` 、コマンドテキストは標準入力から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="19203-113">If the value of `File` is `-`, the command text is read from standard input.</span></span>
<span data-ttu-id="19203-114">`pwsh -File -`リダイレクトされた標準入力なしで実行すると、通常のセッションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="19203-114">Running `pwsh -File -` without redirected standard input starts a regular session.</span></span> <span data-ttu-id="19203-115">これは、パラメーターをまったく指定しない場合と同じです `File` 。</span><span class="sxs-lookup"><span data-stu-id="19203-115">This is the same as not specifying the `File` parameter at all.</span></span>

<span data-ttu-id="19203-116">パラメーターが存在せず、値がコマンドラインに存在する場合は、これが既定のパラメーターになります。</span><span class="sxs-lookup"><span data-stu-id="19203-116">This is the default parameter if no parameters are present but values are present in the command line.</span></span> <span data-ttu-id="19203-117">指定されたスクリプトはローカルスコープ ("ドットソース") で実行されるため、スクリプトによって作成される関数と変数を現在のセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="19203-117">The specified script runs in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="19203-118">スクリプト ファイルのパスと (存在する場合) パラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="19203-118">Enter the script file path and any parameters.</span></span> <span data-ttu-id="19203-119">File パラメーター名の後に入力されたすべての文字は、スクリプトファイルのパスとその後に続くスクリプトパラメーターとして解釈されるため、ファイルはコマンドの最後のパラメーターである必要があります。</span><span class="sxs-lookup"><span data-stu-id="19203-119">File must be the last parameter in the command, because all characters typed after the File parameter name are interpreted as the script file path followed by the script parameters.</span></span>

<span data-ttu-id="19203-120">通常、スクリプトのスイッチ パラメーターは、含めるか省略するかのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="19203-120">Typically, the switch parameters of a script are either included or omitted.</span></span>
<span data-ttu-id="19203-121">たとえば、次のコマンドは、Get-Script.ps1 スクリプトファイルの All パラメーターを使用します。 `-File .\Get-Script.ps1 -All`</span><span class="sxs-lookup"><span data-stu-id="19203-121">For example, the following command uses the All parameter of the Get-Script.ps1 script file: `-File .\Get-Script.ps1 -All`</span></span>

<span data-ttu-id="19203-122">まれに、スイッチパラメーターに **ブール** 値を指定しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="19203-122">In rare cases, you might need to provide a **Boolean** value for a switch parameter.</span></span> <span data-ttu-id="19203-123">**File** パラメーターの値にスイッチパラメーターの **ブール** 値を指定するには、次のように、通常、コロンとブール値の直後に続くパラメーターを使用し `-File .\Get-Script.ps1 -All:$False` ます。</span><span class="sxs-lookup"><span data-stu-id="19203-123">To provide a **Boolean** value for a switch parameter in the value of the **File** parameter, Use the parameter normally followed immediately by a colon and the boolean value, such as the following: `-File .\Get-Script.ps1 -All:$False`.</span></span>

<span data-ttu-id="19203-124">スクリプトに渡されるパラメーターは、(現在のシェルによる解釈の後で) リテラル文字列として渡されます。</span><span class="sxs-lookup"><span data-stu-id="19203-124">Parameters passed to the script are passed as literal strings, after interpretation by the current shell.</span></span> <span data-ttu-id="19203-125">たとえば、で環境変数の値を渡す場合は、 `cmd.exe` 次の構文を使用し `cmd.exe` ます。 `pwsh -File .\test.ps1 -TestParam %windir%`</span><span class="sxs-lookup"><span data-stu-id="19203-125">For example, if you are in `cmd.exe` and want to pass an environment variable value, you would use the `cmd.exe` syntax: `pwsh -File .\test.ps1 -TestParam %windir%`</span></span>

<span data-ttu-id="19203-126">これに対し、でを実行すると、 `pwsh -File .\test.ps1 -TestParam $env:windir` `cmd.exe` 現在の `$env:windir` シェルに特別な意味を持たないため、スクリプトがリテラル文字列を受け取ることになり `cmd.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="19203-126">In contrast, running `pwsh -File .\test.ps1 -TestParam $env:windir` in `cmd.exe` results in the script receiving the literal string `$env:windir` because it has no special meaning to the current `cmd.exe` shell.</span></span> <span data-ttu-id="19203-127">`$env:windir`環境変数参照のスタイルは、PowerShell コードとして解釈されるため、**コマンド** パラメーター内で使用 _でき_ ます。</span><span class="sxs-lookup"><span data-stu-id="19203-127">The `$env:windir` style of environment variable reference _can_ be used inside a **Command** parameter, since there it is interpreted as PowerShell code.</span></span>

<span data-ttu-id="19203-128">同様に、 _バッチスクリプト_ から同じコマンドを実行する場合 `%~dp0` は、またはの代わりにを使用し `.\` `$PSScriptRoot` て、現在の実行ディレクトリを表し `pwsh -File %~dp0test.ps1 -TestParam %windir%` ます。</span><span class="sxs-lookup"><span data-stu-id="19203-128">Similarly, if you want to execute the same command from a _Batch script_, you would use `%~dp0` instead of `.\` or `$PSScriptRoot` to represent the current execution directory: `pwsh -File %~dp0test.ps1 -TestParam %windir%`.</span></span> <span data-ttu-id="19203-129">代わりにを使用すると `.\test.ps1` 、PowerShell はリテラルパスを見つけることができないため、エラーをスローします。 `.\test.ps1`</span><span class="sxs-lookup"><span data-stu-id="19203-129">If you instead used `.\test.ps1`, PowerShell would throw an error because it cannot find the literal path `.\test.ps1`</span></span>

<span data-ttu-id="19203-130">スクリプトファイルがコマンドで終了すると、 `exit` プロセスの終了コードは、コマンドで使用される数値引数に設定され `exit` ます。</span><span class="sxs-lookup"><span data-stu-id="19203-130">When the script file terminates with an `exit` command, the process exit code is set to the numeric argument used with the `exit` command.</span></span> <span data-ttu-id="19203-131">通常の終了では、終了コードは常に `0` です。</span><span class="sxs-lookup"><span data-stu-id="19203-131">With normal termination, the exit code is always `0`.</span></span>

<span data-ttu-id="19203-132">と同様に、 `-Command` スクリプトを終了するエラーが発生すると、終了コードはに設定され `1` ます。</span><span class="sxs-lookup"><span data-stu-id="19203-132">Similar to `-Command`, when a script-terminating error occurs, the exit code is set to `1`.</span></span> <span data-ttu-id="19203-133">ただし、とは異なり、 `-Command` <kbd>Ctrl</kbd>C を使用して実行が中断されると、 - <kbd></kbd>終了コードはに `0` なります。</span><span class="sxs-lookup"><span data-stu-id="19203-133">However, unlike with `-Command`, when the execution is interrupted with <kbd>Ctrl</kbd>-<kbd>C</kbd> the exit code is `0`.</span></span>

### <a name="-command---c"></a><span data-ttu-id="19203-134">-Command |-c</span><span class="sxs-lookup"><span data-stu-id="19203-134">-Command | -c</span></span>

<span data-ttu-id="19203-135">指定されたコマンド (および任意のパラメーター) を PowerShell コマンドプロンプトで入力した場合と同じように実行し `NoExit` ます。パラメーターが指定されていない場合は、を終了します。</span><span class="sxs-lookup"><span data-stu-id="19203-135">Executes the specified commands (and any parameters) as though they were typed at the PowerShell command prompt, and then exits, unless the `NoExit` parameter is specified.</span></span>

<span data-ttu-id="19203-136">**Command** の値には `-` 、、スクリプトブロック、または文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="19203-136">The value of **Command** can be `-`, a script block, or a string.</span></span> <span data-ttu-id="19203-137">**Command** の値がの場合 `-` 、コマンドテキストは標準入力から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="19203-137">If the value of **Command** is `-`, the command text is read from standard input.</span></span>

<span data-ttu-id="19203-138">**コマンド** パラメーターでは、**コマンド** に **ScriptBlock** 型として渡された値を認識できる場合に限り、スクリプトブロックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="19203-138">The **Command** parameter only accepts a script block for execution when it can recognize the value passed to **Command** as a **ScriptBlock** type.</span></span> <span data-ttu-id="19203-139">これは `pwsh` 、別の PowerShell ホストから実行する場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="19203-139">This is _only_ possible when running `pwsh` from another PowerShell host.</span></span> <span data-ttu-id="19203-140">**ScriptBlock** 型は、に渡される前に、既存の変数に格納されるか、式から返されるか、または PowerShell ホストによって、中かっこ () で囲まれたリテラルスクリプトブロックとして解析されることがあり `{}` `pwsh` ます。</span><span class="sxs-lookup"><span data-stu-id="19203-140">The **ScriptBlock** type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces (`{}`), before being passed to `pwsh`.</span></span>

```powershell
pwsh -Command {Get-WinEvent -LogName security}
```

<span data-ttu-id="19203-141">で `cmd.exe` は、スクリプトブロック (または **ScriptBlock** 型) のようなものは存在しないため、 **コマンド** に渡される値は _常に_ 文字列になります。</span><span class="sxs-lookup"><span data-stu-id="19203-141">In `cmd.exe`, there is no such thing as a script block (or **ScriptBlock** type), so the value passed to **Command** will _always_ be a string.</span></span> <span data-ttu-id="19203-142">文字列の中にスクリプト ブロックを記述することはできますが、実行されるのではなく、通常の PowerShell プロンプトで入力した場合とまったく同じように動作し、スクリプト ブロックの内容が出力されます。</span><span class="sxs-lookup"><span data-stu-id="19203-142">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="19203-143">**コマンド** に渡された文字列は PowerShell コードとして実行されます。そのため、からの実行時には、スクリプトブロックの中かっこを最初に記述する必要はありません `cmd.exe` 。</span><span class="sxs-lookup"><span data-stu-id="19203-143">A string passed to **Command** is still executed as PowerShell code, so the script block curly braces are often not required in the first place when running from `cmd.exe`.</span></span> <span data-ttu-id="19203-144">文字列内で定義されているインライン スクリプト ブロックを実行するには、次の[呼び出し演算子](about_operators.md#special-operators) `&` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="19203-144">To execute an inline script block defined inside a string, the [call operator](about_operators.md#special-operators) `&` can be used:</span></span>

```
pwsh -Command "& {Get-WinEvent -LogName security}"
```

<span data-ttu-id="19203-145">**Command** の値が文字列の場合、 **command** は pwsh の最後のパラメーターである必要があります。これは、後続のすべての引数が、実行するコマンドの一部として解釈されるためです。</span><span class="sxs-lookup"><span data-stu-id="19203-145">If the value of **Command** is a string, **Command** must be the last parameter for pwsh, because all arguments following it are interpreted as part of the command to execute.</span></span>

<span data-ttu-id="19203-146">既存の PowerShell セッション内から呼び出された場合、結果は、ライブオブジェクトではなく、逆シリアル化された XML オブジェクトとして親シェルに返されます。</span><span class="sxs-lookup"><span data-stu-id="19203-146">When called from within an existing PowerShell session, the results are returned to the parent shell as deserialized XML objects, not live objects.</span></span> <span data-ttu-id="19203-147">他のシェルの場合、結果は文字列として返されます。</span><span class="sxs-lookup"><span data-stu-id="19203-147">For other shells, the results are returned as strings.</span></span>

<span data-ttu-id="19203-148">**Command** の値がの場合 `-` 、コマンドテキストは標準入力から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="19203-148">If the value of **Command** is `-`, the command text is read from standard input.</span></span> <span data-ttu-id="19203-149">標準入力で **Command** パラメーターを使用する場合は、標準入力をリダイレクトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19203-149">You must redirect standard input when using the **Command** parameter with standard input.</span></span> <span data-ttu-id="19203-150">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="19203-150">For example:</span></span>

```powershell
@'
"in"

"hi" |
  % { "$_ there" }

"out"
'@ | powershell -NoProfile -Command -
```

<span data-ttu-id="19203-151">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="19203-151">This example produces the following output:</span></span>

```Output
in
hi there
out
```

<span data-ttu-id="19203-152">プロセス終了コードは、スクリプトブロック内の最後の (実行された) コマンドの状態によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="19203-152">The process exit code is determined by status of the last (executed) command within the script block.</span></span> <span data-ttu-id="19203-153">がの場合、 `0` `$?` または `$true` `1` `$?` がの場合 `$false` 、終了コードはです。</span><span class="sxs-lookup"><span data-stu-id="19203-153">The exit code is `0` when `$?` is `$true` or `1` when `$?` is `$false`.</span></span> <span data-ttu-id="19203-154">最後のコマンドが、または以外の終了コードを明示的に設定する外部プログラムまたは PowerShell スクリプトの場合 `0` `1` 、終了コードは `1` プロセス終了コード用にに変換されます。</span><span class="sxs-lookup"><span data-stu-id="19203-154">If the last command is an external program or a PowerShell script that explicitly sets an exit code other than `0` or `1`, that exit code is converted to `1` for process exit code.</span></span> <span data-ttu-id="19203-155">特定の終了コードを保持するに `exit $LASTEXITCODE` は、をコマンド文字列またはスクリプトブロックに追加します。</span><span class="sxs-lookup"><span data-stu-id="19203-155">To preserve the specific exit code, add `exit $LASTEXITCODE` to your command string or script block.</span></span>

<span data-ttu-id="19203-156">同様に、やなどのスクリプト終了 (実行空間終了) エラーが発生したとき、または `throw` `-ErrorAction Stop` <kbd>Ctrl C キーを押し</kbd>て実行が中断されたときに、値1が返され - <kbd></kbd>ます。</span><span class="sxs-lookup"><span data-stu-id="19203-156">Similarly, the value 1 is returned when a script-terminating (runspace-terminating) error, such as a `throw` or `-ErrorAction Stop`, occurs or when execution is interrupted with <kbd>Ctrl</kbd>-<kbd>C</kbd>.</span></span>

### <a name="-configurationname---config"></a><span data-ttu-id="19203-157">-ConfigurationName |-config</span><span class="sxs-lookup"><span data-stu-id="19203-157">-ConfigurationName | -config</span></span>

<span data-ttu-id="19203-158">PowerShell を実行する構成エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="19203-158">Specifies a configuration endpoint in which PowerShell is run.</span></span> <span data-ttu-id="19203-159">これには、ローカルコンピューターに登録されている任意のエンドポイントを指定できます。これには、既定の PowerShell リモート処理エンドポイントや、特定のユーザーロール機能を持つカスタムエンドポイントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="19203-159">This can be any endpoint registered on the local machine including the default PowerShell remoting endpoints or a custom endpoint having specific user role capabilities.</span></span>

<span data-ttu-id="19203-160">例: `pwsh -ConfigurationName AdminRoles`</span><span class="sxs-lookup"><span data-stu-id="19203-160">Example: `pwsh -ConfigurationName AdminRoles`</span></span>

### <a name="-custompipename"></a><span data-ttu-id="19203-161">-CustomPipeName</span><span class="sxs-lookup"><span data-stu-id="19203-161">-CustomPipeName</span></span>

<span data-ttu-id="19203-162">デバッグおよびその他のプロセス間通信に使用する追加の IPC サーバー (名前付きパイプ) に使用する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="19203-162">Specifies the name to use for an additional IPC server (named pipe) used for debugging and other cross-process communication.</span></span> <span data-ttu-id="19203-163">これにより、他の PowerShell インスタンスに接続するための予測可能なメカニズムが提供されます。</span><span class="sxs-lookup"><span data-stu-id="19203-163">This offers a predictable mechanism for connecting to other PowerShell instances.</span></span> <span data-ttu-id="19203-164">通常、では **Custompipename** パラメーターと共に使用され `Enter-PSHostProcess` ます。</span><span class="sxs-lookup"><span data-stu-id="19203-164">Typically used with the **CustomPipeName** parameter on `Enter-PSHostProcess`.</span></span>

<span data-ttu-id="19203-165">このパラメーターは、PowerShell 6.2 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="19203-165">This parameter was introduced in PowerShell 6.2.</span></span>

<span data-ttu-id="19203-166">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="19203-166">For example:</span></span>

```powershell
# PowerShell instance 1
pwsh -CustomPipeName mydebugpipe
# PowerShell instance 2
Enter-PSHostProcess -CustomPipeName mydebugpipe
```

### <a name="-encodedcommand---e---ec"></a><span data-ttu-id="19203-167">-EncodedCommand |-e |-ec</span><span class="sxs-lookup"><span data-stu-id="19203-167">-EncodedCommand | -e | -ec</span></span>

<span data-ttu-id="19203-168">Base64 でエンコードされた文字列バージョンのコマンドを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="19203-168">Accepts a Base64-encoded string version of a command.</span></span> <span data-ttu-id="19203-169">このパラメーターを使用して、入れ子になった複雑な引用符を必要とするコマンドを PowerShell に送信します。</span><span class="sxs-lookup"><span data-stu-id="19203-169">Use this parameter to submit commands to PowerShell that require complex, nested quoting.</span></span> <span data-ttu-id="19203-170">Base64 表現は、16LE でエンコードされた文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="19203-170">The Base64 representation must be a UTF-16LE encoded string.</span></span>

<span data-ttu-id="19203-171">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="19203-171">For example:</span></span>

```powershell
$command = 'dir "c:\program files" '
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
pwsh -encodedcommand $encodedCommand
```

### <a name="-executionpolicy---ex---ep"></a><span data-ttu-id="19203-172">-Set-executionpolicy |-ex |-ep</span><span class="sxs-lookup"><span data-stu-id="19203-172">-ExecutionPolicy | -ex | -ep</span></span>

<span data-ttu-id="19203-173">現在のセッションの既定の実行ポリシーを設定し、環境変数に保存し `$env:PSExecutionPolicyPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="19203-173">Sets the default execution policy for the current session and saves it in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="19203-174">このパラメーターでは、永続的に構成された実行ポリシーは変更されません。</span><span class="sxs-lookup"><span data-stu-id="19203-174">This parameter does not change the persistently configured execution policies.</span></span>

<span data-ttu-id="19203-175">このパラメーターは、Windows コンピューターにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="19203-175">This parameter only applies to Windows computers.</span></span> <span data-ttu-id="19203-176">`$env:PSExecutionPolicyPreference`環境変数は、Windows 以外のプラットフォームには存在しません。</span><span class="sxs-lookup"><span data-stu-id="19203-176">The `$env:PSExecutionPolicyPreference` environment variable does not exist on non-Windows platforms.</span></span>

### <a name="-inputformat---inp---if"></a><span data-ttu-id="19203-177">-InputFormat |-sct.inp |-if</span><span class="sxs-lookup"><span data-stu-id="19203-177">-InputFormat | -inp | -if</span></span>

<span data-ttu-id="19203-178">PowerShell に送信されるデータの形式を記述します。</span><span class="sxs-lookup"><span data-stu-id="19203-178">Describes the format of data sent to PowerShell.</span></span> <span data-ttu-id="19203-179">使用できる値は、"Text" (テキスト文字列) と "XML" (シリアル化された CLIXML 形式) です。</span><span class="sxs-lookup"><span data-stu-id="19203-179">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-interactive---i"></a><span data-ttu-id="19203-180">-Interactive |-i</span><span class="sxs-lookup"><span data-stu-id="19203-180">-Interactive | -i</span></span>

<span data-ttu-id="19203-181">対話型プロンプトをユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="19203-181">Present an interactive prompt to the user.</span></span> <span data-ttu-id="19203-182">非対話型パラメーターの逆。</span><span class="sxs-lookup"><span data-stu-id="19203-182">Inverse for NonInteractive parameter.</span></span>

### <a name="-login---l"></a><span data-ttu-id="19203-183">-Login |-l</span><span class="sxs-lookup"><span data-stu-id="19203-183">-Login | -l</span></span>

<span data-ttu-id="19203-184">Linux および macOS では、/bin/sh を使用して/etc/profile や ~/.profile. などのログインプロファイルを実行し、ログインシェルとして PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="19203-184">On Linux and macOS, starts PowerShell as a login shell, using /bin/sh to execute login profiles such as /etc/profile and ~/.profile.</span></span>
<span data-ttu-id="19203-185">Windows では、このスイッチは何も行いません。</span><span class="sxs-lookup"><span data-stu-id="19203-185">On Windows, this switch does nothing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19203-186">このパラメーターは、PowerShell をログインシェルとして起動するために最初に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19203-186">This parameter must come first to start PowerShell as a login shell.</span></span>
> <span data-ttu-id="19203-187">このパラメーターを別の位置に渡すことは無視されます。</span><span class="sxs-lookup"><span data-stu-id="19203-187">Passing this parameter in another position will be ignored.</span></span>

<span data-ttu-id="19203-188">`pwsh`UNIX のようなオペレーティングシステムでログインシェルとしてを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="19203-188">To set up `pwsh` as the login shell on UNIX-like operating systems:</span></span>

- <span data-ttu-id="19203-189">の完全な絶対パスがの下に表示されていることを確認します。 `pwsh``/etc/shells`</span><span class="sxs-lookup"><span data-stu-id="19203-189">Verify that the full absolute path to `pwsh` is listed under `/etc/shells`</span></span>
  - <span data-ttu-id="19203-190">このパスは、通常、 `/usr/bin/pwsh` Linux または `/usr/local/bin/pwsh` macOS では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="19203-190">This path is usually something like `/usr/bin/pwsh` on Linux or `/usr/local/bin/pwsh` on macOS</span></span>
  - <span data-ttu-id="19203-191">インストールの方法によっては、インストール時にこのエントリが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="19203-191">With some installation methods, this entry will be added automatically at installation time</span></span>
  - <span data-ttu-id="19203-192">`pwsh`がに存在しない場合は、エディターを使用して、 `/etc/shells` 最後の行にパスを追加し `pwsh` ます。</span><span class="sxs-lookup"><span data-stu-id="19203-192">If `pwsh` is not present in `/etc/shells`, use an editor to append the path to `pwsh` on the last line.</span></span> <span data-ttu-id="19203-193">このためには、管理者特権でを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19203-193">This requires elevated privileges to edit.</span></span>
- <span data-ttu-id="19203-194">[Chsh](https://linux.die.net/man/1/chsh)ユーティリティを使用して、現在のユーザーのシェルを次のように設定し `pwsh` ます。</span><span class="sxs-lookup"><span data-stu-id="19203-194">Use the [chsh](https://linux.die.net/man/1/chsh) utility to set your current user's shell to `pwsh`:</span></span>

  ```sh
  chsh -s /usr/bin/pwsh
  ```

> [!WARNING]
> <span data-ttu-id="19203-195">`pwsh`現在、ログインシェルとしての設定は、Windows Subsystem For Linux (WSL) ではサポートされていません。また、をログインシェルとして設定しようとすると、 `pwsh` wsl を対話的に開始できなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19203-195">Setting `pwsh` as the login shell is currently not supported on Windows Subsystem for Linux (WSL), and attempting to set `pwsh` as the login shell there may lead to being unable to start WSL interactively.</span></span>

### <a name="-mta"></a><span data-ttu-id="19203-196">-MTA</span><span class="sxs-lookup"><span data-stu-id="19203-196">-MTA</span></span>

<span data-ttu-id="19203-197">マルチスレッドアパートメントを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="19203-197">Start PowerShell using a multi-threaded apartment.</span></span> <span data-ttu-id="19203-198">このスイッチは Windows でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="19203-198">This switch is only available on Windows.</span></span>

### <a name="-noexit---noe"></a><span data-ttu-id="19203-199">-NoExit |-noe</span><span class="sxs-lookup"><span data-stu-id="19203-199">-NoExit | -noe</span></span>

<span data-ttu-id="19203-200">スタートアップ コマンドを実行後、終了しません。</span><span class="sxs-lookup"><span data-stu-id="19203-200">Does not exit after running startup commands.</span></span>

<span data-ttu-id="19203-201">例: `pwsh -NoExit -Command Get-Date`</span><span class="sxs-lookup"><span data-stu-id="19203-201">Example: `pwsh -NoExit -Command Get-Date`</span></span>

### <a name="-nologo---nol"></a><span data-ttu-id="19203-202">-NoLogo |-nol</span><span class="sxs-lookup"><span data-stu-id="19203-202">-NoLogo | -nol</span></span>

<span data-ttu-id="19203-203">対話型セッションの起動時に著作権情報のバナーを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="19203-203">Hides the copyright banner at startup of interactive sessions.</span></span>

### <a name="-noninteractive---noni"></a><span data-ttu-id="19203-204">-非対話型 |-非 i</span><span class="sxs-lookup"><span data-stu-id="19203-204">-NonInteractive | -noni</span></span>

<span data-ttu-id="19203-205">ユーザーに対話的なプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="19203-205">Does not present an interactive prompt to the user.</span></span> <span data-ttu-id="19203-206">またはの確認プロンプトなどの対話機能を使用しようとすると `Read-Host` 、ステートメントの終了エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="19203-206">Any attempts to use interactive features, like `Read-Host` or confirmation prompts, result in statement-terminating errors.</span></span>

### <a name="-noprofile---nop"></a><span data-ttu-id="19203-207">-NoProfile |-nop</span><span class="sxs-lookup"><span data-stu-id="19203-207">-NoProfile | -nop</span></span>

<span data-ttu-id="19203-208">では、PowerShell プロファイルは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="19203-208">Does not load the PowerShell profiles.</span></span>

### <a name="-outputformat---o---of"></a><span data-ttu-id="19203-209">-OutputFormat |-o |-/</span><span class="sxs-lookup"><span data-stu-id="19203-209">-OutputFormat | -o | -of</span></span>

<span data-ttu-id="19203-210">PowerShell からの出力の形式を決定します。</span><span class="sxs-lookup"><span data-stu-id="19203-210">Determines how output from PowerShell is formatted.</span></span> <span data-ttu-id="19203-211">使用できる値は、"Text" (テキスト文字列) と "XML" (シリアル化された CLIXML 形式) です。</span><span class="sxs-lookup"><span data-stu-id="19203-211">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

<span data-ttu-id="19203-212">例: `pwsh -o XML -c Get-Date`</span><span class="sxs-lookup"><span data-stu-id="19203-212">Example: `pwsh -o XML -c Get-Date`</span></span>

<span data-ttu-id="19203-213">でを PowerShell セッションとして呼び出すと、逆シリアル化されたオブジェクトが、プレーンテキストではなく出力として取得されます。</span><span class="sxs-lookup"><span data-stu-id="19203-213">When called withing a PowerShell session, you get deserialized objects as output rather plain strings.</span></span> <span data-ttu-id="19203-214">他のシェルから呼び出された場合、出力は EXPORT-CLIXML text として書式設定された文字列データになります。</span><span class="sxs-lookup"><span data-stu-id="19203-214">When called from other shells, the output is string data formatted as CLIXML text.</span></span>

### <a name="-settingsfile---settings"></a><span data-ttu-id="19203-215">-SettingsFile |-設定</span><span class="sxs-lookup"><span data-stu-id="19203-215">-SettingsFile | -settings</span></span>

<span data-ttu-id="19203-216">セッションのシステム全体の `powershell.config.json` 設定ファイルをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="19203-216">Overrides the system-wide `powershell.config.json` settings file for the session.</span></span> <span data-ttu-id="19203-217">既定では、ディレクトリのからシステム全体の設定が読み取られ `powershell.config.json` `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="19203-217">By default, system-wide settings are read from the `powershell.config.json` in the `$PSHOME` directory.</span></span>

<span data-ttu-id="19203-218">これらの設定は、引数で指定されたエンドポイントでは使用されないことに注意 `-ConfigurationName` してください。</span><span class="sxs-lookup"><span data-stu-id="19203-218">Note that these settings are not used by the endpoint specified by the `-ConfigurationName` argument.</span></span>

<span data-ttu-id="19203-219">例: `pwsh -SettingsFile c:\myproject\powershell.config.json`</span><span class="sxs-lookup"><span data-stu-id="19203-219">Example: `pwsh -SettingsFile c:\myproject\powershell.config.json`</span></span>

### <a name="-sshservermode---sshs"></a><span data-ttu-id="19203-220">-SSHServerMode |-sshs</span><span class="sxs-lookup"><span data-stu-id="19203-220">-SSHServerMode | -sshs</span></span>

<span data-ttu-id="19203-221">SSH サブシステムとして PowerShell を実行するために sshd_config で使用されます。</span><span class="sxs-lookup"><span data-stu-id="19203-221">Used in sshd_config for running PowerShell as an SSH subsystem.</span></span> <span data-ttu-id="19203-222">これは、他の用途のためのものでも、サポートもされていません。</span><span class="sxs-lookup"><span data-stu-id="19203-222">It is not intended or supported for any other use.</span></span>

### <a name="-sta"></a><span data-ttu-id="19203-223">-STA</span><span class="sxs-lookup"><span data-stu-id="19203-223">-STA</span></span>

<span data-ttu-id="19203-224">シングルスレッドアパートメントを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="19203-224">Start PowerShell using a single-threaded apartment.</span></span> <span data-ttu-id="19203-225">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="19203-225">This is the default.</span></span> <span data-ttu-id="19203-226">このスイッチは Windows でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="19203-226">This switch is only available on Windows.</span></span>

### <a name="-version---v"></a><span data-ttu-id="19203-227">-Version |-v</span><span class="sxs-lookup"><span data-stu-id="19203-227">-Version | -v</span></span>

<span data-ttu-id="19203-228">PowerShell のバージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="19203-228">Displays the version of PowerShell.</span></span> <span data-ttu-id="19203-229">追加のパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="19203-229">Additional parameters are ignored.</span></span>

### <a name="-windowstyle---w"></a><span data-ttu-id="19203-230">-System.windows.window.windowstyle |-w</span><span class="sxs-lookup"><span data-stu-id="19203-230">-WindowStyle | -w</span></span>

<span data-ttu-id="19203-231">セッションのウィンドウ スタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="19203-231">Sets the window style for the session.</span></span> <span data-ttu-id="19203-232">使用できる値は、Normal、Minimized、Maximized、Hidden です。</span><span class="sxs-lookup"><span data-stu-id="19203-232">Valid values are Normal, Minimized, Maximized and Hidden.</span></span>

### <a name="-workingdirectory---wd"></a><span data-ttu-id="19203-233">-WorkingDirectory |-wd</span><span class="sxs-lookup"><span data-stu-id="19203-233">-WorkingDirectory | -wd</span></span>

<span data-ttu-id="19203-234">起動時にを実行して初期作業ディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="19203-234">Sets the initial working directory by executing at startup.</span></span> <span data-ttu-id="19203-235">有効な PowerShell ファイルパスがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="19203-235">Any valid PowerShell file path is supported.</span></span>

<span data-ttu-id="19203-236">ホームディレクトリで PowerShell を開始するには、次のように使用します。 `pwsh -WorkingDirectory ~`</span><span class="sxs-lookup"><span data-stu-id="19203-236">To start PowerShell in your home directory, use: `pwsh -WorkingDirectory ~`</span></span>

### <a name="-help---"></a><span data-ttu-id="19203-237">-Help、-?、/?</span><span class="sxs-lookup"><span data-stu-id="19203-237">-Help, -?, /?</span></span>

<span data-ttu-id="19203-238">のヘルプを表示 `pwsh` します。</span><span class="sxs-lookup"><span data-stu-id="19203-238">Displays help for `pwsh`.</span></span> <span data-ttu-id="19203-239">PowerShell で pwsh コマンドを入力する場合は、コマンドパラメーターにスラッシュ () ではなくハイフン () を付加し `-` `/` ます。</span><span class="sxs-lookup"><span data-stu-id="19203-239">If you are typing a pwsh command in PowerShell, prepend the command parameters with a hyphen (`-`), not a forward slash (`/`).</span></span>
