---
description: PowerShell のさまざまなエディションは、基になるさまざまなランタイムで実行されます。
Locale: en-US
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_editions?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Editions
ms.openlocfilehash: 4649c1b47a69423eb2f11a119583f441191882dd
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221376"
---
# <a name="about-powershell-editions"></a><span data-ttu-id="8933b-103">PowerShell のエディションについて</span><span class="sxs-lookup"><span data-stu-id="8933b-103">About PowerShell Editions</span></span>

## <a name="short-description"></a><span data-ttu-id="8933b-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="8933b-104">Short Description</span></span>
<span data-ttu-id="8933b-105">PowerShell のさまざまなエディションは、基になるさまざまなランタイムで実行されます。</span><span class="sxs-lookup"><span data-stu-id="8933b-105">Different editions of PowerShell run on different underlying runtimes.</span></span>

## <a name="long-description"></a><span data-ttu-id="8933b-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="8933b-106">Long Description</span></span>

<span data-ttu-id="8933b-107">PowerShell 5.1 では、それぞれが異なる .NET ランタイムで実行される PowerShell の複数の _エディション_ があります。</span><span class="sxs-lookup"><span data-stu-id="8933b-107">From PowerShell 5.1, there are multiple _editions_ of PowerShell that each run on a different .NET runtime.</span></span> <span data-ttu-id="8933b-108">PowerShell 6.2 の場合、PowerShell には次の2つのエディションがあります。</span><span class="sxs-lookup"><span data-stu-id="8933b-108">As of PowerShell 6.2 there are two editions of PowerShell:</span></span>

- <span data-ttu-id="8933b-109">**デスクトップ** 。 .NET Framework で実行されます。</span><span class="sxs-lookup"><span data-stu-id="8933b-109">**Desktop** , which runs on .NET Framework.</span></span> <span data-ttu-id="8933b-110">PowerShell 4 以降、および Windows デスクトップ、Windows Server、Windows Server Core、その他のほとんどの Windows オペレーティングシステムなどの全機能を備えた windows オペレーティングシステムの PowerShell 5.1 は、Desktop edition です。</span><span class="sxs-lookup"><span data-stu-id="8933b-110">PowerShell 4 and below, as well as PowerShell 5.1 on full-featured Windows editions like Windows Desktop, Windows Server, Windows Server Core and most other Windows operating systems are Desktop edition.</span></span> <span data-ttu-id="8933b-111">これは、元の PowerShell エディションです。</span><span class="sxs-lookup"><span data-stu-id="8933b-111">This is the original PowerShell edition.</span></span>
- <span data-ttu-id="8933b-112">**コア** 。 .net core で実行されます。</span><span class="sxs-lookup"><span data-stu-id="8933b-112">**Core** , which runs on .NET Core.</span></span> <span data-ttu-id="8933b-113">PowerShell 6.0 以降、および .NET Framework が使用できない windows Nano Server や Windows IoT などのフットプリントが縮小された windows エディションの PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="8933b-113">PowerShell 6.0 and above, as well as PowerShell 5.1 on some reduced-footprint Windows editions such as Windows Nano Server and Windows IoT where .NET Framework is unavailable.</span></span>

<span data-ttu-id="8933b-114">PowerShell のエディションは .NET ランタイムに対応しているため、.NET API と PowerShell モジュールの互換性の主要な指標となります。.net の Api、型、またはメソッドの中には、両方の .NET ランタイムで使用できないものがあります。これは、それらに依存する PowerShell スクリプトとモジュールに影響します。</span><span class="sxs-lookup"><span data-stu-id="8933b-114">Because the edition of PowerShell corresponds to its .NET runtime, it is the primary indicator of .NET API and PowerShell module compatibility; some .NET APIs, types or methods are not available in both .NET runtimes and this affects PowerShell scripts and modules that depend on them.</span></span>

## <a name="the-psedition-automatic-variable"></a><span data-ttu-id="8933b-115">`$PSEdition`自動変数</span><span class="sxs-lookup"><span data-stu-id="8933b-115">The `$PSEdition` automatic variable</span></span>

<span data-ttu-id="8933b-116">PowerShell 5.1 以降では、自動変数を使用して実行しているエディションを調べることができ `$PSEdition` ます。</span><span class="sxs-lookup"><span data-stu-id="8933b-116">In PowerShell 5.1 and above, you can find out what edition you are running with the `$PSEdition` automatic variable:</span></span>

