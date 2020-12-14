---
Download Help Link: https://aka.ms/powershell71-help
Help Version: 7.1.0.0
keywords: powershell,コマンドレット
Locale: en-US
Module Guid: 4ae9fd46-338a-459c-8186-07f910774cb8
Module Name: PackageManagement
ms.date: 06/09/2017
schema: 2.0.0
title: PackageManagement
ms.openlocfilehash: 88dcb47bee268af3553bb797aaa264e27ed8c51c
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94889642"
---
# <span data-ttu-id="6954d-103">PackageManagement モジュール</span><span class="sxs-lookup"><span data-stu-id="6954d-103">PackageManagement Module</span></span>

## <span data-ttu-id="6954d-104">説明</span><span class="sxs-lookup"><span data-stu-id="6954d-104">Description</span></span>

<span data-ttu-id="6954d-105">このトピックでは、Package Management コマンドレットのヘルプトピックを示します。</span><span class="sxs-lookup"><span data-stu-id="6954d-105">This topic displays help topics for the Package Management Cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6954d-106">2020年4月の時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン1.0 と1.1 がサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6954d-106">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="6954d-107">TLS 1.2 以降を使用していない場合は、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6954d-107">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="6954d-108">次のコマンドを使用して、TLS 1.2 を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6954d-108">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="6954d-109">詳細については、PowerShell ブログの [お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6954d-109">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="6954d-110">PackageManagement コマンドレット</span><span class="sxs-lookup"><span data-stu-id="6954d-110">PackageManagement Cmdlets</span></span>

### [<span data-ttu-id="6954d-111">Find-Package</span><span class="sxs-lookup"><span data-stu-id="6954d-111">Find-Package</span></span>](Find-Package.md)
<span data-ttu-id="6954d-112">使用可能なパッケージソース内のソフトウェアパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="6954d-112">Finds software packages in available package sources.</span></span>

### [<span data-ttu-id="6954d-113">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="6954d-113">Find-PackageProvider</span></span>](Find-PackageProvider.md)
<span data-ttu-id="6954d-114">インストールに使用できる Package Management パッケージプロバイダーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="6954d-114">Returns a list of Package Management package providers available for installation.</span></span>

### [<span data-ttu-id="6954d-115">Get-Package</span><span class="sxs-lookup"><span data-stu-id="6954d-115">Get-Package</span></span>](Get-Package.md)
<span data-ttu-id="6954d-116">**PackageManagement** と共にインストールされたすべてのソフトウェアパッケージの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="6954d-116">Returns a list of all software packages that were installed with **PackageManagement**.</span></span>

### [<span data-ttu-id="6954d-117">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="6954d-117">Get-PackageProvider</span></span>](Get-PackageProvider.md)
<span data-ttu-id="6954d-118">Package Management に接続されているパッケージプロバイダーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="6954d-118">Returns a list of package providers that are connected to Package Management.</span></span>

### [<span data-ttu-id="6954d-119">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="6954d-119">Get-PackageSource</span></span>](Get-PackageSource.md)
<span data-ttu-id="6954d-120">パッケージプロバイダーに登録されているパッケージソースの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="6954d-120">Gets a list of package sources that are registered for a package provider.</span></span>

### [<span data-ttu-id="6954d-121">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="6954d-121">Import-PackageProvider</span></span>](Import-PackageProvider.md)
<span data-ttu-id="6954d-122">Package Management パッケージプロバイダーを現在のセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="6954d-122">Adds Package Management package providers to the current session.</span></span>

### [<span data-ttu-id="6954d-123">Install-Package</span><span class="sxs-lookup"><span data-stu-id="6954d-123">Install-Package</span></span>](Install-Package.md)
<span data-ttu-id="6954d-124">1つまたは複数のソフトウェアパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6954d-124">Installs one or more software packages.</span></span>

### [<span data-ttu-id="6954d-125">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="6954d-125">Install-PackageProvider</span></span>](Install-PackageProvider.md)
<span data-ttu-id="6954d-126">1つまたは複数の Package Management パッケージプロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6954d-126">Installs one or more Package Management package providers.</span></span>

### [<span data-ttu-id="6954d-127">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="6954d-127">Register-PackageSource</span></span>](Register-PackageSource.md)
<span data-ttu-id="6954d-128">指定したパッケージプロバイダーのパッケージソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="6954d-128">Adds a package source for a specified package provider.</span></span>

### [<span data-ttu-id="6954d-129">Save-Package</span><span class="sxs-lookup"><span data-stu-id="6954d-129">Save-Package</span></span>](Save-Package.md)
<span data-ttu-id="6954d-130">パッケージをインストールせずにローカルコンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="6954d-130">Saves packages to the local computer without installing them.</span></span>

### [<span data-ttu-id="6954d-131">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="6954d-131">Set-PackageSource</span></span>](Set-PackageSource.md)
<span data-ttu-id="6954d-132">指定したパッケージプロバイダーのパッケージソースを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6954d-132">Replaces a package source for a specified package provider.</span></span>

### [<span data-ttu-id="6954d-133">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="6954d-133">Uninstall-Package</span></span>](Uninstall-Package.md)
<span data-ttu-id="6954d-134">1つまたは複数のソフトウェアパッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="6954d-134">Uninstalls one or more software packages.</span></span>

### [<span data-ttu-id="6954d-135">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="6954d-135">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
<span data-ttu-id="6954d-136">登録されているパッケージソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="6954d-136">Removes a registered package source.</span></span>

