# <a name="powershell-remoting-over-ssh"></a><span data-ttu-id="9f294-101">SSH 経由の PowerShell リモート処理</span><span class="sxs-lookup"><span data-stu-id="9f294-101">PowerShell Remoting Over SSH</span></span>

## <a name="overview"></a><span data-ttu-id="9f294-102">概要</span><span class="sxs-lookup"><span data-stu-id="9f294-102">Overview</span></span>

<span data-ttu-id="9f294-103">PowerShell リモート処理では通常、接続交渉とデータ転送に WinRM が使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f294-103">PowerShell remoting normally uses WinRM for connection negotiation and data transport.</span></span>
<span data-ttu-id="9f294-104">Linux プラットフォームと Windows プラットフォームの両方で利用できるようになったこと、真にマルチプラットフォームな PowerShell リモート処理が可能になることから、このリモート処理の実装には SSH が選択されました。</span><span class="sxs-lookup"><span data-stu-id="9f294-104">SSH was chosen for this remoting implementation since it is now available for both Linux and Windows platforms and allows true multiplatform PowerShell remoting.</span></span>
<span data-ttu-id="9f294-105">ただし、WinRM は PowerShell リモート セッションのために堅牢なホスティング モデルも提供します。これは、この実装では現在のところ提供されません。</span><span class="sxs-lookup"><span data-stu-id="9f294-105">However, WinRM also provides a robust hosting model for PowerShell remote sessions which this implementation does not yet do.</span></span>
<span data-ttu-id="9f294-106">つまり、PowerShell リモート エンドポイント構成と JEA (Just Enough Administration) はこの実装ではまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9f294-106">And this means that PowerShell remote endpoint configuration and JEA (Just Enough Administration) is not yet supported in this implementation.</span></span>

<span data-ttu-id="9f294-107">PowerShell SSH リモート処理では、Windows コンピューターと Linux コンピューターの間で基本的な PowerShell セッションをリモート処理できます。</span><span class="sxs-lookup"><span data-stu-id="9f294-107">PowerShell SSH remoting lets you do basic PowerShell session remoting between Windows and Linux machines.</span></span>
<span data-ttu-id="9f294-108">これは、SSH サブシステムとしてターゲット コンピューター上に PowerShell ホスティング プロセスを作成することで行われます。</span><span class="sxs-lookup"><span data-stu-id="9f294-108">This is done by creating a PowerShell hosting process on the target machine as an SSH subsystem.</span></span>
<span data-ttu-id="9f294-109">エンドポイント構成と JEA に対応するために、最終的には、これは WinRM の動作に似た、より一般的なホスティング モデルに変わります。</span><span class="sxs-lookup"><span data-stu-id="9f294-109">Eventually this will be changed to a more general hosting model similar to how WinRM works in order to support endpoint configuration and JEA.</span></span>

<span data-ttu-id="9f294-110">コマンドレットの New-PSSession、Enter-PSSession、Invoke-Command には現在、この新しいリモート処理接続を簡単にする新しいパラメーター セットがあります。</span><span class="sxs-lookup"><span data-stu-id="9f294-110">The New-PSSession, Enter-PSSession and Invoke-Command cmdlets now have a new parameter set to facilitate this new remoting connection</span></span>