```powershell
$PSEdition
```

```Output
Core
```

<span data-ttu-id="8933b-117">PowerShell 4 以降では、この変数は存在しません。</span><span class="sxs-lookup"><span data-stu-id="8933b-117">In PowerShell 4 and below, this variable does not exist.</span></span> <span data-ttu-id="8933b-118">`$PSEdition` null の場合は、値を持つのと同じように処理する必要があり `Desktop` ます。</span><span class="sxs-lookup"><span data-stu-id="8933b-118">`$PSEdition` being null should be treated as the same as having the value `Desktop`.</span></span>

### <a name="edition-in-psversiontable"></a><span data-ttu-id="8933b-119">のエディション `$PSVersionTable`</span><span class="sxs-lookup"><span data-stu-id="8933b-119">Edition in `$PSVersionTable`</span></span>

<span data-ttu-id="8933b-120">自動変数には、 `$PSVersionTable` PowerShell 5.1 以降のエディション情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="8933b-120">The `$PSVersionTable` automatic variable also has edition information in PowerShell 5.1 and above:</span></span>

```powershell
$PSVersionTable
```

```Output
Name                           Value
----                           -----
PSVersion                      6.2.0-rc.1
PSEdition                      Core           # <-- Edition information
GitCommitId                    6.2.0-rc.1
OS                             Microsoft Windows 10.0.18865
Platform                       Win32NT
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
WSManStackVersion              3.0
```

<span data-ttu-id="8933b-121">フィールドには、 `PSEdition` 自動変数と同じ値が設定され `$PSEdition` ます。</span><span class="sxs-lookup"><span data-stu-id="8933b-121">The `PSEdition` field will have the same value as the `$PSEdition` automatic variable.</span></span>

## <a name="the-compatiblepseditions-module-manifest-field"></a><span data-ttu-id="8933b-122">`CompatiblePSEditions`モジュールマニフェストフィールド</span><span class="sxs-lookup"><span data-stu-id="8933b-122">The `CompatiblePSEditions` module manifest field</span></span>

<span data-ttu-id="8933b-123">PowerShell モジュールでは、モジュールマニフェストのフィールドを使用して、互換性のある PowerShell のエディションを宣言でき `CompatiblePSEditions` ます。</span><span class="sxs-lookup"><span data-stu-id="8933b-123">PowerShell modules can declare what editions of PowerShell they are compatible with using the `CompatiblePSEditions` field of the module manifest.</span></span>

<span data-ttu-id="8933b-124">たとえば、PowerShell のとの両方のエディションとの互換性を宣言するモジュールマニフェストは `Desktop` `Core` 次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8933b-124">For example, a module manifest declaring compatibility with both `Desktop` and `Core` editions of PowerShell:</span></span>

```powershell
@{
    ModuleVersion = '1.0'
    FunctionsToExport = @('Test-MyModule')
    CompatiblePSEditions = @('Desktop', 'Core')
}
```

<span data-ttu-id="8933b-125">互換性のみを持つモジュールマニフェストの例を `Desktop` 次に示します。</span><span class="sxs-lookup"><span data-stu-id="8933b-125">An example of a module manifest with only `Desktop` compatibility:</span></span>

```powershell
@{
    ModuleVersion = '1.0'
    FunctionsToExport = @('Test-MyModule')
    CompatiblePSEditions = @('Desktop')
}
```

<span data-ttu-id="8933b-126">`CompatiblePSEditions`モジュールマニフェストからフィールドを除外すると、そのフィールドをに設定した場合と同じ効果が得られ `Desktop` ます。このフィールドを導入する前に作成されたモジュールは、このエディションに対して暗黙的に記述されているためです。</span><span class="sxs-lookup"><span data-stu-id="8933b-126">Omitting the `CompatiblePSEditions` field from a module manifest will have the same effect as setting it to `Desktop`, since modules created before this field was introduced were implicitly written for this edition.</span></span>

