---
description: 必須の要素を使用せずにスクリプトを実行しないようにします。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 07/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_requires?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Requires
ms.openlocfilehash: d499499c58f22bff10d712d33fc3a021e4fa6bbb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222579"
---
# <a name="about-requires"></a><span data-ttu-id="58cf8-104">要求について</span><span class="sxs-lookup"><span data-stu-id="58cf8-104">About Requires</span></span>

## <a name="short-description"></a><span data-ttu-id="58cf8-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="58cf8-105">Short description</span></span>
<span data-ttu-id="58cf8-106">必須の要素を使用せずにスクリプトを実行しないようにします。</span><span class="sxs-lookup"><span data-stu-id="58cf8-106">Prevents a script from running without the required elements.</span></span>

## <a name="long-description"></a><span data-ttu-id="58cf8-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="58cf8-107">Long description</span></span>

<span data-ttu-id="58cf8-108">ステートメントは、 `#Requires` PowerShell のバージョン、モジュール (およびバージョン)、スナップイン (およびバージョン)、およびエディションの前提条件が満たされていない限り、スクリプトを実行しないようにします。</span><span class="sxs-lookup"><span data-stu-id="58cf8-108">The `#Requires` statement prevents a script from running unless the PowerShell version, modules (and version), or snap-ins (and version), and edition prerequisites are met.</span></span> <span data-ttu-id="58cf8-109">前提条件が満たされていない場合、PowerShell はスクリプトを実行しません。</span><span class="sxs-lookup"><span data-stu-id="58cf8-109">If the prerequisites aren't met, PowerShell doesn't run the script.</span></span>

### <a name="syntax"></a><span data-ttu-id="58cf8-110">構文</span><span class="sxs-lookup"><span data-stu-id="58cf8-110">Syntax</span></span>

```
#Requires -Assembly { <Path to .dll> | <.NET assembly specification> }
#Requires -Version <N>[.<n>]
#Requires -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -Modules { <Module-Name> | <Hashtable> }
#Requires -PSEdition <PSEdition-Name>
#Requires -ShellId <ShellId> -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -RunAsAdministrator
```

