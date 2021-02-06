---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Module
ms.openlocfilehash: 0802e025f2bedce0ec312df9878c9524558930cb
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "99602635"
---
# <span data-ttu-id="7b88a-102">Get-Module</span><span class="sxs-lookup"><span data-stu-id="7b88a-102">Get-Module</span></span>

## <span data-ttu-id="7b88a-103">概要</span><span class="sxs-lookup"><span data-stu-id="7b88a-103">SYNOPSIS</span></span>
<span data-ttu-id="7b88a-104">現在のセッションでインポートされたモジュール、または PSModulePath からインポートできるモジュールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-104">List the modules imported in the current session or that can be imported from the PSModulePath.</span></span>

## <span data-ttu-id="7b88a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7b88a-105">SYNTAX</span></span>

### <span data-ttu-id="7b88a-106">読み込み済み (既定値)</span><span class="sxs-lookup"><span data-stu-id="7b88a-106">Loaded (Default)</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [<CommonParameters>]
```

### <span data-ttu-id="7b88a-107">利用可能</span><span class="sxs-lookup"><span data-stu-id="7b88a-107">Available</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [-ListAvailable]
 [-PSEdition <String>] [-SkipEditionCheck] [-Refresh] [<CommonParameters>]
```

### <span data-ttu-id="7b88a-108">PsSession</span><span class="sxs-lookup"><span data-stu-id="7b88a-108">PsSession</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable]
 [-PSEdition <String>] [-SkipEditionCheck] [-Refresh] -PSSession <PSSession> [<CommonParameters>]
```

### <span data-ttu-id="7b88a-109">CimSession</span><span class="sxs-lookup"><span data-stu-id="7b88a-109">CimSession</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable]
 [-SkipEditionCheck] [-Refresh] -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="7b88a-110">Description</span><span class="sxs-lookup"><span data-stu-id="7b88a-110">DESCRIPTION</span></span>

<span data-ttu-id="7b88a-111">`Get-Module`コマンドレットにより、インポートされた、またはインポート可能な powershell モジュールが powershell セッションに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-111">The `Get-Module` cmdlet lists the PowerShell modules that have been imported, or that can be imported, into a PowerShell session.</span></span> <span data-ttu-id="7b88a-112">パラメーターを指定しない場合、 `Get-Module` 現在のセッションにインポートされているモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-112">Without parameters, `Get-Module` gets modules that have been imported into the current session.</span></span> <span data-ttu-id="7b88a-113">**ListAvailable** パラメーターは、PSModulePath 環境変数 () で指定されたパスからインポートできるモジュールを一覧表示するために使用され `$env:PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-113">The **ListAvailable** parameter is used to list the modules that are available to be imported from the paths specified in the PSModulePath environment variable (`$env:PSModulePath`).</span></span>

<span data-ttu-id="7b88a-114">を返すモジュールオブジェクトに `Get-Module` は、モジュールに関する重要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b88a-114">The module object that `Get-Module` returns contains valuable information about the module.</span></span> <span data-ttu-id="7b88a-115">また、 `Import-Module` コマンドレットやコマンドレットなど、他のコマンドレットにモジュールオブジェクトをパイプ処理することもでき `Remove-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-115">You can also pipe the module objects to other cmdlets, such as the `Import-Module` and `Remove-Module` cmdlets.</span></span>

<span data-ttu-id="7b88a-116">`Get-Module` モジュールを一覧表示しますが、インポートしません。</span><span class="sxs-lookup"><span data-stu-id="7b88a-116">`Get-Module` lists modules, but it does not import them.</span></span> <span data-ttu-id="7b88a-117">Windows PowerShell 3.0 以降では、モジュールのコマンドを使用すると、モジュールは自動的にインポートされますが、 `Get-Module` コマンドによって自動インポートがトリガーされることはありません。</span><span class="sxs-lookup"><span data-stu-id="7b88a-117">Starting in Windows PowerShell 3.0, modules are automatically imported when you use a command in the module, but a `Get-Module` command does not trigger an automatic import.</span></span> <span data-ttu-id="7b88a-118">コマンドレットを使用して、モジュールをセッションにインポートすることもでき `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-118">You can also import the modules into your session using the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="7b88a-119">Windows PowerShell 3.0 以降では、リモートセッションからローカルセッションにモジュールを取得してインポートできます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-119">Starting in Windows PowerShell 3.0, you can get and then, import modules from remote sessions into the local session.</span></span> <span data-ttu-id="7b88a-120">この方法では、PowerShell の暗黙的なリモート処理機能を使用します。これは、コマンドレットを使用することと同じです `Import-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="7b88a-120">This strategy uses the Implicit Remoting feature of PowerShell and is equivalent to using the `Import-PSSession` cmdlet.</span></span> <span data-ttu-id="7b88a-121">別のセッションからインポートされたモジュールでコマンドを使用すると、リモートセッションでコマンドが暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-121">When you use commands in modules imported from another session, the commands run implicitly in the remote session.</span></span> <span data-ttu-id="7b88a-122">この機能を使用すると、ローカルセッションからリモートコンピューターを管理できます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-122">This feature lets you manage the remote computer from the local session.</span></span>

<span data-ttu-id="7b88a-123">また、Windows PowerShell 3.0 以降では、およびを使用して `Get-Module` `Import-Module` COMMON INFORMATION MODEL (CIM) モジュールを取得およびインポートできます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-123">Also, starting in Windows PowerShell 3.0, you can use `Get-Module` and `Import-Module` to get and import Common Information Model (CIM) modules.</span></span> <span data-ttu-id="7b88a-124">CIM モジュールは、コマンドレット定義 XML (CDXML) ファイルのコマンドレットを定義します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-124">CIM modules define cmdlets in Cmdlet Definition XML (CDXML) files.</span></span> <span data-ttu-id="7b88a-125">この機能を使用すると、C++ で記述されたものなど、マネージコード以外のアセンブリに実装されているコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-125">This feature lets you use cmdlets that are implemented in non-managed code assemblies, such as those written in C++.</span></span>

