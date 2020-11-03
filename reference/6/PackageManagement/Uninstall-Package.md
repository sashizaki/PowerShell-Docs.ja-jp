---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/uninstall-package?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Package
ms.openlocfilehash: 4be80765181e045f24b1f90243de21f38533bfba
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214808"
---
# <span data-ttu-id="c3658-103">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="c3658-103">Uninstall-Package</span></span>

## <span data-ttu-id="c3658-104">概要</span><span class="sxs-lookup"><span data-stu-id="c3658-104">SYNOPSIS</span></span>
<span data-ttu-id="c3658-105">1つまたは複数のソフトウェアパッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="c3658-105">Uninstalls one or more software packages.</span></span>

## <span data-ttu-id="c3658-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c3658-106">SYNTAX</span></span>

### <span data-ttu-id="c3658-107">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="c3658-107">PackageByInputObject</span></span>

```
Uninstall-Package [-InputObject] <SoftwareIdentity[]> [-AllVersions] [-Force] [-ForceBootstrap]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c3658-108">PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="c3658-108">PackageBySearch</span></span>

```
Uninstall-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="c3658-109">NuGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="c3658-109">NuGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="c3658-110">NuGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="c3658-110">NuGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="c3658-111">PowerShellGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="c3658-111">PowerShellGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="c3658-112">PowerShellGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="c3658-112">PowerShellGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

## <span data-ttu-id="c3658-113">Description</span><span class="sxs-lookup"><span data-stu-id="c3658-113">DESCRIPTION</span></span>

<span data-ttu-id="c3658-114">`Uninstall-Package`コマンドレットは、ローカルコンピューターから1つまたは複数のソフトウェアパッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="c3658-114">The `Uninstall-Package` cmdlet uninstalls one or more software packages from the local computer.</span></span> <span data-ttu-id="c3658-115">インストールされているパッケージを検索するには、コマンドレットを使用し `Get-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="c3658-115">To find installed packages, use the `Get-Package` cmdlet.</span></span>

## <span data-ttu-id="c3658-116">例</span><span class="sxs-lookup"><span data-stu-id="c3658-116">EXAMPLES</span></span>

### <span data-ttu-id="c3658-117">例 1: パッケージをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="c3658-117">Example 1: Uninstall a package</span></span>

<span data-ttu-id="c3658-118">コマンドレットでは、 `Uninstall-Package` パッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="c3658-118">The `Uninstall-Package` cmdlet uninstalls packages.</span></span> <span data-ttu-id="c3658-119">**Name** パラメーターは、アンインストールするパッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="c3658-119">The **Name** parameter specifies the package to uninstall.</span></span> <span data-ttu-id="c3658-120">パッケージの複数のバージョンがインストールされている場合は、最新バージョンがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c3658-120">If multiple versions of a package are installed, the newest version is uninstalled.</span></span>

```
PS> Uninstall-Package -Name NuGet.Core
```

### <span data-ttu-id="c3658-121">例 2: パイプラインを使用してパッケージをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="c3658-121">Example 2: Use the pipeline to uninstall a package</span></span>

<span data-ttu-id="c3658-122">`Get-Package` 特定のパッケージを検索し、そのコマンドレットに対して **ソフトウェア id** オブジェクトをパイプラインの下に送信し `Uninsall-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="c3658-122">`Get-Package` locates a specific package and sends the **SoftwareIdentity** object down the pipeline to the `Uninsall-Package` cmdlet.</span></span>

```
PS> Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 | Uninstall-Package
```

<span data-ttu-id="c3658-123">コマンドレットでは、 `Get-Package` **Name** および **RequiredVersion** パラメーターを使用してパッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="c3658-123">The `Get-Package` cmdlet uses the **Name** and **RequiredVersion** parameters to specify a package.</span></span>
<span data-ttu-id="c3658-124">**ソフトウェア id** オブジェクトは、パイプラインから送信されます。</span><span class="sxs-lookup"><span data-stu-id="c3658-124">A **SoftwareIdentity** object is sent down the pipeline.</span></span> <span data-ttu-id="c3658-125">`Uninstall-Package`コマンドレットは、オブジェクトを **InputObject** として受信し、パッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3658-125">The `Uninstall-Package` cmdlet receives the object as an **InputObject** and removes the package.</span></span>

