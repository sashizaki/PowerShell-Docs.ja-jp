---
description: コマンドラインインターフェイスの使用方法について説明 `pwsh` します。 コマンドラインパラメーターを表示し、構文について説明します。
keywords: powershell,コマンドレット
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pwsh?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Pwsh
ms.openlocfilehash: 2aa1c4ec033b8e7294c269b53c4fe20205a47d7f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223080"
---
# <a name="about-pwsh"></a><span data-ttu-id="37fe8-105">Pwsh の概要</span><span class="sxs-lookup"><span data-stu-id="37fe8-105">About pwsh</span></span>

## <a name="short-description"></a><span data-ttu-id="37fe8-106">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="37fe8-106">Short Description</span></span>
<span data-ttu-id="37fe8-107">コマンドラインインターフェイスの使用方法について説明 `pwsh` します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-107">Explains how to use the `pwsh` command-line interface.</span></span> <span data-ttu-id="37fe8-108">コマンドラインパラメーターを表示し、構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-108">Displays the command-line parameters and describes the syntax.</span></span>

## <a name="long-description"></a><span data-ttu-id="37fe8-109">長い説明</span><span class="sxs-lookup"><span data-stu-id="37fe8-109">Long Description</span></span>

## <a name="syntax"></a><span data-ttu-id="37fe8-110">構文</span><span class="sxs-lookup"><span data-stu-id="37fe8-110">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="37fe8-111">パラメーター</span><span class="sxs-lookup"><span data-stu-id="37fe8-111">Parameters</span></span>

<span data-ttu-id="37fe8-112">すべてのパラメーターで大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-112">All parameters are case-insensitive.</span></span>

### <a name="-file---f"></a><span data-ttu-id="37fe8-113">-File |-f</span><span class="sxs-lookup"><span data-stu-id="37fe8-113">-File | -f</span></span>

<span data-ttu-id="37fe8-114">の値がの `File` 場合 `-` 、コマンドテキストは標準入力から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-114">If the value of `File` is `-`, the command text is read from standard input.</span></span>
<span data-ttu-id="37fe8-115">`pwsh -File -`リダイレクトされた標準入力なしで実行すると、通常のセッションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-115">Running `pwsh -File -` without redirected standard input starts a regular session.</span></span> <span data-ttu-id="37fe8-116">これは、パラメーターをまったく指定しない場合と同じです `File` 。</span><span class="sxs-lookup"><span data-stu-id="37fe8-116">This is the same as not specifying the `File` parameter at all.</span></span>

<span data-ttu-id="37fe8-117">パラメーターが存在せず、値がコマンドラインに存在する場合は、これが既定のパラメーターになります。</span><span class="sxs-lookup"><span data-stu-id="37fe8-117">This is the default parameter if no parameters are present but values are present in the command line.</span></span> <span data-ttu-id="37fe8-118">指定されたスクリプトはローカルスコープ ("ドットソース") で実行されるため、スクリプトによって作成される関数と変数を現在のセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-118">The specified script runs in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="37fe8-119">スクリプト ファイルのパスと (存在する場合) パラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-119">Enter the script file path and any parameters.</span></span> <span data-ttu-id="37fe8-120">File パラメーター名の後に入力されたすべての文字は、スクリプトファイルのパスとその後に続くスクリプトパラメーターとして解釈されるため、ファイルはコマンドの最後のパラメーターである必要があります。</span><span class="sxs-lookup"><span data-stu-id="37fe8-120">File must be the last parameter in the command, because all characters typed after the File parameter name are interpreted as the script file path followed by the script parameters.</span></span>

<span data-ttu-id="37fe8-121">通常、スクリプトのスイッチ パラメーターは、含めるか省略するかのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="37fe8-121">Typically, the switch parameters of a script are either included or omitted.</span></span>
<span data-ttu-id="37fe8-122">たとえば、次のコマンドは、Get-Script.ps1 スクリプトファイルの All パラメーターを使用します。 `-File .\Get-Script.ps1 -All`</span><span class="sxs-lookup"><span data-stu-id="37fe8-122">For example, the following command uses the All parameter of the Get-Script.ps1 script file: `-File .\Get-Script.ps1 -All`</span></span>

