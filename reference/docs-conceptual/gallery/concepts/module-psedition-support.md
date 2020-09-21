---
ms.date: 06/10/2020
contributor: manikb
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: 互換性のある PowerShell エディションが含まれるモジュール
ms.openlocfilehash: 522493714916e9fd21f67a6e7bc2cfb165041807
ms.sourcegitcommit: 4a283fe5419f47102e6c1de7060880a934842ee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "84671412"
---
# <a name="modules-with-compatible-powershell-editions"></a><span data-ttu-id="b7ff4-103">互換性のある PowerShell エディションが含まれるモジュール</span><span class="sxs-lookup"><span data-stu-id="b7ff4-103">Modules with compatible PowerShell Editions</span></span>

<span data-ttu-id="b7ff4-104">バージョン 5.1 から、PowerShell はさまざまな機能セットとプラットフォーム互換性を備えるさまざまなエディションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-104">Starting with version 5.1, PowerShell is available in different editions, which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="b7ff4-105">**Desktop Edition:** .NET Framework に基づいて構成され、Windows デスクトップ、Windows Server、Windows Server Core、およびその他のほとんどの Windows エディション上の Windows PowerShell v4.0 以下と Windows PowerShell 5.1 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-105">**Desktop Edition:** Built on .NET Framework, applies to Windows PowerShell v4.0 and below as well as Windows PowerShell 5.1 on Windows Desktop, Windows Server, Windows Server Core and most other Windows editions.</span></span>
- <span data-ttu-id="b7ff4-106">**Core Edition:** .NET Core に基づいて構築され、Windows IoT や Windows Nanoserver などのフットプリントが小さい Windows エディション上の PowerShell Core 6.0 以上と Windows PowerShell 5.1 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-106">**Core Edition:** Built on .NET Core, applies to PowerShell Core 6.0 and above as well as Windows PowerShell 5.1 on reduced footprint Windows Editions such as Windows IoT and Windows Nanoserver.</span></span>

<span data-ttu-id="b7ff4-107">PowerShell のエディションの詳細については、[about_PowerShell_Editions][] に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-107">For more information on PowerShell editions, see [about_PowerShell_Editions][].</span></span>

## <a name="declaring-compatible-editions"></a><span data-ttu-id="b7ff4-108">互換性のあるエディションを宣言する</span><span class="sxs-lookup"><span data-stu-id="b7ff4-108">Declaring compatible editions</span></span>

<span data-ttu-id="b7ff4-109">モジュールの作成者は、`CompatiblePSEditions` モジュール マニフェスト キーを使用して、モジュールが 1 つ以上の PowerShell エディションと互換性があることを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-109">Module authors can declare their modules to be compatible with one or more PowerShell editions using the `CompatiblePSEditions` module manifest key.</span></span> <span data-ttu-id="b7ff4-110">このキーは、PowerShell 5.1 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-110">This key is only supported on PowerShell 5.1 or later.</span></span>

> [!NOTE]
> <span data-ttu-id="b7ff4-111">`CompatiblePSEditions` キーを使用して指定された、または `$PSEdition` 変数を使用したモジュール マニフェストは、PowerShell v4 またはそれ以前にインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-111">Once a module manifest is specified with the `CompatiblePSEditions` key or uses the `$PSEdition` variable, it can not be imported on PowerShell v4 or lower.</span></span>

```powershell
New-ModuleManifest -Path .\TestModuleWithEdition.psd1 -CompatiblePSEditions Desktop,Core -PowerShellVersion 5.1
$ModuleInfo = Test-ModuleManifest -Path .\TestModuleWithEdition.psd1
$ModuleInfo.CompatiblePSEditions
```

```Output
Desktop
Core
```

```powershell
$ModuleInfo | Get-Member CompatiblePSEditions
```

```Output
   TypeName: System.Management.Automation.PSModuleInfo

Name                 MemberType Definition
----                 ---------- ----------
CompatiblePSEditions Property   System.Collections.Generic.IEnumerable[string] CompatiblePSEditions {get;}
```

<span data-ttu-id="b7ff4-112">使用可能なモジュールの一覧を取得するときには、PowerShell のエディションを条件としてフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-112">When getting a list of available modules, you can filter the list by PowerShell edition.</span></span>

```powershell
Get-Module -ListAvailable -PSEdition Desktop
```

```Output
    Directory: C:\Program Files\WindowsPowerShell\Modules

ModuleType Version    Name                                ExportedCommands
---------- -------    ----                                ----------------
Manifest   1.0        ModuleWithPSEditions
```

```powershell
Get-Module -ListAvailable -PSEdition Core | % CompatiblePSEditions
```

```Output
Desktop
Core
```

