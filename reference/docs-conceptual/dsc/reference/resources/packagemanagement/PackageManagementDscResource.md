---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC の PackageManagement リソース
ms.openlocfilehash: dfc23bfabbc45041e15c56a29a77c5bdda430a30
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953239"
---
# <a name="dsc-packagemanagement-resource"></a><span data-ttu-id="e67d6-103">DSC の PackageManagement リソース</span><span class="sxs-lookup"><span data-stu-id="e67d6-103">DSC PackageManagement Resource</span></span>

<span data-ttu-id="e67d6-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0、Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="e67d6-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span></span>

<span data-ttu-id="e67d6-105">Windows PowerShell Desired State Configuration (DSC) の **PackageManagement** リソースは、ターゲット ノードで Package Management パッケージをインストールまたはアンインストールするメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="e67d6-105">The **PackageManagement** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall Package Management packages on a target node.</span></span> <span data-ttu-id="e67d6-106">このリソースには **PackageManagement** モジュールが必要です。これは、[http://PowerShellGallery.com](https://PowerShellGallery.com) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="e67d6-106">This resource requires the **PackageManagement** module, available from [http://PowerShellGallery.com](https://PowerShellGallery.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e67d6-107">**PackageManagement** モジュールは、次のプロパティ情報が適切であるようにバージョン 1.1.7.0 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e67d6-107">The **PackageManagement** module should be at least version 1.1.7.0 for the following property information to be correct.</span></span>

## <a name="syntax"></a><span data-ttu-id="e67d6-108">構文</span><span class="sxs-lookup"><span data-stu-id="e67d6-108">Syntax</span></span>

```Syntax
PackageManagement [string] #ResourceName
{
    Name = [string]
    [ AdditionalParameters = [HashTable] ]
    [ MaximumVersion = [string] ]
    [ MinimumVersion = [string] ]
    [ ProviderName = [string] ]
    [ RequiredVersion = [string] ]
    [ Source = [string] ]
    [ SourceCredential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string]{ Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="e67d6-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e67d6-109">Properties</span></span>

|<span data-ttu-id="e67d6-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e67d6-110">Property</span></span> |<span data-ttu-id="e67d6-111">説明</span><span class="sxs-lookup"><span data-stu-id="e67d6-111">Description</span></span> |
|---|---|
|<span data-ttu-id="e67d6-112">名前</span><span class="sxs-lookup"><span data-stu-id="e67d6-112">Name</span></span> |<span data-ttu-id="e67d6-113">インストールまたはアンインストールするパッケージの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e67d6-113">Specifies the name of the Package to be installed or uninstalled.</span></span> |
|<span data-ttu-id="e67d6-114">AdditionalParameters</span><span class="sxs-lookup"><span data-stu-id="e67d6-114">AdditionalParameters</span></span> |<span data-ttu-id="e67d6-115">`Get-Package -AdditionalArguments` に渡されるパラメーターのプロバイダー固有のハッシュ テーブル。</span><span class="sxs-lookup"><span data-stu-id="e67d6-115">Provider specific hashtable of parameters that would be passed to `Get-Package -AdditionalArguments`.</span></span> <span data-ttu-id="e67d6-116">たとえば、NuGet プロバイダーでは DestinationPath のような追加のパラメーターを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="e67d6-116">For example, for NuGet provider you can pass additional parameters like DestinationPath.</span></span> |
|<span data-ttu-id="e67d6-117">MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="e67d6-117">MaximumVersion</span></span> |<span data-ttu-id="e67d6-118">検索するパッケージで許容される最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e67d6-118">Specifies the maximum allowed version of the package that you want to find.</span></span> <span data-ttu-id="e67d6-119">このパラメーターを追加しない場合、リソースでは利用できるパッケージの最新バージョンが検索されます。</span><span class="sxs-lookup"><span data-stu-id="e67d6-119">If you do not add this parameter, the resource finds the highest available version of the package.</span></span> |
|<span data-ttu-id="e67d6-120">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="e67d6-120">MinimumVersion</span></span> |<span data-ttu-id="e67d6-121">検索するパッケージで許容される最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e67d6-121">Specifies the minimum allowed version of the package that you want to find.</span></span> <span data-ttu-id="e67d6-122">このパラメーターを追加しない場合、**MaximumVersion** パラメーターで指定された最大バージョンも満たす、パッケージで利用可能な最新バージョンがリソースによって検索されます。</span><span class="sxs-lookup"><span data-stu-id="e67d6-122">If you do not add this parameter, the resource finds the highest available version of the package that also satisfies any maximum specified version specified by the **MaximumVersion** parameter.</span></span> |
|<span data-ttu-id="e67d6-123">ProviderName</span><span class="sxs-lookup"><span data-stu-id="e67d6-123">ProviderName</span></span> |<span data-ttu-id="e67d6-124">パッケージの検索先となるパッケージ プロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e67d6-124">Specifies a package provider name to which to scope your package search.</span></span> <span data-ttu-id="e67d6-125">`Get-PackageProvider` コマンドレットを実行して、パッケージ プロバイダー名を取得できます。</span><span class="sxs-lookup"><span data-stu-id="e67d6-125">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span> |
|<span data-ttu-id="e67d6-126">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="e67d6-126">RequiredVersion</span></span> |<span data-ttu-id="e67d6-127">インストールするパッケージの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e67d6-127">Specifies the exact version of the package that you want to install.</span></span> <span data-ttu-id="e67d6-128">このパラメーターを指定しない場合、**MaximumVersion** パラメーターで指定された最大バージョンも満たす、パッケージで利用可能な最新バージョンがこの DSC リソースによってインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e67d6-128">If you do not specify this parameter, this DSC resource installs the newest available version of the package that also satisfies any maximum version specified by the **MaximumVersion** parameter.</span></span> |
|<span data-ttu-id="e67d6-129">ソース</span><span class="sxs-lookup"><span data-stu-id="e67d6-129">Source</span></span> |<span data-ttu-id="e67d6-130">パッケージのあるパッケージ ソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e67d6-130">Specifies the name of the package source where the package can be found.</span></span> <span data-ttu-id="e67d6-131">これは、URI か、`Register-PackageSource` または PackageManagementSource の DSC リソースに登録されたソースのどちらかになります。</span><span class="sxs-lookup"><span data-stu-id="e67d6-131">This can either be a URI or a source registered with `Register-PackageSource` or PackageManagementSource DSC resource.</span></span> |
|<span data-ttu-id="e67d6-132">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="e67d6-132">SourceCredential</span></span> |<span data-ttu-id="e67d6-133">指定したパッケージ プロバイダーまたはソースのパッケージをインストールする権限を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e67d6-133">Specifies a user account that has rights to install a package for a specified package provider or source.</span></span> |

## <a name="additional-parameters"></a><span data-ttu-id="e67d6-134">追加のパラメーター</span><span class="sxs-lookup"><span data-stu-id="e67d6-134">Additional Parameters</span></span>

<span data-ttu-id="e67d6-135">次の表は、AdditionalParameters プロパティのオプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="e67d6-135">The following table lists options for the AdditionalParameters property.</span></span>

|<span data-ttu-id="e67d6-136">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e67d6-136">Parameter</span></span> |<span data-ttu-id="e67d6-137">説明</span><span class="sxs-lookup"><span data-stu-id="e67d6-137">Description</span></span> |
|---|---|
|<span data-ttu-id="e67d6-138">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="e67d6-138">DestinationPath</span></span> |<span data-ttu-id="e67d6-139">組み込みの Nuget プロバイダーなどのプロバイダーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="e67d6-139">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="e67d6-140">パッケージをインストールするファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="e67d6-140">Specifies a file location where you want the package to be installed.</span></span> |
|<span data-ttu-id="e67d6-141">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="e67d6-141">InstallationPolicy</span></span> |<span data-ttu-id="e67d6-142">組み込みの Nuget プロバイダーなどのプロバイダーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="e67d6-142">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="e67d6-143">パッケージのソースを信頼するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e67d6-143">Determines whether you trust the package's source.</span></span> <span data-ttu-id="e67d6-144">つぎのいずれかです。**Untrusted** または **Trusted**。</span><span class="sxs-lookup"><span data-stu-id="e67d6-144">One of: **Untrusted** or **Trusted**.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="e67d6-145">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="e67d6-145">Common properties</span></span>

|<span data-ttu-id="e67d6-146">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e67d6-146">Property</span></span> |<span data-ttu-id="e67d6-147">説明</span><span class="sxs-lookup"><span data-stu-id="e67d6-147">Description</span></span> |
|---|---|
|<span data-ttu-id="e67d6-148">DependsOn</span><span class="sxs-lookup"><span data-stu-id="e67d6-148">DependsOn</span></span> |<span data-ttu-id="e67d6-149">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="e67d6-149">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="e67d6-150">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="e67d6-150">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="e67d6-151">Ensure</span><span class="sxs-lookup"><span data-stu-id="e67d6-151">Ensure</span></span> |<span data-ttu-id="e67d6-152">パッケージをインストールまたはアンインストールするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e67d6-152">Determines whether the package is to be installed or uninstalled.</span></span> <span data-ttu-id="e67d6-153">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="e67d6-153">The default value is **Present**.</span></span> |
|<span data-ttu-id="e67d6-154">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="e67d6-154">PsDscRunAsCredential</span></span> |<span data-ttu-id="e67d6-155">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="e67d6-155">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="e67d6-156">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="e67d6-156">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="e67d6-157">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e67d6-157">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="e67d6-158">例</span><span class="sxs-lookup"><span data-stu-id="e67d6-158">Example</span></span>

<span data-ttu-id="e67d6-159">この例では、**PackageManagement** DSC リソースを使用して、**JQuery** NuGet パッケージおよび **GistProvider** PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e67d6-159">This example installs the **JQuery** NuGet package and **GistProvider** PowerShell module using the **PackageManagement** DSC resource.</span></span> <span data-ttu-id="e67d6-160">この例では、最初に必要なパッケージのソースが利用できることを確認し、次に **JQuery** および **GistProvider** のパッケージ (それぞれ NuGet と PowerShell) の予期される状態を定義しています。</span><span class="sxs-lookup"><span data-stu-id="e67d6-160">This example first ensures the required package sources are available then defines the expected state of the **JQuery** and **GistProvider** packages (NuGet and PowerShell, respectively).</span></span>

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
        SourceLocation   = "https://www.powershellgallery.com/api/v2"
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