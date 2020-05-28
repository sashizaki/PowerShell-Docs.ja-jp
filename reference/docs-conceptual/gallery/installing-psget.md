---
ms.date: 09/19/2019
contributor: manikb
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: PowerShellGet のインストール
ms.openlocfilehash: f42eb0df101eb63a5dc267196fa9f666747b8e35
ms.sourcegitcommit: 23ea4a36ee85f923684657de5313a5adf0b6b094
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83727797"
---
# <a name="installing-powershellget"></a><span data-ttu-id="073c2-103">PowerShellGet のインストール</span><span class="sxs-lookup"><span data-stu-id="073c2-103">Installing PowerShellGet</span></span>

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a><span data-ttu-id="073c2-104">PowerShellGet は、以下のリリースではインボックス モジュールである</span><span class="sxs-lookup"><span data-stu-id="073c2-104">PowerShellGet is an in-box module in the following releases</span></span>

- <span data-ttu-id="073c2-105">[Windows 10](https://www.microsoft.com/windows) 以降</span><span class="sxs-lookup"><span data-stu-id="073c2-105">[Windows 10](https://www.microsoft.com/windows) or newer</span></span>
- <span data-ttu-id="073c2-106">[Windows Server 2016](/windows-server/windows-server) 以降</span><span class="sxs-lookup"><span data-stu-id="073c2-106">[Windows Server 2016](/windows-server/windows-server) or newer</span></span>
- <span data-ttu-id="073c2-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) 以降</span><span class="sxs-lookup"><span data-stu-id="073c2-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) or newer</span></span>
- [<span data-ttu-id="073c2-108">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="073c2-108">PowerShell 6</span></span>](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-the-latest-version-from-powershell-gallery"></a><span data-ttu-id="073c2-109">PowerShell ギャラリーからの最新バージョンの取得</span><span class="sxs-lookup"><span data-stu-id="073c2-109">Get the latest version from PowerShell Gallery</span></span>

<span data-ttu-id="073c2-110">**PowerShellGet** を更新する前には、最新の **NuGet** プロバイダーをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="073c2-110">Before updating **PowerShellGet**, you should always install the latest **NuGet** provider.</span></span> <span data-ttu-id="073c2-111">管理者特権の PowerShell セッションから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="073c2-111">From an elevated PowerShell session, run the following command.</span></span>

```powershell
Install-PackageProvider -Name NuGet -Force
Exit
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a><span data-ttu-id="073c2-112">PowerShell 5.0 (またはそれ以降) のシステムには、最新の PowerShellGet をインストール可能</span><span class="sxs-lookup"><span data-stu-id="073c2-112">For systems with PowerShell 5.0 (or newer) you can install the latest PowerShellGet</span></span>

<span data-ttu-id="073c2-113">Windows 10、Windows Server 2016、WMF 5.0 または 5.1 がインストールされたシステム、PowerShell 6 を使用するシステムに PowerShellGet をインストールするには、管理者特権の PowerShell セッションから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="073c2-113">To install PowerShellGet on Windows 10, Windows Server 2016, any system with WMF 5.0 or 5.1 installed, or any system with PowerShell 6, run the following commands from an elevated PowerShell session.</span></span>

```powershell
Install-Module -Name PowerShellGet -Force
Exit
```

<span data-ttu-id="073c2-114">`Update-Module` を使用して新しいバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="073c2-114">Use `Update-Module` to get newer versions.</span></span>

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-computers-running-powershell-30-or-powershell-40"></a><span data-ttu-id="073c2-115">PowerShell 3.0 または PowerShell 4.0 を実行しているコンピューターの場合</span><span class="sxs-lookup"><span data-stu-id="073c2-115">For computers running PowerShell 3.0 or PowerShell 4.0</span></span>

<span data-ttu-id="073c2-116">この指示は、**PackageManagement Preview** をインストールしているか、いかなるバージョンの **PowerShellGet** もインストールしていないコンピューターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="073c2-116">These instructions apply to computers that have the **PackageManagement Preview** installed or don't have any version of **PowerShellGet** installed.</span></span>

<span data-ttu-id="073c2-117">`Save-Module` コマンドレットは、両方の指示セットで使用されます。</span><span class="sxs-lookup"><span data-stu-id="073c2-117">The `Save-Module` cmdlet is used in both sets of instructions.</span></span> <span data-ttu-id="073c2-118">`Save-Module` では、モジュールと、登録リポジトリからの依存関係があれば、それがダウンロードされ、保存されます。</span><span class="sxs-lookup"><span data-stu-id="073c2-118">`Save-Module` downloads and saves a module and any dependencies from a registered repository.</span></span> <span data-ttu-id="073c2-119">モジュールの最新版はローカル コンピューターの指定のパスに保存されますが、インストールはされません。</span><span class="sxs-lookup"><span data-stu-id="073c2-119">The module's most current version is saved to a specified path on the local computer, but isn't installed.</span></span> <span data-ttu-id="073c2-120">このモジュールを PowerShell 3.0 または 4.0 にインストールするには、モジュールが保存されたフォルダーを `$env:ProgramFiles\WindowsPowerShell\Modules` にコピーします。</span><span class="sxs-lookup"><span data-stu-id="073c2-120">To install the modules in PowerShell 3.0 or 4.0, copy the module saved folders to `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span>

<span data-ttu-id="073c2-121">詳細については、「[Save-Module](/powershell/module/PowershellGet/Save-Module)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="073c2-121">For more information, see [Save-Module](/powershell/module/PowershellGet/Save-Module).</span></span>

> [!NOTE]
> <span data-ttu-id="073c2-122">PowerShell 3.0 と PowerShell 4.0 では、1 つしかモジュールのバージョンをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="073c2-122">PowerShell 3.0 and PowerShell 4.0 only supported one version of a module.</span></span> <span data-ttu-id="073c2-123">モジュールは PowerShell 5.0 以降、`<modulename>\<version>` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="073c2-123">Starting in PowerShell 5.0, modules are installed in `<modulename>\<version>`.</span></span> <span data-ttu-id="073c2-124">これにより、複数のバージョンを共存させインストールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="073c2-124">This allowed you to install multiple versions side-by-side.</span></span> <span data-ttu-id="073c2-125">`Save-Module` を使用してモジュールをダウンロードしたら、`<modulename>\<version>` から、コピー先のコンピューターの `<modulename>` フォルダーにファイルをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="073c2-125">After downloading the module using `Save-Module` you must copy the files from the `<modulename>\<version>` to the `<modulename>` folder on the destination machine.</span></span>

#### <a name="computers-with-the-packagemanagement-preview-installed"></a><span data-ttu-id="073c2-126">PackageManagement Preview がインストールされているコンピューター</span><span class="sxs-lookup"><span data-stu-id="073c2-126">Computers with the PackageManagement Preview installed</span></span>

1. <span data-ttu-id="073c2-127">PowerShell セッションから `Save-Module` を使用し、ローカル ディレクトリにモジュールを保存します。</span><span class="sxs-lookup"><span data-stu-id="073c2-127">From a PowerShell session, use `Save-Module` to save the modules to a local directory.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="073c2-128">**PowerShellGet** モジュールと **PackageManagement** モジュールが他のプロセスで確実に読み込まれていないようにします。</span><span class="sxs-lookup"><span data-stu-id="073c2-128">Ensure that the **PowerShellGet** and **PackageManagement** modules aren't loaded in any other processes.</span></span>
1. <span data-ttu-id="073c2-129">フォルダー: `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` と `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` のコンテンツを削除します。</span><span class="sxs-lookup"><span data-stu-id="073c2-129">Delete the contents of the folders: `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` and `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`.</span></span>
1. <span data-ttu-id="073c2-130">管理者特権で PowerShell コンソールを再度開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="073c2-130">Reopen the PowerShell console with elevated permissions and run the following commands.</span></span>

   ```powershell
   Copy-Item "C:\LocalFolder\PowerShellGet\<version>\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
   Copy-Item "C:\LocalFolder\PackageManagement\<version>\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
   ```

#### <a name="computers-without-powershellget"></a><span data-ttu-id="073c2-131">PowerShellGet のないコンピューター</span><span class="sxs-lookup"><span data-stu-id="073c2-131">Computers without PowerShellGet</span></span>

<span data-ttu-id="073c2-132">いかなるバージョンの **PowerShellGet** もインストールされていないコンピューターの場合、モジュールをインストールするには、**PowerShellGet** がインストールされているコンピューターが必要になります。</span><span class="sxs-lookup"><span data-stu-id="073c2-132">For computer's without any version of **PowerShellGet** installed, a computer with **PowerShellGet** installed is needed to download the modules.</span></span>

1. <span data-ttu-id="073c2-133">**PowerShellGet** がインストールされているコンピューターから、`Save-Module` を使用して **PowerShellGet** の最新版をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="073c2-133">From the computer that has **PowerShellGet** installed, use `Save-Module` to download the current version of **PowerShellGet**.</span></span> <span data-ttu-id="073c2-134">2 つのフォルダーがダウンロードされます。**PowerShellGet** と **PackageManagement** です。</span><span class="sxs-lookup"><span data-stu-id="073c2-134">Two folders are downloaded: **PowerShellGet** and **PackageManagement**.</span></span> <span data-ttu-id="073c2-135">各フォルダーには、バージョン番号付きのサブフォルダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="073c2-135">Each folder contains a subfolder with a version number.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="073c2-136">**PowerShellGet** がインストールされていないコンピューターに **PowerShellGet** フォルダーと **PackageManagement** フォルダーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="073c2-136">Copy the **PowerShellGet** and **PackageManagement** folders to the computer that doesn't have **PowerShellGet** installed.</span></span>

   <span data-ttu-id="073c2-137">宛先ディレクトリは `$env:ProgramFiles\WindowsPowerShell\Modules` です。</span><span class="sxs-lookup"><span data-stu-id="073c2-137">The destination directory is: `$env:ProgramFiles\WindowsPowerShell\Modules`</span></span>
