---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "PowerShell.exe コマンドラインのヘルプ"
ms.assetid: 1ab7b93b-6785-42c6-a1c9-35ff686a958f
ms.openlocfilehash: c2583dac14f32db414f0a4377b1694ab7fa7523b
ms.sourcegitcommit: cd66d4f49ea762a31887af2c72d087b219ddbe10
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2017
---
# <a name="powershellexe-command-line-help"></a><span data-ttu-id="3e787-103">PowerShell.exe コマンドラインのヘルプ</span><span class="sxs-lookup"><span data-stu-id="3e787-103">PowerShell.exe Command-Line Help</span></span>
<span data-ttu-id="3e787-104">Windows PowerShell セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="3e787-104">Starts a Windows PowerShell session.</span></span> <span data-ttu-id="3e787-105">PowerShell.exe を使用して、Cmd.exe などの別のツールのコマンド ラインから Windows PowerShell セッションを起動したり、PowerShell.exe を Windows PowerShell コマンド ラインで使用して、新しいセッションを開始したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3e787-105">You can use PowerShell.exe to start a Windows PowerShell session from the command line of another tool, such as Cmd.exe, or use it at the Windows PowerShell command line to start a new session.</span></span> <span data-ttu-id="3e787-106">パラメーターを使用して、セッションをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="3e787-106">Use the parameters to customize the session.</span></span>

## <a name="syntax"></a><span data-ttu-id="3e787-107">構文</span><span class="sxs-lookup"><span data-stu-id="3e787-107">Syntax</span></span>

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
       [-PSConsoleFile <FilePath> | -Version <Windows PowerShell version>]
       [-Sta]
       [-WindowStyle <style>]
        

