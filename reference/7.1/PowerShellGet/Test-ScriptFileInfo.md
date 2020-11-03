---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/test-scriptfileinfo?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ScriptFileInfo
ms.openlocfilehash: 4b02b853da5f42eb76d63ec38f77852df838bbe0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212632"
---
# <span data-ttu-id="efa65-103">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="efa65-103">Test-ScriptFileInfo</span></span>

## <span data-ttu-id="efa65-104">概要</span><span class="sxs-lookup"><span data-stu-id="efa65-104">SYNOPSIS</span></span>
<span data-ttu-id="efa65-105">スクリプトのコメントブロックを検証します。</span><span class="sxs-lookup"><span data-stu-id="efa65-105">Validates a comment block for a script.</span></span>

## <span data-ttu-id="efa65-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="efa65-106">SYNTAX</span></span>

### <span data-ttu-id="efa65-107">PathParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="efa65-107">PathParameterSet (Default)</span></span>

```
Test-ScriptFileInfo [-Path] <String> [<CommonParameters>]
```

### <span data-ttu-id="efa65-108">LiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="efa65-108">LiteralPathParameterSet</span></span>

```
Test-ScriptFileInfo -LiteralPath <String> [<CommonParameters>]
```

## <span data-ttu-id="efa65-109">Description</span><span class="sxs-lookup"><span data-stu-id="efa65-109">DESCRIPTION</span></span>

<span data-ttu-id="efa65-110">**New-scriptfileinfo** コマンドレットは、Publish-Script コマンドレットで公開されるスクリプトの先頭にあるコメントブロックを検証します。</span><span class="sxs-lookup"><span data-stu-id="efa65-110">The **Test-ScriptFileInfo** cmdlet validates the comment block at the beginning of a script that will be published with the Publish-Script cmdlet.</span></span>
<span data-ttu-id="efa65-111">コメントブロックにエラーがある場合、このコマンドレットは、エラーが発生している場所または修正方法に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="efa65-111">If the comment block has an error, this cmdlet returns information about where the error is located or how to correct it.</span></span>

## <span data-ttu-id="efa65-112">例</span><span class="sxs-lookup"><span data-stu-id="efa65-112">EXAMPLES</span></span>

### <span data-ttu-id="efa65-113">例 1: スクリプトファイルをテストする</span><span class="sxs-lookup"><span data-stu-id="efa65-113">Example 1: Test a script file</span></span>

```
PS C:\> Test-ScriptFileInfo -Path "C:\temp\temp_scripts\New-ScriptFile.ps1"
Version    Name                      Author               Description
-------    ----                      ------               -----------
1.0        New-ScriptFile            pattif               my new script file test
```

<span data-ttu-id="efa65-114">このコマンドは、New-ScriptFile.ps1 スクリプトファイルをテストし、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="efa65-114">This command tests the New-ScriptFile.ps1 script file and displays the results.</span></span>
<span data-ttu-id="efa65-115">スクリプトファイルには、有効なメタデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="efa65-115">The script file includes valid metadata.</span></span>

### <span data-ttu-id="efa65-116">例 2: すべてのメタデータプロパティの値を含むスクリプトファイルをテストする</span><span class="sxs-lookup"><span data-stu-id="efa65-116">Example 2: Test a script file that has values for all metadata properties</span></span>

```
PS C:\> Test-ScriptFileInfo -Path "D:\code\Test-Runbook.ps1" | Format-List *
Name                       : Test-Runbook
Path                       : D:\code\Test-Runbook.ps1
ScriptBase                 : D:\code
ReleaseNotes               : {contoso script now supports following features, Feature 1, Feature 2, Feature 3...}
Version                    : 1.0
Guid                       : eb246b19-17da-4392-8c89-7c280f69ad0e
Author                     : pattif
CompanyName                : Microsoft Corporation
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
Tags                       : {Tag1, Tag2, Tag3}
LicenseUri                 : https://contoso.com/License
ProjectUri                 : https://contoso.com/
IconUri                    : https://contoso.com/MyScriptIcon
ExternalModuleDependencies : ExternalModule1
RequiredScripts            : {Start-WFContosoServer, Stop-ContosoServerScript}
ExternalScriptDependencies : Stop-ContosoServerScript
Description                : Contoso Script example
RequiredModules            : {RequiredModule1, @{ ModuleName = 'RequiredModule2'; ModuleVersion = '1.0' }, @{ ModuleName = 'RequiredModule3'; RequiredVersion = '2.0' }, ExternalModule1}
ExportedCommands           : {Test-WebUri, ValidateAndAdd-PSScriptInfoEntry, Get-PSScriptInfo, My-Workflow...}
ExportedFunctions          : {Test-WebUri, ValidateAndAdd-PSScriptInfoEntry, Get-PSScriptInfo, My-AdvPSCmdlet}
ExportedWorkflows          : My-Workflow
```

