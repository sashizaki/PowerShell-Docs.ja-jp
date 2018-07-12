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
  > これには、[Homebrew](http://brew.sh/) をインストールして、`brew install openssl` を実行するのが最も簡単です。
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

#### <a name="using-a-specific-installed-version-of-powershell"></a>PowerShell の特定のインストール バージョンの使用

Visual Studio Code で PowerShell の特定のインストール バージョンを使用する場合、ユーザー設定ファイルに新しい変数を追加する必要があります。

1. **[ファイル]、[基本設定]、[設定]** の順にクリックします。
2. 2 つのエディター ウィンドウが表示されます。
   一番右側のウィンドウの (`settings.json`)、2 つの中かっこ (`{` と `}`) の間に、OS に適した設定を追加し、*<version>* をインストール済みの PowerShell のバージョンに置き換えます。

   ```json
    // On Windows:
    "powershell.powerShellExePath": "c:/Program Files/PowerShell/<version>/pwsh.exe"

    // On Linux:
    "powershell.powerShellExePath": "/opt/microsoft/powershell/<version>/pwsh"

    // On macOS:
    "powershell.powerShellExePath": "/usr/local/microsoft/powershell/<version>/pwsh"
   ```

3. 設定を希望の PowerShell の実行可能ファイルへのパスに置き換えます。
4. 設定ファイルを保存し、Visual Studio Code を再起動します。

#### <a name="configuration-settings-for-visual-studio-code"></a>Visual Studio Code の構成設定

前段の手順を使用して、`settings.json` に構成設定を追加することができます。

Visual Studio Code には、次の構成設定をお勧めします。

```json
{
    "csharp.suppressDotnetRestoreNotification": true,
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "omnisharp.projectLoadTimeout": 120,
    "files.trimTrailingWhitespace": true
}
```

## <a name="debugging-with-visual-studio-code"></a>Visual Studio Code を使用したデバッグ

### <a name="no-workspace-debugging"></a>ワークスペースを使用しないデバッグ

Visual Studio Code バージョン 1.9 以降では、PowerShell スクリプトを含むフォルダーを開かずに PowerShell スクリプトをデバッグできます。
単純に、**[ファイル]、[ファイルを開く]** の順にクリックして PowerShell スクリプト ファイルを開き、行にブレークポイントを設定し (F9 キーを押す)、F5 キーを押してデバッグを開始します。
[Debug actions]\(デバッグ アクション\) ウィンドウが表示されます。ここでは、デバッガーを中断したり、デバッグのステップ実行、再開、停止を行ったりすることができます。

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
  3. Visual Studio Code により、**[環境の選択]** が求められます。
  **[PowerShell]** を選択します。

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
  さらに PowerShell デバッグ構成を追加するには、このボタンを押します。 **[PowerShell: Launch Script]\(PowerShell: スクリプトの起動\)** の構成を追加すると便利です。
  この構成では、エディターで現在どのファイルがアクティブであるかに関係なく、F5 キーを押すと起動される特定のファイルを、オプションの引数とともに指定できます。

  デバッグ構成が確立されると、**[デバッグ]** ビューのツールバーのデバッグ構成ドロップダウンから、デバッグ セッションで使用する構成を選択できます。

  Visual Studio Code 用の PowerShell の拡張機能を使用開始するのに便利なブログを、次にいくつか示します。

Visual Studio Code:

- [PowerShell 拡張機能][ps-extension]
- [Visual Studio Code での PowerShell スクリプトの記述およびデバッグ][debug]
- [Visual Studio Code でのデバッグのガイダンス][vscode-guide]
- [Visual Studio Code での PowerShell のデバッグ][ps-vscode]
- [Visual Studio Code での PowerShell 開発の概要][getting-started]
- [PowerShell 開発のための Visual Studio Code の編集機能 – パート 1][editing-part1]
- [PowerShell 開発のための Visual Studio Code の編集機能 – パート 2][editing-part2]
- [Visual Studio Code での PowerShell スクリプトのデバッグ – パート 1][debugging-part1]
- [Visual Studio Code での PowerShell スクリプトのデバッグ – パート 2][debugging-part2]

[ise]: ../ise-guide.md
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