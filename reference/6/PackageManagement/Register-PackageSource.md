---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 04/01/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/register-packagesource?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PackageSource
ms.openlocfilehash: 2509945258d0a5ae1c32580f4d24850b93ad350e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214819"
---
# <span data-ttu-id="5f837-103">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5f837-103">Register-PackageSource</span></span>

## <span data-ttu-id="5f837-104">概要</span><span class="sxs-lookup"><span data-stu-id="5f837-104">SYNOPSIS</span></span>
<span data-ttu-id="5f837-105">指定したパッケージプロバイダーのパッケージソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="5f837-105">Adds a package source for a specified package provider.</span></span>

## <span data-ttu-id="5f837-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5f837-106">SYNTAX</span></span>

### <span data-ttu-id="5f837-107">SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="5f837-107">SourceBySearch</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="5f837-108">NuGet</span><span class="sxs-lookup"><span data-stu-id="5f837-108">NuGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="5f837-109">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="5f837-109">PowerShellGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="5f837-110">Description</span><span class="sxs-lookup"><span data-stu-id="5f837-110">DESCRIPTION</span></span>

<span data-ttu-id="5f837-111">コマンドレットでは、 `Register-PackageSource` 指定したパッケージプロバイダーのパッケージソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="5f837-111">The `Register-PackageSource` cmdlet adds a package source for a specified package provider.</span></span> <span data-ttu-id="5f837-112">パッケージソースは、常にパッケージプロバイダーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="5f837-112">Package sources are always managed by a package provider.</span></span> <span data-ttu-id="5f837-113">パッケージプロバイダーがパッケージソースを追加または置換できない場合は、プロバイダーによってエラーメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5f837-113">If the package provider cannot add or replace a package source, the provider generates an error message.</span></span>

## <span data-ttu-id="5f837-114">例</span><span class="sxs-lookup"><span data-stu-id="5f837-114">EXAMPLES</span></span>

### <span data-ttu-id="5f837-115">例 1: NuGet プロバイダーにパッケージソースを登録する</span><span class="sxs-lookup"><span data-stu-id="5f837-115">Example 1: Register a package source for the NuGet provider</span></span>

<span data-ttu-id="5f837-116">このコマンドは、 **NuGet** プロバイダーの web ベースの場所であるパッケージソースを登録します。</span><span class="sxs-lookup"><span data-stu-id="5f837-116">This command registers a package source, a web-based location for the **NuGet** provider.</span></span> <span data-ttu-id="5f837-117">既定では、ソースは信頼されていません。</span><span class="sxs-lookup"><span data-stu-id="5f837-117">By default, sources aren't trusted.</span></span> <span data-ttu-id="5f837-118">パッケージをインストールする前に、ソースが信頼されていることを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f837-118">You are prompted to confirm the source is trusted before packages are installed.</span></span> <span data-ttu-id="5f837-119">既定値をオーバーライドするには、パラメーターを使用し `-Trusted` ます。</span><span class="sxs-lookup"><span data-stu-id="5f837-119">To override the default, use the `-Trusted` parameter.</span></span>

```powershell
Register-PackageSource -Name MyNuGet -Location https://www.nuget.org/api/v2 -ProviderName NuGet
```

```Output
Name          ProviderName     IsTrusted  Location
----          ------------     ---------  --------
MyNuGet       NuGet            False      https://www.nuget.org/api/v2
```

## <span data-ttu-id="5f837-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5f837-120">PARAMETERS</span></span>

### <span data-ttu-id="5f837-121">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="5f837-121">-ConfigFile</span></span>

<span data-ttu-id="5f837-122">構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="5f837-122">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="5f837-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="5f837-123">-Credential</span></span>

<span data-ttu-id="5f837-124">認証された場所にアクセスするためのアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="5f837-124">Specifies a user account that has permission to access the authenticated location.</span></span>

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

### <span data-ttu-id="5f837-125">-Force</span><span class="sxs-lookup"><span data-stu-id="5f837-125">-Force</span></span>

