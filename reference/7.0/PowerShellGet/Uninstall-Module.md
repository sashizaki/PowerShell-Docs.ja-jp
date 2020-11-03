---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-module?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Module
ms.openlocfilehash: 427f50a697186354c889e85bf080189f5ee4af9c
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211352"
---
# <span data-ttu-id="1cd1b-103">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="1cd1b-103">Uninstall-Module</span></span>

## <span data-ttu-id="1cd1b-104">概要</span><span class="sxs-lookup"><span data-stu-id="1cd1b-104">SYNOPSIS</span></span>
<span data-ttu-id="1cd1b-105">モジュールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-105">Uninstalls a module.</span></span>

## <span data-ttu-id="1cd1b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1cd1b-106">SYNTAX</span></span>

### <span data-ttu-id="1cd1b-107">NameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="1cd1b-107">NameParameterSet (Default)</span></span>

```
Uninstall-Module [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="1cd1b-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="1cd1b-108">InputObject</span></span>

```
Uninstall-Module [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1cd1b-109">Description</span><span class="sxs-lookup"><span data-stu-id="1cd1b-109">DESCRIPTION</span></span>

<span data-ttu-id="1cd1b-110">`Uninstall-Module`コマンドレットは、指定されたモジュールをローカルコンピューターからアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-110">The `Uninstall-Module` cmdlet uninstalls a specified module from the local computer.</span></span> <span data-ttu-id="1cd1b-111">モジュールが依存関係として他のモジュールを持っている場合、モジュールをアンインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-111">You can't uninstall a module if it has other modules as dependencies.</span></span>

## <span data-ttu-id="1cd1b-112">例</span><span class="sxs-lookup"><span data-stu-id="1cd1b-112">EXAMPLES</span></span>

### <span data-ttu-id="1cd1b-113">例 1: モジュールをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="1cd1b-113">Example 1: Uninstall a module</span></span>

<span data-ttu-id="1cd1b-114">この例では、モジュールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-114">This example uninstalls a module.</span></span>

```powershell
Uninstall-Module -Name SpeculationControl
```

<span data-ttu-id="1cd1b-115">`Uninstall-Module`**Name** パラメーターを使用して、ローカルコンピューターからアンインストールするモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-115">`Uninstall-Module` uses the **Name** parameter to specify the module to uninstall from the local computer.</span></span>

### <span data-ttu-id="1cd1b-116">例 2: パイプラインを使用してモジュールをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="1cd1b-116">Example 2: Use the pipeline to uninstall a module</span></span>

<span data-ttu-id="1cd1b-117">この例では、パイプラインを使用してモジュールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-117">In this example, the pipeline is used to uninstall a module.</span></span>

```powershell
Get-InstalledModule -Name SpeculationControl | Uninstall-Module
```

<span data-ttu-id="1cd1b-118">`Get-InstalledModule`**Name** パラメーターを使用してモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-118">`Get-InstalledModule` uses the **Name** parameter to specify the module.</span></span> <span data-ttu-id="1cd1b-119">オブジェクトは、にパイプラインで送信され、 `Uninstall-Module` アンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-119">The object is sent down the pipeline to `Uninstall-Module` and is uninstalled.</span></span>

## <span data-ttu-id="1cd1b-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1cd1b-120">PARAMETERS</span></span>

### <span data-ttu-id="1cd1b-121">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="1cd1b-121">-AllowPrerelease</span></span>

<span data-ttu-id="1cd1b-122">プレリリースとしてマークされているモジュールをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-122">Allows you to uninstall a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="1cd1b-123">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="1cd1b-123">-AllVersions</span></span>

<span data-ttu-id="1cd1b-124">モジュールの使用可能なすべてのバージョンを含めることを指定します。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-124">Specifies that you want to include all available versions of a module.</span></span> <span data-ttu-id="1cd1b-125">**AllVersions** パラメーターは、 **MinimumVersion** 、 **MaximumVersion** 、または **RequiredVersion** パラメーターと共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-125">You can't use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="1cd1b-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1cd1b-126">-Confirm</span></span>

<span data-ttu-id="1cd1b-127">を実行する前に確認メッセージを表示し `Uninstall-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-127">Prompts you for confirmation before running the `Uninstall-Module`.</span></span>

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

### <span data-ttu-id="1cd1b-128">-Force</span><span class="sxs-lookup"><span data-stu-id="1cd1b-128">-Force</span></span>

<span data-ttu-id="1cd1b-129">`Uninstall-Module`ユーザーの確認を求めることなく強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-129">Forces `Uninstall-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="1cd1b-130">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1cd1b-130">-InputObject</span></span>

<span data-ttu-id="1cd1b-131">**できる psrepositoryiteminfo** オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-131">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="1cd1b-132">たとえば、 `Get-InstalledModule` 変数に出力し、その変数を **InputObject** 引数として使用します。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-132">For example, output `Get-InstalledModule` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="1cd1b-133">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="1cd1b-133">-MaximumVersion</span></span>

<span data-ttu-id="1cd1b-134">アンインストールするモジュールの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-134">Specifies the maximum, or newest, version of the module to uninstall.</span></span> <span data-ttu-id="1cd1b-135">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-135">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="1cd1b-136">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="1cd1b-136">-MinimumVersion</span></span>

<span data-ttu-id="1cd1b-137">アンインストールするモジュールの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-137">Specifies the minimum version of the module to uninstall.</span></span> <span data-ttu-id="1cd1b-138">**MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-138">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="1cd1b-139">-Name</span><span class="sxs-lookup"><span data-stu-id="1cd1b-139">-Name</span></span>

<span data-ttu-id="1cd1b-140">アンインストールするモジュール名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-140">Specifies an array of module names to uninstall.</span></span>

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

### <span data-ttu-id="1cd1b-141">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="1cd1b-141">-RequiredVersion</span></span>

<span data-ttu-id="1cd1b-142">アンインストールするモジュールの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-142">Specifies the exact version number of the module to uninstall.</span></span>

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

### <span data-ttu-id="1cd1b-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1cd1b-143">-WhatIf</span></span>

<span data-ttu-id="1cd1b-144">が実行された場合に何が起こるか `Uninstall-Module` を示します。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-144">Shows what would happen if `Uninstall-Module` runs.</span></span> <span data-ttu-id="1cd1b-145">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-145">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="1cd1b-146">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1cd1b-146">CommonParameters</span></span>

<span data-ttu-id="1cd1b-147">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1cd1b-148">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cd1b-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1cd1b-149">入力</span><span class="sxs-lookup"><span data-stu-id="1cd1b-149">INPUTS</span></span>

### <span data-ttu-id="1cd1b-150">System.String[]</span><span class="sxs-lookup"><span data-stu-id="1cd1b-150">System.String[]</span></span>

### <span data-ttu-id="1cd1b-151">システムの管理. PSObject []</span><span class="sxs-lookup"><span data-stu-id="1cd1b-151">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="1cd1b-152">System.String</span><span class="sxs-lookup"><span data-stu-id="1cd1b-152">System.String</span></span>

## <span data-ttu-id="1cd1b-153">出力</span><span class="sxs-lookup"><span data-stu-id="1cd1b-153">OUTPUTS</span></span>

### <span data-ttu-id="1cd1b-154">System.Object</span><span class="sxs-lookup"><span data-stu-id="1cd1b-154">System.Object</span></span>

## <span data-ttu-id="1cd1b-155">注</span><span class="sxs-lookup"><span data-stu-id="1cd1b-155">NOTES</span></span>

## <span data-ttu-id="1cd1b-156">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1cd1b-156">RELATED LINKS</span></span>

[<span data-ttu-id="1cd1b-157">Find-Module</span><span class="sxs-lookup"><span data-stu-id="1cd1b-157">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="1cd1b-158">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="1cd1b-158">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="1cd1b-159">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="1cd1b-159">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="1cd1b-160">Save-Module</span><span class="sxs-lookup"><span data-stu-id="1cd1b-160">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="1cd1b-161">Update-Module</span><span class="sxs-lookup"><span data-stu-id="1cd1b-161">Update-Module</span></span>](Update-Module.md)
