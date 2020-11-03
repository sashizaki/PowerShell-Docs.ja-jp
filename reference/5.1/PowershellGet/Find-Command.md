---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-command?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Command
ms.openlocfilehash: 71ea79cab9bb00c31f1cc78d70b1624f85a5a714
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213219"
---
# <span data-ttu-id="e185c-103">Find-Command</span><span class="sxs-lookup"><span data-stu-id="e185c-103">Find-Command</span></span>

## <span data-ttu-id="e185c-104">概要</span><span class="sxs-lookup"><span data-stu-id="e185c-104">SYNOPSIS</span></span>
<span data-ttu-id="e185c-105">モジュール内の PowerShell コマンドを検索します。</span><span class="sxs-lookup"><span data-stu-id="e185c-105">Finds PowerShell commands in modules.</span></span>

## <span data-ttu-id="e185c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e185c-106">SYNTAX</span></span>

### <span data-ttu-id="e185c-107">All</span><span class="sxs-lookup"><span data-stu-id="e185c-107">All</span></span>

```
Find-Command [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
 [-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="e185c-108">Description</span><span class="sxs-lookup"><span data-stu-id="e185c-108">DESCRIPTION</span></span>

<span data-ttu-id="e185c-109">`Find-Command`コマンドレットでは、コマンドレット、エイリアス、関数、ワークフローなどの PowerShell コマンドを検索します。</span><span class="sxs-lookup"><span data-stu-id="e185c-109">The `Find-Command` cmdlet finds PowerShell commands such as cmdlets, aliases, functions, and workflows.</span></span> <span data-ttu-id="e185c-110">`Find-Command` 登録されているリポジトリ内のモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="e185c-110">`Find-Command` searches modules in registered repositories.</span></span>

<span data-ttu-id="e185c-111">によって検出された各コマンドに対して `Find-Command` 、 **Psgetcommandinfo** オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="e185c-111">For each command found by `Find-Command`, a **PSGetCommandInfo** object is returned.</span></span> <span data-ttu-id="e185c-112">**Psgetcommandinfo** オブジェクトは、パイプラインを使用してコマンドレットに送信でき `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="e185c-112">The **PSGetCommandInfo** object can be sent down the pipeline to the `Install-Module` cmdlet.</span></span>
<span data-ttu-id="e185c-113">`Install-Module` コマンドを含むモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e185c-113">`Install-Module` installs the module that contains the command.</span></span>

## <span data-ttu-id="e185c-114">例</span><span class="sxs-lookup"><span data-stu-id="e185c-114">EXAMPLES</span></span>

### <span data-ttu-id="e185c-115">例 1: 指定されたリポジトリ内のすべてのコマンドを検索する</span><span class="sxs-lookup"><span data-stu-id="e185c-115">Example 1: Find all commands in a specified repository</span></span>

<span data-ttu-id="e185c-116">コマンドレットでは、 `Find-Command` 登録されているリポジトリでモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="e185c-116">The `Find-Command` cmdlet searches a registered repository for modules.</span></span>

```powershell
Find-Command -Repository PSGallery | Select-Object -First 10
```

```output
Name                                Version    ModuleName          Repository
----                                -------    ----------          ----------
Disable-AzureRmDataCollection       5.8.3      AzureRM.profile     PSGallery
Disable-AzureRmContextAutosave      5.8.3      AzureRM.profile     PSGallery
Enable-AzureRmDataCollection        5.8.3      AzureRM.profile     PSGallery
Enable-AzureRmContextAutosave       5.8.3      AzureRM.profile     PSGallery
Remove-AzureRmEnvironment           5.8.3      AzureRM.profile     PSGallery
Get-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Set-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Add-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Get-AzureRmSubscription             5.8.3      AzureRM.profile     PSGallery
Connect-AzureRmAccount              5.8.3      AzureRM.profile     PSGallery
```