<span data-ttu-id="efa65-117">このコマンドは、スクリプトファイル Test-Runbook.ps1 をテストし、パイプライン演算子を使用して結果を Format-List コマンドレットに渡し、結果を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="efa65-117">This command tests the script file Test-Runbook.ps1 and uses the pipeline operator to pass the results to the Format-List cmdlet to format the results.</span></span>

### <span data-ttu-id="efa65-118">例 3: メタデータのないスクリプトファイルをテストする</span><span class="sxs-lookup"><span data-stu-id="efa65-118">Example 3: Test a script file that has no metadata</span></span>

```
PS C:\> Test-ScriptFileInfo -Path "D:\code\Hello-World.ps1"
Test-ScriptFileInfo : Script 'D:\code\Hello-World.ps1' is missing required metadata properties. Verify that the script file has Version, Description
and Author properties. You can use the Update-ScriptFileInfo or New-ScriptFileInfo cmdlet to add or update the PSScriptInfo to the script file.
At line:1 char:1
+ Test-ScriptFileInfo D:\code\Hello-World.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidArgument: (D:\code\Hello-World.ps1:String) [Test-ScriptFileInfo], ArgumentException

+ FullyQualifiedErrorId : MissingRequiredPSScriptInfoProperties,Test-ScriptFile
```

<span data-ttu-id="efa65-119">このコマンドは、メタデータが関連付けられていないスクリプトファイル Hello-World.ps1 をテストします。</span><span class="sxs-lookup"><span data-stu-id="efa65-119">This command tests the script file Hello-World.ps1, which has no metadata associated with it.</span></span>

## <span data-ttu-id="efa65-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="efa65-120">PARAMETERS</span></span>

### <span data-ttu-id="efa65-121">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="efa65-121">-LiteralPath</span></span>

<span data-ttu-id="efa65-122">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="efa65-122">Specifies a path to one or more locations.</span></span>
<span data-ttu-id="efa65-123">*Path* パラメーターとは異なり、 *LiteralPath* パラメーターの値は入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="efa65-123">Unlike the *Path* parameter, the value of the *LiteralPath* parameter is used exactly as it is entered.</span></span>
<span data-ttu-id="efa65-124">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="efa65-124">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="efa65-125">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="efa65-125">If the path includes escape characters, enclose them in single quotation marks.</span></span>
<span data-ttu-id="efa65-126">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="efa65-126">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPathParameterSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="efa65-127">-Path</span><span class="sxs-lookup"><span data-stu-id="efa65-127">-Path</span></span>

<span data-ttu-id="efa65-128">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="efa65-128">Specifies a path to one or more locations.</span></span>
<span data-ttu-id="efa65-129">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="efa65-129">Wildcards are permitted.</span></span>
<span data-ttu-id="efa65-130">既定の場所は現在のディレクトリ (.) です。</span><span class="sxs-lookup"><span data-stu-id="efa65-130">The default location is the current directory (.).</span></span>

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

### <span data-ttu-id="efa65-131">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="efa65-131">CommonParameters</span></span>

<span data-ttu-id="efa65-132">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="efa65-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="efa65-133">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efa65-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="efa65-134">入力</span><span class="sxs-lookup"><span data-stu-id="efa65-134">INPUTS</span></span>

### <span data-ttu-id="efa65-135">System.String</span><span class="sxs-lookup"><span data-stu-id="efa65-135">System.String</span></span>

## <span data-ttu-id="efa65-136">出力</span><span class="sxs-lookup"><span data-stu-id="efa65-136">OUTPUTS</span></span>

### <span data-ttu-id="efa65-137">System.Object</span><span class="sxs-lookup"><span data-stu-id="efa65-137">System.Object</span></span>

## <span data-ttu-id="efa65-138">注</span><span class="sxs-lookup"><span data-stu-id="efa65-138">NOTES</span></span>

## <span data-ttu-id="efa65-139">関連リンク</span><span class="sxs-lookup"><span data-stu-id="efa65-139">RELATED LINKS</span></span>

[<span data-ttu-id="efa65-140">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="efa65-140">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)

[<span data-ttu-id="efa65-141">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="efa65-141">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="efa65-142">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="efa65-142">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)

