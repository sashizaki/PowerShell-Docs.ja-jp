---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 04/01/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/register-packagesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PackageSource
ms.openlocfilehash: 76b3bd49f81f42cc80f4127f4b549acddcd1d906
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99600406"
---
# <span data-ttu-id="21fc8-102">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="21fc8-102">Register-PackageSource</span></span>

## <span data-ttu-id="21fc8-103">概要</span><span class="sxs-lookup"><span data-stu-id="21fc8-103">SYNOPSIS</span></span>
<span data-ttu-id="21fc8-104">指定したパッケージプロバイダーのパッケージソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-104">Adds a package source for a specified package provider.</span></span>

## <span data-ttu-id="21fc8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="21fc8-105">SYNTAX</span></span>

### <span data-ttu-id="21fc8-106">SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="21fc8-106">SourceBySearch</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="21fc8-107">NuGet</span><span class="sxs-lookup"><span data-stu-id="21fc8-107">NuGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="21fc8-108">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="21fc8-108">PowerShellGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="21fc8-109">Description</span><span class="sxs-lookup"><span data-stu-id="21fc8-109">DESCRIPTION</span></span>

<span data-ttu-id="21fc8-110">コマンドレットでは、 `Register-PackageSource` 指定したパッケージプロバイダーのパッケージソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-110">The `Register-PackageSource` cmdlet adds a package source for a specified package provider.</span></span> <span data-ttu-id="21fc8-111">パッケージソースは、常にパッケージプロバイダーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="21fc8-111">Package sources are always managed by a package provider.</span></span> <span data-ttu-id="21fc8-112">パッケージプロバイダーがパッケージソースを追加または置換できない場合は、プロバイダーによってエラーメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="21fc8-112">If the package provider cannot add or replace a package source, the provider generates an error message.</span></span>

## <span data-ttu-id="21fc8-113">例</span><span class="sxs-lookup"><span data-stu-id="21fc8-113">EXAMPLES</span></span>

### <span data-ttu-id="21fc8-114">例 1: NuGet プロバイダーにパッケージソースを登録する</span><span class="sxs-lookup"><span data-stu-id="21fc8-114">Example 1: Register a package source for the NuGet provider</span></span>

<span data-ttu-id="21fc8-115">このコマンドは、 **NuGet** プロバイダーの web ベースの場所であるパッケージソースを登録します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-115">This command registers a package source, a web-based location for the **NuGet** provider.</span></span> <span data-ttu-id="21fc8-116">既定では、ソースは信頼されていません。</span><span class="sxs-lookup"><span data-stu-id="21fc8-116">By default, sources aren't trusted.</span></span> <span data-ttu-id="21fc8-117">パッケージをインストールする前に、ソースが信頼されていることを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="21fc8-117">You are prompted to confirm the source is trusted before packages are installed.</span></span> <span data-ttu-id="21fc8-118">既定値をオーバーライドするには、パラメーターを使用し `-Trusted` ます。</span><span class="sxs-lookup"><span data-stu-id="21fc8-118">To override the default, use the `-Trusted` parameter.</span></span>

```powershell
Register-PackageSource -Name MyNuGet -Location https://www.nuget.org/api/v2 -ProviderName NuGet
```

```Output
Name          ProviderName     IsTrusted  Location
----          ------------     ---------  --------
MyNuGet       NuGet            False      https://www.nuget.org/api/v2
```

## <span data-ttu-id="21fc8-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="21fc8-119">PARAMETERS</span></span>

### <span data-ttu-id="21fc8-120">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="21fc8-120">-ConfigFile</span></span>

<span data-ttu-id="21fc8-121">構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-121">Specifies a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21fc8-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="21fc8-122">-Credential</span></span>

<span data-ttu-id="21fc8-123">認証された場所にアクセスするためのアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-123">Specifies a user account that has permission to access the authenticated location.</span></span>

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

### <span data-ttu-id="21fc8-124">-Force</span><span class="sxs-lookup"><span data-stu-id="21fc8-124">-Force</span></span>

