---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 05/22/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-package?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Package
ms.openlocfilehash: aad8b6f033674c65b4cc56708e09e5320bb046dd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213344"
---
# <span data-ttu-id="4d95d-103">Get-Package</span><span class="sxs-lookup"><span data-stu-id="4d95d-103">Get-Package</span></span>

## <span data-ttu-id="4d95d-104">概要</span><span class="sxs-lookup"><span data-stu-id="4d95d-104">SYNOPSIS</span></span>
<span data-ttu-id="4d95d-105">**PackageManagement** と共にインストールされたすべてのソフトウェアパッケージの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-105">Returns a list of all software packages that were installed with **PackageManagement** .</span></span>

## <span data-ttu-id="4d95d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4d95d-106">SYNTAX</span></span>

### <span data-ttu-id="4d95d-107">msi</span><span class="sxs-lookup"><span data-stu-id="4d95d-107">msi</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-AdditionalArguments <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="4d95d-108">プログラム</span><span class="sxs-lookup"><span data-stu-id="4d95d-108">Programs</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-IncludeWindowsInstaller] [-IncludeSystemComponent] [<CommonParameters>]
```

### <span data-ttu-id="4d95d-109">NuGet</span><span class="sxs-lookup"><span data-stu-id="4d95d-109">NuGet</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="4d95d-110">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="4d95d-110">PowerShellGet</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Scope <String>] [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions]
 [<CommonParameters>]
```

## <span data-ttu-id="4d95d-111">Description</span><span class="sxs-lookup"><span data-stu-id="4d95d-111">DESCRIPTION</span></span>

<span data-ttu-id="4d95d-112">`Get-Package`コマンドレットは、 **PackageManagement** を使用してインストールされたローカルコンピューター上のすべてのソフトウェアパッケージの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-112">The `Get-Package` cmdlet returns a list of all software packages on the local computer that were installed with **PackageManagement** .</span></span> <span data-ttu-id="4d95d-113">`Get-Package`またはコマンドまたはスクリプトの一部として実行することで、リモートコンピューターでを実行でき `Invoke-Command` `Enter-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="4d95d-113">You can run `Get-Package` on remote computers by running it as part of an `Invoke-Command` or `Enter-PSSession` command or script.</span></span>

## <span data-ttu-id="4d95d-114">例</span><span class="sxs-lookup"><span data-stu-id="4d95d-114">EXAMPLES</span></span>

### <span data-ttu-id="4d95d-115">例 1: インストールされているすべてのパッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="4d95d-115">Example 1: Get all installed packages</span></span>

<span data-ttu-id="4d95d-116">`Get-Package`コマンドレットは、ローカルコンピューターにインストールされているすべてのパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-116">The `Get-Package` cmdlet gets all packages that are installed on the local computer.</span></span>

```powershell
Get-Package
```

```Output
Name           Version      Source                                     ProviderName
----           -------      ------                                     ------------
posh-git       0.7.3        https://www.powershellgallery.com/api/v2   PowerShellGet
```

### <span data-ttu-id="4d95d-117">例 2: リモートコンピューターにインストールされているパッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="4d95d-117">Example 2: Get packages that are installed on a remote computer</span></span>

<span data-ttu-id="4d95d-118">このコマンドは、リモートコンピューター上の **PackageManagement** によってインストールされたパッケージの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-118">This command gets a list of packages that were installed by **PackageManagement** on a remote computer.</span></span> <span data-ttu-id="4d95d-119">このコマンドを実行すると、指定したユーザーのパスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="4d95d-119">This command prompts you to provide the specified user's password.</span></span>

```
PS> Invoke-Command -ComputerName Server01 -Credential CONTOSO\TestUser -ScriptBlock {Get-Package}
```

<span data-ttu-id="4d95d-120">`Invoke-Command`**ComputerName** パラメーターを使用して、リモートコンピューター **Server01** を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-120">`Invoke-Command` uses the **ComputerName** parameter to specify a remote computer, **Server01** .</span></span> <span data-ttu-id="4d95d-121">**Credential** パラメーターには、コンピューター上でコマンドを実行するためのアクセス許可を持つドメインとユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-121">The **Credential** parameter specifies a domain and user name with permissions to run commands on the computer.</span></span> <span data-ttu-id="4d95d-122">**ScriptBlock** パラメーターは、 `Get-Package` リモートコンピューター上でコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-122">The **ScriptBlock** parameter runs the `Get-Package` cmdlet on the remote computer.</span></span>

### <span data-ttu-id="4d95d-123">例 3: 指定されたプロバイダーのパッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="4d95d-123">Example 3: Get packages for a specified provider</span></span>