<span data-ttu-id="7b88a-126">暗黙的なリモート処理を使用すると、PowerShell リモート処理が有効になっているリモートコンピューターを管理できます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-126">Implicit remoting can be used to manage remote computers that have PowerShell remoting enabled.</span></span>
<span data-ttu-id="7b88a-127">リモートコンピューター上に **pssession** を作成し、の **pssession** パラメーターを使用して、 `Get-Module` リモートセッションの PowerShell モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-127">Create a **PSSession** on the remote computer and then use the **PSSession** parameter of `Get-Module` to get the PowerShell modules in the remote session.</span></span> <span data-ttu-id="7b88a-128">リモートセッションからモジュールをインポートすると、インポートしたコマンドはリモートコンピューター上のセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-128">When you import a module from the remote session the imported commands run in the session on the remote computer.</span></span>

<span data-ttu-id="7b88a-129">同様の戦略を使用して、PowerShell リモート処理が有効になっていないコンピューターを管理できます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-129">You can use a similar strategy to manage computers that do not have PowerShell remoting enabled.</span></span>
<span data-ttu-id="7b88a-130">これには、Windows オペレーティングシステムを実行していないコンピューターや、powershell を搭載していても PowerShell リモート処理が有効になっていないコンピューターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-130">These include computers that are not running the Windows operating system, and computers that have PowerShell but do not have PowerShell remoting enabled.</span></span>

<span data-ttu-id="7b88a-131">まず、リモートコンピューターに CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-131">Start by creating a CIM session on the remote computer.</span></span> <span data-ttu-id="7b88a-132">CIM セッションは、リモートコンピューター上の Windows Management Instrumentation (WMI) に接続します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-132">A CIM session is a connection to Windows Management Instrumentation (WMI) on the remote computer.</span></span> <span data-ttu-id="7b88a-133">次に、の **CIMSession** パラメーターを使用して `Get-Module` 、CIM セッションから cim モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-133">Then use the **CIMSession** parameter of `Get-Module` to get CIM modules from the CIM session.</span></span> <span data-ttu-id="7b88a-134">コマンドレットを使用して CIM モジュールをインポートし、インポートされたコマンドを実行すると、 `Import-Module` コマンドはリモートコンピューター上で暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-134">When you import a CIM module by using the `Import-Module` cmdlet and then run the imported commands, the commands run implicitly on the remote computer.</span></span> <span data-ttu-id="7b88a-135">この WMI と CIM の戦略を使用して、リモート コンピューターを管理できます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-135">You can use this WMI and CIM strategy to manage the remote computer.</span></span>

## <span data-ttu-id="7b88a-136">例</span><span class="sxs-lookup"><span data-stu-id="7b88a-136">EXAMPLES</span></span>

### <span data-ttu-id="7b88a-137">例 1: 現在のセッションにインポートされたモジュールを取得する</span><span class="sxs-lookup"><span data-stu-id="7b88a-137">Example 1: Get modules imported into the current session</span></span>

```powershell
Get-Module
```

<span data-ttu-id="7b88a-138">このコマンドは、現在のセッションにインポートされているモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-138">This command gets modules that have been imported into the current session.</span></span>

### <span data-ttu-id="7b88a-139">例 2: インストールされているモジュールと使用可能なモジュールを取得する</span><span class="sxs-lookup"><span data-stu-id="7b88a-139">Example 2: Get installed modules and available modules</span></span>

```powershell
Get-Module -ListAvailable
```

<span data-ttu-id="7b88a-140">このコマンドは、コンピューターにインストールされていて現在のセッションにインポートできるモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-140">This command gets the modules that are installed on the computer and can be imported into the current session.</span></span>

<span data-ttu-id="7b88a-141">`Get-Module`**$env:P SModulePath** 環境変数で指定されたパスで使用可能なモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-141">`Get-Module` looks for available modules in the path specified by the **$env:PSModulePath** environment variable.</span></span> <span data-ttu-id="7b88a-142">**PSModulePath** の詳細については、「[about_Modules](About/about_Modules.md)」および「[about_Environment_Variables](About/about_Environment_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b88a-142">For more information about **PSModulePath**, see [about_Modules](About/about_Modules.md) and [about_Environment_Variables](About/about_Environment_Variables.md).</span></span>

### <span data-ttu-id="7b88a-143">例 3: エクスポートされたすべてのファイルを取得する</span><span class="sxs-lookup"><span data-stu-id="7b88a-143">Example 3: Get all exported files</span></span>

```powershell
Get-Module -ListAvailable -All
```

<span data-ttu-id="7b88a-144">このコマンドは、すべての利用可能なモジュールのすべてのエクスポートされたファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-144">This command gets all of the exported files for all available modules.</span></span>

### <span data-ttu-id="7b88a-145">例 4: 完全修飾名でモジュールを取得する</span><span class="sxs-lookup"><span data-stu-id="7b88a-145">Example 4: Get a module by its fully qualified name</span></span>

```powershell
$FullyQualifedName = @{ModuleName="Microsoft.PowerShell.Management";ModuleVersion="3.1.0.0"}
Get-Module -FullyQualifiedName $FullyQualifedName | Format-Table -Property Name,Version
```

```Output
Name                             Version
----                             -------
Microsoft.PowerShell.Management  3.1.0.0
```

<span data-ttu-id="7b88a-146">このコマンドは、 **FullyQualifiedName** パラメーターを使用してモジュールの完全修飾名を指定することによって、**管理** モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-146">This command gets the **Microsoft.PowerShell.Management** module by specifying the fully qualified name of the module by using the **FullyQualifiedName** parameter.</span></span> <span data-ttu-id="7b88a-147">次に、結果をコマンドレットにパイプして、 `Format-Table` 結果を列見出しとして **名前** と **バージョン** を含むテーブルとして書式設定します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-147">The command then pipes the results into the `Format-Table` cmdlet to format the results as a table with **Name** and **Version** as the column headings.</span></span>

