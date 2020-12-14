---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/05/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-rolecapability?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-RoleCapability
ms.openlocfilehash: d3300e0f378139cc873ffef1e798326100644d94
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94889812"
---
# <span data-ttu-id="e86c0-103">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="e86c0-103">Find-RoleCapability</span></span>

## <span data-ttu-id="e86c0-104">概要</span><span class="sxs-lookup"><span data-stu-id="e86c0-104">SYNOPSIS</span></span>
<span data-ttu-id="e86c0-105">モジュール内のロール機能を検索します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-105">Finds role capabilities in modules.</span></span>

## <span data-ttu-id="e86c0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e86c0-106">SYNTAX</span></span>

### <span data-ttu-id="e86c0-107">すべて</span><span class="sxs-lookup"><span data-stu-id="e86c0-107">All</span></span>

```
Find-RoleCapability [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
[-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
[-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
[-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="e86c0-108">Description</span><span class="sxs-lookup"><span data-stu-id="e86c0-108">DESCRIPTION</span></span>

<span data-ttu-id="e86c0-109">`Find-RoleCapability`コマンドレットは、登録されているリポジトリを検索して、PowerShell ロール機能とモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-109">The `Find-RoleCapability` cmdlet searches registered repositories to find PowerShell role capabilities and modules.</span></span>

<span data-ttu-id="e86c0-110">によって検出された各ロール機能に対して `Find-RoleCapability` 、 **Psgetrolecap信頼性情報** オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="e86c0-110">For each role capability found by `Find-RoleCapability`, a **PSGetRoleCapabilityInfo** object is returned.</span></span> <span data-ttu-id="e86c0-111">**Psgetrolecap信頼性情報** オブジェクトは、パイプラインを使用して、 `Install-Module` またはコマンドレットに送信でき `Save-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="e86c0-111">**PSGetRoleCapabilityInfo** objects can be sent down the pipeline to the `Install-Module` or `Save-Module` cmdlets.</span></span>

<span data-ttu-id="e86c0-112">PowerShell ロール機能では、十分な管理 (JEA) エンドポイントでユーザーが使用できるコマンドとアプリケーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-112">PowerShell role capabilities define which commands and applications are available to a user at a Just Enough Administration (JEA) endpoint.</span></span> <span data-ttu-id="e86c0-113">ロール機能は、拡張子の付いたファイルによって定義され `.psrc` ます。</span><span class="sxs-lookup"><span data-stu-id="e86c0-113">Role capabilities are defined by files with a `.psrc` extension.</span></span>

## <span data-ttu-id="e86c0-114">例</span><span class="sxs-lookup"><span data-stu-id="e86c0-114">EXAMPLES</span></span>

### <span data-ttu-id="e86c0-115">例 1: ロール機能を検索する</span><span class="sxs-lookup"><span data-stu-id="e86c0-115">Example 1: Find role capabilities</span></span>

<span data-ttu-id="e86c0-116">`Find-RoleCapability` 登録されている各リポジトリのロール機能を検索します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-116">`Find-RoleCapability` finds role capabilities in each registered repository.</span></span> <span data-ttu-id="e86c0-117">特定のリポジトリを検索するには、 **repository** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-117">To search a specific repository, use the **Repository** parameter.</span></span>

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

### <span data-ttu-id="e86c0-118">例 2: 名前を指定してロール機能を検索する</span><span class="sxs-lookup"><span data-stu-id="e86c0-118">Example 2: Find role capabilities by name</span></span>

<span data-ttu-id="e86c0-119">`Find-RoleCapability` ロール機能を名前で検索します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-119">`Find-RoleCapability` finds role capabilities by name.</span></span> <span data-ttu-id="e86c0-120">名前の配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-120">Use commas to separate an array of names.</span></span>

```powershell
Find-RoleCapability -Name General-Lev1, IIS-Lev2
```

```output
Name             Version    ModuleName     Repository
----             -------    ----------     ----------
General-Lev1     1.0        JeaExamples    PSGallery
IIS-Lev2         1.0        JeaExamples    PSGallery
```

### <span data-ttu-id="e86c0-121">例 3: ロール機能のモジュールを検索して保存する</span><span class="sxs-lookup"><span data-stu-id="e86c0-121">Example 3: Find and save a role capability's module</span></span>

<span data-ttu-id="e86c0-122">コマンドレットでは、 `Find-RoleCapability` ロール機能を検索し、そのオブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-122">The `Find-RoleCapability` cmdlet finds a role capability and sends the object down the pipeline.</span></span>
<span data-ttu-id="e86c0-123">`Save-Module` ロール機能のモジュールをファイルシステムに保存します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-123">`Save-Module` saves the role capability's module to a file system.</span></span> <span data-ttu-id="e86c0-124">`Get-ChildItem` モジュールのディレクトリの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-124">`Get-ChildItem` displays the contents of the module's directory.</span></span>

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

