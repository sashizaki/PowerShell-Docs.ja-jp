---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/save-package?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Package
ms.openlocfilehash: 93ec8264bad588e38554daddcdf5dc9befce053e
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99603041"
---
# <span data-ttu-id="9d775-102">Save-Package</span><span class="sxs-lookup"><span data-stu-id="9d775-102">Save-Package</span></span>

## <span data-ttu-id="9d775-103">概要</span><span class="sxs-lookup"><span data-stu-id="9d775-103">SYNOPSIS</span></span>
<span data-ttu-id="9d775-104">パッケージをインストールせずにローカルコンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="9d775-104">Saves packages to the local computer without installing them.</span></span>

## <span data-ttu-id="9d775-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9d775-105">SYNTAX</span></span>

### <span data-ttu-id="9d775-106">PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="9d775-106">PackageBySearch</span></span>

```
Save-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Path <String>] [-LiteralPath <String>]
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllVersions]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="9d775-107">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="9d775-107">PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] -InputObject <SoftwareIdentity>
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllVersions]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9d775-108">NuGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="9d775-108">NuGet:PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>]
 [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="9d775-109">NuGet</span><span class="sxs-lookup"><span data-stu-id="9d775-109">NuGet</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>]
 [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="9d775-110">PowerShellGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="9d775-110">PowerShellGet:PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AllowPrereleaseVersions] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [<CommonParameters>]
```

### <span data-ttu-id="9d775-111">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="9d775-111">PowerShellGet</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AllowPrereleaseVersions] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [<CommonParameters>]
```

## <span data-ttu-id="9d775-112">Description</span><span class="sxs-lookup"><span data-stu-id="9d775-112">DESCRIPTION</span></span>

<span data-ttu-id="9d775-113">コマンドレットにより、 `Save-Package` パッケージはローカルコンピューターに保存されますが、パッケージはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="9d775-113">The `Save-Package` cmdlet saves packages to the local computer but doesn't install the packages.</span></span>
<span data-ttu-id="9d775-114">このコマンドレットは、 **requiredverion** を指定しない限り、最新バージョンのパッケージを保存します。</span><span class="sxs-lookup"><span data-stu-id="9d775-114">This cmdlet saves the newest version of a package unless you specify a **RequiredVerion**.</span></span> <span data-ttu-id="9d775-115">**Path** パラメーターと **LiteralPath** パラメーターは相互に排他的であり、同じコマンドに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="9d775-115">The **Path** and **LiteralPath** parameters are mutually exclusive, and cannot be added to the same command.</span></span>

## <span data-ttu-id="9d775-116">例</span><span class="sxs-lookup"><span data-stu-id="9d775-116">EXAMPLES</span></span>

### <span data-ttu-id="9d775-117">例 1: パッケージをローカルコンピューターに保存する</span><span class="sxs-lookup"><span data-stu-id="9d775-117">Example 1: Save a package to the local computer</span></span>

<span data-ttu-id="9d775-118">この例では、パッケージの最新バージョンをローカルコンピューター上のディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="9d775-118">This example saves the newest version of the package to a directory on the local computer.</span></span> <span data-ttu-id="9d775-119">パッケージの依存関係は、パッケージと共にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="9d775-119">The package's dependencies are download with the package.</span></span>

```
PS> Save-Package -Name NuGet.Core -ProviderName NuGet -Path C:\LocalPkg
```

```Output
Name                    Version    Source    Summary
----                    -------    ------    -------
Microsoft.Web.Xdt       3.0.0      Nuget     Microsoft Xml Document Transformation (XDT) enables...
NuGet.Core              2.14.0     Nuget     NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="9d775-120">`Save-Package`**Name** パラメーターを使用してパッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-120">`Save-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="9d775-121">パッケージは、 **ProviderName** パラメーターによって指定されたリポジトリからダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="9d775-121">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="9d775-122">**Path** パラメーターによって、パッケージの保存先が決まります。</span><span class="sxs-lookup"><span data-stu-id="9d775-122">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="9d775-123">例 2: 特定のパッケージバージョンを保存する</span><span class="sxs-lookup"><span data-stu-id="9d775-123">Example 2: Save a specific package version</span></span>

<span data-ttu-id="9d775-124">この例では、パッケージのバージョンを指定し、ローカルコンピューター上のディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="9d775-124">This example specifies the package version and saves it to a directory on the local computer.</span></span>