<span data-ttu-id="5f837-126">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5f837-126">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="5f837-127">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="5f837-127">-ForceBootstrap</span></span>

<span data-ttu-id="5f837-128">このコマンドレットによってパッケージプロバイダーが自動的にインストールされることを示します。</span><span class="sxs-lookup"><span data-stu-id="5f837-128">Indicates that this cmdlet automatically installs the package provider.</span></span>

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

### <span data-ttu-id="5f837-129">-Location</span><span class="sxs-lookup"><span data-stu-id="5f837-129">-Location</span></span>

<span data-ttu-id="5f837-130">パッケージソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f837-130">Specifies the package source location.</span></span>

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

### <span data-ttu-id="5f837-131">-Name</span><span class="sxs-lookup"><span data-stu-id="5f837-131">-Name</span></span>

<span data-ttu-id="5f837-132">登録するパッケージソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f837-132">Specifies the name of the package source to register.</span></span>

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

### <span data-ttu-id="5f837-133">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="5f837-133">-PackageManagementProvider</span></span>

<span data-ttu-id="5f837-134">Package Management プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="5f837-134">Specifies the Package Management provider.</span></span>

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

### <span data-ttu-id="5f837-135">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="5f837-135">-ProviderName</span></span>

<span data-ttu-id="5f837-136">パッケージプロバイダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f837-136">Specifies the package provider's name.</span></span>

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

### <span data-ttu-id="5f837-137">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="5f837-137">-Proxy</span></span>

<span data-ttu-id="5f837-138">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="5f837-138">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="5f837-139">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="5f837-139">-ProxyCredential</span></span>

<span data-ttu-id="5f837-140">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="5f837-140">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="5f837-141">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="5f837-141">-PublishLocation</span></span>

<span data-ttu-id="5f837-142">発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f837-142">Specifies the publish location.</span></span>

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

### <span data-ttu-id="5f837-143">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="5f837-143">-ScriptPublishLocation</span></span>

<span data-ttu-id="5f837-144">スクリプトの発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f837-144">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="5f837-145">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="5f837-145">-ScriptSourceLocation</span></span>

<span data-ttu-id="5f837-146">スクリプトのソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f837-146">Specifies the script source location.</span></span>

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

### <span data-ttu-id="5f837-147">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="5f837-147">-SkipValidate</span></span>

<span data-ttu-id="5f837-148">パッケージソースの資格情報の検証をスキップするスイッチ。</span><span class="sxs-lookup"><span data-stu-id="5f837-148">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="5f837-149">-Trusted</span><span class="sxs-lookup"><span data-stu-id="5f837-149">-Trusted</span></span>

<span data-ttu-id="5f837-150">パッケージソースが信頼されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="5f837-150">Indicates that the package source is trusted.</span></span>

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

### <span data-ttu-id="5f837-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5f837-151">-Confirm</span></span>

<span data-ttu-id="5f837-152">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f837-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5f837-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5f837-153">-WhatIf</span></span>

<span data-ttu-id="5f837-154">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="5f837-154">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="5f837-155">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="5f837-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5f837-156">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5f837-156">CommonParameters</span></span>

<span data-ttu-id="5f837-157">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5f837-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5f837-158">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f837-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5f837-159">入力</span><span class="sxs-lookup"><span data-stu-id="5f837-159">INPUTS</span></span>

## <span data-ttu-id="5f837-160">出力</span><span class="sxs-lookup"><span data-stu-id="5f837-160">OUTPUTS</span></span>

## <span data-ttu-id="5f837-161">注</span><span class="sxs-lookup"><span data-stu-id="5f837-161">NOTES</span></span>

## <span data-ttu-id="5f837-162">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5f837-162">RELATED LINKS</span></span>

[<span data-ttu-id="5f837-163">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="5f837-163">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="5f837-164">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5f837-164">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="5f837-165">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5f837-165">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="5f837-166">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5f837-166">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)