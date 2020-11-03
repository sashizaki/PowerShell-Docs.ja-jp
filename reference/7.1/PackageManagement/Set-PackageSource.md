---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/set-packagesource?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PackageSource
ms.openlocfilehash: ad5384f7d708cc708991d4150bf883139007ae1b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215771"
---
# <span data-ttu-id="7023f-103">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="7023f-103">Set-PackageSource</span></span>

## <span data-ttu-id="7023f-104">概要</span><span class="sxs-lookup"><span data-stu-id="7023f-104">SYNOPSIS</span></span>
<span data-ttu-id="7023f-105">指定したパッケージプロバイダーのパッケージソースを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="7023f-105">Replaces a package source for a specified package provider.</span></span>

## <span data-ttu-id="7023f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7023f-106">SYNTAX</span></span>

### <span data-ttu-id="7023f-107">SourceBySearch (既定)</span><span class="sxs-lookup"><span data-stu-id="7023f-107">SourceBySearch (Default)</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [[-Name] <String>] [-Location <String>] [-NewLocation <String>] [-NewName <String>] [-Trusted]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="7023f-108">SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="7023f-108">SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] -InputObject <PackageSource> [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7023f-109">NuGet: SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="7023f-109">NuGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="7023f-110">NuGet: SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="7023f-110">NuGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="7023f-111">PowerShellGet: SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="7023f-111">PowerShellGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### <span data-ttu-id="7023f-112">PowerShellGet: SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="7023f-112">PowerShellGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="7023f-113">Description</span><span class="sxs-lookup"><span data-stu-id="7023f-113">DESCRIPTION</span></span>

<span data-ttu-id="7023f-114">は、 `Set-PackageSource` 指定されたパッケージプロバイダーのパッケージソースを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="7023f-114">The `Set-PackageSource` replaces a package source for a specified package provider.</span></span> <span data-ttu-id="7023f-115">パッケージソースは、常にパッケージプロバイダーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="7023f-115">Package sources are always managed by a package provider.</span></span>

## <span data-ttu-id="7023f-116">例</span><span class="sxs-lookup"><span data-stu-id="7023f-116">EXAMPLES</span></span>

### <span data-ttu-id="7023f-117">例 1: パッケージソースを変更する</span><span class="sxs-lookup"><span data-stu-id="7023f-117">Example 1: Change a package source</span></span>

<span data-ttu-id="7023f-118">このコマンドは、パッケージソースの既存の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="7023f-118">This command changes the existing name of a package source.</span></span> <span data-ttu-id="7023f-119">ソースは [ **信頼済み** ] に設定されています。これにより、パッケージのインストール時にソースを確認するためのプロンプトが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="7023f-119">The source is set to **Trusted** , which eliminates prompts to verify the source when packages are installed.</span></span>

```
PS C:\> Set-PackageSource -Name MyNuget -NewName NewNuGet -Trusted -ProviderName NuGet
```

## <span data-ttu-id="7023f-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7023f-120">PARAMETERS</span></span>

### <span data-ttu-id="7023f-121">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="7023f-121">-ConfigFile</span></span>

<span data-ttu-id="7023f-122">構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="7023f-122">Specifies a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7023f-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="7023f-123">-Credential</span></span>

<span data-ttu-id="7023f-124">パッケージプロバイダーをインストールするアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="7023f-124">Specifies a user account that has permission to install package providers.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7023f-125">-Force</span><span class="sxs-lookup"><span data-stu-id="7023f-125">-Force</span></span>

<span data-ttu-id="7023f-126">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7023f-126">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="7023f-127">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="7023f-127">-ForceBootstrap</span></span>

<span data-ttu-id="7023f-128">が `Set-PackageSource` **PackageManagement** を強制的にパッケージプロバイダーに自動的にインストールすることを示します。</span><span class="sxs-lookup"><span data-stu-id="7023f-128">Indicates that `Set-PackageSource` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="7023f-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7023f-129">-InputObject</span></span>

<span data-ttu-id="7023f-130">変更するパッケージを表すパッケージソース ID オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7023f-130">Specifies a package source ID object that represents the package that you want to change.</span></span> <span data-ttu-id="7023f-131">パッケージソース Id は、コマンドレットの結果の一部です `Get-PackageSource` 。</span><span class="sxs-lookup"><span data-stu-id="7023f-131">Package source IDs are part of the results of the `Get-PackageSource` cmdlet.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.PackageSource
Parameter Sets: SourceByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7023f-132">-Location</span><span class="sxs-lookup"><span data-stu-id="7023f-132">-Location</span></span>

