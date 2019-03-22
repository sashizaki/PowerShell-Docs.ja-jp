---
title: SSH 経由の PowerShell リモート処理
description: SSH を使用した PowerShell Core のリモート処理
ms.date: 08/14/2018
ms.openlocfilehash: 1d7bcb69c7e784bf745cb5c2633106ea53f6226a
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2019
ms.locfileid: "58056534"
---
# <a name="powershell-remoting-over-ssh"></a>SSH 経由の PowerShell リモート処理

## <a name="overview"></a>概要

PowerShell リモート処理では通常、接続交渉とデータ転送に WinRM が使用されます。 SSH が Linux および Windows のプラットフォームで利用可能になり、実際のマルチプラットフォームの PowerShell リモート処理を実行できます。

WinRM は PowerShell リモート処理セッションに堅牢なホスティング モデルを提供します。 SSH ベースのリモート処理では現在、リモート エンドポイント構成および JEA (Just Enough Administration) はサポートされていません。

SSH リモート処理では、Windows コンピューターと Linux コンピューターの間で基本的な PowerShell セッションをリモート処理できます。 SSH リモート処理で、SSH サブシステムとしてターゲット コンピューター上に PowerShell ホスティング プロセスを作成します。
最終的には、エンドポイント構成と JEA をサポートするために、WinRM とほぼ同じ一般的なホスティング モデルが実装される予定です。

現在、`New-PSSession`、`Enter-PSSession`、および `Invoke-Command` コマンドレットには、この新しいリモート処理接続をサポートする新しいパラメーター セットがあります。

