---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-command?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Command
ms.openlocfilehash: a24d66aa1ce9e353e41cc7a686ee9f910a7106fc
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99599298"
---
# <span data-ttu-id="40af8-102">Find-Command</span><span class="sxs-lookup"><span data-stu-id="40af8-102">Find-Command</span></span>

## <span data-ttu-id="40af8-103">概要</span><span class="sxs-lookup"><span data-stu-id="40af8-103">SYNOPSIS</span></span>
<span data-ttu-id="40af8-104">モジュール内の PowerShell コマンドを検索します。</span><span class="sxs-lookup"><span data-stu-id="40af8-104">Finds PowerShell commands in modules.</span></span>

## <span data-ttu-id="40af8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="40af8-105">SYNTAX</span></span>

### <span data-ttu-id="40af8-106">すべて</span><span class="sxs-lookup"><span data-stu-id="40af8-106">All</span></span>

```
Find-Command [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
 [-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="40af8-107">Description</span><span class="sxs-lookup"><span data-stu-id="40af8-107">DESCRIPTION</span></span>

<span data-ttu-id="40af8-108">`Find-Command`コマンドレットでは、コマンドレット、エイリアス、関数、ワークフローなどの PowerShell コマンドを検索します。</span><span class="sxs-lookup"><span data-stu-id="40af8-108">The `Find-Command` cmdlet finds PowerShell commands such as cmdlets, aliases, functions, and workflows.</span></span> <span data-ttu-id="40af8-109">`Find-Command` 登録されているリポジトリ内のモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="40af8-109">`Find-Command` searches modules in registered repositories.</span></span>

<span data-ttu-id="40af8-110">によって検出された各コマンドに対して `Find-Command` 、 **Psgetcommandinfo** オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="40af8-110">For each command found by `Find-Command`, a **PSGetCommandInfo** object is returned.</span></span> <span data-ttu-id="40af8-111">**Psgetcommandinfo** オブジェクトは、パイプラインを使用してコマンドレットに送信でき `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="40af8-111">The **PSGetCommandInfo** object can be sent down the pipeline to the `Install-Module` cmdlet.</span></span>
<span data-ttu-id="40af8-112">`Install-Module` コマンドを含むモジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="40af8-112">`Install-Module` installs the module that contains the command.</span></span>

## <span data-ttu-id="40af8-113">例</span><span class="sxs-lookup"><span data-stu-id="40af8-113">EXAMPLES</span></span>

### <span data-ttu-id="40af8-114">例 1: 指定されたリポジトリ内のすべてのコマンドを検索する</span><span class="sxs-lookup"><span data-stu-id="40af8-114">Example 1: Find all commands in a specified repository</span></span>

<span data-ttu-id="40af8-115">コマンドレットでは、 `Find-Command` 登録されているリポジトリでモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="40af8-115">The `Find-Command` cmdlet searches a registered repository for modules.</span></span>

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

<span data-ttu-id="40af8-116">`Find-Command`**repository** パラメーターを使用して、登録されているリポジトリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="40af8-116">`Find-Command` uses the **Repository** parameter to specify a registered repository's name.</span></span> <span data-ttu-id="40af8-117">オブジェクトは、パイプラインを介して送信されます。</span><span class="sxs-lookup"><span data-stu-id="40af8-117">The objects are sent down the pipeline.</span></span> <span data-ttu-id="40af8-118">`Select-Object` オブジェクトを受け取り、 **1 番目** のパラメーターを使用して最初の10件の結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="40af8-118">`Select-Object` receives the objects and uses the **First** parameter to display the first 10 results.</span></span>

### <span data-ttu-id="40af8-119">例 2: 名前を指定してコマンドを検索する</span><span class="sxs-lookup"><span data-stu-id="40af8-119">Example 2: Find a command by name</span></span>

<span data-ttu-id="40af8-120">`Find-Command` では、コマンドの名前を使用して、リポジトリ内のモジュールを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="40af8-120">`Find-Command` can use the name of a command to locate the module in a repository.</span></span> <span data-ttu-id="40af8-121">コマンド名が複数の **modulenames** 存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40af8-121">It's possible that a command name exists in multiple **ModuleNames**.</span></span>

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

<span data-ttu-id="40af8-122">`Find-Command`**Repository** パラメーターを使用して **PSGallery** を検索します。</span><span class="sxs-lookup"><span data-stu-id="40af8-122">`Find-Command` uses the **Repository** parameter to search the **PSGallery**.</span></span> <span data-ttu-id="40af8-123">**Name** パラメーターは、コマンド **set-targetresource** を指定します。</span><span class="sxs-lookup"><span data-stu-id="40af8-123">The **Name** parameter specifies the command **Get-TargetResource**.</span></span>

### <span data-ttu-id="40af8-124">例 3: 名前を指定してコマンドを検索し、モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="40af8-124">Example 3: Find commands by name and install the module</span></span>

