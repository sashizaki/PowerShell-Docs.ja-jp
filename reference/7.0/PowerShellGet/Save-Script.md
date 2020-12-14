---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-script?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Script
ms.openlocfilehash: 240bd1be4cd4a54fc667fade257e07d29434274d
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891458"
---
# <span data-ttu-id="c0f25-103">Save-Script</span><span class="sxs-lookup"><span data-stu-id="c0f25-103">Save-Script</span></span>

## <span data-ttu-id="c0f25-104">概要</span><span class="sxs-lookup"><span data-stu-id="c0f25-104">SYNOPSIS</span></span>
<span data-ttu-id="c0f25-105">スクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-105">Saves a script.</span></span>

## <span data-ttu-id="c0f25-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c0f25-106">SYNTAX</span></span>

### <span data-ttu-id="c0f25-107">NameAndPathParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="c0f25-107">NameAndPathParameterSet (Default)</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c0f25-108">NameAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="c0f25-108">NameAndLiteralPathParameterSet</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c0f25-109">InputObjectAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="c0f25-109">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c0f25-110">InputObjectAndPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="c0f25-110">InputObjectAndPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c0f25-111">Description</span><span class="sxs-lookup"><span data-stu-id="c0f25-111">DESCRIPTION</span></span>

<span data-ttu-id="c0f25-112">コマンドレットでは、 `Save-Script` 指定されたスクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-112">The `Save-Script` cmdlet saves the specified script.</span></span>

## <span data-ttu-id="c0f25-113">例</span><span class="sxs-lookup"><span data-stu-id="c0f25-113">EXAMPLES</span></span>

### <span data-ttu-id="c0f25-114">例 1: スクリプトを保存し、スクリプトのメタデータを検証する</span><span class="sxs-lookup"><span data-stu-id="c0f25-114">Example 1: Save a script and validate the script's metadata</span></span>

<span data-ttu-id="c0f25-115">この例では、リポジトリからのスクリプトがローカルコンピューターに保存され、スクリプトのメタデータが検証されます。</span><span class="sxs-lookup"><span data-stu-id="c0f25-115">In this example, a script from a repository is saved to the local computer and the script's metadata is validated.</span></span>

```powershell
Save-Script -Name Install-VSCode -Repository PSGallery -Path C:\Test\Scripts
Test-ScriptFileInfo -Path C:\Test\Scripts\Install-VSCode.ps1
```

```Output
Version   Name              Author      Description
-------   ----              ------      -----------
1.3       Install-VSCode    Microsoft   This script can be used to easily install Visual Studio Code
```

<span data-ttu-id="c0f25-116">`Save-Script`**name** パラメーターを使用して、スクリプトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-116">`Save-Script` uses the **Name** parameter to specify the script's name.</span></span> <span data-ttu-id="c0f25-117">**Repository** パラメーターは、スクリプトを検索する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-117">The **Repository** parameter specifies where to find the script.</span></span> <span data-ttu-id="c0f25-118">スクリプトは、 **Path** パラメーターで指定した場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="c0f25-118">The script is saved in the location specified by the **Path** parameter.</span></span> <span data-ttu-id="c0f25-119">`Test-ScriptFileInfo`**パス** を指定し、スクリプトのメタデータを検証します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-119">`Test-ScriptFileInfo` specifies the **Path** and validates the script's metadata.</span></span>

## <span data-ttu-id="c0f25-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c0f25-120">PARAMETERS</span></span>

### <span data-ttu-id="c0f25-121">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="c0f25-121">-AcceptLicense</span></span>

<span data-ttu-id="c0f25-122">スクリプトで必要な場合は、使用許諾契約書に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-122">Automatically accept the license agreement if the script requires it.</span></span>

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

### <span data-ttu-id="c0f25-123">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="c0f25-123">-AllowPrerelease</span></span>

<span data-ttu-id="c0f25-124">プレリリースとしてマークされているスクリプトを保存できます。</span><span class="sxs-lookup"><span data-stu-id="c0f25-124">Allows you to save a script marked as a prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c0f25-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c0f25-125">-Confirm</span></span>

<span data-ttu-id="c0f25-126">実行前に確認メッセージを表示 `Save-Script` します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-126">Prompts you for confirmation before running `Save-Script`.</span></span>

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

### <span data-ttu-id="c0f25-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="c0f25-127">-Credential</span></span>

<span data-ttu-id="c0f25-128">スクリプトを保存するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-128">Specifies a user account that has permission to save a script.</span></span>

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

### <span data-ttu-id="c0f25-129">-Force</span><span class="sxs-lookup"><span data-stu-id="c0f25-129">-Force</span></span>

<span data-ttu-id="c0f25-130">`Save-Script`ユーザーの確認を求めることなく強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-130">Forces `Save-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="c0f25-131">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c0f25-131">-InputObject</span></span>

<span data-ttu-id="c0f25-132">**できる psrepositoryiteminfo** オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c0f25-132">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="c0f25-133">たとえば、 `Find-Script` 変数に出力し、その変数を **InputObject** 引数として使用します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-133">For example, output `Find-Script` to a variable and use that variable as the **InputObject** argument.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObjectAndLiteralPathParameterSet, InputObjectAndPathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c0f25-134">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c0f25-134">-LiteralPath</span></span>

