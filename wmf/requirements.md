# システム要件

- WMF 5.0 RTM をインストールする前に最新の Windows Update をインストールします。
- WMF 5.0 RTM は、次のオペレーティング システムにのみインストールすることができます。

    | オペレーティング システム       | エディション         | 前提条件        | パッケージのリンク |
    |------------------------|--------------|------------------|----------------------| --------------|
    | Windows Server 2012 R2 |  |  | <ctype="x-NOTFOUND" mdpre="[" mdpost="](http://go.microsoft.com/fwlink/?LinkId=717507)">Win8.1AndW2K12R2-KB3134758-x64.msu</ctype="x-NOTFOUND"> |
    | Windows Server 2012    |  |  | <ctype="x-NOTFOUND" mdpre="[" mdpost="](http://go.microsoft.com/fwlink/?LinkId=717506)">W2K12-KB3134759-x64.msu</ctype="x-NOTFOUND"> |
    | Windows Server 2008 R2 SP1 | IA64 を除くすべて | <ctype="x-NOTFOUND" mdpre="[" mdpost="](http://www.microsoft.com/en-us/download/details.aspx?id=40855)">WMF 4.0</ctype="x-NOTFOUND"> と <ctype="x-NOTFOUND" mdpre="[" mdpost="](https://msdn.microsoft.com/en-us/library/5a4x27ek.aspx)">.NET Framework 4.5 以上</ctype="x-NOTFOUND">がインストールされていること | <ctype="x-NOTFOUND" mdpre="[" mdpost="](http://go.microsoft.com/fwlink/?LinkId=717504)">Win7AndW2K8R2-KB3134760-x64.msu</ctype="x-NOTFOUND">|
    | Windows 8.1 | Pro, Enterprise | | <ctype="x-NOTFOUND" mdpre="**" mdpost="**">x64:</ctype="x-NOTFOUND">  <ctype="x-NOTFOUND" mdpre="[" mdpost="](http://go.microsoft.com/fwlink/?LinkId=717507)">Win8.1AndW2K12R2-KB3134758-x64.msu</ctype="x-NOTFOUND"> </br> <ctype="x-NOTFOUND" mdpre="**" mdpost="**">x86:</ctype="x-NOTFOUND">  <ctype="x-NOTFOUND" mdpre="[" mdpost="](http://go.microsoft.com/fwlink/?LinkID=717963)">Win8.1-KB3134758-x86.msu</ctype="x-NOTFOUND">|
    | Windows 7 SP1 | すべて | <ctype="x-NOTFOUND" mdpre="[" mdpost="](http://www.microsoft.com/en-us/download/details.aspx?id=40855)">WMF 4.0</ctype="x-NOTFOUND"> と <ctype="x-NOTFOUND" mdpre="[" mdpost="](https://msdn.microsoft.com/en-us/library/5a4x27ek.aspx)">.NET Framework 4.5 以上</ctype="x-NOTFOUND">がインストールされていること | <ctype="x-NOTFOUND" mdpre="**" mdpost="**">x64:</ctype="x-NOTFOUND">  <ctype="x-NOTFOUND" mdpre="[" mdpost="](http://go.microsoft.com/fwlink/?LinkId=717504)">Win7AndW2K8R2-KB3134760-x64.msu</ctype="x-NOTFOUND">  </br> <ctype="x-NOTFOUND" mdpre="**" mdpost="**">x86:</ctype="x-NOTFOUND">  <ctype="x-NOTFOUND" mdpre="[" mdpost="](http://go.microsoft.com/fwlink/?LinkID=717962)">Win7-KB3134760-x86.msu</ctype="x-NOTFOUND">|

# インストール手順

### Windows エクスプローラー (またはファイル エクスプローラー) から WMF 5.0 をインストールするには:

1. MSU ファイルをダウンロードしたフォルダーに移動します。

2. MSU をダブルクリックして実行します。

### コマンド プロンプトから WMF 5.0 をインストールするには:

1. コンピューターのアーキテクチャに適切なパッケージをダウンロードした後、管理者特権 (管理者として実行) を使ってコマンド プロンプト ウィンドウを開きます。 Windows Server 2012 R2、Windows Server 2012、または Windows Server 2008 R2 SP1 の Server Core インストール オプションで、既定で管理者特権でコマンド プロンプトが開きます。

2. WMF 5.0 のインストール パッケージをダウンロードまたはコピーしたフォルダーにディレクトリを変更します。

3. 次のいずれかのコマンドを実行します。
    - Windows Server 2012 R2 または Windows 8.1 x64 を実行しているコンピューターで、<ctype="x-NOTFOUND" mdpre="**" mdpost="**">Win8.1AndW2K12R2-KB3134758-x64.msu /quiet</ctype="x-NOTFOUND"> を実行します。
    - Windows Server 2012 を実行しているコンピューターで、<ctype="x-NOTFOUND" mdpre="**" mdpost="**">W2K12-KB3134759-x64.msu /quiet</ctype="x-NOTFOUND"> を実行します。
    - Windows Server 2008 R2 SP1 または Windows 7 SP1 x64 を実行しているコンピューターで、<ctype="x-NOTFOUND" mdpre="**" mdpost="**">Win7AndW2K8R2-KB3134760-x64.msu /quiet</ctype="x-NOTFOUND"> を実行します。
    - Windows 8.1 x86 を実行しているコンピューターで、<ctype="x-NOTFOUND" mdpre="**" mdpost="**">Win8.1-KB3134758-x86.msu /quiet</ctype="x-NOTFOUND"> を実行します。
    - Windows 7 SP1 x86 を実行しているコンピューターで、<ctype="x-NOTFOUND" mdpre="**" mdpost="**">Win7-KB3134760-x86.msu /quiet</ctype="x-NOTFOUND"> を実行します。

