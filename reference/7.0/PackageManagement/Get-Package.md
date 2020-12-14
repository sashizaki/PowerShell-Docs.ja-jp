---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 05/22/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-package?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Package
ms.openlocfilehash: bac0fe878a8dd370bda159d785740a4692ae6479
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890578"
---
# <span data-ttu-id="b77c4-103">Get-Package</span><span class="sxs-lookup"><span data-stu-id="b77c4-103">Get-Package</span></span>

## <span data-ttu-id="b77c4-104">概要</span><span class="sxs-lookup"><span data-stu-id="b77c4-104">SYNOPSIS</span></span>
<span data-ttu-id="b77c4-105">**PackageManagement** と共にインストールされたすべてのソフトウェアパッケージの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-105">Returns a list of all software packages that were installed with **PackageManagement**.</span></span>

## <span data-ttu-id="b77c4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b77c4-106">SYNTAX</span></span>

### <span data-ttu-id="b77c4-107">NuGet</span><span class="sxs-lookup"><span data-stu-id="b77c4-107">NuGet</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="b77c4-108">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="b77c4-108">PowerShellGet</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Scope <String>] [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions]
 [<CommonParameters>]
```

## <span data-ttu-id="b77c4-109">Description</span><span class="sxs-lookup"><span data-stu-id="b77c4-109">DESCRIPTION</span></span>

<span data-ttu-id="b77c4-110">`Get-Package`コマンドレットは、 **PackageManagement** を使用してインストールされたローカルコンピューター上のすべてのソフトウェアパッケージの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-110">The `Get-Package` cmdlet returns a list of all software packages on the local computer that were installed with **PackageManagement**.</span></span> <span data-ttu-id="b77c4-111">`Get-Package`またはコマンドまたはスクリプトの一部として実行することで、リモートコンピューターでを実行でき `Invoke-Command` `Enter-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="b77c4-111">You can run `Get-Package` on remote computers by running it as part of an `Invoke-Command` or `Enter-PSSession` command or script.</span></span>

## <span data-ttu-id="b77c4-112">例</span><span class="sxs-lookup"><span data-stu-id="b77c4-112">EXAMPLES</span></span>

### <span data-ttu-id="b77c4-113">例 1: インストールされているすべてのパッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="b77c4-113">Example 1: Get all installed packages</span></span>

<span data-ttu-id="b77c4-114">`Get-Package`コマンドレットは、ローカルコンピューターにインストールされているすべてのパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-114">The `Get-Package` cmdlet gets all packages that are installed on the local computer.</span></span>

```powershell
Get-Package
```

```Output
Name           Version      Source                                     ProviderName
----           -------      ------                                     ------------
posh-git       0.7.3        https://www.powershellgallery.com/api/v2   PowerShellGet
```

### <span data-ttu-id="b77c4-115">例 2: リモートコンピューターにインストールされているパッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="b77c4-115">Example 2: Get packages that are installed on a remote computer</span></span>

<span data-ttu-id="b77c4-116">このコマンドは、リモートコンピューター上の **PackageManagement** によってインストールされたパッケージの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-116">This command gets a list of packages that were installed by **PackageManagement** on a remote computer.</span></span> <span data-ttu-id="b77c4-117">このコマンドを実行すると、指定したユーザーのパスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="b77c4-117">This command prompts you to provide the specified user's password.</span></span>

```
PS> Invoke-Command -ComputerName Server01 -Credential CONTOSO\TestUser -ScriptBlock {Get-Package}
```

<span data-ttu-id="b77c4-118">`Invoke-Command`**ComputerName** パラメーターを使用して、リモートコンピューター **Server01** を指定します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-118">`Invoke-Command` uses the **ComputerName** parameter to specify a remote computer, **Server01**.</span></span> <span data-ttu-id="b77c4-119">**Credential** パラメーターには、コンピューター上でコマンドを実行するためのアクセス許可を持つドメインとユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-119">The **Credential** parameter specifies a domain and user name with permissions to run commands on the computer.</span></span> <span data-ttu-id="b77c4-120">**ScriptBlock** パラメーターは、 `Get-Package` リモートコンピューター上でコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-120">The **ScriptBlock** parameter runs the `Get-Package` cmdlet on the remote computer.</span></span>

### <span data-ttu-id="b77c4-121">例 3: 指定されたプロバイダーのパッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="b77c4-121">Example 3: Get packages for a specified provider</span></span>

