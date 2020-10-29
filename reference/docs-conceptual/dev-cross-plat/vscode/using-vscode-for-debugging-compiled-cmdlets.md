---
ms.date: 10/19/2020
keywords: powershell,コマンドレット,デバッグ
title: Visual Studio Code を使用したコンパイル済みコマンドレットのデバッグ
description: .NET Core で PSModule プロジェクトのビルド タスクと起動構成を設定する方法
ms.openlocfilehash: b51a69110c64b386f5c3ccf2527d1e184ef89257
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501645"
---
# <a name="using-visual-studio-code-to-debug-compiled-cmdlets"></a><span data-ttu-id="20d88-104">Visual Studio Code を使用したコンパイル済みコマンドレットのデバッグ</span><span class="sxs-lookup"><span data-stu-id="20d88-104">Using Visual Studio Code to debug compiled cmdlets</span></span>

<span data-ttu-id="20d88-105">このガイドでは、Visual Studio Code (VS Code) と C# 拡張機能を使用して、コンパイル済み PowerShell モジュールの C# ソース コードを対話形式でデバッグする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="20d88-105">This guide shows you how to interactively debug C# source code for a compiled PowerShell module using Visual Studio Code (VS Code) and the C# extension.</span></span>

<span data-ttu-id="20d88-106">Visual Studio Code デバッガーについてのある程度の知識があることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="20d88-106">Some familiarity with the Visual Studio Code debugger is assumed.</span></span>

- <span data-ttu-id="20d88-107">VS Code デバッガーの概要については、[Visual Studio Code でのデバッグ][]に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20d88-107">For a general introduction to the VS Code debugger, see [Debugging in Visual Studio Code][].</span></span>

- <span data-ttu-id="20d88-108">PowerShell のスクリプト ファイルとモジュールのデバッグの例については、「[Visual Studio Code を使用したリモート編集およびデバッグ][]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20d88-108">For examples of debugging PowerShell script files and modules, see [Using Visual Studio Code for remote editing and debugging][].</span></span>

<span data-ttu-id="20d88-109">このガイドでは、[移植可能なモジュールの作成][]に関するガイドに記載されている手順を読んで従っていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="20d88-109">This guide assumes you have read and followed the instructions in the [Writing Portable Modules][] guide.</span></span>

## <a name="creating-a-build-task"></a><span data-ttu-id="20d88-110">ビルド タスクの作成</span><span class="sxs-lookup"><span data-stu-id="20d88-110">Creating a build task</span></span>

<span data-ttu-id="20d88-111">デバッグ セッションを開始する前に、プロジェクトを自動的にビルドします。</span><span class="sxs-lookup"><span data-stu-id="20d88-111">Build your project automatically before launching a debugging session.</span></span> <span data-ttu-id="20d88-112">リビルドすることで、最新バージョンのコードを確実にデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="20d88-112">Rebuilding ensures that you debug the latest version of your code.</span></span>

<span data-ttu-id="20d88-113">ビルド タスクを構成します。</span><span class="sxs-lookup"><span data-stu-id="20d88-113">Configure a build task:</span></span>

1. <span data-ttu-id="20d88-114">**コマンド パレット** で、 **[Configure Default Build Task]\(既定のビルド タスクを構成する\)** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20d88-114">In the **Command Palette** , run the **Configure Default Build Task** command.</span></span>

   ![[Configure Default Build Task]\(既定のビルド タスクを構成する\) を実行する](media/using-vscode-for-debugging-compiled-cmdlets/configure-default-build-task.png)