<span data-ttu-id="e86c0-125">`Find-RoleCapability`**Name** パラメーターを使用して、 **Lev1** ロール機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-125">`Find-RoleCapability` uses the **Name** parameter to specify the **General-Lev1** role capability.</span></span>
<span data-ttu-id="e86c0-126">オブジェクトは、パイプラインで送信されます。</span><span class="sxs-lookup"><span data-stu-id="e86c0-126">The object is sent down the pipeline.</span></span> <span data-ttu-id="e86c0-127">`Save-Module` ファイルシステムの場所に **Path** パラメーターを使用してモジュールを保存します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-127">`Save-Module` uses the **Path** parameter for the file system location to save the module.</span></span> <span data-ttu-id="e86c0-128">モジュールが保存された後、 `Get-ChildItem` モジュールの **パス** を指定し、 **JeaExamples** モジュールのディレクトリの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-128">After the module is saved, `Get-ChildItem` specifies the module's **Path** and displays the contents of the **JeaExamples** module's directory.</span></span>

### <span data-ttu-id="e86c0-129">例 4: ロール機能のモジュールを検索してインストールする</span><span class="sxs-lookup"><span data-stu-id="e86c0-129">Example 4: Find and install a role capability's module</span></span>

<span data-ttu-id="e86c0-130">`Find-RoleCapability` モジュールを検索し、そのオブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-130">`Find-RoleCapability` finds the module and sends the object down the pipeline.</span></span> <span data-ttu-id="e86c0-131">`Install-Module` モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e86c0-131">`Install-Module` installs the module.</span></span> <span data-ttu-id="e86c0-132">インストール後、を使用し `Get-InstalledModule` て結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-132">After the installation, use `Get-InstalledModule` to see the results.</span></span>

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

<span data-ttu-id="e86c0-133">`Find-RoleCapability`**Name** パラメーターを使用して、 **Lev1** ロール機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-133">`Find-RoleCapability` uses the **Name** parameter to specify the **General-Lev1** role capability.</span></span>
<span data-ttu-id="e86c0-134">オブジェクトは、パイプラインで送信されます。</span><span class="sxs-lookup"><span data-stu-id="e86c0-134">The object is sent down the pipeline.</span></span> <span data-ttu-id="e86c0-135">`Install-Module` では、インストール中に **Verbose** パラメーターを使用してステータスメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e86c0-135">`Install-Module` uses the **Verbose** parameter to display status messages during the installation.</span></span> <span data-ttu-id="e86c0-136">インストールが完了すると、JeaExamples モジュールがインストールされたことが出力によっ `Get-InstalledModule` て確認されます。 </span><span class="sxs-lookup"><span data-stu-id="e86c0-136">After the install is finished, the `Get-InstalledModule` output confirms that the **JeaExamples** module was installed.</span></span>

## <span data-ttu-id="e86c0-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e86c0-137">PARAMETERS</span></span>

### <span data-ttu-id="e86c0-138">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="e86c0-138">-AllowPrerelease</span></span>

<span data-ttu-id="e86c0-139">結果にプレリリースとしてマークされたリソースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e86c0-139">Includes resources marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="e86c0-140">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="e86c0-140">-AllVersions</span></span>

<span data-ttu-id="e86c0-141">このコマンドレットがモジュールのすべてのバージョンを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-141">Indicates that this cmdlet gets all versions of a module.</span></span> <span data-ttu-id="e86c0-142">**AllVersions** パラメーターには、モジュールの使用可能なバージョンがそれぞれ表示されます。</span><span class="sxs-lookup"><span data-stu-id="e86c0-142">The **AllVersions** parameter displays each of a module's available versions.</span></span>

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

### <span data-ttu-id="e86c0-143">-Filter</span><span class="sxs-lookup"><span data-stu-id="e86c0-143">-Filter</span></span>

<span data-ttu-id="e86c0-144">**PackageManagement** プロバイダーの検索構文に基づいてリソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-144">Finds resources based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="e86c0-145">たとえば、 **ModuleName** プロパティと **Description** プロパティ内で検索する単語を指定します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-145">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="e86c0-146">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="e86c0-146">-MaximumVersion</span></span>

<span data-ttu-id="e86c0-147">結果に含めるモジュールの最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-147">Specifies the maximum version of the module to include in results.</span></span> <span data-ttu-id="e86c0-148">**MaximumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e86c0-148">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="e86c0-149">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="e86c0-149">-MinimumVersion</span></span>

<span data-ttu-id="e86c0-150">結果に含めるモジュールの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-150">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="e86c0-151">**MinimumVersion** および **RequiredVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e86c0-151">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="e86c0-152">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="e86c0-152">-ModuleName</span></span>