```powershell
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

<span data-ttu-id="9f294-111">この新しいパラメーター セットはおそらく変更されますが、現在、SSH PSSessions を作成し、コマンド ラインから対話したり、コマンドやスクリプトを呼び出したりできます。</span><span class="sxs-lookup"><span data-stu-id="9f294-111">This new parameter set will likely change but for now allows you to create SSH PSSessions that you can interact with from the command line or invoke commands and scripts on.</span></span>
<span data-ttu-id="9f294-112">HostName パラメーターでターゲット コンピューターを指定し、UserName でユーザー名を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="9f294-112">You specify the target machine with the HostName parameter and provide the user name with UserName.</span></span>
<span data-ttu-id="9f294-113">PowerShell コマンド ラインで対話的にコマンドレットを実行するとき、パスワードが求められます。</span><span class="sxs-lookup"><span data-stu-id="9f294-113">When running the cmdlets interactively at the PowerShell command line you will be prompted for a password.</span></span>
<span data-ttu-id="9f294-114">ただし、SSH キー認証を利用し、KeyFilePath パラメーターで秘密鍵のファイル パスを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="9f294-114">But you also have the option to use SSH key authentication and provide a private key file path with the KeyFilePath parameter.</span></span>

## <a name="general-setup-information"></a><span data-ttu-id="9f294-115">一般的なセットアップ情報</span><span class="sxs-lookup"><span data-stu-id="9f294-115">General setup information</span></span>

<span data-ttu-id="9f294-116">SSH はあらゆるコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f294-116">SSH is required to be installed on all machines.</span></span>
<span data-ttu-id="9f294-117">コンピューターとの間でリモート処理を行うには、クライアント (ssh.exe) とサーバー (sshd.exe) の両方をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f294-117">You should install both client (ssh.exe) and server (sshd.exe) so that you can experiment with remoting to and from the machines.</span></span>
<span data-ttu-id="9f294-118">Windows の場合、[Win32 OpenSSH from GitHub](https://github.com/PowerShell/Win32-OpenSSH/releases) をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f294-118">For Windows you will need to install [Win32 OpenSSH from GitHub](https://github.com/PowerShell/Win32-OpenSSH/releases).</span></span>
<span data-ttu-id="9f294-119">Linux の場合、お使いのプラットフォームに適した SSH (sshd サーバーを含む) をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f294-119">For Linux you will need to install SSH (including sshd server) appropriate to your platform.</span></span>
<span data-ttu-id="9f294-120">SSH リモート処理機能を備えた最近の PowerShell ビルドまたはパッケージを GitHub から入手する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="9f294-120">You will also need a recent PowerShell build or package from GitHub having the SSH remoting feature.</span></span>
<span data-ttu-id="9f294-121">SSH サブシステムはリモート コンピューター上で PowerShell プロセスを確立するために使用されます。SSH サーバーをそれに合わせて構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f294-121">SSH subsystems is used to establish a PowerShell process on the remote machine and the SSH server will need to be configured for that.</span></span>
<span data-ttu-id="9f294-122">また、パスワード認証と、任意で、キーに基づく認証を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f294-122">In addition you will need to enable password authentication and optionally key based authentication.</span></span>

## <a name="setup-on-windows-machine"></a><span data-ttu-id="9f294-123">Windows コンピューターでのセットアップ</span><span class="sxs-lookup"><span data-stu-id="9f294-123">Setup on Windows Machine</span></span>

1. <span data-ttu-id="9f294-124">[Windows 向け PowerShell Core] の最新版をインストールします</span><span class="sxs-lookup"><span data-stu-id="9f294-124">Install the latest version of [PowerShell Core for Windows]</span></span>
    - <span data-ttu-id="9f294-125">New-PSSession のパラメーター セットを見れば、SSH リモート処理に対応しているか確認できます</span><span class="sxs-lookup"><span data-stu-id="9f294-125">You can tell if it has the SSH remoting support by looking at the parameter sets for New-PSSession</span></span>

    ```powershell
    PS> Get-Command New-PSSession -syntax
    New-PSSession [-HostName] <string[]> [-Name <string[]>] [-UserName <string>] [-KeyFilePath <string>] [-SSHTransport] [<CommonParameters>]
    ```

1. <span data-ttu-id="9f294-126">GitHub から最新の [Win32 OpenSSH] ビルドをインストールします (インストール方法は[ここ]で確認できます)</span><span class="sxs-lookup"><span data-stu-id="9f294-126">Install the latest [Win32 OpenSSH] build from GitHub using the [installation] instructions</span></span>
1. <span data-ttu-id="9f294-127">Win32 OpenSSH をインストールした場所で sshd_config ファイルを編集します</span><span class="sxs-lookup"><span data-stu-id="9f294-127">Edit the sshd_config file at the location where you installed Win32 OpenSSH</span></span>
    - <span data-ttu-id="9f294-128">パスワード認証が有効になっていることを確認します</span><span class="sxs-lookup"><span data-stu-id="9f294-128">Make sure password authentication is enabled</span></span>

    ```
    PasswordAuthentication yes
    ```

    - <span data-ttu-id="9f294-129">PowerShell サブシステム エントリを追加し、自分が使用するバージョンのパスに `c:/program files/powershell/6.0.0/pwsh.exe` を変更します</span><span class="sxs-lookup"><span data-stu-id="9f294-129">Add a PowerShell subsystem entry, replace `c:/program files/powershell/6.0.0/pwsh.exe` with the correct path to the version you want to use</span></span>

    ```
    Subsystem    powershell c:/program files/powershell/6.0.0/pwsh.exe -sshs -NoLogo -NoProfile
    ```

    - <span data-ttu-id="9f294-130">必要であればキー認証を有効にします</span><span class="sxs-lookup"><span data-stu-id="9f294-130">Optionally enable key authentication</span></span>

    ```
    PubkeyAuthentication yes
    ```

1. <span data-ttu-id="9f294-131">sshd サービスを再起動します</span><span class="sxs-lookup"><span data-stu-id="9f294-131">Restart the sshd service</span></span>

    ```powershell
    Restart-Service sshd
    ```

1. <span data-ttu-id="9f294-132">OpenSSH がインストールされているパスをパス環境変数に追加します</span><span class="sxs-lookup"><span data-stu-id="9f294-132">Add the path where OpenSSH is installed to your Path Env Variable</span></span>
    - <span data-ttu-id="9f294-133">`C:\Program Files\OpenSSH\` の行に沿ったものになります</span><span class="sxs-lookup"><span data-stu-id="9f294-133">This should be along the lines of `C:\Program Files\OpenSSH\`</span></span>
    - <span data-ttu-id="9f294-134">これで ssh.exe の場所が認識されます</span><span class="sxs-lookup"><span data-stu-id="9f294-134">This allows for the ssh.exe to be found</span></span>

## <a name="setup-on-linux-ubuntu-1404-machine"></a><span data-ttu-id="9f294-135">Linux (Ubuntu 14.04) コンピューターでのセットアップ</span><span class="sxs-lookup"><span data-stu-id="9f294-135">Setup on Linux (Ubuntu 14.04) Machine</span></span>

1. <span data-ttu-id="9f294-136">GitHub から最新の [PowerShell for Linux] ビルドをインストールします</span><span class="sxs-lookup"><span data-stu-id="9f294-136">Install the latest [PowerShell for Linux] build from GitHub</span></span>
1. <span data-ttu-id="9f294-137">必要に応じて [Ubuntu SSH] をインストールします</span><span class="sxs-lookup"><span data-stu-id="9f294-137">Install [Ubuntu SSH] as needed</span></span>

    ```bash
    sudo apt install openssh-client
    sudo apt install openssh-server
    ```

1. <span data-ttu-id="9f294-138">/etc/ssh で sshd_config ファイルを編集します</span><span class="sxs-lookup"><span data-stu-id="9f294-138">Edit the sshd_config file at location /etc/ssh</span></span>
    - <span data-ttu-id="9f294-139">パスワード認証が有効になっていることを確認します</span><span class="sxs-lookup"><span data-stu-id="9f294-139">Make sure password authentication is enabled</span></span>

    ```
    PasswordAuthentication yes
    ```

    - <span data-ttu-id="9f294-140">PowerShell サブシステム エントリを追加します</span><span class="sxs-lookup"><span data-stu-id="9f294-140">Add a PowerShell subsystem entry</span></span>

    ```
    Subsystem powershell /usr/bin/pwsh -sshs -NoLogo -NoProfile
    ```

    - <span data-ttu-id="9f294-141">必要であればキー認証を有効にします</span><span class="sxs-lookup"><span data-stu-id="9f294-141">Optionally enable key authentication</span></span>

    ```
    PubkeyAuthentication yes
    ```

1. <span data-ttu-id="9f294-142">sshd サービスを再起動します</span><span class="sxs-lookup"><span data-stu-id="9f294-142">Restart the sshd service</span></span>

    ```bash
    sudo service sshd restart
    ```

## <a name="setup-on-macos-machine"></a><span data-ttu-id="9f294-143">MacOS コンピューターでのセットアップ</span><span class="sxs-lookup"><span data-stu-id="9f294-143">Setup on MacOS Machine</span></span>

1. <span data-ttu-id="9f294-144">最新の [PowerShell for MacOS] ビルドをインストールします</span><span class="sxs-lookup"><span data-stu-id="9f294-144">Install the latest [PowerShell for MacOS] build</span></span>
    - <span data-ttu-id="9f294-145">次の手順で SSH リモート処理が有効になっていることを確認します</span><span class="sxs-lookup"><span data-stu-id="9f294-145">Make sure SSH Remoting is enabled by following these steps:</span></span>
      - <span data-ttu-id="9f294-146">`System Preferences` を開きます</span><span class="sxs-lookup"><span data-stu-id="9f294-146">Open `System Preferences`</span></span>
      - <span data-ttu-id="9f294-147">`Sharing` をクリックします</span><span class="sxs-lookup"><span data-stu-id="9f294-147">Click on `Sharing`</span></span>
      - <span data-ttu-id="9f294-148">`Remote Login` が `Remote Login: On` になっていることを確認します</span><span class="sxs-lookup"><span data-stu-id="9f294-148">Check `Remote Login` - Should say `Remote Login: On`</span></span>
      - <span data-ttu-id="9f294-149">適切なユーザーにアクセスを許可します</span><span class="sxs-lookup"><span data-stu-id="9f294-149">Allow access to appropriate users</span></span>
1. <span data-ttu-id="9f294-150">`/private/etc/ssh/sshd_config` で `sshd_config` ファイルを編集します</span><span class="sxs-lookup"><span data-stu-id="9f294-150">Edit the `sshd_config` file at location `/private/etc/ssh/sshd_config`</span></span>
    - <span data-ttu-id="9f294-151">お気に入りのエディターを使用します</span><span class="sxs-lookup"><span data-stu-id="9f294-151">Use your favorite editor or</span></span>

    ```bash
    sudo nano /private/etc/ssh/sshd_config
    ```

    - <span data-ttu-id="9f294-152">パスワード認証が有効になっていることを確認します</span><span class="sxs-lookup"><span data-stu-id="9f294-152">Make sure password authentication is enabled</span></span>

    ```
    PasswordAuthentication yes
    ```

    - <span data-ttu-id="9f294-153">PowerShell サブシステム エントリを追加します</span><span class="sxs-lookup"><span data-stu-id="9f294-153">Add a PowerShell subsystem entry</span></span>

    ```
    Subsystem powershell /usr/local/bin/powershell -sshs -NoLogo -NoProfile
    ```

    - <span data-ttu-id="9f294-154">必要であればキー認証を有効にします</span><span class="sxs-lookup"><span data-stu-id="9f294-154">Optionally enable key authentication</span></span>

    ```
    PubkeyAuthentication yes
    ```

1. <span data-ttu-id="9f294-155">sshd サービスを再起動します</span><span class="sxs-lookup"><span data-stu-id="9f294-155">Restart the sshd service</span></span>

    ```bash
    sudo launchctl stop com.openssh.sshd
    sudo launchctl start com.openssh.sshd
    ```

## <a name="powershell-remoting-example"></a><span data-ttu-id="9f294-156">PowerShell リモート処理の例</span><span class="sxs-lookup"><span data-stu-id="9f294-156">PowerShell Remoting Example</span></span>

<span data-ttu-id="9f294-157">リモート処理をテストする最も簡単な方法は、1 台のコンピューターでそれを試すことです。</span><span class="sxs-lookup"><span data-stu-id="9f294-157">The easiest way to test remoting is to just try it on a single machine.</span></span>
<span data-ttu-id="9f294-158">今回、ある Linux ボックス上の同じコンピューターにリモート セッションを行います。</span><span class="sxs-lookup"><span data-stu-id="9f294-158">Here I will create a remote session back to the same machine on a Linux box.</span></span>
<span data-ttu-id="9f294-159">コマンド プロンプトから PowerShell コマンドレットを使用している点に注目してください。SSH のプロンプトから、ホスト コンピューターを確認するように求められます。また、パスワードも求められます。</span><span class="sxs-lookup"><span data-stu-id="9f294-159">Notice that I am using PowerShell cmdlets from a command prompt so we see prompts from SSH asking to verify the host computer as well as password prompts.</span></span>
<span data-ttu-id="9f294-160">ホスト名を変えるだけで、同じことを Windows コンピューターで行い、そのコンピューターで、また、離れているコンピューター間でリモート処理が機能していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9f294-160">You can do the same thing on a Windows machine to ensure remoting is working there and then remote between machines by simply changing the host name.</span></span>

```powershell
#
# Linux to Linux
#
PS /home/TestUser> $session = New-PSSession -HostName UbuntuVM1 -UserName TestUser
The authenticity of host 'UbuntuVM1 (9.129.17.107)' cannot be established.
ECDSA key fingerprint is SHA256:2kCbnhT2dUE6WCGgVJ8Hyfu1z2wE4lifaJXLO7QJy0Y.
Are you sure you want to continue connecting (yes/no)?
TestUser@UbuntuVM1s password:

