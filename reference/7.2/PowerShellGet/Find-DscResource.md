---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/04/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-dscresource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-DscResource
ms.openlocfilehash: e1cb814d349d6b77885ebaaf176a7c3153d93eb5
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99601397"
---
# <span data-ttu-id="3dbc8-102">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="3dbc8-102">Find-DscResource</span></span>

## <span data-ttu-id="3dbc8-103">概要</span><span class="sxs-lookup"><span data-stu-id="3dbc8-103">SYNOPSIS</span></span>
<span data-ttu-id="3dbc8-104">Desired State Configuration (DSC) リソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-104">Finds Desired State Configuration (DSC) resources.</span></span>

## <span data-ttu-id="3dbc8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3dbc8-105">SYNTAX</span></span>

### <span data-ttu-id="3dbc8-106">すべて</span><span class="sxs-lookup"><span data-stu-id="3dbc8-106">All</span></span>

```
Find-DscResource [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
 [-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="3dbc8-107">Description</span><span class="sxs-lookup"><span data-stu-id="3dbc8-107">DESCRIPTION</span></span>

<span data-ttu-id="3dbc8-108">`Find-DscResource`コマンドレットは、登録されているリポジトリを検索して、モジュールに含まれる DSC リソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-108">The `Find-DscResource` cmdlet searches registered repositories to find DSC resources contained in modules.</span></span> <span data-ttu-id="3dbc8-109">既定では、 `Find-DscResource` すべての登録済みリポジトリが検索されます。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-109">By default `Find-DscResource` searches all registered repositories.</span></span>

<span data-ttu-id="3dbc8-110">によって検出されたモジュールごとに `Find-DscResource` 、 **Psgetdscresourceinfo** オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-110">For each module found by `Find-DscResource`, a **PSGetDscResourceInfo** object is returned.</span></span>
<span data-ttu-id="3dbc8-111">**Psgetdscresourceinfo** オブジェクトは、パイプラインを使用してコマンドレットに送信でき `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-111">**PSGetDscResourceInfo** objects can be sent down the pipeline to the `Install-Module` cmdlet.</span></span>
<span data-ttu-id="3dbc8-112">`Install-Module` モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-112">`Install-Module` installs the module.</span></span>

## <span data-ttu-id="3dbc8-113">例</span><span class="sxs-lookup"><span data-stu-id="3dbc8-113">EXAMPLES</span></span>

### <span data-ttu-id="3dbc8-114">例 1: すべての DSC リソースを検索する</span><span class="sxs-lookup"><span data-stu-id="3dbc8-114">Example 1: Find all DSC resources</span></span>

<span data-ttu-id="3dbc8-115">`Find-DscResource` 登録されているリポジトリから DSC リソースを返します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-115">`Find-DscResource` returns DSC resources from registered repositories.</span></span> <span data-ttu-id="3dbc8-116">特定のリポジトリを検索するには、 **repository** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-116">To search a specific repository, use the **Repository** parameter.</span></span>

```powershell
Find-DscResource
```

```Output
Name                           Version    ModuleName                     Repository
----                           -------    ----------                     ----------
Carbon_Privilege               2.8.1      Carbon                         PSGallery
Carbon_ScheduledTask           2.8.1      Carbon                         PSGallery
Carbon_Service                 2.8.1      Carbon                         PSGallery
PackageManagement              1.4        PackageManagement              PSGallery
PackageManagementSource        1.4        PackageManagement              PSGallery
PSModule                       2.1.4      PowerShellGet                  PSGallery
PSRepository                   2.1.4      PowerShellGet                  PSGallery
xArchive                       8.7.0.0    xPSDesiredStateConfiguration   PSGallery
xDSCWebService                 8.7.0.0    xPSDesiredStateConfiguration   PSGallery
xEnvironment                   8.7.0.0    xPSDesiredStateConfiguration   PSGallery
```

### <span data-ttu-id="3dbc8-117">例 2: 名前を指定して DSC リソースを検索する</span><span class="sxs-lookup"><span data-stu-id="3dbc8-117">Example 2: Find a DSC resource by name</span></span>

<span data-ttu-id="3dbc8-118">`Find-DscResource` 名前を指定して DSC リソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-118">`Find-DscResource` locates DSC resources by name.</span></span> <span data-ttu-id="3dbc8-119">リソース名の配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-119">Use commas to separate an array of resource names.</span></span>

