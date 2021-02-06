---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/uninstall-package?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Package
ms.openlocfilehash: ca12f7f2118a004a6f474ae8174b04f9dbb9444d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601804"
---
# <span data-ttu-id="12b60-102">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="12b60-102">Uninstall-Package</span></span>

## <span data-ttu-id="12b60-103">概要</span><span class="sxs-lookup"><span data-stu-id="12b60-103">SYNOPSIS</span></span>
<span data-ttu-id="12b60-104">1つまたは複数のソフトウェアパッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="12b60-104">Uninstalls one or more software packages.</span></span>

## <span data-ttu-id="12b60-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="12b60-105">SYNTAX</span></span>

### <span data-ttu-id="12b60-106">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="12b60-106">PackageByInputObject</span></span>

```
Uninstall-Package [-InputObject] <SoftwareIdentity[]> [-AllVersions] [-Force] [-ForceBootstrap]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="12b60-107">PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="12b60-107">PackageBySearch</span></span>

```
Uninstall-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="12b60-108">NuGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="12b60-108">NuGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="12b60-109">NuGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="12b60-109">NuGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="12b60-110">PowerShellGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="12b60-110">PowerShellGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="12b60-111">PowerShellGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="12b60-111">PowerShellGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

## <span data-ttu-id="12b60-112">Description</span><span class="sxs-lookup"><span data-stu-id="12b60-112">DESCRIPTION</span></span>

<span data-ttu-id="12b60-113">`Uninstall-Package`コマンドレットは、ローカルコンピューターから1つまたは複数のソフトウェアパッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="12b60-113">The `Uninstall-Package` cmdlet uninstalls one or more software packages from the local computer.</span></span> <span data-ttu-id="12b60-114">インストールされているパッケージを検索するには、コマンドレットを使用し `Get-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="12b60-114">To find installed packages, use the `Get-Package` cmdlet.</span></span>

## <span data-ttu-id="12b60-115">例</span><span class="sxs-lookup"><span data-stu-id="12b60-115">EXAMPLES</span></span>

### <span data-ttu-id="12b60-116">例 1: パッケージをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="12b60-116">Example 1: Uninstall a package</span></span>

<span data-ttu-id="12b60-117">コマンドレットでは、 `Uninstall-Package` パッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="12b60-117">The `Uninstall-Package` cmdlet uninstalls packages.</span></span> <span data-ttu-id="12b60-118">**Name** パラメーターは、アンインストールするパッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="12b60-118">The **Name** parameter specifies the package to uninstall.</span></span> <span data-ttu-id="12b60-119">パッケージの複数のバージョンがインストールされている場合は、最新バージョンがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="12b60-119">If multiple versions of a package are installed, the newest version is uninstalled.</span></span>

```
PS> Uninstall-Package -Name NuGet.Core
```

### <span data-ttu-id="12b60-120">例 2: パイプラインを使用してパッケージをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="12b60-120">Example 2: Use the pipeline to uninstall a package</span></span>

<span data-ttu-id="12b60-121">`Get-Package` 特定のパッケージを検索し、そのコマンドレットに対して **ソフトウェア id** オブジェクトをパイプラインの下に送信し `Uninsall-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="12b60-121">`Get-Package` locates a specific package and sends the **SoftwareIdentity** object down the pipeline to the `Uninsall-Package` cmdlet.</span></span>

```
PS> Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 | Uninstall-Package
```

<span data-ttu-id="12b60-122">コマンドレットでは、 `Get-Package` **Name** および **RequiredVersion** パラメーターを使用してパッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="12b60-122">The `Get-Package` cmdlet uses the **Name** and **RequiredVersion** parameters to specify a package.</span></span>
<span data-ttu-id="12b60-123">**ソフトウェア id** オブジェクトは、パイプラインから送信されます。</span><span class="sxs-lookup"><span data-stu-id="12b60-123">A **SoftwareIdentity** object is sent down the pipeline.</span></span> <span data-ttu-id="12b60-124">`Uninstall-Package`コマンドレットは、オブジェクトを **InputObject** として受信し、パッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="12b60-124">The `Uninstall-Package` cmdlet receives the object as an **InputObject** and removes the package.</span></span>

