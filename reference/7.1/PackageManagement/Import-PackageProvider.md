---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/import-packageprovider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PackageProvider
ms.openlocfilehash: 8b900f8e7ff2583e20d359fd3d15aee653b9c1d6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212872"
---
# <span data-ttu-id="ee343-103">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="ee343-103">Import-PackageProvider</span></span>

## <span data-ttu-id="ee343-104">概要</span><span class="sxs-lookup"><span data-stu-id="ee343-104">SYNOPSIS</span></span>
<span data-ttu-id="ee343-105">Package Management パッケージプロバイダーを現在のセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="ee343-105">Adds Package Management package providers to the current session.</span></span>

## <span data-ttu-id="ee343-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ee343-106">SYNTAX</span></span>

```
Import-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="ee343-107">Description</span><span class="sxs-lookup"><span data-stu-id="ee343-107">DESCRIPTION</span></span>

<span data-ttu-id="ee343-108">`Import-PackageProvider`コマンドレットでは、現在のセッションに1つ以上のパッケージプロバイダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ee343-108">The `Import-PackageProvider` cmdlet adds one or more package providers to the current session.</span></span>
<span data-ttu-id="ee343-109">インポートするプロバイダーは、ローカルコンピューターにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee343-109">The provider that you import must be installed on the local computer.</span></span>

<span data-ttu-id="ee343-110">使用可能なプロバイダーの一覧を取得するには、を実行 `Get-PackageProvider -ListAvailable` します。</span><span class="sxs-lookup"><span data-stu-id="ee343-110">To get a list of available providers, run `Get-PackageProvider -ListAvailable`.</span></span>
<span data-ttu-id="ee343-111">パッケージプロバイダー名は、モジュール名とは異なる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ee343-111">Note that a package provider name can be different from its module name.</span></span>

<span data-ttu-id="ee343-112">セキュリティ上の理由により、 **PackageManagement** では、C# ベースのプロバイダーにが含まれている必要があり `provider.manifest` ます。</span><span class="sxs-lookup"><span data-stu-id="ee343-112">Due to security reasons, **PackageManagement** requires C#-based providers to contain a `provider.manifest`.</span></span> <span data-ttu-id="ee343-113">が挿入されたプロバイダーをビルドする方法の詳細については `provider.manifest` 、のプロジェクトファイルを参照してください `.csproj` [https://github.com/oneget/oneget](https://github.com/oneget/oneget) 。</span><span class="sxs-lookup"><span data-stu-id="ee343-113">For more information on how to build a provider with `provider.manifest` injected, see the `.csproj` project files on [https://github.com/oneget/oneget](https://github.com/oneget/oneget).</span></span>

## <span data-ttu-id="ee343-114">例</span><span class="sxs-lookup"><span data-stu-id="ee343-114">EXAMPLES</span></span>

### <span data-ttu-id="ee343-115">例 1: ローカルコンピューターからパッケージプロバイダーをインポートする</span><span class="sxs-lookup"><span data-stu-id="ee343-115">Example 1: Import a package provider from the local computer</span></span>

```powershell
PS C:\> Import-PackageProvider -Name "Nuget"
```

<span data-ttu-id="ee343-116">このコマンドは、ローカルコンピューターにインストールされた Nuget プロバイダーをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ee343-116">This command imports the Nuget provider after it has been installed on the local computer.</span></span>

### <span data-ttu-id="ee343-117">例 2: パッケージプロバイダーの特定のバージョンをインポートする</span><span class="sxs-lookup"><span data-stu-id="ee343-117">Example 2: Import a specific version of a package provider</span></span>

```powershell
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Force
Get-PackageProvider -ListAvailable
Import-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Verbose
```

<span data-ttu-id="ee343-118">このコマンドは、特定のバージョンの Nuget パッケージプロバイダーを検索し、インストールして、インポートします。</span><span class="sxs-lookup"><span data-stu-id="ee343-118">This command finds, installs, and imports a specific version of the Nuget package provider.</span></span>

## <span data-ttu-id="ee343-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ee343-119">PARAMETERS</span></span>

### <span data-ttu-id="ee343-120">-Force</span><span class="sxs-lookup"><span data-stu-id="ee343-120">-Force</span></span>

<span data-ttu-id="ee343-121">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ee343-121">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="ee343-122">パッケージプロバイダーを再インポートします。</span><span class="sxs-lookup"><span data-stu-id="ee343-122">Re-imports a package provider.</span></span>

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

### <span data-ttu-id="ee343-123">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="ee343-123">-ForceBootstrap</span></span>

<span data-ttu-id="ee343-124">このコマンドレットによって、パッケージプロバイダーを自動的にインストールするように Package Management を強制することを示します。</span><span class="sxs-lookup"><span data-stu-id="ee343-124">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="ee343-125">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="ee343-125">-MaximumVersion</span></span>

<span data-ttu-id="ee343-126">インポートするパッケージプロバイダーの許可される最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee343-126">Specifies the maximum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="ee343-127">このパラメーターを追加しない場合、では、 `Import-PackageProvider` プロバイダーの利用可能な最も高いバージョンがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ee343-127">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider.</span></span>

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

### <span data-ttu-id="ee343-128">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="ee343-128">-MinimumVersion</span></span>

<span data-ttu-id="ee343-129">インポートするパッケージプロバイダーの許可される最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee343-129">Specifies the minimum allowed version of the package provider that you want to import.</span></span> <span data-ttu-id="ee343-130">このパラメーターを追加しない場合、は、 `Import-PackageProvider` *MaximumVersion* パラメーターを使用して指定された最大バージョンも満たす、パッケージの利用可能な最も高いバージョンをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ee343-130">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the package that also satisfies any maximum version that is specified using the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="ee343-131">-Name</span><span class="sxs-lookup"><span data-stu-id="ee343-131">-Name</span></span>

<span data-ttu-id="ee343-132">1つまたは複数のパッケージプロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ee343-132">Specifies one or more package provider names.</span></span> <span data-ttu-id="ee343-133">ワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="ee343-133">Wildcards are not permitted.</span></span>

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

### <span data-ttu-id="ee343-134">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="ee343-134">-RequiredVersion</span></span>

<span data-ttu-id="ee343-135">インポートするパッケージプロバイダーの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="ee343-135">Specifies the exact version of the package provider that you want to import.</span></span> <span data-ttu-id="ee343-136">このパラメーターを追加しない場合、は、 `Import-PackageProvider` **MaximumVersion** パラメーターを使用して指定された最大バージョンを満たすプロバイダーの、利用可能な最も高いバージョンをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ee343-136">If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider that also satisfies any maximum version specified using the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="ee343-137">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ee343-137">CommonParameters</span></span>

<span data-ttu-id="ee343-138">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ee343-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ee343-139">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee343-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ee343-140">入力</span><span class="sxs-lookup"><span data-stu-id="ee343-140">INPUTS</span></span>

### <span data-ttu-id="ee343-141">Microsoft... 実装. PackageProvider</span><span class="sxs-lookup"><span data-stu-id="ee343-141">Microsoft.PackageManagement.Implementation.PackageProvider</span></span>

<span data-ttu-id="ee343-142">によって返された **Packageprovider** オブジェクトをにパイプ処理でき `Get-PackageProvider` `Import-PackageProvider` ます。</span><span class="sxs-lookup"><span data-stu-id="ee343-142">You can pipe a **PackageProvider** object returned by `Get-PackageProvider` into `Import-PackageProvider`.</span></span>

## <span data-ttu-id="ee343-143">出力</span><span class="sxs-lookup"><span data-stu-id="ee343-143">OUTPUTS</span></span>

## <span data-ttu-id="ee343-144">注</span><span class="sxs-lookup"><span data-stu-id="ee343-144">NOTES</span></span>

## <span data-ttu-id="ee343-145">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ee343-145">RELATED LINKS</span></span>

[<span data-ttu-id="ee343-146">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="ee343-146">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="ee343-147">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="ee343-147">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

[<span data-ttu-id="ee343-148">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="ee343-148">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="ee343-149">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="ee343-149">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="ee343-150">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="ee343-150">Get-PackageProvider</span></span>](Get-PackageProvider.md)