<span data-ttu-id="b77c4-122">このコマンドは、特定のプロバイダーからローカルコンピューターにインストールされているソフトウェアパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-122">This command gets software packages installed on the local computer from a specific provider.</span></span>

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

<span data-ttu-id="b77c4-123">`Get-Package`**ProviderName** パラメーターを使用して、特定のプロバイダー ( **PowerShellGet**) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-123">`Get-Package` uses the **ProviderName** parameter to specify a specific provider, **PowerShellGet**.</span></span>
<span data-ttu-id="b77c4-124">**すべてのバージョン** のパラメーターには、インストールされている各バージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b77c4-124">The **All-Versions** parameter displays each version that is installed.</span></span>

### <span data-ttu-id="b77c4-125">例 4: 特定のパッケージの正確なバージョンを取得する</span><span class="sxs-lookup"><span data-stu-id="b77c4-125">Example 4: Get an exact version of a specific package</span></span>

<span data-ttu-id="b77c4-126">このコマンドは、インストールされているパッケージの特定のバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-126">This command gets a specific version of an installed package.</span></span> <span data-ttu-id="b77c4-127">パッケージの複数のバージョンをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="b77c4-127">More than one version of a package can be installed.</span></span>

```powershell
Get-Package -Name PackageManagement -ProviderName PowerShellGet -RequiredVersion 1.3.1
```

```Output
Name                  Version      Source                                     ProviderName
----                  -------      ------                                     ------------
PackageManagement     1.3.1        https://www.powershellgallery.com/api/v2   PowerShellGet
```

<span data-ttu-id="b77c4-128">`Get-Package`**name** パラメーターを使用してパッケージ名を指定します。 **PackageManagement** です。</span><span class="sxs-lookup"><span data-stu-id="b77c4-128">`Get-Package` uses **Name** parameter to specify the package name, **PackageManagement**.</span></span> <span data-ttu-id="b77c4-129">**ProviderName** パラメーターは、プロバイダーの **PowerShellGet** を指定します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-129">The **ProviderName** parameter specifies the provider, **PowerShellGet**.</span></span> <span data-ttu-id="b77c4-130">**必須バージョン** のパラメーターには、インストールされているバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-130">The **Required-Version** parameter specifies an installed version.</span></span>

### <span data-ttu-id="b77c4-131">例 5: パッケージをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="b77c4-131">Example 5: Uninstall a package</span></span>

<span data-ttu-id="b77c4-132">この例では、パッケージ情報を取得し、パッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="b77c4-132">This example gets package information and then uninstalls the package.</span></span>

```powershell
Get-Package -Name posh-git -RequiredVersion 0.7.3 | Uninstall-Package
```

