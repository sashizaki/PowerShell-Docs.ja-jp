---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-packageprovider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-PackageProvider
ms.openlocfilehash: 9bb2bf79aa17b139bd89281ac0967f7241414d89
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210432"
---
# <span data-ttu-id="8a431-103">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="8a431-103">Install-PackageProvider</span></span>

## <span data-ttu-id="8a431-104">概要</span><span class="sxs-lookup"><span data-stu-id="8a431-104">SYNOPSIS</span></span>
<span data-ttu-id="8a431-105">1つまたは複数の Package Management パッケージプロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a431-105">Installs one or more Package Management package providers.</span></span>

## <span data-ttu-id="8a431-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8a431-106">SYNTAX</span></span>

### <span data-ttu-id="8a431-107">PackageBySearch (既定)</span><span class="sxs-lookup"><span data-stu-id="8a431-107">PackageBySearch (Default)</span></span>

```
Install-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Credential <PSCredential>] [-Scope <String>] [-Source <String[]>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="8a431-108">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="8a431-108">PackageByInputObject</span></span>

```
Install-PackageProvider [-Scope <String>] [-InputObject] <SoftwareIdentity[]> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="8a431-109">Description</span><span class="sxs-lookup"><span data-stu-id="8a431-109">DESCRIPTION</span></span>

<span data-ttu-id="8a431-110">**Install-PackageProvider** コマンドレットは、 **PowerShellGet** に登録されているパッケージソースで使用できる、一致する Package Management プロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a431-110">The **Install-PackageProvider** cmdlet installs matching Package Management providers that are available in package sources registered with **PowerShellGet** .</span></span>
<span data-ttu-id="8a431-111">既定では、 **PackageManagement** タグを持つ PowerShell ギャラリーで利用できるモジュールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8a431-111">By default, this includes modules available in the PowerShell Gallery with the **PackageManagement** tag.</span></span>
<span data-ttu-id="8a431-112">**PowerShellGet** Package Management プロバイダーは、これらのリポジトリ内のプロバイダーを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a431-112">The **PowerShellGet** Package Management provider is used for finding providers in these repositories.</span></span>

<span data-ttu-id="8a431-113">このコマンドレットは、Package Management ブートストラップアプリケーションを使用して使用できる一致する Package Management プロバイダーもインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a431-113">This cmdlet also installs matching Package Management providers that are available using the Package Management bootstrapping application.</span></span>

<span data-ttu-id="8a431-114">このコマンドレットは、Package Management Azure Blob ストアで利用できる一致する Package Management プロバイダーもインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a431-114">This cmdlet also installs matching Package Management providers that are available in the Package Management Azure Blob store.</span></span>
<span data-ttu-id="8a431-115">ブートストラッププロバイダーを使用して、それらを検索してインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a431-115">Use the bootstrapper provider to find and install them.</span></span>

<span data-ttu-id="8a431-116">最初に実行するには、PackageManagement が Nuget パッケージプロバイダーをダウンロードするためにインターネット接続を必要とします。</span><span class="sxs-lookup"><span data-stu-id="8a431-116">In order to execute the first time, PackageManagement requires an internet connection to download the Nuget package provider.</span></span>
<span data-ttu-id="8a431-117">ただし、コンピューターがインターネットに接続されておらず、Nuget または PowerShellGet プロバイダーを使用する必要がある場合は、それらを別のコンピューターにダウンロードして、対象のコンピューターにコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="8a431-117">However, if your computer does not have an internet connection and you need to use the Nuget or PowerShellGet provider, you can download them on another computer and copy them to your target computer.</span></span>
<span data-ttu-id="8a431-118">これを行うには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="8a431-118">Use the following steps to do this:</span></span>

1.
<span data-ttu-id="8a431-119">を実行し `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` て、インターネットに接続されたコンピューターからプロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a431-119">Run `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` to install the provider from a computer with an internet connection.</span></span>

2.
<span data-ttu-id="8a431-120">インストール後、またはにインストールされているプロバイダーを見つけることができ `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\\\<ProviderName\>\\\<ProviderVersion\>` `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\\\<ProviderName\>\\\<ProviderVersion\>` ます。</span><span class="sxs-lookup"><span data-stu-id="8a431-120">After the install, you can find the provider installed in `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\\\<ProviderName\>\\\<ProviderVersion\>` or `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\\\<ProviderName\>\\\<ProviderVersion\>`.</span></span>

