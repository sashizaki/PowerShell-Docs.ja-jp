---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 05/23/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-package?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Package
ms.openlocfilehash: 7a99c4c00f809c2ec418618b2c1322d2552d1120
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215787"
---
# <span data-ttu-id="a8b7b-103">Install-Package</span><span class="sxs-lookup"><span data-stu-id="a8b7b-103">Install-Package</span></span>

## <span data-ttu-id="a8b7b-104">概要</span><span class="sxs-lookup"><span data-stu-id="a8b7b-104">SYNOPSIS</span></span>
<span data-ttu-id="a8b7b-105">1つまたは複数のソフトウェアパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-105">Installs one or more software packages.</span></span>

## <span data-ttu-id="a8b7b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a8b7b-106">SYNTAX</span></span>

### <span data-ttu-id="a8b7b-107">PackageBySearch (既定)</span><span class="sxs-lookup"><span data-stu-id="a8b7b-107">PackageBySearch (Default)</span></span>

```
Install-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="a8b7b-108">PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="a8b7b-108">PackageByInputObject</span></span>

```
Install-Package [-InputObject] <SoftwareIdentity[]> [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="a8b7b-109">NuGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="a8b7b-109">NuGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="a8b7b-110">NuGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="a8b7b-110">NuGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="a8b7b-111">PowerShellGet: PackageBySearch</span><span class="sxs-lookup"><span data-stu-id="a8b7b-111">PowerShellGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

### <span data-ttu-id="a8b7b-112">PowerShellGet: PackageByInputObject</span><span class="sxs-lookup"><span data-stu-id="a8b7b-112">PowerShellGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

## <span data-ttu-id="a8b7b-113">Description</span><span class="sxs-lookup"><span data-stu-id="a8b7b-113">DESCRIPTION</span></span>

<span data-ttu-id="a8b7b-114">`Install-Package`コマンドレットにより、ローカルコンピューターに1つまたは複数のソフトウェアパッケージがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-114">The `Install-Package` cmdlet installs one or more software packages on the local computer.</span></span> <span data-ttu-id="a8b7b-115">ソフトウェアソースが複数ある場合は、およびを使用して、 `Get-PackageProvider` `Get-PackageSource` プロバイダーの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-115">If you have multiple software sources, use `Get-PackageProvider` and `Get-PackageSource` to display details about your providers.</span></span>

## <span data-ttu-id="a8b7b-116">例</span><span class="sxs-lookup"><span data-stu-id="a8b7b-116">EXAMPLES</span></span>

### <span data-ttu-id="a8b7b-117">例 1: パッケージ名を指定してパッケージをインストールする</span><span class="sxs-lookup"><span data-stu-id="a8b7b-117">Example 1: Install a package by package name</span></span>

<span data-ttu-id="a8b7b-118">コマンドレットにより、 `Install-Package` ソフトウェアパッケージとその依存関係がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-118">The `Install-Package` cmdlet installs a software package and its dependencies.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -Credential Contoso\TestUser
```

<span data-ttu-id="a8b7b-119">`Install-Package` では、パラメーターを使用してパッケージの **名前** と **ソース** を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-119">`Install-Package` uses parameters to specify the packages **Name** and **Source** .</span></span> <span data-ttu-id="a8b7b-120">**Credential** パラメーターでは、パッケージをインストールするためのアクセス許可を持つドメインユーザーアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-120">The **Credential** parameter uses a domain user account with permissions to install packages.</span></span> <span data-ttu-id="a8b7b-121">コマンドを実行すると、ユーザーアカウントのパスワードの入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-121">The command prompts you for the user account password.</span></span>

### <span data-ttu-id="a8b7b-122">例 2: Find-Package を使用してパッケージをインストールする</span><span class="sxs-lookup"><span data-stu-id="a8b7b-122">Example 2: Use Find-Package to install a package</span></span>

<span data-ttu-id="a8b7b-123">この例では、によって返されるオブジェクトはパイプラインに送信され、 `Find-Package` によってインストールされ `Install-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-123">In this example, the object returned by `Find-Package` is sent down the pipeline and installed by `Install-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -Source MyNuGet | Install-Package
```

<span data-ttu-id="a8b7b-124">`Find-Package` は、 **Name** および **Source** パラメーターを使用してパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-124">`Find-Package` uses the **Name** and **Source** parameters to locate a package.</span></span> <span data-ttu-id="a8b7b-125">オブジェクトがパイプラインで送信され、 `Install-Package` パッケージがローカルコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-125">The object is sent down the pipeline and `Install-Package` installs the package on the local computer.</span></span>

### <span data-ttu-id="a8b7b-126">例 3: バージョンの範囲を指定してパッケージをインストールする</span><span class="sxs-lookup"><span data-stu-id="a8b7b-126">Example 3: Install packages by specifying a range of versions</span></span>

<span data-ttu-id="a8b7b-127">`Install-Package`**MinimumVersion** パラメーターと **MaximumVersion** パラメーターを使用して、ソフトウェアのバージョンの範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-127">`Install-Package` uses the **MinimumVersion** and **MaximumVersion** parameters to specify a range of software versions.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -MinimumVersion 2.8.0 -MaximumVersion 2.9.0
```

<span data-ttu-id="a8b7b-128">`Install-Package` は、 **Name** および **Source** パラメーターを使用してパッケージを検索します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-128">`Install-Package` uses the **Name** and **Source** parameters to find a package.</span></span> <span data-ttu-id="a8b7b-129">**MinimumVersion** パラメーターと **MaximumVersion** パラメーターでは、ソフトウェアのバージョンの範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-129">The **MinimumVersion** and **MaximumVersion** parameters specify a range of software versions.</span></span> <span data-ttu-id="a8b7b-130">範囲内の最大バージョンがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-130">The highest version in the range is installed.</span></span>

## <span data-ttu-id="a8b7b-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a8b7b-131">PARAMETERS</span></span>

### <span data-ttu-id="a8b7b-132">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="a8b7b-132">-AcceptLicense</span></span>

 <span data-ttu-id="a8b7b-133">**Acceptlicense** は、インストール時にライセンス契約に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-133">**AcceptLicense** automatically accepts the license agreement during installation.</span></span>

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

### <span data-ttu-id="a8b7b-134">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="a8b7b-134">-AllowClobber</span></span>

<span data-ttu-id="a8b7b-135">既存のコマンドとの競合に関する警告メッセージを上書きします。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-135">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="a8b7b-136">インストールされているコマンドと同じ名前を持つ既存のコマンドを上書きします。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-136">Overwrites existing commands that have the same name as commands being installed.</span></span>

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

### <span data-ttu-id="a8b7b-137">-AllowPrereleaseVersions</span><span class="sxs-lookup"><span data-stu-id="a8b7b-137">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="a8b7b-138">プレリリースとしてマークされているパッケージのインストールを許可します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-138">Allows the installation of packages marked as prerelease.</span></span>

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

### <span data-ttu-id="a8b7b-139">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="a8b7b-139">-AllVersions</span></span>

<span data-ttu-id="a8b7b-140">`Install-Package` パッケージの利用可能なすべてのバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-140">`Install-Package` installs all available versions of the package.</span></span> <span data-ttu-id="a8b7b-141">既定では、最新バージョンのみがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-141">By default, only the newest version is installed.</span></span>

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

### <span data-ttu-id="a8b7b-142">-Command</span><span class="sxs-lookup"><span data-stu-id="a8b7b-142">-Command</span></span>

<span data-ttu-id="a8b7b-143">検索する1つ以上のコマンドを指定し `Install-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-143">Specifies one or more commands that `Install-Package` searches.</span></span>

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

### <span data-ttu-id="a8b7b-144">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="a8b7b-144">-ConfigFile</span></span>

<span data-ttu-id="a8b7b-145">構成ファイルを含むパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-145">Specifies a path that contains a configuration file.</span></span>

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

### <span data-ttu-id="a8b7b-146">-Contains</span><span class="sxs-lookup"><span data-stu-id="a8b7b-146">-Contains</span></span>

<span data-ttu-id="a8b7b-147">`Install-Package` Contains パラメーターに、オブジェクトのプロパティ値と一致する値が指定 **されて** いる場合に、オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-147">`Install-Package` gets objects if the **Contains** parameter specifies a value that matches any of the object's property values.</span></span>

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

### <span data-ttu-id="a8b7b-148">-Credential</span><span class="sxs-lookup"><span data-stu-id="a8b7b-148">-Credential</span></span>

<span data-ttu-id="a8b7b-149">コンピューターにアクセスしてコマンドを実行するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-149">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="a8b7b-150">コマンドレットによって生成されたユーザー名 ( **User01** 、 **domain01\user01」** など) を入力するか、 **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-150">Type a user name, such as **User01** , **Domain01\User01** , or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="a8b7b-151">ユーザー名を入力すると、パスワードの入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-151">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="a8b7b-152">**Credential** パラメーターが指定されていない場合、は `Install-Package` 現在のユーザーを使用します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-152">When the **Credential** parameter isn't specified, `Install-Package` uses the current user.</span></span>

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

### <span data-ttu-id="a8b7b-153">-Destination</span><span class="sxs-lookup"><span data-stu-id="a8b7b-153">-Destination</span></span>

<span data-ttu-id="a8b7b-154">入力オブジェクトへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-154">Specifies a path to an input object.</span></span>

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

### <span data-ttu-id="a8b7b-155">-DscResource</span><span class="sxs-lookup"><span data-stu-id="a8b7b-155">-DscResource</span></span>

<span data-ttu-id="a8b7b-156">によって検索される Desired State Configuration (DSC) リソースを1つ以上指定し `Install-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-156">Specifies one or more Desired State Configuration (DSC) resources that are searched by `Install-Package`.</span></span> <span data-ttu-id="a8b7b-157">`Find-DscResource`DSC リソースを検索するには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-157">Use the `Find-DscResource` cmdlet to find DSC resources.</span></span>

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

### <span data-ttu-id="a8b7b-158">-ExcludeVersion</span><span class="sxs-lookup"><span data-stu-id="a8b7b-158">-ExcludeVersion</span></span>

<span data-ttu-id="a8b7b-159">フォルダーパスのバージョン番号を除外するには、スイッチを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-159">Switch to exclude the version number in the folder path.</span></span>

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

### <span data-ttu-id="a8b7b-160">-Filter</span><span class="sxs-lookup"><span data-stu-id="a8b7b-160">-Filter</span></span>

<span data-ttu-id="a8b7b-161">**名前** と **説明** のプロパティ内で検索する用語を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-161">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

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

### <span data-ttu-id="a8b7b-162">-FilterOnTag</span><span class="sxs-lookup"><span data-stu-id="a8b7b-162">-FilterOnTag</span></span>

<span data-ttu-id="a8b7b-163">結果をフィルター処理し、指定したタグを含まない結果を除外するタグを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-163">Specifies a tag that filters results and excludes results that don't contain the specified tag.</span></span>

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

### <span data-ttu-id="a8b7b-164">-Force</span><span class="sxs-lookup"><span data-stu-id="a8b7b-164">-Force</span></span>

<span data-ttu-id="a8b7b-165">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-165">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="a8b7b-166">は、セキュリティを除いて、が成功するのを妨げる制限をオーバーライドし `Install-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-166">Overrides restrictions that prevent `Install-Package` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="a8b7b-167">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="a8b7b-167">-ForceBootstrap</span></span>

<span data-ttu-id="a8b7b-168">指定されたパッケージのパッケージプロバイダーを自動的にインストールするように **PackageManagement** に強制します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-168">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="a8b7b-169">-ヘッダー</span><span class="sxs-lookup"><span data-stu-id="a8b7b-169">-Headers</span></span>

<span data-ttu-id="a8b7b-170">パッケージヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-170">Specifies the package headers.</span></span>

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

### <span data-ttu-id="a8b7b-171">-インクルード</span><span class="sxs-lookup"><span data-stu-id="a8b7b-171">-Includes</span></span>

<span data-ttu-id="a8b7b-172">`Install-Package`がすべてのパッケージの種類を検索するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-172">Specifies whether `Install-Package` should find all package types.</span></span> <span data-ttu-id="a8b7b-173">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-173">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="a8b7b-174">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="a8b7b-174">Cmdlet</span></span>
- <span data-ttu-id="a8b7b-175">DscResource</span><span class="sxs-lookup"><span data-stu-id="a8b7b-175">DscResource</span></span>
- <span data-ttu-id="a8b7b-176">機能</span><span class="sxs-lookup"><span data-stu-id="a8b7b-176">Function</span></span>
- <span data-ttu-id="a8b7b-177">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="a8b7b-177">RoleCapability</span></span>
- <span data-ttu-id="a8b7b-178">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="a8b7b-178">Workflow</span></span>

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

### <span data-ttu-id="a8b7b-179">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a8b7b-179">-InputObject</span></span>

<span data-ttu-id="a8b7b-180">パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-180">Accepts pipeline input.</span></span> <span data-ttu-id="a8b7b-181">パッケージの **ソフトウェア id** の種類を使用してパッケージを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-181">Specifies a package by using the package's **SoftwareIdentity** type.</span></span>
<span data-ttu-id="a8b7b-182">`Find-Package`**ソフトウェア id** オブジェクトを出力します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-182">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

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

### <span data-ttu-id="a8b7b-183">-InstallUpdate</span><span class="sxs-lookup"><span data-stu-id="a8b7b-183">-InstallUpdate</span></span>

<span data-ttu-id="a8b7b-184">が更新プログラムをインストールすることを示し `Install-Package` ます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-184">Indicates that `Install-Package` installs updates.</span></span>

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

### <span data-ttu-id="a8b7b-185">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="a8b7b-185">-MaximumVersion</span></span>

<span data-ttu-id="a8b7b-186">インストールするパッケージの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-186">Specifies the maximum allowed package version that you want to install.</span></span> <span data-ttu-id="a8b7b-187">このパラメーターを指定しない場合、に `Install-Package` よってパッケージの最新バージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-187">If you don't specify this parameter, `Install-Package` installs the package's newest version.</span></span>

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

### <span data-ttu-id="a8b7b-188">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="a8b7b-188">-MinimumVersion</span></span>

<span data-ttu-id="a8b7b-189">インストールするパッケージの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-189">Specifies the minimum allowed package version that you want to install.</span></span> <span data-ttu-id="a8b7b-190">このパラメーターを追加しない場合、は、 `Install-Package` **MaximumVersion** パラメーターで指定された任意のバージョンを満たすパッケージの最新バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-190">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="a8b7b-191">-Name</span><span class="sxs-lookup"><span data-stu-id="a8b7b-191">-Name</span></span>

<span data-ttu-id="a8b7b-192">1つまたは複数のパッケージ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-192">Specifies one or more package names.</span></span> <span data-ttu-id="a8b7b-193">複数のパッケージ名は、コンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-193">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="a8b7b-194">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="a8b7b-194">-NoPathUpdate</span></span>

<span data-ttu-id="a8b7b-195">**Nopathupdate** はコマンドレットにのみ適用さ `Install-Script` れます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-195">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="a8b7b-196">**Nopathupdate** はプロバイダーによって追加される動的パラメーターであり、ではサポートされていません `Install-Package` 。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-196">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Install-Package`.</span></span>

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

### <span data-ttu-id="a8b7b-197">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="a8b7b-197">-PackageManagementProvider</span></span>

<span data-ttu-id="a8b7b-198">**PackageManagement** プロバイダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-198">Specifies the name of the **PackageManagement** provider.</span></span>

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

### <span data-ttu-id="a8b7b-199">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="a8b7b-199">-ProviderName</span></span>

<span data-ttu-id="a8b7b-200">パッケージの検索範囲を指定する1つまたは複数のパッケージプロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-200">Specifies one or more package provider names to which to scope your package search.</span></span> <span data-ttu-id="a8b7b-201">`Get-PackageProvider` コマンドレットを実行して、パッケージ プロバイダー名を取得できます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-201">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="a8b7b-202">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="a8b7b-202">-Proxy</span></span>

<span data-ttu-id="a8b7b-203">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-203">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="a8b7b-204">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="a8b7b-204">-ProxyCredential</span></span>

<span data-ttu-id="a8b7b-205">**プロキシ** パラメーターによって指定されたプロキシサーバーを使用する権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-205">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="a8b7b-206">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="a8b7b-206">-PublishLocation</span></span>

<span data-ttu-id="a8b7b-207">パッケージの発行場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-207">Specifies the path to a package's published location.</span></span>

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

### <span data-ttu-id="a8b7b-208">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="a8b7b-208">-RequiredVersion</span></span>

<span data-ttu-id="a8b7b-209">インストールするパッケージの許可された正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-209">Specifies the exact allowed version of the package that you want to install.</span></span> <span data-ttu-id="a8b7b-210">このパラメーターを追加しない場合、は、 `Install-Package` **MaximumVersion** パラメーターで指定された任意のバージョンを満たすパッケージの最新バージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-210">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="a8b7b-211">-Find-rolecapability</span><span class="sxs-lookup"><span data-stu-id="a8b7b-211">-RoleCapability</span></span>

<span data-ttu-id="a8b7b-212">ロール機能の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-212">Specifies an array of role capabilities.</span></span>

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

### <span data-ttu-id="a8b7b-213">-スコープ</span><span class="sxs-lookup"><span data-stu-id="a8b7b-213">-Scope</span></span>

<span data-ttu-id="a8b7b-214">パッケージをインストールするスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-214">Specifies the scope for which to install the package.</span></span> <span data-ttu-id="a8b7b-215">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-215">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="a8b7b-216">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="a8b7b-216">CurrentUser</span></span>
- <span data-ttu-id="a8b7b-217">AllUsers</span><span class="sxs-lookup"><span data-stu-id="a8b7b-217">AllUsers</span></span>

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

### <span data-ttu-id="a8b7b-218">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="a8b7b-218">-ScriptPublishLocation</span></span>

<span data-ttu-id="a8b7b-219">スクリプトの発行先のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-219">Specifies the path to a script's published location.</span></span>

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

### <span data-ttu-id="a8b7b-220">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="a8b7b-220">-ScriptSourceLocation</span></span>

<span data-ttu-id="a8b7b-221">スクリプトのソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-221">Specifies the script source location.</span></span>

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

### <span data-ttu-id="a8b7b-222">-SkipDependencies</span><span class="sxs-lookup"><span data-stu-id="a8b7b-222">-SkipDependencies</span></span>

<span data-ttu-id="a8b7b-223">ソフトウェアの依存関係のインストールをスキップします。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-223">Skips the installation of software dependencies.</span></span>

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

### <span data-ttu-id="a8b7b-224">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="a8b7b-224">-SkipPublisherCheck</span></span>

<span data-ttu-id="a8b7b-225">インストールされているバージョンよりも新しいバージョンのパッケージを取得できます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-225">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="a8b7b-226">たとえば、信頼された発行元によってデジタル署名されているが新しいバージョンのパッケージはデジタル署名されていません。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-226">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

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

### <span data-ttu-id="a8b7b-227">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="a8b7b-227">-SkipValidate</span></span>

<span data-ttu-id="a8b7b-228">パッケージの資格情報の検証をスキップするスイッチ。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-228">Switch that skips validating the credentials of a package.</span></span>

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

### <span data-ttu-id="a8b7b-229">-Source</span><span class="sxs-lookup"><span data-stu-id="a8b7b-229">-Source</span></span>

<span data-ttu-id="a8b7b-230">1つまたは複数のパッケージソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-230">Specifies one or more package sources.</span></span> <span data-ttu-id="a8b7b-231">複数のパッケージソース名は、コンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-231">Multiple package source names must be separated by commas.</span></span>
<span data-ttu-id="a8b7b-232">パッケージソース名を取得するには、 `Get-PackageSource` コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-232">You can get package source names by running the `Get-PackageSource` cmdlet.</span></span>

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

### <span data-ttu-id="a8b7b-233">-Tag</span><span class="sxs-lookup"><span data-stu-id="a8b7b-233">-Tag</span></span>

<span data-ttu-id="a8b7b-234">パッケージメタデータ内で検索する1つ以上の文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-234">Specifies one or more strings to search for in the package metadata.</span></span>

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

### <span data-ttu-id="a8b7b-235">-Type</span><span class="sxs-lookup"><span data-stu-id="a8b7b-235">-Type</span></span>

<span data-ttu-id="a8b7b-236">モジュール、スクリプト、またはその両方を含むパッケージを検索するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-236">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="a8b7b-237">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-237">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="a8b7b-238">[Module]</span><span class="sxs-lookup"><span data-stu-id="a8b7b-238">Module</span></span>
- <span data-ttu-id="a8b7b-239">スクリプト</span><span class="sxs-lookup"><span data-stu-id="a8b7b-239">Script</span></span>
- <span data-ttu-id="a8b7b-240">All</span><span class="sxs-lookup"><span data-stu-id="a8b7b-240">All</span></span>

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

### <span data-ttu-id="a8b7b-241">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a8b7b-241">-Confirm</span></span>

<span data-ttu-id="a8b7b-242">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-242">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a8b7b-243">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a8b7b-243">-WhatIf</span></span>

<span data-ttu-id="a8b7b-244">コマンドレットが実行された場合に何が起こるか `Install-Package` を示します。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-244">Shows what would happen if `Install-Package` cmdlet is run.</span></span> <span data-ttu-id="a8b7b-245">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-245">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a8b7b-246">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a8b7b-246">CommonParameters</span></span>

<span data-ttu-id="a8b7b-247">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-247">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a8b7b-248">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-248">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a8b7b-249">入力</span><span class="sxs-lookup"><span data-stu-id="a8b7b-249">INPUTS</span></span>

### <span data-ttu-id="a8b7b-250">`Install-Package` パイプラインからの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-250">`Install-Package` accepts input from the pipeline.</span></span>

## <span data-ttu-id="a8b7b-251">出力</span><span class="sxs-lookup"><span data-stu-id="a8b7b-251">OUTPUTS</span></span>

### <span data-ttu-id="a8b7b-252">ソフトウェア Id []</span><span class="sxs-lookup"><span data-stu-id="a8b7b-252">SoftwareIdentity[]</span></span>

## <span data-ttu-id="a8b7b-253">注</span><span class="sxs-lookup"><span data-stu-id="a8b7b-253">NOTES</span></span>

<span data-ttu-id="a8b7b-254">コマンドにパッケージプロバイダーを含めると、コマンドレットで動的パラメーターを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-254">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="a8b7b-255">動的パラメーターは、パッケージプロバイダーに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-255">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="a8b7b-256">コマンドレットにより、 `Get-Help` コマンドレットのパラメーターセットが一覧表示され、プロバイダーのパラメーターセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-256">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="a8b7b-257">たとえば、には、、、 `Install-Package` およびを含む **PowerShellGet** パラメーターが設定されてい `-NoPathUpdate` `AllowClobber` `SkipPublisherCheck` ます。</span><span class="sxs-lookup"><span data-stu-id="a8b7b-257">For example, `Install-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="a8b7b-258">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a8b7b-258">RELATED LINKS</span></span>

[<span data-ttu-id="a8b7b-259">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="a8b7b-259">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="a8b7b-260">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="a8b7b-260">Find-DscResource</span></span>](../PowershellGet/Find-DscResource.md)

[<span data-ttu-id="a8b7b-261">Get-Help</span><span class="sxs-lookup"><span data-stu-id="a8b7b-261">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="a8b7b-262">Get-Package</span><span class="sxs-lookup"><span data-stu-id="a8b7b-262">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="a8b7b-263">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="a8b7b-263">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="a8b7b-264">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="a8b7b-264">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="a8b7b-265">Find-Package</span><span class="sxs-lookup"><span data-stu-id="a8b7b-265">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="a8b7b-266">Save-Package</span><span class="sxs-lookup"><span data-stu-id="a8b7b-266">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="a8b7b-267">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="a8b7b-267">Uninstall-Package</span></span>](Uninstall-Package.md)
