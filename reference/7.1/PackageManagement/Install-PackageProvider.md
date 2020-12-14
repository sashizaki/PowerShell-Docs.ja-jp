---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-packageprovider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-PackageProvider
ms.openlocfilehash: f9cf0854ed8e2dc4725ce8592a9b9cf86063beb5
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890064"
---
# <span data-ttu-id="00983-103">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="00983-103">Install-PackageProvider</span></span>

## <span data-ttu-id="00983-104">概要</span><span class="sxs-lookup"><span data-stu-id="00983-104">SYNOPSIS</span></span>
<span data-ttu-id="00983-105">1つまたは複数の Package Management パッケージプロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="00983-105">Installs one or more Package Management package providers.</span></span>

## <span data-ttu-id="00983-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="00983-106">SYNTAX</span></span>

### <span data-ttu-id="00983-107">PackageBySearch (既定)</span><span class="sxs-lookup"><span data-stu-id="00983-107">PackageBySearch (Default)</span></span>

```
Install-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Credential <PSCredential>] [-Scope <String>] [-Source <String[]>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="00983-108">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="00983-108">PackageByInputObject</span></span>

```
Install-PackageProvider [-Scope <String>] [-InputObject] <SoftwareIdentity[]> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="00983-109">Description</span><span class="sxs-lookup"><span data-stu-id="00983-109">DESCRIPTION</span></span>

<span data-ttu-id="00983-110">`Install-PackageProvider`コマンドレットは、 **PowerShellGet** に登録されているパッケージソースで使用できる、一致する Package Management プロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="00983-110">The `Install-PackageProvider` cmdlet installs matching Package Management providers that are available in package sources registered with **PowerShellGet**.</span></span> <span data-ttu-id="00983-111">既定では、 **PackageManagement** タグを持つ Windows PowerShell ギャラリーで使用できるモジュールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="00983-111">By default, this includes modules available in the Windows PowerShell Gallery with the **PackageManagement** tag.</span></span> <span data-ttu-id="00983-112">**PowerShellGet** Package Management プロバイダーは、これらのリポジトリ内のプロバイダーを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="00983-112">The **PowerShellGet** Package Management provider is used for finding providers in these repositories.</span></span>

<span data-ttu-id="00983-113">このコマンドレットは、Package Management ブートストラップアプリケーションを使用して使用できる一致する Package Management プロバイダーもインストールします。</span><span class="sxs-lookup"><span data-stu-id="00983-113">This cmdlet also installs matching Package Management providers that are available using the Package Management bootstrapping application.</span></span>

<span data-ttu-id="00983-114">このコマンドレットは、Package Management Azure Blob ストアで利用できる一致する Package Management プロバイダーもインストールします。</span><span class="sxs-lookup"><span data-stu-id="00983-114">This cmdlet also installs matching Package Management providers that are available in the Package Management Azure Blob store.</span></span> <span data-ttu-id="00983-115">ブートストラッププロバイダーを使用して、それらを検索してインストールします。</span><span class="sxs-lookup"><span data-stu-id="00983-115">Use the bootstrapper provider to find and install them.</span></span>

<span data-ttu-id="00983-116">最初に実行するには、PackageManagement が NuGet パッケージプロバイダーをダウンロードするためにインターネット接続を必要とします。</span><span class="sxs-lookup"><span data-stu-id="00983-116">In order to execute the first time, PackageManagement requires an internet connection to download the NuGet package provider.</span></span> <span data-ttu-id="00983-117">ただし、コンピューターがインターネットに接続されておらず、NuGet または PowerShellGet プロバイダーを使用する必要がある場合は、それらを別のコンピューターにダウンロードして、対象のコンピューターにコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="00983-117">However, if your computer does not have an internet connection and you need to use the NuGet or PowerShellGet provider, you can download them on another computer and copy them to your target computer.</span></span> <span data-ttu-id="00983-118">これを行うには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="00983-118">Use the following steps to do this:</span></span>