```
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

リモート セッションを作成するために、`HostName` パラメーターでターゲット コンピューターを指定し、`UserName` でユーザー名を指定できます。 コマンドレットを対話的に実行する場合は、パスワードの入力を求められます。 また、`KeyFilePath` パラメーターでプライベート キー ファイルを使って、SSH キー認証を使用できます。

## <a name="general-setup-information"></a>一般的なセットアップ情報

SSH はすべてのコンピューターにインストールする必要があります。 コンピューター間でリモート処理を行うには、SSH クライアント (`ssh.exe`) とサーバー (`sshd.exe`) の両方をインストールします。 OpenSSH for Windows が Windows 10 ビルド 1809 と Windows Server 2019 で利用できるようになりました。 詳細については、[Windows 向け OpenSSH](/windows-server/administration/openssh/openssh_overview) に関するページを参照してください。 Linux の場合、お使いのプラットフォームに適した SSH (sshd サーバーを含む) をインストールします。 また、SSH リモート処理の機能を取得するために、GitHub から PowerShell Core をインストールする必要があります。 SSH サーバーは、リモート コンピューター上で PowerShell プロセスをホストする SSH サブシステムを作成するように構成される必要があります。 また、有効なパスワードやキーベースの認証を構成する必要があります。

## <a name="set-up-on-windows-machine"></a>Windows コンピューターでのセットアップ

1. [Windows 向け PowerShell Core](../../install/installing-powershell-core-on-windows.md#msi) の最新版をインストールします

   - `New-PSSession` のパラメーター セットを見れば、SSH リモート処理に対応しているか確認できます

   ```powershell
   Get-Command New-PSSession -syntax
   ```

   ```output
   New-PSSession [-HostName] <string[]> [-Name <string[]>] [-UserName <string>] [-KeyFilePath <string>] [-SSHTransport] [<CommonParameters>]
   ```

2. 最新の Win32 OpenSSH をインストールします。 インストール手順については、「[Installation of OpenSSH](/windows-server/administration/openssh/openssh_install_firstuse)」 (OpenSSH のインストール) を参照してください。
3. `$env:ProgramData\ssh` にある `sshd_config` ファイルを編集します。

   - パスワード認証が有効になっていることを確認します

     ```
     PasswordAuthentication yes
     ```

     ```
     Subsystem    powershell c:/program files/powershell/6/pwsh.exe -sshs -NoLogo -NoProfile
     ```

     > [!NOTE]
     > OpenSSH for Windows にバグがあり、サブシステムの実行可能ファイルのパスでスペースが機能しません。 詳細については、[こちらの GitHub の問題](https://github.com/PowerShell/Win32-OpenSSH/issues/784)のページを参照してください。

     解決策の 1 つは、次のようにスペースが含まれていない PowerShell インストール ディレクトリへのシンボリック リンクを作成することです。

     ```powershell
     mklink /D c:\pwsh "C:\Program Files\PowerShell\6"
     ```

     次に、それを以下のようにサブシステムに入力します。

     ```
     Subsystem    powershell c:\pwsh\pwsh.exe -sshs -NoLogo -NoProfile
     ```

   - 必要であればキー認証を有効にします

     ```
     PubkeyAuthentication yes
     ```

4. sshd サービスを再起動します

   ```powershell
   Restart-Service sshd
   ```

5. OpenSSH がインストールされているパスをパス環境変数に追加します。 たとえば、`C:\Program Files\OpenSSH\` のように指定します。 この項目によって、ssh.exe の場所が認識されます。

## <a name="set-up-on-linux-ubuntu-1404-machine"></a>Linux (Ubuntu 14.04) コンピューターでのセットアップ

1. GitHub から最新の [Linux 向け PowerShell Core](../../install/installing-powershell-core-on-linux.md#ubuntu-1404) ビルドをインストールします
2. 必要に応じて [Ubuntu SSH](https://help.ubuntu.com/lts/serverguide/openssh-server.html) をインストールします

   ```bash
   sudo apt install openssh-client
   sudo apt install openssh-server
   ```

3. /etc/ssh で sshd_config ファイルを編集します

   - パスワード認証が有効になっていることを確認します

   ```
   PasswordAuthentication yes
   ```

   - PowerShell サブシステム エントリを追加します

   ```
   Subsystem powershell /usr/bin/pwsh -sshs -NoLogo -NoProfile
   ```

   - 必要であればキー認証を有効にします

   ```
   PubkeyAuthentication yes
   ```

4. sshd サービスを再起動します

   ```bash
   sudo service sshd restart
   ```

## <a name="set-up-on-macos-machine"></a>MacOS コンピューターでのセットアップ

1. 最新の [MacOS 向け PowerShell Core](../../install/installing-powershell-core-on-macos.md) ビルドをインストールします

   - 次の手順で SSH リモート処理が有効になっていることを確認します
     - `System Preferences` を開きます
     - `Sharing` をクリックします
     - `Remote Login` が `Remote Login: On` になっていることを確認します
     - 適切なユーザーにアクセスを許可します

2. `/private/etc/ssh/sshd_config` で `sshd_config` ファイルを編集します

   - お気に入りのエディターを使用します

     ```bash
     sudo nano /private/etc/ssh/sshd_config
     ```

   - パスワード認証が有効になっていることを確認します

     ```
     PasswordAuthentication yes
     ```

   - PowerShell サブシステム エントリを追加します

     ```
     Subsystem powershell /usr/local/bin/pwsh -sshs -NoLogo -NoProfile
     ```

   - 必要であればキー認証を有効にします

     ```
     PubkeyAuthentication yes
     ```

3. sshd サービスを再起動します

   ```bash
   sudo launchctl stop com.openssh.sshd
   sudo launchctl start com.openssh.sshd
   ```

## <a name="authentication"></a>認証

SSH を使用する PowerShell リモート処理では、SSH クライアントと SSH サービスの間の認証交換に依存し、認証スキーム自体は何も実装されません。
つまり、多要素認証などの構成されている認証スキームはすべて SSH によって処理され、PowerShell とは独立しています。
たとえば、セキュリティ強化のため、公開キー認証に加えて 1 回限りのパスワードを要求するように、SSH サービスを構成できます。
多要素認証の構成については、このドキュメントでは説明されていません。
多要素認証を正しく構成し、PowerShell リモート処理での使用を試みる前に PowerShell の外部での動作を検証する方法については、SSH のドキュメントをご覧ください。

## <a name="powershell-remoting-example"></a>PowerShell リモート処理の例

リモート処理をテストする最も簡単な方法は、1 台のコンピューターでリモート処理を試行することです。 以下の例では、同じ Linux コンピューターに戻るリモート セッションを作成します。 PowerShell コマンドレットを対話的に使用しているので、SSH からホスト コンピューターの確認を求めるプロンプトと、パスワードを求めるプロンプトが表示されています。 Windows コンピューター上で同じ操作を行って、リモート処理が動作していることを確認できます。 その後、ホスト名を変更して、コンピューター間をリモート接続します。

```powershell
#
# Linux to Linux
#
$session = New-PSSession -HostName UbuntuVM1 -UserName TestUser
```

```output
The authenticity of host 'UbuntuVM1 (9.129.17.107)' cannot be established.
ECDSA key fingerprint is SHA256:2kCbnhT2dUE6WCGgVJ8Hyfu1z2wE4lifaJXLO7QJy0Y.
Are you sure you want to continue connecting (yes/no)?
TestUser@UbuntuVM1s password:
```

```powershell
$session
```

```output
 Id Name   ComputerName    ComputerType    State    ConfigurationName     Availability
 -- ----   ------------    ------------    -----    -----------------     ------------
  1 SSH1   UbuntuVM1       RemoteMachine   Opened   DefaultShell             Available
