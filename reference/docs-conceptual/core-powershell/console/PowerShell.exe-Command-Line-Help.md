---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: PowerShell.exe コマンドラインのヘルプ
ms.assetid: 1ab7b93b-6785-42c6-a1c9-35ff686a958f
ms.openlocfilehash: 60b6a7e310821a4092b0972b7abbdae0e2d5f738
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
ms.locfileid: "30952581"
---
# <a name="powershellexe-command-line-help"></a><span data-ttu-id="f75a9-103">PowerShell.exe コマンドラインのヘルプ</span><span class="sxs-lookup"><span data-stu-id="f75a9-103">PowerShell.exe Command-Line Help</span></span>

<span data-ttu-id="f75a9-104">PowerShell.exe を使用して、Cmd.exe などの別のツールのコマンド ラインから PowerShell セッションを起動したり、PowerShell.exe を PowerShell コマンド ラインで使用して、新しいセッションを開始したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f75a9-104">You can use PowerShell.exe to start a PowerShell session from the command line of another tool, such as Cmd.exe, or use it at the PowerShell command line to start a new session.</span></span> <span data-ttu-id="f75a9-105">パラメーターを使用して、セッションをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="f75a9-105">Use the parameters to customize the session.</span></span>

## <a name="syntax"></a><span data-ttu-id="f75a9-106">構文</span><span class="sxs-lookup"><span data-stu-id="f75a9-106">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="f75a9-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f75a9-107">Parameters</span></span>

### <a name="-encodedcommand-base64encodedcommand"></a><span data-ttu-id="f75a9-108">-EncodedCommand <Base64EncodedCommand></span><span class="sxs-lookup"><span data-stu-id="f75a9-108">-EncodedCommand <Base64EncodedCommand></span></span>

<span data-ttu-id="f75a9-109">Base 64 エンコード文字列版のコマンドを許可します。</span><span class="sxs-lookup"><span data-stu-id="f75a9-109">Accepts a base-64-encoded string version of a command.</span></span> <span data-ttu-id="f75a9-110">複雑な引用符や中かっこを必要とするコマンドを PowerShell に渡す場合にこのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f75a9-110">Use this parameter to submit commands to PowerShell that require complex quotation marks or curly braces.</span></span>

### <a name="-executionpolicy-executionpolicy"></a><span data-ttu-id="f75a9-111">-ExecutionPolicy <ExecutionPolicy></span><span class="sxs-lookup"><span data-stu-id="f75a9-111">-ExecutionPolicy <ExecutionPolicy></span></span>

