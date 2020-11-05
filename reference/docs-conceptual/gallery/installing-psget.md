---
ms.date: 09/19/2019
title: PowerShellGet のインストール
description: この記事では、さまざまなバージョンの PowerShell で PowerShellGet モジュールをインストールする方法について説明します。
ms.openlocfilehash: 06ec331446849784bb8464912fbce0e5a940823f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662150"
---
# <a name="installing-powershellget"></a><span data-ttu-id="e91a1-103">PowerShellGet のインストール</span><span class="sxs-lookup"><span data-stu-id="e91a1-103">Installing PowerShellGet</span></span>

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a><span data-ttu-id="e91a1-104">PowerShellGet は、以下のリリースではインボックス モジュールである</span><span class="sxs-lookup"><span data-stu-id="e91a1-104">PowerShellGet is an in-box module in the following releases</span></span>

- <span data-ttu-id="e91a1-105">[Windows 10](https://www.microsoft.com/windows) 以降</span><span class="sxs-lookup"><span data-stu-id="e91a1-105">[Windows 10](https://www.microsoft.com/windows) or newer</span></span>
- <span data-ttu-id="e91a1-106">[Windows Server 2016](/windows-server/windows-server) 以降</span><span class="sxs-lookup"><span data-stu-id="e91a1-106">[Windows Server 2016](/windows-server/windows-server) or newer</span></span>
- <span data-ttu-id="e91a1-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) 以降</span><span class="sxs-lookup"><span data-stu-id="e91a1-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) or newer</span></span>
- [<span data-ttu-id="e91a1-108">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="e91a1-108">PowerShell 6</span></span>](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-the-latest-version-from-powershell-gallery"></a><span data-ttu-id="e91a1-109">PowerShell ギャラリーからの最新バージョンの取得</span><span class="sxs-lookup"><span data-stu-id="e91a1-109">Get the latest version from PowerShell Gallery</span></span>

<span data-ttu-id="e91a1-110">**PowerShellGet** を更新する前には、最新の **NuGet** プロバイダーをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e91a1-110">Before updating **PowerShellGet** , you should always install the latest **NuGet** provider.</span></span> <span data-ttu-id="e91a1-111">管理者特権の PowerShell セッションから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e91a1-111">From an elevated PowerShell session, run the following command.</span></span>

```powershell
Install-PackageProvider -Name NuGet -Force
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a><span data-ttu-id="e91a1-112">PowerShell 5.0 (またはそれ以降) のシステムには、最新の PowerShellGet をインストール可能</span><span class="sxs-lookup"><span data-stu-id="e91a1-112">For systems with PowerShell 5.0 (or newer) you can install the latest PowerShellGet</span></span>

<span data-ttu-id="e91a1-113">Windows 10、Windows Server 2016、WMF 5.0 または 5.1 がインストールされたシステム、PowerShell 6 を使用するシステムに PowerShellGet をインストールするには、管理者特権の PowerShell セッションから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e91a1-113">To install PowerShellGet on Windows 10, Windows Server 2016, any system with WMF 5.0 or 5.1 installed, or any system with PowerShell 6, run the following commands from an elevated PowerShell session.</span></span>

```powershell
Install-Module -Name PowerShellGet -Force
```

<span data-ttu-id="e91a1-114">`Update-Module` を使用して新しいバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="e91a1-114">Use `Update-Module` to get newer versions.</span></span>

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-computers-running-powershell-30-or-powershell-40"></a><span data-ttu-id="e91a1-115">PowerShell 3.0 または PowerShell 4.0 を実行しているコンピューターの場合</span><span class="sxs-lookup"><span data-stu-id="e91a1-115">For computers running PowerShell 3.0 or PowerShell 4.0</span></span>

<span data-ttu-id="e91a1-116">この指示は、 **PackageManagement Preview** をインストールしているか、いかなるバージョンの **PowerShellGet** もインストールしていないコンピューターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e91a1-116">These instructions apply to computers that have the **PackageManagement Preview** installed or don't have any version of **PowerShellGet** installed.</span></span>

<span data-ttu-id="e91a1-117">`Save-Module` コマンドレットは、両方の指示セットで使用されます。</span><span class="sxs-lookup"><span data-stu-id="e91a1-117">The `Save-Module` cmdlet is used in both sets of instructions.</span></span> <span data-ttu-id="e91a1-118">`Save-Module` では、モジュールと、登録リポジトリからの依存関係があれば、それがダウンロードされ、保存されます。</span><span class="sxs-lookup"><span data-stu-id="e91a1-118">`Save-Module` downloads and saves a module and any dependencies from a registered repository.</span></span> <span data-ttu-id="e91a1-119">モジュールの最新版はローカル コンピューターの指定のパスに保存されますが、インストールはされません。</span><span class="sxs-lookup"><span data-stu-id="e91a1-119">The module's most current version is saved to a specified path on the local computer, but isn't installed.</span></span> <span data-ttu-id="e91a1-120">このモジュールを PowerShell 3.0 または 4.0 にインストールするには、モジュールが保存されたフォルダーを `$env:ProgramFiles\WindowsPowerShell\Modules` にコピーします。</span><span class="sxs-lookup"><span data-stu-id="e91a1-120">To install the modules in PowerShell 3.0 or 4.0, copy the module saved folders to `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span>

<span data-ttu-id="e91a1-121">詳細については、「[Save-Module](/powershell/module/PowershellGet/Save-Module)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e91a1-121">For more information, see [Save-Module](/powershell/module/PowershellGet/Save-Module).</span></span>

> [!NOTE]
> <span data-ttu-id="e91a1-122">PowerShell 3.0 と PowerShell 4.0 では、1 つしかモジュールのバージョンをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e91a1-122">PowerShell 3.0 and PowerShell 4.0 only supported one version of a module.</span></span> <span data-ttu-id="e91a1-123">モジュールは PowerShell 5.0 以降、`<modulename>\<version>` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e91a1-123">Starting in PowerShell 5.0, modules are installed in `<modulename>\<version>`.</span></span> <span data-ttu-id="e91a1-124">これにより、複数のバージョンを共存させインストールできるようになります。</span><span class="sxs-lookup"><span data-stu-id="e91a1-124">This allows you to install multiple versions side-by-side.</span></span> <span data-ttu-id="e91a1-125">次の手順に示しているように、`Save-Module` を使用してモジュールをダウンロードしたら、`<modulename>\<version>` から、コピー先のコンピューターの `<modulename>` フォルダーにファイルをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e91a1-125">After downloading the module using `Save-Module` you must copy the files from the `<modulename>\<version>` to the `<modulename>` folder on the destination machine, as shown in the instructions below.</span></span>

#### <a name="preparatory-step-on-computers-running-powershell-30"></a><span data-ttu-id="e91a1-126">PowerShell 3.0 を実行しているコンピューターでの準備手順</span><span class="sxs-lookup"><span data-stu-id="e91a1-126">Preparatory Step on computers running PowerShell 3.0</span></span>

<span data-ttu-id="e91a1-127">以下のセクションの手順では、ディレクトリ `$env:ProgramFiles\WindowsPowerShell\Modules` にモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e91a1-127">The instructions in the sections below install the modules in directory `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span>
<span data-ttu-id="e91a1-128">PowerShell 3.0 では、このディレクトリは既定で `$env:PSModulePath` にリストされないため、モジュールを自動読み込みするには、このディレクトリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e91a1-128">In PowerShell 3.0, this directory isn't listed in `$env:PSModulePath` by default, so you'll need to add it in order for the modules to be auto-loaded.</span></span>

<span data-ttu-id="e91a1-129">管理者特権の PowerShell セッションを開き、次のコマンドを実行します (今後のセッションで反映されます)。</span><span class="sxs-lookup"><span data-stu-id="e91a1-129">Open an elevated PowerShell session and run the following command (which will take effect in future sessions):</span></span>

```powershell
[Environment]::SetEnvironmentVariable(
  'PSModulePath',
  ((([Environment]::GetEnvironmentVariable('PSModulePath', 'Machine') -split ';') + "$env:ProgramFiles\WindowsPowerShell\Modules") -join ';'),
  'Machine'
)
```

#### <a name="computers-with-the-packagemanagement-preview-installed"></a><span data-ttu-id="e91a1-130">PackageManagement Preview がインストールされているコンピューター</span><span class="sxs-lookup"><span data-stu-id="e91a1-130">Computers with the PackageManagement Preview installed</span></span>

> [!NOTE]
> <span data-ttu-id="e91a1-131">PackageManagement Preview は、PowerShellGet を PowerShell バージョン 3 および 4 で使用できるようにするためのダウンロード可能なコンポーネントでしたが、現在は利用できなくなっています。</span><span class="sxs-lookup"><span data-stu-id="e91a1-131">PackageManagement Preview was a downloadable component that made PowerShellGet available to PowerShell versions 3 and 4, but it is no longer available.</span></span>
> <span data-ttu-id="e91a1-132">これが特定のコンピューターにインストールされているかどうかをテストするには、`Get-Module -ListAvailable PowerShellGet` を実行します。</span><span class="sxs-lookup"><span data-stu-id="e91a1-132">To test if it was installed on a given computer, run `Get-Module -ListAvailable PowerShellGet`.</span></span>

1. <span data-ttu-id="e91a1-133">PowerShell セッションで `Save-Module` を使用して、現在のバージョンの **PowerShellGet** をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e91a1-133">From a PowerShell session, use `Save-Module` to download the current version of **PowerShellGet**.</span></span> <span data-ttu-id="e91a1-134">2 つのフォルダーがダウンロードされます。 **PowerShellGet** と **PackageManagement** です。</span><span class="sxs-lookup"><span data-stu-id="e91a1-134">Two folders are downloaded: **PowerShellGet** and **PackageManagement**.</span></span> <span data-ttu-id="e91a1-135">各フォルダーには、バージョン番号付きのサブフォルダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e91a1-135">Each folder contains a subfolder with a version number.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="e91a1-136">**PowerShellGet** モジュールと **PackageManagement** モジュールが他のプロセスで確実に読み込まれていないようにします。</span><span class="sxs-lookup"><span data-stu-id="e91a1-136">Ensure that the **PowerShellGet** and **PackageManagement** modules aren't loaded in any other processes.</span></span>

1. <span data-ttu-id="e91a1-137">管理者特権で PowerShell コンソールを再度開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e91a1-137">Reopen the PowerShell console with elevated permissions and run the following command.</span></span>

   ```powershell
   'PowerShellGet', 'PackageManagement' | % {
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     Remove-Item $targetDir\* -Recurse -Force
     Copy-Item C:\LocalFolder\$_\*\* $targetDir\ -Recurse -Force
   }
   ```

#### <a name="computers-without-powershellget"></a><span data-ttu-id="e91a1-138">PowerShellGet のないコンピューター</span><span class="sxs-lookup"><span data-stu-id="e91a1-138">Computers without PowerShellGet</span></span>

<span data-ttu-id="e91a1-139">いかなるバージョンの **PowerShellGet** もインストールされていないコンピューターの場合 (`Get-Module -ListAvailable PowerShellGet` を使用してテストする)、モジュールをインストールするには、 **PowerShellGet** がインストールされているコンピューターが必要になります。</span><span class="sxs-lookup"><span data-stu-id="e91a1-139">For computers without any version of **PowerShellGet** installed (test with `Get-Module -ListAvailable PowerShellGet`), a computer with **PowerShellGet** installed is needed to download the modules.</span></span>

1. <span data-ttu-id="e91a1-140">**PowerShellGet** がインストールされているコンピューターから、`Save-Module` を使用して **PowerShellGet** の最新版をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e91a1-140">From the computer that has **PowerShellGet** installed, use `Save-Module` to download the current version of **PowerShellGet**.</span></span> <span data-ttu-id="e91a1-141">2 つのフォルダーがダウンロードされます。 **PowerShellGet** と **PackageManagement** です。</span><span class="sxs-lookup"><span data-stu-id="e91a1-141">Two folders are downloaded: **PowerShellGet** and **PackageManagement**.</span></span> <span data-ttu-id="e91a1-142">各フォルダーには、バージョン番号付きのサブフォルダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e91a1-142">Each folder contains a subfolder with a version number.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="e91a1-143">**PowerShellGet** および **PackageManagement** フォルダー内の各 `<version>` サブフォルダーを、 **PowerShellGet** がインストールされていないコンピューターのフォルダー `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` と `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` にそれぞれコピーします。これには、管理者特権でのセッションが必要です。</span><span class="sxs-lookup"><span data-stu-id="e91a1-143">Copy the respective `<version>` subfolder in the **PowerShellGet** and **PackageManagement** folders to the computer that doesn't have **PowerShellGet** installed, into folders `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` and `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` respectively, which requires an elevated session.</span></span>

1. <span data-ttu-id="e91a1-144">たとえば、他方のコンピューター (たとえば、`ws1`) のダウンロード フォルダーに、ターゲット コンピューターから UNC パス (たとえば、`\\ws1\C$\LocalFolder`) を使用してアクセスできる場合は、管理者特権で PowerShell コンソールを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e91a1-144">For instance, if you can access the download folder on the other computer, say `ws1`, from the target computer via a UNC path, say `\\ws1\C$\LocalFolder`, open a PowerShell console with elevated permissions and run the following command:</span></span>

   ```powershell
   'PowerShellGet', 'PackageManagement' | % {
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     $null = New-Item -Type Directory -Force $targetDir
     $fromComputer = 'ws1'  # Specify the name of the other computer here.
     Copy-Item \\$fromComputer\C$\LocalFolder\$_\*\* $targetDir -Recurse -Force
     if (-not (Get-ChildItem $targetDir)) { Throw "Copying failed." }
   }
   ```
