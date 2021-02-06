---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-script?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Script
ms.openlocfilehash: 2cd8b51e1d4ef11a0a5f9e3542ff89e094854d8c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599722"
---
# <span data-ttu-id="27b32-102">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="27b32-102">Uninstall-Script</span></span>

## <span data-ttu-id="27b32-103">概要</span><span class="sxs-lookup"><span data-stu-id="27b32-103">SYNOPSIS</span></span>
<span data-ttu-id="27b32-104">スクリプトをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="27b32-104">Uninstalls a script.</span></span>

## <span data-ttu-id="27b32-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="27b32-105">SYNTAX</span></span>

### <span data-ttu-id="27b32-106">NameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="27b32-106">NameParameterSet (Default)</span></span>

```
Uninstall-Script [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="27b32-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="27b32-107">InputObject</span></span>

```
Uninstall-Script [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="27b32-108">Description</span><span class="sxs-lookup"><span data-stu-id="27b32-108">DESCRIPTION</span></span>

<span data-ttu-id="27b32-109">コマンドレットでは、 `Uninstall-Script` 指定したスクリプトをローカルコンピューターからアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="27b32-109">The `Uninstall-Script` cmdlet uninstalls a specified script from the local computer.</span></span>

## <span data-ttu-id="27b32-110">例</span><span class="sxs-lookup"><span data-stu-id="27b32-110">EXAMPLES</span></span>

### <span data-ttu-id="27b32-111">例 1: スクリプトをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="27b32-111">Example 1: Uninstall a script</span></span>

<span data-ttu-id="27b32-112">この例では、スクリプトをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="27b32-112">This example uninstalls a script.</span></span>

```powershell
Uninstall-Script -Name UpdateManagement-Template
```

<span data-ttu-id="27b32-113">`Uninstall-Script`**Name** パラメーターを使用して、ローカルコンピューターからアンインストールするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b32-113">`Uninstall-Script` uses the **Name** parameter to specify the script to uninstall from the local computer.</span></span>

### <span data-ttu-id="27b32-114">例 2: パイプラインを使用してスクリプトをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="27b32-114">Example 2: Use the pipeline to uninstall a script</span></span>

<span data-ttu-id="27b32-115">この例では、パイプラインを使用してスクリプトをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="27b32-115">In this example, the pipeline is used to uninstall a script.</span></span>

```powershell
Get-InstalledScript -Name UpdateManagement-Template | Uninstall-Script
```

<span data-ttu-id="27b32-116">`Get-InstalledScript`**Name** パラメーターを使用して、スクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b32-116">`Get-InstalledScript` uses the **Name** parameter to specify the script.</span></span> <span data-ttu-id="27b32-117">オブジェクトがにパイプラインで送信され、 `Uninstall-Script` スクリプトがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="27b32-117">The object is sent down the pipeline to `Uninstall-Script` and the script is uninstalled.</span></span>

## <span data-ttu-id="27b32-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="27b32-118">PARAMETERS</span></span>

### <span data-ttu-id="27b32-119">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="27b32-119">-AllowPrerelease</span></span>

<span data-ttu-id="27b32-120">プレリリースとしてマークされているスクリプトをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="27b32-120">Allows you to uninstall a script marked as a prerelease.</span></span>

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

### <span data-ttu-id="27b32-121">-Confirm</span><span class="sxs-lookup"><span data-stu-id="27b32-121">-Confirm</span></span>

<span data-ttu-id="27b32-122">実行前に確認メッセージを表示 `Uninstall-Script` します。</span><span class="sxs-lookup"><span data-stu-id="27b32-122">Prompts you for confirmation before running `Uninstall-Script`.</span></span>

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

### <span data-ttu-id="27b32-123">-Force</span><span class="sxs-lookup"><span data-stu-id="27b32-123">-Force</span></span>

<span data-ttu-id="27b32-124">`Uninstall-Script`ユーザーの確認を求めることなく強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="27b32-124">Forces `Uninstall-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="27b32-125">-InputObject</span><span class="sxs-lookup"><span data-stu-id="27b32-125">-InputObject</span></span>

<span data-ttu-id="27b32-126">**できる psrepositoryiteminfo** オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="27b32-126">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="27b32-127">たとえば、 `Get-InstalledScript` 変数に出力し、その変数を **InputObject** 引数として使用します。</span><span class="sxs-lookup"><span data-stu-id="27b32-127">For example, output `Get-InstalledScript` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="27b32-128">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="27b32-128">-MaximumVersion</span></span>

<span data-ttu-id="27b32-129">アンインストールするスクリプトの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b32-129">Specifies the maximum, or newest, version of the script to uninstall.</span></span> <span data-ttu-id="27b32-130">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="27b32-130">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="27b32-131">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="27b32-131">-MinimumVersion</span></span>

<span data-ttu-id="27b32-132">アンインストールするスクリプトの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="27b32-132">Specifies the minimum version of the script to uninstall.</span></span> <span data-ttu-id="27b32-133">**MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="27b32-133">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="27b32-134">-Name</span><span class="sxs-lookup"><span data-stu-id="27b32-134">-Name</span></span>

<span data-ttu-id="27b32-135">アンインストールするスクリプト名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="27b32-135">Specifies an array of script names to uninstall.</span></span>

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

### <span data-ttu-id="27b32-136">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="27b32-136">-RequiredVersion</span></span>

<span data-ttu-id="27b32-137">アンインストールするスクリプトの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="27b32-137">Specifies the exact version number of the script to uninstall.</span></span>

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

### <span data-ttu-id="27b32-138">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="27b32-138">-WhatIf</span></span>

<span data-ttu-id="27b32-139">が実行された場合に何が起こるか `Uninstall-Script` を示します。</span><span class="sxs-lookup"><span data-stu-id="27b32-139">Shows what would happen if `Uninstall-Script` runs.</span></span> <span data-ttu-id="27b32-140">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="27b32-140">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="27b32-141">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="27b32-141">CommonParameters</span></span>

<span data-ttu-id="27b32-142">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="27b32-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="27b32-143">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27b32-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="27b32-144">入力</span><span class="sxs-lookup"><span data-stu-id="27b32-144">INPUTS</span></span>

### <span data-ttu-id="27b32-145">System.String[]</span><span class="sxs-lookup"><span data-stu-id="27b32-145">System.String[]</span></span>

### <span data-ttu-id="27b32-146">システムの管理. PSObject []</span><span class="sxs-lookup"><span data-stu-id="27b32-146">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="27b32-147">System.String</span><span class="sxs-lookup"><span data-stu-id="27b32-147">System.String</span></span>

## <span data-ttu-id="27b32-148">出力</span><span class="sxs-lookup"><span data-stu-id="27b32-148">OUTPUTS</span></span>

### <span data-ttu-id="27b32-149">System.Object</span><span class="sxs-lookup"><span data-stu-id="27b32-149">System.Object</span></span>

## <span data-ttu-id="27b32-150">注</span><span class="sxs-lookup"><span data-stu-id="27b32-150">NOTES</span></span>

## <span data-ttu-id="27b32-151">関連リンク</span><span class="sxs-lookup"><span data-stu-id="27b32-151">RELATED LINKS</span></span>

[<span data-ttu-id="27b32-152">Find-Script</span><span class="sxs-lookup"><span data-stu-id="27b32-152">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="27b32-153">Install-Script</span><span class="sxs-lookup"><span data-stu-id="27b32-153">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="27b32-154">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="27b32-154">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="27b32-155">Save-Script</span><span class="sxs-lookup"><span data-stu-id="27b32-155">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="27b32-156">Update-Script</span><span class="sxs-lookup"><span data-stu-id="27b32-156">Update-Script</span></span>](Update-Script.md)