<span data-ttu-id="c3658-126">別の方法として、 `Uninstall-Package` コマンドレットで **InputObject** パラメーターの値を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c3658-126">As an alternative, the `Uninstall-Package` cmdlet can specify a value for the **InputObject** parameter:</span></span>

`Uninstall-Package -InputObject ( Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 )`

## <span data-ttu-id="c3658-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c3658-127">PARAMETERS</span></span>

### <span data-ttu-id="c3658-128">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="c3658-128">-AllowClobber</span></span>

<span data-ttu-id="c3658-129">既存のコマンドとの競合に関する警告メッセージを上書きします。</span><span class="sxs-lookup"><span data-stu-id="c3658-129">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="c3658-130">インストールされているコマンドと同じ名前を持つ既存のコマンドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="c3658-130">Overwrites existing commands that have the same name as commands being installed.</span></span>

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

### <span data-ttu-id="c3658-131">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="c3658-131">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="c3658-132">プレリリースとしてマークされているパッケージをアンインストールできるようにします。</span><span class="sxs-lookup"><span data-stu-id="c3658-132">Allows packages marked as prerelease to be uninstalled.</span></span>

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

### <span data-ttu-id="c3658-133">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="c3658-133">-AllVersions</span></span>

<span data-ttu-id="c3658-134">このコマンドレットによってパッケージのすべてのバージョンがアンインストールされることを示します。</span><span class="sxs-lookup"><span data-stu-id="c3658-134">Indicates that this cmdlet uninstalls all versions of the package.</span></span>

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

### <span data-ttu-id="c3658-135">-Destination</span><span class="sxs-lookup"><span data-stu-id="c3658-135">-Destination</span></span>

<span data-ttu-id="c3658-136">入力オブジェクトへのパスの文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3658-136">Specifies a string of the path to the input object.</span></span>

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

### <span data-ttu-id="c3658-137">-ExcludeVersion</span><span class="sxs-lookup"><span data-stu-id="c3658-137">-ExcludeVersion</span></span>

<span data-ttu-id="c3658-138">フォルダーパスのバージョン番号を除外するには、スイッチを指定します。</span><span class="sxs-lookup"><span data-stu-id="c3658-138">Switch to exclude the version number in the folder path.</span></span>

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

### <span data-ttu-id="c3658-139">-Force</span><span class="sxs-lookup"><span data-stu-id="c3658-139">-Force</span></span>

<span data-ttu-id="c3658-140">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c3658-140">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="c3658-141">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="c3658-141">-ForceBootstrap</span></span>

<span data-ttu-id="c3658-142">指定されたパッケージのパッケージプロバイダーを自動的にインストールするように **PackageManagement** に強制します。</span><span class="sxs-lookup"><span data-stu-id="c3658-142">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="c3658-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c3658-143">-InputObject</span></span>

<span data-ttu-id="c3658-144">コマンドレットでパッケージの **ソフトウェア id** オブジェクトを指定するパイプライン入力を受け入れ `Get-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="c3658-144">Accepts pipeline input that specifies the package's **SoftwareIdentity** object from the `Get-Package` cmdlet.</span></span> <span data-ttu-id="c3658-145">**InputObject** は、値またはオブジェクトを含む変数として、 **ソフトウェア id** オブジェクトを受け入れ `Get-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="c3658-145">**InputObject** accepts the **SoftwareIdentity** object as a `Get-Package` value or a variable that contains the object.</span></span>

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

### <span data-ttu-id="c3658-146">-InstallUpdate</span><span class="sxs-lookup"><span data-stu-id="c3658-146">-InstallUpdate</span></span>

