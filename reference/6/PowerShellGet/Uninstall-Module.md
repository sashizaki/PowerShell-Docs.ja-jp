---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-module?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Module
ms.openlocfilehash: 9ba7e786acad0ffb2fffd8459561516ea8541109
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216523"
---
# <span data-ttu-id="70f2d-103">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="70f2d-103">Uninstall-Module</span></span>

## <span data-ttu-id="70f2d-104">概要</span><span class="sxs-lookup"><span data-stu-id="70f2d-104">SYNOPSIS</span></span>
<span data-ttu-id="70f2d-105">モジュールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="70f2d-105">Uninstalls a module.</span></span>

## <span data-ttu-id="70f2d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="70f2d-106">SYNTAX</span></span>

### <span data-ttu-id="70f2d-107">NameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="70f2d-107">NameParameterSet (Default)</span></span>

```
Uninstall-Module [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="70f2d-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="70f2d-108">InputObject</span></span>

```
Uninstall-Module [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="70f2d-109">Description</span><span class="sxs-lookup"><span data-stu-id="70f2d-109">DESCRIPTION</span></span>

<span data-ttu-id="70f2d-110">`Uninstall-Module`コマンドレットは、指定されたモジュールをローカルコンピューターからアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="70f2d-110">The `Uninstall-Module` cmdlet uninstalls a specified module from the local computer.</span></span> <span data-ttu-id="70f2d-111">モジュールが依存関係として他のモジュールを持っている場合、モジュールをアンインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="70f2d-111">You can't uninstall a module if it has other modules as dependencies.</span></span>

## <span data-ttu-id="70f2d-112">例</span><span class="sxs-lookup"><span data-stu-id="70f2d-112">EXAMPLES</span></span>

### <span data-ttu-id="70f2d-113">例 1: モジュールをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="70f2d-113">Example 1: Uninstall a module</span></span>

<span data-ttu-id="70f2d-114">この例では、モジュールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="70f2d-114">This example uninstalls a module.</span></span>

```powershell
Uninstall-Module -Name SpeculationControl
```

<span data-ttu-id="70f2d-115">`Uninstall-Module`**Name** パラメーターを使用して、ローカルコンピューターからアンインストールするモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="70f2d-115">`Uninstall-Module` uses the **Name** parameter to specify the module to uninstall from the local computer.</span></span>

### <span data-ttu-id="70f2d-116">例 2: パイプラインを使用してモジュールをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="70f2d-116">Example 2: Use the pipeline to uninstall a module</span></span>

<span data-ttu-id="70f2d-117">この例では、パイプラインを使用してモジュールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="70f2d-117">In this example, the pipeline is used to uninstall a module.</span></span>

```powershell
Get-InstalledModule -Name SpeculationControl | Uninstall-Module
```

<span data-ttu-id="70f2d-118">`Get-InstalledModule`**Name** パラメーターを使用してモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="70f2d-118">`Get-InstalledModule` uses the **Name** parameter to specify the module.</span></span> <span data-ttu-id="70f2d-119">オブジェクトは、にパイプラインで送信され、 `Uninstall-Module` アンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="70f2d-119">The object is sent down the pipeline to `Uninstall-Module` and is uninstalled.</span></span>

## <span data-ttu-id="70f2d-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="70f2d-120">PARAMETERS</span></span>

### <span data-ttu-id="70f2d-121">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="70f2d-121">-AllowPrerelease</span></span>

<span data-ttu-id="70f2d-122">プレリリースとしてマークされているモジュールをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="70f2d-122">Allows you to uninstall a module marked as a prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70f2d-123">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="70f2d-123">-AllVersions</span></span>

<span data-ttu-id="70f2d-124">モジュールの使用可能なすべてのバージョンを含めることを指定します。</span><span class="sxs-lookup"><span data-stu-id="70f2d-124">Specifies that you want to include all available versions of a module.</span></span> <span data-ttu-id="70f2d-125">**AllVersions** パラメーターは、 **MinimumVersion** 、 **MaximumVersion** 、または **RequiredVersion** パラメーターと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="70f2d-125">You can't use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70f2d-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="70f2d-126">-Confirm</span></span>

<span data-ttu-id="70f2d-127">を実行する前に確認メッセージを表示し `Uninstall-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="70f2d-127">Prompts you for confirmation before running the `Uninstall-Module`.</span></span>

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

### <span data-ttu-id="70f2d-128">-Force</span><span class="sxs-lookup"><span data-stu-id="70f2d-128">-Force</span></span>

<span data-ttu-id="70f2d-129">`Uninstall-Module`ユーザーの確認を求めることなく強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="70f2d-129">Forces `Uninstall-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="70f2d-130">-InputObject</span><span class="sxs-lookup"><span data-stu-id="70f2d-130">-InputObject</span></span>

<span data-ttu-id="70f2d-131">**できる psrepositoryiteminfo** オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="70f2d-131">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="70f2d-132">たとえば、 `Get-InstalledModule` 変数に出力し、その変数を **InputObject** 引数として使用します。</span><span class="sxs-lookup"><span data-stu-id="70f2d-132">For example, output `Get-InstalledModule` to a variable and use that variable as the **InputObject** argument.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="70f2d-133">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="70f2d-133">-MaximumVersion</span></span>

<span data-ttu-id="70f2d-134">アンインストールするモジュールの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="70f2d-134">Specifies the maximum, or newest, version of the module to uninstall.</span></span> <span data-ttu-id="70f2d-135">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="70f2d-135">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="70f2d-136">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="70f2d-136">-MinimumVersion</span></span>

<span data-ttu-id="70f2d-137">アンインストールするモジュールの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="70f2d-137">Specifies the minimum version of the module to uninstall.</span></span> <span data-ttu-id="70f2d-138">**MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="70f2d-138">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="70f2d-139">-Name</span><span class="sxs-lookup"><span data-stu-id="70f2d-139">-Name</span></span>

<span data-ttu-id="70f2d-140">アンインストールするモジュール名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="70f2d-140">Specifies an array of module names to uninstall.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="70f2d-141">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="70f2d-141">-RequiredVersion</span></span>

<span data-ttu-id="70f2d-142">アンインストールするモジュールの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="70f2d-142">Specifies the exact version number of the module to uninstall.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="70f2d-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="70f2d-143">-WhatIf</span></span>

<span data-ttu-id="70f2d-144">が実行された場合に何が起こるか `Uninstall-Module` を示します。</span><span class="sxs-lookup"><span data-stu-id="70f2d-144">Shows what would happen if `Uninstall-Module` runs.</span></span> <span data-ttu-id="70f2d-145">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="70f2d-145">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="70f2d-146">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="70f2d-146">CommonParameters</span></span>

<span data-ttu-id="70f2d-147">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="70f2d-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="70f2d-148">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70f2d-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="70f2d-149">入力</span><span class="sxs-lookup"><span data-stu-id="70f2d-149">INPUTS</span></span>

### <span data-ttu-id="70f2d-150">System.String[]</span><span class="sxs-lookup"><span data-stu-id="70f2d-150">System.String[]</span></span>

### <span data-ttu-id="70f2d-151">システムの管理. PSObject []</span><span class="sxs-lookup"><span data-stu-id="70f2d-151">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="70f2d-152">System.String</span><span class="sxs-lookup"><span data-stu-id="70f2d-152">System.String</span></span>

## <span data-ttu-id="70f2d-153">出力</span><span class="sxs-lookup"><span data-stu-id="70f2d-153">OUTPUTS</span></span>

### <span data-ttu-id="70f2d-154">System.Object</span><span class="sxs-lookup"><span data-stu-id="70f2d-154">System.Object</span></span>

## <span data-ttu-id="70f2d-155">注</span><span class="sxs-lookup"><span data-stu-id="70f2d-155">NOTES</span></span>

## <span data-ttu-id="70f2d-156">関連リンク</span><span class="sxs-lookup"><span data-stu-id="70f2d-156">RELATED LINKS</span></span>

[<span data-ttu-id="70f2d-157">Find-Module</span><span class="sxs-lookup"><span data-stu-id="70f2d-157">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="70f2d-158">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="70f2d-158">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="70f2d-159">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="70f2d-159">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="70f2d-160">Save-Module</span><span class="sxs-lookup"><span data-stu-id="70f2d-160">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="70f2d-161">Update-Module</span><span class="sxs-lookup"><span data-stu-id="70f2d-161">Update-Module</span></span>](Update-Module.md)