PS /home/TestUser> $session

 Id Name            ComputerName    ComputerType    State         ConfigurationName     Availability
 -- ----            ------------    ------------    -----         -----------------     ------------
  1 SSH1            UbuntuVM1       RemoteMachine   Opened        DefaultShell             Available

PS /home/TestUser> Enter-PSSession $session

[UbuntuVM1]: PS /home/TestUser> uname -a
Linux TestUser-UbuntuVM1 4.2.0-42-generic 49~14.04.1-Ubuntu SMP Wed Jun 29 20:22:11 UTC 2016 x86_64 x86_64 x86_64 GNU/Linux

[UbuntuVM1]: PS /home/TestUser> Exit-PSSession

PS /home/TestUser> Invoke-Command $session -ScriptBlock { Get-Process powershell }

Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName                    PSComputerName
-------  ------    -----      -----     ------     --  -- -----------                    --------------
      0       0        0         19       3.23  10635 635 powershell                     UbuntuVM1
      0       0        0         21       4.92  11033 017 powershell                     UbuntuVM1
      0       0        0         20       3.07  11076 076 powershell                     UbuntuVM1


#
# Linux to Windows
#
PS /home/TestUser> Enter-PSSession -HostName WinVM1 -UserName PTestName
PTestName@WinVM1s password:

