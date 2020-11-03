---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 05/23/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-package?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Package
ms.openlocfilehash: 058ed7f90e63bd7ca7a29cf6c89864a30255662a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213291"
---
# <span data-ttu-id="3d7a9-103">Install-Package</span><span class="sxs-lookup"><span data-stu-id="3d7a9-103">Install-Package</span></span>

## <span data-ttu-id="3d7a9-104">概要</span><span class="sxs-lookup"><span data-stu-id="3d7a9-104">SYNOPSIS</span></span>
<span data-ttu-id="3d7a9-105">1つまたは複数のソフトウェアパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-105">Installs one or more software packages.</span></span>

## <span data-ttu-id="3d7a9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3d7a9-106">SYNTAX</span></span>

### <span data-ttu-id="3d7a9-107">PackageBySearch (既定)</span><span class="sxs-lookup"><span data-stu-id="3d7a9-107">PackageBySearch (Default)</span></span>

```
Install-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="3d7a9-108">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="3d7a9-108">PackageByInputObject</span></span>

```
Install-Package [-InputObject] <SoftwareIdentity[]> [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="3d7a9-109">プログラム: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="3d7a9-109">Programs:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-IncludeWindowsInstaller]
 [-IncludeSystemComponent] [<CommonParameters>]
```

### <span data-ttu-id="3d7a9-110">プログラム: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="3d7a9-110">Programs:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-IncludeWindowsInstaller]
 [-IncludeSystemComponent] [<CommonParameters>]
```

### <span data-ttu-id="3d7a9-111">msi: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="3d7a9-111">msi:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AdditionalArguments <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="3d7a9-112">msi: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="3d7a9-112">msi:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AdditionalArguments <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="3d7a9-113">NuGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="3d7a9-113">NuGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="3d7a9-114">NuGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="3d7a9-114">NuGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="3d7a9-115">PowerShellGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="3d7a9-115">PowerShellGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

### <span data-ttu-id="3d7a9-116">PowerShellGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="3d7a9-116">PowerShellGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

## <span data-ttu-id="3d7a9-117">Description</span><span class="sxs-lookup"><span data-stu-id="3d7a9-117">DESCRIPTION</span></span>

<span data-ttu-id="3d7a9-118">`Install-Package`コマンドレットにより、ローカルコンピューターに1つまたは複数のソフトウェアパッケージがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-118">The `Install-Package` cmdlet installs one or more software packages on the local computer.</span></span> <span data-ttu-id="3d7a9-119">ソフトウェアソースが複数ある場合は、およびを使用して、 `Get-PackageProvider` `Get-PackageSource` プロバイダーの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-119">If you have multiple software sources, use `Get-PackageProvider` and `Get-PackageSource` to display details about your providers.</span></span>

## <span data-ttu-id="3d7a9-120">例</span><span class="sxs-lookup"><span data-stu-id="3d7a9-120">EXAMPLES</span></span>

### <span data-ttu-id="3d7a9-121">例 1: パッケージ名を指定してパッケージをインストールする</span><span class="sxs-lookup"><span data-stu-id="3d7a9-121">Example 1: Install a package by package name</span></span>

