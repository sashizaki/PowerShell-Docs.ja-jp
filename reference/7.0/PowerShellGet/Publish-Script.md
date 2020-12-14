---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-script?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Script
ms.openlocfilehash: 26fc71546c03fbb49bf8824f6779e6b6371daa0e
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891143"
---
# <span data-ttu-id="92f18-103">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="92f18-103">Publish-Script</span></span>

## <span data-ttu-id="92f18-104">概要</span><span class="sxs-lookup"><span data-stu-id="92f18-104">SYNOPSIS</span></span>
<span data-ttu-id="92f18-105">スクリプトを発行します。</span><span class="sxs-lookup"><span data-stu-id="92f18-105">Publishes a script.</span></span>

## <span data-ttu-id="92f18-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="92f18-106">SYNTAX</span></span>

### <span data-ttu-id="92f18-107">PathParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="92f18-107">PathParameterSet (Default)</span></span>

```
Publish-Script -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="92f18-108">LiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="92f18-108">LiteralPathParameterSet</span></span>

```
Publish-Script -LiteralPath <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="92f18-109">Description</span><span class="sxs-lookup"><span data-stu-id="92f18-109">DESCRIPTION</span></span>

<span data-ttu-id="92f18-110">`Publish-Script`コマンドレットは、指定されたスクリプトをオンラインギャラリーに発行します。</span><span class="sxs-lookup"><span data-stu-id="92f18-110">The `Publish-Script` cmdlet publishes the specified script to the online gallery.</span></span>

## <span data-ttu-id="92f18-111">例</span><span class="sxs-lookup"><span data-stu-id="92f18-111">EXAMPLES</span></span>

### <span data-ttu-id="92f18-112">例 1: スクリプトファイルを作成し、そのファイルにコンテンツを追加して公開する</span><span class="sxs-lookup"><span data-stu-id="92f18-112">Example 1: Create a script file, add content to it, and publish it</span></span>

<span data-ttu-id="92f18-113">`New-ScriptFileInfo`コマンドレットでは、という名前のスクリプトファイルを作成し `Demo-Script.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="92f18-113">The `New-ScriptFileInfo` cmdlet creates a script file named `Demo-Script.ps1`.</span></span> <span data-ttu-id="92f18-114">`Get-Content` の内容を表示 `Demo-Script.ps1` します。</span><span class="sxs-lookup"><span data-stu-id="92f18-114">`Get-Content` displays the content of `Demo-Script.ps1`.</span></span> <span data-ttu-id="92f18-115">コマンドレットでは、 `Add-Content` 関数とワークフローをに追加し `Demo-Script.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="92f18-115">The `Add-Content` cmdlet adds a function and a workflow to `Demo-Script.ps1`.</span></span>

```powershell
$newScriptInfo = @{
  Path = 'D:\ScriptSharingDemo\Demo-Script.ps1'
  Version = '1.0'
  Author = 'author@contoso.com'
  Description = "my test script file description goes here"
}
New-ScriptFileInfo @newScriptInfo
Get-Content -Path $newScriptInfo.Path
```

```Output
<#PSScriptInfo

.VERSION 1.0

.AUTHOR pattif@microsoft.com

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
#>

<#
.DESCRIPTION
 my test script file description goes here
#>
Param()
```

```powershell
Add-Content -Path D:\ScriptSharingDemo\Demo-Script.ps1 -Value @"

Function Demo-ScriptFunction { 'Demo-ScriptFunction' }

Workflow Demo-ScriptWorkflow { 'Demo-ScriptWorkflow' }

Demo-ScriptFunction
Demo-ScriptWorkflow
"@
Test-ScriptFileInfo -Path D:\ScriptSharingDemo\Demo-Script.ps1
```

```Output
Version    Name                 Author                   Description
-------    ----                 ------                   -----------
1.0        Demo-Script          author@contoso.com       my test script file description goes here
```

```powershell
Publish-Script -Path D:\ScriptSharingDemo\Demo-Script.ps1 -Repository LocalRepo1
Find-Script -Repository LocalRepo1 -Name "Demo-Script"
```

```Output
Version    Name                 Type       Repository    Description
-------    ----                 ----       ----------    -----------
1.0        Demo-Script          Script     LocalRepo1    my test script file description goes here
```

<span data-ttu-id="92f18-116">コマンドレットによって `Test-ScriptFileInfo` 検証さ `Demo-Script.ps1` れます。</span><span class="sxs-lookup"><span data-stu-id="92f18-116">The `Test-ScriptFileInfo` cmdlet validates `Demo-Script.ps1`.</span></span> <span data-ttu-id="92f18-117">この `Publish-Script` コマンドレットは、スクリプトを **LocalRepo1** リポジトリに発行します。</span><span class="sxs-lookup"><span data-stu-id="92f18-117">The `Publish-Script` cmdlet publishes the script to the **LocalRepo1** repository.</span></span> <span data-ttu-id="92f18-118">最後に、</span><span class="sxs-lookup"><span data-stu-id="92f18-118">Finally.</span></span> <span data-ttu-id="92f18-119">`Find-Script` は `Demo-Script.ps1` 、 **LocalRepo1** リポジトリでを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="92f18-119">`Find-Script` is used to search for `Demo-Script.ps1` in the **LocalRepo1** repository.</span></span>

## <span data-ttu-id="92f18-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="92f18-120">PARAMETERS</span></span>

### <span data-ttu-id="92f18-121">-Confirm</span><span class="sxs-lookup"><span data-stu-id="92f18-121">-Confirm</span></span>

<span data-ttu-id="92f18-122">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="92f18-122">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="92f18-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="92f18-123">-Credential</span></span>

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

### <span data-ttu-id="92f18-124">-Force</span><span class="sxs-lookup"><span data-stu-id="92f18-124">-Force</span></span>

<span data-ttu-id="92f18-125">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="92f18-125">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="92f18-126">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="92f18-126">-LiteralPath</span></span>

<span data-ttu-id="92f18-127">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="92f18-127">Specifies a path to one or more locations.</span></span> <span data-ttu-id="92f18-128">**Path** パラメーターとは異なり、 **LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="92f18-128">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="92f18-129">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="92f18-129">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="92f18-130">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="92f18-130">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="92f18-131">単一引用符で囲んだ文字はエスケープ シーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="92f18-131">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="92f18-132">-NuGetApiKey</span><span class="sxs-lookup"><span data-stu-id="92f18-132">-NuGetApiKey</span></span>

<span data-ttu-id="92f18-133">オンラインギャラリーにスクリプトを発行するために使用する API キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="92f18-133">Specifies the API key that you want to use to publish a script to the online gallery.</span></span> <span data-ttu-id="92f18-134">API キーは、オンラインギャラリーのプロファイルの一部です。</span><span class="sxs-lookup"><span data-stu-id="92f18-134">The API key is part of your profile in the online gallery.</span></span> <span data-ttu-id="92f18-135">詳細については、「 [API キーの管理](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92f18-135">For more information see [Managing API keys](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span></span>

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

### <span data-ttu-id="92f18-136">-Path</span><span class="sxs-lookup"><span data-stu-id="92f18-136">-Path</span></span>

<span data-ttu-id="92f18-137">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="92f18-137">Specifies a path to one or more locations.</span></span> <span data-ttu-id="92f18-138">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="92f18-138">Wildcards are permitted.</span></span> <span data-ttu-id="92f18-139">既定の場所は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="92f18-139">The default location is the current directory.</span></span>

```yaml
Type: System.String
Parameter Sets: PathParameterSet
Aliases:

Required: True
Position: Named
Default value: <Current location>
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="92f18-140">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="92f18-140">-Repository</span></span>

<span data-ttu-id="92f18-141">を実行して登録されているリポジトリのフレンドリ名を指定し `Register-PSRepository` ます。</span><span class="sxs-lookup"><span data-stu-id="92f18-141">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span>

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

### <span data-ttu-id="92f18-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="92f18-142">-WhatIf</span></span>

<span data-ttu-id="92f18-143">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="92f18-143">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="92f18-144">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="92f18-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="92f18-145">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="92f18-145">CommonParameters</span></span>

<span data-ttu-id="92f18-146">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="92f18-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="92f18-147">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92f18-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="92f18-148">入力</span><span class="sxs-lookup"><span data-stu-id="92f18-148">INPUTS</span></span>

### <span data-ttu-id="92f18-149">System.String</span><span class="sxs-lookup"><span data-stu-id="92f18-149">System.String</span></span>

### <span data-ttu-id="92f18-150">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="92f18-150">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="92f18-151">出力</span><span class="sxs-lookup"><span data-stu-id="92f18-151">OUTPUTS</span></span>

### <span data-ttu-id="92f18-152">System.Object</span><span class="sxs-lookup"><span data-stu-id="92f18-152">System.Object</span></span>

## <span data-ttu-id="92f18-153">注</span><span class="sxs-lookup"><span data-stu-id="92f18-153">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="92f18-154">2020年4月の時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン1.0 と1.1 がサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="92f18-154">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="92f18-155">TLS 1.2 以降を使用していない場合は、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="92f18-155">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="92f18-156">次のコマンドを使用して、TLS 1.2 を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="92f18-156">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="92f18-157">詳細については、PowerShell ブログの [お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92f18-157">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="92f18-158">関連リンク</span><span class="sxs-lookup"><span data-stu-id="92f18-158">RELATED LINKS</span></span>

[<span data-ttu-id="92f18-159">Find-Script</span><span class="sxs-lookup"><span data-stu-id="92f18-159">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="92f18-160">Install-Script</span><span class="sxs-lookup"><span data-stu-id="92f18-160">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="92f18-161">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="92f18-161">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="92f18-162">Save-Script</span><span class="sxs-lookup"><span data-stu-id="92f18-162">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="92f18-163">Update-Script</span><span class="sxs-lookup"><span data-stu-id="92f18-163">Update-Script</span></span>](Update-Script.md)
