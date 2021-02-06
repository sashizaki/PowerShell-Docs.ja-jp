---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-script?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Script
ms.openlocfilehash: 344a789c9daced51b549d562b7fd74677fe403dc
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99600976"
---
# <span data-ttu-id="308f5-102">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="308f5-102">Publish-Script</span></span>

## <span data-ttu-id="308f5-103">概要</span><span class="sxs-lookup"><span data-stu-id="308f5-103">SYNOPSIS</span></span>
<span data-ttu-id="308f5-104">スクリプトを発行します。</span><span class="sxs-lookup"><span data-stu-id="308f5-104">Publishes a script.</span></span>

## <span data-ttu-id="308f5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="308f5-105">SYNTAX</span></span>

### <span data-ttu-id="308f5-106">PathParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="308f5-106">PathParameterSet (Default)</span></span>

```
Publish-Script -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="308f5-107">LiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="308f5-107">LiteralPathParameterSet</span></span>

```
Publish-Script -LiteralPath <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="308f5-108">Description</span><span class="sxs-lookup"><span data-stu-id="308f5-108">DESCRIPTION</span></span>

<span data-ttu-id="308f5-109">`Publish-Script`コマンドレットは、指定されたスクリプトをオンラインギャラリーに発行します。</span><span class="sxs-lookup"><span data-stu-id="308f5-109">The `Publish-Script` cmdlet publishes the specified script to the online gallery.</span></span>

## <span data-ttu-id="308f5-110">例</span><span class="sxs-lookup"><span data-stu-id="308f5-110">EXAMPLES</span></span>

### <span data-ttu-id="308f5-111">例 1: スクリプトファイルを作成し、そのファイルにコンテンツを追加して公開する</span><span class="sxs-lookup"><span data-stu-id="308f5-111">Example 1: Create a script file, add content to it, and publish it</span></span>

<span data-ttu-id="308f5-112">`New-ScriptFileInfo`コマンドレットでは、という名前のスクリプトファイルを作成し `Demo-Script.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="308f5-112">The `New-ScriptFileInfo` cmdlet creates a script file named `Demo-Script.ps1`.</span></span> <span data-ttu-id="308f5-113">`Get-Content` の内容を表示 `Demo-Script.ps1` します。</span><span class="sxs-lookup"><span data-stu-id="308f5-113">`Get-Content` displays the content of `Demo-Script.ps1`.</span></span> <span data-ttu-id="308f5-114">コマンドレットでは、 `Add-Content` 関数とワークフローをに追加し `Demo-Script.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="308f5-114">The `Add-Content` cmdlet adds a function and a workflow to `Demo-Script.ps1`.</span></span>

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

<span data-ttu-id="308f5-115">コマンドレットによって `Test-ScriptFileInfo` 検証さ `Demo-Script.ps1` れます。</span><span class="sxs-lookup"><span data-stu-id="308f5-115">The `Test-ScriptFileInfo` cmdlet validates `Demo-Script.ps1`.</span></span> <span data-ttu-id="308f5-116">この `Publish-Script` コマンドレットは、スクリプトを **LocalRepo1** リポジトリに発行します。</span><span class="sxs-lookup"><span data-stu-id="308f5-116">The `Publish-Script` cmdlet publishes the script to the **LocalRepo1** repository.</span></span> <span data-ttu-id="308f5-117">最後に、</span><span class="sxs-lookup"><span data-stu-id="308f5-117">Finally.</span></span> <span data-ttu-id="308f5-118">`Find-Script` は `Demo-Script.ps1` 、 **LocalRepo1** リポジトリでを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="308f5-118">`Find-Script` is used to search for `Demo-Script.ps1` in the **LocalRepo1** repository.</span></span>

## <span data-ttu-id="308f5-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="308f5-119">PARAMETERS</span></span>

### <span data-ttu-id="308f5-120">-Confirm</span><span class="sxs-lookup"><span data-stu-id="308f5-120">-Confirm</span></span>

<span data-ttu-id="308f5-121">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="308f5-121">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="308f5-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="308f5-122">-Credential</span></span>

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