<span data-ttu-id="e185c-117">`Find-Command`**repository** パラメーターを使用して、登録されているリポジトリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e185c-117">`Find-Command` uses the **Repository** parameter to specify a registered repository's name.</span></span> <span data-ttu-id="e185c-118">オブジェクトは、パイプラインを介して送信されます。</span><span class="sxs-lookup"><span data-stu-id="e185c-118">The objects are sent down the pipeline.</span></span> <span data-ttu-id="e185c-119">`Select-Object` オブジェクトを受け取り、 **1 番目** のパラメーターを使用して最初の10件の結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="e185c-119">`Select-Object` receives the objects and uses the **First** parameter to display the first 10 results.</span></span>

### <span data-ttu-id="e185c-120">例 2: 名前を指定してコマンドを検索する</span><span class="sxs-lookup"><span data-stu-id="e185c-120">Example 2: Find a command by name</span></span>

<span data-ttu-id="e185c-121">`Find-Command` では、コマンドの名前を使用して、リポジトリ内のモジュールを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="e185c-121">`Find-Command` can use the name of a command to locate the module in a repository.</span></span> <span data-ttu-id="e185c-122">コマンド名が複数の **modulenames** 存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e185c-122">It's possible that a command name exists in multiple **ModuleNames** .</span></span>

```powershell
Find-Command -Repository PSGallery -Name Get-TargetResource
```

```Output
Name                  Version    ModuleName                      Repository
----                  -------    ----------                      ----------
Get-TargetResource    3.1.0.0    xPowerShellExecutionPolicy      PSGallery
Get-TargetResource    1.0.0      xInternetExplorerHomePage       PSGallery
Get-TargetResource    1.2.0.0    SystemLocaleDsc                 PSGallery
```

<span data-ttu-id="e185c-123">`Find-Command`**Repository** パラメーターを使用して **PSGallery** を検索します。</span><span class="sxs-lookup"><span data-stu-id="e185c-123">`Find-Command` uses the **Repository** parameter to search the **PSGallery** .</span></span> <span data-ttu-id="e185c-124">**Name** パラメーターは、コマンド **set-targetresource** を指定します。</span><span class="sxs-lookup"><span data-stu-id="e185c-124">The **Name** parameter specifies the command **Get-TargetResource** .</span></span>

### <span data-ttu-id="e185c-125">例 3: 名前を指定してコマンドを検索し、モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="e185c-125">Example 3: Find commands by name and install the module</span></span>

<span data-ttu-id="e185c-126">`Find-Command` は、コマンドとモジュールを見つけて、オブジェクトをに送信でき `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="e185c-126">`Find-Command` can locate the command and module, then send the object to `Install-Module`.</span></span> <span data-ttu-id="e185c-127">複数のモジュールにコマンドが含まれている場合は、コマンド `Find-Command` レット **Module-Name** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e185c-127">If a command is included in multiple modules, use the `Find-Command` cmdlets **Module-Name** parameter.</span></span>
<span data-ttu-id="e185c-128">それ以外の場合は、インストールしたくないモジュールがインストールされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e185c-128">Otherwise, modules might be installed that you didn't want to install.</span></span>

```powershell
PS> Find-Command -Name Get-TargetResource -Repository PSGallery -ModuleName SystemLocaleDsc |
    Install-Module

PS> Get-InstalledModule

