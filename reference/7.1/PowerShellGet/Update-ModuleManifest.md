---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/08/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-modulemanifest?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ModuleManifest
ms.openlocfilehash: f5dc6d086f609b5a3f82a035c3ac5c7433e8d236
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891702"
---
# <span data-ttu-id="48e6e-103">Update-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="48e6e-103">Update-ModuleManifest</span></span>

## <span data-ttu-id="48e6e-104">概要</span><span class="sxs-lookup"><span data-stu-id="48e6e-104">SYNOPSIS</span></span>
<span data-ttu-id="48e6e-105">モジュール マニフェスト ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-105">Updates a module manifest file.</span></span>

## <span data-ttu-id="48e6e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="48e6e-106">SYNTAX</span></span>

### <span data-ttu-id="48e6e-107">すべて</span><span class="sxs-lookup"><span data-stu-id="48e6e-107">All</span></span>

```
Update-ModuleManifest [-Path] <String> [-NestedModules <Object[]>] [-Guid <Guid>] [-Author <String>]
 [-CompanyName <String>] [-Copyright <String>] [-RootModule <String>] [-ModuleVersion <Version>]
 [-Description <String>] [-ProcessorArchitecture <ProcessorArchitecture>]
 [-CompatiblePSEditions <String[]>] [-PowerShellVersion <Version>] [-ClrVersion <Version>]
 [-DotNetFrameworkVersion <Version>] [-PowerShellHostName <String>]
 [-PowerShellHostVersion <Version>] [-RequiredModules <Object[]>] [-TypesToProcess <String[]>]
 [-FormatsToProcess <String[]>] [-ScriptsToProcess <String[]>] [-RequiredAssemblies <String[]>]
 [-FileList <String[]>] [-ModuleList <Object[]>] [-FunctionsToExport <String[]>]
 [-AliasesToExport <String[]>] [-VariablesToExport <String[]>] [-CmdletsToExport <String[]>]
 [-DscResourcesToExport <String[]>] [-PrivateData <Hashtable>] [-Tags <String[]>]
 [-ProjectUri <Uri>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ReleaseNotes <String[]>]
 [-Prerelease <String>] [-HelpInfoUri <Uri>] [-PassThru] [-DefaultCommandPrefix <String>]
 [-ExternalModuleDependencies <String[]>] [-PackageManagementProviders <String[]>]
 [-RequireLicenseAcceptance] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="48e6e-108">Description</span><span class="sxs-lookup"><span data-stu-id="48e6e-108">DESCRIPTION</span></span>

<span data-ttu-id="48e6e-109">`Update-ModuleManifest`コマンドレットでは、モジュールマニフェスト () ファイルを更新し `.psd1` ます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-109">The `Update-ModuleManifest` cmdlet updates a module manifest (`.psd1`) file.</span></span>

## <span data-ttu-id="48e6e-110">例</span><span class="sxs-lookup"><span data-stu-id="48e6e-110">EXAMPLES</span></span>

### <span data-ttu-id="48e6e-111">例 1: モジュールマニフェストを更新する</span><span class="sxs-lookup"><span data-stu-id="48e6e-111">Example 1: Update a module manifest</span></span>

<span data-ttu-id="48e6e-112">この例では、既存のモジュールマニフェストファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-112">This example updates an existing module manifest file.</span></span> <span data-ttu-id="48e6e-113">スプラッティングは、パラメーター値をに渡すために使用され `Update-ModuleManifest` ます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-113">Splatting is used to pass parameter values to `Update-ModuleManifest`.</span></span> <span data-ttu-id="48e6e-114">詳細については、「 [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48e6e-114">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

```powershell
$Parms = @{
  Path = "C:\Test\TestManifest.psd1"
  Author = "TestUser1"
  CompanyName = "Contoso Corporation"
  Copyright = "(c) 2019 Contoso Corporation. All rights reserved."
}