<span data-ttu-id="b7ff4-113">PowerShell 6 以降では、モジュールが `$env:windir\System32\WindowsPowerShell\v1.0\Modules` からインポートされた場合にそのモジュールに互換性があるかどうかを判断するために `CompatiblePSEditions` 値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-113">Beginning in PowerShell 6, the `CompatiblePSEditions` value is used to decide if a module is compatible when modules are imported from `$env:windir\System32\WindowsPowerShell\v1.0\Modules`.</span></span>
<span data-ttu-id="b7ff4-114">この動作は、Windows にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-114">This behavior only applies to Windows.</span></span> <span data-ttu-id="b7ff4-115">このシナリオ以外では、値はメタデータとしてのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-115">Outside of this scenario, the value is only used as metadata.</span></span>

## <a name="finding-compatible-modules"></a><span data-ttu-id="b7ff4-116">互換性のあるモジュールの検索</span><span class="sxs-lookup"><span data-stu-id="b7ff4-116">Finding compatible modules</span></span>

<span data-ttu-id="b7ff4-117">PowerShell ギャラリー ユーザーは、**PSEdition_Desktop** および **PSEdition_Core** のタグを使用して特定の PowerShell エディションでサポートされているモジュールの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-117">PowerShell Gallery users can find the list of modules supported on a specific PowerShell Edition using tags **PSEdition_Desktop** and **PSEdition_Core**.</span></span>

<span data-ttu-id="b7ff4-118">**PSEdition_Desktop** および **PSEdition_Core** のタグがないモジュールは、PowerShell Desktop エディションで正常に動作するものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-118">Modules without **PSEdition_Desktop** and **PSEdition_Core** tags are considered to work fine on PowerShell Desktop editions.</span></span>

```powershell
# Find modules supported on PowerShell Desktop edition
Find-Module -Tag PSEdition_Desktop

# Find modules supported on PowerShell Core editions
Find-Module -Tag PSEdition_Core
```

## <a name="targeting-multiple-editions"></a><span data-ttu-id="b7ff4-119">複数のエディションを対象にする</span><span class="sxs-lookup"><span data-stu-id="b7ff4-119">Targeting multiple editions</span></span>

<span data-ttu-id="b7ff4-120">モジュールの作成者が、PowerShell エディションのどちらかまたは両方を対象とする 1 つのモジュールを発行することができます。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-120">Module authors can publish a single module targeting to either or both PowerShell editions (Desktop and Core).</span></span>

<span data-ttu-id="b7ff4-121">1 つのモジュールが、Desktop と Core の両方のエディションで動作します。そのモジュール内で、作成者は、`$PSEdition` 変数を使用して、RootModule またはモジュール マニフェストで必要なロジックを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-121">A single module can work on both Desktop and Core editions, in that module author has to add required logic in either RootModule or in the module manifest using `$PSEdition` variable.</span></span> <span data-ttu-id="b7ff4-122">モジュールでは、**CoreCLR** と **FullCLR** の両方を対象とするコンパイル済み DLL の 2 つのセットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-122">Modules can have two sets of compiled DLLs targeting both **CoreCLR** and **FullCLR**.</span></span> <span data-ttu-id="b7ff4-123">適切な DLL を読み込むためのロジックを含むパッケージ化オプションを次に示します。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-123">Here are the packaging options with logic for loading proper DLLs.</span></span>

### <a name="option-1-packaging-a-module-for-targeting-multiple-versions-and-multiple-editions-of-powershell"></a><span data-ttu-id="b7ff4-124">オプション 1: PowerShell の複数のバージョンおよび複数のエディションを対象としてパッケージ化する</span><span class="sxs-lookup"><span data-stu-id="b7ff4-124">Option 1: Packaging a module for targeting multiple versions and multiple editions of PowerShell</span></span>

<span data-ttu-id="b7ff4-125">モジュール フォルダーの内容</span><span class="sxs-lookup"><span data-stu-id="b7ff4-125">Module folder contents</span></span>

