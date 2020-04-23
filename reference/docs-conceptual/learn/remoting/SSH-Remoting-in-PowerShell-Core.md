---
title: SSH 経由の PowerShell リモート処理
description: SSH を使用した PowerShell Core のリモート処理
ms.date: 09/30/2019
ms.openlocfilehash: 0f2fb13010d62dec5b19b373a24a199bff22665d
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "73444373"
---
# <a name="powershell-remoting-over-ssh"></a><span data-ttu-id="3caf5-103">SSH 経由の PowerShell リモート処理</span><span class="sxs-lookup"><span data-stu-id="3caf5-103">PowerShell remoting over SSH</span></span>

## <a name="overview"></a><span data-ttu-id="3caf5-104">概要</span><span class="sxs-lookup"><span data-stu-id="3caf5-104">Overview</span></span>

<span data-ttu-id="3caf5-105">PowerShell リモート処理では通常、接続交渉とデータ転送に WinRM が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3caf5-105">PowerShell remoting normally uses WinRM for connection negotiation and data transport.</span></span> <span data-ttu-id="3caf5-106">SSH が Linux および Windows のプラットフォームで利用可能になり、実際のマルチプラットフォームの PowerShell リモート処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="3caf5-106">SSH is now available for Linux and Windows platforms and allows true multiplatform PowerShell remoting.</span></span>

<span data-ttu-id="3caf5-107">WinRM は PowerShell リモート処理セッションに堅牢なホスティング モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-107">WinRM provides a robust hosting model for PowerShell remote sessions.</span></span> <span data-ttu-id="3caf5-108">SSH ベースのリモート処理では現在、リモート エンドポイント構成および JEA (Just Enough Administration) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3caf5-108">SSH-based remoting doesn't currently support remote endpoint configuration and Just Enough Administration (JEA).</span></span>

<span data-ttu-id="3caf5-109">SSH リモート処理では、Windows コンピューターと Linux コンピューターの間で基本的な PowerShell セッションをリモート処理できます。</span><span class="sxs-lookup"><span data-stu-id="3caf5-109">SSH remoting lets you do basic PowerShell session remoting between Windows and Linux computers.</span></span> <span data-ttu-id="3caf5-110">SSH リモート処理で、SSH サブシステムとしてターゲット コンピューター上に PowerShell ホスティング プロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-110">SSH remoting creates a PowerShell host process on the target computer as an SSH subsystem.</span></span> <span data-ttu-id="3caf5-111">最終的には、エンドポイント構成と JEA をサポートするために、WinRM とほぼ同じ一般的なホスティング モデルが実装される予定です。</span><span class="sxs-lookup"><span data-stu-id="3caf5-111">Eventually we'll implement a general hosting model, similar to WinRM, to support endpoint configuration and JEA.</span></span>

<span data-ttu-id="3caf5-112">現在、`New-PSSession`、`Enter-PSSession`、および `Invoke-Command` コマンドレットには、この新しいリモート処理接続をサポートする新しいパラメーター セットがあります。</span><span class="sxs-lookup"><span data-stu-id="3caf5-112">The `New-PSSession`, `Enter-PSSession`, and `Invoke-Command` cmdlets now have a new parameter set to support this new remoting connection.</span></span>

