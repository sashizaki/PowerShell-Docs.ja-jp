---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-script?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Script
ms.openlocfilehash: 2f672cbb814b0641411bb11ffb17bd1ecef96dda
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99602167"
---
# <span data-ttu-id="74102-102">Save-Script</span><span class="sxs-lookup"><span data-stu-id="74102-102">Save-Script</span></span>

## <span data-ttu-id="74102-103">概要</span><span class="sxs-lookup"><span data-stu-id="74102-103">SYNOPSIS</span></span>
<span data-ttu-id="74102-104">スクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="74102-104">Saves a script.</span></span>

## <span data-ttu-id="74102-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="74102-105">SYNTAX</span></span>

### <span data-ttu-id="74102-106">NameAndPathParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="74102-106">NameAndPathParameterSet (Default)</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="74102-107">NameAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="74102-107">NameAndLiteralPathParameterSet</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="74102-108">InputObjectAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="74102-108">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="74102-109">InputObjectAndPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="74102-109">InputObjectAndPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="74102-110">Description</span><span class="sxs-lookup"><span data-stu-id="74102-110">DESCRIPTION</span></span>

<span data-ttu-id="74102-111">コマンドレットでは、 `Save-Script` 指定されたスクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="74102-111">The `Save-Script` cmdlet saves the specified script.</span></span>

## <span data-ttu-id="74102-112">例</span><span class="sxs-lookup"><span data-stu-id="74102-112">EXAMPLES</span></span>

### <span data-ttu-id="74102-113">例 1: スクリプトを保存し、スクリプトのメタデータを検証する</span><span class="sxs-lookup"><span data-stu-id="74102-113">Example 1: Save a script and validate the script's metadata</span></span>

<span data-ttu-id="74102-114">この例では、リポジトリからのスクリプトがローカルコンピューターに保存され、スクリプトのメタデータが検証されます。</span><span class="sxs-lookup"><span data-stu-id="74102-114">In this example, a script from a repository is saved to the local computer and the script's metadata is validated.</span></span>

```powershell
Save-Script -Name Install-VSCode -Repository PSGallery -Path C:\Test\Scripts
Test-ScriptFileInfo -Path C:\Test\Scripts\Install-VSCode.ps1
```

```Output
Version   Name              Author      Description
-------   ----              ------      -----------
1.3       Install-VSCode    Microsoft   This script can be used to easily install Visual Studio Code
```

<span data-ttu-id="74102-115">`Save-Script`**name** パラメーターを使用して、スクリプトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="74102-115">`Save-Script` uses the **Name** parameter to specify the script's name.</span></span> <span data-ttu-id="74102-116">**Repository** パラメーターは、スクリプトを検索する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="74102-116">The **Repository** parameter specifies where to find the script.</span></span> <span data-ttu-id="74102-117">スクリプトは、 **Path** パラメーターで指定した場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="74102-117">The script is saved in the location specified by the **Path** parameter.</span></span> <span data-ttu-id="74102-118">`Test-ScriptFileInfo`**パス** を指定し、スクリプトのメタデータを検証します。</span><span class="sxs-lookup"><span data-stu-id="74102-118">`Test-ScriptFileInfo` specifies the **Path** and validates the script's metadata.</span></span>

## <span data-ttu-id="74102-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="74102-119">PARAMETERS</span></span>

### <span data-ttu-id="74102-120">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="74102-120">-AcceptLicense</span></span>

<span data-ttu-id="74102-121">スクリプトで必要な場合は、使用許諾契約書に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="74102-121">Automatically accept the license agreement if the script requires it.</span></span>

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

### <span data-ttu-id="74102-122">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="74102-122">-AllowPrerelease</span></span>

<span data-ttu-id="74102-123">プレリリースとしてマークされているスクリプトを保存できます。</span><span class="sxs-lookup"><span data-stu-id="74102-123">Allows you to save a script marked as a prerelease.</span></span>

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

### <span data-ttu-id="74102-124">-Confirm</span><span class="sxs-lookup"><span data-stu-id="74102-124">-Confirm</span></span>

<span data-ttu-id="74102-125">実行前に確認メッセージを表示 `Save-Script` します。</span><span class="sxs-lookup"><span data-stu-id="74102-125">Prompts you for confirmation before running `Save-Script`.</span></span>

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

### <span data-ttu-id="74102-126">-Credential</span><span class="sxs-lookup"><span data-stu-id="74102-126">-Credential</span></span>

<span data-ttu-id="74102-127">スクリプトを保存するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="74102-127">Specifies a user account that has permission to save a script.</span></span>

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

### <span data-ttu-id="74102-128">-Force</span><span class="sxs-lookup"><span data-stu-id="74102-128">-Force</span></span>

