---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/install-script?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Script
ms.openlocfilehash: dd4e8169310f23182697ba6bf4263d916f747b84
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211099"
---
# <span data-ttu-id="666f4-103">Install-Script</span><span class="sxs-lookup"><span data-stu-id="666f4-103">Install-Script</span></span>

## <span data-ttu-id="666f4-104">概要</span><span class="sxs-lookup"><span data-stu-id="666f4-104">SYNOPSIS</span></span>
<span data-ttu-id="666f4-105">スクリプトをインストールします。</span><span class="sxs-lookup"><span data-stu-id="666f4-105">Installs a script.</span></span>

## <span data-ttu-id="666f4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="666f4-106">SYNTAX</span></span>

### <span data-ttu-id="666f4-107">NameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="666f4-107">NameParameterSet (Default)</span></span>

```
Install-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Scope <String>] [-NoPathUpdate]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="666f4-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="666f4-108">InputObject</span></span>

```
Install-Script [-InputObject] <PSObject[]> [-Scope <String>] [-NoPathUpdate] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="666f4-109">Description</span><span class="sxs-lookup"><span data-stu-id="666f4-109">DESCRIPTION</span></span>

<span data-ttu-id="666f4-110">`Install-Script`コマンドレットは、リポジトリからスクリプトペイロードを取得し、ペイロードが有効な PowerShell スクリプトであることを確認して、スクリプトファイルを指定したインストール場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="666f4-110">The `Install-Script` cmdlet acquires a script payload from a repository, verifies that the payload is a valid PowerShell script, and copies the script file to a specified installation location.</span></span>

<span data-ttu-id="666f4-111">に対して動作する既定のリポジトリ `Install-Script` は `Register-PSRepository` 、、、 `Set-PSRepository` 、およびコマンドレットを使用して構成 `Unregister-PSRepository` `Get-PSRepository` できます。</span><span class="sxs-lookup"><span data-stu-id="666f4-111">The default repositories `Install-Script` operates against are configurable through the `Register-PSRepository`, `Set-PSRepository`, `Unregister-PSRepository`, and `Get-PSRepository` cmdlets.</span></span> <span data-ttu-id="666f4-112">複数のリポジトリに対して操作を実行する場合、では、 `Install-Script` 最初のリポジトリから、指定した検索条件 ( **Name** 、 **MinimumVersion** 、または **MaximumVersion** ) に一致する最初のスクリプトが、エラーなしでインストールされます。</span><span class="sxs-lookup"><span data-stu-id="666f4-112">When operating against multiple repositories, `Install-Script` installs the first script that matches the specified search criteria ( **Name** , **MinimumVersion** , or **MaximumVersion** ) from the first repository without any error.</span></span>

## <span data-ttu-id="666f4-113">例</span><span class="sxs-lookup"><span data-stu-id="666f4-113">EXAMPLES</span></span>

### <span data-ttu-id="666f4-114">例 1: スクリプトを検索してインストールする</span><span class="sxs-lookup"><span data-stu-id="666f4-114">Example 1: Find a script and install it</span></span>

```
PS C:\> Find-Script -Repository "Local1" -Name "Required-Script2"
Version    Name                           Type       Repository           Description
-------    ----                           ----       ----------           -----------
2.5        Required-Script2               Script     local1               Description for the Required-Script2 script

PS C:\> Find-Script -Repository "Local1" -Name "Required-Script2" | Install-Script
PS C:\> Get-Command -Name "Required-Script2"
CommandType     Name                      Version    Source
-----------     ----                      -------    ------
ExternalScript  Required-Script2.ps1      2.0       C:\Users\pattif\Documents\WindowsPowerShell\Scripts\Required-Script2.ps1

PS C:\> Get-InstalledScript -Name "Required-Script2"
Version    Name                  Type     Repository           Description
-------    ----                  ----     ----------           -----------
2.5        Required-Script2      Script   local1               Description for the Required-Script2 script

PS C:\> Get-InstalledScript -Name "Required-Script2" | Format-List *
Name                       : Required-Script2
Version                    : 2.5
Type                       : Script
Description                : Description for the Required-Script2 script
Author                     : pattif
CompanyName                :
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
PublishedDate              : 8/15/2015 12:42:39 AM
LicenseUri                 : http://required-script2.com/license
ProjectUri                 : http://required-script2.com/
IconUri                    : http://required-script2.com/icon
Tags                       : {Tag1, Tag2, Tag-Required-Script2-2.5, PSScript...}
Includes                   : {Function, DscResource, Cmdlet, Command}
PowerShellGetFormatVersion :
ReleaseNotes               : Required-Script2 release notes
Dependencies               : {}
RepositorySourceLocation   : http://pattif-dev:8765/api/v2/
Repository                 : local1
PackageManagementProvider  : NuGet
InstalledLocation          : C:\Users\pattif\Documents\WindowsPowerShell\Scripts
```