### <span data-ttu-id="7b88a-148">例 5: モジュールのプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="7b88a-148">Example 5: Get properties of a module</span></span>

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

<span data-ttu-id="7b88a-149">このコマンドは、を返す **PSModuleInfo** オブジェクトのプロパティを取得し `Get-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-149">This command gets the properties of the **PSModuleInfo** object that `Get-Module` returns.</span></span> <span data-ttu-id="7b88a-150">モジュール ファイルごとに 1 つのオブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="7b88a-150">There is one object for each module file.</span></span>

<span data-ttu-id="7b88a-151">プロパティを使用して、モジュール オブジェクトを書式設定したり、フィルター処理したりできます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-151">You can use the properties to format and filter the module objects.</span></span> <span data-ttu-id="7b88a-152">プロパティの詳細については、「 [PSModuleInfo properties](/dotnet/api/system.management.automation.psmoduleinfo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b88a-152">For more information about the properties, see [PSModuleInfo Properties](/dotnet/api/system.management.automation.psmoduleinfo).</span></span>

<span data-ttu-id="7b88a-153">出力には、Windows PowerShell 3.0 で導入された **作成者** や **CompanyName** などの新しいプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b88a-153">The output includes the new properties, such as **Author** and **CompanyName**, that were introduced in Windows PowerShell 3.0.</span></span>

### <span data-ttu-id="7b88a-154">例 6: すべてのモジュールを名前でグループ化する</span><span class="sxs-lookup"><span data-stu-id="7b88a-154">Example 6: Group all modules by name</span></span>

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

<span data-ttu-id="7b88a-155">このコマンドは、インポートされたモジュールファイルと使用可能なモジュールファイルの両方を取得し、モジュール名でグループ化します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-155">This command gets all module files, both imported and available, and then groups them by module name.</span></span> <span data-ttu-id="7b88a-156">これにより、それぞれのスクリプトによってエクスポートされるモジュール ファイルを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-156">This lets you see the module files that each script is exporting.</span></span>

### <span data-ttu-id="7b88a-157">例 7: モジュールマニフェストの内容を表示する</span><span class="sxs-lookup"><span data-stu-id="7b88a-157">Example 7: Display the contents of a module manifest</span></span>

<span data-ttu-id="7b88a-158">これらのコマンドは、Windows PowerShell **BitsTransfer** モジュールのモジュールマニフェストの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-158">These commands display the contents of the module manifest for the Windows PowerShell **BitsTransfer** module.</span></span>

<span data-ttu-id="7b88a-159">モジュールにマニフェストファイルを含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7b88a-159">Modules are not required to have manifest files.</span></span> <span data-ttu-id="7b88a-160">マニフェストファイルがある場合、マニフェストファイルはバージョン番号を含めるためにのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="7b88a-160">When they do have a manifest file, the manifest file is required only to include a version number.</span></span> <span data-ttu-id="7b88a-161">ただし、マニフェスト ファイルは、多くの場合、モジュール、その要件、およびその内容に関する有用な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-161">However, manifest files often provide useful information about a module, its requirements, and its contents.</span></span>

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

<span data-ttu-id="7b88a-162">最初のコマンドは、BitsTransfer モジュールを表す PSModuleInfo オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-162">The first command gets the PSModuleInfo object that represents BitsTransfer module.</span></span> <span data-ttu-id="7b88a-163">変数にオブジェクトを保存し `$m` ます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-163">It saves the object in the `$m` variable.</span></span>

<span data-ttu-id="7b88a-164">2番目のコマンドは、コマンドレットを使用して、 `Get-Content` 指定されたパスのマニフェストファイルの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-164">The second command uses the `Get-Content` cmdlet to get the content of the manifest file in the specified path.</span></span> <span data-ttu-id="7b88a-165">ここでは、ドット付き表記を使用してマニフェスト ファイルへのパスを取得し、オブジェクトの Path プロパティに格納しています。</span><span class="sxs-lookup"><span data-stu-id="7b88a-165">It uses dot notation to get the path to the manifest file, which is stored in the Path property of the object.</span></span> <span data-ttu-id="7b88a-166">出力には、モジュール マニフェストの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-166">The output shows the contents of the module manifest.</span></span>

### <span data-ttu-id="7b88a-167">例 8: モジュールディレクトリ内のファイルを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="7b88a-167">Example 8: List files in module directory</span></span>

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

<span data-ttu-id="7b88a-168">このコマンドは、モジュールのディレクトリ内のファイルを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-168">This command lists the files in the directory of the module.</span></span> <span data-ttu-id="7b88a-169">これは、インポートの前にモジュールの内容を確認するためのもう 1 つの方法です。</span><span class="sxs-lookup"><span data-stu-id="7b88a-169">This is another way to determine what is in a module before you import it.</span></span> <span data-ttu-id="7b88a-170">モジュールによっては、ヘルプ ファイルやモジュールについて記述した ReadMe ファイルが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="7b88a-170">Some modules might have help files or ReadMe files that describe the module.</span></span>

### <span data-ttu-id="7b88a-171">例 9: コンピューターにインストールされているモジュールを取得する</span><span class="sxs-lookup"><span data-stu-id="7b88a-171">Example 9: Get modules installed on a computer</span></span>

```powershell
$s = New-PSSession -ComputerName Server01