<span data-ttu-id="12b60-125">別の方法として、 `Uninstall-Package` コマンドレットで **InputObject** パラメーターの値を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="12b60-125">As an alternative, the `Uninstall-Package` cmdlet can specify a value for the **InputObject** parameter:</span></span>

`Uninstall-Package -InputObject ( Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 )`

## <span data-ttu-id="12b60-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="12b60-126">PARAMETERS</span></span>

### <span data-ttu-id="12b60-127">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="12b60-127">-AllowClobber</span></span>

<span data-ttu-id="12b60-128">既存のコマンドとの競合に関する警告メッセージを上書きします。</span><span class="sxs-lookup"><span data-stu-id="12b60-128">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="12b60-129">インストールされているコマンドと同じ名前を持つ既存のコマンドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="12b60-129">Overwrites existing commands that have the same name as commands being installed.</span></span>

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

### <span data-ttu-id="12b60-130">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="12b60-130">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="12b60-131">プレリリースとしてマークされているパッケージをアンインストールできるようにします。</span><span class="sxs-lookup"><span data-stu-id="12b60-131">Allows packages marked as prerelease to be uninstalled.</span></span>

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

### <span data-ttu-id="12b60-132">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="12b60-132">-AllVersions</span></span>

<span data-ttu-id="12b60-133">このコマンドレットによってパッケージのすべてのバージョンがアンインストールされることを示します。</span><span class="sxs-lookup"><span data-stu-id="12b60-133">Indicates that this cmdlet uninstalls all versions of the package.</span></span>

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

### <span data-ttu-id="12b60-134">-Destination</span><span class="sxs-lookup"><span data-stu-id="12b60-134">-Destination</span></span>

<span data-ttu-id="12b60-135">入力オブジェクトへのパスの文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="12b60-135">Specifies a string of the path to the input object.</span></span>

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

### <span data-ttu-id="12b60-136">-ExcludeVersion</span><span class="sxs-lookup"><span data-stu-id="12b60-136">-ExcludeVersion</span></span>

<span data-ttu-id="12b60-137">フォルダーパスのバージョン番号を除外するには、スイッチを指定します。</span><span class="sxs-lookup"><span data-stu-id="12b60-137">Switch to exclude the version number in the folder path.</span></span>

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

### <span data-ttu-id="12b60-138">-Force</span><span class="sxs-lookup"><span data-stu-id="12b60-138">-Force</span></span>

<span data-ttu-id="12b60-139">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="12b60-139">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="12b60-140">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="12b60-140">-ForceBootstrap</span></span>

<span data-ttu-id="12b60-141">指定されたパッケージのパッケージプロバイダーを自動的にインストールするように **PackageManagement** に強制します。</span><span class="sxs-lookup"><span data-stu-id="12b60-141">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="12b60-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="12b60-142">-InputObject</span></span>

<span data-ttu-id="12b60-143">コマンドレットでパッケージの **ソフトウェア id** オブジェクトを指定するパイプライン入力を受け入れ `Get-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="12b60-143">Accepts pipeline input that specifies the package's **SoftwareIdentity** object from the `Get-Package` cmdlet.</span></span> <span data-ttu-id="12b60-144">**InputObject** は、値またはオブジェクトを含む変数として、 **ソフトウェア id** オブジェクトを受け入れ `Get-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="12b60-144">**InputObject** accepts the **SoftwareIdentity** object as a `Get-Package` value or a variable that contains the object.</span></span>

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

### <span data-ttu-id="12b60-145">-InstallUpdate</span><span class="sxs-lookup"><span data-stu-id="12b60-145">-InstallUpdate</span></span>