<span data-ttu-id="3d7a9-122">コマンドレットにより、 `Install-Package` ソフトウェアパッケージとその依存関係がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-122">The `Install-Package` cmdlet installs a software package and its dependencies.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -Credential Contoso\TestUser
```

<span data-ttu-id="3d7a9-123">`Install-Package` では、パラメーターを使用してパッケージの **名前** と **ソース** を指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-123">`Install-Package` uses parameters to specify the packages **Name** and **Source** .</span></span> <span data-ttu-id="3d7a9-124">**Credential** パラメーターでは、パッケージをインストールするためのアクセス許可を持つドメインユーザーアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-124">The **Credential** parameter uses a domain user account with permissions to install packages.</span></span> <span data-ttu-id="3d7a9-125">コマンドを実行すると、ユーザーアカウントのパスワードの入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-125">The command prompts you for the user account password.</span></span>

### <span data-ttu-id="3d7a9-126">例 2: Find-Package を使用してパッケージをインストールする</span><span class="sxs-lookup"><span data-stu-id="3d7a9-126">Example 2: Use Find-Package to install a package</span></span>

<span data-ttu-id="3d7a9-127">この例では、によって返されるオブジェクトはパイプラインに送信され、 `Find-Package` によってインストールされ `Install-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-127">In this example, the object returned by `Find-Package` is sent down the pipeline and installed by `Install-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -Source MyNuGet | Install-Package
```

<span data-ttu-id="3d7a9-128">`Find-Package` は、 **Name** および **Source** パラメーターを使用してパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-128">`Find-Package` uses the **Name** and **Source** parameters to locate a package.</span></span> <span data-ttu-id="3d7a9-129">オブジェクトがパイプラインで送信され、 `Install-Package` パッケージがローカルコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-129">The object is sent down the pipeline and `Install-Package` installs the package on the local computer.</span></span>

### <span data-ttu-id="3d7a9-130">例 3: バージョンの範囲を指定してパッケージをインストールする</span><span class="sxs-lookup"><span data-stu-id="3d7a9-130">Example 3: Install packages by specifying a range of versions</span></span>

<span data-ttu-id="3d7a9-131">`Install-Package`**MinimumVersion** パラメーターと **MaximumVersion** パラメーターを使用して、ソフトウェアのバージョンの範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-131">`Install-Package` uses the **MinimumVersion** and **MaximumVersion** parameters to specify a range of software versions.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -MinimumVersion 2.8.0 -MaximumVersion 2.9.0
```

<span data-ttu-id="3d7a9-132">`Install-Package` は、 **Name** および **Source** パラメーターを使用してパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-132">`Install-Package` uses the **Name** and **Source** parameters to find a package.</span></span> <span data-ttu-id="3d7a9-133">**MinimumVersion** パラメーターと **MaximumVersion** パラメーターでは、ソフトウェアのバージョンの範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-133">The **MinimumVersion** and **MaximumVersion** parameters specify a range of software versions.</span></span> <span data-ttu-id="3d7a9-134">範囲内の最大バージョンがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-134">The highest version in the range is installed.</span></span>

## <span data-ttu-id="3d7a9-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3d7a9-135">PARAMETERS</span></span>

### <span data-ttu-id="3d7a9-136">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="3d7a9-136">-AcceptLicense</span></span>

 <span data-ttu-id="3d7a9-137">**Acceptlicense** は、インストール時にライセンス契約に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-137">**AcceptLicense** automatically accepts the license agreement during installation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-138">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="3d7a9-138">-AllowClobber</span></span>

<span data-ttu-id="3d7a9-139">既存のコマンドとの競合に関する警告メッセージを上書きします。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-139">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="3d7a9-140">インストールされているコマンドと同じ名前を持つ既存のコマンドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-140">Overwrites existing commands that have the same name as commands being installed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-141">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="3d7a9-141">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="3d7a9-142">プレリリースとしてマークされているパッケージのインストールを許可します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-142">Allows the installation of packages marked as prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject, PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-143">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="3d7a9-143">-AllVersions</span></span>

<span data-ttu-id="3d7a9-144">`Install-Package` パッケージの利用可能なすべてのバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-144">`Install-Package` installs all available versions of the package.</span></span> <span data-ttu-id="3d7a9-145">既定では、最新バージョンのみがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-145">By default, only the newest version is installed.</span></span>

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

### <span data-ttu-id="3d7a9-146">-Command</span><span class="sxs-lookup"><span data-stu-id="3d7a9-146">-Command</span></span>