Get-Module -PSSession $s -ListAvailable
```

<span data-ttu-id="7b88a-172">これらのコマンドは、Server01 コンピューターにインストールされているモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-172">These commands get the modules that are installed on the Server01 computer.</span></span>

<span data-ttu-id="7b88a-173">最初のコマンドは、コマンドレットを使用して、 `New-PSSession` Server01 コンピューター上に **PSSession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-173">The first command uses the `New-PSSession` cmdlet to create a **PSSession** on the Server01 computer.</span></span> <span data-ttu-id="7b88a-174">このコマンドは、 **PSSession** を $s 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-174">The command saves the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="7b88a-175">2番目のコマンドは、の **pssession** パラメーターと **ListAvailable** パラメーターを使用して、 `Get-Module` 変数内の **pssession** のモジュールを取得し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-175">The second command uses the **PSSession** and **ListAvailable** parameters of `Get-Module` to get the modules in the **PSSession** in the `$s` variable.</span></span>

<span data-ttu-id="7b88a-176">モジュールを他のセッションからコマンドレットにパイプする場合 `Import-Module` 、は `Import-Module` 暗黙的なリモート処理機能を使用して、モジュールを現在のセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="7b88a-176">If you pipe modules from other sessions to the `Import-Module` cmdlet, `Import-Module` imports the module into the current session by using the implicit remoting feature.</span></span> <span data-ttu-id="7b88a-177">これは、コマンドレットを使用することと同じです `Import-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="7b88a-177">This is equivalent to using the `Import-PSSession` cmdlet.</span></span> <span data-ttu-id="7b88a-178">現在のセッションに含まれるモジュールのコマンドレットを使用することができますが、これらのコマンドレットを使用するコマンドは、実際にはリモート セッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-178">You can use the cmdlets from the module in the current session, but commands that use these cmdlets actually run the remote session.</span></span> <span data-ttu-id="7b88a-179">詳細については、[`Import-Module`](Import-Module.md) および [`Import-PSSession`](../Microsoft.PowerShell.Utility/Import-PSSession.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b88a-179">For more information, see [`Import-Module`](Import-Module.md) and [`Import-PSSession`](../Microsoft.PowerShell.Utility/Import-PSSession.md).</span></span>

### <span data-ttu-id="7b88a-180">例 10: Windows オペレーティングシステムを実行していないコンピューターを管理する</span><span class="sxs-lookup"><span data-stu-id="7b88a-180">Example 10: Manage a computer that does not run the Windows operating system</span></span>

<span data-ttu-id="7b88a-181">この例のコマンドを使用すると、Windows オペレーティングシステムを実行していないリモートコンピューターの記憶域システムを管理できます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-181">The commands in this example enable you to manage the storage systems of a remote computer that is not running the Windows operating system.</span></span>
<span data-ttu-id="7b88a-182">この例では、コンピューターの管理者によってモジュール検出用の WMI プロバイダーがインストールされているため、CIM コマンドでプロバイダー用の既定値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-182">In this example, because the administrator of the computer has installed the Module Discovery WMI provider, the CIM commands can use the default values, which are designed for the provider.</span></span>

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

<span data-ttu-id="7b88a-183">最初のコマンドは、 `New-CimSession` コマンドレットを使用して、RSDGF03 リモートコンピューター上にセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-183">The first command uses the `New-CimSession` cmdlet to create a session on the RSDGF03 remote computer.</span></span> <span data-ttu-id="7b88a-184">このセッションは、リモート コンピューター上の WMI に接続します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-184">The session connects to WMI on the remote computer.</span></span> <span data-ttu-id="7b88a-185">このコマンドは、CIM セッションを変数に保存し `$cs` ます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-185">The command saves the CIM session in the `$cs` variable.</span></span>

<span data-ttu-id="7b88a-186">2番目のコマンドは、変数の CIM セッションを使用して、 `$cs` `Get-Module` RSDGF03 コンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-186">The second command uses the CIM session in the `$cs` variable to run a `Get-Module` command on the RSDGF03 computer.</span></span> <span data-ttu-id="7b88a-187">ここでは、Name パラメーターを使用して、Storage モジュールを指定しています。</span><span class="sxs-lookup"><span data-stu-id="7b88a-187">The command uses the Name parameter to specify the Storage module.</span></span> <span data-ttu-id="7b88a-188">このコマンドは、パイプライン演算子 (|) を使用して、ストレージモジュールをコマンドレットに送信します。これにより `Import-Module` 、ローカルセッションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-188">The command uses a pipeline operator (|) to send the Storage module to the `Import-Module` cmdlet, which imports it into the local session.</span></span>

<span data-ttu-id="7b88a-189">3番目のコマンドは、 `Get-Command` ストレージモジュールのコマンドでコマンドレットを実行し `Get-Disk` ます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-189">The third command runs the `Get-Command` cmdlet on the `Get-Disk` command in the Storage module.</span></span>
<span data-ttu-id="7b88a-190">CIM モジュールをローカルセッションにインポートすると、PowerShell は CIM モジュールを表す CDXML ファイルを PowerShell スクリプトに変換します。これは、ローカルセッションの関数として表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-190">When you import a CIM module into the local session, PowerShell converts the CDXML files that represent the CIM module into PowerShell scripts, which appear as functions in the local session.</span></span>

<span data-ttu-id="7b88a-191">4番目のコマンドは、コマンドを実行し `Get-Disk` ます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-191">The fourth command runs the `Get-Disk` command.</span></span> <span data-ttu-id="7b88a-192">コマンドはローカル セッションで入力されますが、暗黙的にインポート先のリモート コンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-192">Although the command is typed in the local session, it runs implicitly on the remote computer from which it was imported.</span></span> <span data-ttu-id="7b88a-193">コマンドは、リモート コンピューターからオブジェクトを取得してローカル セッションに返します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-193">The command gets objects from the remote computer and returns them to the local session.</span></span>

## <span data-ttu-id="7b88a-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7b88a-194">PARAMETERS</span></span>

### <span data-ttu-id="7b88a-195">-All</span><span class="sxs-lookup"><span data-stu-id="7b88a-195">-All</span></span>

