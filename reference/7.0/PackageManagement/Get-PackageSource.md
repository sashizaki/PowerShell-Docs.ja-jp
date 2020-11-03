---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 03/29/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packagesource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageSource
ms.openlocfilehash: 6fb64b7e95f1f8ddfff6f1be9e880045271706fc
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210451"
---
# <span data-ttu-id="8b2ec-103">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="8b2ec-103">Get-PackageSource</span></span>

## <span data-ttu-id="8b2ec-104">概要</span><span class="sxs-lookup"><span data-stu-id="8b2ec-104">SYNOPSIS</span></span>
<span data-ttu-id="8b2ec-105">パッケージプロバイダーに登録されているパッケージソースの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-105">Gets a list of package sources that are registered for a package provider.</span></span>

## <span data-ttu-id="8b2ec-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8b2ec-106">SYNTAX</span></span>

### <span data-ttu-id="8b2ec-107">NuGet</span><span class="sxs-lookup"><span data-stu-id="8b2ec-107">NuGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="8b2ec-108">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="8b2ec-108">PowerShellGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="8b2ec-109">Description</span><span class="sxs-lookup"><span data-stu-id="8b2ec-109">DESCRIPTION</span></span>

<span data-ttu-id="8b2ec-110">`Get-PackageSource`コマンドレットは、ローカルコンピューター上の **PackageManagement** に登録されているパッケージソースの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-110">The `Get-PackageSource` cmdlet gets a list of package sources that are registered with **PackageManagement** on the local computer.</span></span> <span data-ttu-id="8b2ec-111">パッケージプロバイダーを指定した場合は、 `Get-PackageSource` 指定されたプロバイダーに関連付けられているソースのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-111">If you specify a package provider, `Get-PackageSource` gets only those sources that are associated with the specified provider.</span></span> <span data-ttu-id="8b2ec-112">それ以外の場合、コマンドは **PackageManagement** に登録されているすべてのパッケージソースを返します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-112">Otherwise, the command returns all package sources that are registered with **PackageManagement** .</span></span>

## <span data-ttu-id="8b2ec-113">例</span><span class="sxs-lookup"><span data-stu-id="8b2ec-113">EXAMPLES</span></span>

### <span data-ttu-id="8b2ec-114">例 1: すべてのパッケージソースを取得する</span><span class="sxs-lookup"><span data-stu-id="8b2ec-114">Example 1: Get all package sources</span></span>

<span data-ttu-id="8b2ec-115">`Get-PackageSource`コマンドレットは、ローカルコンピューター上の **PackageManagement** に登録されているすべてのパッケージソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-115">The `Get-PackageSource` cmdlet gets all package sources that are registered with **PackageManagement** on the local computer.</span></span>

```powershell
Get-PackageSource
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
PSGallery            PowerShellGet    False      https://www.powershellgallery.com/api/v2
```

### <span data-ttu-id="8b2ec-116">例 2: 特定のプロバイダーのすべてのパッケージソースを取得する</span><span class="sxs-lookup"><span data-stu-id="8b2ec-116">Example 2: Get all package sources for a specific provider</span></span>

<span data-ttu-id="8b2ec-117">このコマンドは、特定のプロバイダーに登録されているパッケージソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-117">This command gets package sources that are registered for a specific provider.</span></span>

```powershell
Get-PackageSource -ProviderName NuGet
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="8b2ec-118">`Get-PackageSource` では、 **ProviderName** パラメーターを使用して、 **NuGet** プロバイダーに登録されているパッケージソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-118">`Get-PackageSource` uses the **ProviderName** parameter to get package sources that are registered for the **NuGet** provider.</span></span>

### <span data-ttu-id="8b2ec-119">例 3: パッケージプロバイダーからソースを取得する</span><span class="sxs-lookup"><span data-stu-id="8b2ec-119">Example 3: Get sources from a package provider</span></span>

<span data-ttu-id="8b2ec-120">このコマンドは、パッケージプロバイダーを使用してパッケージソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-120">This command uses a package provider to get package sources.</span></span>

```powershell
Get-PackageProvider -Name NuGet | Get-PackageSource
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="8b2ec-121">`Get-PackageProvider`**name** パラメーターを使用して、プロバイダー名 **NuGet** を指定します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-121">`Get-PackageProvider` uses the **Name** parameter specify the provider name, **NuGet** .</span></span> <span data-ttu-id="8b2ec-122">オブジェクトは、パイプライン内でに送信され `Get-PackageSource` ます。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-122">The object is sent down the pipeline to `Get-PackageSource`.</span></span>