<span data-ttu-id="3d7a9-147">検索する1つ以上のコマンドを指定し `Install-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-147">Specifies one or more commands that `Install-Package` searches.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-148">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="3d7a9-148">-ConfigFile</span></span>

<span data-ttu-id="3d7a9-149">構成ファイルを含むパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-149">Specifies a path that contains a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-150">-Contains</span><span class="sxs-lookup"><span data-stu-id="3d7a9-150">-Contains</span></span>

<span data-ttu-id="3d7a9-151">`Install-Package` Contains パラメーターに、オブジェクトのプロパティ値と一致する値が指定 **されて** いる場合に、オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-151">`Install-Package` gets objects if the **Contains** parameter specifies a value that matches any of the object's property values.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-152">-Credential</span><span class="sxs-lookup"><span data-stu-id="3d7a9-152">-Credential</span></span>

<span data-ttu-id="3d7a9-153">コンピューターにアクセスしてコマンドを実行するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-153">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="3d7a9-154">コマンドレットによって生成されたユーザー名 ( **User01** 、 **domain01\user01」** など) を入力するか、 **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-154">Type a user name, such as **User01** , **Domain01\User01** , or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="3d7a9-155">ユーザー名を入力すると、パスワードの入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-155">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="3d7a9-156">**Credential** パラメーターが指定されていない場合、は `Install-Package` 現在のユーザーを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-156">When the **Credential** parameter isn't specified, `Install-Package` uses the current user.</span></span>

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

### <span data-ttu-id="3d7a9-157">-Destination</span><span class="sxs-lookup"><span data-stu-id="3d7a9-157">-Destination</span></span>

<span data-ttu-id="3d7a9-158">入力オブジェクトへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-158">Specifies a path to an input object.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-159">-DscResource</span><span class="sxs-lookup"><span data-stu-id="3d7a9-159">-DscResource</span></span>

<span data-ttu-id="3d7a9-160">によって検索される Desired State Configuration (DSC) リソースを1つ以上指定し `Install-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-160">Specifies one or more Desired State Configuration (DSC) resources that are searched by `Install-Package`.</span></span> <span data-ttu-id="3d7a9-161">`Find-DscResource`DSC リソースを検索するには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-161">Use the `Find-DscResource` cmdlet to find DSC resources.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-162">-ExcludeVersion</span><span class="sxs-lookup"><span data-stu-id="3d7a9-162">-ExcludeVersion</span></span>

<span data-ttu-id="3d7a9-163">フォルダーパスのバージョン番号を除外するには、スイッチを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-163">Switch to exclude the version number in the folder path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-164">-Filter</span><span class="sxs-lookup"><span data-stu-id="3d7a9-164">-Filter</span></span>

<span data-ttu-id="3d7a9-165">**名前** と **説明** のプロパティ内で検索する用語を指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-165">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-166">-FilterOnTag</span><span class="sxs-lookup"><span data-stu-id="3d7a9-166">-FilterOnTag</span></span>

<span data-ttu-id="3d7a9-167">結果をフィルター処理し、指定したタグを含まない結果を除外するタグを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-167">Specifies a tag that filters results and excludes results that don't contain the specified tag.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-168">-Force</span><span class="sxs-lookup"><span data-stu-id="3d7a9-168">-Force</span></span>

<span data-ttu-id="3d7a9-169">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-169">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="3d7a9-170">は、セキュリティを除いて、が成功するのを妨げる制限をオーバーライドし `Install-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-170">Overrides restrictions that prevent `Install-Package` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="3d7a9-171">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="3d7a9-171">-ForceBootstrap</span></span>

<span data-ttu-id="3d7a9-172">指定されたパッケージのパッケージプロバイダーを自動的にインストールするように **PackageManagement** に強制します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-172">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="3d7a9-173">-ヘッダー</span><span class="sxs-lookup"><span data-stu-id="3d7a9-173">-Headers</span></span>

<span data-ttu-id="3d7a9-174">パッケージヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-174">Specifies the package headers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-175">-インクルード</span><span class="sxs-lookup"><span data-stu-id="3d7a9-175">-Includes</span></span>

<span data-ttu-id="3d7a9-176">`Install-Package`がすべてのパッケージの種類を検索するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-176">Specifies whether `Install-Package` should find all package types.</span></span> <span data-ttu-id="3d7a9-177">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-177">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="3d7a9-178">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="3d7a9-178">Cmdlet</span></span>
- <span data-ttu-id="3d7a9-179">DscResource</span><span class="sxs-lookup"><span data-stu-id="3d7a9-179">DscResource</span></span>
- <span data-ttu-id="3d7a9-180">機能</span><span class="sxs-lookup"><span data-stu-id="3d7a9-180">Function</span></span>
- <span data-ttu-id="3d7a9-181">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="3d7a9-181">RoleCapability</span></span>
- <span data-ttu-id="3d7a9-182">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="3d7a9-182">Workflow</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:
Accepted values: Cmdlet, DscResource, Function, RoleCapability, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-183">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3d7a9-183">-InputObject</span></span>

