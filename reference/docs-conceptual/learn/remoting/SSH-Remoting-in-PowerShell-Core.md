---
title: SSH 経由の PowerShell リモート処理
ms.date: 10/19/2020
description: PowerShell のリモート処理用に SSH プロトコルを設定する方法について説明します。
ms.openlocfilehash: c3373ac30fd915d42e8c9fb7f1eae348a2aee7f1
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501339"
---
# <a name="powershell-remoting-over-ssh"></a><span data-ttu-id="5952e-103">SSH 経由の PowerShell リモート処理</span><span class="sxs-lookup"><span data-stu-id="5952e-103">PowerShell remoting over SSH</span></span>

## <a name="overview"></a><span data-ttu-id="5952e-104">概要</span><span class="sxs-lookup"><span data-stu-id="5952e-104">Overview</span></span>

<span data-ttu-id="5952e-105">PowerShell リモート処理では通常、接続交渉とデータ転送に WinRM が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5952e-105">PowerShell remoting normally uses WinRM for connection negotiation and data transport.</span></span> <span data-ttu-id="5952e-106">SSH が Linux および Windows のプラットフォームで利用可能になり、実際のマルチプラットフォームの PowerShell リモート処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="5952e-106">SSH is now available for Linux and Windows platforms and allows true multiplatform PowerShell remoting.</span></span>

<span data-ttu-id="5952e-107">WinRM は PowerShell リモート処理セッションに堅牢なホスティング モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="5952e-107">WinRM provides a robust hosting model for PowerShell remote sessions.</span></span> <span data-ttu-id="5952e-108">SSH ベースのリモート処理では現在、リモート エンドポイント構成および JEA (Just Enough Administration) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5952e-108">SSH-based remoting doesn't currently support remote endpoint configuration and Just Enough Administration (JEA).</span></span>

<span data-ttu-id="5952e-109">SSH リモート処理では、Windows コンピューターと Linux コンピューターの間で基本的な PowerShell セッションをリモート処理できます。</span><span class="sxs-lookup"><span data-stu-id="5952e-109">SSH remoting lets you do basic PowerShell session remoting between Windows and Linux computers.</span></span> <span data-ttu-id="5952e-110">SSH リモート処理で、SSH サブシステムとしてターゲット コンピューター上に PowerShell ホスティング プロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5952e-110">SSH remoting creates a PowerShell host process on the target computer as an SSH subsystem.</span></span> <span data-ttu-id="5952e-111">最終的には、エンドポイント構成と JEA をサポートするために、WinRM とほぼ同じ一般的なホスティング モデルが実装される予定です。</span><span class="sxs-lookup"><span data-stu-id="5952e-111">Eventually we'll implement a general hosting model, similar to WinRM, to support endpoint configuration and JEA.</span></span>

<span data-ttu-id="5952e-112">現在、`New-PSSession`、`Enter-PSSession`、および `Invoke-Command` コマンドレットには、この新しいリモート処理接続をサポートする新しいパラメーター セットがあります。</span><span class="sxs-lookup"><span data-stu-id="5952e-112">The `New-PSSession`, `Enter-PSSession`, and `Invoke-Command` cmdlets now have a new parameter set to support this new remoting connection.</span></span>

