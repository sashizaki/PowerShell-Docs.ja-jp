---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/uninstall-package?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Package
ms.openlocfilehash: 6f22da7040413f64e9e96a7df57401a0701156bd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213267"
---
# <span data-ttu-id="9e554-103">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="9e554-103">Uninstall-Package</span></span>

## <span data-ttu-id="9e554-104">概要</span><span class="sxs-lookup"><span data-stu-id="9e554-104">SYNOPSIS</span></span>
<span data-ttu-id="9e554-105">1つまたは複数のソフトウェアパッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="9e554-105">Uninstalls one or more software packages.</span></span>

## <span data-ttu-id="9e554-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9e554-106">SYNTAX</span></span>

### <span data-ttu-id="9e554-107">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="9e554-107">PackageByInputObject</span></span>

```
Uninstall-Package [-InputObject] <SoftwareIdentity[]> [-AllVersions] [-Force] [-ForceBootstrap]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9e554-108">PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="9e554-108">PackageBySearch</span></span>

```
Uninstall-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="9e554-109">msi: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="9e554-109">msi:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AdditionalArguments <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="9e554-110">msi: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="9e554-110">msi:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AdditionalArguments <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="9e554-111">プログラム: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="9e554-111">Programs:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-IncludeWindowsInstaller] [-IncludeSystemComponent] [<CommonParameters>]
```

### <span data-ttu-id="9e554-112">プログラム: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="9e554-112">Programs:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-IncludeWindowsInstaller] [-IncludeSystemComponent] [<CommonParameters>]
```

### <span data-ttu-id="9e554-113">NuGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="9e554-113">NuGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="9e554-114">NuGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="9e554-114">NuGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="9e554-115">PowerShellGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="9e554-115">PowerShellGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="9e554-116">PowerShellGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="9e554-116">PowerShellGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

## <span data-ttu-id="9e554-117">Description</span><span class="sxs-lookup"><span data-stu-id="9e554-117">DESCRIPTION</span></span>

<span data-ttu-id="9e554-118">`Uninstall-Package`コマンドレットは、ローカルコンピューターから1つまたは複数のソフトウェアパッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="9e554-118">The `Uninstall-Package` cmdlet uninstalls one or more software packages from the local computer.</span></span> <span data-ttu-id="9e554-119">インストールされているパッケージを検索するには、コマンドレットを使用し `Get-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="9e554-119">To find installed packages, use the `Get-Package` cmdlet.</span></span>

## <span data-ttu-id="9e554-120">例</span><span class="sxs-lookup"><span data-stu-id="9e554-120">EXAMPLES</span></span>

### <span data-ttu-id="9e554-121">例 1: パッケージをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="9e554-121">Example 1: Uninstall a package</span></span>

<span data-ttu-id="9e554-122">コマンドレットでは、 `Uninstall-Package` パッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="9e554-122">The `Uninstall-Package` cmdlet uninstalls packages.</span></span> <span data-ttu-id="9e554-123">**Name** パラメーターは、アンインストールするパッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e554-123">The **Name** parameter specifies the package to uninstall.</span></span> <span data-ttu-id="9e554-124">パッケージの複数のバージョンがインストールされている場合は、最新バージョンがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9e554-124">If multiple versions of a package are installed, the newest version is uninstalled.</span></span>

```
PS> Uninstall-Package -Name NuGet.Core
```

### <span data-ttu-id="9e554-125">例 2: パイプラインを使用してパッケージをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="9e554-125">Example 2: Use the pipeline to uninstall a package</span></span>

<span data-ttu-id="9e554-126">`Get-Package` 特定のパッケージを検索し、そのコマンドレットに対して **ソフトウェア id** オブジェクトをパイプラインの下に送信し `Uninsall-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="9e554-126">`Get-Package` locates a specific package and sends the **SoftwareIdentity** object down the pipeline to the `Uninsall-Package` cmdlet.</span></span>

```
PS> Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 | Uninstall-Package
```

