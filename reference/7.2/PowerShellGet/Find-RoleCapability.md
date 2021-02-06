---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/05/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-rolecapability?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-RoleCapability
ms.openlocfilehash: a84dee14872ad5a7d0f7bac8e0057dc527855074
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99600583"
---
# <span data-ttu-id="1f50c-102">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="1f50c-102">Find-RoleCapability</span></span>

## <span data-ttu-id="1f50c-103">概要</span><span class="sxs-lookup"><span data-stu-id="1f50c-103">SYNOPSIS</span></span>
<span data-ttu-id="1f50c-104">モジュール内のロール機能を検索します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-104">Finds role capabilities in modules.</span></span>

## <span data-ttu-id="1f50c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1f50c-105">SYNTAX</span></span>

### <span data-ttu-id="1f50c-106">すべて</span><span class="sxs-lookup"><span data-stu-id="1f50c-106">All</span></span>

```
Find-RoleCapability [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>] 
[-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease] 
[-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] 
[-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="1f50c-107">Description</span><span class="sxs-lookup"><span data-stu-id="1f50c-107">DESCRIPTION</span></span>

<span data-ttu-id="1f50c-108">`Find-RoleCapability`コマンドレットは、登録されているリポジトリを検索して、PowerShell ロール機能とモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-108">The `Find-RoleCapability` cmdlet searches registered repositories to find PowerShell role capabilities and modules.</span></span>

<span data-ttu-id="1f50c-109">によって検出された各ロール機能に対して `Find-RoleCapability` 、 **Psgetrolecap信頼性情報** オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="1f50c-109">For each role capability found by `Find-RoleCapability`, a **PSGetRoleCapabilityInfo** object is returned.</span></span> <span data-ttu-id="1f50c-110">**Psgetrolecap信頼性情報** オブジェクトは、パイプラインを使用して、 `Install-Module` またはコマンドレットに送信でき `Save-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="1f50c-110">**PSGetRoleCapabilityInfo** objects can be sent down the pipeline to the `Install-Module` or `Save-Module` cmdlets.</span></span>

<span data-ttu-id="1f50c-111">PowerShell ロール機能では、十分な管理 (JEA) エンドポイントでユーザーが使用できるコマンドとアプリケーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-111">PowerShell role capabilities define which commands and applications are available to a user at a Just Enough Administration (JEA) endpoint.</span></span> <span data-ttu-id="1f50c-112">ロール機能は、拡張子の付いたファイルによって定義され `.psrc` ます。</span><span class="sxs-lookup"><span data-stu-id="1f50c-112">Role capabilities are defined by files with a `.psrc` extension.</span></span>

## <span data-ttu-id="1f50c-113">例</span><span class="sxs-lookup"><span data-stu-id="1f50c-113">EXAMPLES</span></span>

### <span data-ttu-id="1f50c-114">例 1: ロール機能を検索する</span><span class="sxs-lookup"><span data-stu-id="1f50c-114">Example 1: Find role capabilities</span></span>

<span data-ttu-id="1f50c-115">`Find-RoleCapability` 登録されている各リポジトリのロール機能を検索します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-115">`Find-RoleCapability` finds role capabilities in each registered repository.</span></span> <span data-ttu-id="1f50c-116">特定のリポジトリを検索するには、 **repository** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-116">To search a specific repository, use the **Repository** parameter.</span></span>

```powershell
Find-RoleCapability
```

```output
Name             Version    ModuleName     Repository
----             -------    ----------     ----------
General-Lev1     1.0        JeaExamples    PSGallery
General-Lev2     1.0        JeaExamples    PSGallery
IIS-Lev1         1.0        JeaExamples    PSGallery
IIS-Lev2         1.0        JeaExamples    PSGallery
```

### <span data-ttu-id="1f50c-117">例 2: 名前を指定してロール機能を検索する</span><span class="sxs-lookup"><span data-stu-id="1f50c-117">Example 2: Find role capabilities by name</span></span>

