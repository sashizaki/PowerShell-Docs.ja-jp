---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/find-package?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Package
ms.openlocfilehash: f7c963b59a31b1b5edbf227e30415d6865cc14d7
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891068"
---
# <span data-ttu-id="a4159-103">Find-Package</span><span class="sxs-lookup"><span data-stu-id="a4159-103">Find-Package</span></span>

## <span data-ttu-id="a4159-104">概要</span><span class="sxs-lookup"><span data-stu-id="a4159-104">SYNOPSIS</span></span>
<span data-ttu-id="a4159-105">使用可能なパッケージソース内のソフトウェアパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="a4159-105">Finds software packages in available package sources.</span></span>

## <span data-ttu-id="a4159-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a4159-106">SYNTAX</span></span>

### <span data-ttu-id="a4159-107">NuGet</span><span class="sxs-lookup"><span data-stu-id="a4159-107">NuGet</span></span>

```
Find-Package [-IncludeDependencies] [-AllVersions] [-Source <String[]>] [-Credential <PSCredential>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String[]>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>]
 [-FilterOnTag <String[]>] [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="a4159-108">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="a4159-108">PowerShellGet</span></span>

```
Find-Package [-IncludeDependencies] [-AllVersions] [-Source <String[]>] [-Credential <PSCredential>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String[]>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-AllowPrereleaseVersions] [-PackageManagementProvider <String>]
 [-PublishLocation <String>] [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>]
 [-Type <String>] [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>]
 [-DscResource <String[]>] [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense]
 [<CommonParameters>]
```

## <span data-ttu-id="a4159-109">Description</span><span class="sxs-lookup"><span data-stu-id="a4159-109">DESCRIPTION</span></span>

<span data-ttu-id="a4159-110">`Find-Package` パッケージソースで利用可能なソフトウェアパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="a4159-110">`Find-Package` finds software packages that are available in package sources.</span></span> <span data-ttu-id="a4159-111">`Get-PackageProvider` と `Get-PackageSource` には、プロバイダーの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4159-111">`Get-PackageProvider` and `Get-PackageSource` display details about your providers.</span></span>

## <span data-ttu-id="a4159-112">例</span><span class="sxs-lookup"><span data-stu-id="a4159-112">EXAMPLES</span></span>

### <span data-ttu-id="a4159-113">例 1: パッケージプロバイダーから利用可能なすべてのパッケージを検索する</span><span class="sxs-lookup"><span data-stu-id="a4159-113">Example 1: Find all available packages from a package provider</span></span>

<span data-ttu-id="a4159-114">このコマンドは、登録されているギャラリー内の使用可能なすべての PowerShell モジュールパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="a4159-114">This command finds all available PowerShell module packages in a registered gallery.</span></span> <span data-ttu-id="a4159-115">`Get-PackageProvider`プロバイダー名を取得するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="a4159-115">Use `Get-PackageProvider` to get the provider name.</span></span>

```
Find-Package -ProviderName NuGet
```

```Output
Name               Version   Source     Summary
----               -------   ------     -------
NUnit              3.11.0    MyNuGet    NUnit is a unit-testing framework for all .NET langua...
Newtonsoft.Json    12.0.1    MyNuGet    Json.NET is a popular high-performance JSON framework...
EntityFramework    6.2.0     MyNuGet    Entity Framework is Microsoft's recommended data acce...
MySql.Data         8.0.15    MyNuGet    MySql.Data.MySqlClient .Net Core Class Library
bootstrap          4.3.1     MyNuGet    Bootstrap framework in CSS. Includes fonts and JavaSc...
NuGet.Core         2.14.0    MyNuGet    NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="a4159-116">`Find-Package`**プロバイダーパラメーターを** 使用して、プロバイダーの **NuGet** を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-116">`Find-Package` uses the **Provider** parameter to specify the provider **NuGet**.</span></span>

### <span data-ttu-id="a4159-117">例 2: パッケージソースからパッケージを検索する</span><span class="sxs-lookup"><span data-stu-id="a4159-117">Example 2: Find a package from a package source</span></span>

<span data-ttu-id="a4159-118">このコマンドは、指定されたパッケージソースからパッケージの最新バージョンを検索します。</span><span class="sxs-lookup"><span data-stu-id="a4159-118">This command finds the newest version of a package from a specified package source.</span></span> <span data-ttu-id="a4159-119">パッケージソースが指定されていない場合、は、 `Find-Package` インストールされている各パッケージプロバイダーとそのパッケージソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="a4159-119">If a package source isn't provided, `Find-Package` searches each installed package provider and its package sources.</span></span> <span data-ttu-id="a4159-120">を使用し `Get-PackageSource` て、ソース名を取得します。</span><span class="sxs-lookup"><span data-stu-id="a4159-120">Use `Get-PackageSource` to get the source name.</span></span>