<span data-ttu-id="40af8-125">`Find-Command` は、コマンドとモジュールを見つけて、オブジェクトをに送信でき `Install-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="40af8-125">`Find-Command` can locate the command and module, then send the object to `Install-Module`.</span></span> <span data-ttu-id="40af8-126">複数のモジュールにコマンドが含まれている場合は、コマンド `Find-Command` レット **Module-Name** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="40af8-126">If a command is included in multiple modules, use the `Find-Command` cmdlets **Module-Name** parameter.</span></span>
<span data-ttu-id="40af8-127">それ以外の場合は、インストールしたくないモジュールがインストールされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40af8-127">Otherwise, modules might be installed that you didn't want to install.</span></span>

```powershell
PS> Find-Command -Name Get-TargetResource -Repository PSGallery -ModuleName SystemLocaleDsc |
    Install-Module

PS> Get-InstalledModule

Version   Name               Repository   Description
-------   ----               ----------   -----------
1.2.0.0   SystemLocaleDsc    PSGallery    This DSC Resource allows configuration of the Windows...
```

<span data-ttu-id="40af8-128">`Find-Command`**Name** パラメーターを使用して、コマンド **set-targetresource** を指定します。</span><span class="sxs-lookup"><span data-stu-id="40af8-128">`Find-Command` uses the **Name** parameter to specify the command **Get-TargetResource**.</span></span> <span data-ttu-id="40af8-129">**Repository** パラメーターは、 **PSGallery** を検索します。</span><span class="sxs-lookup"><span data-stu-id="40af8-129">The **Repository** parameter searches the **PSGallery**.</span></span> <span data-ttu-id="40af8-130">**ModuleName** パラメーターは、インストールするモジュール ( **Systemlocaledsc**) を指定します。</span><span class="sxs-lookup"><span data-stu-id="40af8-130">The **ModuleName** parameter specifies the module you want to install, **SystemLocaleDsc**.</span></span> <span data-ttu-id="40af8-131">オブジェクトは、パイプラインの下に送信され、 `Install-Module` モジュールがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="40af8-131">The object is sent down the pipeline to `Install-Module` and the module is installed.</span></span> <span data-ttu-id="40af8-132">インストールが完了したら、を使用し `Get-InstalledModule` て結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="40af8-132">After the installation finishes, you can use `Get-InstalledModule` to display the results.</span></span>

### <span data-ttu-id="40af8-133">例 4: コマンドを検索し、そのモジュールを保存する</span><span class="sxs-lookup"><span data-stu-id="40af8-133">Example 4: Find a command and save its module</span></span>

```
PS> Find-Command -Name Invoke-ScriptAnalyzer -Repository PSGallery | Save-Module -Path C:\Test\Modules -Verbose

VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'PSScriptAnalyzer'.
VERBOSE: Module 'PSScriptAnalyzer' was saved successfully to path 'C:\Test\Modules\PSScriptAnalyzer\1.18.0'.
```

<span data-ttu-id="40af8-134">`Find-Command`では、 **Name** と **repository** パラメーターを使用して、 **PSGallery** リポジトリでコマンド **Invoke-scriptanalyzer** を検索します。</span><span class="sxs-lookup"><span data-stu-id="40af8-134">`Find-Command` uses the **Name** and **Repository** parameters to search for the command **Invoke-ScriptAnalyzer** in the **PSGallery** repository.</span></span> <span data-ttu-id="40af8-135">オブジェクトは、パイプライン内でに送信され `Save-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="40af8-135">The object is sent down the pipeline to `Save-Module`.</span></span> <span data-ttu-id="40af8-136">**Path** パラメーターは、モジュールを保存する場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="40af8-136">The **Path** parameter determines the location to save the module.</span></span> <span data-ttu-id="40af8-137">**Verbose** は省略可能なパラメーターですが、PowerShell コンソールに状態出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="40af8-137">**Verbose** is an optional parameter, but displays status output in the PowerShell console.</span></span> <span data-ttu-id="40af8-138">詳細出力は、トラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="40af8-138">The verbose output is beneficial for troubleshooting.</span></span>

## <span data-ttu-id="40af8-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="40af8-139">PARAMETERS</span></span>

### <span data-ttu-id="40af8-140">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="40af8-140">-AllowPrerelease</span></span>

<span data-ttu-id="40af8-141">結果にプレリリースとしてマークされているモジュールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="40af8-141">Includes modules marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="40af8-142">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="40af8-142">-AllVersions</span></span>

<span data-ttu-id="40af8-143">このコマンドレットがモジュールのすべてのバージョンを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="40af8-143">Indicates that this cmdlet gets all versions of a module.</span></span>

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

### <span data-ttu-id="40af8-144">-Filter</span><span class="sxs-lookup"><span data-stu-id="40af8-144">-Filter</span></span>

