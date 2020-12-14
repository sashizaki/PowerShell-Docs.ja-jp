---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/import-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Module
ms.openlocfilehash: 6b87074f6053189b20b5cc0983f978324420c99b
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564392"
---
# <span data-ttu-id="ae367-102">Import-Module</span><span class="sxs-lookup"><span data-stu-id="ae367-102">Import-Module</span></span>

## <span data-ttu-id="ae367-103">概要</span><span class="sxs-lookup"><span data-stu-id="ae367-103">SYNOPSIS</span></span>
<span data-ttu-id="ae367-104">現在のセッションにモジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae367-104">Adds modules to the current session.</span></span>

## <span data-ttu-id="ae367-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ae367-105">SYNTAX</span></span>

### <span data-ttu-id="ae367-106">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="ae367-106">Name (Default)</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] [<CommonParameters>]
```

### <span data-ttu-id="ae367-107">PSSession</span><span class="sxs-lookup"><span data-stu-id="ae367-107">PSSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -PSSession <PSSession> [<CommonParameters>]
```

### <span data-ttu-id="ae367-108">CimSession</span><span class="sxs-lookup"><span data-stu-id="ae367-108">CimSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="ae367-109">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="ae367-109">FullyQualifiedName</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] [<CommonParameters>]
```

### <span data-ttu-id="ae367-110">FullyQualifiedNameAndPSSession</span><span class="sxs-lookup"><span data-stu-id="ae367-110">FullyQualifiedNameAndPSSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -PSSession <PSSession> [<CommonParameters>]
```

### <span data-ttu-id="ae367-111">アセンブリ</span><span class="sxs-lookup"><span data-stu-id="ae367-111">Assembly</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Assembly] <Assembly[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber] [-Scope <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="ae367-112">ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="ae367-112">ModuleInfo</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Function <String[]>] [-Cmdlet <String[]>]
 [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru] [-AsCustomObject]
 [-ModuleInfo] <PSModuleInfo[]> [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] [<CommonParameters>]
