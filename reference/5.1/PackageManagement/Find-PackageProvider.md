---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/find-packageprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-PackageProvider
ms.openlocfilehash: dc4450e1c9f8b9506ee57948e4cec2d0541c181d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213347"
---
# <span data-ttu-id="e886d-103">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="e886d-103">Find-PackageProvider</span></span>

## <span data-ttu-id="e886d-104">概要</span><span class="sxs-lookup"><span data-stu-id="e886d-104">SYNOPSIS</span></span>
<span data-ttu-id="e886d-105">インストールに使用できる Package Management パッケージプロバイダーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="e886d-105">Returns a list of Package Management package providers available for installation.</span></span>

## <span data-ttu-id="e886d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e886d-106">SYNTAX</span></span>

```
Find-PackageProvider [[-Name] <String[]>] [-AllVersions] [-Source <String[]>] [-IncludeDependencies]
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="e886d-107">Description</span><span class="sxs-lookup"><span data-stu-id="e886d-107">DESCRIPTION</span></span>

<span data-ttu-id="e886d-108">**検索 PackageProvider** コマンドレットは、PowerShellGet に登録されているパッケージソースで使用できる一致する PackageManagement プロバイダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="e886d-108">The **Find-PackageProvider** cmdlet finds matching PackageManagement providers that are available in package sources registered with PowerShellGet.</span></span>
<span data-ttu-id="e886d-109">これらは、Install-PackageProvider コマンドレットを使用したインストールに使用可能なパッケージ プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="e886d-109">These are package providers available for installation with the Install-PackageProvider cmdlet.</span></span>
<span data-ttu-id="e886d-110">既定では、これには、 **PackageManagement** タグと **Provider** タグを持つ PowerShell ギャラリーで使用できるモジュールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e886d-110">By default, this includes modules available in the PowerShell Gallery with the **PackageManagement** and **Provider** tags.</span></span>

<span data-ttu-id="e886d-111">**検索-PackageProvider** は、Package Management Azure Blob ストアで利用できる一致する Package Management プロバイダーも検索します。</span><span class="sxs-lookup"><span data-stu-id="e886d-111">**Find-PackageProvider** also finds matching Package Management providers that are available in the Package Management Azure Blob store.</span></span>
<span data-ttu-id="e886d-112">ブートストラッププロバイダーを使用して、それらを検索してインストールします。</span><span class="sxs-lookup"><span data-stu-id="e886d-112">Use the bootstrapper provider to find and install them.</span></span>

## <span data-ttu-id="e886d-113">例</span><span class="sxs-lookup"><span data-stu-id="e886d-113">EXAMPLES</span></span>

### <span data-ttu-id="e886d-114">例 1: 使用可能なすべてのパッケージプロバイダーを検索する</span><span class="sxs-lookup"><span data-stu-id="e886d-114">Example 1: Find all available package providers</span></span>

```
PS C:\> Find-PackageProvider
```

<span data-ttu-id="e886d-115">このコマンドは、Package Management でサポートされているリポジトリで使用可能なすべてのパッケージプロバイダーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="e886d-115">This command gets a list of all package providers that are available on the repositories supported by Package Management.</span></span>
<span data-ttu-id="e886d-116">既定では、これらのパッケージプロバイダーは、PowerShell ギャラリーと Package Management ブートストラップアプリケーションを使用して入手できます。</span><span class="sxs-lookup"><span data-stu-id="e886d-116">By default, those package providers are available on the PowerShell Gallery and by using the Package Management bootstrapping application.</span></span>

### <span data-ttu-id="e886d-117">例 2: プロバイダーのすべてのバージョンを検索する</span><span class="sxs-lookup"><span data-stu-id="e886d-117">Example 2: Find all versions of a provider</span></span>

```
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
```

<span data-ttu-id="e886d-118">このコマンドは、Nuget という名前のパッケージプロバイダーのすべてのバージョンを検索します。</span><span class="sxs-lookup"><span data-stu-id="e886d-118">This command finds all versions of the package provider named Nuget.</span></span>

### <span data-ttu-id="e886d-119">例 3: 指定されたソースからプロバイダーを検索する</span><span class="sxs-lookup"><span data-stu-id="e886d-119">Example 3: Find a provider from a specified source</span></span>

```
PS C:\> Find-PackageProvider -Name "Gistprovider" -Source "PSGallery"
```

<span data-ttu-id="e886d-120">このコマンドは、指定されたパッケージソースを使用して利用可能なパッケージプロバイダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="e886d-120">This command finds a package provider available by using a specified package source.</span></span>

## <span data-ttu-id="e886d-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e886d-121">PARAMETERS</span></span>

### <span data-ttu-id="e886d-122">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="e886d-122">-AllVersions</span></span>

<span data-ttu-id="e886d-123">このコマンドレットが、使用可能なすべてのバージョンのパッケージプロバイダーを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="e886d-123">Indicates that this cmdlet returns all available versions of the package provider.</span></span>
<span data-ttu-id="e886d-124">既定では、 **検索-PackageProvider** は、利用可能な最新バージョンのみを返します。</span><span class="sxs-lookup"><span data-stu-id="e886d-124">By default, **Find-PackageProvider** only returns the newest available version.</span></span>

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

### <span data-ttu-id="e886d-125">-Credential</span><span class="sxs-lookup"><span data-stu-id="e886d-125">-Credential</span></span>

<span data-ttu-id="e886d-126">パッケージプロバイダーを検索するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e886d-126">Specifies a user account that has permission to search for package providers.</span></span>

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

### <span data-ttu-id="e886d-127">-Force</span><span class="sxs-lookup"><span data-stu-id="e886d-127">-Force</span></span>

<span data-ttu-id="e886d-128">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e886d-128">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="e886d-129">現時点では、これは *Forcebootstrap* パラメーターと同じです。</span><span class="sxs-lookup"><span data-stu-id="e886d-129">Currently, this is equivalent to the *ForceBootstrap* parameter.</span></span>

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

### <span data-ttu-id="e886d-130">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="e886d-130">-ForceBootstrap</span></span>

<span data-ttu-id="e886d-131">このコマンドレットによって、パッケージプロバイダーを自動的にインストールするように Package Management を強制することを示します。</span><span class="sxs-lookup"><span data-stu-id="e886d-131">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="e886d-132">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="e886d-132">-IncludeDependencies</span></span>

<span data-ttu-id="e886d-133">このコマンドレットに依存関係が含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="e886d-133">Indicates that this cmdlet includes dependencies.</span></span>

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

### <span data-ttu-id="e886d-134">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="e886d-134">-MaximumVersion</span></span>

<span data-ttu-id="e886d-135">検索するパッケージプロバイダーの許可される最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e886d-135">Specifies the maximum allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="e886d-136">このパラメーターを追加しない場合は、使用可能な最も高いバージョンのプロバイダーが **検索** されます。</span><span class="sxs-lookup"><span data-stu-id="e886d-136">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the provider.</span></span>

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

### <span data-ttu-id="e886d-137">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="e886d-137">-MinimumVersion</span></span>

<span data-ttu-id="e886d-138">検索するパッケージプロバイダーの許可される最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e886d-138">Specifies the minimum allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="e886d-139">このパラメーターを追加しない場合、 **検索-PackageProvider** は、 *MaximumVersion* パラメーターで指定された、指定された最大バージョンを満たすパッケージの利用可能な最も高いバージョンを検索します。</span><span class="sxs-lookup"><span data-stu-id="e886d-139">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the package that also satisfies any maximum specified version specified by the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="e886d-140">-Name</span><span class="sxs-lookup"><span data-stu-id="e886d-140">-Name</span></span>

<span data-ttu-id="e886d-141">1つまたは複数のパッケージプロバイダーモジュール名、またはワイルドカード文字を含むプロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e886d-141">Specifies one or more package provider module names, or provider names with wildcard characters.</span></span>
<span data-ttu-id="e886d-142">複数のパッケージ名はコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="e886d-142">Separate multiple package names with commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="e886d-143">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="e886d-143">-Proxy</span></span>

<span data-ttu-id="e886d-144">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="e886d-144">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="e886d-145">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="e886d-145">-ProxyCredential</span></span>

<span data-ttu-id="e886d-146">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e886d-146">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="e886d-147">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="e886d-147">-RequiredVersion</span></span>

<span data-ttu-id="e886d-148">検索するパッケージプロバイダーの完全に許可されているバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e886d-148">Specifies the exact allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="e886d-149">このパラメーターを追加しない場合、 **検索-PackageProvider** は、 *MaximumVersion* パラメーターで指定された最大バージョンも満たす、使用可能な最大バージョンのプロバイダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="e886d-149">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the provider that also satisfies any maximum version specified by the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="e886d-150">-Source</span><span class="sxs-lookup"><span data-stu-id="e886d-150">-Source</span></span>

<span data-ttu-id="e886d-151">1つまたは複数のパッケージソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="e886d-151">Specifies one or more package sources.</span></span>
<span data-ttu-id="e886d-152">使用可能なパッケージソースの一覧を取得するには、Get-PackageSource コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e886d-152">You can get a list of available package sources by using the Get-PackageSource cmdlet.</span></span>

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

### <span data-ttu-id="e886d-153">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e886d-153">CommonParameters</span></span>

<span data-ttu-id="e886d-154">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e886d-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e886d-155">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e886d-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e886d-156">入力</span><span class="sxs-lookup"><span data-stu-id="e886d-156">INPUTS</span></span>

## <span data-ttu-id="e886d-157">出力</span><span class="sxs-lookup"><span data-stu-id="e886d-157">OUTPUTS</span></span>

### <span data-ttu-id="e886d-158">Microsoft. パッケージ Id</span><span class="sxs-lookup"><span data-stu-id="e886d-158">Microsoft.PackageManagement.Packaging.SoftwareIdentity</span></span>

<span data-ttu-id="e886d-159">このコマンドレットは、 **ソフトウェア id** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="e886d-159">This cmdlet returns a **SoftwareIdentity** object.</span></span>
<span data-ttu-id="e886d-160">**ソフトウェア id** オブジェクトを **インストール-packageprovider** にパイプして、 **検索** 結果をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="e886d-160">A **SoftwareIdentity** object can be piped into **Install-PackageProvider** to install the results of **Find-PackageProvider** .</span></span>

## <span data-ttu-id="e886d-161">注</span><span class="sxs-lookup"><span data-stu-id="e886d-161">NOTES</span></span>

## <span data-ttu-id="e886d-162">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e886d-162">RELATED LINKS</span></span>

[<span data-ttu-id="e886d-163">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="e886d-163">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="e886d-164">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e886d-164">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

[<span data-ttu-id="e886d-165">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e886d-165">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="e886d-166">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e886d-166">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="e886d-167">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="e886d-167">Install-PackageProvider</span></span>](Install-PackageProvider.md)