<span data-ttu-id="37fe8-123">まれに、スイッチパラメーターに **ブール** 値を指定しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="37fe8-123">In rare cases, you might need to provide a **Boolean** value for a switch parameter.</span></span> <span data-ttu-id="37fe8-124">**File** パラメーターの値にスイッチパラメーターの **ブール** 値を指定するには、次のように、通常、コロンとブール値の直後に続くパラメーターを使用し `-File .\Get-Script.ps1 -All:$False` ます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-124">To provide a **Boolean** value for a switch parameter in the value of the **File** parameter, Use the parameter normally followed immediately by a colon and the boolean value, such as the following: `-File .\Get-Script.ps1 -All:$False`.</span></span>

<span data-ttu-id="37fe8-125">スクリプトに渡されるパラメーターは、(現在のシェルによる解釈の後で) リテラル文字列として渡されます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-125">Parameters passed to the script are passed as literal strings, after interpretation by the current shell.</span></span> <span data-ttu-id="37fe8-126">たとえば、で環境変数の値を渡す場合は、 `cmd.exe` 次の構文を使用し `cmd.exe` ます。 `pwsh -File .\test.ps1 -TestParam %windir%`</span><span class="sxs-lookup"><span data-stu-id="37fe8-126">For example, if you are in `cmd.exe` and want to pass an environment variable value, you would use the `cmd.exe` syntax: `pwsh -File .\test.ps1 -TestParam %windir%`</span></span>

