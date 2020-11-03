---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/save-package?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Package
ms.openlocfilehash: 97ba55f4185d784e4b32bbe669296d44989f72d2
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210424"
---
# <span data-ttu-id="43f33-103">Save-Package</span><span class="sxs-lookup"><span data-stu-id="43f33-103">Save-Package</span></span>

## <span data-ttu-id="43f33-104">概要</span><span class="sxs-lookup"><span data-stu-id="43f33-104">SYNOPSIS</span></span>
<span data-ttu-id="43f33-105">パッケージをインストールせずにローカルコンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="43f33-105">Saves packages to the local computer without installing them.</span></span>

## <span data-ttu-id="43f33-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="43f33-106">SYNTAX</span></span>

### <span data-ttu-id="43f33-107">PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="43f33-107">PackageBySearch</span></span>

```
Save-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Path <String>] [-LiteralPath <String>]
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllVersions]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="43f33-108">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="43f33-108">PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] -InputObject <SoftwareIdentity>
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllVersions]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="43f33-109">NuGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="43f33-109">NuGet:PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>]
 [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="43f33-110">NuGet</span><span class="sxs-lookup"><span data-stu-id="43f33-110">NuGet</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>]
 [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="43f33-111">PowerShellGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="43f33-111">PowerShellGet:PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AllowPrereleaseVersions] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [<CommonParameters>]
```

### <span data-ttu-id="43f33-112">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="43f33-112">PowerShellGet</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AllowPrereleaseVersions] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [<CommonParameters>]
```

## <span data-ttu-id="43f33-113">Description</span><span class="sxs-lookup"><span data-stu-id="43f33-113">DESCRIPTION</span></span>

<span data-ttu-id="43f33-114">コマンドレットにより、 `Save-Package` パッケージはローカルコンピューターに保存されますが、パッケージはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="43f33-114">The `Save-Package` cmdlet saves packages to the local computer but doesn't install the packages.</span></span>
<span data-ttu-id="43f33-115">このコマンドレットは、 **requiredverion** を指定しない限り、最新バージョンのパッケージを保存します。</span><span class="sxs-lookup"><span data-stu-id="43f33-115">This cmdlet saves the newest version of a package unless you specify a **RequiredVerion** .</span></span> <span data-ttu-id="43f33-116">**Path** パラメーターと **LiteralPath** パラメーターは相互に排他的であり、同じコマンドに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="43f33-116">The **Path** and **LiteralPath** parameters are mutually exclusive, and cannot be added to the same command.</span></span>

## <span data-ttu-id="43f33-117">例</span><span class="sxs-lookup"><span data-stu-id="43f33-117">EXAMPLES</span></span>

### <span data-ttu-id="43f33-118">例 1: パッケージをローカルコンピューターに保存する</span><span class="sxs-lookup"><span data-stu-id="43f33-118">Example 1: Save a package to the local computer</span></span>

<span data-ttu-id="43f33-119">この例では、パッケージの最新バージョンをローカルコンピューター上のディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="43f33-119">This example saves the newest version of the package to a directory on the local computer.</span></span> <span data-ttu-id="43f33-120">パッケージの依存関係は、パッケージと共にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="43f33-120">The package's dependencies are download with the package.</span></span>

```
PS> Save-Package -Name NuGet.Core -ProviderName NuGet -Path C:\LocalPkg
```

```Output
Name                    Version    Source    Summary
----                    -------    ------    -------
Microsoft.Web.Xdt       3.0.0      Nuget     Microsoft Xml Document Transformation (XDT) enables...
NuGet.Core              2.14.0     Nuget     NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="43f33-121">`Save-Package`**Name** パラメーターを使用してパッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-121">`Save-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="43f33-122">パッケージは、 **ProviderName** パラメーターによって指定されたリポジトリからダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="43f33-122">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="43f33-123">**Path** パラメーターによって、パッケージの保存先が決まります。</span><span class="sxs-lookup"><span data-stu-id="43f33-123">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="43f33-124">例 2: 特定のパッケージバージョンを保存する</span><span class="sxs-lookup"><span data-stu-id="43f33-124">Example 2: Save a specific package version</span></span>

<span data-ttu-id="43f33-125">この例では、パッケージのバージョンを指定し、ローカルコンピューター上のディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="43f33-125">This example specifies the package version and saves it to a directory on the local computer.</span></span>

```
PS> Save-Package -Name NuGet.Core -RequiredVersion 2.9.0 -ProviderName NuGet -Path C:\LocalPkg
```