<span data-ttu-id="7b88a-196">このコマンドレットが各モジュールフォルダー内のすべてのモジュールを取得することを示します。これには、入れ子になったモジュール、マニフェスト (.psd1) ファイル、スクリプトモジュール (hbase-runner.psm1) ファイル、およびバイナリモジュール (.dll) ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-196">Indicates that this cmdlet gets all modules in each module folder, including nested modules, manifest (.psd1) files, script module (.psm1) files, and binary module (.dll) files.</span></span> <span data-ttu-id="7b88a-197">このパラメーターを指定しない場合、 `Get-Module` 各モジュールフォルダー内の既定のモジュールのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-197">Without this parameter, `Get-Module` gets only the default module in each module folder.</span></span>

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

### <span data-ttu-id="7b88a-198">-CimNamespace</span><span class="sxs-lookup"><span data-stu-id="7b88a-198">-CimNamespace</span></span>

<span data-ttu-id="7b88a-199">CIM モジュールを公開する代替 CIM プロバイダーの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-199">Specifies the namespace of an alternate CIM provider that exposes CIM modules.</span></span> <span data-ttu-id="7b88a-200">既定値は、モジュール検出用の WMI プロバイダーの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="7b88a-200">The default value is the namespace of the Module Discovery WMI provider.</span></span>

<span data-ttu-id="7b88a-201">Windows オペレーティングシステムを実行していないコンピューターやデバイスから CIM モジュールを取得するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-201">Use this parameter to get CIM modules from computers and devices that are not running the Windows operating system.</span></span>

<span data-ttu-id="7b88a-202">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7b88a-202">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="7b88a-203">-CimResourceUri</span><span class="sxs-lookup"><span data-stu-id="7b88a-203">-CimResourceUri</span></span>

<span data-ttu-id="7b88a-204">CIM モジュールの代替の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-204">Specifies an alternate location for CIM modules.</span></span> <span data-ttu-id="7b88a-205">既定値は、リモートコンピューター上のモジュール検出 WMI プロバイダーのリソース URI です。</span><span class="sxs-lookup"><span data-stu-id="7b88a-205">The default value is the resource URI of the Module Discovery WMI provider on the remote computer.</span></span>

<span data-ttu-id="7b88a-206">Windows オペレーティングシステムを実行していないコンピューターやデバイスから CIM モジュールを取得するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-206">Use this parameter to get CIM modules from computers and devices that are not running the Windows operating system.</span></span>

<span data-ttu-id="7b88a-207">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7b88a-207">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="7b88a-208">-CimSession</span><span class="sxs-lookup"><span data-stu-id="7b88a-208">-CimSession</span></span>

<span data-ttu-id="7b88a-209">リモート コンピューター上の CIM セッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-209">Specifies a CIM session on the remote computer.</span></span> <span data-ttu-id="7b88a-210">CIM セッションを含む変数、または [CimSession](/powershell/module/cimcmdlets/get-cimsession) コマンドなどの cim セッションを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-210">Enter a variable that contains the CIM session or a command that gets the CIM session, such as a [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) command.</span></span>

<span data-ttu-id="7b88a-211">`Get-Module` は、CIM セッション接続を使用して、リモートコンピューターからモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-211">`Get-Module` uses the CIM session connection to get modules from the remote computer.</span></span> <span data-ttu-id="7b88a-212">コマンドレットを使用してモジュールをインポート `Import-Module` し、現在のセッションでインポートされたモジュールのコマンドを使用すると、コマンドは実際にはリモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-212">When you import the module by using the `Import-Module` cmdlet and use the commands from the imported module in the current session, the commands actually run on the remote computer.</span></span>

<span data-ttu-id="7b88a-213">このパラメーターを使用すると、Windows オペレーティングシステムを実行していないコンピューターやデバイス、PowerShell を搭載しているが PowerShell リモート処理が有効になっていないコンピューターからモジュールを取得できます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-213">You can use this parameter to get modules from computers and devices that are not running the Windows operating system, and computers that have PowerShell, but do not have PowerShell remoting enabled.</span></span>

<span data-ttu-id="7b88a-214">**CimSession** パラメーターは、**CIMSession** 内のすべてのモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-214">The **CimSession** parameter gets all modules in the **CIMSession**.</span></span> <span data-ttu-id="7b88a-215">ただし、インポートできるのは、CIM ベースのモジュールとコマンドレット定義 XML (CDXML) ベースのモジュールのみです。</span><span class="sxs-lookup"><span data-stu-id="7b88a-215">However, you can import only CIM-based and Cmdlet Definition XML (CDXML)-based modules.</span></span>

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

### <span data-ttu-id="7b88a-216">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="7b88a-216">-FullyQualifiedName</span></span>

<span data-ttu-id="7b88a-217">**Modul特定** のオブジェクトの形式で指定された名前を持つモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-217">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span> <span data-ttu-id="7b88a-218">「 [Modulの認識コンストラクター (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_)」の「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b88a-218">See the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="7b88a-219">たとえば、 **FullyQualifiedModule** パラメーターは、次のいずれかの形式で指定されたモジュール名を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-219">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in either of these formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="7b88a-220">**ModuleName** と **ModuleVersion** は必須ですが、**Guid** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7b88a-220">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span> <span data-ttu-id="7b88a-221">**モジュール** パラメーターと同じコマンドで **FullyQualifiedModule** パラメーターを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="7b88a-221">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="7b88a-222">2つのパラメーターは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="7b88a-222">the two parameters are mutually exclusive.</span></span>

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

### <span data-ttu-id="7b88a-223">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="7b88a-223">-ListAvailable</span></span>

<span data-ttu-id="7b88a-224">このコマンドレットがインストールされているすべてのモジュールを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-224">Indicates that this cmdlet gets all installed modules.</span></span> <span data-ttu-id="7b88a-225">`Get-Module`**PSModulePath** 環境変数に示されているパス内のモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-225">`Get-Module` gets modules in paths listed in the **PSModulePath** environment variable.</span></span> <span data-ttu-id="7b88a-226">このパラメーターを指定しない場合、 `Get-Module` **PSModulePath** 環境変数に一覧表示されているモジュールと、現在のセッションに読み込まれているモジュールのみが取得されます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-226">Without this parameter, `Get-Module` gets only the modules that are both listed in the **PSModulePath** environment variable, and that are loaded in the current session.</span></span> <span data-ttu-id="7b88a-227">**ListAvailable** は、**PSModulePath** 環境変数に含まれていないモジュールが現在のセッションに読み込まれている場合でも、これらのモジュールに関する情報を返しません。</span><span class="sxs-lookup"><span data-stu-id="7b88a-227">**ListAvailable** does not return information about modules that are not found in the **PSModulePath** environment variable, even if those modules are loaded in the current session.</span></span>

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