<span data-ttu-id="3d7a9-184">パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-184">Accepts pipeline input.</span></span> <span data-ttu-id="3d7a9-185">パッケージの **ソフトウェア id** の種類を使用してパッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-185">Specifies a package by using the package's **SoftwareIdentity** type.</span></span>
<span data-ttu-id="3d7a9-186">`Find-Package`**ソフトウェア id** オブジェクトを出力します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-186">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

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

### <span data-ttu-id="3d7a9-187">-InstallUpdate</span><span class="sxs-lookup"><span data-stu-id="3d7a9-187">-InstallUpdate</span></span>

<span data-ttu-id="3d7a9-188">が更新プログラムをインストールすることを示し `Install-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-188">Indicates that `Install-Package` installs updates.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-189">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="3d7a9-189">-MaximumVersion</span></span>

<span data-ttu-id="3d7a9-190">インストールするパッケージの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-190">Specifies the maximum allowed package version that you want to install.</span></span> <span data-ttu-id="3d7a9-191">このパラメーターを指定しない場合、に `Install-Package` よってパッケージの最新バージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-191">If you don't specify this parameter, `Install-Package` installs the package's newest version.</span></span>

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

### <span data-ttu-id="3d7a9-192">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="3d7a9-192">-MinimumVersion</span></span>

<span data-ttu-id="3d7a9-193">インストールするパッケージの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-193">Specifies the minimum allowed package version that you want to install.</span></span> <span data-ttu-id="3d7a9-194">このパラメーターを追加しない場合、は、 `Install-Package` **MaximumVersion** パラメーターで指定された任意のバージョンを満たすパッケージの最新バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-194">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="3d7a9-195">-Name</span><span class="sxs-lookup"><span data-stu-id="3d7a9-195">-Name</span></span>

<span data-ttu-id="3d7a9-196">1つまたは複数のパッケージ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-196">Specifies one or more package names.</span></span> <span data-ttu-id="3d7a9-197">複数のパッケージ名は、コンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-197">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="3d7a9-198">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="3d7a9-198">-NoPathUpdate</span></span>

<span data-ttu-id="3d7a9-199">**Nopathupdate** はコマンドレットにのみ適用さ `Install-Script` れます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-199">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="3d7a9-200">**Nopathupdate** はプロバイダーによって追加される動的パラメーターであり、ではサポートされていません `Install-Package` 。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-200">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Install-Package`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-201">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="3d7a9-201">-PackageManagementProvider</span></span>

<span data-ttu-id="3d7a9-202">**PackageManagement** プロバイダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-202">Specifies the name of the **PackageManagement** provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-203">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="3d7a9-203">-ProviderName</span></span>

<span data-ttu-id="3d7a9-204">パッケージの検索範囲を指定する1つまたは複数のパッケージプロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-204">Specifies one or more package provider names to which to scope your package search.</span></span> <span data-ttu-id="3d7a9-205">`Get-PackageProvider` コマンドレットを実行して、パッケージ プロバイダー名を取得できます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-205">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="3d7a9-206">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="3d7a9-206">-Proxy</span></span>

<span data-ttu-id="3d7a9-207">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-207">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="3d7a9-208">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="3d7a9-208">-ProxyCredential</span></span>

<span data-ttu-id="3d7a9-209">**プロキシ** パラメーターによって指定されたプロキシサーバーを使用する権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-209">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="3d7a9-210">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="3d7a9-210">-PublishLocation</span></span>

<span data-ttu-id="3d7a9-211">パッケージの発行場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-211">Specifies the path to a package's published location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-212">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="3d7a9-212">-RequiredVersion</span></span>