<span data-ttu-id="c3658-147">によって更新プログラムがアンインストールされることを示し `Uninstall-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="c3658-147">Indicates that `Uninstall-Package` uninstalls updates.</span></span>

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

### <span data-ttu-id="c3658-148">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="c3658-148">-MaximumVersion</span></span>

<span data-ttu-id="c3658-149">アンインストールするパッケージの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c3658-149">Specifies the maximum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="c3658-150">このパラメーターを指定しない場合は、 `Uninstall-Package` パッケージの最新バージョンがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c3658-150">If you don't specify this parameter, `Uninstall-Package` uninstalls the package's newest version.</span></span>

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

### <span data-ttu-id="c3658-151">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="c3658-151">-MinimumVersion</span></span>

<span data-ttu-id="c3658-152">アンインストールする最小許容パッケージバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c3658-152">Specifies the minimum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="c3658-153">このパラメーターを追加しない場合、では、 `Uninstall-Package` **MaximumVersion** パラメーターで指定されたバージョンを満たすパッケージの最新バージョンがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c3658-153">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="c3658-154">-Name</span><span class="sxs-lookup"><span data-stu-id="c3658-154">-Name</span></span>

<span data-ttu-id="c3658-155">1つまたは複数のパッケージ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3658-155">Specifies one or more package names.</span></span> <span data-ttu-id="c3658-156">複数のパッケージ名は、コンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3658-156">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="c3658-157">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="c3658-157">-NoPathUpdate</span></span>

<span data-ttu-id="c3658-158">**Nopathupdate** はコマンドレットにのみ適用さ `Install-Script` れます。</span><span class="sxs-lookup"><span data-stu-id="c3658-158">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="c3658-159">**Nopathupdate** はプロバイダーによって追加される動的パラメーターであり、ではサポートされていません `Uninstall-Package` 。</span><span class="sxs-lookup"><span data-stu-id="c3658-159">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Uninstall-Package`.</span></span>

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

### <span data-ttu-id="c3658-160">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="c3658-160">-PackageManagementProvider</span></span>

<span data-ttu-id="c3658-161">**PackageManagement** プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c3658-161">Specifies the **PackageManagement** provider.</span></span>

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

### <span data-ttu-id="c3658-162">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="c3658-162">-ProviderName</span></span>

<span data-ttu-id="c3658-163">パッケージを検索するパッケージプロバイダー名を1つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="c3658-163">Specifies one or more package provider names to search for packages.</span></span> <span data-ttu-id="c3658-164">`Get-PackageProvider` コマンドレットを実行して、パッケージ プロバイダー名を取得できます。</span><span class="sxs-lookup"><span data-stu-id="c3658-164">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="c3658-165">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="c3658-165">-RequiredVersion</span></span>

<span data-ttu-id="c3658-166">アンインストールするパッケージの許可された正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c3658-166">Specifies the exact allowed version of the package that you want to uninstall.</span></span> <span data-ttu-id="c3658-167">このパラメーターを追加しない場合、では、 `Uninstall-Package` **MaximumVersion** パラメーターで指定されたバージョンを満たすパッケージの最新バージョンがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c3658-167">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="c3658-168">-スコープ</span><span class="sxs-lookup"><span data-stu-id="c3658-168">-Scope</span></span>

<span data-ttu-id="c3658-169">パッケージをアンインストールするスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="c3658-169">Specifies the scope for which to uninstall the package.</span></span> <span data-ttu-id="c3658-170">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c3658-170">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="c3658-171">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="c3658-171">CurrentUser</span></span>
- <span data-ttu-id="c3658-172">AllUsers</span><span class="sxs-lookup"><span data-stu-id="c3658-172">AllUsers</span></span>

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

### <span data-ttu-id="c3658-173">-SkipDependencies</span><span class="sxs-lookup"><span data-stu-id="c3658-173">-SkipDependencies</span></span>

<span data-ttu-id="c3658-174">ソフトウェアの依存関係のアンインストールをスキップします。</span><span class="sxs-lookup"><span data-stu-id="c3658-174">Skips the uninstallation of software dependencies.</span></span>

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

### <span data-ttu-id="c3658-175">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="c3658-175">-SkipPublisherCheck</span></span>

