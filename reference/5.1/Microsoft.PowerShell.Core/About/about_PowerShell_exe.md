---
description: コマンドラインインターフェイスの使用方法について説明 `powershell.exe` します。 コマンドラインパラメーターを表示し、構文について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 10/05/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_exe
ms.openlocfilehash: ef03558a6b58868b98c9da488934b0bfbbce9fe7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223331"
---
# <a name="about-powershellexe"></a><span data-ttu-id="04b0a-105">PowerShell.exe について</span><span class="sxs-lookup"><span data-stu-id="04b0a-105">About PowerShell.exe</span></span>

## <a name="short-description"></a><span data-ttu-id="04b0a-106">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="04b0a-106">Short Description</span></span>
<span data-ttu-id="04b0a-107">コマンドラインインターフェイスの使用方法について説明 `powershell.exe` します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-107">Explains how to use the `powershell.exe` command-line interface.</span></span> <span data-ttu-id="04b0a-108">コマンドラインパラメーターを表示し、構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-108">Displays the command-line parameters and describes the syntax.</span></span>

## <a name="long-description"></a><span data-ttu-id="04b0a-109">長い説明</span><span class="sxs-lookup"><span data-stu-id="04b0a-109">Long Description</span></span>

### <a name="syntax"></a><span data-ttu-id="04b0a-110">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="04b0a-110">SYNTAX</span></span>

```
PowerShell[.exe]
    [-PSConsoleFile <file> | -Version <version>]
    [-NoLogo]
    [-NoExit]
    [-Sta]
    [-Mta]
    [-NoProfile]
    [-NonInteractive]
    [-InputFormat {Text | XML}]
    [-OutputFormat {Text | XML}]
    [-WindowStyle <style>]
    [-EncodedCommand <Base64EncodedCommand>]
    [-ConfigurationName <string>]
    [-File - | <filePath> <args>]
    [-ExecutionPolicy <ExecutionPolicy>]
    [-Command - | { <script-block> [-args <arg-array>] }
                | { <string> [<CommandParameters>] } ]

PowerShell[.exe] -Help | -? | /?
```

### <a name="parameters"></a><span data-ttu-id="04b0a-111">パラメーター</span><span class="sxs-lookup"><span data-stu-id="04b0a-111">Parameters</span></span>

#### <a name="-psconsolefile-filepath"></a><span data-ttu-id="04b0a-112">-PSConsoleFile \<FilePath\></span><span class="sxs-lookup"><span data-stu-id="04b0a-112">-PSConsoleFile \<FilePath\></span></span>

<span data-ttu-id="04b0a-113">指定された PowerShell コンソール ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-113">Loads the specified PowerShell console file.</span></span> <span data-ttu-id="04b0a-114">コンソール ファイルの名前とパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-114">Enter the path and name of the console file.</span></span> <span data-ttu-id="04b0a-115">コンソール ファイルを作成するには、PowerShell で Export-Console コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-115">To create a console file, use the Export-Console cmdlet in PowerShell.</span></span>

#### <a name="-version-powershell-version"></a><span data-ttu-id="04b0a-116">-Version \<PowerShell Version\></span><span class="sxs-lookup"><span data-stu-id="04b0a-116">-Version \<PowerShell Version\></span></span>

