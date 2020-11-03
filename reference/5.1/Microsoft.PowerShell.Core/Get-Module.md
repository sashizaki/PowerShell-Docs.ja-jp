---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Module
ms.openlocfilehash: 4098b40c01085b266fa279107e5795b1283705cd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212027"
---
# <span data-ttu-id="71026-103">Get-Module</span><span class="sxs-lookup"><span data-stu-id="71026-103">Get-Module</span></span>

## <span data-ttu-id="71026-104">概要</span><span class="sxs-lookup"><span data-stu-id="71026-104">SYNOPSIS</span></span>
<span data-ttu-id="71026-105">現在のセッションにインポート済みの、またはインポート可能なモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-105">Gets the modules that have been imported or that can be imported into the current session.</span></span>

## <span data-ttu-id="71026-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="71026-106">SYNTAX</span></span>

### <span data-ttu-id="71026-107">読み込み済み (既定値)</span><span class="sxs-lookup"><span data-stu-id="71026-107">Loaded (Default)</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [<CommonParameters>]
```

### <span data-ttu-id="71026-108">使用可能</span><span class="sxs-lookup"><span data-stu-id="71026-108">Available</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [-ListAvailable]
 [-PSEdition <String>] [-Refresh] [<CommonParameters>]
```

### <span data-ttu-id="71026-109">PsSession</span><span class="sxs-lookup"><span data-stu-id="71026-109">PsSession</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable]
 [-PSEdition <String>] [-Refresh] -PSSession <PSSession> [<CommonParameters>]
```

### <span data-ttu-id="71026-110">CimSession</span><span class="sxs-lookup"><span data-stu-id="71026-110">CimSession</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable] [-Refresh]
 -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>] [<CommonParameters>]
```

## <span data-ttu-id="71026-111">Description</span><span class="sxs-lookup"><span data-stu-id="71026-111">DESCRIPTION</span></span>