```
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

<span data-ttu-id="3caf5-113">リモート セッションを作成するために、`HostName` パラメーターでターゲット コンピューターを指定し、`UserName` でユーザー名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3caf5-113">To create a remote session, you specify the target computer with the `HostName` parameter and provide the user name with `UserName`.</span></span> <span data-ttu-id="3caf5-114">コマンドレットを対話的に実行する場合は、パスワードの入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="3caf5-114">When running the cmdlets interactively, you're prompted for a password.</span></span> <span data-ttu-id="3caf5-115">また、`KeyFilePath` パラメーターでプライベート キー ファイルを使って、SSH キー認証を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3caf5-115">You can also, use SSH key authentication using a private key file with the `KeyFilePath` parameter.</span></span>

## <a name="general-setup-information"></a><span data-ttu-id="3caf5-116">一般的なセットアップ情報</span><span class="sxs-lookup"><span data-stu-id="3caf5-116">General setup information</span></span>

<span data-ttu-id="3caf5-117">PowerShell 6 以降と SSH がすべてのコンピューターにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3caf5-117">PowerShell 6 or higher, and SSH must be installed on all computers.</span></span> <span data-ttu-id="3caf5-118">コンピューター間でリモート処理を行うには、SSH クライアント (`ssh.exe`) とサーバー (`sshd.exe`) の両方をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3caf5-118">Install both the SSH client (`ssh.exe`) and server (`sshd.exe`) so that you can remote to and from the computers.</span></span> <span data-ttu-id="3caf5-119">OpenSSH for Windows が Windows 10 ビルド 1809 と Windows Server 2019 で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3caf5-119">OpenSSH for Windows is now available in Windows 10 build 1809 and Windows Server 2019.</span></span> <span data-ttu-id="3caf5-120">詳細については、[OpenSSH で Windows を管理する](/windows-server/administration/openssh/openssh_overview)方法に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3caf5-120">For more information, see [Manage Windows with OpenSSH](/windows-server/administration/openssh/openssh_overview).</span></span> <span data-ttu-id="3caf5-121">Linux の場合、お使いのプラットフォームに適した SSH (sshd サーバーを含む) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3caf5-121">For Linux, install SSH, including sshd server, that's appropriate for your platform.</span></span> <span data-ttu-id="3caf5-122">また、SSH リモート処理の機能を取得するために、GitHub から PowerShell をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3caf5-122">You also need to install PowerShell from GitHub to get the SSH remoting feature.</span></span> <span data-ttu-id="3caf5-123">SSH サーバーは、リモート コンピューター上で PowerShell プロセスをホストする SSH サブシステムを作成するように構成される必要があります。</span><span class="sxs-lookup"><span data-stu-id="3caf5-123">The SSH server must be configured to create an SSH subsystem to host a PowerShell process on the remote computer.</span></span> <span data-ttu-id="3caf5-124">また、**パスワード**や**キーベース**の認証を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3caf5-124">And, you must enable **password** or **key-based** authentication.</span></span>

## <a name="set-up-on-a-windows-computer"></a><span data-ttu-id="3caf5-125">Windows コンピューターでの設定</span><span class="sxs-lookup"><span data-stu-id="3caf5-125">Set up on a Windows computer</span></span>

1. <span data-ttu-id="3caf5-126">PowerShell の最新バージョンをインストールします。「[Windows への PowerShell Core のインストール](../../install/installing-powershell-core-on-windows.md#msi)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3caf5-126">Install the latest version of PowerShell, see [Installing PowerShell Core on Windows](../../install/installing-powershell-core-on-windows.md#msi).</span></span>

   <span data-ttu-id="3caf5-127">`New-PSSession` パラメーター セットをリストアップすることで、PowerShell で SSH リモート処理がサポートされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3caf5-127">You can confirm that PowerShell has SSH remoting support by listing the `New-PSSession` parameter sets.</span></span> <span data-ttu-id="3caf5-128">**SSH** で始まるパラメーター セット名があることに気付くでしょう。</span><span class="sxs-lookup"><span data-stu-id="3caf5-128">You'll notice there are parameter set names that begin with **SSH**.</span></span> <span data-ttu-id="3caf5-129">そのパラメーター セットに **SSH** パラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3caf5-129">Those parameter sets include **SSH** parameters.</span></span>

   ```powershell
   (Get-Command New-PSSession).ParameterSets.Name
   ```

   ```Output
   Name
   ----
   SSHHost
   SSHHostHashParam
   ```

1. <span data-ttu-id="3caf5-130">最新の Win32 OpenSSH をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3caf5-130">Install the latest Win32 OpenSSH.</span></span> <span data-ttu-id="3caf5-131">インストール手順については、[OpenSSH の概要](/windows-server/administration/openssh/openssh_install_firstuse)ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3caf5-131">For installation instructions, see [Getting started with OpenSSH](/windows-server/administration/openssh/openssh_install_firstuse).</span></span>

   > [!NOTE]
   > <span data-ttu-id="3caf5-132">PowerShell を OpenSSH の既定のシェルとして設定する場合、[Windows で OpenSSH を構成する](/windows-server/administration/openssh/openssh_server_configuration)方法に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3caf5-132">If you want to set PowerShell as the default shell for OpenSSH, see [Configuring Windows for OpenSSH](/windows-server/administration/openssh/openssh_server_configuration).</span></span>

1. <span data-ttu-id="3caf5-133">`sshd_config` にある `$env:ProgramData\ssh` ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-133">Edit the `sshd_config` file located at `$env:ProgramData\ssh`.</span></span>

   <span data-ttu-id="3caf5-134">パスワード認証が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-134">Make sure password authentication is enabled:</span></span>

   ```
   PasswordAuthentication yes
   ```

   <span data-ttu-id="3caf5-135">リモート コンピューターで PowerShell プロセスをホストする SSH サブシステムを作成します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-135">Create the SSH subsystem that hosts a PowerShell process on the remote computer:</span></span>

   ```
   Subsystem powershell c:/progra~1/powershell/6/pwsh.exe -sshs -NoLogo -NoProfile
   ```

   > [!NOTE]
   > <span data-ttu-id="3caf5-136">スペースを含むファイル パスには、8.3 の短い名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3caf5-136">You must use the 8.3 short name for any file paths that contain spaces.</span></span> <span data-ttu-id="3caf5-137">OpenSSH for Windows にバグがあり、サブシステムの実行可能ファイルのパスでスペースが機能しません。</span><span class="sxs-lookup"><span data-stu-id="3caf5-137">There's a bug in OpenSSH for Windows that prevents spaces from working in subsystem executable paths.</span></span> <span data-ttu-id="3caf5-138">詳細については、[こちらの GitHub の問題](https://github.com/PowerShell/Win32-OpenSSH/issues/784)のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3caf5-138">For more information, see this [GitHub issue](https://github.com/PowerShell/Win32-OpenSSH/issues/784).</span></span>
   >
   > <span data-ttu-id="3caf5-139">通常、`Program Files` が、Windows の `Progra~1` フォルダーに対する 8.3 の短い名前です。</span><span class="sxs-lookup"><span data-stu-id="3caf5-139">The 8.3 short name for the `Program Files` folder in Windows is usually `Progra~1`.</span></span> <span data-ttu-id="3caf5-140">しかし、次のコマンドを使用して確認することができます。</span><span class="sxs-lookup"><span data-stu-id="3caf5-140">However, you can use the following command to make sure:</span></span>
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

   <span data-ttu-id="3caf5-141">必要であれば、キー認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3caf5-141">Optionally, enable key authentication:</span></span>

   ```
   PubkeyAuthentication yes
   ```

   <span data-ttu-id="3caf5-142">詳細については、[OpenSSH キーの管理](/windows-server/administration/openssh/openssh_keymanagement)方法に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3caf5-142">For more information, see [Managing OpenSSH Keys](/windows-server/administration/openssh/openssh_keymanagement).</span></span>

1. <span data-ttu-id="3caf5-143">**sshd** サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-143">Restart the **sshd** service.</span></span>

   ```powershell
   Restart-Service sshd
   ```

1. <span data-ttu-id="3caf5-144">OpenSSH がインストールされているパスをパス環境変数に追加します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-144">Add the path where OpenSSH is installed to your Path environment variable.</span></span> <span data-ttu-id="3caf5-145">たとえば、「 `C:\Program Files\OpenSSH\` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-145">For example, `C:\Program Files\OpenSSH\`.</span></span> <span data-ttu-id="3caf5-146">この項目によって、`ssh.exe` の場所が認識されます。</span><span class="sxs-lookup"><span data-stu-id="3caf5-146">This entry allows for the `ssh.exe` to be found.</span></span>

## <a name="set-up-on-an-ubuntu-1604-linux-computer"></a><span data-ttu-id="3caf5-147">Ubuntu 16.04 Linux コンピューターでの設定</span><span class="sxs-lookup"><span data-stu-id="3caf5-147">Set up on an Ubuntu 16.04 Linux computer</span></span>

1. <span data-ttu-id="3caf5-148">PowerShell の最新バージョンをインストールします。「[Linux への PowerShell Core のインストール](../../install/installing-powershell-core-on-linux.md#ubuntu-1604)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3caf5-148">Install the latest version of PowerShell, see [Installing PowerShell Core on Linux](../../install/installing-powershell-core-on-linux.md#ubuntu-1604).</span></span>
1. <span data-ttu-id="3caf5-149">[Ubuntu OpenSSH Server](https://help.ubuntu.com/lts/serverguide/openssh-server.html) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3caf5-149">Install [Ubuntu OpenSSH Server](https://help.ubuntu.com/lts/serverguide/openssh-server.html).</span></span>

   ```bash
   sudo apt install openssh-client
   sudo apt install openssh-server
   ```

1. <span data-ttu-id="3caf5-150">`sshd_config` で `/etc/ssh` ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-150">Edit the `sshd_config` file at location `/etc/ssh`.</span></span>

   <span data-ttu-id="3caf5-151">パスワード認証が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-151">Make sure password authentication is enabled:</span></span>

   ```
   PasswordAuthentication yes
   ```

   <span data-ttu-id="3caf5-152">PowerShell サブシステム エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-152">Add a PowerShell subsystem entry:</span></span>

   ```
   Subsystem powershell /usr/bin/pwsh -sshs -NoLogo -NoProfile
   ```

   <span data-ttu-id="3caf5-153">必要であれば、キー認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3caf5-153">Optionally, enable key authentication:</span></span>

   ```
   PubkeyAuthentication yes
   ```

1. <span data-ttu-id="3caf5-154">**sshd** サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-154">Restart the **sshd** service.</span></span>

   ```bash
   sudo service sshd restart
   ```

## <a name="set-up-on-a-macos-computer"></a><span data-ttu-id="3caf5-155">macOS コンピューターでの設定</span><span class="sxs-lookup"><span data-stu-id="3caf5-155">Set up on a macOS computer</span></span>

1. <span data-ttu-id="3caf5-156">PowerShell の最新バージョンをインストールします。「[macOS への PowerShell Core のインストール](../../install/installing-powershell-core-on-macos.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3caf5-156">Install the latest version of PowerShell, see [Installing PowerShell Core on macOS](../../install/installing-powershell-core-on-macos.md).</span></span>

   <span data-ttu-id="3caf5-157">次の手順で SSH リモート処理が有効になっていることを確認します</span><span class="sxs-lookup"><span data-stu-id="3caf5-157">Make sure SSH Remoting is enabled by following these steps:</span></span>

   1. <span data-ttu-id="3caf5-158">`System Preferences`を開きます。</span><span class="sxs-lookup"><span data-stu-id="3caf5-158">Open `System Preferences`.</span></span>
   1. <span data-ttu-id="3caf5-159">`Sharing` をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3caf5-159">Click on `Sharing`.</span></span>
   1. <span data-ttu-id="3caf5-160">`Remote Login` にオンにして `Remote Login: On` を設定します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-160">Check `Remote Login` to set `Remote Login: On`.</span></span>
   1. <span data-ttu-id="3caf5-161">適切なユーザーにアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-161">Allow access to the appropriate users.</span></span>

1. <span data-ttu-id="3caf5-162">`sshd_config` で `/private/etc/ssh/sshd_config` ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-162">Edit the `sshd_config` file at location `/private/etc/ssh/sshd_config`.</span></span>

   <span data-ttu-id="3caf5-163">**nano** などのテキスト エディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-163">Use a text editor such as **nano**:</span></span>

   ```bash
   sudo nano /private/etc/ssh/sshd_config
   ```

   <span data-ttu-id="3caf5-164">パスワード認証が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-164">Make sure password authentication is enabled:</span></span>

   ```
   PasswordAuthentication yes
   ```

   <span data-ttu-id="3caf5-165">PowerShell サブシステム エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-165">Add a PowerShell subsystem entry:</span></span>

   ```
   Subsystem powershell /usr/local/bin/pwsh -sshs -NoLogo -NoProfile
   ```

   <span data-ttu-id="3caf5-166">必要であれば、キー認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3caf5-166">Optionally, enable key authentication:</span></span>

   ```
   PubkeyAuthentication yes
   ```

1. <span data-ttu-id="3caf5-167">**sshd** サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-167">Restart the **sshd** service.</span></span>

   ```bash
   sudo launchctl stop com.openssh.sshd
   sudo launchctl start com.openssh.sshd
   ```

## <a name="authentication"></a><span data-ttu-id="3caf5-168">認証</span><span class="sxs-lookup"><span data-stu-id="3caf5-168">Authentication</span></span>

<span data-ttu-id="3caf5-169">SSH を使用する PowerShell リモート処理では、SSH クライアントと SSH サービスの間の認証交換に依存し、認証スキーム自体は何も実装されません。</span><span class="sxs-lookup"><span data-stu-id="3caf5-169">PowerShell remoting over SSH relies on the authentication exchange between the SSH client and SSH service and doesn't implement any authentication schemes itself.</span></span> <span data-ttu-id="3caf5-170">結果として、多要素認証などの構成されている認証スキームはすべて SSH によって処理され、PowerShell からは独立します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-170">The result is that any configured authentication schemes including multi-factor authentication are handled by SSH and independent of PowerShell.</span></span> <span data-ttu-id="3caf5-171">たとえば、セキュリティ強化のため、公開キー認証と 1 回限りのパスワードを要求するように、SSH サービスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3caf5-171">For example, you can configure the SSH service to require public key authentication and a one-time password for added security.</span></span> <span data-ttu-id="3caf5-172">多要素認証の構成については、このドキュメントでは説明されていません。</span><span class="sxs-lookup"><span data-stu-id="3caf5-172">Configuration of multi-factor authentication is outside the scope of this documentation.</span></span> <span data-ttu-id="3caf5-173">多要素認証を正しく構成し、PowerShell リモート処理での使用を試みる前に PowerShell の外部での動作を検証する方法については、SSH のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3caf5-173">Refer to documentation for SSH on how to correctly configure multi-factor authentication and validate it works outside of PowerShell before attempting to use it with PowerShell remoting.</span></span>

## <a name="powershell-remoting-example"></a><span data-ttu-id="3caf5-174">PowerShell リモート処理の例</span><span class="sxs-lookup"><span data-stu-id="3caf5-174">PowerShell remoting example</span></span>

<span data-ttu-id="3caf5-175">リモート処理をテストする最も簡単な方法は、1 台のコンピューターでリモート処理を試行することです。</span><span class="sxs-lookup"><span data-stu-id="3caf5-175">The easiest way to test remoting is to try it on a single computer.</span></span> <span data-ttu-id="3caf5-176">以下の例では、同じ Linux コンピューターに戻るリモート セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-176">In this example, we create a remote session back to the same Linux computer.</span></span> <span data-ttu-id="3caf5-177">PowerShell コマンドレットを対話的に使用しているので、SSH からホスト コンピューターの確認を求めるプロンプトと、パスワードを求めるプロンプトが表示されています。</span><span class="sxs-lookup"><span data-stu-id="3caf5-177">We're using PowerShell cmdlets interactively so we see prompts from SSH asking to verify the host computer and prompting for a password.</span></span> <span data-ttu-id="3caf5-178">Windows コンピューター上で同じ操作を行って、リモート処理の動作を確実にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3caf5-178">You can do the same thing on a Windows computer to ensure remoting is working.</span></span> <span data-ttu-id="3caf5-179">その後、ホスト名を変更して、コンピューター間をリモート接続します。</span><span class="sxs-lookup"><span data-stu-id="3caf5-179">Then, remote between computers by changing the host name.</span></span>

```powershell
#
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