1. <span data-ttu-id="00983-119">を実行し `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` て、インターネットに接続されたコンピューターからプロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="00983-119">Run `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` to install the provider from a computer with an internet connection.</span></span>
1. <span data-ttu-id="00983-120">インストール後、またはにインストールされているプロバイダーを見つけることができ `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\<ProviderName>\<ProviderVersion>` `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\<ProviderName>\<ProviderVersion>` ます。</span><span class="sxs-lookup"><span data-stu-id="00983-120">After the install, you can find the provider installed in `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\<ProviderName>\<ProviderVersion>` or `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\<ProviderName>\<ProviderVersion>`.</span></span>
1. <span data-ttu-id="00983-121">`<ProviderName>`フォルダー (この場合は NuGet フォルダー) を、ターゲットコンピューター上の対応する場所に配置します。</span><span class="sxs-lookup"><span data-stu-id="00983-121">Place the `<ProviderName>` folder, which in this case is the NuGet folder, in the corresponding location on your target computer.</span></span> <span data-ttu-id="00983-122">ターゲットコンピューターが Nano server の場合は、 `Install-PackageProvider` Nano server からを実行して、正しい NuGet バイナリをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00983-122">If your target computer is a Nano server, you need to run `Install-PackageProvider` from Nano Server to download the correct NuGet binaries.</span></span>
1. <span data-ttu-id="00983-123">PowerShell を再起動して、パッケージプロバイダーを自動読み込みします。</span><span class="sxs-lookup"><span data-stu-id="00983-123">Restart PowerShell to auto-load the package provider.</span></span> <span data-ttu-id="00983-124">または、を実行して、 `Get-PackageProvider -ListAvailable` コンピューターで使用可能なすべてのパッケージプロバイダーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="00983-124">Alternatively, run `Get-PackageProvider -ListAvailable` to list all the package providers available on the computer.</span></span>
   <span data-ttu-id="00983-125">次に、を使用して `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` 、プロバイダーを現在の Windows PowerShell セッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="00983-125">Then use `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` to import the provider to the current Windows PowerShell session.</span></span>

## <span data-ttu-id="00983-126">例</span><span class="sxs-lookup"><span data-stu-id="00983-126">EXAMPLES</span></span>

### <span data-ttu-id="00983-127">例 1: PowerShell ギャラリーからパッケージプロバイダーをインストールする</span><span class="sxs-lookup"><span data-stu-id="00983-127">Example 1: Install a package provider from the PowerShell Gallery</span></span>

<span data-ttu-id="00983-128">このコマンドにより、PowerShell ギャラリーから GistProvider パッケージプロバイダーがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="00983-128">This command installs the GistProvider package provider from the PowerShell Gallery.</span></span>

```powershell
Install-PackageProvider -Name "GistProvider" -Verbose
```

### <span data-ttu-id="00983-129">例 2: 指定したバージョンのパッケージプロバイダーをインストールする</span><span class="sxs-lookup"><span data-stu-id="00983-129">Example 2: Install a specified version of a package provider</span></span>

<span data-ttu-id="00983-130">この例では、指定されたバージョンの NuGet パッケージプロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="00983-130">This example installs a specified version of the NuGet package provider.</span></span>

<span data-ttu-id="00983-131">最初のコマンドは、NuGet という名前のパッケージプロバイダーのすべてのバージョンを検索します。</span><span class="sxs-lookup"><span data-stu-id="00983-131">The first command finds all versions of the package provider named NuGet.</span></span>
<span data-ttu-id="00983-132">2番目のコマンドは、指定されたバージョンの NuGet パッケージプロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="00983-132">The second command installs a specified version of the NuGet package provider.</span></span>

```powershell
Find-PackageProvider -Name "NuGet" -AllVersions
Install-PackageProvider -Name "NuGet" -RequiredVersion "2.8.5.216" -Force
```

### <span data-ttu-id="00983-133">例 3: プロバイダーを検索してインストールする</span><span class="sxs-lookup"><span data-stu-id="00983-133">Example 3: Find a provider and install it</span></span>

<span data-ttu-id="00983-134">この例では、とパイプラインを使用して、 `Find-PackageProvider` Gist プロバイダーを検索してインストールします。</span><span class="sxs-lookup"><span data-stu-id="00983-134">This example uses `Find-PackageProvider` and the pipeline to search for the Gist provider and install it.</span></span>

```powershell
Find-PackageProvider -Name "GistProvider" | Install-PackageProvider -Verbose
```

### <span data-ttu-id="00983-135">例 4: 現在のユーザーのモジュールフォルダーにプロバイダーをインストールする</span><span class="sxs-lookup"><span data-stu-id="00983-135">Example 4: Install a provider to the current user's module folder</span></span>

<span data-ttu-id="00983-136">このコマンドは、 `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies` 現在のユーザーのみが使用できるように、パッケージプロバイダーをにインストールします。</span><span class="sxs-lookup"><span data-stu-id="00983-136">This command installs a package provider to `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies` so that only the current user can use it.</span></span>

```powershell
Install-PackageProvider -Name GistProvider -Verbose -Scope CurrentUser
```

## <span data-ttu-id="00983-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="00983-137">PARAMETERS</span></span>

### <span data-ttu-id="00983-138">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="00983-138">-AllVersions</span></span>