<span data-ttu-id="37fe8-127">これに対し、でを実行すると、 `pwsh -File .\test.ps1 -TestParam $env:windir` `cmd.exe` 現在の `$env:windir` シェルに特別な意味を持たないため、スクリプトがリテラル文字列を受け取ることになり `cmd.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-127">In contrast, running `pwsh -File .\test.ps1 -TestParam $env:windir` in `cmd.exe` results in the script receiving the literal string `$env:windir` because it has no special meaning to the current `cmd.exe` shell.</span></span> <span data-ttu-id="37fe8-128">`$env:windir`環境変数参照のスタイルは、PowerShell コードとして解釈されるため、 **コマンド** パラメーター内で使用 _でき_ ます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-128">The `$env:windir` style of environment variable reference _can_ be used inside a **Command** parameter, since there it is interpreted as PowerShell code.</span></span>

<span data-ttu-id="37fe8-129">同様に、 _バッチスクリプト_ から同じコマンドを実行する場合 `%~dp0` は、またはの代わりにを使用し `.\` `$PSScriptRoot` て、現在の実行ディレクトリを表し `pwsh -File %~dp0test.ps1 -TestParam %windir%` ます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-129">Similarly, if you want to execute the same command from a _Batch script_ , you would use `%~dp0` instead of `.\` or `$PSScriptRoot` to represent the current execution directory: `pwsh -File %~dp0test.ps1 -TestParam %windir%`.</span></span> <span data-ttu-id="37fe8-130">代わりにを使用すると `.\test.ps1` 、PowerShell はリテラルパスを見つけることができないため、エラーをスローします。 `.\test.ps1`</span><span class="sxs-lookup"><span data-stu-id="37fe8-130">If you instead used `.\test.ps1`, PowerShell would throw an error because it cannot find the literal path `.\test.ps1`</span></span>

<span data-ttu-id="37fe8-131">スクリプトファイルがコマンドで終了すると、 `exit` プロセスの終了コードは、コマンドで使用される数値引数に設定され `exit` ます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-131">When the script file terminates with an `exit` command, the process exit code is set to the numeric argument used with the `exit` command.</span></span> <span data-ttu-id="37fe8-132">通常の終了では、終了コードは常に `0` です。</span><span class="sxs-lookup"><span data-stu-id="37fe8-132">With normal termination, the exit code is always `0`.</span></span>

<span data-ttu-id="37fe8-133">と同様に、 `-Command` スクリプトを終了するエラーが発生すると、終了コードはに設定され `1` ます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-133">Similar to `-Command`, when a script-terminating error occurs, the exit code is set to `1`.</span></span> <span data-ttu-id="37fe8-134">ただし、とは異なり、 `-Command` <kbd>Ctrl</kbd>C を使用して実行が中断されると、 - <kbd>C</kbd>終了コードはに `0` なります。</span><span class="sxs-lookup"><span data-stu-id="37fe8-134">However, unlike with `-Command`, when the execution is interrupted with <kbd>Ctrl</kbd>-<kbd>C</kbd> the exit code is `0`.</span></span>

### <a name="-command---c"></a><span data-ttu-id="37fe8-135">-Command |-c</span><span class="sxs-lookup"><span data-stu-id="37fe8-135">-Command | -c</span></span>

<span data-ttu-id="37fe8-136">指定されたコマンド (および任意のパラメーター) を PowerShell コマンドプロンプトで入力した場合と同じように実行し `NoExit` ます。パラメーターが指定されていない場合は、を終了します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-136">Executes the specified commands (and any parameters) as though they were typed at the PowerShell command prompt, and then exits, unless the `NoExit` parameter is specified.</span></span>

<span data-ttu-id="37fe8-137">**Command** の値には `-` 、、スクリプトブロック、または文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-137">The value of **Command** can be `-`, a script block, or a string.</span></span> <span data-ttu-id="37fe8-138">**Command** の値がの場合 `-` 、コマンドテキストは標準入力から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-138">If the value of **Command** is `-`, the command text is read from standard input.</span></span>

<span data-ttu-id="37fe8-139">**コマンド** パラメーターでは、 **コマンド** に **ScriptBlock** 型として渡された値を認識できる場合に限り、スクリプトブロックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-139">The **Command** parameter only accepts a script block for execution when it can recognize the value passed to **Command** as a **ScriptBlock** type.</span></span> <span data-ttu-id="37fe8-140">これは _only_ `pwsh` 、別の PowerShell ホストから実行する場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="37fe8-140">This is _only_ possible when running `pwsh` from another PowerShell host.</span></span> <span data-ttu-id="37fe8-141">**ScriptBlock** 型は、に渡される前に、既存の変数に格納されるか、式から返されるか、または PowerShell ホストによって、中かっこ () で囲まれたリテラルスクリプトブロックとして解析されることがあり `{}` `pwsh` ます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-141">The **ScriptBlock** type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces (`{}`), before being passed to `pwsh`.</span></span>

```powershell
pwsh -Command {Get-WinEvent -LogName security}
```

<span data-ttu-id="37fe8-142">で `cmd.exe` は、スクリプトブロック (または **ScriptBlock** 型) のようなものは存在しないため、 **コマンド** に渡される値は _常に_ 文字列になります。</span><span class="sxs-lookup"><span data-stu-id="37fe8-142">In `cmd.exe`, there is no such thing as a script block (or **ScriptBlock** type), so the value passed to **Command** will _always_ be a string.</span></span> <span data-ttu-id="37fe8-143">文字列の中にスクリプト ブロックを記述することはできますが、実行されるのではなく、通常の PowerShell プロンプトで入力した場合とまったく同じように動作し、スクリプト ブロックの内容が出力されます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-143">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="37fe8-144">**コマンド** に渡された文字列は PowerShell コードとして実行されます。そのため、からの実行時には、スクリプトブロックの中かっこを最初に記述する必要はありません `cmd.exe` 。</span><span class="sxs-lookup"><span data-stu-id="37fe8-144">A string passed to **Command** is still executed as PowerShell code, so the script block curly braces are often not required in the first place when running from `cmd.exe`.</span></span> <span data-ttu-id="37fe8-145">文字列内で定義されているインライン スクリプト ブロックを実行するには、次の[呼び出し演算子](about_operators.md#special-operators) `&` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-145">To execute an inline script block defined inside a string, the [call operator](about_operators.md#special-operators) `&` can be used:</span></span>

```
pwsh -Command "& {Get-WinEvent -LogName security}"
```

<span data-ttu-id="37fe8-146">**Command** の値が文字列の場合、 **command** は pwsh の最後のパラメーターである必要があります。これは、後続のすべての引数が、実行するコマンドの一部として解釈されるためです。</span><span class="sxs-lookup"><span data-stu-id="37fe8-146">If the value of **Command** is a string, **Command** must be the last parameter for pwsh, because all arguments following it are interpreted as part of the command to execute.</span></span>

<span data-ttu-id="37fe8-147">既存の PowerShell セッション内から呼び出された場合、結果は、ライブオブジェクトではなく、逆シリアル化された XML オブジェクトとして親シェルに返されます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-147">When called from within an existing PowerShell session, the results are returned to the parent shell as deserialized XML objects, not live objects.</span></span> <span data-ttu-id="37fe8-148">他のシェルの場合、結果は文字列として返されます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-148">For other shells, the results are returned as strings.</span></span>

<span data-ttu-id="37fe8-149">**Command** の値がの場合 `-` 、コマンドテキストは標準入力から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-149">If the value of **Command** is `-`, the command text is read from standard input.</span></span> <span data-ttu-id="37fe8-150">標準入力で **Command** パラメーターを使用する場合は、標準入力をリダイレクトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="37fe8-150">You must redirect standard input when using the **Command** parameter with standard input.</span></span> <span data-ttu-id="37fe8-151">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-151">For example:</span></span>

```powershell
@'
"in"