```powershell
Find-DscResource -Name xWebsite, xWebApplication, xWebSiteDefaults
```

```Output
Name               Version    ModuleName            Repository
----               -------    ----------            ----------
xWebApplication    2.6.0.0    xWebAdministration    PSGallery
xWebsite           2.6.0.0    xWebAdministration    PSGallery
xWebSiteDefaults   2.6.0.0    xWebAdministration    PSGallery
```

<span data-ttu-id="3dbc8-120">`Find-DscResource`**Name** パラメーターを使用して、指定された DSC リソースの配列を検索します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-120">`Find-DscResource` uses the **Name** parameter to find the specified array of DSC resources.</span></span>

### <span data-ttu-id="3dbc8-121">例 3: DSC リソースを検索してインストールする</span><span class="sxs-lookup"><span data-stu-id="3dbc8-121">Example 3: Find a DSC resource and install it</span></span>

<span data-ttu-id="3dbc8-122">`Find-DscResource` DSC リソースを検索し、インストールするパイプラインの下にオブジェクトを送信します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-122">`Find-DscResource` locates a DSC resource and sends the object down the pipeline to be installed.</span></span>
<span data-ttu-id="3dbc8-123">インストール後、を使用し `Get-InstalledModule` て結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-123">After the installation, use `Get-InstalledModule` to view the results.</span></span>

<span data-ttu-id="3dbc8-124">同じモジュールの複数のリソースをパイプラインからに送信でき `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-124">Multiple resources from the same module can be sent down the pipeline to the `Install-Module`.</span></span>
<span data-ttu-id="3dbc8-125">`Install-Module` モジュールのインストールを1回だけ試行します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-125">`Install-Module` attempts to only install the module once.</span></span>

```powershell
Find-DscResource -Name xWebsite | Install-Module
```

<span data-ttu-id="3dbc8-126">`Find-DscResource`**Name** パラメーターを使用して、 **xwebsite** という名前のリソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-126">`Find-DscResource` uses the **Name** parameter to find the resource named **xWebsite**.</span></span> <span data-ttu-id="3dbc8-127">オブジェクトは、パイプラインを介してコマンドレットに送信され `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-127">The object is sent down the pipeline to the `Install-Module` cmdlet.</span></span> <span data-ttu-id="3dbc8-128">`Install-Module` リソースの **Xwebadministration** モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-128">`Install-Module` installs the **xWebAdministration** module for the resource.</span></span>

### <span data-ttu-id="3dbc8-129">例 4: モジュール内のすべての DSC リソースを検索する</span><span class="sxs-lookup"><span data-stu-id="3dbc8-129">Example 4: Find all DSC resources in a module</span></span>

<span data-ttu-id="3dbc8-130">`Find-DscResource` 指定されたモジュールに含まれるすべての DSC リソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-130">`Find-DscResource` finds all the DSC resources contained in a specified module.</span></span> <span data-ttu-id="3dbc8-131">既定では、現在のバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-131">By default, the current version is displayed.</span></span> <span data-ttu-id="3dbc8-132">他のバージョンを表示するには、 **AllVersions** または **requiredversions** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-132">To display other versions, use the **AllVersions** or **RequiredVersions** parameters.</span></span>

```powershell
Find-DscResource -ModuleName xWebAdministration
```

```Output
Name                                Version    ModuleName              Repository
----                                -------    ----------              ----------
WebApplicationHandler               2.6.0.0    xWebAdministration      PSGallery
xIisFeatureDelegation               2.6.0.0    xWebAdministration      PSGallery
xIisHandler                         2.6.0.0    xWebAdministration      PSGallery
xIisLogging                         2.6.0.0    xWebAdministration      PSGallery
```

<span data-ttu-id="3dbc8-133">`Find-DscResource`**ModuleName** パラメーターを使用して **xwebadministration** を指定し、モジュールに含まれる DSC リソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-133">`Find-DscResource` uses the **ModuleName** parameter to specify the **xWebAdministration** and find the DSC resources contained in the module.</span></span> <span data-ttu-id="3dbc8-134">各リソースの現在のバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-134">The current version of each resource is displayed.</span></span>

### <span data-ttu-id="3dbc8-135">例 5: タグおよび必要なバージョンで DSC リソースを検索する</span><span class="sxs-lookup"><span data-stu-id="3dbc8-135">Example 5: Find a DSC resource by tag and required version</span></span>

