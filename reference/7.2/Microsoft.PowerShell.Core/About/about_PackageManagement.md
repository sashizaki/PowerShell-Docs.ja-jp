---
description: PackageManagement は、ソフトウェアパッケージマネージャーのアグリゲーターです。
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_packagemanagement?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PackageManagement
ms.openlocfilehash: 22f47d01063778fca4f51a534b15d485b3beee28
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602170"
---
# <a name="about-packagemanagement"></a><span data-ttu-id="23115-103">PackageManagement について</span><span class="sxs-lookup"><span data-stu-id="23115-103">About PackageManagement</span></span>

## <a name="short-description"></a><span data-ttu-id="23115-104">概要</span><span class="sxs-lookup"><span data-stu-id="23115-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="23115-105">PackageManagement は、ソフトウェアパッケージマネージャーのアグリゲーターです。</span><span class="sxs-lookup"><span data-stu-id="23115-105">PackageManagement is an aggregator for software package managers.</span></span>

## <a name="long-description"></a><span data-ttu-id="23115-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="23115-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="23115-107">PackageManagement 機能は、Windows PowerShell 5.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="23115-107">PackageManagement functionality was introduced in Windows PowerShell 5.0.</span></span>

<span data-ttu-id="23115-108">PackageManagement は、ソフトウェアパッケージ管理システムのための統一されたインターフェイスです。PackageManagement コマンドレットを実行して、ソフトウェアの検出、インストール、およびインベントリ (SDII) のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="23115-108">PackageManagement is a unified interface for software package management systems; you can run PackageManagement cmdlets to perform software discovery, installation, and inventory (SDII) tasks.</span></span> <span data-ttu-id="23115-109">基になるインストールテクノロジに関係なく、PackageManagement モジュールで共通のコマンドレットを実行して、パッケージの検索、インストール、またはアンインストールを行うことができます。パッケージリポジトリを追加、削除、および照会します。コンピューターに対してクエリを実行し、インストールされているソフトウェアパッケージを確認します。</span><span class="sxs-lookup"><span data-stu-id="23115-109">Regardless of the underlying installation technology, you can run the common cmdlets in the PackageManagement module to search for, install, or uninstall packages; add, remove, and query package repositories; and run queries on a computer to determine which software packages are installed.</span></span>

<span data-ttu-id="23115-110">PackageManagement では、他のソフトウェアパッケージ管理システムのサポートを有効にする柔軟なプラグインモデルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="23115-110">PackageManagement supports a flexible plug-in model that enables support for other software package management systems.</span></span>

<span data-ttu-id="23115-111">PackageManagement モジュールは、PowerShell の Windows PowerShell 5.0 以降のリリースに含まれており、パッケージプロバイダー、パッケージソース、パッケージ自体という3つのレベルのパッケージ管理構造で機能します。</span><span class="sxs-lookup"><span data-stu-id="23115-111">The PackageManagement module is included with Windows PowerShell 5.0 and later releases of PowerShell, and works on three levels of package management structure: package providers, package sources, and the packages themselves.</span></span> <span data-ttu-id="23115-112">いくつかの用語を定義してみましょう。</span><span class="sxs-lookup"><span data-stu-id="23115-112">Let us define some terms:</span></span>

- <span data-ttu-id="23115-113">パッケージマネージャー: ソフトウェアパッケージ管理システム。</span><span class="sxs-lookup"><span data-stu-id="23115-113">Package manager: Software package management system.</span></span> <span data-ttu-id="23115-114">PackageManagement の用語では、これはパッケージプロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="23115-114">In PackageManagement terms, this is a package provider.</span></span>
- <span data-ttu-id="23115-115">パッケージプロバイダー: パッケージマネージャーの PackageManagement 用語。</span><span class="sxs-lookup"><span data-stu-id="23115-115">Package provider: PackageManagement term for a package manager.</span></span> <span data-ttu-id="23115-116">例として、Windows インストーラー、Chocolatey などを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="23115-116">Examples can include Windows Installer, Chocolatey, and others.</span></span>
- <span data-ttu-id="23115-117">パッケージソース: パッケージプロバイダーをリポジトリとして使用するように構成する、URL、ローカルフォルダー、またはネットワーク共有フォルダー。</span><span class="sxs-lookup"><span data-stu-id="23115-117">Package source: A URL, local folder, or network shared folder that you configure package providers to use as a repository.</span></span>
- <span data-ttu-id="23115-118">パッケージ: パッケージプロバイダーが管理し、特定のパッケージソースに格納されているソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="23115-118">Package: A piece of software that a package provider manages, and that is stored in a specific package source.</span></span>

