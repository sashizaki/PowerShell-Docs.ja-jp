---
ms.date: 06/12/2017
contributor: manikb
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: PowerShellGet のインストール
ms.openlocfilehash: a0ef46a9ee4bbf668a58067256d098967bde48c5
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71143591"
---
# <a name="installing-powershellget"></a><span data-ttu-id="d5f9a-103">PowerShellGet のインストール</span><span class="sxs-lookup"><span data-stu-id="d5f9a-103">Installing PowerShellGet</span></span>

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a><span data-ttu-id="d5f9a-104">PowerShellGet は、以下のリリースではインボックス モジュールである</span><span class="sxs-lookup"><span data-stu-id="d5f9a-104">PowerShellGet is an in-box module in the following releases</span></span>

- <span data-ttu-id="d5f9a-105">[Windows 10](https://www.microsoft.com/windows) 以降</span><span class="sxs-lookup"><span data-stu-id="d5f9a-105">[Windows 10](https://www.microsoft.com/windows) or newer</span></span>
- <span data-ttu-id="d5f9a-106">[Windows Server 2016](/windows-server/windows-server) 以降</span><span class="sxs-lookup"><span data-stu-id="d5f9a-106">[Windows Server 2016](/windows-server/windows-server) or newer</span></span>
- <span data-ttu-id="d5f9a-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) 以降</span><span class="sxs-lookup"><span data-stu-id="d5f9a-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) or newer</span></span>
- [<span data-ttu-id="d5f9a-108">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="d5f9a-108">PowerShell 6</span></span>](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-the-latest-version-from-powershell-gallery"></a><span data-ttu-id="d5f9a-109">PowerShell ギャラリーからの最新バージョンの取得</span><span class="sxs-lookup"><span data-stu-id="d5f9a-109">Get the latest version from PowerShell Gallery</span></span>

<span data-ttu-id="d5f9a-110">**PowerShellGet** を更新する前には、最新の **NuGet** プロバイダーをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5f9a-110">Before updating **PowerShellGet**, you should always install the latest **NuGet** provider.</span></span> <span data-ttu-id="d5f9a-111">管理者特権の PowerShell セッションから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d5f9a-111">From an elevated PowerShell session, run the following command.</span></span>

```powershell
Install-PackageProvider -Name NuGet -Force
Exit
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a><span data-ttu-id="d5f9a-112">PowerShell 5.0 (またはそれ以降) のシステムには、最新の PowerShellGet をインストール可能</span><span class="sxs-lookup"><span data-stu-id="d5f9a-112">For systems with PowerShell 5.0 (or newer) you can install the latest PowerShellGet</span></span>

<span data-ttu-id="d5f9a-113">Windows 10、Windows Server 2016、WMF 5.0 または 5.1 がインストールされたシステム、PowerShell 6 を使用するシステムに PowerShellGet をインストールするには、管理者特権の PowerShell セッションから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d5f9a-113">To install PowerShellGet on Windows 10, Windows Server 2016, any system with WMF 5.0 or 5.1 installed, or any system with PowerShell 6, run the following commands from an elevated PowerShell session.</span></span>

```powershell
Install-Module -Name PowerShellGet -Force
Exit
```

<span data-ttu-id="d5f9a-114">`Update-Module` を使用して新しいバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="d5f9a-114">Use `Update-Module` to get newer versions.</span></span>

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-systems-running-powershell-3-or-powershell-4-that-have-installed-the-packagemanagement-preview"></a><span data-ttu-id="d5f9a-115">PackageManagement プレビューをインストールした PowerShell 3 または PowerShell 4 を実行しているシステムの場合</span><span class="sxs-lookup"><span data-stu-id="d5f9a-115">For systems running PowerShell 3 or PowerShell 4, that have installed the PackageManagement Preview</span></span>

1. <span data-ttu-id="d5f9a-116">管理者特権の PowerShell セッションから `Save-Module` を使用し、ローカル ディレクトリにモジュールを保存します。</span><span class="sxs-lookup"><span data-stu-id="d5f9a-116">From an elevated PowerShell session, use `Save-Module` to save the modules to a local directory.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder
   Exit
   ```

1. <span data-ttu-id="d5f9a-117">**PowerShellGet** モジュールと **PackageManagement** モジュールが他のプロセスで確実に読み込まれていないようにします。</span><span class="sxs-lookup"><span data-stu-id="d5f9a-117">Ensure that the **PowerShellGet** and **PackageManagement** modules aren't loaded in any other processes.</span></span>
1. <span data-ttu-id="d5f9a-118">フォルダー: `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` と `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` のコンテンツを削除します。</span><span class="sxs-lookup"><span data-stu-id="d5f9a-118">Delete the contents of the folders: `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` and `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`.</span></span>
1. <span data-ttu-id="d5f9a-119">管理者特権で PowerShell コンソールを再度開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d5f9a-119">Reopen the PowerShell console with elevated permissions and run the following commands.</span></span>

   ```powershell
   Copy-Item "C:\LocalFolder\PowerShellGet\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
   Copy-Item "C:\LocalFolder\PackageManagement\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
   ```
