---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC の PackageManagement リソース
ms.openlocfilehash: f850c389214fe5adf139c3bd01fb60addc5ec238
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="dsc-packagemanagement-resource"></a><span data-ttu-id="4af7d-103">DSC の PackageManagement リソース</span><span class="sxs-lookup"><span data-stu-id="4af7d-103">DSC PackageManagement Resource</span></span>

> <span data-ttu-id="4af7d-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="4af7d-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="4af7d-105">Windows PowerShell Desired State Configuration (DSC) の **PackageManagement** リソースは、ターゲット ノードで Package Management パッケージをインストールまたはアンインストールするメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="4af7d-105">The **PackageManagement** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall Package Management packages on a target node.</span></span> <span data-ttu-id="4af7d-106">このリソースには **PackageManagement** モジュールが必要です。これは、http://PowerShellGallery.com から入手できます。</span><span class="sxs-lookup"><span data-stu-id="4af7d-106">This resource requires the **PackageManagement** module, available from http://PowerShellGallery.com.</span></span>

## <a name="syntax"></a><span data-ttu-id="4af7d-107">構文</span><span class="sxs-lookup"><span data-stu-id="4af7d-107">Syntax</span></span>

```
PackageManagement [string] #ResourceName
{
    Name = [string]
    [ Source = [string] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ RequiredVersion = [string] ]
    [ MinimumVersion = [string] ]
    [ MaximumVersion = [string] ]
    [ SourceCredential = [PSCredential] ]
    [ ProviderName = [string] ]
    [ AdditionalParameters = [Microsoft.Management.Infrastructure.CimInstance[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="4af7d-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4af7d-108">Properties</span></span>
|  <span data-ttu-id="4af7d-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4af7d-109">Property</span></span>  |  <span data-ttu-id="4af7d-110">説明</span><span class="sxs-lookup"><span data-stu-id="4af7d-110">Description</span></span>   |
|---|---|
| <span data-ttu-id="4af7d-111">名前</span><span class="sxs-lookup"><span data-stu-id="4af7d-111">Name</span></span>| <span data-ttu-id="4af7d-112">インストールまたはアンインストールするパッケージの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4af7d-112">Specifies the name of the Package to be installed or uninstalled.</span></span>|
| <span data-ttu-id="4af7d-113">ソース</span><span class="sxs-lookup"><span data-stu-id="4af7d-113">Source</span></span>| <span data-ttu-id="4af7d-114">パッケージのあるパッケージ ソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4af7d-114">Specifies the name of the package source where the package can be found.</span></span> <span data-ttu-id="4af7d-115">これは、URI、または Register-PackageSource または PackageManagementSource の DSC リソースに登録されたソースのどちらかになります。</span><span class="sxs-lookup"><span data-stu-id="4af7d-115">This can either be a URI or a source registered with Register-PackageSource or PackageManagementSource DSC resource.</span></span> <span data-ttu-id="4af7d-116">DSC リソース MSFT_PackageManagementSource にもパッケージ リソースを登録できます。</span><span class="sxs-lookup"><span data-stu-id="4af7d-116">The DSC resource MSFT_PackageManagementSource can also register a package source.</span></span>|
| <span data-ttu-id="4af7d-117">Ensure</span><span class="sxs-lookup"><span data-stu-id="4af7d-117">Ensure</span></span>| <span data-ttu-id="4af7d-118">パッケージをインストールまたはアンインストールするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="4af7d-118">Determines whether the package is to be installed or uninstalled.</span></span>|
| <span data-ttu-id="4af7d-119">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="4af7d-119">RequiredVersion</span></span>| <span data-ttu-id="4af7d-120">インストールするパッケージの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="4af7d-120">Specifies the exact version of the package that you want to install.</span></span> <span data-ttu-id="4af7d-121">このパラメーターを指定しない場合、MaximumVersion パラメーターで指定された最大バージョンも満たす、パッケージで利用可能な最新バージョンがこの DSC リソースによってインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4af7d-121">If you do not specify this parameter, this DSC resource installs the newest available version of the package that also satisfies any maximum version specified by the MaximumVersion parameter.</span></span>|
| <span data-ttu-id="4af7d-122">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="4af7d-122">MinimumVersion</span></span>| <span data-ttu-id="4af7d-123">インストールするパッケージで許容される最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="4af7d-123">Specifies the minimum allowed version of the package that you want to install.</span></span> <span data-ttu-id="4af7d-124">このパラメーターを追加しない場合、MaximumVersion パラメーターで指定された最大バージョンも満たす、パッケージで利用可能な最新バージョンがこの DSC リソースによってインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4af7d-124">If you do not add this parameter, this DSC resource intalls the highest available version of the package that also satisfies any maximum specified version specified by the MaximumVersion parameter.</span></span>|
| <span data-ttu-id="4af7d-125">MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="4af7d-125">MaximumVersion</span></span>| <span data-ttu-id="4af7d-126">インストールするパッケージで許容される最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="4af7d-126">Specifies the maximum allowed version of the package that you want to install.</span></span> <span data-ttu-id="4af7d-127">このパラメーターを指定しない場合、この DSC リソースではパッケージで利用可能な最も高い数字のバージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4af7d-127">If you do not specify this parameter, this DSC resource installs the highest-numbered available version of the package.</span></span>|
| <span data-ttu-id="4af7d-128">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="4af7d-128">SourceCredential</span></span> | <span data-ttu-id="4af7d-129">指定したパッケージ プロバイダーまたはソースのパッケージをインストールする権限を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="4af7d-129">Specifies a user account that has rights to install a package for a specified package provider or source.</span></span>|
| <span data-ttu-id="4af7d-130">ProviderName</span><span class="sxs-lookup"><span data-stu-id="4af7d-130">ProviderName</span></span>| <span data-ttu-id="4af7d-131">パッケージの検索先となるパッケージ プロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4af7d-131">Specifies a package provider name to which to scope your package search.</span></span> <span data-ttu-id="4af7d-132">Get-PackageProvider コマンドレットを実行して、パッケージ プロバイダー名を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4af7d-132">You can get package provider names by running the Get-PackageProvider cmdlet.</span></span>|
| <span data-ttu-id="4af7d-133">AdditionalParameters</span><span class="sxs-lookup"><span data-stu-id="4af7d-133">AdditionalParameters</span></span>| <span data-ttu-id="4af7d-134">ハッシュテーブルとして渡されるプロバイダー固有のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="4af7d-134">Provider specific parameters that are passed as an Hashtable.</span></span> <span data-ttu-id="4af7d-135">たとえば、NuGet プロバイダーでは DestinationPath のような追加のパラメーターを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="4af7d-135">For example, for NuGet provider you can pass additional parameters like DestinationPath.</span></span>|

## <a name="additional-parameters"></a><span data-ttu-id="4af7d-136">追加のパラメーター</span><span class="sxs-lookup"><span data-stu-id="4af7d-136">Additional Parameters</span></span>
<span data-ttu-id="4af7d-137">次の表は、AdditionalParameters プロパティのオプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="4af7d-137">The following table lists options for the AdditionalParameters property.</span></span>
|  <span data-ttu-id="4af7d-138">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4af7d-138">Parameter</span></span>  | <span data-ttu-id="4af7d-139">説明</span><span class="sxs-lookup"><span data-stu-id="4af7d-139">Description</span></span>   |
|---|---|
| <span data-ttu-id="4af7d-140">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="4af7d-140">DestinationPath</span></span>| <span data-ttu-id="4af7d-141">組み込みの Nuget プロバイダーなどのプロバイダーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="4af7d-141">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="4af7d-142">パッケージをインストールするファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="4af7d-142">Specifies a file location where you want the package to be installed.</span></span>|
| <span data-ttu-id="4af7d-143">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="4af7d-143">InstallationPolicy</span></span>| <span data-ttu-id="4af7d-144">組み込みの Nuget プロバイダーなどのプロバイダーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="4af7d-144">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="4af7d-145">パッケージのソースを信頼するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="4af7d-145">Determines whether you trust the package's source.</span></span> <span data-ttu-id="4af7d-146">"Untrusted" または "Trusted" のどちらかです。</span><span class="sxs-lookup"><span data-stu-id="4af7d-146">One of: "Untrusted", "Trusted".</span></span>|

## <a name="example"></a><span data-ttu-id="4af7d-147">例</span><span class="sxs-lookup"><span data-stu-id="4af7d-147">Example</span></span>

<span data-ttu-id="4af7d-148">この例では、**PackageManagement** DSC リソースを使用して、**JQuery** NuGet パッケージおよび **GistProvider** PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4af7d-148">This example installs the **JQuery** NuGet package and **GistProvider** PowerShell module using the **PackageManagement** DSC resource.</span></span> <span data-ttu-id="4af7d-149">この例では、最初に必要なパッケージのソースが利用できることを確認し、次に **JQuery** および **GistProvider** のパッケージ (それぞれ NuGet と PowerShell) の予期される状態を定義しています。</span><span class="sxs-lookup"><span data-stu-id="4af7d-149">This example first ensures the required package sources are available then defines the expected state of the **JQuery** and **GistProvider** packages (NuGet and PowerShell, respectively).</span></span>

```powershell
Configuration PackageTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceUri   = "http://nuget.org/api/v2/"
        InstallationPolicy ="Trusted"
    }

    PackageManagementSource PSGallery
    {
        Ensure      = "Present"
        Name        = "psgallery"
        ProviderName= "PowerShellGet"
        SourceUri   = "https://www.powershellgallery.com/api/v2/"
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