### <span data-ttu-id="7b88a-228">-Name</span><span class="sxs-lookup"><span data-stu-id="7b88a-228">-Name</span></span>

<span data-ttu-id="7b88a-229">このコマンドレットが取得するモジュールの名前または名前パターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-229">Specifies names or name patterns of modules that this cmdlet gets.</span></span> <span data-ttu-id="7b88a-230">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-230">Wildcard characters are permitted.</span></span> <span data-ttu-id="7b88a-231">パイプを使用して名前をにパイプすることもでき `Get-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-231">You can also pipe the names to `Get-Module`.</span></span> <span data-ttu-id="7b88a-232">**Name** パラメーターと同じコマンドで **FullyQualifiedName** パラメーターを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="7b88a-232">You cannot specify the **FullyQualifiedName** parameter in the same command as a **Name** parameter.</span></span>

<span data-ttu-id="7b88a-233">**名前** には、モジュール GUID を値として使用できません。</span><span class="sxs-lookup"><span data-stu-id="7b88a-233">**Name** cannot accept a module GUID as a value.</span></span>
<span data-ttu-id="7b88a-234">GUID を指定してモジュールを返すには、代わりに **FullyQualifiedName** を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-234">To return modules by specifying a GUID, use **FullyQualifiedName** instead.</span></span>

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

### <span data-ttu-id="7b88a-235">-PSEdition</span><span class="sxs-lookup"><span data-stu-id="7b88a-235">-PSEdition</span></span>

<span data-ttu-id="7b88a-236">指定された PowerShell のエディションをサポートするモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-236">Gets the modules that support specified edition of PowerShell.</span></span>

<span data-ttu-id="7b88a-237">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7b88a-237">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7b88a-238">デスクトップ</span><span class="sxs-lookup"><span data-stu-id="7b88a-238">Desktop</span></span>
- <span data-ttu-id="7b88a-239">Core</span><span class="sxs-lookup"><span data-stu-id="7b88a-239">Core</span></span>

<span data-ttu-id="7b88a-240">Get-Module コマンドレットは、指定された値の **PSModuleInfo** オブジェクトの **CompatiblePSEditions** プロパティを確認し、その値が設定されているモジュールだけを返します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-240">The Get-Module cmdlet checks **CompatiblePSEditions** property of **PSModuleInfo** object for the specified value and returns only those modules that have it set.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="7b88a-241">**Desktop Edition:** .NET Framework 上に構築され、Windows の完全フットプリント エディション (Server Core、Windows Desktop など) で実行される PowerShell のバージョンをターゲットとするスクリプトおよびモジュールと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="7b88a-241">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
> - <span data-ttu-id="7b88a-242">**コア エディション:** .NET Core 上に構築されており、Nano Server や Windows IoT などの Windows の縮小エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-242">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

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

### <span data-ttu-id="7b88a-243">-PSSession</span><span class="sxs-lookup"><span data-stu-id="7b88a-243">-PSSession</span></span>

<span data-ttu-id="7b88a-244">指定されたユーザー管理の PowerShell セッション (**PSSession**) 内のモジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-244">Gets the modules in the specified user-managed PowerShell session (**PSSession**).</span></span> <span data-ttu-id="7b88a-245">セッションを含む変数、コマンドなどのセッションを取得するコマンド、またはコマンドなどのセッションを作成するコマンドを入力し `Get-PSSession` `New-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-245">Enter a variable that contains the session, a command that gets the session, such as a `Get-PSSession` command, or a command that creates the session, such as a `New-PSSession` command.</span></span>

<span data-ttu-id="7b88a-246">セッションがリモートコンピューターに接続されている場合は、 **ListAvailable** パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b88a-246">When the session is connected to a remote computer, you must specify the **ListAvailable** parameter.</span></span>

<span data-ttu-id="7b88a-247">`Get-Module` **Pssession** パラメーターを使用するコマンドは、コマンドレットを使用して `Invoke-Command` `Get-Module -ListAvailable` **pssession** でコマンドを実行することと同じです。</span><span class="sxs-lookup"><span data-stu-id="7b88a-247">A `Get-Module` command that uses the **PSSession** parameter is equivalent to using the `Invoke-Command` cmdlet to run a `Get-Module -ListAvailable` command in a **PSSession**.</span></span>

<span data-ttu-id="7b88a-248">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7b88a-248">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="7b88a-249">-更新</span><span class="sxs-lookup"><span data-stu-id="7b88a-249">-Refresh</span></span>

<span data-ttu-id="7b88a-250">このコマンドレットがインストールされているコマンドのキャッシュを更新することを示します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-250">Indicates that this cmdlet refreshes the cache of installed commands.</span></span> <span data-ttu-id="7b88a-251">コマンドのキャッシュは、セッションの開始時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-251">The command cache is created when the session starts.</span></span> <span data-ttu-id="7b88a-252">この `Get-Command` コマンドレットを使用すると、セッションにインポートされていないモジュールからコマンドを取得できます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-252">It enables the `Get-Command` cmdlet to get commands from modules that are not imported into the session.</span></span>

<span data-ttu-id="7b88a-253">このパラメーターは、セッションが開始された時点からモジュールの内容が変化する開発およびテスト シナリオ用に用意されています。</span><span class="sxs-lookup"><span data-stu-id="7b88a-253">This parameter is designed for development and testing scenarios in which the contents of modules have changed since the session started.</span></span>