Update-ModuleManifest @Parms
```

<span data-ttu-id="48e6e-115">`$Parms` は、 **Path**、 **Author**、 **CompanyName**、 **Copyright** のパラメーター値を格納する記号です。</span><span class="sxs-lookup"><span data-stu-id="48e6e-115">`$Parms` is a splat that stores the parameter values for **Path**, **Author**, **CompanyName**, and **Copyright**.</span></span> <span data-ttu-id="48e6e-116">`Update-ModuleManifest` からパラメーター値を取得 `@Parms` し、モジュールマニフェスト ( **TestManifest.psd1**) を更新します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-116">`Update-ModuleManifest` gets the parameter values from `@Parms` and updates the module manifest, **TestManifest.psd1**.</span></span>

## <span data-ttu-id="48e6e-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="48e6e-117">PARAMETERS</span></span>

### <span data-ttu-id="48e6e-118">-Aseasestoexport</span><span class="sxs-lookup"><span data-stu-id="48e6e-118">-AliasesToExport</span></span>

<span data-ttu-id="48e6e-119">モジュールがエクスポートするエイリアスを指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-119">Specifies the aliases that the module exports.</span></span> <span data-ttu-id="48e6e-120">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-120">Wildcards are permitted.</span></span>

<span data-ttu-id="48e6e-121">モジュールによってエクスポートされるエイリアスを制限するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-121">Use this parameter to restrict the aliases that are exported by the module.</span></span> <span data-ttu-id="48e6e-122">この **エクスポート** では、エクスポートされたエイリアスの一覧からエイリアスを削除できますが、エイリアスを一覧に追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="48e6e-122">**AliasesToExport** can remove aliases from the list of exported aliases, but it can't add aliases to the list.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="48e6e-123">-作成者</span><span class="sxs-lookup"><span data-stu-id="48e6e-123">-Author</span></span>

<span data-ttu-id="48e6e-124">モジュールの作成者を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-124">Specifies the module author.</span></span>

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

### <span data-ttu-id="48e6e-125">-ClrVersion</span><span class="sxs-lookup"><span data-stu-id="48e6e-125">-ClrVersion</span></span>

<span data-ttu-id="48e6e-126">モジュールに必要な、Microsoft .NET Framework の共通言語ランタイム (CLR) の最低限のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-126">Specifies the minimum version of the Common Language Runtime (CLR) of the Microsoft .NET Framework that the module requires.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48e6e-127">-///エクスポート</span><span class="sxs-lookup"><span data-stu-id="48e6e-127">-CmdletsToExport</span></span>

<span data-ttu-id="48e6e-128">モジュールがエクスポートするコマンドレットを指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-128">Specifies the cmdlets that the module exports.</span></span> <span data-ttu-id="48e6e-129">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-129">Wildcards are permitted.</span></span>

<span data-ttu-id="48e6e-130">モジュールによってエクスポートされるコマンドレットを制限するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-130">Use this parameter to restrict the cmdlets that are exported by the module.</span></span> <span data-ttu-id="48e6e-131">コマンドレットを **エクスポート** すると、エクスポートしたコマンドレットの一覧からコマンドレットを削除できますが、コマンドレットを一覧に追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="48e6e-131">**CmdletsToExport** can remove cmdlets from the list of exported cmdlets, but it can't add cmdlets to the list.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="48e6e-132">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="48e6e-132">-CompanyName</span></span>

<span data-ttu-id="48e6e-133">モジュールを作成した会社またはベンダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-133">Specifies the company or vendor who created the module.</span></span>

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

### <span data-ttu-id="48e6e-134">-CompatiblePSEditions</span><span class="sxs-lookup"><span data-stu-id="48e6e-134">-CompatiblePSEditions</span></span>

<span data-ttu-id="48e6e-135">モジュールの互換性のある **PSEditions** を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-135">Specifies the compatible **PSEditions** of the module.</span></span> <span data-ttu-id="48e6e-136">**PSEdition** の詳細については、「[モジュールと互換性のある PowerShell のエディション](/powershell/scripting/gallery/concepts/module-psedition-support)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48e6e-136">For information about **PSEdition**, see [Modules with compatible PowerShell Editions](/powershell/scripting/gallery/concepts/module-psedition-support).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Desktop, Core

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48e6e-137">-Confirm</span><span class="sxs-lookup"><span data-stu-id="48e6e-137">-Confirm</span></span>

<span data-ttu-id="48e6e-138">実行前に確認メッセージを表示 `Update-ModuleManifest` します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-138">Prompts you for confirmation before running `Update-ModuleManifest`.</span></span>

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

### <span data-ttu-id="48e6e-139">-Copyright</span><span class="sxs-lookup"><span data-stu-id="48e6e-139">-Copyright</span></span>

<span data-ttu-id="48e6e-140">モジュールの著作権表記を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-140">Specifies a copyright statement for the module.</span></span>

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

### <span data-ttu-id="48e6e-141">-DefaultCommandPrefix</span><span class="sxs-lookup"><span data-stu-id="48e6e-141">-DefaultCommandPrefix</span></span>

<span data-ttu-id="48e6e-142">既定のコマンドプレフィックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-142">Specifies the default command prefix.</span></span>

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

### <span data-ttu-id="48e6e-143">-Description</span><span class="sxs-lookup"><span data-stu-id="48e6e-143">-Description</span></span>

<span data-ttu-id="48e6e-144">モジュールの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-144">Specifies a description of the module.</span></span>

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

### <span data-ttu-id="48e6e-145">-DotNetFrameworkVersion</span><span class="sxs-lookup"><span data-stu-id="48e6e-145">-DotNetFrameworkVersion</span></span>

<span data-ttu-id="48e6e-146">モジュールに必要な、Microsoft .NET Framework の最低限のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-146">Specifies the minimum version of the Microsoft .NET Framework that the module requires.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48e6e-147">-DscResourcesToExport</span><span class="sxs-lookup"><span data-stu-id="48e6e-147">-DscResourcesToExport</span></span>

<span data-ttu-id="48e6e-148">モジュールによってエクスポートされる Desired State Configuration (DSC) リソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-148">Specifies the Desired State Configuration (DSC) resources that the module exports.</span></span> <span data-ttu-id="48e6e-149">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-149">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="48e6e-150">-ExternalModuleDependencies</span><span class="sxs-lookup"><span data-stu-id="48e6e-150">-ExternalModuleDependencies</span></span>

<span data-ttu-id="48e6e-151">外部モジュールの依存関係の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-151">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="48e6e-152">-FileList</span><span class="sxs-lookup"><span data-stu-id="48e6e-152">-FileList</span></span>

<span data-ttu-id="48e6e-153">モジュールに含まれているすべての項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-153">Specifies all items that are included in the module.</span></span>

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

### <span data-ttu-id="48e6e-154">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="48e6e-154">-FormatsToProcess</span></span>

<span data-ttu-id="48e6e-155">`.ps1xml`モジュールのインポート時に実行される書式設定ファイル () を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-155">Specifies the formatting files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="48e6e-156">モジュールをインポートすると、PowerShell は `Update-FormatData` 指定されたファイルを使用してコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-156">When you import a module, PowerShell runs the `Update-FormatData` cmdlet with the specified files.</span></span>
<span data-ttu-id="48e6e-157">書式設定ファイルはスコープが設定されていないため、セッションのすべてのセッション状態に影響します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-157">Because formatting files aren't scoped, they affect all session states in the session.</span></span>

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

### <span data-ttu-id="48e6e-158">-FunctionsToExport</span><span class="sxs-lookup"><span data-stu-id="48e6e-158">-FunctionsToExport</span></span>

<span data-ttu-id="48e6e-159">モジュールがエクスポートする関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-159">Specifies the functions that the module exports.</span></span> <span data-ttu-id="48e6e-160">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-160">Wildcards are permitted.</span></span>

<span data-ttu-id="48e6e-161">モジュールによってエクスポートされる関数を制限するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-161">Use this parameter to restrict the functions that are exported by the module.</span></span> <span data-ttu-id="48e6e-162">**Functionstoexport** では、エクスポートされたエイリアスの一覧から関数を削除できますが、一覧に関数を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="48e6e-162">**FunctionsToExport** can remove functions from the list of exported aliases, but it can't add functions to the list.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="48e6e-163">-Guid</span><span class="sxs-lookup"><span data-stu-id="48e6e-163">-Guid</span></span>

<span data-ttu-id="48e6e-164">モジュールの一意の識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-164">Specifies a unique identifier for the module.</span></span> <span data-ttu-id="48e6e-165">GUID は、同じ名前のモジュールを区別するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-165">The GUID can be used to distinguish among modules with the same name.</span></span>

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48e6e-166">-HelpInfoUri</span><span class="sxs-lookup"><span data-stu-id="48e6e-166">-HelpInfoUri</span></span>

<span data-ttu-id="48e6e-167">モジュールの **HELPINFO XML** ファイルのインターネットアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-167">Specifies the internet address of the module's **HelpInfo XML** file.</span></span> <span data-ttu-id="48e6e-168">**Http** または **https** で始まる Uniform Resource Identifier (URI) を入力します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-168">Enter a Uniform Resource Identifier (URI) that begins with **http** or **https**.</span></span>

<span data-ttu-id="48e6e-169">**HELPINFO XML** ファイルは、PowerShell バージョン3.0 で導入された更新可能なヘルプ機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="48e6e-169">The **HelpInfo XML** file supports the Updatable Help feature that was introduced in PowerShell version 3.0.</span></span> <span data-ttu-id="48e6e-170">これには、モジュールのダウンロード可能なヘルプファイルの場所、およびサポートされている各ロケールの最新のヘルプファイルのバージョン番号に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-170">It contains information about the location of the module's downloadable help files and the version numbers of the newest help files for each supported locale.</span></span>

<span data-ttu-id="48e6e-171">更新可能なヘルプの詳細については、「 [about_Updatable_Help](../Microsoft.PowerShell.Core/About/about_Updatable_Help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48e6e-171">For information about Updatable Help, see [about_Updatable_Help](../Microsoft.PowerShell.Core/About/about_Updatable_Help.md).</span></span>
<span data-ttu-id="48e6e-172">**HELPINFO XML** ファイルの詳細については、「[更新可能なヘルプのサポート](/powershell/scripting/developer/module/supporting-updatable-help)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48e6e-172">For information about the **HelpInfo XML** file, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

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

### <span data-ttu-id="48e6e-173">-IconUri</span><span class="sxs-lookup"><span data-stu-id="48e6e-173">-IconUri</span></span>

<span data-ttu-id="48e6e-174">モジュールのアイコンの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-174">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="48e6e-175">指定されたアイコンは、モジュールのギャラリー web ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-175">The specified icon is displayed on the gallery web page for the module.</span></span>

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

### <span data-ttu-id="48e6e-176">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="48e6e-176">-LicenseUri</span></span>

<span data-ttu-id="48e6e-177">モジュールのライセンス条項の URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-177">Specifies the URL of licensing terms for the module.</span></span>

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

### <span data-ttu-id="48e6e-178">-ModuleList</span><span class="sxs-lookup"><span data-stu-id="48e6e-178">-ModuleList</span></span>

<span data-ttu-id="48e6e-179">モジュールに含まれるモジュールの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-179">Specifies an array of modules that are included in the module.</span></span>

<span data-ttu-id="48e6e-180">各モジュールの名前を文字列として、または **ModuleName**　キーと **ModuleVersion** キーを含むハッシュ テーブルとして入力します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-180">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="48e6e-181">ハッシュ テーブルは、オプションの **GUID** キーも保持できます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-181">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="48e6e-182">パラメーター値として文字列とハッシュ テーブルを組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-182">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="48e6e-183">このキーは、モジュール インベントリとしての動作を想定して設計されています。</span><span class="sxs-lookup"><span data-stu-id="48e6e-183">This key is designed to act as a module inventory.</span></span> <span data-ttu-id="48e6e-184">このキーの値に示されているモジュールは自動的に処理されません。</span><span class="sxs-lookup"><span data-stu-id="48e6e-184">The modules that are listed in the value of this key aren't automatically processed.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48e6e-185">-ModuleVersion</span><span class="sxs-lookup"><span data-stu-id="48e6e-185">-ModuleVersion</span></span>

<span data-ttu-id="48e6e-186">モジュールのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-186">Specifies the version of the module.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48e6e-187">-NestedModules</span><span class="sxs-lookup"><span data-stu-id="48e6e-187">-NestedModules</span></span>

<span data-ttu-id="48e6e-188">`.psm1` `.dll` モジュールのセッション状態にインポートされるスクリプトモジュール () とバイナリモジュール () を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-188">Specifies script modules (`.psm1`) and binary modules (`.dll`) that are imported into the module's session state.</span></span> <span data-ttu-id="48e6e-189">**Nestedmodules** キー内のファイルは、値に示されている順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-189">The files in the **NestedModules** key run in the order in which they're listed in the value.</span></span>

<span data-ttu-id="48e6e-190">各モジュールの名前を文字列として、または **ModuleName**　キーと **ModuleVersion** キーを含むハッシュ テーブルとして入力します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-190">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="48e6e-191">ハッシュ テーブルは、オプションの **GUID** キーも保持できます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-191">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="48e6e-192">パラメーター値として文字列とハッシュ テーブルを組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-192">You can combine strings and hash tables in the parameter value.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48e6e-193">-PackageManagementProviders</span><span class="sxs-lookup"><span data-stu-id="48e6e-193">-PackageManagementProviders</span></span>

<span data-ttu-id="48e6e-194">パッケージ管理プロバイダーの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-194">Specifies an array of package management providers.</span></span>

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

### <span data-ttu-id="48e6e-195">-PassThru</span><span class="sxs-lookup"><span data-stu-id="48e6e-195">-PassThru</span></span>

<span data-ttu-id="48e6e-196">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-196">Returns an object representing the item with which you're working.</span></span> <span data-ttu-id="48e6e-197">既定では、は `Update-ModuleManifest` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="48e6e-197">By default, `Update-ModuleManifest` doesn't generate any output.</span></span>

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

### <span data-ttu-id="48e6e-198">-Path</span><span class="sxs-lookup"><span data-stu-id="48e6e-198">-Path</span></span>

<span data-ttu-id="48e6e-199">モジュールマニフェストのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-199">Specifies the path and file name of the module manifest.</span></span> <span data-ttu-id="48e6e-200">ファイル名拡張子の付いたパスとファイル名を入力し `.psd1` ます。たとえば、のように `$PSHOME\Modules\MyModule\MyModule.psd1` なります。</span><span class="sxs-lookup"><span data-stu-id="48e6e-200">Enter a path and file name with a `.psd1` file name extension, such as `$PSHOME\Modules\MyModule\MyModule.psd1`.</span></span>

<span data-ttu-id="48e6e-201">既存のファイルへのパスを指定すると、ファイルに `Update-ModuleManifest` 読み取り専用属性が含まれていない限り、は警告なしでファイルを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-201">If you specify the path to an existing file, `Update-ModuleManifest` replaces the file without warning unless the file has the read-only attribute.</span></span>

<span data-ttu-id="48e6e-202">マニフェストはモジュールのディレクトリに配置する必要があります。マニフェストファイル名はモジュールディレクトリ名と同じである必要がありますが、 `.psd1` 拡張子はです。</span><span class="sxs-lookup"><span data-stu-id="48e6e-202">The manifest should be located in the module's directory, and the manifest file name should be the same as the module directory name, but with a `.psd1` extension.</span></span>

<span data-ttu-id="48e6e-203">`$PSHOME` `$HOME` **パス** パラメーター値のプロンプトに応答して、やなどの変数を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="48e6e-203">You can't use variables, such as `$PSHOME` or `$HOME`, in response to a prompt for a **Path** parameter value.</span></span> <span data-ttu-id="48e6e-204">変数を使用するには、コマンドに **Path** パラメーターを含めます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-204">To use a variable, include the **Path** parameter in the command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="48e6e-205">-PowerShellHostName</span><span class="sxs-lookup"><span data-stu-id="48e6e-205">-PowerShellHostName</span></span>

<span data-ttu-id="48e6e-206">モジュールに必要な PowerShell ホストプログラムの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-206">Specifies the name of the PowerShell host program that the module requires.</span></span> <span data-ttu-id="48e6e-207">PowerShell ISE Host や ConsoleHost などのホストプログラムの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-207">Enter the name of the host program, such as PowerShell ISE Host or ConsoleHost.</span></span> <span data-ttu-id="48e6e-208">ワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="48e6e-208">Wildcards aren't permitted.</span></span>

<span data-ttu-id="48e6e-209">ホストプログラムの名前を検索するには、プログラムで「」と入力 `$Host.Name` します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-209">To find the name of a host program, in the program, type `$Host.Name`.</span></span>

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

### <span data-ttu-id="48e6e-210">-PowerShellHostVersion</span><span class="sxs-lookup"><span data-stu-id="48e6e-210">-PowerShellHostVersion</span></span>

<span data-ttu-id="48e6e-211">モジュールで動作する PowerShell ホストプログラムの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-211">Specifies the minimum version of the PowerShell host program that works with the module.</span></span> <span data-ttu-id="48e6e-212">1.1 などのバージョン番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-212">Enter a version number, such as 1.1.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48e6e-213">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="48e6e-213">-PowerShellVersion</span></span>

<span data-ttu-id="48e6e-214">このモジュールで動作する PowerShell の最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-214">Specifies the minimum version of PowerShell that will work with this module.</span></span> <span data-ttu-id="48e6e-215">たとえば、このパラメーターの値として3.0、4.0、または5.0 を指定できます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-215">For example, you can specify 3.0, 4.0, or 5.0 as the value of this parameter.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48e6e-216">-プレリリース</span><span class="sxs-lookup"><span data-stu-id="48e6e-216">-Prerelease</span></span>

<span data-ttu-id="48e6e-217">モジュールがプレリリースであることを示します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-217">Indicates the module is prerelease.</span></span>

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

### <span data-ttu-id="48e6e-218">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="48e6e-218">-PrivateData</span></span>

<span data-ttu-id="48e6e-219">インポート時にモジュールに渡されるデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-219">Specifies data that is passed to the module when it's imported.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48e6e-220">-ProcessorArchitecture</span><span class="sxs-lookup"><span data-stu-id="48e6e-220">-ProcessorArchitecture</span></span>

<span data-ttu-id="48e6e-221">モジュールに必要なプロセッサ アーキテクチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-221">Specifies the processor architecture that the module requires.</span></span>

<span data-ttu-id="48e6e-222">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="48e6e-222">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="48e6e-223">Amd64</span><span class="sxs-lookup"><span data-stu-id="48e6e-223">Amd64</span></span>
- <span data-ttu-id="48e6e-224">Arm</span><span class="sxs-lookup"><span data-stu-id="48e6e-224">Arm</span></span>
- <span data-ttu-id="48e6e-225">IA64</span><span class="sxs-lookup"><span data-stu-id="48e6e-225">IA64</span></span>
- <span data-ttu-id="48e6e-226">MSIL</span><span class="sxs-lookup"><span data-stu-id="48e6e-226">MSIL</span></span>
- <span data-ttu-id="48e6e-227">なし (不明または未指定)</span><span class="sxs-lookup"><span data-stu-id="48e6e-227">None (unknown or unspecified)</span></span>
- <span data-ttu-id="48e6e-228">X86</span><span class="sxs-lookup"><span data-stu-id="48e6e-228">X86</span></span>

```yaml
Type: System.Reflection.ProcessorArchitecture
Parameter Sets: (All)
Aliases:
Accepted values: None, MSIL, X86, IA64, Amd64, Arm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48e6e-229">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="48e6e-229">-ProjectUri</span></span>