<span data-ttu-id="12b60-146">によって更新プログラムがアンインストールされることを示し `Uninstall-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="12b60-146">Indicates that `Uninstall-Package` uninstalls updates.</span></span>

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

### <span data-ttu-id="12b60-147">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="12b60-147">-MaximumVersion</span></span>

<span data-ttu-id="12b60-148">アンインストールするパッケージの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="12b60-148">Specifies the maximum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="12b60-149">このパラメーターを指定しない場合は、 `Uninstall-Package` パッケージの最新バージョンがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="12b60-149">If you don't specify this parameter, `Uninstall-Package` uninstalls the package's newest version.</span></span>

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

### <span data-ttu-id="12b60-150">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="12b60-150">-MinimumVersion</span></span>

<span data-ttu-id="12b60-151">アンインストールする最小許容パッケージバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="12b60-151">Specifies the minimum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="12b60-152">このパラメーターを追加しない場合、では、 `Uninstall-Package` **MaximumVersion** パラメーターで指定されたバージョンを満たすパッケージの最新バージョンがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="12b60-152">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="12b60-153">-Name</span><span class="sxs-lookup"><span data-stu-id="12b60-153">-Name</span></span>

<span data-ttu-id="12b60-154">1つまたは複数のパッケージ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="12b60-154">Specifies one or more package names.</span></span> <span data-ttu-id="12b60-155">複数のパッケージ名は、コンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="12b60-155">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="12b60-156">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="12b60-156">-NoPathUpdate</span></span>

<span data-ttu-id="12b60-157">**Nopathupdate** はコマンドレットにのみ適用さ `Install-Script` れます。</span><span class="sxs-lookup"><span data-stu-id="12b60-157">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="12b60-158">**Nopathupdate** はプロバイダーによって追加される動的パラメーターであり、ではサポートされていません `Uninstall-Package` 。</span><span class="sxs-lookup"><span data-stu-id="12b60-158">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Uninstall-Package`.</span></span>

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

### <span data-ttu-id="12b60-159">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="12b60-159">-PackageManagementProvider</span></span>

<span data-ttu-id="12b60-160">**PackageManagement** プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="12b60-160">Specifies the **PackageManagement** provider.</span></span>

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

### <span data-ttu-id="12b60-161">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="12b60-161">-ProviderName</span></span>

<span data-ttu-id="12b60-162">パッケージを検索するパッケージプロバイダー名を1つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="12b60-162">Specifies one or more package provider names to search for packages.</span></span> <span data-ttu-id="12b60-163">`Get-PackageProvider` コマンドレットを実行して、パッケージ プロバイダー名を取得できます。</span><span class="sxs-lookup"><span data-stu-id="12b60-163">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="12b60-164">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="12b60-164">-RequiredVersion</span></span>

<span data-ttu-id="12b60-165">アンインストールするパッケージの許可された正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="12b60-165">Specifies the exact allowed version of the package that you want to uninstall.</span></span> <span data-ttu-id="12b60-166">このパラメーターを追加しない場合、では、 `Uninstall-Package` **MaximumVersion** パラメーターで指定されたバージョンを満たすパッケージの最新バージョンがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="12b60-166">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="12b60-167">-スコープ</span><span class="sxs-lookup"><span data-stu-id="12b60-167">-Scope</span></span>

<span data-ttu-id="12b60-168">パッケージをアンインストールするスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="12b60-168">Specifies the scope for which to uninstall the package.</span></span> <span data-ttu-id="12b60-169">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="12b60-169">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="12b60-170">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="12b60-170">CurrentUser</span></span>
- <span data-ttu-id="12b60-171">AllUsers</span><span class="sxs-lookup"><span data-stu-id="12b60-171">AllUsers</span></span>

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

### <span data-ttu-id="12b60-172">-SkipDependencies</span><span class="sxs-lookup"><span data-stu-id="12b60-172">-SkipDependencies</span></span>

<span data-ttu-id="12b60-173">ソフトウェアの依存関係のアンインストールをスキップします。</span><span class="sxs-lookup"><span data-stu-id="12b60-173">Skips the uninstallation of software dependencies.</span></span>

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

### <span data-ttu-id="12b60-174">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="12b60-174">-SkipPublisherCheck</span></span>