<span data-ttu-id="7b88a-254">コマンドで **Refresh** パラメーターを指定する場合は、 **ListAvailable** を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b88a-254">When you specify the **Refresh** parameter in a command, you must specify **ListAvailable**.</span></span>

<span data-ttu-id="7b88a-255">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7b88a-255">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Available, PsSession, CimSession
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7b88a-256">-SkipEditionCheck</span><span class="sxs-lookup"><span data-stu-id="7b88a-256">-SkipEditionCheck</span></span>

<span data-ttu-id="7b88a-257">フィールドのチェックをスキップし `CompatiblePSEditions` ます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-257">Skips the check of the `CompatiblePSEditions` field.</span></span>

<span data-ttu-id="7b88a-258">既定では、Get-Module は、 `%windir%\System32\WindowsPowerShell\v1.0\Modules` フィールドにを指定していないディレクトリ内のモジュールを省略 `Core` `CompatiblePSEditions` します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-258">By default, Get-Module will omit modules in the `%windir%\System32\WindowsPowerShell\v1.0\Modules` directory that do not specify `Core` in the `CompatiblePSEditions` field.</span></span> <span data-ttu-id="7b88a-259">このスイッチが設定されている場合、 `Core` Powershell Core と互換性のない Windows powershell モジュールパスにあるモジュールが返されるように、を指定せずにモジュールが含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="7b88a-259">When this switch is set, modules without `Core` will be included, so that modules under the Windows PowerShell module path that are incompatible with PowerShell Core will be returned.</span></span>

<span data-ttu-id="7b88a-260">MacOS と Linux では、このパラメーターは何も行いません。</span><span class="sxs-lookup"><span data-stu-id="7b88a-260">On macOS and Linux, this parameter does nothing.</span></span>

