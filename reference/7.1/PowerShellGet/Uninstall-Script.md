---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-script?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Script
ms.openlocfilehash: 26e32cc3d7330026bd77d33ba6574818559d1c6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212616"
---
# <span data-ttu-id="de8ca-103">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="de8ca-103">Uninstall-Script</span></span>

## <span data-ttu-id="de8ca-104">概要</span><span class="sxs-lookup"><span data-stu-id="de8ca-104">SYNOPSIS</span></span>
<span data-ttu-id="de8ca-105">スクリプトをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="de8ca-105">Uninstalls a script.</span></span>

## <span data-ttu-id="de8ca-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="de8ca-106">SYNTAX</span></span>

### <span data-ttu-id="de8ca-107">NameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="de8ca-107">NameParameterSet (Default)</span></span>

```
Uninstall-Script [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="de8ca-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="de8ca-108">InputObject</span></span>

```
Uninstall-Script [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="de8ca-109">Description</span><span class="sxs-lookup"><span data-stu-id="de8ca-109">DESCRIPTION</span></span>

<span data-ttu-id="de8ca-110">コマンドレットでは、 `Uninstall-Script` 指定したスクリプトをローカルコンピューターからアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="de8ca-110">The `Uninstall-Script` cmdlet uninstalls a specified script from the local computer.</span></span>

## <span data-ttu-id="de8ca-111">例</span><span class="sxs-lookup"><span data-stu-id="de8ca-111">EXAMPLES</span></span>

### <span data-ttu-id="de8ca-112">例 1: スクリプトをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="de8ca-112">Example 1: Uninstall a script</span></span>

<span data-ttu-id="de8ca-113">この例では、スクリプトをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="de8ca-113">This example uninstalls a script.</span></span>

```powershell
Uninstall-Script -Name UpdateManagement-Template
```

<span data-ttu-id="de8ca-114">`Uninstall-Script`**Name** パラメーターを使用して、ローカルコンピューターからアンインストールするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="de8ca-114">`Uninstall-Script` uses the **Name** parameter to specify the script to uninstall from the local computer.</span></span>

### <span data-ttu-id="de8ca-115">例 2: パイプラインを使用してスクリプトをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="de8ca-115">Example 2: Use the pipeline to uninstall a script</span></span>

<span data-ttu-id="de8ca-116">この例では、パイプラインを使用してスクリプトをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="de8ca-116">In this example, the pipeline is used to uninstall a script.</span></span>

```powershell
Get-InstalledScript -Name UpdateManagement-Template | Uninstall-Script
```

<span data-ttu-id="de8ca-117">`Get-InstalledScript`**Name** パラメーターを使用して、スクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="de8ca-117">`Get-InstalledScript` uses the **Name** parameter to specify the script.</span></span> <span data-ttu-id="de8ca-118">オブジェクトがにパイプラインで送信され、 `Uninstall-Script` スクリプトがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="de8ca-118">The object is sent down the pipeline to `Uninstall-Script` and the script is uninstalled.</span></span>

## <span data-ttu-id="de8ca-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="de8ca-119">PARAMETERS</span></span>

### <span data-ttu-id="de8ca-120">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="de8ca-120">-AllowPrerelease</span></span>

<span data-ttu-id="de8ca-121">プレリリースとしてマークされているスクリプトをアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="de8ca-121">Allows you to uninstall a script marked as a prerelease.</span></span>

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

### <span data-ttu-id="de8ca-122">-Confirm</span><span class="sxs-lookup"><span data-stu-id="de8ca-122">-Confirm</span></span>

<span data-ttu-id="de8ca-123">実行前に確認メッセージを表示 `Uninstall-Script` します。</span><span class="sxs-lookup"><span data-stu-id="de8ca-123">Prompts you for confirmation before running `Uninstall-Script`.</span></span>

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

### <span data-ttu-id="de8ca-124">-Force</span><span class="sxs-lookup"><span data-stu-id="de8ca-124">-Force</span></span>

<span data-ttu-id="de8ca-125">`Uninstall-Script`ユーザーの確認を求めることなく強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="de8ca-125">Forces `Uninstall-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="de8ca-126">-InputObject</span><span class="sxs-lookup"><span data-stu-id="de8ca-126">-InputObject</span></span>

<span data-ttu-id="de8ca-127">**できる psrepositoryiteminfo** オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="de8ca-127">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="de8ca-128">たとえば、 `Get-InstalledScript` 変数に出力し、その変数を **InputObject** 引数として使用します。</span><span class="sxs-lookup"><span data-stu-id="de8ca-128">For example, output `Get-InstalledScript` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="de8ca-129">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="de8ca-129">-MaximumVersion</span></span>

<span data-ttu-id="de8ca-130">アンインストールするスクリプトの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="de8ca-130">Specifies the maximum, or newest, version of the script to uninstall.</span></span> <span data-ttu-id="de8ca-131">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="de8ca-131">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="de8ca-132">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="de8ca-132">-MinimumVersion</span></span>

<span data-ttu-id="de8ca-133">アンインストールするスクリプトの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="de8ca-133">Specifies the minimum version of the script to uninstall.</span></span> <span data-ttu-id="de8ca-134">**MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="de8ca-134">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="de8ca-135">-Name</span><span class="sxs-lookup"><span data-stu-id="de8ca-135">-Name</span></span>

<span data-ttu-id="de8ca-136">アンインストールするスクリプト名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="de8ca-136">Specifies an array of script names to uninstall.</span></span>

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

### <span data-ttu-id="de8ca-137">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="de8ca-137">-RequiredVersion</span></span>

<span data-ttu-id="de8ca-138">アンインストールするスクリプトの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="de8ca-138">Specifies the exact version number of the script to uninstall.</span></span>

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

### <span data-ttu-id="de8ca-139">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="de8ca-139">-WhatIf</span></span>

<span data-ttu-id="de8ca-140">が実行された場合に何が起こるか `Uninstall-Script` を示します。</span><span class="sxs-lookup"><span data-stu-id="de8ca-140">Shows what would happen if `Uninstall-Script` runs.</span></span> <span data-ttu-id="de8ca-141">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="de8ca-141">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="de8ca-142">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="de8ca-142">CommonParameters</span></span>

<span data-ttu-id="de8ca-143">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="de8ca-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="de8ca-144">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de8ca-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="de8ca-145">入力</span><span class="sxs-lookup"><span data-stu-id="de8ca-145">INPUTS</span></span>

### <span data-ttu-id="de8ca-146">System.String[]</span><span class="sxs-lookup"><span data-stu-id="de8ca-146">System.String[]</span></span>

### <span data-ttu-id="de8ca-147">システムの管理. PSObject []</span><span class="sxs-lookup"><span data-stu-id="de8ca-147">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="de8ca-148">System.String</span><span class="sxs-lookup"><span data-stu-id="de8ca-148">System.String</span></span>

## <span data-ttu-id="de8ca-149">出力</span><span class="sxs-lookup"><span data-stu-id="de8ca-149">OUTPUTS</span></span>

### <span data-ttu-id="de8ca-150">System.Object</span><span class="sxs-lookup"><span data-stu-id="de8ca-150">System.Object</span></span>

## <span data-ttu-id="de8ca-151">注</span><span class="sxs-lookup"><span data-stu-id="de8ca-151">NOTES</span></span>

## <span data-ttu-id="de8ca-152">関連リンク</span><span class="sxs-lookup"><span data-stu-id="de8ca-152">RELATED LINKS</span></span>

[<span data-ttu-id="de8ca-153">Find-Script</span><span class="sxs-lookup"><span data-stu-id="de8ca-153">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="de8ca-154">Install-Script</span><span class="sxs-lookup"><span data-stu-id="de8ca-154">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="de8ca-155">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="de8ca-155">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="de8ca-156">Save-Script</span><span class="sxs-lookup"><span data-stu-id="de8ca-156">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="de8ca-157">Update-Script</span><span class="sxs-lookup"><span data-stu-id="de8ca-157">Update-Script</span></span>](Update-Script.md)

