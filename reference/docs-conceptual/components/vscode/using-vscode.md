---
title: PowerShell 開発のための Visual Studio Code の使用
description: PowerShell 開発のための Visual Studio Code の使用
ms.date: 11/07/2019
ms.openlocfilehash: 4f197e71d3b79828f466584f5d862415726818b1
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74117387"
---
# <a name="using-visual-studio-code-for-powershell-development"></a>PowerShell 開発のための Visual Studio Code の使用

[PowerShell ISE][ise] だけでなく、PowerShell も Visual Studio Code (VSCode) で問題なくサポートされています。 PowerShell Core では ISE はサポートされていませんが、VSCode はすべてのプラットフォーム (Windows、macOS、Linux) の PowerShell Core でサポートされています。

PowerShell バージョンが 5 の Windows で VSCode を使用する場合、Windows 10 を使用するか、ダウンレベルの Windows OS (Windows 8.1 など) 向けの Windows Management Framework 5.1 をインストールします。 詳細については、「[WMF 5.1 のインストールと構成](/powershell/scripting/wmf/setup/install-configure)」を参照してください。

開始する前に、システムに PowerShell があることを確認します。 Windows、macOS、Linux 上の最近のワークロードに対しては、次のリンクを参照してください。

- [Linux への PowerShell Core のインストール][install-pscore-linux]
- [macOS への PowerShell Core のインストール][install-pscore-macos]
- [Windows への PowerShell Core のインストール][install-pscore-windows]

従来の Windows PowerShell ワークロードについては、「[Windows PowerShell のインストール][install-winps]」を参照してください。

## <a name="editing-with-vscode"></a>VSCode による編集

1. VSCode をインストールします。 詳細については、「[Visual Studio Code の設定](https://code.visualstudio.com/Docs/setup/setup-overview)」という概要ページを参照してください。

   プラットフォーム別のインストール手順があります。

   - **Linux**: [Linux 上で VS コードを実行する](https://code.visualstudio.com/docs/setup/linux)方法に関するページのインストール手順に従います。
   - **macOS**: [macOS 上で VS コードを実行する](https://code.visualstudio.com/docs/setup/mac)方法に関するページのインストール手順に従います。

     > [!IMPORTANT]
     > macOS で、PowerShell の拡張機能用が正常に動作するには、OpenSSL をインストールする必要があります。 これには、[Homebrew](https://brew.sh/) をインストールして、`brew install openssl` を実行するのが最も簡単です。 これで、VSCode を使用して PowerShell 拡張機能を正常に読み込むことができます。

   - **Windows**: [Windows 上で VS コードを実行する](https://code.visualstudio.com/docs/setup/windows)方法に関するページのインストール手順に従います。

1. PowerShell 拡張機能をインストールします。

   1. 次の方法で VSCode アプリを起動します。
      - **Windows**: PowerShell セッションで `code` と入力します。
      - **Linux**: ターミナルで `code` と入力します。
      - **macOS**: ターミナルで `code` と入力します。
   1. Windows または Linux の場合、<kbd>Ctrl</kbd>+<kbd>P</kbd> を押し、**Quick Open** を起動します。 macOS の場合、<kbd>Cmd</kbd>+<kbd>P</kbd> を押します。
   1. Quick Open を開き、「`ext install powershell`」と入力し、**Enter** キーを押します。
   1. サイド バーに **[拡張機能]** ビューが開きます。 Microsoft の PowerShell の拡張機能を選択します。
      次の画像のような VSCode 画面が表示されるはずです。

      ![VSCode](../../images/using-vscode/vscode.png)

   1. Microsoft の PowerShell 拡張機能の、 **[インストール]** ボタンをクリックします。
   1. インストール後、 **[インストール]** ボタンは **[再読み込み]** に変わります。 **[再読み込み]** をクリックします。
   1. VSCode が再読み込みされたら、編集が可能になります。

たとえば、新しいファイルを作成するには、 **[ファイル]、[新規]** の順にクリックします。 保存するには、 **[ファイル]、[保存]** の順にクリックし、`HelloWorld.ps1` のようなファイル名を入力します。 ファイルを閉じるには、ファイル名の横の `X` をクリックします。 VSCode を終了するには、 **[ファイル]、[終了]** の順にクリックします。

### <a name="installing-the-powershell-extension-on-restricted-systems"></a>制限されているシステムへの PowerShell 拡張機能のインストール

一部のシステムはすべてのコード署名をチェックする必要があるように設定されているため、PowerShell エディター サービスをシステムで実行することを手動で承認する必要があります。 PowerShell 拡張機能をインストールしたが次のようなエラーが表示される場合、考えられる原因は実行ポリシーを変更するグループ ポリシーの更新です。

```
Language server startup failed.
```

PowerShell エディター サービスおよび VSCode 用 PowerShell 拡張機能を手動で承認するには、PowerShell プロンプトを開いて次のコマンドを実行します。

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

"**この信頼されていない発行元からのソフトウェアを実行しますか?** " というメッセージが表示されます。 `A` キーを押してファイルを実行します。 次に、VSCode を開き、PowerShell 拡張機能が正しく機能していることを確認します。 まだ問題がある場合は、[GitHub](https://github.com/PowerShell/vscode-powershell/issues) で問い合わせてください。

### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a>拡張機能で使用する PowerShell のバージョンを選択

Windows PowerShell と PowerShell Core がインストールされている場合、PowerShell の特定のバージョンを PowerShell の拡張機能で使用できるようになりました。 バージョンは次の手順で選択します。

1. Windows または Linux の場合、<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> を使用して**コマンド パレット**を開きます。 macOS の場合、<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> を使用します。
1. "**セッション**" を検索します。
1. **[PowerShell: Show Session Menu]\(PowerShell: セッション メニューを表示\)** をクリックします。
1. 一覧から、"**PowerShell Core**" など、使用する PowerShell のバージョンを選択します。

> [!IMPORTANT]
> この機能では、異なるオペレーティング システム上のいくつかのよく知られているパスを検索し、PowerShell のインストール場所を検出します。 PowerShell を一般的ではない場所にインストールしている場合、最初にそれがセッション メニューに表示されない場合があります。 次のように、[独自のカスタム パスを追加して](#adding-your-own-powershell-paths-to-the-session-menu)、セッション メニューを拡張できます。

>[!NOTE]
> 次のようにセッション メニューに進むこともできます。 エディターで PowerShell ファイルを開いているときに、右下に緑のバージョン番号が表示されます。 このバージョン番号をクリックすると、セッション メニューに移動できます。

### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a>セッション メニューへの独自の PowerShell のパスの追加

VSCode 設定を利用し、セッション メニューに他の PowerShell の実行可能パスを追加できます。

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

この設定を構成したら、VSCode を再起動します。あるいは**コマンド パレット**から現在の VSCode ウィンドウを再度読み込むには、「**Developer: Reload Window**」と入力します。

これでセッション メニューを開くと、追加した PowerShell バージョンが表示されます。

> [!NOTE]
> これは、ソースから PowerShell をビルドした場合、PowerShell のローカル ビルドをテストする優れた方法です。

### <a name="configuration-settings-for-vscode"></a>VSCode の構成設定

前段の手順を使用して、`settings.json` に構成設定を追加することができます。

VSCode には、次の構成設定をお勧めします。

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

VSCode でのファイル エンコードについて詳しくは、[ファイルのエンコードの理解](understanding-file-encoding.md)に関する記事をご覧ください。

## <a name="debugging-with-vscode"></a>VSCode によるデバッグ

### <a name="no-workspace-debugging"></a>ワークスペースを使用しないデバッグ

VSCode バージョン 1.9 以降では、PowerShell スクリプトを含むフォルダーを開かずに PowerShell スクリプトをデバッグできます。 **[ファイル] > [ファイルを開く]** の順にクリックして PowerShell スクリプト ファイルを開き、行にブレークポイントを設定し、<kbd>F9</kbd> キーを押し、<kbd>F5</kbd> キーを押してデバッグを開始します。 [Debug actions]\(デバッグ アクション\) ウィンドウが表示されます。ここでは、デバッガーを中断したり、デバッグをステップ実行、再開、停止したりできます。

### <a name="workspace-debugging"></a>ワークスペースを使用したデバッグ

ワークスペースを使用したデバッグとは、 **[ファイル]** メニューの **[フォルダーを開く]** を使用して Visual Studio Code で開いたフォルダーのコンテキストでデバッグを行うことを言います。開いたフォルダーは、通常は PowerShell プロジェクトのフォルダーや Git リポジトリのルートです。

このモードの場合も、<kbd>F5</kbd> キーを押せば、現在選択されている PowerShell スクリプトのデバッグを開始できます。 ただし、ワークスペースを使用したデバッグでは、現在開いているファイルをデバッグする以外に、複数のデバッグ構成を定義できます。 たとえば、次の目的で構成を追加できます。

- デバッガーで Pester テストを起動します。
- デバッガーで引数を使用して特定のファイルを起動します。
- デバッガーで対話型セッションを起動します。
- PowerShell ホスト手順にデバッガーをアタッチします。

デバッグ用の構成ファイルを作成するには、次の手順に従います。

  1. Windows または Linux の場合、<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> を押し、 **[デバッグ]** ビューを開きます。 macOS の場合、<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> を押します。
  1. ツールバーの **[構成]** 歯車アイコンをクリックします。
  1. VSCode により、 **[環境の選択]** が求められます。 **[PowerShell]** を選択します。

結果的に、VSCode によってワークスペース フォルダーのルートにディレクトリとファイル `.vscode\launch.json` が作成されます。 この場所にデバッグ構成が格納されます。 ファイルが Git リポジトリにある場合は、通常、`launch.json` ファイルをコミットすることになるでしょう。 `launch.json` ファイルの内容:

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

このファイルは一般的なデバッグ シナリオです。 エディターでこのファイルを開いた場合、 **[構成の追加]** ボタンが表示されます。 このボタンをクリックすることで、PowerShell デバッグ構成をさらに追加できます。 追加すると便利な構成の 1 つは、 **[PowerShell: Launch Script]\(PowerShell: 起動スクリプト\)** です。 この構成では、エディターで現在どのファイルがアクティブであるかに関係なく、<kbd>F5</kbd> キーを押すと起動されるファイルを、オプションの引数と共に指定できます。

デバッグ構成が確立されたら、デバッグ セッション中に使用する構成を選択できます。 **[デバッグ]** ビューのツール バーでデバッグ構成ドロップダウンから構成を選択します。

Visual Studio Code 用の PowerShell の拡張機能を使用開始するのに便利なブログを、次にいくつか示します。

- [PowerShell の拡張機能][ps-extension]
- [Visual Studio Code での PowerShell スクリプトの記述およびデバッグ][debug]
- [Visual Studio Code でのデバッグのガイダンス][vscode-guide]
- [Visual Studio Code での PowerShell のデバッグ][ps-vscode]
- [Visual Studio Code での PowerShell 開発の概要][getting-started]
- [PowerShell 開発のための Visual Studio Code の編集機能 – パート 1][editing-part1]
- [PowerShell 開発のための Visual Studio Code の編集機能 – パート 2][editing-part2]
- [Visual Studio Code での PowerShell スクリプトのデバッグ – パート 1][debugging-part1]
- [Visual Studio Code での PowerShell スクリプトのデバッグ – パート 2][debugging-part2]

[ise]: ../ise/Introducing-the-Windows-PowerShell-ISE.md
[install-pscore-linux]:  ../../install/Installing-PowerShell-Core-on-Linux.md
[install-pscore-macos]:  ../../install/Installing-PowerShell-Core-on-macOS.md
[install-pscore-windows]: ../../install/Installing-PowerShell-Core-on-Windows.md
[install-winps]: ../../install/Installing-Windows-PowerShell.md
[ps-extension]: https://blogs.msdn.microsoft.com/cdndevs/2015/12/11/visual-studio-code-powershell-extension/
[debug]: https://devblogs.microsoft.com/powershell/announcing-powershell-language-support-for-visual-studio-code-and-more/
[vscode-guide]: https://johnpapa.net/debugging-with-visual-studio-code/
[ps-vscode]: https://github.com/PowerShell/vscode-powershell/tree/master/examples
[getting-started]: https://devblogs.microsoft.com/scripting/get-started-with-powershell-development-in-visual-studio-code/
[editing-part1]: https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-1/
[editing-part2]: https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-2/
[debugging-part1]: https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-1/
[debugging-part2]: https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-2/

## <a name="powershell-extension-for-vscode"></a>VSCode 用 PowerShell 拡張機能

PowerShell の拡張機能のソース コードは、[GitHub](https://github.com/PowerShell/vscode-powershell) にあります。