```
Find-Package -Name NuGet.Core -Source MyNuGet
```

```Output
Name         Version   Source    Summary
----         -------   ------    -------
NuGet.Core   2.14.0    MyNuGet   NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="a4159-121">`Find-Package`**name** パラメーターを使用して、パッケージ名として「 **NuGet. Core**」を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-121">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="a4159-122">**Source** パラメーターは、 **MyNuGet** でパッケージを検索するように指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-122">The **Source** parameter specifies to search for the package in **MyNuGet**.</span></span>

### <span data-ttu-id="a4159-123">例 3: パッケージのすべてのバージョンを検索する</span><span class="sxs-lookup"><span data-stu-id="a4159-123">Example 3: Find all versions of a package</span></span>

<span data-ttu-id="a4159-124">このコマンドは、指定されたプロバイダーから、使用可能なすべてのパッケージバージョンを検索します。</span><span class="sxs-lookup"><span data-stu-id="a4159-124">This command finds all available package versions from a specified provider.</span></span>

```
Find-Package -Name NuGet.Core -Source MyNuGet -AllVersions
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.14.0           MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.14.0-rtm-832   MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.13.0           MyNuGet      NuGet.Core is the core framework assembly for NuGet...
...
NuGet.Core    1.1.229.159      MyNuGet      NuGet.Core is the core framework assembly for NuGet...
Nuget.Core    1.0.1120.104     MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="a4159-125">`Find-Package`**Name** パラメーターを使用して、パッケージの **NuGet. Core** を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-125">`Find-Package` uses the **Name** parameter to specify the package **NuGet.Core**.</span></span> <span data-ttu-id="a4159-126">**ProviderName** パラメーターは、 **MyNuGet** でパッケージを検索するように指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-126">The **ProviderName** parameter specifies to search for the package in **MyNuGet**.</span></span> <span data-ttu-id="a4159-127">**AllVersions** は、使用可能なすべてのバージョンが返されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-127">**AllVersions** specifies that all available versions are returned.</span></span>

### <span data-ttu-id="a4159-128">例 4: 特定の名前とバージョンを含むパッケージを検索する</span><span class="sxs-lookup"><span data-stu-id="a4159-128">Example 4: Find a package with a specific name and version</span></span>

<span data-ttu-id="a4159-129">このコマンドは、指定されたプロバイダーから特定のパッケージのバージョンを検索します。</span><span class="sxs-lookup"><span data-stu-id="a4159-129">This command finds a specific package version from a specified provider.</span></span>

```
Find-Package -Name NuGet.Core -ProviderName NuGet -RequiredVersion 2.9.0
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.9.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="a4159-130">`Find-Package`**name** パラメーターを使用して、パッケージ名として「 **NuGet. Core**」を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-130">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="a4159-131">**ProviderName** パラメーターは、 **NuGet** でパッケージを検索するように指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-131">The **ProviderName** parameter specifies to search for the package in **NuGet**.</span></span> <span data-ttu-id="a4159-132">**RequiredVersion** バージョン **2.9.0** のみが返されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-132">**RequiredVersion** specifies that only version **2.9.0** is returned.</span></span>

### <span data-ttu-id="a4159-133">例 5: バージョンの範囲内でパッケージを検索する</span><span class="sxs-lookup"><span data-stu-id="a4159-133">Example 5: Find packages within a range of versions</span></span>

<span data-ttu-id="a4159-134">このコマンドは、指定されたパッケージのバージョンの範囲を検索します。</span><span class="sxs-lookup"><span data-stu-id="a4159-134">This command finds a range of versions for a specified package.</span></span>

```
Find-Package -Name NuGet.Core -ProviderName NuGet -MinimumVersion 2.7.0 -MaximumVersion 2.9.0 -AllVersions
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.9.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.8.6            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.8.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.7.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="a4159-135">`Find-Package`**name** パラメーターを使用して、パッケージ名として「 **NuGet. Core**」を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-135">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="a4159-136">**ProviderName** パラメーターは、 **NuGet** でパッケージを検索するように指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-136">The **ProviderName** parameter specifies to search for the package in **NuGet**.</span></span> <span data-ttu-id="a4159-137">**MinimumVersion** **2.7.0** の最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-137">**MinimumVersion** specifies the lowest version **2.7.0**.</span></span> <span data-ttu-id="a4159-138">**MaximumVersion** 最大バージョン **2.9.0** を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-138">**MaximumVersion** specifies the highest version **2.9.0**.</span></span>
<span data-ttu-id="a4159-139">**AllVersions** は、最小値と最大値によって指定された範囲が返されることを決定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-139">**AllVersions** determines the range is returned as specified by the minimum and maximum.</span></span>