<span data-ttu-id="e86c0-153">ロール機能を検索するモジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-153">Specifies the name of the module in which to search for role capabilities.</span></span> <span data-ttu-id="e86c0-154">既定値はすべてのモジュールです。</span><span class="sxs-lookup"><span data-stu-id="e86c0-154">The default is all modules.</span></span>

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

### <span data-ttu-id="e86c0-155">-Name</span><span class="sxs-lookup"><span data-stu-id="e86c0-155">-Name</span></span>

<span data-ttu-id="e86c0-156">ロール機能の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-156">Specifies the name of a role capability.</span></span> <span data-ttu-id="e86c0-157">既定値は、すべてのロール機能です。</span><span class="sxs-lookup"><span data-stu-id="e86c0-157">The default is all role capabilities.</span></span> <span data-ttu-id="e86c0-158">リソース名の配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-158">Use commas to separate an array of resource names.</span></span>

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

### <span data-ttu-id="e86c0-159">-プロキシ</span><span class="sxs-lookup"><span data-stu-id="e86c0-159">-Proxy</span></span>

<span data-ttu-id="e86c0-160">インターネットリソースに直接接続するのではなく、要求のプロキシサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-160">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="e86c0-161">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="e86c0-161">-ProxyCredential</span></span>

<span data-ttu-id="e86c0-162">**プロキシ** パラメーターで指定されたプロキシサーバーを使用するためのアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-162">Specifies a user account with permission to use the proxy server specified in the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="e86c0-163">-リポジトリ</span><span class="sxs-lookup"><span data-stu-id="e86c0-163">-Repository</span></span>

<span data-ttu-id="e86c0-164">ロール機能を検索するリポジトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-164">Specifies a repository to search for role capabilities.</span></span> <span data-ttu-id="e86c0-165">リポジトリ名の配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-165">Use commas to separate an array of repository names.</span></span>

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

### <span data-ttu-id="e86c0-166">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="e86c0-166">-RequiredVersion</span></span>

<span data-ttu-id="e86c0-167">結果に含めるモジュールの正確なバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-167">Specifies the module's exact version number to include in the results.</span></span> <span data-ttu-id="e86c0-168">**RequiredVersion** パラメーターと **MinimumVersion** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e86c0-168">The **RequiredVersion** and the **MinimumVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="e86c0-169">-Tag</span><span class="sxs-lookup"><span data-stu-id="e86c0-169">-Tag</span></span>

<span data-ttu-id="e86c0-170">リポジトリ内のモジュールを分類するタグを指定します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-170">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="e86c0-171">タグの配列を区切るには、コンマを使用します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-171">Use commas to separate an array of tags.</span></span>

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

### <span data-ttu-id="e86c0-172">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e86c0-172">CommonParameters</span></span>

<span data-ttu-id="e86c0-173">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e86c0-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e86c0-174">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e86c0-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e86c0-175">入力</span><span class="sxs-lookup"><span data-stu-id="e86c0-175">INPUTS</span></span>

## <span data-ttu-id="e86c0-176">出力</span><span class="sxs-lookup"><span data-stu-id="e86c0-176">OUTPUTS</span></span>

### <span data-ttu-id="e86c0-177">PSGetRoleCapabilityInfo</span><span class="sxs-lookup"><span data-stu-id="e86c0-177">PSGetRoleCapabilityInfo</span></span>

<span data-ttu-id="e86c0-178">`Find-RoleCapability`コマンドレットは、 **Psgetrolecap信頼性情報** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-178">The `Find-RoleCapability` cmdlet returns a **PSGetRoleCapabilityInfo** object.</span></span>

## <span data-ttu-id="e86c0-179">注</span><span class="sxs-lookup"><span data-stu-id="e86c0-179">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e86c0-180">2020年4月の時点で、PowerShell ギャラリーでは、トランスポート層セキュリティ (TLS) バージョン1.0 と1.1 がサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e86c0-180">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="e86c0-181">TLS 1.2 以降を使用していない場合は、PowerShell ギャラリーにアクセスしようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-181">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="e86c0-182">次のコマンドを使用して、TLS 1.2 を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e86c0-182">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="e86c0-183">詳細については、PowerShell ブログの [お知らせ](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e86c0-183">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="e86c0-184">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e86c0-184">RELATED LINKS</span></span>

[<span data-ttu-id="e86c0-185">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="e86c0-185">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="e86c0-186">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="e86c0-186">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="e86c0-187">Install-Module</span><span class="sxs-lookup"><span data-stu-id="e86c0-187">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="e86c0-188">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="e86c0-188">New-PSRoleCapabilityFile</span></span>](../Microsoft.PowerShell.Core/New-PSRoleCapabilityFile.md)

[<span data-ttu-id="e86c0-189">Save-Module</span><span class="sxs-lookup"><span data-stu-id="e86c0-189">Save-Module</span></span>](Save-Module.md)
