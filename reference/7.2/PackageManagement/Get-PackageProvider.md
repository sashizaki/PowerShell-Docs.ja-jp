---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packageprovider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageProvider
ms.openlocfilehash: fd8325f1a68755ee1b5c05719a04e71b22a7e9fd
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99601207"
---
# <span data-ttu-id="3bcae-102">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="3bcae-102">Get-PackageProvider</span></span>

## <span data-ttu-id="3bcae-103">概要</span><span class="sxs-lookup"><span data-stu-id="3bcae-103">SYNOPSIS</span></span>
<span data-ttu-id="3bcae-104">Package Management に接続されているパッケージプロバイダーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="3bcae-104">Returns a list of package providers that are connected to Package Management.</span></span>

## <span data-ttu-id="3bcae-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3bcae-105">SYNTAX</span></span>

```
Get-PackageProvider [[-Name] <String[]>] [-ListAvailable] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="3bcae-106">Description</span><span class="sxs-lookup"><span data-stu-id="3bcae-106">DESCRIPTION</span></span>

<span data-ttu-id="3bcae-107">**Get PackageProvider** コマンドレットは、Package Management に接続されているパッケージプロバイダーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="3bcae-107">The **Get-PackageProvider** cmdlet returns a list of package providers that are connected to Package Management.</span></span>
<span data-ttu-id="3bcae-108">これらのプロバイダーの例には、PSModule、NuGet、Chocolatey などがあります。</span><span class="sxs-lookup"><span data-stu-id="3bcae-108">Examples of these providers include PSModule, NuGet, and Chocolatey.</span></span>
<span data-ttu-id="3bcae-109">1つまたは複数のプロバイダー名の全体または一部に基づいて結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="3bcae-109">You can filter the results based on all or part of one or more provider names.</span></span>

## <span data-ttu-id="3bcae-110">例</span><span class="sxs-lookup"><span data-stu-id="3bcae-110">EXAMPLES</span></span>

### <span data-ttu-id="3bcae-111">例 1: 現在読み込まれているすべてのパッケージプロバイダーを取得する</span><span class="sxs-lookup"><span data-stu-id="3bcae-111">Example 1: Get all currently loaded package providers</span></span>

```
PS C:\> Get-PackageProvider
```

<span data-ttu-id="3bcae-112">このコマンドは、ローカルコンピューターに現在読み込まれているすべてのパッケージプロバイダーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="3bcae-112">This command gets a list of all the package providers that are currently loaded on the local computer.</span></span>

### <span data-ttu-id="3bcae-113">例 2: 使用可能なすべてのパッケージプロバイダーを取得する</span><span class="sxs-lookup"><span data-stu-id="3bcae-113">Example 2: Get all available package providers</span></span>

```
PS C:\> Get-PackageProvider -ListAvailable
```

<span data-ttu-id="3bcae-114">このコマンドは、ローカルコンピューターで使用可能なすべてのパッケージプロバイダーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="3bcae-114">This command gets a list of all package providers that are available on the local computer.</span></span>

### <span data-ttu-id="3bcae-115">例 3: パッケージプロバイダーを動的に取得する</span><span class="sxs-lookup"><span data-stu-id="3bcae-115">Example 3: Dynamically get a package provider</span></span>

```
PS C:\> Get-PackageProvider -Name "Chocolatey" -ForceBootstrap
```

<span data-ttu-id="3bcae-116">このコマンドを実行すると、コンピューターに Chocolatey プロバイダーがインストールされていない場合に、Chocolatey プロバイダーが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3bcae-116">This command automatically installs the Chocolatey provider if your computer does not have the Chocolatey provider installed.</span></span>

## <span data-ttu-id="3bcae-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3bcae-117">PARAMETERS</span></span>

### <span data-ttu-id="3bcae-118">-Force</span><span class="sxs-lookup"><span data-stu-id="3bcae-118">-Force</span></span>

<span data-ttu-id="3bcae-119">このコマンドレットが強制的に実行できるこのコマンドレットの他のすべての操作を強制することを示します。</span><span class="sxs-lookup"><span data-stu-id="3bcae-119">Indicates that this cmdlet forces all other actions with this cmdlet that can be forced.</span></span>
<span data-ttu-id="3bcae-120">**Get-PackageProvider** では、 *Force* パラメーターが *forcebootstrap* パラメーターと同じように動作することを意味します。</span><span class="sxs-lookup"><span data-stu-id="3bcae-120">In **Get-PackageProvider**, this means the *Force* parameter acts the same as the *ForceBootstrap* parameter.</span></span>

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

### <span data-ttu-id="3bcae-121">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="3bcae-121">-ForceBootstrap</span></span>

<span data-ttu-id="3bcae-122">このコマンドレットによって、パッケージプロバイダーを自動的にインストールするように Package Management を強制することを示します。</span><span class="sxs-lookup"><span data-stu-id="3bcae-122">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="3bcae-123">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="3bcae-123">-ListAvailable</span></span>

<span data-ttu-id="3bcae-124">インストールされているすべてのプロバイダーを取得します。</span><span class="sxs-lookup"><span data-stu-id="3bcae-124">Gets all installed providers.</span></span>
<span data-ttu-id="3bcae-125">**PSModulePath** 環境変数およびパッケージプロバイダーアセンブリフォルダーに一覧表示されているパス **で、プロバイダーを取得** します。</span><span class="sxs-lookup"><span data-stu-id="3bcae-125">**Get-PackageProvider** gets provider in paths listed in the **PSModulePath** environment variable as well as the package provider assembly folders:</span></span>

<span data-ttu-id="3bcae-126">**$env:P rogramFiles\PackageManagement\ProviderAssemblies \* \* \* \* $env: Localappdata\packagemanagement\providerassemblies から**</span><span class="sxs-lookup"><span data-stu-id="3bcae-126">**$env:ProgramFiles\PackageManagement\ProviderAssemblies\*\*\*\*$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies**</span></span>

<span data-ttu-id="3bcae-127">このパラメーターを指定しない場合、 **Get PackageProvider** は、現在のセッションに読み込まれているプロバイダーのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="3bcae-127">Without this parameter, **Get-PackageProvider** gets only the providers loaded in the current session.</span></span>

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

### <span data-ttu-id="3bcae-128">-Name</span><span class="sxs-lookup"><span data-stu-id="3bcae-128">-Name</span></span>

<span data-ttu-id="3bcae-129">1つまたは複数のプロバイダー名、またはプロバイダー名の一部を指定します。</span><span class="sxs-lookup"><span data-stu-id="3bcae-129">Specifies one or more provider names, or partial provider names.</span></span>
<span data-ttu-id="3bcae-130">複数のプロバイダー名はコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="3bcae-130">Separate multiple provider names with commas.</span></span>
<span data-ttu-id="3bcae-131">このパラメーターの有効な値には、パッケージと共にインストールしたプロバイダーの名前が含まれます。PackageManagement には、 **Psmodule** および **MSI** プロバイダーを含む、既定のプロバイダーのセットが付属しています。</span><span class="sxs-lookup"><span data-stu-id="3bcae-131">Valid values for this parameter include names of providers that you have installed with packages; PackageManagement ships with a set of default providers, including the **PSModule** and **MSI** providers.</span></span>

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

### <span data-ttu-id="3bcae-132">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="3bcae-132">CommonParameters</span></span>

<span data-ttu-id="3bcae-133">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="3bcae-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3bcae-134">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bcae-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3bcae-135">入力</span><span class="sxs-lookup"><span data-stu-id="3bcae-135">INPUTS</span></span>

## <span data-ttu-id="3bcae-136">出力</span><span class="sxs-lookup"><span data-stu-id="3bcae-136">OUTPUTS</span></span>

### <span data-ttu-id="3bcae-137">PackageProvider []</span><span class="sxs-lookup"><span data-stu-id="3bcae-137">PackageProvider[]</span></span>

## <span data-ttu-id="3bcae-138">注</span><span class="sxs-lookup"><span data-stu-id="3bcae-138">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3bcae-139">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="3bcae-139">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="3bcae-140">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="3bcae-140">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="3bcae-141">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="3bcae-141">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="3bcae-142">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bcae-142">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="3bcae-143">関連リンク</span><span class="sxs-lookup"><span data-stu-id="3bcae-143">RELATED LINKS</span></span>

[<span data-ttu-id="3bcae-144">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="3bcae-144">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="3bcae-145">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="3bcae-145">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="3bcae-146">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="3bcae-146">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="3bcae-147">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="3bcae-147">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