<span data-ttu-id="48e6e-230">このプロジェクトについての web ページの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-230">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="48e6e-231">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="48e6e-231">-ReleaseNotes</span></span>

<span data-ttu-id="48e6e-232">このバージョンのスクリプトで使用するリリースノートまたはコメントを格納する文字列配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-232">Specifies a string array that contains release notes or comments that you want available for this version of the script.</span></span>

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

### <span data-ttu-id="48e6e-233">-RequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="48e6e-233">-RequireLicenseAcceptance</span></span>

<span data-ttu-id="48e6e-234">モジュールにライセンスへの同意が必要であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-234">Specifies that a license acceptance is required for the module.</span></span>

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

### <span data-ttu-id="48e6e-235">-RequiredAssemblies</span><span class="sxs-lookup"><span data-stu-id="48e6e-235">-RequiredAssemblies</span></span>

<span data-ttu-id="48e6e-236">モジュールに必要なアセンブリ () ファイルを指定し `.dll` ます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-236">Specifies the assembly (`.dll`) files that the module requires.</span></span> <span data-ttu-id="48e6e-237">アセンブリ ファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-237">Enter the assembly file names.</span></span>
<span data-ttu-id="48e6e-238">PowerShell は、型または形式を更新する前、入れ子になったモジュールをインポートする前、または **RootModule** キーの値に指定されているモジュールファイルをインポートする前に、指定されたアセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-238">PowerShell loads the specified assemblies before updating types or formats, importing nested modules, or importing the module file that is specified in the value of the **RootModule** key.</span></span>