PowerShell[.exe] -Help | -? | /?
```

## <a name="parameters"></a><span data-ttu-id="3e787-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3e787-108">Parameters</span></span>

### <a name="-encodedcommand-base64encodedcommand"></a><span data-ttu-id="3e787-109">-EncodedCommand <Base64EncodedCommand></span><span class="sxs-lookup"><span data-stu-id="3e787-109">-EncodedCommand <Base64EncodedCommand></span></span>
<span data-ttu-id="3e787-110">Base 64 エンコード文字列版のコマンドを許可します。</span><span class="sxs-lookup"><span data-stu-id="3e787-110">Accepts a base-64-encoded string version of a command.</span></span> <span data-ttu-id="3e787-111">このパラメーターは、複雑な引用符や中かっこを必要とするコマンドを Windows PowerShell に渡す場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="3e787-111">Use this parameter to submit commands to Windows PowerShell that require complex quotation marks or curly braces.</span></span>

### <a name="-executionpolicy-executionpolicy"></a><span data-ttu-id="3e787-112">-ExecutionPolicy <ExecutionPolicy></span><span class="sxs-lookup"><span data-stu-id="3e787-112">-ExecutionPolicy <ExecutionPolicy></span></span>
<span data-ttu-id="3e787-113">現在のセッションの既定の実行ポリシーを設定し、$env:PSExecutionPolicyPreference 環境変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="3e787-113">Sets the default execution policy for the current session and saves it in the $env:PSExecutionPolicyPreference environment variable.</span></span> <span data-ttu-id="3e787-114">このパラメーターを指定しても、レジストリで設定された Windows PowerShell の実行ポリシーが変更されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="3e787-114">This parameter does not change the Windows PowerShell execution policy that is set in the registry.</span></span> <span data-ttu-id="3e787-115">使用できる値の一覧など、Windows PowerShell 実行ポリシーの詳細については、「about_Execution_Policies (http://go.microsoft.com/fwlink/?LinkID=135170)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3e787-115">For information about Windows PowerShell execution policies, including a list of valid values, see about_Execution_Policies (http://go.microsoft.com/fwlink/?LinkID=135170).</span></span>

### <a name="-file-filepath-parameters"></a><span data-ttu-id="3e787-116">-File <FilePath> \[<Parameters>]</span><span class="sxs-lookup"><span data-stu-id="3e787-116">-File <FilePath> \[<Parameters>]</span></span>
<span data-ttu-id="3e787-117">スクリプトで作成される関数と変数を現在のセッションで使用できるように、指定したスクリプトをローカル スコープ ("ドット ソース形式") で実行します。</span><span class="sxs-lookup"><span data-stu-id="3e787-117">Runs the specified script in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="3e787-118">スクリプト ファイルのパスと (存在する場合) パラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="3e787-118">Enter the script file path and any parameters.</span></span> <span data-ttu-id="3e787-119">**File** はコマンド内の最後のパラメーターにする必要があります。これは、**File** パラメーター名の後に入力されるすべての文字が、スクリプト ファイルのパス、およびその後に続くスクリプト パラメーターとその値として解釈されるためです。</span><span class="sxs-lookup"><span data-stu-id="3e787-119">**File** must be the last parameter in the command, because all characters typed after the **File** parameter name are interpreted as the script file path followed by the script parameters and their values.</span></span>

<span data-ttu-id="3e787-120">**File** パラメーターの値には、スクリプトのパラメーターとパラメーター値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3e787-120">You can include the parameters of a script, and parameter values, in the value of the **File** parameter.</span></span> <span data-ttu-id="3e787-121">例: `-File .\Get-Script.ps1 -Domain Central`スクリプトに渡されるパラメーターは、リテラル文字列として渡されます (現在のシェルによる解釈の後で)。</span><span class="sxs-lookup"><span data-stu-id="3e787-121">For example: `-File .\Get-Script.ps1 -Domain Central` Note that parameters passed to the script are passed as literal strings (after interpretation by the current shell).</span></span>
<span data-ttu-id="3e787-122">たとえば、cmd.exe で環境変数値を渡す場合は、次の cmd.exe 構文を使用します: `powershell -File .\test.ps1 -Sample %windir%` PowerShell 構文を使用するとしたら、この例では、リテラル "$env:windir" を受け取り、その環境変数の値は受け取りません: `powershell -File .\test.ps1 -Sample $env:windir`</span><span class="sxs-lookup"><span data-stu-id="3e787-122">For example, if you are in cmd.exe and want to pass an environment variable value, you would use the cmd.exe syntax: `powershell -File .\test.ps1 -Sample %windir%` If you were to use PowerShell syntax, then in this example your script would receive the literal "$env:windir" and not the value of that environmental variable: `powershell -File .\test.ps1 -Sample $env:windir`</span></span>

<span data-ttu-id="3e787-123">通常、スクリプトのスイッチ パラメーターは、含めるか省略するかのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="3e787-123">Typically, the switch parameters of a script are either included or omitted.</span></span> <span data-ttu-id="3e787-124">たとえば、次のコマンドは、Get-Script.ps1 スクリプト ファイルの **All** パラメーターを使用します。`-File .\Get-Script.ps1 -All`</span><span class="sxs-lookup"><span data-stu-id="3e787-124">For example, the following command uses the **All** parameter of the Get-Script.ps1 script file: `-File .\Get-Script.ps1 -All`</span></span>

### <a name="-inputformat-text--xml"></a><span data-ttu-id="3e787-125">\-InputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="3e787-125">\-InputFormat {Text | XML}</span></span>
<span data-ttu-id="3e787-126">Windows PowerShell に送信されるデータ形式を記述します。</span><span class="sxs-lookup"><span data-stu-id="3e787-126">Describes the format of data sent to Windows PowerShell.</span></span> <span data-ttu-id="3e787-127">使用できる値は、"Text" (テキスト文字列) と "XML" (シリアル化された CLIXML 形式) です。</span><span class="sxs-lookup"><span data-stu-id="3e787-127">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-mta"></a><span data-ttu-id="3e787-128">-Mta</span><span class="sxs-lookup"><span data-stu-id="3e787-128">-Mta</span></span>
<span data-ttu-id="3e787-129">マルチスレッド アパートメントを使用して、Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="3e787-129">Starts Windows PowerShell using a multi-threaded apartment.</span></span> <span data-ttu-id="3e787-130">このパラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="3e787-130">This parameter is introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="3e787-131">Windows PowerShell 3.0 では、シングルスレッド アパートメント (STA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="3e787-131">In Windows PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span> <span data-ttu-id="3e787-132">Windows PowerShell 2.0 では、マルチスレッド アパートメント (MTA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="3e787-132">In Windows PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span>

### <a name="-noexit"></a><span data-ttu-id="3e787-133">-NoExit</span><span class="sxs-lookup"><span data-stu-id="3e787-133">-NoExit</span></span>
<span data-ttu-id="3e787-134">スタートアップ コマンドを実行後、終了しません。</span><span class="sxs-lookup"><span data-stu-id="3e787-134">Does not exit after running startup commands.</span></span>

### <a name="-nologo"></a><span data-ttu-id="3e787-135">-NoLogo</span><span class="sxs-lookup"><span data-stu-id="3e787-135">-NoLogo</span></span>
<span data-ttu-id="3e787-136">スタートアップ時に著作権の見出しを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="3e787-136">Hides the copyright banner at startup.</span></span>

### <a name="-noninteractive"></a><span data-ttu-id="3e787-137">-NonInteractive</span><span class="sxs-lookup"><span data-stu-id="3e787-137">-NonInteractive</span></span>
<span data-ttu-id="3e787-138">ユーザーに対話的なプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="3e787-138">Does not present an interactive prompt to the user.</span></span>

### <a name="-noprofile"></a><span data-ttu-id="3e787-139">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="3e787-139">-NoProfile</span></span>
<span data-ttu-id="3e787-140">Windows PowerShell プロファイルを読み込みません。</span><span class="sxs-lookup"><span data-stu-id="3e787-140">Does not load the Windows PowerShell profile.</span></span>

### <a name="-outputformat-text--xml"></a><span data-ttu-id="3e787-141">-OutputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="3e787-141">-OutputFormat {Text | XML}</span></span>
<span data-ttu-id="3e787-142">Windows PowerShell からの出力の形式を決定します。</span><span class="sxs-lookup"><span data-stu-id="3e787-142">Determines how output from Windows PowerShell is formatted.</span></span> <span data-ttu-id="3e787-143">使用できる値は、"Text" (テキスト文字列) と "XML" (シリアル化された CLIXML 形式) です。</span><span class="sxs-lookup"><span data-stu-id="3e787-143">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-psconsolefile-filepath"></a><span data-ttu-id="3e787-144">-PSConsoleFile <FilePath></span><span class="sxs-lookup"><span data-stu-id="3e787-144">-PSConsoleFile <FilePath></span></span>
<span data-ttu-id="3e787-145">指定された Windows PowerShell コンソール ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="3e787-145">Loads the specified Windows PowerShell console file.</span></span> <span data-ttu-id="3e787-146">コンソール ファイルの名前とパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="3e787-146">Enter the path and name of the console file.</span></span> <span data-ttu-id="3e787-147">コンソール ファイルを作成するには、Windows PowerShell で [Export-Console](https://technet.microsoft.com/en-us/library/4bab1c02-9e61-4aaf-9957-11d1934ef4ef) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e787-147">To create a console file, use the [Export-Console](https://technet.microsoft.com/en-us/library/4bab1c02-9e61-4aaf-9957-11d1934ef4ef) cmdlet in Windows PowerShell.</span></span>

### <a name="-sta"></a><span data-ttu-id="3e787-148">-Sta</span><span class="sxs-lookup"><span data-stu-id="3e787-148">-Sta</span></span>
<span data-ttu-id="3e787-149">シングルスレッド アパートメントを使用して、Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="3e787-149">Starts Windows PowerShell using a single-threaded apartment.</span></span> <span data-ttu-id="3e787-150">Windows PowerShell 3.0 では、シングルスレッド アパートメント (STA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="3e787-150">In Windows PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span> <span data-ttu-id="3e787-151">Windows PowerShell 2.0 では、マルチスレッド アパートメント (MTA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="3e787-151">In Windows PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span>

### <a name="-version-windows-powershell-version"></a><span data-ttu-id="3e787-152">-Version <Windows PowerShell Version></span><span class="sxs-lookup"><span data-stu-id="3e787-152">-Version <Windows PowerShell Version></span></span>
<span data-ttu-id="3e787-153">指定したバージョンの Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="3e787-153">Starts the specified version of Windows PowerShell.</span></span> <span data-ttu-id="3e787-154">指定するバージョンがシステムにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e787-154">The version that you specify must be installed on the system.</span></span> <span data-ttu-id="3e787-155">Windows PowerShell 3.0 がコンピューターにインストールされている場合、使用できる値は "2.0" と "3.0" です。</span><span class="sxs-lookup"><span data-stu-id="3e787-155">If Windows PowerShell 3.0 is installed on the computer, valid values are "2.0" and "3.0".</span></span> <span data-ttu-id="3e787-156">既定値は "3.0" です。</span><span class="sxs-lookup"><span data-stu-id="3e787-156">The default value is "3.0".</span></span>

<span data-ttu-id="3e787-157">Windows PowerShell 3.0 がコンピューターにインストールされていない場合、使用できる値は "2.0" のみです。</span><span class="sxs-lookup"><span data-stu-id="3e787-157">If Windows PowerShell 3.0 is not installed, the only valid value is "2.0".</span></span> <span data-ttu-id="3e787-158">他の値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="3e787-158">Other values are ignored.</span></span>

<span data-ttu-id="3e787-159">詳細については、「[Windows PowerShell ファースト ステップ ガイド [OLD MSDN]](https://technet.microsoft.com/en-us/library/69555d95-b481-43e1-86e7-b46d68b3e2dd)」の「Windows PowerShell のインストール」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3e787-159">For more information, see "Installing Windows PowerShell" in the [Getting Started with Windows PowerShell [OLD MSDN]](https://technet.microsoft.com/en-us/library/69555d95-b481-43e1-86e7-b46d68b3e2dd).</span></span>

### <a name="-windowstyle-window-style"></a><span data-ttu-id="3e787-160">-WindowStyle <Window style></span><span class="sxs-lookup"><span data-stu-id="3e787-160">-WindowStyle <Window style></span></span>
<span data-ttu-id="3e787-161">セッションのウィンドウ スタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="3e787-161">Sets the window style for the session.</span></span> <span data-ttu-id="3e787-162">使用できる値は、Normal、Minimized、Maximized、Hidden です。</span><span class="sxs-lookup"><span data-stu-id="3e787-162">Valid values are Normal, Minimized, Maximized and Hidden.</span></span>

### <a name="-command"></a><span data-ttu-id="3e787-163">-Command</span><span class="sxs-lookup"><span data-stu-id="3e787-163">-Command</span></span>
<span data-ttu-id="3e787-164">Windows PowerShell のコマンド プロンプトに入力された場合と同様に、指定されたコマンド (および任意のパラメーター) を実行します。NoExit パラメーターが指定されていない場合は、そのまま終了します。</span><span class="sxs-lookup"><span data-stu-id="3e787-164">Executes the specified commands (and any parameters) as though they were typed at the Windows PowerShell command prompt, and then exits, unless the NoExit parameter is specified.</span></span>
<span data-ttu-id="3e787-165">基本的に、`-Command` の後の任意のテキストは、単一のコマンドラインとして PowerShell に送信されます (これは、`-File` がスクリプトに送信されるパラメーターを処理する方法とは異なります)。</span><span class="sxs-lookup"><span data-stu-id="3e787-165">Essentially, any text after `-Command` is sent as a single command line to PowerShell (this is different from how `-File` handles parameters sent to a script).</span></span>

<span data-ttu-id="3e787-166">Command の値には、"-"、文字列、またはスクリプト ブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3e787-166">The value of Command can be "-", a string.</span></span> <span data-ttu-id="3e787-167">またはスクリプト ブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3e787-167">or a script block.</span></span> <span data-ttu-id="3e787-168">Command の値が "-" の場合、コマンド テキストは標準入力から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="3e787-168">If the value of Command is "-", the command text is read from standard input.</span></span>

<span data-ttu-id="3e787-169">スクリプト ブロックは中かっこ ({}) で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e787-169">Script blocks must be enclosed in braces ({}).</span></span> <span data-ttu-id="3e787-170">スクリプト ブロックを指定できるのは、PowerShell.exe を Windows PowerShell で実行する場合だけです。</span><span class="sxs-lookup"><span data-stu-id="3e787-170">You can specify a script block only when running PowerShell.exe in Windows PowerShell.</span></span> <span data-ttu-id="3e787-171">スクリプトの結果は、ライブ オブジェクトとしてではなく、逆シリアル化された XML オブジェクトとして親シェルに返されます。</span><span class="sxs-lookup"><span data-stu-id="3e787-171">The results of the script are returned to the parent shell as deserialized XML objects, not live objects.</span></span>

<span data-ttu-id="3e787-172">Command の値が文字列の場合、**Command** はコマンドの最後のパラメーターでなければなりません。コマンドの後に入力された文字は、コマンド引数として解釈されるためです。</span><span class="sxs-lookup"><span data-stu-id="3e787-172">If the value of Command is a string, **Command** must be the last parameter in the command, because any characters typed after the command are interpreted as the command arguments.</span></span>

<span data-ttu-id="3e787-173">Windows PowerShell コマンドを実行する文字列を記述するには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="3e787-173">To write a string that runs a Windows PowerShell command, use the format:</span></span>

```
"& {<command>}"
```

<span data-ttu-id="3e787-174">引用符によりこれが文字列であることを示し、呼び出し演算子 (&) によりコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3e787-174">where the quotation marks indicate a string and the invoke operator (&) causes the command to be executed.</span></span>

### <a name="-help---"></a><span data-ttu-id="3e787-175">-Help、-?、/?</span><span class="sxs-lookup"><span data-stu-id="3e787-175">-Help, -?, /?</span></span>
<span data-ttu-id="3e787-176">このメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="3e787-176">Shows this message.</span></span> <span data-ttu-id="3e787-177">Windows PowerShell で PowerShell.exe のコマンドを入力している場合、コマンド パラメーターの前にスラッシュ (/) ではなくハイフン (-) を入力してください。</span><span class="sxs-lookup"><span data-stu-id="3e787-177">If you are typing a PowerShell.exe command in Windows PowerShell, prepend the command parameters with a hyphen (-), not a forward slash (/).</span></span> <span data-ttu-id="3e787-178">Cmd.exe では、ハイフンとスラッシュのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e787-178">You can use either a hyphen or forward slash in Cmd.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="3e787-179">トラブルシューティング上の注意: Windows PowerShell 2.0 では、一部のプログラムを Windows PowerShell コンソールで開始すると、LastExitCode 0xc0000142 で失敗します。</span><span class="sxs-lookup"><span data-stu-id="3e787-179">Troubleshooting Note: In Windows PowerShell 2.0, starting some programs in the Windows PowerShell console fails with a LastExitCode of 0xc0000142.</span></span>

## <a name="examples"></a><span data-ttu-id="3e787-180">例</span><span class="sxs-lookup"><span data-stu-id="3e787-180">EXAMPLES</span></span>

```
# Create a new PowerShell session and load a saved console file
PowerShell -PSConsoleFile sqlsnapin.psc1

# Create a new PowerShell V2 session with text input, XML output, and no logo
PowerShell -Version 2.0 -NoLogo -InputFormat text -OutputFormat XML

# Execute a Powerhell Command in a session
PowerShell -Command "Get-EventLog -LogName security"

# Run a script block in a session
PowerShell -Command {Get-EventLog -LogName security}

# An alternate wayh to run a command in a new session
PowerShell -Command "& {Get-EventLog -LogName security}"

# To use the -EncodedCommand parameter:
$command = "dir 'c:\program files' "
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
powershell.exe -encodedCommand $encodedCommand
```

