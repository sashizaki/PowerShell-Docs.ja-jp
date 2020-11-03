---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 05/22/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-package?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Package
ms.openlocfilehash: 0b821f96606215d5d961329ebc69a1e5d3260763
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214843"
---
# <span data-ttu-id="fbe9f-103">Get-Package</span><span class="sxs-lookup"><span data-stu-id="fbe9f-103">Get-Package</span></span>

## <span data-ttu-id="fbe9f-104">概要</span><span class="sxs-lookup"><span data-stu-id="fbe9f-104">SYNOPSIS</span></span>
<span data-ttu-id="fbe9f-105">**PackageManagement** と共にインストールされたすべてのソフトウェアパッケージの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-105">Returns a list of all software packages that were installed with **PackageManagement** .</span></span>

## <span data-ttu-id="fbe9f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fbe9f-106">SYNTAX</span></span>

### <span data-ttu-id="fbe9f-107">NuGet</span><span class="sxs-lookup"><span data-stu-id="fbe9f-107">NuGet</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="fbe9f-108">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="fbe9f-108">PowerShellGet</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Scope <String>] [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions]
 [<CommonParameters>]
```

## <span data-ttu-id="fbe9f-109">Description</span><span class="sxs-lookup"><span data-stu-id="fbe9f-109">DESCRIPTION</span></span>

<span data-ttu-id="fbe9f-110">`Get-Package`コマンドレットは、 **PackageManagement** を使用してインストールされたローカルコンピューター上のすべてのソフトウェアパッケージの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-110">The `Get-Package` cmdlet returns a list of all software packages on the local computer that were installed with **PackageManagement** .</span></span> <span data-ttu-id="fbe9f-111">`Get-Package`またはコマンドまたはスクリプトの一部として実行することで、リモートコンピューターでを実行でき `Invoke-Command` `Enter-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-111">You can run `Get-Package` on remote computers by running it as part of an `Invoke-Command` or `Enter-PSSession` command or script.</span></span>

## <span data-ttu-id="fbe9f-112">例</span><span class="sxs-lookup"><span data-stu-id="fbe9f-112">EXAMPLES</span></span>

### <span data-ttu-id="fbe9f-113">例 1: インストールされているすべてのパッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="fbe9f-113">Example 1: Get all installed packages</span></span>

<span data-ttu-id="fbe9f-114">`Get-Package`コマンドレットは、ローカルコンピューターにインストールされているすべてのパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-114">The `Get-Package` cmdlet gets all packages that are installed on the local computer.</span></span>

```powershell
Get-Package
```

```Output
Name           Version      Source                                     ProviderName
----           -------      ------                                     ------------
posh-git       0.7.3        https://www.powershellgallery.com/api/v2   PowerShellGet
```

### <span data-ttu-id="fbe9f-115">例 2: リモートコンピューターにインストールされているパッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="fbe9f-115">Example 2: Get packages that are installed on a remote computer</span></span>

<span data-ttu-id="fbe9f-116">このコマンドは、リモートコンピューター上の **PackageManagement** によってインストールされたパッケージの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-116">This command gets a list of packages that were installed by **PackageManagement** on a remote computer.</span></span> <span data-ttu-id="fbe9f-117">このコマンドを実行すると、指定したユーザーのパスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-117">This command prompts you to provide the specified user's password.</span></span>

```
PS> Invoke-Command -ComputerName Server01 -Credential CONTOSO\TestUser -ScriptBlock {Get-Package}
```

<span data-ttu-id="fbe9f-118">`Invoke-Command`**ComputerName** パラメーターを使用して、リモートコンピューター **Server01** を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-118">`Invoke-Command` uses the **ComputerName** parameter to specify a remote computer, **Server01** .</span></span> <span data-ttu-id="fbe9f-119">**Credential** パラメーターには、コンピューター上でコマンドを実行するためのアクセス許可を持つドメインとユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-119">The **Credential** parameter specifies a domain and user name with permissions to run commands on the computer.</span></span> <span data-ttu-id="fbe9f-120">**ScriptBlock** パラメーターは、 `Get-Package` リモートコンピューター上でコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-120">The **ScriptBlock** parameter runs the `Get-Package` cmdlet on the remote computer.</span></span>