<span data-ttu-id="3dbc8-136">DSC リソースは、parameters **タグ** および **RequiredVersion** を使用して見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-136">DSC resources can be located using the parameters **Tag** and **RequiredVersion**.</span></span> <span data-ttu-id="3dbc8-137">**タグ** は、リポジトリ内の指定されたタグを含むすべてのリソースの現在のバージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-137">**Tag** displays the current version of every resource that contains the specified tag in the repository.</span></span>
<span data-ttu-id="3dbc8-138">**RequiredVersion** には **ModuleName** パラメーターが必要であり、 **Name** パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-138">**RequiredVersion** needs the **ModuleName** parameter and the **Name** parameter is optional.</span></span> <span data-ttu-id="3dbc8-139">**Name** パラメーターと **ModuleName** パラメーターは、出力を制限します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-139">The **Name** and **ModuleName** parameters limit the output.</span></span> <span data-ttu-id="3dbc8-140">DSC リソースの使用可能なバージョンを表示するには、 **AllVersions** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-140">Use the **AllVersions** parameter to display a DSC resource's available versions.</span></span>

```powershell
Find-DscResource -ModuleName xWebAdministration -Tag DSC -RequiredVersion 1.20
```

```output
Name                    Version    ModuleName             Repository
----                    -------    ----------             ----------
xIisFeatureDelegation   1.20.0.0   xWebAdministration     PSGallery
xIisHandler             1.20.0.0   xWebAdministration     PSGallery
xIisLogging             1.20.0.0   xWebAdministration     PSGallery
xIisMimeTypeMapping     1.20.0.0   xWebAdministration     PSGallery
```

### <span data-ttu-id="3dbc8-141">例 6: フィルターを使用してリソースを検索する</span><span class="sxs-lookup"><span data-stu-id="3dbc8-141">Example 6: Find a resource by using a filter</span></span>

<span data-ttu-id="3dbc8-142">`Find-DscResource` すべてのリソースを検索し、 **Filter** パラメーターを使用して結果を **ドメイン** 別に指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-142">`Find-DscResource` finds all resources and uses the **Filter** parameter to specify the results by **Domain**.</span></span> <span data-ttu-id="3dbc8-143">**Filter** パラメーターを指定すると、オブジェクトの説明またはモジュール名のフィルター値が検索されます。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-143">The **Filter** parameter finds the filter value in the object's description or module name.</span></span> <span data-ttu-id="3dbc8-144">`Select-Object`オブジェクトのプロパティを表示するには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-144">Use the `Select-Object` cmdlet to view an object's properties.</span></span>

```powershell
Find-DscResource -Filter Domain
```

```output
Name                    Version    ModuleName                 Repository
----                    -------    ----------                 ---------
xComputer               4.1.0.0    xComputerManagement        PSGallery
Computer                6.4.0.0    ComputerManagementDsc      PSGallery
xDSCDomainjoin          1.1        xDSCDomainjoin             PSGallery
xDisk                   1.0        xDisk                      PSGallery
xDSCFirewall            1.6.21     xDSCFirewall               PSGallery
dmAwsTagInstance        1.0.1      domainAwsDSCResources      PSGallery
```

## <span data-ttu-id="3dbc8-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3dbc8-145">PARAMETERS</span></span>

### <span data-ttu-id="3dbc8-146">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="3dbc8-146">-AllowPrerelease</span></span>

<span data-ttu-id="3dbc8-147">結果にプレリリースとしてマークされたリソースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-147">Includes resources marked as a prerelease in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbc8-148">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="3dbc8-148">-AllVersions</span></span>

<span data-ttu-id="3dbc8-149">**AllVersions** パラメーターには、DSC リソースの使用可能なバージョンがそれぞれ表示されます。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-149">The **AllVersions** parameter displays each of a DSC resource's available versions.</span></span> <span data-ttu-id="3dbc8-150">**AllVersions** パラメーターは、 **MinimumVersion**、 **MaximumVersion**、または **RequiredVersion** パラメーターと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-150">You can't use the **AllVersions** parameter with the **MinimumVersion**, **MaximumVersion**, or **RequiredVersion** parameters.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbc8-151">-Filter</span><span class="sxs-lookup"><span data-stu-id="3dbc8-151">-Filter</span></span>

<span data-ttu-id="3dbc8-152">**PackageManagement** プロバイダーの検索構文に基づいてリソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-152">Finds resources based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="3dbc8-153">たとえば、 **ModuleName** プロパティと **Description** プロパティ内で検索する単語を指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-153">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbc8-154">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="3dbc8-154">-MaximumVersion</span></span>