- <span data-ttu-id="b7ff4-126">Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="b7ff4-126">Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="b7ff4-127">Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="b7ff4-127">Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="b7ff4-128">PSScriptAnalyzer.psd1</span><span class="sxs-lookup"><span data-stu-id="b7ff4-128">PSScriptAnalyzer.psd1</span></span>
- <span data-ttu-id="b7ff4-129">PSScriptAnalyzer.psm1</span><span class="sxs-lookup"><span data-stu-id="b7ff4-129">PSScriptAnalyzer.psm1</span></span>
- <span data-ttu-id="b7ff4-130">ScriptAnalyzer.format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="b7ff4-130">ScriptAnalyzer.format.ps1xml</span></span>
- <span data-ttu-id="b7ff4-131">ScriptAnalyzer.types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="b7ff4-131">ScriptAnalyzer.types.ps1xml</span></span>
- <span data-ttu-id="b7ff4-132">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="b7ff4-132">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="b7ff4-133">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="b7ff4-133">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="b7ff4-134">en-US\about_PSScriptAnalyzer.help.txt</span><span class="sxs-lookup"><span data-stu-id="b7ff4-134">en-US\about_PSScriptAnalyzer.help.txt</span></span>
- <span data-ttu-id="b7ff4-135">en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml</span><span class="sxs-lookup"><span data-stu-id="b7ff4-135">en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml</span></span>
- <span data-ttu-id="b7ff4-136">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="b7ff4-136">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="b7ff4-137">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="b7ff4-137">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="b7ff4-138">Settings\CmdletDesign.psd1</span><span class="sxs-lookup"><span data-stu-id="b7ff4-138">Settings\CmdletDesign.psd1</span></span>
- <span data-ttu-id="b7ff4-139">Settings\DSC.psd1</span><span class="sxs-lookup"><span data-stu-id="b7ff4-139">Settings\DSC.psd1</span></span>
- <span data-ttu-id="b7ff4-140">Settings\ScriptFunctions.psd1</span><span class="sxs-lookup"><span data-stu-id="b7ff4-140">Settings\ScriptFunctions.psd1</span></span>
- <span data-ttu-id="b7ff4-141">Settings\ScriptingStyle.psd1</span><span class="sxs-lookup"><span data-stu-id="b7ff4-141">Settings\ScriptingStyle.psd1</span></span>
- <span data-ttu-id="b7ff4-142">Settings\ScriptSecurity.psd1</span><span class="sxs-lookup"><span data-stu-id="b7ff4-142">Settings\ScriptSecurity.psd1</span></span>

<span data-ttu-id="b7ff4-143">`PSScriptAnalyzer.psd1` ファイルの内容</span><span class="sxs-lookup"><span data-stu-id="b7ff4-143">Contents of `PSScriptAnalyzer.psd1` file</span></span>

```powershell
@{

# Author of this module
Author = 'Microsoft Corporation'

# Script module or binary module file associated with this manifest.
RootModule = 'PSScriptAnalyzer.psm1'

# Version number of this module.
ModuleVersion = '1.6.1'

# ---
}
```

<span data-ttu-id="b7ff4-144">以下のロジックは、現在のエディションまたはバージョンに応じて必要なアセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-144">Below logic loads the required assemblies depending on the current edition or version.</span></span>

<span data-ttu-id="b7ff4-145">`PSScriptAnalyzer.psm1` ファイルの内容:</span><span class="sxs-lookup"><span data-stu-id="b7ff4-145">Contents of `PSScriptAnalyzer.psm1` file:</span></span>

```powershell
#
# Script module for module 'PSScriptAnalyzer'
#
Set-StrictMode -Version Latest

# Set up some helper variables to make it easier to work with the module
$PSModule = $ExecutionContext.SessionState.Module
$PSModuleRoot = $PSModule.ModuleBase

# Import the appropriate nested binary module based on the current PowerShell version
$binaryModuleRoot = $PSModuleRoot


if (($PSVersionTable.Keys -contains "PSEdition") -and ($PSVersionTable.PSEdition -ne 'Desktop')) {
    $binaryModuleRoot = Join-Path -Path $PSModuleRoot -ChildPath 'coreclr'
}
else
{
    if ($PSVersionTable.PSVersion -lt [Version]'5.0')
    {
        $binaryModuleRoot = Join-Path -Path $PSModuleRoot -ChildPath 'PSv3'
    }
}

$binaryModulePath = Join-Path -Path $binaryModuleRoot -ChildPath 'Microsoft.Windows.PowerShell.ScriptAnalyzer.dll'
$binaryModule = Import-Module -Name $binaryModulePath -PassThru

# When the module is unloaded, remove the nested binary module that was loaded with it
$PSModule.OnRemove = {
    Remove-Module -ModuleInfo $binaryModule
}
```

### <a name="option-2-use-psedition-variable-in-the-psd1-file-to-load-the-proper-dlls"></a><span data-ttu-id="b7ff4-146">オプション 2:PSD1 ファイルで $PSEdition 変数を使用して適切な DLL を読み込む</span><span class="sxs-lookup"><span data-stu-id="b7ff4-146">Option 2: Use $PSEdition variable in the PSD1 file to load the proper DLLs</span></span>