```
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

<span data-ttu-id="5952e-113">リモート セッションを作成するには、 **HostName** パラメーターでターゲット コンピューターを指定し、 **UserName** でユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="5952e-113">To create a remote session, you specify the target computer with the **HostName** parameter and provide the user name with **UserName** .</span></span> <span data-ttu-id="5952e-114">コマンドレットを対話的に実行する場合は、パスワードの入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="5952e-114">When running the cmdlets interactively, you're prompted for a password.</span></span> <span data-ttu-id="5952e-115">また、 **KeyFilePath** パラメーターでプライベート キー ファイルを使用して、SSH キー認証を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5952e-115">You can also use SSH key authentication using a private key file with the **KeyFilePath** parameter.</span></span> <span data-ttu-id="5952e-116">SSH 認証用のキーの作成は、プラットフォームによって異なります。</span><span class="sxs-lookup"><span data-stu-id="5952e-116">Creating keys for SSH authentication varies by platform.</span></span>

## <a name="general-setup-information"></a><span data-ttu-id="5952e-117">一般的なセットアップ情報</span><span class="sxs-lookup"><span data-stu-id="5952e-117">General setup information</span></span>

<span data-ttu-id="5952e-118">PowerShell 6 以降と SSH がすべてのコンピューターにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5952e-118">PowerShell 6 or higher, and SSH must be installed on all computers.</span></span> <span data-ttu-id="5952e-119">コンピューター間でリモート処理を行うには、SSH クライアント (`ssh.exe`) とサーバー (`sshd.exe`) の両方をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5952e-119">Install both the SSH client (`ssh.exe`) and server (`sshd.exe`) so that you can remote to and from the computers.</span></span> <span data-ttu-id="5952e-120">OpenSSH for Windows が Windows 10 ビルド 1809 と Windows Server 2019 で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5952e-120">OpenSSH for Windows is now available in Windows 10 build 1809 and Windows Server 2019.</span></span> <span data-ttu-id="5952e-121">詳細については、[OpenSSH で Windows を管理する](/windows-server/administration/openssh/openssh_overview)方法に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5952e-121">For more information, see [Manage Windows with OpenSSH](/windows-server/administration/openssh/openssh_overview).</span></span> <span data-ttu-id="5952e-122">Linux の場合、お使いのプラットフォームに適した SSH (sshd サーバーを含む) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5952e-122">For Linux, install SSH, including sshd server, that's appropriate for your platform.</span></span> <span data-ttu-id="5952e-123">また、SSH リモート処理の機能を取得するために、GitHub から PowerShell をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5952e-123">You also need to install PowerShell from GitHub to get the SSH remoting feature.</span></span> <span data-ttu-id="5952e-124">SSH サーバーは、リモート コンピューター上で PowerShell プロセスをホストする SSH サブシステムを作成するように構成される必要があります。</span><span class="sxs-lookup"><span data-stu-id="5952e-124">The SSH server must be configured to create an SSH subsystem to host a PowerShell process on the remote computer.</span></span> <span data-ttu-id="5952e-125">また、 **パスワード** や **キーベース** の認証を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5952e-125">And, you must enable **password** or **key-based** authentication.</span></span>

## <a name="set-up-on-a-windows-computer"></a><span data-ttu-id="5952e-126">Windows コンピューターでの設定</span><span class="sxs-lookup"><span data-stu-id="5952e-126">Set up on a Windows computer</span></span>

1. <span data-ttu-id="5952e-127">最新バージョンの PowerShell をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5952e-127">Install the latest version of PowerShell.</span></span> <span data-ttu-id="5952e-128">詳細については、[Windows への PowerShell Core のインストール](../../install/installing-powershell-core-on-windows.md#msi)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5952e-128">For more information, see [Installing PowerShell Core on Windows](../../install/installing-powershell-core-on-windows.md#msi).</span></span>

   <span data-ttu-id="5952e-129">`New-PSSession` パラメーター セットをリストアップすることで、PowerShell で SSH リモート処理がサポートされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5952e-129">You can confirm that PowerShell has SSH remoting support by listing the `New-PSSession` parameter sets.</span></span> <span data-ttu-id="5952e-130">**SSH** で始まるパラメーター セット名があることに気付くでしょう。</span><span class="sxs-lookup"><span data-stu-id="5952e-130">You'll notice there are parameter set names that begin with **SSH** .</span></span> <span data-ttu-id="5952e-131">そのパラメーター セットに **SSH** パラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5952e-131">Those parameter sets include **SSH** parameters.</span></span>

   ```powershell
   (Get-Command New-PSSession).ParameterSets.Name
   ```

   ```Output
   Name
   ----
   SSHHost
   SSHHostHashParam
   ```

1. <span data-ttu-id="5952e-132">最新の Win32 OpenSSH をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5952e-132">Install the latest Win32 OpenSSH.</span></span> <span data-ttu-id="5952e-133">インストール手順については、[OpenSSH の概要](/windows-server/administration/openssh/openssh_install_firstuse)ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5952e-133">For installation instructions, see [Getting started with OpenSSH](/windows-server/administration/openssh/openssh_install_firstuse).</span></span>

   > [!NOTE]
   > <span data-ttu-id="5952e-134">PowerShell を OpenSSH の既定のシェルとして設定する場合、[Windows で OpenSSH を構成する](/windows-server/administration/openssh/openssh_server_configuration)方法に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5952e-134">If you want to set PowerShell as the default shell for OpenSSH, see [Configuring Windows for OpenSSH](/windows-server/administration/openssh/openssh_server_configuration).</span></span>

1. <span data-ttu-id="5952e-135">`$env:ProgramData\ssh` にある `sshd_config` ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="5952e-135">Edit the `sshd_config` file located at `$env:ProgramData\ssh`.</span></span>

   <span data-ttu-id="5952e-136">パスワード認証が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5952e-136">Make sure password authentication is enabled:</span></span>

   ```
   PasswordAuthentication yes
   ```

   <span data-ttu-id="5952e-137">リモート コンピューターで PowerShell プロセスをホストする SSH サブシステムを作成します。</span><span class="sxs-lookup"><span data-stu-id="5952e-137">Create the SSH subsystem that hosts a PowerShell process on the remote computer:</span></span>

   ```
   Subsystem powershell c:/progra~1/powershell/7/pwsh.exe -sshs -NoLogo
   ```

   > [!NOTE]
   > <span data-ttu-id="5952e-138">PowerShell 実行可能ファイルの既定の場所は `c:/progra~1/powershell/7/pwsh.exe` です。</span><span class="sxs-lookup"><span data-stu-id="5952e-138">The default location of the PowerShell executable is `c:/progra~1/powershell/7/pwsh.exe`.</span></span> <span data-ttu-id="5952e-139">この場所は、PowerShell のインストール方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5952e-139">The location can vary depending on how you installed PowerShell.</span></span>
   >
   > <span data-ttu-id="5952e-140">スペースを含むファイル パスには、8.3 の短い名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5952e-140">You must use the 8.3 short name for any file paths that contain spaces.</span></span> <span data-ttu-id="5952e-141">OpenSSH for Windows にバグがあり、サブシステムの実行可能ファイルのパスでスペースが機能しません。</span><span class="sxs-lookup"><span data-stu-id="5952e-141">There's a bug in OpenSSH for Windows that prevents spaces from working in subsystem executable paths.</span></span> <span data-ttu-id="5952e-142">詳細については、[こちらの GitHub の問題](https://github.com/PowerShell/Win32-OpenSSH/issues/784)のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5952e-142">For more information, see this [GitHub issue](https://github.com/PowerShell/Win32-OpenSSH/issues/784).</span></span>
   >
   > <span data-ttu-id="5952e-143">通常、`Progra~1` が、Windows の `Program Files` フォルダーに対する 8.3 の短い名前です。</span><span class="sxs-lookup"><span data-stu-id="5952e-143">The 8.3 short name for the `Program Files` folder in Windows is usually `Progra~1`.</span></span> <span data-ttu-id="5952e-144">しかし、次のコマンドを使用して確認することができます。</span><span class="sxs-lookup"><span data-stu-id="5952e-144">However, you can use the following command to make sure:</span></span>
   >
   > ```powershell
   > Get-CimInstance Win32_Directory -Filter 'Name="C:\\Program Files"' |
   >   Select-Object EightDotThreeFileName
   > ```
   >
   > ```Output
   > EightDotThreeFileName
   > ---------------------
   > c:\progra~1
   > ```

   <span data-ttu-id="5952e-145">必要であれば、キー認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5952e-145">Optionally, enable key authentication:</span></span>

   ```
   PubkeyAuthentication yes
   ```

   <span data-ttu-id="5952e-146">詳細については、[OpenSSH キーの管理](/windows-server/administration/openssh/openssh_keymanagement)方法に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5952e-146">For more information, see [Managing OpenSSH Keys](/windows-server/administration/openssh/openssh_keymanagement).</span></span>

1. <span data-ttu-id="5952e-147">**sshd** サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="5952e-147">Restart the **sshd** service.</span></span>

   ```powershell
   Restart-Service sshd
   ```

1. <span data-ttu-id="5952e-148">OpenSSH がインストールされているパスをパス環境変数に追加します。</span><span class="sxs-lookup"><span data-stu-id="5952e-148">Add the path where OpenSSH is installed to your Path environment variable.</span></span> <span data-ttu-id="5952e-149">たとえば、「 `C:\Program Files\OpenSSH\` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5952e-149">For example, `C:\Program Files\OpenSSH\`.</span></span> <span data-ttu-id="5952e-150">この項目によって、`ssh.exe` の場所が認識されます。</span><span class="sxs-lookup"><span data-stu-id="5952e-150">This entry allows for the `ssh.exe` to be found.</span></span>

## <a name="set-up-on-an-ubuntu-1604-linux-computer"></a><span data-ttu-id="5952e-151">Ubuntu 16.04 Linux コンピューターでの設定</span><span class="sxs-lookup"><span data-stu-id="5952e-151">Set up on an Ubuntu 16.04 Linux computer</span></span>

1. <span data-ttu-id="5952e-152">PowerShell の最新バージョンをインストールします。「[Linux への PowerShell Core のインストール](../../install/installing-powershell-core-on-linux.md#ubuntu-1604)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5952e-152">Install the latest version of PowerShell, see [Installing PowerShell Core on Linux](../../install/installing-powershell-core-on-linux.md#ubuntu-1604).</span></span>
1. <span data-ttu-id="5952e-153">[Ubuntu OpenSSH Server](https://help.ubuntu.com/lts/serverguide/openssh-server.html) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5952e-153">Install [Ubuntu OpenSSH Server](https://help.ubuntu.com/lts/serverguide/openssh-server.html).</span></span>

   ```bash
   sudo apt install openssh-client
   sudo apt install openssh-server
   ```

1. <span data-ttu-id="5952e-154">`/etc/ssh` で `sshd_config` ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="5952e-154">Edit the `sshd_config` file at location `/etc/ssh`.</span></span>

   <span data-ttu-id="5952e-155">パスワード認証が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5952e-155">Make sure password authentication is enabled:</span></span>

   ```
   PasswordAuthentication yes
   ```

   <span data-ttu-id="5952e-156">必要であれば、キー認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5952e-156">Optionally, enable key authentication:</span></span>

   ```
   PubkeyAuthentication yes
   ```

   <span data-ttu-id="5952e-157">Ubuntu での SSH キーの作成の詳細については、[ssh-keygen](http://manpages.ubuntu.com/manpages/xenial/man1/ssh-keygen.1.html) のマニュアル ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5952e-157">For more information about creating SSH keys on Ubuntu, see the manpage for [ssh-keygen](http://manpages.ubuntu.com/manpages/xenial/man1/ssh-keygen.1.html).</span></span>

   <span data-ttu-id="5952e-158">PowerShell サブシステム エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="5952e-158">Add a PowerShell subsystem entry:</span></span>

   ```
   Subsystem powershell /usr/bin/pwsh -sshs -NoLogo
   ```

   > [!NOTE]
   > <span data-ttu-id="5952e-159">PowerShell 実行可能ファイルの既定の場所は `/usr/bin/pwsh` です。</span><span class="sxs-lookup"><span data-stu-id="5952e-159">The default location of the PowerShell executable is `/usr/bin/pwsh`.</span></span> <span data-ttu-id="5952e-160">この場所は、PowerShell のインストール方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5952e-160">The location can vary depending on how you installed PowerShell.</span></span>

   <span data-ttu-id="5952e-161">必要であれば、キー認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5952e-161">Optionally, enable key authentication:</span></span>

   ```
   PubkeyAuthentication yes
   ```

1. <span data-ttu-id="5952e-162">**ssh** サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="5952e-162">Restart the **ssh** service.</span></span>

   ```bash
   sudo service ssh restart
   ```

## <a name="set-up-on-a-macos-computer"></a><span data-ttu-id="5952e-163">macOS コンピューターでの設定</span><span class="sxs-lookup"><span data-stu-id="5952e-163">Set up on a macOS computer</span></span>

1. <span data-ttu-id="5952e-164">最新バージョンの PowerShell をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5952e-164">Install the latest version of PowerShell.</span></span> <span data-ttu-id="5952e-165">詳細については、[macOS への PowerShell Core のインストール](../../install/installing-powershell-core-on-macos.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5952e-165">For more information, [Installing PowerShell Core on macOS](../../install/installing-powershell-core-on-macos.md).</span></span>

   <span data-ttu-id="5952e-166">次の手順で SSH リモート処理が有効になっていることを確認します</span><span class="sxs-lookup"><span data-stu-id="5952e-166">Make sure SSH Remoting is enabled by following these steps:</span></span>

   1. <span data-ttu-id="5952e-167">`System Preferences`を開きます。</span><span class="sxs-lookup"><span data-stu-id="5952e-167">Open `System Preferences`.</span></span>
   1. <span data-ttu-id="5952e-168">`Sharing` をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5952e-168">Click on `Sharing`.</span></span>
   1. <span data-ttu-id="5952e-169">`Remote Login` にオンにして `Remote Login: On` を設定します。</span><span class="sxs-lookup"><span data-stu-id="5952e-169">Check `Remote Login` to set `Remote Login: On`.</span></span>
   1. <span data-ttu-id="5952e-170">適切なユーザーにアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="5952e-170">Allow access to the appropriate users.</span></span>

1. <span data-ttu-id="5952e-171">`/private/etc/ssh/sshd_config` で `sshd_config` ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="5952e-171">Edit the `sshd_config` file at location `/private/etc/ssh/sshd_config`.</span></span>

   <span data-ttu-id="5952e-172">**nano** などのテキスト エディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="5952e-172">Use a text editor such as **nano** :</span></span>

   ```bash
   sudo nano /private/etc/ssh/sshd_config
   ```

   <span data-ttu-id="5952e-173">パスワード認証が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5952e-173">Make sure password authentication is enabled:</span></span>

   ```
   PasswordAuthentication yes
   ```

   <span data-ttu-id="5952e-174">PowerShell サブシステム エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="5952e-174">Add a PowerShell subsystem entry:</span></span>

   ```
   Subsystem powershell /usr/local/bin/pwsh -sshs -NoLogo
   ```

   > [!NOTE]
   > <span data-ttu-id="5952e-175">PowerShell 実行可能ファイルの既定の場所は `/usr/local/bin/pwsh` です。</span><span class="sxs-lookup"><span data-stu-id="5952e-175">The default location of the PowerShell executable is `/usr/local/bin/pwsh`.</span></span> <span data-ttu-id="5952e-176">この場所は、PowerShell のインストール方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5952e-176">The location can vary depending on how you installed PowerShell.</span></span>

   <span data-ttu-id="5952e-177">必要であれば、キー認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5952e-177">Optionally, enable key authentication:</span></span>

   ```
   PubkeyAuthentication yes
   ```

1. <span data-ttu-id="5952e-178">**sshd** サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="5952e-178">Restart the **sshd** service.</span></span>

   ```bash
   sudo launchctl stop com.openssh.sshd
   sudo launchctl start com.openssh.sshd
   ```

## <a name="authentication"></a><span data-ttu-id="5952e-179">認証</span><span class="sxs-lookup"><span data-stu-id="5952e-179">Authentication</span></span>

<span data-ttu-id="5952e-180">SSH を使用する PowerShell リモート処理では、SSH クライアントと SSH サービスの間の認証交換に依存し、認証スキーム自体は何も実装されません。</span><span class="sxs-lookup"><span data-stu-id="5952e-180">PowerShell remoting over SSH relies on the authentication exchange between the SSH client and SSH service and doesn't implement any authentication schemes itself.</span></span> <span data-ttu-id="5952e-181">結果として、多要素認証などの構成されている認証スキームはすべて SSH によって処理され、PowerShell からは独立します。</span><span class="sxs-lookup"><span data-stu-id="5952e-181">The result is that any configured authentication schemes including multi-factor authentication are handled by SSH and independent of PowerShell.</span></span> <span data-ttu-id="5952e-182">たとえば、セキュリティ強化のため、公開キー認証と 1 回限りのパスワードを要求するように、SSH サービスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5952e-182">For example, you can configure the SSH service to require public key authentication and a one-time password for added security.</span></span> <span data-ttu-id="5952e-183">多要素認証の構成については、このドキュメントでは説明されていません。</span><span class="sxs-lookup"><span data-stu-id="5952e-183">Configuration of multi-factor authentication is outside the scope of this documentation.</span></span> <span data-ttu-id="5952e-184">多要素認証を正しく構成し、PowerShell リモート処理での使用を試みる前に PowerShell の外部での動作を検証する方法については、SSH のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5952e-184">Refer to documentation for SSH on how to correctly configure multi-factor authentication and validate it works outside of PowerShell before attempting to use it with PowerShell remoting.</span></span>

> [!NOTE]
> <span data-ttu-id="5952e-185">ユーザーは、リモート セッションで同じ特権を保持します。</span><span class="sxs-lookup"><span data-stu-id="5952e-185">Users retain the same privileges in remote sessions.</span></span> <span data-ttu-id="5952e-186">つまり、管理者は管理者特権シェルにアクセスできますが、通常のユーザーはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="5952e-186">Meaning, Administrators have access to an elevated shell, and normal users will not.</span></span>

## <a name="powershell-remoting-example"></a><span data-ttu-id="5952e-187">PowerShell リモート処理の例</span><span class="sxs-lookup"><span data-stu-id="5952e-187">PowerShell remoting example</span></span>

<span data-ttu-id="5952e-188">リモート処理をテストする最も簡単な方法は、1 台のコンピューターでリモート処理を試行することです。</span><span class="sxs-lookup"><span data-stu-id="5952e-188">The easiest way to test remoting is to try it on a single computer.</span></span> <span data-ttu-id="5952e-189">以下の例では、同じ Linux コンピューターに戻るリモート セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="5952e-189">In this example, we create a remote session back to the same Linux computer.</span></span> <span data-ttu-id="5952e-190">PowerShell コマンドレットを対話的に使用しているので、SSH からホスト コンピューターの確認を求めるプロンプトと、パスワードを求めるプロンプトが表示されています。</span><span class="sxs-lookup"><span data-stu-id="5952e-190">We're using PowerShell cmdlets interactively so we see prompts from SSH asking to verify the host computer and prompting for a password.</span></span> <span data-ttu-id="5952e-191">Windows コンピューター上で同じ操作を行って、リモート処理の動作を確実にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5952e-191">You can do the same thing on a Windows computer to ensure remoting is working.</span></span> <span data-ttu-id="5952e-192">その後、ホスト名を変更して、コンピューター間をリモート接続します。</span><span class="sxs-lookup"><span data-stu-id="5952e-192">Then, remote between computers by changing the host name.</span></span>

```powershell
# Linux to Linux
#
$session = New-PSSession -HostName UbuntuVM1 -UserName TestUser
```

```Output
The authenticity of host 'UbuntuVM1 (9.129.17.107)' cannot be established.
ECDSA key fingerprint is SHA256:2kCbnhT2dUE6WCGgVJ8Hyfu1z2wE4lifaJXLO7QJy0Y.
Are you sure you want to continue connecting (yes/no)?
TestUser@UbuntuVM1s password:
```

```powershell
$session
```

```Output
 Id Name   ComputerName    ComputerType    State    ConfigurationName     Availability
 -- ----   ------------    ------------    -----    -----------------     ------------
  1 SSH1   UbuntuVM1       RemoteMachine   Opened   DefaultShell             Available
