---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-script?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Script
ms.openlocfilehash: 5a43e3382990209c365bb8fe5c0b320624ddfe18
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216160"
---
# <span data-ttu-id="7ae36-103">Update-Script</span><span class="sxs-lookup"><span data-stu-id="7ae36-103">Update-Script</span></span>

## <span data-ttu-id="7ae36-104">概要</span><span class="sxs-lookup"><span data-stu-id="7ae36-104">SYNOPSIS</span></span>
<span data-ttu-id="7ae36-105">スクリプトを更新します。</span><span class="sxs-lookup"><span data-stu-id="7ae36-105">Updates a script.</span></span>

## <span data-ttu-id="7ae36-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7ae36-106">SYNTAX</span></span>

### <span data-ttu-id="7ae36-107">All</span><span class="sxs-lookup"><span data-stu-id="7ae36-107">All</span></span>

```
Update-Script [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7ae36-108">Description</span><span class="sxs-lookup"><span data-stu-id="7ae36-108">DESCRIPTION</span></span>

<span data-ttu-id="7ae36-109">`Update-Script`コマンドレットは、ローカルコンピューターにインストールされているスクリプトを更新します。</span><span class="sxs-lookup"><span data-stu-id="7ae36-109">The `Update-Script` cmdlet updates a script that is installed on the local computer.</span></span> <span data-ttu-id="7ae36-110">更新されたスクリプトは、インストールされているバージョンと同じリポジトリからダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="7ae36-110">The updated script is downloaded from the same repository as the installed version.</span></span>

## <span data-ttu-id="7ae36-111">例</span><span class="sxs-lookup"><span data-stu-id="7ae36-111">EXAMPLES</span></span>

### <span data-ttu-id="7ae36-112">例 1: 指定したスクリプトを更新する</span><span class="sxs-lookup"><span data-stu-id="7ae36-112">Example 1: Update the specified script</span></span>

<span data-ttu-id="7ae36-113">この例では、インストールされているスクリプトを更新し、更新後のバージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="7ae36-113">This example updates an installed script and displays the updated version.</span></span>

```powershell
Update-Script -Name UpdateManagement-Template -RequiredVersion 1.1
Get-InstalledScript -Name UpdateManagement-Template
```

```Output
Version   Name                       Repository   Description
-------   ----                       ----------   -----------
1.1       UpdateManagement-Template  PSGallery    This is a template script for Update Management...
```

<span data-ttu-id="7ae36-114">`Update-Script`**Name** パラメーターを使用して、更新するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7ae36-114">`Update-Script` uses the **Name** parameter to specify the script to update.</span></span> <span data-ttu-id="7ae36-115">**RequiredVersion** パラメーターには、スクリプトのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="7ae36-115">The **RequiredVersion** parameter specifies the script version.</span></span> <span data-ttu-id="7ae36-116">`Get-InstalledScript` スクリプトの更新バージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="7ae36-116">`Get-InstalledScript` displays the updated version of the script.</span></span>

## <span data-ttu-id="7ae36-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7ae36-117">PARAMETERS</span></span>

### <span data-ttu-id="7ae36-118">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="7ae36-118">-AcceptLicense</span></span>

<span data-ttu-id="7ae36-119">パッケージで必要な場合は、インストール中にライセンス契約に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="7ae36-119">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="7ae36-120">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="7ae36-120">-AllowPrerelease</span></span>

<span data-ttu-id="7ae36-121">プレリリースとしてマークされた新しいスクリプトでスクリプトを更新できます。</span><span class="sxs-lookup"><span data-stu-id="7ae36-121">Allows you to update a script with the newer script marked as a prerelease.</span></span>

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

### <span data-ttu-id="7ae36-122">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7ae36-122">-Confirm</span></span>

<span data-ttu-id="7ae36-123">実行前に確認メッセージを表示 `Update-Script` します。</span><span class="sxs-lookup"><span data-stu-id="7ae36-123">Prompts you for confirmation before running `Update-Script`.</span></span>

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

### <span data-ttu-id="7ae36-124">-Credential</span><span class="sxs-lookup"><span data-stu-id="7ae36-124">-Credential</span></span>

<span data-ttu-id="7ae36-125">スクリプトを更新するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="7ae36-125">Specifies a user account that has permission to update a script.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7ae36-126">-Force</span><span class="sxs-lookup"><span data-stu-id="7ae36-126">-Force</span></span>

<span data-ttu-id="7ae36-127">`Update-Script`ユーザーの確認を求めることなく強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="7ae36-127">Forces `Update-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="7ae36-128">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="7ae36-128">-MaximumVersion</span></span>

<span data-ttu-id="7ae36-129">更新するスクリプトの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="7ae36-129">Specifies the maximum, or newest, version of the script to update.</span></span> <span data-ttu-id="7ae36-130">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7ae36-130">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="7ae36-131">-Name</span><span class="sxs-lookup"><span data-stu-id="7ae36-131">-Name</span></span>

<span data-ttu-id="7ae36-132">更新する1つのスクリプト名またはスクリプト名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ae36-132">Specifies one script name or an array of script names to update.</span></span>

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

### <span data-ttu-id="7ae36-133">-PassThru</span><span class="sxs-lookup"><span data-stu-id="7ae36-133">-PassThru</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7ae36-134">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="7ae36-134">-Proxy</span></span>

<span data-ttu-id="7ae36-135">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="7ae36-135">Specifies a proxy server for the request rather than connecting directly to an internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7ae36-136">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="7ae36-136">-ProxyCredential</span></span>

<span data-ttu-id="7ae36-137">**プロキシ** パラメーターによって指定されたプロキシサーバーを使用する権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="7ae36-137">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7ae36-138">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="7ae36-138">-RequiredVersion</span></span>

<span data-ttu-id="7ae36-139">更新するスクリプトの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ae36-139">Specifies the exact version number of the script to update.</span></span> <span data-ttu-id="7ae36-140">**MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7ae36-140">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="7ae36-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7ae36-141">-WhatIf</span></span>

<span data-ttu-id="7ae36-142">が実行された場合に何が起こるか `Update-Script` を示します。</span><span class="sxs-lookup"><span data-stu-id="7ae36-142">Shows what would happen if `Update-Script` runs.</span></span> <span data-ttu-id="7ae36-143">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="7ae36-143">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="7ae36-144">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7ae36-144">CommonParameters</span></span>

<span data-ttu-id="7ae36-145">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7ae36-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7ae36-146">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ae36-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7ae36-147">入力</span><span class="sxs-lookup"><span data-stu-id="7ae36-147">INPUTS</span></span>

## <span data-ttu-id="7ae36-148">出力</span><span class="sxs-lookup"><span data-stu-id="7ae36-148">OUTPUTS</span></span>

## <span data-ttu-id="7ae36-149">注</span><span class="sxs-lookup"><span data-stu-id="7ae36-149">NOTES</span></span>

## <span data-ttu-id="7ae36-150">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7ae36-150">RELATED LINKS</span></span>

[<span data-ttu-id="7ae36-151">Find-Script</span><span class="sxs-lookup"><span data-stu-id="7ae36-151">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="7ae36-152">Install-Script</span><span class="sxs-lookup"><span data-stu-id="7ae36-152">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="7ae36-153">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="7ae36-153">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="7ae36-154">Save-Script</span><span class="sxs-lookup"><span data-stu-id="7ae36-154">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="7ae36-155">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="7ae36-155">Uninstall-Script</span></span>](Uninstall-Script.md)
