---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-module?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Module
ms.openlocfilehash: f167990361a332f3b6f696d934e5d2835de849ed
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892622"
---
# <span data-ttu-id="c06ea-103">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="c06ea-103">Publish-Module</span></span>

## <span data-ttu-id="c06ea-104">概要</span><span class="sxs-lookup"><span data-stu-id="c06ea-104">SYNOPSIS</span></span>
<span data-ttu-id="c06ea-105">指定したモジュールをローカル コンピューターからオンライン ギャラリーに発行します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-105">Publishes a specified module from the local computer to an online gallery.</span></span>

## <span data-ttu-id="c06ea-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c06ea-106">SYNTAX</span></span>

### <span data-ttu-id="c06ea-107">ModuleNameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="c06ea-107">ModuleNameParameterSet (Default)</span></span>

```
Publish-Module -Name <String> [-RequiredVersion <String>] [-NuGetApiKey <String>]
 [-Repository <String>] [-Credential <PSCredential>] [-FormatVersion <Version>]
 [-ReleaseNotes <String[]>] [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>]
 [-ProjectUri <Uri>] [-Exclude <String[]>] [-Force] [-AllowPrerelease] [-SkipAutomaticTags]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c06ea-108">ModulePathParameterSet</span><span class="sxs-lookup"><span data-stu-id="c06ea-108">ModulePathParameterSet</span></span>

```
Publish-Module -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-FormatVersion <Version>] [-ReleaseNotes <String[]>]
 [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ProjectUri <Uri>] [-Force]
 [-SkipAutomaticTags] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c06ea-109">Description</span><span class="sxs-lookup"><span data-stu-id="c06ea-109">DESCRIPTION</span></span>

<span data-ttu-id="c06ea-110">`Publish-Module`コマンドレットは、ギャラリーにユーザーのプロファイルの一部として格納されている API キーを使用して、モジュールをオンラインの NuGet ベースのギャラリーに発行します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-110">The `Publish-Module` cmdlet publishes a module to an online NuGet-based gallery by using an API key, stored as part of a user's profile in the gallery.</span></span> <span data-ttu-id="c06ea-111">モジュールの名前、またはモジュールを含むフォルダーへのパスのいずれかでモジュールを発行するように指定できます。</span><span class="sxs-lookup"><span data-stu-id="c06ea-111">You can specify the module to publish either by the module's name, or by the path to the folder containing the module.</span></span>

<span data-ttu-id="c06ea-112">モジュールを名前で指定すると、は、を `Publish-Module` 実行して検出される最初のモジュールを発行し `Get-Module -ListAvailable <Name>` ます。</span><span class="sxs-lookup"><span data-stu-id="c06ea-112">When you specify a module by name, `Publish-Module` publishes the first module that would be found by running `Get-Module -ListAvailable <Name>`.</span></span> <span data-ttu-id="c06ea-113">発行するモジュールの最小バージョンを指定すると、は、指定した最小バージョン以上のバージョンを `Publish-Module` 持つ最初のモジュールを発行します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-113">If you specify a minimum version of a module to publish, `Publish-Module` publishes the first module with a version that is greater than or equal to the minimum version that you have specified.</span></span>

<span data-ttu-id="c06ea-114">モジュールを発行するには、モジュールのギャラリー ページに表示されるメタデータが必要です。</span><span class="sxs-lookup"><span data-stu-id="c06ea-114">Publishing a module requires metadata that is displayed on the gallery page for the module.</span></span> <span data-ttu-id="c06ea-115">必要なメタデータには、モジュールの名前、バージョン、説明、作成者が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c06ea-115">Required metadata includes the module name, version, description, and author.</span></span> <span data-ttu-id="c06ea-116">ほとんどのメタデータはモジュールマニフェストから取得されますが、一部のメタデータは、 `Publish-Module` **Tag**、 **ReleaseNote**、 **IconUri**、 **ProjectUri**、 **LicenseUri** などのパラメーターで指定する必要があります。これらのパラメーターは、NuGet ベースのギャラリーのフィールドと一致するためです。</span><span class="sxs-lookup"><span data-stu-id="c06ea-116">Although most metadata is taken from the module manifest, some metadata must be specified in `Publish-Module` parameters, such as **Tag**, **ReleaseNote**, **IconUri**, **ProjectUri**, and **LicenseUri**, because these parameters match fields in a NuGet-based gallery.</span></span>

## <span data-ttu-id="c06ea-117">例</span><span class="sxs-lookup"><span data-stu-id="c06ea-117">EXAMPLES</span></span>

### <span data-ttu-id="c06ea-118">例 1: モジュールを公開する</span><span class="sxs-lookup"><span data-stu-id="c06ea-118">Example 1: Publish a module</span></span>

