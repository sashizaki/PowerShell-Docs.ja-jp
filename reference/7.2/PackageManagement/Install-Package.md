---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 05/23/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-package?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Package
ms.openlocfilehash: 1518be0d34733e36217b46cbbf496e580ec7b649
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99602199"
---
# <span data-ttu-id="27b27-102">Install-Package</span><span class="sxs-lookup"><span data-stu-id="27b27-102">Install-Package</span></span>

## <span data-ttu-id="27b27-103">概要</span><span class="sxs-lookup"><span data-stu-id="27b27-103">SYNOPSIS</span></span>
<span data-ttu-id="27b27-104">1つまたは複数のソフトウェアパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="27b27-104">Installs one or more software packages.</span></span>

## <span data-ttu-id="27b27-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="27b27-105">SYNTAX</span></span>

### <span data-ttu-id="27b27-106">PackageBySearch (既定)</span><span class="sxs-lookup"><span data-stu-id="27b27-106">PackageBySearch (Default)</span></span>

```
Install-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="27b27-107">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="27b27-107">PackageByInputObject</span></span>

```
Install-Package [-InputObject] <SoftwareIdentity[]> [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="27b27-108">NuGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="27b27-108">NuGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="27b27-109">NuGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="27b27-109">NuGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="27b27-110">PowerShellGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="27b27-110">PowerShellGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

### <span data-ttu-id="27b27-111">PowerShellGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="27b27-111">PowerShellGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

## <span data-ttu-id="27b27-112">Description</span><span class="sxs-lookup"><span data-stu-id="27b27-112">DESCRIPTION</span></span>

<span data-ttu-id="27b27-113">`Install-Package`コマンドレットにより、ローカルコンピューターに1つまたは複数のソフトウェアパッケージがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="27b27-113">The `Install-Package` cmdlet installs one or more software packages on the local computer.</span></span> <span data-ttu-id="27b27-114">ソフトウェアソースが複数ある場合は、およびを使用して、 `Get-PackageProvider` `Get-PackageSource` プロバイダーの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="27b27-114">If you have multiple software sources, use `Get-PackageProvider` and `Get-PackageSource` to display details about your providers.</span></span>

## <span data-ttu-id="27b27-115">例</span><span class="sxs-lookup"><span data-stu-id="27b27-115">EXAMPLES</span></span>

### <span data-ttu-id="27b27-116">例 1: パッケージ名を指定してパッケージをインストールする</span><span class="sxs-lookup"><span data-stu-id="27b27-116">Example 1: Install a package by package name</span></span>

<span data-ttu-id="27b27-117">コマンドレットにより、 `Install-Package` ソフトウェアパッケージとその依存関係がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="27b27-117">The `Install-Package` cmdlet installs a software package and its dependencies.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -Credential Contoso\TestUser
```

<span data-ttu-id="27b27-118">`Install-Package` では、パラメーターを使用してパッケージの **名前** と **ソース** を指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-118">`Install-Package` uses parameters to specify the packages **Name** and **Source**.</span></span> <span data-ttu-id="27b27-119">**Credential** パラメーターでは、パッケージをインストールするためのアクセス許可を持つドメインユーザーアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="27b27-119">The **Credential** parameter uses a domain user account with permissions to install packages.</span></span> <span data-ttu-id="27b27-120">コマンドを実行すると、ユーザーアカウントのパスワードの入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="27b27-120">The command prompts you for the user account password.</span></span>

### <span data-ttu-id="27b27-121">例 2: Find-Package を使用してパッケージをインストールする</span><span class="sxs-lookup"><span data-stu-id="27b27-121">Example 2: Use Find-Package to install a package</span></span>

<span data-ttu-id="27b27-122">この例では、によって返されるオブジェクトはパイプラインに送信され、 `Find-Package` によってインストールされ `Install-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="27b27-122">In this example, the object returned by `Find-Package` is sent down the pipeline and installed by `Install-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -Source MyNuGet | Install-Package
```

<span data-ttu-id="27b27-123">`Find-Package` は、 **Name** および **Source** パラメーターを使用してパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="27b27-123">`Find-Package` uses the **Name** and **Source** parameters to locate a package.</span></span> <span data-ttu-id="27b27-124">オブジェクトがパイプラインで送信され、 `Install-Package` パッケージがローカルコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="27b27-124">The object is sent down the pipeline and `Install-Package` installs the package on the local computer.</span></span>

### <span data-ttu-id="27b27-125">例 3: バージョンの範囲を指定してパッケージをインストールする</span><span class="sxs-lookup"><span data-stu-id="27b27-125">Example 3: Install packages by specifying a range of versions</span></span>

<span data-ttu-id="27b27-126">`Install-Package`**MinimumVersion** パラメーターと **MaximumVersion** パラメーターを使用して、ソフトウェアのバージョンの範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-126">`Install-Package` uses the **MinimumVersion** and **MaximumVersion** parameters to specify a range of software versions.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -MinimumVersion 2.8.0 -MaximumVersion 2.9.0
```

<span data-ttu-id="27b27-127">`Install-Package` は、 **Name** および **Source** パラメーターを使用してパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="27b27-127">`Install-Package` uses the **Name** and **Source** parameters to find a package.</span></span> <span data-ttu-id="27b27-128">**MinimumVersion** パラメーターと **MaximumVersion** パラメーターでは、ソフトウェアのバージョンの範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-128">The **MinimumVersion** and **MaximumVersion** parameters specify a range of software versions.</span></span> <span data-ttu-id="27b27-129">範囲内の最大バージョンがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="27b27-129">The highest version in the range is installed.</span></span>

## <span data-ttu-id="27b27-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="27b27-130">PARAMETERS</span></span>

### <span data-ttu-id="27b27-131">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="27b27-131">-AcceptLicense</span></span>

 <span data-ttu-id="27b27-132">**Acceptlicense** は、インストール時にライセンス契約に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="27b27-132">**AcceptLicense** automatically accepts the license agreement during installation.</span></span>

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

### <span data-ttu-id="27b27-133">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="27b27-133">-AllowClobber</span></span>

<span data-ttu-id="27b27-134">既存のコマンドとの競合に関する警告メッセージを上書きします。</span><span class="sxs-lookup"><span data-stu-id="27b27-134">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="27b27-135">インストールされているコマンドと同じ名前を持つ既存のコマンドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="27b27-135">Overwrites existing commands that have the same name as commands being installed.</span></span>

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

### <span data-ttu-id="27b27-136">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="27b27-136">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="27b27-137">プレリリースとしてマークされているパッケージのインストールを許可します。</span><span class="sxs-lookup"><span data-stu-id="27b27-137">Allows the installation of packages marked as prerelease.</span></span>

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

### <span data-ttu-id="27b27-138">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="27b27-138">-AllVersions</span></span>

<span data-ttu-id="27b27-139">`Install-Package` パッケージの利用可能なすべてのバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="27b27-139">`Install-Package` installs all available versions of the package.</span></span> <span data-ttu-id="27b27-140">既定では、最新バージョンのみがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="27b27-140">By default, only the newest version is installed.</span></span>

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

### <span data-ttu-id="27b27-141">-Command</span><span class="sxs-lookup"><span data-stu-id="27b27-141">-Command</span></span>

<span data-ttu-id="27b27-142">検索する1つ以上のコマンドを指定し `Install-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="27b27-142">Specifies one or more commands that `Install-Package` searches.</span></span>

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

### <span data-ttu-id="27b27-143">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="27b27-143">-ConfigFile</span></span>

<span data-ttu-id="27b27-144">構成ファイルを含むパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-144">Specifies a path that contains a configuration file.</span></span>

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

### <span data-ttu-id="27b27-145">-Contains</span><span class="sxs-lookup"><span data-stu-id="27b27-145">-Contains</span></span>

<span data-ttu-id="27b27-146">`Install-Package` Contains パラメーターに、オブジェクトのプロパティ値と一致する値が指定 **されて** いる場合に、オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="27b27-146">`Install-Package` gets objects if the **Contains** parameter specifies a value that matches any of the object's property values.</span></span>

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

### <span data-ttu-id="27b27-147">-Credential</span><span class="sxs-lookup"><span data-stu-id="27b27-147">-Credential</span></span>

<span data-ttu-id="27b27-148">コンピューターにアクセスしてコマンドを実行するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-148">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="27b27-149">コマンドレットによって生成されたユーザー名 ( **User01**、 **domain01\user01」** など) を入力するか、 **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="27b27-149">Type a user name, such as **User01**, **Domain01\User01**, or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="27b27-150">ユーザー名を入力すると、パスワードの入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27b27-150">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="27b27-151">**Credential** パラメーターが指定されていない場合、は `Install-Package` 現在のユーザーを使用します。</span><span class="sxs-lookup"><span data-stu-id="27b27-151">When the **Credential** parameter isn't specified, `Install-Package` uses the current user.</span></span>

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

### <span data-ttu-id="27b27-152">-Destination</span><span class="sxs-lookup"><span data-stu-id="27b27-152">-Destination</span></span>

<span data-ttu-id="27b27-153">入力オブジェクトへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-153">Specifies a path to an input object.</span></span>

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

### <span data-ttu-id="27b27-154">-DscResource</span><span class="sxs-lookup"><span data-stu-id="27b27-154">-DscResource</span></span>

<span data-ttu-id="27b27-155">によって検索される Desired State Configuration (DSC) リソースを1つ以上指定し `Install-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="27b27-155">Specifies one or more Desired State Configuration (DSC) resources that are searched by `Install-Package`.</span></span> <span data-ttu-id="27b27-156">`Find-DscResource`DSC リソースを検索するには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="27b27-156">Use the `Find-DscResource` cmdlet to find DSC resources.</span></span>

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

### <span data-ttu-id="27b27-157">-ExcludeVersion</span><span class="sxs-lookup"><span data-stu-id="27b27-157">-ExcludeVersion</span></span>

<span data-ttu-id="27b27-158">フォルダーパスのバージョン番号を除外するには、スイッチを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-158">Switch to exclude the version number in the folder path.</span></span>

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

### <span data-ttu-id="27b27-159">-Filter</span><span class="sxs-lookup"><span data-stu-id="27b27-159">-Filter</span></span>

<span data-ttu-id="27b27-160">**名前** と **説明** のプロパティ内で検索する用語を指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-160">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

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

### <span data-ttu-id="27b27-161">-FilterOnTag</span><span class="sxs-lookup"><span data-stu-id="27b27-161">-FilterOnTag</span></span>

<span data-ttu-id="27b27-162">結果をフィルター処理し、指定したタグを含まない結果を除外するタグを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-162">Specifies a tag that filters results and excludes results that don't contain the specified tag.</span></span>

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

### <span data-ttu-id="27b27-163">-Force</span><span class="sxs-lookup"><span data-stu-id="27b27-163">-Force</span></span>

<span data-ttu-id="27b27-164">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="27b27-164">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="27b27-165">は、セキュリティを除いて、が成功するのを妨げる制限をオーバーライドし `Install-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="27b27-165">Overrides restrictions that prevent `Install-Package` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="27b27-166">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="27b27-166">-ForceBootstrap</span></span>

<span data-ttu-id="27b27-167">指定されたパッケージのパッケージプロバイダーを自動的にインストールするように **PackageManagement** に強制します。</span><span class="sxs-lookup"><span data-stu-id="27b27-167">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="27b27-168">-ヘッダー</span><span class="sxs-lookup"><span data-stu-id="27b27-168">-Headers</span></span>

<span data-ttu-id="27b27-169">パッケージヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-169">Specifies the package headers.</span></span>

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

### <span data-ttu-id="27b27-170">-インクルード</span><span class="sxs-lookup"><span data-stu-id="27b27-170">-Includes</span></span>

<span data-ttu-id="27b27-171">`Install-Package`がすべてのパッケージの種類を検索するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-171">Specifies whether `Install-Package` should find all package types.</span></span> <span data-ttu-id="27b27-172">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="27b27-172">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="27b27-173">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="27b27-173">Cmdlet</span></span>
- <span data-ttu-id="27b27-174">DscResource</span><span class="sxs-lookup"><span data-stu-id="27b27-174">DscResource</span></span>
- <span data-ttu-id="27b27-175">Function</span><span class="sxs-lookup"><span data-stu-id="27b27-175">Function</span></span>
- <span data-ttu-id="27b27-176">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="27b27-176">RoleCapability</span></span>
- <span data-ttu-id="27b27-177">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="27b27-177">Workflow</span></span>

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

### <span data-ttu-id="27b27-178">-InputObject</span><span class="sxs-lookup"><span data-stu-id="27b27-178">-InputObject</span></span>

<span data-ttu-id="27b27-179">パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="27b27-179">Accepts pipeline input.</span></span> <span data-ttu-id="27b27-180">パッケージの **ソフトウェア id** の種類を使用してパッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-180">Specifies a package by using the package's **SoftwareIdentity** type.</span></span>
<span data-ttu-id="27b27-181">`Find-Package`**ソフトウェア id** オブジェクトを出力します。</span><span class="sxs-lookup"><span data-stu-id="27b27-181">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

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

### <span data-ttu-id="27b27-182">-InstallUpdate</span><span class="sxs-lookup"><span data-stu-id="27b27-182">-InstallUpdate</span></span>

<span data-ttu-id="27b27-183">が更新プログラムをインストールすることを示し `Install-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="27b27-183">Indicates that `Install-Package` installs updates.</span></span>

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

### <span data-ttu-id="27b27-184">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="27b27-184">-MaximumVersion</span></span>

<span data-ttu-id="27b27-185">インストールするパッケージの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-185">Specifies the maximum allowed package version that you want to install.</span></span> <span data-ttu-id="27b27-186">このパラメーターを指定しない場合、に `Install-Package` よってパッケージの最新バージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="27b27-186">If you don't specify this parameter, `Install-Package` installs the package's newest version.</span></span>

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

### <span data-ttu-id="27b27-187">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="27b27-187">-MinimumVersion</span></span>

<span data-ttu-id="27b27-188">インストールするパッケージの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-188">Specifies the minimum allowed package version that you want to install.</span></span> <span data-ttu-id="27b27-189">このパラメーターを追加しない場合、は、 `Install-Package` **MaximumVersion** パラメーターで指定された任意のバージョンを満たすパッケージの最新バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="27b27-189">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="27b27-190">-Name</span><span class="sxs-lookup"><span data-stu-id="27b27-190">-Name</span></span>

<span data-ttu-id="27b27-191">1つまたは複数のパッケージ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-191">Specifies one or more package names.</span></span> <span data-ttu-id="27b27-192">複数のパッケージ名は、コンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="27b27-192">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="27b27-193">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="27b27-193">-NoPathUpdate</span></span>

<span data-ttu-id="27b27-194">**Nopathupdate** はコマンドレットにのみ適用さ `Install-Script` れます。</span><span class="sxs-lookup"><span data-stu-id="27b27-194">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="27b27-195">**Nopathupdate** はプロバイダーによって追加される動的パラメーターであり、ではサポートされていません `Install-Package` 。</span><span class="sxs-lookup"><span data-stu-id="27b27-195">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Install-Package`.</span></span>

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

### <span data-ttu-id="27b27-196">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="27b27-196">-PackageManagementProvider</span></span>

<span data-ttu-id="27b27-197">**PackageManagement** プロバイダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-197">Specifies the name of the **PackageManagement** provider.</span></span>

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

### <span data-ttu-id="27b27-198">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="27b27-198">-ProviderName</span></span>

<span data-ttu-id="27b27-199">パッケージの検索範囲を指定する1つまたは複数のパッケージプロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-199">Specifies one or more package provider names to which to scope your package search.</span></span> <span data-ttu-id="27b27-200">`Get-PackageProvider` コマンドレットを実行して、パッケージ プロバイダー名を取得できます。</span><span class="sxs-lookup"><span data-stu-id="27b27-200">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="27b27-201">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="27b27-201">-Proxy</span></span>

<span data-ttu-id="27b27-202">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-202">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="27b27-203">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="27b27-203">-ProxyCredential</span></span>

<span data-ttu-id="27b27-204">**プロキシ** パラメーターによって指定されたプロキシサーバーを使用する権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-204">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="27b27-205">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="27b27-205">-PublishLocation</span></span>

<span data-ttu-id="27b27-206">パッケージの発行場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-206">Specifies the path to a package's published location.</span></span>

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

### <span data-ttu-id="27b27-207">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="27b27-207">-RequiredVersion</span></span>

<span data-ttu-id="27b27-208">インストールするパッケージの許可された正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-208">Specifies the exact allowed version of the package that you want to install.</span></span> <span data-ttu-id="27b27-209">このパラメーターを追加しない場合、は、 `Install-Package` **MaximumVersion** パラメーターで指定された任意のバージョンを満たすパッケージの最新バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="27b27-209">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="27b27-210">-Find-rolecapability</span><span class="sxs-lookup"><span data-stu-id="27b27-210">-RoleCapability</span></span>

<span data-ttu-id="27b27-211">ロール機能の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-211">Specifies an array of role capabilities.</span></span>

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

### <span data-ttu-id="27b27-212">-スコープ</span><span class="sxs-lookup"><span data-stu-id="27b27-212">-Scope</span></span>

<span data-ttu-id="27b27-213">パッケージをインストールするスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-213">Specifies the scope for which to install the package.</span></span> <span data-ttu-id="27b27-214">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="27b27-214">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="27b27-215">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="27b27-215">CurrentUser</span></span>
- <span data-ttu-id="27b27-216">AllUsers</span><span class="sxs-lookup"><span data-stu-id="27b27-216">AllUsers</span></span>

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

### <span data-ttu-id="27b27-217">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="27b27-217">-ScriptPublishLocation</span></span>

<span data-ttu-id="27b27-218">スクリプトの発行先のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-218">Specifies the path to a script's published location.</span></span>

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

### <span data-ttu-id="27b27-219">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="27b27-219">-ScriptSourceLocation</span></span>

<span data-ttu-id="27b27-220">スクリプトのソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-220">Specifies the script source location.</span></span>

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

### <span data-ttu-id="27b27-221">-SkipDependencies</span><span class="sxs-lookup"><span data-stu-id="27b27-221">-SkipDependencies</span></span>

<span data-ttu-id="27b27-222">ソフトウェアの依存関係のインストールをスキップします。</span><span class="sxs-lookup"><span data-stu-id="27b27-222">Skips the installation of software dependencies.</span></span>

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

### <span data-ttu-id="27b27-223">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="27b27-223">-SkipPublisherCheck</span></span>

<span data-ttu-id="27b27-224">インストールされているバージョンよりも新しいバージョンのパッケージを取得できます。</span><span class="sxs-lookup"><span data-stu-id="27b27-224">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="27b27-225">たとえば、信頼された発行元によってデジタル署名されているが新しいバージョンのパッケージはデジタル署名されていません。</span><span class="sxs-lookup"><span data-stu-id="27b27-225">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

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

### <span data-ttu-id="27b27-226">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="27b27-226">-SkipValidate</span></span>

<span data-ttu-id="27b27-227">パッケージの資格情報の検証をスキップするスイッチ。</span><span class="sxs-lookup"><span data-stu-id="27b27-227">Switch that skips validating the credentials of a package.</span></span>

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

### <span data-ttu-id="27b27-228">-Source</span><span class="sxs-lookup"><span data-stu-id="27b27-228">-Source</span></span>

<span data-ttu-id="27b27-229">1つまたは複数のパッケージソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-229">Specifies one or more package sources.</span></span> <span data-ttu-id="27b27-230">複数のパッケージソース名は、コンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="27b27-230">Multiple package source names must be separated by commas.</span></span>
<span data-ttu-id="27b27-231">パッケージソース名を取得するには、 `Get-PackageSource` コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="27b27-231">You can get package source names by running the `Get-PackageSource` cmdlet.</span></span>

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

### <span data-ttu-id="27b27-232">-Tag</span><span class="sxs-lookup"><span data-stu-id="27b27-232">-Tag</span></span>

<span data-ttu-id="27b27-233">パッケージメタデータ内で検索する1つ以上の文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-233">Specifies one or more strings to search for in the package metadata.</span></span>

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

### <span data-ttu-id="27b27-234">-Type</span><span class="sxs-lookup"><span data-stu-id="27b27-234">-Type</span></span>

<span data-ttu-id="27b27-235">モジュール、スクリプト、またはその両方を含むパッケージを検索するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b27-235">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="27b27-236">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="27b27-236">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="27b27-237">Module</span><span class="sxs-lookup"><span data-stu-id="27b27-237">Module</span></span>
- <span data-ttu-id="27b27-238">スクリプト</span><span class="sxs-lookup"><span data-stu-id="27b27-238">Script</span></span>
- <span data-ttu-id="27b27-239">すべて</span><span class="sxs-lookup"><span data-stu-id="27b27-239">All</span></span>

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

### <span data-ttu-id="27b27-240">-Confirm</span><span class="sxs-lookup"><span data-stu-id="27b27-240">-Confirm</span></span>

<span data-ttu-id="27b27-241">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27b27-241">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="27b27-242">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="27b27-242">-WhatIf</span></span>

<span data-ttu-id="27b27-243">コマンドレットが実行された場合に何が起こるか `Install-Package` を示します。</span><span class="sxs-lookup"><span data-stu-id="27b27-243">Shows what would happen if `Install-Package` cmdlet is run.</span></span> <span data-ttu-id="27b27-244">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="27b27-244">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="27b27-245">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="27b27-245">CommonParameters</span></span>

<span data-ttu-id="27b27-246">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="27b27-246">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="27b27-247">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27b27-247">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="27b27-248">入力</span><span class="sxs-lookup"><span data-stu-id="27b27-248">INPUTS</span></span>

### <span data-ttu-id="27b27-249">`Install-Package` パイプラインからの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="27b27-249">`Install-Package` accepts input from the pipeline.</span></span>

## <span data-ttu-id="27b27-250">出力</span><span class="sxs-lookup"><span data-stu-id="27b27-250">OUTPUTS</span></span>

### <span data-ttu-id="27b27-251">ソフトウェア Id []</span><span class="sxs-lookup"><span data-stu-id="27b27-251">SoftwareIdentity[]</span></span>

## <span data-ttu-id="27b27-252">注</span><span class="sxs-lookup"><span data-stu-id="27b27-252">NOTES</span></span>

<span data-ttu-id="27b27-253">コマンドにパッケージプロバイダーを含めると、コマンドレットで動的パラメーターを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="27b27-253">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="27b27-254">動的パラメーターは、パッケージプロバイダーに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="27b27-254">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="27b27-255">コマンドレットにより、 `Get-Help` コマンドレットのパラメーターセットが一覧表示され、プロバイダーのパラメーターセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="27b27-255">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="27b27-256">たとえば、には、、、 `Install-Package` およびを含む **PowerShellGet** パラメーターが設定されてい `-NoPathUpdate` `AllowClobber` `SkipPublisherCheck` ます。</span><span class="sxs-lookup"><span data-stu-id="27b27-256">For example, `Install-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27b27-257">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="27b27-257">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="27b27-258">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="27b27-258">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="27b27-259">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="27b27-259">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="27b27-260">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27b27-260">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="27b27-261">関連リンク</span><span class="sxs-lookup"><span data-stu-id="27b27-261">RELATED LINKS</span></span>

[<span data-ttu-id="27b27-262">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="27b27-262">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="27b27-263">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="27b27-263">Find-DscResource</span></span>](../PowershellGet/Find-DscResource.md)

[<span data-ttu-id="27b27-264">Get-Help</span><span class="sxs-lookup"><span data-stu-id="27b27-264">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="27b27-265">Get-Package</span><span class="sxs-lookup"><span data-stu-id="27b27-265">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="27b27-266">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="27b27-266">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="27b27-267">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="27b27-267">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="27b27-268">Find-Package</span><span class="sxs-lookup"><span data-stu-id="27b27-268">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="27b27-269">Save-Package</span><span class="sxs-lookup"><span data-stu-id="27b27-269">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="27b27-270">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="27b27-270">Uninstall-Package</span></span>](Uninstall-Package.md)