## <span data-ttu-id="8b2ec-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8b2ec-123">PARAMETERS</span></span>

### <span data-ttu-id="8b2ec-124">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="8b2ec-124">-ConfigFile</span></span>

<span data-ttu-id="8b2ec-125">構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-125">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="8b2ec-126">-Force</span><span class="sxs-lookup"><span data-stu-id="8b2ec-126">-Force</span></span>

<span data-ttu-id="8b2ec-127">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-127">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="8b2ec-128">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="8b2ec-128">-ForceBootstrap</span></span>

<span data-ttu-id="8b2ec-129">このコマンドレットにより、 **PackageManagement** によってパッケージプロバイダーが自動的にインストールされることを示します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-129">Indicates that this cmdlet forces **PackageManagement** to automatically install a package provider.</span></span>

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

### <span data-ttu-id="8b2ec-130">-Location</span><span class="sxs-lookup"><span data-stu-id="8b2ec-130">-Location</span></span>

<span data-ttu-id="8b2ec-131">パッケージ管理ソースまたはリポジトリの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-131">Specifies the location of a package management source or repository.</span></span>

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

### <span data-ttu-id="8b2ec-132">-Name</span><span class="sxs-lookup"><span data-stu-id="8b2ec-132">-Name</span></span>

<span data-ttu-id="8b2ec-133">パッケージ管理ソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-133">Specifies the name of a package management source.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8b2ec-134">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="8b2ec-134">-PackageManagementProvider</span></span>

<span data-ttu-id="8b2ec-135">パッケージ管理プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-135">Specifies a package management provider.</span></span>

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

### <span data-ttu-id="8b2ec-136">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="8b2ec-136">-ProviderName</span></span>

<span data-ttu-id="8b2ec-137">1つまたは複数のパッケージプロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-137">Specifies one or more package provider names.</span></span> <span data-ttu-id="8b2ec-138">複数のパッケージプロバイダー名をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-138">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="8b2ec-139">使用 `Get-PackageProvider` 可能なパッケージプロバイダーの一覧を取得するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-139">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

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

### <span data-ttu-id="8b2ec-140">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="8b2ec-140">-PublishLocation</span></span>

<span data-ttu-id="8b2ec-141">パッケージソースの発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-141">Specifies the publish location for the package source.</span></span>

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

### <span data-ttu-id="8b2ec-142">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="8b2ec-142">-ScriptPublishLocation</span></span>

<span data-ttu-id="8b2ec-143">スクリプトの発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-143">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="8b2ec-144">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="8b2ec-144">-ScriptSourceLocation</span></span>

<span data-ttu-id="8b2ec-145">スクリプトのソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-145">Specifies the script source location.</span></span>

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

### <span data-ttu-id="8b2ec-146">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="8b2ec-146">-SkipValidate</span></span>

<span data-ttu-id="8b2ec-147">パッケージソースの資格情報の検証をスキップするスイッチ。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-147">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="8b2ec-148">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8b2ec-148">CommonParameters</span></span>

<span data-ttu-id="8b2ec-149">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8b2ec-150">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8b2ec-151">入力</span><span class="sxs-lookup"><span data-stu-id="8b2ec-151">INPUTS</span></span>

## <span data-ttu-id="8b2ec-152">出力</span><span class="sxs-lookup"><span data-stu-id="8b2ec-152">OUTPUTS</span></span>

### <span data-ttu-id="8b2ec-153">Register-packagesource []</span><span class="sxs-lookup"><span data-stu-id="8b2ec-153">PackageSource[]</span></span>

<span data-ttu-id="8b2ec-154">1つまたは複数のパッケージソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="8b2ec-154">Specifies one or more package sources.</span></span>

## <span data-ttu-id="8b2ec-155">注</span><span class="sxs-lookup"><span data-stu-id="8b2ec-155">NOTES</span></span>

## <span data-ttu-id="8b2ec-156">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8b2ec-156">RELATED LINKS</span></span>

[<span data-ttu-id="8b2ec-157">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="8b2ec-157">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="8b2ec-158">Find-Package</span><span class="sxs-lookup"><span data-stu-id="8b2ec-158">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="8b2ec-159">Get-Package</span><span class="sxs-lookup"><span data-stu-id="8b2ec-159">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="8b2ec-160">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="8b2ec-160">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="8b2ec-161">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="8b2ec-161">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="8b2ec-162">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="8b2ec-162">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="8b2ec-163">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="8b2ec-163">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