<span data-ttu-id="c06ea-119">この例では、API キーを使用して、モジュール所有者のオンラインギャラリーアカウントを示すことによって、MyDscModule がオンラインギャラリーに発行されます。</span><span class="sxs-lookup"><span data-stu-id="c06ea-119">In this example, MyDscModule is published to the online gallery by using the API key to indicate the module owner's online gallery account.</span></span> <span data-ttu-id="c06ea-120">MyDscModule が、名前、バージョン、説明、および作成者を指定する有効なマニフェストモジュールでない場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-120">If MyDscModule is not a valid manifest module that specifies a name, version, description, and author, an error occurs.</span></span>

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73"
```

### <span data-ttu-id="c06ea-121">例 2: ギャラリーメタデータを使用してモジュールを公開する</span><span class="sxs-lookup"><span data-stu-id="c06ea-121">Example 2: Publish a module with gallery metadata</span></span>

<span data-ttu-id="c06ea-122">この例では、API キーを使用して、モジュール所有者のギャラリーアカウントを示すことで、MyDscModule がオンラインギャラリーに発行されます。</span><span class="sxs-lookup"><span data-stu-id="c06ea-122">In this example, MyDscModule is published to the online gallery by using the API key to indicate the module owner's gallery account.</span></span> <span data-ttu-id="c06ea-123">提供された追加のメタデータは、ギャラリー内のモジュールの web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c06ea-123">The additional metadata provided is displayed on the webpage for the module in the gallery.</span></span> <span data-ttu-id="c06ea-124">所有者は、モジュールに対して2つの検索タグを追加し、それを Active Directory に関連付けます。簡単なリリースノートが追加されます。</span><span class="sxs-lookup"><span data-stu-id="c06ea-124">The owner adds two search tags for the module, relating it to Active Directory; a brief release note is added.</span></span> <span data-ttu-id="c06ea-125">MyDscModule が、名前、バージョン、説明、および作成者を指定する有効なマニフェストモジュールでない場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-125">If MyDscModule is not a valid manifest module that specifies a name, version, description, and author, an error occurs.</span></span>

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73" -LicenseUri "http://contoso.com/license" -Tag "Active Directory","DSC" -ReleaseNote "Updated the ActiveDirectory DSC Resources to support adding users."
```

## <span data-ttu-id="c06ea-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c06ea-126">PARAMETERS</span></span>

### <span data-ttu-id="c06ea-127">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="c06ea-127">-AllowPrerelease</span></span>

<span data-ttu-id="c06ea-128">プレリリースとしてマークされているモジュールを公開できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c06ea-128">Allows modules marked as prerelease to be published.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c06ea-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c06ea-129">-Confirm</span></span>

<span data-ttu-id="c06ea-130">を実行する前に確認メッセージを表示し `Publish-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="c06ea-130">Prompts you for confirmation before running the `Publish-Module`.</span></span>

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

### <span data-ttu-id="c06ea-131">-Credential</span><span class="sxs-lookup"><span data-stu-id="c06ea-131">-Credential</span></span>

<span data-ttu-id="c06ea-132">指定したパッケージプロバイダーまたはソースのモジュールを発行する権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-132">Specifies a user account that has rights to publish a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="c06ea-133">-除外</span><span class="sxs-lookup"><span data-stu-id="c06ea-133">-Exclude</span></span>

<span data-ttu-id="c06ea-134">パブリッシュされたモジュールから除外するファイルを定義します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-134">Defines files to exclude from the published module.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c06ea-135">-Force</span><span class="sxs-lookup"><span data-stu-id="c06ea-135">-Force</span></span>

<span data-ttu-id="c06ea-136">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-136">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="c06ea-137">-FormatVersion</span><span class="sxs-lookup"><span data-stu-id="c06ea-137">-FormatVersion</span></span>

<span data-ttu-id="c06ea-138">**Validateset** 属性によって指定された有効な値のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="c06ea-138">Accepts only valid values specified by the **ValidateSet** attribute.</span></span>

<span data-ttu-id="c06ea-139">詳細については、「 [Validateset 属性の宣言](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) と [ValidateSetAttribute](/dotnet/api/system.management.automation.validatesetattribute)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c06ea-139">For more information, see [ValidateSet Attribute Declaration](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) and [ValidateSetAttribute](/dotnet/api/system.management.automation.validatesetattribute).</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:
Accepted values: 2.0

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c06ea-140">-IconUri</span><span class="sxs-lookup"><span data-stu-id="c06ea-140">-IconUri</span></span>

<span data-ttu-id="c06ea-141">モジュールのアイコンの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-141">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="c06ea-142">指定されたアイコンは、そのモジュールのギャラリー web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c06ea-142">The specified icon is displayed on the gallery webpage for the module.</span></span>

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

### <span data-ttu-id="c06ea-143">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="c06ea-143">-LicenseUri</span></span>

<span data-ttu-id="c06ea-144">発行するモジュールのライセンス条項の URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-144">Specifies the URL of licensing terms for the module you want to publish.</span></span>

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

### <span data-ttu-id="c06ea-145">-Name</span><span class="sxs-lookup"><span data-stu-id="c06ea-145">-Name</span></span>

<span data-ttu-id="c06ea-146">発行するモジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-146">Specifies the name of the module that you want to publish.</span></span> <span data-ttu-id="c06ea-147">`Publish-Module` 指定されたモジュール名をで検索 `$Env:PSModulePath` します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-147">`Publish-Module` searches for the specified module name in `$Env:PSModulePath`.</span></span>

```yaml
Type: System.String
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c06ea-148">-NuGetApiKey</span><span class="sxs-lookup"><span data-stu-id="c06ea-148">-NuGetApiKey</span></span>