<span data-ttu-id="23115-119">PackageManagement モジュールには、次のコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="23115-119">The PackageManagement module includes the following cmdlets.</span></span> <span data-ttu-id="23115-120">詳細については、 [PackageManagement](/powershell/module/packagemanagement) のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="23115-120">For more information, see the [PackageManagement](/powershell/module/packagemanagement) help.</span></span>

- <span data-ttu-id="23115-121">`Get-PackageProvider`: PackageManagement に接続されているパッケージプロバイダーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="23115-121">`Get-PackageProvider`: Returns a list of package providers that are  connected to PackageManagement.</span></span>
- <span data-ttu-id="23115-122">`Get-PackageSource`: パッケージプロバイダーに登録されているパッケージソースの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="23115-122">`Get-PackageSource`: Gets a list of package sources that are registered for a package provider.</span></span>
- <span data-ttu-id="23115-123">`Register-PackageSource`: 指定したパッケージプロバイダーのパッケージソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="23115-123">`Register-PackageSource`: Adds a package source for a specified package provider.</span></span>
- <span data-ttu-id="23115-124">`Set-PackageSource`: 既存のパッケージソースのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="23115-124">`Set-PackageSource`: Sets properties on an existing package source.</span></span>
- <span data-ttu-id="23115-125">`Unregister-PackageSource`: 登録されているパッケージソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="23115-125">`Unregister-PackageSource`: Removes a registered package source.</span></span>
- <span data-ttu-id="23115-126">`Get-Package`: インストールされているソフトウェアパッケージの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="23115-126">`Get-Package`: Returns a list of installed software packages.</span></span>
- <span data-ttu-id="23115-127">`Find-Package`: 使用可能なパッケージソース内のソフトウェアパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="23115-127">`Find-Package`: Finds software packages in available package sources.</span></span>
- <span data-ttu-id="23115-128">`Install-Package`: 1 つまたは複数のソフトウェアパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="23115-128">`Install-Package`: Installs one or more software packages.</span></span>
- <span data-ttu-id="23115-129">`Save-Package`: パッケージをインストールせずにローカルコンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="23115-129">`Save-Package`: Saves packages to the local computer without installing them.</span></span>
- <span data-ttu-id="23115-130">`Uninstall-Package`: 1 つまたは複数のソフトウェアパッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="23115-130">`Uninstall-Package`: Uninstalls one or more software packages.</span></span>

### <a name="package-provider-bootstrapping-and-dynamic-cmdlet-parameters"></a><span data-ttu-id="23115-131">パッケージプロバイダーブートストラップと動的コマンドレットパラメーター</span><span class="sxs-lookup"><span data-stu-id="23115-131">Package Provider Bootstrapping and Dynamic Cmdlet Parameters</span></span>

<span data-ttu-id="23115-132">既定では、PackageManagement はコアブートストラッププロバイダーに付属しています。</span><span class="sxs-lookup"><span data-stu-id="23115-132">By default, PackageManagement ships with a core bootstrap provider.</span></span> <span data-ttu-id="23115-133">プロバイダーをブートストラップすることで、必要に応じて追加のパッケージプロバイダーをインストールできます。つまり、web サービスからプロバイダーを自動的にインストールするように求めるプロンプトに応答します。</span><span class="sxs-lookup"><span data-stu-id="23115-133">You can install additional package providers as you need them by bootstrapping the providers; that is, responding to a prompt to install the provider automatically, from a web service.</span></span> <span data-ttu-id="23115-134">任意の PackageManagement コマンドレットを使用してパッケージプロバイダーを指定できます。指定したプロバイダーが使用できない場合は、プロバイダーをブートストラップする (または自動的にインストールする) ことを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="23115-134">You can specify a package provider with any PackageManagement cmdlet; if the specified provider is not available, PackageManagement prompts you to bootstrap (or automatically install) the provider.</span></span> <span data-ttu-id="23115-135">次の例では、Chocolatey プロバイダーがまだインストールされていない場合、PackageManagement ブートストラップによってプロバイダーがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="23115-135">In the following examples, if the Chocolatey provider is not already installed, PackageManagement bootstrapping installs the provider.</span></span>

