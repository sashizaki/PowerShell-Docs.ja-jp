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
# <a name="using-visual-studio-code-to-debug-compiled-cmdlets"></a>Visual Studio Code を使用したコンパイル済みコマンドレットのデバッグ

このガイドでは、Visual Studio Code (VS Code) と C# 拡張機能を使用して、コンパイル済み PowerShell モジュールの C# ソース コードを対話形式でデバッグする方法について説明します。

Visual Studio Code デバッガーについてのある程度の知識があることを前提としています。

- VS Code デバッガーの概要については、[Visual Studio Code でのデバッグ][]に関するページを参照してください。

- PowerShell のスクリプト ファイルとモジュールのデバッグの例については、「[Visual Studio Code を使用したリモート編集およびデバッグ][]」を参照してください。

このガイドでは、[移植可能なモジュールの作成][]に関するガイドに記載されている手順を読んで従っていることを前提としています。

## <a name="creating-a-build-task"></a>ビルド タスクの作成

デバッグ セッションを開始する前に、プロジェクトを自動的にビルドします。 リビルドすることで、最新バージョンのコードを確実にデバッグできます。

ビルド タスクを構成します。

1. **コマンド パレット** で、 **[Configure Default Build Task]\(既定のビルド タスクを構成する\)** コマンドを実行します。

   ![[Configure Default Build Task]\(既定のビルド タスクを構成する\) を実行する](media/using-vscode-for-debugging-compiled-cmdlets/configure-default-build-task.png)

1. **[Create tasks.json file from template]\(構成するタスクを選択\)** ダイアログで、 **[テンプレートから tasks.json を生成]** を選択します。

1. **[Select a Task Template]\(タスク テンプレートを選択\)** ダイアログで、 **[.NET Core]** を選択します。

まだ存在しない場合は、新しい `tasks.json` ファイルが作成されます。

ビルド タスクをテストするには:

1. **コマンド パレット** で、 **[ビルド タスクの実行]** コマンドを実行します。

1. **[Select the build task to run]\(実行するビルド タスクを選択\)** ダイアログで、 **[ビルド]** を選択します。

### <a name="information-about-dll-files-being-locked"></a>ロックされている DLL ファイルに関する情報

既定では、ビルドが成功した場合は、ターミナル ペインに出力は表示されません。 " **プロジェクトファイルが存在しません** " というテキストが含まれる出力が表示される場合は、`tasks.json` ファイルを編集する必要があります。 C# プロジェクトへの明示的なパスの `"${workspaceFolder}/myModule"` という表記を含めます。 この例で、`myModule` はプロジェクト フォルダーの名前です。 次のように、`args` リストの `build` エントリの後にこのエントリを追加する必要があります。

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

デバッグ時には、モジュールの DLL が VS Code ターミナルの PowerShell セッションにインポートされます。 DLL はロックされます。 ターミナル セッションを閉じずにビルド タスクを実行すると、次のメッセージが表示されます。