<span data-ttu-id="12b60-175">インストールされているバージョンよりも新しいバージョンのパッケージを取得できます。</span><span class="sxs-lookup"><span data-stu-id="12b60-175">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="12b60-176">たとえば、信頼された発行元によってデジタル署名されているが新しいバージョンのパッケージはデジタル署名されていません。</span><span class="sxs-lookup"><span data-stu-id="12b60-176">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

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

### <span data-ttu-id="12b60-177">-Type</span><span class="sxs-lookup"><span data-stu-id="12b60-177">-Type</span></span>

<span data-ttu-id="12b60-178">モジュール、スクリプト、またはその両方を含むパッケージを検索するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="12b60-178">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="12b60-179">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="12b60-179">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="12b60-180">Module</span><span class="sxs-lookup"><span data-stu-id="12b60-180">Module</span></span>
- <span data-ttu-id="12b60-181">スクリプト</span><span class="sxs-lookup"><span data-stu-id="12b60-181">Script</span></span>
- <span data-ttu-id="12b60-182">すべて</span><span class="sxs-lookup"><span data-stu-id="12b60-182">All</span></span>

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

### <span data-ttu-id="12b60-183">-Confirm</span><span class="sxs-lookup"><span data-stu-id="12b60-183">-Confirm</span></span>

<span data-ttu-id="12b60-184">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="12b60-184">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="12b60-185">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="12b60-185">-WhatIf</span></span>

<span data-ttu-id="12b60-186">コマンドレットが実行された場合に何が起こるか `Uninstall-Package` を示します。</span><span class="sxs-lookup"><span data-stu-id="12b60-186">Shows what would happen if `Uninstall-Package` cmdlet is run.</span></span> <span data-ttu-id="12b60-187">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="12b60-187">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="12b60-188">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="12b60-188">CommonParameters</span></span>

<span data-ttu-id="12b60-189">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="12b60-189">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="12b60-190">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12b60-190">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="12b60-191">入力</span><span class="sxs-lookup"><span data-stu-id="12b60-191">INPUTS</span></span>

### <span data-ttu-id="12b60-192">`Uninstall-Package` パイプラインからの **ソフトウェア id** オブジェクトを入力として受け入れます。</span><span class="sxs-lookup"><span data-stu-id="12b60-192">`Uninstall-Package` accepts **SoftwareIdentity** objects from the pipeline as input.</span></span>

## <span data-ttu-id="12b60-193">出力</span><span class="sxs-lookup"><span data-stu-id="12b60-193">OUTPUTS</span></span>

### <span data-ttu-id="12b60-194">`Uninstall-Package` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="12b60-194">`Uninstall-Package` doesn't generate any output.</span></span>

## <span data-ttu-id="12b60-195">注</span><span class="sxs-lookup"><span data-stu-id="12b60-195">NOTES</span></span>

<span data-ttu-id="12b60-196">コマンドにパッケージプロバイダーを含めると、コマンドレットで動的パラメーターを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="12b60-196">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="12b60-197">動的パラメーターは、パッケージプロバイダーに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="12b60-197">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="12b60-198">コマンドレットにより、 `Get-Help` コマンドレットのパラメーターセットが一覧表示され、プロバイダーのパラメーターセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="12b60-198">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="12b60-199">たとえば、には、、、 `Uninstall-Package` およびを含む **PowerShellGet** パラメーターが設定されてい `-NoPathUpdate` `AllowClobber` `SkipPublisherCheck` ます。</span><span class="sxs-lookup"><span data-stu-id="12b60-199">For example, `Uninstall-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="12b60-200">関連リンク</span><span class="sxs-lookup"><span data-stu-id="12b60-200">RELATED LINKS</span></span>

[<span data-ttu-id="12b60-201">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="12b60-201">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="12b60-202">Find-Package</span><span class="sxs-lookup"><span data-stu-id="12b60-202">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="12b60-203">Get-Package</span><span class="sxs-lookup"><span data-stu-id="12b60-203">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="12b60-204">Install-Package</span><span class="sxs-lookup"><span data-stu-id="12b60-204">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="12b60-205">Save-Package</span><span class="sxs-lookup"><span data-stu-id="12b60-205">Save-Package</span></span>](Save-Package.md)

