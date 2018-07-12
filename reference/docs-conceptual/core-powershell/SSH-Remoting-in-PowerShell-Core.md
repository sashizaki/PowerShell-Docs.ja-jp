
# <a name="powershell-remoting-over-ssh"></a>SSH 経由の PowerShell リモート処理

## <a name="overview"></a>概要

PowerShell リモート処理では通常、接続交渉とデータ転送に WinRM が使用されます。
Linux プラットフォームと Windows プラットフォームの両方で利用できるようになったこと、真にマルチプラットフォームな PowerShell リモート処理が可能になることから、このリモート処理の実装には SSH が選択されました。
ただし、WinRM は PowerShell リモート セッションのために堅牢なホスティング モデルも提供します。これは、この実装では現在のところ提供されません。
つまり、PowerShell リモート エンドポイント構成と JEA (Just Enough Administration) はこの実装ではまだサポートされていません。

PowerShell SSH リモート処理では、Windows コンピューターと Linux コンピューターの間で基本的な PowerShell セッションをリモート処理できます。
これは、SSH サブシステムとしてターゲット コンピューター上に PowerShell ホスティング プロセスを作成することで行われます。
エンドポイント構成と JEA に対応するために、最終的には、これは WinRM の動作に似た、より一般的なホスティング モデルに変わります。

現在、`New-PSSession`、`Enter-PSSession`、`Invoke-Command` コマンドレットには、この新しいリモート処理接続を簡単にする新しいパラメーター セットがあります。

```
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

この新しいパラメーター セットはおそらく変更されますが、現在、SSH PSSessions を作成し、コマンド ラインから対話したり、コマンドやスクリプトを呼び出したりできます。
HostName パラメーターでターゲット コンピューターを指定し、UserName でユーザー名を与えることができます。
PowerShell コマンド ラインで対話的にコマンドレットを実行するとき、パスワードが求められます。
ただし、SSH キー認証を利用し、KeyFilePath パラメーターで秘密鍵のファイル パスを指定することもできます。

## <a name="general-setup-information"></a>一般的なセットアップ情報

SSH はあらゆるコンピューターにインストールする必要があります。
コンピューターとの間でリモート処理を行うには、クライアント (`ssh.exe`) とサーバー (`sshd.exe`) の両方をインストールする必要があります。
Windows の場合、[Win32 OpenSSH from GitHub](https://github.com/PowerShell/Win32-OpenSSH/releases) をインストールする必要があります。
Linux の場合、お使いのプラットフォームに適した SSH (sshd サーバーを含む) をインストールする必要があります。
SSH リモート処理機能を備えた最近の PowerShell ビルドまたはパッケージを GitHub から入手する必要もあります。
SSH サブシステムはリモート コンピューター上で PowerShell プロセスを確立するために使用されます。SSH サーバーをそれに合わせて構成する必要があります。
また、パスワード認証と、任意で、キーに基づく認証を有効にする必要があります。

## <a name="setup-on-windows-machine"></a>Windows コンピューターでのセットアップ

1. [Windows 向け PowerShell Core] の最新版をインストールします
   - `New-PSSession` のパラメーター セットを見れば、SSH リモート処理に対応しているか確認できます

   ```powershell
   Get-Command New-PSSession -syntax
   ```

   ```output
   New-PSSession [-HostName] <string[]> [-Name <string[]>] [-UserName <string>] [-KeyFilePath <string>] [-SSHTransport] [<CommonParameters>]
   ```

2. [インストール] の手順を使用して、GitHub から最新の [Win32 OpenSSH] ビルドをインストールします
3. Win32 OpenSSH をインストールした場所で sshd_config ファイルを編集します
   - パスワード認証が有効になっていることを確認します

   ```
   PasswordAuthentication yes
   ```

    ```
    Subsystem    powershell c:/program files/powershell/6.0.0/pwsh.exe -sshs -NoLogo -NoProfile
    ```

    > [!NOTE]
    OpenSSH for Windows にバグがあり、サブシステムの実行可能ファイルのパスでスペースが機能しません。
    この問題の詳細については、GitHub の[こちらのページ](https://github.com/PowerShell/Win32-OpenSSH/issues/784)を参照してください。

    解決策の 1 つは、次のようにスペースが含まれていない PowerShell インストール ディレクトリへのシンボリック リンクを作成することです。

    ```powershell
    mklink /D c:\pwsh "C:\Program Files\PowerShell\6.0.0"
    ```

    次に、それを以下のようにサブシステムに入力します。

    ```
    Subsystem    powershell c:\pwsh\pwsh.exe -sshs -NoLogo -NoProfile
    ```

   ```
   Subsystem    powershell c:/program files/powershell/6.0.0/pwsh.exe -sshs -NoLogo -NoProfile
   ```

   - 必要であればキー認証を有効にします

   ```
   PubkeyAuthentication yes
   ```

4. sshd サービスを再起動します

   ```powershell
   Restart-Service sshd
   ```

5. OpenSSH がインストールされているパスをパス環境変数に追加します
   - `C:\Program Files\OpenSSH\` の行に沿ったものになります
   - これで ssh.exe の場所が認識されます

## <a name="setup-on-linux-ubuntu-1404-machine"></a>Linux (Ubuntu 14.04) コンピューターでのセットアップ

1. GitHub から最新の [Linux 向け PowerShell Core] ビルドをインストールします
2. 必要に応じて [Ubuntu SSH] をインストールします

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

## <a name="setup-on-macos-machine"></a>MacOS コンピューターでのセットアップ

1. 最新の [MacOS 向け PowerShell Core] ビルドをインストールします
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

## <a name="powershell-remoting-example"></a>PowerShell リモート処理の例

リモート処理をテストする最も簡単な方法は、1 台のコンピューターでそれを試すことです。
今回、ある Linux ボックス上の同じコンピューターにリモート セッションを行います。
コマンド プロンプトから PowerShell コマンドレットを使用している点に注目してください。SSH のプロンプトから、ホスト コンピューターを確認するように求められます。また、パスワードも求められます。
ホスト名を変えるだけで、同じことを Windows コンピューターで行い、そのコンピューターで、また、離れているコンピューター間でリモート処理が機能していることを確認できます。

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
 Id Name            ComputerName    ComputerType    State         ConfigurationName     Availability
 -- ----            ------------    ------------    -----         -----------------     ------------
  1 SSH1            UbuntuVM1       RemoteMachine   Opened        DefaultShell             Available
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

- sudo コマンドは、Linux コンピューターへのリモート セッションでは機能しません。

## <a name="see-also"></a>参照

[Windows 向け PowerShell Core](../setup/installing-powershell-core-on-windows.md#msi)

[Linux 向け PowerShell Core](../setup/installing-powershell-core-on-linux.md#ubuntu-1404)

[MacOS 向け PowerShell Core](../setup/installing-powershell-core-on-macos.md)

[Win32 OpenSSH](https://github.com/PowerShell/Win32-OpenSSH/releases)

[インストール](https://github.com/PowerShell/Win32-OpenSSH/wiki/Install-Win32-OpenSSH)

[Ubuntu SSH](https://help.ubuntu.com/lts/serverguide/openssh-server.html)