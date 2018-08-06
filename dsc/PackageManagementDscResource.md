---
ms.date: 06/20/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC の PackageManagement リソース
ms.openlocfilehash: 18cbbfe0715c82dcfdf4a5fb6ee36ee814e43d3b
ms.sourcegitcommit: c3f1a83b59484651119630f3089aa51b6e7d4c3c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2018
ms.locfileid: "39268094"
---
# <a name="dsc-packagemanagement-resource"></a><span data-ttu-id="739cc-103">DSC の PackageManagement リソース</span><span class="sxs-lookup"><span data-stu-id="739cc-103">DSC PackageManagement Resource</span></span>

<span data-ttu-id="739cc-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0、Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="739cc-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span></span>

<span data-ttu-id="739cc-105">Windows PowerShell Desired State Configuration (DSC) の **PackageManagement** リソースは、ターゲット ノードで Package Management パッケージをインストールまたはアンインストールするメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="739cc-105">The **PackageManagement** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall Package Management packages on a target node.</span></span> <span data-ttu-id="739cc-106">このリソースには **PackageManagement** モジュールが必要です。これは、[http://PowerShellGallery.com](http://PowerShellGallery.com) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="739cc-106">This resource requires the **PackageManagement** module, available from [http://PowerShellGallery.com](http://PowerShellGallery.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="739cc-107">**PackageManagement** モジュールは、次のプロパティ情報が適切であるようにバージョン 1.1.7.0 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="739cc-107">The **PackageManagement** module should be at least version 1.1.7.0 for the following property information to be correct.</span></span>

## <a name="syntax"></a><span data-ttu-id="739cc-108">構文</span><span class="sxs-lookup"><span data-stu-id="739cc-108">Syntax</span></span>

```
PackageManagement [string] #ResourceName
{
    Name = [string]
    [AdditionalParameters = [HashTable]]
    [DependsOn = [string[]]]
    [Ensure = [string]{ Absent | Present }]
    [MaximumVersion = [string]]
    [MinimumVersion = [string]]
    [ProviderName = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [RequiredVersion = [string]]
    [Source = [string]]
    [SourceCredential = [PSCredential]]
}
```

## <a name="properties"></a><span data-ttu-id="739cc-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="739cc-109">Properties</span></span>

| <span data-ttu-id="739cc-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="739cc-110">Property</span></span> | <span data-ttu-id="739cc-111">説明</span><span class="sxs-lookup"><span data-stu-id="739cc-111">Description</span></span> |
| --- | --- |
| <span data-ttu-id="739cc-112">名前</span><span class="sxs-lookup"><span data-stu-id="739cc-112">Name</span></span>| <span data-ttu-id="739cc-113">インストールまたはアンインストールするパッケージの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="739cc-113">Specifies the name of the Package to be installed or uninstalled.</span></span>|
| <span data-ttu-id="739cc-114">AdditionalParameters</span><span class="sxs-lookup"><span data-stu-id="739cc-114">AdditionalParameters</span></span>| <span data-ttu-id="739cc-115">`Get-Package -AdditionalArguments` に渡されるパラメーターのプロバイダー固有のハッシュ テーブル。</span><span class="sxs-lookup"><span data-stu-id="739cc-115">Provider specific hashtable of parameters that would be passed to `Get-Package -AdditionalArguments`.</span></span> <span data-ttu-id="739cc-116">たとえば、NuGet プロバイダーでは DestinationPath のような追加のパラメーターを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="739cc-116">For example, for NuGet provider you can pass additional parameters like DestinationPath.</span></span>|
| <span data-ttu-id="739cc-117">Ensure</span><span class="sxs-lookup"><span data-stu-id="739cc-117">Ensure</span></span>| <span data-ttu-id="739cc-118">パッケージをインストールまたはアンインストールするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="739cc-118">Determines whether the package is to be installed or uninstalled.</span></span>|
| <span data-ttu-id="739cc-119">MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="739cc-119">MaximumVersion</span></span>|<span data-ttu-id="739cc-120">検索するパッケージで許容される最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="739cc-120">Specifies the maximum allowed version of the package that you want to find.</span></span> <span data-ttu-id="739cc-121">このパラメーターを追加しない場合、リソースでは利用できるパッケージの最新バージョンが検索されます。</span><span class="sxs-lookup"><span data-stu-id="739cc-121">If you do not add this parameter, the resource finds the highest available version of the package.</span></span>|
| <span data-ttu-id="739cc-122">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="739cc-122">MinimumVersion</span></span>|<span data-ttu-id="739cc-123">検索するパッケージで許容される最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="739cc-123">Specifies the minimum allowed version of the package that you want to find.</span></span> <span data-ttu-id="739cc-124">このパラメーターを追加しない場合、_MaximumVersion_ パラメーターで指定された最大バージョンも満たす、パッケージで利用可能な最新バージョンがリソースによって検索されます。</span><span class="sxs-lookup"><span data-stu-id="739cc-124">If you do not add this parameter, the resource finds the highest available version of the package that also satisfies any maximum specified version specified by the _MaximumVersion_ parameter.</span></span>|
| <span data-ttu-id="739cc-125">ProviderName</span><span class="sxs-lookup"><span data-stu-id="739cc-125">ProviderName</span></span>| <span data-ttu-id="739cc-126">パッケージの検索先となるパッケージ プロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="739cc-126">Specifies a package provider name to which to scope your package search.</span></span> <span data-ttu-id="739cc-127">`Get-PackageProvider` コマンドレットを実行して、パッケージ プロバイダー名を取得できます。</span><span class="sxs-lookup"><span data-stu-id="739cc-127">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>|
| <span data-ttu-id="739cc-128">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="739cc-128">RequiredVersion</span></span>| <span data-ttu-id="739cc-129">インストールするパッケージの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="739cc-129">Specifies the exact version of the package that you want to install.</span></span> <span data-ttu-id="739cc-130">このパラメーターを指定しない場合、_MaximumVersion_ パラメーターで指定された最大バージョンも満たす、パッケージで利用可能な最新バージョンがこの DSC リソースによってインストールされます。</span><span class="sxs-lookup"><span data-stu-id="739cc-130">If you do not specify this parameter, this DSC resource installs the newest available version of the package that also satisfies any maximum version specified by the _MaximumVersion_ parameter.</span></span>|
| <span data-ttu-id="739cc-131">ソース</span><span class="sxs-lookup"><span data-stu-id="739cc-131">Source</span></span>| <span data-ttu-id="739cc-132">パッケージのあるパッケージ ソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="739cc-132">Specifies the name of the package source where the package can be found.</span></span> <span data-ttu-id="739cc-133">これは、URI か、`Register-PackageSource` または PackageManagementSource の DSC リソースに登録されたソースのどちらかになります。</span><span class="sxs-lookup"><span data-stu-id="739cc-133">This can either be a URI or a source registered with `Register-PackageSource` or PackageManagementSource DSC resource.</span></span>|
| <span data-ttu-id="739cc-134">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="739cc-134">SourceCredential</span></span> | <span data-ttu-id="739cc-135">指定したパッケージ プロバイダーまたはソースのパッケージをインストールする権限を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="739cc-135">Specifies a user account that has rights to install a package for a specified package provider or source.</span></span>|

## <a name="additional-parameters"></a><span data-ttu-id="739cc-136">追加のパラメーター</span><span class="sxs-lookup"><span data-stu-id="739cc-136">Additional Parameters</span></span>

<span data-ttu-id="739cc-137">次の表は、AdditionalParameters プロパティのオプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="739cc-137">The following table lists options for the AdditionalParameters property.</span></span>

| <span data-ttu-id="739cc-138">パラメーター</span><span class="sxs-lookup"><span data-stu-id="739cc-138">Parameter</span></span> | <span data-ttu-id="739cc-139">説明</span><span class="sxs-lookup"><span data-stu-id="739cc-139">Description</span></span> |
| --- | --- |
| <span data-ttu-id="739cc-140">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="739cc-140">DestinationPath</span></span>| <span data-ttu-id="739cc-141">組み込みの Nuget プロバイダーなどのプロバイダーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="739cc-141">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="739cc-142">パッケージをインストールするファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="739cc-142">Specifies a file location where you want the package to be installed.</span></span>|
| <span data-ttu-id="739cc-143">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="739cc-143">InstallationPolicy</span></span>| <span data-ttu-id="739cc-144">組み込みの Nuget プロバイダーなどのプロバイダーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="739cc-144">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="739cc-145">パッケージのソースを信頼するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="739cc-145">Determines whether you trust the package's source.</span></span> <span data-ttu-id="739cc-146">`Untrusted` または `Trusted` のどちらかです。</span><span class="sxs-lookup"><span data-stu-id="739cc-146">One of: `Untrusted`, `Trusted`.</span></span>|

## <a name="example"></a><span data-ttu-id="739cc-147">例</span><span class="sxs-lookup"><span data-stu-id="739cc-147">Example</span></span>

<span data-ttu-id="739cc-148">この例では、**PackageManagement** DSC リソースを使用して、**JQuery** NuGet パッケージおよび **GistProvider** PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="739cc-148">This example installs the **JQuery** NuGet package and **GistProvider** PowerShell module using the **PackageManagement** DSC resource.</span></span> <span data-ttu-id="739cc-149">この例では、最初に必要なパッケージのソースが利用できることを確認し、次に **JQuery** および **GistProvider** のパッケージ (それぞれ NuGet と PowerShell) の予期される状態を定義しています。</span><span class="sxs-lookup"><span data-stu-id="739cc-149">This example first ensures the required package sources are available then defines the expected state of the **JQuery** and **GistProvider** packages (NuGet and PowerShell, respectively).</span></span>

```powershell
Configuration PackageTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceLocation   = "http://nuget.org/api/v2/"
        InstallationPolicy ="Trusted"
    }

    PackageManagementSource PSGallery
    {
        Ensure      = "Present"
        Name        = "psgallery"
        ProviderName= "PowerShellGet"
        SourceLocation   = "https://www.powershellgallery.com/api/v2/"
        InstallationPolicy ="Trusted"
    }

    PackageManagement NugetPackage
    {
        Ensure               = "Present"
        Name                 = "JQuery"
        AdditionalParameters = "$env:HomeDrive\nuget"
        RequiredVersion      = "2.0.1"
        DependsOn            = "[PackageManagementSource]SourceRepository"
    }

    PackageManagement PSModule
    {
        Ensure               = "Present"
        Name                 = "gistprovider"
        Source               = "PSGallery"
        DependsOn            = "[PackageManagementSource]PSGallery"
    }
}
```