---
ms.date: 08/14/2018
keywords: PowerShell, コマンドレット
title: PowerShell.exe コマンドラインのヘルプ
ms.assetid: 1ab7b93b-6785-42c6-a1c9-35ff686a958f
ms.openlocfilehash: 0a11ebb11d29adf5853c232b3aa10bc72f92bf0c
ms.sourcegitcommit: 03c7672ee72698fe88a73e99702ceaadf87e702f
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "51691832"
---
# <a name="powershellexe-command-line-help"></a><span data-ttu-id="95e40-103">PowerShell.exe コマンドラインのヘルプ</span><span class="sxs-lookup"><span data-stu-id="95e40-103">PowerShell.exe Command-Line Help</span></span>

<span data-ttu-id="95e40-104">PowerShell.exe を使用して、Cmd.exe などの別のツールのコマンド ラインから PowerShell セッションを起動したり、PowerShell.exe を PowerShell コマンド ラインで使用して、新しいセッションを開始したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="95e40-104">You can use PowerShell.exe to start a PowerShell session from the command line of another tool, such as Cmd.exe, or use it at the PowerShell command line to start a new session.</span></span> <span data-ttu-id="95e40-105">パラメーターを使用して、セッションをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="95e40-105">Use the parameters to customize the session.</span></span>

## <a name="syntax"></a><span data-ttu-id="95e40-106">構文</span><span class="sxs-lookup"><span data-stu-id="95e40-106">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="95e40-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="95e40-107">Parameters</span></span>

### <a name="-encodedcommand-base64encodedcommand"></a><span data-ttu-id="95e40-108">-EncodedCommand <Base64EncodedCommand></span><span class="sxs-lookup"><span data-stu-id="95e40-108">-EncodedCommand <Base64EncodedCommand></span></span>

<span data-ttu-id="95e40-109">Base 64 エンコード文字列版のコマンドを許可します。</span><span class="sxs-lookup"><span data-stu-id="95e40-109">Accepts a base-64-encoded string version of a command.</span></span> <span data-ttu-id="95e40-110">複雑な引用符や中かっこを必要とするコマンドを PowerShell に渡す場合にこのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="95e40-110">Use this parameter to submit commands to PowerShell that require complex quotation marks or curly braces.</span></span>

### <a name="-executionpolicy-executionpolicy"></a><span data-ttu-id="95e40-111">-ExecutionPolicy <ExecutionPolicy></span><span class="sxs-lookup"><span data-stu-id="95e40-111">-ExecutionPolicy <ExecutionPolicy></span></span>

<span data-ttu-id="95e40-112">現在のセッションの既定の実行ポリシーを設定し、$env:PSExecutionPolicyPreference 環境変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="95e40-112">Sets the default execution policy for the current session and saves it in the $env:PSExecutionPolicyPreference environment variable.</span></span> <span data-ttu-id="95e40-113">このパラメーターは、レジストリに設定された PowerShell 実行ポリシーを変更しません。</span><span class="sxs-lookup"><span data-stu-id="95e40-113">This parameter doesn't change the PowerShell execution policy that is set in the registry.</span></span> <span data-ttu-id="95e40-114">有効な値の一覧など、PowerShell 実行ポリシーについては、「[about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95e40-114">For information about PowerShell execution policies, including a list of valid values, see [about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>

### <a name="-file-filepath-parameters"></a><span data-ttu-id="95e40-115">-File <FilePath> \[<Parameters>]</span><span class="sxs-lookup"><span data-stu-id="95e40-115">-File <FilePath> \[<Parameters>]</span></span>

<span data-ttu-id="95e40-116">スクリプトで作成される関数と変数を現在のセッションで使用できるように、指定したスクリプトをローカル スコープ ("ドット ソース形式") で実行します。</span><span class="sxs-lookup"><span data-stu-id="95e40-116">Runs the specified script in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="95e40-117">スクリプト ファイルのパスと (存在する場合) パラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="95e40-117">Enter the script file path and any parameters.</span></span> <span data-ttu-id="95e40-118">**File** は、コマンド内の最後のパラメーターにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="95e40-118">**File** must be the last parameter in the command.</span></span> <span data-ttu-id="95e40-119">**-File** パラメーターの後に入力されたすべての値は、スクリプト ファイルのパスとそのスクリプトに渡されるパラメーターとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="95e40-119">All values typed after the **-File** parameter are interpreted as the script file path and parameters passed to that script.</span></span>