```

```powershell
Enter-PSSession $session
```

```Output
[UbuntuVM1]: PS /home/TestUser> uname -a
Linux TestUser-UbuntuVM1 4.2.0-42-generic 49~16.04.1-Ubuntu SMP Wed Jun 29 20:22:11 UTC 2016 x86_64 x86_64 x86_64 GNU/Linux

[UbuntuVM1]: PS /home/TestUser> Exit-PSSession
```

```powershell
Invoke-Command $session -ScriptBlock { Get-Process powershell }
```

```Output
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

```
PTestName@WinVM1s password:
```

```powershell
[WinVM1]: PS C:\Users\PTestName\Documents> cmd /c ver
```

```Output
Microsoft Windows [Version 10.0.10586]
```

```powershell
#
# Windows to Windows
#
C:\Users\PSUser\Documents>pwsh.exe
```

```Output
PowerShell
Copyright (c) Microsoft Corporation. All rights reserved.
```

```powershell
$session = New-PSSession -HostName WinVM2 -UserName PSRemoteUser
```

```Output
The authenticity of host 'WinVM2 (10.13.37.3)' can't be established.
ECDSA key fingerprint is SHA256:kSU6slAROyQVMEynVIXAdxSiZpwDBigpAF/TXjjWjmw.
Are you sure you want to continue connecting (yes/no)?
Warning: Permanently added 'WinVM2,10.13.37.3' (ECDSA) to the list of known hosts.
PSRemoteUser@WinVM2's password:
```

```powershell
$session
```

```Output
 Id Name            ComputerName    ComputerType    State         ConfigurationName     Availability
 -- ----            ------------    ------------    -----         -----------------     ------------
  1 SSH1            WinVM2          RemoteMachine   Opened        DefaultShell             Available
```

```powershell
Enter-PSSession -Session $session
```

```Output
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

### <a name="limitations"></a><span data-ttu-id="5952e-193">制限事項</span><span class="sxs-lookup"><span data-stu-id="5952e-193">Limitations</span></span>

- <span data-ttu-id="5952e-194">**sudo** コマンドは、Linux コンピューターへのリモート セッションでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="5952e-194">The **sudo** command doesn't work in a remote session to a Linux computer.</span></span>

- <span data-ttu-id="5952e-195">SSH 経由の PSRemoting は、プロファイルをサポートしていないため、`$PROFILE` へのアクセス権がありません。</span><span class="sxs-lookup"><span data-stu-id="5952e-195">PSRemoting over SSH does not support Profiles and does not have access to `$PROFILE`.</span></span> <span data-ttu-id="5952e-196">セッションでは、完全なファイルパスが含まれるプロファイルをドット ソースで実行することで、プロファイルを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="5952e-196">Once in a session, you can load a profile by dot sourcing the profile with the full filepath.</span></span> <span data-ttu-id="5952e-197">これは、SSH プロファイルには関連していません。</span><span class="sxs-lookup"><span data-stu-id="5952e-197">This is not related to SSH profiles.</span></span> <span data-ttu-id="5952e-198">PowerShell を既定のシェルとして使用するように SSH サーバーを構成して、SSH を使用してプロファイルを読み込むことはできます。</span><span class="sxs-lookup"><span data-stu-id="5952e-198">You can configure the SSH server to use PowerShell as the default shell and to load a profile through SSH.</span></span> <span data-ttu-id="5952e-199">詳細については、SSH のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5952e-199">See the SSH documentation for more information.</span></span>

- <span data-ttu-id="5952e-200">PowerShell 7.1 より前では、SSH 経由のリモート処理は、次ホップのリモート セッションをサポートしていませんでした。</span><span class="sxs-lookup"><span data-stu-id="5952e-200">Prior to PowerShell 7.1, remoting over SSH did not support second-hop remote sessions.</span></span> <span data-ttu-id="5952e-201">この機能は、WinRM を使用したセッションに限定されていました。</span><span class="sxs-lookup"><span data-stu-id="5952e-201">This capability was limited to sessions using WinRM.</span></span> <span data-ttu-id="5952e-202">PowerShell 7.1 を使用すると、任意の対話型リモート セッション内で `Enter-PSSession` と `Enter-PSHostProcess` が機能します。</span><span class="sxs-lookup"><span data-stu-id="5952e-202">PowerShell 7.1 allows `Enter-PSSession` and `Enter-PSHostProcess` to work from within any interactive remote session.</span></span>

## <a name="see-also"></a><span data-ttu-id="5952e-203">関連項目</span><span class="sxs-lookup"><span data-stu-id="5952e-203">See also</span></span>

[<span data-ttu-id="5952e-204">Linux に PowerShell Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="5952e-204">Installing PowerShell Core on Linux</span></span>](../../install/installing-powershell-core-on-linux.md#ubuntu-1604)

[<span data-ttu-id="5952e-205">macOS に PowerShell Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="5952e-205">Installing PowerShell Core on macOS</span></span>](../../install/installing-powershell-core-on-macos.md)

[<span data-ttu-id="5952e-206">Windows に PowerShell Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="5952e-206">Installing PowerShell Core on Windows</span></span>](../../install/installing-powershell-core-on-windows.md#msi)

[<span data-ttu-id="5952e-207">OpenSSH で Windows を管理する</span><span class="sxs-lookup"><span data-stu-id="5952e-207">Manage Windows with OpenSSH</span></span>](/windows-server/administration/openssh/openssh_overview)

[<span data-ttu-id="5952e-208">OpenSSH キーの管理</span><span class="sxs-lookup"><span data-stu-id="5952e-208">Managing OpenSSH Keys</span></span>](/windows-server/administration/openssh/openssh_keymanagement)

[<span data-ttu-id="5952e-209">Ubuntu SSH</span><span class="sxs-lookup"><span data-stu-id="5952e-209">Ubuntu SSH</span></span>](https://help.ubuntu.com/lts/serverguide/openssh-server.html)