<span data-ttu-id="58cf8-111">構文の詳細については、「 [Scriptrequirements 要件](/dotnet/api/system.management.automation.language.scriptrequirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58cf8-111">For more information about the syntax, see [ScriptRequirements](/dotnet/api/system.management.automation.language.scriptrequirements).</span></span>

### <a name="rules-for-use"></a><span data-ttu-id="58cf8-112">使用するための規則</span><span class="sxs-lookup"><span data-stu-id="58cf8-112">Rules for use</span></span>

<span data-ttu-id="58cf8-113">1つのスクリプトに複数のステートメントを含めることができ `#Requires` ます。</span><span class="sxs-lookup"><span data-stu-id="58cf8-113">A script can include more than one `#Requires` statement.</span></span> <span data-ttu-id="58cf8-114">ステートメントは、 `#Requires` スクリプト内の任意の行に記述できます。</span><span class="sxs-lookup"><span data-stu-id="58cf8-114">The `#Requires` statements can appear on any line in a script.</span></span>

<span data-ttu-id="58cf8-115">ステートメントを `#Requires` 関数内に配置しても、そのスコープは制限されません。</span><span class="sxs-lookup"><span data-stu-id="58cf8-115">Placing a `#Requires` statement inside a function does NOT limit its scope.</span></span> <span data-ttu-id="58cf8-116">`#Requires`スクリプトを実行する前に、すべてのステートメントがグローバルに適用され、満たされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="58cf8-116">All `#Requires` statements are always applied globally, and must be met, before the script can execute.</span></span>

> [!WARNING]
> <span data-ttu-id="58cf8-117">ステートメントは、 `#Requires` スクリプト内のどの行にも記述できますが、スクリプト内のその位置はアプリケーションのシーケンスに影響しません。</span><span class="sxs-lookup"><span data-stu-id="58cf8-117">Even though a `#Requires` statement can appear on any line in a script, its position in a script does not affect the sequence of its application.</span></span> <span data-ttu-id="58cf8-118">スクリプトを実行する前に、ステートメントが示すグローバル状態を `#Requires` 満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="58cf8-118">The global state the `#Requires` statement presents must be met before script execution.</span></span>

<span data-ttu-id="58cf8-119">例:</span><span class="sxs-lookup"><span data-stu-id="58cf8-119">Example:</span></span>

```powershell
Get-Module AzureRM.Netcore | Remove-Module
#Requires -Modules AzureRM.Netcore
```

<span data-ttu-id="58cf8-120">必要なモジュールがステートメントの前に削除されたため、上記のコードが実行されない可能性があり `#Requires` ます。</span><span class="sxs-lookup"><span data-stu-id="58cf8-120">You might think that the above code shouldn't run because the required module was removed before the `#Requires` statement.</span></span> <span data-ttu-id="58cf8-121">ただし、 `#Requires` スクリプトが実行される前に、状態が満たされている必要がありました。</span><span class="sxs-lookup"><span data-stu-id="58cf8-121">However, the `#Requires` state had to be met before the script could even execute.</span></span> <span data-ttu-id="58cf8-122">次に、スクリプトの最初の行で必要な状態が無効になります。</span><span class="sxs-lookup"><span data-stu-id="58cf8-122">Then the first line of the script invalidated the required state.</span></span>

### <a name="parameters"></a><span data-ttu-id="58cf8-123">パラメーター</span><span class="sxs-lookup"><span data-stu-id="58cf8-123">Parameters</span></span>

#### <a name="-assembly-assembly-path--net-assembly-specification"></a><span data-ttu-id="58cf8-124">-Assembly \<Assembly path> |\<.NET assembly specification></span><span class="sxs-lookup"><span data-stu-id="58cf8-124">-Assembly \<Assembly path> | \<.NET assembly specification></span></span>

<span data-ttu-id="58cf8-125">アセンブリ DLL ファイルまたは .NET アセンブリ名へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-125">Specifies the path to the assembly DLL file or a .NET assembly name.</span></span> <span data-ttu-id="58cf8-126">**Assembly** パラメーターは、PowerShell 5.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="58cf8-126">The **Assembly** parameter was introduced in PowerShell 5.0.</span></span> <span data-ttu-id="58cf8-127">.NET アセンブリの詳細については、「 [アセンブリ名](/dotnet/standard/assembly/names)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58cf8-127">For more information about .NET assemblies, see [Assembly names](/dotnet/standard/assembly/names).</span></span>

<span data-ttu-id="58cf8-128">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-128">For example:</span></span>

```
#Requires -Assembly path\to\foo.dll
```

```
#Requires -Assembly "System.Management.Automation, Version=3.0.0.0,
  Culture=neutral, PublicKeyToken=31bf3856ad364e35"
```

#### <a name="-version-nn"></a><span data-ttu-id="58cf8-129">-Version \<N\> [. \<n\> ]</span><span class="sxs-lookup"><span data-stu-id="58cf8-129">-Version \<N\>[.\<n\>]</span></span>

<span data-ttu-id="58cf8-130">スクリプトに必要な PowerShell の最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-130">Specifies the minimum version of PowerShell that the script requires.</span></span> <span data-ttu-id="58cf8-131">メジャーバージョン番号と省略可能なマイナーバージョン番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-131">Enter a major version number and optional minor version number.</span></span>

<span data-ttu-id="58cf8-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-132">For example:</span></span>

```powershell
#Requires -Version 5.1
```

#### <a name="-pssnapin-pssnapin-name--version-nn"></a><span data-ttu-id="58cf8-133">-Add-pssnapin \<PSSnapin-Name\> [-Version \<N\> [. \<n\> ]]</span><span class="sxs-lookup"><span data-stu-id="58cf8-133">-PSSnapin \<PSSnapin-Name\> [-Version \<N\>[.\<n\>]]</span></span>

<span data-ttu-id="58cf8-134">スクリプトに必要な PowerShell スナップインを指定します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-134">Specifies a PowerShell snap-in that the script requires.</span></span> <span data-ttu-id="58cf8-135">スナップイン名とオプションのバージョン番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-135">Enter the snap-in name and an optional version number.</span></span>

<span data-ttu-id="58cf8-136">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-136">For example:</span></span>

```powershell
#Requires -PSSnapin DiskSnapin -Version 1.2
```

#### <a name="-modules-module-name--hashtable"></a><span data-ttu-id="58cf8-137">-モジュール \<Module-Name\> |\<Hashtable\></span><span class="sxs-lookup"><span data-stu-id="58cf8-137">-Modules \<Module-Name\> | \<Hashtable\></span></span>

<span data-ttu-id="58cf8-138">スクリプトに必要な PowerShell モジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-138">Specifies PowerShell modules that the script requires.</span></span> <span data-ttu-id="58cf8-139">モジュール名とオプションのバージョン番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-139">Enter the module name and an optional version number.</span></span>

<span data-ttu-id="58cf8-140">必要なモジュールが現在のセッションにない場合は、PowerShell によってインポートされます。</span><span class="sxs-lookup"><span data-stu-id="58cf8-140">If the required modules aren't in the current session, PowerShell imports them.</span></span>
<span data-ttu-id="58cf8-141">モジュールをインポートできない場合、PowerShell は終了エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="58cf8-141">If the modules can't be imported, PowerShell throws a terminating error.</span></span>

<span data-ttu-id="58cf8-142">モジュールごとに、モジュール名 ( \<String\> ) またはハッシュテーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-142">For each module, type the module name (\<String\>) or a hash table.</span></span> <span data-ttu-id="58cf8-143">値には、文字列とハッシュテーブルの組み合わせを指定できます。</span><span class="sxs-lookup"><span data-stu-id="58cf8-143">The value can be a combination of strings and hash tables.</span></span> <span data-ttu-id="58cf8-144">ハッシュテーブルには、次のキーがあります。</span><span class="sxs-lookup"><span data-stu-id="58cf8-144">The hash table has the following keys.</span></span>

- <span data-ttu-id="58cf8-145">`ModuleName` - **必須** モジュール名を指定します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-145">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="58cf8-146">`GUID` - **省略可能** モジュールの GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-146">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="58cf8-147">以下の3つのキーのいずれかを指定する **必要** もあります。</span><span class="sxs-lookup"><span data-stu-id="58cf8-147">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="58cf8-148">これらのキーを一緒に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="58cf8-148">These keys can't be used together.</span></span>
  - <span data-ttu-id="58cf8-149">`ModuleVersion` -モジュールの許容される最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-149">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="58cf8-150">`RequiredVersion` -モジュールの正確な必須バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-150">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="58cf8-151">`MaximumVersion` -モジュールの許容される最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-151">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

> [!NOTE]
> <span data-ttu-id="58cf8-152">`RequiredVersion` は Windows PowerShell 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="58cf8-152">`RequiredVersion` was added in Windows PowerShell 5.0.</span></span>
> <span data-ttu-id="58cf8-153">`MaximumVersion` は Windows PowerShell 5.1 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="58cf8-153">`MaximumVersion` was added in Windows PowerShell 5.1.</span></span>

<span data-ttu-id="58cf8-154">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-154">For example:</span></span>

<span data-ttu-id="58cf8-155">`Hyper-V`(バージョン `1.1` 以上) がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="58cf8-155">Require that `Hyper-V` (version `1.1` or greater) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="Hyper-V"; ModuleVersion="1.1" }
```

<span data-ttu-id="58cf8-156">`Hyper-V`(バージョン **のみ** `1.1` ) がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="58cf8-156">Requires that `Hyper-V` ( **only** version `1.1`) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="Hyper-V"; RequiredVersion="1.1" }
```