<span data-ttu-id="95e40-120">スクリプトに渡されるパラメーターは、(現在のシェルによる解釈の後で) リテラル文字列として渡されます。</span><span class="sxs-lookup"><span data-stu-id="95e40-120">Parameters passed to the script are passed as literal strings, after interpretation by the current shell.</span></span> <span data-ttu-id="95e40-121">たとえば、cmd.exe でし、環境変数の値を渡す、場合は、cmd.exe 構文を使用します。 `powershell.exe -File .\test.ps1 -TestParam %windir%`</span><span class="sxs-lookup"><span data-stu-id="95e40-121">For example, if you are in cmd.exe and want to pass an environment variable value, you would use the cmd.exe syntax: `powershell.exe -File .\test.ps1 -TestParam %windir%`</span></span>

<span data-ttu-id="95e40-122">これに対しを実行している`powershell.exe -File .\test.ps1 -TestParam $env:windir`リテラル文字列を受信するスクリプトの結果を cmd.exe で`$env:windir`を現在の cmd.exe シェルに特別な意味を持たないためです。</span><span class="sxs-lookup"><span data-stu-id="95e40-122">In contrast, running `powershell.exe -File .\test.ps1 -TestParam $env:windir` in cmd.exe results in the script receiving the literal string `$env:windir` because it has no special meaning to the current cmd.exe shell.</span></span>
<span data-ttu-id="95e40-123">`$env:windir`の環境変数の参照スタイル_できます_内で使用する、`-Command`パラメーター、PowerShell コードとして解釈されますがありますので。</span><span class="sxs-lookup"><span data-stu-id="95e40-123">The `$env:windir` style of environment variable reference _can_ be used inside a `-Command` parameter, since there it will be interpreted as PowerShell code.</span></span>

### <a name="-inputformat-text--xml"></a><span data-ttu-id="95e40-124">\-InputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="95e40-124">\-InputFormat {Text | XML}</span></span>

<span data-ttu-id="95e40-125">PowerShell に送信されるデータの形式を記述します。</span><span class="sxs-lookup"><span data-stu-id="95e40-125">Describes the format of data sent to PowerShell.</span></span> <span data-ttu-id="95e40-126">使用できる値は、"Text" (テキスト文字列) と "XML" (シリアル化された CLIXML 形式) です。</span><span class="sxs-lookup"><span data-stu-id="95e40-126">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-mta"></a><span data-ttu-id="95e40-127">-Mta</span><span class="sxs-lookup"><span data-stu-id="95e40-127">-Mta</span></span>