<span data-ttu-id="666f4-115">最初のコマンドは、Local1 リポジトリからという名前のスクリプトを検索 `Required-Script2` し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="666f4-115">The first command finds the script named `Required-Script2` from the Local1 repository and displays the results.</span></span>

<span data-ttu-id="666f4-116">2番目のコマンドは、スクリプトを検索し、パイプライン演算子を使用してそれをコマンド `Required-Script2` レットに渡して `Install-Script` インストールします。</span><span class="sxs-lookup"><span data-stu-id="666f4-116">The second command finds the `Required-Script2` script, and then uses the pipeline operator to pass it to the `Install-Script` cmdlet to install it.</span></span>

<span data-ttu-id="666f4-117">3番目のコマンドは、 `Get-Command` コマンドレットを使用してを取得し、 `Required-Script2` 結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="666f4-117">The third command uses the `Get-Command` cmdlet to get `Required-Script2`, and then displays the results.</span></span>

<span data-ttu-id="666f4-118">4番目のコマンドは、 `Get-InstalledScript` コマンドレットを使用して結果を取得 `Required-Script2` し、表示します。</span><span class="sxs-lookup"><span data-stu-id="666f4-118">The fourth command uses the `Get-InstalledScript` cmdlet to get `Required-Script2` and display the results.</span></span>

<span data-ttu-id="666f4-119">5番目のコマンドは、パイプライン演算子を取得して使用し、 `Required-Script2` コマンドレットに渡して `Format-List` 出力を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="666f4-119">The fifth command gets `Required-Script2` and uses the pipeline operator to pass it to the `Format-List` cmdlet to format the output.</span></span>

### <span data-ttu-id="666f4-120">例 2: AllUsers スコープでスクリプトをインストールする</span><span class="sxs-lookup"><span data-stu-id="666f4-120">Example 2: Install a script with AllUsers scope</span></span>

```
PS C:\> Install-Script -Repository "Local1" -Name "Required-Script3" -Scope "AllUsers"
PS C:\> Get-InstalledScript -Name "Required-Script3"
Version    Name                  Type       Repository    Description
-------    ----                  ----       ----------    -----------
2.5        Required-Script3      Script     local1        Description for the Required-Script3 script

PS C:\> Get-InstalledScript -Name "Required-Script3" | Format-List *
Name                       : Required-Script3
Version                    : 2.5
Type                       : Script
Description                : Description for the Required-Script3 script
Author                     : pattif
CompanyName                :
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
PublishedDate              : 8/15/2015 12:42:45 AM
LicenseUri                 : http://required-script3.com/license
ProjectUri                 : http://required-script3.com/
IconUri                    : http://required-script3.com/icon
Tags                       : {Tag1, Tag2, Tag-Required-Script3-2.5, PSScript...}
Includes                   : {Function, DscResource, Cmdlet, Command}
PowerShellGetFormatVersion :
ReleaseNotes               : Required-Script3 release notes
Dependencies               : {}
RepositorySourceLocation   : http://pattif-dev:8765/api/v2/
Repository                 : local1
PackageManagementProvider  : NuGet
InstalledLocation          : C:\Program Files\WindowsPowerShell\Scripts
```

<span data-ttu-id="666f4-121">最初のコマンドは、という名前のスクリプトをインストール `Required-Script3` し、それに AllUsers スコープを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="666f4-121">The first command installs the script named `Required-Script3` and assigns it AllUsers scope.</span></span>

<span data-ttu-id="666f4-122">2番目のコマンドは、インストールされているスクリプトを取得 `Required-Script3` し、それに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="666f4-122">The second command gets the installed script `Required-Script3` and displays information about it.</span></span>

<span data-ttu-id="666f4-123">3番目のコマンドは、パイプライン演算子を取得して使用し、 `Required-Script3` コマンドレットに渡して `Format-List` 出力を書式設定します。</span><span class="sxs-lookup"><span data-stu-id="666f4-123">The third command gets `Required-Script3` and uses the pipeline operator to pass it to the `Format-List` cmdlet to format the output.</span></span>