### Windows Server 2008 R2 SP1 および Windows 7 SP1 でのインストールに関する追加の注記:

次の前提条件が満たされていることを確認します。
- 最新のサービス パックがインストールされていること。
- <ctype="x-NOTFOUND" mdpre="[" mdpost="](http://www.microsoft.com/en-us/download/details.aspx?id=40855)">WMF 4.0</ctype="x-NOTFOUND"> がインストールされていること。
- <ctype="x-NOTFOUND" mdpre="[" mdpost="](https://msdn.microsoft.com/en-us/library/5a4x27ek.aspx)">.NET Framework 4.5 以上</ctype="x-NOTFOUND">がインストールされていること。

**WMF 4.0 の依存関係**

Windows Server 2008 R2 SP1 システムと Windows 7 SP1 システムには、組み込みの PowerShell 2.0、WinRM、および WMI があります。 これらの組み込みコンポーネントを更新する WMF 3.0 パッケージと WMF 4.0 パッケージは、Windows Server 2008 R2 SP1 および Windows 7 SP1 のリリース後にリリースされました。 WMF 3.0 パッケージと WMF 4.0 パッケージのインストール/アンインストールでは、次のアップグレード パスでいくつかの問題が見つかりました。

- 組み込み --> WMF 4.0
- 組み込み --> WMF 3.0 --> WMF4.0 

これらのすべての問題を、WMF 4.0 パッケージで修正しました。 したがって、Windows Server 2008 R2 SP1 および Windows 7 SP1 に WMF 5.0 をインストールするには、WMF 4.0 が前提条件になります。 WMF 5.0 にアップグレードする前に WMF 4.0 をインストールしなかった場合に発生する可能性のある問題を下に示します。

- Windows 7 SP1 および Windows Server 2008 R2 SP1 で、WMF 3.0 または WMF 5.0 (前提条件の WMF 4.0 がインストールされていない場合) をアンインストールすると、転送されたイベント ログが利用できなくなり、イベント ビューアーに EventCollector ログが表示されなくなります (<ctype="x-NOTFOUND" mdpre="[" mdpost="](https://support.microsoft.com/en-us/kb/2809215)">KB2809215</ctype="x-NOTFOUND">)。
- Windows 7 SP1 および Windows Server 2008 R2 SP1 で、組み込みの PowerShell 2.0 から直接 WMF 5.0 にアップグレードした場合 (<ctype="x-NOTFOUND" mdpre="[" mdpost="](https://support.microsoft.com/en-us/kb/2872035)">KB2872035</ctype="x-NOTFOUND">)、または WMF 3.0 から WMF 5.0 にアップグレードした場合<ctype="x-NOTFOUND" mdpre="*" mdpost="*"></ctype="x-NOTFOUND"> (<ctype="x-NOTFOUND" mdpre="[" mdpost="](https://support.microsoft.com/en-us/kb/2872047)">KB2872047</ctype="x-NOTFOUND">)、PSModulePath 環境変数に対するカスタマイズが既定値にリセットされます。

**WinRM の依存関係**

Windows PowerShell Desired State Configuration (DSC) は、WinRM に依存します。 WinRM は、Windows Server 2008 R2 SP1 および Windows 7 SP1 では既定で無効になっています。 WinRM を有効にするには、Windows PowerShell 管理者特権セッションで <ctype="x-NOTFOUND" mdpre="**" mdpost="**">Set-WSManQuickConfig</ctype="x-NOTFOUND"> を実行します。

# アンインストール手順

### コマンド プロンプトを使用

1.  <ctype="x-NOTFOUND" mdpre="**" mdpost="**">コマンド プロンプト</ctype="x-NOTFOUND">を開きます。

2.  <ctype="x-NOTFOUND" mdpre="[" mdpost="](https://support.microsoft.com/en-us/kb/934307)">Windows Update スタンドアロン ランチャー</ctype="x-NOTFOUND">を次のように実行します。

Windows Server 2012 R2 および Windows 8.1:
```powershell
wusa /uninstall /kb:3134758
```
Windows Server 2012:
```powershell
wusa /uninstall /kb:3134759
```
Windows Server 2008 R2 SP1 および Windows 7 SP1:
```powershell
wusa /uninstall /kb:3134760
```

### コントロール パネルを使用

1.  <ctype="x-NOTFOUND" mdpre="**" mdpost="**">コントロール パネル</ctype="x-NOTFOUND">を開きます。

2.  <ctype="x-NOTFOUND" mdpre="**" mdpost="**">[プログラム]</ctype="x-NOTFOUND"> を開き、<ctype="x-NOTFOUND" mdpre="**" mdpost="**">[プログラムのアンインストール]</ctype="x-NOTFOUND"> を開きます。

3.  <ctype="x-NOTFOUND" mdpre="**" mdpost="**">[インストールされた更新プログラムを表示]</ctype="x-NOTFOUND"> をクリックします。

4.  インストールされた更新プログラムの一覧から <ctype="x-NOTFOUND" mdpre="**" mdpost="**">[Windows Management Framework 5.0]</ctype="x-NOTFOUND"> を選びます。 これは <ctype="x-NOTFOUND" mdpre="*" mdpost="*">KB3134758</ctype="x-NOTFOUND">、<ctype="x-NOTFOUND" mdpre="*" mdpost="*">KB3134759</ctype="x-NOTFOUND">、または <ctype="x-NOTFOUND" mdpre="*" mdpost="*">KB3134760</ctype="x-NOTFOUND"> に対応しています。 <ctype="x-NOTFOUND" mdpre="**" mdpost="**">[アンインストール]</ctype="x-NOTFOUND"> をクリックします。


<!--HONumber=Mar16_HO4-->