<span data-ttu-id="8933b-127">Windows の一部として出荷されていないモジュール (つまり、ギャラリーから作成またはインストールするモジュール) では、このフィールドは情報提供のみを目的としています。PowerShell では、フィールドに基づく動作は変更されません `CompatiblePSEditions` が、 `PSModuleInfo` `Get-Module` 独自のロジックに対して (によって返される) オブジェクトで公開されます。</span><span class="sxs-lookup"><span data-stu-id="8933b-127">For modules not shipped as part of Windows (i.e. modules you write or install from the gallery), this field is informational only; PowerShell does not change behavior based on the `CompatiblePSEditions` field, but does expose it on the `PSModuleInfo` object (returned by `Get-Module`) for your own logic:</span></span>

```powershell
New-ModuleManifest -Path .\TestModuleWithEdition.psd1 -CompatiblePSEditions Desktop,Core -PowerShellVersion '5.1'
$ModuleInfo = Test-ModuleManifest -Path .\TestModuleWithEdition.psd1
$ModuleInfo.CompatiblePSEditions
```

```Output
Desktop
Core
```

> [!NOTE]
> <span data-ttu-id="8933b-128">`CompatiblePSEditions`モジュールフィールドは、PowerShell 5.1 以降とのみ互換性があります。</span><span class="sxs-lookup"><span data-stu-id="8933b-128">The `CompatiblePSEditions` module field is only compatible with PowerShell 5.1 and above.</span></span> <span data-ttu-id="8933b-129">このフィールドを含めると、モジュールは PowerShell 4 以下と互換性がなくなります。</span><span class="sxs-lookup"><span data-stu-id="8933b-129">Including this field will cause a module to be incompatible with PowerShell 4 and below.</span></span> <span data-ttu-id="8933b-130">フィールドは純粋な情報であるため、後の PowerShell バージョンでは省略できます。</span><span class="sxs-lookup"><span data-stu-id="8933b-130">Since the field is purely informational, it can be safely omitted in later PowerShell versions.</span></span>

<span data-ttu-id="8933b-131">PowerShell 6.1 で `Get-Module -ListAvailable` は、各モジュールのエディション互換性を表示するために、フォーマッタが更新されています。</span><span class="sxs-lookup"><span data-stu-id="8933b-131">In PowerShell 6.1, `Get-Module -ListAvailable` has had its formatter updated to display the edition-compatibility of each module:</span></span>

```PowerShell
Get-Module -ListAvailable
```

```Output

    Directory: C:\Users\me\Documents\PowerShell\Modules

ModuleType Version    Name                   PSEdition ExportedCommands
---------- -------    ----                   --------- ----------------
Script     1.4.0      Az                     Core,Desk
Script     1.3.1      Az.Accounts            Core,Desk {Disable-AzDataCollection, Disable-AzContextAutosave, E...
Script     1.0.1      Az.Aks                 Core,Desk {Get-AzAks, New-AzAks, Remove-AzAks, Import-AzAksCreden...

...

Script     4.4.0      Pester                 Desk      {Describe, Context, It, Should...}
Script     1.18.0     PSScriptAnalyzer       Desk      {Get-ScriptAnalyzerRule, Invoke-ScriptAnalyzer, Invoke-...
Script     1.0.0      WindowsCompatibility   Core      {Initialize-WinSession, Add-WinFunction, Invoke-WinComm...

```

## <a name="edition-compatibility-for-modules-that-ship-as-part-of-windows"></a><span data-ttu-id="8933b-132">エディション-Windows の一部として出荷されるモジュールの互換性</span><span class="sxs-lookup"><span data-stu-id="8933b-132">Edition-compatibility for modules that ship as part of Windows</span></span>

<span data-ttu-id="8933b-133">Windows の一部として提供されるモジュール (または役割または機能の一部としてインストールされるモジュール) では、PowerShell 6.1 以降ではフィールドが異なる方法で処理され `CompatiblePSEditions` ます。</span><span class="sxs-lookup"><span data-stu-id="8933b-133">For modules that come as part of Windows (or are installed as part of a role or feature), PowerShell 6.1 and above treat the `CompatiblePSEditions` field differently.</span></span> <span data-ttu-id="8933b-134">このようなモジュールは、Windows PowerShell のシステムモジュールディレクトリ () にあり `%windir%\System\WindowsPowerShell\v1.0\Modules` ます。</span><span class="sxs-lookup"><span data-stu-id="8933b-134">Such modules are found in the Windows PowerShell system modules directory (`%windir%\System\WindowsPowerShell\v1.0\Modules`).</span></span>