Version   Name               Repository   Description
-------   ----               ----------   -----------
1.2.0.0   SystemLocaleDsc    PSGallery    This DSC Resource allows configuration of the Windows...
```

<span data-ttu-id="e185c-129">`Find-Command`**Name** パラメーターを使用して、コマンド **set-targetresource** を指定します。</span><span class="sxs-lookup"><span data-stu-id="e185c-129">`Find-Command` uses the **Name** parameter to specify the command **Get-TargetResource** .</span></span> <span data-ttu-id="e185c-130">**Repository** パラメーターは、 **PSGallery** を検索します。</span><span class="sxs-lookup"><span data-stu-id="e185c-130">The **Repository** parameter searches the **PSGallery** .</span></span> <span data-ttu-id="e185c-131">**ModuleName** パラメーターは、インストールするモジュール ( **Systemlocaledsc** ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e185c-131">The **ModuleName** parameter specifies the module you want to install, **SystemLocaleDsc** .</span></span> <span data-ttu-id="e185c-132">オブジェクトは、パイプラインの下に送信され、 `Install-Module` モジュールがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e185c-132">The object is sent down the pipeline to `Install-Module` and the module is installed.</span></span> <span data-ttu-id="e185c-133">インストールが完了したら、を使用し `Get-InstalledModule` て結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e185c-133">After the installation finishes, you can use `Get-InstalledModule` to display the results.</span></span>

### <span data-ttu-id="e185c-134">例 4: コマンドを検索し、そのモジュールを保存する</span><span class="sxs-lookup"><span data-stu-id="e185c-134">Example 4: Find a command and save its module</span></span>

```
PS> Find-Command -Name Invoke-ScriptAnalyzer -Repository PSGallery | Save-Module -Path C:\Test\Modules -Verbose

VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'PSScriptAnalyzer'.
VERBOSE: Module 'PSScriptAnalyzer' was saved successfully to path 'C:\Test\Modules\PSScriptAnalyzer\1.18.0'.
```

<span data-ttu-id="e185c-135">`Find-Command`では、 **Name** と **repository** パラメーターを使用して、 **PSGallery** リポジトリでコマンド **Invoke-scriptanalyzer** を検索します。</span><span class="sxs-lookup"><span data-stu-id="e185c-135">`Find-Command` uses the **Name** and **Repository** parameters to search for the command **Invoke-ScriptAnalyzer** in the **PSGallery** repository.</span></span> <span data-ttu-id="e185c-136">オブジェクトは、パイプライン内でに送信され `Save-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="e185c-136">The object is sent down the pipeline to `Save-Module`.</span></span> <span data-ttu-id="e185c-137">**Path** パラメーターは、モジュールを保存する場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="e185c-137">The **Path** parameter determines the location to save the module.</span></span> <span data-ttu-id="e185c-138">**Verbose** は省略可能なパラメーターですが、PowerShell コンソールに状態出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e185c-138">**Verbose** is an optional parameter, but displays status output in the PowerShell console.</span></span> <span data-ttu-id="e185c-139">詳細出力は、トラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e185c-139">The verbose output is beneficial for troubleshooting.</span></span>

## <span data-ttu-id="e185c-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e185c-140">PARAMETERS</span></span>

### <span data-ttu-id="e185c-141">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="e185c-141">-AllowPrerelease</span></span>

<span data-ttu-id="e185c-142">結果にプレリリースとしてマークされているモジュールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e185c-142">Includes modules marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="e185c-143">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="e185c-143">-AllVersions</span></span>

<span data-ttu-id="e185c-144">このコマンドレットがモジュールのすべてのバージョンを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="e185c-144">Indicates that this cmdlet gets all versions of a module.</span></span>

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

### <span data-ttu-id="e185c-145">-Filter</span><span class="sxs-lookup"><span data-stu-id="e185c-145">-Filter</span></span>

<span data-ttu-id="e185c-146">**PackageManagement** プロバイダーの検索構文に基づいてモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="e185c-146">Finds modules based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="e185c-147">たとえば、 **ModuleName** プロパティと **Description** プロパティ内で検索する単語を指定します。</span><span class="sxs-lookup"><span data-stu-id="e185c-147">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="e185c-148">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="e185c-148">-MaximumVersion</span></span>

<span data-ttu-id="e185c-149">結果に含めるモジュールの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e185c-149">Specifies the maximum version of the module to include in results.</span></span> <span data-ttu-id="e185c-150">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e185c-150">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="e185c-151">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="e185c-151">-MinimumVersion</span></span>