### <span data-ttu-id="666f4-124">例 3: スクリプトとその依存関係をインストールする</span><span class="sxs-lookup"><span data-stu-id="666f4-124">Example 3: Install a script and its dependencies</span></span>

```
PS C:\> Find-Script -Repository "Local1" -Name "Script-WithDependencies2" -IncludeDependencies
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.0        Script-WithDependencies2    Script     local1        Description for the Script-WithDependencies2 script
2.5        RequiredModule1             Module     local1        RequiredModule1 module
2.5        RequiredModule2             Module     local1        RequiredModule2 module
2.5        RequiredModule3             Module     local1        RequiredModule3 module
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script

PS C:\> Install-Script -Repository "Local1" -Name "Script-WithDependencies2"
PS C:\> Get-InstalledScript
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script
2.0        Script-WithDependencies2    Script     local1        Description for the Script-WithDependencies2 script

PS C:\> Get-InstalledModule
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        RequiredModule1             Module     local1        RequiredModule1 module
2.5        RequiredModule2             Module     local1        RequiredModule2 module
2.5        RequiredModule3             Module     local1        RequiredModule3 module

PS C:\> Find-Script -Repository "Local1" -Name "Required-Script*"
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script

PS C:\> Install-Script -Repository "Local1" -Name "Required-Script*"
PS C:\> Get-InstalledScript
Version    Name                        Type       Repository    Description
-------    ----                        ----       ----------    -----------
2.5        Required-Script1            Script     local1        Description for the Required-Script1 script
2.5        Required-Script2            Script     local1        Description for the Required-Script2 script
2.5        Required-Script3            Script     local1        Description for the Required-Script3 script
```

<span data-ttu-id="666f4-125">最初のコマンドは、 `Script-WithDependencies2` Local1 リポジトリ内のという名前のスクリプトとその依存関係を検索し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="666f4-125">The first command finds the script named `Script-WithDependencies2` and its dependencies in the Local1 repository and displays the results.</span></span>

<span data-ttu-id="666f4-126">2番目のコマンドは、をインストール `Script-WithDependencies2` します。</span><span class="sxs-lookup"><span data-stu-id="666f4-126">The second command installs `Script-WithDependencies2`.</span></span>

<span data-ttu-id="666f4-127">3番目のコマンドは、 `Get-InstalledScript` スクリプトコマンドレットを使用して、インストールされているスクリプトを取得し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="666f4-127">The third command uses the `Get-InstalledScript` script cmdlet to get installed scripts and display the results.</span></span>

<span data-ttu-id="666f4-128">4番目のコマンドは、コマンドレットを使用し `Get-InstalledModule` て、インストールされているモジュールを取得し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="666f4-128">The fourth command uses the `Get-InstalledModule` cmdlet to get installed modules and display the results.</span></span>

<span data-ttu-id="666f4-129">5番目のコマンドは、コマンドレットを使用して、 `Find-Script` 名前がで始まるスクリプトを検索 `Required-Script` し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="666f4-129">The fifth command uses the `Find-Script` cmdlet to find scripts where the name begins with `Required-Script` and display the results.</span></span>

<span data-ttu-id="666f4-130">6番目のコマンドは、名前が Local1 リポジトリ内で始まるスクリプトをインストールし `Required-Script` ます。</span><span class="sxs-lookup"><span data-stu-id="666f4-130">The sixth command installs the scripts where the name begins with `Required-Script` in the Local1 repository.</span></span>

<span data-ttu-id="666f4-131">最後のコマンドは、インストールされているスクリプトを取得し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="666f4-131">The final command gets installed scripts and displays the results.</span></span>

## <span data-ttu-id="666f4-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="666f4-132">PARAMETERS</span></span>

### <span data-ttu-id="666f4-133">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="666f4-133">-AcceptLicense</span></span>

<span data-ttu-id="666f4-134">モジュールで必要な場合は、インストール中にライセンス契約に自動的に同意します。</span><span class="sxs-lookup"><span data-stu-id="666f4-134">Automatically accept the license agreement during installation if the module requires it.</span></span>

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

### <span data-ttu-id="666f4-135">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="666f4-135">-AllowPrerelease</span></span>