<span data-ttu-id="40af8-145">**PackageManagement** プロバイダーの検索構文に基づいてモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="40af8-145">Finds modules based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="40af8-146">たとえば、 **ModuleName** プロパティと **Description** プロパティ内で検索する単語を指定します。</span><span class="sxs-lookup"><span data-stu-id="40af8-146">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="40af8-147">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="40af8-147">-MaximumVersion</span></span>

<span data-ttu-id="40af8-148">結果に含めるモジュールの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="40af8-148">Specifies the maximum version of the module to include in results.</span></span> <span data-ttu-id="40af8-149">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="40af8-149">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="40af8-150">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="40af8-150">-MinimumVersion</span></span>

<span data-ttu-id="40af8-151">結果に含めるモジュールの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="40af8-151">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="40af8-152">**MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="40af8-152">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="40af8-153">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="40af8-153">-ModuleName</span></span>

<span data-ttu-id="40af8-154">コマンドを検索するモジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="40af8-154">Specifies the name of a module to search for commands.</span></span> <span data-ttu-id="40af8-155">既定値はすべてのモジュールです。</span><span class="sxs-lookup"><span data-stu-id="40af8-155">The default is all modules.</span></span>

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

### <span data-ttu-id="40af8-156">-Name</span><span class="sxs-lookup"><span data-stu-id="40af8-156">-Name</span></span>

<span data-ttu-id="40af8-157">リポジトリ内で検索するコマンド名を指定します。</span><span class="sxs-lookup"><span data-stu-id="40af8-157">Specifies the command name to search for in a repository.</span></span> <span data-ttu-id="40af8-158">コマンド名の配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="40af8-158">Use commas to separate an array of command names.</span></span>

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

### <span data-ttu-id="40af8-159">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="40af8-159">-Proxy</span></span>

<span data-ttu-id="40af8-160">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="40af8-160">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="40af8-161">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="40af8-161">-ProxyCredential</span></span>

<span data-ttu-id="40af8-162">**Proxy** パラメーターに指定したプロキシ サーバーを使用するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="40af8-162">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="40af8-163">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="40af8-163">-Repository</span></span>

<span data-ttu-id="40af8-164">コマンドを検索するリポジトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="40af8-164">Specifies the repository to search for commands.</span></span> <span data-ttu-id="40af8-165">リポジトリ名の配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="40af8-165">Use commas to separate an array of repository names.</span></span> <span data-ttu-id="40af8-166">既定値は [すべてのリポジトリです。</span><span class="sxs-lookup"><span data-stu-id="40af8-166">The default is all repositories.</span></span>

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

### <span data-ttu-id="40af8-167">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="40af8-167">-RequiredVersion</span></span>

<span data-ttu-id="40af8-168">結果に含めるモジュールのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="40af8-168">Specifies the version of the module to include in the results.</span></span>

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

### <span data-ttu-id="40af8-169">-Tag</span><span class="sxs-lookup"><span data-stu-id="40af8-169">-Tag</span></span>

<span data-ttu-id="40af8-170">リポジトリ内のモジュールを分類するタグを指定します。</span><span class="sxs-lookup"><span data-stu-id="40af8-170">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="40af8-171">タグの配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="40af8-171">Use commas to separate an array of tags.</span></span>

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

### <span data-ttu-id="40af8-172">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="40af8-172">CommonParameters</span></span>

<span data-ttu-id="40af8-173">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="40af8-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="40af8-174">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40af8-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="40af8-175">入力</span><span class="sxs-lookup"><span data-stu-id="40af8-175">INPUTS</span></span>

## <span data-ttu-id="40af8-176">出力</span><span class="sxs-lookup"><span data-stu-id="40af8-176">OUTPUTS</span></span>

### <span data-ttu-id="40af8-177">PSGetCommandInfo</span><span class="sxs-lookup"><span data-stu-id="40af8-177">PSGetCommandInfo</span></span>

<span data-ttu-id="40af8-178">`Find-Command`**Psgetcommandinfo** オブジェクトを出力します。</span><span class="sxs-lookup"><span data-stu-id="40af8-178">`Find-Command` outputs a **PSGetCommandInfo** object.</span></span>

## <span data-ttu-id="40af8-179">注</span><span class="sxs-lookup"><span data-stu-id="40af8-179">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40af8-180">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="40af8-180">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="40af8-181">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="40af8-181">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="40af8-182">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="40af8-182">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="40af8-183">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40af8-183">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="40af8-184">関連リンク</span><span class="sxs-lookup"><span data-stu-id="40af8-184">RELATED LINKS</span></span>

[<span data-ttu-id="40af8-185">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="40af8-185">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="40af8-186">Install-Module</span><span class="sxs-lookup"><span data-stu-id="40af8-186">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="40af8-187">Save-Module</span><span class="sxs-lookup"><span data-stu-id="40af8-187">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="40af8-188">Select-Object</span><span class="sxs-lookup"><span data-stu-id="40af8-188">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="40af8-189">アンインストール-モジュール</span><span class="sxs-lookup"><span data-stu-id="40af8-189">Uninstall-Module</span></span>](Uninstall-Module.md)