<span data-ttu-id="71026-112">この `Get-Module` コマンドレットは、powershell セッションにインポートされた、またはインポートできる powershell モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-112">The `Get-Module` cmdlet gets the PowerShell modules that have been imported, or that can be imported, into a PowerShell session.</span></span>
<span data-ttu-id="71026-113">を返すモジュールオブジェクトに `Get-Module` は、モジュールに関する重要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="71026-113">The module object that `Get-Module` returns contains valuable information about the module.</span></span>
<span data-ttu-id="71026-114">また、 `Import-Module` コマンドレットやコマンドレットなど、他のコマンドレットにモジュールオブジェクトをパイプ処理することもでき `Remove-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="71026-114">You can also pipe the module objects to other cmdlets, such as the `Import-Module` and `Remove-Module` cmdlets.</span></span>

<span data-ttu-id="71026-115">パラメーターを指定しない場合、 `Get-Module` 現在のセッションにインポートされているモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-115">Without parameters, `Get-Module` gets modules that have been imported into the current session.</span></span>
<span data-ttu-id="71026-116">インストールされているモジュールをすべて取得するには、 **ListAvailable** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="71026-116">To get all installed modules, specify the **ListAvailable** parameter.</span></span>

<span data-ttu-id="71026-117">`Get-Module` モジュールを取得しますが、インポートしません。</span><span class="sxs-lookup"><span data-stu-id="71026-117">`Get-Module` gets modules, but it does not import them.</span></span>
<span data-ttu-id="71026-118">Windows PowerShell 3.0 以降では、モジュールのコマンドを使用すると、モジュールは自動的にインポートされますが、 `Get-Module` コマンドによって自動インポートがトリガーされることはありません。</span><span class="sxs-lookup"><span data-stu-id="71026-118">Starting in Windows PowerShell 3.0, modules are automatically imported when you use a command in the module, but a `Get-Module` command does not trigger an automatic import.</span></span>
<span data-ttu-id="71026-119">コマンドレットを使用して、モジュールをセッションにインポートすることもでき `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="71026-119">You can also import the modules into your session by using the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="71026-120">Windows PowerShell 3.0 以降では、リモートセッションからローカルセッションにモジュールを取得してインポートできます。</span><span class="sxs-lookup"><span data-stu-id="71026-120">Starting in Windows PowerShell 3.0, you can get and then, import modules from remote sessions into the local session.</span></span>
<span data-ttu-id="71026-121">この方法では、PowerShell の暗黙的なリモート処理機能を使用します。これは、コマンドレットを使用することと同じです `Import-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="71026-121">This strategy uses the Implicit Remoting feature of PowerShell and is equivalent to using the `Import-PSSession` cmdlet.</span></span>
<span data-ttu-id="71026-122">別のセッションからインポートされたモジュールでコマンドを使用すると、リモートセッションでコマンドが暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="71026-122">When you use commands in modules imported from another session, the commands run implicitly in the remote session.</span></span> <span data-ttu-id="71026-123">この機能を使用すると、ローカルセッションからリモートコンピューターを管理できます。</span><span class="sxs-lookup"><span data-stu-id="71026-123">This feature lets you manage the remote computer from the local session.</span></span>

<span data-ttu-id="71026-124">また、Windows PowerShell 3.0 以降では、およびを使用して `Get-Module` `Import-Module` COMMON INFORMATION MODEL (CIM) モジュールを取得およびインポートできます。このモジュールでは、コマンドレットがコマンドレット定義 XML (CDXML) ファイルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="71026-124">Also, starting in Windows PowerShell 3.0, you can use `Get-Module` and `Import-Module` to get and import Common Information Model (CIM) modules, in which the cmdlets are defined in Cmdlet Definition XML (CDXML) files.</span></span>
<span data-ttu-id="71026-125">この機能を使用すると、C++ で記述されたものなど、マネージコード以外のアセンブリに実装されているコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="71026-125">This feature lets you use cmdlets that are implemented in non-managed code assemblies, such as those written in C++.</span></span>

<span data-ttu-id="71026-126">これらの新機能により、 `Get-Module` との `Import-Module` コマンドレットは、Windows オペレーティングシステムを実行するコンピューターと他のオペレーティングシステムを実行するコンピューターを含む異種企業を管理するための主要なツールになります。</span><span class="sxs-lookup"><span data-stu-id="71026-126">With these new features, the `Get-Module` and `Import-Module` cmdlets become primary tools for managing heterogeneous enterprises that include computers that run the Windows operating system and computers that run other operating systems.</span></span>

<span data-ttu-id="71026-127">PowerShell と PowerShell リモート処理が有効になっている Windows オペレーティングシステムを実行しているリモートコンピューターを管理するには、リモートコンピューター上に **pssession** を作成し、の **pssession** パラメーターを使用して、 `Get-Module` **pssession** 内の PowerShell モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-127">To manage remote computers that run the Windows operating system that have PowerShell and PowerShell remoting enabled, create a **PSSession** on the remote computer and then use the **PSSession** parameter of `Get-Module` to get the PowerShell modules in the **PSSession** .</span></span>
<span data-ttu-id="71026-128">モジュールをインポートした後、現在のセッションでインポートしたコマンドを使用すると、コマンドはリモートコンピューター上の **PSSession** で暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="71026-128">When you import the modules, and then use the imported commands in the current session, the commands run implicitly in the **PSSession** on the remote computer.</span></span>
<span data-ttu-id="71026-129">この戦略を使用して、リモート コンピューターを管理できます。</span><span class="sxs-lookup"><span data-stu-id="71026-129">You can use this strategy to manage the remote computer.</span></span>

<span data-ttu-id="71026-130">同様の戦略を使用して、PowerShell リモート処理が有効になっていないコンピューターを管理できます。</span><span class="sxs-lookup"><span data-stu-id="71026-130">You can use a similar strategy to manage computers that do not have PowerShell remoting enabled.</span></span>
<span data-ttu-id="71026-131">これには、Windows オペレーティングシステムを実行していないコンピューターや、powershell を搭載していても PowerShell リモート処理が有効になっていないコンピューターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="71026-131">These include computers that are not running the Windows operating system, and computers that have PowerShell but do not have PowerShell remoting enabled.</span></span>

<span data-ttu-id="71026-132">まず、リモートコンピューターに CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="71026-132">Start by creating a CIM session on the remote computer.</span></span>
<span data-ttu-id="71026-133">CIM セッションは、リモートコンピューター上の Windows Management Instrumentation (WMI) に接続します。</span><span class="sxs-lookup"><span data-stu-id="71026-133">A CIM session is a connection to Windows Management Instrumentation (WMI) on the remote computer.</span></span>
<span data-ttu-id="71026-134">次に、の **CIMSession** パラメーターを使用して `Get-Module` 、CIM セッションから cim モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-134">Then use the **CIMSession** parameter of `Get-Module` to get CIM modules from the CIM session.</span></span>
<span data-ttu-id="71026-135">コマンドレットを使用して CIM モジュールをインポートし、インポートされたコマンドを実行すると、 `Import-Module` コマンドはリモートコンピューター上で暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="71026-135">When you import a CIM module by using the `Import-Module` cmdlet and then run the imported commands, the commands run implicitly on the remote computer.</span></span>
<span data-ttu-id="71026-136">この WMI と CIM の戦略を使用して、リモート コンピューターを管理できます。</span><span class="sxs-lookup"><span data-stu-id="71026-136">You can use this WMI and CIM strategy to manage the remote computer.</span></span>

## <span data-ttu-id="71026-137">例</span><span class="sxs-lookup"><span data-stu-id="71026-137">EXAMPLES</span></span>

### <span data-ttu-id="71026-138">例 1: 現在のセッションにインポートされたモジュールを取得する</span><span class="sxs-lookup"><span data-stu-id="71026-138">Example 1: Get modules imported into the current session</span></span>

```powershell
Get-Module
```

<span data-ttu-id="71026-139">このコマンドは、現在のセッションにインポートされているモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-139">This command gets modules that have been imported into the current session.</span></span>

### <span data-ttu-id="71026-140">例 2: インストールされているモジュールと使用可能なモジュールを取得する</span><span class="sxs-lookup"><span data-stu-id="71026-140">Example 2: Get installed modules and available modules</span></span>

```powershell
Get-Module -ListAvailable
```

<span data-ttu-id="71026-141">このコマンドは、コンピューターにインストールされていて現在のセッションにインポートできるモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-141">This command gets the modules that are installed on the computer and can be imported into the current session.</span></span>

<span data-ttu-id="71026-142">`Get-Module`**$env:P SModulePath** 環境変数で指定されたパスで使用可能なモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="71026-142">`Get-Module` looks for available modules in the path specified by the **$env:PSModulePath** environment variable.</span></span>
<span data-ttu-id="71026-143">**PSModulePath** の詳細については、「 [about_Modules](About/about_Modules.md)」および「 [about_Environment_Variables](About/about_Environment_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71026-143">For more information about **PSModulePath** , see [about_Modules](About/about_Modules.md) and [about_Environment_Variables](About/about_Environment_Variables.md).</span></span>

### <span data-ttu-id="71026-144">例 3: エクスポートされたすべてのファイルを取得する</span><span class="sxs-lookup"><span data-stu-id="71026-144">Example 3: Get all exported files</span></span>

```powershell
Get-Module -ListAvailable -All
```

<span data-ttu-id="71026-145">このコマンドは、すべての利用可能なモジュールのすべてのエクスポートされたファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-145">This command gets all of the exported files for all available modules.</span></span>

### <span data-ttu-id="71026-146">例 4: 完全修飾名でモジュールを取得する</span><span class="sxs-lookup"><span data-stu-id="71026-146">Example 4: Get a module by its fully qualified name</span></span>

```powershell
$FullyQualifedName = @{ModuleName="Microsoft.PowerShell.Management";ModuleVersion="3.1.0.0"}
Get-Module -FullyQualifiedName $FullyQualifedName | Format-Table -Property Name,Version
```

```Output
Name                             Version
----                             -------
Microsoft.PowerShell.Management  3.1.0.0
```

<span data-ttu-id="71026-147">このコマンドは、 **FullyQualifiedName** パラメーターを使用してモジュールの完全修飾名を指定することによって、 **管理** モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-147">This command gets the **Microsoft.PowerShell.Management** module by specifying the fully qualified name of the module by using the **FullyQualifiedName** parameter.</span></span>
<span data-ttu-id="71026-148">次に、結果をコマンドレットにパイプして、 `Format-Table` 結果を列見出しとして **名前** と **バージョン** を含むテーブルとして書式設定します。</span><span class="sxs-lookup"><span data-stu-id="71026-148">The command then pipes the results into the `Format-Table` cmdlet to format the results as a table with **Name** and **Version** as the column headings.</span></span>

### <span data-ttu-id="71026-149">例 5: モジュールのプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="71026-149">Example 5: Get properties of a module</span></span>

```powershell
Get-Module | Get-Member -MemberType Property | Format-Table Name
```

```Output
Name
----
AccessMode
Author
ClrVersion
CompanyName
Copyright
Definition
Description
DotNetFrameworkVersion
ExportedAliases
ExportedCmdlets
ExportedCommands
ExportedFormatFiles
ExportedFunctions
ExportedTypeFiles
ExportedVariables
ExportedWorkflows
FileList
Guid
HelpInfoUri
LogPipelineExecutionDetails
ModuleBase
ModuleList
ModuleType
Name
NestedModules
OnRemove
Path
PowerShellHostName
PowerShellHostVersion
PowerShellVersion
PrivateData
ProcessorArchitecture
RequiredAssemblies
RequiredModules
RootModule
Scripts
SessionState
Version
```

<span data-ttu-id="71026-150">このコマンドは、を返す **PSModuleInfo** オブジェクトのプロパティを取得し `Get-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="71026-150">This command gets the properties of the **PSModuleInfo** object that `Get-Module` returns.</span></span>
<span data-ttu-id="71026-151">モジュール ファイルごとに 1 つのオブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="71026-151">There is one object for each module file.</span></span>