```
PS> Save-Package -Name NuGet.Core -RequiredVersion 2.9.0 -ProviderName NuGet -Path C:\LocalPkg
```

```Output
Name                    Version    Source    Summary
----                    -------    ------    -------
Microsoft.Web.Xdt       3.0.0      Nuget     Microsoft Xml Document Transformation (XDT) enables...
NuGet.Core              2.9.0      Nuget     NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="9d775-125">`Save-Package`**Name** パラメーターを使用してパッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-125">`Save-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="9d775-126">**RequiredVersion** 特定のパッケージのバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="9d775-126">**RequiredVersion** indicates a specific package version.</span></span> <span data-ttu-id="9d775-127">パッケージは、 **ProviderName** パラメーターによって指定されたリポジトリからダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="9d775-127">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="9d775-128">**Path** パラメーターによって、パッケージの保存先が決まります。</span><span class="sxs-lookup"><span data-stu-id="9d775-128">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="9d775-129">例 3: Find-Package を使用してパッケージを保存する</span><span class="sxs-lookup"><span data-stu-id="9d775-129">Example 3: Use Find-Package to save a package</span></span>

<span data-ttu-id="9d775-130">このコマンドは、を使用して `Find-Package` パッケージの最新バージョンを検索し、オブジェクトをに送信し `Save-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="9d775-130">This command uses `Find-Package` to locate the newest version of the package and sends the object to `Save-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -ProviderName NuGet | Save-Package -Path C:\LocalPkg
```

<span data-ttu-id="9d775-131">`Find-Package`**Name** パラメーターを使用してパッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-131">`Find-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="9d775-132">パッケージは、 **ProviderName** パラメーターによって指定されたリポジトリからダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="9d775-132">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="9d775-133">オブジェクトは、パイプライン内でに送信され `Save-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="9d775-133">The object is sent down the pipeline to `Save-Package`.</span></span> <span data-ttu-id="9d775-134">**Path** パラメーターによって、パッケージの保存先が決まります。</span><span class="sxs-lookup"><span data-stu-id="9d775-134">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="9d775-135">例 4: パッケージを保存してインストールする</span><span class="sxs-lookup"><span data-stu-id="9d775-135">Example 4: Save and install the package</span></span>

<span data-ttu-id="9d775-136">パッケージとその依存関係の最新バージョンがダウンロードされ、ローカルコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9d775-136">The newest version of the package and its dependencies are downloaded and installed on the local computer.</span></span>

```
PS> Save-Package -Name NuGet.Core -ProviderName NuGet -Path C:\LocalPkg
PS> Install-Package C:\LocalPkg\NuGet.Core.2.14.0.nupkg
```

<span data-ttu-id="9d775-137">`Save-Package` パッケージファイルとその依存関係をローカルコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9d775-137">`Save-Package` downloads the package file and its dependencies to the local computer.</span></span>
<span data-ttu-id="9d775-138">`Install-Package` 指定されたディレクトリからパッケージと依存関係をインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d775-138">`Install-Package` installs the package and dependencies from the specified directory.</span></span>

## <span data-ttu-id="9d775-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9d775-139">PARAMETERS</span></span>

### <span data-ttu-id="9d775-140">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="9d775-140">-AcceptLicense</span></span>

<span data-ttu-id="9d775-141">パッケージで必要な場合は、インストール中にライセンス契約に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="9d775-141">Automatically accept the license agreement during installation if the package requires it.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-142">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="9d775-142">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="9d775-143">プレリリースとしてマークされているパッケージを保存できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9d775-143">Allows packages marked as Prerelease to be saved.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet, PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-144">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="9d775-144">-AllVersions</span></span>

<span data-ttu-id="9d775-145">このコマンドレットが、使用可能なすべてのバージョンのパッケージを保存することを示します。</span><span class="sxs-lookup"><span data-stu-id="9d775-145">Indicates that this cmdlet saves all available versions of the package.</span></span>

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

### <span data-ttu-id="9d775-146">-Command</span><span class="sxs-lookup"><span data-stu-id="9d775-146">-Command</span></span>

<span data-ttu-id="9d775-147">パッケージに含まれる1つ以上のコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-147">Specifies one or more commands included in the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-148">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="9d775-148">-ConfigFile</span></span>

<span data-ttu-id="9d775-149">構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-149">Specifies a configuration File.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-150">-Contains</span><span class="sxs-lookup"><span data-stu-id="9d775-150">-Contains</span></span>

<span data-ttu-id="9d775-151">`Save-Package` オブジェクトのプロパティ値内のいずれかの項目が指定した値と完全に一致する場合は、オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="9d775-151">`Save-Package` gets objects if any item in the object's property values are an exact match for the specified value.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-152">-Credential</span><span class="sxs-lookup"><span data-stu-id="9d775-152">-Credential</span></span>

<span data-ttu-id="9d775-153">指定したパッケージプロバイダーまたはソースからパッケージを保存するためのアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-153">Specifies a user account that has permission to save a package from a specified package provider or source.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-154">-DscResource</span><span class="sxs-lookup"><span data-stu-id="9d775-154">-DscResource</span></span>

<span data-ttu-id="9d775-155">パッケージの Desired State Configuration (DSC) リソースを1つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-155">Specifies one or more Desired State Configuration (DSC) resources for the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-156">-Filter</span><span class="sxs-lookup"><span data-stu-id="9d775-156">-Filter</span></span>

<span data-ttu-id="9d775-157">パッケージのフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-157">Specifies a filter for the package.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-158">-FilterOnTag</span><span class="sxs-lookup"><span data-stu-id="9d775-158">-FilterOnTag</span></span>

<span data-ttu-id="9d775-159">結果をフィルター処理するタグを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-159">Specifies the tag that filters the results.</span></span> <span data-ttu-id="9d775-160">指定されたタグを含まない結果は除外されます。</span><span class="sxs-lookup"><span data-stu-id="9d775-160">Results that don't contain the specified tag are excluded.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-161">-Force</span><span class="sxs-lookup"><span data-stu-id="9d775-161">-Force</span></span>

<span data-ttu-id="9d775-162">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9d775-162">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="9d775-163">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="9d775-163">-ForceBootstrap</span></span>

<span data-ttu-id="9d775-164">が、 `Save-Package` 指定されたパッケージのパッケージプロバイダーを自動的にインストールすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-164">Indicates that `Save-Package` forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="9d775-165">-ヘッダー</span><span class="sxs-lookup"><span data-stu-id="9d775-165">-Headers</span></span>

<span data-ttu-id="9d775-166">パッケージのヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-166">Specifies the headers for the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-167">-インクルード</span><span class="sxs-lookup"><span data-stu-id="9d775-167">-Includes</span></span>

<span data-ttu-id="9d775-168">パッケージに含まれるリソースを示します。</span><span class="sxs-lookup"><span data-stu-id="9d775-168">Indicates the resources that the package includes.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:
Accepted values: DscResource, Cmdlet, Function, Workflow, RoleCapability

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-169">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9d775-169">-InputObject</span></span>

<span data-ttu-id="9d775-170">保存するパッケージを表すソフトウェア ID オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9d775-170">A software ID object that represents the package that you want to save.</span></span> <span data-ttu-id="9d775-171">ソフトウェア Id は、コマンドレットの結果の一部です `Find-Package` 。</span><span class="sxs-lookup"><span data-stu-id="9d775-171">Software IDs are part of the results of the `Find-Package` cmdlet.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.SoftwareIdentity
Parameter Sets: PackageByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-172">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9d775-172">-LiteralPath</span></span>

<span data-ttu-id="9d775-173">パッケージを保存するリテラルパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-173">Specifies the literal path to which you want to save the package.</span></span> <span data-ttu-id="9d775-174">このパラメーターと **Path** パラメーターの両方を同じコマンドに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="9d775-174">You cannot add both this parameter and the **Path** parameter to the same command.</span></span>

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

### <span data-ttu-id="9d775-175">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="9d775-175">-MaximumVersion</span></span>

<span data-ttu-id="9d775-176">保存するパッケージの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-176">Specifies the maximum version of the package that you want to save.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-177">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="9d775-177">-MinimumVersion</span></span>

<span data-ttu-id="9d775-178">検索するパッケージの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-178">Specifies the minimum version of the package that you want to find.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-179">-Name</span><span class="sxs-lookup"><span data-stu-id="9d775-179">-Name</span></span>

<span data-ttu-id="9d775-180">1つまたは複数のパッケージ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-180">Specifies one or more package names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-181">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="9d775-181">-PackageManagementProvider</span></span>

<span data-ttu-id="9d775-182">パッケージ管理プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-182">Specifies a package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-183">-Path</span><span class="sxs-lookup"><span data-stu-id="9d775-183">-Path</span></span>

<span data-ttu-id="9d775-184">パッケージを格納するローカルコンピューター上の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-184">Specifies the location on the local computer to store the package.</span></span>

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

### <span data-ttu-id="9d775-185">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="9d775-185">-ProviderName</span></span>

<span data-ttu-id="9d775-186">1つまたは複数のプロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-186">Specifies one or more provider names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-187">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="9d775-187">-Proxy</span></span>

<span data-ttu-id="9d775-188">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-188">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-189">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="9d775-189">-ProxyCredential</span></span>

<span data-ttu-id="9d775-190">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-190">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-191">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="9d775-191">-PublishLocation</span></span>

<span data-ttu-id="9d775-192">発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-192">Specifies the publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-193">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="9d775-193">-RequiredVersion</span></span>

<span data-ttu-id="9d775-194">保存するパッケージの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-194">Specifies the exact version of the package to save.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-195">-Find-rolecapability</span><span class="sxs-lookup"><span data-stu-id="9d775-195">-RoleCapability</span></span>

<span data-ttu-id="9d775-196">ロール機能の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-196">Specifies an array of role capabilities.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-197">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="9d775-197">-ScriptPublishLocation</span></span>

<span data-ttu-id="9d775-198">スクリプトの発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-198">Specifies the script publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-199">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="9d775-199">-ScriptSourceLocation</span></span>

<span data-ttu-id="9d775-200">スクリプトのソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-200">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-201">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="9d775-201">-SkipValidate</span></span>

<span data-ttu-id="9d775-202">パッケージの資格情報の検証をスキップするスイッチ。</span><span class="sxs-lookup"><span data-stu-id="9d775-202">Switch that skips validating the credentials of a package.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-203">-Source</span><span class="sxs-lookup"><span data-stu-id="9d775-203">-Source</span></span>

<span data-ttu-id="9d775-204">1つまたは複数のパッケージソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-204">Specifies one or more package sources.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-205">-Tag</span><span class="sxs-lookup"><span data-stu-id="9d775-205">-Tag</span></span>

<span data-ttu-id="9d775-206">パッケージメタデータ内で検索するタグを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-206">Specifies a tag to search for within the package metadata.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-207">-Type</span><span class="sxs-lookup"><span data-stu-id="9d775-207">-Type</span></span>

<span data-ttu-id="9d775-208">モジュール、スクリプト、またはいずれかを使用してパッケージを検索するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d775-208">Specifies whether to search for packages with a module, a script, or either.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-209">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9d775-209">-Confirm</span></span>

<span data-ttu-id="9d775-210">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d775-210">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-211">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9d775-211">-WhatIf</span></span>

<span data-ttu-id="9d775-212">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="9d775-212">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="9d775-213">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="9d775-213">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d775-214">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9d775-214">CommonParameters</span></span>

<span data-ttu-id="9d775-215">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="9d775-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9d775-216">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d775-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9d775-217">入力</span><span class="sxs-lookup"><span data-stu-id="9d775-217">INPUTS</span></span>

### <span data-ttu-id="9d775-218">`Save-Package` パイプラインからのオブジェクトを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9d775-218">`Save-Package` accepts objects from the pipeline.</span></span>

## <span data-ttu-id="9d775-219">出力</span><span class="sxs-lookup"><span data-stu-id="9d775-219">OUTPUTS</span></span>

### <span data-ttu-id="9d775-220">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="9d775-220">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9d775-221">注</span><span class="sxs-lookup"><span data-stu-id="9d775-221">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d775-222">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="9d775-222">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="9d775-223">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="9d775-223">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="9d775-224">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="9d775-224">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="9d775-225">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d775-225">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="9d775-226">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9d775-226">RELATED LINKS</span></span>

[<span data-ttu-id="9d775-227">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="9d775-227">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="9d775-228">Get-Package</span><span class="sxs-lookup"><span data-stu-id="9d775-228">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="9d775-229">Install-Package</span><span class="sxs-lookup"><span data-stu-id="9d775-229">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="9d775-230">Save-Package</span><span class="sxs-lookup"><span data-stu-id="9d775-230">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="9d775-231">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="9d775-231">Uninstall-Package</span></span>](Uninstall-Package.md)