<span data-ttu-id="8933b-135">このディレクトリに読み込まれた、またはこのディレクトリにあるモジュールの場合、PowerShell 6.1 以降では、 `CompatiblePSEditions` モジュールが現在のセッションと互換性があるかどうかを判断するためにフィールドを使用し、それに応じて動作します。</span><span class="sxs-lookup"><span data-stu-id="8933b-135">For modules loaded from or found in this directory, PowerShell 6.1 and above uses the `CompatiblePSEditions` field to determine whether the module will be compatible with the current session and behaves accordingly.</span></span>

<span data-ttu-id="8933b-136">を使用した場合 `Import-Module` 、に含まれていないモジュールはインポートされず、 `Core` `CompatiblePSEditions` エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8933b-136">When `Import-Module` is used, a module without `Core` in `CompatiblePSEditions` will not be imported and an error will be displayed:</span></span>

```powershell
Import-Module BitsTransfer
```

```Output
Import-Module : Module 'C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\BitsT
ransfer\BitsTransfer.psd1' does not support current PowerShell edition 'Core'.
Its supported editions are 'Desktop'. Use 'Import-Module -SkipEditionCheck' to i
gnore the compatibility of this module.
At line:1 char:1
+ Import-Module BitsTransfer
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : ResourceUnavailable: (C:\WINDOWS\system32\u2026r\BitsT
ransfer.psd1:String) [Import-Module], InvalidOperationException
+ FullyQualifiedErrorId : Modules_PSEditionNotSupported,Microsoft.PowerShell.Com
mands.ImportModuleCommand
```

<span data-ttu-id="8933b-137">`Get-Module -ListAvailable`を使用した場合、 `Core` に含まれていないモジュールは表示され `CompatiblePSEditions` ません。</span><span class="sxs-lookup"><span data-stu-id="8933b-137">When `Get-Module -ListAvailable` is used, modules without `Core` in `CompatiblePSEditions` will not be displayed:</span></span>

```powershell
Get-Module -ListAvailable BitsTransfer
```

```Output
# No output
```

<span data-ttu-id="8933b-138">どちらの場合も、 `-SkipEditionCheck` スイッチパラメーターを使用して、この動作をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="8933b-138">In both cases, the `-SkipEditionCheck` switch parameter can be used to override this behavior:</span></span>

```powershell
Get-Module -ListAvailable -SkipEditionCheck BitsTransfer
```

```Output
    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name             PSEdition ExportedCommands
---------- -------    ----             --------- ----------------
Manifest   2.0.0.0    BitsTransfer     Desk      {Add-BitsFile, Complete-BitsTransfer, Get-BitsTransfer,...
```

> [!WARNING]
> <span data-ttu-id="8933b-139">`Import-Module -SkipEditionCheck` モジュールに対して成功するように見えますが、そのモジュールを使用すると、後で非互換性が発生する可能性があります。最初にモジュールの読み込みが成功しても、コマンドは後で互換性のない API を呼び出し、自発的に失敗します。</span><span class="sxs-lookup"><span data-stu-id="8933b-139">`Import-Module -SkipEditionCheck` may appear to succeed for a module, but using that module runs the risk of encountering an incompatibility later on; while loading the module initially succeeds, a command may later call an incompatible API and fail spontaneously.</span></span>

## <a name="authoring-powershell-modules-for-edition-cross-compatibility"></a><span data-ttu-id="8933b-140">エディション間の互換性のための PowerShell モジュールの作成</span><span class="sxs-lookup"><span data-stu-id="8933b-140">Authoring PowerShell modules for edition cross-compatibility</span></span>

<span data-ttu-id="8933b-141">Powershell モジュールを作成 `Desktop` して powershell のエディションとエディションの両方を対象とする場合は `Core` 、エディション間の互換性を確保するために実行できることがあります。</span><span class="sxs-lookup"><span data-stu-id="8933b-141">When writing a PowerShell module to target both `Desktop` and `Core` editions of PowerShell, there are things you can do to ensure cross-edition compatibility.</span></span>

<span data-ttu-id="8933b-142">ただし、互換性を確認し、継続的に検証する唯一の方法は、スクリプトまたはモジュールのテストを記述し、それらを PowerShell のすべてのバージョンおよびエディションで実行して互換性が必要な場合です。</span><span class="sxs-lookup"><span data-stu-id="8933b-142">The only true way to confirm and continually validate compatibility however is to write tests for your script or module and run them on all versions and editions of PowerShell you need compatibility with.</span></span> <span data-ttu-id="8933b-143">この場合の推奨されるテストフレームワークは、 [次のよう][]になります。</span><span class="sxs-lookup"><span data-stu-id="8933b-143">A recommended testing framework for this is [Pester][].</span></span>