<span data-ttu-id="7b88a-261">詳細については、「 [about_PowerShell_Editions](About/about_PowerShell_Editions.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b88a-261">See [about_PowerShell_Editions](About/about_PowerShell_Editions.md) for more information.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Available, PsSession, CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7b88a-262">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7b88a-262">CommonParameters</span></span>

<span data-ttu-id="7b88a-263">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7b88a-263">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7b88a-264">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b88a-264">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7b88a-265">入力</span><span class="sxs-lookup"><span data-stu-id="7b88a-265">INPUTS</span></span>

### <span data-ttu-id="7b88a-266">System.String</span><span class="sxs-lookup"><span data-stu-id="7b88a-266">System.String</span></span>

<span data-ttu-id="7b88a-267">パイプを使用してモジュール名をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-267">You can pipe module names to this cmdlet.</span></span>

## <span data-ttu-id="7b88a-268">出力</span><span class="sxs-lookup"><span data-stu-id="7b88a-268">OUTPUTS</span></span>

### <span data-ttu-id="7b88a-269">PSModuleInfo (システム管理)</span><span class="sxs-lookup"><span data-stu-id="7b88a-269">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="7b88a-270">このコマンドレットは、モジュールを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-270">This cmdlet returns objects that represent modules.</span></span>
<span data-ttu-id="7b88a-271">**ListAvailable** パラメーターを指定すると、は `Get-Module` **moduleinfogrouping** オブジェクトを返します。これは、同じプロパティとメソッドを持つ **PSModuleInfo** オブジェクトの一種です。</span><span class="sxs-lookup"><span data-stu-id="7b88a-271">When you specify the **ListAvailable** parameter, `Get-Module` returns a **ModuleInfoGrouping** object, which is a type of **PSModuleInfo** object that has the same properties and methods.</span></span>

## <span data-ttu-id="7b88a-272">注</span><span class="sxs-lookup"><span data-stu-id="7b88a-272">NOTES</span></span>

- <span data-ttu-id="7b88a-273">Windows PowerShell 3.0 以降では、PowerShell に含まれるコアコマンドはモジュールにパッケージ化されています。</span><span class="sxs-lookup"><span data-stu-id="7b88a-273">Beginning in Windows PowerShell 3.0, the core commands that are included in PowerShell are packaged in modules.</span></span> <span data-ttu-id="7b88a-274">この例外は、スナップイン (**add-pssnapin**) である、 **PowerShell のコア** です。</span><span class="sxs-lookup"><span data-stu-id="7b88a-274">The exception is **Microsoft.PowerShell.Core**, which is a snap-in (**PSSnapin**).</span></span> <span data-ttu-id="7b88a-275">既定では、**Microsoft.PowerShell.Core** スナップインのみがセッションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-275">By default, only the **Microsoft.PowerShell.Core** snap-in is added to the session.</span></span> <span data-ttu-id="7b88a-276">モジュールは初回使用時に自動的にインポートされ、コマンドレットを使用して `Import-Module` インポートできます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-276">Modules are imported automatically on first use and you can use the `Import-Module` cmdlet to import them.</span></span>

- <span data-ttu-id="7b88a-277">Windows PowerShell 2.0、およびそれ以降のバージョンの PowerShell で古いスタイルのセッションを作成するホストプログラムでは、コアコマンドはスナップイン (**PSSnapins**) にパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-277">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of PowerShell, the core commands are packaged in snap-ins (**PSSnapins**).</span></span> <span data-ttu-id="7b88a-278">例外は、常にスナップインである、 **PowerShell です**。</span><span class="sxs-lookup"><span data-stu-id="7b88a-278">The exception is **Microsoft.PowerShell.Core**, which is always a snap-in.</span></span> <span data-ttu-id="7b88a-279">また、コマンドレットによって開始されるようなリモートセッション `New-PSSession` は、コアスナップインを含む古いスタイルのセッションです。</span><span class="sxs-lookup"><span data-stu-id="7b88a-279">Also, remote sessions, such as those started by the `New-PSSession` cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="7b88a-280">コアモジュールで新しいスタイルのセッションを作成する **CreateDefault2** メソッドの詳細については、「 [CreateDefault2 メソッド](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b88a-280">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see [CreateDefault2 Method](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).</span></span>

- <span data-ttu-id="7b88a-281">`Get-Module`**PSModulePath** 環境変数の値 ($Env:P SModulePath) に格納されている場所のモジュールのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-281">`Get-Module` only gets modules in locations that are stored in the value of the **PSModulePath** environment variable ($env:PSModulePath).</span></span> <span data-ttu-id="7b88a-282">コマンドレットでは、 `Import-Module` 他の場所にモジュールをインポートできますが、コマンドレットを使用してモジュールを取得することはできません `Get-Module` 。</span><span class="sxs-lookup"><span data-stu-id="7b88a-282">The `Import-Module` cmdlet can import modules in other locations, but you cannot use the `Get-Module` cmdlet to get them.</span></span>

- <span data-ttu-id="7b88a-283">また、PowerShell 3.0 以降では、を返すオブジェクトに新しいプロパティが追加されました `Get-Module` 。これにより、モジュールをインポートする前でも簡単に学習できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7b88a-283">Also, starting in PowerShell 3.0, new properties have been added to the object that `Get-Module` returns that make it easier to learn about modules even before they are imported.</span></span> <span data-ttu-id="7b88a-284">インポートする前に、すべてのプロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-284">All properties are populated before importing.</span></span> <span data-ttu-id="7b88a-285">これには、モジュールによってエクスポートされるコマンドを一覧表示する **ExportedCommands**、 **ExportedCmdlets** 、 **ExportedFunctions** の各プロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-285">These include the **ExportedCommands**, **ExportedCmdlets** and **ExportedFunctions** properties that list the commands that the module exports.</span></span>

- <span data-ttu-id="7b88a-286">**ListAvailable** パラメーターは、適切な形式のモジュールのみを取得します。つまり、基本名がモジュールフォルダーの名前と同じファイルを少なくとも1つ含むフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="7b88a-286">The **ListAvailable** parameter gets only well-formed modules, that is, folders that contain at least one file whose base name is the same as the name of the module folder.</span></span> <span data-ttu-id="7b88a-287">基本名は、ファイル名拡張子のない名前です。</span><span class="sxs-lookup"><span data-stu-id="7b88a-287">The base name is the name without the file name extension.</span></span> <span data-ttu-id="7b88a-288">異なる名前を持つファイルを含むフォルダーは、コンテナーと見なされますが、モジュールではありません。</span><span class="sxs-lookup"><span data-stu-id="7b88a-288">Folders that contain files that have different names are considered to be containers, but not modules.</span></span>

  <span data-ttu-id="7b88a-289">DLL ファイルとして実装されていてもモジュールフォルダーには含まれていないモジュールを取得するには、 **ListAvailable** と **All** の両方のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-289">To get modules that are implemented as DLL files, but are not enclosed in a module folder, specify both the **ListAvailable** and **All** parameters.</span></span>

- <span data-ttu-id="7b88a-290">CIM セッション機能を使用するには、リモート コンピューターにおいて、WS-Management リモート処理と Common Information Model (CIM) 標準の Microsoft 実装である Windows Management Instrumentation (WMI) が必要です。</span><span class="sxs-lookup"><span data-stu-id="7b88a-290">To use the CIM session feature, the remote computer must have WS-Management remoting and Windows Management Instrumentation (WMI), which is the Microsoft implementation of the Common Information Model (CIM) standard.</span></span> <span data-ttu-id="7b88a-291">さらに、モジュール検出用の WMI プロバイダーまたは同じ基本機能を備えた代替 WMI プロバイダーもコンピューターに必要です。</span><span class="sxs-lookup"><span data-stu-id="7b88a-291">The computer must also have the Module Discovery WMI provider or an alternate WMI provider that has the same basic features.</span></span>

  <span data-ttu-id="7b88a-292">CIM セッション機能は、Windows オペレーティングシステムを実行していないコンピューターと PowerShell を搭載している Windows コンピューターで使用できますが、PowerShell リモート処理は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="7b88a-292">You can use the CIM session feature on computers that are not running the Windows operating system and on Windows computers that have PowerShell, but do not have PowerShell remoting enabled.</span></span>

  <span data-ttu-id="7b88a-293">また、CIM パラメーターを使用して、PowerShell リモート処理が有効になっているコンピューターから CIM モジュールを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-293">You can also use the CIM parameters to get CIM modules from computers that have PowerShell remoting enabled.</span></span> <span data-ttu-id="7b88a-294">これには、ローカルコンピューターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7b88a-294">This includes the local computer.</span></span> <span data-ttu-id="7b88a-295">ローカルコンピューターに CIM セッションを作成すると、PowerShell は WMI ではなく DCOM を使用してセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7b88a-295">When you create a CIM session on the local computer, PowerShell uses DCOM, instead of WMI, to create the session.</span></span>

## <span data-ttu-id="7b88a-296">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7b88a-296">RELATED LINKS</span></span>

[<span data-ttu-id="7b88a-297">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="7b88a-297">Get-CimSession</span></span>](../CimCmdlets/Get-CimSession.md)

[<span data-ttu-id="7b88a-298">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="7b88a-298">New-CimSession</span></span>](../CimCmdlets/New-CimSession.md)

[<span data-ttu-id="7b88a-299">about_Modules</span><span class="sxs-lookup"><span data-stu-id="7b88a-299">about_Modules</span></span>](About/about_Modules.md)

[<span data-ttu-id="7b88a-300">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="7b88a-300">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="7b88a-301">Import-Module</span><span class="sxs-lookup"><span data-stu-id="7b88a-301">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="7b88a-302">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="7b88a-302">Import-PSSession</span></span>](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[<span data-ttu-id="7b88a-303">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="7b88a-303">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="7b88a-304">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="7b88a-304">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="7b88a-305">about_PowerShell_Editions</span><span class="sxs-lookup"><span data-stu-id="7b88a-305">about_PowerShell_Editions</span></span>](About/about_PowerShell_Editions.md)