<span data-ttu-id="3d7a9-213">インストールするパッケージの許可された正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-213">Specifies the exact allowed version of the package that you want to install.</span></span> <span data-ttu-id="3d7a9-214">このパラメーターを追加しない場合、は、 `Install-Package` **MaximumVersion** パラメーターで指定された任意のバージョンを満たすパッケージの最新バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-214">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="3d7a9-215">-Find-rolecapability</span><span class="sxs-lookup"><span data-stu-id="3d7a9-215">-RoleCapability</span></span>

<span data-ttu-id="3d7a9-216">ロール機能の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-216">Specifies an array of role capabilities.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-217">-スコープ</span><span class="sxs-lookup"><span data-stu-id="3d7a9-217">-Scope</span></span>

<span data-ttu-id="3d7a9-218">パッケージをインストールするスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-218">Specifies the scope for which to install the package.</span></span> <span data-ttu-id="3d7a9-219">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-219">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="3d7a9-220">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="3d7a9-220">CurrentUser</span></span>
- <span data-ttu-id="3d7a9-221">AllUsers</span><span class="sxs-lookup"><span data-stu-id="3d7a9-221">AllUsers</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject, PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-222">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="3d7a9-222">-ScriptPublishLocation</span></span>

<span data-ttu-id="3d7a9-223">スクリプトの発行先のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-223">Specifies the path to a script's published location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-224">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="3d7a9-224">-ScriptSourceLocation</span></span>

<span data-ttu-id="3d7a9-225">スクリプトのソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-225">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-226">-SkipDependencies</span><span class="sxs-lookup"><span data-stu-id="3d7a9-226">-SkipDependencies</span></span>

<span data-ttu-id="3d7a9-227">ソフトウェアの依存関係のインストールをスキップします。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-227">Skips the installation of software dependencies.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-228">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="3d7a9-228">-SkipPublisherCheck</span></span>

<span data-ttu-id="3d7a9-229">インストールされているバージョンよりも新しいバージョンのパッケージを取得できます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-229">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="3d7a9-230">たとえば、信頼された発行元によってデジタル署名されているが新しいバージョンのパッケージはデジタル署名されていません。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-230">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-231">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="3d7a9-231">-SkipValidate</span></span>

<span data-ttu-id="3d7a9-232">パッケージの資格情報の検証をスキップするスイッチ。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-232">Switch that skips validating the credentials of a package.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-233">-Source</span><span class="sxs-lookup"><span data-stu-id="3d7a9-233">-Source</span></span>

<span data-ttu-id="3d7a9-234">1つまたは複数のパッケージソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-234">Specifies one or more package sources.</span></span> <span data-ttu-id="3d7a9-235">複数のパッケージソース名は、コンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-235">Multiple package source names must be separated by commas.</span></span>
<span data-ttu-id="3d7a9-236">パッケージソース名を取得するには、 `Get-PackageSource` コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-236">You can get package source names by running the `Get-PackageSource` cmdlet.</span></span>

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

### <span data-ttu-id="3d7a9-237">-Tag</span><span class="sxs-lookup"><span data-stu-id="3d7a9-237">-Tag</span></span>

<span data-ttu-id="3d7a9-238">パッケージメタデータ内で検索する1つ以上の文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-238">Specifies one or more strings to search for in the package metadata.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-239">-Type</span><span class="sxs-lookup"><span data-stu-id="3d7a9-239">-Type</span></span>

<span data-ttu-id="3d7a9-240">モジュール、スクリプト、またはその両方を含むパッケージを検索するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-240">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="3d7a9-241">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-241">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="3d7a9-242">[Module]</span><span class="sxs-lookup"><span data-stu-id="3d7a9-242">Module</span></span>
- <span data-ttu-id="3d7a9-243">スクリプト</span><span class="sxs-lookup"><span data-stu-id="3d7a9-243">Script</span></span>
- <span data-ttu-id="3d7a9-244">All</span><span class="sxs-lookup"><span data-stu-id="3d7a9-244">All</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-245">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3d7a9-245">-Confirm</span></span>

<span data-ttu-id="3d7a9-246">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-246">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3d7a9-247">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3d7a9-247">-WhatIf</span></span>