<span data-ttu-id="58cf8-157">`Hyper-V`(バージョン `1.1` 以降) がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="58cf8-157">Requires that `Hyper-V` (version `1.1` or lesser) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="Hyper-V"; MaximumVersion="1.1" }
```

<span data-ttu-id="58cf8-158">では、およびのすべてのバージョンがインストールされている必要があり `PSScheduledJob` `PSWorkflow` ます。</span><span class="sxs-lookup"><span data-stu-id="58cf8-158">Requires that any version of `PSScheduledJob` and `PSWorkflow`, is installed.</span></span>

```powershell
#Requires -Modules PSWorkflow, PSScheduledJob
```

<span data-ttu-id="58cf8-159">キーを使用する場合は `RequiredVersion` 、バージョン文字列が必要なバージョン文字列と完全に一致していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="58cf8-159">When using the `RequiredVersion` key, ensure your version string exactly matches the version string you wish to require.</span></span>

```powershell
Get-Module Hyper-V
```

```Output
ModuleType Version    Name     ExportedCommands
---------- -------    ----     ------------------
Binary     2.0.0.0    hyper-v  {Add-VMAssignableDevice, ...}
```

<span data-ttu-id="58cf8-160">**2.0.0** が **2.0.0.0** と完全に一致しないため、次の例は失敗します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-160">The following example fails because **2.0.0** doesn't exactly match **2.0.0.0**.</span></span>

```powershell
#Requires -Modules @{ ModuleName="Hyper-V"; RequiredVersion="2.0.0" }
```

#### <a name="-psedition-psedition-name"></a><span data-ttu-id="58cf8-161">-PSEdition \<PSEdition-Name\></span><span class="sxs-lookup"><span data-stu-id="58cf8-161">-PSEdition \<PSEdition-Name\></span></span>

<span data-ttu-id="58cf8-162">スクリプトに必要な PowerShell エディションを指定します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-162">Specifies a PowerShell edition that the script requires.</span></span> <span data-ttu-id="58cf8-163">有効な値は、PowerShell Core の **コア** と Windows powershell 用の **デスクトップ** です。</span><span class="sxs-lookup"><span data-stu-id="58cf8-163">Valid values are **Core** for PowerShell Core and **Desktop** for Windows PowerShell.</span></span>

<span data-ttu-id="58cf8-164">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-164">For example:</span></span>

```powershell
#Requires -PSEdition Core
```

#### <a name="-shellid"></a><span data-ttu-id="58cf8-165">-ShellId</span><span class="sxs-lookup"><span data-stu-id="58cf8-165">-ShellId</span></span>

<span data-ttu-id="58cf8-166">スクリプトに必要なシェルを指定します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-166">Specifies the shell that the script requires.</span></span> <span data-ttu-id="58cf8-167">シェル ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-167">Enter the shell ID.</span></span> <span data-ttu-id="58cf8-168">**ShellId** パラメーターを使用する場合は、 **add-pssnapin** パラメーターも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="58cf8-168">If you use the **ShellId** parameter, you must also include the **PSSnapin** parameter.</span></span>
<span data-ttu-id="58cf8-169">自動変数に対してクエリを実行することで、現在の **ShellId** を見つけることができ `$ShellId` ます。</span><span class="sxs-lookup"><span data-stu-id="58cf8-169">You can find the current **ShellId** by querying the `$ShellId` automatic variable.</span></span>

<span data-ttu-id="58cf8-170">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-170">For example:</span></span>

```powershell
#Requires -ShellId MyLocalShell -PSSnapin Microsoft.PowerShell.Core
```

> [!NOTE]
> <span data-ttu-id="58cf8-171">このパラメーターは、非推奨とされたミニシェルで使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="58cf8-171">This parameter is intended for use in mini-shells, which have been deprecated.</span></span>

#### <a name="-runasadministrator"></a><span data-ttu-id="58cf8-172">-RunAsAdministrator</span><span class="sxs-lookup"><span data-stu-id="58cf8-172">-RunAsAdministrator</span></span>

<span data-ttu-id="58cf8-173">このスイッチパラメーターをステートメントに追加すると、スクリプトを実行している `#Requires` PowerShell セッションを管理者特権で起動する必要があることが指定されます。</span><span class="sxs-lookup"><span data-stu-id="58cf8-173">When this switch parameter is added to your `#Requires` statement, it specifies that the PowerShell session in which you're running the script must be started with elevated user rights.</span></span> <span data-ttu-id="58cf8-174">Windows 以外のオペレーティングシステムでは、 **RunAsAdministrator** パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="58cf8-174">The **RunAsAdministrator** parameter is ignored on a non-Windows operating system.</span></span> <span data-ttu-id="58cf8-175">**RunAsAdministrator** パラメーターは、PowerShell 4.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="58cf8-175">The **RunAsAdministrator** parameter was introduced in PowerShell 4.0.</span></span>