```Output
Name                    Version    Source    Summary
----                    -------    ------    -------
Microsoft.Web.Xdt       3.0.0      Nuget     Microsoft Xml Document Transformation (XDT) enables...
NuGet.Core              2.9.0      Nuget     NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="43f33-126">`Save-Package`**Name** パラメーターを使用してパッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-126">`Save-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="43f33-127">**RequiredVersion** 特定のパッケージのバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="43f33-127">**RequiredVersion** indicates a specific package version.</span></span> <span data-ttu-id="43f33-128">パッケージは、 **ProviderName** パラメーターによって指定されたリポジトリからダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="43f33-128">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="43f33-129">**Path** パラメーターによって、パッケージの保存先が決まります。</span><span class="sxs-lookup"><span data-stu-id="43f33-129">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="43f33-130">例 3: Find-Package を使用してパッケージを保存する</span><span class="sxs-lookup"><span data-stu-id="43f33-130">Example 3: Use Find-Package to save a package</span></span>

<span data-ttu-id="43f33-131">このコマンドは、を使用して `Find-Package` パッケージの最新バージョンを検索し、オブジェクトをに送信し `Save-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="43f33-131">This command uses `Find-Package` to locate the newest version of the package and sends the object to `Save-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -ProviderName NuGet | Save-Package -Path C:\LocalPkg
```

<span data-ttu-id="43f33-132">`Find-Package`**Name** パラメーターを使用してパッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-132">`Find-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="43f33-133">パッケージは、 **ProviderName** パラメーターによって指定されたリポジトリからダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="43f33-133">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="43f33-134">オブジェクトは、パイプライン内でに送信され `Save-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="43f33-134">The object is sent down the pipeline to `Save-Package`.</span></span> <span data-ttu-id="43f33-135">**Path** パラメーターによって、パッケージの保存先が決まります。</span><span class="sxs-lookup"><span data-stu-id="43f33-135">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="43f33-136">例 4: パッケージを保存してインストールする</span><span class="sxs-lookup"><span data-stu-id="43f33-136">Example 4: Save and install the package</span></span>

<span data-ttu-id="43f33-137">パッケージとその依存関係の最新バージョンがダウンロードされ、ローカルコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="43f33-137">The newest version of the package and its dependencies are downloaded and installed on the local computer.</span></span>

```
PS> Save-Package -Name NuGet.Core -ProviderName NuGet -Path C:\LocalPkg
PS> Install-Package C:\LocalPkg\NuGet.Core.2.14.0.nupkg
```

<span data-ttu-id="43f33-138">`Save-Package` パッケージファイルとその依存関係をローカルコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="43f33-138">`Save-Package` downloads the package file and its dependencies to the local computer.</span></span>
<span data-ttu-id="43f33-139">`Install-Package` 指定されたディレクトリからパッケージと依存関係をインストールします。</span><span class="sxs-lookup"><span data-stu-id="43f33-139">`Install-Package` installs the package and dependencies from the specified directory.</span></span>

## <span data-ttu-id="43f33-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="43f33-140">PARAMETERS</span></span>

### <span data-ttu-id="43f33-141">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="43f33-141">-AcceptLicense</span></span>

<span data-ttu-id="43f33-142">パッケージで必要な場合は、インストール中にライセンス契約に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="43f33-142">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="43f33-143">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="43f33-143">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="43f33-144">プレリリースとしてマークされているパッケージを保存できるようにします。</span><span class="sxs-lookup"><span data-stu-id="43f33-144">Allows packages marked as Prerelease to be saved.</span></span>

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

### <span data-ttu-id="43f33-145">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="43f33-145">-AllVersions</span></span>

<span data-ttu-id="43f33-146">このコマンドレットが、使用可能なすべてのバージョンのパッケージを保存することを示します。</span><span class="sxs-lookup"><span data-stu-id="43f33-146">Indicates that this cmdlet saves all available versions of the package.</span></span>

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

### <span data-ttu-id="43f33-147">-Command</span><span class="sxs-lookup"><span data-stu-id="43f33-147">-Command</span></span>

<span data-ttu-id="43f33-148">パッケージに含まれる1つ以上のコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-148">Specifies one or more commands included in the package.</span></span>

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

### <span data-ttu-id="43f33-149">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="43f33-149">-ConfigFile</span></span>

<span data-ttu-id="43f33-150">構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-150">Specifies a configuration File.</span></span>

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

### <span data-ttu-id="43f33-151">-Contains</span><span class="sxs-lookup"><span data-stu-id="43f33-151">-Contains</span></span>

<span data-ttu-id="43f33-152">`Save-Package` オブジェクトのプロパティ値内のいずれかの項目が指定した値と完全に一致する場合は、オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="43f33-152">`Save-Package` gets objects if any item in the object's property values are an exact match for the specified value.</span></span>

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

### <span data-ttu-id="43f33-153">-Credential</span><span class="sxs-lookup"><span data-stu-id="43f33-153">-Credential</span></span>

<span data-ttu-id="43f33-154">指定したパッケージプロバイダーまたはソースからパッケージを保存するためのアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-154">Specifies a user account that has permission to save a package from a specified package provider or source.</span></span>

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

### <span data-ttu-id="43f33-155">-DscResource</span><span class="sxs-lookup"><span data-stu-id="43f33-155">-DscResource</span></span>

<span data-ttu-id="43f33-156">パッケージの Desired State Configuration (DSC) リソースを1つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-156">Specifies one or more Desired State Configuration (DSC) resources for the package.</span></span>

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

### <span data-ttu-id="43f33-157">-Filter</span><span class="sxs-lookup"><span data-stu-id="43f33-157">-Filter</span></span>

<span data-ttu-id="43f33-158">パッケージのフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-158">Specifies a filter for the package.</span></span>

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

### <span data-ttu-id="43f33-159">-FilterOnTag</span><span class="sxs-lookup"><span data-stu-id="43f33-159">-FilterOnTag</span></span>

<span data-ttu-id="43f33-160">結果をフィルター処理するタグを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-160">Specifies the tag that filters the results.</span></span> <span data-ttu-id="43f33-161">指定されたタグを含まない結果は除外されます。</span><span class="sxs-lookup"><span data-stu-id="43f33-161">Results that don't contain the specified tag are excluded.</span></span>

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

### <span data-ttu-id="43f33-162">-Force</span><span class="sxs-lookup"><span data-stu-id="43f33-162">-Force</span></span>

<span data-ttu-id="43f33-163">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="43f33-163">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="43f33-164">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="43f33-164">-ForceBootstrap</span></span>

<span data-ttu-id="43f33-165">が、 `Save-Package` 指定 **PackageManagement** されたパッケージのパッケージプロバイダーを自動的にインストールすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-165">Indicates that `Save-Package` forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="43f33-166">-ヘッダー</span><span class="sxs-lookup"><span data-stu-id="43f33-166">-Headers</span></span>

<span data-ttu-id="43f33-167">パッケージのヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-167">Specifies the headers for the package.</span></span>

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

### <span data-ttu-id="43f33-168">-インクルード</span><span class="sxs-lookup"><span data-stu-id="43f33-168">-Includes</span></span>

<span data-ttu-id="43f33-169">パッケージに含まれるリソースを示します。</span><span class="sxs-lookup"><span data-stu-id="43f33-169">Indicates the resources that the package includes.</span></span>

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

### <span data-ttu-id="43f33-170">-InputObject</span><span class="sxs-lookup"><span data-stu-id="43f33-170">-InputObject</span></span>

<span data-ttu-id="43f33-171">保存するパッケージを表すソフトウェア ID オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="43f33-171">A software ID object that represents the package that you want to save.</span></span> <span data-ttu-id="43f33-172">ソフトウェア Id は、コマンドレットの結果の一部です `Find-Package` 。</span><span class="sxs-lookup"><span data-stu-id="43f33-172">Software IDs are part of the results of the `Find-Package` cmdlet.</span></span>

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

### <span data-ttu-id="43f33-173">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="43f33-173">-LiteralPath</span></span>

<span data-ttu-id="43f33-174">パッケージを保存するリテラルパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-174">Specifies the literal path to which you want to save the package.</span></span> <span data-ttu-id="43f33-175">このパラメーターと **Path** パラメーターの両方を同じコマンドに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="43f33-175">You cannot add both this parameter and the **Path** parameter to the same command.</span></span>

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

### <span data-ttu-id="43f33-176">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="43f33-176">-MaximumVersion</span></span>

<span data-ttu-id="43f33-177">保存するパッケージの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-177">Specifies the maximum version of the package that you want to save.</span></span>

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

### <span data-ttu-id="43f33-178">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="43f33-178">-MinimumVersion</span></span>

<span data-ttu-id="43f33-179">検索するパッケージの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-179">Specifies the minimum version of the package that you want to find.</span></span>

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

### <span data-ttu-id="43f33-180">-Name</span><span class="sxs-lookup"><span data-stu-id="43f33-180">-Name</span></span>

<span data-ttu-id="43f33-181">1つまたは複数のパッケージ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-181">Specifies one or more package names.</span></span>

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

### <span data-ttu-id="43f33-182">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="43f33-182">-PackageManagementProvider</span></span>

<span data-ttu-id="43f33-183">パッケージ管理プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-183">Specifies a package management provider.</span></span>

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

### <span data-ttu-id="43f33-184">-Path</span><span class="sxs-lookup"><span data-stu-id="43f33-184">-Path</span></span>

<span data-ttu-id="43f33-185">パッケージを格納するローカルコンピューター上の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-185">Specifies the location on the local computer to store the package.</span></span>

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

### <span data-ttu-id="43f33-186">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="43f33-186">-ProviderName</span></span>

<span data-ttu-id="43f33-187">1つまたは複数のプロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-187">Specifies one or more provider names.</span></span>

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

### <span data-ttu-id="43f33-188">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="43f33-188">-Proxy</span></span>

<span data-ttu-id="43f33-189">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-189">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="43f33-190">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="43f33-190">-ProxyCredential</span></span>

<span data-ttu-id="43f33-191">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-191">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="43f33-192">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="43f33-192">-PublishLocation</span></span>

<span data-ttu-id="43f33-193">発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-193">Specifies the publish location.</span></span>

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

### <span data-ttu-id="43f33-194">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="43f33-194">-RequiredVersion</span></span>

<span data-ttu-id="43f33-195">保存するパッケージの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-195">Specifies the exact version of the package to save.</span></span>

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

### <span data-ttu-id="43f33-196">-Find-rolecapability</span><span class="sxs-lookup"><span data-stu-id="43f33-196">-RoleCapability</span></span>

<span data-ttu-id="43f33-197">ロール機能の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-197">Specifies an array of role capabilities.</span></span>

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

### <span data-ttu-id="43f33-198">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="43f33-198">-ScriptPublishLocation</span></span>

<span data-ttu-id="43f33-199">スクリプトの発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-199">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="43f33-200">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="43f33-200">-ScriptSourceLocation</span></span>

<span data-ttu-id="43f33-201">スクリプトのソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-201">Specifies the script source location.</span></span>

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

### <span data-ttu-id="43f33-202">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="43f33-202">-SkipValidate</span></span>

<span data-ttu-id="43f33-203">パッケージの資格情報の検証をスキップするスイッチ。</span><span class="sxs-lookup"><span data-stu-id="43f33-203">Switch that skips validating the credentials of a package.</span></span>

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

### <span data-ttu-id="43f33-204">-Source</span><span class="sxs-lookup"><span data-stu-id="43f33-204">-Source</span></span>

<span data-ttu-id="43f33-205">1つまたは複数のパッケージソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-205">Specifies one or more package sources.</span></span>

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

### <span data-ttu-id="43f33-206">-Tag</span><span class="sxs-lookup"><span data-stu-id="43f33-206">-Tag</span></span>

<span data-ttu-id="43f33-207">パッケージメタデータ内で検索するタグを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-207">Specifies a tag to search for within the package metadata.</span></span>

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

### <span data-ttu-id="43f33-208">-Type</span><span class="sxs-lookup"><span data-stu-id="43f33-208">-Type</span></span>

<span data-ttu-id="43f33-209">モジュール、スクリプト、またはいずれかを使用してパッケージを検索するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="43f33-209">Specifies whether to search for packages with a module, a script, or either.</span></span>

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

### <span data-ttu-id="43f33-210">-Confirm</span><span class="sxs-lookup"><span data-stu-id="43f33-210">-Confirm</span></span>

<span data-ttu-id="43f33-211">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="43f33-211">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="43f33-212">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="43f33-212">-WhatIf</span></span>

<span data-ttu-id="43f33-213">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="43f33-213">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="43f33-214">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="43f33-214">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="43f33-215">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="43f33-215">CommonParameters</span></span>

<span data-ttu-id="43f33-216">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="43f33-216">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="43f33-217">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43f33-217">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="43f33-218">入力</span><span class="sxs-lookup"><span data-stu-id="43f33-218">INPUTS</span></span>

### <span data-ttu-id="43f33-219">`Save-Package` パイプラインからのオブジェクトを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="43f33-219">`Save-Package` accepts objects from the pipeline.</span></span>

## <span data-ttu-id="43f33-220">出力</span><span class="sxs-lookup"><span data-stu-id="43f33-220">OUTPUTS</span></span>

### <span data-ttu-id="43f33-221">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="43f33-221">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="43f33-222">注</span><span class="sxs-lookup"><span data-stu-id="43f33-222">NOTES</span></span>

## <span data-ttu-id="43f33-223">関連リンク</span><span class="sxs-lookup"><span data-stu-id="43f33-223">RELATED LINKS</span></span>

[<span data-ttu-id="43f33-224">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="43f33-224">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="43f33-225">Get-Package</span><span class="sxs-lookup"><span data-stu-id="43f33-225">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="43f33-226">Install-Package</span><span class="sxs-lookup"><span data-stu-id="43f33-226">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="43f33-227">Save-Package</span><span class="sxs-lookup"><span data-stu-id="43f33-227">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="43f33-228">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="43f33-228">Uninstall-Package</span></span>](Uninstall-Package.md)