"hi" |
  % { "$_ there" }

"out"
'@ | powershell -NoProfile -Command -
```

<span data-ttu-id="37fe8-152">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-152">This example produces the following output:</span></span>

```Output
in
hi there
out
```

<span data-ttu-id="37fe8-153">プロセス終了コードは、スクリプトブロック内の最後の (実行された) コマンドの状態によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-153">The process exit code is determined by status of the last (executed) command within the script block.</span></span> <span data-ttu-id="37fe8-154">がの場合、 `0` `$?` または `$true` `1` `$?` がの場合 `$false` 、終了コードはです。</span><span class="sxs-lookup"><span data-stu-id="37fe8-154">The exit code is `0` when `$?` is `$true` or `1` when `$?` is `$false`.</span></span> <span data-ttu-id="37fe8-155">最後のコマンドが、または以外の終了コードを明示的に設定する外部プログラムまたは PowerShell スクリプトの場合 `0` `1` 、終了コードは `1` プロセス終了コード用にに変換されます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-155">If the last command is an external program or a PowerShell script that explicitly sets an exit code other than `0` or `1`, that exit code is converted to `1` for process exit code.</span></span> <span data-ttu-id="37fe8-156">特定の終了コードを保持するに `exit $LASTEXITCODE` は、をコマンド文字列またはスクリプトブロックに追加します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-156">To preserve the specific exit code, add `exit $LASTEXITCODE` to your command string or script block.</span></span>

<span data-ttu-id="37fe8-157">同様に、やなどのスクリプト終了 (実行空間終了) エラーが発生したとき、または `throw` `-ErrorAction Stop` <kbd>Ctrl C キーを押し</kbd>て実行が中断されたときに、値1が返され - <kbd>C</kbd>ます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-157">Similarly, the value 1 is returned when a script-terminating (runspace-terminating) error, such as a `throw` or `-ErrorAction Stop`, occurs or when execution is interrupted with <kbd>Ctrl</kbd>-<kbd>C</kbd>.</span></span>

### <a name="-configurationname---config"></a><span data-ttu-id="37fe8-158">-ConfigurationName |-config</span><span class="sxs-lookup"><span data-stu-id="37fe8-158">-ConfigurationName | -config</span></span>

<span data-ttu-id="37fe8-159">PowerShell を実行する構成エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-159">Specifies a configuration endpoint in which PowerShell is run.</span></span> <span data-ttu-id="37fe8-160">これには、ローカルコンピューターに登録されている任意のエンドポイントを指定できます。これには、既定の PowerShell リモート処理エンドポイントや、特定のユーザーロール機能を持つカスタムエンドポイントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-160">This can be any endpoint registered on the local machine including the default PowerShell remoting endpoints or a custom endpoint having specific user role capabilities.</span></span>

<span data-ttu-id="37fe8-161">例: `pwsh -ConfigurationName AdminRoles`</span><span class="sxs-lookup"><span data-stu-id="37fe8-161">Example: `pwsh -ConfigurationName AdminRoles`</span></span>

### <a name="-custompipename"></a><span data-ttu-id="37fe8-162">-CustomPipeName</span><span class="sxs-lookup"><span data-stu-id="37fe8-162">-CustomPipeName</span></span>

<span data-ttu-id="37fe8-163">デバッグおよびその他のプロセス間通信に使用する追加の IPC サーバー (名前付きパイプ) に使用する名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-163">Specifies the name to use for an additional IPC server (named pipe) used for debugging and other cross-process communication.</span></span> <span data-ttu-id="37fe8-164">これにより、他の PowerShell インスタンスに接続するための予測可能なメカニズムが提供されます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-164">This offers a predictable mechanism for connecting to other PowerShell instances.</span></span> <span data-ttu-id="37fe8-165">通常、では **Custompipename** パラメーターと共に使用され `Enter-PSHostProcess` ます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-165">Typically used with the **CustomPipeName** parameter on `Enter-PSHostProcess`.</span></span>

<span data-ttu-id="37fe8-166">このパラメーターは、PowerShell 6.2 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="37fe8-166">This parameter was introduced in PowerShell 6.2.</span></span>

<span data-ttu-id="37fe8-167">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-167">For example:</span></span>

```powershell
# PowerShell instance 1
pwsh -CustomPipeName mydebugpipe
# PowerShell instance 2
Enter-PSHostProcess -CustomPipeName mydebugpipe
```

### <a name="-encodedcommand---e---ec"></a><span data-ttu-id="37fe8-168">-EncodedCommand |-e |-ec</span><span class="sxs-lookup"><span data-stu-id="37fe8-168">-EncodedCommand | -e | -ec</span></span>

<span data-ttu-id="37fe8-169">Base64 でエンコードされた文字列バージョンのコマンドを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-169">Accepts a Base64-encoded string version of a command.</span></span> <span data-ttu-id="37fe8-170">このパラメーターを使用して、入れ子になった複雑な引用符を必要とするコマンドを PowerShell に送信します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-170">Use this parameter to submit commands to PowerShell that require complex, nested quoting.</span></span> <span data-ttu-id="37fe8-171">Base64 表現は、UTF-16 でエンコードされた文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="37fe8-171">The Base64 representation must be a UTF-16 encoded string.</span></span>

<span data-ttu-id="37fe8-172">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-172">For example:</span></span>

```powershell
$command = 'dir "c:\program files" '
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
pwsh -encodedcommand $encodedCommand
```

### <a name="-executionpolicy---ex---ep"></a><span data-ttu-id="37fe8-173">-Set-executionpolicy |-ex |-ep</span><span class="sxs-lookup"><span data-stu-id="37fe8-173">-ExecutionPolicy | -ex | -ep</span></span>

<span data-ttu-id="37fe8-174">現在のセッションの既定の実行ポリシーを設定し、環境変数に保存し `$env:PSExecutionPolicyPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-174">Sets the default execution policy for the current session and saves it in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="37fe8-175">このパラメーターでは、永続的に構成された実行ポリシーは変更されません。</span><span class="sxs-lookup"><span data-stu-id="37fe8-175">This parameter does not change the persistently configured execution policies.</span></span>