<span data-ttu-id="9e554-127">コマンドレットでは、 `Get-Package` **Name** および **RequiredVersion** パラメーターを使用してパッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e554-127">The `Get-Package` cmdlet uses the **Name** and **RequiredVersion** parameters to specify a package.</span></span>
<span data-ttu-id="9e554-128">**ソフトウェア id** オブジェクトは、パイプラインから送信されます。</span><span class="sxs-lookup"><span data-stu-id="9e554-128">A **SoftwareIdentity** object is sent down the pipeline.</span></span> <span data-ttu-id="9e554-129">`Uninstall-Package`コマンドレットは、オブジェクトを **InputObject** として受信し、パッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="9e554-129">The `Uninstall-Package` cmdlet receives the object as an **InputObject** and removes the package.</span></span>

<span data-ttu-id="9e554-130">別の方法として、 `Uninstall-Package` コマンドレットで **InputObject** パラメーターの値を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="9e554-130">As an alternative, the `Uninstall-Package` cmdlet can specify a value for the **InputObject** parameter:</span></span>

`Uninstall-Package -InputObject ( Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 )`

## <span data-ttu-id="9e554-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9e554-131">PARAMETERS</span></span>

### <span data-ttu-id="9e554-132">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="9e554-132">-AllowClobber</span></span>

<span data-ttu-id="9e554-133">既存のコマンドとの競合に関する警告メッセージを上書きします。</span><span class="sxs-lookup"><span data-stu-id="9e554-133">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="9e554-134">インストールされているコマンドと同じ名前を持つ既存のコマンドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="9e554-134">Overwrites existing commands that have the same name as commands being installed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e554-135">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="9e554-135">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="9e554-136">プレリリースとしてマークされているパッケージをアンインストールできるようにします。</span><span class="sxs-lookup"><span data-stu-id="9e554-136">Allows packages marked as prerelease to be uninstalled.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e554-137">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="9e554-137">-AllVersions</span></span>

<span data-ttu-id="9e554-138">このコマンドレットによってパッケージのすべてのバージョンがアンインストールされることを示します。</span><span class="sxs-lookup"><span data-stu-id="9e554-138">Indicates that this cmdlet uninstalls all versions of the package.</span></span>

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

### <span data-ttu-id="9e554-139">-Destination</span><span class="sxs-lookup"><span data-stu-id="9e554-139">-Destination</span></span>

<span data-ttu-id="9e554-140">入力オブジェクトへのパスの文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e554-140">Specifies a string of the path to the input object.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e554-141">-ExcludeVersion</span><span class="sxs-lookup"><span data-stu-id="9e554-141">-ExcludeVersion</span></span>

<span data-ttu-id="9e554-142">フォルダーパスのバージョン番号を除外するには、スイッチを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e554-142">Switch to exclude the version number in the folder path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e554-143">-Force</span><span class="sxs-lookup"><span data-stu-id="9e554-143">-Force</span></span>

<span data-ttu-id="9e554-144">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9e554-144">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="9e554-145">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="9e554-145">-ForceBootstrap</span></span>

<span data-ttu-id="9e554-146">指定されたパッケージのパッケージプロバイダーを自動的にインストールするように **PackageManagement** に強制します。</span><span class="sxs-lookup"><span data-stu-id="9e554-146">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="9e554-147">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9e554-147">-InputObject</span></span>

<span data-ttu-id="9e554-148">コマンドレットでパッケージの **ソフトウェア id** オブジェクトを指定するパイプライン入力を受け入れ `Get-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="9e554-148">Accepts pipeline input that specifies the package's **SoftwareIdentity** object from the `Get-Package` cmdlet.</span></span> <span data-ttu-id="9e554-149">**InputObject** は、値またはオブジェクトを含む変数として、 **ソフトウェア id** オブジェクトを受け入れ `Get-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="9e554-149">**InputObject** accepts the **SoftwareIdentity** object as a `Get-Package` value or a variable that contains the object.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.SoftwareIdentity[]
Parameter Sets: PackageByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9e554-150">-InstallUpdate</span><span class="sxs-lookup"><span data-stu-id="9e554-150">-InstallUpdate</span></span>

