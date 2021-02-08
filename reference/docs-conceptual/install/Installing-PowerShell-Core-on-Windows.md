---
title: Windows への PowerShell のインストール
description: Windows への PowerShell のインストールに関する情報
ms.date: 02/02/2021
ms.openlocfilehash: befc5ff156cb7c3843d89e394e903778682ba28e
ms.sourcegitcommit: 40b6d8e9b6d791ac69e2ff85224e900b21552bc1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "99536492"
---
# <a name="installing-powershell-on-windows"></a><span data-ttu-id="cb274-103">Windows への PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="cb274-103">Installing PowerShell on Windows</span></span>

<span data-ttu-id="cb274-104">Windows に PowerShell をインストールする方法は複数あります。</span><span class="sxs-lookup"><span data-stu-id="cb274-104">There are multiple ways to install PowerShell in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cb274-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="cb274-105">Prerequisites</span></span>

<span data-ttu-id="cb274-106">PowerShell の最新リリースは、Windows 7 SP1、Server 2008 R2、およびそれ以降のバージョンでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cb274-106">The latest release of PowerShell is supported on Windows 7 SP1, Server 2008 R2, and later versions.</span></span>

<span data-ttu-id="cb274-107">WSMan を介して PowerShell のリモート処理を有効にするには、次の前提条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb274-107">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="cb274-108">Windows 10 より前のバージョンの Windows に[ユニバーサル C ランタイム](https://www.microsoft.com/download/details.aspx?id=50410)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="cb274-108">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions predating Windows 10.</span></span> <span data-ttu-id="cb274-109">これは、直接ダウンロードすることも、Windows Update 経由で入手することもできます。</span><span class="sxs-lookup"><span data-stu-id="cb274-109">It's available via direct download or Windows Update.</span></span> <span data-ttu-id="cb274-110">完全にパッチが適用されたシステムには、既にこのパッケージがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="cb274-110">Fully patched systems already have this package installed.</span></span>
- <span data-ttu-id="cb274-111">Windows Management Framework (WMF) 4.0 以降を Windows 7 と Windows Server 2008 R2 にインストールします。</span><span class="sxs-lookup"><span data-stu-id="cb274-111">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="cb274-112">WMF の詳細については、[WMF の概要](/powershell/scripting/wmf/overview)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb274-112">For more information about WMF, see [WMF Overview](/powershell/scripting/wmf/overview).</span></span>

## <a name="download-the-installer-package"></a><span data-ttu-id="cb274-113">インストーラー パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="cb274-113">Download the installer package</span></span>

<span data-ttu-id="cb274-114">Windows に PowerShell をインストールするには、[最新][]のインストール パッケージを GitHub からダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="cb274-114">To install PowerShell on Windows, download the [latest][] install package from GitHub.</span></span> <span data-ttu-id="cb274-115">最新の[プレビュー][] バージョンも確認できます。</span><span class="sxs-lookup"><span data-stu-id="cb274-115">You can also find the latest [preview][] version.</span></span> <span data-ttu-id="cb274-116">リリース ページの **[Assets]** セクションまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="cb274-116">Scroll down to the **Assets** section of the Release page.</span></span> <span data-ttu-id="cb274-117">**[Assets]** セクションは折りたたまれている場合があります。その場合は、クリックして展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb274-117">The **Assets** section may be collapsed, so you may need to click to expand it.</span></span>

## <a name="installing-the-msi-package"></a><span data-ttu-id="cb274-118"><a id="msi" />MSI パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="cb274-118"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="cb274-119">MSI ファイルは、`PowerShell-<version>-win-<os-arch>.msi` のようになります。</span><span class="sxs-lookup"><span data-stu-id="cb274-119">The MSI file looks like `PowerShell-<version>-win-<os-arch>.msi`.</span></span> <span data-ttu-id="cb274-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cb274-120">For example:</span></span>

- `PowerShell-7.1.1-win-x64.msi`
- `PowerShell-7.1.1-win-x86.msi`