```Output
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

### <a name="known-issues"></a><span data-ttu-id="3caf5-180">既知の問題</span><span class="sxs-lookup"><span data-stu-id="3caf5-180">Known issues</span></span>

<span data-ttu-id="3caf5-181">**sudo** コマンドは、Linux コンピューターへのリモート セッションでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="3caf5-181">The **sudo** command doesn't work in a remote session to a Linux computer.</span></span>

## <a name="see-also"></a><span data-ttu-id="3caf5-182">参照</span><span class="sxs-lookup"><span data-stu-id="3caf5-182">See also</span></span>

[<span data-ttu-id="3caf5-183">Linux に PowerShell Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="3caf5-183">Installing PowerShell Core on Linux</span></span>](../../install/installing-powershell-core-on-linux.md#ubuntu-1604)

[<span data-ttu-id="3caf5-184">macOS に PowerShell Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="3caf5-184">Installing PowerShell Core on macOS</span></span>](../../install/installing-powershell-core-on-macos.md)

[<span data-ttu-id="3caf5-185">Windows に PowerShell Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="3caf5-185">Installing PowerShell Core on Windows</span></span>](../../install/installing-powershell-core-on-windows.md#msi)

[<span data-ttu-id="3caf5-186">OpenSSH で Windows を管理する</span><span class="sxs-lookup"><span data-stu-id="3caf5-186">Manage Windows with OpenSSH</span></span>](/windows-server/administration/openssh/openssh_overview)

[<span data-ttu-id="3caf5-187">OpenSSH キーの管理</span><span class="sxs-lookup"><span data-stu-id="3caf5-187">Managing OpenSSH Keys</span></span>](/windows-server/administration/openssh/openssh_keymanagement)

[<span data-ttu-id="3caf5-188">Ubuntu SSH</span><span class="sxs-lookup"><span data-stu-id="3caf5-188">Ubuntu SSH</span></span>](https://help.ubuntu.com/lts/serverguide/openssh-server.html)
