---
title: Windows への PowerShell のインストール
description: Windows への PowerShell のインストールに関する情報
ms.date: 05/21/2020
ms.openlocfilehash: 864f297e4f569030439bd6b581ef593d36f8b910
ms.sourcegitcommit: fd6a33b9fac973b3554fecfea7f51475e650a606
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2020
ms.locfileid: "83791478"
---
# <a name="installing-powershell-on-windows"></a><span data-ttu-id="4457e-103">Windows への PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="4457e-103">Installing PowerShell on Windows</span></span>

<span data-ttu-id="4457e-104">Windows に PowerShell をインストールする方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="4457e-104">There are multiple ways to install PowerShell in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4457e-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="4457e-105">Prerequisites</span></span>

<span data-ttu-id="4457e-106">PowerShell の最新リリースは、Windows 7 SP1、Server 2008 R2、およびそれ以降のバージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4457e-106">The latest release of PowerShell is supported on Windows 7 SP1, Server 2008 R2, and later versions.</span></span>

<span data-ttu-id="4457e-107">WSMan を介して PowerShell のリモート処理を有効にするには、次の前提条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="4457e-107">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="4457e-108">Windows 10 より前のバージョンの Windows に[ユニバーサル C ランタイム](https://www.microsoft.com/download/details.aspx?id=50410)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4457e-108">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions predating Windows 10.</span></span> <span data-ttu-id="4457e-109">これは、直接ダウンロードすることも、Windows Update 経由で入手することもできます。</span><span class="sxs-lookup"><span data-stu-id="4457e-109">It's available via direct download or Windows Update.</span></span> <span data-ttu-id="4457e-110">完全にパッチが適用されたシステムには、既にこのパッケージがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="4457e-110">Fully patched systems already have this package installed.</span></span>
- <span data-ttu-id="4457e-111">Windows Management Framework (WMF) 4.0 以降を Windows 7 と Windows Server 2008 R2 にインストールします。</span><span class="sxs-lookup"><span data-stu-id="4457e-111">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="4457e-112">WMF の詳細については、[WMF の概要](/powershell/scripting/wmf/overview)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4457e-112">For more information about WMF, see [WMF Overview](/powershell/scripting/wmf/overview).</span></span>

## <a name="download-the-installer-package"></a><span data-ttu-id="4457e-113">インストーラー パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="4457e-113">Download the installer package</span></span>

<span data-ttu-id="4457e-114">Windows に PowerShell をインストールするには、GitHub の[リリース][releases] ページからインストール パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="4457e-114">To install PowerShell on Windows, download the install package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="4457e-115">リリース ページの **[Assets]** セクションまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="4457e-115">Scroll down to the **Assets** section of the Release page.</span></span> <span data-ttu-id="4457e-116">**[Assets]** セクションは折りたたまれている場合があります。その場合は、クリックして展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4457e-116">The **Assets** section may be collapsed, so you may need to click to expand it.</span></span>

## <a name="installing-the-msi-package"></a><span data-ttu-id="4457e-117"><a id="msi" />MSI パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="4457e-117"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="4457e-118">MSI ファイルは、`PowerShell-<version>-win-<os-arch>.msi` のようになります。</span><span class="sxs-lookup"><span data-stu-id="4457e-118">The MSI file looks like `PowerShell-<version>-win-<os-arch>.msi`.</span></span> <span data-ttu-id="4457e-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4457e-119">For example:</span></span>

- `PowerShell-7.0.1-win-x64.msi`
- `PowerShell-7.0.1-win-x86.msi`

<span data-ttu-id="4457e-120">ダウンロードしたら、インストーラーをダブルクリックし、プロンプトの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="4457e-120">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="4457e-121">インストーラーにより、Windows の [スタート] メニューにショートカットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4457e-121">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="4457e-122">パッケージは、既定で `$env:ProgramFiles\PowerShell\<version>` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4457e-122">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="4457e-123">PowerShell は、スタート メニューまたは  `$env:ProgramFiles\PowerShell\<version>\pwsh.exe` から起動できます。</span><span class="sxs-lookup"><span data-stu-id="4457e-123">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="4457e-124">PowerShell 7 は新しいディレクトリにインストールされ、Windows PowerShell 5.1 と side-by-side 実行されます。</span><span class="sxs-lookup"><span data-stu-id="4457e-124">PowerShell 7 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span> <span data-ttu-id="4457e-125">PowerShell Core 6.x がインストールされている場合、PowerShell 7 にインプレース アップグレードされ、PowerShell Core 6.x は削除されます。</span><span class="sxs-lookup"><span data-stu-id="4457e-125">For PowerShell Core 6.x, PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> - <span data-ttu-id="4457e-126">PowerShell 7 は `$env:ProgramFiles\PowerShell\7` にインストールされます</span><span class="sxs-lookup"><span data-stu-id="4457e-126">PowerShell 7 is installed to `$env:ProgramFiles\PowerShell\7`</span></span>
> - <span data-ttu-id="4457e-127">`$env:ProgramFiles\PowerShell\7` フォルダーは `$env:PATH` に追加されます</span><span class="sxs-lookup"><span data-stu-id="4457e-127">The `$env:ProgramFiles\PowerShell\7` folder is added to `$env:PATH`</span></span>
> - <span data-ttu-id="4457e-128">`$env:ProgramFiles\PowerShell\6` フォルダーは削除されます</span><span class="sxs-lookup"><span data-stu-id="4457e-128">The `$env:ProgramFiles\PowerShell\6` folder is deleted</span></span>
>
> <span data-ttu-id="4457e-129">PowerShell 6 を PowerShell 7 と side-by-side 実行する必要がある場合は、[ZIP インストール](#zip)方法を使用して PowerShell 6 を再インストールします。</span><span class="sxs-lookup"><span data-stu-id="4457e-129">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [ZIP install](#zip) method.</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="4457e-130">コマンド ラインからの管理者インストール</span><span class="sxs-lookup"><span data-stu-id="4457e-130">Administrative install from the command line</span></span>

<span data-ttu-id="4457e-131">MSI パッケージはコマンド ラインからインストールできるため、管理者はユーザーの介入なしにパッケージを展開できます。</span><span class="sxs-lookup"><span data-stu-id="4457e-131">MSI packages can be installed from the command line allowing administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="4457e-132">MSI パッケージには、インストールのオプションを制御するための次のプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4457e-132">The MSI package includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="4457e-133">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - このプロパティでは、エクスプローラーのコンテキスト メニューに **[Open PowerShell]\(PowerShell を開く\)** 項目を追加するためのオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="4457e-133">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="4457e-134">**ENABLE_PSREMOTING** - このプロパティでは、インストール中に PowerShell リモート処理を有効にするためのオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="4457e-134">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="4457e-135">**REGISTER_MANIFEST** - このプロパティでは、Windows イベント ログのマニフェストを登録するためのオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="4457e-135">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="4457e-136">すべてのインストール オプションを有効にして PowerShell をサイレント インストールする方法を、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="4457e-136">The following example shows how to silently install PowerShell with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-7.0.1-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="4457e-137">`Msiexec.exe` 用のコマンド ライン オプションの完全な一覧については、[コマンド ライン オプション](/windows/desktop/Msi/command-line-options)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4457e-137">For a full list of command-line options for `Msiexec.exe`, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

## <a name="installing-the-msix-package"></a><span data-ttu-id="4457e-138"><a id="msix" />MSIX パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="4457e-138"><a id="msix" />Installing the MSIX package</span></span>

<span data-ttu-id="4457e-139">Windows 10 クライアントに MSIX パッケージを手動でインストールするには、Microsoft の GitHub [リリース][releases] ページから MSIX パッケージをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="4457e-139">To manually install the MSIX package on a Windows 10 client, download the MSIX package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="4457e-140">インストールしたいリリースの **[Assets]** セクションまでスクロールダウンします。</span><span class="sxs-lookup"><span data-stu-id="4457e-140">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="4457e-141">[Assets] セクションは折りたたまれている場合があります。その場合は、クリックして展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4457e-141">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="4457e-142">MSIX ファイルは、`PowerShell-<version>-win-<os-arch>.msix` のようになります。</span><span class="sxs-lookup"><span data-stu-id="4457e-142">The MSIX file looks like this - `PowerShell-<version>-win-<os-arch>.msix`</span></span>

<span data-ttu-id="4457e-143">パッケージをインストールするには、`Add-AppxPackage` コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4457e-143">To install the package, you must use the `Add-AppxPackage` cmdlet.</span></span>

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

> [!NOTE]
> <span data-ttu-id="4457e-144">MSIX パッケージはまだリリースされていません。</span><span class="sxs-lookup"><span data-stu-id="4457e-144">The MSIX package has not been released yet.</span></span> <span data-ttu-id="4457e-145">パッケージがリリースされると、Microsoft Store と GitHub の[リリース][releases] ページから入手できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4457e-145">When released, the package will be available in the Microsoft Store and from the GitHub [releases][releases] page.</span></span>

## <a name="installing-the-zip-package"></a><span data-ttu-id="4457e-146"><a id="zip" />ZIP パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="4457e-146"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="4457e-147">PowerShell バイナリ ZIP アーカイブは、高度な展開シナリオ用に用意されています。</span><span class="sxs-lookup"><span data-stu-id="4457e-147">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="4457e-148">ZIP アーカイブをインストールしても、MSI パッケージのように前提条件は確認されません。</span><span class="sxs-lookup"><span data-stu-id="4457e-148">Installing the ZIP archive doesn't check the prerequisites like the MSI packages do.</span></span> <span data-ttu-id="4457e-149">[リリース][releases] ページから ZIP アーカイブをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="4457e-149">Download the ZIP archive from the [releases][releases] page.</span></span> <span data-ttu-id="4457e-150">ファイルのダウンロード方法によっては、`Unblock-File` コマンドレットを使用して、ファイルのブロックを解除することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4457e-150">Depending on how you download the file you may need to unblock the file using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="4457e-151">任意の場所にコンテンツを解凍し、そこから `pwsh.exe` を実行します。</span><span class="sxs-lookup"><span data-stu-id="4457e-151">Unzip the contents to the location of your choice and run `pwsh.exe` from there.</span></span> <span data-ttu-id="4457e-152">WSMan 経由でのリモート処理を正常に動作させるために、[前提条件](#prerequisites)を満たしていることを確かめてください。</span><span class="sxs-lookup"><span data-stu-id="4457e-152">For remoting over WSMan to work properly, ensure that you've met the [prerequisites](#prerequisites).</span></span>

## <a name="deploying-on-windows-10-iot-enterprise"></a><span data-ttu-id="4457e-153">Windows 10 IoT Enterprise への展開</span><span class="sxs-lookup"><span data-stu-id="4457e-153">Deploying on Windows 10 IoT Enterprise</span></span>

<span data-ttu-id="4457e-154">Windows 10 IoT Enterprise には、PowerShell 7 の展開に使用できる Windows PowerShell が付属しています。</span><span class="sxs-lookup"><span data-stu-id="4457e-154">Windows 10 IoT Enterprise comes with Windows PowerShell, which we can use to deploy PowerShell 7.</span></span>

1. <span data-ttu-id="4457e-155">ターゲット デバイスに対して `PSSession` を作成します</span><span class="sxs-lookup"><span data-stu-id="4457e-155">Create `PSSession` to target device</span></span>

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

2. <span data-ttu-id="4457e-156">ZIP パッケージをデバイスにコピーします</span><span class="sxs-lookup"><span data-stu-id="4457e-156">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

3. <span data-ttu-id="4457e-157">デバイスに接続してアーカイブを展開します</span><span class="sxs-lookup"><span data-stu-id="4457e-157">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

4. <span data-ttu-id="4457e-158">PowerShell 7 へのリモート処理を設定します</span><span class="sxs-lookup"><span data-stu-id="4457e-158">Set up remoting to PowerShell 7</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

5. <span data-ttu-id="4457e-159">デバイス上の PowerShell 7 エンドポイントに接続します</span><span class="sxs-lookup"><span data-stu-id="4457e-159">Connect to PowerShell 7 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-windows-10-iot-core"></a><span data-ttu-id="4457e-160">Windows 10 IoT Core への展開</span><span class="sxs-lookup"><span data-stu-id="4457e-160">Deploying on Windows 10 IoT Core</span></span>

<span data-ttu-id="4457e-161">PowerShell 7 の展開に使用できる *IOT_POWERSHELL* 機能を取り込む場合、Windows 10 IoT Core によって Windows PowerShell が追加されます。</span><span class="sxs-lookup"><span data-stu-id="4457e-161">Windows 10 IoT Core adds Windows PowerShell when you include *IOT_POWERSHELL* feature, which we can use to deploy PowerShell 7.</span></span>
<span data-ttu-id="4457e-162">上記で Windows 10 IoT Enterprise に対して定義した手順は、IoT Core にも適用できます。</span><span class="sxs-lookup"><span data-stu-id="4457e-162">The steps defined above for Windows 10 IoT Enterprise can be followed for IoT Core as well.</span></span>

<span data-ttu-id="4457e-163">配布イメージに最新の powershell を追加する場合は、[Import-PSCoreRelease](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease) コマンドを使用して、ワークスペースにパッケージを取り込み、さらに *OPENSRC_POWERSHELL* 機能をご利用のイメージに追加します。</span><span class="sxs-lookup"><span data-stu-id="4457e-163">For adding the latest powershell in the shipping image, use [Import-PSCoreRelease](https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease) command to include the package in the workarea and add *OPENSRC_POWERSHELL* feature to your image.</span></span>

> [!NOTE]
> <span data-ttu-id="4457e-164">ARM64 アーキテクチャの場合、*IOT_POWERSHELL* を取り込むときに、Windows Powershell は追加されません。</span><span class="sxs-lookup"><span data-stu-id="4457e-164">For ARM64 architecture, Windows Powershell is not added when you include *IOT_POWERSHELL*.</span></span> <span data-ttu-id="4457e-165">そのため、zip ベースのインストールは機能しません。</span><span class="sxs-lookup"><span data-stu-id="4457e-165">So the zip based install will not work.</span></span>
> <span data-ttu-id="4457e-166">イメージに追加するには、Import-PSCoreRelease コマンドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4457e-166">You will need to use Import-PSCoreRelease command to add it in the image.</span></span>

## <a name="deploying-on-nano-server"></a><span data-ttu-id="4457e-167">Nano Server への展開</span><span class="sxs-lookup"><span data-stu-id="4457e-167">Deploying on Nano Server</span></span>

<span data-ttu-id="4457e-168">以下の手順では、Nano Server が "ヘッドレス" OS であり、あるバージョンの PowerShell が既に実行されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="4457e-168">These instructions assume that the Nano Server is a "headless" OS that has a version of PowerShell is already running on it.</span></span> <span data-ttu-id="4457e-169">詳細については、[Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4457e-169">For more information, see the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) documentation.</span></span>

<span data-ttu-id="4457e-170">PowerShell バイナリを展開するには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="4457e-170">PowerShell binaries can be deployed using two different methods.</span></span>

1. <span data-ttu-id="4457e-171">オフライン: Nano Server VHD をマウントし、zip ファイルの中身をマウント イメージ内の選択した場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="4457e-171">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
2. <span data-ttu-id="4457e-172">オンライン: zip ファイルを PowerShell セッションを介して転送し、選択した場所にそれを展開します。</span><span class="sxs-lookup"><span data-stu-id="4457e-172">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="4457e-173">どちらの場合も、Windows 10 x64 の ZIP リリース パッケージが必要です。</span><span class="sxs-lookup"><span data-stu-id="4457e-173">In both cases, you need the Windows 10 x64 ZIP release package.</span></span> <span data-ttu-id="4457e-174">PowerShell の "管理者" インスタンス内でコマンドを実行してください。</span><span class="sxs-lookup"><span data-stu-id="4457e-174">Run the commands within an "Administrator" instance of PowerShell.</span></span>

### <a name="offline-deployment-of-powershell"></a><span data-ttu-id="4457e-175">PowerShell のオフラインでの展開</span><span class="sxs-lookup"><span data-stu-id="4457e-175">Offline Deployment of PowerShell</span></span>

1. <span data-ttu-id="4457e-176">お好みの zip ユーティリティを使用して、マウントされた Nano Server イメージ内のディレクトリにパッケージを解凍します。</span><span class="sxs-lookup"><span data-stu-id="4457e-176">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
2. <span data-ttu-id="4457e-177">イメージをマウント解除し、ブートします。</span><span class="sxs-lookup"><span data-stu-id="4457e-177">Unmount the image and boot it.</span></span>
3. <span data-ttu-id="4457e-178">Windows PowerShell のインボックス インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="4457e-178">Connect to the inbox instance of Windows PowerShell.</span></span>
4. <span data-ttu-id="4457e-179">「[別のインスタンスのテクニック](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)」の、リモート エンドポイントを作成する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4457e-179">Follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

### <a name="online-deployment-of-powershell"></a><span data-ttu-id="4457e-180">PowerShell のオンラインでの展開</span><span class="sxs-lookup"><span data-stu-id="4457e-180">Online Deployment of PowerShell</span></span>

<span data-ttu-id="4457e-181">次の手順に従って、PowerShell を Nano Server に展開します。</span><span class="sxs-lookup"><span data-stu-id="4457e-181">Deploy PowerShell to Nano Server using the following steps.</span></span>

- <span data-ttu-id="4457e-182">Windows PowerShell のインボックス インスタンスに接続する</span><span class="sxs-lookup"><span data-stu-id="4457e-182">Connect to the inbox instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="4457e-183">Nano Server のインスタンスにファイルをコピーする</span><span class="sxs-lookup"><span data-stu-id="4457e-183">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="4457e-184">セッションに入る</span><span class="sxs-lookup"><span data-stu-id="4457e-184">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="4457e-185">ZIP ファイルを解凍します</span><span class="sxs-lookup"><span data-stu-id="4457e-185">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- <span data-ttu-id="4457e-186">WSMan を使用してリモート処理を行う場合、「[別のインスタンスのテクニック](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register)」の、リモート エンドポイントを作成する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4457e-186">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="4457e-187">.NET グローバル ツールとしてインストールする</span><span class="sxs-lookup"><span data-stu-id="4457e-187">Install as a .NET Global tool</span></span>

<span data-ttu-id="4457e-188">[.NET Core SDK](/dotnet/core/sdk) が既にインストールされている場合は、PowerShell を [.NET グローバル ツール](/dotnet/core/tools/global-tools)として簡単にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4457e-188">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="4457e-189">dotnet tool install によって、`$env:PATH` 環境変数に `$env:USERPROFILE\dotnet\tools` が追加されます。</span><span class="sxs-lookup"><span data-stu-id="4457e-189">The dotnet tool installer adds `$env:USERPROFILE\dotnet\tools` to your `$env:PATH` environment variable.</span></span> <span data-ttu-id="4457e-190">ただし、現在実行中のシェルには更新された `$env:PATH` が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="4457e-190">However, the currently running shell doesn't have the updated `$env:PATH`.</span></span> <span data-ttu-id="4457e-191">新しいシェルからは、「`pwsh`」と入力すると PowerShell を起動できます。</span><span class="sxs-lookup"><span data-stu-id="4457e-191">You can start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="4457e-192">リモート エンドポイントの作成方法</span><span class="sxs-lookup"><span data-stu-id="4457e-192">How to create a remoting endpoint</span></span>

<span data-ttu-id="4457e-193">PowerShell では、WSMan と SSH の両方について PowerShell Remoting Protocol (PSRP) がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4457e-193">PowerShell supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="4457e-194">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4457e-194">For more information, see:</span></span>

- <span data-ttu-id="4457e-195">[PowerShell Core での SSH リモート処理][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="4457e-195">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="4457e-196">[PowerShell Core での WSMan リモート処理][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="4457e-196">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

<!-- [download-center]: TODO -->

[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