```Output
Could not copy "obj\Debug\netstandard2.0\myModule.dll" to "bin\Debug\netstandard2.0\myModule.dll"`.
```

リビルドの前に、ターミナル セッションを閉じる必要があります。

## <a name="setting-up-the-debugger"></a>デバッガーの設定

PowerShell コマンドレットをデバッグするには、カスタム起動構成を設定する必要があります。 この構成は、次のために使用されます。

- ソース コードをビルドします
- モジュールを読み込んで PowerShell を開始します
- ターミナル ペインで PowerShell を開いたままにします

ターミナル セッションでコマンドレットを呼び出すと、ソース コードに設定されているブレークポイントでデバッガーが停止します。

### <a name="configuring-launchjson-for-powershell-core"></a>PowerShell Core 用の launch.json の構成

1. [Visual Studio Code 用 C#][] 拡張機能をインストールします

1. [デバッグ] ペインで、デバッグ構成を追加します

1. [`Select environment`] ダイアログで、[`.NET Core`] を選択します

1. `launch.json` がエディターで開かれます。 `configurations` 配列の内側にカーソルを置くと、`configuration` ピッカーが表示されます。 このリストが表示されない場合は、 **[構成の追加]** を選択します。

1. 既定のデバッグ構成を作成するには、 **[Launch .NET Core Console App]\(.NET Core コンソールアプリの起動\)** を選択します。

   ![.NET Core コンソールアプリの起動](media/using-vscode-for-debugging-compiled-cmdlets/add-configuration-dialog.png)

1. `name`、`program`、`args`、`console` の各フィールドを次のように編集します。

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

`program` フィールドは、デバッグ対象のコマンドレットを実行できるように `pwsh` を起動するために使用されます。 引数 `-NoExit` を指定すると、モジュールがインポートされても PowerShell セッションはすぐに終了しません。
`Import-Module` 引数のパスは、[移植可能なモジュールの作成][]に関するガイドに従っている場合の既定のビルド出力パスです。 モジュール マニフェスト (`.psd1` ファイル) を作成した場合は、代わりにそのパスを使用する必要があります。 パス区切り記号 `/` は、Windows、Linux、macOS で動作します。 デバッグ対象の PowerShell コマンドを実行するには、統合ターミナルを使用する必要があります。

> [!NOTE]
> デバッガーがどのブレークポイントでも停止しない場合は、Visual Studio Code のデバッグ コンソールで次のような行を探します。
>
> ```
> Loaded '/path/to/myModule.dll'. Skipped loading symbols. Module is optimized and the debugger option 'Just My Code' is enabled.
> ```
>
> これがある場合は、起動構成に `"justMyCode": false` を追加します (`"console": "integratedTerminal"` と同じレベル)。

### <a name="configuring-launchjson-for-windows-powershell"></a>Windows PowerShell 用の launch.json の構成

この起動構成は、Windows PowerShell でコマンドレットをテストするために機能します (`powershell.exe`)。
次のように変更して、2 番目の起動構成を作成します。

1. `name` は、`PowerShell cmdlets: powershell` である必要があります。

1. `type` は、`clr` である必要があります。

1. `program` は、`powershell` である必要があります。

   次のようになります。

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

## <a name="launching-a-debugging-session"></a>デバッグ セッションの起動

これで、デバッグを始める準備がすべて整いました。

- デバッグするコマンドレットのソース コードにブレークポイントを配置します。

  ![ブレークポイントは、余白の赤い点で示されます](media/using-vscode-for-debugging-compiled-cmdlets/set-breakpoint.png)

- **[デバッグ]** ビューの構成ドロップダウン メニューで、関連する **PowerShell コマンドレット** の構成が選択されていることを確認します。

  ![起動構成を選択する](media/using-vscode-for-debugging-compiled-cmdlets/select-launch-configuration.png)

- <kbd>F5</kbd> キーを押すか、 **[デバッグの開始]** ボタンをクリックします

- ターミナル ペインに切り替えて、コマンドレットを呼び出します。

  ![コマンドレットを呼び出す](media/using-vscode-for-debugging-compiled-cmdlets/invoke-the-cmdlet.png)

- ブレークポイントで実行が停止します。

  ![実行がブレークポイントで停止する](media/using-vscode-for-debugging-compiled-cmdlets/stopped-at-breakpoint.png)

ソース コードをステップ実行したり、変数を調べたり、呼び出し履歴を調べたりできます。

デバッグを終了するには、デバッグ ツール バーの **[停止]** をクリックするか、<kbd>Shift</kbd> - <kbd>F5</kbd> キーを押します。 デバッグに使用されたシェルが終了し、コンパイルされた DLL ファイルに対するロックが解除されます。

<!-- reference links -->
[Visual Studio Code でのデバッグ]: https://code.visualstudio.com/docs/editor/debugging
[Visual Studio Code を使用したリモート編集およびデバッグ]: using-vscode-for-remote-editing-and-debugging.md
[移植可能なモジュールの作成]: ../writing-portable-modules.md
[Visual Studio Code 用 C#]: https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp
