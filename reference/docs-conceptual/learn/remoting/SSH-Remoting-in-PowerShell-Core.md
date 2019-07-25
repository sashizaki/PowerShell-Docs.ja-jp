---
title: SSH 経由の PowerShell リモート処理
description: SSH を使用した PowerShell Core のリモート処理
ms.date: 08/14/2018
ms.openlocfilehash: d994a3888b9a372b803a65666634775a8905d63a
ms.sourcegitcommit: 118eb294d5a84a772e6449d42a9d9324e18ef6b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2019
ms.locfileid: "68372136"
---
# <a name="powershell-remoting-over-ssh"></a><span data-ttu-id="29b57-103">SSH 経由の PowerShell リモート処理</span><span class="sxs-lookup"><span data-stu-id="29b57-103">PowerShell Remoting Over SSH</span></span>

## <a name="overview"></a><span data-ttu-id="29b57-104">概要</span><span class="sxs-lookup"><span data-stu-id="29b57-104">Overview</span></span>

<span data-ttu-id="29b57-105">PowerShell リモート処理では通常、接続交渉とデータ転送に WinRM が使用されます。</span><span class="sxs-lookup"><span data-stu-id="29b57-105">PowerShell remoting normally uses WinRM for connection negotiation and data transport.</span></span> <span data-ttu-id="29b57-106">SSH が Linux および Windows のプラットフォームで利用可能になり、実際のマルチプラットフォームの PowerShell リモート処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="29b57-106">SSH is now available for Linux and Windows platforms and allows true multiplatform PowerShell remoting.</span></span>

<span data-ttu-id="29b57-107">WinRM は PowerShell リモート処理セッションに堅牢なホスティング モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="29b57-107">WinRM provides a robust hosting model for PowerShell remote sessions.</span></span> <span data-ttu-id="29b57-108">SSH ベースのリモート処理では現在、リモート エンドポイント構成および JEA (Just Enough Administration) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="29b57-108">SSH-based remoting doesn't currently support remote endpoint configuration and JEA (Just Enough Administration).</span></span>

<span data-ttu-id="29b57-109">SSH リモート処理では、Windows コンピューターと Linux コンピューターの間で基本的な PowerShell セッションをリモート処理できます。</span><span class="sxs-lookup"><span data-stu-id="29b57-109">SSH remoting lets you do basic PowerShell session remoting between Windows and Linux machines.</span></span> <span data-ttu-id="29b57-110">SSH リモート処理で、SSH サブシステムとしてターゲット コンピューター上に PowerShell ホスティング プロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="29b57-110">SSH Remoting creates a PowerShell host process on the target machine as an SSH subsystem.</span></span> <span data-ttu-id="29b57-111">最終的には、エンドポイント構成と JEA をサポートするために、WinRM とほぼ同じ一般的なホスティング モデルが実装される予定です。</span><span class="sxs-lookup"><span data-stu-id="29b57-111">Eventually we'll implement a general hosting model, similar to WinRM, to support endpoint configuration and JEA.</span></span>

<span data-ttu-id="29b57-112">現在、`New-PSSession`、`Enter-PSSession`、および `Invoke-Command` コマンドレットには、この新しいリモート処理接続をサポートする新しいパラメーター セットがあります。</span><span class="sxs-lookup"><span data-stu-id="29b57-112">The `New-PSSession`, `Enter-PSSession`, and `Invoke-Command` cmdlets now have a new parameter set to support this new remoting connection.</span></span>

```
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

<span data-ttu-id="29b57-113">リモート セッションを作成するために、`HostName` パラメーターでターゲット コンピューターを指定し、`UserName` でユーザー名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="29b57-113">To create a remote session, you specify the target machine with the `HostName` parameter and provide the user name with `UserName`.</span></span> <span data-ttu-id="29b57-114">コマンドレットを対話的に実行する場合は、パスワードの入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="29b57-114">When running the cmdlets interactively, you're prompted for a password.</span></span> <span data-ttu-id="29b57-115">また、`KeyFilePath` パラメーターでプライベート キー ファイルを使って、SSH キー認証を使用できます。</span><span class="sxs-lookup"><span data-stu-id="29b57-115">You can also, use SSH key authentication using a private key file with the `KeyFilePath` parameter.</span></span>

## <a name="general-setup-information"></a><span data-ttu-id="29b57-116">一般的なセットアップ情報</span><span class="sxs-lookup"><span data-stu-id="29b57-116">General setup information</span></span>

<span data-ttu-id="29b57-117">SSH はすべてのコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29b57-117">SSH must be installed on all machines.</span></span> <span data-ttu-id="29b57-118">コンピューター間でリモート処理を行うには、SSH クライアント (`ssh.exe`) とサーバー (`sshd.exe`) の両方をインストールします。</span><span class="sxs-lookup"><span data-stu-id="29b57-118">Install both the SSH client (`ssh.exe`) and server (`sshd.exe`) so that you can remote to and from the machines.</span></span> <span data-ttu-id="29b57-119">OpenSSH for Windows が Windows 10 ビルド 1809 と Windows Server 2019 で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="29b57-119">OpenSSH for Windows is now available in Windows 10 build 1809 and Windows Server 2019.</span></span> <span data-ttu-id="29b57-120">詳細については、[Windows 向け OpenSSH](/windows-server/administration/openssh/openssh_overview) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="29b57-120">For more information, see [OpenSSH for Windows](/windows-server/administration/openssh/openssh_overview).</span></span> <span data-ttu-id="29b57-121">Linux の場合、お使いのプラットフォームに適した SSH (sshd サーバーを含む) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="29b57-121">For Linux, install SSH (including sshd server) appropriate to your platform.</span></span> <span data-ttu-id="29b57-122">また、SSH リモート処理の機能を取得するために、GitHub から PowerShell Core をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29b57-122">You also need to install PowerShell Core from GitHub to get the SSH remoting feature.</span></span> <span data-ttu-id="29b57-123">SSH サーバーは、リモート コンピューター上で PowerShell プロセスをホストする SSH サブシステムを作成するように構成される必要があります。</span><span class="sxs-lookup"><span data-stu-id="29b57-123">The SSH server must be configured to create an SSH subsystem to host a PowerShell process on the remote machine.</span></span> <span data-ttu-id="29b57-124">また、有効なパスワードやキーベースの認証を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29b57-124">You also must configure enable password or key-based authentication.</span></span>

## <a name="set-up-on-windows-machine"></a><span data-ttu-id="29b57-125">Windows コンピューターでのセットアップ</span><span class="sxs-lookup"><span data-stu-id="29b57-125">Set up on Windows Machine</span></span>

1. <span data-ttu-id="29b57-126">[Windows 向け PowerShell Core](../../install/installing-powershell-core-on-windows.md#msi) の最新版をインストールします</span><span class="sxs-lookup"><span data-stu-id="29b57-126">Install the latest version of [PowerShell Core for Windows](../../install/installing-powershell-core-on-windows.md#msi)</span></span>

   - <span data-ttu-id="29b57-127">`New-PSSession` のパラメーター セットを見れば、SSH リモート処理に対応しているか確認できます</span><span class="sxs-lookup"><span data-stu-id="29b57-127">You can tell if it has the SSH remoting support by looking at the parameter sets for `New-PSSession`</span></span>

   ```powershell
   Get-Command New-PSSession -syntax
   ```

   ```output
   New-PSSession [-HostName] <string[]> [-Name <string[]>] [-UserName <string>] [-KeyFilePath <string>] [-SSHTransport] [<CommonParameters>]
   ```

2. <span data-ttu-id="29b57-128">最新の Win32 OpenSSH をインストールします。</span><span class="sxs-lookup"><span data-stu-id="29b57-128">Install the latest Win32 OpenSSH.</span></span> <span data-ttu-id="29b57-129">インストール手順については、「[Installation of OpenSSH](/windows-server/administration/openssh/openssh_install_firstuse)」 (OpenSSH のインストール) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29b57-129">For installation instructions, see [Installation of OpenSSH](/windows-server/administration/openssh/openssh_install_firstuse).</span></span>
3. <span data-ttu-id="29b57-130">`$env:ProgramData\ssh` にある `sshd_config` ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="29b57-130">Edit the `sshd_config` file located at `$env:ProgramData\ssh`.</span></span>

   - <span data-ttu-id="29b57-131">パスワード認証が有効になっていることを確認します</span><span class="sxs-lookup"><span data-stu-id="29b57-131">Make sure password authentication is enabled</span></span>

     ```
     PasswordAuthentication yes
     ```

     ```
     Subsystem    powershell c:/program files/powershell/6/pwsh.exe -sshs -NoLogo -NoProfile
     ```

     > [!NOTE]
     > <span data-ttu-id="29b57-132">OpenSSH for Windows にバグがあり、サブシステムの実行可能ファイルのパスでスペースが機能しません。</span><span class="sxs-lookup"><span data-stu-id="29b57-132">There is a bug in OpenSSH for Windows that prevents spaces from working in subsystem executable paths.</span></span> <span data-ttu-id="29b57-133">詳細については、[こちらの GitHub の問題](https://github.com/PowerShell/Win32-OpenSSH/issues/784)のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="29b57-133">For more information, see [this GitHub issue](https://github.com/PowerShell/Win32-OpenSSH/issues/784).</span></span>

     <span data-ttu-id="29b57-134">解決策の 1 つは、次のようにスペースが含まれていない PowerShell インストール ディレクトリへのシンボリック リンクを作成することです。</span><span class="sxs-lookup"><span data-stu-id="29b57-134">One solution is to create a symlink to the PowerShell installation directory that doesn't have spaces:</span></span>

     ```powershell
     mklink /D c:\pwsh "C:\Program Files\PowerShell\6"
     ```

     <span data-ttu-id="29b57-135">次に、それを以下のようにサブシステムに入力します。</span><span class="sxs-lookup"><span data-stu-id="29b57-135">and then enter it in the subsystem:</span></span>

     ```
     Subsystem    powershell c:\pwsh\pwsh.exe -sshs -NoLogo -NoProfile
     ```

   - <span data-ttu-id="29b57-136">必要であればキー認証を有効にします</span><span class="sxs-lookup"><span data-stu-id="29b57-136">Optionally enable key authentication</span></span>

     ```
     PubkeyAuthentication yes
     ```

4. <span data-ttu-id="29b57-137">sshd サービスを再起動します</span><span class="sxs-lookup"><span data-stu-id="29b57-137">Restart the sshd service</span></span>

   ```powershell
   Restart-Service sshd
   ```

5. <span data-ttu-id="29b57-138">OpenSSH がインストールされているパスをパス環境変数に追加します。</span><span class="sxs-lookup"><span data-stu-id="29b57-138">Add the path where OpenSSH is installed to your Path environment variable.</span></span> <span data-ttu-id="29b57-139">たとえば、`C:\Program Files\OpenSSH\` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="29b57-139">For example, `C:\Program Files\OpenSSH\`.</span></span> <span data-ttu-id="29b57-140">この項目によって、ssh.exe の場所が認識されます。</span><span class="sxs-lookup"><span data-stu-id="29b57-140">This entry allows for the ssh.exe to be found.</span></span>

## <a name="set-up-on-linux-ubuntu-1604-machine"></a><span data-ttu-id="29b57-141">Linux (Ubuntu 16.04) コンピューターでのセットアップ</span><span class="sxs-lookup"><span data-stu-id="29b57-141">Set up on Linux (Ubuntu 16.04) Machine</span></span>

1. <span data-ttu-id="29b57-142">GitHub から最新の [Linux 向け PowerShell Core](../../install/installing-powershell-core-on-linux.md#ubuntu-1604) ビルドをインストールします</span><span class="sxs-lookup"><span data-stu-id="29b57-142">Install the latest [PowerShell Core for Linux](../../install/installing-powershell-core-on-linux.md#ubuntu-1604) build from GitHub</span></span>
2. <span data-ttu-id="29b57-143">必要に応じて [Ubuntu SSH](https://help.ubuntu.com/lts/serverguide/openssh-server.html) をインストールします</span><span class="sxs-lookup"><span data-stu-id="29b57-143">Install [Ubuntu SSH](https://help.ubuntu.com/lts/serverguide/openssh-server.html) as needed</span></span>

   ```bash
   sudo apt install openssh-client
   sudo apt install openssh-server
   ```

3. <span data-ttu-id="29b57-144">/etc/ssh で sshd_config ファイルを編集します</span><span class="sxs-lookup"><span data-stu-id="29b57-144">Edit the sshd_config file at location /etc/ssh</span></span>

   - <span data-ttu-id="29b57-145">パスワード認証が有効になっていることを確認します</span><span class="sxs-lookup"><span data-stu-id="29b57-145">Make sure password authentication is enabled</span></span>

   ```
   PasswordAuthentication yes
   ```

   - <span data-ttu-id="29b57-146">PowerShell サブシステム エントリを追加します</span><span class="sxs-lookup"><span data-stu-id="29b57-146">Add a PowerShell subsystem entry</span></span>

   ```
   Subsystem powershell /usr/bin/pwsh -sshs -NoLogo -NoProfile
   ```

   - <span data-ttu-id="29b57-147">必要であればキー認証を有効にします</span><span class="sxs-lookup"><span data-stu-id="29b57-147">Optionally enable key authentication</span></span>

   ```
   PubkeyAuthentication yes
   ```

4. <span data-ttu-id="29b57-148">sshd サービスを再起動します</span><span class="sxs-lookup"><span data-stu-id="29b57-148">Restart the sshd service</span></span>

   ```bash
   sudo service sshd restart
   ```

## <a name="set-up-on-macos-machine"></a><span data-ttu-id="29b57-149">MacOS コンピューターでのセットアップ</span><span class="sxs-lookup"><span data-stu-id="29b57-149">Set up on MacOS Machine</span></span>

1. <span data-ttu-id="29b57-150">最新の [MacOS 向け PowerShell Core](../../install/installing-powershell-core-on-macos.md) ビルドをインストールします</span><span class="sxs-lookup"><span data-stu-id="29b57-150">Install the latest [PowerShell Core for MacOS](../../install/installing-powershell-core-on-macos.md) build</span></span>

   - <span data-ttu-id="29b57-151">次の手順で SSH リモート処理が有効になっていることを確認します</span><span class="sxs-lookup"><span data-stu-id="29b57-151">Make sure SSH Remoting is enabled by following these steps:</span></span>
     - <span data-ttu-id="29b57-152">`System Preferences` を開きます</span><span class="sxs-lookup"><span data-stu-id="29b57-152">Open `System Preferences`</span></span>
     - <span data-ttu-id="29b57-153">`Sharing` をクリックします</span><span class="sxs-lookup"><span data-stu-id="29b57-153">Click on `Sharing`</span></span>
     - <span data-ttu-id="29b57-154">`Remote Login` が `Remote Login: On` になっていることを確認します</span><span class="sxs-lookup"><span data-stu-id="29b57-154">Check `Remote Login` - Should say `Remote Login: On`</span></span>
     - <span data-ttu-id="29b57-155">適切なユーザーにアクセスを許可します</span><span class="sxs-lookup"><span data-stu-id="29b57-155">Allow access to appropriate users</span></span>

2. <span data-ttu-id="29b57-156">`/private/etc/ssh/sshd_config` で `sshd_config` ファイルを編集します</span><span class="sxs-lookup"><span data-stu-id="29b57-156">Edit the `sshd_config` file at location `/private/etc/ssh/sshd_config`</span></span>

   - <span data-ttu-id="29b57-157">お気に入りのエディターを使用します</span><span class="sxs-lookup"><span data-stu-id="29b57-157">Use your favorite editor or</span></span>

     ```bash
     sudo nano /private/etc/ssh/sshd_config
     ```

   - <span data-ttu-id="29b57-158">パスワード認証が有効になっていることを確認します</span><span class="sxs-lookup"><span data-stu-id="29b57-158">Make sure password authentication is enabled</span></span>

     ```
     PasswordAuthentication yes
     ```

   - <span data-ttu-id="29b57-159">PowerShell サブシステム エントリを追加します</span><span class="sxs-lookup"><span data-stu-id="29b57-159">Add a PowerShell subsystem entry</span></span>

     ```
     Subsystem powershell /usr/local/bin/pwsh -sshs -NoLogo -NoProfile
     ```

   - <span data-ttu-id="29b57-160">必要であればキー認証を有効にします</span><span class="sxs-lookup"><span data-stu-id="29b57-160">Optionally enable key authentication</span></span>

     ```
     PubkeyAuthentication yes
     ```

3. <span data-ttu-id="29b57-161">sshd サービスを再起動します</span><span class="sxs-lookup"><span data-stu-id="29b57-161">Restart the sshd service</span></span>

   ```bash
   sudo launchctl stop com.openssh.sshd
   sudo launchctl start com.openssh.sshd
   ```

## <a name="authentication"></a><span data-ttu-id="29b57-162">認証</span><span class="sxs-lookup"><span data-stu-id="29b57-162">Authentication</span></span>

<span data-ttu-id="29b57-163">SSH を使用する PowerShell リモート処理では、SSH クライアントと SSH サービスの間の認証交換に依存し、認証スキーム自体は何も実装されません。</span><span class="sxs-lookup"><span data-stu-id="29b57-163">PowerShell remoting over SSH relies on the authentication exchange between the SSH client and SSH service and does not implement any authentication schemes itself.</span></span> <span data-ttu-id="29b57-164">つまり、多要素認証などの構成されている認証スキームはすべて SSH によって処理され、PowerShell とは独立しています。</span><span class="sxs-lookup"><span data-stu-id="29b57-164">This means that any configured authentication schemes including multi-factor authentication is handled by SSH and independent of PowerShell.</span></span> <span data-ttu-id="29b57-165">たとえば、セキュリティ強化のため、公開キー認証に加えて 1 回限りのパスワードを要求するように、SSH サービスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="29b57-165">For example, you can configure the SSH service to require public key authentication as well as a one-time password for added security.</span></span> <span data-ttu-id="29b57-166">多要素認証の構成については、このドキュメントでは説明されていません。</span><span class="sxs-lookup"><span data-stu-id="29b57-166">Configuration of multi-factor authentication is outside the scope of this documentation.</span></span> <span data-ttu-id="29b57-167">多要素認証を正しく構成し、PowerShell リモート処理での使用を試みる前に PowerShell の外部での動作を検証する方法については、SSH のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="29b57-167">Refer to documentation for SSH on how to correctly configure multi-factor authentication and validate it works outside of PowerShell before attempting to use it with PowerShell remoting.</span></span>

## <a name="powershell-remoting-example"></a><span data-ttu-id="29b57-168">PowerShell リモート処理の例</span><span class="sxs-lookup"><span data-stu-id="29b57-168">PowerShell Remoting Example</span></span>

<span data-ttu-id="29b57-169">リモート処理をテストする最も簡単な方法は、1 台のコンピューターでリモート処理を試行することです。</span><span class="sxs-lookup"><span data-stu-id="29b57-169">The easiest way to test remoting is to try it on a single machine.</span></span> <span data-ttu-id="29b57-170">以下の例では、同じ Linux コンピューターに戻るリモート セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="29b57-170">In this example, we create a remote session back to the same Linux machine.</span></span> <span data-ttu-id="29b57-171">PowerShell コマンドレットを対話的に使用しているので、SSH からホスト コンピューターの確認を求めるプロンプトと、パスワードを求めるプロンプトが表示されています。</span><span class="sxs-lookup"><span data-stu-id="29b57-171">We are using PowerShell cmdlets interactively so we see prompts from SSH asking to verify the host computer and prompting for a password.</span></span> <span data-ttu-id="29b57-172">Windows コンピューター上で同じ操作を行って、リモート処理が動作していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="29b57-172">You can do the same thing on a Windows machine to ensure remoting is working.</span></span> <span data-ttu-id="29b57-173">その後、ホスト名を変更して、コンピューター間をリモート接続します。</span><span class="sxs-lookup"><span data-stu-id="29b57-173">Then remote between machines by changing the host name.</span></span>

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
Linux TestUser-UbuntuVM1 4.2.0-42-generic 49~16.04.1-Ubuntu SMP Wed Jun 29 20:22:11 UTC 2016 x86_64 x86_64 x86_64 GNU/Linux

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

### <a name="known-issues"></a><span data-ttu-id="29b57-174">の既知の問題</span><span class="sxs-lookup"><span data-stu-id="29b57-174">Known Issues</span></span>

<span data-ttu-id="29b57-175">sudo コマンドは、Linux コンピューターへのリモート セッションでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="29b57-175">The sudo command doesn't work in remote session to Linux machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="29b57-176">参照</span><span class="sxs-lookup"><span data-stu-id="29b57-176">See Also</span></span>

[<span data-ttu-id="29b57-177">Windows 向け PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="29b57-177">PowerShell Core for Windows</span></span>](../../install/installing-powershell-core-on-windows.md#msi)

[<span data-ttu-id="29b57-178">Linux 向け PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="29b57-178">PowerShell Core for Linux</span></span>](../../install/installing-powershell-core-on-linux.md#ubuntu-1604)

[<span data-ttu-id="29b57-179">MacOS 向け PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="29b57-179">PowerShell Core for MacOS</span></span>](../../install/installing-powershell-core-on-macos.md)

[<span data-ttu-id="29b57-180">Windows 向け OpenSSH</span><span class="sxs-lookup"><span data-stu-id="29b57-180">OpenSSH for Windows</span></span>](/windows-server/administration/openssh/openssh_overview)

[<span data-ttu-id="29b57-181">Ubuntu SSH</span><span class="sxs-lookup"><span data-stu-id="29b57-181">Ubuntu SSH</span></span>](https://help.ubuntu.com/lts/serverguide/openssh-server.html)
