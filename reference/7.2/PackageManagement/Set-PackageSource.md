---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/set-packagesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PackageSource
ms.openlocfilehash: 9f258c3b02064aafdaf272141f2613ff5cbaf5b5
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99602187"
---
# <span data-ttu-id="dcdcb-102">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="dcdcb-102">Set-PackageSource</span></span>

## <span data-ttu-id="dcdcb-103">概要</span><span class="sxs-lookup"><span data-stu-id="dcdcb-103">SYNOPSIS</span></span>
<span data-ttu-id="dcdcb-104">指定したパッケージプロバイダーのパッケージソースを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-104">Replaces a package source for a specified package provider.</span></span>

## <span data-ttu-id="dcdcb-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dcdcb-105">SYNTAX</span></span>

### <span data-ttu-id="dcdcb-106">SourceBySearch (既定)</span><span class="sxs-lookup"><span data-stu-id="dcdcb-106">SourceBySearch (Default)</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [[-Name] <String>] [-Location <String>] [-NewLocation <String>] [-NewName <String>] [-Trusted]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="dcdcb-107">SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="dcdcb-107">SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] -InputObject <PackageSource> [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="dcdcb-108">NuGet: SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="dcdcb-108">NuGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="dcdcb-109">NuGet: SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="dcdcb-109">NuGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="dcdcb-110">PowerShellGet: SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="dcdcb-110">PowerShellGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### <span data-ttu-id="dcdcb-111">PowerShellGet: SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="dcdcb-111">PowerShellGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="dcdcb-112">Description</span><span class="sxs-lookup"><span data-stu-id="dcdcb-112">DESCRIPTION</span></span>

<span data-ttu-id="dcdcb-113">は、 `Set-PackageSource` 指定されたパッケージプロバイダーのパッケージソースを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-113">The `Set-PackageSource` replaces a package source for a specified package provider.</span></span> <span data-ttu-id="dcdcb-114">パッケージソースは、常にパッケージプロバイダーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-114">Package sources are always managed by a package provider.</span></span>

## <span data-ttu-id="dcdcb-115">例</span><span class="sxs-lookup"><span data-stu-id="dcdcb-115">EXAMPLES</span></span>

### <span data-ttu-id="dcdcb-116">例 1: パッケージソースを変更する</span><span class="sxs-lookup"><span data-stu-id="dcdcb-116">Example 1: Change a package source</span></span>

<span data-ttu-id="dcdcb-117">このコマンドは、パッケージソースの既存の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-117">This command changes the existing name of a package source.</span></span> <span data-ttu-id="dcdcb-118">ソースは [ **信頼済み**] に設定されています。これにより、パッケージのインストール時にソースを確認するためのプロンプトが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-118">The source is set to **Trusted**, which eliminates prompts to verify the source when packages are installed.</span></span>

```
PS C:\> Set-PackageSource -Name MyNuget -NewName NewNuGet -Trusted -ProviderName NuGet
```

## <span data-ttu-id="dcdcb-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dcdcb-119">PARAMETERS</span></span>

### <span data-ttu-id="dcdcb-120">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="dcdcb-120">-ConfigFile</span></span>

<span data-ttu-id="dcdcb-121">構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-121">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="dcdcb-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="dcdcb-122">-Credential</span></span>

<span data-ttu-id="dcdcb-123">パッケージプロバイダーをインストールするアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-123">Specifies a user account that has permission to install package providers.</span></span>

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

### <span data-ttu-id="dcdcb-124">-Force</span><span class="sxs-lookup"><span data-stu-id="dcdcb-124">-Force</span></span>

<span data-ttu-id="dcdcb-125">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-125">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="dcdcb-126">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="dcdcb-126">-ForceBootstrap</span></span>

<span data-ttu-id="dcdcb-127">が `Set-PackageSource` **PackageManagement** を強制的にパッケージプロバイダーに自動的にインストールすることを示します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-127">Indicates that `Set-PackageSource` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="dcdcb-128">-InputObject</span><span class="sxs-lookup"><span data-stu-id="dcdcb-128">-InputObject</span></span>

<span data-ttu-id="dcdcb-129">変更するパッケージを表すパッケージソース ID オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-129">Specifies a package source ID object that represents the package that you want to change.</span></span> <span data-ttu-id="dcdcb-130">パッケージソース Id は、コマンドレットの結果の一部です `Get-PackageSource` 。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-130">Package source IDs are part of the results of the `Get-PackageSource` cmdlet.</span></span>

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

### <span data-ttu-id="dcdcb-131">-Location</span><span class="sxs-lookup"><span data-stu-id="dcdcb-131">-Location</span></span>

<span data-ttu-id="dcdcb-132">現在のパッケージソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-132">Specifies the current package source location.</span></span> <span data-ttu-id="dcdcb-133">この値には、URI、ファイルパス、またはパッケージプロバイダーでサポートされているその他の変換先の形式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-133">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

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