<span data-ttu-id="21fc8-125">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-125">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="21fc8-126">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="21fc8-126">-ForceBootstrap</span></span>

<span data-ttu-id="21fc8-127">このコマンドレットによってパッケージプロバイダーが自動的にインストールされることを示します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-127">Indicates that this cmdlet automatically installs the package provider.</span></span>

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

### <span data-ttu-id="21fc8-128">-Location</span><span class="sxs-lookup"><span data-stu-id="21fc8-128">-Location</span></span>

<span data-ttu-id="21fc8-129">パッケージソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-129">Specifies the package source location.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21fc8-130">-Name</span><span class="sxs-lookup"><span data-stu-id="21fc8-130">-Name</span></span>

<span data-ttu-id="21fc8-131">登録するパッケージソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-131">Specifies the name of the package source to register.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21fc8-132">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="21fc8-132">-PackageManagementProvider</span></span>

<span data-ttu-id="21fc8-133">Package Management プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-133">Specifies the Package Management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21fc8-134">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="21fc8-134">-ProviderName</span></span>

<span data-ttu-id="21fc8-135">パッケージプロバイダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-135">Specifies the package provider's name.</span></span>

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

### <span data-ttu-id="21fc8-136">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="21fc8-136">-Proxy</span></span>

<span data-ttu-id="21fc8-137">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-137">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="21fc8-138">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="21fc8-138">-ProxyCredential</span></span>

<span data-ttu-id="21fc8-139">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-139">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="21fc8-140">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="21fc8-140">-PublishLocation</span></span>

<span data-ttu-id="21fc8-141">発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-141">Specifies the publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21fc8-142">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="21fc8-142">-ScriptPublishLocation</span></span>

<span data-ttu-id="21fc8-143">スクリプトの発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-143">Specifies the script publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21fc8-144">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="21fc8-144">-ScriptSourceLocation</span></span>

<span data-ttu-id="21fc8-145">スクリプトのソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-145">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21fc8-146">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="21fc8-146">-SkipValidate</span></span>

<span data-ttu-id="21fc8-147">パッケージソースの資格情報の検証をスキップするスイッチ。</span><span class="sxs-lookup"><span data-stu-id="21fc8-147">Switch that skips validating the credentials of a package source.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21fc8-148">-Trusted</span><span class="sxs-lookup"><span data-stu-id="21fc8-148">-Trusted</span></span>

<span data-ttu-id="21fc8-149">パッケージソースが信頼されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-149">Indicates that the package source is trusted.</span></span>

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

### <span data-ttu-id="21fc8-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="21fc8-150">-Confirm</span></span>

<span data-ttu-id="21fc8-151">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="21fc8-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="21fc8-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="21fc8-152">-WhatIf</span></span>

<span data-ttu-id="21fc8-153">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-153">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="21fc8-154">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="21fc8-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="21fc8-155">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="21fc8-155">CommonParameters</span></span>

<span data-ttu-id="21fc8-156">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="21fc8-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="21fc8-157">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21fc8-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="21fc8-158">入力</span><span class="sxs-lookup"><span data-stu-id="21fc8-158">INPUTS</span></span>

## <span data-ttu-id="21fc8-159">出力</span><span class="sxs-lookup"><span data-stu-id="21fc8-159">OUTPUTS</span></span>

## <span data-ttu-id="21fc8-160">注</span><span class="sxs-lookup"><span data-stu-id="21fc8-160">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21fc8-161">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="21fc8-161">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="21fc8-162">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="21fc8-162">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="21fc8-163">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="21fc8-163">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="21fc8-164">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21fc8-164">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="21fc8-165">関連リンク</span><span class="sxs-lookup"><span data-stu-id="21fc8-165">RELATED LINKS</span></span>

[<span data-ttu-id="21fc8-166">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="21fc8-166">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="21fc8-167">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="21fc8-167">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="21fc8-168">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="21fc8-168">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="21fc8-169">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="21fc8-169">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