<span data-ttu-id="48e6e-239">このパラメーターを使用して、モジュールが必要とするすべてのアセンブリを指定します。これらのアセンブリが **nestedmodules** キーにバイナリモジュールとして表示されている場合でも、 **Formatstoprocess** または **TypesToProcess** キーに一覧表示されているフォーマットファイルまたは型ファイルを更新するために読み込む必要があるアセンブリも含まれます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-239">Use this parameter to specify all the assemblies that the module requires, including assemblies that must be loaded to update any formatting or type files that are listed in the **FormatsToProcess** or **TypesToProcess** keys, even if those assemblies are also listed as binary modules in the **NestedModules** key.</span></span>

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

### <span data-ttu-id="48e6e-240">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="48e6e-240">-RequiredModules</span></span>

<span data-ttu-id="48e6e-241">グローバル セッション状態にする必要があるモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-241">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="48e6e-242">必要なモジュールがグローバルセッション状態でない場合は、PowerShell によってインポートされます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-242">If the required modules aren't in the global session state, PowerShell imports them.</span></span> <span data-ttu-id="48e6e-243">必要なモジュールが使用できない場合、 `Import-Module` コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-243">If the required modules aren't available, the `Import-Module` command fails.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48e6e-244">-RootModule</span><span class="sxs-lookup"><span data-stu-id="48e6e-244">-RootModule</span></span>