<span data-ttu-id="9e554-151">によって更新プログラムがアンインストールされることを示し `Uninstall-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="9e554-151">Indicates that `Uninstall-Package` uninstalls updates.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e554-152">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="9e554-152">-MaximumVersion</span></span>

<span data-ttu-id="9e554-153">アンインストールするパッケージの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e554-153">Specifies the maximum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="9e554-154">このパラメーターを指定しない場合は、 `Uninstall-Package` パッケージの最新バージョンがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9e554-154">If you don't specify this parameter, `Uninstall-Package` uninstalls the package's newest version.</span></span>

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

### <span data-ttu-id="9e554-155">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="9e554-155">-MinimumVersion</span></span>

<span data-ttu-id="9e554-156">アンインストールする最小許容パッケージバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e554-156">Specifies the minimum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="9e554-157">このパラメーターを追加しない場合、では、 `Uninstall-Package` **MaximumVersion** パラメーターで指定されたバージョンを満たすパッケージの最新バージョンがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9e554-157">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="9e554-158">-Name</span><span class="sxs-lookup"><span data-stu-id="9e554-158">-Name</span></span>

<span data-ttu-id="9e554-159">1つまたは複数のパッケージ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e554-159">Specifies one or more package names.</span></span> <span data-ttu-id="9e554-160">複数のパッケージ名は、コンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e554-160">Multiple package names must be separated by commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e554-161">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="9e554-161">-NoPathUpdate</span></span>

<span data-ttu-id="9e554-162">**Nopathupdate** はコマンドレットにのみ適用さ `Install-Script` れます。</span><span class="sxs-lookup"><span data-stu-id="9e554-162">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="9e554-163">**Nopathupdate** はプロバイダーによって追加される動的パラメーターであり、ではサポートされていません `Uninstall-Package` 。</span><span class="sxs-lookup"><span data-stu-id="9e554-163">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Uninstall-Package`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e554-164">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="9e554-164">-PackageManagementProvider</span></span>

<span data-ttu-id="9e554-165">**PackageManagement** プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e554-165">Specifies the **PackageManagement** provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e554-166">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="9e554-166">-ProviderName</span></span>

<span data-ttu-id="9e554-167">パッケージを検索するパッケージプロバイダー名を1つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="9e554-167">Specifies one or more package provider names to search for packages.</span></span> <span data-ttu-id="9e554-168">`Get-PackageProvider` コマンドレットを実行して、パッケージ プロバイダー名を取得できます。</span><span class="sxs-lookup"><span data-stu-id="9e554-168">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="9e554-169">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="9e554-169">-RequiredVersion</span></span>

<span data-ttu-id="9e554-170">アンインストールするパッケージの許可された正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e554-170">Specifies the exact allowed version of the package that you want to uninstall.</span></span> <span data-ttu-id="9e554-171">このパラメーターを追加しない場合、では、 `Uninstall-Package` **MaximumVersion** パラメーターで指定されたバージョンを満たすパッケージの最新バージョンがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9e554-171">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="9e554-172">-スコープ</span><span class="sxs-lookup"><span data-stu-id="9e554-172">-Scope</span></span>

<span data-ttu-id="9e554-173">パッケージをアンインストールするスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e554-173">Specifies the scope for which to uninstall the package.</span></span> <span data-ttu-id="9e554-174">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9e554-174">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="9e554-175">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="9e554-175">CurrentUser</span></span>
- <span data-ttu-id="9e554-176">AllUsers</span><span class="sxs-lookup"><span data-stu-id="9e554-176">AllUsers</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch, PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e554-177">-SkipDependencies</span><span class="sxs-lookup"><span data-stu-id="9e554-177">-SkipDependencies</span></span>

<span data-ttu-id="9e554-178">ソフトウェアの依存関係のアンインストールをスキップします。</span><span class="sxs-lookup"><span data-stu-id="9e554-178">Skips the uninstallation of software dependencies.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e554-179">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="9e554-179">-SkipPublisherCheck</span></span>

<span data-ttu-id="9e554-180">インストールされているバージョンよりも新しいバージョンのパッケージを取得できます。</span><span class="sxs-lookup"><span data-stu-id="9e554-180">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="9e554-181">たとえば、信頼された発行元によってデジタル署名されているが新しいバージョンのパッケージはデジタル署名されていません。</span><span class="sxs-lookup"><span data-stu-id="9e554-181">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e554-182">-Type</span><span class="sxs-lookup"><span data-stu-id="9e554-182">-Type</span></span>

