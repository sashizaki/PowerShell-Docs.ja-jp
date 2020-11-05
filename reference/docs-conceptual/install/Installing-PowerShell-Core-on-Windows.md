---
title: Windows への PowerShell のインストール
description: Windows への PowerShell のインストールに関する情報
ms.date: 10/30/2020
ms.openlocfilehash: 1b341b496cef34a2a98afeac9d24f0a51e8dbda0
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142788"
---
# <a name="installing-powershell-on-windows"></a><span data-ttu-id="26b86-103">Windows への PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="26b86-103">Installing PowerShell on Windows</span></span>

<span data-ttu-id="26b86-104">Windows に PowerShell をインストールする方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="26b86-104">There are multiple ways to install PowerShell in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="26b86-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="26b86-105">Prerequisites</span></span>

<span data-ttu-id="26b86-106">PowerShell の最新リリースは、Windows 7 SP1、Server 2008 R2、およびそれ以降のバージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="26b86-106">The latest release of PowerShell is supported on Windows 7 SP1, Server 2008 R2, and later versions.</span></span>

<span data-ttu-id="26b86-107">WSMan を介して PowerShell のリモート処理を有効にするには、次の前提条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="26b86-107">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="26b86-108">Windows 10 より前のバージョンの Windows に[ユニバーサル C ランタイム](https://www.microsoft.com/download/details.aspx?id=50410)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="26b86-108">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions predating Windows 10.</span></span> <span data-ttu-id="26b86-109">これは、直接ダウンロードすることも、Windows Update 経由で入手することもできます。</span><span class="sxs-lookup"><span data-stu-id="26b86-109">It's available via direct download or Windows Update.</span></span> <span data-ttu-id="26b86-110">完全にパッチが適用されたシステムには、既にこのパッケージがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="26b86-110">Fully patched systems already have this package installed.</span></span>
- <span data-ttu-id="26b86-111">Windows Management Framework (WMF) 4.0 以降を Windows 7 と Windows Server 2008 R2 にインストールします。</span><span class="sxs-lookup"><span data-stu-id="26b86-111">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="26b86-112">WMF の詳細については、[WMF の概要](/powershell/scripting/wmf/overview)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26b86-112">For more information about WMF, see [WMF Overview](/powershell/scripting/wmf/overview).</span></span>

## <a name="download-the-installer-package"></a><span data-ttu-id="26b86-113">インストーラー パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="26b86-113">Download the installer package</span></span>

<span data-ttu-id="26b86-114">Windows に PowerShell をインストールするには、GitHub の[リリース][releases] ページからインストール パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="26b86-114">To install PowerShell on Windows, download the install package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="26b86-115">リリース ページの **[Assets]** セクションまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="26b86-115">Scroll down to the **Assets** section of the Release page.</span></span> <span data-ttu-id="26b86-116">**[Assets]** セクションは折りたたまれている場合があります。その場合は、クリックして展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26b86-116">The **Assets** section may be collapsed, so you may need to click to expand it.</span></span>

## <a name="installing-the-msi-package"></a><span data-ttu-id="26b86-117"><a id="msi" />MSI パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="26b86-117"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="26b86-118">MSI ファイルは、`PowerShell-<version>-win-<os-arch>.msi` のようになります。</span><span class="sxs-lookup"><span data-stu-id="26b86-118">The MSI file looks like `PowerShell-<version>-win-<os-arch>.msi`.</span></span> <span data-ttu-id="26b86-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="26b86-119">For example:</span></span>

- `PowerShell-7.0.3-win-x64.msi`
- `PowerShell-7.0.3-win-x86.msi`

<span data-ttu-id="26b86-120">ダウンロードしたら、インストーラーをダブルクリックし、プロンプトの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="26b86-120">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="26b86-121">インストーラーにより、Windows の [スタート] メニューにショートカットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="26b86-121">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="26b86-122">パッケージは、既定で `$env:ProgramFiles\PowerShell\<version>` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="26b86-122">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="26b86-123">PowerShell は、スタート メニューまたは  `$env:ProgramFiles\PowerShell\<version>\pwsh.exe` から起動できます。</span><span class="sxs-lookup"><span data-stu-id="26b86-123">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="26b86-124">PowerShell 7 は新しいディレクトリにインストールされ、Windows PowerShell 5.1 と side-by-side 実行されます。</span><span class="sxs-lookup"><span data-stu-id="26b86-124">PowerShell 7 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span> <span data-ttu-id="26b86-125">PowerShell Core 6.x がインストールされている場合、PowerShell 7 にインプレース アップグレードされ、PowerShell Core 6.x は削除されます。</span><span class="sxs-lookup"><span data-stu-id="26b86-125">For PowerShell Core 6.x, PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> - <span data-ttu-id="26b86-126">PowerShell 7 は `$env:ProgramFiles\PowerShell\7` にインストールされます</span><span class="sxs-lookup"><span data-stu-id="26b86-126">PowerShell 7 is installed to `$env:ProgramFiles\PowerShell\7`</span></span>
> - <span data-ttu-id="26b86-127">`$env:ProgramFiles\PowerShell\7` フォルダーは `$env:PATH` に追加されます</span><span class="sxs-lookup"><span data-stu-id="26b86-127">The `$env:ProgramFiles\PowerShell\7` folder is added to `$env:PATH`</span></span>
> - <span data-ttu-id="26b86-128">`$env:ProgramFiles\PowerShell\6` フォルダーは削除されます</span><span class="sxs-lookup"><span data-stu-id="26b86-128">The `$env:ProgramFiles\PowerShell\6` folder is deleted</span></span>
>
> <span data-ttu-id="26b86-129">PowerShell 6 を PowerShell 7 と side-by-side 実行する必要がある場合は、[ZIP インストール](#zip)方法を使用して PowerShell 6 を再インストールします。</span><span class="sxs-lookup"><span data-stu-id="26b86-129">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [ZIP install](#zip) method.</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="26b86-130">コマンド ラインからの管理者インストール</span><span class="sxs-lookup"><span data-stu-id="26b86-130">Administrative install from the command line</span></span>

<span data-ttu-id="26b86-131">MSI パッケージはコマンド ラインからインストールできるため、管理者はユーザーの介入なしにパッケージを展開できます。</span><span class="sxs-lookup"><span data-stu-id="26b86-131">MSI packages can be installed from the command line allowing administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="26b86-132">MSI パッケージには、インストールのオプションを制御するための次のプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="26b86-132">The MSI package includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="26b86-133">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - このプロパティでは、エクスプローラーのコンテキスト メニューに **[Open PowerShell]\(PowerShell を開く\)** 項目を追加するためのオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="26b86-133">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="26b86-134">**ENABLE_PSREMOTING** - このプロパティでは、インストール中に PowerShell リモート処理を有効にするためのオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="26b86-134">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="26b86-135">**REGISTER_MANIFEST** - このプロパティでは、Windows イベント ログのマニフェストを登録するためのオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="26b86-135">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="26b86-136">すべてのインストール オプションを有効にして PowerShell をサイレント インストールする方法を、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="26b86-136">The following example shows how to silently install PowerShell with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-7.0.3-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="26b86-137">`Msiexec.exe` 用のコマンド ライン オプションの完全な一覧については、[コマンド ライン オプション](/windows/desktop/Msi/command-line-options)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="26b86-137">For a full list of command-line options for `Msiexec.exe`, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

### <a name="registry-keys-created-during-installation"></a><span data-ttu-id="26b86-138">インストール時に作成されるレジストリ キー</span><span class="sxs-lookup"><span data-stu-id="26b86-138">Registry keys created during installation</span></span>

<span data-ttu-id="26b86-139">PowerShell 7.1 以降では、MSI パッケージによって、インストール場所と PowerShell のバージョンを格納するレジストリ キーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="26b86-139">Beginning in PowerShell 7.1, the MSI package creates registry keys that store the installation location and version of PowerShell.</span></span> <span data-ttu-id="26b86-140">これらの値は `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>` にあります。</span><span class="sxs-lookup"><span data-stu-id="26b86-140">These values are located in `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`.</span></span> <span data-ttu-id="26b86-141">`<GUID>` の値は、ビルドの種類 (リリースまたはプレビュー)、メジャー バージョン、およびアーキテクチャごとに一意です。</span><span class="sxs-lookup"><span data-stu-id="26b86-141">The value of `<GUID>` is unique for each build type (release or preview), major version, and architecture.</span></span>

|    <span data-ttu-id="26b86-142">Release</span><span class="sxs-lookup"><span data-stu-id="26b86-142">Release</span></span>    | <span data-ttu-id="26b86-143">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="26b86-143">Architecture</span></span> |                                          <span data-ttu-id="26b86-144">レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="26b86-144">Registry Key</span></span>                                           |
| ------------- | :----------: | ----------------------------------------------------------------------------------------------- |
| <span data-ttu-id="26b86-145">7.1.x リリース</span><span class="sxs-lookup"><span data-stu-id="26b86-145">7.1.x Release</span></span> |     <span data-ttu-id="26b86-146">x86</span><span class="sxs-lookup"><span data-stu-id="26b86-146">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\1d00683b-0f84-4db8-a64f-2f98ad42fe06` |
| <span data-ttu-id="26b86-147">7.1.x リリース</span><span class="sxs-lookup"><span data-stu-id="26b86-147">7.1.x Release</span></span> |     <span data-ttu-id="26b86-148">X64</span><span class="sxs-lookup"><span data-stu-id="26b86-148">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\31ab5147-9a97-4452-8443-d9709f0516e1` |
| <span data-ttu-id="26b86-149">7.1.x プレビュー</span><span class="sxs-lookup"><span data-stu-id="26b86-149">7.1.x Preview</span></span> |     <span data-ttu-id="26b86-150">x86</span><span class="sxs-lookup"><span data-stu-id="26b86-150">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\86abcfbd-1ccc-4a88-b8b2-0facfde29094` |
| <span data-ttu-id="26b86-151">7.1.x プレビュー</span><span class="sxs-lookup"><span data-stu-id="26b86-151">7.1.x Preview</span></span> |     <span data-ttu-id="26b86-152">X64</span><span class="sxs-lookup"><span data-stu-id="26b86-152">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\39243d76-adaf-42b1-94fb-16ecf83237c8` |

<span data-ttu-id="26b86-153">これは、管理者と開発者が PowerShell へのパスを見つけるために使用できます。</span><span class="sxs-lookup"><span data-stu-id="26b86-153">This can be used by administrators and developers to find the path to PowerShell.</span></span> <span data-ttu-id="26b86-154">`<GUID>` の値は、すべてのプレビューおよびマイナー バージョンのリリースで同じになります。</span><span class="sxs-lookup"><span data-stu-id="26b86-154">The `<GUID>` values will be the same for all preview and minor version releases.</span></span> <span data-ttu-id="26b86-155">`<GUID>` の値はメジャー リリースごとに変更されます。</span><span class="sxs-lookup"><span data-stu-id="26b86-155">The `<GUID>` values are changed for each major release.</span></span>

## <a name="installing-the-msix-package"></a><span data-ttu-id="26b86-156"><a id="msix" />MSIX パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="26b86-156"><a id="msix" />Installing the MSIX package</span></span>

> [!NOTE]
> <span data-ttu-id="26b86-157">現時点では、MSIX パッケージは公式にサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="26b86-157">The MSIX package is not officially supported at this time.</span></span> <span data-ttu-id="26b86-158">私たちは引き続き、内部テストのみを目的としてパッケージをビルドします。</span><span class="sxs-lookup"><span data-stu-id="26b86-158">We continue to build the package for internal testing purposes only.</span></span>

<span data-ttu-id="26b86-159">Windows 10 クライアントに MSIX パッケージを手動でインストールするには、Microsoft の GitHub [リリース][releases] ページから MSIX パッケージをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="26b86-159">To manually install the MSIX package on a Windows 10 client, download the MSIX package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="26b86-160">インストールしたいリリースの **[Assets]** セクションまでスクロールダウンします。</span><span class="sxs-lookup"><span data-stu-id="26b86-160">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="26b86-161">[Assets] セクションは折りたたまれている場合があります。その場合は、クリックして展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26b86-161">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="26b86-162">MSIX ファイルは、`PowerShell-<version>-win-<os-arch>.msix` のようになります。</span><span class="sxs-lookup"><span data-stu-id="26b86-162">The MSIX file looks like this - `PowerShell-<version>-win-<os-arch>.msix`</span></span>

<span data-ttu-id="26b86-163">パッケージをインストールするには、`Add-AppxPackage` コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26b86-163">To install the package, you must use the `Add-AppxPackage` cmdlet.</span></span>

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

## <a name="installing-the-zip-package"></a><span data-ttu-id="26b86-164"><a id="zip" />ZIP パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="26b86-164"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="26b86-165">PowerShell バイナリ ZIP アーカイブは、高度な展開シナリオ用に用意されています。</span><span class="sxs-lookup"><span data-stu-id="26b86-165">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="26b86-166">[リリース][releases] ページから、次のいずれかの ZIP アーカイブをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="26b86-166">Download one of the following ZIP archives from the [releases][releases] page.</span></span>

- <span data-ttu-id="26b86-167">PowerShell-7.0.3-win-x64.zip</span><span class="sxs-lookup"><span data-stu-id="26b86-167">PowerShell-7.0.3-win-x64.zip</span></span>
- <span data-ttu-id="26b86-168">PowerShell-7.0.3-win-x86.zip</span><span class="sxs-lookup"><span data-stu-id="26b86-168">PowerShell-7.0.3-win-x86.zip</span></span>
- <span data-ttu-id="26b86-169">PowerShell-7.0.3-win-arm64.zip</span><span class="sxs-lookup"><span data-stu-id="26b86-169">PowerShell-7.0.3-win-arm64.zip</span></span>
- <span data-ttu-id="26b86-170">PowerShell-7.0.3-win-arm32.zip</span><span class="sxs-lookup"><span data-stu-id="26b86-170">PowerShell-7.0.3-win-arm32.zip</span></span>

<span data-ttu-id="26b86-171">ファイルのダウンロード方法によっては、`Unblock-File` コマンドレットを使用して、ファイルのブロックを解除することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="26b86-171">Depending on how you download the file you may need to unblock the file using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="26b86-172">任意の場所にコンテンツを解凍し、そこから `pwsh.exe` を実行します。</span><span class="sxs-lookup"><span data-stu-id="26b86-172">Unzip the contents to the location of your choice and run `pwsh.exe` from there.</span></span> <span data-ttu-id="26b86-173">MSI パッケージをインストールする場合とは異なり、ZIP アーカイブをインストールしても、前提条件は確認されません。</span><span class="sxs-lookup"><span data-stu-id="26b86-173">Unlike installing the MSI packages, installing the ZIP archive doesn't check for prerequisites.</span></span> <span data-ttu-id="26b86-174">WSMan 経由でのリモート処理を正常に動作させるために、[前提条件](#prerequisites)を満たしていることを確かめてください。</span><span class="sxs-lookup"><span data-stu-id="26b86-174">For remoting over WSMan to work properly, ensure that you've met the [prerequisites](#prerequisites).</span></span>

<span data-ttu-id="26b86-175">この方法を使用して、Microsoft Surface Pro X のようなコンピューターに ARM ベース バージョンの PowerShell をインストールします。最適な結果を得るには、PowerShell を `$env:ProgramFiles\PowerShell\7` フォルダーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="26b86-175">Use this method to install the ARM-based version of PowerShell on computers like the Microsoft Surface Pro X. For best results, install PowerShell to the to `$env:ProgramFiles\PowerShell\7` folder.</span></span>

## <a name="deploying-on-windows-10-iot-enterprise"></a><span data-ttu-id="26b86-176">Windows 10 IoT Enterprise への展開</span><span class="sxs-lookup"><span data-stu-id="26b86-176">Deploying on Windows 10 IoT Enterprise</span></span>

<span data-ttu-id="26b86-177">Windows 10 IoT Enterprise には、PowerShell 7 の展開に使用できる Windows PowerShell が付属しています。</span><span class="sxs-lookup"><span data-stu-id="26b86-177">Windows 10 IoT Enterprise comes with Windows PowerShell, which we can use to deploy PowerShell 7.</span></span>

1. <span data-ttu-id="26b86-178">ターゲット デバイスに対して `PSSession` を作成します</span><span class="sxs-lookup"><span data-stu-id="26b86-178">Create `PSSession` to target device</span></span>

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

1. <span data-ttu-id="26b86-179">ZIP パッケージをデバイスにコピーします</span><span class="sxs-lookup"><span data-stu-id="26b86-179">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

1. <span data-ttu-id="26b86-180">デバイスに接続してアーカイブを展開します</span><span class="sxs-lookup"><span data-stu-id="26b86-180">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

1. <span data-ttu-id="26b86-181">PowerShell 7 へのリモート処理を設定します</span><span class="sxs-lookup"><span data-stu-id="26b86-181">Set up remoting to PowerShell 7</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because
   # it has to restart WinRM
   ```

1. <span data-ttu-id="26b86-182">デバイス上の PowerShell 7 エンドポイントに接続します</span><span class="sxs-lookup"><span data-stu-id="26b86-182">Connect to PowerShell 7 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter. If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-windows-10-iot-core"></a><span data-ttu-id="26b86-183">Windows 10 IoT Core への展開</span><span class="sxs-lookup"><span data-stu-id="26b86-183">Deploying on Windows 10 IoT Core</span></span>

<span data-ttu-id="26b86-184">PowerShell 7 の展開に使用できる _IOT_POWERSHELL_ 機能を取り込む場合、Windows 10 IoT Core によって Windows PowerShell が追加されます。</span><span class="sxs-lookup"><span data-stu-id="26b86-184">Windows 10 IoT Core adds Windows PowerShell when you include _IOT_POWERSHELL_ feature, which we can use to deploy PowerShell 7.</span></span> <span data-ttu-id="26b86-185">上記で Windows 10 IoT Enterprise に対して定義した手順は、IoT Core にも適用できます。</span><span class="sxs-lookup"><span data-stu-id="26b86-185">The steps defined above for Windows 10 IoT Enterprise can be followed for IoT Core as well.</span></span>

<span data-ttu-id="26b86-186">配布イメージに最新の PowerShell を追加する場合は、 [Import-PSCoreRelease][] コマンドを使用して、ワークスペースにパッケージを取り込み、さらに _OPENSRC_POWERSHELL_ 機能をご利用のイメージに追加します。</span><span class="sxs-lookup"><span data-stu-id="26b86-186">For adding the latest PowerShell in the shipping image, use [Import-PSCoreRelease][] command to include the package in the workarea and add _OPENSRC_POWERSHELL_ feature to your image.</span></span>

> [!NOTE]
> <span data-ttu-id="26b86-187">ARM64 アーキテクチャの場合、 _IOT_POWERSHELL_ を取り込むときに、Windows PowerShell は追加されません。</span><span class="sxs-lookup"><span data-stu-id="26b86-187">For ARM64 architecture, Windows PowerShell is not added when you include _IOT_POWERSHELL_.</span></span> <span data-ttu-id="26b86-188">そのため、zip ベースのインストールは機能しません。</span><span class="sxs-lookup"><span data-stu-id="26b86-188">So the zip based install will not work.</span></span> <span data-ttu-id="26b86-189">イメージに追加するには、`Import-PSCoreRelease` コマンドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26b86-189">You will need to use `Import-PSCoreRelease` command to add it in the image.</span></span>

## <a name="deploying-on-nano-server"></a><span data-ttu-id="26b86-190">Nano Server への展開</span><span class="sxs-lookup"><span data-stu-id="26b86-190">Deploying on Nano Server</span></span>

<span data-ttu-id="26b86-191">以下の手順では、Nano Server が "ヘッドレス" OS であり、あるバージョンの PowerShell が既に実行されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="26b86-191">These instructions assume that the Nano Server is a "headless" OS that has a version of PowerShell is already running on it.</span></span> <span data-ttu-id="26b86-192">詳細については、[Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="26b86-192">For more information, see the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) documentation.</span></span>

<span data-ttu-id="26b86-193">PowerShell バイナリを展開するには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="26b86-193">PowerShell binaries can be deployed using two different methods.</span></span>

1. <span data-ttu-id="26b86-194">オフライン: Nano Server VHD をマウントし、zip ファイルの中身をマウント イメージ内の選択した場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="26b86-194">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
1. <span data-ttu-id="26b86-195">オンライン: zip ファイルを PowerShell セッションを介して転送し、選択した場所にそれを展開します。</span><span class="sxs-lookup"><span data-stu-id="26b86-195">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="26b86-196">どちらの場合も、Windows 10 x64 の ZIP リリース パッケージが必要です。</span><span class="sxs-lookup"><span data-stu-id="26b86-196">In both cases, you need the Windows 10 x64 ZIP release package.</span></span> <span data-ttu-id="26b86-197">PowerShell の "管理者" インスタンス内でコマンドを実行してください。</span><span class="sxs-lookup"><span data-stu-id="26b86-197">Run the commands within an "Administrator" instance of PowerShell.</span></span>

### <a name="offline-deployment-of-powershell"></a><span data-ttu-id="26b86-198">PowerShell のオフラインでの展開</span><span class="sxs-lookup"><span data-stu-id="26b86-198">Offline Deployment of PowerShell</span></span>

1. <span data-ttu-id="26b86-199">お好みの zip ユーティリティを使用して、マウントされた Nano Server イメージ内のディレクトリにパッケージを解凍します。</span><span class="sxs-lookup"><span data-stu-id="26b86-199">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
1. <span data-ttu-id="26b86-200">イメージをマウント解除し、ブートします。</span><span class="sxs-lookup"><span data-stu-id="26b86-200">Unmount the image and boot it.</span></span>
1. <span data-ttu-id="26b86-201">Windows PowerShell の組み込みインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="26b86-201">Connect to the built-in instance of Windows PowerShell.</span></span>
1. <span data-ttu-id="26b86-202">「[別のインスタンスのテクニック][]」の、リモート エンドポイントを作成する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="26b86-202">Follow the instructions to create a remoting endpoint using the ["another instance technique"][].</span></span>

### <a name="online-deployment-of-powershell"></a><span data-ttu-id="26b86-203">PowerShell のオンラインでの展開</span><span class="sxs-lookup"><span data-stu-id="26b86-203">Online Deployment of PowerShell</span></span>

<span data-ttu-id="26b86-204">次の手順に従って、PowerShell を Nano Server に展開します。</span><span class="sxs-lookup"><span data-stu-id="26b86-204">Deploy PowerShell to Nano Server using the following steps.</span></span>

- <span data-ttu-id="26b86-205">Windows PowerShell の組み込みインスタンスに接続します</span><span class="sxs-lookup"><span data-stu-id="26b86-205">Connect to the built-in instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="26b86-206">Nano Server のインスタンスにファイルをコピーする</span><span class="sxs-lookup"><span data-stu-id="26b86-206">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="26b86-207">セッションに入る</span><span class="sxs-lookup"><span data-stu-id="26b86-207">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="26b86-208">ZIP ファイルを解凍します</span><span class="sxs-lookup"><span data-stu-id="26b86-208">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- <span data-ttu-id="26b86-209">WSMan を使用してリモート処理を行う場合、「[別のインスタンスのテクニック][]」の、リモート エンドポイントを作成する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="26b86-209">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"][].</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="26b86-210">.NET グローバル ツールとしてインストールする</span><span class="sxs-lookup"><span data-stu-id="26b86-210">Install as a .NET Global tool</span></span>

<span data-ttu-id="26b86-211">[.NET Core SDK](/dotnet/core/sdk) が既にインストールされている場合は、PowerShell を [.NET グローバル ツール](/dotnet/core/tools/global-tools)として簡単にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="26b86-211">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="26b86-212">dotnet tool install によって、`$env:PATH` 環境変数に `$env:USERPROFILE\dotnet\tools` が追加されます。</span><span class="sxs-lookup"><span data-stu-id="26b86-212">The dotnet tool installer adds `$env:USERPROFILE\dotnet\tools` to your `$env:PATH` environment variable.</span></span> <span data-ttu-id="26b86-213">ただし、現在実行中のシェルには更新された `$env:PATH` が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="26b86-213">However, the currently running shell doesn't have the updated `$env:PATH`.</span></span> <span data-ttu-id="26b86-214">新しいシェルからは、「`pwsh`」と入力すると PowerShell を起動できます。</span><span class="sxs-lookup"><span data-stu-id="26b86-214">You can start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="install-powershell-via-winget"></a><span data-ttu-id="26b86-215">Winget を使用して PowerShell をインストールする</span><span class="sxs-lookup"><span data-stu-id="26b86-215">Install PowerShell via Winget</span></span>

<span data-ttu-id="26b86-216">開発者は、`winget` コマンドライン ツールを使用して、Windows 10 コンピューター上のアプリケーションの検出、インストール、アップグレード、削除、および構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="26b86-216">The `winget` command-line tool enables developers to discover, install, upgrade, remove, and configure applications on Windows 10 computers.</span></span> <span data-ttu-id="26b86-217">このツールは、Windows パッケージ マネージャー サービスに対するクライアント インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="26b86-217">This tool is the client interface to the Windows Package Manager service.</span></span>

> [!NOTE]
> <span data-ttu-id="26b86-218">`winget` ツールは現在プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="26b86-218">The `winget` tool is currently a preview.</span></span> <span data-ttu-id="26b86-219">現時点では、計画されたすべての機能を使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="26b86-219">Not all planned functionality is available at this time.</span></span>
> <span data-ttu-id="26b86-220">運用環境の展開シナリオでは、この方法を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="26b86-220">You should not use this method in a production deployment scenario.</span></span> <span data-ttu-id="26b86-221">システム要件とインストール手順の一覧については、[winget] に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="26b86-221">See the [winget] documentation for a list of system requirements and install instructions.</span></span>

<span data-ttu-id="26b86-222">次のコマンドを使用すると、公開済みの `winget` パッケージを使用して PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="26b86-222">The following commands can be used to install PowerShell using the published `winget` packages:</span></span>

1. <span data-ttu-id="26b86-223">最新バージョンの PowerShell を検索します</span><span class="sxs-lookup"><span data-stu-id="26b86-223">Search for the latest version of PowerShell</span></span>

   ```powershell
   winget search Microsoft.PowerShell
   ```

   ```Output
   Name               Id                           Version
   ---------------------------------------------------------------
   PowerShell         Microsoft.PowerShell         7.0.3
   PowerShell-Preview Microsoft.PowerShell-Preview 7.1.0-preview.5
   ```

1. <span data-ttu-id="26b86-224">`--exact` パラメーターを使用して、いずれかのバージョンの PowerShell をインストールします</span><span class="sxs-lookup"><span data-stu-id="26b86-224">Install a version of PowerShell using the `--exact` parameter</span></span>

   ```powershell
   winget install --name PowerShell --exact
   winget install --name PowerShell-Preview --exact
   ```

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="26b86-225">リモート エンドポイントの作成方法</span><span class="sxs-lookup"><span data-stu-id="26b86-225">How to create a remoting endpoint</span></span>

<span data-ttu-id="26b86-226">PowerShell では、WSMan と SSH の両方について PowerShell Remoting Protocol (PSRP) がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="26b86-226">PowerShell supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="26b86-227">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26b86-227">For more information, see:</span></span>

- <span data-ttu-id="26b86-228">[PowerShell Core での SSH リモート処理][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="26b86-228">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="26b86-229">[PowerShell Core での WSMan リモート処理][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="26b86-229">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="upgrading-an-existing-installation"></a><span data-ttu-id="26b86-230">既存のインストールのアップグレード</span><span class="sxs-lookup"><span data-stu-id="26b86-230">Upgrading an existing installation</span></span>

<span data-ttu-id="26b86-231">アップグレード時に最適な結果を得るには、最初に PowerShell をインストールしたときと同じインストール方法を使用してください。</span><span class="sxs-lookup"><span data-stu-id="26b86-231">For best results when upgrading, you should use the same install method you used when you first installed PowerShell.</span></span> <span data-ttu-id="26b86-232">各インストール方法では、PowerShell をそれぞれ異なる場所にインストールします。</span><span class="sxs-lookup"><span data-stu-id="26b86-232">Each installation method installs PowerShell in a different location.</span></span> <span data-ttu-id="26b86-233">PowerShell がインストールされた方法がわからない場合は、この記事のパッケージ情報とインストールされている場所を比較できます。</span><span class="sxs-lookup"><span data-stu-id="26b86-233">If you are not sure how PowerShell was installed, you can compare the installed location with the package information in this article.</span></span> <span data-ttu-id="26b86-234">MSI パッケージを使用してインストールした場合、その情報は **[プログラムと機能]** コントロール パネルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="26b86-234">If you installed via the MSI package, that information appears in the **Programs and Features** Control Panel.</span></span>

## <a name="installation-support"></a><span data-ttu-id="26b86-235">インストールのサポート</span><span class="sxs-lookup"><span data-stu-id="26b86-235">Installation support</span></span>

<span data-ttu-id="26b86-236">Microsoft は、このドキュメントでインストール方法をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="26b86-236">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="26b86-237">他のソースには、利用可能な別のインストール方法が存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="26b86-237">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="26b86-238">そのようなツールと方法は機能しても、Microsoft ではそれらの方法をサポートできません。</span><span class="sxs-lookup"><span data-stu-id="26b86-238">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

<!-- link references -->

[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
[winget]: /windows/package-manager/winget
<span data-ttu-id="26b86-240">「[別のインスタンスのテクニック]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register」</span><span class="sxs-lookup"><span data-stu-id="26b86-240">["another instance technique"]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register</span></span>
[Import-PSCoreRelease]: https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease
