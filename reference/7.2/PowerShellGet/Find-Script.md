---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/find-script?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Script
ms.openlocfilehash: 8095c895f2c9645647f27e72cc95a502684950bf
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99599709"
---
# <span data-ttu-id="30c31-102">Find-Script</span><span class="sxs-lookup"><span data-stu-id="30c31-102">Find-Script</span></span>

## <span data-ttu-id="30c31-103">概要</span><span class="sxs-lookup"><span data-stu-id="30c31-103">SYNOPSIS</span></span>
<span data-ttu-id="30c31-104">スクリプトを検索します。</span><span class="sxs-lookup"><span data-stu-id="30c31-104">Finds a script.</span></span>

## <span data-ttu-id="30c31-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="30c31-105">SYNTAX</span></span>

```
Find-Script [[-Name] <String[]>] [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-AllVersions] [-IncludeDependencies] [-Filter <String>] [-Tag <String[]>]
 [-Includes <String[]>] [-Command <String[]>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [-Credential <PSCredential>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="30c31-106">Description</span><span class="sxs-lookup"><span data-stu-id="30c31-106">DESCRIPTION</span></span>

<span data-ttu-id="30c31-107">**検索スクリプト** コマンドレットは、登録されているリポジトリ内の指定したスクリプトを検索します。</span><span class="sxs-lookup"><span data-stu-id="30c31-107">The **Find-Script** cmdlet finds a specified script in registered repositories.</span></span>

## <span data-ttu-id="30c31-108">例</span><span class="sxs-lookup"><span data-stu-id="30c31-108">EXAMPLES</span></span>

### <span data-ttu-id="30c31-109">例 1: 使用可能なすべてのスクリプトを検索する</span><span class="sxs-lookup"><span data-stu-id="30c31-109">Example 1: Find all available scripts</span></span>

```
PS C:\> Find-Script
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Fabrikam-ClientScript               Script     LocalRepo1           Description for the Fabrikam-ClientScript script
2.5        Fabrikam-Script                     Script     LocalRepo1           Description for the Fabrikam-Script script
2.5        Fabrikam-ServerScript               Script     LocalRepo1           Description for the Fabrikam-ServerScript script
2.5        Required-Script1                    Script     LocalRepo1           Description for the Required-Script1 script
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
2.5        Required-Script3                    Script     LocalRepo1           Description for the Required-Script3 script
2.0        Script-WithDependencies1            Script     LocalRepo1           Description for the Script-WithDependencies1 script
2.0        Script-WithDependencies2            Script     LocalRepo1           Description for the Script-WithDependencies2 script
2.0        Start-WFContosoServer               Script     LocalRepo1           Start-WFContosoServer Script example
2.1        Test-Script1                        Script     LocalRepo1           Test-Script1 Script example
2.0        Test-Script2                        Script     LocalRepo1           Test-Script2 Script example
1.0        TestRunbook                         Script     LocalRepo1           Contoso Script example
```

<span data-ttu-id="30c31-110">このコマンドは、使用可能なすべてのスクリプトを検索します。</span><span class="sxs-lookup"><span data-stu-id="30c31-110">This command finds all available scripts.</span></span>

### <span data-ttu-id="30c31-111">例 2: 名前を指定してスクリプトを検索する</span><span class="sxs-lookup"><span data-stu-id="30c31-111">Example 2: Find a script by name</span></span>

```
PS C:\> Find-Script -Name "Start-WFContosoServer"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.0        Start-WFContosoServer               Script     LocalRepo1           Start-WFContosoServer Script example
```

<span data-ttu-id="30c31-112">このコマンドは、WFContosoServer という名前のスクリプトを検索します。</span><span class="sxs-lookup"><span data-stu-id="30c31-112">This command find the script named Start-WFContosoServer.</span></span>

### <span data-ttu-id="30c31-113">例 3: 名前、必要なバージョン、および指定されたリポジトリからスクリプトを検索する</span><span class="sxs-lookup"><span data-stu-id="30c31-113">Example 3: Find a script by name, required version, and from a specified repository</span></span>

```
PS C:\> Find-Script -Name "Required-Script2" -RequiredVersion 2.0 -Repository "LocalRepo01"
```

<span data-ttu-id="30c31-114">このコマンドは、LocalRepo01 リポジトリで名前と必要なバージョンを使ってスクリプトを検索します。</span><span class="sxs-lookup"><span data-stu-id="30c31-114">This command finds a script by name and required version in the LocalRepo01 repository.</span></span>

### <span data-ttu-id="30c31-115">例 4: スクリプトを検索し、出力を一覧として書式設定する</span><span class="sxs-lookup"><span data-stu-id="30c31-115">Example 4: Find a script and format the output as a list</span></span>

```
PS C:\> Find-Script -Name "Required-Script2" -RequiredVersion 2.0 -Repository "LocalRepo1" | Format-List * -Force
Name                       : Required-Script2
Version                    : 2.0
Type                       : Script
Description                : Description for the Required-Script2 script
Author                     : pattif
CompanyName                : Microsoft Corporation
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
PublishedDate              : 8/14/2015 2:37:01 PM
LicenseUri                 : http://required-script2.com/license
ProjectUri                 : http://required-script2.com/
IconUri                    : http://required-script2.com/icon
Tags                       : {, Tag1, Tag2, Tag-Required-Script2-2.0...}
Includes                   : {Function, DscResource, Cmdlet, Command}
PowerShellGetFormatVersion :
ReleaseNotes               : Required-Script2 release notes
Dependencies               : {}
RepositorySourceLocation   : C:\MyLocalRepo
Repository                 : LocalRepo01
PackageManagementProvider  : NuGet
```

<span data-ttu-id="30c31-116">このコマンドは、LocalRepo1 リポジトリ内の Required-Script2 を検索し、結果として得られる **できる psrepositoryiteminfo** オブジェクトを Format-List コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="30c31-116">This command finds Required-Script2 in the LocalRepo1 repository, and then passes the resulting **PSRepositoryItemInfo** object to the Format-List cmdlet.</span></span>

### <span data-ttu-id="30c31-117">例 5: 指定したバージョンの範囲でスクリプトを検索する</span><span class="sxs-lookup"><span data-stu-id="30c31-117">Example 5: Find a script in the specified version range</span></span>

```
PS C:\> Find-Script -Name "Required-Script2" -MinimumVersion 2.1 -MaximumVersion 2.5 -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="30c31-118">このコマンドは、LocalRepo1 リポジトリ内のバージョン2.1 と2.5 の間の RequiredScript2 のすべてのバージョンを検索します。</span><span class="sxs-lookup"><span data-stu-id="30c31-118">This command finds all versions of RequiredScript2 between versions 2.1 and 2.5 in the LocalRepo1 respository.</span></span>