<span data-ttu-id="1f50c-118">`Find-RoleCapability` ロール機能を名前で検索します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-118">`Find-RoleCapability` finds role capabilities by name.</span></span> <span data-ttu-id="1f50c-119">名前の配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-119">Use commas to separate an array of names.</span></span>

```powershell
Find-RoleCapability -Name General-Lev1, IIS-Lev2
```

```output
Name             Version    ModuleName     Repository
----             -------    ----------     ----------
General-Lev1     1.0        JeaExamples    PSGallery
IIS-Lev2         1.0        JeaExamples    PSGallery
```

### <span data-ttu-id="1f50c-120">例 3: ロール機能のモジュールを検索して保存する</span><span class="sxs-lookup"><span data-stu-id="1f50c-120">Example 3: Find and save a role capability's module</span></span>

<span data-ttu-id="1f50c-121">コマンドレットでは、 `Find-RoleCapability` ロール機能を検索し、そのオブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-121">The `Find-RoleCapability` cmdlet finds a role capability and sends the object down the pipeline.</span></span>
<span data-ttu-id="1f50c-122">`Save-Module` ロール機能のモジュールをファイルシステムに保存します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-122">`Save-Module` saves the role capability's module to a file system.</span></span> <span data-ttu-id="1f50c-123">`Get-ChildItem` モジュールのディレクトリの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-123">`Get-ChildItem` displays the contents of the module's directory.</span></span>

```
PS> Find-RoleCapability -Name General-Lev1 | Save-Module -Path C:\Test\Modules

PS> Get-ChildItem -Path C:\Test\Modules\JeaExamples\1.0\

    Directory: C:\Test\Modules\JeaExamples\1.0

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----          6/4/2019    16:37                RoleCapabilities
-a----          2/5/2019    18:46           1702 CreateRegisterPSSC.ps1
-a----          2/5/2019    18:46           7656 JeaExamples.psd1
-a----         10/1/2018    08:16            595 JeaExamples.psm1
```

<span data-ttu-id="1f50c-124">`Find-RoleCapability`**Name** パラメーターを使用して、 **Lev1** ロール機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-124">`Find-RoleCapability` uses the **Name** parameter to specify the **General-Lev1** role capability.</span></span>
<span data-ttu-id="1f50c-125">オブジェクトは、パイプラインで送信されます。</span><span class="sxs-lookup"><span data-stu-id="1f50c-125">The object is sent down the pipeline.</span></span> <span data-ttu-id="1f50c-126">`Save-Module` ファイルシステムの場所に **Path** パラメーターを使用してモジュールを保存します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-126">`Save-Module` uses the **Path** parameter for the file system location to save the module.</span></span> <span data-ttu-id="1f50c-127">モジュールが保存された後、 `Get-ChildItem` モジュールの **パス** を指定し、 **JeaExamples** モジュールのディレクトリの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-127">After the module is saved, `Get-ChildItem` specifies the module's **Path** and displays the contents of the **JeaExamples** module's directory.</span></span>

### <span data-ttu-id="1f50c-128">例 4: ロール機能のモジュールを検索してインストールする</span><span class="sxs-lookup"><span data-stu-id="1f50c-128">Example 4: Find and install a role capability's module</span></span>

<span data-ttu-id="1f50c-129">`Find-RoleCapability` モジュールを検索し、そのオブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-129">`Find-RoleCapability` finds the module and sends the object down the pipeline.</span></span> <span data-ttu-id="1f50c-130">`Install-Module` モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1f50c-130">`Install-Module` installs the module.</span></span> <span data-ttu-id="1f50c-131">インストール後、を使用し `Get-InstalledModule` て結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-131">After the installation, use `Get-InstalledModule` to see the results.</span></span>

