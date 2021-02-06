---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/01/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/new-scriptfileinfo?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScriptFileInfo
ms.openlocfilehash: d3e3c0ec257bd9c405accaf3051abd1ae4501f0f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602415"
---
# <span data-ttu-id="558b8-102">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="558b8-102">New-ScriptFileInfo</span></span>

## <span data-ttu-id="558b8-103">概要</span><span class="sxs-lookup"><span data-stu-id="558b8-103">SYNOPSIS</span></span>
<span data-ttu-id="558b8-104">メタデータを持つスクリプト ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="558b8-104">Creates a script file with metadata.</span></span>

## <span data-ttu-id="558b8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="558b8-105">SYNTAX</span></span>

### <span data-ttu-id="558b8-106">すべて</span><span class="sxs-lookup"><span data-stu-id="558b8-106">All</span></span>

```
New-ScriptFileInfo [[-Path] <String>] [-Version <String>] [-Author <String>] -Description <String>
 [-Guid <Guid>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="558b8-107">Description</span><span class="sxs-lookup"><span data-stu-id="558b8-107">DESCRIPTION</span></span>

<span data-ttu-id="558b8-108">`New-ScriptFileInfo`コマンドレットにより、スクリプトに関するメタデータを含む PowerShell スクリプトファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="558b8-108">The `New-ScriptFileInfo` cmdlet creates a PowerShell script file, including metadata about the script.</span></span>

<span data-ttu-id="558b8-109">この例では、スプラッティングを使用してコマンドレットにパラメーターを渡し `New-ScriptFileInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="558b8-109">The examples use splatting to pass parameters to the `New-ScriptFileInfo` cmdlet.</span></span> <span data-ttu-id="558b8-110">詳細については、「 [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="558b8-110">For more information, see [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span></span>

## <span data-ttu-id="558b8-111">例</span><span class="sxs-lookup"><span data-stu-id="558b8-111">EXAMPLES</span></span>

### <span data-ttu-id="558b8-112">例 1: スクリプトファイルを作成し、そのバージョン、作成者、および説明を指定する</span><span class="sxs-lookup"><span data-stu-id="558b8-112">Example 1: Create a script file and specify its version, author, and description</span></span>

<span data-ttu-id="558b8-113">この例では、スクリプトファイルが作成され、その内容が PowerShell コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="558b8-113">In this example, a script file is created and its contents are displayed in the PowerShell console.</span></span>

```powershell
$Parms = @{
  Path = "C:\Test\Temp-Scriptfile.ps1"
  Version = "1.0"
  Author = "pattif@contoso.com"
  Description = "My test script file description goes here"
  }
New-ScriptFileInfo @Parms
Get-Content -Path C:\Test\Temp-Scriptfile.ps1
```

```Output
<#PSScriptInfo

.VERSION 1.0

.GUID 3bb10ee7-38c1-41b9-88ea-16899164fc19

.AUTHOR pattif@contoso.com

.COMPANYNAME

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
 My test script file description goes here

#>
Param()
```

<span data-ttu-id="558b8-114">コマンドレットでは、 `New-ScriptFileInfo` スプラッティングを使用してスクリプトのいくつかのパラメーターを構成します。</span><span class="sxs-lookup"><span data-stu-id="558b8-114">The `New-ScriptFileInfo` cmdlet uses splatting to configure several parameters for the script.</span></span>
<span data-ttu-id="558b8-115">**パス** スクリプトの場所と名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-115">**Path** sets the location and name of the script.</span></span> <span data-ttu-id="558b8-116">**バージョン** スクリプトのバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-116">**Version** specifies the script's version number.</span></span> <span data-ttu-id="558b8-117">**Author** は、スクリプトを作成したユーザーの電子メールアドレスです。</span><span class="sxs-lookup"><span data-stu-id="558b8-117">**Author** is the email address of the person who created the script.</span></span> <span data-ttu-id="558b8-118">**説明** スクリプトの目的を説明します。</span><span class="sxs-lookup"><span data-stu-id="558b8-118">**Description** explains the script's purpose.</span></span>

<span data-ttu-id="558b8-119">スクリプトが作成された後、は `Get-Content` **Path** パラメーターを使用してスクリプトを検索します。</span><span class="sxs-lookup"><span data-stu-id="558b8-119">After the script is created, `Get-Content` uses the **Path** parameter to locate the script.</span></span> <span data-ttu-id="558b8-120">スクリプトの内容は、PowerShell コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="558b8-120">The script's contents are displayed in the PowerShell console.</span></span>

### <span data-ttu-id="558b8-121">例 2: スクリプトファイルをテストする</span><span class="sxs-lookup"><span data-stu-id="558b8-121">Example 2: Test a script file</span></span>

<span data-ttu-id="558b8-122">この例では、 **例 1** で作成したスクリプトのメタデータがテストされます。</span><span class="sxs-lookup"><span data-stu-id="558b8-122">In this example, the metadata for the script created in **Example 1** is tested.</span></span>

```powershell
Test-ScriptFileInfo -Path C:\Test\Temp-Scriptfile.ps1
```

```Output
Version   Name                  Author               Description
-------   ----                  ------               -----------
1.0       Temp-Scriptfile       pattif@contoso.com   My test script file description goes here
```

<span data-ttu-id="558b8-123">`Test-ScriptFileInfo`コマンドレットでは、 **Path** パラメーターを使用して、スクリプトファイルの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-123">The `Test-ScriptFileInfo` cmdlet uses the **Path** parameter to specify the script file's location.</span></span>

### <span data-ttu-id="558b8-124">例 3: すべてのメタデータプロパティを含むスクリプトファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="558b8-124">Example 3: Create a script file with all the metadata properties</span></span>

<span data-ttu-id="558b8-125">この例では、スプラッティングを使用して `New-ScriptFile.ps1` 、すべてのメタデータプロパティを含むという名前のスクリプトファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="558b8-125">This example uses splatting to create a script file named `New-ScriptFile.ps1` that includes all its metadata properties.</span></span> <span data-ttu-id="558b8-126">**Verbose** パラメーターは、スクリプトの作成時に詳細出力を表示することを指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-126">The **Verbose** parameter specifies that verbose output is displayed as the script is created.</span></span>

```powershell
$Parms = @{
 Path = "C:\Test\New-ScriptFile.ps1"
 Verbose = $True
 Version = "1.0"
 Author = "pattif@contoso.com"
 Description = "My new script file test"
 CompanyName = "Contoso Corporation"
 Copyright = "2019 Contoso Corporation. All rights reserved."
 ExternalModuleDependencies = "ff","bb"
 RequiredScripts = "Start-WFContosoServer", "Stop-ContosoServerScript"
 ExternalScriptDependencies = "Stop-ContosoServerScript"
 Tags = @("Tag1", "Tag2", "Tag3")
 ProjectUri = "https://contoso.com"
 LicenseUri = "https://contoso.com/License"
 IconUri = "https://contoso.com/Icon"
 PassThru = $True
 ReleaseNotes = @("Contoso script now supports the following features:",
   "Feature 1",
   "Feature 2",
   "Feature 3",
   "Feature 4",
   "Feature 5")
 RequiredModules =
   "1",
   "2",
   "RequiredModule1",
   @{ModuleName="RequiredModule2";ModuleVersion="1.0"},
   @{ModuleName="RequiredModule3";RequiredVersion="2.0"},
   "ExternalModule1"
 }
New-ScriptFileInfo @Parms
```

```Output
VERBOSE: Performing the operation "Creating the 'C:\Test\New-ScriptFile.ps1'
  PowerShell Script file" on target "C:\Test\New-ScriptFile.ps1".

<#PSScriptInfo

.VERSION 1.0

.GUID 4fabe8c7-7862-45b1-a72e-1352a433b77d

.AUTHOR pattif@contoso.com

.COMPANYNAME Contoso Corporation

.COPYRIGHT 2019 Contoso Corporation. All rights reserved.

.TAGS Tag1 Tag2 Tag3

.LICENSEURI https://contoso.com/License

.PROJECTURI https://contoso.com/

.ICONURI https://contoso.com/Icon

.EXTERNALMODULEDEPENDENCIES ff,bb

.REQUIREDSCRIPTS Start-WFContosoServer,Stop-ContosoServerScript

.EXTERNALSCRIPTDEPENDENCIES Stop-ContosoServerScript

.RELEASENOTES
Contoso script now supports the following features:
Feature 1
Feature 2
Feature 3
Feature 4
Feature 5

.PRIVATEDATA

#>

#Requires -Module 1
#Requires -Module 2
#Requires -Module RequiredModule1
#Requires -Module @{ModuleName = 'RequiredModule2'; ModuleVersion = '1.0'}
#Requires -Module @{RequiredVersion = '2.0'; ModuleName = 'RequiredModule3'}
#Requires -Module ExternalModule1

<#

.DESCRIPTION
 My new script file test

#>
Param()
```

## <span data-ttu-id="558b8-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="558b8-127">PARAMETERS</span></span>

### <span data-ttu-id="558b8-128">-作成者</span><span class="sxs-lookup"><span data-stu-id="558b8-128">-Author</span></span>

<span data-ttu-id="558b8-129">スクリプトの作成者を指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-129">Specifies the script author.</span></span>

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

### <span data-ttu-id="558b8-130">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="558b8-130">-CompanyName</span></span>

<span data-ttu-id="558b8-131">スクリプトを作成した会社またはベンダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-131">Specifies the company or vendor who created the script.</span></span>

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

### <span data-ttu-id="558b8-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="558b8-132">-Confirm</span></span>

<span data-ttu-id="558b8-133">を実行する前に確認メッセージを表示し `New-ScriptFileInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="558b8-133">Prompts you for confirmation before running the `New-ScriptFileInfo`.</span></span>

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

### <span data-ttu-id="558b8-134">-Copyright</span><span class="sxs-lookup"><span data-stu-id="558b8-134">-Copyright</span></span>

<span data-ttu-id="558b8-135">スクリプトの著作権に関する声明を指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-135">Specifies a copyright statement for the script.</span></span>

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

### <span data-ttu-id="558b8-136">-Description</span><span class="sxs-lookup"><span data-stu-id="558b8-136">-Description</span></span>

<span data-ttu-id="558b8-137">スクリプトの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-137">Specifies a description for the script.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="558b8-138">-ExternalModuleDependencies</span><span class="sxs-lookup"><span data-stu-id="558b8-138">-ExternalModuleDependencies</span></span>

<span data-ttu-id="558b8-139">外部モジュールの依存関係の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-139">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="558b8-140">-ExternalScriptDependencies</span><span class="sxs-lookup"><span data-stu-id="558b8-140">-ExternalScriptDependencies</span></span>

<span data-ttu-id="558b8-141">外部スクリプトの依存関係の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-141">Specifies an array of external script dependencies.</span></span>

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

### <span data-ttu-id="558b8-142">-Force</span><span class="sxs-lookup"><span data-stu-id="558b8-142">-Force</span></span>

<span data-ttu-id="558b8-143">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="558b8-143">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="558b8-144">-Guid</span><span class="sxs-lookup"><span data-stu-id="558b8-144">-Guid</span></span>

<span data-ttu-id="558b8-145">スクリプトの一意の ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-145">Specifies a unique ID for the script.</span></span>

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

### <span data-ttu-id="558b8-146">-IconUri</span><span class="sxs-lookup"><span data-stu-id="558b8-146">-IconUri</span></span>

<span data-ttu-id="558b8-147">スクリプトのアイコンの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-147">Specifies the URL of an icon for the script.</span></span> <span data-ttu-id="558b8-148">スクリプトのギャラリー web ページに、指定したアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="558b8-148">The specified icon is displayed on the gallery web page for the script.</span></span>

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

### <span data-ttu-id="558b8-149">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="558b8-149">-LicenseUri</span></span>

<span data-ttu-id="558b8-150">ライセンス条項の URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-150">Specifies the URL of licensing terms.</span></span>

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

### <span data-ttu-id="558b8-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="558b8-151">-PassThru</span></span>

<span data-ttu-id="558b8-152">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="558b8-152">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="558b8-153">既定では、は `New-ScriptFileInfo` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="558b8-153">By default, `New-ScriptFileInfo` doesn't generate any output.</span></span>

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

### <span data-ttu-id="558b8-154">-Path</span><span class="sxs-lookup"><span data-stu-id="558b8-154">-Path</span></span>

<span data-ttu-id="558b8-155">スクリプトファイルを保存する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-155">Specifies the location where the script file is saved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="558b8-156">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="558b8-156">-PrivateData</span></span>

<span data-ttu-id="558b8-157">スクリプトのプライベートデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-157">Specifies private data for the script.</span></span>

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

### <span data-ttu-id="558b8-158">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="558b8-158">-ProjectUri</span></span>

<span data-ttu-id="558b8-159">このプロジェクトについての web ページの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-159">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="558b8-160">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="558b8-160">-ReleaseNotes</span></span>

<span data-ttu-id="558b8-161">このバージョンのスクリプトのユーザーが使用できるようにするリリースノートまたはコメントを含む文字列配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-161">Specifies a string array that contains release notes or comments that you want available to users of this version of the script.</span></span>

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

### <span data-ttu-id="558b8-162">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="558b8-162">-RequiredModules</span></span>

<span data-ttu-id="558b8-163">グローバル セッション状態にする必要があるモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-163">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="558b8-164">必要なモジュールがグローバルセッション状態でない場合は、PowerShell によってインポートされます。</span><span class="sxs-lookup"><span data-stu-id="558b8-164">If the required modules aren't in the global session state, PowerShell imports them.</span></span>

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

### <span data-ttu-id="558b8-165">-RequiredScripts</span><span class="sxs-lookup"><span data-stu-id="558b8-165">-RequiredScripts</span></span>

<span data-ttu-id="558b8-166">必須のスクリプトの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-166">Specifies an array of required scripts.</span></span>

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

### <span data-ttu-id="558b8-167">-タグ</span><span class="sxs-lookup"><span data-stu-id="558b8-167">-Tags</span></span>

<span data-ttu-id="558b8-168">タグの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-168">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="558b8-169">-Version</span><span class="sxs-lookup"><span data-stu-id="558b8-169">-Version</span></span>

<span data-ttu-id="558b8-170">スクリプトのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="558b8-170">Specifies the version of the script.</span></span>

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

### <span data-ttu-id="558b8-171">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="558b8-171">-WhatIf</span></span>

<span data-ttu-id="558b8-172">が実行された場合に何が起こるか `New-ScriptFileInfo` を示します。</span><span class="sxs-lookup"><span data-stu-id="558b8-172">Shows what would happen if `New-ScriptFileInfo` runs.</span></span> <span data-ttu-id="558b8-173">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="558b8-173">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="558b8-174">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="558b8-174">CommonParameters</span></span>

<span data-ttu-id="558b8-175">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="558b8-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="558b8-176">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="558b8-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="558b8-177">入力</span><span class="sxs-lookup"><span data-stu-id="558b8-177">INPUTS</span></span>

### <span data-ttu-id="558b8-178">System.String</span><span class="sxs-lookup"><span data-stu-id="558b8-178">System.String</span></span>

## <span data-ttu-id="558b8-179">出力</span><span class="sxs-lookup"><span data-stu-id="558b8-179">OUTPUTS</span></span>

### <span data-ttu-id="558b8-180">System.Object</span><span class="sxs-lookup"><span data-stu-id="558b8-180">System.Object</span></span>

## <span data-ttu-id="558b8-181">注</span><span class="sxs-lookup"><span data-stu-id="558b8-181">NOTES</span></span>

## <span data-ttu-id="558b8-182">関連リンク</span><span class="sxs-lookup"><span data-stu-id="558b8-182">RELATED LINKS</span></span>

[<span data-ttu-id="558b8-183">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="558b8-183">about_Splatting</span></span>](../Microsoft.Powershell.Core/About/about_splatting.md)

[<span data-ttu-id="558b8-184">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="558b8-184">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

[<span data-ttu-id="558b8-185">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="558b8-185">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)