<span data-ttu-id="c3658-176">インストールされているバージョンよりも新しいバージョンのパッケージを取得できます。</span><span class="sxs-lookup"><span data-stu-id="c3658-176">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="c3658-177">たとえば、信頼された発行元によってデジタル署名されているが新しいバージョンのパッケージはデジタル署名されていません。</span><span class="sxs-lookup"><span data-stu-id="c3658-177">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

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

### <span data-ttu-id="c3658-178">-Type</span><span class="sxs-lookup"><span data-stu-id="c3658-178">-Type</span></span>

<span data-ttu-id="c3658-179">モジュール、スクリプト、またはその両方を含むパッケージを検索するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c3658-179">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="c3658-180">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c3658-180">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="c3658-181">[Module]</span><span class="sxs-lookup"><span data-stu-id="c3658-181">Module</span></span>
- <span data-ttu-id="c3658-182">スクリプト</span><span class="sxs-lookup"><span data-stu-id="c3658-182">Script</span></span>
- <span data-ttu-id="c3658-183">All</span><span class="sxs-lookup"><span data-stu-id="c3658-183">All</span></span>

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

### <span data-ttu-id="c3658-184">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c3658-184">-Confirm</span></span>

<span data-ttu-id="c3658-185">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3658-185">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c3658-186">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c3658-186">-WhatIf</span></span>

<span data-ttu-id="c3658-187">コマンドレットが実行された場合に何が起こるか `Uninstall-Package` を示します。</span><span class="sxs-lookup"><span data-stu-id="c3658-187">Shows what would happen if `Uninstall-Package` cmdlet is run.</span></span> <span data-ttu-id="c3658-188">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c3658-188">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="c3658-189">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3658-189">CommonParameters</span></span>

<span data-ttu-id="c3658-190">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c3658-190">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c3658-191">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3658-191">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c3658-192">入力</span><span class="sxs-lookup"><span data-stu-id="c3658-192">INPUTS</span></span>

### <span data-ttu-id="c3658-193">`Uninstall-Package` パイプラインからの **ソフトウェア id** オブジェクトを入力として受け入れます。</span><span class="sxs-lookup"><span data-stu-id="c3658-193">`Uninstall-Package` accepts **SoftwareIdentity** objects from the pipeline as input.</span></span>

## <span data-ttu-id="c3658-194">出力</span><span class="sxs-lookup"><span data-stu-id="c3658-194">OUTPUTS</span></span>

### <span data-ttu-id="c3658-195">`Uninstall-Package` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="c3658-195">`Uninstall-Package` doesn't generate any output.</span></span>

## <span data-ttu-id="c3658-196">注</span><span class="sxs-lookup"><span data-stu-id="c3658-196">NOTES</span></span>

<span data-ttu-id="c3658-197">コマンドにパッケージプロバイダーを含めると、コマンドレットで動的パラメーターを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c3658-197">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="c3658-198">動的パラメーターは、パッケージプロバイダーに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="c3658-198">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="c3658-199">コマンドレットにより、 `Get-Help` コマンドレットのパラメーターセットが一覧表示され、プロバイダーのパラメーターセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c3658-199">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="c3658-200">たとえば、には、、、 `Uninstall-Package` およびを含む **PowerShellGet** パラメーターが設定されてい `-NoPathUpdate` `AllowClobber` `SkipPublisherCheck` ます。</span><span class="sxs-lookup"><span data-stu-id="c3658-200">For example, `Uninstall-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="c3658-201">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c3658-201">RELATED LINKS</span></span>

[<span data-ttu-id="c3658-202">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="c3658-202">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="c3658-203">Find-Package</span><span class="sxs-lookup"><span data-stu-id="c3658-203">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="c3658-204">Get-Package</span><span class="sxs-lookup"><span data-stu-id="c3658-204">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="c3658-205">Install-Package</span><span class="sxs-lookup"><span data-stu-id="c3658-205">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="c3658-206">Save-Package</span><span class="sxs-lookup"><span data-stu-id="c3658-206">Save-Package</span></span>](Save-Package.md)