```powershell
Find-Package -Provider Chocolatey <PackageName>
```

<span data-ttu-id="23115-136">Chocolatey プロバイダーがまだインストールされていない場合は、上記のコマンドを実行すると、インストールを求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="23115-136">If the Chocolatey provider is not already installed, when you run the preceding command, you are prompted to install it.</span></span>

```powershell
Install-Package <Chocolatey package Name> -ForceBootstrap
```

<span data-ttu-id="23115-137">Chocolatey プロバイダーがまだインストールされていない場合は、上記のコマンドを実行すると、プロバイダーがインストールされます。ただし、ForceBootstrap パラメーターがコマンドに追加されているため、インストールするように求められることはありません。プロバイダーとパッケージの両方が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="23115-137">If the Chocolatey provider is not already installed, when you run the preceding command, the provider is installed; but because the ForceBootstrap parameter has been added to the command, you are not prompted to install it; both the provider and the package are installed automatically.</span></span>

<span data-ttu-id="23115-138">パッケージをインストールしようとしたときに、サポートプロバイダーがまだインストールされていない場合に、ForceBootstrap パラメーターをコマンドに追加しないと、PackageManagement によってプロバイダーをインストールするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="23115-138">When you try to install a package, if you do not already have the supporting provider installed, and you do not add the ForceBootstrap parameter to your command, PackageManagement prompts you to install the provider.</span></span>

<span data-ttu-id="23115-139">PackageManagement コマンドでパッケージプロバイダーを指定すると、そのパッケージプロバイダーに固有の動的パラメーターを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="23115-139">Specifying a package provider in your PackageManagement command can make dynamic parameters available that are specific to that package provider.</span></span> <span data-ttu-id="23115-140">特定の PackageManagement コマンドレットに対して Get-Help を実行すると、パラメーターセットの一覧が返され、使用可能なパッケージプロバイダーの動的パラメーターが個別のパラメーターセットにグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="23115-140">When you run Get-Help for a specific PackageManagement cmdlet, a list of parameter sets are returned, grouping dynamic parameters for available package providers in separate parameter sets.</span></span>

<span data-ttu-id="23115-141">PackageManagement プロジェクトに関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="23115-141">More Information About the PackageManagement Project</span></span>

<span data-ttu-id="23115-142">Packagemanagement パッケージプロバイダーの作成方法を含め、PackageManagement open development プロジェクトの詳細については、GitHub の PackageManagement プロジェクトを参照してください https://oneget.org 。</span><span class="sxs-lookup"><span data-stu-id="23115-142">For more information about the PackageManagement open development project, including how to create a PackageManagement package provider, see the PackageManagement project on GitHub at https://oneget.org.</span></span>

## <a name="see-also"></a><span data-ttu-id="23115-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="23115-143">SEE ALSO</span></span>

[<span data-ttu-id="23115-144">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="23115-144">Get-PackageProvider</span></span>](xref:PackageManagement.Get-PackageProvider)

[<span data-ttu-id="23115-145">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="23115-145">Get-PackageSource</span></span>](xref:PackageManagement.Get-PackageSource)

[<span data-ttu-id="23115-146">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="23115-146">Register-PackageSource</span></span>](xref:PackageManagement.Register-PackageSource)

[<span data-ttu-id="23115-147">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="23115-147">Set-PackageSource</span></span>](xref:PackageManagement.Set-PackageSource)

[<span data-ttu-id="23115-148">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="23115-148">Unregister-PackageSource</span></span>](xref:PackageManagement.Unregister-PackageSource)

[<span data-ttu-id="23115-149">Get-Package</span><span class="sxs-lookup"><span data-stu-id="23115-149">Get-Package</span></span>](xref:PackageManagement.Get-Package)

[<span data-ttu-id="23115-150">Find-Package</span><span class="sxs-lookup"><span data-stu-id="23115-150">Find-Package</span></span>](xref:PackageManagement.Find-Package)

[<span data-ttu-id="23115-151">Install-Package</span><span class="sxs-lookup"><span data-stu-id="23115-151">Install-Package</span></span>](xref:PackageManagement.Install-Package)

[<span data-ttu-id="23115-152">Save-Package</span><span class="sxs-lookup"><span data-stu-id="23115-152">Save-Package</span></span>](xref:PackageManagement.Save-Package)

[<span data-ttu-id="23115-153">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="23115-153">Uninstall-Package</span></span>](xref:PackageManagement.Uninstall-Package)