<span data-ttu-id="74102-129">`Save-Script`ユーザーの確認を求めることなく強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="74102-129">Forces `Save-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="74102-130">-InputObject</span><span class="sxs-lookup"><span data-stu-id="74102-130">-InputObject</span></span>

<span data-ttu-id="74102-131">**できる psrepositoryiteminfo** オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="74102-131">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="74102-132">たとえば、 `Find-Script` 変数に出力し、その変数を **InputObject** 引数として使用します。</span><span class="sxs-lookup"><span data-stu-id="74102-132">For example, output `Find-Script` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="74102-133">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="74102-133">-LiteralPath</span></span>

<span data-ttu-id="74102-134">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="74102-134">Specifies a path to one or more locations.</span></span> <span data-ttu-id="74102-135">**LiteralPath** パラメーターの値は、入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="74102-135">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="74102-136">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="74102-136">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="74102-137">パスにエスケープ文字が含まれている場合は、パスを単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="74102-137">If the path includes escape characters, enclose the path within single quotation marks.</span></span> <span data-ttu-id="74102-138">PowerShell は、単一引用符で囲まれた文字をエスケープシーケンスとして解釈しません。</span><span class="sxs-lookup"><span data-stu-id="74102-138">PowerShell doesn't interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

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

### <span data-ttu-id="74102-139">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="74102-139">-MaximumVersion</span></span>

<span data-ttu-id="74102-140">保存するスクリプトの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="74102-140">Specifies the maximum, or newest version of the script to save.</span></span> <span data-ttu-id="74102-141">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="74102-141">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="74102-142">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="74102-142">-MinimumVersion</span></span>

<span data-ttu-id="74102-143">保存するスクリプトの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="74102-143">Specifies the minimum version of a script to save.</span></span> <span data-ttu-id="74102-144">**MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="74102-144">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="74102-145">-Name</span><span class="sxs-lookup"><span data-stu-id="74102-145">-Name</span></span>

<span data-ttu-id="74102-146">保存するスクリプト名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="74102-146">Specifies an array of script names to save.</span></span>

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

### <span data-ttu-id="74102-147">-Path</span><span class="sxs-lookup"><span data-stu-id="74102-147">-Path</span></span>

<span data-ttu-id="74102-148">保存されているモジュールを格納するローカルコンピューター上の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="74102-148">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="74102-149">ワイルドカード文字を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="74102-149">Accepts wildcard characters.</span></span>

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

### <span data-ttu-id="74102-150">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="74102-150">-Proxy</span></span>

<span data-ttu-id="74102-151">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="74102-151">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="74102-152">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="74102-152">-ProxyCredential</span></span>

<span data-ttu-id="74102-153">**プロキシ** パラメーターによって指定されたプロキシサーバーを使用する権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="74102-153">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="74102-154">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="74102-154">-Repository</span></span>

<span data-ttu-id="74102-155">を実行して登録されているリポジトリのフレンドリ名を指定し `Register-PSRepository` ます。</span><span class="sxs-lookup"><span data-stu-id="74102-155">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="74102-156">`Get-PSRepository`登録されたリポジトリを表示するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="74102-156">Use `Get-PSRepository` to display registered repositories.</span></span>

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

### <span data-ttu-id="74102-157">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="74102-157">-RequiredVersion</span></span>

<span data-ttu-id="74102-158">保存するスクリプトの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="74102-158">Specifies the exact version number of the script to save.</span></span>

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

### <span data-ttu-id="74102-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="74102-159">-WhatIf</span></span>

<span data-ttu-id="74102-160">が実行された場合に何が起こるか `Save-Script` を示します。</span><span class="sxs-lookup"><span data-stu-id="74102-160">Shows what would happen if `Save-Script` runs.</span></span> <span data-ttu-id="74102-161">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="74102-161">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="74102-162">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="74102-162">CommonParameters</span></span>

<span data-ttu-id="74102-163">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="74102-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="74102-164">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74102-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="74102-165">入力</span><span class="sxs-lookup"><span data-stu-id="74102-165">INPUTS</span></span>

### <span data-ttu-id="74102-166">System.String[]</span><span class="sxs-lookup"><span data-stu-id="74102-166">System.String[]</span></span>

### <span data-ttu-id="74102-167">システムの管理. PSObject []</span><span class="sxs-lookup"><span data-stu-id="74102-167">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="74102-168">System.String</span><span class="sxs-lookup"><span data-stu-id="74102-168">System.String</span></span>

### <span data-ttu-id="74102-169">System.Uri</span><span class="sxs-lookup"><span data-stu-id="74102-169">System.Uri</span></span>

### <span data-ttu-id="74102-170">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="74102-170">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="74102-171">出力</span><span class="sxs-lookup"><span data-stu-id="74102-171">OUTPUTS</span></span>

### <span data-ttu-id="74102-172">System.Object</span><span class="sxs-lookup"><span data-stu-id="74102-172">System.Object</span></span>

## <span data-ttu-id="74102-173">注</span><span class="sxs-lookup"><span data-stu-id="74102-173">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74102-174">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="74102-174">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="74102-175">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="74102-175">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="74102-176">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="74102-176">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="74102-177">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74102-177">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="74102-178">関連リンク</span><span class="sxs-lookup"><span data-stu-id="74102-178">RELATED LINKS</span></span>

[<span data-ttu-id="74102-179">Find-Script</span><span class="sxs-lookup"><span data-stu-id="74102-179">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="74102-180">Install-Script</span><span class="sxs-lookup"><span data-stu-id="74102-180">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="74102-181">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="74102-181">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="74102-182">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="74102-182">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

[<span data-ttu-id="74102-183">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="74102-183">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="74102-184">Update-Script</span><span class="sxs-lookup"><span data-stu-id="74102-184">Update-Script</span></span>](Update-Script.md)