```

## <span data-ttu-id="ae367-113">Description</span><span class="sxs-lookup"><span data-stu-id="ae367-113">DESCRIPTION</span></span>

<span data-ttu-id="ae367-114">`Import-Module`コマンドレットでは、現在のセッションに1つ以上のモジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae367-114">The `Import-Module` cmdlet adds one or more modules to the current session.</span></span> <span data-ttu-id="ae367-115">PowerShell 3.0 以降では、モジュール内のコマンドまたはプロバイダーを使用すると、インストールされているモジュールが自動的にセッションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ae367-115">Starting in PowerShell 3.0, installed modules are automatically imported to the session when you use any commands or providers in the module.</span></span> <span data-ttu-id="ae367-116">ただし、このコマンドを使用してモジュールをインポートすることもでき `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-116">However, you can still use the `Import-Module` command to import a module.</span></span>
<span data-ttu-id="ae367-117">自動モジュールインポートは、ユーザー設定変数を使用して無効にすることができ `$PSModuleAutoloadingPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-117">You can disable automatic module importing using the `$PSModuleAutoloadingPreference` preference variable.</span></span> <span data-ttu-id="ae367-118">変数の詳細については `$PSModuleAutoloadingPreference` 、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae367-118">For more information about the `$PSModuleAutoloadingPreference` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="ae367-119">モジュールは、PowerShell で使用できるメンバーを含むパッケージです。</span><span class="sxs-lookup"><span data-stu-id="ae367-119">A module is a package that contains members that can be used in PowerShell.</span></span> <span data-ttu-id="ae367-120">メンバーには、コマンドレット、プロバイダー、スクリプト、関数、変数、およびその他のツールとファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae367-120">Members include cmdlets, providers, scripts, functions, variables, and other tools and files.</span></span> <span data-ttu-id="ae367-121">モジュールをインポートすると、モジュールのメンバーをセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-121">After a module is imported, you can use the module members in your session.</span></span> <span data-ttu-id="ae367-122">モジュールの詳細については、「 [about_Modules](About/about_Modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae367-122">For more information about modules, see [about_Modules](About/about_Modules.md).</span></span>

<span data-ttu-id="ae367-123">既定では、は、モジュールによっ `Import-Module` てエクスポートされるすべてのメンバーをインポートしますが、 **エイリアス**、 **関数**、 **コマンドレット**、および **変数** パラメーターを使用して、インポートするメンバーを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="ae367-123">By default, `Import-Module` imports all members that the module exports, but you can use the **Alias**, **Function**, **Cmdlet**, and **Variable** parameters to restrict which members are imported.</span></span> <span data-ttu-id="ae367-124">**NoClobber** パラメーターは、 `Import-Module` 現在のセッションのメンバーと同じ名前を持つメンバーをでインポートできないようにします。</span><span class="sxs-lookup"><span data-stu-id="ae367-124">The **NoClobber** parameter prevents `Import-Module` from importing members that have the same names as members in the current session.</span></span>

<span data-ttu-id="ae367-125">`Import-Module` 現在のセッションにのみモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-125">`Import-Module` imports a module only into the current session.</span></span> <span data-ttu-id="ae367-126">すべての新しいセッションにモジュールをインポートするには、 `Import-Module` PowerShell プロファイルにコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae367-126">To import the module into every new session, add an `Import-Module` command to your PowerShell profile.</span></span> <span data-ttu-id="ae367-127">プロファイルの詳細については、「[about_Profiles](About/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae367-127">For more information about profiles, see [about_Profiles](About/about_Profiles.md).</span></span>

<span data-ttu-id="ae367-128">リモートコンピューター上に **PSSession** を作成することによって、PowerShell リモート処理が有効になっているリモート Windows コンピューターを管理できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-128">You can manage remote Windows computers that have PowerShell remoting enabled by creating a **PSSession** on the remote computer.</span></span> <span data-ttu-id="ae367-129">次に、の **PSSession** パラメーター `Import-Module` を使用して、リモートコンピューターにインストールされているモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-129">Then use the **PSSession** parameter of `Import-Module` to import the modules that are installed on the remote computer.</span></span> <span data-ttu-id="ae367-130">現在のセッションでインポートされたコマンドを使用すると、コマンドはリモートコンピューター上で暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-130">When you use the imported commands in the current session the commands implicitly run on the remote computer.</span></span>

<span data-ttu-id="ae367-131">Windows PowerShell 3.0 以降では、を使用して `Import-Module` Common Information Model (CIM) モジュールをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="ae367-131">Starting in Windows PowerShell 3.0, you can use `Import-Module` to import Common Information Model (CIM) modules.</span></span> <span data-ttu-id="ae367-132">CIM モジュールは、コマンドレット定義 XML (CDXML) ファイルのコマンドレットを定義します。</span><span class="sxs-lookup"><span data-stu-id="ae367-132">CIM modules define cmdlets in Cmdlet Definition XML (CDXML) files.</span></span> <span data-ttu-id="ae367-133">この機能を使用すると、C++ で記述されたものなど、マネージコード以外のアセンブリに実装されているコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-133">This feature lets you use cmdlets that are implemented in non-managed code assemblies, such as those written in C++.</span></span>

<span data-ttu-id="ae367-134">Windows オペレーティングシステムを実行していないコンピューターを含め、PowerShell リモート処理が有効になっていないリモートコンピューターの場合は、の **CIMSession** パラメーターを使用して、 `Import-Module` リモートコンピューターから CIM モジュールをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="ae367-134">For remote computers that don't have PowerShell remoting enabled, including computers that aren't running the Windows operating system, you can use the **CIMSession** parameter of `Import-Module` to import CIM modules from the remote computer.</span></span> <span data-ttu-id="ae367-135">インポートされたコマンドは、リモートコンピューター上で暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-135">The imported commands run implicitly on the remote computer.</span></span> <span data-ttu-id="ae367-136">**CIMSession** は、リモートコンピューター上の WINDOWS MANAGEMENT INSTRUMENTATION (WMI) に接続します。</span><span class="sxs-lookup"><span data-stu-id="ae367-136">A **CIMSession** is a connection to Windows Management Instrumentation (WMI) on the remote computer.</span></span>

## <span data-ttu-id="ae367-137">例</span><span class="sxs-lookup"><span data-stu-id="ae367-137">EXAMPLES</span></span>

### <span data-ttu-id="ae367-138">例 1: モジュールのメンバーを現在のセッションにインポートする</span><span class="sxs-lookup"><span data-stu-id="ae367-138">Example 1: Import the members of a module into the current session</span></span>

<span data-ttu-id="ae367-139">この例では、 **Psdiagnostics** モジュールのメンバーを現在のセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-139">This example imports the members of the **PSDiagnostics** module into the current session.</span></span>

```powershell
Import-Module -Name PSDiagnostics
```

### <span data-ttu-id="ae367-140">例 2: モジュールパスで指定されたすべてのモジュールをインポートする</span><span class="sxs-lookup"><span data-stu-id="ae367-140">Example 2: Import all modules specified by the module path</span></span>

<span data-ttu-id="ae367-141">この例では、環境変数によって指定されたパスにある使用可能なすべてのモジュール `$env:PSModulePath` を現在のセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-141">This example imports all available modules in the path specified by the `$env:PSModulePath` environment variable into the current session.</span></span>

```powershell
Get-Module -ListAvailable | Import-Module
```

### <span data-ttu-id="ae367-142">例 3: 現在のセッションに複数のモジュールのメンバーをインポートする</span><span class="sxs-lookup"><span data-stu-id="ae367-142">Example 3: Import the members of several modules into the current session</span></span>

<span data-ttu-id="ae367-143">この例では、 **Psdiagnostics** および **Dism** モジュールのメンバーを現在のセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-143">This example imports the members of the **PSDiagnostics** and **Dism** modules into the current session.</span></span>

```powershell
$m = Get-Module -ListAvailable PSDiagnostics, Dism
Import-Module -ModuleInfo $m
```

<span data-ttu-id="ae367-144">`Get-Module`コマンドレットは、 **Psdiagnostics** および **Dism** モジュールを取得し、変数にオブジェクトを保存し `$m` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-144">The `Get-Module` cmdlet gets the **PSDiagnostics** and **Dism** modules and saves the objects in the `$m` variable.</span></span> <span data-ttu-id="ae367-145">セッションにまだインポートされていないモジュールを取得する場合は、 **ListAvailable** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="ae367-145">The **ListAvailable** parameter is required when you're getting modules that aren't yet imported into the session.</span></span>

<span data-ttu-id="ae367-146">の **Moduleinfo** パラメーター `Import-Module` は、モジュールを現在のセッションにインポートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-146">The **ModuleInfo** parameter of `Import-Module` is used to import the modules into the current session.</span></span>

### <span data-ttu-id="ae367-147">例 4: パスによって指定されたすべてのモジュールをインポートする</span><span class="sxs-lookup"><span data-stu-id="ae367-147">Example 4: Import all modules specified by a path</span></span>

<span data-ttu-id="ae367-148">この例では、明示的なパスを使用して、インポートするモジュールを識別します。</span><span class="sxs-lookup"><span data-stu-id="ae367-148">This example uses an explicit path to identify the module to import.</span></span>

```powershell
Import-Module -Name c:\ps-test\modules\test -Verbose
```

```Output
VERBOSE: Loading module from path 'C:\ps-test\modules\Test\Test.psm1'.
VERBOSE: Exporting function 'my-parm'.
VERBOSE: Exporting function 'Get-Parameter'.
VERBOSE: Exporting function 'Get-Specification'.
VERBOSE: Exporting function 'Get-SpecDetails'.
```

<span data-ttu-id="ae367-149">**Verbose** パラメーターを使用すると、は、 `Import-Module` モジュールを読み込むときに進行状況を報告します。</span><span class="sxs-lookup"><span data-stu-id="ae367-149">Using the **Verbose** parameter causes `Import-Module` to report progress as it loads the module.</span></span>
<span data-ttu-id="ae367-150">**Verbose**、 **PassThru**、または **ascustomobject** 各パラメーターを指定しない `Import-Module` と、モジュールをインポートしても出力は生成されません。</span><span class="sxs-lookup"><span data-stu-id="ae367-150">Without the **Verbose**, **PassThru**, or **AsCustomObject** parameter, `Import-Module` does not generate any output when it imports a module.</span></span>

### <span data-ttu-id="ae367-151">例 5: セッションにインポートされたモジュールメンバーを制限する</span><span class="sxs-lookup"><span data-stu-id="ae367-151">Example 5: Restrict module members imported into a session</span></span>

<span data-ttu-id="ae367-152">この例では、セッションにインポートされるモジュールメンバーと、セッションに対するこのコマンドの影響を制限する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ae367-152">This example shows how to restrict which module members are imported into the session and the effect of this command on the session.</span></span> <span data-ttu-id="ae367-153">**関数** パラメーターは、モジュールからインポートされるメンバーを制限します。</span><span class="sxs-lookup"><span data-stu-id="ae367-153">The **Function** parameter limits the members that are imported from the module.</span></span> <span data-ttu-id="ae367-154">**エイリアス**、**変数**、および **コマンドレット** パラメーターを使用して、モジュールがインポートする他のメンバーを制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="ae367-154">You can also use the **Alias**, **Variable**, and **Cmdlet** parameters to restrict other members that a module imports.</span></span>

<span data-ttu-id="ae367-155">`Get-Module`コマンドレットは、 **psdiagnostics** モジュールを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="ae367-155">The `Get-Module` cmdlet gets the object that represents the **PSDiagnostics** module.</span></span> <span data-ttu-id="ae367-156">**ExportedCmdlets** プロパティは、すべてがインポートされていない場合でも、モジュールがエクスポートするすべてのコマンドレットを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ae367-156">The **ExportedCmdlets** property lists all the cmdlets that the module exports, even though they were not all imported.</span></span>

```powershell
Import-Module PSDiagnostics -Function Disable-PSTrace, Enable-PSTrace
(Get-Module PSDiagnostics).ExportedCommands
```

```Output
Key                          Value
---                          -----
Disable-PSTrace              Disable-PSTrace
Disable-PSWSManCombinedTrace Disable-PSWSManCombinedTrace
Disable-WSManTrace           Disable-WSManTrace
Enable-PSTrace               Enable-PSTrace
Enable-PSWSManCombinedTrace  Enable-PSWSManCombinedTrace
Enable-WSManTrace            Enable-WSManTrace
Get-LogProperties            Get-LogProperties
Set-LogProperties            Set-LogProperties
Start-Trace                  Start-Trace
Stop-Trace                   Stop-Trace
```

```powershell
Get-Command -Module PSDiagnostics
```

```Output
CommandType     Name                 Version    Source
-----------     ----                 -------    ------
Function        Disable-PSTrace      6.1.0.0    PSDiagnostics
Function        Enable-PSTrace       6.1.0.0    PSDiagnostics
```

<span data-ttu-id="ae367-157">コマンドレットの **module** パラメーターを使用すると、 `Get-Command` **psdiagnostics** モジュールからインポートされたコマンドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-157">Using the **Module** parameter of the `Get-Command` cmdlet shows the commands that were imported from the **PSDiagnostics** module.</span></span> <span data-ttu-id="ae367-158">結果によって、およびコマンドレットだけがインポートされたことが確認さ `Disable-PSTrace` `Enable-PSTrace` れます。</span><span class="sxs-lookup"><span data-stu-id="ae367-158">The results confirm that only the `Disable-PSTrace` and `Enable-PSTrace` cmdlets were imported.</span></span>

### <span data-ttu-id="ae367-159">例 6: モジュールのメンバーをインポートし、プレフィックスを追加する</span><span class="sxs-lookup"><span data-stu-id="ae367-159">Example 6: Import the members of a module and add a prefix</span></span>

<span data-ttu-id="ae367-160">この例では、 **Psdiagnostics** モジュールを現在のセッションにインポートし、メンバー名にプレフィックスを追加して、プレフィックスの付いたメンバー名を表示します。</span><span class="sxs-lookup"><span data-stu-id="ae367-160">This example imports the **PSDiagnostics** module into the current session, adds a prefix to the member names, and then displays the prefixed member names.</span></span> <span data-ttu-id="ae367-161">の **prefix** パラメーターは、 `Import-Module` モジュールからインポートされるすべてのメンバーに **x** プレフィックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae367-161">The **Prefix** parameter of `Import-Module` adds the **x** prefix to all members that are imported from the module.</span></span> <span data-ttu-id="ae367-162">プレフィックスは、現在のセッションのメンバーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-162">The prefix applies only to the members in the current session.</span></span> <span data-ttu-id="ae367-163">モジュールは変更されません。</span><span class="sxs-lookup"><span data-stu-id="ae367-163">It does not change the module.</span></span> <span data-ttu-id="ae367-164">**PassThru** パラメーターは、インポートされたモジュールを表すモジュールオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="ae367-164">The **PassThru** parameter returns a module object that represents the imported module.</span></span>

```powershell
Import-Module PSDiagnostics -Prefix x -PassThru
```

```Output
ModuleType Version    Name               ExportedCommands
---------- -------    ----               ----------------
Script     6.1.0.0    PSDiagnostics      {Disable-xPSTrace, Disable-xPSWSManCombinedTrace, Disable-xW...
```

```powershell
Get-Command -Module PSDiagnostics
```

```Output
CommandType     Name                                   Version    Source
-----------     ----                                   -------    ------
Function        Disable-xPSTrace                       6.1.0.0    PSDiagnostics
Function        Disable-xPSWSManCombinedTrace          6.1.0.0    PSDiagnostics
Function        Disable-xWSManTrace                    6.1.0.0    PSDiagnostics
Function        Enable-xPSTrace                        6.1.0.0    PSDiagnostics
Function        Enable-xPSWSManCombinedTrace           6.1.0.0    PSDiagnostics
Function        Enable-xWSManTrace                     6.1.0.0    PSDiagnostics
Function        Get-xLogProperties                     6.1.0.0    PSDiagnostics
Function        Set-xLogProperties                     6.1.0.0    PSDiagnostics
Function        Start-xTrace                           6.1.0.0    PSDiagnostics
Function        Stop-xTrace                            6.1.0.0    PSDiagnostics
```

<span data-ttu-id="ae367-165">`Get-Command` モジュールからインポートされたメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="ae367-165">`Get-Command` gets the members that have been imported from the module.</span></span> <span data-ttu-id="ae367-166">出力から、モジュール メンバーにプレフィックスが正しく追加されたことがわかります。</span><span class="sxs-lookup"><span data-stu-id="ae367-166">The output shows that the module members were correctly prefixed.</span></span>

### <span data-ttu-id="ae367-167">例 7: カスタムオブジェクトを取得して使用する</span><span class="sxs-lookup"><span data-stu-id="ae367-167">Example 7: Get and use a custom object</span></span>

<span data-ttu-id="ae367-168">この例では、によって返されるカスタムオブジェクトを取得して使用する方法を示し `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-168">This example demonstrates how to get and use the custom object returned by `Import-Module`.</span></span>

<span data-ttu-id="ae367-169">カスタム オブジェクトには、インポートされた各モジュール メンバーを表す合成メンバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae367-169">Custom objects include synthetic members that represent each of the imported module members.</span></span> <span data-ttu-id="ae367-170">たとえば、モジュールのコマンドレットと関数は、カスタム オブジェクトのスクリプト メソッドに変換されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-170">For example, the cmdlets and functions in a module are converted to script methods of the custom object.</span></span>

<span data-ttu-id="ae367-171">カスタムオブジェクトは、スクリプト作成に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ae367-171">Custom objects are useful in scripting.</span></span> <span data-ttu-id="ae367-172">また、インポートされた複数のオブジェクトが同じ名前を持つ場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ae367-172">They are also useful when several imported objects have the same names.</span></span> <span data-ttu-id="ae367-173">オブジェクトのスクリプト メソッドを使用すると、モジュール名を含め、インポートされたメンバーの完全修飾名を指定した場合と同じ効果が得られます。</span><span class="sxs-lookup"><span data-stu-id="ae367-173">Using the script method of an object is equivalent to specifying the fully qualified name of an imported member, including its module name.</span></span>

<span data-ttu-id="ae367-174">**Ascustomobject** "パラメーター" は、スクリプトモジュールをインポートするときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-174">The **AsCustomObject** parameter can be used only when importing a script module.</span></span> <span data-ttu-id="ae367-175">使用 `Get-Module` できるモジュールがスクリプトモジュールであるかどうかを判断するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="ae367-175">Use `Get-Module` to determine which of the available modules is a script module.</span></span>

```powershell
Get-Module -List | Format-Table -Property Name, ModuleType -AutoSize
```

```Output
Name          ModuleType
----          ----------
Show-Calendar     Script
BitsTransfer    Manifest
PSDiagnostics   Manifest
TestCmdlets       Script
...
```

```powershell
$a = Import-Module -Name Show-Calendar -AsCustomObject -Passthru
$a | Get-Member
```

```Output
    TypeName: System.Management.Automation.PSCustomObject
Name          MemberType   Definition
----          ----------   ----------
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
ToString      Method       string ToString()
Show-Calendar ScriptMethod System.Object Show-Calendar();
```

```powershell
$a."Show-Calendar"()
```

<span data-ttu-id="ae367-176">`Show-Calendar`スクリプトモジュールは、 **Ascustomobject** ユーザーパラメーターを使用してインポートされ、カスタムオブジェクトを要求し、 **PassThru** パラメーターを使用してオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="ae367-176">The `Show-Calendar` script module is imported using the **AsCustomObject** parameter to request a custom object and the **PassThru** parameter to return the object.</span></span> <span data-ttu-id="ae367-177">生成されたカスタムオブジェクトは変数に保存され `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-177">The resulting custom object is saved in the `$a` variable.</span></span>

<span data-ttu-id="ae367-178">`$a`変数をコマンドレットにパイプ処理して、保存された `Get-Member` オブジェクトのプロパティとメソッドを表示します。</span><span class="sxs-lookup"><span data-stu-id="ae367-178">The `$a` variable is piped to the `Get-Member` cmdlet to show the properties and methods of the saved object.</span></span> <span data-ttu-id="ae367-179">出力には、 `Show-Calendar` スクリプトメソッドが示されています。</span><span class="sxs-lookup"><span data-stu-id="ae367-179">The output shows a `Show-Calendar` script method.</span></span>

<span data-ttu-id="ae367-180">スクリプトメソッドを呼び出すには、 `Show-Calendar` 名前にハイフンが含まれているため、メソッド名を引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae367-180">To call the `Show-Calendar` script method, the method name must be enclosed in quotation marks because the name includes a hyphen.</span></span>

### <span data-ttu-id="ae367-181">例 8: 同じセッションにモジュールを再インポートする</span><span class="sxs-lookup"><span data-stu-id="ae367-181">Example 8: Reimport a module into the same session</span></span>

<span data-ttu-id="ae367-182">この例では、  `Import-Module` モジュールを同じセッションに再インポートときにの Force パラメーターを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ae367-182">This example shows how to use the **Force** parameter of `Import-Module` when you're reimporting a module into the same session.</span></span> <span data-ttu-id="ae367-183">**Force** パラメーターは、読み込まれたモジュールを削除し、再度インポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-183">The **Force** parameter removes the loaded module and then imports it again.</span></span>

```powershell
Import-Module PSDiagnostics
Import-Module PSDiagnostics -Force -Prefix PS
```

<span data-ttu-id="ae367-184">最初のコマンドは、 **Psdiagnostics** モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-184">The first command imports the **PSDiagnostics** module.</span></span> <span data-ttu-id="ae367-185">2 番目のコマンドは、このモジュールを今度は **Prefix** パラメーターを使用してインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-185">The second command imports the module again, this time using the **Prefix** parameter.</span></span>

<span data-ttu-id="ae367-186">**Force** パラメーターを指定しない場合、セッションには各 **psdiagnostics** コマンドレットの2つのコピーが含まれます。1つは標準名、もう1つはプレフィックス付きの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="ae367-186">Without the **Force** parameter, the session would include two copies of each **PSDiagnostics** cmdlet, one with the standard name and one with the prefixed name.</span></span>

### <span data-ttu-id="ae367-187">例 9: インポートされたコマンドによって非表示になっているコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="ae367-187">Example 9: Run commands that have been hidden by imported commands</span></span>

<span data-ttu-id="ae367-188">この例は、インポートされたコマンドで非表示になったコマンドを実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ae367-188">This example shows how to run commands that have been hidden by imported commands.</span></span> <span data-ttu-id="ae367-189">**Testmodule** モジュールには、年と日を返すという名前の関数が含まれてい `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-189">The **TestModule** module includes a function named `Get-Date` that returns the year and day of the year.</span></span>

```powershell
Get-Date
```

```Output
Thursday, August 15, 2019 2:26:12 PM
```

```powershell
Import-Module TestModule
Get-Date
```

```Output
19227
```

```powershell
Get-Command Get-Date -All | Format-Table -Property CommandType, Name, ModuleName -AutoSize
```

```Output
CommandType     Name         ModuleName
-----------     ----         ----------
Function        Get-Date     TestModule
Cmdlet          Get-Date     Microsoft.PowerShell.Utility
```

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

```Output
Thursday, August 15, 2019 2:28:31 PM
```

<span data-ttu-id="ae367-190">最初の `Get-Date` コマンドレットは、現在の日付の **DateTime** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="ae367-190">The first `Get-Date` cmdlet returns a **DateTime** object with the current date.</span></span> <span data-ttu-id="ae367-191">**Testmodule** モジュールをインポートすると、は年 `Get-Date` と日を返します。</span><span class="sxs-lookup"><span data-stu-id="ae367-191">After importing the **TestModule** module, `Get-Date` returns the year and day of the year.</span></span>

<span data-ttu-id="ae367-192">の **all** パラメーターを使用すると、 `Get-Command` セッション内のすべてのコマンドが表示され `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-192">Using the **All** parameter of `Get-Command` show all the `Get-Date` commands in the session.</span></span> <span data-ttu-id="ae367-193">結果には、セッションに2つの `Get-Date` コマンド ( **testmodule** モジュールの関数と、 **Microsoft. PowerShell. ユーティリティ** モジュールのコマンドレット) があることが示されています。</span><span class="sxs-lookup"><span data-stu-id="ae367-193">The results show that there are two `Get-Date` commands in the session, a function from the **TestModule** module and a cmdlet from the **Microsoft.PowerShell.Utility** module.</span></span>

<span data-ttu-id="ae367-194">関数はコマンドレットよりも優先されるため、 `Get-Date` **testmodule** モジュールの関数はコマンドレットではなく、を実行し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-194">Because functions take precedence over cmdlets, the `Get-Date` function from the **TestModule** module runs, instead of the `Get-Date` cmdlet.</span></span> <span data-ttu-id="ae367-195">の元のバージョンを実行するには、 `Get-Date` コマンド名をモジュール名で修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae367-195">To run the original version of `Get-Date`, you must qualify the command name with the module name.</span></span>

<span data-ttu-id="ae367-196">PowerShell でのコマンドの優先順位の詳細については、「 [about_Command_Precedence](about/about_Command_Precedence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae367-196">For more information about command precedence in PowerShell, see [about_Command_Precedence](about/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="ae367-197">例 10: モジュールの最小バージョンをインポートする</span><span class="sxs-lookup"><span data-stu-id="ae367-197">Example 10: Import a minimum version of a module</span></span>

<span data-ttu-id="ae367-198">この例では、 **PowerShellGet** モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-198">This example imports the **PowerShellGet** module.</span></span> <span data-ttu-id="ae367-199">の **MinimumVersion** パラメーターを使用して `Import-Module` 、バージョン2.0.0 以上のモジュールのみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-199">It uses the **MinimumVersion** parameter of `Import-Module` to import only version 2.0.0 or greater of the module.</span></span>

```powershell
Import-Module -Name PowerShellGet -MinimumVersion 2.0.0
```

<span data-ttu-id="ae367-200">また、 **RequiredVersion** パラメーターを使用して、モジュールの特定のバージョンをインポートしたり、キーワードの **Module** パラメーターと **version** パラメーターを使用して、 `#Requires` スクリプト内でモジュールの特定のバージョンを要求したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ae367-200">You can also use the **RequiredVersion** parameter to import a particular version of a module, or use the **Module** and **Version** parameters of the `#Requires` keyword to require a particular version of a module in a script.</span></span>

### <span data-ttu-id="ae367-201">例 11: 完全修飾名を使用してインポートする</span><span class="sxs-lookup"><span data-stu-id="ae367-201">Example 11: Import using a fully qualified name</span></span>

<span data-ttu-id="ae367-202">この例では、FullyQualifiedName を使用して、モジュールの特定のバージョンをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-202">This example imports a specific version of a module using the FullyQualifiedName.</span></span>

```powershell
PS> Get-Module -ListAvailable PowerShellGet | Select-Object Name, Version

Name          Version
----          -------
PowerShellGet 2.2.1
PowerShellGet 2.1.3
PowerShellGet 2.1.2
PowerShellGet 1.0.0.1

PS> Import-Module -FullyQualifiedName @{ModuleName = 'PowerShellGet'; ModuleVersion = '2.1.3' }
```

### <span data-ttu-id="ae367-203">例 12: 完全修飾パスを使用してインポートする</span><span class="sxs-lookup"><span data-stu-id="ae367-203">Example 12: Import using a fully qualified path</span></span>

<span data-ttu-id="ae367-204">この例では、完全修飾パスを使用して、モジュールの特定のバージョンをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-204">This example imports a specific version of a module using the fully qualified path.</span></span>

```powershell
PS> Get-Module -ListAvailable PowerShellGet | Select-Object Path

Path
----
C:\Program Files\PowerShell\Modules\PowerShellGet\2.2.1\PowerShellGet.psd1
C:\program files\powershell\6\Modules\PowerShellGet\PowerShellGet.psd1
C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\2.1.2\PowerShellGet.psd1
C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1

PS> Import-Module -Name 'C:\Program Files\PowerShell\Modules\PowerShellGet\2.2.1\PowerShellGet.psd1'
```

### <span data-ttu-id="ae367-205">例 13: リモートコンピューターからモジュールをインポートする</span><span class="sxs-lookup"><span data-stu-id="ae367-205">Example 13: Import a module from a remote computer</span></span>

<span data-ttu-id="ae367-206">この例では、コマンドレットを使用して、 `Import-Module` リモートコンピューターからモジュールをインポートする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ae367-206">This example shows how to use the `Import-Module` cmdlet to import a module from a remote computer.</span></span>
<span data-ttu-id="ae367-207">このコマンドは、PowerShell の暗黙的なリモート処理機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="ae367-207">This command uses the Implicit Remoting feature of PowerShell.</span></span>

<span data-ttu-id="ae367-208">別のセッションからモジュールをインポートすると、現在のセッションでコマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ae367-208">When you import modules from another session, you can use the cmdlets in the current session.</span></span>
<span data-ttu-id="ae367-209">ただし、コマンドレットを使用するコマンドは、リモートセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-209">However, commands that use the cmdlets run in the remote session.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01
Get-Module -PSSession $s -ListAvailable -Name NetSecurity
```

```Output
ModuleType Name             ExportedCommands
---------- ----             ----------------
Manifest   NetSecurity      {New-NetIPsecAuthProposal, New-NetIPsecMainModeCryptoProposal, New-Ne...
```

```powershell
Import-Module -PSSession $s -Name NetSecurity
Get-Command -Module NetSecurity -Name Get-*Firewall*
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Function        Get-NetFirewallAddressFilter                       NetSecurity
Function        Get-NetFirewallApplicationFilter                   NetSecurity
Function        Get-NetFirewallInterfaceFilter                     NetSecurity
Function        Get-NetFirewallInterfaceTypeFilter                 NetSecurity
Function        Get-NetFirewallPortFilter                          NetSecurity
Function        Get-NetFirewallProfile                             NetSecurity
Function        Get-NetFirewallRule                                NetSecurity
Function        Get-NetFirewallSecurityFilter                      NetSecurity
Function        Get-NetFirewallServiceFilter                       NetSecurity
Function        Get-NetFirewallSetting                             NetSecurity
```

```powershell
Get-NetFirewallRule -DisplayName "Windows Remote Management*" |
  Format-Table -Property DisplayName, Name -AutoSize
```

```Output
DisplayName                                              Name
-----------                                              ----
Windows Remote Management (HTTP-In)                      WINRM-HTTP-In-TCP
Windows Remote Management (HTTP-In)                      WINRM-HTTP-In-TCP-PUBLIC
Windows Remote Management - Compatibility Mode (HTTP-In) WINRM-HTTP-Compat-In-TCP
```

<span data-ttu-id="ae367-210">`New-PSSession` Server01 コンピューターへのリモートセッション (**PSSession**) を作成します。</span><span class="sxs-lookup"><span data-stu-id="ae367-210">`New-PSSession` creates a remote session (**PSSession**) to the Server01 computer.</span></span> <span data-ttu-id="ae367-211">**PSSession** は変数に保存され `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-211">The **PSSession** is saved in the `$s` variable.</span></span>

<span data-ttu-id="ae367-212">PSSession パラメーターを指定してを実行 `Get-Module` すると、 **netsecurity** モジュールがリモートコンピューターにインストールされ、使用可能であることが示されます。 </span><span class="sxs-lookup"><span data-stu-id="ae367-212">Running `Get-Module` with the **PSSession** parameter shows that the **NetSecurity** module is installed and available on the remote computer.</span></span> <span data-ttu-id="ae367-213">このコマンドは、コマンドレットを使用して `Invoke-Command` `Get-Module` リモートセッションでコマンドを実行することと同じです。</span><span class="sxs-lookup"><span data-stu-id="ae367-213">This command is equivalent to using the `Invoke-Command` cmdlet to run `Get-Module` command in the remote session.</span></span> <span data-ttu-id="ae367-214">例: (`Invoke-Command $s {Get-Module -ListAvailable -Name NetSecurity`</span><span class="sxs-lookup"><span data-stu-id="ae367-214">For example: (`Invoke-Command $s {Get-Module -ListAvailable -Name NetSecurity`</span></span>

<span data-ttu-id="ae367-215">`Import-Module` **PSSession** パラメーターを指定してを実行すると、リモートコンピューターから **netsecurity** モジュールが現在のセッションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ae367-215">Running `Import-Module` with the **PSSession** parameter imports the **NetSecurity** module from the remote computer into the current session.</span></span> <span data-ttu-id="ae367-216">コマンド `Get-Command` レットを使用すると、 **netsecurity** モジュールから **get** および include **Firewall** で始まるコマンドを取得できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-216">The `Get-Command` cmdlet is used to get commands that begin with **Get** and include **Firewall** from the **NetSecurity** module.</span></span> <span data-ttu-id="ae367-217">出力によって、モジュールとそのコマンドレットが現在のセッションにインポートされたことが確認されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-217">The output confirms that the module and its cmdlets were imported into the current session.</span></span>

<span data-ttu-id="ae367-218">次に、 `Get-NetFirewallRule` コマンドレットは、Server01 コンピューター上のファイアウォール規則を取得 Windows リモート管理します。</span><span class="sxs-lookup"><span data-stu-id="ae367-218">Next, the `Get-NetFirewallRule` cmdlet gets Windows Remote Management firewall rules on the Server01 computer.</span></span> <span data-ttu-id="ae367-219">これは、コマンドレットを使用して `Invoke-Command` `Get-NetFirewallRule` リモートセッションで実行することと同じです。</span><span class="sxs-lookup"><span data-stu-id="ae367-219">This is equivalent to using the `Invoke-Command` cmdlet to run `Get-NetFirewallRule` on the remote session.</span></span>

### <span data-ttu-id="ae367-220">例 14: Windows オペレーティングシステムを使用せずにリモートコンピューター上の記憶域を管理する</span><span class="sxs-lookup"><span data-stu-id="ae367-220">Example 14: Manage storage on a remote computer without the Windows operating system</span></span>

<span data-ttu-id="ae367-221">この例では、コンピューターの管理者がモジュール検出 WMI プロバイダーをインストールしています。これにより、プロバイダー用に設計された CIM コマンドを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ae367-221">In this example, the administrator of the computer has installed the Module Discovery WMI provider, which allows you to use CIM commands that are designed for the provider.</span></span>

<span data-ttu-id="ae367-222">コマンドレットでは、 `New-CimSession` RSDGF03 という名前のリモートコンピューター上にセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ae367-222">The `New-CimSession` cmdlet creates a session on the remote computer named RSDGF03.</span></span> <span data-ttu-id="ae367-223">セッションは、リモートコンピューター上の WMI サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="ae367-223">The session connects to the WMI service on the remote computer.</span></span> <span data-ttu-id="ae367-224">CIM セッションは変数に保存され `$cs` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-224">The CIM session is saved in the `$cs` variable.</span></span>
<span data-ttu-id="ae367-225">`Import-Module` の **CimSession** を使用して、 `$cs` RSDGF03 コンピューターから **ストレージ** CIM モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-225">`Import-Module` uses the **CimSession** in `$cs` to import the **Storage** CIM module from the RSDGF03 computer.</span></span>

<span data-ttu-id="ae367-226">`Get-Command`コマンドレットは、 `Get-Disk` **ストレージ** モジュール内のコマンドを表示します。</span><span class="sxs-lookup"><span data-stu-id="ae367-226">The `Get-Command` cmdlet shows the `Get-Disk` command in the **Storage** module.</span></span> <span data-ttu-id="ae367-227">CIM モジュールをローカルセッションにインポートすると、PowerShell によって各コマンドの CDXML ファイルが PowerShell スクリプトに変換されます。 PowerShell スクリプトは、ローカルセッションの関数として表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-227">When you import a CIM module into the local session, PowerShell converts the CDXML files for each command into PowerShell scripts, which appear as functions in the local session.</span></span>

<span data-ttu-id="ae367-228">`Get-Disk`はローカルセッションで入力されますが、コマンドレットは、インポート元のリモートコンピューター上で暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-228">Although `Get-Disk` is typed in the local session, the cmdlet implicitly runs on the remote computer from which it was imported.</span></span> <span data-ttu-id="ae367-229">コマンドを実行すると、リモートコンピューターからローカルセッションにオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-229">The command returns objects from the remote computer to the local session.</span></span>

```powershell
$cs = New-CimSession -ComputerName RSDGF03
Import-Module -CimSession $cs -Name Storage
# Importing a CIM module, converts the CDXML files for each command into PowerShell scripts.
# These appear as functions in the local session.
Get-Command Get-Disk
```

```Output
CommandType     Name                  ModuleName
-----------     ----                  ----------
Function        Get-Disk              Storage
```

```powershell
# Use implicit remoting to query disks on the remote computer from which the module was imported.
Get-Disk
```

```Output
Number Friendly Name           OperationalStatus  Total Size Partition Style
------ -------------           -----------------  ---------- ---------------
0      Virtual HD ATA Device   Online                  40 GB MBR
```

## <span data-ttu-id="ae367-230">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ae367-230">PARAMETERS</span></span>

### <span data-ttu-id="ae367-231">-エイリアス</span><span class="sxs-lookup"><span data-stu-id="ae367-231">-Alias</span></span>

<span data-ttu-id="ae367-232">このコマンドレットがモジュールから現在のセッションにインポートするエイリアスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-232">Specifies the aliases that this cmdlet imports from the module into the current session.</span></span> <span data-ttu-id="ae367-233">エイリアスのコンマ区切りのリストを入力します。</span><span class="sxs-lookup"><span data-stu-id="ae367-233">Enter a comma-separated list of aliases.</span></span> <span data-ttu-id="ae367-234">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-234">Wildcard characters are permitted.</span></span>

<span data-ttu-id="ae367-235">一部のモジュールは、モジュールをインポートすると、選択されたエイリアスをセッションに自動的にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-235">Some modules automatically export selected aliases into your session when you import the module.</span></span>
<span data-ttu-id="ae367-236">このパラメーターを使用すると、エクスポートされたエイリアスの中から選択できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-236">This parameter lets you select from among the exported aliases.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ae367-237">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="ae367-237">-ArgumentList</span></span>

<span data-ttu-id="ae367-238">コマンドの実行中にスクリプトモジュールに渡される引数の配列、またはパラメーター値を指定し `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-238">Specifies an array of arguments, or parameter values, that are passed to a script module during the `Import-Module` command.</span></span> <span data-ttu-id="ae367-239">このパラメーターは、スクリプトモジュールをインポートする場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="ae367-239">This parameter is valid only when you're importing a script module.</span></span>

<span data-ttu-id="ae367-240">**ArgumentList** パラメーターは、別名 **args** を使用して参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="ae367-240">You can also refer to the **ArgumentList** parameter by its alias, **args**.</span></span> <span data-ttu-id="ae367-241">**ArgumentList** の動作の詳細については、「 [about_Splatting](about/about_Splatting.md#splatting-with-arrays)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae367-241">For more information about the behavior of **ArgumentList**, see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae367-242">-AsCustomObject 場合</span><span class="sxs-lookup"><span data-stu-id="ae367-242">-AsCustomObject</span></span>

<span data-ttu-id="ae367-243">このコマンドレットが、インポートされたモジュールメンバーを表すメンバーを持つカスタムオブジェクトを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="ae367-243">Indicates that this cmdlet returns a custom object with members that represent the imported module members.</span></span> <span data-ttu-id="ae367-244">このパラメーターは、スクリプト モジュールに対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="ae367-244">This parameter is valid only for script modules.</span></span>

<span data-ttu-id="ae367-245">**Ascustomobject** パラメーターを使用すると、 `Import-Module` モジュールメンバーがセッションにインポートされ、その後、 オブジェクトではなく **pscustomobject** オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-245">When you use the **AsCustomObject** parameter, `Import-Module` imports the module members into the session and then returns a **PSCustomObject** object instead of a **PSModuleInfo** object.</span></span> <span data-ttu-id="ae367-246">カスタム オブジェクトを変数に保存し、ドット表記を使用してメンバーを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="ae367-246">You can save the custom object in a variable and use dot notation to invoke the members.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae367-247">-Assembly</span><span class="sxs-lookup"><span data-stu-id="ae367-247">-Assembly</span></span>

<span data-ttu-id="ae367-248">アセンブリオブジェクトの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-248">Specifies an array of assembly objects.</span></span> <span data-ttu-id="ae367-249">このコマンドレットは、指定したアセンブリオブジェクトに実装されているコマンドレットとプロバイダーをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-249">This cmdlet imports the cmdlets and providers implemented in the specified assembly objects.</span></span> <span data-ttu-id="ae367-250">アセンブリ オブジェクトが保存されている変数か、アセンブリ オブジェクトを作成するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ae367-250">Enter a variable that contains assembly objects or a command that creates assembly objects.</span></span> <span data-ttu-id="ae367-251">パイプを使用してアセンブリオブジェクトをにパイプすることもでき `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-251">You can also pipe an assembly object to `Import-Module`.</span></span>

<span data-ttu-id="ae367-252">このパラメーターを使用すると、指定されたアセンブリによって実装されたコマンドレットとプロバイダーのみがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ae367-252">When you use this parameter, only the cmdlets and providers implemented by the specified assemblies are imported.</span></span> <span data-ttu-id="ae367-253">モジュールに他のファイルが含まれている場合は、インポートされないため、モジュールの重要なメンバーが不足している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ae367-253">If the module contains other files, they aren't imported, and you might be missing important members of the module.</span></span> <span data-ttu-id="ae367-254">モジュールのデバッグとテスト、またはモジュールの作成者によって使用するように指示された場合は、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae367-254">Use this parameter for debugging and testing the module, or when you're instructed to use it by the module author.</span></span>

```yaml
Type: System.Reflection.Assembly[]
Parameter Sets: Assembly
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ae367-255">-CimNamespace</span><span class="sxs-lookup"><span data-stu-id="ae367-255">-CimNamespace</span></span>

<span data-ttu-id="ae367-256">CIM モジュールを公開する代替 CIM プロバイダーの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-256">Specifies the namespace of an alternate CIM provider that exposes CIM modules.</span></span> <span data-ttu-id="ae367-257">既定値は、モジュール検出用の WMI プロバイダーの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="ae367-257">The default value is the namespace of the Module Discovery WMI provider.</span></span>

<span data-ttu-id="ae367-258">Windows オペレーティングシステムを実行していないコンピューターやデバイスから CIM モジュールをインポートするには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae367-258">Use this parameter to import CIM modules from computers and devices that aren't running a Windows operating system.</span></span>

<span data-ttu-id="ae367-259">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ae367-259">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ae367-260">-CimResourceUri</span><span class="sxs-lookup"><span data-stu-id="ae367-260">-CimResourceUri</span></span>

<span data-ttu-id="ae367-261">CIM モジュールの代替の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-261">Specifies an alternate location for CIM modules.</span></span> <span data-ttu-id="ae367-262">既定値は、リモートコンピューター上のモジュール検出 WMI プロバイダーのリソース URI です。</span><span class="sxs-lookup"><span data-stu-id="ae367-262">The default value is the resource URI of the Module Discovery WMI provider on the remote computer.</span></span>

<span data-ttu-id="ae367-263">Windows オペレーティングシステムを実行していないコンピューターやデバイスから CIM モジュールをインポートするには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae367-263">Use this parameter to import CIM modules from computers and devices that aren't running a Windows operating system.</span></span>

<span data-ttu-id="ae367-264">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ae367-264">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ae367-265">-CimSession</span><span class="sxs-lookup"><span data-stu-id="ae367-265">-CimSession</span></span>

<span data-ttu-id="ae367-266">リモート コンピューター上の CIM セッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-266">Specifies a CIM session on the remote computer.</span></span> <span data-ttu-id="ae367-267">CIM セッションを含む変数、または [CimSession](../CimCmdlets/Get-CimSession.md) コマンドなどの cim セッションを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ae367-267">Enter a variable that contains the CIM session or a command that gets the CIM session, such as a [Get-CimSession](../CimCmdlets/Get-CimSession.md) command.</span></span>

<span data-ttu-id="ae367-268">`Import-Module` CIM セッション接続を使用して、リモートコンピューターから現在のセッションにモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-268">`Import-Module` uses the CIM session connection to import modules from the remote computer into the current session.</span></span> <span data-ttu-id="ae367-269">現在のセッションでインポートされたモジュールのコマンドを使用すると、コマンドはリモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-269">When you use the commands from the imported module in the current session, the commands run on the remote computer.</span></span>

<span data-ttu-id="ae367-270">このパラメーターを使用して、Windows オペレーティングシステムを実行していないコンピューターやデバイス、PowerShell を搭載しているが PowerShell リモート処理が有効になっていない Windows コンピューターからモジュールをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="ae367-270">You can use this parameter to import modules from computers and devices that aren't running the Windows operating system, and Windows computers that have PowerShell, but don't have PowerShell remoting enabled.</span></span>

<span data-ttu-id="ae367-271">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ae367-271">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ae367-272">-コマンドレット</span><span class="sxs-lookup"><span data-stu-id="ae367-272">-Cmdlet</span></span>

<span data-ttu-id="ae367-273">このコマンドレットがモジュールから現在のセッションにインポートするコマンドレットの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-273">Specifies an array of cmdlets that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="ae367-274">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-274">Wildcard characters are permitted.</span></span>

<span data-ttu-id="ae367-275">一部のモジュールは、モジュールをインポートすると、選択されたコマンドレットをセッションに自動的にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-275">Some modules automatically export selected cmdlets into your session when you import the module.</span></span>
<span data-ttu-id="ae367-276">このパラメーターを使用すると、エクスポートされたコマンドレットの中から選択できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-276">This parameter lets you select from among the exported cmdlets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ae367-277">-DisableNameChecking</span><span class="sxs-lookup"><span data-stu-id="ae367-277">-DisableNameChecking</span></span>

<span data-ttu-id="ae367-278">このコマンドレットが、許可されていない動詞または禁止された文字を含んでいる名前を持つコマンドレットまたは関数をインポートしたときに警告するメッセージを抑制することを示します。</span><span class="sxs-lookup"><span data-stu-id="ae367-278">Indicates that this cmdlet suppresses the message that warns you when you import a cmdlet or function whose name includes an unapproved verb or a prohibited character.</span></span>

<span data-ttu-id="ae367-279">既定では、インポートしたモジュールによって、名前に許可されていない動詞を持つコマンドレットまたは関数がエクスポートされると、PowerShell によって次の警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-279">By default, when a module that you import exports cmdlets or functions that have unapproved verbs in their names, PowerShell displays the following warning message:</span></span>

> <span data-ttu-id="ae367-280">警告: インポートされたコマンド名には、検出できない可能性がある未承認の動詞が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ae367-280">WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="ae367-281">詳細については Verbose パラメーターを使用するか、「Get-Verb」と入力して承認されている動詞の一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae367-281">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs.</span></span>

<span data-ttu-id="ae367-282">このメッセージは、単なる警告です。</span><span class="sxs-lookup"><span data-stu-id="ae367-282">This message is only a warning.</span></span> <span data-ttu-id="ae367-283">実際には、非準拠のコマンドを含む、すべてのモジュールがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ae367-283">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="ae367-284">モジュール ユーザーにメッセージが表示されますが、名前付けの問題はモジュール作成者が解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae367-284">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae367-285">-Force</span><span class="sxs-lookup"><span data-stu-id="ae367-285">-Force</span></span>

<span data-ttu-id="ae367-286">このパラメーターを指定すると、現在のモジュールの上にモジュールが読み込まれるか、再度読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="ae367-286">This parameter causes a module to be loaded, or reloaded, over top of the current one.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae367-287">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="ae367-287">-FullyQualifiedName</span></span>

<span data-ttu-id="ae367-288">モジュールの完全修飾名をハッシュテーブルとして指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-288">Specifies the fully qualified name of the module as a hash table.</span></span> <span data-ttu-id="ae367-289">値には、文字列とハッシュテーブルの組み合わせを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-289">The value can be a combination of strings and hash tables.</span></span> <span data-ttu-id="ae367-290">ハッシュテーブルには、次のキーがあります。</span><span class="sxs-lookup"><span data-stu-id="ae367-290">The hash table has the following keys.</span></span>

- <span data-ttu-id="ae367-291">`ModuleName` - **必須** モジュール名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-291">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="ae367-292">`GUID` - **省略可能** モジュールの GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-292">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="ae367-293">以下の3つのキーのいずれかを指定する **必要** もあります。</span><span class="sxs-lookup"><span data-stu-id="ae367-293">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="ae367-294">これらのキーを一緒に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ae367-294">These keys can't be used together.</span></span>
  - <span data-ttu-id="ae367-295">`ModuleVersion` -モジュールの許容される最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-295">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="ae367-296">`RequiredVersion` -モジュールの正確な必須バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-296">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="ae367-297">`MaximumVersion` -モジュールの許容される最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-297">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedName, FullyQualifiedNameAndPSSession
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ae367-298">-関数</span><span class="sxs-lookup"><span data-stu-id="ae367-298">-Function</span></span>

<span data-ttu-id="ae367-299">このコマンドレットがモジュールから現在のセッションにインポートする関数の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-299">Specifies an array of functions that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="ae367-300">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-300">Wildcard characters are permitted.</span></span> <span data-ttu-id="ae367-301">一部のモジュールは、モジュールをインポートすると、選択された関数をセッションに自動的にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-301">Some modules automatically export selected functions into your session when you import the module.</span></span> <span data-ttu-id="ae367-302">このパラメーターを使用すると、エクスポートされた関数の中から選択できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-302">This parameter lets you select from among the exported functions.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ae367-303">-グローバル</span><span class="sxs-lookup"><span data-stu-id="ae367-303">-Global</span></span>

<span data-ttu-id="ae367-304">このコマンドレットがモジュールをグローバルセッション状態にインポートして、セッションのすべてのコマンドで使用できるようにすることを示します。</span><span class="sxs-lookup"><span data-stu-id="ae367-304">Indicates that this cmdlet imports modules into the global session state so they are available to all commands in the session.</span></span>

<span data-ttu-id="ae367-305">既定では、 `Import-Module` コマンドプロンプト、スクリプトファイル、または scriptblock からコマンドレットを呼び出すと、すべてのコマンドがグローバルセッション状態にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ae367-305">By default, when `Import-Module` cmdlet is called from the command prompt, script file, or scriptblock, all the commands are imported into the global session state.</span></span>

<span data-ttu-id="ae367-306">別のモジュールから呼び出されると、コマンドレットは、 `Import-Module` モジュール内のコマンド (入れ子になったモジュールのコマンドを含む) を呼び出し元のモジュールのセッション状態にインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-306">When invoked from another module, `Import-Module` cmdlet imports the commands in a module, including commands from nested modules, into the calling module's session state.</span></span>

> [!TIP]
> <span data-ttu-id="ae367-307">モジュール内からを呼び出すことは避けてください `Import-Module` 。</span><span class="sxs-lookup"><span data-stu-id="ae367-307">You should avoid calling `Import-Module` from within a module.</span></span> <span data-ttu-id="ae367-308">代わりに、親モジュールのマニフェストで入れ子になったモジュールとしてターゲットモジュールを宣言します。</span><span class="sxs-lookup"><span data-stu-id="ae367-308">Instead, declare the target module as a nested module in the parent module's manifest.</span></span> <span data-ttu-id="ae367-309">入れ子になったモジュールを宣言すると、依存関係の発見可能性が向上します。</span><span class="sxs-lookup"><span data-stu-id="ae367-309">Declaring nested modules improves the discoverability of dependencies.</span></span>

<span data-ttu-id="ae367-310">**Global** パラメーターは、値が **Global** である **Scope** パラメーターと同じ効果が得られます。</span><span class="sxs-lookup"><span data-stu-id="ae367-310">The **Global** parameter is equivalent to the **Scope** parameter with a value of **Global**.</span></span>

<span data-ttu-id="ae367-311">モジュールによってエクスポートされるコマンドを制限するには、 `Export-ModuleMember` スクリプトモジュールでコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae367-311">To restrict the commands that a module exports, use an `Export-ModuleMember` command in the script module.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae367-312">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="ae367-312">-MaximumVersion</span></span>

<span data-ttu-id="ae367-313">最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-313">Specifies a maximum version.</span></span> <span data-ttu-id="ae367-314">このコマンドレットは、指定した値以下のバージョンのモジュールのみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-314">This cmdlet imports only a version of the module that is less than or equal to the specified value.</span></span> <span data-ttu-id="ae367-315">バージョンが修飾していない場合は、 `Import-Module` エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="ae367-315">If no version qualifies, `Import-Module` returns an error.</span></span>

```yaml
Type: System.String
Parameter Sets: Name, PSSession, CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae367-316">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="ae367-316">-MinimumVersion</span></span>

<span data-ttu-id="ae367-317">最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-317">Specifies a minimum version.</span></span> <span data-ttu-id="ae367-318">このコマンドレットは、指定した値以上のバージョンのモジュールのみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-318">This cmdlet imports only a version of the module that is greater than or equal to the specified value.</span></span> <span data-ttu-id="ae367-319">**MinimumVersion** パラメーター名またはそのエイリアスである **Version** を使用します。</span><span class="sxs-lookup"><span data-stu-id="ae367-319">Use the **MinimumVersion** parameter name or its alias, **Version**.</span></span> <span data-ttu-id="ae367-320">バージョンが修飾されていない場合、は `Import-Module` エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="ae367-320">If no version qualifies, `Import-Module` generates an error.</span></span>

<span data-ttu-id="ae367-321">正確なバージョンを指定するには、**RequiredVersion** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae367-321">To specify an exact version, use the **RequiredVersion** parameter.</span></span> <span data-ttu-id="ae367-322">また、 **#Requires** キーワードの **Module** パラメーターと **Version** パラメーターを使用して、スクリプト内でモジュールの特定のバージョンを要求することもできます。</span><span class="sxs-lookup"><span data-stu-id="ae367-322">You can also use the **Module** and **Version** parameters of the **#Requires** keyword to require a specific version of a module in a script.</span></span>

<span data-ttu-id="ae367-323">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ae367-323">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession
Aliases: Version

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae367-324">-ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="ae367-324">-ModuleInfo</span></span>

<span data-ttu-id="ae367-325">インポートするモジュールオブジェクトの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-325">Specifies an array of module objects to import.</span></span> <span data-ttu-id="ae367-326">モジュールオブジェクトを含む変数、またはモジュールオブジェクトを取得するコマンド (など) を入力し `Get-Module -ListAvailable` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-326">Enter a variable that contains the module objects, or a command that gets the module objects, such as the following command: `Get-Module -ListAvailable`.</span></span> <span data-ttu-id="ae367-327">パイプを使用してモジュールオブジェクトをにパイプすることもでき `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-327">You can also pipe module objects to `Import-Module`.</span></span>

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: ModuleInfo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ae367-328">-Name</span><span class="sxs-lookup"><span data-stu-id="ae367-328">-Name</span></span>

<span data-ttu-id="ae367-329">インポートするモジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-329">Specifies the names of the modules to import.</span></span> <span data-ttu-id="ae367-330">モジュールの名前、または、、、またはファイルなどのモジュール内のファイルの名前を入力し `.psd1` `.psm1` `.dll` `.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-330">Enter the name of the module or the name of a file in the module, such as a `.psd1`, `.psm1`, `.dll`, or `.ps1` file.</span></span> <span data-ttu-id="ae367-331">ファイル パスは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="ae367-331">File paths are optional.</span></span> <span data-ttu-id="ae367-332">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="ae367-332">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="ae367-333">パイプを使用してモジュール名とファイル名をにパイプすることもでき `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-333">You can also pipe module names and filenames to `Import-Module`.</span></span>

<span data-ttu-id="ae367-334">パスを省略した場合、は `Import-Module` 環境変数に保存されているパスでモジュールを検索し `$env:PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-334">If you omit a path, `Import-Module` looks for the module in the paths saved in the `$env:PSModulePath` environment variable.</span></span>

<span data-ttu-id="ae367-335">可能な限り、モジュール名のみを指定してください。</span><span class="sxs-lookup"><span data-stu-id="ae367-335">Specify only the module name whenever possible.</span></span> <span data-ttu-id="ae367-336">ファイル名を指定した場合は、そのファイルに実装されているメンバーのみがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ae367-336">When you specify a file name, only the members that are implemented in that file are imported.</span></span> <span data-ttu-id="ae367-337">モジュールに他のファイルが含まれている場合は、インポートされないため、モジュールの重要なメンバーが不足している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ae367-337">If the module contains other files, they aren't imported, and you might be missing important members of the module.</span></span>

> [!NOTE]
> <span data-ttu-id="ae367-338">スクリプト ( `.ps1` ) ファイルはモジュールとしてインポートできますが、スクリプトファイルは通常、スクリプトモジュールファイル () ファイルのようには構成されていません `.psm1` 。</span><span class="sxs-lookup"><span data-stu-id="ae367-338">While it is possible to import a script (`.ps1`) file as a module, script files are usually not structured like script modules file (`.psm1`) file.</span></span> <span data-ttu-id="ae367-339">スクリプトファイルをインポートしても、モジュールとして使用できることは保証されません。</span><span class="sxs-lookup"><span data-stu-id="ae367-339">Importing a script file does not guarantee that it is usable as a module.</span></span> <span data-ttu-id="ae367-340">詳細については、「 [about_Modules](about/about_Modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae367-340">For more information, see [about_Modules](about/about_Modules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, PSSession, CimSession
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="ae367-341">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="ae367-341">-NoClobber</span></span>

<span data-ttu-id="ae367-342">現在のセッションの既存のコマンドと同じ名前のコマンドがインポートされないようにします。</span><span class="sxs-lookup"><span data-stu-id="ae367-342">Prevents importing commands that have the same names as existing commands in the current session.</span></span> <span data-ttu-id="ae367-343">既定では、 `Import-Module` エクスポートされたすべてのモジュールコマンドがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ae367-343">By default, `Import-Module` imports all exported module commands.</span></span>

<span data-ttu-id="ae367-344">同じ名前を持つコマンドは、セッション内のコマンドを非表示にしたり置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="ae367-344">Commands that have the same names can hide or replace commands in the session.</span></span> <span data-ttu-id="ae367-345">セッションでのコマンド名の競合を回避するには、**Prefix** パラメーターまたは **NoClobber** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae367-345">To avoid command name conflicts in a session, use the **Prefix** or **NoClobber** parameters.</span></span> <span data-ttu-id="ae367-346">名前の競合およびコマンドの優先順位の詳細については、[about_Modules](about/about_Modules.md) の「モジュールと名前の競合」および [about_Command_Precedence](about/about_Command_Precedence.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae367-346">For more information about name conflicts and command precedence, see "Modules and Name Conflicts" in [about_Modules](about/about_Modules.md) and [about_Command_Precedence](about/about_Command_Precedence.md).</span></span>

<span data-ttu-id="ae367-347">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ae367-347">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae367-348">-PassThru</span><span class="sxs-lookup"><span data-stu-id="ae367-348">-PassThru</span></span>

<span data-ttu-id="ae367-349">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="ae367-349">Returns an object representing the item with which you're working.</span></span> <span data-ttu-id="ae367-350">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="ae367-350">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae367-351">-Prefix</span><span class="sxs-lookup"><span data-stu-id="ae367-351">-Prefix</span></span>

<span data-ttu-id="ae367-352">インポートされたモジュールメンバーの名前の名詞にこのコマンドレットが追加するプレフィックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-352">Specifies a prefix that this cmdlet adds to the nouns in the names of imported module members.</span></span>

<span data-ttu-id="ae367-353">セッションに同じ名前の別のメンバーが存在する場合に発生する名前の競合を回避するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae367-353">Use this parameter to avoid name conflicts that might occur when different members in the session have the same name.</span></span> <span data-ttu-id="ae367-354">このパラメーターによってモジュールが変更されることはなく、モジュールが自身で使用するためにインポートするファイルには影響しません。</span><span class="sxs-lookup"><span data-stu-id="ae367-354">This parameter does not change the module, and it does not affect files that the module imports for its own use.</span></span> <span data-ttu-id="ae367-355">これらは、入れ子になったモジュールと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ae367-355">These are known as nested modules.</span></span> <span data-ttu-id="ae367-356">このコマンドレットは、現在のセッションのメンバーの名前にのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="ae367-356">This cmdlet affects only the names of members in the current session.</span></span>

<span data-ttu-id="ae367-357">たとえば、プレフィックス UTC を指定してからコマンドレットをインポートした場合、 `Get-Date` このコマンドレットはセッションではとして認識され、 `Get-UTCDate` 元のコマンドレットと混同されることはありません `Get-Date` 。</span><span class="sxs-lookup"><span data-stu-id="ae367-357">For example, if you specify the prefix UTC and then import a `Get-Date` cmdlet, the cmdlet is known in the session as `Get-UTCDate`, and it is not confused with the original `Get-Date` cmdlet.</span></span>

<span data-ttu-id="ae367-358">このパラメーターの値は、モジュールの **DefaultCommandPrefix** プロパティ (既定のプレフィックスを指定する) よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-358">The value of this parameter takes precedence over the **DefaultCommandPrefix** property of the module, which specifies the default prefix.</span></span>

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

### <span data-ttu-id="ae367-359">-PSSession</span><span class="sxs-lookup"><span data-stu-id="ae367-359">-PSSession</span></span>

<span data-ttu-id="ae367-360">このコマンドレットが現在のセッションにモジュールをインポートするときに使用する、PowerShell のユーザー管理セッション (**PSSession**) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-360">Specifies a PowerShell user-managed session (**PSSession**) from which this cmdlet imports modules into the current session.</span></span> <span data-ttu-id="ae367-361">**Pssession** を含む変数、またはコマンドなどの **pssession** を取得するコマンドを入力し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-361">Enter a variable that contains a **PSSession** or a command that gets a **PSSession**, such as a `Get-PSSession` command.</span></span>

<span data-ttu-id="ae367-362">別のセッションから現在のセッションにモジュールをインポートする際、ローカル モジュールのコマンドレットを使用するのと同じように、モジュールのコマンドレットを現在のセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-362">When you import a module from a different session into the current session, you can use the cmdlets from the module in the current session, just as you would use cmdlets from a local module.</span></span> <span data-ttu-id="ae367-363">リモートコマンドレットを使用するコマンドはリモートセッションで実行されますが、リモート処理の詳細は PowerShell によってバックグラウンドで管理されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-363">Commands that use the remote cmdlets run in the remote session, but the remoting details are managed in the background by PowerShell.</span></span>

<span data-ttu-id="ae367-364">このパラメーターは、PowerShell の暗黙的なリモート処理機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="ae367-364">This parameter uses the Implicit Remoting feature of PowerShell.</span></span> <span data-ttu-id="ae367-365">これは、コマンドレットを使用して、セッションから特定のモジュールをインポートすることと同じです `Import-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="ae367-365">It is equivalent to using the `Import-PSSession` cmdlet to import particular modules from a session.</span></span>

<span data-ttu-id="ae367-366">`Import-Module` 別のセッションから PowerShell コアモジュールをインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ae367-366">`Import-Module` cannot import PowerShell Core modules from another session.</span></span> <span data-ttu-id="ae367-367">PowerShell コアモジュールには、Microsoft. PowerShell で始まる名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="ae367-367">The PowerShell Core modules have names that begin with Microsoft.PowerShell.</span></span>

<span data-ttu-id="ae367-368">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ae367-368">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: PSSession, FullyQualifiedNameAndPSSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae367-369">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="ae367-369">-RequiredVersion</span></span>

<span data-ttu-id="ae367-370">このコマンドレットによってインポートされるモジュールのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-370">Specifies a version of the module that this cmdlet imports.</span></span> <span data-ttu-id="ae367-371">バージョンがインストールされていない場合は、によって `Import-Module` エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-371">If the version is not installed, `Import-Module` generates an error.</span></span>

<span data-ttu-id="ae367-372">既定では、は `Import-Module` バージョン番号をチェックせずにモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-372">By default, `Import-Module` imports the module without checking the version number.</span></span>

<span data-ttu-id="ae367-373">最小バージョンを指定するには、**MinimumVersion** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae367-373">To specify a minimum version, use the **MinimumVersion** parameter.</span></span> <span data-ttu-id="ae367-374">また、 **#Requires** キーワードの **Module** パラメーターと **Version** パラメーターを使用して、スクリプト内でモジュールの特定のバージョンを要求することもできます。</span><span class="sxs-lookup"><span data-stu-id="ae367-374">You can also use the **Module** and **Version** parameters of the **#Requires** keyword to require a specific version of a module in a script.</span></span>

<span data-ttu-id="ae367-375">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ae367-375">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="ae367-376">Windows オペレーティングシステムの既存のリリースに含まれているモジュールをインポートするために、 **RequiredVersion** を使用するスクリプトは、windows オペレーティングシステムの将来のリリースでは自動的には実行されません。</span><span class="sxs-lookup"><span data-stu-id="ae367-376">Scripts that use **RequiredVersion** to import modules that are included with existing releases of the Windows operating system don't automatically run in future releases of the Windows operating system.</span></span> <span data-ttu-id="ae367-377">これは、Windows オペレーティングシステムの将来のリリースにおける PowerShell モジュールのバージョン番号が、Windows オペレーティングシステムの既存のリリースにおけるモジュールのバージョン番号よりも大きいためです。</span><span class="sxs-lookup"><span data-stu-id="ae367-377">This is because PowerShell module version numbers in future releases of the Windows operating system are higher than module version numbers in existing releases of the Windows operating system.</span></span>

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae367-378">-スコープ</span><span class="sxs-lookup"><span data-stu-id="ae367-378">-Scope</span></span>

<span data-ttu-id="ae367-379">このコマンドレットがモジュールをインポートするスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-379">Specifies a scope into which this cmdlet imports the module.</span></span>

<span data-ttu-id="ae367-380">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ae367-380">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ae367-381">**グローバル**。</span><span class="sxs-lookup"><span data-stu-id="ae367-381">**Global**.</span></span> <span data-ttu-id="ae367-382">セッション内のすべてのコマンドに使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-382">Available to all commands in the session.</span></span> <span data-ttu-id="ae367-383">**Global** パラメーターと同じ効果が得られます。</span><span class="sxs-lookup"><span data-stu-id="ae367-383">Equivalent to the **Global** parameter.</span></span>
- <span data-ttu-id="ae367-384">**ローカル**。</span><span class="sxs-lookup"><span data-stu-id="ae367-384">**Local**.</span></span> <span data-ttu-id="ae367-385">現在のスコープでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-385">Available only in the current scope.</span></span>

<span data-ttu-id="ae367-386">既定では、 `Import-Module` コマンドプロンプト、スクリプトファイル、または scriptblock からコマンドレットを呼び出すと、すべてのコマンドがグローバルセッション状態にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ae367-386">By default, when `Import-Module` cmdlet is called from the command prompt, script file, or scriptblock, all the commands are imported into the global session state.</span></span> <span data-ttu-id="ae367-387">パラメーターを使用し `-Scope Local` て、モジュールの内容をスクリプトまたは scriptblock スコープにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="ae367-387">You can use the `-Scope Local` parameter to import module content into the script or scriptblock scope.</span></span>

<span data-ttu-id="ae367-388">別のモジュールから呼び出された場合、コマンドレットは、 `Import-Module` 入れ子になったモジュールのコマンドを含むモジュール内のコマンドを呼び出し元のセッション状態にインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-388">When invoked from another module, `Import-Module` cmdlet imports the commands in a module, including commands from nested modules, into the caller's session state.</span></span> <span data-ttu-id="ae367-389">またはを指定する `-Scope Global` と `-Global` 、このコマンドレットによってモジュールがグローバルセッション状態にインポートされ、セッションのすべてのコマンドで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ae367-389">Specifying `-Scope Global` or `-Global` indicates that this cmdlet imports modules into the global session state so they are available to all commands in the session.</span></span>

<span data-ttu-id="ae367-390">**Global** パラメーターは、値が **Global** である **Scope** パラメーターと同じ効果が得られます。</span><span class="sxs-lookup"><span data-stu-id="ae367-390">The **Global** parameter is equivalent to the **Scope** parameter with a value of **Global**.</span></span>

<span data-ttu-id="ae367-391">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="ae367-391">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Local, Global

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae367-392">-Variable</span><span class="sxs-lookup"><span data-stu-id="ae367-392">-Variable</span></span>

<span data-ttu-id="ae367-393">このコマンドレットがモジュールから現在のセッションにインポートする変数の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-393">Specifies an array of variables that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="ae367-394">変数のリストを入力します。</span><span class="sxs-lookup"><span data-stu-id="ae367-394">Enter a list of variables.</span></span> <span data-ttu-id="ae367-395">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-395">Wildcard characters are permitted.</span></span>

<span data-ttu-id="ae367-396">一部のモジュールは、モジュールをインポートすると、選択された変数をセッションに自動的にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-396">Some modules automatically export selected variables into your session when you import the module.</span></span>
<span data-ttu-id="ae367-397">このパラメーターを使用すると、エクスポートされた変数の中から選択できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-397">This parameter lets you select from among the exported variables.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ae367-398">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ae367-398">CommonParameters</span></span>
<span data-ttu-id="ae367-399">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ae367-399">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ae367-400">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae367-400">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ae367-401">入力</span><span class="sxs-lookup"><span data-stu-id="ae367-401">INPUTS</span></span>

### <span data-ttu-id="ae367-402">System.string、PSModuleInfo、システムのアセンブリを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae367-402">System.String, System.Management.Automation.PSModuleInfo, System.Reflection.Assembly</span></span>

<span data-ttu-id="ae367-403">パイプを使用して、モジュール名、モジュールオブジェクト、またはアセンブリオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="ae367-403">You can pipe a module name, module object, or assembly object to this cmdlet.</span></span>

## <span data-ttu-id="ae367-404">出力</span><span class="sxs-lookup"><span data-stu-id="ae367-404">OUTPUTS</span></span>

### <span data-ttu-id="ae367-405">なし、PSModuleInfo、またはシステムの管理.......</span><span class="sxs-lookup"><span data-stu-id="ae367-405">None, System.Management.Automation.PSModuleInfo, or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="ae367-406">既定で `Import-Module` は、は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="ae367-406">By default, `Import-Module` does not generate any output.</span></span> <span data-ttu-id="ae367-407">**PassThru** パラメーターを指定すると、このコマンドレットは、モジュールを表す **PSModuleInfo** オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="ae367-407">If you specify the **PassThru** parameter, the cmdlet generates a **System.Management.Automation.PSModuleInfo** object that represents the module.</span></span> <span data-ttu-id="ae367-408">**Ascustomobject** いうパラメーターを指定すると、 **pscustomobject** オブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-408">If you specify the **AsCustomObject** parameter, it generates a **PSCustomObject** object.</span></span>

## <span data-ttu-id="ae367-409">注</span><span class="sxs-lookup"><span data-stu-id="ae367-409">NOTES</span></span>

- <span data-ttu-id="ae367-410">モジュールをインポートする前に、モジュールがローカルコンピューターにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae367-410">Before you can import a module, the module must be installed on the local computer.</span></span> <span data-ttu-id="ae367-411">つまり、モジュールディレクトリは、ローカルコンピューターからアクセスできるディレクトリにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae367-411">That is, the module directory must be copied to a directory that is accessible to your local computer.</span></span> <span data-ttu-id="ae367-412">詳細については、「 [about_Modules](About/about_Modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae367-412">For more information, see [about_Modules](About/about_Modules.md).</span></span>

  <span data-ttu-id="ae367-413">また、**PSSession** パラメーターと **CIMSession** パラメーターを使用すれば、リモート コンピューターにインストールされているモジュールをインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ae367-413">You can also use the **PSSession** and **CIMSession** parameters to import modules that are installed on remote computers.</span></span> <span data-ttu-id="ae367-414">ただし、これらのモジュールのコマンドレットを使用するコマンドは、リモートコンピューター上のリモートセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-414">However, commands that use the cmdlets in these modules run in the remote session on the remote computer.</span></span>

- <span data-ttu-id="ae367-415">セッションに同じ名前と同じ種類のメンバーをインポートする場合、PowerShell は、既定で最後にインポートされたメンバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae367-415">If you import members with the same name and the same type into your session, PowerShell uses the member imported last by default.</span></span> <span data-ttu-id="ae367-416">変数と別名は置き換えられ、元の変数にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="ae367-416">Variables and aliases are replaced, and the originals aren't accessible.</span></span> <span data-ttu-id="ae367-417">関数、コマンドレット、およびプロバイダーは、新しいメンバーによって単純にシャドウされます。</span><span class="sxs-lookup"><span data-stu-id="ae367-417">Functions, cmdlets, and providers are merely shadowed by the new members.</span></span> <span data-ttu-id="ae367-418">これらのコマンド名には、スナップイン、モジュール、または関数パスの名前を指定することによってアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ae367-418">They can be accessed by qualifying the command name with the name of its snap-in, module, or function path.</span></span>

- <span data-ttu-id="ae367-419">モジュールからインポートされたコマンドの書式設定データを更新するには、 `Update-FormatData` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae367-419">To update the formatting data for commands that have been imported from a module, use the `Update-FormatData` cmdlet.</span></span> <span data-ttu-id="ae367-420">`Update-FormatData` では、モジュールからインポートされたセッションのコマンドの書式設定データも更新されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-420">`Update-FormatData` also updates the formatting data for commands in the session that were imported from modules.</span></span> <span data-ttu-id="ae367-421">モジュールのフォーマットファイルが変更された場合は、コマンドを実行して、インポートした `Update-FormatData` コマンドの書式設定データを更新できます。</span><span class="sxs-lookup"><span data-stu-id="ae367-421">If the formatting file for a module changes, you can run an `Update-FormatData` command to update the formatting data for imported commands.</span></span> <span data-ttu-id="ae367-422">モジュールをもう一度インポートする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ae367-422">You don't need to import the module again.</span></span>

- <span data-ttu-id="ae367-423">Windows PowerShell 3.0 以降では、PowerShell でインストールされるコアコマンドはモジュールにパッケージ化されています。</span><span class="sxs-lookup"><span data-stu-id="ae367-423">Starting in Windows PowerShell 3.0, the core commands that are installed with PowerShell are packaged in modules.</span></span> <span data-ttu-id="ae367-424">Windows PowerShell 2.0、およびそれ以降のバージョンの PowerShell で古いスタイルのセッションを作成するホストプログラムでは、コアコマンドはスナップイン (**PSSnapins**) にパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-424">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of PowerShell, the core commands are packaged in snap-ins (**PSSnapins**).</span></span> <span data-ttu-id="ae367-425">例外は、常にスナップインである、 **PowerShell です**。</span><span class="sxs-lookup"><span data-stu-id="ae367-425">The exception is **Microsoft.PowerShell.Core**, which is always a snap-in.</span></span> <span data-ttu-id="ae367-426">また、コマンドレットによって開始されるようなリモートセッション `New-PSSession` は、コアスナップインを含む古いスタイルのセッションです。</span><span class="sxs-lookup"><span data-stu-id="ae367-426">Also, remote sessions, such as those started by the `New-PSSession` cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="ae367-427">コアモジュールで新しいスタイルのセッションを作成する **CreateDefault2** メソッドの詳細については、 [CreateDefault2 メソッド](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae367-427">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see the [CreateDefault2 Method](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).</span></span>

- <span data-ttu-id="ae367-428">Windows PowerShell 2.0 では、モジュールオブジェクトの一部のプロパティ値 ( **ExportedCmdlets** や **nestedmodules** プロパティ値など) は、モジュールがインポートされるまで設定されませんでした。</span><span class="sxs-lookup"><span data-stu-id="ae367-428">In Windows PowerShell 2.0, some of the property values of the module object, such as the **ExportedCmdlets** and **NestedModules** property values, were not populated until the module was imported.</span></span>

- <span data-ttu-id="ae367-429">Windows PowerShell 3.0 + と互換性のない混合モードのアセンブリを含むモジュールをインポートしようとすると、 `Import-Module` 次のようなエラーメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-429">If you attempt to import a module that contains mixed-mode assemblies that aren't compatible with Windows PowerShell 3.0+, `Import-Module` returns an error message like the following one.</span></span>

  > <span data-ttu-id="ae367-430">Import-Module: 混合モードのアセンブリは、ランタイムのバージョン ' v v2.0.50727 ' に対してビルドされており、追加の構成情報がないと、4.0 ランタイムに読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="ae367-430">Import-Module : Mixed mode assembly is built against version 'v2.0.50727' of the runtime and cannot be loaded in the 4.0 runtime without additional configuration information.</span></span>

  <span data-ttu-id="ae367-431">このエラーは、Windows PowerShell 2.0 用に設計されたモジュールに、少なくとも1つのモジュールアセンブリが含まれている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="ae367-431">This error occurs when a module that is designed for Windows PowerShell 2.0 contains at least one mixed-module assembly.</span></span> <span data-ttu-id="ae367-432">C++ や C# などのマネージコードと非マネージコードの両方を含む、モジュールが混在するアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="ae367-432">A mixed-module assembly that includes both managed and non-managed code, such as C++ and C#.</span></span>

  <span data-ttu-id="ae367-433">混合モードアセンブリを含むモジュールをインポートするには、次のコマンドを使用して Windows PowerShell 2.0 を起動し、コマンドを再試行し `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="ae367-433">To import a module that contains mixed-mode assemblies, start Windows PowerShell 2.0 by using the following command, and then try the `Import-Module` command again.</span></span>

  `PowerShell.exe -Version 2.0`

- <span data-ttu-id="ae367-434">CIM セッション機能を使用するには、リモート コンピューターにおいて、WS-Management リモート処理と Common Information Model (CIM) 標準の Microsoft 実装である Windows Management Instrumentation (WMI) が必要です。</span><span class="sxs-lookup"><span data-stu-id="ae367-434">To use the CIM session feature, the remote computer must have WS-Management remoting and Windows Management Instrumentation (WMI), which is the Microsoft implementation of the Common Information Model (CIM) standard.</span></span> <span data-ttu-id="ae367-435">さらに、モジュール検出用の WMI プロバイダーまたは同じ基本機能を備えた代替 CIM プロバイダーもコンピューターに必要です。</span><span class="sxs-lookup"><span data-stu-id="ae367-435">The computer must also have the Module Discovery WMI provider or an alternate CIM provider that has the same basic features.</span></span>

  <span data-ttu-id="ae367-436">CIM セッション機能は、Windows オペレーティングシステムを実行していないコンピューターと PowerShell を搭載している Windows コンピューターで使用できますが、PowerShell リモート処理は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="ae367-436">You can use the CIM session feature on computers that aren't running a Windows operating system and on Windows computers that have PowerShell, but don't have PowerShell remoting enabled.</span></span>

  <span data-ttu-id="ae367-437">また、CIM パラメーターを使用して、ローカルコンピューターを含め、PowerShell リモート処理が有効になっているコンピューターから CIM モジュールを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="ae367-437">You can also use the CIM parameters to get CIM modules from computers that have PowerShell remoting enabled, including the local computer.</span></span> <span data-ttu-id="ae367-438">ローカルコンピューターに CIM セッションを作成すると、PowerShell は WMI ではなく DCOM を使用してセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ae367-438">When you create a CIM session on the local computer, PowerShell uses DCOM, instead of WMI, to create the session.</span></span>

- <span data-ttu-id="ae367-439">既定では、は、 `Import-Module` 子孫スコープから呼び出された場合でも、グローバルスコープ内のモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae367-439">By default, `Import-Module` imports modules in the global scope even when called from a descendant scope.</span></span> <span data-ttu-id="ae367-440">最上位レベルのスコープとすべての子孫のスコープは、モジュールのエクスポートされた要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ae367-440">The top-level scope and all descendant scopes have access to the module's exported elements.</span></span>

  <span data-ttu-id="ae367-441">子孫スコープでは、 `-Scope Local` そのスコープとそのすべての子孫スコープへのインポートが制限されます。</span><span class="sxs-lookup"><span data-stu-id="ae367-441">In a descendant scope, `-Scope Local` limits the import to that scope and all its descendant scopes.</span></span> <span data-ttu-id="ae367-442">親スコープでは、インポートされたメンバーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="ae367-442">Parent scopes then do not see the imported members.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ae367-443">`Get-Module` 現在のセッションで読み込まれたすべてのモジュールを表示します。</span><span class="sxs-lookup"><span data-stu-id="ae367-443">`Get-Module` shows all modules loaded in the current session.</span></span> <span data-ttu-id="ae367-444">これには、子孫スコープにローカルに読み込まれたモジュールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae367-444">This includes modules loaded locally in a descendant scope.</span></span> <span data-ttu-id="ae367-445">`Get-Command -Module modulename`現在のスコープに読み込まれているメンバーを確認するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="ae367-445">Use `Get-Command -Module modulename` to see which members are loaded in the current scope.</span></span>

  <span data-ttu-id="ae367-446">`Import-Module` モジュール内のクラス定義と列挙型定義を読み込みません。</span><span class="sxs-lookup"><span data-stu-id="ae367-446">`Import-Module` does not load class and enum definitions in the module.</span></span> <span data-ttu-id="ae367-447">`using module`スクリプトの先頭にあるステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae367-447">Use the `using module` statement at the beginning of your script.</span></span> <span data-ttu-id="ae367-448">これにより、クラスと列挙型の定義を含むモジュールがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ae367-448">This imports the module, including the class and enum definitions.</span></span> <span data-ttu-id="ae367-449">詳細については、「 [about_Using](About/about_Using.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae367-449">For more information, see [about_Using](About/about_Using.md).</span></span>

## <span data-ttu-id="ae367-450">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ae367-450">RELATED LINKS</span></span>

[<span data-ttu-id="ae367-451">about_Modules</span><span class="sxs-lookup"><span data-stu-id="ae367-451">about_Modules</span></span>](about/about_Modules.md)

[<span data-ttu-id="ae367-452">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="ae367-452">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="ae367-453">Get-Module</span><span class="sxs-lookup"><span data-stu-id="ae367-453">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="ae367-454">New-Module</span><span class="sxs-lookup"><span data-stu-id="ae367-454">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="ae367-455">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="ae367-455">Remove-Module</span></span>](Remove-Module.md)