3.
<span data-ttu-id="8a431-121">\<ProviderName\>フォルダー (この場合は Nuget フォルダー) を、ターゲットコンピューター上の対応する場所に配置します。</span><span class="sxs-lookup"><span data-stu-id="8a431-121">Place the \<ProviderName\> folder, which in this case is the Nuget folder, in the corresponding location on your target computer.</span></span>
<span data-ttu-id="8a431-122">ターゲットコンピューターが Nano server の場合は、Nano Server から **Install-PackageProvider** を実行して、正しい Nuget バイナリをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a431-122">If your target computer is a Nano server, you need to run **Install-PackageProvider** from Nano Server to download the correct Nuget binaries.</span></span>

4.
<span data-ttu-id="8a431-123">PowerShell を再起動して、パッケージプロバイダーを自動読み込みします。</span><span class="sxs-lookup"><span data-stu-id="8a431-123">Restart PowerShell to auto-load the package provider.</span></span>
<span data-ttu-id="8a431-124">または、を実行して、 `Get-PackageProvider -ListAvailable` コンピューターで使用可能なすべてのパッケージプロバイダーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8a431-124">Alternatively, run `Get-PackageProvider -ListAvailable` to list all the package providers available on the computer.</span></span>
<span data-ttu-id="8a431-125">次に、を使用して、 `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` 現在の PowerShell セッションにプロバイダーをインポートします。</span><span class="sxs-lookup"><span data-stu-id="8a431-125">Then use `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` to import the provider to the current PowerShell session.</span></span>

## <span data-ttu-id="8a431-126">例</span><span class="sxs-lookup"><span data-stu-id="8a431-126">EXAMPLES</span></span>

### <span data-ttu-id="8a431-127">例 1: PowerShell ギャラリーからパッケージプロバイダーをインストールする</span><span class="sxs-lookup"><span data-stu-id="8a431-127">Example 1: Install a package provider from the PowerShell Gallery</span></span>

```
PS C:\> Install-PackageProvider -Name "Gistprovider" -Verbose
```

<span data-ttu-id="8a431-128">このコマンドは、PowerShell ギャラリーから Gistprovider をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a431-128">This command installs the Gistprovider from the PowerShell Gallery.</span></span>

### <span data-ttu-id="8a431-129">例 2: 指定したバージョンのパッケージプロバイダーをインストールする</span><span class="sxs-lookup"><span data-stu-id="8a431-129">Example 2: Install a specified version of a package provider</span></span>

```
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
PS C:\> Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.216" -Force
```

<span data-ttu-id="8a431-130">この例では、指定されたバージョンの Nuget パッケージプロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a431-130">This example installs a specified version of the Nuget package provider.</span></span>

<span data-ttu-id="8a431-131">最初のコマンドは、Nuget という名前のパッケージプロバイダーのすべてのバージョンを検索します。</span><span class="sxs-lookup"><span data-stu-id="8a431-131">The first command finds all versions of the package provider named Nuget.</span></span>
<span data-ttu-id="8a431-132">2番目のコマンドは、指定されたバージョンの Nuget パッケージプロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a431-132">The second command installs a specified version of the Nuget package provider.</span></span>

### <span data-ttu-id="8a431-133">例 3: プロバイダーを検索してインストールする</span><span class="sxs-lookup"><span data-stu-id="8a431-133">Example 3: Find a provider and install it</span></span>

```
PS C:\> Find-PackageProvider -Name "Gistprovider" | Install-PackageProvider -Verbose
```

<span data-ttu-id="8a431-134">このコマンドは、 **検索 packageprovider** とパイプラインを使用して、Gist プロバイダーを検索してインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a431-134">This command uses **Find-PackageProvider** and the pipeline to search for the Gist provider and install it.</span></span>

### <span data-ttu-id="8a431-135">例 4: 現在のユーザーのモジュールフォルダーにプロバイダーをインストールする</span><span class="sxs-lookup"><span data-stu-id="8a431-135">Example 4: Install a provider to the current user's module folder</span></span>

```
PS C:\> Install-PackageProvider -Name Gistprovider -Verbose -Scope CurrentUser
```

<span data-ttu-id="8a431-136">このコマンドは、現在のユーザーのみが使用できるように $env: Localappdata\packagemanagement\providerassemblies からにパッケージプロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a431-136">This command installs a package provider to $env:LOCALAPPDATA\PackageManagement\ProviderAssemblies so that only the current user can use it.</span></span>

## <span data-ttu-id="8a431-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8a431-137">PARAMETERS</span></span>

### <span data-ttu-id="8a431-138">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="8a431-138">-AllVersions</span></span>