<span data-ttu-id="b77c4-133">`Get-Package`**name** パラメーターを使用して、パッケージ名を指定 **します。**</span><span class="sxs-lookup"><span data-stu-id="b77c4-133">`Get-Package` uses the **Name** parameter to specify the package name, **posh-git**.</span></span> <span data-ttu-id="b77c4-134">**RequiredVersion** パラメーターは、パッケージの特定のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="b77c4-134">The **RequiredVersion** parameter is a specific version of the package.</span></span> <span data-ttu-id="b77c4-135">オブジェクトは、パイプラインを介してコマンドレットに送信され `Uninstall-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="b77c4-135">The object is sent down the pipeline to the `Uninstall-Package` cmdlet.</span></span> <span data-ttu-id="b77c4-136">`Uninstall-Package` パッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-136">`Uninstall-Package` removes the package.</span></span>

## <span data-ttu-id="b77c4-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b77c4-137">PARAMETERS</span></span>

### <span data-ttu-id="b77c4-138">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="b77c4-138">-AllowClobber</span></span>

<span data-ttu-id="b77c4-139">既存のコマンドとの競合に関する警告メッセージを上書きします。</span><span class="sxs-lookup"><span data-stu-id="b77c4-139">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="b77c4-140">モジュールによってインストールされたコマンドと同じ名前を持つ既存のコマンドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="b77c4-140">Overwrites existing commands that have the same name as commands being installed by a module.</span></span>

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

### <span data-ttu-id="b77c4-141">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="b77c4-141">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="b77c4-142">結果にプレリリースとしてマークされているパッケージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b77c4-142">Includes packages marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="b77c4-143">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="b77c4-143">-AllVersions</span></span>

<span data-ttu-id="b77c4-144">`Get-Package`パッケージの利用可能なすべてのバージョンをが返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-144">Indicates that `Get-Package` returns all available versions of the package.</span></span> <span data-ttu-id="b77c4-145">既定では、は、 `Get-Package` 使用可能な最新バージョンのみを返します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-145">By default, `Get-Package` only returns the newest available version.</span></span>

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

### <span data-ttu-id="b77c4-146">-Destination</span><span class="sxs-lookup"><span data-stu-id="b77c4-146">-Destination</span></span>

<span data-ttu-id="b77c4-147">抽出されたパッケージファイルを含むディレクトリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-147">Specifies the path to a directory that contains extracted package files.</span></span>

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

### <span data-ttu-id="b77c4-148">-ExcludeVersion</span><span class="sxs-lookup"><span data-stu-id="b77c4-148">-ExcludeVersion</span></span>

<span data-ttu-id="b77c4-149">フォルダーパスのバージョン番号を除外するには、スイッチを指定します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-149">Switch to exclude the version number in the folder path.</span></span>

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

### <span data-ttu-id="b77c4-150">-Force</span><span class="sxs-lookup"><span data-stu-id="b77c4-150">-Force</span></span>

<span data-ttu-id="b77c4-151">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-151">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="b77c4-152">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="b77c4-152">-ForceBootstrap</span></span>

<span data-ttu-id="b77c4-153">が `Get-Package` **PackageManagement** を強制的にパッケージプロバイダーに自動的にインストールすることを示します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-153">Indicates that `Get-Package` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="b77c4-154">-InstallUpdate</span><span class="sxs-lookup"><span data-stu-id="b77c4-154">-InstallUpdate</span></span>

<span data-ttu-id="b77c4-155">このコマンドレットによって更新プログラムがインストールされることを示します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-155">Indicates that this cmdlet installs updates.</span></span>

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

### <span data-ttu-id="b77c4-156">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="b77c4-156">-MaximumVersion</span></span>

<span data-ttu-id="b77c4-157">検索するパッケージの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-157">Specifies the maximum package version that you want to find.</span></span>

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

### <span data-ttu-id="b77c4-158">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="b77c4-158">-MinimumVersion</span></span>

<span data-ttu-id="b77c4-159">検索するパッケージの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-159">Specifies the minimum package version that you want to find.</span></span> <span data-ttu-id="b77c4-160">より新しいバージョンが使用可能な場合は、そのバージョンが返されます。</span><span class="sxs-lookup"><span data-stu-id="b77c4-160">If a higher version is available, that version is returned.</span></span>

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

### <span data-ttu-id="b77c4-161">-Name</span><span class="sxs-lookup"><span data-stu-id="b77c4-161">-Name</span></span>

<span data-ttu-id="b77c4-162">1つまたは複数のパッケージ名、またはワイルドカード文字を含むパッケージ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-162">Specifies one or more package names, or package names with wildcard characters.</span></span> <span data-ttu-id="b77c4-163">複数のパッケージ名はコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="b77c4-163">Separate multiple package names with commas.</span></span>

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

### <span data-ttu-id="b77c4-164">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="b77c4-164">-NoPathUpdate</span></span>

<span data-ttu-id="b77c4-165">**Nopathupdate** はコマンドレットにのみ適用さ `Install-Script` れます。</span><span class="sxs-lookup"><span data-stu-id="b77c4-165">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="b77c4-166">**Nopathupdate** はプロバイダーによって追加される動的パラメーターであり、ではサポートされていません `Get-Package` 。</span><span class="sxs-lookup"><span data-stu-id="b77c4-166">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Get-Package`.</span></span>

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

### <span data-ttu-id="b77c4-167">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="b77c4-167">-PackageManagementProvider</span></span>

<span data-ttu-id="b77c4-168">パッケージ管理プロバイダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-168">Specifies the name of a package management provider.</span></span>

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

### <span data-ttu-id="b77c4-169">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="b77c4-169">-ProviderName</span></span>

<span data-ttu-id="b77c4-170">1つまたは複数のパッケージプロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-170">Specifies one or more package provider names.</span></span> <span data-ttu-id="b77c4-171">複数のパッケージプロバイダー名をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="b77c4-171">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="b77c4-172">使用 `Get-PackageProvider` 可能なパッケージプロバイダーの一覧を取得するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-172">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

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

### <span data-ttu-id="b77c4-173">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="b77c4-173">-RequiredVersion</span></span>

<span data-ttu-id="b77c4-174">検索するパッケージの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-174">Specifies the exact version of the package to find.</span></span>

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

