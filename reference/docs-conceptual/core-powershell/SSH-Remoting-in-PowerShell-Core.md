---
title: SSH 経由の PowerShell リモート処理
description: SSH を使用した PowerShell Core のリモート処理
ms.date: 08/06/2018
ms.openlocfilehash: 27a8fc5623796a270a2ea67aa550c9a0998e766b
ms.sourcegitcommit: 01ac77cd0b00e4e5e964504563a9212e8002e5e0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39587501"
---
# <a name="powershell-remoting-over-ssh"></a><span data-ttu-id="65be8-103">SSH 経由の PowerShell リモート処理</span><span class="sxs-lookup"><span data-stu-id="65be8-103">PowerShell Remoting Over SSH</span></span>

## <a name="overview"></a><span data-ttu-id="65be8-104">概要</span><span class="sxs-lookup"><span data-stu-id="65be8-104">Overview</span></span>

<span data-ttu-id="65be8-105">PowerShell リモート処理では通常、接続交渉とデータ転送に WinRM が使用されます。</span><span class="sxs-lookup"><span data-stu-id="65be8-105">PowerShell remoting normally uses WinRM for connection negotiation and data transport.</span></span> <span data-ttu-id="65be8-106">Linux プラットフォームと Windows プラットフォームの両方で利用できるようになったこと、真にマルチプラットフォームな PowerShell リモート処理が可能になることから、このリモート処理の実装には SSH が選択されました。</span><span class="sxs-lookup"><span data-stu-id="65be8-106">SSH was chosen for this remoting implementation since it is now available for both Linux and Windows platforms and allows true multiplatform PowerShell remoting.</span></span> <span data-ttu-id="65be8-107">ただし、WinRM は PowerShell リモート セッションのために堅牢なホスティング モデルも提供します。これは、この実装では現在のところ提供されません。</span><span class="sxs-lookup"><span data-stu-id="65be8-107">However, WinRM also provides a robust hosting model for PowerShell remote sessions which this implementation does not yet do.</span></span> <span data-ttu-id="65be8-108">つまり、PowerShell リモート エンドポイント構成と JEA (Just Enough Administration) はこの実装ではまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="65be8-108">And this means that PowerShell remote endpoint configuration and JEA (Just Enough Administration) is not yet supported in this implementation.</span></span>

<span data-ttu-id="65be8-109">PowerShell SSH リモート処理では、Windows コンピューターと Linux コンピューターの間で基本的な PowerShell セッションをリモート処理できます。</span><span class="sxs-lookup"><span data-stu-id="65be8-109">PowerShell SSH remoting lets you do basic PowerShell session remoting between Windows and Linux machines.</span></span> <span data-ttu-id="65be8-110">これは、SSH サブシステムとしてターゲット コンピューター上に PowerShell ホスティング プロセスを作成することで行われます。</span><span class="sxs-lookup"><span data-stu-id="65be8-110">This is done by creating a PowerShell hosting process on the target machine as an SSH subsystem.</span></span> <span data-ttu-id="65be8-111">エンドポイント構成と JEA に対応するために、最終的には、これは WinRM の動作に似た、より一般的なホスティング モデルに変わります。</span><span class="sxs-lookup"><span data-stu-id="65be8-111">Eventually this will be changed to a more general hosting model similar to how WinRM works in order to support endpoint configuration and JEA.</span></span>

<span data-ttu-id="65be8-112">現在、`New-PSSession`、`Enter-PSSession`、`Invoke-Command` コマンドレットには、この新しいリモート処理接続を簡単にする新しいパラメーター セットがあります。</span><span class="sxs-lookup"><span data-stu-id="65be8-112">The `New-PSSession`, `Enter-PSSession` and `Invoke-Command` cmdlets now have a new parameter set to facilitate this new remoting connection</span></span>

```
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

<span data-ttu-id="65be8-113">この新しいパラメーター セットはおそらく変更されますが、現在、SSH PSSessions を作成し、コマンド ラインから対話したり、コマンドやスクリプトを呼び出したりできます。</span><span class="sxs-lookup"><span data-stu-id="65be8-113">This new parameter set will likely change but for now allows you to create SSH PSSessions that you can interact with from the command line or invoke commands and scripts on.</span></span> <span data-ttu-id="65be8-114">HostName パラメーターでターゲット コンピューターを指定し、UserName でユーザー名を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="65be8-114">You specify the target machine with the HostName parameter and provide the user name with UserName.</span></span> <span data-ttu-id="65be8-115">PowerShell コマンド ラインで対話的にコマンドレットを実行するとき、パスワードが求められます。</span><span class="sxs-lookup"><span data-stu-id="65be8-115">When running the cmdlets interactively at the PowerShell command line you will be prompted for a password.</span></span> <span data-ttu-id="65be8-116">ただし、SSH キー認証を利用し、KeyFilePath パラメーターで秘密鍵のファイル パスを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="65be8-116">But you also have the option to use SSH key authentication and provide a private key file path with the KeyFilePath parameter.</span></span>

## <a name="general-setup-information"></a><span data-ttu-id="65be8-117">一般的なセットアップ情報</span><span class="sxs-lookup"><span data-stu-id="65be8-117">General setup information</span></span>

<span data-ttu-id="65be8-118">SSH はあらゆるコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65be8-118">SSH is required to be installed on all machines.</span></span> <span data-ttu-id="65be8-119">コンピューターとの間でリモート処理を行うには、クライアント (`ssh.exe`) とサーバー (`sshd.exe`) の両方をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65be8-119">You should install both client (`ssh.exe`) and server (`sshd.exe`) so that you can experiment with remoting to and from the machines.</span></span> <span data-ttu-id="65be8-120">Windows の場合、[Win32 OpenSSH from GitHub](https://github.com/PowerShell/Win32-OpenSSH/releases) をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65be8-120">For Windows you will need to install [Win32 OpenSSH from GitHub](https://github.com/PowerShell/Win32-OpenSSH/releases).</span></span>
<span data-ttu-id="65be8-121">Linux の場合、お使いのプラットフォームに適した SSH (sshd サーバーを含む) をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65be8-121">For Linux you will need to install SSH (including sshd server) appropriate to your platform.</span></span> <span data-ttu-id="65be8-122">SSH リモート処理機能を備えた最近の PowerShell ビルドまたはパッケージを GitHub から入手する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="65be8-122">You will also need a recent PowerShell build or package from GitHub having the SSH remoting feature.</span></span>
<span data-ttu-id="65be8-123">SSH サブシステムはリモート コンピューター上で PowerShell プロセスを確立するために使用されます。SSH サーバーをそれに合わせて構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65be8-123">SSH subsystems is used to establish a PowerShell process on the remote machine and the SSH server will need to be configured for that.</span></span> <span data-ttu-id="65be8-124">また、パスワード認証と、任意で、キーに基づく認証を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65be8-124">In addition you will need to enable password authentication and optionally key based authentication.</span></span>

## <a name="setup-on-windows-machine"></a><span data-ttu-id="65be8-125">Windows コンピューターでのセットアップ</span><span class="sxs-lookup"><span data-stu-id="65be8-125">Setup on Windows Machine</span></span>

1. <span data-ttu-id="65be8-126">[Windows 向け PowerShell Core] の最新版をインストールします</span><span class="sxs-lookup"><span data-stu-id="65be8-126">Install the latest version of [PowerShell Core for Windows]</span></span>

   - <span data-ttu-id="65be8-127">`New-PSSession` のパラメーター セットを見れば、SSH リモート処理に対応しているか確認できます</span><span class="sxs-lookup"><span data-stu-id="65be8-127">You can tell if it has the SSH remoting support by looking at the parameter sets for `New-PSSession`</span></span>

   ```powershell
   Get-Command New-PSSession -syntax
   ```

   ```output
   New-PSSession [-HostName] <string[]> [-Name <string[]>] [-UserName <string>] [-KeyFilePath <string>] [-SSHTransport] [<CommonParameters>]
   ```

2. <span data-ttu-id="65be8-128">[インストール] の手順を使用して、GitHub から最新の [Win32 OpenSSH] ビルドをインストールします</span><span class="sxs-lookup"><span data-stu-id="65be8-128">Install the latest [Win32 OpenSSH] build from GitHub using the [installation] instructions</span></span>
3. <span data-ttu-id="65be8-129">Win32 OpenSSH をインストールした場所で sshd_config ファイルを編集します</span><span class="sxs-lookup"><span data-stu-id="65be8-129">Edit the sshd_config file at the location where you installed Win32 OpenSSH</span></span>

   - <span data-ttu-id="65be8-130">パスワード認証が有効になっていることを確認します</span><span class="sxs-lookup"><span data-stu-id="65be8-130">Make sure password authentication is enabled</span></span>

     ```
     PasswordAuthentication yes
     ```

     ```
     Subsystem    powershell c:/program files/powershell/6.0.0/pwsh.exe -sshs -NoLogo -NoProfile
     ```

     > [!NOTE]
     > <span data-ttu-id="65be8-131">OpenSSH for Windows にバグがあり、サブシステムの実行可能ファイルのパスでスペースが機能しません。</span><span class="sxs-lookup"><span data-stu-id="65be8-131">There is a bug in OpenSSH for Windows that prevents spaces from working in subsystem executable paths.</span></span>
     > <span data-ttu-id="65be8-132">この問題の詳細については、GitHub の[こちらのページ](https://github.com/PowerShell/Win32-OpenSSH/issues/784)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65be8-132">See [this issue on GitHub for more information](https://github.com/PowerShell/Win32-OpenSSH/issues/784).</span></span>

     <span data-ttu-id="65be8-133">解決策の 1 つは、次のようにスペースが含まれていない PowerShell インストール ディレクトリへのシンボリック リンクを作成することです。</span><span class="sxs-lookup"><span data-stu-id="65be8-133">One solution is to create a symlink to the Powershell installation directory that does not contain spaces:</span></span>

     ```powershell
     mklink /D c:\pwsh "C:\Program Files\PowerShell\6.0.0"
     ```

     <span data-ttu-id="65be8-134">次に、それを以下のようにサブシステムに入力します。</span><span class="sxs-lookup"><span data-stu-id="65be8-134">and then enter it in the subsystem:</span></span>

     ```
     Subsystem    powershell c:\pwsh\pwsh.exe -sshs -NoLogo -NoProfile
     ```

     ```
     Subsystem    powershell c:/program files/powershell/6.0.0/pwsh.exe -sshs -NoLogo -NoProfile
     ```

   - <span data-ttu-id="65be8-135">必要であればキー認証を有効にします</span><span class="sxs-lookup"><span data-stu-id="65be8-135">Optionally enable key authentication</span></span>

     ```
     PubkeyAuthentication yes
     ```

4. <span data-ttu-id="65be8-136">sshd サービスを再起動します</span><span class="sxs-lookup"><span data-stu-id="65be8-136">Restart the sshd service</span></span>

   ```powershell
   Restart-Service sshd
   ```

5. <span data-ttu-id="65be8-137">OpenSSH がインストールされているパスをパス環境変数に追加します</span><span class="sxs-lookup"><span data-stu-id="65be8-137">Add the path where OpenSSH is installed to your Path Env Variable</span></span>

   - <span data-ttu-id="65be8-138">`C:\Program Files\OpenSSH\` の行に沿ったものになります</span><span class="sxs-lookup"><span data-stu-id="65be8-138">This should be along the lines of `C:\Program Files\OpenSSH\`</span></span>
   - <span data-ttu-id="65be8-139">これで ssh.exe の場所が認識されます</span><span class="sxs-lookup"><span data-stu-id="65be8-139">This allows for the ssh.exe to be found</span></span>

## <a name="setup-on-linux-ubuntu-1404-machine"></a><span data-ttu-id="65be8-140">Linux (Ubuntu 14.04) コンピューターでのセットアップ</span><span class="sxs-lookup"><span data-stu-id="65be8-140">Setup on Linux (Ubuntu 14.04) Machine</span></span>

1. <span data-ttu-id="65be8-141">GitHub から最新の [Linux 向け PowerShell Core] ビルドをインストールします</span><span class="sxs-lookup"><span data-stu-id="65be8-141">Install the latest [PowerShell Core for Linux] build from GitHub</span></span>
2. <span data-ttu-id="65be8-142">必要に応じて [Ubuntu SSH] をインストールします</span><span class="sxs-lookup"><span data-stu-id="65be8-142">Install [Ubuntu SSH] as needed</span></span>

   ```bash
   sudo apt install openssh-client
   sudo apt install openssh-server
   ```

3. <span data-ttu-id="65be8-143">/etc/ssh で sshd_config ファイルを編集します</span><span class="sxs-lookup"><span data-stu-id="65be8-143">Edit the sshd_config file at location /etc/ssh</span></span>

   - <span data-ttu-id="65be8-144">パスワード認証が有効になっていることを確認します</span><span class="sxs-lookup"><span data-stu-id="65be8-144">Make sure password authentication is enabled</span></span>

   ```
   PasswordAuthentication yes
   ```

   - <span data-ttu-id="65be8-145">PowerShell サブシステム エントリを追加します</span><span class="sxs-lookup"><span data-stu-id="65be8-145">Add a PowerShell subsystem entry</span></span>

   ```
   Subsystem powershell /usr/bin/pwsh -sshs -NoLogo -NoProfile
   ```

   - <span data-ttu-id="65be8-146">必要であればキー認証を有効にします</span><span class="sxs-lookup"><span data-stu-id="65be8-146">Optionally enable key authentication</span></span>

   ```
   PubkeyAuthentication yes
   ```

4. <span data-ttu-id="65be8-147">sshd サービスを再起動します</span><span class="sxs-lookup"><span data-stu-id="65be8-147">Restart the sshd service</span></span>

   ```bash
   sudo service sshd restart
   ```

## <a name="setup-on-macos-machine"></a><span data-ttu-id="65be8-148">MacOS コンピューターでのセットアップ</span><span class="sxs-lookup"><span data-stu-id="65be8-148">Setup on MacOS Machine</span></span>

1. <span data-ttu-id="65be8-149">最新の [MacOS 向け PowerShell Core] ビルドをインストールします</span><span class="sxs-lookup"><span data-stu-id="65be8-149">Install the latest [PowerShell Core for MacOS] build</span></span>

   - <span data-ttu-id="65be8-150">次の手順で SSH リモート処理が有効になっていることを確認します</span><span class="sxs-lookup"><span data-stu-id="65be8-150">Make sure SSH Remoting is enabled by following these steps:</span></span>
     - <span data-ttu-id="65be8-151">`System Preferences` を開きます</span><span class="sxs-lookup"><span data-stu-id="65be8-151">Open `System Preferences`</span></span>
     - <span data-ttu-id="65be8-152">`Sharing` をクリックします</span><span class="sxs-lookup"><span data-stu-id="65be8-152">Click on `Sharing`</span></span>
     - <span data-ttu-id="65be8-153">`Remote Login` が `Remote Login: On` になっていることを確認します</span><span class="sxs-lookup"><span data-stu-id="65be8-153">Check `Remote Login` - Should say `Remote Login: On`</span></span>
     - <span data-ttu-id="65be8-154">適切なユーザーにアクセスを許可します</span><span class="sxs-lookup"><span data-stu-id="65be8-154">Allow access to appropriate users</span></span>

2. <span data-ttu-id="65be8-155">`/private/etc/ssh/sshd_config` で `sshd_config` ファイルを編集します</span><span class="sxs-lookup"><span data-stu-id="65be8-155">Edit the `sshd_config` file at location `/private/etc/ssh/sshd_config`</span></span>

   - <span data-ttu-id="65be8-156">お気に入りのエディターを使用します</span><span class="sxs-lookup"><span data-stu-id="65be8-156">Use your favorite editor or</span></span>

     ```bash
     sudo nano /private/etc/ssh/sshd_config
     ```

   - <span data-ttu-id="65be8-157">パスワード認証が有効になっていることを確認します</span><span class="sxs-lookup"><span data-stu-id="65be8-157">Make sure password authentication is enabled</span></span>

     ```
     PasswordAuthentication yes
     ```

   - <span data-ttu-id="65be8-158">PowerShell サブシステム エントリを追加します</span><span class="sxs-lookup"><span data-stu-id="65be8-158">Add a PowerShell subsystem entry</span></span>

     ```
     Subsystem powershell /usr/local/bin/pwsh -sshs -NoLogo -NoProfile
     ```

   - <span data-ttu-id="65be8-159">必要であればキー認証を有効にします</span><span class="sxs-lookup"><span data-stu-id="65be8-159">Optionally enable key authentication</span></span>

     ```
     PubkeyAuthentication yes
     ```

3. <span data-ttu-id="65be8-160">sshd サービスを再起動します</span><span class="sxs-lookup"><span data-stu-id="65be8-160">Restart the sshd service</span></span>

   ```bash
   sudo launchctl stop com.openssh.sshd
   sudo launchctl start com.openssh.sshd
   ```

## <a name="powershell-remoting-example"></a><span data-ttu-id="65be8-161">PowerShell リモート処理の例</span><span class="sxs-lookup"><span data-stu-id="65be8-161">PowerShell Remoting Example</span></span>

<span data-ttu-id="65be8-162">リモート処理をテストする最も簡単な方法は、1 台のコンピューターでそれを試すことです。</span><span class="sxs-lookup"><span data-stu-id="65be8-162">The easiest way to test remoting is to just try it on a single machine.</span></span> <span data-ttu-id="65be8-163">今回、ある Linux ボックス上の同じコンピューターにリモート セッションを行います。</span><span class="sxs-lookup"><span data-stu-id="65be8-163">Here I will create a remote session back to the same machine on a Linux box.</span></span> <span data-ttu-id="65be8-164">コマンド プロンプトから PowerShell コマンドレットを使用している点に注目してください。SSH のプロンプトから、ホスト コンピューターを確認するように求められます。また、パスワードも求められます。</span><span class="sxs-lookup"><span data-stu-id="65be8-164">Notice that I am using PowerShell cmdlets from a command prompt so we see prompts from SSH asking to verify the host computer as well as password prompts.</span></span> <span data-ttu-id="65be8-165">ホスト名を変えるだけで、同じことを Windows コンピューターで行い、そのコンピューターで、また、離れているコンピューター間でリモート処理が機能していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="65be8-165">You can do the same thing on a Windows machine to ensure remoting is working there and then remote between machines by simply changing the host name.</span></span>

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

### <a name="known-issues"></a><span data-ttu-id="65be8-166">の既知の問題</span><span class="sxs-lookup"><span data-stu-id="65be8-166">Known Issues</span></span>

<span data-ttu-id="65be8-167">sudo コマンドは、Linux コンピューターへのリモート セッションでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="65be8-167">The sudo command does not work in remote session to Linux machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="65be8-168">参照</span><span class="sxs-lookup"><span data-stu-id="65be8-168">See Also</span></span>

[<span data-ttu-id="65be8-169">Windows 向け PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="65be8-169">PowerShell Core for Windows</span></span>](../setup/installing-powershell-core-on-windows.md#msi)

[<span data-ttu-id="65be8-170">Linux 向け PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="65be8-170">PowerShell Core for Linux</span></span>](../setup/installing-powershell-core-on-linux.md#ubuntu-1404)

[<span data-ttu-id="65be8-171">MacOS 向け PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="65be8-171">PowerShell Core for MacOS</span></span>](../setup/installing-powershell-core-on-macos.md)

[<span data-ttu-id="65be8-172">Win32 OpenSSH</span><span class="sxs-lookup"><span data-stu-id="65be8-172">Win32 OpenSSH</span></span>](https://github.com/PowerShell/Win32-OpenSSH/releases)

[<span data-ttu-id="65be8-173">インストール</span><span class="sxs-lookup"><span data-stu-id="65be8-173">installation</span></span>](https://github.com/PowerShell/Win32-OpenSSH/wiki/Install-Win32-OpenSSH)

[<span data-ttu-id="65be8-174">Ubuntu SSH</span><span class="sxs-lookup"><span data-stu-id="65be8-174">Ubuntu SSH</span></span>](https://help.ubuntu.com/lts/serverguide/openssh-server.html)