<span data-ttu-id="b7ff4-147">PS 5.1 以降では、`$PSEdition` グローバル変数をモジュール マニフェスト ファイル内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-147">In PS 5.1 or newer, `$PSEdition` global variable is allowed in the module manifest file.</span></span> <span data-ttu-id="b7ff4-148">この変数を使用すると、モジュールの作成者が、モジュール マニフェスト ファイル内で条件値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-148">Using this variable, module author can specify the conditional values in the module manifest file.</span></span> <span data-ttu-id="b7ff4-149">`$PSEdition` 変数は、制限された言語モードまたはデータ セクション内で参照できます。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-149">`$PSEdition` variable can be referenced in restricted language mode or a Data section.</span></span>

<span data-ttu-id="b7ff4-150">`CompatiblePSEditions` キーを持つサンプル モジュール マニフェスト ファイル。</span><span class="sxs-lookup"><span data-stu-id="b7ff4-150">Sample module manifest file with `CompatiblePSEditions` key.</span></span>

```powershell
@{
    # Script module or binary module file associated with this manifest.
    RootModule = if($PSEdition -eq 'Core')
    {
        'coreclr\MyCoreClrRM.dll'
    }
    else # Desktop
    {
        'clr\MyFullClrRM.dll'
    }

    # Supported PSEditions
    CompatiblePSEditions = 'Desktop', 'Core'

    # Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
    NestedModules = if($PSEdition -eq 'Core')
    {
        'coreclr\MyCoreClrNM1.dll',
        'coreclr\MyCoreClrNM2.dll'
    }
    else # Desktop
    {
        'clr\MyFullClrNM1.dll',
        'clr\MyFullClrNM2.dll'
    }
}
```

<span data-ttu-id="b7ff4-151">モジュールの内容</span><span class="sxs-lookup"><span data-stu-id="b7ff4-151">Module contents</span></span>

- <span data-ttu-id="b7ff4-152">ModuleWithEditions\ModuleWithEditions.psd1</span><span class="sxs-lookup"><span data-stu-id="b7ff4-152">ModuleWithEditions\ModuleWithEditions.psd1</span></span>
- <span data-ttu-id="b7ff4-153">ModuleWithEditions\clr\MyFullClrNM1.dll</span><span class="sxs-lookup"><span data-stu-id="b7ff4-153">ModuleWithEditions\clr\MyFullClrNM1.dll</span></span>
- <span data-ttu-id="b7ff4-154">ModuleWithEditions\clr\MyFullClrNM2.dll</span><span class="sxs-lookup"><span data-stu-id="b7ff4-154">ModuleWithEditions\clr\MyFullClrNM2.dll</span></span>
- <span data-ttu-id="b7ff4-155">ModuleWithEditions\clr\MyFullClrRM.dll</span><span class="sxs-lookup"><span data-stu-id="b7ff4-155">ModuleWithEditions\clr\MyFullClrRM.dll</span></span>
- <span data-ttu-id="b7ff4-156">ModuleWithEditions\coreclr\MyCoreClrNM1.dll</span><span class="sxs-lookup"><span data-stu-id="b7ff4-156">ModuleWithEditions\coreclr\MyCoreClrNM1.dll</span></span>
- <span data-ttu-id="b7ff4-157">ModuleWithEditions\coreclr\MyCoreClrNM2.dll</span><span class="sxs-lookup"><span data-stu-id="b7ff4-157">ModuleWithEditions\coreclr\MyCoreClrNM2.dll</span></span>
- <span data-ttu-id="b7ff4-158">ModuleWithEditions\coreclr\MyCoreClrRM.dll</span><span class="sxs-lookup"><span data-stu-id="b7ff4-158">ModuleWithEditions\coreclr\MyCoreClrRM.dll</span></span>

## <a name="more-details"></a><span data-ttu-id="b7ff4-159">詳細</span><span class="sxs-lookup"><span data-stu-id="b7ff4-159">More details</span></span>

[<span data-ttu-id="b7ff4-160">PSEditions のスクリプト</span><span class="sxs-lookup"><span data-stu-id="b7ff4-160">Scripts with PSEditions</span></span>](script-psedition-support.md)

[<span data-ttu-id="b7ff4-161">PowerShellGallery での PSEditions のサポート</span><span class="sxs-lookup"><span data-stu-id="b7ff4-161">PSEditions support on PowerShellGallery</span></span>](../how-to/finding-packages/searching-by-compatibility.md)

[<span data-ttu-id="b7ff4-162">モジュール マニフェストを更新する</span><span class="sxs-lookup"><span data-stu-id="b7ff4-162">Update module manifest</span></span>](/powershell/module/powershellget/update-modulemanifest)

<span data-ttu-id="b7ff4-163">[about_PowerShell_Editions][]</span><span class="sxs-lookup"><span data-stu-id="b7ff4-163">[about_PowerShell_Editions][]</span></span>

[about_PowerShell_Editions]: /powershell/module/Microsoft.PowerShell.Core/About/about_PowerShell_Editions