<span data-ttu-id="8a431-139">このコマンドレットによって、使用可能なすべてのバージョンのパッケージプロバイダーがインストールされることを示します。</span><span class="sxs-lookup"><span data-stu-id="8a431-139">Indicates that this cmdlet installs all available versions of the package provider.</span></span>
<span data-ttu-id="8a431-140">既定では、 **Install-PackageProvider** は、使用可能な最も高いバージョンのみを返します。</span><span class="sxs-lookup"><span data-stu-id="8a431-140">By default, **Install-PackageProvider** only returns the highest available version.</span></span>

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

### <span data-ttu-id="8a431-141">-Credential</span><span class="sxs-lookup"><span data-stu-id="8a431-141">-Credential</span></span>

<span data-ttu-id="8a431-142">パッケージプロバイダーをインストールするアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="8a431-142">Specifies a user account that has permission to install package providers.</span></span>

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

### <span data-ttu-id="8a431-143">-Force</span><span class="sxs-lookup"><span data-stu-id="8a431-143">-Force</span></span>

<span data-ttu-id="8a431-144">このコマンドレットが強制的に実行できるこのコマンドレットのすべての操作を強制することを示します。</span><span class="sxs-lookup"><span data-stu-id="8a431-144">Indicates that this cmdlet forces all actions with this cmdlet that can be forced.</span></span>
<span data-ttu-id="8a431-145">現時点では、 *Force* パラメーターは *forcebootstrap* パラメーターと同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="8a431-145">Currently, this means the *Force* parameter acts the same as the *ForceBootstrap* parameter.</span></span>

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

### <span data-ttu-id="8a431-146">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="8a431-146">-ForceBootstrap</span></span>

<span data-ttu-id="8a431-147">このコマンドレットによってパッケージプロバイダーが自動的にインストールされることを示します。</span><span class="sxs-lookup"><span data-stu-id="8a431-147">Indicates that this cmdlet automatically installs the package provider.</span></span>

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

### <span data-ttu-id="8a431-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="8a431-148">-InputObject</span></span>

<span data-ttu-id="8a431-149">**ソフトウェア id** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="8a431-149">Specifies a **SoftwareIdentity** object.</span></span>
<span data-ttu-id="8a431-150">**検索 packageprovider** コマンドレットを使用して、 **Install-packageprovider** にパイプするための **ソフトウェア id** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="8a431-150">Use the **Find-PackageProvider** cmdlet to obtain a **SoftwareIdentity** object to pipe into **Install-PackageProvider** .</span></span>

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

### <span data-ttu-id="8a431-151">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="8a431-151">-MaximumVersion</span></span>

<span data-ttu-id="8a431-152">インストールするパッケージプロバイダーの許可される最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="8a431-152">Specifies the maximum allowed version of the package provider that you want to install.</span></span>
<span data-ttu-id="8a431-153">このパラメーターを追加しない場合、 **インストール-PackageProvider** は、使用可能な最も高いバージョンのプロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a431-153">If you do not add this parameter, **Install-PackageProvider** installs the highest available version of the provider.</span></span>

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

### <span data-ttu-id="8a431-154">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="8a431-154">-MinimumVersion</span></span>

<span data-ttu-id="8a431-155">インストールするパッケージプロバイダーの許可される最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="8a431-155">Specifies the minimum allowed version of the package provider that you want to install.</span></span>
<span data-ttu-id="8a431-156">このパラメーターを追加しない場合、 **Install-PackageProvider** は、 *MaximumVersion* パラメーターで指定された要件を満たす、利用可能な最も高いバージョンのパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a431-156">If you do not add this parameter, **Install-PackageProvider** installs the highest available version of the package that also satisfies any requirement specified by the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="8a431-157">-Name</span><span class="sxs-lookup"><span data-stu-id="8a431-157">-Name</span></span>

<span data-ttu-id="8a431-158">1つまたは複数のパッケージプロバイダーモジュール名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8a431-158">Specifies one or more package provider module names.</span></span>
<span data-ttu-id="8a431-159">複数のパッケージ名はコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="8a431-159">Separate multiple package names with commas.</span></span>
<span data-ttu-id="8a431-160">ワイルドカード文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8a431-160">Wildcard characters are not supported.</span></span>

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

### <span data-ttu-id="8a431-161">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="8a431-161">-Proxy</span></span>

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

### <span data-ttu-id="8a431-162">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="8a431-162">-ProxyCredential</span></span>

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

### <span data-ttu-id="8a431-163">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="8a431-163">-RequiredVersion</span></span>

