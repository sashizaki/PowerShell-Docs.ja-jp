---
title: PowerShell 開発のための Visual Studio Code の使用
description: PowerShell 開発のための Visual Studio Code の使用
ms.date: 08/06/2018
ms.openlocfilehash: 5badffd49252e0d72ae2c20d3147ad4b1e92d5ed
ms.sourcegitcommit: cf1a281cce9f7239c440c90f8b2798d32a13778d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882571"
---
# <a name="using-visual-studio-code-for-powershell-development"></a>PowerShell 開発のための Visual Studio Code の使用

Visual Studio Code は、[PowerShell ISE] に加え[ise]、PowerShell でも十分にサポートされています。
さらに、PowerShell Core で ISE はサポートされていませんが、Visual Studio Code はすべてのプラットフォーム (Windows、macOS、および Linux) の PowerShell Core でサポートされています。

Windows で Visual Studio Code を使用する場合、Windows 10 を使用して PowerShell バージョン 5 を使用するか、ダウンレベルの (Windows 8.1 などの) Windows OS に、[Windows Management Framework 5.0 RTM](https://www.microsoft.com/en-us/download/details.aspx?id=50395) をインストールします。

開始する前に、システムに PowerShell があることを確認してください。
Windows、macOS、および Linux 上の最近のワークロードに対しては、次を参照してください。

- [Linux への PowerShell Core のインストール][install-pscore-linux]
- [macOS への PowerShell Core のインストール][install-pscore-macos]
- [Windows への PowerShell Core のインストール][install-pscore-windows]

従来の Windows PowerShell ワークロードに対しては、「[Windows PowerShell のインストール][install-winps]」を参照してください。

## <a name="editing-with-visual-studio-code"></a>Visual Studio Code を使用した編集

### <a name="1-installing-visual-studio-codehttpscodevisualstudiocomdocssetupsetup-overview"></a>[1.Visual Studio Code のインストール](https://code.visualstudio.com/Docs/setup/setup-overview)

- **Linux**: 「[Running VS Code on Linux](https://code.visualstudio.com/docs/setup/linux)」 (Linux 上での VS コードの実行) ページのインストール手順に従います。

- **macOS**: 「[Running VS Code on macOS](https://code.visualstudio.com/docs/setup/mac)」 (macOS 上での VS コードの実行) ページのインストール手順に従います。

  > [!IMPORTANT]
  > macOS で、PowerShell の拡張機能用が正常に動作するには、OpenSSL をインストールする必要があります。
  > これには、[Homebrew](https://brew.sh/) をインストールして、`brew install openssl` を実行するのが最も簡単です。
  > これで、VS Code を使用して PowerShell 拡張機能を正常に読み込むことができます。

- **Windows**: 「[Running VS Code on Windows](https://code.visualstudio.com/docs/setup/windows)」 (Windows 上での VS コードの実行) ページのインストール手順に従います。

### <a name="2-installing-powershell-extension"></a>2.PowerShell 拡張機能のインストール

- Visual Studio Code アプリを次のように起動します。
  - **Windows**: PowerShell セッションで `code` と入力します。
  - **Linux**: ターミナルで `code` と入力します。
  - **macOS**: ターミナルで `code` と入力します。

- **CTRL + P** (Mac 上では、**Cmd + P**) を押して、**Quick Open** を起動します。
- Quick Open で `ext install powershell` と入力し、**Enter** キーを押します。
- サイド バーに **[拡張機能]** ビューが開きます。 Microsoft の PowerShell の拡張機能を選択します。
  次のように表示されます。

  ![VSCode](../../images/vscode.png)

- Microsoft の PowerShell 拡張機能の、**[インストール]** ボタンをクリックします。
- インストール後、**[インストール]** ボタンは **[再読み込み]** に変わります。
  **[再読み込み]** をクリックします。
- Visual Studio Code が再読み込みされたら、編集が可能になります。

たとえば、新しいファイルを作成するには、**[ファイル]、[新規]** の順にクリックします。
保存するには、**[ファイル]、[保存]** の順にクリックし、`HelloWorld.ps1` などのファイル名を入力します。
ファイルを閉じるには、ファイル名の横の "x" をクリックします。
**[ファイル]、[終了]** の順にクリックし、Visual Studio Code を終了します。

### <a name="installing-the-powershell-extension-on-restricted-systems"></a>制限されているシステムへの PowerShell 拡張機能のインストール

一部のシステムはすべてのコード署名をチェックする必要があるように設定されているため、PowerShell エディター サービスをシステムで実行することを手動で承認する必要があります。
PowerShell 拡張機能をインストールしたが次のようなエラーが表示される場合、考えられる原因は実行ポリシーを変更するグループ ポリシーの更新です。

```
Language server startup failed.
```

PowerShell エディター サービスおよび VSCode 用 PowerShell 拡張機能を手動で承認するには、PowerShell プロンプトを開いて以下を実行します。

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

"この信頼されていない発行元からのソフトウェアを実行しますか?" というメッセージが表示されます。
`R` キーを押してファイルを実行します。 次に、Visual Studio Code を開き、PowerShell 拡張機能が正しく機能していることを確認します。 まだ問題がある場合は、[GitHub](https://github.com/PowerShell/vscode-powershell/issues) で問い合わせてください。

#### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a>拡張機能で使用する PowerShell のバージョンを選択

Windows PowerShell と PowerShell Core がインストールされている場合、PowerShell の特定のバージョンを PowerShell の拡張機能で使用できるようになりました。 バージョンを選択するには、次の手順を実行します。

1. コマンド パレットを開きます (Windows と Linux では、<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd>、macOS では、<kbd>Cmd</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd>)。
1. "セッション" を検索します。
1. [PowerShell:Show Session Menu]\(PowerShell: セッション メニューを表示\) をクリックします。
1. 一覧から、"PowerShell Core" など、使用する PowerShell のバージョンを選択します。

>[!IMPORTANT]
> この機能では、異なるオペレーティング システム上のいくつかのよく知られているパスを検索し、PowerShell のインストール場所を検出します。 PowerShell を一般的ではない場所にインストールしている場合、最初にそれがセッション メニューに表示されない場合があります。 次のように、[独自のカスタム パスを追加して](#adding-your-own-powershell-paths-to-the-session-menu)、セッション メニューを拡張できます。

>[!NOTE]
> 次のようにセッション メニューに進むこともできます。 エディターで PowerShell ファイルを開いているときに、右下に緑のバージョン番号が表示されます。 このバージョン番号をクリックすると、セッション メニューに移動できます。

##### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a>セッション メニューへの独自の PowerShell のパスの追加

VS Code を設定して、セッション メニューに他の PowerShell の実行パスを追加できます。

次のように `powershell.powerShellAdditionalExePaths` のリストに項目を追加するか、`settings.json` にない場合はリストを作成します。

```json
{
    // other settings...

    "powershell.powerShellAdditionalExePaths": [
        {
            "exePath": "C:\\Users\\tyler\\Downloads\\PowerShell\\pwsh.exe",
            "versionName": "Downloaded PowerShell"
        }
    ],
    
    // other settings...
}
```

各項目には次が必要です。

* `exePath`:`pwsh` または `powershell` 実行可能ファイルへのパス。
* `versionName`:セッション メニューに表示されるテキスト。

`powershell.powerShellDefaultVersion` の設定を使用して、これをセッション メニューに表示されるテキストに設定して、使用する既定の PowerShell のバージョンを設定できます (前の設定での `versionName`)。

```json
{
    // other settings...

    "powershell.powerShellAdditionalExePaths": [
        {
            "exePath": "C:\\Users\\tyler\\Downloads\\PowerShell\\pwsh.exe",
            "versionName": "Downloaded PowerShell"
        }
    ],
    
    "powershell.powerShellDefaultVersion": "Downloaded PowerShell",
    
    // other settings...
}
```

この設定を設定したら、Visual Studio Code を再開するか [Developer:Reload Window]\(Developer: ウィンドウの再読み込み\) のコマンド パレットアクションを使用して、現在の vscode ウィンドウを再読み込みします。

これでセッション メニューを開くと、追加した PowerShell バージョンが表示されます。

> [!NOTE]
> これは、ソースから PowerShell をビルドした場合、PowerShell のローカル ビルドをテストする優れた方法です。

#### <a name="configuration-settings-for-visual-studio-code"></a>Visual Studio Code の構成設定

前段の手順を使用して、`settings.json` に構成設定を追加することができます。

Visual Studio Code には、次の構成設定をお勧めします。

```json
{
    "csharp.suppressDotnetRestoreNotification": true,
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "omnisharp.projectLoadTimeout": 120,
    "files.trimTrailingWhitespace": true,
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

これらの設定がすべてのファイルの種類に影響しないようにする場合、VSCode では言語ごとに構成することもできます。 `[<language-name>]` フィールドに設定を指定して、言語固有の設定を作成します。 たとえば、次のように入力します。

```json
"[powershell]": {
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

VS Code でのファイル エンコードについて詳しくは、[ファイルのエンコードの理解](understanding-file-encoding.md)に関する記事をご覧ください。

## <a name="debugging-with-visual-studio-code"></a>Visual Studio Code を使用したデバッグ

### <a name="no-workspace-debugging"></a>ワークスペースを使用しないデバッグ

Visual Studio Code バージョン 1.9 以降では、PowerShell スクリプトを含むフォルダーを開かずに PowerShell スクリプトをデバッグできます。 **[ファイル] > [ファイルを開く]** の順にクリックして PowerShell スクリプト ファイルを開き、行にブレークポイントを設定し (F9 キーを押す)、F5 キーを押してデバッグを開始します。 [Debug actions]\(デバッグ アクション\) ウィンドウが表示されます。ここでは、デバッガーを中断したり、デバッグのステップ実行、再開、停止を行ったりすることができます。

### <a name="workspace-debugging"></a>ワークスペースを使用したデバッグ

ワークスペースを使用したデバッグとは、**[ファイル]** メニューの **[ファイルを開く]** を使用して Visual Studio Code で開いたフォルダーのコンテキストでデバッグを行うことを言います。
開いたフォルダーは、通常は PowerShell プロジェクトのフォルダーや Git リポジトリのルートです。

このモードの場合も、単純に F5 キーを押せば、現在選択されている PowerShell スクリプトのデバッグを開始できます。
ただし、ワークスペースを使用したデバッグでは、現在開いているファイルをデバッグする以外に、複数のデバッグ構成を定義できます。
たとえば、次に構成を追加できます。

- デバッガーでの Pester テストの起動
- デバッガーでの引数を使用した特定のファイルの起動
- デバッガーでの対話型セッションの起動
- PowerShell ホスト手順へのデバッガーのアタッチ

デバッグ用の構成ファイルを作成するには、次の手順に従います。

  1. **Ctrl + Shift + D** (Mac の場合は **Cmd + Shift + D**) と押して、**[デバッグ]** ビューを開きます。
  2. ツールバーの **[構成]** 歯車アイコンキーを押します。
  3. Visual Studio Code により、**[環境の選択]** が求められます。 **[PowerShell]** を選択します。

  これを行うときに、Visual Studio Code によってワークスペース フォルダーのルートに、".vscode\launch.json" のディレクトリとファイルが作成されます。
  ここにデバッグ構成が格納されます。 ファイルが Git リポジトリにある場合は、通常は launch.json ファイルをコミットしたいでしょう。
  launch.json ファイルの内容は次のとおりです。

  ```json
  {
    "version": "0.2.0",
    "configurations": [
        {
            "type": "PowerShell",
            "request": "launch",
            "name": "PowerShell Launch (current file)",
            "script": "${file}",
            "args": [],
            "cwd": "${file}"
        },
        {
            "type": "PowerShell",
            "request": "attach",
            "name": "PowerShell Attach to Host Process",
            "processId": "${command.PickPSHostProcess}",
            "runspaceId": 1
        },
        {
            "type": "PowerShell",
            "request": "launch",
            "name": "PowerShell Interactive Session",
            "cwd": "${workspaceRoot}"
        }
    ]
  }
  ```

  これが、一般的なデバッグ シナリオです。
  ただし、エディターでこのファイルを開いた場合、**[構成の追加]** ボタンが表示されます。
  さらに PowerShell デバッグ構成を追加するには、このボタンを押します。 追加すると便利な構成の 1 つは、**[PowerShell: Launch Script]\(PowerShell: 起動スクリプト\)** です。
  この構成では、エディターで現在どのファイルがアクティブであるかに関係なく、F5 キーを押すと起動される特定のファイルを、オプションの引数とともに指定できます。

  デバッグ構成が確立されると、**[デバッグ]** ビューのツールバーのデバッグ構成ドロップダウンから、デバッグ セッションで使用する構成を選択できます。

Visual Studio Code 用の PowerShell の拡張機能を使用開始するのに便利なブログを、次にいくつか示します。

- [PowerShell 拡張機能][ps-extension]
- [Visual Studio Code での PowerShell スクリプトの記述およびデバッグ][debug]
- [Visual Studio Code でのデバッグのガイダンス][vscode-guide]
- [Visual Studio Code での PowerShell のデバッグ][ps-vscode]
- [Visual Studio Code での PowerShell 開発の概要][getting-started]
- [PowerShell 開発のための Visual Studio Code の編集機能 – パート 1][editing-part1]
- [PowerShell 開発のための Visual Studio Code の編集機能 – パート 2][editing-part2]
- [Visual Studio Code での PowerShell スクリプトのデバッグ – パート 1][debugging-part1]
- [Visual Studio Code での PowerShell スクリプトのデバッグ – パート 2][debugging-part2]

[ise]: ../ise/Introducing-the-Windows-PowerShell-ISE.md
[install-pscore-linux]:  ../../setup/Installing-PowerShell-Core-on-Linux.md
[install-pscore-macos]:  ../../setup/Installing-PowerShell-Core-on-macOS.md
[install-pscore-windows]: ../../setup/Installing-PowerShell-Core-on-Windows.md
[install-winps]: ../../setup/Installing-Windows-PowerShell.md
[ps-extension]: https://blogs.msdn.microsoft.com/cdndevs/2015/12/11/visual-studio-code-powershell-extension/
[debug]: https://blogs.msdn.microsoft.com/powershell/2015/11/16/announcing-powershell-language-support-for-visual-studio-code-and-more/
[vscode-guide]: https://johnpapa.net/debugging-with-visual-studio-code/
[ps-vscode]: https://github.com/PowerShell/vscode-powershell/tree/master/examples
[getting-started]: https://blogs.technet.microsoft.com/heyscriptingguy/2016/12/05/get-started-with-powershell-development-in-visual-studio-code/
[editing-part1]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/01/11/visual-studio-code-editing-features-for-powershell-development-part-1/
[editing-part2]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/01/12/visual-studio-code-editing-features-for-powershell-development-part-2/
[debugging-part1]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/02/06/debugging-powershell-script-in-visual-studio-code-part-1/
[debugging-part2]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/02/13/debugging-powershell-script-in-visual-studio-code-part-2/

## <a name="powershell-extension-for-visual-studio-code"></a>Visual Studio Code 用の PowerShell Extension の拡張機能

PowerShell の拡張機能のソース コードは、[GitHub](https://github.com/PowerShell/vscode-powershell) にあります。