<span data-ttu-id="71026-152">プロパティを使用して、モジュール オブジェクトを書式設定したり、フィルター処理したりできます。</span><span class="sxs-lookup"><span data-stu-id="71026-152">You can use the properties to format and filter the module objects.</span></span>
<span data-ttu-id="71026-153">プロパティの詳細については、「 [PSModuleInfo properties](/dotnet/api/system.management.automation.psmoduleinfo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71026-153">For more information about the properties, see [PSModuleInfo Properties](/dotnet/api/system.management.automation.psmoduleinfo).</span></span>

<span data-ttu-id="71026-154">出力には、Windows PowerShell 3.0 で導入された **作成者** や **CompanyName** などの新しいプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="71026-154">The output includes the new properties, such as **Author** and **CompanyName** , that were introduced in Windows PowerShell 3.0.</span></span>

### <span data-ttu-id="71026-155">例 6: すべてのモジュールを名前でグループ化する</span><span class="sxs-lookup"><span data-stu-id="71026-155">Example 6: Group all modules by name</span></span>

```powershell
Get-Module -ListAvailable -All | Format-Table -Property Name, Moduletype, Path -Groupby Name
```

```Output
Name: AppLocker

Name      ModuleType Path
----      ---------- ----
AppLocker   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\AppLocker\AppLocker.psd1


   Name: Appx

Name ModuleType Path
---- ---------- ----
Appx   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\en-US\Appx.psd1
Appx   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\Appx.psd1
Appx     Script C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\Appx.psm1


   Name: BestPractices

Name          ModuleType Path
----          ---------- ----
BestPractices   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\BestPractices\BestPractices.psd1


   Name: BitsTransfer

Name         ModuleType Path
----         ---------- ----
BitsTransfer   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\BitsTransfer\BitsTransfer.psd1
```

<span data-ttu-id="71026-156">このコマンドは、インポートされたモジュールファイルと使用可能なモジュールファイルの両方を取得し、モジュール名でグループ化します。</span><span class="sxs-lookup"><span data-stu-id="71026-156">This command gets all module files, both imported and available, and then groups them by module name.</span></span> <span data-ttu-id="71026-157">これにより、それぞれのスクリプトによってエクスポートされるモジュール ファイルを確認できます。</span><span class="sxs-lookup"><span data-stu-id="71026-157">This lets you see the module files that each script is exporting.</span></span>

### <span data-ttu-id="71026-158">例 7: モジュールマニフェストの内容を表示する</span><span class="sxs-lookup"><span data-stu-id="71026-158">Example 7: Display the contents of a module manifest</span></span>

<span data-ttu-id="71026-159">これらのコマンドは、Windows PowerShell **BitsTransfer** モジュールのモジュールマニフェストの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="71026-159">These commands display the contents of the module manifest for the Windows PowerShell **BitsTransfer** module.</span></span>

<span data-ttu-id="71026-160">モジュールにマニフェストファイルを含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="71026-160">Modules are not required to have manifest files.</span></span>
<span data-ttu-id="71026-161">マニフェストファイルがある場合、マニフェストファイルはバージョン番号を含めるためにのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="71026-161">When they do have a manifest file, the manifest file is required only to include a version number.</span></span>
<span data-ttu-id="71026-162">ただし、マニフェスト ファイルは、多くの場合、モジュール、その要件、およびその内容に関する有用な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="71026-162">However, manifest files often provide useful information about a module, its requirements, and its contents.</span></span>

```powershell
# First command
$m = Get-Module -list -Name BitsTransfer

# Second command
Get-Content $m.Path
```

```Output
@ {
    GUID               = "{8FA5064B-8479-4c5c-86EA-0D311FE48875}"
    Author             = "Microsoft Corporation"
    CompanyName        = "Microsoft Corporation"
    Copyright          = "Microsoft Corporation. All rights reserved."
    ModuleVersion      = "1.0.0.0"
    Description        = "Windows PowerShell File Transfer Module"
    PowerShellVersion  = "2.0"
    CLRVersion         = "2.0"
    NestedModules      = "Microsoft.BackgroundIntelligentTransfer.Management"
    FormatsToProcess   = "FileTransfer.Format.ps1xml"
    RequiredAssemblies = Join-Path $psScriptRoot "Microsoft.BackgroundIntelligentTransfer.Management.Interop.dll"
}
```

<span data-ttu-id="71026-163">最初のコマンドは、BitsTransfer モジュールを表す PSModuleInfo オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-163">The first command gets the PSModuleInfo object that represents BitsTransfer module.</span></span> <span data-ttu-id="71026-164">変数にオブジェクトを保存し `$m` ます。</span><span class="sxs-lookup"><span data-stu-id="71026-164">It saves the object in the `$m` variable.</span></span>

<span data-ttu-id="71026-165">2番目のコマンドは、コマンドレットを使用して、 `Get-Content` 指定されたパスのマニフェストファイルの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-165">The second command uses the `Get-Content` cmdlet to get the content of the manifest file in the specified path.</span></span> <span data-ttu-id="71026-166">ここでは、ドット付き表記を使用してマニフェスト ファイルへのパスを取得し、オブジェクトの Path プロパティに格納しています。</span><span class="sxs-lookup"><span data-stu-id="71026-166">It uses dot notation to get the path to the manifest file, which is stored in the Path property of the object.</span></span> <span data-ttu-id="71026-167">出力には、モジュール マニフェストの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="71026-167">The output shows the contents of the module manifest.</span></span>

### <span data-ttu-id="71026-168">例 8: モジュールディレクトリ内のファイルを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="71026-168">Example 8: List files in module directory</span></span>

```powershell
dir (Get-Module -ListAvailable FileTransfer).ModuleBase
```

```Output
Directory: C:\Windows\system32\WindowsPowerShell\v1.0\Modules\FileTransfer
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----        12/16/2008  12:36 PM            en-US
-a---        11/19/2008  11:30 PM      16184 FileTransfer.Format.ps1xml
-a---        11/20/2008  11:30 PM       1044 FileTransfer.psd1
-a---        12/16/2008  12:20 AM     108544 Microsoft.BackgroundIntelligentTransfer.Management.Interop.dll
```

<span data-ttu-id="71026-169">このコマンドは、モジュールのディレクトリ内のファイルを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="71026-169">This command lists the files in the directory of the module.</span></span>
<span data-ttu-id="71026-170">これは、インポートの前にモジュールの内容を確認するためのもう 1 つの方法です。</span><span class="sxs-lookup"><span data-stu-id="71026-170">This is another way to determine what is in a module before you import it.</span></span>
<span data-ttu-id="71026-171">モジュールによっては、ヘルプ ファイルやモジュールについて記述した ReadMe ファイルが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="71026-171">Some modules might have help files or ReadMe files that describe the module.</span></span>

### <span data-ttu-id="71026-172">例 9: コンピューターにインストールされているモジュールを取得する</span><span class="sxs-lookup"><span data-stu-id="71026-172">Example 9: Get modules installed on a computer</span></span>

```powershell
$s = New-PSSession -ComputerName Server01

Get-Module -PSSession $s -ListAvailable
```

<span data-ttu-id="71026-173">これらのコマンドは、Server01 コンピューターにインストールされているモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-173">These commands get the modules that are installed on the Server01 computer.</span></span>

<span data-ttu-id="71026-174">最初のコマンドは、コマンドレットを使用して、 `New-PSSession` Server01 コンピューター上に **PSSession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="71026-174">The first command uses the `New-PSSession` cmdlet to create a **PSSession** on the Server01 computer.</span></span> <span data-ttu-id="71026-175">このコマンドは、 **PSSession** を $s 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="71026-175">The command saves the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="71026-176">2番目のコマンドは、の **pssession** パラメーターと **ListAvailable** パラメーターを使用して、 `Get-Module` $s 変数内の **pssession** のモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-176">The second command uses the **PSSession** and **ListAvailable** parameters of `Get-Module` to get the modules in the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="71026-177">モジュールを他のセッションからコマンドレットにパイプする場合 `Import-Module` 、は `Import-Module` 暗黙的なリモート処理機能を使用して、モジュールを現在のセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="71026-177">If you pipe modules from other sessions to the `Import-Module` cmdlet, `Import-Module` imports the module into the current session by using the implicit remoting feature.</span></span>
<span data-ttu-id="71026-178">これは、コマンドレットを使用することと同じです `Import-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="71026-178">This is equivalent to using the `Import-PSSession` cmdlet.</span></span>
<span data-ttu-id="71026-179">現在のセッションに含まれるモジュールのコマンドレットを使用することができますが、これらのコマンドレットを使用するコマンドは、実際にはリモート セッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="71026-179">You can use the cmdlets from the module in the current session, but commands that use these cmdlets actually run the remote session.</span></span>
<span data-ttu-id="71026-180">詳細については、[`Import-Module`](Import-Module.md) および [`Import-PSSession`](../Microsoft.PowerShell.Utility/Import-PSSession.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71026-180">For more information, see [`Import-Module`](Import-Module.md) and [`Import-PSSession`](../Microsoft.PowerShell.Utility/Import-PSSession.md).</span></span>

### <span data-ttu-id="71026-181">例 10: Windows オペレーティングシステムを実行していないコンピューターを管理する</span><span class="sxs-lookup"><span data-stu-id="71026-181">Example 10: Manage a computer that does not run the Windows operating system</span></span>

<span data-ttu-id="71026-182">この例のコマンドを使用すると、Windows オペレーティングシステムを実行していないリモートコンピューターの記憶域システムを管理できます。</span><span class="sxs-lookup"><span data-stu-id="71026-182">The commands in this example enable you to manage the storage systems of a remote computer that is not running the Windows operating system.</span></span>
<span data-ttu-id="71026-183">この例では、コンピューターの管理者によってモジュール検出用の WMI プロバイダーがインストールされているため、CIM コマンドでプロバイダー用の既定値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="71026-183">In this example, because the administrator of the computer has installed the Module Discovery WMI provider, the CIM commands can use the default values, which are designed for the provider.</span></span>

```powershell
$cs = New-CimSession -ComputerName RSDGF03
Get-Module -CimSession $cs -Name Storage | Import-Module
Get-Command Get-Disk
```

```Output
CommandType     Name                  ModuleName
-----------     ----                  ----------
Function        Get-Disk              Storage
```

```powershell
Get-Disk
```

```Output
Number Friendly Name              OperationalStatus          Total Size Partition Style
------ -------------              -----------------          ---------- ---------------
0      Virtual HD ATA Device      Online                          40 GB MBR
```

<span data-ttu-id="71026-184">最初のコマンドは、 `New-CimSession` コマンドレットを使用して、RSDGF03 リモートコンピューター上にセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="71026-184">The first command uses the `New-CimSession` cmdlet to create a session on the RSDGF03 remote computer.</span></span> <span data-ttu-id="71026-185">このセッションは、リモート コンピューター上の WMI に接続します。</span><span class="sxs-lookup"><span data-stu-id="71026-185">The session connects to WMI on the remote computer.</span></span> <span data-ttu-id="71026-186">このコマンドは、CIM セッションを変数に保存し `$cs` ます。</span><span class="sxs-lookup"><span data-stu-id="71026-186">The command saves the CIM session in the `$cs` variable.</span></span>

<span data-ttu-id="71026-187">2番目のコマンドは、変数の CIM セッションを使用して、 `$cs` `Get-Module` RSDGF03 コンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="71026-187">The second command uses the CIM session in the `$cs` variable to run a `Get-Module` command on the RSDGF03 computer.</span></span> <span data-ttu-id="71026-188">ここでは、Name パラメーターを使用して、Storage モジュールを指定しています。</span><span class="sxs-lookup"><span data-stu-id="71026-188">The command uses the Name parameter to specify the Storage module.</span></span> <span data-ttu-id="71026-189">このコマンドは、パイプライン演算子 (|) を使用して、ストレージモジュールをコマンドレットに送信します。これにより `Import-Module` 、ローカルセッションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="71026-189">The command uses a pipeline operator (|) to send the Storage module to the `Import-Module` cmdlet, which imports it into the local session.</span></span>

<span data-ttu-id="71026-190">3番目のコマンドは、 `Get-Command` ストレージモジュールのコマンドでコマンドレットを実行し `Get-Disk` ます。</span><span class="sxs-lookup"><span data-stu-id="71026-190">The third command runs the `Get-Command` cmdlet on the `Get-Disk` command in the Storage module.</span></span>
<span data-ttu-id="71026-191">CIM モジュールをローカルセッションにインポートすると、PowerShell は CIM モジュールを表す CDXML ファイルを PowerShell スクリプトに変換します。これは、ローカルセッションの関数として表示されます。</span><span class="sxs-lookup"><span data-stu-id="71026-191">When you import a CIM module into the local session, PowerShell converts the CDXML files that represent the CIM module into PowerShell scripts, which appear as functions in the local session.</span></span>

<span data-ttu-id="71026-192">4番目のコマンドは、コマンドを実行し `Get-Disk` ます。</span><span class="sxs-lookup"><span data-stu-id="71026-192">The fourth command runs the `Get-Disk` command.</span></span> <span data-ttu-id="71026-193">コマンドはローカル セッションで入力されますが、暗黙的にインポート先のリモート コンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="71026-193">Although the command is typed in the local session, it runs implicitly on the remote computer from which it was imported.</span></span> <span data-ttu-id="71026-194">コマンドは、リモート コンピューターからオブジェクトを取得してローカル セッションに返します。</span><span class="sxs-lookup"><span data-stu-id="71026-194">The command gets objects from the remote computer and returns them to the local session.</span></span>

## <span data-ttu-id="71026-195">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="71026-195">PARAMETERS</span></span>

### <span data-ttu-id="71026-196">-All</span><span class="sxs-lookup"><span data-stu-id="71026-196">-All</span></span>

<span data-ttu-id="71026-197">このコマンドレットが各モジュールフォルダー内のすべてのモジュールを取得することを示します。これには、入れ子になったモジュール、マニフェスト (.psd1) ファイル、スクリプトモジュール (hbase-runner.psm1) ファイル、およびバイナリモジュール (.dll) ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="71026-197">Indicates that this cmdlet gets all modules in each module folder, including nested modules, manifest (.psd1) files, script module (.psm1) files, and binary module (.dll) files.</span></span>
<span data-ttu-id="71026-198">このパラメーターを指定しない場合、 `Get-Module` 各モジュールフォルダー内の既定のモジュールのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-198">Without this parameter, `Get-Module` gets only the default module in each module folder.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Loaded, Available
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="71026-199">-CimNamespace</span><span class="sxs-lookup"><span data-stu-id="71026-199">-CimNamespace</span></span>

<span data-ttu-id="71026-200">CIM モジュールを公開する代替 CIM プロバイダーの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="71026-200">Specifies the namespace of an alternate CIM provider that exposes CIM modules.</span></span>
<span data-ttu-id="71026-201">既定値は、モジュール検出用の WMI プロバイダーの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="71026-201">The default value is the namespace of the Module Discovery WMI provider.</span></span>

<span data-ttu-id="71026-202">Windows オペレーティングシステムを実行していないコンピューターやデバイスから CIM モジュールを取得するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="71026-202">Use this parameter to get CIM modules from computers and devices that are not running the Windows operating system.</span></span>

<span data-ttu-id="71026-203">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="71026-203">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="71026-204">-CimResourceUri</span><span class="sxs-lookup"><span data-stu-id="71026-204">-CimResourceUri</span></span>

<span data-ttu-id="71026-205">CIM モジュールの代替の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="71026-205">Specifies an alternate location for CIM modules.</span></span>
<span data-ttu-id="71026-206">既定値は、リモートコンピューター上のモジュール検出 WMI プロバイダーのリソース URI です。</span><span class="sxs-lookup"><span data-stu-id="71026-206">The default value is the resource URI of the Module Discovery WMI provider on the remote computer.</span></span>

<span data-ttu-id="71026-207">Windows オペレーティングシステムを実行していないコンピューターやデバイスから CIM モジュールを取得するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="71026-207">Use this parameter to get CIM modules from computers and devices that are not running the Windows operating system.</span></span>

<span data-ttu-id="71026-208">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="71026-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Uri
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="71026-209">-CimSession</span><span class="sxs-lookup"><span data-stu-id="71026-209">-CimSession</span></span>

<span data-ttu-id="71026-210">リモート コンピューター上の CIM セッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="71026-210">Specifies a CIM session on the remote computer.</span></span>
<span data-ttu-id="71026-211">CIM セッションを含む変数、または [CimSession](/powershell/module/cimcmdlets/get-cimsession) コマンドなどの cim セッションを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="71026-211">Enter a variable that contains the CIM session or a command that gets the CIM session, such as a [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) command.</span></span>

<span data-ttu-id="71026-212">`Get-Module` は、CIM セッション接続を使用して、リモートコンピューターからモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-212">`Get-Module` uses the CIM session connection to get modules from the remote computer.</span></span>
<span data-ttu-id="71026-213">コマンドレットを使用してモジュールをインポート `Import-Module` し、現在のセッションでインポートされたモジュールのコマンドを使用すると、コマンドは実際にはリモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="71026-213">When you import the module by using the `Import-Module` cmdlet and use the commands from the imported module in the current session, the commands actually run on the remote computer.</span></span>

<span data-ttu-id="71026-214">このパラメーターを使用すると、Windows オペレーティングシステムを実行していないコンピューターやデバイス、PowerShell を搭載しているが PowerShell リモート処理が有効になっていないコンピューターからモジュールを取得できます。</span><span class="sxs-lookup"><span data-stu-id="71026-214">You can use this parameter to get modules from computers and devices that are not running the Windows operating system, and computers that have PowerShell, but do not have PowerShell remoting enabled.</span></span>

<span data-ttu-id="71026-215">**CimSession** パラメーターは、 **CIMSession** 内のすべてのモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-215">The **CimSession** parameter gets all modules in the **CIMSession** .</span></span>
<span data-ttu-id="71026-216">ただし、インポートできるのは、CIM ベースのモジュールとコマンドレット定義 XML (CDXML) ベースのモジュールのみです。</span><span class="sxs-lookup"><span data-stu-id="71026-216">However, you can import only CIM-based and Cmdlet Definition XML (CDXML)-based modules.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession
Parameter Sets: CimSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="71026-217">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="71026-217">-FullyQualifiedName</span></span>

<span data-ttu-id="71026-218">モジュールの名前を **modulの** 指定オブジェクトの形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="71026-218">Specifies names of modules in the form of **ModuleSpecification** objects.</span></span>
<span data-ttu-id="71026-219">これらのオブジェクトについては、MSDN ライブラリの「 [modulの注意事項コンストラクター (Hashtable)](https://msdn.microsoft.com/library/jj136290) 」の「解説」で説明されています。</span><span class="sxs-lookup"><span data-stu-id="71026-219">These objects are described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](https://msdn.microsoft.com/library/jj136290) in the MSDN library.</span></span>
<span data-ttu-id="71026-220">たとえば、 **FullyQualifiedName** パラメーターは、次の形式で指定されたモジュール名を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="71026-220">For example, the **FullyQualifiedName** parameter accepts a module name that is specified in the following formats:</span></span>

- <span data-ttu-id="71026-221">@ {ModuleName = "ModuleName";ModuleVersion = "version_number"}</span><span class="sxs-lookup"><span data-stu-id="71026-221">@{ModuleName = "modulename"; ModuleVersion = "version_number"}</span></span>
- <span data-ttu-id="71026-222">@ {ModuleName = "ModuleName";ModuleVersion = "version_number";Guid = "GUID"}</span><span class="sxs-lookup"><span data-stu-id="71026-222">@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}</span></span>

<span data-ttu-id="71026-223">**ModuleName** と **ModuleVersion** は必須ですが、 **Guid** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="71026-223">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="71026-224">**Name** パラメーターと同じコマンドで **FullyQualifiedName** パラメーターを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="71026-224">You cannot specify the **FullyQualifiedName** parameter in the same command as a **Name** parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="71026-225">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="71026-225">-ListAvailable</span></span>

<span data-ttu-id="71026-226">このコマンドレットがインストールされているすべてのモジュールを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="71026-226">Indicates that this cmdlet gets all installed modules.</span></span>
<span data-ttu-id="71026-227">`Get-Module`**PSModulePath** 環境変数に示されているパス内のモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-227">`Get-Module` gets modules in paths listed in the **PSModulePath** environment variable.</span></span>
<span data-ttu-id="71026-228">このパラメーターを指定しない場合、 `Get-Module` **PSModulePath** 環境変数に一覧表示されているモジュールと、現在のセッションに読み込まれているモジュールのみが取得されます。</span><span class="sxs-lookup"><span data-stu-id="71026-228">Without this parameter, `Get-Module` gets only the modules that are both listed in the **PSModulePath** environment variable, and that are loaded in the current session.</span></span>
<span data-ttu-id="71026-229">**ListAvailable** は、 **PSModulePath** 環境変数に含まれていないモジュールが現在のセッションに読み込まれている場合でも、これらのモジュールに関する情報を返しません。</span><span class="sxs-lookup"><span data-stu-id="71026-229">**ListAvailable** does not return information about modules that are not found in the **PSModulePath** environment variable, even if those modules are loaded in the current session.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Available, PsSession, CimSession
Aliases:

Required: True (Available), False (PsSession, CimSession)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="71026-230">-Name</span><span class="sxs-lookup"><span data-stu-id="71026-230">-Name</span></span>

<span data-ttu-id="71026-231">このコマンドレットが取得するモジュールの名前または名前パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="71026-231">Specifies names or name patterns of modules that this cmdlet gets.</span></span>
<span data-ttu-id="71026-232">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="71026-232">Wildcard characters are permitted.</span></span>
<span data-ttu-id="71026-233">パイプを使用して名前をにパイプすることもでき `Get-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="71026-233">You can also pipe the names to `Get-Module`.</span></span>
<span data-ttu-id="71026-234">**Name** パラメーターと同じコマンドで **FullyQualifiedName** パラメーターを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="71026-234">You cannot specify the **FullyQualifiedName** parameter in the same command as a **Name** parameter.</span></span>

<span data-ttu-id="71026-235">**名前** には、モジュール GUID を値として使用できません。</span><span class="sxs-lookup"><span data-stu-id="71026-235">**Name** cannot accept a module GUID as a value.</span></span>
<span data-ttu-id="71026-236">GUID を指定してモジュールを返すには、代わりに **FullyQualifiedName** を使用します。</span><span class="sxs-lookup"><span data-stu-id="71026-236">To return modules by specifying a GUID, use **FullyQualifiedName** instead.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="71026-237">-PSEdition</span><span class="sxs-lookup"><span data-stu-id="71026-237">-PSEdition</span></span>

<span data-ttu-id="71026-238">指定された PowerShell のエディションをサポートするモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-238">Gets the modules that support specified edition of PowerShell.</span></span>

<span data-ttu-id="71026-239">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="71026-239">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="71026-240">デスクトップ</span><span class="sxs-lookup"><span data-stu-id="71026-240">Desktop</span></span>
- <span data-ttu-id="71026-241">コア</span><span class="sxs-lookup"><span data-stu-id="71026-241">Core</span></span>

<span data-ttu-id="71026-242">Get-Module コマンドレットは、指定された値の **PSModuleInfo** オブジェクトの **CompatiblePSEditions** プロパティを確認し、その値が設定されているモジュールだけを返します。</span><span class="sxs-lookup"><span data-stu-id="71026-242">The Get-Module cmdlet checks **CompatiblePSEditions** property of **PSModuleInfo** object for the specified value and returns only those modules that have it set.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="71026-243">**Desktop Edition:** .NET Framework 上に構築され、Windows の完全フットプリント エディション (Server Core、Windows Desktop など) で実行される PowerShell のバージョンをターゲットとするスクリプトおよびモジュールと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="71026-243">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
> - <span data-ttu-id="71026-244">**Core Edition:** .NET Core 上に構築されており、Nano Server や Windows IoT などの Windows の縮小エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="71026-244">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

```yaml
Type: System.String
Parameter Sets: PsSession, Available
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="71026-245">-PSSession</span><span class="sxs-lookup"><span data-stu-id="71026-245">-PSSession</span></span>

<span data-ttu-id="71026-246">指定されたユーザー管理の PowerShell セッション ( **PSSession** ) 内のモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-246">Gets the modules in the specified user-managed PowerShell session ( **PSSession** ).</span></span>
<span data-ttu-id="71026-247">セッションを含む変数、コマンドなどのセッションを取得するコマンド、またはコマンドなどのセッションを作成するコマンドを入力し `Get-PSSession` `New-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="71026-247">Enter a variable that contains the session, a command that gets the session, such as a `Get-PSSession` command, or a command that creates the session, such as a `New-PSSession` command.</span></span>

<span data-ttu-id="71026-248">セッションがリモートコンピューターに接続されている場合は、 **ListAvailable** パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71026-248">When the session is connected to a remote computer, you must specify the **ListAvailable** parameter.</span></span>

<span data-ttu-id="71026-249">`Get-Module` **Pssession** パラメーターを使用するコマンドは、コマンドレットを使用して `Invoke-Command` `Get-Module -ListAvailable` **pssession** でコマンドを実行することと同じです。</span><span class="sxs-lookup"><span data-stu-id="71026-249">A `Get-Module` command that uses the **PSSession** parameter is equivalent to using the `Invoke-Command` cmdlet to run a `Get-Module -ListAvailable` command in a **PSSession** .</span></span>

<span data-ttu-id="71026-250">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="71026-250">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: PsSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="71026-251">-更新</span><span class="sxs-lookup"><span data-stu-id="71026-251">-Refresh</span></span>

<span data-ttu-id="71026-252">このコマンドレットがインストールされているコマンドのキャッシュを更新することを示します。</span><span class="sxs-lookup"><span data-stu-id="71026-252">Indicates that this cmdlet refreshes the cache of installed commands.</span></span>
<span data-ttu-id="71026-253">コマンドのキャッシュは、セッションの開始時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="71026-253">The command cache is created when the session starts.</span></span>
<span data-ttu-id="71026-254">この `Get-Command` コマンドレットを使用すると、セッションにインポートされていないモジュールからコマンドを取得できます。</span><span class="sxs-lookup"><span data-stu-id="71026-254">It enables the `Get-Command` cmdlet to get commands from modules that are not imported into the session.</span></span>

<span data-ttu-id="71026-255">このパラメーターは、セッションが開始された時点からモジュールの内容が変化する開発およびテスト シナリオ用に用意されています。</span><span class="sxs-lookup"><span data-stu-id="71026-255">This parameter is designed for development and testing scenarios in which the contents of modules have changed since the session started.</span></span>

<span data-ttu-id="71026-256">コマンドで **Refresh** パラメーターを指定する場合は、 **ListAvailable** を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71026-256">When you specify the **Refresh** parameter in a command, you must specify **ListAvailable** .</span></span>

<span data-ttu-id="71026-257">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="71026-257">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PsSession, Available, CimSession
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="71026-258">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="71026-258">CommonParameters</span></span>

<span data-ttu-id="71026-259">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="71026-259">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="71026-260">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71026-260">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="71026-261">入力</span><span class="sxs-lookup"><span data-stu-id="71026-261">INPUTS</span></span>

### <span data-ttu-id="71026-262">System.String</span><span class="sxs-lookup"><span data-stu-id="71026-262">System.String</span></span>

<span data-ttu-id="71026-263">パイプを使用してモジュール名をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="71026-263">You can pipe module names to this cmdlet.</span></span>

## <span data-ttu-id="71026-264">出力</span><span class="sxs-lookup"><span data-stu-id="71026-264">OUTPUTS</span></span>

### <span data-ttu-id="71026-265">PSModuleInfo (システム管理)</span><span class="sxs-lookup"><span data-stu-id="71026-265">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="71026-266">このコマンドレットは、モジュールを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="71026-266">This cmdlet returns objects that represent modules.</span></span>
<span data-ttu-id="71026-267">**ListAvailable** パラメーターを指定すると、は `Get-Module` **moduleinfogrouping** オブジェクトを返します。これは、同じプロパティとメソッドを持つ **PSModuleInfo** オブジェクトの一種です。</span><span class="sxs-lookup"><span data-stu-id="71026-267">When you specify the **ListAvailable** parameter, `Get-Module` returns a **ModuleInfoGrouping** object, which is a type of **PSModuleInfo** object that has the same properties and methods.</span></span>

## <span data-ttu-id="71026-268">注</span><span class="sxs-lookup"><span data-stu-id="71026-268">NOTES</span></span>

- <span data-ttu-id="71026-269">Windows PowerShell 3.0 以降では、PowerShell に含まれるコアコマンドはモジュールにパッケージ化されています。</span><span class="sxs-lookup"><span data-stu-id="71026-269">Beginning in Windows PowerShell 3.0, the core commands that are included in PowerShell are packaged in modules.</span></span> <span data-ttu-id="71026-270">この例外は、スナップイン ( **add-pssnapin** ) である、 **PowerShell のコア** です。</span><span class="sxs-lookup"><span data-stu-id="71026-270">The exception is **Microsoft.PowerShell.Core** , which is a snap-in ( **PSSnapin** ).</span></span> <span data-ttu-id="71026-271">既定では、 **Microsoft.PowerShell.Core** スナップインのみがセッションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="71026-271">By default, only the **Microsoft.PowerShell.Core** snap-in is added to the session.</span></span>
<span data-ttu-id="71026-272">モジュールは初回使用時に自動的にインポートされ、コマンドレットを使用して `Import-Module` インポートできます。</span><span class="sxs-lookup"><span data-stu-id="71026-272">Modules are imported automatically on first use and you can use the `Import-Module` cmdlet to import them.</span></span>
- <span data-ttu-id="71026-273">Windows PowerShell 3.0 以降では、PowerShell でインストールされるコアコマンドはモジュールにパッケージ化されています。</span><span class="sxs-lookup"><span data-stu-id="71026-273">Starting in Windows PowerShell 3.0, the core commands that are installed with PowerShell are packaged in modules.</span></span> <span data-ttu-id="71026-274">Windows PowerShell 2.0、およびそれ以降のバージョンの PowerShell で古いスタイルのセッションを作成するホストプログラムでは、コアコマンドはスナップイン ( **PSSnapins** ) にパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="71026-274">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of PowerShell, the core commands are packaged in snap-ins ( **PSSnapins** ).</span></span> <span data-ttu-id="71026-275">例外は、常にスナップインである、 **PowerShell です** 。</span><span class="sxs-lookup"><span data-stu-id="71026-275">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="71026-276">また、コマンドレットによって開始されるようなリモートセッション `New-PSSession` は、コアスナップインを含む古いスタイルのセッションです。</span><span class="sxs-lookup"><span data-stu-id="71026-276">Also, remote sessions, such as those started by the `New-PSSession` cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="71026-277">コアモジュールで新しいスタイルのセッションを作成する **CreateDefault2** メソッドの詳細については、MSDN ライブラリの「 [CreateDefault2 メソッド](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71026-277">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see [CreateDefault2 Method](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2) in the MSDN library.</span></span>

- <span data-ttu-id="71026-278">`Get-Module`**PSModulePath** 環境変数の値 ($Env:P SModulePath) に格納されている場所のモジュールのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="71026-278">`Get-Module` only gets modules in locations that are stored in the value of the **PSModulePath** environment variable ($env:PSModulePath).</span></span> <span data-ttu-id="71026-279">コマンドレットの **Path** パラメーターを使用して `Import-Module` 、他の場所にあるモジュールをインポートできますが、コマンドレットを使用してそれらを取得することはできません `Get-Module` 。</span><span class="sxs-lookup"><span data-stu-id="71026-279">You can use the **Path** parameter of the `Import-Module` cmdlet to import modules in other locations, but you cannot use the `Get-Module` cmdlet to get them.</span></span>
- <span data-ttu-id="71026-280">また、PowerShell 3.0 以降では、を返すオブジェクトに新しいプロパティが追加されました `Get-Module` 。これにより、モジュールをインポートする前でも簡単に学習できるようになります。</span><span class="sxs-lookup"><span data-stu-id="71026-280">Also, starting in PowerShell 3.0, new properties have been added to the object that `Get-Module` returns that make it easier to learn about modules even before they are imported.</span></span> <span data-ttu-id="71026-281">インポートする前に、すべてのプロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="71026-281">All properties are populated before importing.</span></span> <span data-ttu-id="71026-282">これには、モジュールによってエクスポートされるコマンドを一覧表示する **ExportedCommands** 、 **ExportedCmdlets** 、 **ExportedFunctions** の各プロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="71026-282">These include the **ExportedCommands** , **ExportedCmdlets** and **ExportedFunctions** properties that list the commands that the module exports.</span></span>
- <span data-ttu-id="71026-283">**ListAvailable** パラメーターは、適切な形式のモジュールのみを取得します。つまり、基本名がモジュールフォルダーの名前と同じファイルを少なくとも1つ含むフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="71026-283">The **ListAvailable** parameter gets only well-formed modules, that is, folders that contain at least one file whose base name is the same as the name of the module folder.</span></span> <span data-ttu-id="71026-284">基本名は、ファイル名拡張子のない名前です。</span><span class="sxs-lookup"><span data-stu-id="71026-284">The base name is the name without the file name extension.</span></span> <span data-ttu-id="71026-285">異なる名前を持つファイルを含むフォルダーは、コンテナーと見なされますが、モジュールではありません。</span><span class="sxs-lookup"><span data-stu-id="71026-285">Folders that contain files that have different names are considered to be containers, but not modules.</span></span>

  <span data-ttu-id="71026-286">.Dll ファイルとして実装されていてもモジュールフォルダーには含まれていないモジュールを取得するには、 **ListAvailable** と **All** の両方のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="71026-286">To get modules that are implemented as .dll files, but are not enclosed in a module folder, specify both the **ListAvailable** and **All** parameters.</span></span>

- <span data-ttu-id="71026-287">CIM セッション機能を使用するには、リモート コンピューターにおいて、WS-Management リモート処理と Common Information Model (CIM) 標準の Microsoft 実装である Windows Management Instrumentation (WMI) が必要です。</span><span class="sxs-lookup"><span data-stu-id="71026-287">To use the CIM session feature, the remote computer must have WS-Management remoting and Windows Management Instrumentation (WMI), which is the Microsoft implementation of the Common Information Model (CIM) standard.</span></span> <span data-ttu-id="71026-288">さらに、モジュール検出用の WMI プロバイダーまたは同じ基本機能を備えた代替 WMI プロバイダーもコンピューターに必要です。</span><span class="sxs-lookup"><span data-stu-id="71026-288">The computer must also have the Module Discovery WMI provider or an alternate WMI provider that has the same basic features.</span></span>

  <span data-ttu-id="71026-289">CIM セッション機能は、Windows オペレーティングシステムを実行していないコンピューターと PowerShell を搭載している Windows コンピューターで使用できますが、PowerShell リモート処理は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="71026-289">You can use the CIM session feature on computers that are not running the Windows operating system and on Windows computers that have PowerShell, but do not have PowerShell remoting enabled.</span></span>

  <span data-ttu-id="71026-290">また、CIM パラメーターを使用して、PowerShell リモート処理が有効になっているコンピューターから CIM モジュールを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="71026-290">You can also use the CIM parameters to get CIM modules from computers that have PowerShell remoting enabled.</span></span> <span data-ttu-id="71026-291">これには、ローカルコンピューターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="71026-291">This includes the local computer.</span></span>
<span data-ttu-id="71026-292">ローカルコンピューターに CIM セッションを作成すると、PowerShell は WMI ではなく DCOM を使用してセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="71026-292">When you create a CIM session on the local computer, PowerShell uses DCOM, instead of WMI, to create the session.</span></span>

## <span data-ttu-id="71026-293">関連リンク</span><span class="sxs-lookup"><span data-stu-id="71026-293">RELATED LINKS</span></span>

[<span data-ttu-id="71026-294">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="71026-294">Get-CimSession</span></span>](../CimCmdlets/Get-CimSession.md)

[<span data-ttu-id="71026-295">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="71026-295">New-CimSession</span></span>](../CimCmdlets/New-CimSession.md)

[<span data-ttu-id="71026-296">about_Modules</span><span class="sxs-lookup"><span data-stu-id="71026-296">about_Modules</span></span>](About/about_Modules.md)

[<span data-ttu-id="71026-297">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="71026-297">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="71026-298">Import-Module</span><span class="sxs-lookup"><span data-stu-id="71026-298">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="71026-299">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="71026-299">Import-PSSession</span></span>](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[<span data-ttu-id="71026-300">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="71026-300">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="71026-301">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="71026-301">Remove-Module</span></span>](Remove-Module.md)