<span data-ttu-id="37fe8-176">このパラメーターは、Windows コンピューターにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-176">This parameter only applies to Windows computers.</span></span> <span data-ttu-id="37fe8-177">`$env:PSExecutionPolicyPreference`環境変数は、Windows 以外のプラットフォームには存在しません。</span><span class="sxs-lookup"><span data-stu-id="37fe8-177">The `$env:PSExecutionPolicyPreference` environment variable does not exist on non-Windows platforms.</span></span>

### <a name="-inputformat---inp---if"></a><span data-ttu-id="37fe8-178">-InputFormat |-sct.inp |-if</span><span class="sxs-lookup"><span data-stu-id="37fe8-178">-InputFormat | -inp | -if</span></span>

<span data-ttu-id="37fe8-179">PowerShell に送信されるデータの形式を記述します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-179">Describes the format of data sent to PowerShell.</span></span> <span data-ttu-id="37fe8-180">使用できる値は、"Text" (テキスト文字列) と "XML" (シリアル化された CLIXML 形式) です。</span><span class="sxs-lookup"><span data-stu-id="37fe8-180">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-interactive---i"></a><span data-ttu-id="37fe8-181">-Interactive |-i</span><span class="sxs-lookup"><span data-stu-id="37fe8-181">-Interactive | -i</span></span>

<span data-ttu-id="37fe8-182">対話型プロンプトをユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-182">Present an interactive prompt to the user.</span></span> <span data-ttu-id="37fe8-183">非対話型パラメーターの逆。</span><span class="sxs-lookup"><span data-stu-id="37fe8-183">Inverse for NonInteractive parameter.</span></span>