<span data-ttu-id="00983-139">このコマンドレットによって、使用可能なすべてのバージョンのパッケージプロバイダーがインストールされることを示します。</span><span class="sxs-lookup"><span data-stu-id="00983-139">Indicates that this cmdlet installs all available versions of the package provider.</span></span> <span data-ttu-id="00983-140">既定では、は、 `Install-PackageProvider` 使用可能な最も高いバージョンのみを返します。</span><span class="sxs-lookup"><span data-stu-id="00983-140">By default, `Install-PackageProvider` only returns the highest available version.</span></span>

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

### <span data-ttu-id="00983-141">-Credential</span><span class="sxs-lookup"><span data-stu-id="00983-141">-Credential</span></span>

<span data-ttu-id="00983-142">パッケージプロバイダーをインストールするアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="00983-142">Specifies a user account that has permission to install package providers.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="00983-143">-Force</span><span class="sxs-lookup"><span data-stu-id="00983-143">-Force</span></span>

<span data-ttu-id="00983-144">このコマンドレットが強制的に実行できるこのコマンドレットのすべての操作を強制することを示します。</span><span class="sxs-lookup"><span data-stu-id="00983-144">Indicates that this cmdlet forces all actions with this cmdlet that can be forced.</span></span> <span data-ttu-id="00983-145">現時点では、 **Force** パラメーターは **forcebootstrap** パラメーターと同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="00983-145">Currently, this means the **Force** parameter acts the same as the **ForceBootstrap** parameter.</span></span>

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

### <span data-ttu-id="00983-146">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="00983-146">-ForceBootstrap</span></span>

<span data-ttu-id="00983-147">このコマンドレットによってパッケージプロバイダーが自動的にインストールされることを示します。</span><span class="sxs-lookup"><span data-stu-id="00983-147">Indicates that this cmdlet automatically installs the package provider.</span></span>

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

### <span data-ttu-id="00983-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="00983-148">-InputObject</span></span>

<span data-ttu-id="00983-149">**ソフトウェア id** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="00983-149">Specifies a **SoftwareIdentity** object.</span></span> <span data-ttu-id="00983-150">コマンドレットを使用して `Find-PackageProvider` 、パイプするための **ソフトウェア id** オブジェクトを取得し `Install-PackageProvider` ます。</span><span class="sxs-lookup"><span data-stu-id="00983-150">Use the `Find-PackageProvider` cmdlet to obtain a **SoftwareIdentity** object to pipe into `Install-PackageProvider`.</span></span>

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

### <span data-ttu-id="00983-151">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="00983-151">-MaximumVersion</span></span>

<span data-ttu-id="00983-152">インストールするパッケージプロバイダーの許可される最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="00983-152">Specifies the maximum allowed version of the package provider that you want to install.</span></span> <span data-ttu-id="00983-153">このパラメーターを追加しない場合、では、 `Install-PackageProvider` 使用可能な最も高いバージョンのプロバイダーがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="00983-153">If you do not add this parameter, `Install-PackageProvider` installs the highest available version of the provider.</span></span>

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

### <span data-ttu-id="00983-154">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="00983-154">-MinimumVersion</span></span>

<span data-ttu-id="00983-155">インストールするパッケージプロバイダーの許可される最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="00983-155">Specifies the minimum allowed version of the package provider that you want to install.</span></span> <span data-ttu-id="00983-156">このパラメーターを追加しない場合、では、 `Install-PackageProvider` *MaximumVersion* パラメーターで指定された要件を満たす、利用可能な最も高いバージョンのパッケージがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="00983-156">If you do not add this parameter, `Install-PackageProvider` installs the highest available version of the package that also satisfies any requirement specified by the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="00983-157">-Name</span><span class="sxs-lookup"><span data-stu-id="00983-157">-Name</span></span>

<span data-ttu-id="00983-158">1つまたは複数のパッケージプロバイダーモジュール名を指定します。</span><span class="sxs-lookup"><span data-stu-id="00983-158">Specifies one or more package provider module names.</span></span> <span data-ttu-id="00983-159">複数のパッケージ名はコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="00983-159">Separate multiple package names with commas.</span></span>
<span data-ttu-id="00983-160">ワイルドカード文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="00983-160">Wildcard characters are not supported.</span></span>

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

### <span data-ttu-id="00983-161">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="00983-161">-Proxy</span></span>

<span data-ttu-id="00983-162">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="00983-162">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="00983-163">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="00983-163">-ProxyCredential</span></span>

<span data-ttu-id="00983-164">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="00983-164">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="00983-165">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="00983-165">-RequiredVersion</span></span>