<span data-ttu-id="7023f-133">現在のパッケージソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="7023f-133">Specifies the current package source location.</span></span> <span data-ttu-id="7023f-134">この値には、URI、ファイルパス、またはパッケージプロバイダーでサポートされているその他の変換先の形式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7023f-134">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7023f-135">-Name</span><span class="sxs-lookup"><span data-stu-id="7023f-135">-Name</span></span>

<span data-ttu-id="7023f-136">パッケージソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7023f-136">Specifies a package source's name.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: SourceName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7023f-137">-NewLocation</span><span class="sxs-lookup"><span data-stu-id="7023f-137">-NewLocation</span></span>

<span data-ttu-id="7023f-138">パッケージソースの新しい場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="7023f-138">Specifies the new location for a package source.</span></span> <span data-ttu-id="7023f-139">この値には、URI、ファイルパス、またはパッケージプロバイダーでサポートされているその他の変換先の形式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7023f-139">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7023f-140">-NewName</span><span class="sxs-lookup"><span data-stu-id="7023f-140">-NewName</span></span>

<span data-ttu-id="7023f-141">パッケージソースに割り当てる新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7023f-141">Specifies the new name you assign to a package source.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7023f-142">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="7023f-142">-PackageManagementProvider</span></span>

<span data-ttu-id="7023f-143">パッケージ管理プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="7023f-143">Specifies a package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7023f-144">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="7023f-144">-ProviderName</span></span>

<span data-ttu-id="7023f-145">プロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="7023f-145">Specifies a provider name.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7023f-146">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="7023f-146">-Proxy</span></span>

<span data-ttu-id="7023f-147">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="7023f-147">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7023f-148">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="7023f-148">-ProxyCredential</span></span>

<span data-ttu-id="7023f-149">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="7023f-149">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7023f-150">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="7023f-150">-PublishLocation</span></span>

<span data-ttu-id="7023f-151">発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="7023f-151">Specifies the publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7023f-152">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="7023f-152">-ScriptPublishLocation</span></span>

<span data-ttu-id="7023f-153">スクリプトの発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="7023f-153">Specifies the script publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7023f-154">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="7023f-154">-ScriptSourceLocation</span></span>

<span data-ttu-id="7023f-155">スクリプトのソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="7023f-155">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7023f-156">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="7023f-156">-SkipValidate</span></span>

<span data-ttu-id="7023f-157">パッケージソースの資格情報の検証をスキップするスイッチ。</span><span class="sxs-lookup"><span data-stu-id="7023f-157">Switch that skips validating the credentials of a package source.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7023f-158">-Trusted</span><span class="sxs-lookup"><span data-stu-id="7023f-158">-Trusted</span></span>

<span data-ttu-id="7023f-159">は、ソースが信頼できるパッケージプロバイダーであることを示します。</span><span class="sxs-lookup"><span data-stu-id="7023f-159">Indicates that the source is a trusted package provider.</span></span> <span data-ttu-id="7023f-160">信頼できるソースは、パッケージのインストールを確認するプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="7023f-160">Trusted sources don't prompt for verification to install packages.</span></span>

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

### <span data-ttu-id="7023f-161">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7023f-161">-Confirm</span></span>

<span data-ttu-id="7023f-162">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7023f-162">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7023f-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7023f-163">-WhatIf</span></span>

<span data-ttu-id="7023f-164">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="7023f-164">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="7023f-165">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="7023f-165">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7023f-166">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7023f-166">CommonParameters</span></span>

<span data-ttu-id="7023f-167">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7023f-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7023f-168">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7023f-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7023f-169">入力</span><span class="sxs-lookup"><span data-stu-id="7023f-169">INPUTS</span></span>

### <span data-ttu-id="7023f-170">`Set-PackageSource` パイプラインの入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="7023f-170">`Set-PackageSource` doesn't accept pipeline input.</span></span>

## <span data-ttu-id="7023f-171">出力</span><span class="sxs-lookup"><span data-stu-id="7023f-171">OUTPUTS</span></span>

### <span data-ttu-id="7023f-172">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="7023f-172">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7023f-173">注</span><span class="sxs-lookup"><span data-stu-id="7023f-173">NOTES</span></span>

## <span data-ttu-id="7023f-174">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7023f-174">RELATED LINKS</span></span>

[<span data-ttu-id="7023f-175">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="7023f-175">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="7023f-176">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="7023f-176">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="7023f-177">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="7023f-177">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="7023f-178">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="7023f-178">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

