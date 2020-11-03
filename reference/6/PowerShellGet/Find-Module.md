---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-module?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Module
ms.openlocfilehash: 5795d48b2b76b4853d80d0cd79cb99d62332a39b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216008"
---
# <span data-ttu-id="dea94-103">Find-Module</span><span class="sxs-lookup"><span data-stu-id="dea94-103">Find-Module</span></span>

## <span data-ttu-id="dea94-104">概要</span><span class="sxs-lookup"><span data-stu-id="dea94-104">SYNOPSIS</span></span>
<span data-ttu-id="dea94-105">指定された条件に一致するリポジトリ内のモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="dea94-105">Finds modules in a repository that match specified criteria.</span></span>

## <span data-ttu-id="dea94-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dea94-106">SYNTAX</span></span>

### <span data-ttu-id="dea94-107">All</span><span class="sxs-lookup"><span data-stu-id="dea94-107">All</span></span>

```
Find-Module [[-Name] <string[]>] [-MinimumVersion <string>] [-MaximumVersion <string>]
 [-RequiredVersion <string>] [-AllVersions] [-IncludeDependencies] [-Filter <string>]
 [-Tag <string[]>] [-Includes <string[]>] [-DscResource <string[]>] [-RoleCapability <string[]>]
 [-Command <string[]>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Repository <string[]>]
 [-Credential <pscredential>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="dea94-108">Description</span><span class="sxs-lookup"><span data-stu-id="dea94-108">DESCRIPTION</span></span>

<span data-ttu-id="dea94-109">`Find-Module`コマンドレットは、指定された条件に一致するリポジトリ内のモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="dea94-109">The `Find-Module` cmdlet finds modules in a repository that match the specified criteria.</span></span>
<span data-ttu-id="dea94-110">`Find-Module` 検出された各モジュールの **できる psrepositoryiteminfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="dea94-110">`Find-Module` returns a **PSRepositoryItemInfo** object for each module it finds.</span></span> <span data-ttu-id="dea94-111">オブジェクトは、などのコマンドレットにパイプラインを介して送信でき `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="dea94-111">The objects can be sent down the pipeline to cmdlets such as `Install-Module`.</span></span>

<span data-ttu-id="dea94-112">最初に `Find-Module` リポジトリを使用しようとすると、更新プログラムのインストールを求めるメッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="dea94-112">The first time `Find-Module` attempts to use a repository, you might be prompted to install updates.</span></span>
<span data-ttu-id="dea94-113">リポジトリソースがコマンドレットに登録されていない場合 `Register-PSRepository` は、エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="dea94-113">If the repository source is not registered with `Register-PSRepository` cmdlet, an error is returned.</span></span>

<span data-ttu-id="dea94-114">`Find-Module` バージョンを制限するパラメーターが使用されていない場合は、最新バージョンのモジュールを返します。</span><span class="sxs-lookup"><span data-stu-id="dea94-114">`Find-Module` returns the newest version of a module if no parameters are used that limit the version.</span></span> <span data-ttu-id="dea94-115">リポジトリのモジュールバージョンの一覧を取得するには、パラメーター **AllVersions** を使用します。</span><span class="sxs-lookup"><span data-stu-id="dea94-115">To get a repository's list of a module's versions, use the parameter **AllVersions** .</span></span>

<span data-ttu-id="dea94-116">**MinimumVersion** パラメーターが指定されている場合、は、 `Find-Module` 最小値以上のモジュールのバージョンを返します。</span><span class="sxs-lookup"><span data-stu-id="dea94-116">If the **MinimumVersion** parameter is specified, `Find-Module` returns the module's version that is equal to or greater than the minimum.</span></span> <span data-ttu-id="dea94-117">リポジトリに使用可能な新しいバージョンがある場合は、新しいバージョンが返されます。</span><span class="sxs-lookup"><span data-stu-id="dea94-117">If there is a newer version available in the repository, the newer version is returned.</span></span>