<span data-ttu-id="00983-166">インストールするパッケージプロバイダーの完全に許可されているバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="00983-166">Specifies the exact allowed version of the package provider that you want to install.</span></span> <span data-ttu-id="00983-167">このパラメーターを追加しない場合、では、 `Install-PackageProvider` **MaximumVersion** パラメーターで指定された最大バージョンも満たす、利用可能な最も高いバージョンのプロバイダーがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="00983-167">If you do not add this parameter, `Install-PackageProvider` installs the highest available version of the provider that also satisfies any maximum version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="00983-168">-スコープ</span><span class="sxs-lookup"><span data-stu-id="00983-168">-Scope</span></span>

<span data-ttu-id="00983-169">プロバイダーのインストールスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="00983-169">Specifies the installation scope of the provider.</span></span> <span data-ttu-id="00983-170">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="00983-170">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="00983-171">**AllUsers** -コンピューターのすべてのユーザーがアクセスできる場所にプロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="00983-171">**AllUsers** - installs providers in a location that is accessible to all users of the computer.</span></span>
  <span data-ttu-id="00983-172">既定では、これは **$env:P rogramfiles\packagemanagement\providerassemblies.**</span><span class="sxs-lookup"><span data-stu-id="00983-172">By default, this is **$env:ProgramFiles\PackageManagement\ProviderAssemblies.**</span></span>

- <span data-ttu-id="00983-173">**CurrentUser** -現在のユーザーだけがアクセスできる場所にプロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="00983-173">**CurrentUser** - installs providers in a location where they are only accessible to the current user.</span></span> <span data-ttu-id="00983-174">既定では **$env: LOCALAPPDATA\PackageManagement\ProviderAssemblies.**</span><span class="sxs-lookup"><span data-stu-id="00983-174">By default, this is **$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies.**</span></span>

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

### <span data-ttu-id="00983-175">-Source</span><span class="sxs-lookup"><span data-stu-id="00983-175">-Source</span></span>

<span data-ttu-id="00983-176">1つまたは複数のパッケージソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="00983-176">Specifies one or more package sources.</span></span> <span data-ttu-id="00983-177">`Get-PackageSource`使用可能なパッケージソースの一覧を取得するには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="00983-177">Use the `Get-PackageSource` cmdlet to get a list of available package sources.</span></span>

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

### <span data-ttu-id="00983-178">-Confirm</span><span class="sxs-lookup"><span data-stu-id="00983-178">-Confirm</span></span>

<span data-ttu-id="00983-179">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="00983-179">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="00983-180">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="00983-180">-WhatIf</span></span>

<span data-ttu-id="00983-181">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="00983-181">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="00983-182">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="00983-182">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="00983-183">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="00983-183">CommonParameters</span></span>

<span data-ttu-id="00983-184">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="00983-184">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="00983-185">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00983-185">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="00983-186">入力</span><span class="sxs-lookup"><span data-stu-id="00983-186">INPUTS</span></span>

### <span data-ttu-id="00983-187">Microsoft. パッケージ Id</span><span class="sxs-lookup"><span data-stu-id="00983-187">Microsoft.PackageManagement.Packaging.SoftwareIdentity</span></span>

<span data-ttu-id="00983-188">パイプを使用して、このコマンドレットに **ソフトウェア id** オブジェクトをパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="00983-188">You can pipe a **SoftwareIdentity** object to this cmdlet.</span></span> <span data-ttu-id="00983-189">に `Find-PackageProvider` パイプ処理できる **ソフトウェア id** オブジェクトを取得するには、を使用し `Install-PackageProvider` ます。</span><span class="sxs-lookup"><span data-stu-id="00983-189">Use `Find-PackageProvider` to get a **SoftwareIdentity** object that can be piped into `Install-PackageProvider`.</span></span>

## <span data-ttu-id="00983-190">出力</span><span class="sxs-lookup"><span data-stu-id="00983-190">OUTPUTS</span></span>

## <span data-ttu-id="00983-191">注</span><span class="sxs-lookup"><span data-stu-id="00983-191">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00983-192">2020年4月の時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン1.0 と1.1 がサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="00983-192">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="00983-193">TLS 1.2 以降を使用していない場合は、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="00983-193">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="00983-194">次のコマンドを使用して、TLS 1.2 を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="00983-194">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="00983-195">詳細については、PowerShell ブログの [お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00983-195">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="00983-196">関連リンク</span><span class="sxs-lookup"><span data-stu-id="00983-196">RELATED LINKS</span></span>

[<span data-ttu-id="00983-197">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="00983-197">Find-PackageProvider</span></span>](Find-PackageProvider.md)

[<span data-ttu-id="00983-198">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="00983-198">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="00983-199">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="00983-199">Import-PackageProvider</span></span>](Import-PackageProvider.md)