<span data-ttu-id="48e6e-245">モジュールのプライマリファイルまたはルートファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-245">Specifies the primary or root file of the module.</span></span> <span data-ttu-id="48e6e-246">スクリプト ( `.ps1` )、スクリプトモジュール ( `.psm1` )、モジュールマニフェスト ( `.psd1` )、アセンブリ ( `.dll` )、コマンドレット定義 XML ファイル ()、 `.cdxml` またはワークフロー ( `.xaml` ) のファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-246">Enter the file name of a script (`.ps1`), a script module (`.psm1`), a module manifest (`.psd1`), an assembly (`.dll`), a cmdlet definition XML file (`.cdxml`), or a workflow (`.xaml`).</span></span> <span data-ttu-id="48e6e-247">モジュールのインポート時に、ルート モジュール ファイルからエクスポートされるメンバーは、呼び出し元のセッション状態にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-247">When the module is imported, the members that are exported from the root module file are imported into the caller's session state.</span></span>

<span data-ttu-id="48e6e-248">モジュールにマニフェストファイルがあり、 **RootModule** キーでルートファイルが指定されていない場合、マニフェストはモジュールのプライマリファイルになります。</span><span class="sxs-lookup"><span data-stu-id="48e6e-248">If a module has a manifest file and no root file has been specified in the **RootModule** key, the manifest becomes the primary file for the module.</span></span> <span data-ttu-id="48e6e-249">また、モジュールはマニフェストモジュール (ModuleType = Manifest) になります。</span><span class="sxs-lookup"><span data-stu-id="48e6e-249">And, the module becomes a manifest module (ModuleType = Manifest).</span></span>