### <span data-ttu-id="a4159-140">例 6: ファイルシステムからパッケージを検索する</span><span class="sxs-lookup"><span data-stu-id="a4159-140">Example 6: Find a package from a file system</span></span>

<span data-ttu-id="a4159-141">このコマンド `.nupkg` は、ローカルコンピューターに格納されているファイル拡張子を持つパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="a4159-141">This command finds packages with the file extension `.nupkg` that are stored on the local computer.</span></span>
<span data-ttu-id="a4159-142">ファイルは、 **NuGet** などのギャラリーからダウンロードされたパッケージです。</span><span class="sxs-lookup"><span data-stu-id="a4159-142">The files are packages downloaded from a gallery such as the **NuGet**.</span></span>

```
PS> Find-Package -Source C:\LocalPkg
```

```Output
Name                 Version    Source           Summary
----                 -------    ------           -------
Microsoft.Web.Xdt    3.0.0      C:\LocalPkg\     Microsoft Xml Document Transformation (XDT)...
NuGet.Core           2.14.0     C:\LocalPkg\     NuGet.Core is the core framework assembly...
```

## <span data-ttu-id="a4159-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a4159-143">PARAMETERS</span></span>

### <span data-ttu-id="a4159-144">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="a4159-144">-AcceptLicense</span></span>

<span data-ttu-id="a4159-145">パッケージで必要な場合は、使用許諾契約書を自動的に受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a4159-145">Automatically accepts a license agreement if the package requires it.</span></span>

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

### <span data-ttu-id="a4159-146">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="a4159-146">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="a4159-147">結果にプレリリースとしてマークされているパッケージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a4159-147">Includes packages marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="a4159-148">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="a4159-148">-AllVersions</span></span>

<span data-ttu-id="a4159-149">`Find-Package`パッケージの利用可能なすべてのバージョンをが返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="a4159-149">Indicates that `Find-Package` returns all available versions of the package.</span></span> <span data-ttu-id="a4159-150">既定では、は、 `Find-Package` 使用可能な最新バージョンのみを返します。</span><span class="sxs-lookup"><span data-stu-id="a4159-150">By default, `Find-Package` only returns the newest available version.</span></span>

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

### <span data-ttu-id="a4159-151">-Command</span><span class="sxs-lookup"><span data-stu-id="a4159-151">-Command</span></span>

