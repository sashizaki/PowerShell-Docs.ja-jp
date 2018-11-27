---
title: Windows への PowerShell Core のインストール
description: Windows への PowerShell Core のインストールに関する情報
ms.date: 08/06/2018
ms.openlocfilehash: ba159a69df7e117e90e21dd26228b61146260475
ms.sourcegitcommit: 221b7daab7f597f8b2e4864cf9b5d9dda9b9879b
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2018
ms.locfileid: "52320893"
---
# <a name="installing-powershell-core-on-windows"></a>Windows への PowerShell Core のインストール

## <a name="msi"></a>MSI

PowerShell を Windows クライアントまたは Windows Server にインストールするには (Windows 7 SP1、Server 2008 R2 以降で機能)、MSI パッケージを弊社の GitHub [リリース][] ページからダウンロードします。

MSI ファイルは、`PowerShell-<version>-win-<os-arch>.msi`
<!-- TODO: should be updated to point to the Download Center as well --> のようになります。

ダウンロードしたら、インストーラーをダブルクリックし、プロンプトの指示に従います。

インストールすると [スタート] メニューにショートカットが表示されます。

- パッケージは、既定で `$env:ProgramFiles\PowerShell\<version>` にインストールされます。
- PowerShell は、スタート メニューまたは  `$env:ProgramFiles\PowerShell\<version>\pwsh.exe` から起動できます。

### <a name="prerequisites"></a>前提条件

WSMan を介して PowerShell のリモート処理を有効にするには、次の前提条件を満たす必要があります。

- Windows 10 以前のバージョンの Windows に [ユニバーサル C ランタイム](https://www.microsoft.com/download/details.aspx?id=50410)をインストールします。
  これは、直接ダウンロードすることも、Windows Update 経由で入手することもできます。
  (オプション パッケージも含め) 修正プログラムはすべて適用されており、サポート対象のシステムには、これが既にインストールされています。
- Windows Management Framework (WMF) 4.0 以降を Windows 7 と Windows Server 2008 R2 にインストールします。

## <a name="zip"></a>ZIP

PowerShell バイナリ ZIP アーカイブは、高度な展開シナリオ用に用意されています。
なお、ZIP アーカイブを使用する場合、MSI パッケージのような前提条件確認は行われません。
したがって、Windows 10 以前のバージョンで WSMan 経由でのリモート処理が正常に動作するには、[前提条件](#prerequisites)が満たされていることを確認する必要があります。

## <a name="deploying-on-windows-iot"></a>Windows IoT への展開

Windows IoT には既に Windows PowerShell が付属しており、PowerShell Core 6 の展開に使用します。

1. ターゲット デバイスに対して `PSSession` を作成します

   ```powershell
   $s = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

2. ZIP パッケージをデバイスにコピーします

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-6.1.0-win-arm32.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

3. デバイスに接続してアーカイブを展開します

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-6.1.0-win-arm32.zip
   ```

4. PowerShell Core 6 へのリモート処理を設定します

   ```powershell
   Set-Location .\PowerShell-6.1.0-win-arm32
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

5. デバイス上の PowerShell Core 6 エンドポイントに接続します

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.6.1.0
   ```

## <a name="deploying-on-nano-server"></a>Nano Server への展開

これらの手順では、Nano Server イメージ上で PowerShell のバージョンが既に実行されており、それが [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) で生成されていることを前提としています。
Nano Server は "ヘッドレス" OS です。 コア バイナリを展開するには、2 つの方法があります。

1. オフライン: Nano Server VHD をマウントし、zip ファイルの中身をマウント イメージ内の選択した場所に展開します。
2. オンライン: zip ファイルを PowerShell セッションを介して転送し、選択した場所にそれを展開します。

いずれの場合も、Windows 10 x64 ZIP リリース パッケージが必要であり、"管理者" PowerShell インスタンス内でコマンドを実行する必要があります。

### <a name="offline-deployment-of-powershell-core"></a>PowerShell Core のオフラインでの展開

1. お好みの zip ユーティリティを使用して、マウントされた Nano Server イメージ内のディレクトリにパッケージを解凍します。
2. イメージをマウント解除し、ブートします。
3. Windows PowerShell のインボックス インスタンスに接続します。
4. 「[別のインスタンスのテクニック](../core-powershell/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)」の、リモート エンドポイントを作成する手順に従います。

### <a name="online-deployment-of-powershell-core"></a>オンラインでの PowerShell Core の展開

次の手順では、PowerShell Core を Nano Server の実行中のインスタンスに展開し、そのリモート エンドポイントを構成します。

- Windows PowerShell のインボックス インスタンスに接続する

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- Nano Server のインスタンスにファイルをコピーする

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- セッションに入る

  ```powershell
  Enter-PSSession $session
  ```

- ZIP ファイルを抽出する

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShellCore_<version>"
  ```

- WSMan を使用してリモート処理を行う場合、「[別のインスタンスのテクニック](../core-powershell/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)」の、リモート エンドポイントを作成する手順に従います。

## <a name="instructions-to-create-a-remoting-endpoint"></a>リモート エンドポイントの作成手順

PowerShell Core は、WSMan と SSH の両方で PowerShell Remoting Protocol (PSRP) をサポートしています。
詳細については、次のドキュメントをご覧ください。

- [PowerShell Core での SSH リモート処理][ssh-remoting]
- [PowerShell Core での WSMan リモート処理][wsman-remoting]

## <a name="artifact-installation-instructions"></a>成果物のインストール手順

アーカイブは CoreCLR ビットを使用して各 CI ビルドに [AppVeyor][] で公開します。

CoreCLR のアーティファクトから PowerShell Core をインストールするには:

1. 特定のビルドの **[アーティファクト]** タブから、zip パッケージをダウンロードします。
2. [エクスプローラー] で右クリックし、[プロパティ] をクリックし、[ブロックの解除] ボックスをオンにして ZIP ファイルのブロックを解除します。
3. zip ファイルを `bin` ディレクトリに抽出します
4. `./bin/pwsh.exe`

<!-- [download-center]: TODO -->

[リリース]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../core-powershell/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../core-powershell/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