### <span data-ttu-id="dcdcb-134">-Name</span><span class="sxs-lookup"><span data-stu-id="dcdcb-134">-Name</span></span>

<span data-ttu-id="dcdcb-135">パッケージソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-135">Specifies a package source's name.</span></span>

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

### <span data-ttu-id="dcdcb-136">-NewLocation</span><span class="sxs-lookup"><span data-stu-id="dcdcb-136">-NewLocation</span></span>

<span data-ttu-id="dcdcb-137">パッケージソースの新しい場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-137">Specifies the new location for a package source.</span></span> <span data-ttu-id="dcdcb-138">この値には、URI、ファイルパス、またはパッケージプロバイダーでサポートされているその他の変換先の形式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-138">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

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

### <span data-ttu-id="dcdcb-139">-NewName</span><span class="sxs-lookup"><span data-stu-id="dcdcb-139">-NewName</span></span>

<span data-ttu-id="dcdcb-140">パッケージソースに割り当てる新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-140">Specifies the new name you assign to a package source.</span></span>

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

### <span data-ttu-id="dcdcb-141">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="dcdcb-141">-PackageManagementProvider</span></span>

<span data-ttu-id="dcdcb-142">パッケージ管理プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-142">Specifies a package management provider.</span></span>

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

### <span data-ttu-id="dcdcb-143">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="dcdcb-143">-ProviderName</span></span>

<span data-ttu-id="dcdcb-144">プロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-144">Specifies a provider name.</span></span>

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

### <span data-ttu-id="dcdcb-145">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="dcdcb-145">-Proxy</span></span>

<span data-ttu-id="dcdcb-146">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-146">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="dcdcb-147">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="dcdcb-147">-ProxyCredential</span></span>

<span data-ttu-id="dcdcb-148">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-148">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="dcdcb-149">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="dcdcb-149">-PublishLocation</span></span>

<span data-ttu-id="dcdcb-150">発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-150">Specifies the publish location.</span></span>

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

### <span data-ttu-id="dcdcb-151">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="dcdcb-151">-ScriptPublishLocation</span></span>

<span data-ttu-id="dcdcb-152">スクリプトの発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-152">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="dcdcb-153">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="dcdcb-153">-ScriptSourceLocation</span></span>

<span data-ttu-id="dcdcb-154">スクリプトのソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-154">Specifies the script source location.</span></span>

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

### <span data-ttu-id="dcdcb-155">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="dcdcb-155">-SkipValidate</span></span>

<span data-ttu-id="dcdcb-156">パッケージソースの資格情報の検証をスキップするスイッチ。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-156">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="dcdcb-157">-Trusted</span><span class="sxs-lookup"><span data-stu-id="dcdcb-157">-Trusted</span></span>

<span data-ttu-id="dcdcb-158">は、ソースが信頼できるパッケージプロバイダーであることを示します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-158">Indicates that the source is a trusted package provider.</span></span> <span data-ttu-id="dcdcb-159">信頼できるソースは、パッケージのインストールを確認するプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-159">Trusted sources don't prompt for verification to install packages.</span></span>

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

### <span data-ttu-id="dcdcb-160">-Confirm</span><span class="sxs-lookup"><span data-stu-id="dcdcb-160">-Confirm</span></span>

<span data-ttu-id="dcdcb-161">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-161">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="dcdcb-162">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="dcdcb-162">-WhatIf</span></span>

<span data-ttu-id="dcdcb-163">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-163">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="dcdcb-164">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-164">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="dcdcb-165">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="dcdcb-165">CommonParameters</span></span>

<span data-ttu-id="dcdcb-166">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-166">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dcdcb-167">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-167">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dcdcb-168">入力</span><span class="sxs-lookup"><span data-stu-id="dcdcb-168">INPUTS</span></span>

### <span data-ttu-id="dcdcb-169">`Set-PackageSource` パイプラインの入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-169">`Set-PackageSource` doesn't accept pipeline input.</span></span>

## <span data-ttu-id="dcdcb-170">出力</span><span class="sxs-lookup"><span data-stu-id="dcdcb-170">OUTPUTS</span></span>

### <span data-ttu-id="dcdcb-171">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-171">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="dcdcb-172">注</span><span class="sxs-lookup"><span data-stu-id="dcdcb-172">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dcdcb-173">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-173">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="dcdcb-174">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-174">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="dcdcb-175">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-175">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="dcdcb-176">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcdcb-176">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="dcdcb-177">関連リンク</span><span class="sxs-lookup"><span data-stu-id="dcdcb-177">RELATED LINKS</span></span>

[<span data-ttu-id="dcdcb-178">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="dcdcb-178">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="dcdcb-179">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="dcdcb-179">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="dcdcb-180">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="dcdcb-180">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="dcdcb-181">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="dcdcb-181">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
