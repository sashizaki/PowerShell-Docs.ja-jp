---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/unregister-packagesource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PackageSource
ms.openlocfilehash: 06a4649d0d2f0912807219f25e60d85ba22564b0
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210139"
---
# <span data-ttu-id="cc71f-103">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="cc71f-103">Unregister-PackageSource</span></span>

## <span data-ttu-id="cc71f-104">概要</span><span class="sxs-lookup"><span data-stu-id="cc71f-104">SYNOPSIS</span></span>
<span data-ttu-id="cc71f-105">登録されているパッケージソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-105">Removes a registered package source.</span></span>

## <span data-ttu-id="cc71f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cc71f-106">SYNTAX</span></span>

### <span data-ttu-id="cc71f-107">SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="cc71f-107">SourceBySearch</span></span>

```
Unregister-PackageSource [[-Source] <String>] [-Location <String>] [-Credential <PSCredential>]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="cc71f-108">SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="cc71f-108">SourceByInputObject</span></span>

```
Unregister-PackageSource -InputObject <PackageSource[]> [-Credential <PSCredential>] [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cc71f-109">NuGet: SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="cc71f-109">NuGet:SourceByInputObject</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="cc71f-110">NuGet: SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="cc71f-110">NuGet:SourceBySearch</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="cc71f-111">PowerShellGet: SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="cc71f-111">PowerShellGet:SourceByInputObject</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### <span data-ttu-id="cc71f-112">PowerShellGet: SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="cc71f-112">PowerShellGet:SourceBySearch</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="cc71f-113">Description</span><span class="sxs-lookup"><span data-stu-id="cc71f-113">DESCRIPTION</span></span>

<span data-ttu-id="cc71f-114">コマンドレットでは、 `Unregister-PackageSource` 登録されているパッケージソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-114">The `Unregister-PackageSource` cmdlet removes a registered package source.</span></span> <span data-ttu-id="cc71f-115">パッケージソースは、常にパッケージプロバイダーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="cc71f-115">Package sources are always managed by a package provider.</span></span> <span data-ttu-id="cc71f-116">パッケージソースを検索するには、コマンドレットを使用し `Get-PackageSource` ます。</span><span class="sxs-lookup"><span data-stu-id="cc71f-116">To find package sources, use the `Get-PackageSource` cmdlet.</span></span>

## <span data-ttu-id="cc71f-117">例</span><span class="sxs-lookup"><span data-stu-id="cc71f-117">EXAMPLES</span></span>

### <span data-ttu-id="cc71f-118">例 1: Nuget プロバイダーのパッケージソースの登録を解除する</span><span class="sxs-lookup"><span data-stu-id="cc71f-118">Example 1: Unregister a package source for the Nuget provider</span></span>

<span data-ttu-id="cc71f-119">`Unregister-PackageSource`コマンドレットは、ローカルコンピューターからパッケージソースの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-119">The `Unregister-PackageSource` cmdlet unregisters a package source from the local computer.</span></span> <span data-ttu-id="cc71f-120">**場所** と **プロバイダー** のパラメーターを使用して、削除するソースをさらに指定できます。</span><span class="sxs-lookup"><span data-stu-id="cc71f-120">The **Location** and **Provider** parameters can be used to further specify the source to remove.</span></span>

```
PS> Unregister-PackageSource -Source MyNuGet
```

<span data-ttu-id="cc71f-121">`Unregister-PackageSource`コマンドレットでは、 **source** パラメーターを使用して、削除するソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-121">The `Unregister-PackageSource` cmdlet uses the **Source** parameter to specify which source to remove.</span></span>

### <span data-ttu-id="cc71f-122">例 2: Register-packagesource オブジェクトを使用してパッケージの登録を解除する</span><span class="sxs-lookup"><span data-stu-id="cc71f-122">Example 2: Use a PackageSource object to unregister a package</span></span>

<span data-ttu-id="cc71f-123">この例では、およびを使用し `Get-PackageSource` て、 `Unregister-PackageSource` パッケージソースの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-123">This example uses the `Get-PackageSource` and `Unregister-PackageSource` to unregister a package source.</span></span> <span data-ttu-id="cc71f-124">**Register-packagesource** オブジェクトは変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="cc71f-124">The **PackageSource** object is stored in a variable.</span></span>

```
PS> $pkgsource = Get-PackageSource -Name MyNuGet
PS> Unregister-PackageSource -InputObject $pkgsource
```

<span data-ttu-id="cc71f-125">変数は、 `$pkgsource` コマンドレットによって作成された **register-packagesource** を格納し `Get-PackageSource` ます。</span><span class="sxs-lookup"><span data-stu-id="cc71f-125">The `$pkgsource` variable stores the **PackageSource** created by the `Get-PackageSource` cmdlet.</span></span>
<span data-ttu-id="cc71f-126">`Unregister-PackageSource``$pkgsource` **InputObject** パラメーターへの入力としてを使用します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-126">`Unregister-PackageSource` uses the `$pkgsource` as input to the **InputObject** parameter.</span></span>

<span data-ttu-id="cc71f-127">別の方法として、 `Unregister-PackageSource` コマンドレットで **InputObject** パラメーターの値を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="cc71f-127">As an alternative, the `Unregister-PackageSource` cmdlet can specify a value for the **InputObject** parameter:</span></span>

`Unregister-PackageSource -InputObject ( Get-PackageSource -Name MyNuGet )`

## <span data-ttu-id="cc71f-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cc71f-128">PARAMETERS</span></span>

### <span data-ttu-id="cc71f-129">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="cc71f-129">-ConfigFile</span></span>

<span data-ttu-id="cc71f-130">構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-130">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="cc71f-131">-Credential</span><span class="sxs-lookup"><span data-stu-id="cc71f-131">-Credential</span></span>

<span data-ttu-id="cc71f-132">コンピューターにアクセスしてコマンドを実行するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-132">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="cc71f-133">コマンドレットによって生成されたユーザー名 ( **User01** 、 **domain01\user01」** など) を入力するか、 **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="cc71f-133">Type a user name, such as **User01** , **Domain01\User01** , or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="cc71f-134">ユーザー名を入力すると、パスワードの入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc71f-134">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="cc71f-135">**Credential** パラメーターが指定されていない場合は、現在のユーザーアカウントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="cc71f-135">When the **Credential** parameter isn't specified, the current user account is used.</span></span>

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

### <span data-ttu-id="cc71f-136">-Force</span><span class="sxs-lookup"><span data-stu-id="cc71f-136">-Force</span></span>

<span data-ttu-id="cc71f-137">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-137">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="cc71f-138">は、セキュリティを除いて、が成功するのを妨げる制限をオーバーライドし `Unregister-PackageSource` ます。</span><span class="sxs-lookup"><span data-stu-id="cc71f-138">Overrides restrictions that prevent `Unregister-PackageSource` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="cc71f-139">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="cc71f-139">-ForceBootstrap</span></span>

<span data-ttu-id="cc71f-140">が、 `Unregister-PackageSource` 指定 **PackageManagement** されたパッケージソースのパッケージプロバイダーを自動的にアンインストールすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-140">Indicates that `Unregister-PackageSource` forces **PackageManagement** to automatically uninstall the package provider for the specified package source.</span></span>

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

### <span data-ttu-id="cc71f-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="cc71f-141">-InputObject</span></span>

<span data-ttu-id="cc71f-142">コマンドレットから **register-packagesource** オブジェクトを指定するパイプラインの入力を受け入れ `Get-PackageSource` ます。</span><span class="sxs-lookup"><span data-stu-id="cc71f-142">Accepts pipeline input that specifies the **PackageSource** object from the `Get-PackageSource` cmdlet.</span></span> <span data-ttu-id="cc71f-143">**InputObject** は、 **register-packagesource** オブジェクトを `Get-PackageSource` 値またはオブジェクトを含む変数として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="cc71f-143">**InputObject** accepts the **PackageSource** object as a `Get-PackageSource` value or a variable that contains the object.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.PackageSource[]
Parameter Sets: SourceByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="cc71f-144">-Location</span><span class="sxs-lookup"><span data-stu-id="cc71f-144">-Location</span></span>

<span data-ttu-id="cc71f-145">パッケージソースが参照する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-145">Specifies the location to which a package source points.</span></span> <span data-ttu-id="cc71f-146">このパラメーターの値には、URI、ファイルパス、またはパッケージプロバイダーでサポートされているその他の変換先の形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc71f-146">The value of this parameter can be a URI, a file path, or any other destination format that is supported by the package provider.</span></span>

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

### <span data-ttu-id="cc71f-147">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="cc71f-147">-PackageManagementProvider</span></span>

<span data-ttu-id="cc71f-148">**PackageManagement** プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-148">Specifies the **PackageManagement** provider.</span></span>

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

### <span data-ttu-id="cc71f-149">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="cc71f-149">-ProviderName</span></span>

<span data-ttu-id="cc71f-150">プロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-150">Specifies the provider name.</span></span>

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

### <span data-ttu-id="cc71f-151">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="cc71f-151">-PublishLocation</span></span>

<span data-ttu-id="cc71f-152">発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-152">Specifies the publish location.</span></span>

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

### <span data-ttu-id="cc71f-153">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="cc71f-153">-ScriptPublishLocation</span></span>

<span data-ttu-id="cc71f-154">スクリプトの発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-154">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="cc71f-155">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="cc71f-155">-ScriptSourceLocation</span></span>

<span data-ttu-id="cc71f-156">スクリプトのソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-156">Specifies the script source location.</span></span>

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

### <span data-ttu-id="cc71f-157">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="cc71f-157">-SkipValidate</span></span>

<span data-ttu-id="cc71f-158">パッケージソースの資格情報の検証をスキップするスイッチ。</span><span class="sxs-lookup"><span data-stu-id="cc71f-158">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="cc71f-159">-Source</span><span class="sxs-lookup"><span data-stu-id="cc71f-159">-Source</span></span>

<span data-ttu-id="cc71f-160">パッケージソースのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-160">Specifies the friendly name of the package source.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cc71f-161">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cc71f-161">-Confirm</span></span>

<span data-ttu-id="cc71f-162">を実行する前に確認メッセージを表示 `Unregister-PackageSource` します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-162">Prompts you for confirmation before `Unregister-PackageSource` is run.</span></span>

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

### <span data-ttu-id="cc71f-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cc71f-163">-WhatIf</span></span>

<span data-ttu-id="cc71f-164">コマンドレットが実行された場合に何が起こるか `Unregister-PackageSource` を示します。</span><span class="sxs-lookup"><span data-stu-id="cc71f-164">Shows what would happen if `Unregister-PackageSource` cmdlet is run.</span></span> <span data-ttu-id="cc71f-165">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="cc71f-165">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="cc71f-166">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="cc71f-166">CommonParameters</span></span>

<span data-ttu-id="cc71f-167">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="cc71f-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cc71f-168">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc71f-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cc71f-169">入力</span><span class="sxs-lookup"><span data-stu-id="cc71f-169">INPUTS</span></span>

### <span data-ttu-id="cc71f-170">`Unregister-PackageSource` パイプラインからの **register-packagesource** オブジェクトを入力として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="cc71f-170">`Unregister-PackageSource` accepts **PackageSource** objects from the pipeline as input.</span></span>

## <span data-ttu-id="cc71f-171">出力</span><span class="sxs-lookup"><span data-stu-id="cc71f-171">OUTPUTS</span></span>

### <span data-ttu-id="cc71f-172">`Unregister-PackageSource` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="cc71f-172">`Unregister-PackageSource` doesn't generate any output.</span></span>

## <span data-ttu-id="cc71f-173">注</span><span class="sxs-lookup"><span data-stu-id="cc71f-173">NOTES</span></span>

<span data-ttu-id="cc71f-174">コマンドにパッケージプロバイダーを含めると、コマンドレットで動的パラメーターを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="cc71f-174">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="cc71f-175">動的パラメーターは、パッケージプロバイダーに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="cc71f-175">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="cc71f-176">コマンドレットにより、 `Get-Help` コマンドレットのパラメーターセットが一覧表示され、プロバイダーのパラメーターセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cc71f-176">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span>

## <span data-ttu-id="cc71f-177">関連リンク</span><span class="sxs-lookup"><span data-stu-id="cc71f-177">RELATED LINKS</span></span>

[<span data-ttu-id="cc71f-178">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="cc71f-178">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="cc71f-179">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="cc71f-179">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="cc71f-180">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="cc71f-180">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="cc71f-181">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="cc71f-181">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="cc71f-182">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="cc71f-182">Set-PackageSource</span></span>](Set-PackageSource.md)