```

```powershell
Enter-PSSession $session
```

```output
[UbuntuVM1]: PS /home/TestUser> uname -a
Linux TestUser-UbuntuVM1 4.2.0-42-generic 49~14.04.1-Ubuntu SMP Wed Jun 29 20:22:11 UTC 2016 x86_64 x86_64 x86_64 GNU/Linux

[UbuntuVM1]: PS /home/TestUser> Exit-PSSession
```

```powershell
Invoke-Command $session -ScriptBlock { Get-Process powershell }
```

```output
Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName                    PSComputerName
-------  ------    -----      -----     ------     --  -- -----------                    --------------
      0       0        0         19       3.23  10635 635 powershell                     UbuntuVM1
      0       0        0         21       4.92  11033 017 powershell                     UbuntuVM1
      0       0        0         20       3.07  11076 076 powershell                     UbuntuVM1
```

```powershell
#
# Linux to Windows
#
Enter-PSSession -HostName WinVM1 -UserName PTestName
```

```output
PTestName@WinVM1s password:
```

```powershell
[WinVM1]: PS C:\Users\PTestName\Documents> cmd /c ver
```

```output
Microsoft Windows [Version 10.0.10586]
```

```powershell
#
# Windows to Windows
#
C:\Users\PSUser\Documents>pwsh.exe
```

```output
PowerShell
Copyright (c) Microsoft Corporation. All rights reserved.
```

```powershell
$session = New-PSSession -HostName WinVM2 -UserName PSRemoteUser
```

```output
The authenticity of host 'WinVM2 (10.13.37.3)' can't be established.
ECDSA key fingerprint is SHA256:kSU6slAROyQVMEynVIXAdxSiZpwDBigpAF/TXjjWjmw.
Are you sure you want to continue connecting (yes/no)?
Warning: Permanently added 'WinVM2,10.13.37.3' (ECDSA) to the list of known hosts.
PSRemoteUser@WinVM2's password:
```

```powershell
$session
```

```output
 Id Name            ComputerName    ComputerType    State         ConfigurationName     Availability
 -- ----            ------------    ------------    -----         -----------------     ------------
  1 SSH1            WinVM2          RemoteMachine   Opened        DefaultShell             Available
```

```powershell
Enter-PSSession -Session $session
```

```output
[WinVM2]: PS C:\Users\PSRemoteUser\Documents> $PSVersionTable

Name                           Value
----                           -----
PSEdition                      Core
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
SerializationVersion           1.1.0.1
BuildVersion                   3.0.0.0
CLRVersion
PSVersion                      6.0.0-alpha
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
GitCommitId                    v6.0.0-alpha.17


[WinVM2]: PS C:\Users\PSRemoteUser\Documents>
```

### <a name="known-issues"></a>の既知の問題

sudo コマンドは、Linux コンピューターへのリモート セッションでは機能しません。

## <a name="see-also"></a>参照

[Windows 向け PowerShell Core](../../install/installing-powershell-core-on-windows.md#msi)

[Linux 向け PowerShell Core](../../install/installing-powershell-core-on-linux.md#ubuntu-1404)

[MacOS 向け PowerShell Core](../../install/installing-powershell-core-on-macos.md)

[Windows 向け OpenSSH](/windows-server/administration/openssh/openssh_overview)

[Ubuntu SSH](https://help.ubuntu.com/lts/serverguide/openssh-server.html)