### <span data-ttu-id="30c31-119">例 6: スクリプトのすべてのバージョンを検索する</span><span class="sxs-lookup"><span data-stu-id="30c31-119">Example 6: Find all versions of a script</span></span>

```
PS C:\> Find-Script -Name "Required-Script02" -AllVersions
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
1.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
2.0        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="30c31-120">このコマンドは、Script02 のすべてのバージョンを検索します。</span><span class="sxs-lookup"><span data-stu-id="30c31-120">This command finds all versions of Required-Script02.</span></span>

### <span data-ttu-id="30c31-121">例 7: スクリプトとその依存関係を検索する</span><span class="sxs-lookup"><span data-stu-id="30c31-121">Example 7: Find a script and its dependencies</span></span>

```
PS C:\> Find-Script -Name "Script-WithDependencies1" -IncludeDependencies -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Script-WithDependencies1            Script     LocalRepo1           Description for the Script-WithDependencies1 script
2.0        RequiredModule3                     Script     LocalRepo1           RequiredModule3 module
2.5        Required-Script1                    Script     LocalRepo1           Description for the Required-Script1 script
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="30c31-122">このコマンドは、スクリプトとその依存関係を検索します。</span><span class="sxs-lookup"><span data-stu-id="30c31-122">This command finds a script and its dependencies.</span></span>

### <span data-ttu-id="30c31-123">例 8: 指定したタグを持つスクリプトを検索する</span><span class="sxs-lookup"><span data-stu-id="30c31-123">Example 8: Find scripts with the specified tag</span></span>

```
PS C:\> Find-Script -Tag "Tag1" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Fabrikam-ClientScript               Script     LocalRepo1           Description for the Fabrikam-ClientScript script
```

<span data-ttu-id="30c31-124">このコマンドは、LocalRepo1 リポジトリに Tag1 タグがあるスクリプトを検索します。</span><span class="sxs-lookup"><span data-stu-id="30c31-124">This command finds scripts that have the tag Tag1 in the LocalRepo1 repository</span></span>

### <span data-ttu-id="30c31-125">例 9: 指定したコマンド名を使用してスクリプトを検索する</span><span class="sxs-lookup"><span data-stu-id="30c31-125">Example 9: Find scripts with specified command name</span></span>

```
PS C:\> Find-Script -Command Test-FunctionFromScript_Required-Script3 -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script3                    Script     LocalRepo1           Description for the Required-Script3 script
```

<span data-ttu-id="30c31-126">このコマンドは、指定されたコマンド名を含むスクリプトを検索します。</span><span class="sxs-lookup"><span data-stu-id="30c31-126">This command finds a script that contains the specified command name.</span></span>

### <span data-ttu-id="30c31-127">例 10: ワークフローを使用してスクリプトを検索する</span><span class="sxs-lookup"><span data-stu-id="30c31-127">Example 10: Find scripts with workflows</span></span>

```
PS C:\> Find-Script -Includes "Workflow" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Fabrikam-ClientScript               Script     LocalRepo1           Description for the Fabrikam-ClientScript script
1.0        Fabrikam-Script                     Script     LocalRepo1           Description for the Fabrikam-Script script
```

<span data-ttu-id="30c31-128">このコマンドは、LocalRepo1 リポジトリ内のワークフロースクリプトを検索します。</span><span class="sxs-lookup"><span data-stu-id="30c31-128">This command finds workflow scripts in the LocalRepo1 repository.</span></span>

### <span data-ttu-id="30c31-129">例 11: ワイルドカードを使用してスクリプトを検索する</span><span class="sxs-lookup"><span data-stu-id="30c31-129">Example 11: Find scripts using wildcards</span></span>

```
PS C:\> Find-Script -Name "Required-Script*" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
```

<span data-ttu-id="30c31-130">このコマンドは、ワイルドカード文字 (\*) を使用して、Required-Script で始まるスクリプトを検索します。</span><span class="sxs-lookup"><span data-stu-id="30c31-130">This command uses the wildcard character (\*) to find scripts that begin with Required-Script.</span></span>

## <span data-ttu-id="30c31-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="30c31-131">PARAMETERS</span></span>

### <span data-ttu-id="30c31-132">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="30c31-132">-AllowPrerelease</span></span>

<span data-ttu-id="30c31-133">プレリリースとしてマークされた結果スクリプトにを含めます。</span><span class="sxs-lookup"><span data-stu-id="30c31-133">Includes in the results scripts marked as a prerelease.</span></span>

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

### <span data-ttu-id="30c31-134">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="30c31-134">-AllVersions</span></span>

<span data-ttu-id="30c31-135">この操作がすべてのスクリプトのバージョンを検索することを示します。</span><span class="sxs-lookup"><span data-stu-id="30c31-135">Indicates that this operation finds all script versions.</span></span>

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

### <span data-ttu-id="30c31-136">-Command</span><span class="sxs-lookup"><span data-stu-id="30c31-136">-Command</span></span>

<span data-ttu-id="30c31-137">スクリプト内で検索するコマンドの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="30c31-137">Specifies an array of commands to find in scripts.</span></span>
<span data-ttu-id="30c31-138">コマンドは、関数またはワークフローにすることができます。</span><span class="sxs-lookup"><span data-stu-id="30c31-138">A command can be a function or workflow.</span></span>

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

### <span data-ttu-id="30c31-139">-Credential</span><span class="sxs-lookup"><span data-stu-id="30c31-139">-Credential</span></span>

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

### <span data-ttu-id="30c31-140">-Filter</span><span class="sxs-lookup"><span data-stu-id="30c31-140">-Filter</span></span>

<span data-ttu-id="30c31-141">PackageManagement プロバイダー固有の検索構文に基づいてスクリプトを検索します。</span><span class="sxs-lookup"><span data-stu-id="30c31-141">Finds scripts based on the PackageManagement provider-specific search syntax.</span></span>

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

### <span data-ttu-id="30c31-142">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="30c31-142">-IncludeDependencies</span></span>

<span data-ttu-id="30c31-143">この操作で、 *Name* パラメーターに指定されたスクリプトに依存するすべてのスクリプトを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="30c31-143">Indicates that this operation gets all scripts that are dependent upon the script specified in the *Name* parameter.</span></span>

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

### <span data-ttu-id="30c31-144">-インクルード</span><span class="sxs-lookup"><span data-stu-id="30c31-144">-Includes</span></span>

