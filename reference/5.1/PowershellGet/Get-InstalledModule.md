---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 02/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedmodule?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledModule
ms.openlocfilehash: e894e2f71e0a76badd05b86b42903d49aab4af0b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213203"
---
# <span data-ttu-id="a1afb-103">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="a1afb-103">Get-InstalledModule</span></span>

## <span data-ttu-id="a1afb-104">概要</span><span class="sxs-lookup"><span data-stu-id="a1afb-104">SYNOPSIS</span></span>
<span data-ttu-id="a1afb-105">PowerShellGet によってインストールされたコンピューター上のモジュールの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="a1afb-105">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

## <span data-ttu-id="a1afb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a1afb-106">SYNTAX</span></span>

```
Get-InstalledModule [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="a1afb-107">Description</span><span class="sxs-lookup"><span data-stu-id="a1afb-107">DESCRIPTION</span></span>

<span data-ttu-id="a1afb-108">`Get-InstalledModule`コマンドレットは、PowerShellGet を使用してコンピューターにインストールされている PowerShell モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="a1afb-108">The `Get-InstalledModule` cmdlet gets PowerShell modules that are installed on a computer using PowerShellGet.</span></span> <span data-ttu-id="a1afb-109">システムにインストールされているすべてのモジュールを表示するには、コマンドを使用し `Get-Module -ListAvailable` ます。</span><span class="sxs-lookup"><span data-stu-id="a1afb-109">To see all modules installed on the system, use the `Get-Module -ListAvailable` command.</span></span>

## <span data-ttu-id="a1afb-110">例</span><span class="sxs-lookup"><span data-stu-id="a1afb-110">EXAMPLES</span></span>

### <span data-ttu-id="a1afb-111">例 1: インストールされているすべてのモジュールを取得する</span><span class="sxs-lookup"><span data-stu-id="a1afb-111">Example 1: Get all installed modules</span></span>

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

<span data-ttu-id="a1afb-112">このコマンドは、インストールされているすべてのモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="a1afb-112">This command gets all installed modules.</span></span>

### <span data-ttu-id="a1afb-113">例 2: モジュールの特定のバージョンを取得する</span><span class="sxs-lookup"><span data-stu-id="a1afb-113">Example 2: Get specific versions of a module</span></span>

```powershell
Get-InstalledModule -Name "AzureRM.Automation" -MinimumVersion 1.0 -MaximumVersion 2.0
```

```Output
Version    Name                                Type       Repository     Description
-------    ----                                ----       ----------     -----------
1.0.1      AzureRM.Automation                  Module     PSGallery      Microsoft Azure PowerShell - Automation service cmdlets for Azure Resource Manager
```

<span data-ttu-id="a1afb-114">このコマンドは、バージョン1.0 からバージョン2.0 の AzureRM. Automation モジュールのバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="a1afb-114">This command gets versions of the AzureRM.Automation module from version 1.0 through version 2.0.</span></span>

## <span data-ttu-id="a1afb-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a1afb-115">PARAMETERS</span></span>

### <span data-ttu-id="a1afb-116">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="a1afb-116">-AllowPrerelease</span></span>

<span data-ttu-id="a1afb-117">プレリリースとしてマークされた結果モジュールにを含めます。</span><span class="sxs-lookup"><span data-stu-id="a1afb-117">Includes in the results modules marked as a prerelease.</span></span>

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

### <span data-ttu-id="a1afb-118">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="a1afb-118">-AllVersions</span></span>

<span data-ttu-id="a1afb-119">モジュールの使用可能なすべてのバージョンを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="a1afb-119">Indicates that you want to get all available versions of a module.</span></span>
<span data-ttu-id="a1afb-120">**AllVersions** パラメーターは、 **MinimumVersion** 、 **MaximumVersion** 、または **RequiredVersion** パラメーターと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a1afb-120">You cannot use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="a1afb-121">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="a1afb-121">-MaximumVersion</span></span>

<span data-ttu-id="a1afb-122">取得するモジュールの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1afb-122">Specifies the maximum, or newest, version of a module to get.</span></span> <span data-ttu-id="a1afb-123">**MaximumVersion** および **RequiredVersion** パラメーターは相互に排他的です。両方のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a1afb-123">The **MaximumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="a1afb-124">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="a1afb-124">-MinimumVersion</span></span>

<span data-ttu-id="a1afb-125">取得する1つのモジュールの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1afb-125">Specifies the minimum version of a single module to get.</span></span> <span data-ttu-id="a1afb-126">**MinimumVersion** および **RequiredVersion** パラメーターは相互に排他的です。両方のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a1afb-126">The **MinimumVersion** and **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="a1afb-127">-Name</span><span class="sxs-lookup"><span data-stu-id="a1afb-127">-Name</span></span>

<span data-ttu-id="a1afb-128">取得するモジュールの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1afb-128">Specifies an array of names of modules to get.</span></span>

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

### <span data-ttu-id="a1afb-129">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="a1afb-129">-RequiredVersion</span></span>

<span data-ttu-id="a1afb-130">取得するモジュールの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1afb-130">Specifies the exact version of a module to get.</span></span>

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

### <span data-ttu-id="a1afb-131">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1afb-131">CommonParameters</span></span>

<span data-ttu-id="a1afb-132">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a1afb-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a1afb-133">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1afb-133">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a1afb-134">入力</span><span class="sxs-lookup"><span data-stu-id="a1afb-134">INPUTS</span></span>

## <span data-ttu-id="a1afb-135">出力</span><span class="sxs-lookup"><span data-stu-id="a1afb-135">OUTPUTS</span></span>

### <span data-ttu-id="a1afb-136">システムの管理. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="a1afb-136">System.Management.Automation.PSCustomObject</span></span>

## <span data-ttu-id="a1afb-137">注</span><span class="sxs-lookup"><span data-stu-id="a1afb-137">NOTES</span></span>

## <span data-ttu-id="a1afb-138">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a1afb-138">RELATED LINKS</span></span>