1. <span data-ttu-id="20d88-116">**[Create tasks.json file from template]\(構成するタスクを選択\)** ダイアログで、 **[テンプレートから tasks.json を生成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="20d88-116">In the **Select a task to configure** dialog, choose **Create tasks.json file from template** .</span></span>

1. <span data-ttu-id="20d88-117">**[Select a Task Template]\(タスク テンプレートを選択\)** ダイアログで、 **[.NET Core]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="20d88-117">In the **Select a Task Template** dialog, choose **.NET Core** .</span></span>

<span data-ttu-id="20d88-118">まだ存在しない場合は、新しい `tasks.json` ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="20d88-118">A new `tasks.json` file is created if one doesn't exist yet.</span></span>

<span data-ttu-id="20d88-119">ビルド タスクをテストするには:</span><span class="sxs-lookup"><span data-stu-id="20d88-119">To test your build task:</span></span>

1. <span data-ttu-id="20d88-120">**コマンド パレット** で、 **[ビルド タスクの実行]** コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20d88-120">In the **Command Palette** , run the **Run Build Task** command.</span></span>

1. <span data-ttu-id="20d88-121">**[Select the build task to run]\(実行するビルド タスクを選択\)** ダイアログで、 **[ビルド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="20d88-121">In the **Select the build task to run** dialog, choose **build** .</span></span>

### <a name="information-about-dll-files-being-locked"></a><span data-ttu-id="20d88-122">ロックされている DLL ファイルに関する情報</span><span class="sxs-lookup"><span data-stu-id="20d88-122">Information about DLL files being locked</span></span>

<span data-ttu-id="20d88-123">既定では、ビルドが成功した場合は、ターミナル ペインに出力は表示されません。</span><span class="sxs-lookup"><span data-stu-id="20d88-123">By default, a successful build doesn't show output in the terminal pane.</span></span> <span data-ttu-id="20d88-124">" **プロジェクトファイルが存在しません** " というテキストが含まれる出力が表示される場合は、`tasks.json` ファイルを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20d88-124">If you see output that contains the text **Project file doesn't exist** , you should edit the `tasks.json` file.</span></span> <span data-ttu-id="20d88-125">C# プロジェクトへの明示的なパスの `"${workspaceFolder}/myModule"` という表記を含めます。</span><span class="sxs-lookup"><span data-stu-id="20d88-125">Include the explicit path to the C# project expressed as `"${workspaceFolder}/myModule"`.</span></span> <span data-ttu-id="20d88-126">この例で、`myModule` はプロジェクト フォルダーの名前です。</span><span class="sxs-lookup"><span data-stu-id="20d88-126">In this example, `myModule` is the name of the project folder.</span></span> <span data-ttu-id="20d88-127">次のように、`args` リストの `build` エントリの後にこのエントリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20d88-127">This entry must go after the `build` entry in the `args` list as follows:</span></span>

```json
    {
        "label": "build",
        "command": "dotnet",
        "type": "shell",
        "args": [
            "build",
            "${workspaceFolder}/myModule",
            // Ask dotnet build to generate full paths for file names.
            "/property:GenerateFullPaths=true",
            // Do not generate summary otherwise it leads to duplicate errors in Problems panel
            "/consoleloggerparameters:NoSummary",
        ],
        "group": "build",
        "presentation": {
            "reveal": "silent"
        },
        "problemMatcher": "$msCompile"
    }
```

<span data-ttu-id="20d88-128">デバッグ時には、モジュールの DLL が VS Code ターミナルの PowerShell セッションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="20d88-128">When debugging, your module DLL is imported into the PowerShell session in the VS Code terminal.</span></span> <span data-ttu-id="20d88-129">DLL はロックされます。</span><span class="sxs-lookup"><span data-stu-id="20d88-129">The DLL becomes locked.</span></span> <span data-ttu-id="20d88-130">ターミナル セッションを閉じずにビルド タスクを実行すると、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20d88-130">The following message is displayed when you run the build task without closing the terminal session:</span></span>

```Output
Could not copy "obj\Debug\netstandard2.0\myModule.dll" to "bin\Debug\netstandard2.0\myModule.dll"`.
```

<span data-ttu-id="20d88-131">リビルドの前に、ターミナル セッションを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="20d88-131">Terminal sessions must be closed before you rebuild.</span></span>

## <a name="setting-up-the-debugger"></a><span data-ttu-id="20d88-132">デバッガーの設定</span><span class="sxs-lookup"><span data-stu-id="20d88-132">Setting up the debugger</span></span>

<span data-ttu-id="20d88-133">PowerShell コマンドレットをデバッグするには、カスタム起動構成を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20d88-133">To debug the PowerShell cmdlet, you need to set up a custom launch configuration.</span></span> <span data-ttu-id="20d88-134">この構成は、次のために使用されます。</span><span class="sxs-lookup"><span data-stu-id="20d88-134">This configuration is used to:</span></span>

- <span data-ttu-id="20d88-135">ソース コードをビルドします</span><span class="sxs-lookup"><span data-stu-id="20d88-135">Build your source code</span></span>
- <span data-ttu-id="20d88-136">モジュールを読み込んで PowerShell を開始します</span><span class="sxs-lookup"><span data-stu-id="20d88-136">Start PowerShell with your module loaded</span></span>
- <span data-ttu-id="20d88-137">ターミナル ペインで PowerShell を開いたままにします</span><span class="sxs-lookup"><span data-stu-id="20d88-137">Leave PowerShell open in the terminal pane</span></span>

<span data-ttu-id="20d88-138">ターミナル セッションでコマンドレットを呼び出すと、ソース コードに設定されているブレークポイントでデバッガーが停止します。</span><span class="sxs-lookup"><span data-stu-id="20d88-138">When you invoke your cmdlet in the terminal session, the debugger stops at any breakpoints set in your source code.</span></span>

### <a name="configuring-launchjson-for-powershell-core"></a><span data-ttu-id="20d88-139">PowerShell Core 用の launch.json の構成</span><span class="sxs-lookup"><span data-stu-id="20d88-139">Configuring launch.json for PowerShell Core</span></span>

1. <span data-ttu-id="20d88-140">[Visual Studio Code 用 C#][] 拡張機能をインストールします</span><span class="sxs-lookup"><span data-stu-id="20d88-140">Install the [C# for Visual Studio Code][] extension</span></span>

1. <span data-ttu-id="20d88-141">[デバッグ] ペインで、デバッグ構成を追加します</span><span class="sxs-lookup"><span data-stu-id="20d88-141">In the Debug pane, add a debug configuration</span></span>

1. <span data-ttu-id="20d88-142">[`Select environment`] ダイアログで、[`.NET Core`] を選択します</span><span class="sxs-lookup"><span data-stu-id="20d88-142">In the `Select environment` dialog, choose `.NET Core`</span></span>

1. <span data-ttu-id="20d88-143">`launch.json` がエディターで開かれます。</span><span class="sxs-lookup"><span data-stu-id="20d88-143">The `launch.json` file is opened in the editor.</span></span> <span data-ttu-id="20d88-144">`configurations` 配列の内側にカーソルを置くと、`configuration` ピッカーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20d88-144">With your cursor inside the `configurations` array, you see the `configuration` picker.</span></span> <span data-ttu-id="20d88-145">このリストが表示されない場合は、 **[構成の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="20d88-145">If you don't see this list, select **Add Configuration** .</span></span>

1. <span data-ttu-id="20d88-146">既定のデバッグ構成を作成するには、 **[Launch .NET Core Console App]\(.NET Core コンソールアプリの起動\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="20d88-146">To create a default debug configuration, select **Launch .NET Core Console App** :</span></span>

   ![.NET Core コンソールアプリの起動](media/using-vscode-for-debugging-compiled-cmdlets/add-configuration-dialog.png)

1. <span data-ttu-id="20d88-148">`name`、`program`、`args`、`console` の各フィールドを次のように編集します。</span><span class="sxs-lookup"><span data-stu-id="20d88-148">Edit the `name`, `program`, `args`, and `console` fields as follows:</span></span>

   ```json
    {
        "name": "PowerShell cmdlets: pwsh",
        "type": "coreclr",
        "request": "launch",
        "preLaunchTask": "build",
        "program": "pwsh",
        "args": [
            "-NoExit",
            "-NoProfile",
            "-Command",
            "Import-Module ${workspaceFolder}/myModule/bin/Debug/netstandard2.0/myModule.dll",
        ],
        "cwd": "${workspaceFolder}",
        "stopAtEntry": false,
        "console": "integratedTerminal"
    }
   ```

<span data-ttu-id="20d88-149">`program` フィールドは、デバッグ対象のコマンドレットを実行できるように `pwsh` を起動するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="20d88-149">The `program` field is used to launch `pwsh` so that the cmdlet being debugged can be run.</span></span> <span data-ttu-id="20d88-150">引数 `-NoExit` を指定すると、モジュールがインポートされても PowerShell セッションはすぐに終了しません。</span><span class="sxs-lookup"><span data-stu-id="20d88-150">The `-NoExit` argument prevents the PowerShell session from exiting as soon as the module is imported.</span></span>
<span data-ttu-id="20d88-151">`Import-Module` 引数のパスは、[移植可能なモジュールの作成][]に関するガイドに従っている場合の既定のビルド出力パスです。</span><span class="sxs-lookup"><span data-stu-id="20d88-151">The path in the `Import-Module` argument is the default build output path when you've followed the [Writing Portable Modules][] guide.</span></span> <span data-ttu-id="20d88-152">モジュール マニフェスト (`.psd1` ファイル) を作成した場合は、代わりにそのパスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20d88-152">If you've created a module manifest (`.psd1` file), you should use the path to that instead.</span></span> <span data-ttu-id="20d88-153">パス区切り記号 `/` は、Windows、Linux、macOS で動作します。</span><span class="sxs-lookup"><span data-stu-id="20d88-153">The `/` path separator works on Windows, Linux, and macOS.</span></span> <span data-ttu-id="20d88-154">デバッグ対象の PowerShell コマンドを実行するには、統合ターミナルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20d88-154">You must use the integrated terminal to run the PowerShell commands you want to debug.</span></span>

> [!NOTE]
> <span data-ttu-id="20d88-155">デバッガーがどのブレークポイントでも停止しない場合は、Visual Studio Code のデバッグ コンソールで次のような行を探します。</span><span class="sxs-lookup"><span data-stu-id="20d88-155">If the debugger doesn't stop at any breakpoints, look in the Visual Studio Code Debug Console for a line that says:</span></span>
>
> ```
> Loaded '/path/to/myModule.dll'. Skipped loading symbols. Module is optimized and the debugger option 'Just My Code' is enabled.
> ```
>
> <span data-ttu-id="20d88-156">これがある場合は、起動構成に `"justMyCode": false` を追加します (`"console": "integratedTerminal"` と同じレベル)。</span><span class="sxs-lookup"><span data-stu-id="20d88-156">If you see this, add `"justMyCode": false` to your launch config (at the same level as `"console": "integratedTerminal"`.</span></span>

### <a name="configuring-launchjson-for-windows-powershell"></a><span data-ttu-id="20d88-157">Windows PowerShell 用の launch.json の構成</span><span class="sxs-lookup"><span data-stu-id="20d88-157">Configuring launch.json for Windows PowerShell</span></span>

<span data-ttu-id="20d88-158">この起動構成は、Windows PowerShell でコマンドレットをテストするために機能します (`powershell.exe`)。</span><span class="sxs-lookup"><span data-stu-id="20d88-158">This launch configuration works for testing your cmdlets in Windows PowerShell (`powershell.exe`).</span></span>
<span data-ttu-id="20d88-159">次のように変更して、2 番目の起動構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="20d88-159">Create a second launch configuration with the following changes:</span></span>

1. <span data-ttu-id="20d88-160">`name` は、`PowerShell cmdlets: powershell` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="20d88-160">`name` should be `PowerShell cmdlets: powershell`</span></span>

1. <span data-ttu-id="20d88-161">`type` は、`clr` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="20d88-161">`type` should be `clr`</span></span>

1. <span data-ttu-id="20d88-162">`program` は、`powershell` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="20d88-162">`program` should be `powershell`</span></span>

   <span data-ttu-id="20d88-163">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="20d88-163">It should look like this:</span></span>

   ```json
    {
        "name": "PowerShell cmdlets: powershell",
        "type": "clr",
        "request": "launch",
        "preLaunchTask": "build",
        "program": "powershell",
        "args": [
            "-NoExit",
            "-NoProfile",
            "-Command",
            "Import-Module ${workspaceFolder}/myModule/bin/Debug/netstandard2.0/myModule.dll",
        ],
        "cwd": "${workspaceFolder}",
        "stopAtEntry": false,
        "console": "integratedTerminal"
    }
   ```

## <a name="launching-a-debugging-session"></a><span data-ttu-id="20d88-164">デバッグ セッションの起動</span><span class="sxs-lookup"><span data-stu-id="20d88-164">Launching a debugging session</span></span>

<span data-ttu-id="20d88-165">これで、デバッグを始める準備がすべて整いました。</span><span class="sxs-lookup"><span data-stu-id="20d88-165">Now everything is ready to begin debugging.</span></span>

- <span data-ttu-id="20d88-166">デバッグするコマンドレットのソース コードにブレークポイントを配置します。</span><span class="sxs-lookup"><span data-stu-id="20d88-166">Place a breakpoint in the source code for the cmdlet you want to debug:</span></span>

  ![ブレークポイントは、余白の赤い点で示されます](media/using-vscode-for-debugging-compiled-cmdlets/set-breakpoint.png)

- <span data-ttu-id="20d88-168">**[デバッグ]** ビューの構成ドロップダウン メニューで、関連する **PowerShell コマンドレット** の構成が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="20d88-168">Ensure that the relevant **PowerShell cmdlets** configuration is selected in the configuration drop-down menu in the **Debug** view:</span></span>

  ![起動構成を選択する](media/using-vscode-for-debugging-compiled-cmdlets/select-launch-configuration.png)

- <span data-ttu-id="20d88-170"><kbd>F5</kbd> キーを押すか、 **[デバッグの開始]** ボタンをクリックします</span><span class="sxs-lookup"><span data-stu-id="20d88-170">Press <kbd>F5</kbd> or click on the **Start Debugging** button</span></span>

- <span data-ttu-id="20d88-171">ターミナル ペインに切り替えて、コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="20d88-171">Switch to the terminal pane and invoke your cmdlet:</span></span>

  ![コマンドレットを呼び出す](media/using-vscode-for-debugging-compiled-cmdlets/invoke-the-cmdlet.png)

- <span data-ttu-id="20d88-173">ブレークポイントで実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="20d88-173">Execution stops at the breakpoint:</span></span>

  ![実行がブレークポイントで停止する](media/using-vscode-for-debugging-compiled-cmdlets/stopped-at-breakpoint.png)

<span data-ttu-id="20d88-175">ソース コードをステップ実行したり、変数を調べたり、呼び出し履歴を調べたりできます。</span><span class="sxs-lookup"><span data-stu-id="20d88-175">You can step through the source code, inspect variables, and inspect the call stack.</span></span>

<span data-ttu-id="20d88-176">デバッグを終了するには、デバッグ ツール バーの **[停止]** をクリックするか、<kbd>Shift</kbd> - <kbd>F5</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="20d88-176">To end debugging, click **Stop** in the debug toolbar or press <kbd>Shift</kbd>-<kbd>F5</kbd>.</span></span> <span data-ttu-id="20d88-177">デバッグに使用されたシェルが終了し、コンパイルされた DLL ファイルに対するロックが解除されます。</span><span class="sxs-lookup"><span data-stu-id="20d88-177">The shell used for debugging exits and releases the lock on the compiled DLL file.</span></span>

<!-- reference links -->
[Visual Studio Code でのデバッグ]: https://code.visualstudio.com/docs/editor/debugging
[Debugging in Visual Studio Code]: https://code.visualstudio.com/docs/editor/debugging
[Visual Studio Code を使用したリモート編集およびデバッグ]: using-vscode-for-remote-editing-and-debugging.md
[Using Visual Studio Code for remote editing and debugging]: using-vscode-for-remote-editing-and-debugging.md
[移植可能なモジュールの作成]: ../writing-portable-modules.md
[Writing Portable Modules]: ../writing-portable-modules.md
[Visual Studio Code 用 C#]: https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp
[C# for Visual Studio Code]: https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp
