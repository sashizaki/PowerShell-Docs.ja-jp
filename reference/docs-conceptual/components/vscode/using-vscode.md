---
title: PowerShell 開発のための Visual Studio Code の使用
description: PowerShell 開発のための Visual Studio Code の使用
ms.date: 11/07/2019
ms.openlocfilehash: 8644aa7c648d649651ca679238e0b79ff35ac579
ms.sourcegitcommit: 30ccbbb32915b551c4cd4c91ef1df96b5b7514c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2020
ms.locfileid: "80500904"
---
# <a name="using-visual-studio-code-for-powershell-development"></a>PowerShell 開発のための Visual Studio Code の使用

[Visual Studio Code](https://code.visualstudio.com/) は、Microsoft によるクロスプラットフォーム (Windows、macOS、Linux) のスクリプト エディターです。 [PowerShell 拡張機能](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell)と共に使用すると、充実した対話型のスクリプト編集エクスペリエンスがもたらされ、信頼性の高い PowerShell スクリプトを簡単に記述できます。

PowerShell スクリプトの記述に使用するエディターとしては、PowerShell 拡張機能を備えた Visual Studio Code をお勧めします。
次の PowerShell バージョンがサポートされています。

- PowerShell 7 以上
- PowerShell Core 6
- Windows PowerShell 5.1

開始する前に、システムに PowerShell があることを確認します。 Windows、macOS、Linux 上の最近のワークロードに対しては、次のリンクを参照してください。

- [Linux への PowerShell のインストール][install-pscore-linux]
- [macOS への PowerShell のインストール][install-pscore-macos]
- [Windows への PowerShell のインストール][install-pscore-windows]

従来の Windows PowerShell ワークロードについては、「[Windows PowerShell のインストール][install-winps]」を参照してください。

> [!NOTE]
> Visual Studio Code は、[Visual Studio](https://visualstudio.microsoft.com/) と同じものではありません。

> [!IMPORTANT]
> Windows では [Windows PowerShell ISE][ise] も引き続き使用できますが、これはアクティブな機能開発の対象ではなくなっており、PowerShell 7 以降および PowerShell Core 6 は使用できません。
> Windows に付属するコンポーネントとして、セキュリティや優先順位の高いサービスに関する修正プログラムが引き続き公式でサポートされます。 現在、Windows から ISE が削除される予定はありません。

## <a name="editing-with-visual-studio-code"></a>Visual Studio Code を使用した編集

1. Visual Studio Code をインストールします。 詳細については、「[Visual Studio Code の設定](https://code.visualstudio.com/Docs/setup/setup-overview)」という概要ページを参照してください。

    プラットフォーム別のインストール手順があります。

    - **Windows**: [Windows 上での Visual Studio Code の実行](https://code.visualstudio.com/docs/setup/windows)に関するページに記載されているインストール手順に従ってください。
    - **macOS**: [macOS 上での Visual Studio Code の実行](https://code.visualstudio.com/docs/setup/mac)に関するページに記載されているインストール手順に従ってください。
    - **Linux**: [Linux 上での Visual Studio Code の実行](https://code.visualstudio.com/docs/setup/linux)に関するページに記載されているインストール手順に従ってください。

1. PowerShell 拡張機能をインストールします。

   1. コンソールで「`code`」と入力するか、Visual Studio Code Insiders をインストールした場合は「`code-insiders`」と入力して、Visual Studio Code アプリを起動します。
   1. Windows または Linux の場合、<kbd>Ctrl</kbd>+<kbd>P</kbd> を押し、**Quick Open** を起動します。 macOS の場合、<kbd>Cmd</kbd>+<kbd>P</kbd> を押します。
   1. Quick Open を開き、「`ext install powershell`」と入力し、**Enter** キーを押します。
   1. サイド バーに **[拡張機能]** ビューが開きます。 Microsoft の PowerShell の拡張機能を選択します。
      次の画像のような Visual Studio Code の画面が表示されるはずです。

      ![Visual Studio Code](media/using-vscode/vscode.png)

   1. Microsoft の PowerShell 拡張機能の、 **[インストール]** ボタンをクリックします。
   1. インストール後、 **[インストール]** ボタンが **[再読み込み]** に変わった場合は、 **[再読み込み]** をクリックします。
   1. Visual Studio Code が再読み込みされたら、編集が可能になります。

たとえば、新しいファイルを作成するには、 **[ファイル]、[新規]** の順にクリックします。 保存するには、 **[ファイル]、[保存]** の順にクリックし、`HelloWorld.ps1` のようなファイル名を入力します。 ファイルを閉じるには、ファイル名の横の `X` をクリックします。 Visual Studio Code を終了するには、 **[ファイル] > [終了]** を選択します。

### <a name="installing-the-powershell-extension-on-restricted-systems"></a>制限されているシステムへの PowerShell 拡張機能のインストール

一部のシステムはすべてのコード署名をチェックする必要があるように設定されているため、PowerShell エディター サービスをシステムで実行することを手動で承認する必要があります。 PowerShell 拡張機能をインストールしたが次のようなエラーが表示される場合、考えられる原因は実行ポリシーを変更するグループ ポリシーの更新です。

```
Language server startup failed.
```

PowerShell エディター サービスおよび Visual Studio Code 用 PowerShell 拡張機能を手動で承認するには、PowerShell プロンプトを開いて次のコマンドを実行します。

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

"**この信頼されていない発行元からのソフトウェアを実行しますか?** " というメッセージが表示されます。
`A` キーを押してファイルを実行します。 次に、Visual Studio Code を開き、PowerShell 拡張機能が正しく機能していることを確認します。 まだ問題がある場合は、[GitHub](https://github.com/PowerShell/vscode-powershell/issues) で問い合わせてください。

> [!NOTE]
> Visual Studio Code 用 PowerShell 拡張機能では、制約付き言語モードでの実行はサポートされていません。 詳細については、[そのサポートを追跡する GitHub イシュー](https://github.com/PowerShell/vscode-powershell/issues/606)を参照してください。

### <a name="using-an-older-version-of-the-powershell-extension-for-windows-powershell-v3-and-v4"></a>Windows PowerShell v3 および v4 用の古いバージョンの PowerShell 拡張機能を使用する

現在の PowerShell 拡張機能では [v3 と v4 のサポートが停止されています](https://github.com/PowerShell/vscode-powershell/issues/1310)が、サポートされていた最終バージョンの拡張機能を引き続き使用できます。

> [!NOTE]
> この古いバージョンの拡張機能に修正プログラムが追加されることはありません。 これは "そのままの状態で" 提供されますが、Windows PowerShell v3 と Windows PowerShell v4 を引き続き使用している場合に利用できます。

まず、[拡張機能] ペインを開いて「`PowerShell`」を検索します。 次に、歯車をクリックして、 **[Install another version...]\(別のバージョンをインストール...\)** を選択します。

![別のバージョンをインストール...](media/using-vscode/install-another-version.png)

次に、 **`2020.1.0`** バージョンを選択します。 このバージョンの拡張機能は、v3 と v4 がサポートされている最後のバージョンです。

また、拡張機能のバージョンが自動的に更新されないように、次の設定を追加します。

```json
{
    "extensions.autoUpdate": false
}
```

これはしばらくの間は動作しますが、このバージョンの拡張機能が動作しなくなるような変更が Visual Studio Code で実装される可能性があります。
このことと、サポートがないことにより、次のいずれかを強くお勧めします。

- PowerShell 7 をダウンロードする - これは Windows PowerShell とのサイド バイ サイド インストールであり、PowerShell 拡張機能と最適に連携します
- Windows PowerShell 5.1 にアップグレードする

この記事の「[Visual Studio Code を使用した編集](#editing-with-visual-studio-code)」セクションに、これらをインストールする場所へのリンクが記載されています。

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

[Visual Studio Code 設定](https://code.visualstudio.com/docs/getstarted/settings): `powershell.powerShellAdditionalExePaths` を使用して、セッション メニューに他の PowerShell の実行パスを追加できます。

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

- `exePath`:`pwsh` または `powershell` 実行可能ファイルへのパス。
- `versionName`:セッション メニューに表示されるテキスト。

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

この設定を構成したら、Visual Studio Code を再起動します。または、**コマンド パレット**から現在の Visual Studio Code ウィンドウを再度読み込むには、「**Developer: Reload Window**」と入力します。

これでセッション メニューを開くと、追加した PowerShell バージョンが表示されます。

> [!NOTE]
> これは、ソースから PowerShell をビルドした場合、PowerShell のローカル ビルドをテストする優れた方法です。

### <a name="configuration-settings-for-visual-studio-code"></a>Visual Studio Code の構成設定

まず、Visual Studio Code の設定を変更する方法に慣れていない場合は、[Visual Studio Code の設定に関するドキュメント](https://code.visualstudio.com/docs/getstarted/settings)を確認することをお勧めします。

前段の手順を使用して、`settings.json` に構成設定を追加することができます。

```json
{
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "files.trimTrailingWhitespace": true,
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

これらの設定がすべてのファイルの種類に影響しないようにする場合、Visual Studio Code では言語ごとに構成することもできます。 `[<language-name>]` フィールドに設定を指定して、言語固有の設定を作成します。 次に例を示します。

```json
{
    "[powershell]": {
        "files.encoding": "utf8bom",
        "files.autoGuessEncoding": true
    }
}
```

> [!TIP]
> Visual Studio Code でのファイル エンコードについて詳しくは、[ファイル エンコードの概要](understanding-file-encoding.md)に関する記事をご覧ください。
>
> また、PowerShell 編集用に Visual Studio Code を構成する方法に関するその他のヒントについては、「[Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法](How-To-Replicate-the-ISE-Experience-In-VSCode.md)」もご覧ください。

## <a name="debugging-with-visual-studio-code"></a>Visual Studio Code を使用したデバッグ

### <a name="no-workspace-debugging"></a>ワークスペースを使用しないデバッグ

Visual Studio Code バージョン 1.9 以降では、PowerShell スクリプトを含むフォルダーを開かずに PowerShell スクリプトをデバッグできます。 **[ファイル] > [ファイルを開く]** の順にクリックして PowerShell スクリプト ファイルを開き、行にブレークポイントを設定し、<kbd>F9</kbd> キーを押し、<kbd>F5</kbd> キーを押してデバッグを開始します。 [Debug actions]\(デバッグ アクション\) ウィンドウが表示されます。ここでは、デバッガーを中断したり、デバッグをステップ実行、再開、停止したりできます。

### <a name="workspace-debugging"></a>ワークスペースを使用したデバッグ

ワークスペースを使用したデバッグとは、 **[ファイル]** メニューの **[フォルダーを開く]** を使用して Visual Studio Code で開いたフォルダーのコンテキストでデバッグを行うことを言います。開いたフォルダーは、通常は PowerShell プロジェクトのフォルダーや Git リポジトリのルートです。

このモードの場合も、<kbd>F5</kbd> キーを押せば、現在選択されている PowerShell スクリプトのデバッグを開始できます。 ただし、ワークスペースを使用したデバッグでは、現在開いているファイルをデバッグする以外に、複数のデバッグ構成を定義できます。 これらについては、この後すぐに説明します。

デバッグ用の構成ファイルを作成するには、次の手順に従います。

  1. Windows または Linux の場合、<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> を押し、 **[デバッグ]** ビューを開きます。 macOS の場合、<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> を押します。
  1. "launch.json ファイルの作成" リンクをクリックします。
  1. Visual Studio Code により、 **[環境の選択]** が求められます。 **[PowerShell]** を選択します。
  1. 最後に、使用するデバッグの種類を選択します。

- **現在のファイルを起動** - 現在アクティブなエディター ウィンドウのファイルを起動してデバッグします
- **スクリプトを起動** - 指定したファイルまたはコマンドを起動してデバッグします
- **対話型セッション** - 統合コンソールから実行されたコマンドをデバッグします
- **アタッチ** - 実行中の PowerShell ホスト プロセスにデバッガーをアタッチします

結果として、Visual Studio Code によってワークスペース フォルダーのルートにディレクトリとファイル `.vscode\launch.json` が作成されます。 この場所にデバッグ構成が格納されます。 ファイルが Git リポジトリにある場合は、通常、`launch.json` ファイルをコミットすることになるでしょう。 `launch.json` ファイルの内容:

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

## <a name="useful-resources"></a>有用なリソース

Visual Studio Code 用の PowerShell 拡張機能の使用を開始するのに役立つビデオとブログ記事を、次にいくつか示します。

### <a name="videos"></a>ビデオ

- [既定の PowerShell エディターとして Visual Studio Code を使用する](https://youtu.be/bGn45vIeAMM)
- [Visual Studio Code: PowerShell スクリプトのデバッグの詳細](https://youtu.be/cSbIXmlkr8o)

### <a name="blog-posts"></a>ブログ記事

- [PowerShell の拡張機能][ps-extension]
- [Visual Studio Code での PowerShell スクリプトの記述およびデバッグ][debug]
- [Visual Studio Code でのデバッグのガイダンス][vscode-guide]
- [Visual Studio Code での PowerShell のデバッグ][ps-vscode]
- [Visual Studio Code での PowerShell 開発の概要][getting-started]
- [PowerShell 開発のための Visual Studio Code の編集機能 – パート 1][editing-part1]
- [PowerShell 開発のための Visual Studio Code の編集機能 – パート 2][editing-part2]
- [Visual Studio Code での PowerShell スクリプトのデバッグ – パート 1][debugging-part1]
- [Visual Studio Code での PowerShell スクリプトのデバッグ – パート 2][debugging-part2]

## <a name="powershell-extension-for-visual-studio-code"></a>Visual Studio Code 用 PowerShell 拡張機能

PowerShell の拡張機能のソース コードは、[GitHub](https://github.com/PowerShell/vscode-powershell) にあります。

共同作成に興味をお持ちの場合は、ぜひ pull request をご活用ください。 [GitHub 上の 開発者向けドキュメント](https://github.com/PowerShell/vscode-powershell/blob/master/docs/development.md)を参照して、作業を開始してください。

## <a name="troubleshooting-the-powershell-extension-for-visual-studio-code"></a>Visual Studio Code 用 PowerShell 拡張機能のトラブルシューティング

PowerShell スクリプト開発のための Visual Studio Code の使用に関して問題が発生した場合は、[GitHub 上のトラブルシューティング ガイド](https://github.com/PowerShell/vscode-powershell/blob/master/docs/troubleshooting.md)を参照してください

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
