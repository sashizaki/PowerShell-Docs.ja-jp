---
ms.date: 06/12/2017
contributor: manikb
ms.topic: reference
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: PowerShellGet のインストール
ms.openlocfilehash: 6190c7caee61b43e70073ff7b30f867a901d3042
ms.sourcegitcommit: e9ad4d85fd7eb72fb5bc37f6ca3ae1282ae3c6d7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
---
# <a name="get-powershellget-module"></a><span data-ttu-id="62e4c-103">PowerShellGet モジュールの取得</span><span class="sxs-lookup"><span data-stu-id="62e4c-103">Get PowerShellGet module</span></span>

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a><span data-ttu-id="62e4c-104">PowerShellGet は、以下のリリースではインボックス モジュールである</span><span class="sxs-lookup"><span data-stu-id="62e4c-104">PowerShellGet is an in-box module in the following releases</span></span>

- <span data-ttu-id="62e4c-105">[Windows 10](https://www.microsoft.com/windows/get-windows-10) 以降</span><span class="sxs-lookup"><span data-stu-id="62e4c-105">[Windows 10](https://www.microsoft.com/windows/get-windows-10) or newer</span></span>
- <span data-ttu-id="62e4c-106">[Windows Server 2016](https://technet.microsoft.com/windows-server-docs/get-started/windows-server-2016) 以降</span><span class="sxs-lookup"><span data-stu-id="62e4c-106">[Windows Server 2016](https://technet.microsoft.com/windows-server-docs/get-started/windows-server-2016) or newer</span></span>
- <span data-ttu-id="62e4c-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) 以降</span><span class="sxs-lookup"><span data-stu-id="62e4c-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) or newer</span></span>
- [<span data-ttu-id="62e4c-108">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="62e4c-108">PowerShell 6</span></span>](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-powershellget-module-for-powershell-versions-30-and-40"></a><span data-ttu-id="62e4c-109">PowerShell バージョン 3.0 および 4.0 用の PowerShellGet モジュールの取得</span><span class="sxs-lookup"><span data-stu-id="62e4c-109">Get PowerShellGet module for PowerShell versions 3.0 and 4.0</span></span>

- [<span data-ttu-id="62e4c-110">PackageManagement MSI</span><span class="sxs-lookup"><span data-stu-id="62e4c-110">PackageManagement MSI</span></span>](http://go.microsoft.com/fwlink/?LinkID=746217&clcid=0x409)

## <a name="get-the-latest-version-from-powershell-gallery"></a><span data-ttu-id="62e4c-111">PowerShell ギャラリーからの最新バージョンの取得</span><span class="sxs-lookup"><span data-stu-id="62e4c-111">Get the latest version from PowerShell Gallery</span></span>

- <span data-ttu-id="62e4c-112">PowerShellGet を更新する前には、最新の Nuget プロバイダーをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="62e4c-112">Before updating PowerShellGet, you should always install the latest Nuget provider.</span></span> <span data-ttu-id="62e4c-113">そのためには、PowerShell セッションで、管理者特権で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="62e4c-113">To do that, run the following in an elevated PowerShell session.</span></span>

```powershell
Install-PackageProvider Nuget –Force
Exit
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a><span data-ttu-id="62e4c-114">PowerShell 5.0 (またはそれ以降) のシステムには、最新の PowerShellGet をインストール可能</span><span class="sxs-lookup"><span data-stu-id="62e4c-114">For systems with PowerShell 5.0 (or newer) you can install the latest PowerShellGet</span></span>

- <span data-ttu-id="62e4c-115">Windows 10、Windows Server 2016、WMF 5.0 または 5.1 がインストールされたシステム、PowerShell 6 を使用するシステムでこれを実行するには、管理者特権で PowerShell セッションから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="62e4c-115">To do this on Windows 10, Windows Server 2016, any system with WMF 5.0 or 5.1 installed, or any system with PowerShell 6, run the following commands from an elevated PowerShell session.</span></span>

```powershell
Install-Module –Name PowerShellGet –Force
Exit
```

- <span data-ttu-id="62e4c-116">新しいバージョンを取得するには、Update-Module を使用します。</span><span class="sxs-lookup"><span data-stu-id="62e4c-116">Use Update-Module to get newer versions.</span></span>

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-systems-running-powershell-3-or-powershell-4-that-have-installed-the-packagemanagement-msihttpgomicrosoftcomfwlinklinkid746217clcid0x409"></a><span data-ttu-id="62e4c-117">[PackageManagement MSI](http://go.microsoft.com/fwlink/?LinkID=746217&clcid=0x409) をインストールした PowerShell 3 または PowerShell 4 を実行しているシステムの場合</span><span class="sxs-lookup"><span data-stu-id="62e4c-117">For systems running PowerShell 3 or PowerShell 4, that have installed the [PackageManagement MSI](http://go.microsoft.com/fwlink/?LinkID=746217&clcid=0x409)</span></span>

- <span data-ttu-id="62e4c-118">管理者特権で、PowerShell セッションから PowerShellGet のコマンドレットを使用して、ローカル ディレクトリにモジュールを保存します。</span><span class="sxs-lookup"><span data-stu-id="62e4c-118">Use below PowerShellGet cmdlet from an elevated PowerShell session to save the modules to a local directory</span></span>

```powershell
Save-Module PowerShellGet -Path C:\LocalFolder
Exit
```

- <span data-ttu-id="62e4c-119">PowerShellGet および PackageManagment モジュールが他のプロセスで読み込まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="62e4c-119">Ensure that PowerShellGet and PackageManagment modules are not loaded in any other processes.</span></span>
- <span data-ttu-id="62e4c-120">`$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` フォルダーと `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` フォルダーの内容を削除します。</span><span class="sxs-lookup"><span data-stu-id="62e4c-120">Delete contents of `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` and  `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` folders.</span></span>
- <span data-ttu-id="62e4c-121">管理者特権で PS コンソールを再度開いて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="62e4c-121">Re-open the PS Console with elevated permissions then run the following commands.</span></span>

```powershell
Copy-Item "C:\LocalFolder\PowerShellGet\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
Copy-Item "C:\LocalFolder\PackageManagement\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
```