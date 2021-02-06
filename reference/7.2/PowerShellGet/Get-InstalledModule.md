---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 02/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedmodule?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledModule
ms.openlocfilehash: 33621a89f846ca277c21aaf0ad8cd788b428da33
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600602"
---
# <span data-ttu-id="b2812-102">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="b2812-102">Get-InstalledModule</span></span>

## <span data-ttu-id="b2812-103">概要</span><span class="sxs-lookup"><span data-stu-id="b2812-103">SYNOPSIS</span></span>
<span data-ttu-id="b2812-104">PowerShellGet によってインストールされたコンピューター上のモジュールの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="b2812-104">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

## <span data-ttu-id="b2812-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b2812-105">SYNTAX</span></span>

```
Get-InstalledModule [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="b2812-106">Description</span><span class="sxs-lookup"><span data-stu-id="b2812-106">DESCRIPTION</span></span>

<span data-ttu-id="b2812-107">`Get-InstalledModule`コマンドレットは、PowerShellGet を使用してコンピューターにインストールされている PowerShell モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="b2812-107">The `Get-InstalledModule` cmdlet gets PowerShell modules that are installed on a computer using PowerShellGet.</span></span> <span data-ttu-id="b2812-108">システムにインストールされているすべてのモジュールを表示するには、コマンドを使用し `Get-Module -ListAvailable` ます。</span><span class="sxs-lookup"><span data-stu-id="b2812-108">To see all modules installed on the system, use the `Get-Module -ListAvailable` command.</span></span>

## <span data-ttu-id="b2812-109">例</span><span class="sxs-lookup"><span data-stu-id="b2812-109">EXAMPLES</span></span>

### <span data-ttu-id="b2812-110">例 1: インストールされているすべてのモジュールを取得する</span><span class="sxs-lookup"><span data-stu-id="b2812-110">Example 1: Get all installed modules</span></span>

```powershell
Get-InstalledModule
```

```Output
Version    Name                                Type       Repository     Description
-------    ----                                ----       ----------     -----------
2.0.0      PSGTEST-UploadMultipleVersionOfP... Module     GalleryINT     Module for DAC functionality
1.3.5      AzureAutomationDebug                Module     PSGallery      Module for debugging Azure Automation runbooks, emulating AA native cmdlets
1.0.1      AzureRM.Automation                  Module     PSGallery      Microsoft Azure PowerShell - Automation service cmdlets for Azure Resource Manager
```

<span data-ttu-id="b2812-111">このコマンドは、インストールされているすべてのモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="b2812-111">This command gets all installed modules.</span></span>

### <span data-ttu-id="b2812-112">例 2: モジュールの特定のバージョンを取得する</span><span class="sxs-lookup"><span data-stu-id="b2812-112">Example 2: Get specific versions of a module</span></span>

```powershell
Get-InstalledModule -Name "AzureRM.Automation" -MinimumVersion 1.0 -MaximumVersion 2.0
```

```Output
Version    Name                                Type       Repository     Description
-------    ----                                ----       ----------     -----------
1.0.1      AzureRM.Automation                  Module     PSGallery      Microsoft Azure PowerShell - Automation service cmdlets for Azure Resource Manager
```

<span data-ttu-id="b2812-113">このコマンドは、バージョン1.0 からバージョン2.0 の AzureRM. Automation モジュールのバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="b2812-113">This command gets versions of the AzureRM.Automation module from version 1.0 through version 2.0.</span></span>

## <span data-ttu-id="b2812-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b2812-114">PARAMETERS</span></span>

### <span data-ttu-id="b2812-115">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="b2812-115">-AllowPrerelease</span></span>

<span data-ttu-id="b2812-116">プレリリースとしてマークされた結果モジュールにを含めます。</span><span class="sxs-lookup"><span data-stu-id="b2812-116">Includes in the results modules marked as a prerelease.</span></span>

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

### <span data-ttu-id="b2812-117">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="b2812-117">-AllVersions</span></span>

<span data-ttu-id="b2812-118">モジュールの使用可能なすべてのバージョンを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="b2812-118">Indicates that you want to get all available versions of a module.</span></span>
<span data-ttu-id="b2812-119">**AllVersions** パラメーターは、 **MinimumVersion**、 **MaximumVersion**、または **RequiredVersion** パラメーターと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b2812-119">You cannot use the **AllVersions** parameter with the **MinimumVersion**, **MaximumVersion**, or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="b2812-120">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="b2812-120">-MaximumVersion</span></span>

<span data-ttu-id="b2812-121">取得するモジュールの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="b2812-121">Specifies the maximum, or newest, version of a module to get.</span></span> <span data-ttu-id="b2812-122">**MaximumVersion** および **RequiredVersion** パラメーターは相互に排他的です。両方のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b2812-122">The **MaximumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="b2812-123">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="b2812-123">-MinimumVersion</span></span>

<span data-ttu-id="b2812-124">取得する1つのモジュールの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="b2812-124">Specifies the minimum version of a single module to get.</span></span> <span data-ttu-id="b2812-125">**MinimumVersion** および **RequiredVersion** パラメーターは相互に排他的です。両方のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b2812-125">The **MinimumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="b2812-126">-Name</span><span class="sxs-lookup"><span data-stu-id="b2812-126">-Name</span></span>

<span data-ttu-id="b2812-127">取得するモジュールの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b2812-127">Specifies an array of names of modules to get.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b2812-128">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="b2812-128">-RequiredVersion</span></span>

<span data-ttu-id="b2812-129">取得するモジュールの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="b2812-129">Specifies the exact version of a module to get.</span></span>

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

### <span data-ttu-id="b2812-130">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b2812-130">CommonParameters</span></span>

<span data-ttu-id="b2812-131">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b2812-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b2812-132">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2812-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b2812-133">入力</span><span class="sxs-lookup"><span data-stu-id="b2812-133">INPUTS</span></span>

### <span data-ttu-id="b2812-134">System.String[]</span><span class="sxs-lookup"><span data-stu-id="b2812-134">System.String[]</span></span>

### <span data-ttu-id="b2812-135">System.String</span><span class="sxs-lookup"><span data-stu-id="b2812-135">System.String</span></span>

## <span data-ttu-id="b2812-136">出力</span><span class="sxs-lookup"><span data-stu-id="b2812-136">OUTPUTS</span></span>

### <span data-ttu-id="b2812-137">システムの管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="b2812-137">System.Management.Automation.PSCustomObject</span></span>

## <span data-ttu-id="b2812-138">注</span><span class="sxs-lookup"><span data-stu-id="b2812-138">NOTES</span></span>

## <span data-ttu-id="b2812-139">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b2812-139">RELATED LINKS</span></span>