<span data-ttu-id="f75a9-112">現在のセッションの既定の実行ポリシーを設定し、$env:PSExecutionPolicyPreference 環境変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="f75a9-112">Sets the default execution policy for the current session and saves it in the $env:PSExecutionPolicyPreference environment variable.</span></span> <span data-ttu-id="f75a9-113">このパラメーターを指定しても、レジストリで設定された PowerShell の実行ポリシーが変更されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="f75a9-113">This parameter does not change the PowerShell execution policy that is set in the registry.</span></span> <span data-ttu-id="f75a9-114">有効な値の一覧など、PowerShell 実行ポリシーについては、「[about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f75a9-114">For information about PowerShell execution policies, including a list of valid values, see [about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>

### <a name="-file-filepath-parameters"></a><span data-ttu-id="f75a9-115">-File <FilePath> \[<Parameters>]</span><span class="sxs-lookup"><span data-stu-id="f75a9-115">-File <FilePath> \[<Parameters>]</span></span>

<span data-ttu-id="f75a9-116">スクリプトで作成される関数と変数を現在のセッションで使用できるように、指定したスクリプトをローカル スコープ ("ドット ソース形式") で実行します。</span><span class="sxs-lookup"><span data-stu-id="f75a9-116">Runs the specified script in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="f75a9-117">スクリプト ファイルのパスと (存在する場合) パラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="f75a9-117">Enter the script file path and any parameters.</span></span> <span data-ttu-id="f75a9-118">**File** はコマンド内の最後のパラメーターにする必要があります。これは、**File** パラメーター名の後に入力されるすべての文字が、スクリプト ファイルのパス、およびその後に続くスクリプト パラメーターとその値として解釈されるためです。</span><span class="sxs-lookup"><span data-stu-id="f75a9-118">**File** must be the last parameter in the command, because all characters typed after the **File** parameter name are interpreted as the script file path followed by the script parameters and their values.</span></span>

<span data-ttu-id="f75a9-119">**File** パラメーターの値には、スクリプトのパラメーターとパラメーター値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f75a9-119">You can include the parameters of a script, and parameter values, in the value of the **File** parameter.</span></span> <span data-ttu-id="f75a9-120">例: `-File .\Get-Script.ps1 -Domain Central`スクリプトに渡されるパラメーターは、リテラル文字列として渡されます (現在のシェルによる解釈の後で)。</span><span class="sxs-lookup"><span data-stu-id="f75a9-120">For example: `-File .\Get-Script.ps1 -Domain Central` Note that parameters passed to the script are passed as literal strings (after interpretation by the current shell).</span></span>
<span data-ttu-id="f75a9-121">たとえば、cmd.exe で環境変数値を渡す場合は、次の cmd.exe 構文を使用します: `powershell -File .\test.ps1 -Sample %windir%` PowerShell 構文を使用するとしたら、この例では、リテラル "$env:windir" を受け取り、その環境変数の値は受け取りません: `powershell -File .\test.ps1 -Sample $env:windir`</span><span class="sxs-lookup"><span data-stu-id="f75a9-121">For example, if you are in cmd.exe and want to pass an environment variable value, you would use the cmd.exe syntax: `powershell -File .\test.ps1 -Sample %windir%` If you were to use PowerShell syntax, then in this example your script would receive the literal "$env:windir" and not the value of that environmental variable: `powershell -File .\test.ps1 -Sample $env:windir`</span></span>

<span data-ttu-id="f75a9-122">通常、スクリプトのスイッチ パラメーターは、含めるか省略するかのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="f75a9-122">Typically, the switch parameters of a script are either included or omitted.</span></span> <span data-ttu-id="f75a9-123">たとえば、次のコマンドは、Get-Script.ps1 スクリプト ファイルの **All** パラメーターを使用します。`-File .\Get-Script.ps1 -All`</span><span class="sxs-lookup"><span data-stu-id="f75a9-123">For example, the following command uses the **All** parameter of the Get-Script.ps1 script file: `-File .\Get-Script.ps1 -All`</span></span>

### <a name="-inputformat-text--xml"></a><span data-ttu-id="f75a9-124">\-InputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="f75a9-124">\-InputFormat {Text | XML}</span></span>

<span data-ttu-id="f75a9-125">PowerShell に送信されるデータの形式を記述します。</span><span class="sxs-lookup"><span data-stu-id="f75a9-125">Describes the format of data sent to PowerShell.</span></span> <span data-ttu-id="f75a9-126">使用できる値は、"Text" (テキスト文字列) と "XML" (シリアル化された CLIXML 形式) です。</span><span class="sxs-lookup"><span data-stu-id="f75a9-126">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-mta"></a><span data-ttu-id="f75a9-127">-Mta</span><span class="sxs-lookup"><span data-stu-id="f75a9-127">-Mta</span></span>

<span data-ttu-id="f75a9-128">マルチスレッド アパートメントを使用して、PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="f75a9-128">Starts PowerShell using a multi-threaded apartment.</span></span> <span data-ttu-id="f75a9-129">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f75a9-129">This parameter is introduced in PowerShell 3.0.</span></span> <span data-ttu-id="f75a9-130">PowerShell 3.0 では、シングルスレッド アパートメント (STA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="f75a9-130">In PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span> <span data-ttu-id="f75a9-131">PowerShell 2.0 では、マルチスレッド アパートメント (MTA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="f75a9-131">In PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span>

### <a name="-noexit"></a><span data-ttu-id="f75a9-132">-NoExit</span><span class="sxs-lookup"><span data-stu-id="f75a9-132">-NoExit</span></span>

<span data-ttu-id="f75a9-133">スタートアップ コマンドを実行後、終了しません。</span><span class="sxs-lookup"><span data-stu-id="f75a9-133">Does not exit after running startup commands.</span></span>

### <a name="-nologo"></a><span data-ttu-id="f75a9-134">-NoLogo</span><span class="sxs-lookup"><span data-stu-id="f75a9-134">-NoLogo</span></span>

<span data-ttu-id="f75a9-135">スタートアップ時に著作権の見出しを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="f75a9-135">Hides the copyright banner at startup.</span></span>

### <a name="-noninteractive"></a><span data-ttu-id="f75a9-136">-NonInteractive</span><span class="sxs-lookup"><span data-stu-id="f75a9-136">-NonInteractive</span></span>

<span data-ttu-id="f75a9-137">ユーザーに対話的なプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="f75a9-137">Does not present an interactive prompt to the user.</span></span>

### <a name="-noprofile"></a><span data-ttu-id="f75a9-138">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="f75a9-138">-NoProfile</span></span>

<span data-ttu-id="f75a9-139">PowerShell プロファイルを読み込みません。</span><span class="sxs-lookup"><span data-stu-id="f75a9-139">Does not load the PowerShell profile.</span></span>

### <a name="-outputformat-text--xml"></a><span data-ttu-id="f75a9-140">-OutputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="f75a9-140">-OutputFormat {Text | XML}</span></span>

<span data-ttu-id="f75a9-141">PowerShell からの出力の形式を決定します。</span><span class="sxs-lookup"><span data-stu-id="f75a9-141">Determines how output from PowerShell is formatted.</span></span> <span data-ttu-id="f75a9-142">使用できる値は、"Text" (テキスト文字列) と "XML" (シリアル化された CLIXML 形式) です。</span><span class="sxs-lookup"><span data-stu-id="f75a9-142">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-psconsolefile-filepath"></a><span data-ttu-id="f75a9-143">-PSConsoleFile <FilePath></span><span class="sxs-lookup"><span data-stu-id="f75a9-143">-PSConsoleFile <FilePath></span></span>

<span data-ttu-id="f75a9-144">指定された PowerShell コンソール ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="f75a9-144">Loads the specified PowerShell console file.</span></span> <span data-ttu-id="f75a9-145">コンソール ファイルの名前とパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="f75a9-145">Enter the path and name of the console file.</span></span> <span data-ttu-id="f75a9-146">コンソール ファイルを作成するには、PowerShell で [`Export-Console`](/powershell/module/Microsoft.PowerShell.Core/Export-Console) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f75a9-146">To create a console file, use the [`Export-Console`](/powershell/module/Microsoft.PowerShell.Core/Export-Console) cmdlet in PowerShell.</span></span>

### <a name="-sta"></a><span data-ttu-id="f75a9-147">-Sta</span><span class="sxs-lookup"><span data-stu-id="f75a9-147">-Sta</span></span>

<span data-ttu-id="f75a9-148">シングルスレッド アパートメントを使用して、PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="f75a9-148">Starts PowerShell using a single-threaded apartment.</span></span> <span data-ttu-id="f75a9-149">PowerShell 3.0 では、シングルスレッド アパートメント (STA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="f75a9-149">In PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span> <span data-ttu-id="f75a9-150">PowerShell 2.0 では、マルチスレッド アパートメント (MTA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="f75a9-150">In PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span>

### <a name="-version-powershell-version"></a><span data-ttu-id="f75a9-151">-Version <PowerShell Version></span><span class="sxs-lookup"><span data-stu-id="f75a9-151">-Version <PowerShell Version></span></span>

<span data-ttu-id="f75a9-152">指定したバージョンの PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="f75a9-152">Starts the specified version of PowerShell.</span></span> <span data-ttu-id="f75a9-153">指定するバージョンがシステムにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f75a9-153">The version that you specify must be installed on the system.</span></span> <span data-ttu-id="f75a9-154">PowerShell 3.0 がコンピューターにインストールされている場合、有効な値は "2.0" と "3.0" です。</span><span class="sxs-lookup"><span data-stu-id="f75a9-154">If PowerShell 3.0 is installed on the computer, valid values are "2.0" and "3.0".</span></span> <span data-ttu-id="f75a9-155">既定値は "3.0" です。</span><span class="sxs-lookup"><span data-stu-id="f75a9-155">The default value is "3.0".</span></span>

<span data-ttu-id="f75a9-156">PowerShell 3.0 がコンピューターにインストールされていない場合、有効な値は "2.0" のみです。</span><span class="sxs-lookup"><span data-stu-id="f75a9-156">If PowerShell 3.0 is not installed, the only valid value is "2.0".</span></span> <span data-ttu-id="f75a9-157">他の値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="f75a9-157">Other values are ignored.</span></span>

<span data-ttu-id="f75a9-158">詳細については「[Windows PowerShell のインストール](../../setup/installing-windows-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f75a9-158">For more information, see "[Installing Windows PowerShell](../../setup/installing-windows-powershell.md)".</span></span>

### <a name="-windowstyle-window-style"></a><span data-ttu-id="f75a9-159">-WindowStyle <Window style></span><span class="sxs-lookup"><span data-stu-id="f75a9-159">-WindowStyle <Window style></span></span>

<span data-ttu-id="f75a9-160">セッションのウィンドウ スタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="f75a9-160">Sets the window style for the session.</span></span> <span data-ttu-id="f75a9-161">使用できる値は、Normal、Minimized、Maximized、Hidden です。</span><span class="sxs-lookup"><span data-stu-id="f75a9-161">Valid values are Normal, Minimized, Maximized and Hidden.</span></span>

### <a name="-command"></a><span data-ttu-id="f75a9-162">-Command</span><span class="sxs-lookup"><span data-stu-id="f75a9-162">-Command</span></span>

<span data-ttu-id="f75a9-163">PowerShell のコマンド プロンプトに入力された場合と同様に、指定されたコマンド (および任意のパラメーター) を実行します。NoExit パラメーターが指定されていない場合は、そのまま終了します。</span><span class="sxs-lookup"><span data-stu-id="f75a9-163">Executes the specified commands (and any parameters) as though they were typed at the PowerShell command prompt, and then exits, unless the NoExit parameter is specified.</span></span>
<span data-ttu-id="f75a9-164">基本的に、`-Command` の後の任意のテキストは、単一のコマンドラインとして PowerShell に送信されます (これは、`-File` がスクリプトに送信されるパラメーターを処理する方法とは異なります)。</span><span class="sxs-lookup"><span data-stu-id="f75a9-164">Essentially, any text after `-Command` is sent as a single command line to PowerShell (this is different from how `-File` handles parameters sent to a script).</span></span>

<span data-ttu-id="f75a9-165">Command の値には、"-"、文字列、またはスクリプト ブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f75a9-165">The value of Command can be "-", a string.</span></span> <span data-ttu-id="f75a9-166">またはスクリプト ブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f75a9-166">or a script block.</span></span> <span data-ttu-id="f75a9-167">Command の値が "-" の場合、コマンド テキストは標準入力から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="f75a9-167">If the value of Command is "-", the command text is read from standard input.</span></span>

<span data-ttu-id="f75a9-168">スクリプト ブロックは中かっこ ({}) で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="f75a9-168">Script blocks must be enclosed in braces ({}).</span></span> <span data-ttu-id="f75a9-169">スクリプト ブロックを指定できるのは、PowerShell.exe を PowerShell で実行する場合だけです。</span><span class="sxs-lookup"><span data-stu-id="f75a9-169">You can specify a script block only when running PowerShell.exe in PowerShell.</span></span> <span data-ttu-id="f75a9-170">スクリプトの結果は、ライブ オブジェクトとしてではなく、逆シリアル化された XML オブジェクトとして親シェルに返されます。</span><span class="sxs-lookup"><span data-stu-id="f75a9-170">The results of the script are returned to the parent shell as deserialized XML objects, not live objects.</span></span>

<span data-ttu-id="f75a9-171">Command の値が文字列の場合、**Command** はコマンドの最後のパラメーターでなければなりません。コマンドの後に入力された文字は、コマンド引数として解釈されるためです。</span><span class="sxs-lookup"><span data-stu-id="f75a9-171">If the value of Command is a string, **Command** must be the last parameter in the command, because any characters typed after the command are interpreted as the command arguments.</span></span>

<span data-ttu-id="f75a9-172">PowerShell コマンドを実行する文字列を書き込むには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="f75a9-172">To write a string that runs a PowerShell command, use the format:</span></span>

```powershell
"& {<command>}"
```

<span data-ttu-id="f75a9-173">引用符によりこれが文字列であることを示し、呼び出し演算子 (&) によりコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f75a9-173">where the quotation marks indicate a string and the invoke operator (&) causes the command to be executed.</span></span>

### <a name="-help---"></a><span data-ttu-id="f75a9-174">-Help、-?、/?</span><span class="sxs-lookup"><span data-stu-id="f75a9-174">-Help, -?, /?</span></span>

<span data-ttu-id="f75a9-175">このメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="f75a9-175">Shows this message.</span></span> <span data-ttu-id="f75a9-176">PowerShell で PowerShell.exe のコマンドを入力している場合、コマンド パラメーターの前にスラッシュ (/) ではなくハイフン (-) を入力してください。</span><span class="sxs-lookup"><span data-stu-id="f75a9-176">If you are typing a PowerShell.exe command in PowerShell, prepend the command parameters with a hyphen (-), not a forward slash (/).</span></span> <span data-ttu-id="f75a9-177">Cmd.exe では、ハイフンとスラッシュのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f75a9-177">You can use either a hyphen or forward slash in Cmd.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="f75a9-178">トラブルシューティング上の注意: PowerShell 2.0 では、一部のプログラムを Windows PowerShell コンソールで開始すると、LastExitCode 0xc0000142 で失敗します。</span><span class="sxs-lookup"><span data-stu-id="f75a9-178">Troubleshooting Note: In PowerShell 2.0, starting some programs in the Windows PowerShell console fails with a LastExitCode of 0xc0000142.</span></span>

## <a name="examples"></a><span data-ttu-id="f75a9-179">例</span><span class="sxs-lookup"><span data-stu-id="f75a9-179">EXAMPLES</span></span>

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