```
PS> Find-RoleCapability -Name General-Lev1 | Install-Module -Verbose

VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/JeaExamples/1.0.0'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/JeaExamples/1.0.0'.
VERBOSE: Completed downloading 'JeaExamples'.
VERBOSE: InstallPackageLocal' - name='JeaExamples', version='1.0',
VERBOSE: Validating the 'JeaExamples' module contents
VERBOSE: Test-ModuleManifest successfully validated the module manifest file
VERBOSE: Module 'JeaExamples' was installed successfully to path

PS> Get-InstalledModule

Version    Name            Repository     Description
-------    ----            ----------     -----------
1.0        JeaExamples     PSGallery      Some example Jea roles for general server maintenance...
```

<span data-ttu-id="1f50c-132">`Find-RoleCapability`**Name** パラメーターを使用して、 **Lev1** ロール機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-132">`Find-RoleCapability` uses the **Name** parameter to specify the **General-Lev1** role capability.</span></span>
<span data-ttu-id="1f50c-133">オブジェクトは、パイプラインで送信されます。</span><span class="sxs-lookup"><span data-stu-id="1f50c-133">The object is sent down the pipeline.</span></span> <span data-ttu-id="1f50c-134">`Install-Module` では、インストール中に **Verbose** パラメーターを使用してステータスメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f50c-134">`Install-Module` uses the **Verbose** parameter to display status messages during the installation.</span></span> <span data-ttu-id="1f50c-135">インストールが完了すると、JeaExamples モジュールがインストールされたことが出力によっ `Get-InstalledModule` て確認されます。 </span><span class="sxs-lookup"><span data-stu-id="1f50c-135">After the install is finished, the `Get-InstalledModule` output confirms that the **JeaExamples** module was installed.</span></span>

## <span data-ttu-id="1f50c-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1f50c-136">PARAMETERS</span></span>

### <span data-ttu-id="1f50c-137">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="1f50c-137">-AllowPrerelease</span></span>

<span data-ttu-id="1f50c-138">結果にプレリリースとしてマークされたリソースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1f50c-138">Includes resources marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="1f50c-139">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="1f50c-139">-AllVersions</span></span>

<span data-ttu-id="1f50c-140">このコマンドレットがモジュールのすべてのバージョンを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-140">Indicates that this cmdlet gets all versions of a module.</span></span> <span data-ttu-id="1f50c-141">**AllVersions** パラメーターには、モジュールの使用可能なバージョンがそれぞれ表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f50c-141">The **AllVersions** parameter displays each of a module's available versions.</span></span>

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

### <span data-ttu-id="1f50c-142">-Filter</span><span class="sxs-lookup"><span data-stu-id="1f50c-142">-Filter</span></span>

<span data-ttu-id="1f50c-143">**PackageManagement** プロバイダーの検索構文に基づいてリソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-143">Finds resources based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="1f50c-144">たとえば、 **ModuleName** プロパティと **Description** プロパティ内で検索する単語を指定します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-144">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="1f50c-145">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="1f50c-145">-MaximumVersion</span></span>

<span data-ttu-id="1f50c-146">結果に含めるモジュールの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-146">Specifies the maximum version of the module to include in results.</span></span> <span data-ttu-id="1f50c-147">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1f50c-147">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="1f50c-148">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="1f50c-148">-MinimumVersion</span></span>

<span data-ttu-id="1f50c-149">結果に含めるモジュールの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-149">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="1f50c-150">**MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1f50c-150">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="1f50c-151">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="1f50c-151">-ModuleName</span></span>

<span data-ttu-id="1f50c-152">ロール機能を検索するモジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-152">Specifies the name of the module in which to search for role capabilities.</span></span> <span data-ttu-id="1f50c-153">既定値はすべてのモジュールです。</span><span class="sxs-lookup"><span data-stu-id="1f50c-153">The default is all modules.</span></span>

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

### <span data-ttu-id="1f50c-154">-Name</span><span class="sxs-lookup"><span data-stu-id="1f50c-154">-Name</span></span>

<span data-ttu-id="1f50c-155">ロール機能の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-155">Specifies the name of a role capability.</span></span> <span data-ttu-id="1f50c-156">既定値は、すべてのロール機能です。</span><span class="sxs-lookup"><span data-stu-id="1f50c-156">The default is all role capabilities.</span></span> <span data-ttu-id="1f50c-157">リソース名の配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-157">Use commas to separate an array of resource names.</span></span>

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