<span data-ttu-id="8a431-164">インストールするパッケージプロバイダーの完全に許可されているバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="8a431-164">Specifies the exact allowed version of the package provider that you want to install.</span></span>
<span data-ttu-id="8a431-165">このパラメーターを追加しない場合、 **Install-PackageProvider** は、 *MaximumVersion* パラメーターで指定された最大バージョンも満たすプロバイダーの利用可能な最も高いバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a431-165">If you do not add this parameter, **Install-PackageProvider** installs the highest available version of the provider that also satisfies any maximum version specified by the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="8a431-166">-スコープ</span><span class="sxs-lookup"><span data-stu-id="8a431-166">-Scope</span></span>

<span data-ttu-id="8a431-167">プロバイダーのインストールスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="8a431-167">Specifies the installation scope of the provider.</span></span>
<span data-ttu-id="8a431-168">このパラメーターに指定できる値は、 **AllUsers** と **CurrentUser** です。</span><span class="sxs-lookup"><span data-stu-id="8a431-168">The acceptable values for this parameter are: **AllUsers** and **CurrentUser** .</span></span>

<span data-ttu-id="8a431-169">**AllUsers** スコープは、コンピューターのすべてのユーザーがアクセスできる場所にプロバイダーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a431-169">The **AllUsers** scope installs providers in a location that is accessible to all users of the computer.</span></span>
<span data-ttu-id="8a431-170">既定では、これは **$env:P rogramfiles\packagemanagement\providerassemblies.**</span><span class="sxs-lookup"><span data-stu-id="8a431-170">By default, this is **$env:ProgramFiles\PackageManagement\ProviderAssemblies.**</span></span>

<span data-ttu-id="8a431-171">**CurrentUser** スコープでは、現在のユーザーだけがアクセスできる場所にプロバイダーがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8a431-171">The **CurrentUser** scope installs providers in a location where they are only accessible to the current user.</span></span>
<span data-ttu-id="8a431-172">既定では **$env: LOCALAPPDATA\PackageManagement\ProviderAssemblies.**</span><span class="sxs-lookup"><span data-stu-id="8a431-172">By default, this is **$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies.**</span></span>

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

### <span data-ttu-id="8a431-173">-Source</span><span class="sxs-lookup"><span data-stu-id="8a431-173">-Source</span></span>

<span data-ttu-id="8a431-174">1つまたは複数のパッケージソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="8a431-174">Specifies one or more package sources.</span></span>
<span data-ttu-id="8a431-175">使用可能なパッケージソースの一覧を取得するには、Get-PackageSource コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8a431-175">Use the Get-PackageSource cmdlet to get a list of available package sources.</span></span>

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

### <span data-ttu-id="8a431-176">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8a431-176">-Confirm</span></span>

<span data-ttu-id="8a431-177">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a431-177">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8a431-178">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8a431-178">-WhatIf</span></span>

<span data-ttu-id="8a431-179">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="8a431-179">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8a431-180">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="8a431-180">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8a431-181">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a431-181">CommonParameters</span></span>

<span data-ttu-id="8a431-182">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8a431-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8a431-183">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a431-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8a431-184">入力</span><span class="sxs-lookup"><span data-stu-id="8a431-184">INPUTS</span></span>

### <span data-ttu-id="8a431-185">Microsoft. パッケージ Id</span><span class="sxs-lookup"><span data-stu-id="8a431-185">Microsoft.PackageManagement.Packaging.SoftwareIdentity</span></span>

<span data-ttu-id="8a431-186">パイプを使用して、このコマンドレットに **ソフトウェア id** オブジェクトをパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="8a431-186">You can pipe a **SoftwareIdentity** object to this cmdlet.</span></span>
<span data-ttu-id="8a431-187">Find-PackageProvider を使用して、 **インストール-PackageProvider** にパイプできる **ソフトウェア id** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="8a431-187">Use Find-PackageProvider to get a **SoftwareIdentity** object that can be piped into **Install-PackageProvider** .</span></span>

## <span data-ttu-id="8a431-188">出力</span><span class="sxs-lookup"><span data-stu-id="8a431-188">OUTPUTS</span></span>

## <span data-ttu-id="8a431-189">注</span><span class="sxs-lookup"><span data-stu-id="8a431-189">NOTES</span></span>

## <span data-ttu-id="8a431-190">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8a431-190">RELATED LINKS</span></span>

[<span data-ttu-id="8a431-191">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="8a431-191">Find-PackageProvider</span></span>](Find-PackageProvider.md)

[<span data-ttu-id="8a431-192">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="8a431-192">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="8a431-193">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="8a431-193">Import-PackageProvider</span></span>](Import-PackageProvider.md)