### <span data-ttu-id="308f5-123">-Force</span><span class="sxs-lookup"><span data-stu-id="308f5-123">-Force</span></span>

<span data-ttu-id="308f5-124">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="308f5-124">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="308f5-125">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="308f5-125">-LiteralPath</span></span>

<span data-ttu-id="308f5-126">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="308f5-126">Specifies a path to one or more locations.</span></span> <span data-ttu-id="308f5-127">**Path** パラメーターとは異なり、 **LiteralPath** パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="308f5-127">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="308f5-128">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="308f5-128">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="308f5-129">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="308f5-129">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="308f5-130">単一引用符で囲んだ文字はエスケープ シーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="308f5-130">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="308f5-131">-NuGetApiKey</span><span class="sxs-lookup"><span data-stu-id="308f5-131">-NuGetApiKey</span></span>

<span data-ttu-id="308f5-132">オンラインギャラリーにスクリプトを発行するために使用する API キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="308f5-132">Specifies the API key that you want to use to publish a script to the online gallery.</span></span> <span data-ttu-id="308f5-133">API キーは、オンラインギャラリーのプロファイルの一部です。</span><span class="sxs-lookup"><span data-stu-id="308f5-133">The API key is part of your profile in the online gallery.</span></span> <span data-ttu-id="308f5-134">詳細については、「 [API キーの管理](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="308f5-134">For more information see [Managing API keys](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span></span>

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

### <span data-ttu-id="308f5-135">-Path</span><span class="sxs-lookup"><span data-stu-id="308f5-135">-Path</span></span>

<span data-ttu-id="308f5-136">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="308f5-136">Specifies a path to one or more locations.</span></span> <span data-ttu-id="308f5-137">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="308f5-137">Wildcards are permitted.</span></span> <span data-ttu-id="308f5-138">既定の場所は、現在のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="308f5-138">The default location is the current directory.</span></span>

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

### <span data-ttu-id="308f5-139">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="308f5-139">-Repository</span></span>

<span data-ttu-id="308f5-140">を実行して登録されているリポジトリのフレンドリ名を指定し `Register-PSRepository` ます。</span><span class="sxs-lookup"><span data-stu-id="308f5-140">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span>

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

### <span data-ttu-id="308f5-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="308f5-141">-WhatIf</span></span>

<span data-ttu-id="308f5-142">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="308f5-142">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="308f5-143">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="308f5-143">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="308f5-144">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="308f5-144">CommonParameters</span></span>

<span data-ttu-id="308f5-145">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="308f5-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="308f5-146">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="308f5-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="308f5-147">入力</span><span class="sxs-lookup"><span data-stu-id="308f5-147">INPUTS</span></span>

### <span data-ttu-id="308f5-148">System.String</span><span class="sxs-lookup"><span data-stu-id="308f5-148">System.String</span></span>

### <span data-ttu-id="308f5-149">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="308f5-149">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="308f5-150">出力</span><span class="sxs-lookup"><span data-stu-id="308f5-150">OUTPUTS</span></span>

### <span data-ttu-id="308f5-151">System.Object</span><span class="sxs-lookup"><span data-stu-id="308f5-151">System.Object</span></span>

## <span data-ttu-id="308f5-152">注</span><span class="sxs-lookup"><span data-stu-id="308f5-152">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="308f5-153">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="308f5-153">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="308f5-154">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="308f5-154">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="308f5-155">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="308f5-155">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="308f5-156">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="308f5-156">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="308f5-157">関連リンク</span><span class="sxs-lookup"><span data-stu-id="308f5-157">RELATED LINKS</span></span>

[<span data-ttu-id="308f5-158">Find-Script</span><span class="sxs-lookup"><span data-stu-id="308f5-158">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="308f5-159">Install-Script</span><span class="sxs-lookup"><span data-stu-id="308f5-159">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="308f5-160">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="308f5-160">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="308f5-161">Save-Script</span><span class="sxs-lookup"><span data-stu-id="308f5-161">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="308f5-162">Update-Script</span><span class="sxs-lookup"><span data-stu-id="308f5-162">Update-Script</span></span>](Update-Script.md)
