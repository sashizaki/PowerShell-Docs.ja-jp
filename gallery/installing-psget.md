---
ms.date: 06/12/2017
contributor: manikb
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: PowerShellGet のインストール
ms.openlocfilehash: 23a53a9117c9f6a7ad157b635cd7ff4b3b3444c5
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62075275"
---
# <a name="installing-powershellget"></a><span data-ttu-id="00a05-103">PowerShellGet のインストール</span><span class="sxs-lookup"><span data-stu-id="00a05-103">Installing PowerShellGet</span></span>

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a><span data-ttu-id="00a05-104">PowerShellGet は、以下のリリースではインボックス モジュールである</span><span class="sxs-lookup"><span data-stu-id="00a05-104">PowerShellGet is an in-box module in the following releases</span></span>

- <span data-ttu-id="00a05-105">[Windows 10](https://www.microsoft.com/windows) 以降</span><span class="sxs-lookup"><span data-stu-id="00a05-105">[Windows 10](https://www.microsoft.com/windows) or newer</span></span>
- <span data-ttu-id="00a05-106">[Windows Server 2016](/windows-server/windows-server) 以降</span><span class="sxs-lookup"><span data-stu-id="00a05-106">[Windows Server 2016](/windows-server/windows-server) or newer</span></span>
- <span data-ttu-id="00a05-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) 以降</span><span class="sxs-lookup"><span data-stu-id="00a05-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) or newer</span></span>
- [<span data-ttu-id="00a05-108">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="00a05-108">PowerShell 6</span></span>](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-powershellget-module-for-powershell-versions-30-and-40"></a><span data-ttu-id="00a05-109">PowerShell バージョン 3.0 および 4.0 用の PowerShellGet モジュールの取得</span><span class="sxs-lookup"><span data-stu-id="00a05-109">Get PowerShellGet module for PowerShell versions 3.0 and 4.0</span></span>

- [<span data-ttu-id="00a05-110">PackageManagement MSI</span><span class="sxs-lookup"><span data-stu-id="00a05-110">PackageManagement MSI</span></span>](https://www.microsoft.com/download/details.aspx?id=51451)

## <a name="get-the-latest-version-from-powershell-gallery"></a><span data-ttu-id="00a05-111">PowerShell ギャラリーからの最新バージョンの取得</span><span class="sxs-lookup"><span data-stu-id="00a05-111">Get the latest version from PowerShell Gallery</span></span>

- <span data-ttu-id="00a05-112">PowerShellGet を更新する前には、最新の Nuget プロバイダーをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00a05-112">Before updating PowerShellGet, you should always install the latest Nuget provider.</span></span> <span data-ttu-id="00a05-113">そのためには、PowerShell セッションで、管理者特権で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="00a05-113">To do that, run the following in an elevated PowerShell session.</span></span>

  ```powershell
  Install-PackageProvider Nuget –Force
  Exit
  ```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a><span data-ttu-id="00a05-114">PowerShell 5.0 (またはそれ以降) のシステムには、最新の PowerShellGet をインストール可能</span><span class="sxs-lookup"><span data-stu-id="00a05-114">For systems with PowerShell 5.0 (or newer) you can install the latest PowerShellGet</span></span>

- <span data-ttu-id="00a05-115">Windows 10、Windows Server 2016、WMF 5.0 または 5.1 がインストールされたシステム、PowerShell 6 を使用するシステムでこれを実行するには、管理者特権で PowerShell セッションから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="00a05-115">To do this on Windows 10, Windows Server 2016, any system with WMF 5.0 or 5.1 installed, or any system with PowerShell 6, run the following commands from an elevated PowerShell session.</span></span>

  ```powershell
  Install-Module –Name PowerShellGet –Force
  Exit
  ```

- <span data-ttu-id="00a05-116">`Update-Module` を使用して新しいバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="00a05-116">Use `Update-Module` to get newer versions.</span></span>

  ```powershell
  Update-Module -Name PowerShellGet
  Exit
  ```

### <a name="for-systems-running-powershell-3-or-powershell-4-that-have-installed-the-packagemanagement-msihttpswwwmicrosoftcomdownloaddetailsaspxid51451"></a><span data-ttu-id="00a05-117">[PackageManagement MSI](https://www.microsoft.com/download/details.aspx?id=51451) をインストールした PowerShell 3 または PowerShell 4 を実行しているシステムの場合</span><span class="sxs-lookup"><span data-stu-id="00a05-117">For systems running PowerShell 3 or PowerShell 4, that have installed the [PackageManagement MSI](https://www.microsoft.com/download/details.aspx?id=51451)</span></span>

- <span data-ttu-id="00a05-118">管理者特権で、PowerShell セッションから PowerShellGet のコマンドレットを使用して、ローカル ディレクトリにモジュールを保存します。</span><span class="sxs-lookup"><span data-stu-id="00a05-118">Use below PowerShellGet cmdlet from an elevated PowerShell session to save the modules to a local directory</span></span>

  ```powershell
  Save-Module PowerShellGet -Path C:\LocalFolder
  Exit
  ```

- <span data-ttu-id="00a05-119">PowerShellGet および PackageManagement モジュールが他のプロセスで確実に読み込まれていないようにします。</span><span class="sxs-lookup"><span data-stu-id="00a05-119">Ensure that PowerShellGet and PackageManagement modules are not loaded in any other processes.</span></span>
- <span data-ttu-id="00a05-120">`$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` フォルダーと `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` フォルダーの内容を削除します。</span><span class="sxs-lookup"><span data-stu-id="00a05-120">Delete contents of `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` and  `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` folders.</span></span>
- <span data-ttu-id="00a05-121">管理者特権で PS コンソールを再度開いて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="00a05-121">Re-open the PS Console with elevated permissions then run the following commands.</span></span>

  ```powershell
  Copy-Item "C:\LocalFolder\PowerShellGet\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
  Copy-Item "C:\LocalFolder\PackageManagement\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
  ```