<span data-ttu-id="666f4-136">プレリリースとしてマークされたスクリプトをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="666f4-136">Allows you to install a script marked as a prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="666f4-137">-Confirm</span><span class="sxs-lookup"><span data-stu-id="666f4-137">-Confirm</span></span>

<span data-ttu-id="666f4-138">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="666f4-138">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="666f4-139">-Credential</span><span class="sxs-lookup"><span data-stu-id="666f4-139">-Credential</span></span>

<span data-ttu-id="666f4-140">指定したパッケージプロバイダーまたはソースのスクリプトをインストールする権限を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="666f4-140">Specifies a user account that has rights to install a script for a specified package provider or source.</span></span>

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

### <span data-ttu-id="666f4-141">-Force</span><span class="sxs-lookup"><span data-stu-id="666f4-141">-Force</span></span>

<span data-ttu-id="666f4-142">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="666f4-142">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="666f4-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="666f4-143">-InputObject</span></span>

<span data-ttu-id="666f4-144">パイプラインの入力に使用されます。</span><span class="sxs-lookup"><span data-stu-id="666f4-144">Used for pipeline input.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="666f4-145">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="666f4-145">-MaximumVersion</span></span>

<span data-ttu-id="666f4-146">インストールする1つのスクリプトの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="666f4-146">Specifies the maximum version of a single scripts to install.</span></span> <span data-ttu-id="666f4-147">複数のスクリプトをインストールしようとする場合、このパラメーターを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="666f4-147">You cannot add this parameter if you are attempting to install multiple scripts.</span></span> <span data-ttu-id="666f4-148">**MaximumVersion** および **RequiredVersion** パラメーターは相互に排他的です。両方のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="666f4-148">The **MaximumVersion** and the **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="666f4-149">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="666f4-149">-MinimumVersion</span></span>

<span data-ttu-id="666f4-150">インストールする1つのスクリプトの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="666f4-150">Specifies the minimum version of a single script to install.</span></span> <span data-ttu-id="666f4-151">複数のスクリプトをインストールしようとする場合、このパラメーターを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="666f4-151">You cannot add this parameter if you are attempting to install multiple scripts.</span></span> <span data-ttu-id="666f4-152">**MinimumVersion** および **RequiredVersion** パラメーターは相互に排他的です。両方のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="666f4-152">The **MinimumVersion** and the **RequiredVersion** parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="666f4-153">-Name</span><span class="sxs-lookup"><span data-stu-id="666f4-153">-Name</span></span>

<span data-ttu-id="666f4-154">インストールするスクリプトの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="666f4-154">Specifies an array of names of scripts to install.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="666f4-155">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="666f4-155">-NoPathUpdate</span></span>

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

### <span data-ttu-id="666f4-156">-PassThru</span><span class="sxs-lookup"><span data-stu-id="666f4-156">-PassThru</span></span>

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

### <span data-ttu-id="666f4-157">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="666f4-157">-Proxy</span></span>

<span data-ttu-id="666f4-158">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="666f4-158">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="666f4-159">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="666f4-159">-ProxyCredential</span></span>

<span data-ttu-id="666f4-160">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="666f4-160">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="666f4-161">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="666f4-161">-Repository</span></span>

<span data-ttu-id="666f4-162">コマンドレットに登録されているリポジトリのフレンドリ名を指定し `Register-PSRepository` ます。</span><span class="sxs-lookup"><span data-stu-id="666f4-162">Specifies the friendly name of a repository that has been registered with the `Register-PSRepository` cmdlet.</span></span> <span data-ttu-id="666f4-163">既定値は、登録されているすべてのリポジトリです。</span><span class="sxs-lookup"><span data-stu-id="666f4-163">The default is all registered repositories.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="666f4-164">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="666f4-164">-RequiredVersion</span></span>

<span data-ttu-id="666f4-165">インストールするスクリプトの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="666f4-165">Specifies the exact version number of the script to install.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="666f4-166">-スコープ</span><span class="sxs-lookup"><span data-stu-id="666f4-166">-Scope</span></span>

<span data-ttu-id="666f4-167">スクリプトのインストール スコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="666f4-167">Specifies the installation scope of the script.</span></span>
<span data-ttu-id="666f4-168">有効な値は、AllUsers と CurrentUser です。</span><span class="sxs-lookup"><span data-stu-id="666f4-168">Valid values are: AllUsers and CurrentUser.</span></span>

