---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/import-packageprovider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PackageProvider
ms.openlocfilehash: 570ed2a314c498fe59546d30cba17913bc91b70c
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890476"
---
# <span data-ttu-id="5ee26-103">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="5ee26-103">Import-PackageProvider</span></span>

## <span data-ttu-id="5ee26-104">概要</span><span class="sxs-lookup"><span data-stu-id="5ee26-104">SYNOPSIS</span></span>
<span data-ttu-id="5ee26-105">Package Management パッケージプロバイダーを現在のセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="5ee26-105">Adds Package Management package providers to the current session.</span></span>

## <span data-ttu-id="5ee26-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5ee26-106">SYNTAX</span></span>

```
Import-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="5ee26-107">Description</span><span class="sxs-lookup"><span data-stu-id="5ee26-107">DESCRIPTION</span></span>

<span data-ttu-id="5ee26-108">`Import-PackageProvider`コマンドレットでは、現在のセッションに1つ以上のパッケージプロバイダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5ee26-108">The `Import-PackageProvider` cmdlet adds one or more package providers to the current session.</span></span>
<span data-ttu-id="5ee26-109">インポートするプロバイダーは、ローカルコンピューターにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ee26-109">The provider that you import must be installed on the local computer.</span></span>

<span data-ttu-id="5ee26-110">使用可能なプロバイダーの一覧を取得するには、を実行 `Get-PackageProvider -ListAvailable` します。</span><span class="sxs-lookup"><span data-stu-id="5ee26-110">To get a list of available providers, run `Get-PackageProvider -ListAvailable`.</span></span>
<span data-ttu-id="5ee26-111">パッケージプロバイダー名は、モジュール名とは異なる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5ee26-111">Note that a package provider name can be different from its module name.</span></span>

<span data-ttu-id="5ee26-112">セキュリティ上の理由により、 **PackageManagement** では、C# ベースのプロバイダーにが含まれている必要があり `provider.manifest` ます。</span><span class="sxs-lookup"><span data-stu-id="5ee26-112">Due to security reasons, **PackageManagement** requires C#-based providers to contain a `provider.manifest`.</span></span> <span data-ttu-id="5ee26-113">が挿入されたプロバイダーをビルドする方法の詳細については `provider.manifest` 、のプロジェクトファイルを参照してください `.csproj` [https://github.com/oneget/oneget](https://github.com/oneget/oneget) 。</span><span class="sxs-lookup"><span data-stu-id="5ee26-113">For more information on how to build a provider with `provider.manifest` injected, see the `.csproj` project files on [https://github.com/oneget/oneget](https://github.com/oneget/oneget).</span></span>

## <span data-ttu-id="5ee26-114">例</span><span class="sxs-lookup"><span data-stu-id="5ee26-114">EXAMPLES</span></span>

### <span data-ttu-id="5ee26-115">例 1: ローカルコンピューターからパッケージプロバイダーをインポートする</span><span class="sxs-lookup"><span data-stu-id="5ee26-115">Example 1: Import a package provider from the local computer</span></span>

```powershell
PS C:\> Import-PackageProvider -Name "Nuget"
```

<span data-ttu-id="5ee26-116">このコマンドは、ローカルコンピューターにインストールされた Nuget プロバイダーをインポートします。</span><span class="sxs-lookup"><span data-stu-id="5ee26-116">This command imports the Nuget provider after it has been installed on the local computer.</span></span>

### <span data-ttu-id="5ee26-117">例 2: パッケージプロバイダーの特定のバージョンをインポートする</span><span class="sxs-lookup"><span data-stu-id="5ee26-117">Example 2: Import a specific version of a package provider</span></span>

```powershell
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Force
Get-PackageProvider -ListAvailable
Import-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Verbose
```

<span data-ttu-id="5ee26-118">このコマンドは、特定のバージョンの Nuget パッケージプロバイダーを検索し、インストールして、インポートします。</span><span class="sxs-lookup"><span data-stu-id="5ee26-118">This command finds, installs, and imports a specific version of the Nuget package provider.</span></span>

## <span data-ttu-id="5ee26-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5ee26-119">PARAMETERS</span></span>

### <span data-ttu-id="5ee26-120">-Force</span><span class="sxs-lookup"><span data-stu-id="5ee26-120">-Force</span></span>

<span data-ttu-id="5ee26-121">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5ee26-121">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="5ee26-122">パッケージプロバイダーを再インポートします。</span><span class="sxs-lookup"><span data-stu-id="5ee26-122">Re-imports a package provider.</span></span>

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

### <span data-ttu-id="5ee26-123">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="5ee26-123">-ForceBootstrap</span></span>

<span data-ttu-id="5ee26-124">このコマンドレットによって、パッケージプロバイダーを自動的にインストールするように Package Management を強制することを示します。</span><span class="sxs-lookup"><span data-stu-id="5ee26-124">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="5ee26-125">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="5ee26-125">-MaximumVersion</span></span>

<span data-ttu-id="5ee26-126">インポートするパッケージプロバイダーの許可される最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="5ee26-126">Specifies the maximum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="5ee26-127">このパラメーターを追加しない場合、では、 `Import-PackageProvider` プロバイダーの利用可能な最も高いバージョンがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="5ee26-127">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider.</span></span>

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

### <span data-ttu-id="5ee26-128">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="5ee26-128">-MinimumVersion</span></span>

<span data-ttu-id="5ee26-129">インポートするパッケージプロバイダーの許可される最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="5ee26-129">Specifies the minimum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="5ee26-130">このパラメーターを追加しない場合、は、 `Import-PackageProvider` *MaximumVersion* パラメーターを使用して指定された最大バージョンも満たす、パッケージの利用可能な最も高いバージョンをインポートします。</span><span class="sxs-lookup"><span data-stu-id="5ee26-130">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the package that also satisfies any maximum version that is specified using the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="5ee26-131">-Name</span><span class="sxs-lookup"><span data-stu-id="5ee26-131">-Name</span></span>

<span data-ttu-id="5ee26-132">1つまたは複数のパッケージプロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="5ee26-132">Specifies one or more package provider names.</span></span> <span data-ttu-id="5ee26-133">ワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5ee26-133">Wildcards are not permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5ee26-134">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="5ee26-134">-RequiredVersion</span></span>

<span data-ttu-id="5ee26-135">インポートするパッケージプロバイダーの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="5ee26-135">Specifies the exact version of the package provider that you want to import.</span></span> <span data-ttu-id="5ee26-136">このパラメーターを追加しない場合、は、 `Import-PackageProvider` **MaximumVersion** パラメーターを使用して指定された最大バージョンを満たすプロバイダーの、利用可能な最も高いバージョンをインポートします。</span><span class="sxs-lookup"><span data-stu-id="5ee26-136">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider that also satisfies any maximum version specified using the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="5ee26-137">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5ee26-137">CommonParameters</span></span>

<span data-ttu-id="5ee26-138">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5ee26-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5ee26-139">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ee26-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5ee26-140">入力</span><span class="sxs-lookup"><span data-stu-id="5ee26-140">INPUTS</span></span>

### <span data-ttu-id="5ee26-141">Microsoft... 実装. PackageProvider</span><span class="sxs-lookup"><span data-stu-id="5ee26-141">Microsoft.PackageManagement.Implementation.PackageProvider</span></span>

<span data-ttu-id="5ee26-142">によって返された **Packageprovider** オブジェクトをにパイプ処理でき `Get-PackageProvider` `Import-PackageProvider` ます。</span><span class="sxs-lookup"><span data-stu-id="5ee26-142">You can pipe a **PackageProvider** object returned by `Get-PackageProvider` into `Import-PackageProvider`.</span></span>

## <span data-ttu-id="5ee26-143">出力</span><span class="sxs-lookup"><span data-stu-id="5ee26-143">OUTPUTS</span></span>

## <span data-ttu-id="5ee26-144">注</span><span class="sxs-lookup"><span data-stu-id="5ee26-144">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ee26-145">2020年4月の時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン1.0 と1.1 がサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5ee26-145">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="5ee26-146">TLS 1.2 以降を使用していない場合は、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="5ee26-146">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="5ee26-147">次のコマンドを使用して、TLS 1.2 を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ee26-147">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="5ee26-148">詳細については、PowerShell ブログの [お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ee26-148">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="5ee26-149">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5ee26-149">RELATED LINKS</span></span>

[<span data-ttu-id="5ee26-150">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="5ee26-150">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="5ee26-151">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5ee26-151">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

[<span data-ttu-id="5ee26-152">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5ee26-152">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="5ee26-153">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5ee26-153">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="5ee26-154">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="5ee26-154">Get-PackageProvider</span></span>](Get-PackageProvider.md)