<span data-ttu-id="95e40-128">マルチスレッド アパートメントを使用して、PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="95e40-128">Starts PowerShell using a multi-threaded apartment.</span></span> <span data-ttu-id="95e40-129">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="95e40-129">This parameter is introduced in PowerShell 3.0.</span></span> <span data-ttu-id="95e40-130">PowerShell 3.0 では、シングルスレッド アパートメント (STA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="95e40-130">In PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span> <span data-ttu-id="95e40-131">PowerShell 2.0 では、マルチスレッド アパートメント (MTA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="95e40-131">In PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span>

### <a name="-noexit"></a><span data-ttu-id="95e40-132">-NoExit</span><span class="sxs-lookup"><span data-stu-id="95e40-132">-NoExit</span></span>

<span data-ttu-id="95e40-133">スタートアップ コマンドを実行後、終了しません。</span><span class="sxs-lookup"><span data-stu-id="95e40-133">Doesn't exit after running startup commands.</span></span>

### <a name="-nologo"></a><span data-ttu-id="95e40-134">-NoLogo</span><span class="sxs-lookup"><span data-stu-id="95e40-134">-NoLogo</span></span>

<span data-ttu-id="95e40-135">スタートアップ時に著作権の見出しを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="95e40-135">Hides the copyright banner at startup.</span></span>

### <a name="-noninteractive"></a><span data-ttu-id="95e40-136">-NonInteractive</span><span class="sxs-lookup"><span data-stu-id="95e40-136">-NonInteractive</span></span>

<span data-ttu-id="95e40-137">ユーザーに対話的なプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="95e40-137">Doesn't present an interactive prompt to the user.</span></span>

### <a name="-noprofile"></a><span data-ttu-id="95e40-138">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="95e40-138">-NoProfile</span></span>

<span data-ttu-id="95e40-139">PowerShell プロファイルを読み込みません。</span><span class="sxs-lookup"><span data-stu-id="95e40-139">Doesn't load the PowerShell profile.</span></span>

### <a name="-outputformat-text--xml"></a><span data-ttu-id="95e40-140">-OutputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="95e40-140">-OutputFormat {Text | XML}</span></span>

<span data-ttu-id="95e40-141">PowerShell からの出力の形式を決定します。</span><span class="sxs-lookup"><span data-stu-id="95e40-141">Determines how output from PowerShell is formatted.</span></span> <span data-ttu-id="95e40-142">使用できる値は、"Text" (テキスト文字列) と "XML" (シリアル化された CLIXML 形式) です。</span><span class="sxs-lookup"><span data-stu-id="95e40-142">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

### <a name="-psconsolefile-filepath"></a><span data-ttu-id="95e40-143">-PSConsoleFile <FilePath></span><span class="sxs-lookup"><span data-stu-id="95e40-143">-PSConsoleFile <FilePath></span></span>

<span data-ttu-id="95e40-144">指定された PowerShell コンソール ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="95e40-144">Loads the specified PowerShell console file.</span></span> <span data-ttu-id="95e40-145">コンソール ファイルの名前とパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="95e40-145">Enter the path and name of the console file.</span></span> <span data-ttu-id="95e40-146">コンソール ファイルを作成するには、PowerShell で [`Export-Console`](/powershell/module/Microsoft.PowerShell.Core/Export-Console) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="95e40-146">To create a console file, use the [`Export-Console`](/powershell/module/Microsoft.PowerShell.Core/Export-Console) cmdlet in PowerShell.</span></span>

### <a name="-sta"></a><span data-ttu-id="95e40-147">-Sta</span><span class="sxs-lookup"><span data-stu-id="95e40-147">-Sta</span></span>

<span data-ttu-id="95e40-148">シングルスレッド アパートメントを使用して、PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="95e40-148">Starts PowerShell using a single-threaded apartment.</span></span> <span data-ttu-id="95e40-149">PowerShell 3.0 では、シングルスレッド アパートメント (STA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="95e40-149">In PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span> <span data-ttu-id="95e40-150">PowerShell 2.0 では、マルチスレッド アパートメント (MTA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="95e40-150">In PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span>

### <a name="-version-powershell-version"></a><span data-ttu-id="95e40-151">-Version <PowerShell Version></span><span class="sxs-lookup"><span data-stu-id="95e40-151">-Version <PowerShell Version></span></span>

<span data-ttu-id="95e40-152">指定したバージョンの PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="95e40-152">Starts the specified version of PowerShell.</span></span> <span data-ttu-id="95e40-153">指定するバージョンがシステムにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="95e40-153">The version that you specify must be installed on the system.</span></span> <span data-ttu-id="95e40-154">PowerShell 3.0 がコンピューターにインストールされている場合、有効な値は "2.0" と "3.0" です。</span><span class="sxs-lookup"><span data-stu-id="95e40-154">If PowerShell 3.0 is installed on the computer, valid values are "2.0" and "3.0".</span></span> <span data-ttu-id="95e40-155">既定値は "3.0" です。</span><span class="sxs-lookup"><span data-stu-id="95e40-155">The default value is "3.0".</span></span>

<span data-ttu-id="95e40-156">PowerShell 3.0 がインストールされていない場合、有効な値は "2.0" のみです。</span><span class="sxs-lookup"><span data-stu-id="95e40-156">If PowerShell 3.0 isn't installed, the only valid value is "2.0".</span></span> <span data-ttu-id="95e40-157">他の値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="95e40-157">Other values are ignored.</span></span>

<span data-ttu-id="95e40-158">詳しくは、「[Windows PowerShell のインストール](../../setup/installing-windows-powershell.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="95e40-158">For more information, see [Installing Windows PowerShell](../../setup/installing-windows-powershell.md).</span></span>

### <a name="-windowstyle-window-style"></a><span data-ttu-id="95e40-159">-WindowStyle <Window style></span><span class="sxs-lookup"><span data-stu-id="95e40-159">-WindowStyle <Window style></span></span>

<span data-ttu-id="95e40-160">セッションのウィンドウ スタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="95e40-160">Sets the window style for the session.</span></span> <span data-ttu-id="95e40-161">使用できる値は、Normal、Minimized、Maximized、および Hidden です。</span><span class="sxs-lookup"><span data-stu-id="95e40-161">Valid values are Normal, Minimized, Maximized, and Hidden.</span></span>

### <a name="-command"></a><span data-ttu-id="95e40-162">-Command</span><span class="sxs-lookup"><span data-stu-id="95e40-162">-Command</span></span>

<span data-ttu-id="95e40-163">PowerShell のコマンド プロンプトに入力された場合と同様に、指定されたコマンド (任意のパラメーターを付与する) を実行します。</span><span class="sxs-lookup"><span data-stu-id="95e40-163">Executes the specified commands (with any parameters) as though they were typed at the PowerShell command prompt.</span></span>
<span data-ttu-id="95e40-164">実行後、PowerShell を終了しない限り、 **NoExit**パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="95e40-164">After execution, PowerShell exits unless the **NoExit** parameter is specified.</span></span>
<span data-ttu-id="95e40-165">`-Command` の後にある任意のテキストは、単一のコマンド ラインとして PowerShell に送信されます。</span><span class="sxs-lookup"><span data-stu-id="95e40-165">Any text after `-Command` is sent as a single command line to PowerShell.</span></span>
<span data-ttu-id="95e40-166">これは、`-File` がスクリプトに送信されたパラメーターを処理する方法とは異なります。</span><span class="sxs-lookup"><span data-stu-id="95e40-166">This is different from how `-File` handles parameters sent to a script.</span></span>

<span data-ttu-id="95e40-167">値`-Command`は、"-"、文字列、またはスクリプト ブロック。</span><span class="sxs-lookup"><span data-stu-id="95e40-167">The value of `-Command` can be "-", a string, or a script block.</span></span>
<span data-ttu-id="95e40-168">コマンドの結果は、XML の逆シリアル化されたオブジェクト、いないライブ オブジェクトとして親シェルに返されます。</span><span class="sxs-lookup"><span data-stu-id="95e40-168">The results of the command are returned to the parent shell as deserialized XML objects, not live objects.</span></span>

<span data-ttu-id="95e40-169">場合の値`-Command`が"-"、コマンド テキストが標準の入力から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="95e40-169">If the value of `-Command` is "-", the command text is read from standard input.</span></span>

<span data-ttu-id="95e40-170">ときの値`-Command`文字列**コマンド**_する必要があります_最後のコマンドは、コマンド引数として解釈されます後に任意の文字が入力されたため、指定されたパラメーターします。</span><span class="sxs-lookup"><span data-stu-id="95e40-170">When the value of `-Command` is a string, **Command** _must_ be the last parameter specified because any characters typed after the command are interpreted as the command arguments.</span></span>

<span data-ttu-id="95e40-171">**コマンド**パラメーターに渡される値を認識できる場合にのみ実行するためのスクリプト ブロックを受け入れる`-Command`ScriptBlock 型として。</span><span class="sxs-lookup"><span data-stu-id="95e40-171">The **Command** parameter only accepts a script block for execution when it can recognize the value passed to `-Command` as a ScriptBlock type.</span></span>
<span data-ttu-id="95e40-172">これは_のみ_PowerShell.exe を PowerShell の別のホストから実行するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="95e40-172">This is _only_ possible when running PowerShell.exe from another PowerShell host.</span></span>
<span data-ttu-id="95e40-173">既存の変数、式から返されたまたは、PowerShell によって解析された型を含めることがスクリプト ブロックを中かっこで囲まれたリテラルのスクリプト ブロックとしてホスト`{}`PowerShell.exe へ渡される前に、します。</span><span class="sxs-lookup"><span data-stu-id="95e40-173">The ScriptBlock type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces `{}`, before being passed to PowerShell.exe.</span></span>

<span data-ttu-id="95e40-174">Cmd.exe ではありませんようなものとしてスクリプト ブロック (またはスクリプト ブロックの型) ために渡される値**コマンド**は_常に_文字列であります。</span><span class="sxs-lookup"><span data-stu-id="95e40-174">In cmd.exe, there is no such thing as a script block (or ScriptBlock type), so the value passed to **Command** will _always_ be a string.</span></span>
<span data-ttu-id="95e40-175">文字列の中のスクリプト ブロックを記述することができますが、実行されているのではなくの動作は正確に、一般的な PowerShell プロンプトで入力したかのように元に戻すをブロック スクリプトの内容を印刷します。</span><span class="sxs-lookup"><span data-stu-id="95e40-175">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="95e40-176">渡される文字列`-Command`のでスクリプト ブロックの中かっこは多くの場合、最初に cmd.exe から実行する場合でも、PowerShell としてに実行されます。</span><span class="sxs-lookup"><span data-stu-id="95e40-176">A string passed to `-Command` will still be executed as PowerShell, so the script block curly braces are often not required in the first place when running from cmd.exe.</span></span>
<span data-ttu-id="95e40-177">文字列内で定義されているインライン スクリプト ブロックを実行する、[呼び出し演算子](/powershell/module/microsoft.powershell.core/about/about_operators#call-operator-)`&`ことができます。</span><span class="sxs-lookup"><span data-stu-id="95e40-177">To execute an inline script block defined inside a string, the [call operator](/powershell/module/microsoft.powershell.core/about/about_operators#call-operator-) `&` can be used:</span></span>

```console
"& {<command>}"
```

### <a name="-help---"></a><span data-ttu-id="95e40-178">-Help、-?、/?</span><span class="sxs-lookup"><span data-stu-id="95e40-178">-Help, -?, /?</span></span>

<span data-ttu-id="95e40-179">Powershell.exe の構文を示します。</span><span class="sxs-lookup"><span data-stu-id="95e40-179">Shows the syntax of powershell.exe.</span></span> <span data-ttu-id="95e40-180">PowerShell で PowerShell.exe のコマンドを入力している場合、コマンド パラメーターの前にスラッシュ (/) ではなくハイフン (-) を入力してください。</span><span class="sxs-lookup"><span data-stu-id="95e40-180">If you are typing a PowerShell.exe command in PowerShell, prepend the command parameters with a hyphen (-), not a forward slash (/).</span></span> <span data-ttu-id="95e40-181">Cmd.exe では、ハイフンとスラッシュのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="95e40-181">You can use either a hyphen or forward slash in Cmd.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="95e40-182">トラブルシューティング上の注意: PowerShell 2.0 では、一部のプログラムを Windows PowerShell コンソールで開始すると、LastExitCode 0xc0000142 で失敗します。</span><span class="sxs-lookup"><span data-stu-id="95e40-182">Troubleshooting Note: In PowerShell 2.0, starting some programs in the Windows PowerShell console fails with a LastExitCode of 0xc0000142.</span></span>

## <a name="examples"></a><span data-ttu-id="95e40-183">例</span><span class="sxs-lookup"><span data-stu-id="95e40-183">EXAMPLES</span></span>

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