<span data-ttu-id="9e554-183">モジュール、スクリプト、またはその両方を含むパッケージを検索するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e554-183">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="9e554-184">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9e554-184">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="9e554-185">[Module]</span><span class="sxs-lookup"><span data-stu-id="9e554-185">Module</span></span>
- <span data-ttu-id="9e554-186">スクリプト</span><span class="sxs-lookup"><span data-stu-id="9e554-186">Script</span></span>
- <span data-ttu-id="9e554-187">All</span><span class="sxs-lookup"><span data-stu-id="9e554-187">All</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e554-188">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9e554-188">-Confirm</span></span>

<span data-ttu-id="9e554-189">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e554-189">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9e554-190">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9e554-190">-WhatIf</span></span>

<span data-ttu-id="9e554-191">コマンドレットが実行された場合に何が起こるか `Uninstall-Package` を示します。</span><span class="sxs-lookup"><span data-stu-id="9e554-191">Shows what would happen if `Uninstall-Package` cmdlet is run.</span></span> <span data-ttu-id="9e554-192">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="9e554-192">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="9e554-193">-AdditionalArguments</span><span class="sxs-lookup"><span data-stu-id="9e554-193">-AdditionalArguments</span></span>

<span data-ttu-id="9e554-194">追加の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e554-194">Specifies additional arguments.</span></span>

```yaml
Type: System.String[]
Parameter Sets: msi:PackageByInputObject, msi:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e554-195">-IncludeSystemComponent</span><span class="sxs-lookup"><span data-stu-id="9e554-195">-IncludeSystemComponent</span></span>

<span data-ttu-id="9e554-196">このコマンドレットによってシステムコンポーネントがアンインストールされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e554-196">Specifies that this cmdlet uninstalls system components.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs:PackageByInputObject, Programs:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e554-197">-IncludeWindowsInstaller</span><span class="sxs-lookup"><span data-stu-id="9e554-197">-IncludeWindowsInstaller</span></span>

<span data-ttu-id="9e554-198">このコマンドレットによって、Windows インストーラーによってパッケージがアンインストールされることを示します。</span><span class="sxs-lookup"><span data-stu-id="9e554-198">Indicates that this cmdlet uninstalls the package through Windows Installer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs:PackageByInputObject, Programs:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9e554-199">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9e554-199">CommonParameters</span></span>

<span data-ttu-id="9e554-200">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="9e554-200">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9e554-201">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e554-201">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9e554-202">入力</span><span class="sxs-lookup"><span data-stu-id="9e554-202">INPUTS</span></span>

### <span data-ttu-id="9e554-203">`Uninstall-Package` パイプラインからの **ソフトウェア id** オブジェクトを入力として受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9e554-203">`Uninstall-Package` accepts **SoftwareIdentity** objects from the pipeline as input.</span></span>

## <span data-ttu-id="9e554-204">出力</span><span class="sxs-lookup"><span data-stu-id="9e554-204">OUTPUTS</span></span>

### <span data-ttu-id="9e554-205">`Uninstall-Package` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="9e554-205">`Uninstall-Package` doesn't generate any output.</span></span>

## <span data-ttu-id="9e554-206">注</span><span class="sxs-lookup"><span data-stu-id="9e554-206">NOTES</span></span>

<span data-ttu-id="9e554-207">コマンドにパッケージプロバイダーを含めると、コマンドレットで動的パラメーターを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9e554-207">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="9e554-208">動的パラメーターは、パッケージプロバイダーに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="9e554-208">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="9e554-209">コマンドレットにより、 `Get-Help` コマンドレットのパラメーターセットが一覧表示され、プロバイダーのパラメーターセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9e554-209">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="9e554-210">たとえば、には、、、 `Uninstall-Package` およびを含む **PowerShellGet** パラメーターが設定されてい `-NoPathUpdate` `AllowClobber` `SkipPublisherCheck` ます。</span><span class="sxs-lookup"><span data-stu-id="9e554-210">For example, `Uninstall-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="9e554-211">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9e554-211">RELATED LINKS</span></span>

[<span data-ttu-id="9e554-212">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="9e554-212">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="9e554-213">Find-Package</span><span class="sxs-lookup"><span data-stu-id="9e554-213">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="9e554-214">Get-Package</span><span class="sxs-lookup"><span data-stu-id="9e554-214">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="9e554-215">Install-Package</span><span class="sxs-lookup"><span data-stu-id="9e554-215">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="9e554-216">Save-Package</span><span class="sxs-lookup"><span data-stu-id="9e554-216">Save-Package</span></span>](Save-Package.md)