<span data-ttu-id="a4159-152">によって検索されるコマンドの配列を指定し `Find-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="a4159-152">Specifies an array of commands searched by `Find-Package`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a4159-153">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="a4159-153">-ConfigFile</span></span>

<span data-ttu-id="a4159-154">構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-154">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="a4159-155">-Contains</span><span class="sxs-lookup"><span data-stu-id="a4159-155">-Contains</span></span>

<span data-ttu-id="a4159-156">`Find-Package` オブジェクトのプロパティ値内のいずれかの項目が指定した値と完全に一致する場合は、オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="a4159-156">`Find-Package` gets objects if any item in the object's property values are an exact match for the specified value.</span></span>

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

### <span data-ttu-id="a4159-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="a4159-157">-Credential</span></span>

<span data-ttu-id="a4159-158">パッケージを検索するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-158">Specifies a user account that has permission to search for packages.</span></span>

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

### <span data-ttu-id="a4159-159">-DscResource</span><span class="sxs-lookup"><span data-stu-id="a4159-159">-DscResource</span></span>

<span data-ttu-id="a4159-160">このコマンドレットが検索する Desired State Configuration (DSC) リソースの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-160">Specifies an array of Desired State Configuration (DSC) resources that this cmdlet searches.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a4159-161">-Filter</span><span class="sxs-lookup"><span data-stu-id="a4159-161">-Filter</span></span>

<span data-ttu-id="a4159-162">**名前** と **説明** のプロパティ内で検索する用語を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-162">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

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

### <span data-ttu-id="a4159-163">-FilterOnTag</span><span class="sxs-lookup"><span data-stu-id="a4159-163">-FilterOnTag</span></span>

<span data-ttu-id="a4159-164">結果をフィルター処理するタグを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-164">Specifies the tag that filters the results.</span></span> <span data-ttu-id="a4159-165">指定されたタグを含まない結果は除外されます。</span><span class="sxs-lookup"><span data-stu-id="a4159-165">Results that don't contain the specified tag are excluded.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a4159-166">-Force</span><span class="sxs-lookup"><span data-stu-id="a4159-166">-Force</span></span>

<span data-ttu-id="a4159-167">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a4159-167">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="a4159-168">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="a4159-168">-ForceBootstrap</span></span>

<span data-ttu-id="a4159-169">が `Find-Package` **PackageManagement** を強制的にパッケージプロバイダーに自動的にインストールすることを示します。</span><span class="sxs-lookup"><span data-stu-id="a4159-169">Indicates that `Find-Package` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="a4159-170">-ヘッダー</span><span class="sxs-lookup"><span data-stu-id="a4159-170">-Headers</span></span>

<span data-ttu-id="a4159-171">パッケージのヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-171">Specifies the headers for the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a4159-172">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="a4159-172">-IncludeDependencies</span></span>

<span data-ttu-id="a4159-173">このコマンドレットが結果にパッケージの依存関係を含むことを示します。</span><span class="sxs-lookup"><span data-stu-id="a4159-173">Indicates that this cmdlet includes package dependencies in the results.</span></span>

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

### <span data-ttu-id="a4159-174">-インクルード</span><span class="sxs-lookup"><span data-stu-id="a4159-174">-Includes</span></span>

<span data-ttu-id="a4159-175">`Find-Package`がカテゴリ内のすべてのパッケージを検索するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-175">Specifies whether `Find-Package` should find all packages within a category.</span></span>

<span data-ttu-id="a4159-176">許容される値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a4159-176">The accepted values are as follows:</span></span>

- <span data-ttu-id="a4159-177">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="a4159-177">Cmdlet</span></span>
- <span data-ttu-id="a4159-178">DscResource</span><span class="sxs-lookup"><span data-stu-id="a4159-178">DscResource</span></span>
- <span data-ttu-id="a4159-179">機能</span><span class="sxs-lookup"><span data-stu-id="a4159-179">Function</span></span>
- <span data-ttu-id="a4159-180">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="a4159-180">RoleCapability</span></span>
- <span data-ttu-id="a4159-181">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="a4159-181">Workflow</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:
Accepted values: Cmdlet, DscResource, Function, RoleCapability, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a4159-182">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="a4159-182">-MaximumVersion</span></span>

<span data-ttu-id="a4159-183">検索するパッケージの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-183">Specifies the maximum package version that you want to find.</span></span>

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

### <span data-ttu-id="a4159-184">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="a4159-184">-MinimumVersion</span></span>

<span data-ttu-id="a4159-185">検索するパッケージの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-185">Specifies the minimum package version that you want to find.</span></span> <span data-ttu-id="a4159-186">より新しいバージョンが使用可能な場合は、そのバージョンが返されます。</span><span class="sxs-lookup"><span data-stu-id="a4159-186">If a higher version is available, that version is returned.</span></span>

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

### <span data-ttu-id="a4159-187">-Name</span><span class="sxs-lookup"><span data-stu-id="a4159-187">-Name</span></span>

<span data-ttu-id="a4159-188">1つまたは複数のパッケージ名、またはワイルドカード文字を含むパッケージ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-188">Specifies one or more package names, or package names with wildcard characters.</span></span> <span data-ttu-id="a4159-189">複数のパッケージ名はコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="a4159-189">Separate multiple package names with commas.</span></span>

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

### <span data-ttu-id="a4159-190">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="a4159-190">-PackageManagementProvider</span></span>

<span data-ttu-id="a4159-191">パッケージ管理プロバイダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-191">Specifies the name of a package management provider.</span></span>

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

### <span data-ttu-id="a4159-192">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="a4159-192">-ProviderName</span></span>

<span data-ttu-id="a4159-193">1つまたは複数のパッケージプロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-193">Specifies one or more package provider names.</span></span> <span data-ttu-id="a4159-194">複数のパッケージプロバイダー名をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="a4159-194">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="a4159-195">使用 `Get-PackageProvider` 可能なパッケージプロバイダーの一覧を取得するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="a4159-195">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

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

### <span data-ttu-id="a4159-196">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="a4159-196">-Proxy</span></span>

<span data-ttu-id="a4159-197">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-197">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="a4159-198">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="a4159-198">-ProxyCredential</span></span>

<span data-ttu-id="a4159-199">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-199">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="a4159-200">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="a4159-200">-PublishLocation</span></span>

<span data-ttu-id="a4159-201">パッケージを公開する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-201">Specifies a location for publishing the package.</span></span>

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

### <span data-ttu-id="a4159-202">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="a4159-202">-RequiredVersion</span></span>

<span data-ttu-id="a4159-203">検索するパッケージの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-203">Specifies an exact package version that you want to find.</span></span>

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

### <span data-ttu-id="a4159-204">-Find-rolecapability</span><span class="sxs-lookup"><span data-stu-id="a4159-204">-RoleCapability</span></span>

<span data-ttu-id="a4159-205">ロール機能の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-205">Specifies an array of role capabilities.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a4159-206">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="a4159-206">-ScriptPublishLocation</span></span>

<span data-ttu-id="a4159-207">パッケージのスクリプト発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-207">Specifies a script publishing location for the package.</span></span>

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

### <span data-ttu-id="a4159-208">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="a4159-208">-ScriptSourceLocation</span></span>

<span data-ttu-id="a4159-209">スクリプトソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-209">Specifies a script source location.</span></span>

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

### <span data-ttu-id="a4159-210">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="a4159-210">-SkipValidate</span></span>

<span data-ttu-id="a4159-211">パッケージの資格情報の検証をスキップするスイッチ。</span><span class="sxs-lookup"><span data-stu-id="a4159-211">Switch that skips package credential validation.</span></span>

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

### <span data-ttu-id="a4159-212">-Source</span><span class="sxs-lookup"><span data-stu-id="a4159-212">-Source</span></span>

<span data-ttu-id="a4159-213">1つまたは複数のパッケージソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-213">Specifies one or more package sources.</span></span> <span data-ttu-id="a4159-214">使用 `Get-PackageSource` 可能なパッケージソースの一覧を取得するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="a4159-214">Use `Get-PackageSource` to get a list of available package sources.</span></span> <span data-ttu-id="a4159-215">ファイルシステムディレクトリは、ダウンロードパッケージのソースとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4159-215">A file system directory can be used as a source for download packages.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a4159-216">-Tag</span><span class="sxs-lookup"><span data-stu-id="a4159-216">-Tag</span></span>

<span data-ttu-id="a4159-217">パッケージメタデータ内で検索する1つ以上の文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-217">Specifies one or more strings to search for in the package metadata.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a4159-218">-Type</span><span class="sxs-lookup"><span data-stu-id="a4159-218">-Type</span></span>

<span data-ttu-id="a4159-219">モジュール、スクリプト、またはいずれかを使用してパッケージを検索するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4159-219">Specifies whether to search for packages with a module, a script, or either.</span></span>

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

### <span data-ttu-id="a4159-220">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a4159-220">CommonParameters</span></span>

<span data-ttu-id="a4159-221">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a4159-221">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a4159-222">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4159-222">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a4159-223">入力</span><span class="sxs-lookup"><span data-stu-id="a4159-223">INPUTS</span></span>

### <span data-ttu-id="a4159-224">なし</span><span class="sxs-lookup"><span data-stu-id="a4159-224">None</span></span>

<span data-ttu-id="a4159-225">`Find-Package` は、パイプラインからの入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="a4159-225">`Find-Package` doesn't accept input from the pipeline.</span></span>

## <span data-ttu-id="a4159-226">出力</span><span class="sxs-lookup"><span data-stu-id="a4159-226">OUTPUTS</span></span>

### <span data-ttu-id="a4159-227">ソフトウェアの識別 []</span><span class="sxs-lookup"><span data-stu-id="a4159-227">SoftwareIdentify[]</span></span>

<span data-ttu-id="a4159-228">`Find-Package`**ソフトウェア id** オブジェクトを出力します。</span><span class="sxs-lookup"><span data-stu-id="a4159-228">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

## <span data-ttu-id="a4159-229">注</span><span class="sxs-lookup"><span data-stu-id="a4159-229">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4159-230">2020年4月の時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン1.0 と1.1 がサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a4159-230">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="a4159-231">TLS 1.2 以降を使用していない場合は、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="a4159-231">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="a4159-232">次のコマンドを使用して、TLS 1.2 を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a4159-232">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="a4159-233">詳細については、PowerShell ブログの [お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4159-233">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="a4159-234">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a4159-234">RELATED LINKS</span></span>

[<span data-ttu-id="a4159-235">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="a4159-235">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="a4159-236">Get-Package</span><span class="sxs-lookup"><span data-stu-id="a4159-236">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="a4159-237">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="a4159-237">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="a4159-238">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="a4159-238">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="a4159-239">Install-Package</span><span class="sxs-lookup"><span data-stu-id="a4159-239">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="a4159-240">Save-Package</span><span class="sxs-lookup"><span data-stu-id="a4159-240">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="a4159-241">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="a4159-241">Uninstall-Package</span></span>](Uninstall-Package.md)