<span data-ttu-id="30c31-145">取得するスクリプトの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="30c31-145">Specifies type of script to get.</span></span>
<span data-ttu-id="30c31-146">このパラメーターに指定できる値は、Function、Workflow です。</span><span class="sxs-lookup"><span data-stu-id="30c31-146">The acceptable values for this parameter are: Function, Workflow.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Function, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30c31-147">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="30c31-147">-MaximumVersion</span></span>

<span data-ttu-id="30c31-148">検索するスクリプトの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="30c31-148">Specifies the maximum, or newest, version of the script to find.</span></span>
<span data-ttu-id="30c31-149">*MaximumVersion* および *RequiredVersion* パラメーターは相互に排他的です。両方のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="30c31-149">The *MaximumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="30c31-150">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="30c31-150">-MinimumVersion</span></span>

<span data-ttu-id="30c31-151">検索するスクリプトの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="30c31-151">Specifies the minimum version of the script to find.</span></span>
<span data-ttu-id="30c31-152">*MinimumVersion* および *RequiredVersion* パラメーターは相互に排他的です。両方のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="30c31-152">The *MinimumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="30c31-153">-Name</span><span class="sxs-lookup"><span data-stu-id="30c31-153">-Name</span></span>

<span data-ttu-id="30c31-154">検索するスクリプトの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="30c31-154">Specifies an array of names of scripts to find.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="30c31-155">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="30c31-155">-Proxy</span></span>

<span data-ttu-id="30c31-156">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="30c31-156">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="30c31-157">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="30c31-157">-ProxyCredential</span></span>

<span data-ttu-id="30c31-158">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="30c31-158">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="30c31-159">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="30c31-159">-Repository</span></span>

<span data-ttu-id="30c31-160">Register-psrepository を実行して登録されているリポジトリのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="30c31-160">Specifies the friendly name of a repository that has been registered by running Register-PSRepository.</span></span>

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

### <span data-ttu-id="30c31-161">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="30c31-161">-RequiredVersion</span></span>

<span data-ttu-id="30c31-162">検索するスクリプトの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="30c31-162">Specifies the exact version number of the script to find.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="30c31-163">-Tag</span><span class="sxs-lookup"><span data-stu-id="30c31-163">-Tag</span></span>

<span data-ttu-id="30c31-164">タグの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="30c31-164">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="30c31-165">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="30c31-165">CommonParameters</span></span>

<span data-ttu-id="30c31-166">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="30c31-166">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="30c31-167">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30c31-167">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="30c31-168">入力</span><span class="sxs-lookup"><span data-stu-id="30c31-168">INPUTS</span></span>

### <span data-ttu-id="30c31-169">System.String[]</span><span class="sxs-lookup"><span data-stu-id="30c31-169">System.String[]</span></span>

### <span data-ttu-id="30c31-170">System.String</span><span class="sxs-lookup"><span data-stu-id="30c31-170">System.String</span></span>

### <span data-ttu-id="30c31-171">System.Uri</span><span class="sxs-lookup"><span data-stu-id="30c31-171">System.Uri</span></span>

### <span data-ttu-id="30c31-172">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="30c31-172">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="30c31-173">出力</span><span class="sxs-lookup"><span data-stu-id="30c31-173">OUTPUTS</span></span>

### <span data-ttu-id="30c31-174">できる psrepositoryiteminfo</span><span class="sxs-lookup"><span data-stu-id="30c31-174">PSRepositoryItemInfo</span></span>

## <span data-ttu-id="30c31-175">注</span><span class="sxs-lookup"><span data-stu-id="30c31-175">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30c31-176">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="30c31-176">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="30c31-177">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="30c31-177">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="30c31-178">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="30c31-178">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="30c31-179">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30c31-179">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="30c31-180">関連リンク</span><span class="sxs-lookup"><span data-stu-id="30c31-180">RELATED LINKS</span></span>

[<span data-ttu-id="30c31-181">Install-Script</span><span class="sxs-lookup"><span data-stu-id="30c31-181">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="30c31-182">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="30c31-182">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="30c31-183">Save-Script</span><span class="sxs-lookup"><span data-stu-id="30c31-183">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="30c31-184">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="30c31-184">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="30c31-185">Update-Script</span><span class="sxs-lookup"><span data-stu-id="30c31-185">Update-Script</span></span>](Update-Script.md)