<span data-ttu-id="c06ea-149">オンラインギャラリーにモジュールを発行するために使用する API キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-149">Specifies the API key that you want to use to publish a module to the online gallery.</span></span> <span data-ttu-id="c06ea-150">API キーは、オンラインギャラリーのプロファイルの一部であり、ギャラリーのユーザーアカウントページで確認できます。</span><span class="sxs-lookup"><span data-stu-id="c06ea-150">The API key is part of your profile in the online gallery, and can be found on your user account page in the gallery.</span></span> <span data-ttu-id="c06ea-151">API キーは NuGet 固有の機能です。</span><span class="sxs-lookup"><span data-stu-id="c06ea-151">The API key is NuGet-specific functionality.</span></span>

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

### <span data-ttu-id="c06ea-152">-Path</span><span class="sxs-lookup"><span data-stu-id="c06ea-152">-Path</span></span>

<span data-ttu-id="c06ea-153">発行するモジュールへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-153">Specifies the path to the module that you want to publish.</span></span> <span data-ttu-id="c06ea-154">このパラメーターは、モジュールを含むフォルダーへのパスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c06ea-154">This parameter accepts the path to the folder that contains the module.</span></span>

```yaml
Type: System.String
Parameter Sets: ModulePathParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c06ea-155">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="c06ea-155">-ProjectUri</span></span>

<span data-ttu-id="c06ea-156">このプロジェクトに関する web ページの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-156">Specifies the URL of a webpage about this project.</span></span>

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

### <span data-ttu-id="c06ea-157">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="c06ea-157">-ReleaseNotes</span></span>

<span data-ttu-id="c06ea-158">このバージョンのモジュールのユーザーが使用できるようにするリリースノートまたはコメントを含む文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-158">Specifies a string containing release notes or comments that you want to be available to users of this version of the module.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c06ea-159">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="c06ea-159">-Repository</span></span>

<span data-ttu-id="c06ea-160">を実行して登録されているリポジトリのフレンドリ名を指定し `Register-PSRepository` ます。</span><span class="sxs-lookup"><span data-stu-id="c06ea-160">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="c06ea-161">リポジトリには、有効な NuGet URI である **PublishLocation** が必要です。</span><span class="sxs-lookup"><span data-stu-id="c06ea-161">The repository must have a **PublishLocation**, which is a valid NuGet URI.</span></span>
<span data-ttu-id="c06ea-162">**PublishLocation** は、を実行して設定でき `Set-PSRepository` ます。</span><span class="sxs-lookup"><span data-stu-id="c06ea-162">The **PublishLocation** can be set by running `Set-PSRepository`.</span></span>

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

### <span data-ttu-id="c06ea-163">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="c06ea-163">-RequiredVersion</span></span>

<span data-ttu-id="c06ea-164">発行する1つのモジュールの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-164">Specifies the exact version of a single module to publish.</span></span>

```yaml
Type: System.String
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c06ea-165">-Skip自動タグ</span><span class="sxs-lookup"><span data-stu-id="c06ea-165">-SkipAutomaticTags</span></span>

<span data-ttu-id="c06ea-166">コマンドおよびリソースをタグとして含めないようにします。</span><span class="sxs-lookup"><span data-stu-id="c06ea-166">Removes commands and resources from being included as tags.</span></span> <span data-ttu-id="c06ea-167">自動的にタグをモジュールに追加しないようにします。</span><span class="sxs-lookup"><span data-stu-id="c06ea-167">Skips automatically adding tags to a module.</span></span>

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