[WinVM1]: PS C:\Users\PTestName\Documents> cmd /c ver

Microsoft Windows [Version 10.0.10586]

[WinVM1]: PS C:\Users\PTestName\Documents>

#
# Windows to Windows
#
C:\Users\PSUser\Documents>pwsh.exe
PowerShell
Copyright (c) Microsoft Corporation. All rights reserved.

PS C:\Users\PSUser\Documents> $session = New-PSSession -HostName WinVM2 -UserName PSRemoteUser
The authenticity of host 'WinVM2 (10.13.37.3)' can't be established.
ECDSA key fingerprint is SHA256:kSU6slAROyQVMEynVIXAdxSiZpwDBigpAF/TXjjWjmw.
Are you sure you want to continue connecting (yes/no)?
Warning: Permanently added 'WinVM2,10.13.37.3' (ECDSA) to the list of known hosts.
PSRemoteUser@WinVM2's password:
PS C:\Users\PSUser\Documents> $session

 Id Name            ComputerName    ComputerType    State         ConfigurationName     Availability
 -- ----            ------------    ------------    -----         -----------------     ------------
  1 SSH1            WinVM2          RemoteMachine   Opened        DefaultShell             Available


PS C:\Users\PSUser\Documents> Enter-PSSession -Session $session
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

### <a name="known-issues"></a><span data-ttu-id="9f294-161">の既知の問題</span><span class="sxs-lookup"><span data-stu-id="9f294-161">Known Issues</span></span>

1. <span data-ttu-id="9f294-162">sudo コマンドは、Linux コンピューターへのリモート セッションでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="9f294-162">sudo command does not work in remote session to Linux machine.</span></span>

[Windows 向け PowerShell Core]: https://github.com/PowerShell/PowerShell/blob/master/docs/installation/windows.md#msi
[PowerShell Core for Windows]: https://github.com/PowerShell/PowerShell/blob/master/docs/installation/windows.md#msi
[Win32 OpenSSH]: https://github.com/PowerShell/Win32-OpenSSH
[ここ]: https://github.com/PowerShell/Win32-OpenSSH/wiki/Install-Win32-OpenSSH
[installation]: https://github.com/PowerShell/Win32-OpenSSH/wiki/Install-Win32-OpenSSH
[PowerShell for Linux]: https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#ubuntu-1404
[Ubuntu SSH]: https://help.ubuntu.com/lts/serverguide/openssh-server.html
[PowerShell for MacOS]: https://github.com/PowerShell/PowerShell/blob/master/docs/installation/macos.md#macos-1012