<span data-ttu-id="cb274-121">ダウンロードしたら、インストーラーをダブルクリックし、プロンプトの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="cb274-121">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="cb274-122">インストーラーにより、Windows の [スタート] メニューにショートカットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cb274-122">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="cb274-123">パッケージは、既定で `$env:ProgramFiles\PowerShell\<version>` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cb274-123">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="cb274-124">PowerShell は、スタート メニューまたは  `$env:ProgramFiles\PowerShell\<version>\pwsh.exe` から起動できます。</span><span class="sxs-lookup"><span data-stu-id="cb274-124">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="cb274-125">PowerShell 7.1 は新しいディレクトリにインストールされ、Windows PowerShell 5.1 と side-by-side 実行されます。</span><span class="sxs-lookup"><span data-stu-id="cb274-125">PowerShell 7.1 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span>
> <span data-ttu-id="cb274-126">PowerShell 7.1 はインプレース アップグレードであり、PowerShell Core 6.x</span><span class="sxs-lookup"><span data-stu-id="cb274-126">PowerShell 7.1 is an in-place upgrade that replaces PowerShell 6.x.</span></span> <span data-ttu-id="cb274-127">または PowerShell 7.0 が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="cb274-127">or PowerShell 7.0.</span></span>
>
> - <span data-ttu-id="cb274-128">PowerShell 7.1 は `$env:ProgramFiles\PowerShell\7` にインストールされます</span><span class="sxs-lookup"><span data-stu-id="cb274-128">PowerShell 7.1 is installed to `$env:ProgramFiles\PowerShell\7`</span></span>
> - <span data-ttu-id="cb274-129">`$env:ProgramFiles\PowerShell\7` フォルダーは `$env:PATH` に追加されます</span><span class="sxs-lookup"><span data-stu-id="cb274-129">The `$env:ProgramFiles\PowerShell\7` folder is added to `$env:PATH`</span></span>
> - <span data-ttu-id="cb274-130">`$env:ProgramFiles\PowerShell\6` フォルダーは削除されます</span><span class="sxs-lookup"><span data-stu-id="cb274-130">The `$env:ProgramFiles\PowerShell\6` folder is deleted</span></span>
>
> <span data-ttu-id="cb274-131">PowerShell 7.1 を他のバージョンと side-by-side 実行する場合、[ZIP インストール](#zip)手法を利用し、他のバージョンを別のフォルダーにインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="cb274-131">If you need to run PowerShell 7.1 side-by-side with other versions, use the [ZIP install](#zip) method to install the other version to a different folder.</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="cb274-132">コマンド ラインからの管理者インストール</span><span class="sxs-lookup"><span data-stu-id="cb274-132">Administrative install from the command line</span></span>

<span data-ttu-id="cb274-133">MSI パッケージはコマンド ラインからインストールできるため、管理者はユーザーの介入なしにパッケージを展開できます。</span><span class="sxs-lookup"><span data-stu-id="cb274-133">MSI packages can be installed from the command line allowing administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="cb274-134">MSI パッケージには、インストールのオプションを制御するための次のプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cb274-134">The MSI package includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="cb274-135">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - このプロパティでは、エクスプローラーのコンテキスト メニューに **[Open PowerShell]\(PowerShell を開く\)** 項目を追加するためのオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="cb274-135">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="cb274-136">**ADD_FILE_CONTEXT_MENU_RUNPOWERSHELL** - このプロパティでは、エクスプローラーのコンテキスト メニューに **[PowerShell を使用しての実行]** 項目を追加するためのオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="cb274-136">**ADD_FILE_CONTEXT_MENU_RUNPOWERSHELL** - This property controls the option for adding the **Run with PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="cb274-137">**ENABLE_PSREMOTING** - このプロパティでは、インストール中に PowerShell リモート処理を有効にするためのオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="cb274-137">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="cb274-138">**REGISTER_MANIFEST** - このプロパティでは、Windows イベント ログのマニフェストを登録するためのオプションを制御します。</span><span class="sxs-lookup"><span data-stu-id="cb274-138">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="cb274-139">すべてのインストール オプションを有効にして PowerShell をサイレント インストールする方法を、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="cb274-139">The following example shows how to silently install PowerShell with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-7.1.1-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="cb274-140">`Msiexec.exe` 用のコマンド ライン オプションの完全な一覧については、[コマンド ライン オプション](/windows/desktop/Msi/command-line-options)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cb274-140">For a full list of command-line options for `Msiexec.exe`, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

### <a name="registry-keys-created-during-installation"></a><span data-ttu-id="cb274-141">インストール時に作成されるレジストリ キー</span><span class="sxs-lookup"><span data-stu-id="cb274-141">Registry keys created during installation</span></span>

<span data-ttu-id="cb274-142">PowerShell 7.1 以降では、MSI パッケージによって、インストール場所と PowerShell のバージョンを格納するレジストリ キーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cb274-142">Beginning in PowerShell 7.1, the MSI package creates registry keys that store the installation location and version of PowerShell.</span></span> <span data-ttu-id="cb274-143">これらの値は `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>` にあります。</span><span class="sxs-lookup"><span data-stu-id="cb274-143">These values are located in `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`.</span></span> <span data-ttu-id="cb274-144">`<GUID>` の値は、ビルドの種類 (リリースまたはプレビュー)、メジャー バージョン、およびアーキテクチャごとに一意です。</span><span class="sxs-lookup"><span data-stu-id="cb274-144">The value of `<GUID>` is unique for each build type (release or preview), major version, and architecture.</span></span>

|    <span data-ttu-id="cb274-145">Release</span><span class="sxs-lookup"><span data-stu-id="cb274-145">Release</span></span>    | <span data-ttu-id="cb274-146">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="cb274-146">Architecture</span></span> |                                          <span data-ttu-id="cb274-147">レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="cb274-147">Registry Key</span></span>                                           |
| ------------- | :----------: | ----------------------------------------------------------------------------------------------- |
| <span data-ttu-id="cb274-148">7.1.x リリース</span><span class="sxs-lookup"><span data-stu-id="cb274-148">7.1.x Release</span></span> |     <span data-ttu-id="cb274-149">x86</span><span class="sxs-lookup"><span data-stu-id="cb274-149">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\1d00683b-0f84-4db8-a64f-2f98ad42fe06` |
| <span data-ttu-id="cb274-150">7.1.x リリース</span><span class="sxs-lookup"><span data-stu-id="cb274-150">7.1.x Release</span></span> |     <span data-ttu-id="cb274-151">X64</span><span class="sxs-lookup"><span data-stu-id="cb274-151">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\31ab5147-9a97-4452-8443-d9709f0516e1` |
| <span data-ttu-id="cb274-152">7.1.x プレビュー</span><span class="sxs-lookup"><span data-stu-id="cb274-152">7.1.x Preview</span></span> |     <span data-ttu-id="cb274-153">x86</span><span class="sxs-lookup"><span data-stu-id="cb274-153">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\86abcfbd-1ccc-4a88-b8b2-0facfde29094` |
| <span data-ttu-id="cb274-154">7.1.x プレビュー</span><span class="sxs-lookup"><span data-stu-id="cb274-154">7.1.x Preview</span></span> |     <span data-ttu-id="cb274-155">X64</span><span class="sxs-lookup"><span data-stu-id="cb274-155">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\39243d76-adaf-42b1-94fb-16ecf83237c8` |

<span data-ttu-id="cb274-156">これは、管理者と開発者が PowerShell へのパスを見つけるために使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb274-156">This can be used by administrators and developers to find the path to PowerShell.</span></span> <span data-ttu-id="cb274-157">`<GUID>` の値は、すべてのプレビューおよびマイナー バージョンのリリースで同じになります。</span><span class="sxs-lookup"><span data-stu-id="cb274-157">The `<GUID>` values will be the same for all preview and minor version releases.</span></span> <span data-ttu-id="cb274-158">`<GUID>` の値はメジャー リリースごとに変更されます。</span><span class="sxs-lookup"><span data-stu-id="cb274-158">The `<GUID>` values are changed for each major release.</span></span>

## <a name="installing-the-zip-package"></a><span data-ttu-id="cb274-159"><a id="zip" />ZIP パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="cb274-159"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="cb274-160">PowerShell バイナリ ZIP アーカイブは、高度な展開シナリオ用に用意されています。</span><span class="sxs-lookup"><span data-stu-id="cb274-160">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="cb274-161">[リリース][リリース] ページから、次のいずれかの ZIP アーカイブをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="cb274-161">Download one of the following ZIP archives from the [releases][releases] page.</span></span>

- <span data-ttu-id="cb274-162">PowerShell-7.1.1-win-x64.zip</span><span class="sxs-lookup"><span data-stu-id="cb274-162">PowerShell-7.1.1-win-x64.zip</span></span>
- <span data-ttu-id="cb274-163">PowerShell-7.1.1-win-x86.zip</span><span class="sxs-lookup"><span data-stu-id="cb274-163">PowerShell-7.1.1-win-x86.zip</span></span>
- <span data-ttu-id="cb274-164">PowerShell-7.1.1-win-arm64.zip</span><span class="sxs-lookup"><span data-stu-id="cb274-164">PowerShell-7.1.1-win-arm64.zip</span></span>
- <span data-ttu-id="cb274-165">PowerShell-7.1.1-win-arm32.zip</span><span class="sxs-lookup"><span data-stu-id="cb274-165">PowerShell-7.1.1-win-arm32.zip</span></span>

<span data-ttu-id="cb274-166">ファイルのダウンロード方法によっては、`Unblock-File` コマンドレットを使用して、ファイルのブロックを解除することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cb274-166">Depending on how you download the file you may need to unblock the file using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="cb274-167">任意の場所にコンテンツを解凍し、そこから `pwsh.exe` を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb274-167">Unzip the contents to the location of your choice and run `pwsh.exe` from there.</span></span> <span data-ttu-id="cb274-168">MSI パッケージをインストールする場合とは異なり、ZIP アーカイブをインストールしても、前提条件は確認されません。</span><span class="sxs-lookup"><span data-stu-id="cb274-168">Unlike installing the MSI packages, installing the ZIP archive doesn't check for prerequisites.</span></span> <span data-ttu-id="cb274-169">WSMan 経由でのリモート処理を正常に動作させるために、[前提条件](#prerequisites)を満たしていることを確かめてください。</span><span class="sxs-lookup"><span data-stu-id="cb274-169">For remoting over WSMan to work properly, ensure that you've met the [prerequisites](#prerequisites).</span></span>

<span data-ttu-id="cb274-170">この方法を使用して、Microsoft Surface Pro X のようなコンピューターに ARM ベース バージョンの PowerShell をインストールします。最適な結果を得るには、PowerShell を `$env:ProgramFiles\PowerShell\7` フォルダーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="cb274-170">Use this method to install the ARM-based version of PowerShell on computers like the Microsoft Surface Pro X. For best results, install PowerShell to the to `$env:ProgramFiles\PowerShell\7` folder.</span></span>

## <a name="deploying-on-windows-10-iot-enterprise"></a><span data-ttu-id="cb274-171">Windows 10 IoT Enterprise への展開</span><span class="sxs-lookup"><span data-stu-id="cb274-171">Deploying on Windows 10 IoT Enterprise</span></span>

<span data-ttu-id="cb274-172">Windows 10 IoT Enterprise には、PowerShell 7 の展開に使用できる Windows PowerShell が付属しています。</span><span class="sxs-lookup"><span data-stu-id="cb274-172">Windows 10 IoT Enterprise comes with Windows PowerShell, which we can use to deploy PowerShell 7.</span></span>

1. <span data-ttu-id="cb274-173">ターゲット デバイスに対して `PSSession` を作成します</span><span class="sxs-lookup"><span data-stu-id="cb274-173">Create `PSSession` to target device</span></span>

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

1. <span data-ttu-id="cb274-174">ZIP パッケージをデバイスにコピーします</span><span class="sxs-lookup"><span data-stu-id="cb274-174">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

1. <span data-ttu-id="cb274-175">デバイスに接続してアーカイブを展開します</span><span class="sxs-lookup"><span data-stu-id="cb274-175">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

1. <span data-ttu-id="cb274-176">PowerShell 7 へのリモート処理を設定します</span><span class="sxs-lookup"><span data-stu-id="cb274-176">Set up remoting to PowerShell 7</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because
   # it has to restart WinRM
   ```

1. <span data-ttu-id="cb274-177">デバイス上の PowerShell 7 エンドポイントに接続します</span><span class="sxs-lookup"><span data-stu-id="cb274-177">Connect to PowerShell 7 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter. If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-windows-10-iot-core"></a><span data-ttu-id="cb274-178">Windows 10 IoT Core への展開</span><span class="sxs-lookup"><span data-stu-id="cb274-178">Deploying on Windows 10 IoT Core</span></span>

<span data-ttu-id="cb274-179">PowerShell 7 の展開に使用できる _IOT_POWERSHELL_ 機能を取り込む場合、Windows 10 IoT Core によって Windows PowerShell が追加されます。</span><span class="sxs-lookup"><span data-stu-id="cb274-179">Windows 10 IoT Core adds Windows PowerShell when you include _IOT_POWERSHELL_ feature, which we can use to deploy PowerShell 7.</span></span> <span data-ttu-id="cb274-180">上記で Windows 10 IoT Enterprise に対して定義した手順は、IoT Core にも適用できます。</span><span class="sxs-lookup"><span data-stu-id="cb274-180">The steps defined above for Windows 10 IoT Enterprise can be followed for IoT Core as well.</span></span>

<span data-ttu-id="cb274-181">配布イメージに最新の PowerShell を追加する場合は、[Import-PSCoreRelease][] コマンドを使用して、ワークスペースにパッケージを取り込み、さらに _OPENSRC_POWERSHELL_ 機能をご利用のイメージに追加します。</span><span class="sxs-lookup"><span data-stu-id="cb274-181">For adding the latest PowerShell in the shipping image, use [Import-PSCoreRelease][] command to include the package in the workarea and add _OPENSRC_POWERSHELL_ feature to your image.</span></span>

> [!NOTE]
> <span data-ttu-id="cb274-182">ARM64 アーキテクチャの場合、_IOT_POWERSHELL_ を取り込むときに、Windows PowerShell は追加されません。</span><span class="sxs-lookup"><span data-stu-id="cb274-182">For ARM64 architecture, Windows PowerShell is not added when you include _IOT_POWERSHELL_.</span></span> <span data-ttu-id="cb274-183">そのため、zip ベースのインストールは機能しません。</span><span class="sxs-lookup"><span data-stu-id="cb274-183">So the zip based install will not work.</span></span> <span data-ttu-id="cb274-184">イメージに追加するには、`Import-PSCoreRelease` コマンドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb274-184">You will need to use `Import-PSCoreRelease` command to add it in the image.</span></span>

## <a name="deploying-on-nano-server"></a><span data-ttu-id="cb274-185">Nano Server への展開</span><span class="sxs-lookup"><span data-stu-id="cb274-185">Deploying on Nano Server</span></span>

<span data-ttu-id="cb274-186">以下の手順では、Nano Server が "ヘッドレス" OS であり、あるバージョンの PowerShell が既に実行されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="cb274-186">These instructions assume that the Nano Server is a "headless" OS that has a version of PowerShell is already running on it.</span></span> <span data-ttu-id="cb274-187">詳細については、[Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cb274-187">For more information, see the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) documentation.</span></span>

<span data-ttu-id="cb274-188">PowerShell バイナリを展開するには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="cb274-188">PowerShell binaries can be deployed using two different methods.</span></span>

1. <span data-ttu-id="cb274-189">オフライン: Nano Server VHD をマウントし、zip ファイルの中身をマウント イメージ内の選択した場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="cb274-189">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
1. <span data-ttu-id="cb274-190">オンライン: zip ファイルを PowerShell セッションを介して転送し、選択した場所にそれを展開します。</span><span class="sxs-lookup"><span data-stu-id="cb274-190">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="cb274-191">どちらの場合も、Windows 10 x64 の ZIP リリース パッケージが必要です。</span><span class="sxs-lookup"><span data-stu-id="cb274-191">In both cases, you need the Windows 10 x64 ZIP release package.</span></span> <span data-ttu-id="cb274-192">PowerShell の "管理者" インスタンス内でコマンドを実行してください。</span><span class="sxs-lookup"><span data-stu-id="cb274-192">Run the commands within an "Administrator" instance of PowerShell.</span></span>

### <a name="offline-deployment-of-powershell"></a><span data-ttu-id="cb274-193">PowerShell のオフラインでの展開</span><span class="sxs-lookup"><span data-stu-id="cb274-193">Offline Deployment of PowerShell</span></span>

1. <span data-ttu-id="cb274-194">お好みの zip ユーティリティを使用して、マウントされた Nano Server イメージ内のディレクトリにパッケージを解凍します。</span><span class="sxs-lookup"><span data-stu-id="cb274-194">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
1. <span data-ttu-id="cb274-195">イメージをマウント解除し、ブートします。</span><span class="sxs-lookup"><span data-stu-id="cb274-195">Unmount the image and boot it.</span></span>
1. <span data-ttu-id="cb274-196">Windows PowerShell の組み込みインスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="cb274-196">Connect to the built-in instance of Windows PowerShell.</span></span>
1. <span data-ttu-id="cb274-197">「[別のインスタンスのテクニック][]」の、リモート エンドポイントを作成する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cb274-197">Follow the instructions to create a remoting endpoint using the ["another instance technique"][].</span></span>

### <a name="online-deployment-of-powershell"></a><span data-ttu-id="cb274-198">PowerShell のオンラインでの展開</span><span class="sxs-lookup"><span data-stu-id="cb274-198">Online Deployment of PowerShell</span></span>

<span data-ttu-id="cb274-199">次の手順に従って、PowerShell を Nano Server に展開します。</span><span class="sxs-lookup"><span data-stu-id="cb274-199">Deploy PowerShell to Nano Server using the following steps.</span></span>

- <span data-ttu-id="cb274-200">Windows PowerShell の組み込みインスタンスに接続します</span><span class="sxs-lookup"><span data-stu-id="cb274-200">Connect to the built-in instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="cb274-201">Nano Server のインスタンスにファイルをコピーする</span><span class="sxs-lookup"><span data-stu-id="cb274-201">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="cb274-202">セッションに入る</span><span class="sxs-lookup"><span data-stu-id="cb274-202">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="cb274-203">ZIP ファイルを解凍します</span><span class="sxs-lookup"><span data-stu-id="cb274-203">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- <span data-ttu-id="cb274-204">WSMan を使用してリモート処理を行う場合、「[別のインスタンスのテクニック][]」の、リモート エンドポイントを作成する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cb274-204">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"][].</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="cb274-205">.NET グローバル ツールとしてインストールする</span><span class="sxs-lookup"><span data-stu-id="cb274-205">Install as a .NET Global tool</span></span>

<span data-ttu-id="cb274-206">[.NET Core SDK](/dotnet/core/sdk) が既にインストールされている場合は、PowerShell を [.NET グローバル ツール](/dotnet/core/tools/global-tools)として簡単にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="cb274-206">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="cb274-207">dotnet tool install によって、`$env:PATH` 環境変数に `$env:USERPROFILE\dotnet\tools` が追加されます。</span><span class="sxs-lookup"><span data-stu-id="cb274-207">The dotnet tool installer adds `$env:USERPROFILE\dotnet\tools` to your `$env:PATH` environment variable.</span></span> <span data-ttu-id="cb274-208">ただし、現在実行中のシェルには更新された `$env:PATH` が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="cb274-208">However, the currently running shell doesn't have the updated `$env:PATH`.</span></span> <span data-ttu-id="cb274-209">新しいシェルからは、「`pwsh`」と入力すると PowerShell を起動できます。</span><span class="sxs-lookup"><span data-stu-id="cb274-209">You can start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="install-powershell-via-winget"></a><span data-ttu-id="cb274-210">Winget を使用して PowerShell をインストールする</span><span class="sxs-lookup"><span data-stu-id="cb274-210">Install PowerShell via Winget</span></span>

<span data-ttu-id="cb274-211">開発者は、`winget` コマンドライン ツールを使用して、Windows 10 コンピューター上のアプリケーションの検出、インストール、アップグレード、削除、および構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cb274-211">The `winget` command-line tool enables developers to discover, install, upgrade, remove, and configure applications on Windows 10 computers.</span></span> <span data-ttu-id="cb274-212">このツールは、Windows パッケージ マネージャー サービスに対するクライアント インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="cb274-212">This tool is the client interface to the Windows Package Manager service.</span></span>

> [!NOTE]
> <span data-ttu-id="cb274-213">`winget` ツールは現在プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="cb274-213">The `winget` tool is currently a preview.</span></span> <span data-ttu-id="cb274-214">現時点では、計画されたすべての機能を使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="cb274-214">Not all planned functionality is available at this time.</span></span>
> <span data-ttu-id="cb274-215">運用環境の展開シナリオでは、この方法を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="cb274-215">You should not use this method in a production deployment scenario.</span></span> <span data-ttu-id="cb274-216">システム要件とインストール手順の一覧については、[winget] に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb274-216">See the [winget] documentation for a list of system requirements and install instructions.</span></span>

<span data-ttu-id="cb274-217">次のコマンドを使用すると、公開済みの `winget` パッケージを使用して PowerShell をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="cb274-217">The following commands can be used to install PowerShell using the published `winget` packages:</span></span>

1. <span data-ttu-id="cb274-218">最新バージョンの PowerShell を検索します</span><span class="sxs-lookup"><span data-stu-id="cb274-218">Search for the latest version of PowerShell</span></span>

   ```powershell
   winget search Microsoft.PowerShell
   ```

   ```Output
   Name               Id                           Version
   ---------------------------------------------------------------
   PowerShell         Microsoft.PowerShell         7.1.1
   PowerShell-Preview Microsoft.PowerShell-Preview 7.1.1-preview.5
   ```

1. <span data-ttu-id="cb274-219">`--exact` パラメーターを使用して、いずれかのバージョンの PowerShell をインストールします</span><span class="sxs-lookup"><span data-stu-id="cb274-219">Install a version of PowerShell using the `--exact` parameter</span></span>

   ```powershell
   winget install --name PowerShell --exact
   winget install --name PowerShell-Preview --exact
   ```

## <a name="installing-from-the-microsoft-store"></a><span data-ttu-id="cb274-220"><a id="msix" />Microsoft Store からインストールする</span><span class="sxs-lookup"><span data-stu-id="cb274-220"><a id="msix" />Installing from the Microsoft Store</span></span>

<span data-ttu-id="cb274-221">PowerShell 7.1 が Microsoft Store に公開されています。</span><span class="sxs-lookup"><span data-stu-id="cb274-221">PowerShell 7.1 has been published to the Microsoft Store.</span></span> <span data-ttu-id="cb274-222">PowerShell リリースは [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) Web サイトまたは Windows の Store アプリケーションで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="cb274-222">You can find the PowerShell release on the [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) website or in the Store application in Windows.</span></span>

<span data-ttu-id="cb274-223">Microsoft Store パッケージの利点:</span><span class="sxs-lookup"><span data-stu-id="cb274-223">Benefits of the Microsoft Store package:</span></span>

- <span data-ttu-id="cb274-224">Windows 10 に直接組み込まれた自動更新</span><span class="sxs-lookup"><span data-stu-id="cb274-224">Automatic updates built right into Windows 10</span></span>
- <span data-ttu-id="cb274-225">Intune や SCCM など、他のソフトウェア配布メカニズムとの統合</span><span class="sxs-lookup"><span data-stu-id="cb274-225">Integrates with other software distribution mechanisms like Intune and SCCM</span></span>

<span data-ttu-id="cb274-226">制限事項:</span><span class="sxs-lookup"><span data-stu-id="cb274-226">Limitations:</span></span>

<span data-ttu-id="cb274-227">MSIX パッケージは、一部のファイルシステムとレジストリの場所へのアクセスを仮想化するアプリケーション サンドボックスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="cb274-227">MSIX packages run in an application sandbox that virtualizes access to some filesystem and registry locations.</span></span>

- <span data-ttu-id="cb274-228">HKEY_CURRENT_USER の下でのレジストリ変更はすべて、書き込み時、ユーザーごとにアプリ別のプライベートの場所にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="cb274-228">All registry changes under HKEY_CURRENT_USER are copied on write to a private, per-user, per-app location.</span></span> <span data-ttu-id="cb274-229">そのため、これらの値は他のアプリケーションでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="cb274-229">Therefore, those values are not available to other applications.</span></span>
- <span data-ttu-id="cb274-230">`$PSHOME` に格納されているシステムレベルの構成設定は変更できません。</span><span class="sxs-lookup"><span data-stu-id="cb274-230">Any system-level configuration settings stored in `$PSHOME` cannot be modified.</span></span> <span data-ttu-id="cb274-231">これには WSMAN 構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cb274-231">This includes the WSMAN configuration.</span></span> <span data-ttu-id="cb274-232">これにより、リモート セッションが PowerShell のストアベース インストールに接続できなくなります。</span><span class="sxs-lookup"><span data-stu-id="cb274-232">This prevents remote sessions from connecting to Store-based installs of PowerShell.</span></span> <span data-ttu-id="cb274-233">ユーザーレベル構成と SSH リモート処理がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="cb274-233">User-level configurations and SSH remoting are supported.</span></span>

<span data-ttu-id="cb274-234">詳細については、「[Windows でパッケージ化されたデスクトップ アプリが動作するしくみについて](/windows/msix/desktop/desktop-to-uwp-behind-the-scenes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb274-234">For more information, see [Understanding how packaged desktop apps run on Windows](/windows/msix/desktop/desktop-to-uwp-behind-the-scenes).</span></span>

### <a name="using-the-msix-package"></a><span data-ttu-id="cb274-235">MSIX パッケージの使用</span><span class="sxs-lookup"><span data-stu-id="cb274-235">Using the MSIX package</span></span>

> [!NOTE]
> <span data-ttu-id="cb274-236">PowerShell のプレビュー ビルドには MSIX パッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cb274-236">The preview builds of PowerShell include an MSIX package.</span></span> <span data-ttu-id="cb274-237">MSIX パッケージは公式にサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="cb274-237">The MSIX package is not officially supported.</span></span> <span data-ttu-id="cb274-238">このパッケージは、プレビュー期間中のテスト目的で作られています。</span><span class="sxs-lookup"><span data-stu-id="cb274-238">The package is built for testing purposes during the preview period.</span></span>

<span data-ttu-id="cb274-239">Windows 10 クライアントに MSIX パッケージを手動でインストールするには、Microsoft の GitHub [リリース][リリース] ページから MSIX パッケージをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="cb274-239">To manually install the MSIX package on a Windows 10 client, download the MSIX package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="cb274-240">インストールしたいリリースの **[Assets]** セクションまでスクロールダウンします。</span><span class="sxs-lookup"><span data-stu-id="cb274-240">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="cb274-241">[Assets] セクションは折りたたまれている場合があります。その場合は、クリックして展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb274-241">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="cb274-242">MSIX ファイルは、`PowerShell-<version>-win-<os-arch>.msix` のようになります。</span><span class="sxs-lookup"><span data-stu-id="cb274-242">The MSIX file looks like this - `PowerShell-<version>-win-<os-arch>.msix`</span></span>

<span data-ttu-id="cb274-243">パッケージをインストールするには、`Add-AppxPackage` コマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb274-243">To install the package, you must use the `Add-AppxPackage` cmdlet.</span></span>

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="cb274-244">リモート エンドポイントの作成方法</span><span class="sxs-lookup"><span data-stu-id="cb274-244">How to create a remoting endpoint</span></span>

<span data-ttu-id="cb274-245">PowerShell では、WSMan と SSH の両方について PowerShell Remoting Protocol (PSRP) がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cb274-245">PowerShell supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="cb274-246">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb274-246">For more information, see:</span></span>

- <span data-ttu-id="cb274-247">[PowerShell Core での SSH リモート処理][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="cb274-247">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="cb274-248">[PowerShell Core での WSMan リモート処理][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="cb274-248">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="upgrading-an-existing-installation"></a><span data-ttu-id="cb274-249">既存のインストールのアップグレード</span><span class="sxs-lookup"><span data-stu-id="cb274-249">Upgrading an existing installation</span></span>

<span data-ttu-id="cb274-250">アップグレード時に最適な結果を得るには、最初に PowerShell をインストールしたときと同じインストール方法を使用してください。</span><span class="sxs-lookup"><span data-stu-id="cb274-250">For best results when upgrading, you should use the same install method you used when you first installed PowerShell.</span></span> <span data-ttu-id="cb274-251">各インストール方法では、PowerShell をそれぞれ異なる場所にインストールします。</span><span class="sxs-lookup"><span data-stu-id="cb274-251">Each installation method installs PowerShell in a different location.</span></span> <span data-ttu-id="cb274-252">PowerShell がインストールされた方法がわからない場合は、この記事のパッケージ情報とインストールされている場所を比較できます。</span><span class="sxs-lookup"><span data-stu-id="cb274-252">If you are not sure how PowerShell was installed, you can compare the installed location with the package information in this article.</span></span> <span data-ttu-id="cb274-253">MSI パッケージを使用してインストールした場合、その情報は **[プログラムと機能]** コントロール パネルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb274-253">If you installed via the MSI package, that information appears in the **Programs and Features** Control Panel.</span></span>

## <a name="installation-support"></a><span data-ttu-id="cb274-254">インストールのサポート</span><span class="sxs-lookup"><span data-stu-id="cb274-254">Installation support</span></span>

<span data-ttu-id="cb274-255">Microsoft は、このドキュメントでインストール方法をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="cb274-255">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="cb274-256">他のソースには、利用可能な別のインストール方法が存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cb274-256">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="cb274-257">そのようなツールや方法が役に立つものであっても、Microsoft は、そのような方法をサポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cb274-257">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

<!-- link references -->

[preview]: https://aka.ms/powershell-release?tag=preview
[latest]: https://aka.ms/powershell-release?tag=stable
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
[winget]: /windows/package-manager/winget
<span data-ttu-id="cb274-261">「[別のインスタンスのテクニック]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register」</span><span class="sxs-lookup"><span data-stu-id="cb274-261">["another instance technique"]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register</span></span>
[Import-PSCoreRelease]: https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease
