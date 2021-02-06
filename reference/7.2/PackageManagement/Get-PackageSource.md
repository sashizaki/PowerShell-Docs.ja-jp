---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 03/29/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packagesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageSource
ms.openlocfilehash: 8b91c5b950e0e16c4ce0821ee2f96b830dab1fc2
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99605175"
---
# <span data-ttu-id="160c6-102">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="160c6-102">Get-PackageSource</span></span>

## <span data-ttu-id="160c6-103">概要</span><span class="sxs-lookup"><span data-stu-id="160c6-103">SYNOPSIS</span></span>
<span data-ttu-id="160c6-104">パッケージプロバイダーに登録されているパッケージソースの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="160c6-104">Gets a list of package sources that are registered for a package provider.</span></span>

## <span data-ttu-id="160c6-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="160c6-105">SYNTAX</span></span>

### <span data-ttu-id="160c6-106">NuGet</span><span class="sxs-lookup"><span data-stu-id="160c6-106">NuGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="160c6-107">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="160c6-107">PowerShellGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="160c6-108">Description</span><span class="sxs-lookup"><span data-stu-id="160c6-108">DESCRIPTION</span></span>

<span data-ttu-id="160c6-109">`Get-PackageSource`コマンドレットは、ローカルコンピューター上の **PackageManagement** に登録されているパッケージソースの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="160c6-109">The `Get-PackageSource` cmdlet gets a list of package sources that are registered with **PackageManagement** on the local computer.</span></span> <span data-ttu-id="160c6-110">パッケージプロバイダーを指定した場合は、 `Get-PackageSource` 指定されたプロバイダーに関連付けられているソースのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="160c6-110">If you specify a package provider, `Get-PackageSource` gets only those sources that are associated with the specified provider.</span></span> <span data-ttu-id="160c6-111">それ以外の場合、コマンドは **PackageManagement** に登録されているすべてのパッケージソースを返します。</span><span class="sxs-lookup"><span data-stu-id="160c6-111">Otherwise, the command returns all package sources that are registered with **PackageManagement**.</span></span>

## <span data-ttu-id="160c6-112">例</span><span class="sxs-lookup"><span data-stu-id="160c6-112">EXAMPLES</span></span>

### <span data-ttu-id="160c6-113">例 1: すべてのパッケージソースを取得する</span><span class="sxs-lookup"><span data-stu-id="160c6-113">Example 1: Get all package sources</span></span>

<span data-ttu-id="160c6-114">`Get-PackageSource`コマンドレットは、ローカルコンピューター上の **PackageManagement** に登録されているすべてのパッケージソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="160c6-114">The `Get-PackageSource` cmdlet gets all package sources that are registered with **PackageManagement** on the local computer.</span></span>

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

### <span data-ttu-id="160c6-115">例 2: 特定のプロバイダーのすべてのパッケージソースを取得する</span><span class="sxs-lookup"><span data-stu-id="160c6-115">Example 2: Get all package sources for a specific provider</span></span>

<span data-ttu-id="160c6-116">このコマンドは、特定のプロバイダーに登録されているパッケージソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="160c6-116">This command gets package sources that are registered for a specific provider.</span></span>

```powershell
Get-PackageSource -ProviderName NuGet
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="160c6-117">`Get-PackageSource` では、 **ProviderName** パラメーターを使用して、 **NuGet** プロバイダーに登録されているパッケージソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="160c6-117">`Get-PackageSource` uses the **ProviderName** parameter to get package sources that are registered for the **NuGet** provider.</span></span>

### <span data-ttu-id="160c6-118">例 3: パッケージプロバイダーからソースを取得する</span><span class="sxs-lookup"><span data-stu-id="160c6-118">Example 3: Get sources from a package provider</span></span>

<span data-ttu-id="160c6-119">このコマンドは、パッケージプロバイダーを使用してパッケージソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="160c6-119">This command uses a package provider to get package sources.</span></span>

```powershell
Get-PackageProvider -Name NuGet | Get-PackageSource
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="160c6-120">`Get-PackageProvider`**name** パラメーターを使用して、プロバイダー名 **NuGet** を指定します。</span><span class="sxs-lookup"><span data-stu-id="160c6-120">`Get-PackageProvider` uses the **Name** parameter specify the provider name, **NuGet**.</span></span> <span data-ttu-id="160c6-121">オブジェクトは、パイプライン内でに送信され `Get-PackageSource` ます。</span><span class="sxs-lookup"><span data-stu-id="160c6-121">The object is sent down the pipeline to `Get-PackageSource`.</span></span>

