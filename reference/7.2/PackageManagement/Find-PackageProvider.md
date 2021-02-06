---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/find-packageprovider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-PackageProvider
ms.openlocfilehash: cca73714cebf8f0d527c669358458f8509b80a90
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99602399"
---
# <span data-ttu-id="93f2b-102">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="93f2b-102">Find-PackageProvider</span></span>

## <span data-ttu-id="93f2b-103">概要</span><span class="sxs-lookup"><span data-stu-id="93f2b-103">SYNOPSIS</span></span>
<span data-ttu-id="93f2b-104">インストールに使用できる Package Management パッケージプロバイダーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-104">Returns a list of Package Management package providers available for installation.</span></span>

## <span data-ttu-id="93f2b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="93f2b-105">SYNTAX</span></span>

```
Find-PackageProvider [[-Name] <String[]>] [-AllVersions] [-Source <String[]>] [-IncludeDependencies]
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="93f2b-106">Description</span><span class="sxs-lookup"><span data-stu-id="93f2b-106">DESCRIPTION</span></span>

<span data-ttu-id="93f2b-107">**検索 PackageProvider** コマンドレットは、PowerShellGet に登録されているパッケージソースで使用できる一致する PackageManagement プロバイダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-107">The **Find-PackageProvider** cmdlet finds matching PackageManagement providers that are available in package sources registered with PowerShellGet.</span></span>
<span data-ttu-id="93f2b-108">これらは、Install-PackageProvider コマンドレットを使用したインストールに使用可能なパッケージ プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="93f2b-108">These are package providers available for installation with the Install-PackageProvider cmdlet.</span></span>
<span data-ttu-id="93f2b-109">既定では、これには、 **PackageManagement** タグと **Provider** タグを持つ PowerShell ギャラリーで使用できるモジュールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="93f2b-109">By default, this includes modules available in the PowerShell Gallery with the **PackageManagement** and **Provider** tags.</span></span>

<span data-ttu-id="93f2b-110">**検索-PackageProvider** は、Package Management Azure Blob ストアで利用できる一致する Package Management プロバイダーも検索します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-110">**Find-PackageProvider** also finds matching Package Management providers that are available in the Package Management Azure Blob store.</span></span>
<span data-ttu-id="93f2b-111">ブートストラッププロバイダーを使用して、それらを検索してインストールします。</span><span class="sxs-lookup"><span data-stu-id="93f2b-111">Use the bootstrapper provider to find and install them.</span></span>

## <span data-ttu-id="93f2b-112">例</span><span class="sxs-lookup"><span data-stu-id="93f2b-112">EXAMPLES</span></span>

### <span data-ttu-id="93f2b-113">例 1: 使用可能なすべてのパッケージプロバイダーを検索する</span><span class="sxs-lookup"><span data-stu-id="93f2b-113">Example 1: Find all available package providers</span></span>

```
PS C:\> Find-PackageProvider
```

<span data-ttu-id="93f2b-114">このコマンドは、Package Management でサポートされているリポジトリで使用可能なすべてのパッケージプロバイダーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-114">This command gets a list of all package providers that are available on the repositories supported by Package Management.</span></span>
<span data-ttu-id="93f2b-115">既定では、これらのパッケージプロバイダーは、PowerShell ギャラリーと Package Management ブートストラップアプリケーションを使用して入手できます。</span><span class="sxs-lookup"><span data-stu-id="93f2b-115">By default, those package providers are available on the PowerShell Gallery and by using the Package Management bootstrapping application.</span></span>

### <span data-ttu-id="93f2b-116">例 2: プロバイダーのすべてのバージョンを検索する</span><span class="sxs-lookup"><span data-stu-id="93f2b-116">Example 2: Find all versions of a provider</span></span>

```
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
```

<span data-ttu-id="93f2b-117">このコマンドは、Nuget という名前のパッケージプロバイダーのすべてのバージョンを検索します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-117">This command finds all versions of the package provider named Nuget.</span></span>

### <span data-ttu-id="93f2b-118">例 3: 指定されたソースからプロバイダーを検索する</span><span class="sxs-lookup"><span data-stu-id="93f2b-118">Example 3: Find a provider from a specified source</span></span>

```
PS C:\> Find-PackageProvider -Name "Gistprovider" -Source "PSGallery"
```

<span data-ttu-id="93f2b-119">このコマンドは、指定されたパッケージソースを使用して利用可能なパッケージプロバイダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-119">This command finds a package provider available by using a specified package source.</span></span>

## <span data-ttu-id="93f2b-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="93f2b-120">PARAMETERS</span></span>

### <span data-ttu-id="93f2b-121">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="93f2b-121">-AllVersions</span></span>

<span data-ttu-id="93f2b-122">このコマンドレットが、使用可能なすべてのバージョンのパッケージプロバイダーを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-122">Indicates that this cmdlet returns all available versions of the package provider.</span></span>
<span data-ttu-id="93f2b-123">既定では、 **検索-PackageProvider** は、利用可能な最新バージョンのみを返します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-123">By default, **Find-PackageProvider** only returns the newest available version.</span></span>

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

### <span data-ttu-id="93f2b-124">-Credential</span><span class="sxs-lookup"><span data-stu-id="93f2b-124">-Credential</span></span>

<span data-ttu-id="93f2b-125">パッケージプロバイダーを検索するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-125">Specifies a user account that has permission to search for package providers.</span></span>

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

### <span data-ttu-id="93f2b-126">-Force</span><span class="sxs-lookup"><span data-stu-id="93f2b-126">-Force</span></span>

<span data-ttu-id="93f2b-127">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-127">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="93f2b-128">現時点では、これは *Forcebootstrap* パラメーターと同じです。</span><span class="sxs-lookup"><span data-stu-id="93f2b-128">Currently, this is equivalent to the *ForceBootstrap* parameter.</span></span>

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

### <span data-ttu-id="93f2b-129">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="93f2b-129">-ForceBootstrap</span></span>

<span data-ttu-id="93f2b-130">このコマンドレットによって、パッケージプロバイダーを自動的にインストールするように Package Management を強制することを示します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-130">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="93f2b-131">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="93f2b-131">-IncludeDependencies</span></span>

<span data-ttu-id="93f2b-132">このコマンドレットに依存関係が含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-132">Indicates that this cmdlet includes dependencies.</span></span>

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

### <span data-ttu-id="93f2b-133">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="93f2b-133">-MaximumVersion</span></span>

<span data-ttu-id="93f2b-134">検索するパッケージプロバイダーの許可される最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-134">Specifies the maximum allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="93f2b-135">このパラメーターを追加しない場合は、使用可能な最も高いバージョンのプロバイダーが **検索** されます。</span><span class="sxs-lookup"><span data-stu-id="93f2b-135">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the provider.</span></span>

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

### <span data-ttu-id="93f2b-136">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="93f2b-136">-MinimumVersion</span></span>

<span data-ttu-id="93f2b-137">検索するパッケージプロバイダーの許可される最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-137">Specifies the minimum allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="93f2b-138">このパラメーターを追加しない場合、 **検索-PackageProvider** は、 *MaximumVersion* パラメーターで指定された、指定された最大バージョンを満たすパッケージの利用可能な最も高いバージョンを検索します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-138">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the package that also satisfies any maximum specified version specified by the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="93f2b-139">-Name</span><span class="sxs-lookup"><span data-stu-id="93f2b-139">-Name</span></span>

<span data-ttu-id="93f2b-140">1つまたは複数のパッケージプロバイダーモジュール名、またはワイルドカード文字を含むプロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-140">Specifies one or more package provider module names, or provider names with wildcard characters.</span></span>
<span data-ttu-id="93f2b-141">複数のパッケージ名はコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="93f2b-141">Separate multiple package names with commas.</span></span>

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

### <span data-ttu-id="93f2b-142">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="93f2b-142">-Proxy</span></span>

<span data-ttu-id="93f2b-143">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-143">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="93f2b-144">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="93f2b-144">-ProxyCredential</span></span>

<span data-ttu-id="93f2b-145">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-145">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="93f2b-146">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="93f2b-146">-RequiredVersion</span></span>

<span data-ttu-id="93f2b-147">検索するパッケージプロバイダーの完全に許可されているバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-147">Specifies the exact allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="93f2b-148">このパラメーターを追加しない場合、 **検索-PackageProvider** は、 *MaximumVersion* パラメーターで指定された最大バージョンも満たす、使用可能な最大バージョンのプロバイダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-148">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the provider that also satisfies any maximum version specified by the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="93f2b-149">-Source</span><span class="sxs-lookup"><span data-stu-id="93f2b-149">-Source</span></span>

<span data-ttu-id="93f2b-150">1つまたは複数のパッケージソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-150">Specifies one or more package sources.</span></span>
<span data-ttu-id="93f2b-151">使用可能なパッケージソースの一覧を取得するには、Get-PackageSource コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-151">You can get a list of available package sources by using the Get-PackageSource cmdlet.</span></span>

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

### <span data-ttu-id="93f2b-152">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="93f2b-152">CommonParameters</span></span>

<span data-ttu-id="93f2b-153">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="93f2b-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="93f2b-154">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93f2b-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="93f2b-155">入力</span><span class="sxs-lookup"><span data-stu-id="93f2b-155">INPUTS</span></span>

## <span data-ttu-id="93f2b-156">出力</span><span class="sxs-lookup"><span data-stu-id="93f2b-156">OUTPUTS</span></span>

### <span data-ttu-id="93f2b-157">Microsoft. パッケージ Id</span><span class="sxs-lookup"><span data-stu-id="93f2b-157">Microsoft.PackageManagement.Packaging.SoftwareIdentity</span></span>

<span data-ttu-id="93f2b-158">このコマンドレットは、 **ソフトウェア id** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-158">This cmdlet returns a **SoftwareIdentity** object.</span></span>
<span data-ttu-id="93f2b-159">**ソフトウェア id** オブジェクトを **インストール-packageprovider** にパイプして、**検索** 結果をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="93f2b-159">A **SoftwareIdentity** object can be piped into **Install-PackageProvider** to install the results of **Find-PackageProvider**.</span></span>

## <span data-ttu-id="93f2b-160">注</span><span class="sxs-lookup"><span data-stu-id="93f2b-160">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93f2b-161">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="93f2b-161">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="93f2b-162">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="93f2b-162">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="93f2b-163">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="93f2b-163">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="93f2b-164">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93f2b-164">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="93f2b-165">関連リンク</span><span class="sxs-lookup"><span data-stu-id="93f2b-165">RELATED LINKS</span></span>

[<span data-ttu-id="93f2b-166">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="93f2b-166">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="93f2b-167">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="93f2b-167">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

[<span data-ttu-id="93f2b-168">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="93f2b-168">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="93f2b-169">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="93f2b-169">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="93f2b-170">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="93f2b-170">Install-PackageProvider</span></span>](Install-PackageProvider.md)