<span data-ttu-id="04b0a-117">指定したバージョンの PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-117">Starts the specified version of PowerShell.</span></span> <span data-ttu-id="04b0a-118">有効な値は2.0 および3.0 です。</span><span class="sxs-lookup"><span data-stu-id="04b0a-118">Valid values are 2.0 and 3.0.</span></span> <span data-ttu-id="04b0a-119">指定するバージョンがシステムにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="04b0a-119">The version that you specify must be installed on the system.</span></span> <span data-ttu-id="04b0a-120">コンピューターに Windows PowerShell 3.0 がインストールされている場合は、"3.0" が既定のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="04b0a-120">If Windows PowerShell 3.0 is installed on the computer, "3.0" is the default version.</span></span>
<span data-ttu-id="04b0a-121">それ以外の場合は、"2.0" が既定のバージョンになります。</span><span class="sxs-lookup"><span data-stu-id="04b0a-121">Otherwise, "2.0" is the default version.</span></span> <span data-ttu-id="04b0a-122">詳細については、「 [PowerShell のインストール](/powershell/scripting/install/installing-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04b0a-122">For more information, see [Installing PowerShell](/powershell/scripting/install/installing-windows-powershell).</span></span>

#### <a name="-nologo"></a><span data-ttu-id="04b0a-123">-NoLogo</span><span class="sxs-lookup"><span data-stu-id="04b0a-123">-NoLogo</span></span>

<span data-ttu-id="04b0a-124">スタートアップ時に著作権の見出しを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="04b0a-124">Hides the copyright banner at startup.</span></span>

#### <a name="-noexit"></a><span data-ttu-id="04b0a-125">-NoExit</span><span class="sxs-lookup"><span data-stu-id="04b0a-125">-NoExit</span></span>

<span data-ttu-id="04b0a-126">スタートアップ コマンドを実行後、終了しません。</span><span class="sxs-lookup"><span data-stu-id="04b0a-126">Does not exit after running startup commands.</span></span>

#### <a name="-sta"></a><span data-ttu-id="04b0a-127">-Sta</span><span class="sxs-lookup"><span data-stu-id="04b0a-127">-Sta</span></span>

<span data-ttu-id="04b0a-128">シングルスレッド アパートメントを使用して、PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-128">Starts PowerShell using a single-threaded apartment.</span></span> <span data-ttu-id="04b0a-129">Windows PowerShell 2.0 では、マルチスレッド アパートメント (MTA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="04b0a-129">In Windows PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span> <span data-ttu-id="04b0a-130">Windows PowerShell 3.0 では、シングルスレッド アパートメント (STA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="04b0a-130">In Windows PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span>

#### <a name="-mta"></a><span data-ttu-id="04b0a-131">-Mta</span><span class="sxs-lookup"><span data-stu-id="04b0a-131">-Mta</span></span>

<span data-ttu-id="04b0a-132">マルチスレッド アパートメントを使用して、PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-132">Starts PowerShell using a multi-threaded apartment.</span></span> <span data-ttu-id="04b0a-133">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="04b0a-133">This parameter is introduced in PowerShell 3.0.</span></span> <span data-ttu-id="04b0a-134">PowerShell 2.0 では、マルチスレッド アパートメント (MTA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="04b0a-134">In PowerShell 2.0, multi-threaded apartment (MTA) is the default.</span></span> <span data-ttu-id="04b0a-135">PowerShell 3.0 では、シングルスレッド アパートメント (STA) が既定値です。</span><span class="sxs-lookup"><span data-stu-id="04b0a-135">In PowerShell 3.0, single-threaded apartment (STA) is the default.</span></span>

#### <a name="-noprofile"></a><span data-ttu-id="04b0a-136">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="04b0a-136">-NoProfile</span></span>

<span data-ttu-id="04b0a-137">PowerShell プロファイルを読み込みません。</span><span class="sxs-lookup"><span data-stu-id="04b0a-137">Does not load the PowerShell profile.</span></span>

#### <a name="-noninteractive"></a><span data-ttu-id="04b0a-138">-NonInteractive</span><span class="sxs-lookup"><span data-stu-id="04b0a-138">-NonInteractive</span></span>

<span data-ttu-id="04b0a-139">ユーザーに対話的なプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="04b0a-139">Does not present an interactive prompt to the user.</span></span>

#### <a name="-inputformat-text--xml"></a><span data-ttu-id="04b0a-140">-InputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="04b0a-140">-InputFormat {Text | XML}</span></span>

<span data-ttu-id="04b0a-141">PowerShell に送信されるデータの形式を記述します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-141">Describes the format of data sent to PowerShell.</span></span> <span data-ttu-id="04b0a-142">使用できる値は、"Text" (テキスト文字列) と "XML" (シリアル化された CLIXML 形式) です。</span><span class="sxs-lookup"><span data-stu-id="04b0a-142">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

#### <a name="-outputformat-text--xml"></a><span data-ttu-id="04b0a-143">-OutputFormat {Text | XML}</span><span class="sxs-lookup"><span data-stu-id="04b0a-143">-OutputFormat {Text | XML}</span></span>

<span data-ttu-id="04b0a-144">PowerShell からの出力の形式を決定します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-144">Determines how output from PowerShell is formatted.</span></span> <span data-ttu-id="04b0a-145">使用できる値は、"Text" (テキスト文字列) と "XML" (シリアル化された CLIXML 形式) です。</span><span class="sxs-lookup"><span data-stu-id="04b0a-145">Valid values are "Text" (text strings) or "XML" (serialized CLIXML format).</span></span>

#### <a name="-windowstyle-window-style"></a><span data-ttu-id="04b0a-146">-WindowStyle \<Window style\></span><span class="sxs-lookup"><span data-stu-id="04b0a-146">-WindowStyle \<Window style\></span></span>

<span data-ttu-id="04b0a-147">セッションのウィンドウ スタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-147">Sets the window style for the session.</span></span> <span data-ttu-id="04b0a-148">使用できる値は、Normal、Minimized、Maximized、Hidden です。</span><span class="sxs-lookup"><span data-stu-id="04b0a-148">Valid values are Normal, Minimized, Maximized and Hidden.</span></span>

#### <a name="-encodedcommand-base64encodedcommand"></a><span data-ttu-id="04b0a-149">-EncodedCommand \<Base64EncodedCommand\></span><span class="sxs-lookup"><span data-stu-id="04b0a-149">-EncodedCommand \<Base64EncodedCommand\></span></span>

<span data-ttu-id="04b0a-150">Base 64 エンコード文字列版のコマンドを許可します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-150">Accepts a base-64-encoded string version of a command.</span></span> <span data-ttu-id="04b0a-151">複雑な引用符や中かっこを必要とするコマンドを PowerShell に渡す場合にこのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-151">Use this parameter to submit commands to PowerShell that require complex quotation marks or curly braces.</span></span> <span data-ttu-id="04b0a-152">文字列は、16LE 文字エンコーディングを使用して書式設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04b0a-152">The string must be formatted using UTF-16LE character encoding.</span></span>

#### <a name="-configurationname-string"></a><span data-ttu-id="04b0a-153">-ConfigurationName \<string\></span><span class="sxs-lookup"><span data-stu-id="04b0a-153">-ConfigurationName \<string\></span></span>

<span data-ttu-id="04b0a-154">PowerShell を実行する構成エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-154">Specifies a configuration endpoint in which PowerShell is run.</span></span> <span data-ttu-id="04b0a-155">これには、ローカルコンピューターに登録されている任意のエンドポイントを指定できます。これには、既定の PowerShell リモート処理エンドポイントや、特定のユーザーロール機能を持つカスタムエンドポイントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-155">This can be any endpoint registered on the local machine including the default PowerShell remoting endpoints or a custom endpoint having specific user role capabilities.</span></span>

#### <a name="-file----filepath-args"></a><span data-ttu-id="04b0a-156">-File-|\<filePath\>\<args\></span><span class="sxs-lookup"><span data-stu-id="04b0a-156">-File - | \<filePath\> \<args\></span></span>

<span data-ttu-id="04b0a-157">**File** の値が "-" の場合、コマンドテキストは標準入力から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-157">If the value of **File** is "-", the command text is read from standard input.</span></span>
<span data-ttu-id="04b0a-158">`powershell -File -`リダイレクトされた標準入力なしで実行すると、通常のセッションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-158">Running `powershell -File -` without redirected standard input starts a regular session.</span></span> <span data-ttu-id="04b0a-159">これは、 **File** パラメーターを指定しない場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="04b0a-159">This is the same as not specifying the **File** parameter at all.</span></span>

<span data-ttu-id="04b0a-160">**ファイル** の値がファイルパスの場合、スクリプトはローカルスコープ ("ドットソース") で実行されるので、スクリプトによって作成される関数と変数を現在のセッションで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="04b0a-160">If the value of **File** is a file path, the script runs in the local scope ("dot-sourced"), so that the functions and variables that the script creates are available in the current session.</span></span> <span data-ttu-id="04b0a-161">スクリプト ファイルのパスと (存在する場合) パラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-161">Enter the script file path and any parameters.</span></span> <span data-ttu-id="04b0a-162">**File** は、コマンド内の最後のパラメーターにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04b0a-162">**File** must be the last parameter in the command.</span></span> <span data-ttu-id="04b0a-163">**File** パラメーターの後に入力されるすべての値は、スクリプトファイルのパスと、そのスクリプトに渡されるパラメーターとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-163">All values typed after the **File** parameter are interpreted as the script file path and parameters passed to that script.</span></span>

<span data-ttu-id="04b0a-164">スクリプトに渡されるパラメーターは、(現在のシェルによる解釈の後で) リテラル文字列として渡されます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-164">Parameters passed to the script are passed as literal strings, after interpretation by the current shell.</span></span> <span data-ttu-id="04b0a-165">たとえば、 **cmd.exe** で環境変数の値を渡す必要がある場合は、 **cmd.exe** 構文を使用します。 `powershell.exe -File .\test.ps1 -TestParam %windir%`</span><span class="sxs-lookup"><span data-stu-id="04b0a-165">For example, if you are in **cmd.exe** and want to pass an environment variable value, you would use the **cmd.exe** syntax: `powershell.exe -File .\test.ps1 -TestParam %windir%`</span></span>

<span data-ttu-id="04b0a-166">これに対し、 `powershell.exe -File .\test.ps1 -TestParam $env:windir` **cmd.exe** で実行すると、 `$env:windir` 現在の **cmd.exe** シェルに特別な意味を持たないため、スクリプトがリテラル文字列を受け取ることになります。</span><span class="sxs-lookup"><span data-stu-id="04b0a-166">In contrast, running `powershell.exe -File .\test.ps1 -TestParam $env:windir` in **cmd.exe** results in the script receiving the literal string `$env:windir` because it has no special meaning to the current **cmd.exe** shell.</span></span> <span data-ttu-id="04b0a-167">`$env:windir`環境変数参照のスタイルは、PowerShell コードとして解釈されるため、 **コマンド** パラメーター内で使用 _でき_ ます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-167">The `$env:windir` style of environment variable reference _can_ be used inside a **Command** parameter, since there it will be interpreted as PowerShell code.</span></span>

<span data-ttu-id="04b0a-168">同様に、 **バッチスクリプト** から同じコマンドを実行する場合 `%~dp0` は、またはの代わりにを使用し `.\` `$PSScriptRoot` て、現在の実行ディレクトリを表し `powershell.exe -File %~dp0test.ps1 -TestParam %windir%` ます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-168">Similarly, if you want to execute the same command from a **Batch script** , you would use `%~dp0` instead of `.\` or `$PSScriptRoot` to represent the current execution directory: `powershell.exe -File %~dp0test.ps1 -TestParam %windir%`.</span></span>
<span data-ttu-id="04b0a-169">代わりにを使用すると `.\test.ps1` 、PowerShell はリテラルパスを見つけることができないため、エラーをスローします。 `.\test.ps1`</span><span class="sxs-lookup"><span data-stu-id="04b0a-169">If you instead used `.\test.ps1`, PowerShell would throw an error because it cannot find the literal path `.\test.ps1`</span></span>

<span data-ttu-id="04b0a-170">ファイルの値がファイルパスの場合、 **file パラメーター名** の後に入力された文字はスクリプトファイルのパスとして解釈され、その後にスクリプトパラメーターが続くため、 **ファイル\*\*\*\*はコマンド** の最後のパラメーターである _必要があり_ ます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-170">When the value of **File** is a file path, **File** _must_ be the last parameter in the command because any characters typed after the **File** parameter name are interpreted as the script file path followed by the script parameters.</span></span>

<span data-ttu-id="04b0a-171">**ファイル** パラメーターの値には、スクリプトのパラメーターと値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-171">You can include the script parameters and values in the value of the **File** parameter.</span></span> <span data-ttu-id="04b0a-172">例: `-File .\Get-Script.ps1 -Domain Central`</span><span class="sxs-lookup"><span data-stu-id="04b0a-172">For example: `-File .\Get-Script.ps1 -Domain Central`</span></span>

<span data-ttu-id="04b0a-173">通常、スクリプトのスイッチ パラメーターは、含めるか省略するかのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="04b0a-173">Typically, the switch parameters of a script are either included or omitted.</span></span>
<span data-ttu-id="04b0a-174">たとえば、次のコマンドは、スクリプトファイルの **All** パラメーターを使用し `Get-Script.ps1` ます。 `-File .\Get-Script.ps1 -All`</span><span class="sxs-lookup"><span data-stu-id="04b0a-174">For example, the following command uses the **All** parameter of the `Get-Script.ps1` script file: `-File .\Get-Script.ps1 -All`</span></span>

<span data-ttu-id="04b0a-175">まれに、パラメーターの **ブール** 値の指定が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="04b0a-175">In rare cases, you might need to provide a **Boolean** value for a parameter.</span></span>
<span data-ttu-id="04b0a-176">この方法でスクリプトを実行するときに、スイッチパラメーターに明示的なブール値を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="04b0a-176">It is not possible to pass an explicit boolean value for a switch parameter when running a script in this way.</span></span> <span data-ttu-id="04b0a-177">この制限は、PowerShell 6 () で削除されました `pwsh.exe` 。</span><span class="sxs-lookup"><span data-stu-id="04b0a-177">This limitation was removed in PowerShell 6 (`pwsh.exe`).</span></span>

#### <a name="-executionpolicy-executionpolicy"></a><span data-ttu-id="04b0a-178">-ExecutionPolicy \<ExecutionPolicy\></span><span class="sxs-lookup"><span data-stu-id="04b0a-178">-ExecutionPolicy \<ExecutionPolicy\></span></span>

<span data-ttu-id="04b0a-179">現在のセッションの既定の実行ポリシーを設定し、環境変数に保存し `$env:PSExecutionPolicyPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-179">Sets the default execution policy for the current session and saves it in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="04b0a-180">このパラメーターを指定しても、レジストリで設定された PowerShell の実行ポリシーが変更されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="04b0a-180">This parameter does not change the PowerShell execution policy that is set in the registry.</span></span> <span data-ttu-id="04b0a-181">有効な値の一覧など、PowerShell 実行ポリシーについては、「[about_Execution_Policies](about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04b0a-181">For information about PowerShell execution policies, including a list of valid values, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

#### <a name="-command"></a><span data-ttu-id="04b0a-182">-Command</span><span class="sxs-lookup"><span data-stu-id="04b0a-182">-Command</span></span>

<span data-ttu-id="04b0a-183">指定されたコマンド (および任意のパラメーター) を PowerShell コマンドプロンプトで入力した場合と同じように実行し `NoExit` ます。パラメーターが指定されていない場合は、を終了します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-183">Executes the specified commands (and any parameters) as though they were typed at the PowerShell command prompt, and then exits, unless the `NoExit` parameter is specified.</span></span>

<span data-ttu-id="04b0a-184">**Command** の値には `-` 、、スクリプトブロック、または文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-184">The value of **Command** can be `-`, a script block, or a string.</span></span> <span data-ttu-id="04b0a-185">**Command** の値がの場合 `-` 、コマンドテキストは標準入力から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-185">If the value of **Command** is `-`, the command text is read from standard input.</span></span>

<span data-ttu-id="04b0a-186">**コマンド** パラメーターでは、 **コマンド** に **ScriptBlock** 型として渡された値を認識できる場合に限り、スクリプトブロックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-186">The **Command** parameter only accepts a script block for execution when it can recognize the value passed to **Command** as a **ScriptBlock** type.</span></span> <span data-ttu-id="04b0a-187">これは _only_ `powershell.exe` 、別の PowerShell ホストから実行する場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="04b0a-187">This is _only_ possible when running `powershell.exe` from another PowerShell host.</span></span> <span data-ttu-id="04b0a-188">**ScriptBlock** 型は、に渡される前に、既存の変数に格納されるか、式から返されるか、または PowerShell ホストによって、中かっこ () で囲まれたリテラルスクリプトブロックとして解析されることがあり `{}` `powershell.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-188">The **ScriptBlock** type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces (`{}`), before being passed to `powershell.exe`.</span></span>

```powershell
powershell -Command {Get-WinEvent -LogName security}
```

<span data-ttu-id="04b0a-189">で `cmd.exe` は、スクリプトブロック (または **ScriptBlock** 型) のようなものは存在しないため、 **コマンド** に渡される値は _常に_ 文字列になります。</span><span class="sxs-lookup"><span data-stu-id="04b0a-189">In `cmd.exe`, there is no such thing as a script block (or **ScriptBlock** type), so the value passed to **Command** will _always_ be a string.</span></span> <span data-ttu-id="04b0a-190">文字列の中にスクリプト ブロックを記述することはできますが、実行されるのではなく、通常の PowerShell プロンプトで入力した場合とまったく同じように動作し、スクリプト ブロックの内容が出力されます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-190">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="04b0a-191">**コマンド** に渡された文字列は PowerShell コードとして実行されます。そのため、からの実行時には、スクリプトブロックの中かっこを最初に記述する必要はありません `cmd.exe` 。</span><span class="sxs-lookup"><span data-stu-id="04b0a-191">A string passed to **Command** is still executed as PowerShell code, so the script block curly braces are often not required in the first place when running from `cmd.exe`.</span></span> <span data-ttu-id="04b0a-192">文字列内で定義されているインライン スクリプト ブロックを実行するには、次の[呼び出し演算子](about_operators.md#special-operators) `&` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-192">To execute an inline script block defined inside a string, the [call operator](about_operators.md#special-operators) `&` can be used:</span></span>

```cmd
pwsh -Command "& {Get-WinEvent -LogName security}"
```

<span data-ttu-id="04b0a-193">**Command** の値が文字列の場合、 **command** は pwsh の最後のパラメーターである必要があります。これは、後続のすべての引数が、実行するコマンドの一部として解釈されるためです。</span><span class="sxs-lookup"><span data-stu-id="04b0a-193">If the value of **Command** is a string, **Command** must be the last parameter for pwsh, because all arguments following it are interpreted as part of the command to execute.</span></span>

<span data-ttu-id="04b0a-194">既存の PowerShell セッション内から呼び出された場合、結果は、ライブオブジェクトではなく、逆シリアル化された XML オブジェクトとして親シェルに返されます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-194">When called from within an existing PowerShell session, the results are returned to the parent shell as deserialized XML objects, not live objects.</span></span> <span data-ttu-id="04b0a-195">他のシェルの場合、結果は文字列として返されます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-195">For other shells, the results are returned as strings.</span></span>

<span data-ttu-id="04b0a-196">**Command** の値がの場合 `-` 、コマンドテキストは標準入力から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-196">If the value of **Command** is `-`, the command text is read from standard input.</span></span> <span data-ttu-id="04b0a-197">標準入力で **Command** パラメーターを使用する場合は、標準入力をリダイレクトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04b0a-197">You must redirect standard input when using the **Command** parameter with standard input.</span></span> <span data-ttu-id="04b0a-198">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-198">For example:</span></span>

```powershell
@'
"in"

"hi" |
  % { "$_ there" }

"out"
'@ | powershell -NoProfile -Command -
```

<span data-ttu-id="04b0a-199">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-199">This example produces the following output:</span></span>

```Output
in
hi there
out
```

<span data-ttu-id="04b0a-200">プロセス終了コードは、スクリプトブロック内の最後の (実行された) コマンドの状態によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-200">The process exit code is determined by status of the last (executed) command within the script block.</span></span> <span data-ttu-id="04b0a-201">がの場合、 `0` `$?` または `$true` `1` `$?` がの場合 `$false` 、終了コードはです。</span><span class="sxs-lookup"><span data-stu-id="04b0a-201">The exit code is `0` when `$?` is `$true` or `1` when `$?` is `$false`.</span></span> <span data-ttu-id="04b0a-202">最後のコマンドが、または以外の終了コードを明示的に設定する外部プログラムまたは PowerShell スクリプトの場合 `0` `1` 、終了コードは `1` プロセス終了コード用にに変換されます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-202">If the last command is an external program or a PowerShell script that explicitly sets an exit code other than `0` or `1`, that exit code is converted to `1` for process exit code.</span></span> <span data-ttu-id="04b0a-203">特定の終了コードを保持するに `exit $LASTEXITCODE` は、をコマンド文字列またはスクリプトブロックに追加します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-203">To preserve the specific exit code, add `exit $LASTEXITCODE` to your command string or script block.</span></span>

<span data-ttu-id="04b0a-204">同様に、やなどのスクリプト終了 (実行空間終了) エラーが発生したとき、または `throw` `-ErrorAction Stop` <kbd>Ctrl C キーを押し</kbd>て実行が中断されたときに、値1が返され - <kbd>C</kbd>ます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-204">Similarly, the value 1 is returned when a script-terminating (runspace-terminating) error, such as a `throw` or `-ErrorAction Stop`, occurs or when execution is interrupted with <kbd>Ctrl</kbd>-<kbd>C</kbd>.</span></span>

<span data-ttu-id="04b0a-205">別の PowerShell ホストから **PowerShell.exe** を実行する場合に _のみ_ 可能です。</span><span class="sxs-lookup"><span data-stu-id="04b0a-205">_only_ possible when running **PowerShell.exe** from another PowerShell host.</span></span>
<span data-ttu-id="04b0a-206">**ScriptBlock** 型は、 `{}` **PowerShell.exe** に渡される前に、既存の変数に格納されているか、式から返されるか、または PowerShell ホストによって中かっこで囲まれたリテラルスクリプトブロックとして解析されることがあります。</span><span class="sxs-lookup"><span data-stu-id="04b0a-206">The **ScriptBlock** type may be contained in an existing variable, returned from an expression, or parsed by the PowerShell host as a literal script block enclosed in curly braces `{}`, before being passed to **PowerShell.exe**.</span></span>

<span data-ttu-id="04b0a-207">**cmd.exe** では、スクリプトブロック (または **ScriptBlock** 型) のようなものは存在しないため、 **コマンド** に渡される値は _常に_ 文字列になります。</span><span class="sxs-lookup"><span data-stu-id="04b0a-207">In **cmd.exe** , there is no such thing as a script block (or **ScriptBlock** type), so the value passed to **Command** will _always_ be a string.</span></span> <span data-ttu-id="04b0a-208">文字列の中にスクリプト ブロックを記述することはできますが、実行されるのではなく、通常の PowerShell プロンプトで入力した場合とまったく同じように動作し、スクリプト ブロックの内容が出力されます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-208">You can write a script block inside the string, but instead of being executed it will behave exactly as though you typed it at a typical PowerShell prompt, printing the contents of the script block back out to you.</span></span>

<span data-ttu-id="04b0a-209">**コマンド** に渡された文字列は PowerShell として実行されます。そのため、 **cmd.exe** から実行した場合、最初の場所では、スクリプトブロック中かっこが不要になることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="04b0a-209">A string passed to **Command** will still be executed as PowerShell, so the script block curly braces are often not required in the first place when running from **cmd.exe**.</span></span> <span data-ttu-id="04b0a-210">文字列内に定義されているインラインスクリプトブロックを実行するには、[呼び出し演算子](about_operators.md#special-operators)を 
 `&` 使用できます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-210">To execute an inline script block defined inside a string, the [call operator](about_operators.md#special-operators)
`&` can be used:</span></span>

```console
"& {<command>}"
```

#### <a name="-help---"></a><span data-ttu-id="04b0a-211">-Help、-?、/?</span><span class="sxs-lookup"><span data-stu-id="04b0a-211">-Help, -?, /?</span></span>

<span data-ttu-id="04b0a-212">**PowerShell.exe** のヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-212">Displays help for **PowerShell.exe**.</span></span> <span data-ttu-id="04b0a-213">PowerShell セッションで **PowerShell.exe** コマンドを入力する場合は、コマンドパラメーターにスラッシュ (/) ではなくハイフン (-) を付加します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-213">If you are typing a **PowerShell.exe** command in a PowerShell session, prepend the command parameters with a hyphen (-), not a forward slash (/).</span></span> <span data-ttu-id="04b0a-214">**cmd.exe** では、ハイフンとスラッシュのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="04b0a-214">You can use either a hyphen or forward slash in **cmd.exe**.</span></span>

### <a name="remarks"></a><span data-ttu-id="04b0a-215">REMARKS</span><span class="sxs-lookup"><span data-stu-id="04b0a-215">REMARKS</span></span>

<span data-ttu-id="04b0a-216">トラブルシューティング上の注意: PowerShell 2.0 では、PowerShell コンソールから一部のプログラムを開始すると、 **LastExitCode** 0xc0000142 で失敗します。</span><span class="sxs-lookup"><span data-stu-id="04b0a-216">Troubleshooting note: In PowerShell 2.0, starting some programs from the PowerShell console fails with a **LastExitCode** of 0xc0000142.</span></span>

### <a name="examples"></a><span data-ttu-id="04b0a-217">例</span><span class="sxs-lookup"><span data-stu-id="04b0a-217">EXAMPLES</span></span>

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