<span data-ttu-id="58cf8-176">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="58cf8-176">For example:</span></span>

```powershell
#Requires -RunAsAdministrator
```

### <a name="examples"></a><span data-ttu-id="58cf8-177">例</span><span class="sxs-lookup"><span data-stu-id="58cf8-177">Examples</span></span>

<span data-ttu-id="58cf8-178">次のスクリプトには2つのステートメントがあり `#Requires` ます。</span><span class="sxs-lookup"><span data-stu-id="58cf8-178">The following script has two `#Requires` statements.</span></span> <span data-ttu-id="58cf8-179">両方のステートメントで指定された要件を満たしていない場合、スクリプトは実行されません。</span><span class="sxs-lookup"><span data-stu-id="58cf8-179">If the requirements specified in both statements aren't met, the script doesn't run.</span></span> <span data-ttu-id="58cf8-180">各 `#Requires` ステートメントは、行の最初の項目である必要があります。</span><span class="sxs-lookup"><span data-stu-id="58cf8-180">Each `#Requires` statement must be the first item on a line:</span></span>

```powershell
#Requires -Modules PSWorkflow
#Requires -Version 3
Param
(
    [parameter(Mandatory=$true)]
    [String[]]
    $Path
)
...
```

## <a name="see-also"></a><span data-ttu-id="58cf8-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="58cf8-181">See also</span></span>

[<span data-ttu-id="58cf8-182">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="58cf8-182">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="58cf8-183">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="58cf8-183">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="58cf8-184">about_PSSnapins</span><span class="sxs-lookup"><span data-stu-id="58cf8-184">about_PSSnapins</span></span>](about_PSSnapins.md)

[<span data-ttu-id="58cf8-185">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="58cf8-185">Get-PSSnapin</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSnapin)