### <span data-ttu-id="b77c4-175">-スコープ</span><span class="sxs-lookup"><span data-stu-id="b77c4-175">-Scope</span></span>

<span data-ttu-id="b77c4-176">パッケージの検索範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-176">Specifies the search scope for the package.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b77c4-177">-SkipDependencies</span><span class="sxs-lookup"><span data-stu-id="b77c4-177">-SkipDependencies</span></span>

<span data-ttu-id="b77c4-178">パッケージの依存関係の検索をスキップするように指定するスイッチ。</span><span class="sxs-lookup"><span data-stu-id="b77c4-178">Switch that specifies to skip finding any package dependencies.</span></span>

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

### <span data-ttu-id="b77c4-179">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="b77c4-179">-SkipPublisherCheck</span></span>

<span data-ttu-id="b77c4-180">インストールされているバージョンよりも新しいバージョンのパッケージを取得できます。</span><span class="sxs-lookup"><span data-stu-id="b77c4-180">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="b77c4-181">たとえば、信頼された発行元によってデジタル署名されているが新しいバージョンのパッケージはデジタル署名されていません。</span><span class="sxs-lookup"><span data-stu-id="b77c4-181">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

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

### <span data-ttu-id="b77c4-182">-Type</span><span class="sxs-lookup"><span data-stu-id="b77c4-182">-Type</span></span>

<span data-ttu-id="b77c4-183">モジュール、スクリプト、またはいずれかを使用してパッケージを検索するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-183">Specifies whether to search for packages with a module, a script, or either.</span></span>

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

### <span data-ttu-id="b77c4-184">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b77c4-184">CommonParameters</span></span>

<span data-ttu-id="b77c4-185">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b77c4-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b77c4-186">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b77c4-186">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b77c4-187">入力</span><span class="sxs-lookup"><span data-stu-id="b77c4-187">INPUTS</span></span>

## <span data-ttu-id="b77c4-188">出力</span><span class="sxs-lookup"><span data-stu-id="b77c4-188">OUTPUTS</span></span>

### <span data-ttu-id="b77c4-189">ソフトウェア Id []</span><span class="sxs-lookup"><span data-stu-id="b77c4-189">SoftwareIdentity[]</span></span>

## <span data-ttu-id="b77c4-190">注</span><span class="sxs-lookup"><span data-stu-id="b77c4-190">NOTES</span></span>

<span data-ttu-id="b77c4-191">コマンドにパッケージプロバイダーを含めると、コマンドレットで動的パラメーターを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b77c4-191">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="b77c4-192">動的パラメーターは、パッケージプロバイダーに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="b77c4-192">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="b77c4-193">コマンドレットにより、 `Get-Help` コマンドレットのパラメーターセットが一覧表示され、プロバイダーのパラメーターセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b77c4-193">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="b77c4-194">たとえば、には、、、 `Get-Package` およびを含む **PowerShellGet** パラメーターが設定されてい `-NoPathUpdate` `AllowClobber` `SkipPublisherCheck` ます。</span><span class="sxs-lookup"><span data-stu-id="b77c4-194">For example, `Get-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b77c4-195">2020年4月の時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン1.0 と1.1 がサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b77c4-195">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="b77c4-196">TLS 1.2 以降を使用していない場合は、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-196">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="b77c4-197">次のコマンドを使用して、TLS 1.2 を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b77c4-197">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="b77c4-198">詳細については、PowerShell ブログの [お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b77c4-198">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="b77c4-199">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b77c4-199">RELATED LINKS</span></span>

[<span data-ttu-id="b77c4-200">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="b77c4-200">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="b77c4-201">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="b77c4-201">Enter-PSSession</span></span>](../Microsoft.PowerShell.Core/Enter-PSSession.md)

[<span data-ttu-id="b77c4-202">Find-Package</span><span class="sxs-lookup"><span data-stu-id="b77c4-202">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="b77c4-203">Get-Help</span><span class="sxs-lookup"><span data-stu-id="b77c4-203">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="b77c4-204">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="b77c4-204">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="b77c4-205">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="b77c4-205">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="b77c4-206">Install-Package</span><span class="sxs-lookup"><span data-stu-id="b77c4-206">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="b77c4-207">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="b77c4-207">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="b77c4-208">Save-Package</span><span class="sxs-lookup"><span data-stu-id="b77c4-208">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="b77c4-209">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="b77c4-209">Uninstall-Package</span></span>](Uninstall-Package.md)