<span data-ttu-id="4d95d-124">このコマンドは、特定のプロバイダーからローカルコンピューターにインストールされているソフトウェアパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-124">This command gets software packages installed on the local computer from a specific provider.</span></span>

```powershell
Get-Package -ProviderName PowerShellGet -AllVersions
```

```Output
Name                  Version      Source                                     ProviderName
----                  -------      ------                                     ------------
PackageManagement     1.2.2        https://www.powershellgallery.com/api/v2   PowerShellGet
PackageManagement     1.3.1        https://www.powershellgallery.com/api/v2   PowerShellGet
posh-git              0.7.3        https://www.powershellgallery.com/api/v2   PowerShellGet
PowerShellGet         2.0.1        https://www.powershellgallery.com/api/v2   PowerShellGet
```

<span data-ttu-id="4d95d-125">`Get-Package`**ProviderName** パラメーターを使用して、特定のプロバイダー ( **PowerShellGet** ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-125">`Get-Package` uses the **ProviderName** parameter to specify a specific provider, **PowerShellGet** .</span></span>
<span data-ttu-id="4d95d-126">**すべてのバージョン** のパラメーターには、インストールされている各バージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d95d-126">The **All-Versions** parameter displays each version that is installed.</span></span>

### <span data-ttu-id="4d95d-127">例 4: 特定のパッケージの正確なバージョンを取得する</span><span class="sxs-lookup"><span data-stu-id="4d95d-127">Example 4: Get an exact version of a specific package</span></span>

<span data-ttu-id="4d95d-128">このコマンドは、インストールされているパッケージの特定のバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-128">This command gets a specific version of an installed package.</span></span> <span data-ttu-id="4d95d-129">パッケージの複数のバージョンをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4d95d-129">More than one version of a package can be installed.</span></span>

```powershell
Get-Package -Name PackageManagement -ProviderName PowerShellGet -RequiredVersion 1.3.1
```

```Output
Name                  Version      Source                                     ProviderName
----                  -------      ------                                     ------------
PackageManagement     1.3.1        https://www.powershellgallery.com/api/v2   PowerShellGet
```

<span data-ttu-id="4d95d-130">`Get-Package`**name** パラメーターを使用してパッケージ名を指定します。 **PackageManagement** です。</span><span class="sxs-lookup"><span data-stu-id="4d95d-130">`Get-Package` uses **Name** parameter to specify the package name, **PackageManagement** .</span></span> <span data-ttu-id="4d95d-131">**ProviderName** パラメーターは、プロバイダーの **PowerShellGet** を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-131">The **ProviderName** parameter specifies the provider, **PowerShellGet** .</span></span> <span data-ttu-id="4d95d-132">**必須バージョン** のパラメーターには、インストールされているバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-132">The **Required-Version** parameter specifies an installed version.</span></span>

### <span data-ttu-id="4d95d-133">例 5: パッケージをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="4d95d-133">Example 5: Uninstall a package</span></span>

<span data-ttu-id="4d95d-134">この例では、パッケージ情報を取得し、パッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="4d95d-134">This example gets package information and then uninstalls the package.</span></span>

```powershell
Get-Package -Name posh-git -RequiredVersion 0.7.3 | Uninstall-Package
```

<span data-ttu-id="4d95d-135">`Get-Package`**name** パラメーターを使用して、パッケージ名を指定 **します。**</span><span class="sxs-lookup"><span data-stu-id="4d95d-135">`Get-Package` uses the **Name** parameter to specify the package name, **posh-git** .</span></span> <span data-ttu-id="4d95d-136">**RequiredVersion** パラメーターは、パッケージの特定のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="4d95d-136">The **RequiredVersion** parameter is a specific version of the package.</span></span> <span data-ttu-id="4d95d-137">オブジェクトは、パイプラインを介してコマンドレットに送信され `Uninstall-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="4d95d-137">The object is sent down the pipeline to the `Uninstall-Package` cmdlet.</span></span> <span data-ttu-id="4d95d-138">`Uninstall-Package` パッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-138">`Uninstall-Package` removes the package.</span></span>

## <span data-ttu-id="4d95d-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4d95d-139">PARAMETERS</span></span>

### <span data-ttu-id="4d95d-140">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="4d95d-140">-AllowClobber</span></span>

<span data-ttu-id="4d95d-141">既存のコマンドとの競合に関する警告メッセージを上書きします。</span><span class="sxs-lookup"><span data-stu-id="4d95d-141">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="4d95d-142">モジュールによってインストールされたコマンドと同じ名前を持つ既存のコマンドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="4d95d-142">Overwrites existing commands that have the same name as commands being installed by a module.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d95d-143">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="4d95d-143">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="4d95d-144">結果にプレリリースとしてマークされているパッケージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d95d-144">Includes packages marked as a prerelease in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d95d-145">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="4d95d-145">-AllVersions</span></span>

<span data-ttu-id="4d95d-146">`Get-Package`パッケージの利用可能なすべてのバージョンをが返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-146">Indicates that `Get-Package` returns all available versions of the package.</span></span> <span data-ttu-id="4d95d-147">既定では、は、 `Get-Package` 使用可能な最新バージョンのみを返します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-147">By default, `Get-Package` only returns the newest available version.</span></span>

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

### <span data-ttu-id="4d95d-148">-Destination</span><span class="sxs-lookup"><span data-stu-id="4d95d-148">-Destination</span></span>

<span data-ttu-id="4d95d-149">抽出されたパッケージファイルを含むディレクトリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-149">Specifies the path to a directory that contains extracted package files.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d95d-150">-ExcludeVersion</span><span class="sxs-lookup"><span data-stu-id="4d95d-150">-ExcludeVersion</span></span>

<span data-ttu-id="4d95d-151">フォルダーパスのバージョン番号を除外するには、スイッチを指定します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-151">Switch to exclude the version number in the folder path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d95d-152">-Force</span><span class="sxs-lookup"><span data-stu-id="4d95d-152">-Force</span></span>

<span data-ttu-id="4d95d-153">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-153">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="4d95d-154">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="4d95d-154">-ForceBootstrap</span></span>

<span data-ttu-id="4d95d-155">が `Get-Package` **PackageManagement** を強制的にパッケージプロバイダーに自動的にインストールすることを示します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-155">Indicates that `Get-Package` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="4d95d-156">-InstallUpdate</span><span class="sxs-lookup"><span data-stu-id="4d95d-156">-InstallUpdate</span></span>

<span data-ttu-id="4d95d-157">このコマンドレットによって更新プログラムがインストールされることを示します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-157">Indicates that this cmdlet installs updates.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d95d-158">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="4d95d-158">-MaximumVersion</span></span>

<span data-ttu-id="4d95d-159">検索するパッケージの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-159">Specifies the maximum package version that you want to find.</span></span>

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

### <span data-ttu-id="4d95d-160">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="4d95d-160">-MinimumVersion</span></span>

<span data-ttu-id="4d95d-161">検索するパッケージの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-161">Specifies the minimum package version that you want to find.</span></span> <span data-ttu-id="4d95d-162">より新しいバージョンが使用可能な場合は、そのバージョンが返されます。</span><span class="sxs-lookup"><span data-stu-id="4d95d-162">If a higher version is available, that version is returned.</span></span>

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

### <span data-ttu-id="4d95d-163">-Name</span><span class="sxs-lookup"><span data-stu-id="4d95d-163">-Name</span></span>

<span data-ttu-id="4d95d-164">1つまたは複数のパッケージ名、またはワイルドカード文字を含むパッケージ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-164">Specifies one or more package names, or package names with wildcard characters.</span></span> <span data-ttu-id="4d95d-165">複数のパッケージ名はコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="4d95d-165">Separate multiple package names with commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="4d95d-166">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="4d95d-166">-NoPathUpdate</span></span>

<span data-ttu-id="4d95d-167">**Nopathupdate** はコマンドレットにのみ適用さ `Install-Script` れます。</span><span class="sxs-lookup"><span data-stu-id="4d95d-167">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="4d95d-168">**Nopathupdate** はプロバイダーによって追加される動的パラメーターであり、ではサポートされていません `Get-Package` 。</span><span class="sxs-lookup"><span data-stu-id="4d95d-168">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Get-Package`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d95d-169">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="4d95d-169">-PackageManagementProvider</span></span>

<span data-ttu-id="4d95d-170">パッケージ管理プロバイダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-170">Specifies the name of a package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d95d-171">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="4d95d-171">-ProviderName</span></span>

<span data-ttu-id="4d95d-172">1つまたは複数のパッケージプロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-172">Specifies one or more package provider names.</span></span> <span data-ttu-id="4d95d-173">複数のパッケージプロバイダー名をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="4d95d-173">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="4d95d-174">使用 `Get-PackageProvider` 可能なパッケージプロバイダーの一覧を取得するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-174">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4d95d-175">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="4d95d-175">-RequiredVersion</span></span>

<span data-ttu-id="4d95d-176">検索するパッケージの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-176">Specifies the exact version of the package to find.</span></span>

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

### <span data-ttu-id="4d95d-177">-スコープ</span><span class="sxs-lookup"><span data-stu-id="4d95d-177">-Scope</span></span>

<span data-ttu-id="4d95d-178">パッケージの検索範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-178">Specifies the search scope for the package.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet, PowerShellGet
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d95d-179">-SkipDependencies</span><span class="sxs-lookup"><span data-stu-id="4d95d-179">-SkipDependencies</span></span>

<span data-ttu-id="4d95d-180">パッケージの依存関係の検索をスキップするように指定するスイッチ。</span><span class="sxs-lookup"><span data-stu-id="4d95d-180">Switch that specifies to skip finding any package dependencies.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d95d-181">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="4d95d-181">-SkipPublisherCheck</span></span>

<span data-ttu-id="4d95d-182">インストールされているバージョンよりも新しいバージョンのパッケージを取得できます。</span><span class="sxs-lookup"><span data-stu-id="4d95d-182">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="4d95d-183">たとえば、信頼された発行元によってデジタル署名されているが新しいバージョンのパッケージはデジタル署名されていません。</span><span class="sxs-lookup"><span data-stu-id="4d95d-183">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d95d-184">-Type</span><span class="sxs-lookup"><span data-stu-id="4d95d-184">-Type</span></span>

<span data-ttu-id="4d95d-185">モジュール、スクリプト、またはいずれかを使用してパッケージを検索するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-185">Specifies whether to search for packages with a module, a script, or either.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d95d-186">-AdditionalArguments</span><span class="sxs-lookup"><span data-stu-id="4d95d-186">-AdditionalArguments</span></span>

<span data-ttu-id="4d95d-187">追加の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-187">Specifies additional arguments.</span></span>

```yaml
Type: System.String[]
Parameter Sets: msi
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d95d-188">-IncludeSystemComponent</span><span class="sxs-lookup"><span data-stu-id="4d95d-188">-IncludeSystemComponent</span></span>

<span data-ttu-id="4d95d-189">このコマンドレットが結果にシステムコンポーネントを含めることを示します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-189">Indicates that this cmdlet includes system components in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d95d-190">-IncludeWindowsInstaller</span><span class="sxs-lookup"><span data-stu-id="4d95d-190">-IncludeWindowsInstaller</span></span>

<span data-ttu-id="4d95d-191">このコマンドレットが結果に Windows インストーラーを含めることを示します。</span><span class="sxs-lookup"><span data-stu-id="4d95d-191">Indicates that this cmdlet includes the Windows Installer in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d95d-192">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4d95d-192">CommonParameters</span></span>

<span data-ttu-id="4d95d-193">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="4d95d-193">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4d95d-194">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d95d-194">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4d95d-195">入力</span><span class="sxs-lookup"><span data-stu-id="4d95d-195">INPUTS</span></span>

## <span data-ttu-id="4d95d-196">出力</span><span class="sxs-lookup"><span data-stu-id="4d95d-196">OUTPUTS</span></span>

### <span data-ttu-id="4d95d-197">ソフトウェア Id []</span><span class="sxs-lookup"><span data-stu-id="4d95d-197">SoftwareIdentity[]</span></span>

## <span data-ttu-id="4d95d-198">注</span><span class="sxs-lookup"><span data-stu-id="4d95d-198">NOTES</span></span>

<span data-ttu-id="4d95d-199">コマンドにパッケージプロバイダーを含めると、コマンドレットで動的パラメーターを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4d95d-199">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="4d95d-200">動的パラメーターは、パッケージプロバイダーに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="4d95d-200">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="4d95d-201">コマンドレットにより、 `Get-Help` コマンドレットのパラメーターセットが一覧表示され、プロバイダーのパラメーターセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d95d-201">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="4d95d-202">たとえば、には、、、 `Get-Package` およびを含む **PowerShellGet** パラメーターが設定されてい `-NoPathUpdate` `AllowClobber` `SkipPublisherCheck` ます。</span><span class="sxs-lookup"><span data-stu-id="4d95d-202">For example, `Get-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="4d95d-203">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4d95d-203">RELATED LINKS</span></span>

[<span data-ttu-id="4d95d-204">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="4d95d-204">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="4d95d-205">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="4d95d-205">Enter-PSSession</span></span>](../Microsoft.PowerShell.Core/Enter-PSSession.md)

[<span data-ttu-id="4d95d-206">Find-Package</span><span class="sxs-lookup"><span data-stu-id="4d95d-206">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="4d95d-207">Get-Help</span><span class="sxs-lookup"><span data-stu-id="4d95d-207">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="4d95d-208">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="4d95d-208">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="4d95d-209">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="4d95d-209">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="4d95d-210">Install-Package</span><span class="sxs-lookup"><span data-stu-id="4d95d-210">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="4d95d-211">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="4d95d-211">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="4d95d-212">Save-Package</span><span class="sxs-lookup"><span data-stu-id="4d95d-212">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="4d95d-213">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="4d95d-213">Uninstall-Package</span></span>](Uninstall-Package.md)
