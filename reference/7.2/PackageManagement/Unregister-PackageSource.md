---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/unregister-packagesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PackageSource
ms.openlocfilehash: 6ef89e9143fe8883bc98723d10775bf739fe72f9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601798"
---
# <span data-ttu-id="35acd-102">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="35acd-102">Unregister-PackageSource</span></span>

## <span data-ttu-id="35acd-103">概要</span><span class="sxs-lookup"><span data-stu-id="35acd-103">SYNOPSIS</span></span>
<span data-ttu-id="35acd-104">登録されているパッケージソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="35acd-104">Removes a registered package source.</span></span>

## <span data-ttu-id="35acd-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="35acd-105">SYNTAX</span></span>

### <span data-ttu-id="35acd-106">SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="35acd-106">SourceBySearch</span></span>

```
Unregister-PackageSource [[-Source] <String>] [-Location <String>] [-Credential <PSCredential>]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="35acd-107">SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="35acd-107">SourceByInputObject</span></span>

```
Unregister-PackageSource -InputObject <PackageSource[]> [-Credential <PSCredential>] [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="35acd-108">NuGet: SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="35acd-108">NuGet:SourceByInputObject</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="35acd-109">NuGet: SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="35acd-109">NuGet:SourceBySearch</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="35acd-110">PowerShellGet: SourceByInputObject</span><span class="sxs-lookup"><span data-stu-id="35acd-110">PowerShellGet:SourceByInputObject</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### <span data-ttu-id="35acd-111">PowerShellGet: SourceBySearch</span><span class="sxs-lookup"><span data-stu-id="35acd-111">PowerShellGet:SourceBySearch</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="35acd-112">Description</span><span class="sxs-lookup"><span data-stu-id="35acd-112">DESCRIPTION</span></span>

<span data-ttu-id="35acd-113">コマンドレットでは、 `Unregister-PackageSource` 登録されているパッケージソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="35acd-113">The `Unregister-PackageSource` cmdlet removes a registered package source.</span></span> <span data-ttu-id="35acd-114">パッケージソースは、常にパッケージプロバイダーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="35acd-114">Package sources are always managed by a package provider.</span></span> <span data-ttu-id="35acd-115">パッケージソースを検索するには、コマンドレットを使用し `Get-PackageSource` ます。</span><span class="sxs-lookup"><span data-stu-id="35acd-115">To find package sources, use the `Get-PackageSource` cmdlet.</span></span>

## <span data-ttu-id="35acd-116">例</span><span class="sxs-lookup"><span data-stu-id="35acd-116">EXAMPLES</span></span>

### <span data-ttu-id="35acd-117">例 1: Nuget プロバイダーのパッケージソースの登録を解除する</span><span class="sxs-lookup"><span data-stu-id="35acd-117">Example 1: Unregister a package source for the Nuget provider</span></span>

<span data-ttu-id="35acd-118">`Unregister-PackageSource`コマンドレットは、ローカルコンピューターからパッケージソースの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="35acd-118">The `Unregister-PackageSource` cmdlet unregisters a package source from the local computer.</span></span> <span data-ttu-id="35acd-119">**場所** と **プロバイダー** のパラメーターを使用して、削除するソースをさらに指定できます。</span><span class="sxs-lookup"><span data-stu-id="35acd-119">The **Location** and **Provider** parameters can be used to further specify the source to remove.</span></span>

```
PS> Unregister-PackageSource -Source MyNuGet
```

<span data-ttu-id="35acd-120">`Unregister-PackageSource`コマンドレットでは、 **source** パラメーターを使用して、削除するソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="35acd-120">The `Unregister-PackageSource` cmdlet uses the **Source** parameter to specify which source to remove.</span></span>

### <span data-ttu-id="35acd-121">例 2: Register-packagesource オブジェクトを使用してパッケージの登録を解除する</span><span class="sxs-lookup"><span data-stu-id="35acd-121">Example 2: Use a PackageSource object to unregister a package</span></span>

<span data-ttu-id="35acd-122">この例では、およびを使用し `Get-PackageSource` て、 `Unregister-PackageSource` パッケージソースの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="35acd-122">This example uses the `Get-PackageSource` and `Unregister-PackageSource` to unregister a package source.</span></span> <span data-ttu-id="35acd-123">**Register-packagesource** オブジェクトは変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="35acd-123">The **PackageSource** object is stored in a variable.</span></span>

```
PS> $pkgsource = Get-PackageSource -Name MyNuGet
PS> Unregister-PackageSource -InputObject $pkgsource
```

<span data-ttu-id="35acd-124">変数は、 `$pkgsource` コマンドレットによって作成された **register-packagesource** を格納し `Get-PackageSource` ます。</span><span class="sxs-lookup"><span data-stu-id="35acd-124">The `$pkgsource` variable stores the **PackageSource** created by the `Get-PackageSource` cmdlet.</span></span>
<span data-ttu-id="35acd-125">`Unregister-PackageSource``$pkgsource` **InputObject** パラメーターへの入力としてを使用します。</span><span class="sxs-lookup"><span data-stu-id="35acd-125">`Unregister-PackageSource` uses the `$pkgsource` as input to the **InputObject** parameter.</span></span>

<span data-ttu-id="35acd-126">別の方法として、 `Unregister-PackageSource` コマンドレットで **InputObject** パラメーターの値を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="35acd-126">As an alternative, the `Unregister-PackageSource` cmdlet can specify a value for the **InputObject** parameter:</span></span>

`Unregister-PackageSource -InputObject ( Get-PackageSource -Name MyNuGet )`

## <span data-ttu-id="35acd-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="35acd-127">PARAMETERS</span></span>

### <span data-ttu-id="35acd-128">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="35acd-128">-ConfigFile</span></span>

<span data-ttu-id="35acd-129">構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="35acd-129">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="35acd-130">-Credential</span><span class="sxs-lookup"><span data-stu-id="35acd-130">-Credential</span></span>

<span data-ttu-id="35acd-131">コンピューターにアクセスしてコマンドを実行するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="35acd-131">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="35acd-132">コマンドレットによって生成されたユーザー名 ( **User01**、 **domain01\user01」** など) を入力するか、 **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="35acd-132">Type a user name, such as **User01**, **Domain01\User01**, or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="35acd-133">ユーザー名を入力すると、パスワードの入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35acd-133">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="35acd-134">**Credential** パラメーターが指定されていない場合は、現在のユーザーアカウントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="35acd-134">When the **Credential** parameter isn't specified, the current user account is used.</span></span>

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

### <span data-ttu-id="35acd-135">-Force</span><span class="sxs-lookup"><span data-stu-id="35acd-135">-Force</span></span>

<span data-ttu-id="35acd-136">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="35acd-136">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="35acd-137">は、セキュリティを除いて、が成功するのを妨げる制限をオーバーライドし `Unregister-PackageSource` ます。</span><span class="sxs-lookup"><span data-stu-id="35acd-137">Overrides restrictions that prevent `Unregister-PackageSource` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="35acd-138">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="35acd-138">-ForceBootstrap</span></span>

<span data-ttu-id="35acd-139">が、 `Unregister-PackageSource` 指定されたパッケージソースのパッケージプロバイダーを自動的にアンインストールすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="35acd-139">Indicates that `Unregister-PackageSource` forces **PackageManagement** to automatically uninstall the package provider for the specified package source.</span></span>

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

### <span data-ttu-id="35acd-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="35acd-140">-InputObject</span></span>

<span data-ttu-id="35acd-141">コマンドレットから **register-packagesource** オブジェクトを指定するパイプラインの入力を受け入れ `Get-PackageSource` ます。</span><span class="sxs-lookup"><span data-stu-id="35acd-141">Accepts pipeline input that specifies the **PackageSource** object from the `Get-PackageSource` cmdlet.</span></span> <span data-ttu-id="35acd-142">**InputObject** は、 **register-packagesource** オブジェクトを `Get-PackageSource` 値またはオブジェクトを含む変数として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="35acd-142">**InputObject** accepts the **PackageSource** object as a `Get-PackageSource` value or a variable that contains the object.</span></span>

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

### <span data-ttu-id="35acd-143">-Location</span><span class="sxs-lookup"><span data-stu-id="35acd-143">-Location</span></span>

<span data-ttu-id="35acd-144">パッケージソースが参照する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="35acd-144">Specifies the location to which a package source points.</span></span> <span data-ttu-id="35acd-145">このパラメーターの値には、URI、ファイルパス、またはパッケージプロバイダーでサポートされているその他の変換先の形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="35acd-145">The value of this parameter can be a URI, a file path, or any other destination format that is supported by the package provider.</span></span>

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

### <span data-ttu-id="35acd-146">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="35acd-146">-PackageManagementProvider</span></span>

<span data-ttu-id="35acd-147">**PackageManagement** プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="35acd-147">Specifies the **PackageManagement** provider.</span></span>

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

### <span data-ttu-id="35acd-148">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="35acd-148">-ProviderName</span></span>

<span data-ttu-id="35acd-149">プロバイダー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="35acd-149">Specifies the provider name.</span></span>

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

### <span data-ttu-id="35acd-150">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="35acd-150">-PublishLocation</span></span>

<span data-ttu-id="35acd-151">発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="35acd-151">Specifies the publish location.</span></span>

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

### <span data-ttu-id="35acd-152">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="35acd-152">-ScriptPublishLocation</span></span>

<span data-ttu-id="35acd-153">スクリプトの発行場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="35acd-153">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="35acd-154">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="35acd-154">-ScriptSourceLocation</span></span>

<span data-ttu-id="35acd-155">スクリプトのソースの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="35acd-155">Specifies the script source location.</span></span>

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

### <span data-ttu-id="35acd-156">-SkipValidate</span><span class="sxs-lookup"><span data-stu-id="35acd-156">-SkipValidate</span></span>

<span data-ttu-id="35acd-157">パッケージソースの資格情報の検証をスキップするスイッチ。</span><span class="sxs-lookup"><span data-stu-id="35acd-157">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="35acd-158">-Source</span><span class="sxs-lookup"><span data-stu-id="35acd-158">-Source</span></span>

<span data-ttu-id="35acd-159">パッケージソースのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="35acd-159">Specifies the friendly name of the package source.</span></span>

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

### <span data-ttu-id="35acd-160">-Confirm</span><span class="sxs-lookup"><span data-stu-id="35acd-160">-Confirm</span></span>

<span data-ttu-id="35acd-161">を実行する前に確認メッセージを表示 `Unregister-PackageSource` します。</span><span class="sxs-lookup"><span data-stu-id="35acd-161">Prompts you for confirmation before `Unregister-PackageSource` is run.</span></span>

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

### <span data-ttu-id="35acd-162">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="35acd-162">-WhatIf</span></span>

<span data-ttu-id="35acd-163">コマンドレットが実行された場合に何が起こるか `Unregister-PackageSource` を示します。</span><span class="sxs-lookup"><span data-stu-id="35acd-163">Shows what would happen if `Unregister-PackageSource` cmdlet is run.</span></span> <span data-ttu-id="35acd-164">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="35acd-164">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="35acd-165">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="35acd-165">CommonParameters</span></span>

<span data-ttu-id="35acd-166">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="35acd-166">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="35acd-167">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35acd-167">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="35acd-168">入力</span><span class="sxs-lookup"><span data-stu-id="35acd-168">INPUTS</span></span>

### <span data-ttu-id="35acd-169">`Unregister-PackageSource` パイプラインからの **register-packagesource** オブジェクトを入力として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="35acd-169">`Unregister-PackageSource` accepts **PackageSource** objects from the pipeline as input.</span></span>

## <span data-ttu-id="35acd-170">出力</span><span class="sxs-lookup"><span data-stu-id="35acd-170">OUTPUTS</span></span>

### <span data-ttu-id="35acd-171">`Unregister-PackageSource` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="35acd-171">`Unregister-PackageSource` doesn't generate any output.</span></span>

## <span data-ttu-id="35acd-172">注</span><span class="sxs-lookup"><span data-stu-id="35acd-172">NOTES</span></span>

<span data-ttu-id="35acd-173">コマンドにパッケージプロバイダーを含めると、コマンドレットで動的パラメーターを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="35acd-173">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="35acd-174">動的パラメーターは、パッケージプロバイダーに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="35acd-174">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="35acd-175">コマンドレットにより、 `Get-Help` コマンドレットのパラメーターセットが一覧表示され、プロバイダーのパラメーターセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="35acd-175">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span>

## <span data-ttu-id="35acd-176">関連リンク</span><span class="sxs-lookup"><span data-stu-id="35acd-176">RELATED LINKS</span></span>

[<span data-ttu-id="35acd-177">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="35acd-177">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="35acd-178">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="35acd-178">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="35acd-179">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="35acd-179">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="35acd-180">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="35acd-180">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="35acd-181">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="35acd-181">Set-PackageSource</span></span>](Set-PackageSource.md)