<span data-ttu-id="e185c-152">結果に含めるモジュールの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e185c-152">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="e185c-153">**MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e185c-153">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="e185c-154">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="e185c-154">-ModuleName</span></span>

<span data-ttu-id="e185c-155">コマンドを検索するモジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e185c-155">Specifies the name of a module to search for commands.</span></span> <span data-ttu-id="e185c-156">既定値はすべてのモジュールです。</span><span class="sxs-lookup"><span data-stu-id="e185c-156">The default is all modules.</span></span>

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

### <span data-ttu-id="e185c-157">-Name</span><span class="sxs-lookup"><span data-stu-id="e185c-157">-Name</span></span>

<span data-ttu-id="e185c-158">リポジトリ内で検索するコマンド名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e185c-158">Specifies the command name to search for in a repository.</span></span> <span data-ttu-id="e185c-159">コマンド名の配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="e185c-159">Use commas to separate an array of command names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e185c-160">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="e185c-160">-Proxy</span></span>

<span data-ttu-id="e185c-161">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="e185c-161">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="e185c-162">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="e185c-162">-ProxyCredential</span></span>

<span data-ttu-id="e185c-163">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e185c-163">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="e185c-164">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="e185c-164">-Repository</span></span>

<span data-ttu-id="e185c-165">コマンドを検索するリポジトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="e185c-165">Specifies the repository to search for commands.</span></span> <span data-ttu-id="e185c-166">リポジトリ名の配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="e185c-166">Use commas to separate an array of repository names.</span></span> <span data-ttu-id="e185c-167">既定値は [すべてのリポジトリです。</span><span class="sxs-lookup"><span data-stu-id="e185c-167">The default is all repositories.</span></span>

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

### <span data-ttu-id="e185c-168">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="e185c-168">-RequiredVersion</span></span>

<span data-ttu-id="e185c-169">結果に含めるモジュールのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e185c-169">Specifies the version of the module to include in the results.</span></span>

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

### <span data-ttu-id="e185c-170">-Tag</span><span class="sxs-lookup"><span data-stu-id="e185c-170">-Tag</span></span>

<span data-ttu-id="e185c-171">リポジトリ内のモジュールを分類するタグを指定します。</span><span class="sxs-lookup"><span data-stu-id="e185c-171">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="e185c-172">タグの配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="e185c-172">Use commas to separate an array of tags.</span></span>

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

### <span data-ttu-id="e185c-173">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e185c-173">CommonParameters</span></span>

<span data-ttu-id="e185c-174">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e185c-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e185c-175">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e185c-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e185c-176">入力</span><span class="sxs-lookup"><span data-stu-id="e185c-176">INPUTS</span></span>

## <span data-ttu-id="e185c-177">出力</span><span class="sxs-lookup"><span data-stu-id="e185c-177">OUTPUTS</span></span>

### <span data-ttu-id="e185c-178">PSGetCommandInfo</span><span class="sxs-lookup"><span data-stu-id="e185c-178">PSGetCommandInfo</span></span>

<span data-ttu-id="e185c-179">`Find-Command`**Psgetcommandinfo** オブジェクトを出力します。</span><span class="sxs-lookup"><span data-stu-id="e185c-179">`Find-Command` outputs a **PSGetCommandInfo** object.</span></span>

## <span data-ttu-id="e185c-180">注</span><span class="sxs-lookup"><span data-stu-id="e185c-180">NOTES</span></span>

## <span data-ttu-id="e185c-181">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e185c-181">RELATED LINKS</span></span>

[<span data-ttu-id="e185c-182">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="e185c-182">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="e185c-183">Install-Module</span><span class="sxs-lookup"><span data-stu-id="e185c-183">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="e185c-184">Save-Module</span><span class="sxs-lookup"><span data-stu-id="e185c-184">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="e185c-185">Select-Object</span><span class="sxs-lookup"><span data-stu-id="e185c-185">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="e185c-186">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="e185c-186">Uninstall-Module</span></span>](Uninstall-Module.md)