<span data-ttu-id="c0f25-135">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-135">Specifies a path to one or more locations.</span></span> <span data-ttu-id="c0f25-136">**LiteralPath** パラメーターの値は、入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c0f25-136">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="c0f25-137">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="c0f25-137">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="c0f25-138">パスにエスケープ文字が含まれている場合は、パスを単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c0f25-138">If the path includes escape characters, enclose the path within single quotation marks.</span></span> <span data-ttu-id="c0f25-139">PowerShell は、単一引用符で囲まれた文字をエスケープシーケンスとして解釈しません。</span><span class="sxs-lookup"><span data-stu-id="c0f25-139">PowerShell doesn't interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndLiteralPathParameterSet, InputObjectAndLiteralPathParameterSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c0f25-140">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="c0f25-140">-MaximumVersion</span></span>

<span data-ttu-id="c0f25-141">保存するスクリプトの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-141">Specifies the maximum, or newest version of the script to save.</span></span> <span data-ttu-id="c0f25-142">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c0f25-142">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c0f25-143">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="c0f25-143">-MinimumVersion</span></span>

<span data-ttu-id="c0f25-144">保存するスクリプトの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-144">Specifies the minimum version of a script to save.</span></span> <span data-ttu-id="c0f25-145">**MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c0f25-145">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c0f25-146">-Name</span><span class="sxs-lookup"><span data-stu-id="c0f25-146">-Name</span></span>

<span data-ttu-id="c0f25-147">保存するスクリプト名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-147">Specifies an array of script names to save.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c0f25-148">-Path</span><span class="sxs-lookup"><span data-stu-id="c0f25-148">-Path</span></span>

<span data-ttu-id="c0f25-149">保存されているモジュールを格納するローカルコンピューター上の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-149">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="c0f25-150">ワイルドカード文字を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="c0f25-150">Accepts wildcard characters.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, InputObjectAndPathParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="c0f25-151">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="c0f25-151">-Proxy</span></span>

<span data-ttu-id="c0f25-152">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-152">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c0f25-153">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="c0f25-153">-ProxyCredential</span></span>

<span data-ttu-id="c0f25-154">**プロキシ** パラメーターによって指定されたプロキシサーバーを使用する権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-154">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="c0f25-155">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="c0f25-155">-Repository</span></span>

<span data-ttu-id="c0f25-156">を実行して登録されているリポジトリのフレンドリ名を指定し `Register-PSRepository` ます。</span><span class="sxs-lookup"><span data-stu-id="c0f25-156">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="c0f25-157">`Get-PSRepository`登録されたリポジトリを表示するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-157">Use `Get-PSRepository` to display registered repositories.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c0f25-158">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="c0f25-158">-RequiredVersion</span></span>

<span data-ttu-id="c0f25-159">保存するスクリプトの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-159">Specifies the exact version number of the script to save.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c0f25-160">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c0f25-160">-WhatIf</span></span>

<span data-ttu-id="c0f25-161">が実行された場合に何が起こるか `Save-Script` を示します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-161">Shows what would happen if `Save-Script` runs.</span></span> <span data-ttu-id="c0f25-162">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c0f25-162">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="c0f25-163">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0f25-163">CommonParameters</span></span>

<span data-ttu-id="c0f25-164">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c0f25-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c0f25-165">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0f25-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c0f25-166">入力</span><span class="sxs-lookup"><span data-stu-id="c0f25-166">INPUTS</span></span>

### <span data-ttu-id="c0f25-167">System.String[]</span><span class="sxs-lookup"><span data-stu-id="c0f25-167">System.String[]</span></span>

### <span data-ttu-id="c0f25-168">システムの管理. PSObject []</span><span class="sxs-lookup"><span data-stu-id="c0f25-168">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="c0f25-169">System.String</span><span class="sxs-lookup"><span data-stu-id="c0f25-169">System.String</span></span>

### <span data-ttu-id="c0f25-170">System.Uri</span><span class="sxs-lookup"><span data-stu-id="c0f25-170">System.Uri</span></span>

### <span data-ttu-id="c0f25-171">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="c0f25-171">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="c0f25-172">出力</span><span class="sxs-lookup"><span data-stu-id="c0f25-172">OUTPUTS</span></span>

### <span data-ttu-id="c0f25-173">System.Object</span><span class="sxs-lookup"><span data-stu-id="c0f25-173">System.Object</span></span>

## <span data-ttu-id="c0f25-174">注</span><span class="sxs-lookup"><span data-stu-id="c0f25-174">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0f25-175">2020年4月の時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン1.0 と1.1 がサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c0f25-175">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="c0f25-176">TLS 1.2 以降を使用していない場合は、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-176">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="c0f25-177">次のコマンドを使用して、TLS 1.2 を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c0f25-177">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="c0f25-178">詳細については、PowerShell ブログの [お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0f25-178">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="c0f25-179">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c0f25-179">RELATED LINKS</span></span>

[<span data-ttu-id="c0f25-180">Find-Script</span><span class="sxs-lookup"><span data-stu-id="c0f25-180">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="c0f25-181">Install-Script</span><span class="sxs-lookup"><span data-stu-id="c0f25-181">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="c0f25-182">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="c0f25-182">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="c0f25-183">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="c0f25-183">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

[<span data-ttu-id="c0f25-184">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="c0f25-184">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="c0f25-185">Update-Script</span><span class="sxs-lookup"><span data-stu-id="c0f25-185">Update-Script</span></span>](Update-Script.md)