### <a name="powershell-script"></a><span data-ttu-id="8933b-144">PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="8933b-144">PowerShell script</span></span>

<span data-ttu-id="8933b-145">言語として、PowerShell はエディションによっても同じように機能します。これは、エディションの互換性によって影響を受ける、使用するコマンドレット、モジュール、.NET Api です。</span><span class="sxs-lookup"><span data-stu-id="8933b-145">As a language, PowerShell works the same between editions; it is the cmdlets, modules and .NET APIs you use that are affected by edition compatibility.</span></span>

<span data-ttu-id="8933b-146">一般に、PowerShell 6.1 以降で動作するスクリプトは Windows PowerShell 5.1 で動作しますが、いくつかの例外があります。</span><span class="sxs-lookup"><span data-stu-id="8933b-146">Generally, scripts that work in PowerShell 6.1 and above will work with Windows PowerShell 5.1, but there are some exceptions.</span></span>

<span data-ttu-id="8933b-147">バージョン 1.18.0 [Psscriptanalyzer][] モジュールには、 [PSUseCompatibleCommands][] や [PSUseCompatibleTypes][] のような規則があり、互換性のない可能性があるコマンドと .net api の使用を PowerShell スクリプトで検出できます。</span><span class="sxs-lookup"><span data-stu-id="8933b-147">Version 1.18.0 [PSScriptAnalyzer][] module has rules like [PSUseCompatibleCommands][] and [PSUseCompatibleTypes][] that are able to detect possibly incompatible usage of commands and .NET APIs in PowerShell scripts.</span></span>

### <a name="net-assemblies"></a><span data-ttu-id="8933b-148">.NET アセンブリ</span><span class="sxs-lookup"><span data-stu-id="8933b-148">.NET assemblies</span></span>

<span data-ttu-id="8933b-149">ソースコードから生成された .NET アセンブリ (Dll) を組み込んだバイナリモジュールまたはモジュールを作成する場合は、.NET と PowerShell API の互換性のコンパイル時の互換性検証のために、 [.NET Standard][] と [powershell の標準][] に対してコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8933b-149">If you are writing a binary module or a module that incorporates .NET assemblies (DLLs) generated from source code, you should compile against [.NET Standard][] and [PowerShell Standard][] for compile-time compatibility validation of .NET and PowerShell API compatibility.</span></span>

<span data-ttu-id="8933b-150">これらのライブラリはコンパイル時に一部の互換性を確認できますが、エディション間の動作の違いを検出することはできません。</span><span class="sxs-lookup"><span data-stu-id="8933b-150">Although these libraries are able to check some compatibility at compile time, they won't be able to catch possible behavioral differences between editions.</span></span>
<span data-ttu-id="8933b-151">この場合も、テストを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8933b-151">For this you must still write tests.</span></span>

## <a name="see-also"></a><span data-ttu-id="8933b-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="8933b-152">See also</span></span>

- [<span data-ttu-id="8933b-153">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="8933b-153">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)
- [<span data-ttu-id="8933b-154">Import-Module</span><span class="sxs-lookup"><span data-stu-id="8933b-154">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)
- [<span data-ttu-id="8933b-155">Get-Module</span><span class="sxs-lookup"><span data-stu-id="8933b-155">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)
- [<span data-ttu-id="8933b-156">互換性のある PowerShell エディションが含まれるモジュール</span><span class="sxs-lookup"><span data-stu-id="8933b-156">Modules with compatible PowerShell Editions</span></span>](/powershell/scripting/gallery/concepts/module-psedition-support)

[Pester]: https://github.com/pester/Pester/wiki/Pester
[PSScriptAnalyzer]: https://github.com/PowerShell/PSScriptAnalyzer
[PSUseCompatibleCommands]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleCommands.md
[PSUseCompatibleTypes]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleTypes.md
[.NET Standard]: /dotnet/standard/net-standard
[PowerShell Standard]: https://devblogs.microsoft.com/powershell/powershell-standard-library-build-single-module-that-works-across-windows-powershell-and-powershell-core/