<span data-ttu-id="dea94-118">**MaximumVersion** パラメーターが指定されている場合、は、 `Find-Module` 指定されたバージョンを超えるモジュールの最新バージョンを返します。</span><span class="sxs-lookup"><span data-stu-id="dea94-118">If the **MaximumVersion** parameter is specified, `Find-Module` returns the newest version of the module that does not exceed the version specified.</span></span>

<span data-ttu-id="dea94-119">**RequiredVersion** パラメーターが指定されている場合は、 `Find-Module` 指定したバージョンと完全に一致するモジュールバージョンのみが返されます。</span><span class="sxs-lookup"><span data-stu-id="dea94-119">If the **RequiredVersion** parameter is specified, `Find-Module` only returns the module version that is an exact match to the specified version.</span></span> <span data-ttu-id="dea94-120">`Find-Module` は、ソース間で名前の競合が発生する可能性があるため、使用可能なすべてのモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="dea94-120">`Find-Module` searches through all available modules, because name conflicts between sources can occur.</span></span>

<span data-ttu-id="dea94-121">次の例では、唯一の登録済みリポジトリとして [PowerShell ギャラリー](https://www.powershellgallery.com/) を使用します。</span><span class="sxs-lookup"><span data-stu-id="dea94-121">The following examples use the [PowerShell Gallery](https://www.powershellgallery.com/) as the only registered repository.</span></span> <span data-ttu-id="dea94-122">`Get-PSRepository` 登録されているリポジトリを表示します。</span><span class="sxs-lookup"><span data-stu-id="dea94-122">`Get-PSRepository` displays the registered repositories.</span></span> <span data-ttu-id="dea94-123">複数の登録済みリポジトリがある場合は、パラメーターを使用して、 `-Repository` リポジトリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-123">If you have multiple registered repositories, use the `-Repository` parameter to specify the repository's name.</span></span>

## <span data-ttu-id="dea94-124">例</span><span class="sxs-lookup"><span data-stu-id="dea94-124">EXAMPLES</span></span>

### <span data-ttu-id="dea94-125">例 1: 名前を指定してモジュールを検索する</span><span class="sxs-lookup"><span data-stu-id="dea94-125">Example 1: Find a module by name</span></span>

<span data-ttu-id="dea94-126">この例では、既定のリポジトリでモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="dea94-126">This example finds a module in the default repository.</span></span>

```powershell
Find-Module -Name PowerShellGet
```

```Output
Version   Name              Repository           Description
-------   ----              ----------           -----------
2.1.0     PowerShellGet     PSGallery            PowerShell module with commands for discovering...
```

<span data-ttu-id="dea94-127">コマンドレットでは、 `Find-Module` **Name** パラメーターを使用して **PowerShellGet** モジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-127">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span>

### <span data-ttu-id="dea94-128">例 2: 類似した名前のモジュールを検索する</span><span class="sxs-lookup"><span data-stu-id="dea94-128">Example 2: Find modules with similar names</span></span>

<span data-ttu-id="dea94-129">この例では、アスタリスク ( `*` ) ワイルドカードを使用して、類似した名前のモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="dea94-129">This example uses the asterisk (`*`) wildcard to find modules with similar names.</span></span>

```powershell
Find-Module -Name PowerShell*
```

```Output
Version   Name                            Repository    Description
-------   ----                            ----------    -----------
0.4.0     powershell-yaml                 PSGallery     Powershell module for serializing and...
2.1.0     PowerShellGet                   PSGallery     PowerShell module with commands for...
1.9       Powershell.Helper.Extension     PSGallery     # Powershell.Helper.Extension...
3.1       PowerShellHumanizer             PSGallery     PowerShell Humanizer wraps Humanizer...
4.0       PowerShellISEModule             PSGallery     a module that adds capability to the ISE
```

<span data-ttu-id="dea94-130">コマンドレットでは、 `Find-Module` **Name** パラメーターをアスタリスク () ワイルドカードと共に使用して、 `*` **PowerShell** を含むすべてのモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="dea94-130">The `Find-Module` cmdlet uses the **Name** parameter with the asterisk (`*`) wildcard to find all modules that contain **PowerShell** .</span></span>

### <span data-ttu-id="dea94-131">例 3: 最小バージョンでモジュールを検索する</span><span class="sxs-lookup"><span data-stu-id="dea94-131">Example 3: Find a module by minimum version</span></span>

<span data-ttu-id="dea94-132">この例では、モジュールの最小バージョンを検索します。</span><span class="sxs-lookup"><span data-stu-id="dea94-132">This example searches for a module's minimum version.</span></span> <span data-ttu-id="dea94-133">リポジトリに新しいバージョンのモジュールが含まれている場合は、新しいバージョンが返されます。</span><span class="sxs-lookup"><span data-stu-id="dea94-133">If the repository contains a newer version of the module, the newer version is returned.</span></span>

```powershell
Find-Module -Name PowerShellGet -MinimumVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="dea94-134">コマンドレットでは、 `Find-Module` **Name** パラメーターを使用して **PowerShellGet** モジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-134">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="dea94-135">**MinimumVersion** はバージョン **1.6.5** を指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-135">The **MinimumVersion** specifies version **1.6.5** .</span></span> <span data-ttu-id="dea94-136">`Find-Module` は、最小バージョンを超えており、最新バージョンであるため、PowerShellGet バージョン **2.1.0** を返します。</span><span class="sxs-lookup"><span data-stu-id="dea94-136">`Find-Module` returns PowerShellGet version **2.1.0** because it exceeds the minimum version and is the most current version.</span></span>

### <span data-ttu-id="dea94-137">例 4: 特定のバージョンでモジュールを検索する</span><span class="sxs-lookup"><span data-stu-id="dea94-137">Example 4: Find a module by specific version</span></span>

<span data-ttu-id="dea94-138">この例では、モジュールの特定のバージョンを表すオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="dea94-138">This example returns an object that represents a module's specific version.</span></span> <span data-ttu-id="dea94-139">指定したバージョンが見つからない場合は、エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="dea94-139">If the specified version is not found, an error is returned.</span></span>

```powershell
Find-Module -Name PowerShellGet -RequiredVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
1.6.5     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="dea94-140">コマンドレットでは、 `Find-Module` **Name** パラメーターを使用して **PowerShellGet** モジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-140">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="dea94-141">**RequiredVersion** パラメーターにはバージョン **1.6.5** が指定されています。</span><span class="sxs-lookup"><span data-stu-id="dea94-141">The **RequiredVersion** parameter specifies version **1.6.5** .</span></span>

### <span data-ttu-id="dea94-142">例 5: 特定のリポジトリでモジュールを検索する</span><span class="sxs-lookup"><span data-stu-id="dea94-142">Example 5: Find a module in a specific repository</span></span>

<span data-ttu-id="dea94-143">この例では、 **repository** パラメーターを使用して、特定のリポジトリ内のモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="dea94-143">This example uses the **Repository** parameter to find a module in a specific repository.</span></span>

```powershell
Find-Module -Name PowerShellGet -Repository PSGallery
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="dea94-144">コマンドレットでは、 `Find-Module` **Name** パラメーターを使用して **PowerShellGet** モジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-144">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="dea94-145">**Repository** パラメーターは、 **PSGallery** リポジトリを検索するように指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-145">The **Repository** parameter specifies to search the **PSGallery** repository.</span></span>

### <span data-ttu-id="dea94-146">例 6: 複数のリポジトリでモジュールを検索する</span><span class="sxs-lookup"><span data-stu-id="dea94-146">Example 6: Find a module in multiple repositories</span></span>

<span data-ttu-id="dea94-147">この例では、を使用して `Register-PSRepository` リポジトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-147">This example uses the `Register-PSRepository` to specify a repository.</span></span> <span data-ttu-id="dea94-148">`Find-Module` は、リポジトリを使用してモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="dea94-148">`Find-Module` uses the repository to search for a module.</span></span>

```powershell
Register-PSRepository -Name MySource -SourceLocation https://www.myget.org/F/powershellgetdemo/
Find-Module -Name Contoso* -Repository PSGallery, MySource
```

```Output
Repository    Version   Name             Description
----------    -------   ----             -----------
PSGallery     2.0.0.0   ContosoServer    Cmdlets and DSC resources for managing Contoso Server...
MySource      1.2.0.0   ContosoClient    Cmdlets and DSC resources for managing Contoso Client...
```

<span data-ttu-id="dea94-149">コマンドレットにより、 `Register-PSRepository` 新しいリポジトリが登録されます。</span><span class="sxs-lookup"><span data-stu-id="dea94-149">The `Register-PSRepository` cmdlet registers a new repository.</span></span> <span data-ttu-id="dea94-150">**Name** パラメーターを指定すると、 **MySource** という名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="dea94-150">The **Name** parameter assigns the name **MySource** .</span></span> <span data-ttu-id="dea94-151">**SourceLocation** パラメーターでは、リポジトリのアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-151">The **SourceLocation** parameter specifies the repository's address.</span></span>

<span data-ttu-id="dea94-152">コマンドレットでは、 `Find-Module` **Name** パラメーターをアスタリスク ( `*` ) ワイルドカードと共に使用して **Contoso** モジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-152">The `Find-Module` cmdlet uses the **Name** parameter with the asterisk (`*`) wildcard to specify the **Contoso** module.</span></span> <span data-ttu-id="dea94-153">**Repository** パラメーターでは、 **PSGallery** と **MySource** の2つのリポジトリを検索するように指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-153">The **Repository** parameter specifies to search two repositories, **PSGallery** and **MySource** .</span></span>

### <span data-ttu-id="dea94-154">例 7: DSC リソースが含まれているモジュールを検索する</span><span class="sxs-lookup"><span data-stu-id="dea94-154">Example 7: Find a module that contains a DSC resource</span></span>

<span data-ttu-id="dea94-155">このコマンドは、DSC リソースを含むモジュールを返します。</span><span class="sxs-lookup"><span data-stu-id="dea94-155">This command returns modules that contain DSC resources.</span></span> <span data-ttu-id="dea94-156">**インクルード** パラメーターには、リポジトリの検索に使用される4つの定義済み機能があります。</span><span class="sxs-lookup"><span data-stu-id="dea94-156">The **Includes** parameter has four predefined functionalities that are used to search the repository.</span></span> <span data-ttu-id="dea94-157">[タブの完了] を使用すると、 **インクルード** パラメーターでサポートされている4つの機能を表示できます。</span><span class="sxs-lookup"><span data-stu-id="dea94-157">Use tab-complete to display the four functionalities supported by the **Includes** parameter.</span></span>

```powershell
Find-Module -Repository PSGallery -Includes DscResource
```

```Output
Version     Name                            Repository    Description
-------     ----                            ----------    -----------
2.7.0       Carbon                          PSGallery     Carbon is a PowerShell module...
8.5.0.0     xPSDesiredStateConfiguration    PSGallery     The xPSDesiredStateConfiguration module...
1.3.1       PackageManagement               PSGallery     PackageManagement (a.k.a. OneGet) is...
2.7.0.0     xWindowsUpdate                  PSGallery     Module with DSC Resources...
3.2.0.0     xCertificate                    PSGallery     This module includes DSC resources...
3.1.0.0     xPowerShellExecutionPolicy      PSGallery     This DSC resource can change the user...
```

<span data-ttu-id="dea94-158">このコマンドレットでは、repository パラメーターを使用して `Find-Module` リポジトリ **PSGallery** を検索します。 **Repository**</span><span class="sxs-lookup"><span data-stu-id="dea94-158">The `Find-Module` cmdlet uses the **Repository** parameter to search the repository, **PSGallery** .</span></span>
<span data-ttu-id="dea94-159">**インクルード** パラメーターは **DscResource** を指定します。これは、パラメーターがリポジトリで検索できる機能です。</span><span class="sxs-lookup"><span data-stu-id="dea94-159">The **Includes** parameter specifies **DscResource** , which is a functionality that the parameter can search for in the repository.</span></span>

### <span data-ttu-id="dea94-160">例 8: フィルターを使用してモジュールを検索する</span><span class="sxs-lookup"><span data-stu-id="dea94-160">Example 8: Find a module with a filter</span></span>

<span data-ttu-id="dea94-161">この例では、モジュールを検索するために、フィルターを使用してリポジトリを検索します。</span><span class="sxs-lookup"><span data-stu-id="dea94-161">In this example, to find modules, a filter is used to search the repository.</span></span>

<span data-ttu-id="dea94-162">NuGet ベースのリポジトリの場合、 **Filter** パラメーターは引数の名前、説明、およびタグを検索します。</span><span class="sxs-lookup"><span data-stu-id="dea94-162">For a NuGet-based repository, the **Filter** parameter searches through the name, description, and tags for the argument.</span></span>

```powershell
Find-Module -Filter AppDomain
```

```Output
Version    Name              Repository           Description
-------    ----              ----------           -----------
1.0.0.0  AppDomainConfig     PSGallery            Manipulate AppDomain configuration...
1.1.0    ClassExplorer       PSGallery            Quickly search the AppDomain for classes...
```

<span data-ttu-id="dea94-163">コマンドレットでは、 `Find-Module` **Filter** パラメーターを使用して、リポジトリで **AppDomain** を検索します。</span><span class="sxs-lookup"><span data-stu-id="dea94-163">The `Find-Module` cmdlet uses the **Filter** parameter to search the repository for **AppDomain** .</span></span>

## <span data-ttu-id="dea94-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dea94-164">PARAMETERS</span></span>

### <span data-ttu-id="dea94-165">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="dea94-165">-AllowPrerelease</span></span>

<span data-ttu-id="dea94-166">プレリリースとしてマークされた結果モジュールにを含めます。</span><span class="sxs-lookup"><span data-stu-id="dea94-166">Includes in the results modules marked as a pre-release.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dea94-167">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="dea94-167">-AllVersions</span></span>

<span data-ttu-id="dea94-168">すべてのバージョンのモジュールを結果に含めるように指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-168">Specifies to include all versions of a module in the results.</span></span> <span data-ttu-id="dea94-169">**AllVersions** パラメーターは、 **MinimumVersion** 、 **MaximumVersion** 、または **RequiredVersion** パラメーターと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="dea94-169">You cannot use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="dea94-170">-Command</span><span class="sxs-lookup"><span data-stu-id="dea94-170">-Command</span></span>

<span data-ttu-id="dea94-171">モジュール内で検索するコマンドの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-171">Specifies an array of commands to find in modules.</span></span> <span data-ttu-id="dea94-172">コマンドは、関数またはワークフローにすることができます。</span><span class="sxs-lookup"><span data-stu-id="dea94-172">A command can be a function or workflow.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dea94-173">-Credential</span><span class="sxs-lookup"><span data-stu-id="dea94-173">-Credential</span></span>

<span data-ttu-id="dea94-174">指定したパッケージプロバイダーまたはソースのモジュールをインストールする権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-174">Specifies a user account that has rights to install a module for a specified package provider or source.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="dea94-175">-DscResource</span><span class="sxs-lookup"><span data-stu-id="dea94-175">-DscResource</span></span>

<span data-ttu-id="dea94-176">DSC リソースを含むモジュールの名前または名前の一部を指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-176">Specifies the name, or part of the name, of modules that contain DSC resources.</span></span> <span data-ttu-id="dea94-177">PowerShell の規則ごとに、複数の引数を指定すると、 **または** 検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="dea94-177">Per PowerShell conventions, performs an **OR** search when you provide multiple arguments.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dea94-178">-Filter</span><span class="sxs-lookup"><span data-stu-id="dea94-178">-Filter</span></span>

<span data-ttu-id="dea94-179">**PackageManagement** プロバイダー固有の検索構文に基づくフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-179">Specifies a filter based on the **PackageManagement** provider-specific search syntax.</span></span> <span data-ttu-id="dea94-180">NuGet モジュールの場合、このパラメーターは、 [PowerShell ギャラリー](https://www.powershellgallery.com/) web サイトの検索バーを使用した検索に相当します。</span><span class="sxs-lookup"><span data-stu-id="dea94-180">For NuGet modules, this parameter is the equivalent of searching by using the Search bar on the [PowerShell Gallery](https://www.powershellgallery.com/) website.</span></span>

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

### <span data-ttu-id="dea94-181">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="dea94-181">-IncludeDependencies</span></span>

<span data-ttu-id="dea94-182">この操作に、 **Name** パラメーターで指定されたモジュールに依存するすべてのモジュールが含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="dea94-182">Indicates that this operation includes all modules that are dependent upon the module specified in the **Name** parameter.</span></span>

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

### <span data-ttu-id="dea94-183">-インクルード</span><span class="sxs-lookup"><span data-stu-id="dea94-183">-Includes</span></span>

<span data-ttu-id="dea94-184">特定の種類の PowerShell 機能を含むモジュールだけを返します。</span><span class="sxs-lookup"><span data-stu-id="dea94-184">Returns only those modules that include specific kinds of PowerShell functionality.</span></span> <span data-ttu-id="dea94-185">たとえば、 **DSCResource** を含むモジュールだけを検索する場合があります。</span><span class="sxs-lookup"><span data-stu-id="dea94-185">For example, you might only want to find modules that include **DSCResource** .</span></span> <span data-ttu-id="dea94-186">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dea94-186">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="dea94-187">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="dea94-187">Cmdlet</span></span>
- <span data-ttu-id="dea94-188">DscResource</span><span class="sxs-lookup"><span data-stu-id="dea94-188">DscResource</span></span>
- <span data-ttu-id="dea94-189">機能</span><span class="sxs-lookup"><span data-stu-id="dea94-189">Function</span></span>
- <span data-ttu-id="dea94-190">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="dea94-190">RoleCapability</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: DscResource, Cmdlet, Function, RoleCapability

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dea94-191">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="dea94-191">-MaximumVersion</span></span>

<span data-ttu-id="dea94-192">検索結果に含めるモジュールの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-192">Specifies the maximum, or latest, version of the module to include in the search results.</span></span>
<span data-ttu-id="dea94-193">**MaximumVersion** と **RequiredVersion** を同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="dea94-193">**MaximumVersion** and **RequiredVersion** cannot be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="dea94-194">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="dea94-194">-MinimumVersion</span></span>

<span data-ttu-id="dea94-195">結果に含めるモジュールの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-195">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="dea94-196">**MinimumVersion** および **RequiredVersion** を同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="dea94-196">**MinimumVersion** and **RequiredVersion** cannot be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="dea94-197">-Name</span><span class="sxs-lookup"><span data-stu-id="dea94-197">-Name</span></span>

<span data-ttu-id="dea94-198">リポジトリ内で検索するモジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-198">Specifies the names of modules to search for in the repository.</span></span> <span data-ttu-id="dea94-199">モジュール名のコンマ区切りのリストが受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="dea94-199">A comma-separated list of module names is accepted.</span></span> <span data-ttu-id="dea94-200">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dea94-200">Wildcards are accepted.</span></span>

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

### <span data-ttu-id="dea94-201">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="dea94-201">-Proxy</span></span>

<span data-ttu-id="dea94-202">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-202">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="dea94-203">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="dea94-203">-ProxyCredential</span></span>

<span data-ttu-id="dea94-204">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-204">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="dea94-205">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="dea94-205">-Repository</span></span>

<span data-ttu-id="dea94-206">**Repository** パラメーターを使用して、モジュールを検索するリポジトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-206">Use the **Repository** parameter to specify which repository to search for a module.</span></span> <span data-ttu-id="dea94-207">複数のリポジトリが登録されている場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="dea94-207">Used when multiple repositories are registered.</span></span> <span data-ttu-id="dea94-208">リポジトリのコンマ区切りリストを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="dea94-208">Accepts a comma-separated list of repositories.</span></span> <span data-ttu-id="dea94-209">リポジトリを登録するには、を使用 `Register-PSRepository` します。</span><span class="sxs-lookup"><span data-stu-id="dea94-209">To register a repository, use `Register-PSRepository`.</span></span> <span data-ttu-id="dea94-210">登録されているリポジトリを表示するには、を使用 `Get-PSRepository` します。</span><span class="sxs-lookup"><span data-stu-id="dea94-210">To display registered repositories, use `Get-PSRepository`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dea94-211">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="dea94-211">-RequiredVersion</span></span>

<span data-ttu-id="dea94-212">結果に含めるモジュールの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-212">Specifies the exact version number of the module to include in the results.</span></span> <span data-ttu-id="dea94-213">**RequiredVersion** は、 **MinimumVersion** または **MaximumVersion** と同じコマンドでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="dea94-213">**RequiredVersion** cannot be used in the same command as **MinimumVersion** or **MaximumVersion** .</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="dea94-214">-Find-rolecapability</span><span class="sxs-lookup"><span data-stu-id="dea94-214">-RoleCapability</span></span>

<span data-ttu-id="dea94-215">ロール機能の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-215">Specifies an array of role capabilities.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dea94-216">-Tag</span><span class="sxs-lookup"><span data-stu-id="dea94-216">-Tag</span></span>

<span data-ttu-id="dea94-217">タグの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="dea94-217">Specifies an array of tags.</span></span> <span data-ttu-id="dea94-218">タグの例としては、 **DesiredStateConfiguration** 、 **DSC** 、 **Dscresourcekit** 、 **psmodule** などがあります。</span><span class="sxs-lookup"><span data-stu-id="dea94-218">Example tags include **DesiredStateConfiguration** , **DSC** , **DSCResourceKit** , or **PSModule** .</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dea94-219">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="dea94-219">CommonParameters</span></span>

<span data-ttu-id="dea94-220">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="dea94-220">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dea94-221">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dea94-221">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dea94-222">入力</span><span class="sxs-lookup"><span data-stu-id="dea94-222">INPUTS</span></span>

### <span data-ttu-id="dea94-223">System.String[]</span><span class="sxs-lookup"><span data-stu-id="dea94-223">System.String[]</span></span>

### <span data-ttu-id="dea94-224">System.String</span><span class="sxs-lookup"><span data-stu-id="dea94-224">System.String</span></span>

### <span data-ttu-id="dea94-225">System.Uri</span><span class="sxs-lookup"><span data-stu-id="dea94-225">System.Uri</span></span>

### <span data-ttu-id="dea94-226">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="dea94-226">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="dea94-227">出力</span><span class="sxs-lookup"><span data-stu-id="dea94-227">OUTPUTS</span></span>

### <span data-ttu-id="dea94-228">できる psrepositoryiteminfo</span><span class="sxs-lookup"><span data-stu-id="dea94-228">PSRepositoryItemInfo</span></span>

<span data-ttu-id="dea94-229">`Find-Module` などのコマンドレットにパイプラインから送信できる **できる psrepositoryiteminfo** オブジェクトを作成し `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="dea94-229">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to cmdlets such as `Install-Module`.</span></span>

## <span data-ttu-id="dea94-230">注</span><span class="sxs-lookup"><span data-stu-id="dea94-230">NOTES</span></span>

<span data-ttu-id="dea94-231">このコマンドレットは、powershell 5.0 以降の PowerShell、Windows 7、または windows 2008 R2 以降の Windows のリリースで実行されます。</span><span class="sxs-lookup"><span data-stu-id="dea94-231">This cmdlet runs on PowerShell 5.0 or later releases of PowerShell, on Windows 7, or Windows 2008 R2 and later releases of Windows.</span></span>

## <span data-ttu-id="dea94-232">関連リンク</span><span class="sxs-lookup"><span data-stu-id="dea94-232">RELATED LINKS</span></span>

[<span data-ttu-id="dea94-233">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="dea94-233">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="dea94-234">Install-Module</span><span class="sxs-lookup"><span data-stu-id="dea94-234">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="dea94-235">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="dea94-235">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="dea94-236">Save-Module</span><span class="sxs-lookup"><span data-stu-id="dea94-236">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="dea94-237">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="dea94-237">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="dea94-238">Update-Module</span><span class="sxs-lookup"><span data-stu-id="dea94-238">Update-Module</span></span>](Update-Module.md)

[<span data-ttu-id="dea94-239">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="dea94-239">Register-PSRepository</span></span>](Register-PSRepository.md)