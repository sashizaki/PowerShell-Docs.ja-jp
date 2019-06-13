---
title: Windows への PowerShell Core のインストール
description: Windows への PowerShell Core のインストールに関する情報
ms.date: 08/06/2018
ms.openlocfilehash: 3f21761037311891162f1083234edb0aca80d28b
ms.sourcegitcommit: 4ec9e10647b752cc62b1eabb897ada3dc03c93eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "66830225"
---
# <a name="installing-powershell-core-on-windows"></a>Windows への PowerShell Core のインストール

Windows に PowerShell Core をインストールする方法は複数あります。

## <a name="prerequisites"></a>前提条件

WSMan を介して PowerShell のリモート処理を有効にするには、次の前提条件を満たす必要があります。

- Windows 10 以前のバージョンの Windows に [ユニバーサル C ランタイム](https://www.microsoft.com/download/details.aspx?id=50410)をインストールします。 これは、直接ダウンロードすることも、Windows Update 経由で入手することもできます。 (オプション パッケージも含め) 修正プログラムはすべて適用されており、サポート対象のシステムには、これが既にインストールされています。
- Windows Management Framework (WMF) 4.0 以降を Windows 7 と Windows Server 2008 R2 にインストールします。 WMF の詳細については、[WMF の概要](/powershell/wmf/overview)に関する記事を参照してください。

## <a name="a-idmsi-installing-the-msi-package"></a><a id="msi" />MSI パッケージのインストール

PowerShell を Windows クライアントまたは Windows Server にインストールするには (Windows 7 SP1、Server 2008 R2 以降が対象)、Microsoft の GitHub [リリース][releases] ページから MSI パッケージをダウンロードしてください。 インストールするリリースの **[資産]** セクションまで下へスクロールします。 [資産] セクションは折りたたまれている場合があります。その場合は、クリックして展開する必要があります。

MSI ファイルは、`PowerShell-<version>-win-<os-arch>.msi` のようになります。
<!-- TODO: should be updated to point to the Download Center as well -->

ダウンロードしたら、インストーラーをダブルクリックし、プロンプトの指示に従います。

インストーラーにより、Windows の [スタート] メニューにショートカットが作成されます。

- パッケージは、既定で `$env:ProgramFiles\PowerShell\<version>` にインストールされます。
- PowerShell は、スタート メニューまたは  `$env:ProgramFiles\PowerShell\<version>\pwsh.exe` から起動できます。

### <a name="administrative-install-from-the-command-line"></a>コマンド ラインからの管理者インストール

MSI パッケージは、コマンド ラインからインストールできます。 これにより、管理者はユーザーの介入なしでパッケージを展開できます。 PowerShell 用の MSI パッケージには、インストールのオプションを制御するための次のプロパティが含まれます。

- **ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - このプロパティでは、エクスプローラーのコンテキスト メニューに **[Open PowerShell]\(PowerShell を開く\)** 項目を追加するためのオプションを制御します。
- **ENABLE_PSREMOTING** - このプロパティでは、インストール中に PowerShell リモート処理を有効にするためのオプションを制御します。
- **REGISTER_MANIFEST** - このプロパティでは、Windows イベント ログのマニフェストを登録するためのオプションを制御します。

すべてのインストール オプションを有効にして PowerShell Core をサイレント インストールする方法を、次の例に示します。

```powershell
msiexec.exe /package PowerShell-<version>-win-<os-arch>.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

Msiexec.exe 用のコマンド ライン オプションの完全な一覧については、[コマンド ライン オプション](/windows/desktop/Msi/command-line-options)に関するページをご覧ください。

## <a name="a-idzip-installing-the-zip-package"></a><a id="zip" />ZIP パッケージのインストール

PowerShell バイナリ ZIP アーカイブは、高度な展開シナリオ用に用意されています。 なお、ZIP アーカイブを使用する場合、MSI パッケージのような前提条件確認は行われません。 WSMan 経由でのリモート処理を正常に動作させるために、[前提条件](#prerequisites)を満たしていることを確認します。

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
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

3. デバイスに接続してアーカイブを展開します

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

4. PowerShell Core 6 へのリモート処理を設定します

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

5. デバイス上の PowerShell Core 6 エンドポイントに接続します

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
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
4. 「[別のインスタンスのテクニック](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)」の、リモート エンドポイントを作成する手順に従います。

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

- WSMan を使用してリモート処理を行う場合、「[別のインスタンスのテクニック](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)」の、リモート エンドポイントを作成する手順に従います。

## <a name="how-to-create-a-remoting-endpoint"></a>リモート エンドポイントの作成方法

PowerShell Core は、WSMan と SSH の両方で PowerShell Remoting Protocol (PSRP) をサポートしています。 詳細については、次のドキュメントをご覧ください。

- [PowerShell Core での SSH リモート処理][ssh-remoting]
- [PowerShell Core での WSMan リモート処理][wsman-remoting]

<!-- [download-center]: TODO -->

[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