<span data-ttu-id="48e6e-250">マニフェストを持つモジュール内のまたはファイルからメンバーをエクスポートするに `.psm1` は、 `.dll` マニフェスト内の **RootModule** または **nestedmodules** キーの値でこれらのファイルの名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48e6e-250">To export members from `.psm1` or `.dll` files in a module that has a manifest, the names of those files must be specified in the values of the **RootModule** or **NestedModules** keys in the manifest.</span></span> <span data-ttu-id="48e6e-251">それ以外の場合、メンバーはエクスポートされません。</span><span class="sxs-lookup"><span data-stu-id="48e6e-251">Otherwise, their members aren't exported.</span></span>

<span data-ttu-id="48e6e-252">PowerShell 2.0 では、このキーは **ModuleToProcess** と呼ばれていました。</span><span class="sxs-lookup"><span data-stu-id="48e6e-252">In PowerShell 2.0, this key was called **ModuleToProcess**.</span></span>

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

### <span data-ttu-id="48e6e-253">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="48e6e-253">-ScriptsToProcess</span></span>

<span data-ttu-id="48e6e-254">`.ps1`モジュールをインポートするときに、呼び出し元のセッション状態で実行されるスクリプト () ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-254">Specifies script (`.ps1`) files that run in the caller's session state when the module is imported.</span></span>
<span data-ttu-id="48e6e-255">ログイン スクリプトを使用する場合と同様に、これらのスクリプトを使用して、環境を準備できます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-255">You can use these scripts to prepare an environment, just as you might use a login script.</span></span>