<span data-ttu-id="3d7a9-248">コマンドレットが実行された場合に何が起こるか `Install-Package` を示します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-248">Shows what would happen if `Install-Package` cmdlet is run.</span></span> <span data-ttu-id="3d7a9-249">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-249">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3d7a9-250">-AdditionalArguments</span><span class="sxs-lookup"><span data-stu-id="3d7a9-250">-AdditionalArguments</span></span>

<span data-ttu-id="3d7a9-251">インストールのための追加の引数を1つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-251">Specifies one or more additional arguments for installation.</span></span>

```yaml
Type: System.String[]
Parameter Sets: msi:PackageBySearch, msi:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-252">-IncludeSystemComponent</span><span class="sxs-lookup"><span data-stu-id="3d7a9-252">-IncludeSystemComponent</span></span>

<span data-ttu-id="3d7a9-253">このコマンドレットが結果にシステムコンポーネントを含めることを示します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-253">Indicates that this cmdlet includes system components in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs:PackageBySearch, Programs:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-254">-IncludeWindowsInstaller</span><span class="sxs-lookup"><span data-stu-id="3d7a9-254">-IncludeWindowsInstaller</span></span>

<span data-ttu-id="3d7a9-255">このコマンドレットによって、結果に Windows インストーラーが含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-255">Indicates that this cmdlet includes the Windows installer in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs:PackageBySearch, Programs:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7a9-256">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="3d7a9-256">CommonParameters</span></span>

<span data-ttu-id="3d7a9-257">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-257">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3d7a9-258">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-258">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3d7a9-259">入力</span><span class="sxs-lookup"><span data-stu-id="3d7a9-259">INPUTS</span></span>

### <span data-ttu-id="3d7a9-260">`Install-Package` パイプラインからの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-260">`Install-Package` accepts input from the pipeline.</span></span>

## <span data-ttu-id="3d7a9-261">出力</span><span class="sxs-lookup"><span data-stu-id="3d7a9-261">OUTPUTS</span></span>

### <span data-ttu-id="3d7a9-262">ソフトウェア Id []</span><span class="sxs-lookup"><span data-stu-id="3d7a9-262">SoftwareIdentity[]</span></span>

## <span data-ttu-id="3d7a9-263">注</span><span class="sxs-lookup"><span data-stu-id="3d7a9-263">NOTES</span></span>

<span data-ttu-id="3d7a9-264">コマンドにパッケージプロバイダーを含めると、コマンドレットで動的パラメーターを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-264">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="3d7a9-265">動的パラメーターは、パッケージプロバイダーに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-265">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="3d7a9-266">コマンドレットにより、 `Get-Help` コマンドレットのパラメーターセットが一覧表示され、プロバイダーのパラメーターセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-266">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="3d7a9-267">たとえば、には、、、 `Install-Package` およびを含む **PowerShellGet** パラメーターが設定されてい `-NoPathUpdate` `AllowClobber` `SkipPublisherCheck` ます。</span><span class="sxs-lookup"><span data-stu-id="3d7a9-267">For example, `Install-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="3d7a9-268">関連リンク</span><span class="sxs-lookup"><span data-stu-id="3d7a9-268">RELATED LINKS</span></span>

[<span data-ttu-id="3d7a9-269">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="3d7a9-269">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="3d7a9-270">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="3d7a9-270">Find-DscResource</span></span>](../PowershellGet/Find-DscResource.md)

[<span data-ttu-id="3d7a9-271">Get-Help</span><span class="sxs-lookup"><span data-stu-id="3d7a9-271">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="3d7a9-272">Get-Package</span><span class="sxs-lookup"><span data-stu-id="3d7a9-272">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="3d7a9-273">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="3d7a9-273">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="3d7a9-274">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="3d7a9-274">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="3d7a9-275">Find-Package</span><span class="sxs-lookup"><span data-stu-id="3d7a9-275">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="3d7a9-276">Save-Package</span><span class="sxs-lookup"><span data-stu-id="3d7a9-276">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="3d7a9-277">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="3d7a9-277">Uninstall-Package</span></span>](Uninstall-Package.md)