### <span data-ttu-id="fbe9f-121">例 3: 指定されたプロバイダーのパッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="fbe9f-121">Example 3: Get packages for a specified provider</span></span>

<span data-ttu-id="fbe9f-122">このコマンドは、特定のプロバイダーからローカルコンピューターにインストールされているソフトウェアパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-122">This command gets software packages installed on the local computer from a specific provider.</span></span>

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

<span data-ttu-id="fbe9f-123">`Get-Package`**ProviderName** パラメーターを使用して、特定のプロバイダー ( **PowerShellGet** ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-123">`Get-Package` uses the **ProviderName** parameter to specify a specific provider, **PowerShellGet** .</span></span>
<span data-ttu-id="fbe9f-124">**すべてのバージョン** のパラメーターには、インストールされている各バージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-124">The **All-Versions** parameter displays each version that is installed.</span></span>

### <span data-ttu-id="fbe9f-125">例 4: 特定のパッケージの正確なバージョンを取得する</span><span class="sxs-lookup"><span data-stu-id="fbe9f-125">Example 4: Get an exact version of a specific package</span></span>

<span data-ttu-id="fbe9f-126">このコマンドは、インストールされているパッケージの特定のバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-126">This command gets a specific version of an installed package.</span></span> <span data-ttu-id="fbe9f-127">パッケージの複数のバージョンをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-127">More than one version of a package can be installed.</span></span>

```powershell
Get-Package -Name PackageManagement -ProviderName PowerShellGet -RequiredVersion 1.3.1
```

```Output
Name                  Version      Source                                     ProviderName
----                  -------      ------                                     ------------
PackageManagement     1.3.1        https://www.powershellgallery.com/api/v2   PowerShellGet
```

<span data-ttu-id="fbe9f-128">`Get-Package`**name** パラメーターを使用してパッケージ名を指定します。 **PackageManagement** です。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-128">`Get-Package` uses **Name** parameter to specify the package name, **PackageManagement** .</span></span> <span data-ttu-id="fbe9f-129">**ProviderName** パラメーターは、プロバイダーの **PowerShellGet** を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-129">The **ProviderName** parameter specifies the provider, **PowerShellGet** .</span></span> <span data-ttu-id="fbe9f-130">**必須バージョン** のパラメーターには、インストールされているバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-130">The **Required-Version** parameter specifies an installed version.</span></span>

### <span data-ttu-id="fbe9f-131">例 5: パッケージをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="fbe9f-131">Example 5: Uninstall a package</span></span>

<span data-ttu-id="fbe9f-132">この例では、パッケージ情報を取得し、パッケージをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-132">This example gets package information and then uninstalls the package.</span></span>

```powershell
Get-Package -Name posh-git -RequiredVersion 0.7.3 | Uninstall-Package
```

<span data-ttu-id="fbe9f-133">`Get-Package`**name** パラメーターを使用して、パッケージ名を指定 **します。**</span><span class="sxs-lookup"><span data-stu-id="fbe9f-133">`Get-Package` uses the **Name** parameter to specify the package name, **posh-git** .</span></span> <span data-ttu-id="fbe9f-134">**RequiredVersion** パラメーターは、パッケージの特定のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-134">The **RequiredVersion** parameter is a specific version of the package.</span></span> <span data-ttu-id="fbe9f-135">オブジェクトは、パイプラインを介してコマンドレットに送信され `Uninstall-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-135">The object is sent down the pipeline to the `Uninstall-Package` cmdlet.</span></span> <span data-ttu-id="fbe9f-136">`Uninstall-Package` パッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-136">`Uninstall-Package` removes the package.</span></span>

## <span data-ttu-id="fbe9f-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fbe9f-137">PARAMETERS</span></span>

### <span data-ttu-id="fbe9f-138">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="fbe9f-138">-AllowClobber</span></span>

<span data-ttu-id="fbe9f-139">既存のコマンドとの競合に関する警告メッセージを上書きします。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-139">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="fbe9f-140">モジュールによってインストールされたコマンドと同じ名前を持つ既存のコマンドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-140">Overwrites existing commands that have the same name as commands being installed by a module.</span></span>

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

### <span data-ttu-id="fbe9f-141">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="fbe9f-141">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="fbe9f-142">結果にプレリリースとしてマークされているパッケージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-142">Includes packages marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="fbe9f-143">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="fbe9f-143">-AllVersions</span></span>

<span data-ttu-id="fbe9f-144">`Get-Package`パッケージの利用可能なすべてのバージョンをが返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-144">Indicates that `Get-Package` returns all available versions of the package.</span></span> <span data-ttu-id="fbe9f-145">既定では、は、 `Get-Package` 使用可能な最新バージョンのみを返します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-145">By default, `Get-Package` only returns the newest available version.</span></span>

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

### <span data-ttu-id="fbe9f-146">-Destination</span><span class="sxs-lookup"><span data-stu-id="fbe9f-146">-Destination</span></span>

<span data-ttu-id="fbe9f-147">抽出されたパッケージファイルを含むディレクトリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-147">Specifies the path to a directory that contains extracted package files.</span></span>

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

### <span data-ttu-id="fbe9f-148">-ExcludeVersion</span><span class="sxs-lookup"><span data-stu-id="fbe9f-148">-ExcludeVersion</span></span>

<span data-ttu-id="fbe9f-149">フォルダーパスのバージョン番号を除外するには、スイッチを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-149">Switch to exclude the version number in the folder path.</span></span>

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

### <span data-ttu-id="fbe9f-150">-Force</span><span class="sxs-lookup"><span data-stu-id="fbe9f-150">-Force</span></span>

<span data-ttu-id="fbe9f-151">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-151">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="fbe9f-152">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="fbe9f-152">-ForceBootstrap</span></span>

<span data-ttu-id="fbe9f-153">が `Get-Package` **PackageManagement** を強制的にパッケージプロバイダーに自動的にインストールすることを示します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-153">Indicates that `Get-Package` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="fbe9f-154">-InstallUpdate</span><span class="sxs-lookup"><span data-stu-id="fbe9f-154">-InstallUpdate</span></span>

<span data-ttu-id="fbe9f-155">このコマンドレットによって更新プログラムがインストールされることを示します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-155">Indicates that this cmdlet installs updates.</span></span>

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

### <span data-ttu-id="fbe9f-156">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="fbe9f-156">-MaximumVersion</span></span>

<span data-ttu-id="fbe9f-157">検索するパッケージの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-157">Specifies the maximum package version that you want to find.</span></span>

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

### <span data-ttu-id="fbe9f-158">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="fbe9f-158">-MinimumVersion</span></span>

<span data-ttu-id="fbe9f-159">検索するパッケージの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-159">Specifies the minimum package version that you want to find.</span></span> <span data-ttu-id="fbe9f-160">より新しいバージョンが使用可能な場合は、そのバージョンが返されます。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-160">If a higher version is available, that version is returned.</span></span>

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

### <span data-ttu-id="fbe9f-161">-Name</span><span class="sxs-lookup"><span data-stu-id="fbe9f-161">-Name</span></span>

<span data-ttu-id="fbe9f-162">1つまたは複数のパッケージ名、またはワイルドカード文字を含むパッケージ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-162">Specifies one or more package names, or package names with wildcard characters.</span></span> <span data-ttu-id="fbe9f-163">複数のパッケージ名はコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-163">Separate multiple package names with commas.</span></span>

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

### <span data-ttu-id="fbe9f-164">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="fbe9f-164">-NoPathUpdate</span></span>

<span data-ttu-id="fbe9f-165">**Nopathupdate** はコマンドレットにのみ適用さ `Install-Script` れます。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-165">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="fbe9f-166">**Nopathupdate** はプロバイダーによって追加される動的パラメーターであり、ではサポートされていません `Get-Package` 。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-166">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Get-Package`.</span></span>

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

### <span data-ttu-id="fbe9f-167">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="fbe9f-167">-PackageManagementProvider</span></span>

<span data-ttu-id="fbe9f-168">パッケージ管理プロバイダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-168">Specifies the name of a package management provider.</span></span>

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

### <span data-ttu-id="fbe9f-169">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="fbe9f-169">-ProviderName</span></span>

<span data-ttu-id="fbe9f-170">1つまたは複数のパッケージプロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-170">Specifies one or more package provider names.</span></span> <span data-ttu-id="fbe9f-171">複数のパッケージプロバイダー名をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-171">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="fbe9f-172">使用 `Get-PackageProvider` 可能なパッケージプロバイダーの一覧を取得するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-172">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

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

### <span data-ttu-id="fbe9f-173">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="fbe9f-173">-RequiredVersion</span></span>

<span data-ttu-id="fbe9f-174">検索するパッケージの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-174">Specifies the exact version of the package to find.</span></span>

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

### <span data-ttu-id="fbe9f-175">-スコープ</span><span class="sxs-lookup"><span data-stu-id="fbe9f-175">-Scope</span></span>

<span data-ttu-id="fbe9f-176">パッケージの検索範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-176">Specifies the search scope for the package.</span></span>

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

### <span data-ttu-id="fbe9f-177">-SkipDependencies</span><span class="sxs-lookup"><span data-stu-id="fbe9f-177">-SkipDependencies</span></span>

<span data-ttu-id="fbe9f-178">パッケージの依存関係の検索をスキップするように指定するスイッチ。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-178">Switch that specifies to skip finding any package dependencies.</span></span>

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

### <span data-ttu-id="fbe9f-179">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="fbe9f-179">-SkipPublisherCheck</span></span>

<span data-ttu-id="fbe9f-180">インストールされているバージョンよりも新しいバージョンのパッケージを取得できます。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-180">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="fbe9f-181">たとえば、信頼された発行元によってデジタル署名されているが新しいバージョンのパッケージはデジタル署名されていません。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-181">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

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

### <span data-ttu-id="fbe9f-182">-Type</span><span class="sxs-lookup"><span data-stu-id="fbe9f-182">-Type</span></span>

<span data-ttu-id="fbe9f-183">モジュール、スクリプト、またはいずれかを使用してパッケージを検索するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-183">Specifies whether to search for packages with a module, a script, or either.</span></span>

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

### <span data-ttu-id="fbe9f-184">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fbe9f-184">CommonParameters</span></span>

<span data-ttu-id="fbe9f-185">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fbe9f-186">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-186">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fbe9f-187">入力</span><span class="sxs-lookup"><span data-stu-id="fbe9f-187">INPUTS</span></span>

## <span data-ttu-id="fbe9f-188">出力</span><span class="sxs-lookup"><span data-stu-id="fbe9f-188">OUTPUTS</span></span>

### <span data-ttu-id="fbe9f-189">ソフトウェア Id []</span><span class="sxs-lookup"><span data-stu-id="fbe9f-189">SoftwareIdentity[]</span></span>

## <span data-ttu-id="fbe9f-190">注</span><span class="sxs-lookup"><span data-stu-id="fbe9f-190">NOTES</span></span>

<span data-ttu-id="fbe9f-191">コマンドにパッケージプロバイダーを含めると、コマンドレットで動的パラメーターを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-191">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="fbe9f-192">動的パラメーターは、パッケージプロバイダーに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-192">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="fbe9f-193">コマンドレットにより、 `Get-Help` コマンドレットのパラメーターセットが一覧表示され、プロバイダーのパラメーターセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-193">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="fbe9f-194">たとえば、には、、、 `Get-Package` およびを含む **PowerShellGet** パラメーターが設定されてい `-NoPathUpdate` `AllowClobber` `SkipPublisherCheck` ます。</span><span class="sxs-lookup"><span data-stu-id="fbe9f-194">For example, `Get-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="fbe9f-195">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fbe9f-195">RELATED LINKS</span></span>

[<span data-ttu-id="fbe9f-196">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="fbe9f-196">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="fbe9f-197">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="fbe9f-197">Enter-PSSession</span></span>](../Microsoft.PowerShell.Core/Enter-PSSession.md)

[<span data-ttu-id="fbe9f-198">Find-Package</span><span class="sxs-lookup"><span data-stu-id="fbe9f-198">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="fbe9f-199">Get-Help</span><span class="sxs-lookup"><span data-stu-id="fbe9f-199">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="fbe9f-200">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="fbe9f-200">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="fbe9f-201">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="fbe9f-201">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="fbe9f-202">Install-Package</span><span class="sxs-lookup"><span data-stu-id="fbe9f-202">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="fbe9f-203">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="fbe9f-203">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="fbe9f-204">Save-Package</span><span class="sxs-lookup"><span data-stu-id="fbe9f-204">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="fbe9f-205">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="fbe9f-205">Uninstall-Package</span></span>](Uninstall-Package.md)