<span data-ttu-id="48e6e-256">モジュールのセッション状態で実行するスクリプトを指定するには、**NestedModules** キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-256">To specify scripts that run in the module's session state, use the **NestedModules** key.</span></span>

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

### <span data-ttu-id="48e6e-257">-タグ</span><span class="sxs-lookup"><span data-stu-id="48e6e-257">-Tags</span></span>

<span data-ttu-id="48e6e-258">タグの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-258">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="48e6e-259">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="48e6e-259">-TypesToProcess</span></span>

<span data-ttu-id="48e6e-260">`.ps1xml`モジュールをインポートするときに実行される型ファイル () を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-260">Specifies the type files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="48e6e-261">モジュールをインポートすると、PowerShell は `Update-TypeData` 指定されたファイルを使用してコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-261">When you import the module, PowerShell runs the `Update-TypeData` cmdlet with the specified files.</span></span>
<span data-ttu-id="48e6e-262">型ファイルはスコープが設定されていないため、セッションのすべてのセッション状態に影響します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-262">Because type files aren't scoped, they affect all session states in the session.</span></span>

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

### <span data-ttu-id="48e6e-263">-変数 Stoexport</span><span class="sxs-lookup"><span data-stu-id="48e6e-263">-VariablesToExport</span></span>