### <span data-ttu-id="c06ea-168">-タグ</span><span class="sxs-lookup"><span data-stu-id="c06ea-168">-Tags</span></span>

<span data-ttu-id="c06ea-169">発行するモジュールに1つ以上のタグを追加します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-169">Adds one or more tags to the module that you are publishing.</span></span> <span data-ttu-id="c06ea-170">タグの例としては、DesiredStateConfiguration、DSC、DSCResourceKit、PSModule などがあります。</span><span class="sxs-lookup"><span data-stu-id="c06ea-170">Example tags include DesiredStateConfiguration, DSC, DSCResourceKit, or PSModule.</span></span> <span data-ttu-id="c06ea-171">複数のタグはコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="c06ea-171">Separate multiple tags with commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c06ea-172">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c06ea-172">-WhatIf</span></span>

<span data-ttu-id="c06ea-173">が実行された場合に何が起こるかを示し `Publish-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="c06ea-173">Shows what would happen if the `Publish-Module` runs.</span></span> <span data-ttu-id="c06ea-174">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c06ea-174">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c06ea-175">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c06ea-175">CommonParameters</span></span>

<span data-ttu-id="c06ea-176">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c06ea-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c06ea-177">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c06ea-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c06ea-178">入力</span><span class="sxs-lookup"><span data-stu-id="c06ea-178">INPUTS</span></span>

### <span data-ttu-id="c06ea-179">System.String</span><span class="sxs-lookup"><span data-stu-id="c06ea-179">System.String</span></span>

### <span data-ttu-id="c06ea-180">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="c06ea-180">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="c06ea-181">出力</span><span class="sxs-lookup"><span data-stu-id="c06ea-181">OUTPUTS</span></span>

### <span data-ttu-id="c06ea-182">System.Object</span><span class="sxs-lookup"><span data-stu-id="c06ea-182">System.Object</span></span>

## <span data-ttu-id="c06ea-183">注</span><span class="sxs-lookup"><span data-stu-id="c06ea-183">NOTES</span></span>

<span data-ttu-id="c06ea-184">`Publish-Module` powershell 3.0 以降の PowerShell で、windows 7 または Windows 2008 R2 以降のリリースの Windows で実行されます。</span><span class="sxs-lookup"><span data-stu-id="c06ea-184">`Publish-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c06ea-185">2020年4月の時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン1.0 と1.1 がサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c06ea-185">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="c06ea-186">TLS 1.2 以降を使用していない場合は、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-186">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="c06ea-187">次のコマンドを使用して、TLS 1.2 を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c06ea-187">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="c06ea-188">詳細については、PowerShell ブログの [お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c06ea-188">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

<span data-ttu-id="c06ea-189">モジュールを発行するには、モジュールのギャラリー ページに表示されるメタデータが必要です。</span><span class="sxs-lookup"><span data-stu-id="c06ea-189">Publishing a module requires metadata that is displayed on the gallery page for the module.</span></span> <span data-ttu-id="c06ea-190">必要なメタデータには、モジュールの名前、バージョン、説明、作成者が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c06ea-190">Required metadata includes the module name, version, description, and author.</span></span> <span data-ttu-id="c06ea-191">ほとんどのメタデータはモジュールマニフェストから取得されますが、一部のメタデータは、 `Publish-Module` **Tag**、 **ReleaseNote**、 **IconUri**、 **ProjectUri**、 **LicenseUri** などのパラメーターで指定できます。</span><span class="sxs-lookup"><span data-stu-id="c06ea-191">Most metadata is taken from the module manifest, but some metadata can be specified in `Publish-Module` parameters, such as **Tag**, **ReleaseNote**, **IconUri**, **ProjectUri**, and **LicenseUri**.</span></span> <span data-ttu-id="c06ea-192">詳細については、「 [POWERSHELL ギャラリー UI に影響するパッケージマニフェスト値](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c06ea-192">For more information, see [Package manifest values that impact the PowerShell Gallery UI](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui).</span></span>

## <span data-ttu-id="c06ea-193">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c06ea-193">RELATED LINKS</span></span>

[<span data-ttu-id="c06ea-194">Find-Module</span><span class="sxs-lookup"><span data-stu-id="c06ea-194">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="c06ea-195">Install-Module</span><span class="sxs-lookup"><span data-stu-id="c06ea-195">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="c06ea-196">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="c06ea-196">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="c06ea-197">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="c06ea-197">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="c06ea-198">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="c06ea-198">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="c06ea-199">Update-Module</span><span class="sxs-lookup"><span data-stu-id="c06ea-199">Update-Module</span></span>](Update-Module.md)
