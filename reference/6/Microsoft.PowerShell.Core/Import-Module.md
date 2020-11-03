---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/import-module?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Module
ms.openlocfilehash: 4be0e64f05f841f3cf3dfdd8b5f91fdcaa158965
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216464"
---
# <span data-ttu-id="1770b-103">Import-Module</span><span class="sxs-lookup"><span data-stu-id="1770b-103">Import-Module</span></span>

## <span data-ttu-id="1770b-104">概要</span><span class="sxs-lookup"><span data-stu-id="1770b-104">SYNOPSIS</span></span>
<span data-ttu-id="1770b-105">現在のセッションにモジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="1770b-105">Adds modules to the current session.</span></span>

## <span data-ttu-id="1770b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1770b-106">SYNTAX</span></span>

### <span data-ttu-id="1770b-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="1770b-107">Name (Default)</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>]  [<CommonParameters>]
```

### <span data-ttu-id="1770b-108">PSSession</span><span class="sxs-lookup"><span data-stu-id="1770b-108">PSSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -PSSession <PSSession>  [<CommonParameters>]
```

### <span data-ttu-id="1770b-109">CimSession</span><span class="sxs-lookup"><span data-stu-id="1770b-109">CimSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="1770b-110">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="1770b-110">FullyQualifiedName</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-SkipEditionCheck] [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking]
 [-NoClobber] [-Scope <String>]  [<CommonParameters>]
```

### <span data-ttu-id="1770b-111">FullyQualifiedNameAndPSSession</span><span class="sxs-lookup"><span data-stu-id="1770b-111">FullyQualifiedNameAndPSSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-SkipEditionCheck] [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking]
 [-NoClobber] [-Scope <String>] -PSSession <PSSession>  [<CommonParameters>]
```

### <span data-ttu-id="1770b-112">アセンブリ</span><span class="sxs-lookup"><span data-stu-id="1770b-112">Assembly</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Assembly] <Assembly[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>]  [<CommonParameters>]
```

### <span data-ttu-id="1770b-113">ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="1770b-113">ModuleInfo</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Function <String[]>] [-Cmdlet <String[]>]
 [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck] [-PassThru]
 [-AsCustomObject] [-ModuleInfo] <PSModuleInfo[]> [-ArgumentList <Object[]>] [-DisableNameChecking]
 [-NoClobber] [-Scope <String>]  [<CommonParameters>]
```

## <span data-ttu-id="1770b-114">Description</span><span class="sxs-lookup"><span data-stu-id="1770b-114">DESCRIPTION</span></span>

