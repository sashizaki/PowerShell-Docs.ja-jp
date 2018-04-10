# <a name="installing-powershell-core-on-windows"></a>Windows への PowerShell Core のインストール

## <a name="msi"></a>MSI

PowerShell を Windows クライアントまたは Windows Server にインストールするには (Windows 7 SP1、Server 2008 R2 以降で機能)、MSI パッケージを弊社の GitHub [リリース][] ページからダウンロードします。

MSI ファイルは、`PowerShell-6.0.0.<buildversion>.<os-arch>.msi` のようになります。
<!-- TODO: should be updated to point to the Download Center as well -->

ダウンロードしたら、インストーラーをダブルクリックし、プロンプトの指示に従います。

インストールすると [スタート] メニューにショートカットが表示されます。

* パッケージは、既定で `$env:ProgramFiles\PowerShell\` にインストールされます。
* PowerShell は、[スタート] メニューまたは `$env:ProgramFiles\PowerShell\pwsh.exe` から起動できます。

### <a name="prerequisites"></a>前提条件

WSMan を介して PowerShell のリモート処理を有効にするには、次の前提条件を満たす必要があります。

* Windows 10 以前のバージョンの Windows に [ユニバーサル C ランタイム](https://www.microsoft.com/download/details.aspx?id=50410)をインストールします。
  これは、直接ダウンロードすることも、Windows Update 経由で入手することもできます。
  (オプション パッケージも含め) 修正プログラムはすべて適用されており、サポート対象のシステムには、これが既にインストールされています。
* Windows Management Framework (WMF) [4.0](https://www.microsoft.com/download/details.aspx?id=40855) 以降 ([5.1](https://www.microsoft.com/download/details.aspx?id=54616)) を Windows 7 と Windows Server 2008 R2 にインストールします。

## <a name="zip"></a>ZIP

PowerShell バイナリ ZIP アーカイブは、高度な展開シナリオ用に用意されています。
なお、ZIP アーカイブを使用する場合、MSI パッケージのような前提条件確認は行われません。
したがって、Windows 10 以前のバージョンで WSMan 経由でのリモート処理が正常に動作するには、[前提条件](#prerequisites)が満たされていることを確認する必要があります。

## <a name="deploying-on-nano-server"></a>Nano Server への展開

これらの手順では、Nano Server イメージ上で PowerShell のバージョンが既に実行されており、それが [Nano Server Image Builder](https://technet.microsoft.com/windows-server-docs/get-started/deploy-nano-server) で生成されていることを前提としています。
Nano Server は、"ヘッドレス" OS であり、PowerShell Core バイナリは次の 2 つの方法で展開できます。

1. オフライン: Nano Server VHD をマウントし、zip ファイルの中身をマウント イメージ内の選択した場所に展開します。
1. オンライン: zip ファイルを PowerShell セッションを介して転送し、選択した場所にそれを展開します。

いずれの場合も、Windows 10 x64 Zip リリース パッケージが必要であり、"管理者" PowerShell インスタンス内でコマンドを実行する必要があります。

### <a name="offline-deployment-of-powershell-core"></a>PowerShell Core のオフラインでの展開

1. お好みの zip ユーティリティを使用して、マウントされた Nano Server イメージ内のディレクトリにパッケージを解凍します。
1. イメージをマウント解除し、ブートします。
1. Windows PowerShell のインボックス インスタンスに接続します。
1. [別のインスタンスのテクニック](#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)の、リモート エンドポイントを作成する手順に従います。

### <a name="online-deployment-of-powershell-core"></a>オンラインでの PowerShell Core の展開

次の手順では、PowerShell Core を Nano Server の実行中のインスタンスに展開し、そのリモート エンドポイントを構成します。

* Windows PowerShell のインボックス インスタンスに接続する

```powershell
$session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
```

* Nano Server のインスタンスにファイルをコピーする

```powershell
Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
```

* セッションに入る

```powershell
Enter-PSSession $session
```

* ZIP ファイルを抽出する

```powershell
# Insert the appropriate version.
Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShellCore_<version>"
```

* WSMan を使用してリモート処理を行う場合、[別のインスタンスのテクニック](../core-powershell/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)の、リモート エンドポイントを作成する手順に従います。

## <a name="instructions-to-create-a-remoting-endpoint"></a>リモート エンドポイントの作成手順

PowerShell Core は、WSMan と SSH の両方で PowerShell Remoting Protocol (PSRP) をサポートしています。 詳細については、次のドキュメントをご覧ください。

* [PowerShell Core での SSH リモート処理][ssh-remoting]
* [PowerShell Core での WSMan リモート処理][wsman-remoting]

## <a name="artifact-installation-instructions"></a>成果物のインストール手順

アーカイブは CoreCLR ビットを使用して各 CI ビルドに [AppVeyor][] で公開します。

## <a name="coreclr-artifacts"></a>CoreCLR の成果物

* 特定のビルドの **[artifacts]\(成果物\)** タブから、zip パッケージをダウンロードします。
* [エクスプローラー] で右クリックし、[プロパティ] をクリックし、[ブロックの解除] ボックスをオンにして zip ファイルのブロックを解除します。
* zip ファイルを `bin` ディレクトリに抽出します
* `./bin/pwsh.exe`

<!-- [download-center]: TODO -->
[リリース]: https://github.com/PowerShell/PowerShell/releases
[signing]: ../../tools/Sign-Package.ps1
[ssh-remoting]: ../core-powershell/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../core-powershell/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell