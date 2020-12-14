---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-script?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Script
ms.openlocfilehash: 25da03724603b0000c46ae2da69d63cdf2f36cec
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891685"
---
# <span data-ttu-id="cfb22-103">Update-Script</span><span class="sxs-lookup"><span data-stu-id="cfb22-103">Update-Script</span></span>

## <span data-ttu-id="cfb22-104">概要</span><span class="sxs-lookup"><span data-stu-id="cfb22-104">SYNOPSIS</span></span>
<span data-ttu-id="cfb22-105">スクリプトを更新します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-105">Updates a script.</span></span>

## <span data-ttu-id="cfb22-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cfb22-106">SYNTAX</span></span>

### <span data-ttu-id="cfb22-107">すべて</span><span class="sxs-lookup"><span data-stu-id="cfb22-107">All</span></span>

```
Update-Script [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cfb22-108">Description</span><span class="sxs-lookup"><span data-stu-id="cfb22-108">DESCRIPTION</span></span>

<span data-ttu-id="cfb22-109">`Update-Script`コマンドレットは、ローカルコンピューターにインストールされているスクリプトを更新します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-109">The `Update-Script` cmdlet updates a script that is installed on the local computer.</span></span> <span data-ttu-id="cfb22-110">更新されたスクリプトは、インストールされているバージョンと同じリポジトリからダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="cfb22-110">The updated script is downloaded from the same repository as the installed version.</span></span>

## <span data-ttu-id="cfb22-111">例</span><span class="sxs-lookup"><span data-stu-id="cfb22-111">EXAMPLES</span></span>

### <span data-ttu-id="cfb22-112">例 1: 指定したスクリプトを更新する</span><span class="sxs-lookup"><span data-stu-id="cfb22-112">Example 1: Update the specified script</span></span>

<span data-ttu-id="cfb22-113">この例では、インストールされているスクリプトを更新し、更新後のバージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-113">This example updates an installed script and displays the updated version.</span></span>

```powershell
Update-Script -Name UpdateManagement-Template -RequiredVersion 1.1
Get-InstalledScript -Name UpdateManagement-Template
```

```Output
Version   Name                       Repository   Description
-------   ----                       ----------   -----------
1.1       UpdateManagement-Template  PSGallery    This is a template script for Update Management...
```

<span data-ttu-id="cfb22-114">`Update-Script`**Name** パラメーターを使用して、更新するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-114">`Update-Script` uses the **Name** parameter to specify the script to update.</span></span> <span data-ttu-id="cfb22-115">**RequiredVersion** パラメーターには、スクリプトのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-115">The **RequiredVersion** parameter specifies the script version.</span></span> <span data-ttu-id="cfb22-116">`Get-InstalledScript` スクリプトの更新バージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-116">`Get-InstalledScript` displays the updated version of the script.</span></span>

## <span data-ttu-id="cfb22-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cfb22-117">PARAMETERS</span></span>

### <span data-ttu-id="cfb22-118">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="cfb22-118">-AcceptLicense</span></span>

<span data-ttu-id="cfb22-119">パッケージで必要な場合は、インストール中にライセンス契約に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-119">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="cfb22-120">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="cfb22-120">-AllowPrerelease</span></span>

<span data-ttu-id="cfb22-121">プレリリースとしてマークされた新しいスクリプトでスクリプトを更新できます。</span><span class="sxs-lookup"><span data-stu-id="cfb22-121">Allows you to update a script with the newer script marked as a prerelease.</span></span>

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

### <span data-ttu-id="cfb22-122">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cfb22-122">-Confirm</span></span>

<span data-ttu-id="cfb22-123">実行前に確認メッセージを表示 `Update-Script` します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-123">Prompts you for confirmation before running `Update-Script`.</span></span>

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

### <span data-ttu-id="cfb22-124">-Credential</span><span class="sxs-lookup"><span data-stu-id="cfb22-124">-Credential</span></span>

<span data-ttu-id="cfb22-125">スクリプトを更新するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-125">Specifies a user account that has permission to update a script.</span></span>

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

### <span data-ttu-id="cfb22-126">-Force</span><span class="sxs-lookup"><span data-stu-id="cfb22-126">-Force</span></span>

<span data-ttu-id="cfb22-127">`Update-Script`ユーザーの確認を求めることなく強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-127">Forces `Update-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="cfb22-128">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="cfb22-128">-MaximumVersion</span></span>

<span data-ttu-id="cfb22-129">更新するスクリプトの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-129">Specifies the maximum, or newest, version of the script to update.</span></span> <span data-ttu-id="cfb22-130">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="cfb22-130">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="cfb22-131">-Name</span><span class="sxs-lookup"><span data-stu-id="cfb22-131">-Name</span></span>

<span data-ttu-id="cfb22-132">更新する1つのスクリプト名またはスクリプト名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-132">Specifies one script name or an array of script names to update.</span></span>

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

### <span data-ttu-id="cfb22-133">-PassThru</span><span class="sxs-lookup"><span data-stu-id="cfb22-133">-PassThru</span></span>

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

### <span data-ttu-id="cfb22-134">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="cfb22-134">-Proxy</span></span>

<span data-ttu-id="cfb22-135">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-135">Specifies a proxy server for the request rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="cfb22-136">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="cfb22-136">-ProxyCredential</span></span>

<span data-ttu-id="cfb22-137">**プロキシ** パラメーターによって指定されたプロキシサーバーを使用する権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-137">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="cfb22-138">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="cfb22-138">-RequiredVersion</span></span>

<span data-ttu-id="cfb22-139">更新するスクリプトの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-139">Specifies the exact version number of the script to update.</span></span> <span data-ttu-id="cfb22-140">**MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="cfb22-140">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="cfb22-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cfb22-141">-WhatIf</span></span>

<span data-ttu-id="cfb22-142">が実行された場合に何が起こるか `Update-Script` を示します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-142">Shows what would happen if `Update-Script` runs.</span></span> <span data-ttu-id="cfb22-143">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="cfb22-143">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="cfb22-144">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="cfb22-144">CommonParameters</span></span>

<span data-ttu-id="cfb22-145">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="cfb22-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cfb22-146">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfb22-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cfb22-147">入力</span><span class="sxs-lookup"><span data-stu-id="cfb22-147">INPUTS</span></span>

### <span data-ttu-id="cfb22-148">System.String[]</span><span class="sxs-lookup"><span data-stu-id="cfb22-148">System.String[]</span></span>

### <span data-ttu-id="cfb22-149">System.String</span><span class="sxs-lookup"><span data-stu-id="cfb22-149">System.String</span></span>

### <span data-ttu-id="cfb22-150">System.Uri</span><span class="sxs-lookup"><span data-stu-id="cfb22-150">System.Uri</span></span>

### <span data-ttu-id="cfb22-151">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="cfb22-151">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="cfb22-152">出力</span><span class="sxs-lookup"><span data-stu-id="cfb22-152">OUTPUTS</span></span>

### <span data-ttu-id="cfb22-153">System.Object</span><span class="sxs-lookup"><span data-stu-id="cfb22-153">System.Object</span></span>

## <span data-ttu-id="cfb22-154">注</span><span class="sxs-lookup"><span data-stu-id="cfb22-154">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cfb22-155">2020年4月の時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン1.0 と1.1 がサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="cfb22-155">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="cfb22-156">TLS 1.2 以降を使用していない場合は、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-156">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="cfb22-157">次のコマンドを使用して、TLS 1.2 を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cfb22-157">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="cfb22-158">詳細については、PowerShell ブログの [お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfb22-158">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="cfb22-159">関連リンク</span><span class="sxs-lookup"><span data-stu-id="cfb22-159">RELATED LINKS</span></span>

[<span data-ttu-id="cfb22-160">Find-Script</span><span class="sxs-lookup"><span data-stu-id="cfb22-160">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="cfb22-161">Install-Script</span><span class="sxs-lookup"><span data-stu-id="cfb22-161">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="cfb22-162">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="cfb22-162">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="cfb22-163">Save-Script</span><span class="sxs-lookup"><span data-stu-id="cfb22-163">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="cfb22-164">アンインストール-スクリプト</span><span class="sxs-lookup"><span data-stu-id="cfb22-164">Uninstall-Script</span></span>](Uninstall-Script.md)

