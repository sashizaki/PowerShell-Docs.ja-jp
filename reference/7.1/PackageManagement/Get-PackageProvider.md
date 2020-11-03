---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packageprovider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageProvider
ms.openlocfilehash: b3414b9f34787cc5285475d9de784fd779bd1431
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212867"
---
# <span data-ttu-id="091d5-103">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="091d5-103">Get-PackageProvider</span></span>

## <span data-ttu-id="091d5-104">概要</span><span class="sxs-lookup"><span data-stu-id="091d5-104">SYNOPSIS</span></span>
<span data-ttu-id="091d5-105">Package Management に接続されているパッケージプロバイダーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="091d5-105">Returns a list of package providers that are connected to Package Management.</span></span>

## <span data-ttu-id="091d5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="091d5-106">SYNTAX</span></span>

```
Get-PackageProvider [[-Name] <String[]>] [-ListAvailable] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="091d5-107">Description</span><span class="sxs-lookup"><span data-stu-id="091d5-107">DESCRIPTION</span></span>

<span data-ttu-id="091d5-108">**Get PackageProvider** コマンドレットは、Package Management に接続されているパッケージプロバイダーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="091d5-108">The **Get-PackageProvider** cmdlet returns a list of package providers that are connected to Package Management.</span></span>
<span data-ttu-id="091d5-109">これらのプロバイダーの例には、PSModule、NuGet、Chocolatey などがあります。</span><span class="sxs-lookup"><span data-stu-id="091d5-109">Examples of these providers include PSModule, NuGet, and Chocolatey.</span></span>
<span data-ttu-id="091d5-110">1つまたは複数のプロバイダー名の全体または一部に基づいて結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="091d5-110">You can filter the results based on all or part of one or more provider names.</span></span>

## <span data-ttu-id="091d5-111">例</span><span class="sxs-lookup"><span data-stu-id="091d5-111">EXAMPLES</span></span>

### <span data-ttu-id="091d5-112">例 1: 現在読み込まれているすべてのパッケージプロバイダーを取得する</span><span class="sxs-lookup"><span data-stu-id="091d5-112">Example 1: Get all currently loaded package providers</span></span>

```
PS C:\> Get-PackageProvider
```

<span data-ttu-id="091d5-113">このコマンドは、ローカルコンピューターに現在読み込まれているすべてのパッケージプロバイダーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="091d5-113">This command gets a list of all the package providers that are currently loaded on the local computer.</span></span>

### <span data-ttu-id="091d5-114">例 2: 使用可能なすべてのパッケージプロバイダーを取得する</span><span class="sxs-lookup"><span data-stu-id="091d5-114">Example 2: Get all available package providers</span></span>

```
PS C:\> Get-PackageProvider -ListAvailable
```

<span data-ttu-id="091d5-115">このコマンドは、ローカルコンピューターで使用可能なすべてのパッケージプロバイダーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="091d5-115">This command gets a list of all package providers that are available on the local computer.</span></span>

### <span data-ttu-id="091d5-116">例 3: パッケージプロバイダーを動的に取得する</span><span class="sxs-lookup"><span data-stu-id="091d5-116">Example 3: Dynamically get a package provider</span></span>

```
PS C:\> Get-PackageProvider -Name "Chocolatey" -ForceBootstrap
```

<span data-ttu-id="091d5-117">このコマンドを実行すると、コンピューターに Chocolatey プロバイダーがインストールされていない場合に、Chocolatey プロバイダーが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="091d5-117">This command automatically installs the Chocolatey provider if your computer does not have the Chocolatey provider installed.</span></span>

## <span data-ttu-id="091d5-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="091d5-118">PARAMETERS</span></span>

### <span data-ttu-id="091d5-119">-Force</span><span class="sxs-lookup"><span data-stu-id="091d5-119">-Force</span></span>

<span data-ttu-id="091d5-120">このコマンドレットが強制的に実行できるこのコマンドレットの他のすべての操作を強制することを示します。</span><span class="sxs-lookup"><span data-stu-id="091d5-120">Indicates that this cmdlet forces all other actions with this cmdlet that can be forced.</span></span>
<span data-ttu-id="091d5-121">**Get-PackageProvider** では、 *Force* パラメーターが *forcebootstrap* パラメーターと同じように動作することを意味します。</span><span class="sxs-lookup"><span data-stu-id="091d5-121">In **Get-PackageProvider** , this means the *Force* parameter acts the same as the *ForceBootstrap* parameter.</span></span>

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

### <span data-ttu-id="091d5-122">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="091d5-122">-ForceBootstrap</span></span>

<span data-ttu-id="091d5-123">このコマンドレットによって、パッケージプロバイダーを自動的にインストールするように Package Management を強制することを示します。</span><span class="sxs-lookup"><span data-stu-id="091d5-123">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="091d5-124">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="091d5-124">-ListAvailable</span></span>

<span data-ttu-id="091d5-125">インストールされているすべてのプロバイダーを取得します。</span><span class="sxs-lookup"><span data-stu-id="091d5-125">Gets all installed providers.</span></span>
<span data-ttu-id="091d5-126">**PSModulePath** 環境変数およびパッケージプロバイダーアセンブリフォルダーに一覧表示されているパス **で、プロバイダーを取得** します。</span><span class="sxs-lookup"><span data-stu-id="091d5-126">**Get-PackageProvider** gets provider in paths listed in the **PSModulePath** environment variable as well as the package provider assembly folders:</span></span>

<span data-ttu-id="091d5-127">**$env:P rogramFiles\PackageManagement\ProviderAssemblies \* \* \* \* $env: Localappdata\packagemanagement\providerassemblies から**</span><span class="sxs-lookup"><span data-stu-id="091d5-127">**$env:ProgramFiles\PackageManagement\ProviderAssemblies\*\*\*\*$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies**</span></span>

<span data-ttu-id="091d5-128">このパラメーターを指定しない場合、 **Get PackageProvider** は、現在のセッションに読み込まれているプロバイダーのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="091d5-128">Without this parameter, **Get-PackageProvider** gets only the providers loaded in the current session.</span></span>

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

### <span data-ttu-id="091d5-129">-Name</span><span class="sxs-lookup"><span data-stu-id="091d5-129">-Name</span></span>

<span data-ttu-id="091d5-130">1つまたは複数のプロバイダー名、またはプロバイダー名の一部を指定します。</span><span class="sxs-lookup"><span data-stu-id="091d5-130">Specifies one or more provider names, or partial provider names.</span></span>
<span data-ttu-id="091d5-131">複数のプロバイダー名はコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="091d5-131">Separate multiple provider names with commas.</span></span>
<span data-ttu-id="091d5-132">このパラメーターの有効な値には、パッケージと共にインストールしたプロバイダーの名前が含まれます。PackageManagement には、 **Psmodule** および **MSI** プロバイダーを含む、既定のプロバイダーのセットが付属しています。</span><span class="sxs-lookup"><span data-stu-id="091d5-132">Valid values for this parameter include names of providers that you have installed with packages; PackageManagement ships with a set of default providers, including the **PSModule** and **MSI** providers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="091d5-133">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="091d5-133">CommonParameters</span></span>

<span data-ttu-id="091d5-134">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="091d5-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="091d5-135">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="091d5-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="091d5-136">入力</span><span class="sxs-lookup"><span data-stu-id="091d5-136">INPUTS</span></span>

## <span data-ttu-id="091d5-137">出力</span><span class="sxs-lookup"><span data-stu-id="091d5-137">OUTPUTS</span></span>

### <span data-ttu-id="091d5-138">PackageProvider []</span><span class="sxs-lookup"><span data-stu-id="091d5-138">PackageProvider[]</span></span>

## <span data-ttu-id="091d5-139">注</span><span class="sxs-lookup"><span data-stu-id="091d5-139">NOTES</span></span>

## <span data-ttu-id="091d5-140">関連リンク</span><span class="sxs-lookup"><span data-stu-id="091d5-140">RELATED LINKS</span></span>

[<span data-ttu-id="091d5-141">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="091d5-141">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="091d5-142">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="091d5-142">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="091d5-143">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="091d5-143">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="091d5-144">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="091d5-144">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