<span data-ttu-id="3dbc8-155">結果に含めるリソースの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-155">Specifies the maximum version of the resource to include in results.</span></span> <span data-ttu-id="3dbc8-156">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-156">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbc8-157">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="3dbc8-157">-MinimumVersion</span></span>

<span data-ttu-id="3dbc8-158">結果に含めるリソースの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-158">Specifies the minimum version of the resource to include in results.</span></span> <span data-ttu-id="3dbc8-159">**MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-159">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbc8-160">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="3dbc8-160">-ModuleName</span></span>

<span data-ttu-id="3dbc8-161">DSC リソースを含むモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-161">Specifies a module that contains the DSC resource.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbc8-162">-Name</span><span class="sxs-lookup"><span data-stu-id="3dbc8-162">-Name</span></span>

<span data-ttu-id="3dbc8-163">リソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-163">Specifies the name of a resource.</span></span> <span data-ttu-id="3dbc8-164">既定値はすべてのリソースです。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-164">The default is all resources.</span></span> <span data-ttu-id="3dbc8-165">リソース名の配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-165">Use commas to separate an array of resource names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbc8-166">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="3dbc8-166">-Proxy</span></span>

<span data-ttu-id="3dbc8-167">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-167">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3dbc8-168">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="3dbc8-168">-ProxyCredential</span></span>

<span data-ttu-id="3dbc8-169">**プロキシ** パラメーターで指定されたプロキシサーバーを使用するためのアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-169">Specifies a user account with permission to use the proxy server specified in the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3dbc8-170">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="3dbc8-170">-Repository</span></span>

<span data-ttu-id="3dbc8-171">リソースを検索するリポジトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-171">Specifies a repository to search for resources.</span></span> <span data-ttu-id="3dbc8-172">リポジトリ名の配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-172">Use commas to separate an array of repository names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbc8-173">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="3dbc8-173">-RequiredVersion</span></span>

<span data-ttu-id="3dbc8-174">結果に含めるモジュールの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-174">Specifies the module's exact version number to include in the results.</span></span> <span data-ttu-id="3dbc8-175">**RequiredVersion** パラメーターと **MinimumVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-175">The **RequiredVersion** and the **MinimumVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbc8-176">-Tag</span><span class="sxs-lookup"><span data-stu-id="3dbc8-176">-Tag</span></span>

<span data-ttu-id="3dbc8-177">リポジトリ内のモジュールを分類するタグを指定します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-177">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="3dbc8-178">タグの配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-178">Use commas to separate an array of tags.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dbc8-179">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="3dbc8-179">CommonParameters</span></span>

<span data-ttu-id="3dbc8-180">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-180">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3dbc8-181">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-181">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3dbc8-182">入力</span><span class="sxs-lookup"><span data-stu-id="3dbc8-182">INPUTS</span></span>

## <span data-ttu-id="3dbc8-183">出力</span><span class="sxs-lookup"><span data-stu-id="3dbc8-183">OUTPUTS</span></span>

### <span data-ttu-id="3dbc8-184">PSGetDscResourceInfo</span><span class="sxs-lookup"><span data-stu-id="3dbc8-184">PSGetDscResourceInfo</span></span>

<span data-ttu-id="3dbc8-185">`Find-DscResource`**Psgetdscresourceinfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-185">`Find-DscResource` returns a **PSGetDscResourceInfo** object.</span></span>

## <span data-ttu-id="3dbc8-186">注</span><span class="sxs-lookup"><span data-stu-id="3dbc8-186">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3dbc8-187">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-187">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="3dbc8-188">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-188">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="3dbc8-189">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-189">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="3dbc8-190">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3dbc8-190">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="3dbc8-191">関連リンク</span><span class="sxs-lookup"><span data-stu-id="3dbc8-191">RELATED LINKS</span></span>

[<span data-ttu-id="3dbc8-192">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="3dbc8-192">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="3dbc8-193">Install-Module</span><span class="sxs-lookup"><span data-stu-id="3dbc8-193">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="3dbc8-194">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="3dbc8-194">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="3dbc8-195">Select-Object</span><span class="sxs-lookup"><span data-stu-id="3dbc8-195">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="3dbc8-196">アンインストール-モジュール</span><span class="sxs-lookup"><span data-stu-id="3dbc8-196">Uninstall-Module</span></span>](Uninstall-Module.md)
