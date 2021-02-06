---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-scriptfileinfo?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ScriptFileInfo
ms.openlocfilehash: de138a27ed9425057406dc6120a8354b72a3b8a3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601427"
---
# <span data-ttu-id="476a1-102">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="476a1-102">Update-ScriptFileInfo</span></span>

## <span data-ttu-id="476a1-103">概要</span><span class="sxs-lookup"><span data-stu-id="476a1-103">SYNOPSIS</span></span>
<span data-ttu-id="476a1-104">スクリプトの情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="476a1-104">Updates information for a script.</span></span>

## <span data-ttu-id="476a1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="476a1-105">SYNTAX</span></span>

### <span data-ttu-id="476a1-106">PathParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="476a1-106">PathParameterSet (Default)</span></span>

```
Update-ScriptFileInfo [-Path] <String> [-Version <String>] [-Author <String>] [-Guid <Guid>]
 [-Description <String>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="476a1-107">LiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="476a1-107">LiteralPathParameterSet</span></span>

```
Update-ScriptFileInfo [-LiteralPath] <String> [-Version <String>] [-Author <String>] [-Guid <Guid>]
 [-Description <String>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="476a1-108">Description</span><span class="sxs-lookup"><span data-stu-id="476a1-108">DESCRIPTION</span></span>

<span data-ttu-id="476a1-109">コマンドレットでは、 `Update-ScriptFileInfo` スクリプトのプロパティ値を更新します。</span><span class="sxs-lookup"><span data-stu-id="476a1-109">The `Update-ScriptFileInfo` cmdlet updates a script's property values.</span></span> <span data-ttu-id="476a1-110">たとえば、[バージョン]、[作成者]、または [説明] の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-110">For example, the values for version, author, or description.</span></span>

## <span data-ttu-id="476a1-111">例</span><span class="sxs-lookup"><span data-stu-id="476a1-111">EXAMPLES</span></span>

### <span data-ttu-id="476a1-112">例 1: スクリプトファイルのバージョンを更新する</span><span class="sxs-lookup"><span data-stu-id="476a1-112">Example 1: Update the version of a script file</span></span>

<span data-ttu-id="476a1-113">この例では、既存のスクリプトファイルが新しいプロパティ値で更新されます。</span><span class="sxs-lookup"><span data-stu-id="476a1-113">In this example, an existing script file is updated with new property values.</span></span>

<span data-ttu-id="476a1-114">スプラッティングは、コマンドレットにパラメーターを渡すために使用され `Update-ScriptFileInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="476a1-114">Splatting is used to pass parameters to the `Update-ScriptFileInfo` cmdlet.</span></span> <span data-ttu-id="476a1-115">詳細については、「 [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="476a1-115">For more information, see [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span></span>

```powershell
$Parms = @{
  Path = "C:\Test\Temp-Scriptfile.ps1"
  Version = "2.0"
  Author = "bob@contoso.com"
  CompanyName = "Contoso"
  Description = "This is the updated description"
  }
Update-ScriptFileInfo @Parms -PassThru
```

```Output
<#PSScriptInfo

.VERSION 2.0

.GUID 4609f00c-e850-4d3f-9c69-3741e56e4133

.AUTHOR bob@contoso.com

.COMPANYNAME Contoso

.COPYRIGHT

.TAGS

.LICENSEURI

.PROJECTURI

.ICONURI

.EXTERNALMODULEDEPENDENCIES

.REQUIREDSCRIPTS

.EXTERNALSCRIPTDEPENDENCIES

.RELEASENOTES

.PRIVATEDATA

#>

<#

.DESCRIPTION
This is the updated description

#>
Param()
```

<span data-ttu-id="476a1-116">`$Parms`**Path**、 **Version**、 **Author**、 **CompanyName**、および **Description** のパラメーター値を格納します。</span><span class="sxs-lookup"><span data-stu-id="476a1-116">`$Parms` stores the parameter values for **Path**, **Version**, **Author**, **CompanyName**, and **Description**.</span></span> <span data-ttu-id="476a1-117">`Update-ScriptFileInfo` からパラメーター値を取得 `@Parms` し、スクリプトを更新します。</span><span class="sxs-lookup"><span data-stu-id="476a1-117">`Update-ScriptFileInfo` gets the parameter values from `@Parms` and updates the script.</span></span> <span data-ttu-id="476a1-118">**PassThru** パラメーターは、スクリプトの内容を PowerShell コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="476a1-118">The **PassThru** parameter displays the script's contents in the PowerShell console.</span></span>

## <span data-ttu-id="476a1-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="476a1-119">PARAMETERS</span></span>

### <span data-ttu-id="476a1-120">-作成者</span><span class="sxs-lookup"><span data-stu-id="476a1-120">-Author</span></span>

<span data-ttu-id="476a1-121">スクリプトの作成者を指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-121">Specifies the script author.</span></span>

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

### <span data-ttu-id="476a1-122">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="476a1-122">-CompanyName</span></span>

<span data-ttu-id="476a1-123">スクリプトを作成した会社またはベンダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-123">Specifies the company or vendor who created the script.</span></span>

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

### <span data-ttu-id="476a1-124">-Confirm</span><span class="sxs-lookup"><span data-stu-id="476a1-124">-Confirm</span></span>

<span data-ttu-id="476a1-125">実行前に確認メッセージを表示 `Update-ScriptFileInfo` します。</span><span class="sxs-lookup"><span data-stu-id="476a1-125">Prompts you for confirmation before running `Update-ScriptFileInfo`.</span></span>

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

### <span data-ttu-id="476a1-126">-Copyright</span><span class="sxs-lookup"><span data-stu-id="476a1-126">-Copyright</span></span>

<span data-ttu-id="476a1-127">スクリプトの著作権に関する声明を指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-127">Specifies a copyright statement for the script.</span></span>

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

### <span data-ttu-id="476a1-128">-Description</span><span class="sxs-lookup"><span data-stu-id="476a1-128">-Description</span></span>

<span data-ttu-id="476a1-129">スクリプトの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-129">Specifies a description for the script.</span></span>

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

### <span data-ttu-id="476a1-130">-ExternalModuleDependencies</span><span class="sxs-lookup"><span data-stu-id="476a1-130">-ExternalModuleDependencies</span></span>

<span data-ttu-id="476a1-131">外部モジュールの依存関係の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-131">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="476a1-132">-ExternalScriptDependencies</span><span class="sxs-lookup"><span data-stu-id="476a1-132">-ExternalScriptDependencies</span></span>

<span data-ttu-id="476a1-133">外部スクリプトの依存関係の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-133">Specifies an array of external script dependencies.</span></span>

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

### <span data-ttu-id="476a1-134">-Force</span><span class="sxs-lookup"><span data-stu-id="476a1-134">-Force</span></span>

<span data-ttu-id="476a1-135">`Update-ScriptFileInfo`ユーザーの確認を求めることなく強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="476a1-135">Forces `Update-ScriptFileInfo` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="476a1-136">-Guid</span><span class="sxs-lookup"><span data-stu-id="476a1-136">-Guid</span></span>

<span data-ttu-id="476a1-137">スクリプトの一意の ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-137">Specifies a unique ID for a script.</span></span>

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

### <span data-ttu-id="476a1-138">-IconUri</span><span class="sxs-lookup"><span data-stu-id="476a1-138">-IconUri</span></span>

<span data-ttu-id="476a1-139">スクリプトのアイコンの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-139">Specifies the URL of an icon for the script.</span></span> <span data-ttu-id="476a1-140">スクリプトのギャラリー web ページに、指定したアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="476a1-140">The specified icon is displayed on the gallery web page for the script.</span></span>

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

### <span data-ttu-id="476a1-141">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="476a1-141">-LicenseUri</span></span>

<span data-ttu-id="476a1-142">ライセンス条項の URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-142">Specifies the URL of licensing terms.</span></span>

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

### <span data-ttu-id="476a1-143">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="476a1-143">-LiteralPath</span></span>

<span data-ttu-id="476a1-144">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-144">Specifies a path to one or more locations.</span></span> <span data-ttu-id="476a1-145">**LiteralPath** パラメーターの値は、入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="476a1-145">The **LiteralPath** parameter's value is used exactly as it's entered.</span></span> <span data-ttu-id="476a1-146">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="476a1-146">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="476a1-147">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="476a1-147">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="476a1-148">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="476a1-148">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPathParameterSet
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="476a1-149">-PassThru</span><span class="sxs-lookup"><span data-stu-id="476a1-149">-PassThru</span></span>

<span data-ttu-id="476a1-150">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="476a1-150">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="476a1-151">既定では、は `Update-ScriptFileInfo` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="476a1-151">By default, `Update-ScriptFileInfo` doesn't generate any output.</span></span>

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

### <span data-ttu-id="476a1-152">-Path</span><span class="sxs-lookup"><span data-stu-id="476a1-152">-Path</span></span>

<span data-ttu-id="476a1-153">スクリプトファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-153">Specifies the script file's location.</span></span> <span data-ttu-id="476a1-154">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="476a1-154">Wildcards are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: PathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="476a1-155">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="476a1-155">-PrivateData</span></span>

<span data-ttu-id="476a1-156">スクリプトのプライベートデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-156">Specifies the private data for the script.</span></span>

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

### <span data-ttu-id="476a1-157">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="476a1-157">-ProjectUri</span></span>

<span data-ttu-id="476a1-158">このプロジェクトについての web ページの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-158">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="476a1-159">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="476a1-159">-ReleaseNotes</span></span>

<span data-ttu-id="476a1-160">このバージョンのスクリプトで使用するリリースノートまたはコメントを格納する文字列配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-160">Specifies a string array that contains release notes or comments that you want available for this version of the script.</span></span>

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

### <span data-ttu-id="476a1-161">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="476a1-161">-RequiredModules</span></span>

<span data-ttu-id="476a1-162">グローバル セッション状態にする必要があるモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-162">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="476a1-163">必要なモジュールがグローバルセッション状態でない場合は、PowerShell によってインポートされます。</span><span class="sxs-lookup"><span data-stu-id="476a1-163">If the required modules aren't in the global session state, PowerShell imports them.</span></span>

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

### <span data-ttu-id="476a1-164">-RequiredScripts</span><span class="sxs-lookup"><span data-stu-id="476a1-164">-RequiredScripts</span></span>

<span data-ttu-id="476a1-165">必須のスクリプトの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-165">Specifies an array of required scripts.</span></span>

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

### <span data-ttu-id="476a1-166">-タグ</span><span class="sxs-lookup"><span data-stu-id="476a1-166">-Tags</span></span>

<span data-ttu-id="476a1-167">タグの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-167">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="476a1-168">-Version</span><span class="sxs-lookup"><span data-stu-id="476a1-168">-Version</span></span>

<span data-ttu-id="476a1-169">スクリプトのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="476a1-169">Specifies the script's version.</span></span>

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

### <span data-ttu-id="476a1-170">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="476a1-170">-WhatIf</span></span>

<span data-ttu-id="476a1-171">が実行された場合に何が起こるか `Update-ScriptFileInfo` を示します。</span><span class="sxs-lookup"><span data-stu-id="476a1-171">Shows what would happen if `Update-ScriptFileInfo` runs.</span></span> <span data-ttu-id="476a1-172">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="476a1-172">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="476a1-173">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="476a1-173">CommonParameters</span></span>

<span data-ttu-id="476a1-174">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="476a1-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="476a1-175">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="476a1-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="476a1-176">入力</span><span class="sxs-lookup"><span data-stu-id="476a1-176">INPUTS</span></span>

### <span data-ttu-id="476a1-177">System.String</span><span class="sxs-lookup"><span data-stu-id="476a1-177">System.String</span></span>

## <span data-ttu-id="476a1-178">出力</span><span class="sxs-lookup"><span data-stu-id="476a1-178">OUTPUTS</span></span>

### <span data-ttu-id="476a1-179">System.Object</span><span class="sxs-lookup"><span data-stu-id="476a1-179">System.Object</span></span>

## <span data-ttu-id="476a1-180">注</span><span class="sxs-lookup"><span data-stu-id="476a1-180">NOTES</span></span>

<span data-ttu-id="476a1-181">`Test-ScriptFileInfo`スクリプトのメタデータを検証するには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="476a1-181">Use the `Test-ScriptFileInfo` cmdlet to validate a script's metadata.</span></span> <span data-ttu-id="476a1-182">スクリプトには、バージョン、GUID、説明、および作成者の値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="476a1-182">Scripts must include values for version, GUID, description, and author.</span></span>

## <span data-ttu-id="476a1-183">関連リンク</span><span class="sxs-lookup"><span data-stu-id="476a1-183">RELATED LINKS</span></span>

[<span data-ttu-id="476a1-184">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="476a1-184">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)

[<span data-ttu-id="476a1-185">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="476a1-185">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