## <span data-ttu-id="160c6-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="160c6-122">PARAMETERS</span></span>

### <span data-ttu-id="160c6-123">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="160c6-123">-ConfigFile</span></span>

<span data-ttu-id="160c6-124">構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="160c6-124">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="160c6-125">-Force</span><span class="sxs-lookup"><span data-stu-id="160c6-125">-Force</span></span>

<span data-ttu-id="160c6-126">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="160c6-126">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="160c6-127">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="160c6-127">-ForceBootstrap</span></span>

<span data-ttu-id="160c6-128">このコマンドレットにより、 **PackageManagement** によってパッケージプロバイダーが自動的にインストールされることを示します。</span><span class="sxs-lookup"><span data-stu-id="160c6-128">Indicates that this cmdlet forces **PackageManagement** to automatically install a package provider.</span></span>

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

### <span data-ttu-id="160c6-129">-Location</span><span class="sxs-lookup"><span data-stu-id="160c6-129">-Location</span></span>

<span data-ttu-id="160c6-130">パッケージ管理ソースまたはリポジトリの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="160c6-130">Specifies the location of a package management source or repository.</span></span>

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

### <span data-ttu-id="160c6-131">-Name</span><span class="sxs-lookup"><span data-stu-id="160c6-131">-Name</span></span>

<span data-ttu-id="160c6-132">パッケージ管理ソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="160c6-132">Specifies the name of a package management source.</span></span>

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

### <span data-ttu-id="160c6-133">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="160c6-133">-PackageManagementProvider</span></span>

<span data-ttu-id="160c6-134">パッケージ管理プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="160c6-134">Specifies a package management provider.</span></span>

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

### <span data-ttu-id="160c6-135">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="160c6-135">-ProviderName</span></span>

<span data-ttu-id="160c6-136">1つまたは複数のパッケージプロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="160c6-136">Specifies one or more package provider names.</span></span> <span data-ttu-id="160c6-137">複数のパッケージプロバイダー名をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="160c6-137">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="160c6-138">使用 `Get-PackageProvider` 可能なパッケージプロバイダーの一覧を取得するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="160c6-138">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

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

### <span data-ttu-id="160c6-139">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="160c6-139">-PublishLocation</span></span>

<span data-ttu-id="160c6-140">パッケージソースの発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="160c6-140">Specifies the publish location for the package source.</span></span>

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

### <span data-ttu-id="160c6-141">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="160c6-141">-ScriptPublishLocation</span></span>

<span data-ttu-id="160c6-142">スクリプトの発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="160c6-142">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="160c6-143">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="160c6-143">-ScriptSourceLocation</span></span>

<span data-ttu-id="160c6-144">スクリプトのソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="160c6-144">Specifies the script source location.</span></span>

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

### <span data-ttu-id="160c6-145">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="160c6-145">-SkipValidate</span></span>

<span data-ttu-id="160c6-146">パッケージソースの資格情報の検証をスキップするスイッチ。</span><span class="sxs-lookup"><span data-stu-id="160c6-146">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="160c6-147">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="160c6-147">CommonParameters</span></span>

<span data-ttu-id="160c6-148">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="160c6-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="160c6-149">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="160c6-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="160c6-150">入力</span><span class="sxs-lookup"><span data-stu-id="160c6-150">INPUTS</span></span>

## <span data-ttu-id="160c6-151">出力</span><span class="sxs-lookup"><span data-stu-id="160c6-151">OUTPUTS</span></span>

### <span data-ttu-id="160c6-152">Register-packagesource []</span><span class="sxs-lookup"><span data-stu-id="160c6-152">PackageSource[]</span></span>

<span data-ttu-id="160c6-153">1つまたは複数のパッケージソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="160c6-153">Specifies one or more package sources.</span></span>

## <span data-ttu-id="160c6-154">注</span><span class="sxs-lookup"><span data-stu-id="160c6-154">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="160c6-155">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="160c6-155">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="160c6-156">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="160c6-156">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="160c6-157">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="160c6-157">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="160c6-158">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="160c6-158">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="160c6-159">関連リンク</span><span class="sxs-lookup"><span data-stu-id="160c6-159">RELATED LINKS</span></span>

[<span data-ttu-id="160c6-160">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="160c6-160">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="160c6-161">Find-Package</span><span class="sxs-lookup"><span data-stu-id="160c6-161">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="160c6-162">Get-Package</span><span class="sxs-lookup"><span data-stu-id="160c6-162">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="160c6-163">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="160c6-163">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="160c6-164">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="160c6-164">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="160c6-165">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="160c6-165">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="160c6-166">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="160c6-166">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
