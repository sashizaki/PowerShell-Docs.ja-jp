---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: 4ae9fd46-338a-459c-8186-07f910774cb8
Module Name: PackageManagement
ms.date: 06/09/2017
schema: 2.0.0
title: PackageManagement
ms.openlocfilehash: 86e6f37f6f7f0527c5dcca309cf581cb6f1b4de5
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99599913"
---
# <span data-ttu-id="62284-102">PackageManagement モジュール</span><span class="sxs-lookup"><span data-stu-id="62284-102">PackageManagement Module</span></span>

## <span data-ttu-id="62284-103">説明</span><span class="sxs-lookup"><span data-stu-id="62284-103">Description</span></span>

<span data-ttu-id="62284-104">このトピックでは、Package Management コマンドレットのヘルプトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="62284-104">This topic displays help topics for the Package Management Cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62284-105">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="62284-105">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="62284-106">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="62284-106">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="62284-107">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="62284-107">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="62284-108">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62284-108">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="62284-109">PackageManagement コマンドレット</span><span class="sxs-lookup"><span data-stu-id="62284-109">PackageManagement Cmdlets</span></span>

### [<span data-ttu-id="62284-110">Find-Package</span><span class="sxs-lookup"><span data-stu-id="62284-110">Find-Package</span></span>](Find-Package.md)
<span data-ttu-id="62284-111">使用可能なパッケージソース内のソフトウェアパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="62284-111">Finds software packages in available package sources.</span></span>

### [<span data-ttu-id="62284-112">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="62284-112">Find-PackageProvider</span></span>](Find-PackageProvider.md)
<span data-ttu-id="62284-113">インストールに使用できる Package Management パッケージプロバイダーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="62284-113">Returns a list of Package Management package providers available for installation.</span></span>

### [<span data-ttu-id="62284-114">Get-Package</span><span class="sxs-lookup"><span data-stu-id="62284-114">Get-Package</span></span>](Get-Package.md)
<span data-ttu-id="62284-115">**PackageManagement** と共にインストールされたすべてのソフトウェアパッケージの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="62284-115">Returns a list of all software packages that were installed with **PackageManagement**.</span></span>

### [<span data-ttu-id="62284-116">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="62284-116">Get-PackageProvider</span></span>](Get-PackageProvider.md)
<span data-ttu-id="62284-117">Package Management に接続されているパッケージプロバイダーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="62284-117">Returns a list of package providers that are connected to Package Management.</span></span>

### [<span data-ttu-id="62284-118">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="62284-118">Get-PackageSource</span></span>](Get-PackageSource.md)
<span data-ttu-id="62284-119">パッケージプロバイダーに登録されているパッケージソースの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="62284-119">Gets a list of package sources that are registered for a package provider.</span></span>

### [<span data-ttu-id="62284-120">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="62284-120">Import-PackageProvider</span></span>](Import-PackageProvider.md)
<span data-ttu-id="62284-121">Package Management パッケージプロバイダーを現在のセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="62284-121">Adds Package Management package providers to the current session.</span></span>

### [<span data-ttu-id="62284-122">Install-Package</span><span class="sxs-lookup"><span data-stu-id="62284-122">Install-Package</span></span>](Install-Package.md)
<span data-ttu-id="62284-123">1つまたは複数のソフトウェアパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="62284-123">Installs one or more software packages.</span></span>

### [<span data-ttu-id="62284-124">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="62284-124">Install-PackageProvider</span></span>](Install-PackageProvider.md)
<span data-ttu-id="62284-125">1つまたは複数の Package Management パッケージプロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="62284-125">Installs one or more Package Management package providers.</span></span>

### [<span data-ttu-id="62284-126">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="62284-126">Register-PackageSource</span></span>](Register-PackageSource.md)
<span data-ttu-id="62284-127">指定したパッケージプロバイダーのパッケージソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="62284-127">Adds a package source for a specified package provider.</span></span>

### [<span data-ttu-id="62284-128">Save-Package</span><span class="sxs-lookup"><span data-stu-id="62284-128">Save-Package</span></span>](Save-Package.md)
<span data-ttu-id="62284-129">パッケージをインストールせずにローカルコンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="62284-129">Saves packages to the local computer without installing them.</span></span>

### [<span data-ttu-id="62284-130">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="62284-130">Set-PackageSource</span></span>](Set-PackageSource.md)
<span data-ttu-id="62284-131">指定したパッケージプロバイダーのパッケージソースを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="62284-131">Replaces a package source for a specified package provider.</span></span>

### [<span data-ttu-id="62284-132">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="62284-132">Uninstall-Package</span></span>](Uninstall-Package.md)
<span data-ttu-id="62284-133">1つまたは複数のソフトウェアパッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="62284-133">Uninstalls one or more software packages.</span></span>

### [<span data-ttu-id="62284-134">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="62284-134">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
<span data-ttu-id="62284-135">登録されているパッケージソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="62284-135">Removes a registered package source.</span></span>
