---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Module
ms.openlocfilehash: 0df911ad8b1f7b4516eef4a1c2b0180893013e3e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599930"
---
# <span data-ttu-id="0d3ee-102">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="0d3ee-102">Uninstall-Module</span></span>

## <span data-ttu-id="0d3ee-103">概要</span><span class="sxs-lookup"><span data-stu-id="0d3ee-103">SYNOPSIS</span></span>
<span data-ttu-id="0d3ee-104">モジュールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-104">Uninstalls a module.</span></span>

## <span data-ttu-id="0d3ee-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0d3ee-105">SYNTAX</span></span>

### <span data-ttu-id="0d3ee-106">NameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="0d3ee-106">NameParameterSet (Default)</span></span>

```
Uninstall-Module [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="0d3ee-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="0d3ee-107">InputObject</span></span>

```
Uninstall-Module [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0d3ee-108">Description</span><span class="sxs-lookup"><span data-stu-id="0d3ee-108">DESCRIPTION</span></span>

<span data-ttu-id="0d3ee-109">`Uninstall-Module`コマンドレットは、指定されたモジュールをローカルコンピューターからアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-109">The `Uninstall-Module` cmdlet uninstalls a specified module from the local computer.</span></span> <span data-ttu-id="0d3ee-110">モジュールが依存関係として他のモジュールを持っている場合、モジュールをアンインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-110">You can't uninstall a module if it has other modules as dependencies.</span></span>

## <span data-ttu-id="0d3ee-111">例</span><span class="sxs-lookup"><span data-stu-id="0d3ee-111">EXAMPLES</span></span>

### <span data-ttu-id="0d3ee-112">例 1: モジュールをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="0d3ee-112">Example 1: Uninstall a module</span></span>

<span data-ttu-id="0d3ee-113">この例では、モジュールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-113">This example uninstalls a module.</span></span>

```powershell
Uninstall-Module -Name SpeculationControl
```

<span data-ttu-id="0d3ee-114">`Uninstall-Module`**Name** パラメーターを使用して、ローカルコンピューターからアンインストールするモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-114">`Uninstall-Module` uses the **Name** parameter to specify the module to uninstall from the local computer.</span></span>

### <span data-ttu-id="0d3ee-115">例 2: パイプラインを使用してモジュールをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="0d3ee-115">Example 2: Use the pipeline to uninstall a module</span></span>

<span data-ttu-id="0d3ee-116">この例では、パイプラインを使用してモジュールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-116">In this example, the pipeline is used to uninstall a module.</span></span>

```powershell
Get-InstalledModule -Name SpeculationControl | Uninstall-Module
```

<span data-ttu-id="0d3ee-117">`Get-InstalledModule`**Name** パラメーターを使用してモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-117">`Get-InstalledModule` uses the **Name** parameter to specify the module.</span></span> <span data-ttu-id="0d3ee-118">オブジェクトは、にパイプラインで送信され、 `Uninstall-Module` アンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-118">The object is sent down the pipeline to `Uninstall-Module` and is uninstalled.</span></span>

## <span data-ttu-id="0d3ee-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0d3ee-119">PARAMETERS</span></span>

### <span data-ttu-id="0d3ee-120">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="0d3ee-120">-AllowPrerelease</span></span>

<span data-ttu-id="0d3ee-121">プレリリースとしてマークされているモジュールをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-121">Allows you to uninstall a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="0d3ee-122">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="0d3ee-122">-AllVersions</span></span>

<span data-ttu-id="0d3ee-123">モジュールの使用可能なすべてのバージョンを含めることを指定します。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-123">Specifies that you want to include all available versions of a module.</span></span> <span data-ttu-id="0d3ee-124">**AllVersions** パラメーターは、 **MinimumVersion**、 **MaximumVersion**、または **RequiredVersion** パラメーターと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-124">You can't use the **AllVersions** parameter with the **MinimumVersion**, **MaximumVersion**, or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="0d3ee-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0d3ee-125">-Confirm</span></span>

<span data-ttu-id="0d3ee-126">を実行する前に確認メッセージを表示し `Uninstall-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-126">Prompts you for confirmation before running the `Uninstall-Module`.</span></span>

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

### <span data-ttu-id="0d3ee-127">-Force</span><span class="sxs-lookup"><span data-stu-id="0d3ee-127">-Force</span></span>

<span data-ttu-id="0d3ee-128">`Uninstall-Module`ユーザーの確認を求めることなく強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-128">Forces `Uninstall-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="0d3ee-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0d3ee-129">-InputObject</span></span>

<span data-ttu-id="0d3ee-130">**できる psrepositoryiteminfo** オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-130">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="0d3ee-131">たとえば、 `Get-InstalledModule` 変数に出力し、その変数を **InputObject** 引数として使用します。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-131">For example, output `Get-InstalledModule` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="0d3ee-132">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="0d3ee-132">-MaximumVersion</span></span>

<span data-ttu-id="0d3ee-133">アンインストールするモジュールの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-133">Specifies the maximum, or newest, version of the module to uninstall.</span></span> <span data-ttu-id="0d3ee-134">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-134">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="0d3ee-135">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="0d3ee-135">-MinimumVersion</span></span>

<span data-ttu-id="0d3ee-136">アンインストールするモジュールの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-136">Specifies the minimum version of the module to uninstall.</span></span> <span data-ttu-id="0d3ee-137">**MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-137">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="0d3ee-138">-Name</span><span class="sxs-lookup"><span data-stu-id="0d3ee-138">-Name</span></span>

<span data-ttu-id="0d3ee-139">アンインストールするモジュール名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-139">Specifies an array of module names to uninstall.</span></span>

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

### <span data-ttu-id="0d3ee-140">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="0d3ee-140">-RequiredVersion</span></span>

<span data-ttu-id="0d3ee-141">アンインストールするモジュールの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-141">Specifies the exact version number of the module to uninstall.</span></span>

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

### <span data-ttu-id="0d3ee-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0d3ee-142">-WhatIf</span></span>

<span data-ttu-id="0d3ee-143">が実行された場合に何が起こるか `Uninstall-Module` を示します。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-143">Shows what would happen if `Uninstall-Module` runs.</span></span> <span data-ttu-id="0d3ee-144">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-144">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="0d3ee-145">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="0d3ee-145">CommonParameters</span></span>

<span data-ttu-id="0d3ee-146">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0d3ee-147">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d3ee-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0d3ee-148">入力</span><span class="sxs-lookup"><span data-stu-id="0d3ee-148">INPUTS</span></span>

### <span data-ttu-id="0d3ee-149">System.String[]</span><span class="sxs-lookup"><span data-stu-id="0d3ee-149">System.String[]</span></span>

### <span data-ttu-id="0d3ee-150">システムの管理. PSObject []</span><span class="sxs-lookup"><span data-stu-id="0d3ee-150">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="0d3ee-151">System.String</span><span class="sxs-lookup"><span data-stu-id="0d3ee-151">System.String</span></span>

## <span data-ttu-id="0d3ee-152">出力</span><span class="sxs-lookup"><span data-stu-id="0d3ee-152">OUTPUTS</span></span>

### <span data-ttu-id="0d3ee-153">System.Object</span><span class="sxs-lookup"><span data-stu-id="0d3ee-153">System.Object</span></span>

## <span data-ttu-id="0d3ee-154">注</span><span class="sxs-lookup"><span data-stu-id="0d3ee-154">NOTES</span></span>

## <span data-ttu-id="0d3ee-155">関連リンク</span><span class="sxs-lookup"><span data-stu-id="0d3ee-155">RELATED LINKS</span></span>

[<span data-ttu-id="0d3ee-156">Find-Module</span><span class="sxs-lookup"><span data-stu-id="0d3ee-156">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="0d3ee-157">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="0d3ee-157">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="0d3ee-158">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="0d3ee-158">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="0d3ee-159">Save-Module</span><span class="sxs-lookup"><span data-stu-id="0d3ee-159">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="0d3ee-160">Update-Module</span><span class="sxs-lookup"><span data-stu-id="0d3ee-160">Update-Module</span></span>](Update-Module.md)