### <span data-ttu-id="1f50c-158">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="1f50c-158">-Proxy</span></span>

<span data-ttu-id="1f50c-159">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-159">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="1f50c-160">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="1f50c-160">-ProxyCredential</span></span>

<span data-ttu-id="1f50c-161">**プロキシ** パラメーターで指定されたプロキシサーバーを使用するためのアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-161">Specifies a user account with permission to use the proxy server specified in the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="1f50c-162">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="1f50c-162">-Repository</span></span>

<span data-ttu-id="1f50c-163">ロール機能を検索するリポジトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-163">Specifies a repository to search for role capabilities.</span></span> <span data-ttu-id="1f50c-164">リポジトリ名の配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-164">Use commas to separate an array of repository names.</span></span>

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

### <span data-ttu-id="1f50c-165">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="1f50c-165">-RequiredVersion</span></span>

<span data-ttu-id="1f50c-166">結果に含めるモジュールの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-166">Specifies the module's exact version number to include in the results.</span></span> <span data-ttu-id="1f50c-167">**RequiredVersion** パラメーターと **MinimumVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1f50c-167">The **RequiredVersion** and the **MinimumVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="1f50c-168">-Tag</span><span class="sxs-lookup"><span data-stu-id="1f50c-168">-Tag</span></span>

<span data-ttu-id="1f50c-169">リポジトリ内のモジュールを分類するタグを指定します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-169">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="1f50c-170">タグの配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-170">Use commas to separate an array of tags.</span></span>

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

### <span data-ttu-id="1f50c-171">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f50c-171">CommonParameters</span></span>

<span data-ttu-id="1f50c-172">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="1f50c-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1f50c-173">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f50c-173">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1f50c-174">入力</span><span class="sxs-lookup"><span data-stu-id="1f50c-174">INPUTS</span></span>

### <span data-ttu-id="1f50c-175">System.Uri</span><span class="sxs-lookup"><span data-stu-id="1f50c-175">System.Uri</span></span>

### <span data-ttu-id="1f50c-176">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="1f50c-176">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="1f50c-177">出力</span><span class="sxs-lookup"><span data-stu-id="1f50c-177">OUTPUTS</span></span>

### <span data-ttu-id="1f50c-178">PSGetRoleCapabilityInfo</span><span class="sxs-lookup"><span data-stu-id="1f50c-178">PSGetRoleCapabilityInfo</span></span>

<span data-ttu-id="1f50c-179">`Find-RoleCapability`コマンドレットは、 **Psgetrolecap信頼性情報** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-179">The `Find-RoleCapability` cmdlet returns a **PSGetRoleCapabilityInfo** object.</span></span>

## <span data-ttu-id="1f50c-180">注</span><span class="sxs-lookup"><span data-stu-id="1f50c-180">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f50c-181">2020 年 4 月時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="1f50c-181">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="1f50c-182">TLS 1.2 以降を使用していない場合、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1f50c-182">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="1f50c-183">次のコマンドを使用して、確実に TLS 1.2 を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="1f50c-183">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="1f50c-184">詳細については、PowerShell ブログの[お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f50c-184">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="1f50c-185">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1f50c-185">RELATED LINKS</span></span>

[<span data-ttu-id="1f50c-186">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="1f50c-186">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="1f50c-187">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="1f50c-187">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="1f50c-188">Install-Module</span><span class="sxs-lookup"><span data-stu-id="1f50c-188">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="1f50c-189">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="1f50c-189">New-PSRoleCapabilityFile</span></span>](../Microsoft.PowerShell.Core/New-PSRoleCapabilityFile.md)

[<span data-ttu-id="1f50c-190">Save-Module</span><span class="sxs-lookup"><span data-stu-id="1f50c-190">Save-Module</span></span>](Save-Module.md)