<span data-ttu-id="1770b-115">`Import-Module`コマンドレットでは、現在のセッションに1つ以上のモジュールを追加します。</span><span class="sxs-lookup"><span data-stu-id="1770b-115">The `Import-Module` cmdlet adds one or more modules to the current session.</span></span> <span data-ttu-id="1770b-116">PowerShell 3.0 以降では、モジュール内のコマンドまたはプロバイダーを使用すると、インストールされているモジュールが自動的にセッションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="1770b-116">Starting in PowerShell 3.0, installed modules are automatically imported to the session when you use any commands or providers in the module.</span></span> <span data-ttu-id="1770b-117">ただし、このコマンドを使用してモジュールをインポートすることもでき `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-117">However, you can still use the `Import-Module` command to import a module.</span></span>
<span data-ttu-id="1770b-118">自動モジュールインポートは、ユーザー設定変数を使用して無効にすることができ `$PSModuleAutoloadingPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-118">You can disable automatic module importing using the `$PSModuleAutoloadingPreference` preference variable.</span></span> <span data-ttu-id="1770b-119">変数の詳細については `$PSModuleAutoloadingPreference` 、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1770b-119">For more information about the `$PSModuleAutoloadingPreference` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="1770b-120">モジュールは、PowerShell で使用できるメンバーを含むパッケージです。</span><span class="sxs-lookup"><span data-stu-id="1770b-120">A module is a package that contains members that can be used in PowerShell.</span></span> <span data-ttu-id="1770b-121">メンバーには、コマンドレット、プロバイダー、スクリプト、関数、変数、およびその他のツールとファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1770b-121">Members include cmdlets, providers, scripts, functions, variables, and other tools and files.</span></span> <span data-ttu-id="1770b-122">モジュールをインポートすると、モジュールのメンバーをセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1770b-122">After a module is imported, you can use the module members in your session.</span></span> <span data-ttu-id="1770b-123">モジュールの詳細については、「 [about_Modules](About/about_Modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1770b-123">For more information about modules, see [about_Modules](About/about_Modules.md).</span></span>

<span data-ttu-id="1770b-124">既定では、は、モジュールによっ `Import-Module` てエクスポートされるすべてのメンバーをインポートしますが、 **エイリアス** 、 **関数** 、 **コマンドレット** 、および **変数** パラメーターを使用して、インポートするメンバーを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="1770b-124">By default, `Import-Module` imports all members that the module exports, but you can use the **Alias** , **Function** , **Cmdlet** , and **Variable** parameters to restrict which members are imported.</span></span> <span data-ttu-id="1770b-125">**NoClobber** パラメーターは、 `Import-Module` 現在のセッションのメンバーと同じ名前を持つメンバーをでインポートできないようにします。</span><span class="sxs-lookup"><span data-stu-id="1770b-125">The **NoClobber** parameter prevents `Import-Module` from importing members that have the same names as members in the current session.</span></span>

<span data-ttu-id="1770b-126">`Import-Module` 現在のセッションにのみモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-126">`Import-Module` imports a module only into the current session.</span></span> <span data-ttu-id="1770b-127">すべての新しいセッションにモジュールをインポートするには、 `Import-Module` PowerShell プロファイルにコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="1770b-127">To import the module into every new session, add an `Import-Module` command to your PowerShell profile.</span></span> <span data-ttu-id="1770b-128">プロファイルの詳細については、「[about_Profiles](About/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1770b-128">For more information about profiles, see [about_Profiles](About/about_Profiles.md).</span></span>

<span data-ttu-id="1770b-129">リモートコンピューター上に **PSSession** を作成することによって、PowerShell リモート処理が有効になっているリモート Windows コンピューターを管理できます。</span><span class="sxs-lookup"><span data-stu-id="1770b-129">You can manage remote Windows computers that have PowerShell remoting enabled by creating a **PSSession** on the remote computer.</span></span> <span data-ttu-id="1770b-130">次に、の **PSSession** パラメーター `Import-Module` を使用して、リモートコンピューターにインストールされているモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-130">Then use the **PSSession** parameter of `Import-Module` to import the modules that are installed on the remote computer.</span></span> <span data-ttu-id="1770b-131">現在のセッションでインポートしたコマンドを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1770b-131">You can now use the imported commands in the current session.</span></span> <span data-ttu-id="1770b-132">コマンドは、リモートコンピューター上で暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-132">The commands implicitly run on the remote computer.</span></span>

<span data-ttu-id="1770b-133">Windows PowerShell 3.0 以降では、を使用し `Import-Module` て Common Information Model (CIM) モジュールをインポートできます。このモジュールでは、コマンドレットがコマンドレット定義 XML (CDXML) ファイルで定義されています。</span><span class="sxs-lookup"><span data-stu-id="1770b-133">Starting in Windows PowerShell 3.0, you can use `Import-Module` to import Common Information Model (CIM) modules, in which the cmdlets are defined in Cmdlet Definition XML (CDXML) files.</span></span> <span data-ttu-id="1770b-134">この機能により、C++ で記述されたコードなどの非マネージ コード アセンブリに実装されているコマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1770b-134">This feature allows you to use cmdlets that are implemented in non-managed code assemblies, such as those written in C++.</span></span>

<span data-ttu-id="1770b-135">Windows オペレーティングシステムを実行していないコンピューターを含め、PowerShell リモート処理が有効になっていないリモートコンピューターの場合は、の **CIMSession** パラメーターを使用して、 `Import-Module` リモートコンピューターから CIM モジュールをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="1770b-135">For remote computers that don't have PowerShell remoting enabled, including computers that aren't running the Windows operating system, you can use the **CIMSession** parameter of `Import-Module` to import CIM modules from the remote computer.</span></span> <span data-ttu-id="1770b-136">インポートされたコマンドは、リモートコンピューター上で暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-136">The imported commands run implicitly on the remote computer.</span></span> <span data-ttu-id="1770b-137">**CIMSession** は、リモートコンピューター上の WINDOWS MANAGEMENT INSTRUMENTATION (WMI) に接続します。</span><span class="sxs-lookup"><span data-stu-id="1770b-137">A **CIMSession** is a connection to Windows Management Instrumentation (WMI) on the remote computer.</span></span>

## <span data-ttu-id="1770b-138">例</span><span class="sxs-lookup"><span data-stu-id="1770b-138">EXAMPLES</span></span>

### <span data-ttu-id="1770b-139">例 1: モジュールのメンバーを現在のセッションにインポートする</span><span class="sxs-lookup"><span data-stu-id="1770b-139">Example 1: Import the members of a module into the current session</span></span>

<span data-ttu-id="1770b-140">この例では、 **Psdiagnostics** モジュールのメンバーを現在のセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-140">This example imports the members of the **PSDiagnostics** module into the current session.</span></span>

```powershell
Import-Module -Name PSDiagnostics
```

### <span data-ttu-id="1770b-141">例 2: モジュールパスで指定されたすべてのモジュールをインポートする</span><span class="sxs-lookup"><span data-stu-id="1770b-141">Example 2: Import all modules specified by the module path</span></span>

<span data-ttu-id="1770b-142">この例では、環境変数によって指定されたパスにある使用可能なすべてのモジュール `$env:PSModulePath` を現在のセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-142">This example imports all available modules in the path specified by the `$env:PSModulePath` environment variable into the current session.</span></span>

```powershell
Get-Module -ListAvailable | Import-Module
```

### <span data-ttu-id="1770b-143">例 3: 現在のセッションに複数のモジュールのメンバーをインポートする</span><span class="sxs-lookup"><span data-stu-id="1770b-143">Example 3: Import the members of several modules into the current session</span></span>

<span data-ttu-id="1770b-144">この例では、 **Psdiagnostics** および **Dism** モジュールのメンバーを現在のセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-144">This example imports the members of the **PSDiagnostics** and **Dism** modules into the current session.</span></span>

```powershell
$m = Get-Module -ListAvailable PSDiagnostics, Dism
Import-Module -ModuleInfo $m
```

<span data-ttu-id="1770b-145">`Get-Module`コマンドレットは、 **Psdiagnostics** および **Dism** モジュールを取得し、変数にオブジェクトを保存し `$m` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-145">The `Get-Module` cmdlet gets the **PSDiagnostics** and **Dism** modules and saves the objects in the `$m` variable.</span></span> <span data-ttu-id="1770b-146">セッションにまだインポートされていないモジュールを取得する場合は、 **ListAvailable** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="1770b-146">The **ListAvailable** parameter is required when you're getting modules that aren't yet imported into the session.</span></span>

<span data-ttu-id="1770b-147">の **Moduleinfo** パラメーター `Import-Module` は、モジュールを現在のセッションにインポートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-147">The **ModuleInfo** parameter of `Import-Module` is used to import the modules into the current session.</span></span>

### <span data-ttu-id="1770b-148">例 4: パスによって指定されたすべてのモジュールをインポートする</span><span class="sxs-lookup"><span data-stu-id="1770b-148">Example 4: Import all modules specified by a path</span></span>

<span data-ttu-id="1770b-149">この例では、明示的なパスを使用して、インポートするモジュールを識別します。</span><span class="sxs-lookup"><span data-stu-id="1770b-149">This example uses an explicit path to identify the module to import.</span></span>

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

<span data-ttu-id="1770b-150">**Verbose** パラメーターを使用すると、は、 `Import-Module` モジュールを読み込むときに進行状況を報告します。</span><span class="sxs-lookup"><span data-stu-id="1770b-150">Using the **Verbose** parameter causes `Import-Module` to report progress as it loads the module.</span></span>
<span data-ttu-id="1770b-151">**Verbose** 、 **PassThru** 、または **ascustomobject** 各パラメーターを指定しない `Import-Module` と、モジュールをインポートしても出力は生成されません。</span><span class="sxs-lookup"><span data-stu-id="1770b-151">Without the **Verbose** , **PassThru** , or **AsCustomObject** parameter, `Import-Module` does not generate any output when it imports a module.</span></span>

### <span data-ttu-id="1770b-152">例 5: セッションにインポートされたモジュールメンバーを制限する</span><span class="sxs-lookup"><span data-stu-id="1770b-152">Example 5: Restrict module members imported into a session</span></span>

<span data-ttu-id="1770b-153">この例では、セッションにインポートされるモジュールメンバーと、セッションに対するこのコマンドの影響を制限する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1770b-153">This example shows how to restrict which module members are imported into the session and the effect of this command on the session.</span></span> <span data-ttu-id="1770b-154">**関数** パラメーターは、モジュールからインポートされるメンバーを制限します。</span><span class="sxs-lookup"><span data-stu-id="1770b-154">The **Function** parameter limits the members that are imported from the module.</span></span> <span data-ttu-id="1770b-155">**エイリアス** 、 **変数** 、および **コマンドレット** パラメーターを使用して、モジュールがインポートする他のメンバーを制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="1770b-155">You can also use the **Alias** , **Variable** , and **Cmdlet** parameters to restrict other members that a module imports.</span></span>

<span data-ttu-id="1770b-156">`Get-Module`コマンドレットは、 **psdiagnostics** モジュールを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="1770b-156">The `Get-Module` cmdlet gets the object that represents the **PSDiagnostics** module.</span></span> <span data-ttu-id="1770b-157">**ExportedCmdlets** プロパティは、すべてがインポートされていない場合でも、モジュールがエクスポートするすべてのコマンドレットを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="1770b-157">The **ExportedCmdlets** property lists all the cmdlets that the module exports, even though they were not all imported.</span></span>

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

<span data-ttu-id="1770b-158">コマンドレットの **module** パラメーターを使用すると、 `Get-Command` **psdiagnostics** モジュールからインポートされたコマンドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-158">Using the **Module** parameter of the `Get-Command` cmdlet shows the commands that were imported from the **PSDiagnostics** module.</span></span> <span data-ttu-id="1770b-159">結果によって、およびコマンドレットだけがインポートされたことが確認さ `Disable-PSTrace` `Enable-PSTrace` れます。</span><span class="sxs-lookup"><span data-stu-id="1770b-159">The results confirm that only the `Disable-PSTrace` and `Enable-PSTrace` cmdlets were imported.</span></span>

### <span data-ttu-id="1770b-160">例 6: モジュールのメンバーをインポートし、プレフィックスを追加する</span><span class="sxs-lookup"><span data-stu-id="1770b-160">Example 6: Import the members of a module and add a prefix</span></span>

<span data-ttu-id="1770b-161">この例では、 **Psdiagnostics** モジュールを現在のセッションにインポートし、メンバー名にプレフィックスを追加して、プレフィックスの付いたメンバー名を表示します。</span><span class="sxs-lookup"><span data-stu-id="1770b-161">This example imports the **PSDiagnostics** module into the current session, adds a prefix to the member names, and then displays the prefixed member names.</span></span> <span data-ttu-id="1770b-162">の **prefix** パラメーターは、 `Import-Module` モジュールからインポートされるすべてのメンバーに **x** プレフィックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="1770b-162">The **Prefix** parameter of `Import-Module` adds the **x** prefix to all members that are imported from the module.</span></span> <span data-ttu-id="1770b-163">プレフィックスは、現在のセッションのメンバーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-163">The prefix applies only to the members in the current session.</span></span> <span data-ttu-id="1770b-164">モジュールは変更されません。</span><span class="sxs-lookup"><span data-stu-id="1770b-164">It does not change the module.</span></span> <span data-ttu-id="1770b-165">**PassThru** パラメーターは、インポートされたモジュールを表すモジュールオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="1770b-165">The **PassThru** parameter returns a module object that represents the imported module.</span></span>

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

<span data-ttu-id="1770b-166">`Get-Command` モジュールからインポートされたメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="1770b-166">`Get-Command` gets the members that have been imported from the module.</span></span> <span data-ttu-id="1770b-167">出力から、モジュール メンバーにプレフィックスが正しく追加されたことがわかります。</span><span class="sxs-lookup"><span data-stu-id="1770b-167">The output shows that the module members were correctly prefixed.</span></span>

### <span data-ttu-id="1770b-168">例 7: カスタムオブジェクトを取得して使用する</span><span class="sxs-lookup"><span data-stu-id="1770b-168">Example 7: Get and use a custom object</span></span>

<span data-ttu-id="1770b-169">この例では、 **インポートモジュール** によって返されたカスタムオブジェクトを取得して使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1770b-169">This example demonstrates how to get and use the custom object returned by **Import-Module** .</span></span>

<span data-ttu-id="1770b-170">カスタム オブジェクトには、インポートされた各モジュール メンバーを表す合成メンバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1770b-170">Custom objects include synthetic members that represent each of the imported module members.</span></span> <span data-ttu-id="1770b-171">たとえば、モジュールのコマンドレットと関数は、カスタム オブジェクトのスクリプト メソッドに変換されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-171">For example, the cmdlets and functions in a module are converted to script methods of the custom object.</span></span>

<span data-ttu-id="1770b-172">カスタムオブジェクトは、スクリプト作成に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1770b-172">Custom objects are useful in scripting.</span></span> <span data-ttu-id="1770b-173">また、インポートされた複数のオブジェクトが同じ名前を持つ場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1770b-173">They are also useful when several imported objects have the same names.</span></span> <span data-ttu-id="1770b-174">オブジェクトのスクリプト メソッドを使用すると、モジュール名を含め、インポートされたメンバーの完全修飾名を指定した場合と同じ効果が得られます。</span><span class="sxs-lookup"><span data-stu-id="1770b-174">Using the script method of an object is equivalent to specifying the fully qualified name of an imported member, including its module name.</span></span>

<span data-ttu-id="1770b-175">**Ascustomobject** "パラメーター" は、スクリプトモジュールをインポートするときにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1770b-175">The **AsCustomObject** parameter can be used only when importing a script module.</span></span> <span data-ttu-id="1770b-176">使用 `Get-Module` できるモジュールがスクリプトモジュールであるかどうかを判断するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="1770b-176">Use `Get-Module` to determine which of the available modules is a script module.</span></span>

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

<span data-ttu-id="1770b-177">**カレンダーの表示** スクリプトモジュールは、 **ascustomobject** 使用してカスタムオブジェクトを要求し、 **PassThru** パラメーターを使用してオブジェクトを返すことによってインポートされます。</span><span class="sxs-lookup"><span data-stu-id="1770b-177">The **Show-Calendar** script module is imported using the **AsCustomObject** parameter to request a custom object and the **PassThru** parameter to return the object.</span></span> <span data-ttu-id="1770b-178">生成されたカスタムオブジェクトは変数に保存され `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-178">The resulting custom object is saved in the `$a` variable.</span></span>

<span data-ttu-id="1770b-179">`$a`変数をコマンドレットにパイプ処理して、保存された `Get-Member` オブジェクトのプロパティとメソッドを表示します。</span><span class="sxs-lookup"><span data-stu-id="1770b-179">The `$a` variable is piped to the `Get-Member` cmdlet to show the properties and methods of the saved object.</span></span> <span data-ttu-id="1770b-180">出力には、 **カレンダーの表示** スクリプトメソッドが示されています。</span><span class="sxs-lookup"><span data-stu-id="1770b-180">The output shows a **Show-Calendar** script method.</span></span>

<span data-ttu-id="1770b-181">**Calendar** script メソッドを呼び出すには、名前にハイフンが含まれているため、メソッド名を引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="1770b-181">To call the **Show-Calendar** script method, the method name must be enclosed in quotation marks because the name includes a hyphen.</span></span>

### <span data-ttu-id="1770b-182">例 8: 同じセッションにモジュールを再インポートする</span><span class="sxs-lookup"><span data-stu-id="1770b-182">Example 8: Reimport a module into the same session</span></span>

<span data-ttu-id="1770b-183">この例では、 **Force** `Import-Module` モジュールを同じセッションに再インポートときにの Force パラメーターを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1770b-183">This example shows how to use the **Force** parameter of `Import-Module` when you're reimporting a module into the same session.</span></span> <span data-ttu-id="1770b-184">**Force** パラメーターは、読み込まれたモジュールを削除し、再度インポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-184">The **Force** parameter removes the loaded module and then imports it again.</span></span>

```powershell
Import-Module PSDiagnostics
Import-Module PSDiagnostics -Force -Prefix PS
```

<span data-ttu-id="1770b-185">最初のコマンドは、 **Psdiagnostics** モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-185">The first command imports the **PSDiagnostics** module.</span></span> <span data-ttu-id="1770b-186">2 番目のコマンドは、このモジュールを今度は **Prefix** パラメーターを使用してインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-186">The second command imports the module again, this time using the **Prefix** parameter.</span></span>

<span data-ttu-id="1770b-187">**Force** パラメーターを指定しない場合、セッションには各 **psdiagnostics** コマンドレットの2つのコピーが含まれます。1つは標準名、もう1つはプレフィックス付きの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="1770b-187">Without the **Force** parameter, the session would include two copies of each **PSDiagnostics** cmdlet, one with the standard name and one with the prefixed name.</span></span>

### <span data-ttu-id="1770b-188">例 9: インポートされたコマンドによって非表示になっているコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="1770b-188">Example 9: Run commands that have been hidden by imported commands</span></span>

<span data-ttu-id="1770b-189">この例は、インポートされたコマンドで非表示になったコマンドを実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1770b-189">This example shows how to run commands that have been hidden by imported commands.</span></span> <span data-ttu-id="1770b-190">**Testmodule** モジュールには、年と日を返すという名前の関数が含まれてい `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-190">The **TestModule** module includes a function named `Get-Date` that returns the year and day of the year.</span></span>

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

<span data-ttu-id="1770b-191">最初の `Get-Date` コマンドレットは、現在の日付の **DateTime** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="1770b-191">The first `Get-Date` cmdlet returns a **DateTime** object with the current date.</span></span> <span data-ttu-id="1770b-192">**Testmodule** モジュールをインポートすると、は年 `Get-Date` と日を返します。</span><span class="sxs-lookup"><span data-stu-id="1770b-192">After importing the **TestModule** module, `Get-Date` returns the year and day of the year.</span></span>

<span data-ttu-id="1770b-193">の **all** パラメーターを使用すると、 `Get-Command` セッション内のすべてのコマンドが表示され `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-193">Using the **All** parameter of `Get-Command` show all the `Get-Date` commands in the session.</span></span> <span data-ttu-id="1770b-194">結果には、セッションに2つの `Get-Date` コマンド ( **testmodule** モジュールの関数と、 **Microsoft. PowerShell. ユーティリティ** モジュールのコマンドレット) があることが示されています。</span><span class="sxs-lookup"><span data-stu-id="1770b-194">The results show that there are two `Get-Date` commands in the session, a function from the **TestModule** module and a cmdlet from the **Microsoft.PowerShell.Utility** module.</span></span>

<span data-ttu-id="1770b-195">関数はコマンドレットよりも優先されるため、 `Get-Date` **testmodule** モジュールの関数はコマンドレットではなく、を実行し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-195">Because functions take precedence over cmdlets, the `Get-Date` function from the **TestModule** module runs, instead of the `Get-Date` cmdlet.</span></span> <span data-ttu-id="1770b-196">の元のバージョンを実行するには、 `Get-Date` コマンド名をモジュール名で修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1770b-196">To run the original version of `Get-Date`, you must qualify the command name with the module name.</span></span>

<span data-ttu-id="1770b-197">PowerShell でのコマンドの優先順位の詳細については、「 [about_Command_Precedence](about/about_Command_Precedence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1770b-197">For more information about command precedence in PowerShell, see [about_Command_Precedence](about/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="1770b-198">例 10: モジュールの最小バージョンをインポートする</span><span class="sxs-lookup"><span data-stu-id="1770b-198">Example 10: Import a minimum version of a module</span></span>

<span data-ttu-id="1770b-199">この例では、 **PowerShellGet** モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-199">This example imports the **PowerShellGet** module.</span></span> <span data-ttu-id="1770b-200">の **MinimumVersion** パラメーターを使用して `Import-Module` 、バージョン2.0.0 以上のモジュールのみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-200">It uses the **MinimumVersion** parameter of `Import-Module` to import only version 2.0.0 or greater of the module.</span></span>

```powershell
Import-Module -Name PowerShellGet -MinimumVersion 2.0.0
```

<span data-ttu-id="1770b-201">また、 **RequiredVersion** パラメーターを使用して、モジュールの特定のバージョンをインポートしたり、キーワードの **Module** パラメーターと **version** パラメーターを使用して、 `#Requires` スクリプト内でモジュールの特定のバージョンを要求したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1770b-201">You can also use the **RequiredVersion** parameter to import a particular version of a module, or use the **Module** and **Version** parameters of the `#Requires` keyword to require a particular version of a module in a script.</span></span>

### <span data-ttu-id="1770b-202">例 11: 完全修飾名を使用してインポートする</span><span class="sxs-lookup"><span data-stu-id="1770b-202">Example 11: Import using a fully qualified name</span></span>

<span data-ttu-id="1770b-203">この例では、FullyQualifiedName を使用して、モジュールの特定のバージョンをインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-203">This example imports a specific version of a module using the FullyQualifiedName.</span></span>

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

### <span data-ttu-id="1770b-204">例 12: 完全修飾パスを使用してインポートする</span><span class="sxs-lookup"><span data-stu-id="1770b-204">Example 12: Import using a fully qualified path</span></span>

<span data-ttu-id="1770b-205">この例では、完全修飾パスを使用して、モジュールの特定のバージョンをインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-205">This example imports a specific version of a module using the fully qualified path.</span></span>

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

### <span data-ttu-id="1770b-206">例 13: リモートコンピューターからモジュールをインポートする</span><span class="sxs-lookup"><span data-stu-id="1770b-206">Example 13: Import a module from a remote computer</span></span>

<span data-ttu-id="1770b-207">この例では、コマンドレットを使用して、 `Import-Module` リモートコンピューターからモジュールをインポートする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1770b-207">This example shows how to use the `Import-Module` cmdlet to import a module from a remote computer.</span></span>
<span data-ttu-id="1770b-208">このコマンドは、PowerShell の暗黙的なリモート処理機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="1770b-208">This command uses the Implicit Remoting feature of PowerShell.</span></span>

<span data-ttu-id="1770b-209">別のセッションからモジュールをインポートすると、現在のセッションでコマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1770b-209">When you import modules from another session, you can use the cmdlets in the current session.</span></span>
<span data-ttu-id="1770b-210">ただし、コマンドレットを使用するコマンドは、リモートセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-210">However, commands that use the cmdlets run in the remote session.</span></span>

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

<span data-ttu-id="1770b-211">`New-PSSession` Server01 コンピューターへのリモートセッション ( **PSSession** ) を作成します。</span><span class="sxs-lookup"><span data-stu-id="1770b-211">`New-PSSession` creates a remote session ( **PSSession** ) to the Server01 computer.</span></span> <span data-ttu-id="1770b-212">**PSSession** は変数に保存され `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-212">The **PSSession** is saved in the `$s` variable.</span></span>

<span data-ttu-id="1770b-213">PSSession パラメーターを指定してを実行 `Get-Module` すると、 **netsecurity** モジュールがリモートコンピューターにインストールされ、使用可能であることが示されます。 **PSSession**</span><span class="sxs-lookup"><span data-stu-id="1770b-213">Running `Get-Module` with the **PSSession** parameter shows that the **NetSecurity** module is installed and available on the remote computer.</span></span> <span data-ttu-id="1770b-214">このコマンドは、コマンドレットを使用して `Invoke-Command` `Get-Module` リモートセッションでコマンドを実行することと同じです。</span><span class="sxs-lookup"><span data-stu-id="1770b-214">This command is equivalent to using the `Invoke-Command` cmdlet to run `Get-Module` command in the remote session.</span></span> <span data-ttu-id="1770b-215">例: (`Invoke-Command $s {Get-Module -ListAvailable -Name NetSecurity`</span><span class="sxs-lookup"><span data-stu-id="1770b-215">For example: (`Invoke-Command $s {Get-Module -ListAvailable -Name NetSecurity`</span></span>

<span data-ttu-id="1770b-216">`Import-Module` **PSSession** パラメーターを指定してを実行すると、リモートコンピューターから **netsecurity** モジュールが現在のセッションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="1770b-216">Running `Import-Module` with the **PSSession** parameter imports the **NetSecurity** module from the remote computer into the current session.</span></span> <span data-ttu-id="1770b-217">コマンド `Get-Command` レットを使用すると、 **netsecurity** モジュールから **get** および include **Firewall** で始まるコマンドを取得できます。</span><span class="sxs-lookup"><span data-stu-id="1770b-217">The `Get-Command` cmdlet is used to get commands that begin with **Get** and include **Firewall** from the **NetSecurity** module.</span></span> <span data-ttu-id="1770b-218">出力によって、モジュールとそのコマンドレットが現在のセッションにインポートされたことが確認されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-218">The output confirms that the module and its cmdlets were imported into the current session.</span></span>

<span data-ttu-id="1770b-219">次に、 `Get-NetFirewallRule` コマンドレットは、Server01 コンピューター上のファイアウォール規則を取得 Windows リモート管理します。</span><span class="sxs-lookup"><span data-stu-id="1770b-219">Next, the `Get-NetFirewallRule` cmdlet gets Windows Remote Management firewall rules on the Server01 computer.</span></span> <span data-ttu-id="1770b-220">これは、コマンドレットを使用して `Invoke-Command` `Get-NetFirewallRule` リモートセッションで実行することと同じです。</span><span class="sxs-lookup"><span data-stu-id="1770b-220">This is equivalent to using the `Invoke-Command` cmdlet to run `Get-NetFirewallRule` on the remote session.</span></span>

### <span data-ttu-id="1770b-221">例 14: Windows オペレーティングシステムを使用せずにリモートコンピューター上の記憶域を管理する</span><span class="sxs-lookup"><span data-stu-id="1770b-221">Example 14: Manage storage on a remote computer without the Windows operating system</span></span>

<span data-ttu-id="1770b-222">この例では、コンピューターの管理者がモジュール検出 WMI プロバイダーをインストールしています。これにより、プロバイダー用に設計された CIM コマンドを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1770b-222">In this example, the administrator of the computer has installed the Module Discovery WMI provider, which allows you to use CIM commands that are designed for the provider.</span></span>

<span data-ttu-id="1770b-223">コマンドレットでは、 `New-CimSession` RSDGF03 という名前のリモートコンピューター上にセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="1770b-223">The `New-CimSession` cmdlet creates a session on the remote computer named RSDGF03.</span></span> <span data-ttu-id="1770b-224">セッションは、リモートコンピューター上の WMI サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="1770b-224">The session connects to the WMI service on the remote computer.</span></span> <span data-ttu-id="1770b-225">CIM セッションは変数に保存され `$cs` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-225">The CIM session is saved in the `$cs` variable.</span></span>
<span data-ttu-id="1770b-226">`Import-Module` の **CimSession** を使用して、 `$cs` RSDGF03 コンピューターから **ストレージ** CIM モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-226">`Import-Module` uses the **CimSession** in `$cs` to import the **Storage** CIM module from the RSDGF03 computer.</span></span>

<span data-ttu-id="1770b-227">`Get-Command`コマンドレットは、 `Get-Disk` **ストレージ** モジュール内のコマンドを表示します。</span><span class="sxs-lookup"><span data-stu-id="1770b-227">The `Get-Command` cmdlet shows the `Get-Disk` command in the **Storage** module.</span></span> <span data-ttu-id="1770b-228">CIM モジュールをローカルセッションにインポートすると、PowerShell によって各コマンドの CDXML ファイルが PowerShell スクリプトに変換されます。 PowerShell スクリプトは、ローカルセッションの関数として表示されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-228">When you import a CIM module into the local session, PowerShell converts the CDXML files for each command into PowerShell scripts, which appear as functions in the local session.</span></span>

<span data-ttu-id="1770b-229">`Get-Disk`はローカルセッションで入力されますが、コマンドレットは、インポート元のリモートコンピューター上で暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-229">Although `Get-Disk` is typed in the local session, the cmdlet implicitly runs on the remote computer from which it was imported.</span></span> <span data-ttu-id="1770b-230">コマンドを実行すると、リモートコンピューターからローカルセッションにオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-230">The command returns objects from the remote computer to the local session.</span></span>

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

## <span data-ttu-id="1770b-231">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1770b-231">PARAMETERS</span></span>

### <span data-ttu-id="1770b-232">-エイリアス</span><span class="sxs-lookup"><span data-stu-id="1770b-232">-Alias</span></span>

<span data-ttu-id="1770b-233">このコマンドレットがモジュールから現在のセッションにインポートするエイリアスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-233">Specifies the aliases that this cmdlet imports from the module into the current session.</span></span> <span data-ttu-id="1770b-234">エイリアスのコンマ区切りのリストを入力します。</span><span class="sxs-lookup"><span data-stu-id="1770b-234">Enter a comma-separated list of aliases.</span></span> <span data-ttu-id="1770b-235">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1770b-235">Wildcard characters are permitted.</span></span>

<span data-ttu-id="1770b-236">一部のモジュールは、モジュールをインポートすると、選択されたエイリアスをセッションに自動的にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-236">Some modules automatically export selected aliases into your session when you import the module.</span></span>
<span data-ttu-id="1770b-237">このパラメーターを使用すると、エクスポートされたエイリアスの中から選択できます。</span><span class="sxs-lookup"><span data-stu-id="1770b-237">This parameter lets you select from among the exported aliases.</span></span>

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

### <span data-ttu-id="1770b-238">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="1770b-238">-ArgumentList</span></span>

<span data-ttu-id="1770b-239">コマンドの実行中にスクリプトモジュールに渡される引数の配列、またはパラメーター値を指定し `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-239">Specifies an array of arguments, or parameter values, that are passed to a script module during the `Import-Module` command.</span></span> <span data-ttu-id="1770b-240">このパラメーターは、スクリプトモジュールをインポートする場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="1770b-240">This parameter is valid only when you're importing a script module.</span></span>

<span data-ttu-id="1770b-241">**ArgumentList** パラメーターは、別名 **args** を使用して参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="1770b-241">You can also refer to the **ArgumentList** parameter by its alias, **args** .</span></span> <span data-ttu-id="1770b-242">**ArgumentList** の動作の詳細については、「 [about_Splatting](about/about_Splatting.md#splatting-with-arrays)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1770b-242">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

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

### <span data-ttu-id="1770b-243">-AsCustomObject 場合</span><span class="sxs-lookup"><span data-stu-id="1770b-243">-AsCustomObject</span></span>

<span data-ttu-id="1770b-244">このコマンドレットが、インポートされたモジュールメンバーを表すメンバーを持つカスタムオブジェクトを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="1770b-244">Indicates that this cmdlet returns a custom object with members that represent the imported module members.</span></span> <span data-ttu-id="1770b-245">このパラメーターは、スクリプト モジュールに対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="1770b-245">This parameter is valid only for script modules.</span></span>

<span data-ttu-id="1770b-246">**Ascustomobject** パラメーターを使用すると、 `Import-Module` モジュールメンバーがセッションにインポートされ、その後、 **PSModuleInfo** オブジェクトではなく **pscustomobject** オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-246">When you use the **AsCustomObject** parameter, `Import-Module` imports the module members into the session and then returns a **PSCustomObject** object instead of a **PSModuleInfo** object.</span></span> <span data-ttu-id="1770b-247">カスタム オブジェクトを変数に保存し、ドット表記を使用してメンバーを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="1770b-247">You can save the custom object in a variable and use dot notation to invoke the members.</span></span>

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

### <span data-ttu-id="1770b-248">-Assembly</span><span class="sxs-lookup"><span data-stu-id="1770b-248">-Assembly</span></span>

<span data-ttu-id="1770b-249">アセンブリオブジェクトの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-249">Specifies an array of assembly objects.</span></span> <span data-ttu-id="1770b-250">このコマンドレットは、指定したアセンブリオブジェクトに実装されているコマンドレットとプロバイダーをインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-250">This cmdlet imports the cmdlets and providers implemented in the specified assembly objects.</span></span> <span data-ttu-id="1770b-251">アセンブリ オブジェクトが保存されている変数か、アセンブリ オブジェクトを作成するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="1770b-251">Enter a variable that contains assembly objects or a command that creates assembly objects.</span></span> <span data-ttu-id="1770b-252">パイプを使用してアセンブリオブジェクトをにパイプすることもでき `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-252">You can also pipe an assembly object to `Import-Module`.</span></span>

<span data-ttu-id="1770b-253">このパラメーターを使用すると、指定されたアセンブリによって実装されたコマンドレットとプロバイダーのみがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="1770b-253">When you use this parameter, only the cmdlets and providers implemented by the specified assemblies are imported.</span></span> <span data-ttu-id="1770b-254">モジュールに他のファイルが含まれている場合は、インポートされないため、モジュールの重要なメンバーが不足している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1770b-254">If the module contains other files, they aren't imported, and you might be missing important members of the module.</span></span> <span data-ttu-id="1770b-255">モジュールのデバッグとテスト、またはモジュールの作成者によって使用するように指示された場合は、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1770b-255">Use this parameter for debugging and testing the module, or when you're instructed to use it by the module author.</span></span>

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

### <span data-ttu-id="1770b-256">-CimNamespace</span><span class="sxs-lookup"><span data-stu-id="1770b-256">-CimNamespace</span></span>

<span data-ttu-id="1770b-257">CIM モジュールを公開する代替 CIM プロバイダーの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-257">Specifies the namespace of an alternate CIM provider that exposes CIM modules.</span></span> <span data-ttu-id="1770b-258">既定値は、モジュール検出用の WMI プロバイダーの名前空間です。</span><span class="sxs-lookup"><span data-stu-id="1770b-258">The default value is the namespace of the Module Discovery WMI provider.</span></span>

<span data-ttu-id="1770b-259">Windows オペレーティングシステムを実行していないコンピューターやデバイスから CIM モジュールをインポートするには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1770b-259">Use this parameter to import CIM modules from computers and devices that aren't running a Windows operating system.</span></span>

<span data-ttu-id="1770b-260">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1770b-260">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="1770b-261">-CimResourceUri</span><span class="sxs-lookup"><span data-stu-id="1770b-261">-CimResourceUri</span></span>

<span data-ttu-id="1770b-262">CIM モジュールの代替の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-262">Specifies an alternate location for CIM modules.</span></span> <span data-ttu-id="1770b-263">既定値は、リモートコンピューター上のモジュール検出 WMI プロバイダーのリソース URI です。</span><span class="sxs-lookup"><span data-stu-id="1770b-263">The default value is the resource URI of the Module Discovery WMI provider on the remote computer.</span></span>

<span data-ttu-id="1770b-264">Windows オペレーティングシステムを実行していないコンピューターやデバイスから CIM モジュールをインポートするには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1770b-264">Use this parameter to import CIM modules from computers and devices that aren't running a Windows operating system.</span></span>

<span data-ttu-id="1770b-265">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1770b-265">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="1770b-266">-CimSession</span><span class="sxs-lookup"><span data-stu-id="1770b-266">-CimSession</span></span>

<span data-ttu-id="1770b-267">リモート コンピューター上の CIM セッションを指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-267">Specifies a CIM session on the remote computer.</span></span> <span data-ttu-id="1770b-268">CIM セッションを含む変数、または [CimSession](../CimCmdlets/Get-CimSession.md) コマンドなどの cim セッションを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="1770b-268">Enter a variable that contains the CIM session or a command that gets the CIM session, such as a [Get-CimSession](../CimCmdlets/Get-CimSession.md) command.</span></span>

<span data-ttu-id="1770b-269">`Import-Module` CIM セッション接続を使用して、リモートコンピューターから現在のセッションにモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-269">`Import-Module` uses the CIM session connection to import modules from the remote computer into the current session.</span></span> <span data-ttu-id="1770b-270">現在のセッションでインポートされたモジュールのコマンドを使用すると、コマンドはリモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-270">When you use the commands from the imported module in the current session, the commands run on the remote computer.</span></span>

<span data-ttu-id="1770b-271">このパラメーターを使用して、Windows オペレーティングシステムを実行していないコンピューターやデバイス、PowerShell を搭載しているが PowerShell リモート処理が有効になっていない Windows コンピューターからモジュールをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="1770b-271">You can use this parameter to import modules from computers and devices that aren't running the Windows operating system, and Windows computers that have PowerShell, but don't have PowerShell remoting enabled.</span></span>

<span data-ttu-id="1770b-272">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1770b-272">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="1770b-273">-コマンドレット</span><span class="sxs-lookup"><span data-stu-id="1770b-273">-Cmdlet</span></span>

<span data-ttu-id="1770b-274">このコマンドレットがモジュールから現在のセッションにインポートするコマンドレットの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-274">Specifies an array of cmdlets that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="1770b-275">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1770b-275">Wildcard characters are permitted.</span></span>

<span data-ttu-id="1770b-276">一部のモジュールは、モジュールをインポートすると、選択されたコマンドレットをセッションに自動的にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-276">Some modules automatically export selected cmdlets into your session when you import the module.</span></span>
<span data-ttu-id="1770b-277">このパラメーターを使用すると、エクスポートされたコマンドレットの中から選択できます。</span><span class="sxs-lookup"><span data-stu-id="1770b-277">This parameter lets you select from among the exported cmdlets.</span></span>

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

### <span data-ttu-id="1770b-278">-DisableNameChecking</span><span class="sxs-lookup"><span data-stu-id="1770b-278">-DisableNameChecking</span></span>

<span data-ttu-id="1770b-279">このコマンドレットが、許可されていない動詞または禁止された文字を含んでいる名前を持つコマンドレットまたは関数をインポートしたときに警告するメッセージを抑制することを示します。</span><span class="sxs-lookup"><span data-stu-id="1770b-279">Indicates that this cmdlet suppresses the message that warns you when you import a cmdlet or function whose name includes an unapproved verb or a prohibited character.</span></span>

<span data-ttu-id="1770b-280">既定では、インポートしたモジュールによって、名前に許可されていない動詞を持つコマンドレットまたは関数がエクスポートされると、PowerShell によって次の警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-280">By default, when a module that you import exports cmdlets or functions that have unapproved verbs in their names, PowerShell displays the following warning message:</span></span>

> <span data-ttu-id="1770b-281">警告: インポートされたコマンド名には、検出できない可能性がある未承認の動詞が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1770b-281">WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="1770b-282">詳細については Verbose パラメーターを使用するか、「Get-Verb」と入力して承認されている動詞の一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1770b-282">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs.</span></span>

<span data-ttu-id="1770b-283">このメッセージは、単なる警告です。</span><span class="sxs-lookup"><span data-stu-id="1770b-283">This message is only a warning.</span></span> <span data-ttu-id="1770b-284">実際には、非準拠のコマンドを含む、すべてのモジュールがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="1770b-284">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="1770b-285">モジュール ユーザーにメッセージが表示されますが、名前付けの問題はモジュール作成者が解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1770b-285">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

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

### <span data-ttu-id="1770b-286">-Force</span><span class="sxs-lookup"><span data-stu-id="1770b-286">-Force</span></span>

<span data-ttu-id="1770b-287">このパラメーターを指定すると、現在のモジュールの上にモジュールが読み込まれるか、再度読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="1770b-287">This parameter causes a module to be loaded, or reloaded, over top of the current one.</span></span>

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

### <span data-ttu-id="1770b-288">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="1770b-288">-FullyQualifiedName</span></span>

<span data-ttu-id="1770b-289">モジュールの完全修飾名をハッシュテーブルとして指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-289">Specifies the fully qualified name of the module as a hash table.</span></span> <span data-ttu-id="1770b-290">値には、文字列とハッシュテーブルの組み合わせを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1770b-290">The value can be a combination of strings and hash tables.</span></span> <span data-ttu-id="1770b-291">ハッシュテーブルには、次のキーがあります。</span><span class="sxs-lookup"><span data-stu-id="1770b-291">The hash table has the following keys.</span></span>

- <span data-ttu-id="1770b-292">`ModuleName` - **必須** モジュール名を指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-292">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="1770b-293">`GUID` - **省略可能** モジュールの GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-293">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="1770b-294">以下の3つのキーのいずれかを指定する **必要** もあります。</span><span class="sxs-lookup"><span data-stu-id="1770b-294">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="1770b-295">これらのキーを一緒に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1770b-295">These keys can't be used together.</span></span>
  - <span data-ttu-id="1770b-296">`ModuleVersion` -モジュールの許容される最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-296">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="1770b-297">`RequiredVersion` -モジュールの正確な必須バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-297">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="1770b-298">`MaximumVersion` -モジュールの許容される最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-298">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

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

### <span data-ttu-id="1770b-299">-関数</span><span class="sxs-lookup"><span data-stu-id="1770b-299">-Function</span></span>

<span data-ttu-id="1770b-300">このコマンドレットがモジュールから現在のセッションにインポートする関数の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-300">Specifies an array of functions that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="1770b-301">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1770b-301">Wildcard characters are permitted.</span></span> <span data-ttu-id="1770b-302">一部のモジュールは、モジュールをインポートすると、選択された関数をセッションに自動的にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-302">Some modules automatically export selected functions into your session when you import the module.</span></span> <span data-ttu-id="1770b-303">このパラメーターを使用すると、エクスポートされた関数の中から選択できます。</span><span class="sxs-lookup"><span data-stu-id="1770b-303">This parameter lets you select from among the exported functions.</span></span>

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

### <span data-ttu-id="1770b-304">-グローバル</span><span class="sxs-lookup"><span data-stu-id="1770b-304">-Global</span></span>

<span data-ttu-id="1770b-305">このコマンドレットがモジュールをグローバルセッション状態にインポートして、セッションのすべてのコマンドで使用できるようにすることを示します。</span><span class="sxs-lookup"><span data-stu-id="1770b-305">Indicates that this cmdlet imports modules into the global session state so they are available to all commands in the session.</span></span>

<span data-ttu-id="1770b-306">既定では、 `Import-Module` コマンドプロンプト、スクリプトファイル、または scriptblock からコマンドレットを呼び出すと、すべてのコマンドがグローバルセッション状態にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="1770b-306">By default, when `Import-Module` cmdlet is called from the command prompt, script file, or scriptblock, all the commands are imported into the global session state.</span></span>

<span data-ttu-id="1770b-307">別のモジュールから呼び出されると、コマンドレットは、 `Import-Module` モジュール内のコマンド (入れ子になったモジュールのコマンドを含む) を呼び出し元のモジュールのセッション状態にインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-307">When invoked from another module, `Import-Module` cmdlet imports the commands in a module, including commands from nested modules, into the calling module's session state.</span></span>

> [!TIP]
> <span data-ttu-id="1770b-308">モジュール内からを呼び出すことは避けてください `Import-Module` 。</span><span class="sxs-lookup"><span data-stu-id="1770b-308">You should avoid calling `Import-Module` from within a module.</span></span> <span data-ttu-id="1770b-309">代わりに、親モジュールのマニフェストで入れ子になったモジュールとしてターゲットモジュールを宣言します。</span><span class="sxs-lookup"><span data-stu-id="1770b-309">Instead, declare the target module as a nested module in the parent module's manifest.</span></span> <span data-ttu-id="1770b-310">入れ子になったモジュールを宣言すると、依存関係の発見可能性が向上します。</span><span class="sxs-lookup"><span data-stu-id="1770b-310">Declaring nested modules improves the discoverability of dependencies.</span></span>

<span data-ttu-id="1770b-311">**Global** パラメーターは、値が **Global** である **Scope** パラメーターと同じ効果が得られます。</span><span class="sxs-lookup"><span data-stu-id="1770b-311">The **Global** parameter is equivalent to the **Scope** parameter with a value of **Global** .</span></span>

<span data-ttu-id="1770b-312">モジュールによってエクスポートされるコマンドを制限するには、 `Export-ModuleMember` スクリプトモジュールでコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="1770b-312">To restrict the commands that a module exports, use an `Export-ModuleMember` command in the script module.</span></span>

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

### <span data-ttu-id="1770b-313">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="1770b-313">-MaximumVersion</span></span>

<span data-ttu-id="1770b-314">最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-314">Specifies a maximum version.</span></span> <span data-ttu-id="1770b-315">このコマンドレットは、指定した値以下のバージョンのモジュールのみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-315">This cmdlet imports only a version of the module that is less than or equal to the specified value.</span></span> <span data-ttu-id="1770b-316">バージョンが修飾していない場合は、 `Import-Module` エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="1770b-316">If no version qualifies, `Import-Module` returns an error.</span></span>

```yaml
Type: System.String
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1770b-317">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="1770b-317">-MinimumVersion</span></span>

<span data-ttu-id="1770b-318">最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-318">Specifies a minimum version.</span></span> <span data-ttu-id="1770b-319">このコマンドレットは、指定した値以上のバージョンのモジュールのみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-319">This cmdlet imports only a version of the module that is greater than or equal to the specified value.</span></span> <span data-ttu-id="1770b-320">**MinimumVersion** パラメーター名またはそのエイリアスである **Version** を使用します。</span><span class="sxs-lookup"><span data-stu-id="1770b-320">Use the **MinimumVersion** parameter name or its alias, **Version** .</span></span> <span data-ttu-id="1770b-321">バージョンが修飾されていない場合、は `Import-Module` エラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="1770b-321">If no version qualifies, `Import-Module` generates an error.</span></span>

<span data-ttu-id="1770b-322">正確なバージョンを指定するには、 **RequiredVersion** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1770b-322">To specify an exact version, use the **RequiredVersion** parameter.</span></span> <span data-ttu-id="1770b-323">また、 **#Requires** キーワードの **Module** パラメーターと **Version** パラメーターを使用して、スクリプト内でモジュールの特定のバージョンを要求することもできます。</span><span class="sxs-lookup"><span data-stu-id="1770b-323">You can also use the **Module** and **Version** parameters of the **#Requires** keyword to require a specific version of a module in a script.</span></span>

<span data-ttu-id="1770b-324">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1770b-324">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases: Version

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1770b-325">-ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="1770b-325">-ModuleInfo</span></span>

<span data-ttu-id="1770b-326">インポートするモジュールオブジェクトの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-326">Specifies an array of module objects to import.</span></span> <span data-ttu-id="1770b-327">モジュールオブジェクトを含む変数、またはモジュールオブジェクトを取得するコマンド (など) を入力し `Get-Module -ListAvailable` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-327">Enter a variable that contains the module objects, or a command that gets the module objects, such as the following command: `Get-Module -ListAvailable`.</span></span> <span data-ttu-id="1770b-328">パイプを使用してモジュールオブジェクトをにパイプすることもでき `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-328">You can also pipe module objects to `Import-Module`.</span></span>

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

### <span data-ttu-id="1770b-329">-Name</span><span class="sxs-lookup"><span data-stu-id="1770b-329">-Name</span></span>

<span data-ttu-id="1770b-330">インポートするモジュールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-330">Specifies the names of the modules to import.</span></span> <span data-ttu-id="1770b-331">モジュールの名前、または、、、またはファイルなどのモジュール内のファイルの名前を入力し `.psd1` `.psm1` `.dll` `.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-331">Enter the name of the module or the name of a file in the module, such as a `.psd1`, `.psm1`, `.dll`, or `.ps1` file.</span></span> <span data-ttu-id="1770b-332">ファイル パスは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="1770b-332">File paths are optional.</span></span> <span data-ttu-id="1770b-333">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="1770b-333">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="1770b-334">パイプを使用してモジュール名とファイル名をにパイプすることもでき `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-334">You can also pipe module names and filenames to `Import-Module`.</span></span>

<span data-ttu-id="1770b-335">パスを省略した場合、は `Import-Module` 環境変数に保存されているパスでモジュールを検索し `$env:PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-335">If you omit a path, `Import-Module` looks for the module in the paths saved in the `$env:PSModulePath` environment variable.</span></span>

<span data-ttu-id="1770b-336">可能な限り、モジュール名のみを指定してください。</span><span class="sxs-lookup"><span data-stu-id="1770b-336">Specify only the module name whenever possible.</span></span> <span data-ttu-id="1770b-337">ファイル名を指定した場合は、そのファイルに実装されているメンバーのみがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="1770b-337">When you specify a file name, only the members that are implemented in that file are imported.</span></span> <span data-ttu-id="1770b-338">モジュールに他のファイルが含まれている場合は、インポートされないため、モジュールの重要なメンバーが不足している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1770b-338">If the module contains other files, they aren't imported, and you might be missing important members of the module.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="1770b-339">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="1770b-339">-NoClobber</span></span>

<span data-ttu-id="1770b-340">現在のセッションの既存のコマンドと同じ名前のコマンドがインポートされないようにします。</span><span class="sxs-lookup"><span data-stu-id="1770b-340">Prevents importing commands that have the same names as existing commands in the current session.</span></span> <span data-ttu-id="1770b-341">既定では、 `Import-Module` エクスポートされたすべてのモジュールコマンドがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="1770b-341">By default, `Import-Module` imports all exported module commands.</span></span>

<span data-ttu-id="1770b-342">同じ名前を持つコマンドは、セッション内のコマンドを非表示にしたり置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="1770b-342">Commands that have the same names can hide or replace commands in the session.</span></span> <span data-ttu-id="1770b-343">セッションでのコマンド名の競合を回避するには、 **Prefix** パラメーターまたは **NoClobber** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1770b-343">To avoid command name conflicts in a session, use the **Prefix** or **NoClobber** parameters.</span></span> <span data-ttu-id="1770b-344">名前の競合およびコマンドの優先順位の詳細については、[about_Modules](about/about_Modules.md) の「モジュールと名前の競合」および [about_Command_Precedence](about/about_Command_Precedence.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1770b-344">For more information about name conflicts and command precedence, see "Modules and Name Conflicts" in [about_Modules](about/about_Modules.md) and [about_Command_Precedence](about/about_Command_Precedence.md).</span></span>

<span data-ttu-id="1770b-345">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1770b-345">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="1770b-346">-PassThru</span><span class="sxs-lookup"><span data-stu-id="1770b-346">-PassThru</span></span>

<span data-ttu-id="1770b-347">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="1770b-347">Returns an object representing the item with which you're working.</span></span> <span data-ttu-id="1770b-348">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="1770b-348">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="1770b-349">-Prefix</span><span class="sxs-lookup"><span data-stu-id="1770b-349">-Prefix</span></span>

<span data-ttu-id="1770b-350">インポートされたモジュールメンバーの名前の名詞にこのコマンドレットが追加するプレフィックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-350">Specifies a prefix that this cmdlet adds to the nouns in the names of imported module members.</span></span>

<span data-ttu-id="1770b-351">セッションに同じ名前の別のメンバーが存在する場合に発生する名前の競合を回避するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1770b-351">Use this parameter to avoid name conflicts that might occur when different members in the session have the same name.</span></span> <span data-ttu-id="1770b-352">このパラメーターによってモジュールが変更されることはなく、モジュールが自身で使用するためにインポートするファイルには影響しません。</span><span class="sxs-lookup"><span data-stu-id="1770b-352">This parameter does not change the module, and it does not affect files that the module imports for its own use.</span></span> <span data-ttu-id="1770b-353">これらは、入れ子になったモジュールと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="1770b-353">These are known as nested modules.</span></span> <span data-ttu-id="1770b-354">このコマンドレットは、現在のセッションのメンバーの名前にのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="1770b-354">This cmdlet affects only the names of members in the current session.</span></span>

<span data-ttu-id="1770b-355">たとえば、プレフィックス UTC を指定してからコマンドレットをインポートした場合、 `Get-Date` このコマンドレットはセッションではとして認識され、 `Get-UTCDate` 元のコマンドレットと混同されることはありません `Get-Date` 。</span><span class="sxs-lookup"><span data-stu-id="1770b-355">For example, if you specify the prefix UTC and then import a `Get-Date` cmdlet, the cmdlet is known in the session as `Get-UTCDate`, and it is not confused with the original `Get-Date` cmdlet.</span></span>

<span data-ttu-id="1770b-356">このパラメーターの値は、モジュールの **DefaultCommandPrefix** プロパティ (既定のプレフィックスを指定する) よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-356">The value of this parameter takes precedence over the **DefaultCommandPrefix** property of the module, which specifies the default prefix.</span></span>

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

### <span data-ttu-id="1770b-357">-PSSession</span><span class="sxs-lookup"><span data-stu-id="1770b-357">-PSSession</span></span>

<span data-ttu-id="1770b-358">このコマンドレットが現在のセッションにモジュールをインポートするときに使用する、PowerShell のユーザー管理セッション ( **PSSession** ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-358">Specifies a PowerShell user-managed session ( **PSSession** ) from which this cmdlet imports modules into the current session.</span></span> <span data-ttu-id="1770b-359">**Pssession** を含む変数、またはコマンドなどの **pssession** を取得するコマンドを入力し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-359">Enter a variable that contains a **PSSession** or a command that gets a **PSSession** , such as a `Get-PSSession` command.</span></span>

<span data-ttu-id="1770b-360">別のセッションから現在のセッションにモジュールをインポートする際、ローカル モジュールのコマンドレットを使用するのと同じように、モジュールのコマンドレットを現在のセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1770b-360">When you import a module from a different session into the current session, you can use the cmdlets from the module in the current session, just as you would use cmdlets from a local module.</span></span> <span data-ttu-id="1770b-361">リモートコマンドレットを使用するコマンドはリモートセッションで実行されますが、リモート処理の詳細は PowerShell によってバックグラウンドで管理されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-361">Commands that use the remote cmdlets run in the remote session, but the remoting details are managed in the background by PowerShell.</span></span>

<span data-ttu-id="1770b-362">このパラメーターは、PowerShell の暗黙的なリモート処理機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="1770b-362">This parameter uses the Implicit Remoting feature of PowerShell.</span></span> <span data-ttu-id="1770b-363">これは、コマンドレットを使用して、セッションから特定のモジュールをインポートすることと同じです `Import-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="1770b-363">It is equivalent to using the `Import-PSSession` cmdlet to import particular modules from a session.</span></span>

<span data-ttu-id="1770b-364">`Import-Module` 別のセッションから PowerShell コアモジュールをインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1770b-364">`Import-Module` cannot import PowerShell Core modules from another session.</span></span> <span data-ttu-id="1770b-365">PowerShell コアモジュールには、Microsoft. PowerShell で始まる名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="1770b-365">The PowerShell Core modules have names that begin with Microsoft.PowerShell.</span></span>

<span data-ttu-id="1770b-366">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1770b-366">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="1770b-367">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="1770b-367">-RequiredVersion</span></span>

<span data-ttu-id="1770b-368">このコマンドレットによってインポートされるモジュールのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-368">Specifies a version of the module that this cmdlet imports.</span></span> <span data-ttu-id="1770b-369">バージョンがインストールされていない場合は、によって `Import-Module` エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-369">If the version is not installed, `Import-Module` generates an error.</span></span>

<span data-ttu-id="1770b-370">既定では、は `Import-Module` バージョン番号をチェックせずにモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-370">By default, `Import-Module` imports the module without checking the version number.</span></span>

<span data-ttu-id="1770b-371">最小バージョンを指定するには、 **MinimumVersion** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1770b-371">To specify a minimum version, use the **MinimumVersion** parameter.</span></span> <span data-ttu-id="1770b-372">また、 **#Requires** キーワードの **Module** パラメーターと **Version** パラメーターを使用して、スクリプト内でモジュールの特定のバージョンを要求することもできます。</span><span class="sxs-lookup"><span data-stu-id="1770b-372">You can also use the **Module** and **Version** parameters of the **#Requires** keyword to require a specific version of a module in a script.</span></span>

<span data-ttu-id="1770b-373">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1770b-373">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="1770b-374">Windows オペレーティングシステムの既存のリリースに含まれているモジュールをインポートするために、 **RequiredVersion** を使用するスクリプトは、windows オペレーティングシステムの将来のリリースでは自動的には実行されません。</span><span class="sxs-lookup"><span data-stu-id="1770b-374">Scripts that use **RequiredVersion** to import modules that are included with existing releases of the Windows operating system don't automatically run in future releases of the Windows operating system.</span></span> <span data-ttu-id="1770b-375">これは、Windows オペレーティングシステムの将来のリリースにおける PowerShell モジュールのバージョン番号が、Windows オペレーティングシステムの既存のリリースにおけるモジュールのバージョン番号よりも大きいためです。</span><span class="sxs-lookup"><span data-stu-id="1770b-375">This is because PowerShell module version numbers in future releases of the Windows operating system are higher than module version numbers in existing releases of the Windows operating system.</span></span>

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1770b-376">-スコープ</span><span class="sxs-lookup"><span data-stu-id="1770b-376">-Scope</span></span>

<span data-ttu-id="1770b-377">このコマンドレットがモジュールをインポートするスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-377">Specifies a scope into which this cmdlet imports the module.</span></span>

<span data-ttu-id="1770b-378">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1770b-378">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1770b-379">**グローバル** 。</span><span class="sxs-lookup"><span data-stu-id="1770b-379">**Global** .</span></span> <span data-ttu-id="1770b-380">セッション内のすべてのコマンドに使用できます。</span><span class="sxs-lookup"><span data-stu-id="1770b-380">Available to all commands in the session.</span></span> <span data-ttu-id="1770b-381">**Global** パラメーターと同じ効果が得られます。</span><span class="sxs-lookup"><span data-stu-id="1770b-381">Equivalent to the **Global** parameter.</span></span>
- <span data-ttu-id="1770b-382">**ローカル** 。</span><span class="sxs-lookup"><span data-stu-id="1770b-382">**Local** .</span></span> <span data-ttu-id="1770b-383">現在のスコープでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1770b-383">Available only in the current scope.</span></span>

<span data-ttu-id="1770b-384">既定では、 `Import-Module` コマンドプロンプト、スクリプトファイル、または scriptblock からコマンドレットを呼び出すと、すべてのコマンドがグローバルセッション状態にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="1770b-384">By default, when `Import-Module` cmdlet is called from the command prompt, script file, or scriptblock, all the commands are imported into the global session state.</span></span> <span data-ttu-id="1770b-385">**-Scope** パラメーターを **Local** の値と共に使用すると、モジュールコンテンツをスクリプトまたは scriptblock スコープにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="1770b-385">You can use the **-Scope** parameter with the value of **Local** to import module content into the script or scriptblock scope.</span></span>

<span data-ttu-id="1770b-386">別のモジュールから呼び出された場合、コマンドレットは、 `Import-Module` 入れ子になったモジュールのコマンドを含むモジュール内のコマンドを呼び出し元のセッション状態にインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-386">When invoked from another module, `Import-Module` cmdlet imports the commands in a module, including commands from nested modules, into the caller's session state.</span></span> <span data-ttu-id="1770b-387">またはを指定する `-Scope Global` と `-Global` 、このコマンドレットによってモジュールがグローバルセッション状態にインポートされ、セッションのすべてのコマンドで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1770b-387">Specifying `-Scope Global` or `-Global` indicates that this cmdlet imports modules into the global session state so they are available to all commands in the session.</span></span>

<span data-ttu-id="1770b-388">**Global** パラメーターは、global 型の値を持つ **Scope** パラメーターに相当します。</span><span class="sxs-lookup"><span data-stu-id="1770b-388">The **Global** parameter is equivalent to the **Scope** parameter with a value of Global.</span></span>

<span data-ttu-id="1770b-389">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1770b-389">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="1770b-390">-Variable</span><span class="sxs-lookup"><span data-stu-id="1770b-390">-Variable</span></span>

<span data-ttu-id="1770b-391">このコマンドレットがモジュールから現在のセッションにインポートする変数の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-391">Specifies an array of variables that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="1770b-392">変数のリストを入力します。</span><span class="sxs-lookup"><span data-stu-id="1770b-392">Enter a list of variables.</span></span> <span data-ttu-id="1770b-393">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1770b-393">Wildcard characters are permitted.</span></span>

<span data-ttu-id="1770b-394">一部のモジュールは、モジュールをインポートすると、選択された変数をセッションに自動的にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-394">Some modules automatically export selected variables into your session when you import the module.</span></span>
<span data-ttu-id="1770b-395">このパラメーターを使用すると、エクスポートされた変数の中から選択できます。</span><span class="sxs-lookup"><span data-stu-id="1770b-395">This parameter lets you select from among the exported variables.</span></span>

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

### <span data-ttu-id="1770b-396">-SkipEditionCheck</span><span class="sxs-lookup"><span data-stu-id="1770b-396">-SkipEditionCheck</span></span>

<span data-ttu-id="1770b-397">フィールドのチェックをスキップし `CompatiblePSEditions` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-397">Skips the check on the `CompatiblePSEditions` field.</span></span>

<span data-ttu-id="1770b-398">モジュールが `"$($env:windir)\System32\WindowsPowerShell\v1.0\Modules"` マニフェストフィールドにを指定していない場合に、モジュールディレクトリから PowerShell Core にモジュールを読み込むことができ `Core` `CompatiblePSEditions` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-398">Allows loading a module from the `"$($env:windir)\System32\WindowsPowerShell\v1.0\Modules"` module directory into PowerShell Core when that module does not specify `Core` in the `CompatiblePSEditions` manifest field.</span></span>

<span data-ttu-id="1770b-399">別のパスからモジュールをインポートする場合、このスイッチは何も実行しません。これは、チェックが実行されないためです。</span><span class="sxs-lookup"><span data-stu-id="1770b-399">When importing a module from another path, this switch does nothing, since the check is not performed.</span></span> <span data-ttu-id="1770b-400">Linux と macOS では、このスイッチは何も行いません。</span><span class="sxs-lookup"><span data-stu-id="1770b-400">On Linux and macOS, this switch does nothing.</span></span>

<span data-ttu-id="1770b-401">詳細については、「 [about_PowerShell_Editions](About/about_PowerShell_Editions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1770b-401">For more information, see [about_PowerShell_Editions](About/about_PowerShell_Editions.md).</span></span>

> [!WARNING]
> <span data-ttu-id="1770b-402">`Import-Module -SkipEditionCheck` でも、モジュールのインポートに失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1770b-402">`Import-Module -SkipEditionCheck` is still likely to fail to import a module.</span></span> <span data-ttu-id="1770b-403">成功した場合でも、モジュールからコマンドを呼び出すと、互換性のない API を使用しようとすると、後でエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1770b-403">Even if it does succeed, invoking a command from the module may later fail when it tries to use an incompatible API.</span></span>

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

### <span data-ttu-id="1770b-404">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1770b-404">CommonParameters</span></span>

<span data-ttu-id="1770b-405">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="1770b-405">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1770b-406">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1770b-406">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1770b-407">入力</span><span class="sxs-lookup"><span data-stu-id="1770b-407">INPUTS</span></span>

### <span data-ttu-id="1770b-408">System.string、PSModuleInfo、システムのアセンブリを指定します。</span><span class="sxs-lookup"><span data-stu-id="1770b-408">System.String, System.Management.Automation.PSModuleInfo, System.Reflection.Assembly</span></span>

<span data-ttu-id="1770b-409">パイプを使用して、モジュール名、モジュールオブジェクト、またはアセンブリオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="1770b-409">You can pipe a module name, module object, or assembly object to this cmdlet.</span></span>

## <span data-ttu-id="1770b-410">出力</span><span class="sxs-lookup"><span data-stu-id="1770b-410">OUTPUTS</span></span>

### <span data-ttu-id="1770b-411">なし、PSModuleInfo、またはシステムの管理.......</span><span class="sxs-lookup"><span data-stu-id="1770b-411">None, System.Management.Automation.PSModuleInfo, or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="1770b-412">既定で `Import-Module` は、は出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="1770b-412">By default, `Import-Module` does not generate any output.</span></span> <span data-ttu-id="1770b-413">**PassThru** パラメーターを指定すると、このコマンドレットは、モジュールを表す **PSModuleInfo** オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="1770b-413">If you specify the **PassThru** parameter, the cmdlet generates a **System.Management.Automation.PSModuleInfo** object that represents the module.</span></span> <span data-ttu-id="1770b-414">**Ascustomobject** いうパラメーターを指定すると、 **pscustomobject** オブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-414">If you specify the **AsCustomObject** parameter, it generates a **PSCustomObject** object.</span></span>

## <span data-ttu-id="1770b-415">注</span><span class="sxs-lookup"><span data-stu-id="1770b-415">NOTES</span></span>

- <span data-ttu-id="1770b-416">モジュールをインポートする前に、モジュールがローカルコンピューターにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1770b-416">Before you can import a module, the module must be installed on the local computer.</span></span> <span data-ttu-id="1770b-417">つまり、モジュールディレクトリは、ローカルコンピューターからアクセスできるディレクトリにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1770b-417">That is, the module directory must be copied to a directory that is accessible to your local computer.</span></span> <span data-ttu-id="1770b-418">詳細については、「 [about_Modules](About/about_Modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1770b-418">For more information, see [about_Modules](About/about_Modules.md).</span></span>

  <span data-ttu-id="1770b-419">また、 **PSSession** パラメーターと **CIMSession** パラメーターを使用すれば、リモート コンピューターにインストールされているモジュールをインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1770b-419">You can also use the **PSSession** and **CIMSession** parameters to import modules that are installed on remote computers.</span></span> <span data-ttu-id="1770b-420">ただし、これらのモジュールのコマンドレットを使用するコマンドは、リモートコンピューター上のリモートセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-420">However, commands that use the cmdlets in these modules run in the remote session on the remote computer.</span></span>

- <span data-ttu-id="1770b-421">セッションに同じ名前と同じ種類のメンバーをインポートする場合、PowerShell は、既定で最後にインポートされたメンバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="1770b-421">If you import members with the same name and the same type into your session, PowerShell uses the member imported last by default.</span></span> <span data-ttu-id="1770b-422">変数と別名は置き換えられ、元の変数にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="1770b-422">Variables and aliases are replaced, and the originals aren't accessible.</span></span> <span data-ttu-id="1770b-423">関数、コマンドレット、およびプロバイダーは、新しいメンバーによって単純にシャドウされます。</span><span class="sxs-lookup"><span data-stu-id="1770b-423">Functions, cmdlets, and providers are merely shadowed by the new members.</span></span> <span data-ttu-id="1770b-424">これらのコマンド名には、スナップイン、モジュール、または関数パスの名前を指定することによってアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1770b-424">They can be accessed by qualifying the command name with the name of its snap-in, module, or function path.</span></span>

- <span data-ttu-id="1770b-425">モジュールからインポートされたコマンドの書式設定データを更新するには、 `Update-FormatData` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1770b-425">To update the formatting data for commands that have been imported from a module, use the `Update-FormatData` cmdlet.</span></span> <span data-ttu-id="1770b-426">`Update-FormatData` では、モジュールからインポートされたセッションのコマンドの書式設定データも更新されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-426">`Update-FormatData` also updates the formatting data for commands in the session that were imported from modules.</span></span> <span data-ttu-id="1770b-427">モジュールのフォーマットファイルが変更された場合は、コマンドを実行して、インポートした `Update-FormatData` コマンドの書式設定データを更新できます。</span><span class="sxs-lookup"><span data-stu-id="1770b-427">If the formatting file for a module changes, you can run an `Update-FormatData` command to update the formatting data for imported commands.</span></span> <span data-ttu-id="1770b-428">モジュールをもう一度インポートする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1770b-428">You don't need to import the module again.</span></span>

- <span data-ttu-id="1770b-429">Windows PowerShell 3.0 以降では、PowerShell でインストールされるコアコマンドはモジュールにパッケージ化されています。</span><span class="sxs-lookup"><span data-stu-id="1770b-429">Starting in Windows PowerShell 3.0, the core commands that are installed with PowerShell are packaged in modules.</span></span> <span data-ttu-id="1770b-430">Windows PowerShell 2.0、およびそれ以降のバージョンの PowerShell で古いスタイルのセッションを作成するホストプログラムでは、コアコマンドはスナップイン ( **PSSnapins** ) にパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-430">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of PowerShell, the core commands are packaged in snap-ins ( **PSSnapins** ).</span></span> <span data-ttu-id="1770b-431">例外は、常にスナップインである、 **PowerShell です** 。</span><span class="sxs-lookup"><span data-stu-id="1770b-431">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="1770b-432">また、コマンドレットによって開始されるようなリモートセッション `New-PSSession` は、コアスナップインを含む古いスタイルのセッションです。</span><span class="sxs-lookup"><span data-stu-id="1770b-432">Also, remote sessions, such as those started by the `New-PSSession` cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="1770b-433">コアモジュールで新しいスタイルのセッションを作成する **CreateDefault2** メソッドの詳細については、 [CreateDefault2 メソッド](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1770b-433">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see the [CreateDefault2 Method](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).</span></span>

- <span data-ttu-id="1770b-434">`Import-Module` 別のセッションから PowerShell コアモジュールをインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1770b-434">`Import-Module` cannot import PowerShell Core modules from another session.</span></span> <span data-ttu-id="1770b-435">PowerShell コアモジュールには、で始まる名前が付いてい `Microsoft.PowerShell` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-435">The PowerShell Core modules have names that begin with `Microsoft.PowerShell`.</span></span>

- <span data-ttu-id="1770b-436">Windows PowerShell 2.0 では、モジュールオブジェクトの一部のプロパティ値 ( **ExportedCmdlets** および **nestedmodules** プロパティ値など) は、モジュールがインポートされ、 **PassThru** パラメーターが返すモジュールオブジェクトで使用できなくなるまで、設定されませんでした。</span><span class="sxs-lookup"><span data-stu-id="1770b-436">In Windows PowerShell 2.0, some of the property values of the module object, such as the **ExportedCmdlets** and **NestedModules** property values, were not populated until the module was imported and were not available on the module object that the **PassThru** parameter returns.</span></span> <span data-ttu-id="1770b-437">Windows PowerShell 3.0 では、すべてのモジュールプロパティ値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-437">In Windows PowerShell 3.0, all module property values are populated.</span></span>

- <span data-ttu-id="1770b-438">Windows PowerShell 3.0 と互換性のない混合モードアセンブリを含むモジュールをインポートしようとすると、は `Import-Module` 次のようなエラーメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="1770b-438">If you attempt to import a module that contains mixed-mode assemblies that aren't compatible with Windows PowerShell 3.0, `Import-Module` returns an error message like the following one.</span></span>

  > <span data-ttu-id="1770b-439">Import-Module: 混合モードのアセンブリは、ランタイムのバージョン ' v v2.0.50727 ' に対してビルドされており、追加の構成情報がないと、4.0 ランタイムに読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="1770b-439">Import-Module : Mixed mode assembly is built against version 'v2.0.50727' of the runtime and cannot be loaded in the 4.0 runtime without additional configuration information.</span></span>

  <span data-ttu-id="1770b-440">このエラーは、Windows PowerShell 2.0 用に設計されたモジュールに、少なくとも1つの混合モジュールアセンブリ (C++ や C# などのマネージコードと非マネージコードの両方を含むアセンブリ) が含まれている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="1770b-440">This error occurs when a module that is designed for Windows PowerShell 2.0 contains at least one mixed-module assembly, that is, an assembly that includes both managed and non-managed code, such as C++ and C#.</span></span>

  <span data-ttu-id="1770b-441">混合モードアセンブリを含むモジュールをインポートするには、次のコマンドを使用して Windows PowerShell 2.0 を起動し、コマンドを再試行し `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="1770b-441">To import a module that contains mixed-mode assemblies, start Windows PowerShell 2.0 by using the following command, and then try the `Import-Module` command again.</span></span>

  `PowerShell.exe -Version 2.0`

- <span data-ttu-id="1770b-442">CIM セッション機能を使用するには、リモート コンピューターにおいて、WS-Management リモート処理と Common Information Model (CIM) 標準の Microsoft 実装である Windows Management Instrumentation (WMI) が必要です。</span><span class="sxs-lookup"><span data-stu-id="1770b-442">To use the CIM session feature, the remote computer must have WS-Management remoting and Windows Management Instrumentation (WMI), which is the Microsoft implementation of the Common Information Model (CIM) standard.</span></span> <span data-ttu-id="1770b-443">さらに、モジュール検出用の WMI プロバイダーまたは同じ基本機能を備えた代替 CIM プロバイダーもコンピューターに必要です。</span><span class="sxs-lookup"><span data-stu-id="1770b-443">The computer must also have the Module Discovery WMI provider or an alternate CIM provider that has the same basic features.</span></span>

  <span data-ttu-id="1770b-444">CIM セッション機能は、Windows オペレーティングシステムを実行していないコンピューターと PowerShell を搭載している Windows コンピューターで使用できますが、PowerShell リモート処理は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="1770b-444">You can use the CIM session feature on computers that aren't running a Windows operating system and on Windows computers that have PowerShell, but don't have PowerShell remoting enabled.</span></span>

  <span data-ttu-id="1770b-445">また、CIM パラメーターを使用して、ローカルコンピューターを含め、PowerShell リモート処理が有効になっているコンピューターから CIM モジュールを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="1770b-445">You can also use the CIM parameters to get CIM modules from computers that have PowerShell remoting enabled, including the local computer.</span></span> <span data-ttu-id="1770b-446">ローカルコンピューターに CIM セッションを作成すると、PowerShell は WMI ではなく DCOM を使用してセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="1770b-446">When you create a CIM session on the local computer, PowerShell uses DCOM, instead of WMI, to create the session.</span></span>

- <span data-ttu-id="1770b-447">既定では、は、 `Import-Module` 子孫スコープから呼び出された場合でも、グローバルスコープ内のモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="1770b-447">By default, `Import-Module` imports modules in the global scope even when called from a descendant scope.</span></span> <span data-ttu-id="1770b-448">最上位レベルのスコープとすべての子孫のスコープは、モジュールのエクスポートされた要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1770b-448">The top-level scope and all descendant scopes have access to the module's exported elements.</span></span>

  <span data-ttu-id="1770b-449">子孫スコープでは、 `-Scope Local` そのスコープとそのすべての子孫スコープへのインポートが制限されます。</span><span class="sxs-lookup"><span data-stu-id="1770b-449">In a descendant scope, `-Scope Local` limits the import to that scope and all its descendant scopes.</span></span> <span data-ttu-id="1770b-450">親スコープでは、インポートされたメンバーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="1770b-450">Parent scopes then do not see the imported members.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1770b-451">`Get-Module` 現在のセッションで読み込まれたすべてのモジュールを表示します。</span><span class="sxs-lookup"><span data-stu-id="1770b-451">`Get-Module` shows all modules loaded in the current session.</span></span> <span data-ttu-id="1770b-452">これには、子孫スコープにローカルに読み込まれたモジュールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1770b-452">This includes modules loaded locally in a descendant scope.</span></span> <span data-ttu-id="1770b-453">`Get-Command -Module modulename`現在のスコープに読み込まれているメンバーを確認するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="1770b-453">Use `Get-Command -Module modulename` to see which members are loaded in the current scope.</span></span>

  <span data-ttu-id="1770b-454">モジュールにクラスと列挙型の定義が含まれている場合は、 `using module` スクリプトの先頭でを使用します。</span><span class="sxs-lookup"><span data-stu-id="1770b-454">If the module includes class and enum definitions, use `using module` at the beginning of your script.</span></span> <span data-ttu-id="1770b-455">これにより、クラスや列挙の定義など、スクリプトがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="1770b-455">This import the scripts, including the class and enum definitions.</span></span> <span data-ttu-id="1770b-456">詳細については、「 [about_Using](About/about_Using.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1770b-456">For more information, see [about_Using](About/about_Using.md).</span></span>

## <span data-ttu-id="1770b-457">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1770b-457">RELATED LINKS</span></span>

[<span data-ttu-id="1770b-458">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="1770b-458">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="1770b-459">Get-Module</span><span class="sxs-lookup"><span data-stu-id="1770b-459">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="1770b-460">New-Module</span><span class="sxs-lookup"><span data-stu-id="1770b-460">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="1770b-461">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="1770b-461">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="1770b-462">about_PowerShell_Editions</span><span class="sxs-lookup"><span data-stu-id="1770b-462">about_PowerShell_Editions</span></span>](About/about_PowerShell_Editions.md)