### <a name="-login---l"></a><span data-ttu-id="37fe8-184">-Login |-l</span><span class="sxs-lookup"><span data-stu-id="37fe8-184">-Login | -l</span></span>

<span data-ttu-id="37fe8-185">Linux および macOS では、/bin/sh を使用して/etc/profile や ~/.profile. などのログインプロファイルを実行し、ログインシェルとして PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-185">On Linux and macOS, starts PowerShell as a login shell, using /bin/sh to execute login profiles such as /etc/profile and ~/.profile.</span></span>
<span data-ttu-id="37fe8-186">Windows では、このスイッチは何も行いません。</span><span class="sxs-lookup"><span data-stu-id="37fe8-186">On Windows, this switch does nothing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37fe8-187">このパラメーターは、PowerShell をログインシェルとして起動するために最初に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37fe8-187">This parameter must come first to start PowerShell as a login shell.</span></span>
> <span data-ttu-id="37fe8-188">このパラメーターを別の位置に渡すことは無視されます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-188">Passing this parameter in another position will be ignored.</span></span>

<span data-ttu-id="37fe8-189">`pwsh`UNIX のようなオペレーティングシステムでログインシェルとしてを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="37fe8-189">To set up `pwsh` as the login shell on UNIX-like operating systems:</span></span>

- <span data-ttu-id="37fe8-190">の完全な絶対パスがの下に表示されていることを確認します。 `pwsh``/etc/shells`</span><span class="sxs-lookup"><span data-stu-id="37fe8-190">Verify that the full absolute path to `pwsh` is listed under `/etc/shells`</span></span>
  - <span data-ttu-id="37fe8-191">このパスは、通常、 `/usr/bin/pwsh` Linux または `/usr/local/bin/pwsh` macOS では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="37fe8-191">This path is usually something like `/usr/bin/pwsh` on Linux or `/usr/local/bin/pwsh` on macOS</span></span>
  - <span data-ttu-id="37fe8-192">インストールの方法によっては、インストール時にこのエントリが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-192">With some installation methods, this entry will be added automatically at installation time</span></span>
  - <span data-ttu-id="37fe8-193">`pwsh`がに存在しない場合は、エディターを使用して、 `/etc/shells` 最後の行にパスを追加し `pwsh` ます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-193">If `pwsh` is not present in `/etc/shells`, use an editor to append the path to `pwsh` on the last line.</span></span> <span data-ttu-id="37fe8-194">このためには、管理者特権でを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37fe8-194">This requires elevated privileges to edit.</span></span>