<span data-ttu-id="666f4-169">AllUsers スコープを使用すると、コンピューターのすべてのユーザーがアクセスできる場所 (つまり) にモジュールをインストールでき `$env:ProgramFiles\WindowsPowerShell\Scripts` ます。</span><span class="sxs-lookup"><span data-stu-id="666f4-169">The AllUsers scope lets modules be installed in a location that is accessible to all users of the computer, that is, `$env:ProgramFiles\WindowsPowerShell\Scripts`.</span></span>

<span data-ttu-id="666f4-170">CurrentUser スコープでは、モジュールをにのみインストールでき `$home\Documents\WindowsPowerShell\Scripts` ます。これにより、モジュールは現在のユーザーのみが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="666f4-170">The CurrentUser scope lets modules be installed only to `$home\Documents\WindowsPowerShell\Scripts`, so that the module is available only to the current user.</span></span>

<span data-ttu-id="666f4-171">**スコープ** が定義されていない場合、既定値は現在のセッションに基づいて設定されます。</span><span class="sxs-lookup"><span data-stu-id="666f4-171">When no **Scope** is defined, the default will be set based on the current session:</span></span>

- <span data-ttu-id="666f4-172">管理者特権の PowerShell セッションの場合、 **スコープ** の既定値は AllUsers です。</span><span class="sxs-lookup"><span data-stu-id="666f4-172">For an elevated PowerShell session, **Scope** defaults to AllUsers;</span></span>
- <span data-ttu-id="666f4-173">[PowerShellGet バージョン 2.0.0](https://www.powershellgallery.com/packages/PowerShellGet)以上の管理者特権以外の PowerShell セッションの場合、 **スコープ** は CurrentUser です。</span><span class="sxs-lookup"><span data-stu-id="666f4-173">For non-elevated PowerShell sessions in [PowerShellGet versions 2.0.0](https://www.powershellgallery.com/packages/PowerShellGet) and above, **Scope** is CurrentUser;</span></span>
- <span data-ttu-id="666f4-174">PowerShellGet バージョン1.6.7 以前の管理者以外の PowerShell セッションの場合、 **スコープ** は未定義で `Install-Module` あり、失敗します。</span><span class="sxs-lookup"><span data-stu-id="666f4-174">For non-elevated PowerShell sessions in PowerShellGet versions 1.6.7 and earlier, **Scope** is undefined, and `Install-Module` fails.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="666f4-175">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="666f4-175">-WhatIf</span></span>

<span data-ttu-id="666f4-176">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="666f4-176">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="666f4-177">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="666f4-177">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="666f4-178">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="666f4-178">CommonParameters</span></span>

<span data-ttu-id="666f4-179">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="666f4-179">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="666f4-180">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="666f4-180">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="666f4-181">入力</span><span class="sxs-lookup"><span data-stu-id="666f4-181">INPUTS</span></span>

### <span data-ttu-id="666f4-182">System.String[]</span><span class="sxs-lookup"><span data-stu-id="666f4-182">System.String[]</span></span>

### <span data-ttu-id="666f4-183">システムの管理. PSObject []</span><span class="sxs-lookup"><span data-stu-id="666f4-183">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="666f4-184">System.String</span><span class="sxs-lookup"><span data-stu-id="666f4-184">System.String</span></span>

### <span data-ttu-id="666f4-185">System.Uri</span><span class="sxs-lookup"><span data-stu-id="666f4-185">System.Uri</span></span>

### <span data-ttu-id="666f4-186">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="666f4-186">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="666f4-187">出力</span><span class="sxs-lookup"><span data-stu-id="666f4-187">OUTPUTS</span></span>

### <span data-ttu-id="666f4-188">System.Object</span><span class="sxs-lookup"><span data-stu-id="666f4-188">System.Object</span></span>

## <span data-ttu-id="666f4-189">注</span><span class="sxs-lookup"><span data-stu-id="666f4-189">NOTES</span></span>

## <span data-ttu-id="666f4-190">関連リンク</span><span class="sxs-lookup"><span data-stu-id="666f4-190">RELATED LINKS</span></span>

[<span data-ttu-id="666f4-191">Find-Script</span><span class="sxs-lookup"><span data-stu-id="666f4-191">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="666f4-192">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="666f4-192">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="666f4-193">Save-Script</span><span class="sxs-lookup"><span data-stu-id="666f4-193">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="666f4-194">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="666f4-194">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="666f4-195">Update-Script</span><span class="sxs-lookup"><span data-stu-id="666f4-195">Update-Script</span></span>](Update-Script.md)