<span data-ttu-id="48e6e-264">モジュールがエクスポートする変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-264">Specifies the variables that the module exports.</span></span> <span data-ttu-id="48e6e-265">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="48e6e-265">Wildcards are permitted.</span></span>

<span data-ttu-id="48e6e-266">モジュールによってエクスポートされる変数を制限するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-266">Use this parameter to restrict the variables that are exported by the module.</span></span> <span data-ttu-id="48e6e-267">Variables **Stoexport** では、エクスポートされた変数の一覧から変数を削除できますが、変数を一覧に追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="48e6e-267">**VariablesToExport** can remove variables from the list of exported variables, but it can't add variables to the list.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="48e6e-268">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="48e6e-268">-WhatIf</span></span>

<span data-ttu-id="48e6e-269">が実行された場合に何が起こるか `Update-ModuleManifest` を示します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-269">Shows what would happen if `Update-ModuleManifest` runs.</span></span> <span data-ttu-id="48e6e-270">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="48e6e-270">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="48e6e-271">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="48e6e-271">CommonParameters</span></span>

<span data-ttu-id="48e6e-272">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="48e6e-272">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="48e6e-273">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48e6e-273">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="48e6e-274">入力</span><span class="sxs-lookup"><span data-stu-id="48e6e-274">INPUTS</span></span>

### <span data-ttu-id="48e6e-275">System.String</span><span class="sxs-lookup"><span data-stu-id="48e6e-275">System.String</span></span>

## <span data-ttu-id="48e6e-276">出力</span><span class="sxs-lookup"><span data-stu-id="48e6e-276">OUTPUTS</span></span>

### <span data-ttu-id="48e6e-277">System.Object</span><span class="sxs-lookup"><span data-stu-id="48e6e-277">System.Object</span></span>

## <span data-ttu-id="48e6e-278">注</span><span class="sxs-lookup"><span data-stu-id="48e6e-278">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48e6e-279">2020年4月の時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン1.0 と1.1 がサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="48e6e-279">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="48e6e-280">TLS 1.2 以降を使用していない場合は、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-280">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="48e6e-281">次のコマンドを使用して、TLS 1.2 を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="48e6e-281">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="48e6e-282">詳細については、PowerShell ブログの [お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48e6e-282">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="48e6e-283">関連リンク</span><span class="sxs-lookup"><span data-stu-id="48e6e-283">RELATED LINKS</span></span>
