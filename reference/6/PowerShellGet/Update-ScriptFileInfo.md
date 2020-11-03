---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-scriptfileinfo?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ScriptFileInfo
ms.openlocfilehash: ff1d59cd3a956c6e6964bdfc64de6f52ef2e944b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216499"
---
# <span data-ttu-id="32312-103">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="32312-103">Update-ScriptFileInfo</span></span>

## <span data-ttu-id="32312-104">概要</span><span class="sxs-lookup"><span data-stu-id="32312-104">SYNOPSIS</span></span>
<span data-ttu-id="32312-105">スクリプトの情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="32312-105">Updates information for a script.</span></span>

## <span data-ttu-id="32312-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="32312-106">SYNTAX</span></span>

### <span data-ttu-id="32312-107">PathParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="32312-107">PathParameterSet (Default)</span></span>

```
Update-ScriptFileInfo [-Path] <String> [-Version <String>] [-Author <String>] [-Guid <Guid>]
 [-Description <String>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="32312-108">LiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="32312-108">LiteralPathParameterSet</span></span>

```
Update-ScriptFileInfo [-LiteralPath] <String> [-Version <String>] [-Author <String>] [-Guid <Guid>]
 [-Description <String>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="32312-109">Description</span><span class="sxs-lookup"><span data-stu-id="32312-109">DESCRIPTION</span></span>

<span data-ttu-id="32312-110">コマンドレットでは、 `Update-ScriptFileInfo` スクリプトのプロパティ値を更新します。</span><span class="sxs-lookup"><span data-stu-id="32312-110">The `Update-ScriptFileInfo` cmdlet updates a script's property values.</span></span> <span data-ttu-id="32312-111">たとえば、[バージョン]、[作成者]、または [説明] の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-111">For example, the values for version, author, or description.</span></span>

## <span data-ttu-id="32312-112">例</span><span class="sxs-lookup"><span data-stu-id="32312-112">EXAMPLES</span></span>

### <span data-ttu-id="32312-113">例 1: スクリプトファイルのバージョンを更新する</span><span class="sxs-lookup"><span data-stu-id="32312-113">Example 1: Update the version of a script file</span></span>

<span data-ttu-id="32312-114">この例では、既存のスクリプトファイルが新しいプロパティ値で更新されます。</span><span class="sxs-lookup"><span data-stu-id="32312-114">In this example, an existing script file is updated with new property values.</span></span>

<span data-ttu-id="32312-115">スプラッティングは、コマンドレットにパラメーターを渡すために使用され `Update-ScriptFileInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="32312-115">Splatting is used to pass parameters to the `Update-ScriptFileInfo` cmdlet.</span></span> <span data-ttu-id="32312-116">詳細については、「 [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32312-116">For more information, see [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span></span>

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

<span data-ttu-id="32312-117">`$Parms`**Path** 、 **Version** 、 **Author** 、 **CompanyName** 、および **Description** のパラメーター値を格納します。</span><span class="sxs-lookup"><span data-stu-id="32312-117">`$Parms` stores the parameter values for **Path** , **Version** , **Author** , **CompanyName** , and **Description** .</span></span> <span data-ttu-id="32312-118">`Update-ScriptFileInfo` からパラメーター値を取得 `@Parms` し、スクリプトを更新します。</span><span class="sxs-lookup"><span data-stu-id="32312-118">`Update-ScriptFileInfo` gets the parameter values from `@Parms` and updates the script.</span></span> <span data-ttu-id="32312-119">**PassThru** パラメーターは、スクリプトの内容を PowerShell コンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="32312-119">The **PassThru** parameter displays the script's contents in the PowerShell console.</span></span>

## <span data-ttu-id="32312-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="32312-120">PARAMETERS</span></span>

### <span data-ttu-id="32312-121">-作成者</span><span class="sxs-lookup"><span data-stu-id="32312-121">-Author</span></span>

<span data-ttu-id="32312-122">スクリプトの作成者を指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-122">Specifies the script author.</span></span>

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

### <span data-ttu-id="32312-123">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="32312-123">-CompanyName</span></span>

<span data-ttu-id="32312-124">スクリプトを作成した会社またはベンダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-124">Specifies the company or vendor who created the script.</span></span>

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

### <span data-ttu-id="32312-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="32312-125">-Confirm</span></span>

<span data-ttu-id="32312-126">実行前に確認メッセージを表示 `Update-ScriptFileInfo` します。</span><span class="sxs-lookup"><span data-stu-id="32312-126">Prompts you for confirmation before running `Update-ScriptFileInfo`.</span></span>

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

### <span data-ttu-id="32312-127">-Copyright</span><span class="sxs-lookup"><span data-stu-id="32312-127">-Copyright</span></span>

<span data-ttu-id="32312-128">スクリプトの著作権に関する声明を指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-128">Specifies a copyright statement for the script.</span></span>

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

### <span data-ttu-id="32312-129">-Description</span><span class="sxs-lookup"><span data-stu-id="32312-129">-Description</span></span>

<span data-ttu-id="32312-130">スクリプトの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-130">Specifies a description for the script.</span></span>

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

### <span data-ttu-id="32312-131">-ExternalModuleDependencies</span><span class="sxs-lookup"><span data-stu-id="32312-131">-ExternalModuleDependencies</span></span>

<span data-ttu-id="32312-132">外部モジュールの依存関係の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-132">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="32312-133">-ExternalScriptDependencies</span><span class="sxs-lookup"><span data-stu-id="32312-133">-ExternalScriptDependencies</span></span>

<span data-ttu-id="32312-134">外部スクリプトの依存関係の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-134">Specifies an array of external script dependencies.</span></span>

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

### <span data-ttu-id="32312-135">-Force</span><span class="sxs-lookup"><span data-stu-id="32312-135">-Force</span></span>

<span data-ttu-id="32312-136">`Update-ScriptFileInfo`ユーザーの確認を求めることなく強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="32312-136">Forces `Update-ScriptFileInfo` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="32312-137">-Guid</span><span class="sxs-lookup"><span data-stu-id="32312-137">-Guid</span></span>

<span data-ttu-id="32312-138">スクリプトの一意の ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-138">Specifies a unique ID for a script.</span></span>

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

### <span data-ttu-id="32312-139">-IconUri</span><span class="sxs-lookup"><span data-stu-id="32312-139">-IconUri</span></span>

<span data-ttu-id="32312-140">スクリプトのアイコンの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-140">Specifies the URL of an icon for the script.</span></span> <span data-ttu-id="32312-141">スクリプトのギャラリー web ページに、指定したアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="32312-141">The specified icon is displayed on the gallery web page for the script.</span></span>

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

### <span data-ttu-id="32312-142">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="32312-142">-LicenseUri</span></span>

<span data-ttu-id="32312-143">ライセンス条項の URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-143">Specifies the URL of licensing terms.</span></span>

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

### <span data-ttu-id="32312-144">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="32312-144">-LiteralPath</span></span>

<span data-ttu-id="32312-145">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-145">Specifies a path to one or more locations.</span></span> <span data-ttu-id="32312-146">**LiteralPath** パラメーターの値は、入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="32312-146">The **LiteralPath** parameter's value is used exactly as it's entered.</span></span> <span data-ttu-id="32312-147">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="32312-147">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="32312-148">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="32312-148">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="32312-149">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="32312-149">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="32312-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="32312-150">-PassThru</span></span>

<span data-ttu-id="32312-151">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="32312-151">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="32312-152">既定では、は `Update-ScriptFileInfo` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="32312-152">By default, `Update-ScriptFileInfo` doesn't generate any output.</span></span>

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

### <span data-ttu-id="32312-153">-Path</span><span class="sxs-lookup"><span data-stu-id="32312-153">-Path</span></span>

<span data-ttu-id="32312-154">スクリプトファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-154">Specifies the script file's location.</span></span> <span data-ttu-id="32312-155">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="32312-155">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="32312-156">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="32312-156">-PrivateData</span></span>

<span data-ttu-id="32312-157">スクリプトのプライベートデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-157">Specifies the private data for the script.</span></span>

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

### <span data-ttu-id="32312-158">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="32312-158">-ProjectUri</span></span>

<span data-ttu-id="32312-159">このプロジェクトについての web ページの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-159">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="32312-160">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="32312-160">-ReleaseNotes</span></span>

<span data-ttu-id="32312-161">このバージョンのスクリプトで使用するリリースノートまたはコメントを格納する文字列配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-161">Specifies a string array that contains release notes or comments that you want available for this version of the script.</span></span>

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

### <span data-ttu-id="32312-162">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="32312-162">-RequiredModules</span></span>

<span data-ttu-id="32312-163">グローバル セッション状態にする必要があるモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-163">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="32312-164">必要なモジュールがグローバルセッション状態でない場合は、PowerShell によってインポートされます。</span><span class="sxs-lookup"><span data-stu-id="32312-164">If the required modules aren't in the global session state, PowerShell imports them.</span></span>

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

### <span data-ttu-id="32312-165">-RequiredScripts</span><span class="sxs-lookup"><span data-stu-id="32312-165">-RequiredScripts</span></span>

<span data-ttu-id="32312-166">必須のスクリプトの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-166">Specifies an array of required scripts.</span></span>

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

### <span data-ttu-id="32312-167">-タグ</span><span class="sxs-lookup"><span data-stu-id="32312-167">-Tags</span></span>

<span data-ttu-id="32312-168">タグの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-168">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="32312-169">-Version</span><span class="sxs-lookup"><span data-stu-id="32312-169">-Version</span></span>

<span data-ttu-id="32312-170">スクリプトのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="32312-170">Specifies the script's version.</span></span>

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

### <span data-ttu-id="32312-171">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="32312-171">-WhatIf</span></span>

<span data-ttu-id="32312-172">が実行された場合に何が起こるか `Update-ScriptFileInfo` を示します。</span><span class="sxs-lookup"><span data-stu-id="32312-172">Shows what would happen if `Update-ScriptFileInfo` runs.</span></span> <span data-ttu-id="32312-173">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="32312-173">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="32312-174">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="32312-174">CommonParameters</span></span>

<span data-ttu-id="32312-175">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="32312-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="32312-176">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32312-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="32312-177">入力</span><span class="sxs-lookup"><span data-stu-id="32312-177">INPUTS</span></span>

### <span data-ttu-id="32312-178">System.String</span><span class="sxs-lookup"><span data-stu-id="32312-178">System.String</span></span>

## <span data-ttu-id="32312-179">出力</span><span class="sxs-lookup"><span data-stu-id="32312-179">OUTPUTS</span></span>

### <span data-ttu-id="32312-180">System.Object</span><span class="sxs-lookup"><span data-stu-id="32312-180">System.Object</span></span>

## <span data-ttu-id="32312-181">注</span><span class="sxs-lookup"><span data-stu-id="32312-181">NOTES</span></span>

<span data-ttu-id="32312-182">`Test-ScriptFileInfo`スクリプトのメタデータを検証するには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="32312-182">Use the `Test-ScriptFileInfo` cmdlet to validate a script's metadata.</span></span> <span data-ttu-id="32312-183">スクリプトには、バージョン、GUID、説明、および作成者の値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="32312-183">Scripts must include values for version, GUID, description, and author.</span></span>

## <span data-ttu-id="32312-184">関連リンク</span><span class="sxs-lookup"><span data-stu-id="32312-184">RELATED LINKS</span></span>

[<span data-ttu-id="32312-185">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="32312-185">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)

[<span data-ttu-id="32312-186">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="32312-186">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)