- <span data-ttu-id="37fe8-195">[Chsh](https://linux.die.net/man/1/chsh)ユーティリティを使用して、現在のユーザーのシェルを次のように設定し `pwsh` ます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-195">Use the [chsh](https://linux.die.net/man/1/chsh) utility to set your current user's shell to `pwsh`:</span></span>

  ```sh
  chsh -s /usr/bin/pwsh
  ```

> [!WARNING]
> <span data-ttu-id="37fe8-196">`pwsh`現在、ログインシェルとしての設定は、Windows Subsystem For Linux (WSL) ではサポートされていません。また、をログインシェルとして設定しようとすると、 `pwsh` wsl を対話的に開始できなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="37fe8-196">Setting `pwsh` as the login shell is currently not supported on Windows Subsystem for Linux (WSL), and attempting to set `pwsh` as the login shell there may lead to being unable to start WSL interactively.</span></span>

### <a name="-mta"></a><span data-ttu-id="37fe8-197">-MTA</span><span class="sxs-lookup"><span data-stu-id="37fe8-197">-MTA</span></span>

<span data-ttu-id="37fe8-198">マルチスレッドアパートメントを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-198">Start PowerShell using a multi-threaded apartment.</span></span> <span data-ttu-id="37fe8-199">このスイッチは Windows でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-199">This switch is only available on Windows.</span></span>

### <a name="-noexit---noe"></a><span data-ttu-id="37fe8-200">-NoExit |-noe</span><span class="sxs-lookup"><span data-stu-id="37fe8-200">-NoExit | -noe</span></span>

<span data-ttu-id="37fe8-201">スタートアップ コマンドを実行後、終了しません。</span><span class="sxs-lookup"><span data-stu-id="37fe8-201">Does not exit after running startup commands.</span></span>

<span data-ttu-id="37fe8-202">例: `pwsh -NoExit -Command Get-Date`</span><span class="sxs-lookup"><span data-stu-id="37fe8-202">Example: `pwsh -NoExit -Command Get-Date`</span></span>

### <a name="-nologo---nol"></a><span data-ttu-id="37fe8-203">-NoLogo |-nol</span><span class="sxs-lookup"><span data-stu-id="37fe8-203">-NoLogo | -nol</span></span>

<span data-ttu-id="37fe8-204">対話型セッションの起動時に著作権情報のバナーを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="37fe8-204">Hides the copyright banner at startup of interactive sessions.</span></span>

### <a name="-noninteractive---noni"></a><span data-ttu-id="37fe8-205">-非対話型 |-非 i</span><span class="sxs-lookup"><span data-stu-id="37fe8-205">-NonInteractive | -noni</span></span>

<span data-ttu-id="37fe8-206">ユーザーに対話的なプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="37fe8-206">Does not present an interactive prompt to the user.</span></span> <span data-ttu-id="37fe8-207">またはの確認プロンプトなどの対話機能を使用しようとすると `Read-Host` 、ステートメントの終了エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-207">Any attempts to use interactive features, like `Read-Host` or confirmation prompts, result in statement-terminating errors.</span></span>

### <a name="-noprofile---nop"></a><span data-ttu-id="37fe8-208">-NoProfile |-nop</span><span class="sxs-lookup"><span data-stu-id="37fe8-208">-NoProfile | -nop</span></span>

<span data-ttu-id="37fe8-209">では、PowerShell プロファイルは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="37fe8-209">Does not load the PowerShell profiles.</span></span>

### <a name="-outputformat---o---of"></a><span data-ttu-id="37fe8-210">-OutputFormat |-o |-/</span><span class="sxs-lookup"><span data-stu-id="37fe8-210">-OutputFormat | -o | -of</span></span>

<span data-ttu-id="37fe8-211">PowerShell からの出力の形式を決定します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-211">Determines how output from PowerShell is formatted.</span></span> <span data-ttu-id="37fe8-212">使用できる値は、"Text" (テキスト文字列) と "XML" (シリアル化された CLIXML 形式) です。</span><span class="sxs-lookup"><span data-stu-id="37fe8-212">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

<span data-ttu-id="37fe8-213">例: `pwsh -o XML -c Get-Date`</span><span class="sxs-lookup"><span data-stu-id="37fe8-213">Example: `pwsh -o XML -c Get-Date`</span></span>

<span data-ttu-id="37fe8-214">でを PowerShell セッションとして呼び出すと、逆シリアル化されたオブジェクトが、プレーンテキストではなく出力として取得されます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-214">When called withing a PowerShell session, you get deserialized objects as output rather plain strings.</span></span> <span data-ttu-id="37fe8-215">他のシェルから呼び出された場合、出力は EXPORT-CLIXML text として書式設定された文字列データになります。</span><span class="sxs-lookup"><span data-stu-id="37fe8-215">When called from other shells, the output is string data formatted as CLIXML text.</span></span>

### <a name="-settingsfile---settings"></a><span data-ttu-id="37fe8-216">-SettingsFile |-設定</span><span class="sxs-lookup"><span data-stu-id="37fe8-216">-SettingsFile | -settings</span></span>

<span data-ttu-id="37fe8-217">セッションのシステム全体の `powershell.config.json` 設定ファイルをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="37fe8-217">Overrides the system-wide `powershell.config.json` settings file for the session.</span></span> <span data-ttu-id="37fe8-218">既定では、ディレクトリのからシステム全体の設定が読み取られ `powershell.config.json` `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-218">By default, system-wide settings are read from the `powershell.config.json` in the `$PSHOME` directory.</span></span>

<span data-ttu-id="37fe8-219">これらの設定は、引数で指定されたエンドポイントでは使用されないことに注意 `-ConfigurationName` してください。</span><span class="sxs-lookup"><span data-stu-id="37fe8-219">Note that these settings are not used by the endpoint specified by the `-ConfigurationName` argument.</span></span>

<span data-ttu-id="37fe8-220">例: `pwsh -SettingsFile c:\myproject\powershell.config.json`</span><span class="sxs-lookup"><span data-stu-id="37fe8-220">Example: `pwsh -SettingsFile c:\myproject\powershell.config.json`</span></span>

### <a name="-sshservermode---sshs"></a><span data-ttu-id="37fe8-221">-SSHServerMode |-sshs</span><span class="sxs-lookup"><span data-stu-id="37fe8-221">-SSHServerMode | -sshs</span></span>

<span data-ttu-id="37fe8-222">SSH サブシステムとして PowerShell を実行するために sshd_config で使用されます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-222">Used in sshd_config for running PowerShell as an SSH subsystem.</span></span> <span data-ttu-id="37fe8-223">これは、他の用途のためのものでも、サポートもされていません。</span><span class="sxs-lookup"><span data-stu-id="37fe8-223">It is not intended or supported for any other use.</span></span>

### <a name="-sta"></a><span data-ttu-id="37fe8-224">-STA</span><span class="sxs-lookup"><span data-stu-id="37fe8-224">-STA</span></span>

<span data-ttu-id="37fe8-225">シングルスレッドアパートメントを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-225">Start PowerShell using a single-threaded apartment.</span></span> <span data-ttu-id="37fe8-226">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="37fe8-226">This is the default.</span></span> <span data-ttu-id="37fe8-227">このスイッチは Windows でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-227">This switch is only available on Windows.</span></span>

### <a name="-version---v"></a><span data-ttu-id="37fe8-228">-Version |-v</span><span class="sxs-lookup"><span data-stu-id="37fe8-228">-Version | -v</span></span>

<span data-ttu-id="37fe8-229">PowerShell のバージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-229">Displays the version of PowerShell.</span></span> <span data-ttu-id="37fe8-230">追加のパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-230">Additional parameters are ignored.</span></span>

### <a name="-windowstyle---w"></a><span data-ttu-id="37fe8-231">-System.windows.window.windowstyle |-w</span><span class="sxs-lookup"><span data-stu-id="37fe8-231">-WindowStyle | -w</span></span>

<span data-ttu-id="37fe8-232">セッションのウィンドウ スタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-232">Sets the window style for the session.</span></span> <span data-ttu-id="37fe8-233">使用できる値は、Normal、Minimized、Maximized、Hidden です。</span><span class="sxs-lookup"><span data-stu-id="37fe8-233">Valid values are Normal, Minimized, Maximized and Hidden.</span></span>

### <a name="-workingdirectory---wd"></a><span data-ttu-id="37fe8-234">-WorkingDirectory |-wd</span><span class="sxs-lookup"><span data-stu-id="37fe8-234">-WorkingDirectory | -wd</span></span>

<span data-ttu-id="37fe8-235">起動時にを実行して初期作業ディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-235">Sets the initial working directory by executing at startup.</span></span> <span data-ttu-id="37fe8-236">有効な PowerShell ファイルパスがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="37fe8-236">Any valid PowerShell file path is supported.</span></span>

<span data-ttu-id="37fe8-237">ホームディレクトリで PowerShell を開始するには、次のように使用します。 `pwsh -WorkingDirectory ~`</span><span class="sxs-lookup"><span data-stu-id="37fe8-237">To start PowerShell in your home directory, use: `pwsh -WorkingDirectory ~`</span></span>

### <a name="-help---"></a><span data-ttu-id="37fe8-238">-Help、-?、/?</span><span class="sxs-lookup"><span data-stu-id="37fe8-238">-Help, -?, /?</span></span>

<span data-ttu-id="37fe8-239">のヘルプを表示 `pwsh` します。</span><span class="sxs-lookup"><span data-stu-id="37fe8-239">Displays help for `pwsh`.</span></span> <span data-ttu-id="37fe8-240">PowerShell で pwsh コマンドを入力する場合は、コマンドパラメーターにスラッシュ () ではなくハイフン () を付加し `-` `/` ます。</span><span class="sxs-lookup"><span data-stu-id="37fe8-240">If you are typing a pwsh command in PowerShell, prepend the command parameters with a hyphen (`-`), not a forward slash (`/`).</span></span>
