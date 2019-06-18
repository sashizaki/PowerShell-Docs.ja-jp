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
# <a name="installing-powershell-core-on-windows"></a><span data-ttu-id="0115c-103">Windows への PowerShell Core のインストール</span><span class="sxs-lookup"><span data-stu-id="0115c-103">Installing PowerShell Core on Windows</span></span>

<span data-ttu-id="0115c-104">Windows に PowerShell Core をインストールする方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="0115c-104">There are multiple ways to install PowerShell Core in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0115c-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="0115c-105">Prerequisites</span></span>

<span data-ttu-id="0115c-106">WSMan を介して PowerShell のリモート処理を有効にするには、次の前提条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="0115c-106">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="0115c-107">Windows 10 以前のバージョンの Windows に [ユニバーサル C ランタイム](https://www.microsoft.com/download/details.aspx?id=50410)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0115c-107">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions prior to Windows 10.</span></span> <span data-ttu-id="0115c-108">これは、直接ダウンロードすることも、Windows Update 経由で入手することもできます。</span><span class="sxs-lookup"><span data-stu-id="0115c-108">It is available via direct download or Windows Update.</span></span> <span data-ttu-id="0115c-109">修正プログラムが(オプション パッケージも含め)すべて適用されていて、かつサポート対象のシステムには、既にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="0115c-109">Fully patched (including optional packages), supported systems will already have this installed.</span></span>
- <span data-ttu-id="0115c-110">Windows Management Framework (WMF) 4.0 以降を Windows 7 と Windows Server 2008 R2 にインストールします。</span><span class="sxs-lookup"><span data-stu-id="0115c-110">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="0115c-111">WMF の詳細については、[WMF の概要](/powershell/wmf/overview)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0115c-111">For more information about WMF, see [WMF Overview](/powershell/wmf/overview).</span></span>

## <a name="a-idmsi-installing-the-msi-package"></a><span data-ttu-id="0115c-112"><a id="msi" />MSI パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="0115c-112"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="0115c-113">PowerShell を Windows クライアントまたは Windows Server にインストールするには (Windows 7 SP1、Server 2008 R2 以降が対象)、Microsoft の GitHub [リリース][releases] ページから MSI パッケージをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="0115c-113">To install PowerShell on a Windows client or Windows Server (works on Windows 7 SP1, Server 2008 R2, and later), download the MSI package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="0115c-114">インストールするリリースの **[資産]** セクションまで下へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="0115c-114">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="0115c-115">[資産] セクションは折りたたまれている場合があります。その場合は、クリックして展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0115c-115">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="0115c-116">MSI ファイルは、`PowerShell-<version>-win-<os-arch>.msi` のようになります。</span><span class="sxs-lookup"><span data-stu-id="0115c-116">The MSI file looks like this - `PowerShell-<version>-win-<os-arch>.msi`</span></span>
<!-- TODO: should be updated to point to the Download Center as well -->

<span data-ttu-id="0115c-117">ダウンロードしたら、インストーラーをダブルクリックし、プロンプトの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="0115c-117">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="0115c-118">インストーラーにより、Windows の [スタート] メニューにショートカットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0115c-118">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="0115c-119">パッケージは、既定で `$env:ProgramFiles\PowerShell\<version>` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0115c-119">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="0115c-120">PowerShell は、スタート メニューまたは  `$env:ProgramFiles\PowerShell\<version>\pwsh.exe` から起動できます。</span><span class="sxs-lookup"><span data-stu-id="0115c-120">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="0115c-121">コマンド ラインからの管理者インストール</span><span class="sxs-lookup"><span data-stu-id="0115c-121">Administrative install from the command line</span></span>

<span data-ttu-id="0115c-122">MSI パッケージは、コマンド ラインからインストールできます。</span><span class="sxs-lookup"><span data-stu-id="0115c-122">MSI packages can be installed from the command line.</span></span> <span data-ttu-id="0115c-123">これにより、管理者はユーザーの介入なしでパッケージを展開できます。</span><span class="sxs-lookup"><span data-stu-id="0115c-123">This allows administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="0115c-124">PowerShell 用の MSI パッケージには、インストールのオプションを制御するための次のプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0115c-124">The MSI package for PowerShell includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="0115c-125">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - このプロパティでは、エクスプローラーのコンテキスト メニューに **[Open PowerShell]\(PowerShell を開く\)** 項目を追加するためのオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="0115c-125">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="0115c-126">**ENABLE_PSREMOTING** - このプロパティでは、インストール中に PowerShell リモート処理を有効にするためのオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="0115c-126">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="0115c-127">**REGISTER_MANIFEST** - このプロパティでは、Windows イベント ログのマニフェストを登録するためのオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="0115c-127">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="0115c-128">すべてのインストール オプションを有効にして PowerShell Core をサイレント インストールする方法を、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="0115c-128">The following examples shows how to silently install PowerShell Core with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-<version>-win-<os-arch>.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="0115c-129">Msiexec.exe 用のコマンド ライン オプションの完全な一覧については、[コマンド ライン オプション](/windows/desktop/Msi/command-line-options)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0115c-129">For a full list of command line options for Msiexec.exe, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

## <a name="a-idzip-installing-the-zip-package"></a><span data-ttu-id="0115c-130"><a id="zip" />ZIP パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="0115c-130"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="0115c-131">PowerShell バイナリ ZIP アーカイブは、高度な展開シナリオ用に用意されています。</span><span class="sxs-lookup"><span data-stu-id="0115c-131">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="0115c-132">なお、ZIP アーカイブを使用する場合、MSI パッケージのような前提条件確認は行われません。</span><span class="sxs-lookup"><span data-stu-id="0115c-132">Be noted that when using the ZIP archive, you won't get the prerequisites check as in the MSI package.</span></span> <span data-ttu-id="0115c-133">WSMan 経由でのリモート処理を正常に動作させるために、[前提条件](#prerequisites)を満たしていることを確かめてください。</span><span class="sxs-lookup"><span data-stu-id="0115c-133">For remoting over WSMan to work properly, ensure that you have met the [prerequisites](#prerequisites).</span></span>

## <a name="deploying-on-windows-iot"></a><span data-ttu-id="0115c-134">Windows IoT への展開</span><span class="sxs-lookup"><span data-stu-id="0115c-134">Deploying on Windows IoT</span></span>

<span data-ttu-id="0115c-135">Windows IoT には既に PowerShell Core 6 の展開に使用するための Windows PowerShell が付属しています。</span><span class="sxs-lookup"><span data-stu-id="0115c-135">Windows IoT already comes with Windows PowerShell which we will use to deploy PowerShell Core 6.</span></span>

1. <span data-ttu-id="0115c-136">ターゲット デバイスに対して `PSSession` を作成します</span><span class="sxs-lookup"><span data-stu-id="0115c-136">Create `PSSession` to target device</span></span>

   ```powershell
   $s = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

2. <span data-ttu-id="0115c-137">ZIP パッケージをデバイスにコピーします</span><span class="sxs-lookup"><span data-stu-id="0115c-137">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

3. <span data-ttu-id="0115c-138">デバイスに接続してアーカイブを展開します</span><span class="sxs-lookup"><span data-stu-id="0115c-138">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

4. <span data-ttu-id="0115c-139">PowerShell Core 6 へのリモート処理を設定します</span><span class="sxs-lookup"><span data-stu-id="0115c-139">Setup remoting to PowerShell Core 6</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

5. <span data-ttu-id="0115c-140">デバイス上の PowerShell Core 6 エンドポイントに接続します</span><span class="sxs-lookup"><span data-stu-id="0115c-140">Connect to PowerShell Core 6 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-nano-server"></a><span data-ttu-id="0115c-141">Nano Server への展開</span><span class="sxs-lookup"><span data-stu-id="0115c-141">Deploying on Nano Server</span></span>

<span data-ttu-id="0115c-142">これらの手順では、Nano Server イメージ上で PowerShell のバージョンが既に実行されており、それが [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) で生成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0115c-142">These instructions assume that a version of PowerShell is already running on the Nano Server image and that it has been generated by the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).</span></span>
<span data-ttu-id="0115c-143">Nano Server は "ヘッドレス" OS です。</span><span class="sxs-lookup"><span data-stu-id="0115c-143">Nano Server is a "headless" OS.</span></span> <span data-ttu-id="0115c-144">コア バイナリを展開するには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="0115c-144">Core binaries can be deploy using two different methods.</span></span>

1. <span data-ttu-id="0115c-145">オフライン: Nano Server VHD をマウントし、zip ファイルの中身をマウント イメージ内の選択した場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="0115c-145">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
2. <span data-ttu-id="0115c-146">オンライン: zip ファイルを PowerShell セッションを介して転送し、選択した場所にそれを展開します。</span><span class="sxs-lookup"><span data-stu-id="0115c-146">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="0115c-147">いずれの場合も、Windows 10 x64 ZIP リリース パッケージが必要であり、"管理者" PowerShell インスタンス内でコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0115c-147">In both cases, you will need the Windows 10 x64 ZIP release package and will need to run the commands within an "Administrator" PowerShell instance.</span></span>

### <a name="offline-deployment-of-powershell-core"></a><span data-ttu-id="0115c-148">PowerShell Core のオフラインでの展開</span><span class="sxs-lookup"><span data-stu-id="0115c-148">Offline Deployment of PowerShell Core</span></span>

1. <span data-ttu-id="0115c-149">お好みの zip ユーティリティを使用して、マウントされた Nano Server イメージ内のディレクトリにパッケージを解凍します。</span><span class="sxs-lookup"><span data-stu-id="0115c-149">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
2. <span data-ttu-id="0115c-150">イメージをマウント解除し、ブートします。</span><span class="sxs-lookup"><span data-stu-id="0115c-150">Unmount the image and boot it.</span></span>
3. <span data-ttu-id="0115c-151">Windows PowerShell のインボックス インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="0115c-151">Connect to the inbox instance of Windows PowerShell.</span></span>
4. <span data-ttu-id="0115c-152">「[別のインスタンスのテクニック](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)」の、リモート エンドポイントを作成する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0115c-152">Follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

### <a name="online-deployment-of-powershell-core"></a><span data-ttu-id="0115c-153">オンラインでの PowerShell Core の展開</span><span class="sxs-lookup"><span data-stu-id="0115c-153">Online Deployment of PowerShell Core</span></span>

<span data-ttu-id="0115c-154">次の手順では、PowerShell Core を Nano Server の実行中のインスタンスに展開し、そのリモート エンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="0115c-154">The following steps guide you through the deployment of PowerShell Core to a running instance of Nano Server and the configuration of its remote endpoint.</span></span>

- <span data-ttu-id="0115c-155">Windows PowerShell のインボックス インスタンスに接続する</span><span class="sxs-lookup"><span data-stu-id="0115c-155">Connect to the inbox instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="0115c-156">Nano Server のインスタンスにファイルをコピーする</span><span class="sxs-lookup"><span data-stu-id="0115c-156">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="0115c-157">セッションに入る</span><span class="sxs-lookup"><span data-stu-id="0115c-157">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="0115c-158">ZIP ファイルを抽出する</span><span class="sxs-lookup"><span data-stu-id="0115c-158">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShellCore_<version>"
  ```

- <span data-ttu-id="0115c-159">WSMan を使用してリモート処理を行う場合、「[別のインスタンスのテクニック](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)」の、リモート エンドポイントを作成する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0115c-159">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="0115c-160">リモート エンドポイントの作成方法</span><span class="sxs-lookup"><span data-stu-id="0115c-160">How to create a remoting endpoint</span></span>

<span data-ttu-id="0115c-161">PowerShell Core は、WSMan と SSH の両方で PowerShell Remoting Protocol (PSRP) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0115c-161">PowerShell Core supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="0115c-162">詳細については、次のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0115c-162">For more information, see:</span></span>

- <span data-ttu-id="0115c-163">[PowerShell Core での SSH リモート処理][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="0115c-163">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="0115c-164">[PowerShell Core での WSMan リモート処理][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="0115c-164">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

<!-- [download-center]: TODO -->

[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
